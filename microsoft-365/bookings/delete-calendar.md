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
ms.openlocfilehash: 3a1cb1c54f60247ab72056b3e39b56b0981228b7
ms.sourcegitcommit: eb3c30d53a5434d8bad7c8f48a5612f3e2675945
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422443"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="cb501-103">Eliminare un calendario di prenotazione nelle prenotazioni</span><span class="sxs-lookup"><span data-stu-id="cb501-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="cb501-104">In questo articolo viene illustrato come eliminare un calendario di prenotazione indesiderato.</span><span class="sxs-lookup"><span data-stu-id="cb501-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="cb501-105">È possibile eliminare il calendario delle prenotazioni nell'interfaccia di amministrazione di Microsoft 365 oppure è possibile utilizzare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb501-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="cb501-106">Il calendario delle prenotazioni è una cassetta postale in Exchange online in modo da eliminare l'account utente corrispondente per eliminare il calendario di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="cb501-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb501-107">Tutti i calendari di prenotazione creati in 2017 o prima devono essere eliminati utilizzando le istruzioni di PowerShell su questo argomento.</span><span class="sxs-lookup"><span data-stu-id="cb501-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="cb501-108">Tutti i calendari di prenotazione creati in 2018 o dopo possono essere eliminati nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb501-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="cb501-109">Il calendario di prenotazione è il luogo in cui vengono archiviate tutte le informazioni rilevanti relative al calendario e ai dati di prenotazione, tra cui:</span><span class="sxs-lookup"><span data-stu-id="cb501-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="cb501-110">Informazioni aziendali, logo e ore lavorative aggiunte quando è stato creato il calendario di prenotazione</span><span class="sxs-lookup"><span data-stu-id="cb501-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="cb501-111">Personale e servizi rilevanti aggiunti al momento della creazione del calendario di prenotazione</span><span class="sxs-lookup"><span data-stu-id="cb501-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="cb501-112">Tutte le prenotazioni e gli appuntamenti disattivati sono stati aggiunti al calendario di prenotazione dopo la sua creazione.</span><span class="sxs-lookup"><span data-stu-id="cb501-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="cb501-113">Dopo l'eliminazione di un calendario di prenotazione, anche queste informazioni aggiuntive vengono eliminate definitivamente e non possono essere recuperate.</span><span class="sxs-lookup"><span data-stu-id="cb501-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="cb501-114">Eliminare un calendario di prenotazione nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb501-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="cb501-115">Passare all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb501-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="cb501-116">Nell'interfaccia di amministrazione selezionare **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="cb501-116">In the Admin center, select **Users**.</span></span>

   ![Immagine dell'interfaccia utente degli utenti in Microsoft 365 Admin Center](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="cb501-118">Nella pagina **Utenti attivi** scegliere i nomi degli utenti da eliminare, quindi selezionare **Elimina utente**.</span><span class="sxs-lookup"><span data-stu-id="cb501-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Immagine di Delete User UI in Microsoft 365 Admin Center](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="cb501-120">Eliminare un calendario di prenotazione tramite Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb501-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="cb501-121">Per informazioni sui prerequisiti e le linee guida per la connessione a PowerShell di Exchange Online, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) .</span><span class="sxs-lookup"><span data-stu-id="cb501-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="cb501-122">Per eseguire questa procedura, è necessario utilizzare una finestra di comando di Microsoft PowerShell attiva scegliendo l'opzione "Esegui come amministratore".</span><span class="sxs-lookup"><span data-stu-id="cb501-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="cb501-123">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cb501-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="cb501-124">Quando viene richiesto, eseguire l'accesso con le credenziali di amministratore tenant al tenant di Microsoft 365 che ospita il calendario di prenotazione che si desidera eliminare in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="cb501-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="cb501-125">Al prompt dei comandi di PowerShell, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cb501-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="cb501-126">Immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cb501-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="cb501-127">Terminata l'elaborazione di questo comando, immettere il comando seguente per ottenere un elenco delle cassette postali delle prenotazioni nel tenant:</span><span class="sxs-lookup"><span data-stu-id="cb501-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="cb501-128">Digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cb501-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="cb501-129">Fare attenzione a digitare il nome esatto dell'alias della cassetta postale di prenotazione che si desidera eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="cb501-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="cb501-130">Per verificare che il calendario sia stato eliminato, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cb501-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="cb501-131">Il calendario eliminato non verrà visualizzato nell'output.</span><span class="sxs-lookup"><span data-stu-id="cb501-131">The deleted calendar will not appear in the output.</span></span>
