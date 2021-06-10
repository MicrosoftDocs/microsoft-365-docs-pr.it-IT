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
description: Scopri come accedere a Microsoft Bookings in Microsoft 365.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913767"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Attivare o disattivare Microsoft Bookings

Le prenotazioni possono essere attivate o disattivate per l'intera organizzazione o per utenti specifici. Quando attivi Bookings per gli utenti, può creare una pagina Prenotazioni, creare un calendario e consentire ad altre persone di prenotare tempo con loro.

> [!NOTE]
> I controlli di amministrazione descritti in queste sezioni non sono disponibili per Office 365 clienti gestiti da 21Vianet (Cina).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Attivare o disattivare Bookings per l'organizzazione tramite l'Microsoft 365 di amministrazione

1. Accedi all'Microsoft 365 di amministrazione come amministratore globale.

2. Nell'interfaccia di amministrazione passare a  **Impostazioni**   \> **organizzazione Impostazioni** e selezionare **Prenotazioni**.

3. Seleziona la casella di controllo **Consenti all'organizzazione di usare Bookings** per abilitare o disabilitare Bookings per l'organizzazione.

   > [!NOTE]
   > La disattivazione di Bookings disabiliterà tutti gli accessi al servizio, inclusa la creazione e la gestione delle pagine di Bookings.

4. Selezionare **Salva modifiche**.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Attivare o disattivare Bookings per l'organizzazione tramite PowerShell

Per attivare o disattivare Bookings per l'organizzazione utilizzando il cmdlet [PowerShell Set-OrganizationConfig,](/powershell/module/exchange/set-organizationconfig)Connessione per Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) ed eseguire il comando seguente:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Attivare o disattivare Prenotazioni per singoli utenti

È possibile disabilitare Bookings per singoli utenti.

1. Passare all'Microsoft 365 di amministrazione, quindi selezionare **Utenti** \> **Utenti attivi**.

1. Seleziona l'utente desiderato, quindi **seleziona Licenze e app.**

1. Espandi **App** e deseleziona la casella di controllo per Microsoft Bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Richiedere l'approvazione del personale prima di condividere le informazioni sulla disponibilità

Gli amministratori possono richiedere ai dipendenti dell'organizzazione di acconsentire esplicitamente prima che le informazioni sulla disponibilità siano condivise tramite Bookings e prima che possano essere prenotabili tramite una pagina di prenotazione. Questa impostazione è disponibile nell'interfaccia Microsoft 365 di amministrazione in **Impostazioni** \> **Impostazioni** \> **Bookings**.

Quando questa impostazione è abilitata, i dipendenti aggiunti come personale nei calendari di prenotazione troveranno un collegamento Approva/Rifiuta nella notifica di posta elettronica che ricevono.

Questa funzionalità viene gradualmente ampliata a livello mondiale per Microsoft 365 clienti. Se questa opzione non è disponibile nell'interfaccia Microsoft 365, tornare presto.

## <a name="block-social-sharing-options"></a>Bloccare le opzioni di condivisione di social network

Gli amministratori possono controllare la modalità di condivisione delle pagine di prenotazione sui social network. Questa impostazione è disponibile nell'interfaccia Microsoft 365 di amministrazione in **Impostazioni** \> **Impostazioni** \> **Bookings**.

Questa funzionalità viene gradualmente ampliata a livello mondiale per Microsoft 365 clienti. Se questa opzione non è disponibile nell'interfaccia Microsoft 365, tornare presto.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Consenti solo agli utenti selezionati di creare calendari di Bookings

Utilizzando le restrizioni dei criteri, è possibile impedire agli utenti con licenza di creare calendari di Bookings. È innanzitutto necessario abilitare Bookings per l'intera organizzazione. Tutti gli utenti dell'organizzazione avranno licenze Bookings, ma solo quelli inclusi nel criterio possono creare calendari di Bookings e avere il controllo completo su chi può accedere ai calendari creati.

Gli utenti inclusi in questo criterio possono creare nuovi calendari di Bookings e possono essere aggiunti come personale in qualsiasi capacità (incluso il ruolo di amministratore) ai calendari esistenti di Bookings. Gli utenti che non sono inclusi in questo criterio non potranno creare nuovi calendari di Bookings e riceveranno un messaggio di errore se tentano di farlo.

Dovrai eseguire i comandi seguenti usando Exchange Online PowerShell. Per ulteriori informazioni sull'esecuzione Exchange Online cmdlet, [vedere Connessione to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> I passaggi seguenti presuppongono che non siano stati creati altri Outlook Web App (OWA) nell'organizzazione.

1. Creare un nuovo criterio cassetta postale per gli utenti a cui dovrebbe essere consentito creare calendari di Bookings. La creazione del calendario bookings è consentita per impostazione predefinita dai nuovi criteri cassetta postale.

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Per ulteriori informazioni, vedere [New-OwaMailboxPolicy.](/powershell/module/exchange/new-owamailboxpolicy)

2. Assegnare questo criterio agli utenti rilevanti eseguendo questo comando per ogni utente a cui si desidera concedere l'autorizzazione per la creazione di calendari di Bookings.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Per ulteriori informazioni, vedere [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).

3. Facoltativo: eseguire questo comando se si desidera disabilitare Bookings per tutti gli altri utenti dell'organizzazione.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Per ulteriori informazioni, vedere [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).

Per ulteriori informazioni sui criteri OWA cassetta postale, vedere i seguenti argomenti:

- [Creare un Outlook sul criterio cassetta postale Web in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Applicare o rimuovere un Outlook sul criterio cassetta postale Web in una cassetta postale in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)