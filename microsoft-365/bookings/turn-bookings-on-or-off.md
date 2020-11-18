---
title: Attivazione o disattivazione delle prenotazioni Microsoft
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Informazioni su come accedere a Microsoft bookings in Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126592"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Attivazione o disattivazione delle prenotazioni Microsoft

Le prenotazioni possono essere attivate o disattivate per l'intera organizzazione o per utenti specifici. Quando si attivano le prenotazioni per gli utenti, è possibile creare una pagina di prenotazione, creare un calendario e consentire ad altre persone di prenotare tempo con loro.

> [!NOTE]
> I controlli di amministratore descritti in queste sezioni non sono disponibili per Office 365 gestito da clienti di 21Vianet (Cina).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Attivazione o disattivazione delle prenotazioni per la propria organizzazione tramite l'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di amministrazione di Microsoft 365 come amministratore globale.

2. Nell'interfaccia di amministrazione, passare a  **Settings** impostazioni   \> **org** impostazioni e selezionare **prenotazioni**.

3. Selezionare la casella di controllo per **consentire all'organizzazione di utilizzare le prenotazioni** per abilitare o disabilitare le prenotazioni per la propria organizzazione.

   > [!NOTE]
   > La disattivazione delle prenotazioni disattiverà tutti gli accessi al servizio, inclusa la creazione e la gestione delle pagine di prenotazione.

4. Selezionare **Salva modifiche**.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Attivazione o disattivazione delle prenotazioni per la propria organizzazione tramite PowerShell

Per abilitare o disabilitare le prenotazioni per l'organizzazione utilizzando il cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)di PowerShell, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) ed eseguire il comando riportato di seguito:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Attivazione o disattivazione delle prenotazioni per singoli utenti

È possibile disabilitare le prenotazioni per singoli utenti.

1. Accedere all'interfaccia di amministrazione di Microsoft 365, quindi **selezionare utenti** \> **attivi**.

1. Selezionare l'utente desiderato, quindi selezionare **licenze e app**.

1. Espandi le **app** e deseleziona la casella di controllo per Microsoft bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Richiedi approvazione del personale prima della condivisione delle informazioni sulla disponibilità

Gli amministratori possono richiedere ai dipendenti dell'organizzazione l'opt-in prima che le informazioni sulla disponibilità siano condivise tramite le prenotazioni e prima che possano essere prenotabili tramite una pagina di prenotazione. Questa impostazione è disponibile nell'interfaccia di amministrazione di Microsoft 365 **Settings** nelle \> **Settings** \> **prenotazioni** delle impostazioni delle impostazioni.

Quando questa impostazione è abilitata, i dipendenti aggiunti come personale nei calendari di prenotazione troveranno un collegamento Approva/Rifiuta nella notifica di posta elettronica che ricevono.

Questa funzionalità è gradualmente distribuita a livello mondiale nei clienti di Microsoft 365. Se questa opzione non è disponibile nell'interfaccia di amministrazione di Microsoft 365, eseguire il controllo di nuovo a breve.

## <a name="block-social-sharing-options"></a>Bloccare le opzioni di condivisione sociale

Gli amministratori possono controllare il modo in cui le pagine di prenotazione sono condivise sui social network. Questa impostazione è disponibile nell'interfaccia di amministrazione di Microsoft 365 **Settings** nelle \> **Settings** \> **prenotazioni** delle impostazioni delle impostazioni.

Questa funzionalità è gradualmente distribuita a livello mondiale nei clienti di Microsoft 365. Se questa opzione non è disponibile nell'interfaccia di amministrazione di Microsoft 365, eseguire il controllo di nuovo a breve.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Consenti solo agli utenti selezionati di creare calendari di prenotazione

Se si utilizzano restrizioni ai criteri, è possibile limitare gli utenti autorizzati a creare calendari di prenotazione. Prima di tutto, è necessario abilitare le prenotazioni per l'intera organizzazione. Tutti gli utenti dell'organizzazione disporranno delle licenze di prenotazione, ma solo quelle incluse nel criterio possono creare calendari di prenotazione e avere il controllo completo su chi può accedere ai calendari creati.

Gli utenti inclusi in questo criterio possono creare nuovi calendari di prenotazione e possono essere aggiunti come membri del personale in qualsiasi capacità (incluso il ruolo di amministratore) ai calendari delle prenotazioni esistenti. Gli utenti che non sono inclusi in questo criterio non saranno in grado di creare nuovi calendari di prenotazione e riceveranno un messaggio di errore se si tenta di eseguire questa operazione.

È necessario eseguire i comandi seguenti usando PowerShell di Exchange Online. Per ulteriori informazioni sull'esecuzione dei cmdlet di Exchange Online, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> Nella procedura riportata di seguito si presuppone che non siano stati creati altri criteri cassetta postale di Outlook Web App (OWA) nell'organizzazione.

1. Creare un nuovo criterio cassetta postale per gli utenti che devono essere autorizzati a creare calendari di prenotazione. (La creazione del calendario delle prenotazioni è consentita per impostazione predefinita dai nuovi criteri cassetta postale).

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Per ulteriori informazioni, vedere [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).

2. Assegnare questo criterio agli utenti rilevanti eseguendo questo comando per ogni utente che si desidera concedere l'autorizzazione per creare calendari di prenotazione.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Per ulteriori informazioni, vedere [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).

3. Facoltativo: eseguire questo comando se si desidera disabilitare le prenotazioni per tutti gli altri utenti dell'organizzazione.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Per ulteriori informazioni, vedere [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).

Per ulteriori informazioni sui criteri cassetta postale di OWA, vedere gli argomenti seguenti:

- [Creare un criterio cassetta postale di Outlook sul Web in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Applicare o rimuovere un criterio cassetta postale di Outlook sul Web in una cassetta postale in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
