---
title: Eliminare un calendario delle prenotazioni
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Utilizzare il interfaccia di amministrazione di Microsoft 365 o Windows PowerShell per eliminare i calendari di Bookings.
ms.openlocfilehash: 1ef67ce4dbf67da6f081106815f76ff85f11ef92
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288444"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Eliminare un calendario delle prenotazioni in Bookings

Questo articolo spiega come eliminare un calendario di prenotazione indesiderato. È possibile eliminare il calendario di prenotazione nell interfaccia di amministrazione di Microsoft 365 oppure è possibile usare PowerShell. Il calendario bookings è una cassetta postale in Exchange Online in modo da eliminare l'account utente corrispondente per eliminare il calendario di prenotazione.

> [!IMPORTANT]
> Tutti i calendari di prenotazione creati nella versione 2017 o precedente devono essere eliminati usando le istruzioni di PowerShell in questo argomento. Tutti i calendari di prenotazione creati nel 2018 o dopo possono essere eliminati nella interfaccia di amministrazione di Microsoft 365.

Il calendario di prenotazione è il luogo in cui vengono archiviate tutte le informazioni pertinenti sul calendario e i dati della prenotazione, tra cui:

- Informazioni aziendali, logo e ore lavorative aggiunte al momento della creazione del calendario della prenotazione
- Personale e servizi rilevanti aggiunti al momento della creazione del calendario di prenotazione
- Tutte le prenotazioni e gli appuntamenti fuori servizio aggiunti al calendario di prenotazione dopo la sua creazione.

> [!WARNING]
> Una volta eliminato un calendario di prenotazione, anche queste informazioni aggiuntive vengono eliminate definitivamente e non possono essere recuperate.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Eliminare un calendario di prenotazione nella interfaccia di amministrazione di Microsoft 365

1. Passare all'interfaccia di amministrazione di Microsoft 365.

1. Nell'interfaccia di amministrazione selezionare **Utenti**.

   ![Immagine dell'interfaccia utente degli utenti in interfaccia di amministrazione di Microsoft 365](../media/bookings-admin-center-users.png)

1. Nella pagina **Utenti attivi** scegliere i nomi degli utenti da eliminare, quindi selezionare **Elimina utente**.

   ![Immagine dell'interfaccia utente di eliminazione in interfaccia di amministrazione di Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Eliminare un calendario di prenotazione Exchange Online PowerShell

Vedere [Connessione per Exchange Online PowerShell per](/powershell/exchange/exchange-online-powershell-v2) prerequisiti e indicazioni per la connessione a Exchange Online PowerShell.

Per eseguire questi passaggi, è necessario utilizzare una finestra di comando attiva di Microsoft PowerShell eseguita scegliendo l'opzione "Esegui come amministratore".

1. In una finestra di PowerShell caricare il modulo EXO V2 eseguendo il comando seguente:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > Se si è già [installato il modulo EXO V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module), il comando precedente funzionerà come descritto.
   
2. Il comando da eseguire utilizza la sintassi seguente:

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - _\<UPN\>_ è il proprio account in formato del nome dell'entità utente, (ad esempio `john@contoso.com`).

3. Quando richiesto, accedere con le credenziali di amministratore tenant al tenant Microsoft 365 che ospita il calendario di prenotazione che si desidera eliminare definitivamente.

4. Terminata l'elaborazione di questo comando, immettere il comando seguente per ottenere un elenco delle cassette postali delle prenotazioni nel tenant:

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. Digitare il comando seguente:

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Fare attenzione a digitare il nome esatto dell'alias della cassetta postale di prenotazione che si desidera eliminare definitivamente.

6. Per verificare che il calendario sia stato eliminato, immettere il comando seguente:

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   Il calendario eliminato non verrà visualizzato nell'output.
