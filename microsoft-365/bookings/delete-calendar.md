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
ms.openlocfilehash: 1f8df15eafac7867f7ae852e344e1c5730362598
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454206"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="f7f12-103">Eliminare un calendario delle prenotazioni in Bookings</span><span class="sxs-lookup"><span data-stu-id="f7f12-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="f7f12-104">Questo articolo spiega come eliminare un calendario delle prenotazioni indesiderato.</span><span class="sxs-lookup"><span data-stu-id="f7f12-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="f7f12-105">È possibile eliminare il calendario delle prenotazioni nell'interfaccia di amministrazione di Microsoft 365 oppure usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f7f12-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="f7f12-106">Il calendario di Bookings è una cassetta postale in Exchange Online in modo da eliminare l'account utente corrispondente per eliminare il calendario delle prenotazioni.</span><span class="sxs-lookup"><span data-stu-id="f7f12-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7f12-107">Tutti i calendari di prenotazione creati nel 2017 o prima devono essere eliminati usando le istruzioni di PowerShell in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f7f12-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="f7f12-108">Tutti i calendari di prenotazione creati nel 2018 o dopo possono essere eliminati nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f7f12-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="f7f12-109">Nel calendario di prenotazione sono archiviate tutte le informazioni rilevanti relative a tale calendario e dati di prenotazione, tra cui:</span><span class="sxs-lookup"><span data-stu-id="f7f12-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="f7f12-110">Informazioni aziendali, logo e orario di lavoro aggiunti al momento della creazione del calendario delle prenotazioni</span><span class="sxs-lookup"><span data-stu-id="f7f12-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="f7f12-111">Personale e servizi pertinenti aggiunti al momento della creazione del calendario delle prenotazioni</span><span class="sxs-lookup"><span data-stu-id="f7f12-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="f7f12-112">Tutte le prenotazioni e gli appuntamenti fuori servizio aggiunti al calendario delle prenotazioni dopo la sua creazione.</span><span class="sxs-lookup"><span data-stu-id="f7f12-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="f7f12-113">Una volta eliminato un calendario delle prenotazioni, anche queste informazioni aggiuntive vengono eliminate definitivamente e non possono essere recuperate.</span><span class="sxs-lookup"><span data-stu-id="f7f12-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f7f12-114">Eliminare un calendario delle prenotazioni nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f7f12-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="f7f12-115">Passare all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f7f12-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="f7f12-116">Nell'interfaccia di amministrazione selezionare **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="f7f12-116">In the Admin center, select **Users**.</span></span>

   ![Immagine dell'interfaccia utente degli utenti nell'interfaccia di amministrazione di Microsoft 365](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="f7f12-118">Nella pagina **Utenti attivi** scegliere i nomi degli utenti da eliminare, quindi selezionare **Elimina utente**.</span><span class="sxs-lookup"><span data-stu-id="f7f12-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Immagine dell'interfaccia utente Elimina utente nell'interfaccia di amministrazione di Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="f7f12-120">Eliminare un calendario delle prenotazioni tramite PowerShell di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f7f12-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="f7f12-121">Vedere [Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) per i prerequisiti e le indicazioni per la connessione a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f7f12-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="f7f12-122">Per eseguire questi passaggi, è necessario utilizzare una finestra di comando attiva di Microsoft PowerShell eseguita scegliendo l'opzione "Esegui come amministratore".</span><span class="sxs-lookup"><span data-stu-id="f7f12-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="f7f12-123">In una finestra di PowerShell caricare il modulo EXO V2 eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f7f12-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="f7f12-124">Se si è già [installato il modulo EXO V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), il comando precedente funzionerà come descritto.</span><span class="sxs-lookup"><span data-stu-id="f7f12-124">If you've already [installed the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="f7f12-125">Il comando da eseguire utilizza la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f7f12-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="f7f12-126">_\<UPN\>_ è il proprio account in formato del nome dell'entità utente, (ad esempio `john@contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="f7f12-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="f7f12-127">Quando richiesto, accedere con le credenziali di amministratore tenant al tenant di Microsoft 365 che ospita il calendario delle prenotazioni che si desidera eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="f7f12-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="f7f12-128">Terminata l'elaborazione di questo comando, immettere il comando seguente per ottenere un elenco delle cassette postali delle prenotazioni nel tenant:</span><span class="sxs-lookup"><span data-stu-id="f7f12-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

5. <span data-ttu-id="f7f12-129">Digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f7f12-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="f7f12-130">Prestare attenzione a digitare il nome esatto dell'alias della cassetta postale di prenotazione che si desidera eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="f7f12-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="f7f12-131">Per verificare che il calendario sia stato eliminato, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f7f12-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="f7f12-132">Il calendario eliminato non verrà visualizzato nell'output.</span><span class="sxs-lookup"><span data-stu-id="f7f12-132">The deleted calendar will not appear in the output.</span></span>
