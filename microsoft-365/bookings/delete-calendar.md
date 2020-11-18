---
title: Eliminare un calendario di prenotazione
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Utilizzare l'interfaccia di amministrazione di Microsoft 365 o Windows PowerShell per eliminare i calendari delle prenotazioni.
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126650"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Eliminare un calendario di prenotazione nelle prenotazioni

In questo articolo viene illustrato come eliminare un calendario di prenotazione indesiderato. È possibile eliminare il calendario delle prenotazioni nell'interfaccia di amministrazione di Microsoft 365 oppure è possibile utilizzare PowerShell. Il calendario delle prenotazioni è una cassetta postale in Exchange online in modo da eliminare l'account utente corrispondente per eliminare il calendario di prenotazione.

> [!IMPORTANT]
> Tutti i calendari di prenotazione creati in 2017 o prima devono essere eliminati utilizzando le istruzioni di PowerShell su questo argomento. Tutti i calendari di prenotazione creati in 2018 o dopo possono essere eliminati nell'interfaccia di amministrazione di Microsoft 365.

Il calendario di prenotazione è il luogo in cui vengono archiviate tutte le informazioni rilevanti relative al calendario e ai dati di prenotazione, tra cui:

- Informazioni aziendali, logo e ore lavorative aggiunte quando è stato creato il calendario di prenotazione
- Personale e servizi rilevanti aggiunti al momento della creazione del calendario di prenotazione
- Tutte le prenotazioni e gli appuntamenti disattivati sono stati aggiunti al calendario di prenotazione dopo la sua creazione.

> [!WARNING]
> Dopo l'eliminazione di un calendario di prenotazione, anche queste informazioni aggiuntive vengono eliminate definitivamente e non possono essere recuperate.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Eliminare un calendario di prenotazione nell'interfaccia di amministrazione di Microsoft 365

1. Passare all'interfaccia di amministrazione di Microsoft 365.

1. Nell'interfaccia di amministrazione selezionare **Utenti**.

   ![Immagine dell'interfaccia utente degli utenti in Microsoft 365 Admin Center](../media/bookings-admin-center-users.png)

1. Nella pagina **Utenti attivi** scegliere i nomi degli utenti da eliminare, quindi selezionare **Elimina utente**.

   ![Immagine di Delete User UI in Microsoft 365 Admin Center](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Eliminare un calendario di prenotazione tramite Exchange Online PowerShell

Per informazioni sui prerequisiti e le linee guida per la connessione a PowerShell di Exchange Online, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) .

Per eseguire questa procedura, è necessario utilizzare una finestra di comando di Microsoft PowerShell attiva scegliendo l'opzione "Esegui come amministratore".

1. Immettere il comando seguente:

   ```PowerShell
    $user = get-credential
   ```

1. Quando viene richiesto, eseguire l'accesso con le credenziali di amministratore tenant al tenant di Microsoft 365 che ospita il calendario di prenotazione che si desidera eliminare in modo definitivo.

1. Al prompt dei comandi di PowerShell, immettere il comando seguente:

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. Immettere il comando seguente:

   ```PowerShell
    Import-PSSession $s
   ```

1. Terminata l'elaborazione di questo comando, immettere il comando seguente per ottenere un elenco delle cassette postali delle prenotazioni nel tenant:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. Digitare il comando seguente:

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Fare attenzione a digitare il nome esatto dell'alias della cassetta postale di prenotazione che si desidera eliminare definitivamente.

1. Per verificare che il calendario sia stato eliminato, immettere il comando seguente:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   Il calendario eliminato non verrà visualizzato nell'output.
