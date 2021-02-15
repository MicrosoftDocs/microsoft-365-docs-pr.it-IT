---
title: Attivare o disattivare Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Informazioni su come accedere a Microsoft Bookings in Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126592"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Attivare o disattivare Microsoft Bookings

Bookings può essere attivato o disattivato per l'intera organizzazione o per utenti specifici. Quando si attiva Bookings per gli utenti, questi possono creare una pagina prenotazioni, creare un calendario e consentire ad altri utenti di prenotare tempo con loro.

> [!NOTE]
> I controlli di amministrazione descritti in queste sezioni non sono disponibili per i clienti di Office 365 Gestito da 21Vianet (Cina).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Attivare o disattivare Bookings per l'organizzazione tramite l'interfaccia di amministrazione di Microsoft 365

1. Accedere all'interfaccia di amministrazione di Microsoft 365 come amministratore globale.

2. Nell'interfaccia di amministrazione passare a  **Impostazioni**   \> **organizzazione e** selezionare **Prenotazioni.**

3. Selezionare la casella di controllo Consenti **all'organizzazione di usare Bookings** per abilitare o disabilitare Prenotazioni per l'organizzazione.

   > [!NOTE]
   > La disattivazione di Bookings disabiliterà tutti gli accessi al servizio, inclusa la creazione e la gestione delle pagine di Bookings.

4. Selezionare **Salva modifiche.**

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Attivare o disattivare Prenotazioni per l'organizzazione tramite PowerShell

Per attivare o disattivare Bookings per l'organizzazione utilizzando il cmdlet [PowerShell Set-OrganizationConfig,](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) ed eseguire il comando seguente:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Attivare o disattivare Prenotazioni per singoli utenti

È possibile disabilitare Prenotazioni per singoli utenti.

1. Passare all'interfaccia di amministrazione di Microsoft 365, quindi selezionare **Utenti** \> **attivi.**

1. Selezionare l'utente desiderato, quindi **selezionare Licenze e app.**

1. Espandi **App** e deseleziona la casella di controllo per Microsoft Bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Richiedere l'approvazione del personale prima di condividere le informazioni sulla disponibilità

Gli amministratori possono richiedere ai dipendenti dell'organizzazione di acconsentire esplicitamente prima che le informazioni sulla disponibilità siano condivise tramite Bookings e prima che possano essere prenotabili tramite una pagina di prenotazione. Questa impostazione è disponibile nell'interfaccia di  amministrazione di Microsoft 365 in \> **Impostazioni** \> **Prenotazioni.**

Quando questa impostazione è abilitata, i dipendenti aggiunti come personale nei calendari di prenotazione troveranno un collegamento Approva/Rifiuta nella notifica tramite posta elettronica che ricevono.

Questa funzionalità è in fase di implementazione graduale a livello mondiale per i clienti di Microsoft 365. Se questa opzione non viene visualizzata nell'interfaccia di amministrazione di Microsoft 365, tornare a breve.

## <a name="block-social-sharing-options"></a>Bloccare le opzioni di condivisione social network

Gli amministratori possono controllare la modalità di condivisione delle pagine di prenotazione nei social network. Questa impostazione è disponibile nell'interfaccia di  amministrazione di Microsoft 365 in \> **Impostazioni** \> **Prenotazioni.**

Questa funzionalità è in fase di implementazione graduale a livello mondiale per i clienti di Microsoft 365. Se questa opzione non viene visualizzata nell'interfaccia di amministrazione di Microsoft 365, tornare a breve.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Consenti solo agli utenti selezionati di creare calendari di Bookings

Utilizzando le restrizioni dei criteri, è possibile impedire agli utenti con licenza di creare calendari di Bookings. È innanzitutto necessario abilitare Bookings per l'intera organizzazione. Tutti gli utenti dell'organizzazione avranno licenze bookings, ma solo quelli inclusi nel criterio possono creare calendari di Bookings e avere il controllo completo su chi può accedere ai calendari creati.

Gli utenti inclusi in questo criterio possono creare nuovi calendari di Bookings e possono essere aggiunti come membri del personale in qualsiasi capacità (incluso il ruolo di amministratore) ai calendari di Bookings esistenti. Gli utenti che non sono inclusi in questo criterio non potranno creare nuovi calendari di Bookings e, se tentano di farlo, riceveranno un messaggio di errore.

È necessario eseguire i seguenti comandi utilizzando PowerShell di Exchange Online. Per ulteriori informazioni sull'esecuzione dei cmdlet di Exchange Online, vedere [Connettersi a PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

> [!IMPORTANT]
> I passaggi seguenti presuppongono che non siano stati creati altri criteri cassetta postale di Outlook Web App (OWA) nell'organizzazione.

1. Creare un nuovo criterio cassetta postale per gli utenti a cui consentire di creare calendari di Bookings. La creazione del calendario di Bookings è consentita per impostazione predefinita dai nuovi criteri cassetta postale.

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Per ulteriori informazioni, vedere [New-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)

2. Assegnare questo criterio agli utenti rilevanti eseguendo questo comando per ogni utente a cui si desidera concedere l'autorizzazione per la creazione di calendari di Bookings.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Per ulteriori informazioni, vedere [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).

3. Facoltativo: eseguire questo comando se si desidera disabilitare Prenotazioni per tutti gli altri utenti dell'organizzazione.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Per ulteriori informazioni, vedere [Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)

Per ulteriori informazioni sui criteri OWA cassetta postale, vedere i seguenti argomenti:

- [Creare un criterio cassetta postale di Outlook sul Web in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Applicare o rimuovere un criterio cassetta postale di Outlook sul Web su una cassetta postale in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
