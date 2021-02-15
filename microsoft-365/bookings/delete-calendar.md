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
description: Usare l'interfaccia di amministrazione di Microsoft 365 o Windows PowerShell per eliminare i calendari di Bookings.
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126650"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Eliminare un calendario delle prenotazioni in Bookings

Questo articolo spiega come eliminare un calendario di prenotazione indesiderato. È possibile eliminare il calendario delle prenotazioni nell'interfaccia di amministrazione di Microsoft 365 oppure usare PowerShell. Il calendario di Bookings è una cassetta postale in Exchange Online in modo da eliminare l'account utente corrispondente per eliminare il calendario delle prenotazioni.

> [!IMPORTANT]
> Tutti i calendari di prenotazione creati nel 2017 o prima devono essere eliminati usando le istruzioni di PowerShell in questo argomento. Tutti i calendari di prenotazione creati nel 2018 o dopo possono essere eliminati nell'interfaccia di amministrazione di Microsoft 365.

Nel calendario di prenotazione sono archiviate tutte le informazioni rilevanti relative a tale calendario e dati di prenotazione, tra cui:

- Informazioni aziendali, logo e orario di lavoro aggiunti al momento della creazione del calendario delle prenotazioni
- Personale e servizi pertinenti aggiunti al momento della creazione del calendario delle prenotazioni
- Tutte le prenotazioni e gli appuntamenti fuori servizio aggiunti al calendario delle prenotazioni dopo la sua creazione.

> [!WARNING]
> Una volta eliminato un calendario delle prenotazioni, anche queste informazioni aggiuntive vengono eliminate definitivamente e non possono essere recuperate.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Eliminare un calendario delle prenotazioni nell'interfaccia di amministrazione di Microsoft 365

1. Passare all'interfaccia di amministrazione di Microsoft 365.

1. Nell'interfaccia di amministrazione selezionare **Utenti**.

   ![Immagine dell'interfaccia utente degli utenti nell'interfaccia di amministrazione di Microsoft 365](../media/bookings-admin-center-users.png)

1. Nella pagina **Utenti attivi** scegliere i nomi degli utenti da eliminare, quindi selezionare **Elimina utente**.

   ![Immagine dell'interfaccia utente Elimina utente nell'interfaccia di amministrazione di Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Eliminare un calendario delle prenotazioni tramite PowerShell di Exchange Online

Vedere [Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) per i prerequisiti e le indicazioni per la connessione a PowerShell di Exchange Online.

Per eseguire questa procedura, è necessario utilizzare una finestra di comando attiva di Microsoft PowerShell eseguita scegliendo l'opzione "Esegui come amministratore".

1. Immettere il comando seguente:

   ```PowerShell
    $user = get-credential
   ```

1. Quando richiesto, accedere con le credenziali di amministratore tenant al tenant di Microsoft 365 che ospita il calendario delle prenotazioni che si desidera eliminare definitivamente.

1. Al prompt dei comandi di PowerShell immettere questo comando:

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
   > Prestare attenzione a digitare il nome esatto dell'alias della cassetta postale di prenotazione che si desidera eliminare definitivamente.

1. Per verificare che il calendario sia stato eliminato, immettere il comando seguente:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   Il calendario eliminato non verrà visualizzato nell'output.
