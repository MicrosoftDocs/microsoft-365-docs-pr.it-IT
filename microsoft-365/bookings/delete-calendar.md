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
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="1a5d5-103">Eliminare un calendario delle prenotazioni in Bookings</span><span class="sxs-lookup"><span data-stu-id="1a5d5-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="1a5d5-104">Questo articolo spiega come eliminare un calendario di prenotazione indesiderato.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="1a5d5-105">È possibile eliminare il calendario di prenotazione nell interfaccia di amministrazione di Microsoft 365 oppure è possibile usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="1a5d5-106">Il calendario bookings è una cassetta postale in Exchange Online in modo da eliminare l'account utente corrispondente per eliminare il calendario di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a5d5-107">Tutti i calendari di prenotazione creati nella versione 2017 o precedente devono essere eliminati usando le istruzioni di PowerShell in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="1a5d5-108">Tutti i calendari di prenotazione creati nel 2018 o dopo possono essere eliminati nella interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="1a5d5-109">Il calendario di prenotazione è il luogo in cui vengono archiviate tutte le informazioni pertinenti sul calendario e i dati della prenotazione, tra cui:</span><span class="sxs-lookup"><span data-stu-id="1a5d5-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="1a5d5-110">Informazioni aziendali, logo e ore lavorative aggiunte al momento della creazione del calendario della prenotazione</span><span class="sxs-lookup"><span data-stu-id="1a5d5-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="1a5d5-111">Personale e servizi rilevanti aggiunti al momento della creazione del calendario di prenotazione</span><span class="sxs-lookup"><span data-stu-id="1a5d5-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="1a5d5-112">Tutte le prenotazioni e gli appuntamenti fuori servizio aggiunti al calendario di prenotazione dopo la sua creazione.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="1a5d5-113">Una volta eliminato un calendario di prenotazione, anche queste informazioni aggiuntive vengono eliminate definitivamente e non possono essere recuperate.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1a5d5-114">Eliminare un calendario di prenotazione nella interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a5d5-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="1a5d5-115">Passare all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="1a5d5-116">Nell'interfaccia di amministrazione selezionare **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-116">In the Admin center, select **Users**.</span></span>

   ![Immagine dell'interfaccia utente degli utenti in interfaccia di amministrazione di Microsoft 365](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="1a5d5-118">Nella pagina **Utenti attivi** scegliere i nomi degli utenti da eliminare, quindi selezionare **Elimina utente**.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Immagine dell'interfaccia utente di eliminazione in interfaccia di amministrazione di Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="1a5d5-120">Eliminare un calendario di prenotazione Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a5d5-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="1a5d5-121">Vedere [Connessione per Exchange Online PowerShell per](/powershell/exchange/exchange-online-powershell-v2) prerequisiti e indicazioni per la connessione a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-121">See [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="1a5d5-122">Per eseguire questi passaggi, è necessario utilizzare una finestra di comando attiva di Microsoft PowerShell eseguita scegliendo l'opzione "Esegui come amministratore".</span><span class="sxs-lookup"><span data-stu-id="1a5d5-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="1a5d5-123">In una finestra di PowerShell caricare il modulo EXO V2 eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1a5d5-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="1a5d5-124">Se si è già [installato il modulo EXO V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module), il comando precedente funzionerà come descritto.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-124">If you've already [installed the EXO V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="1a5d5-125">Il comando da eseguire utilizza la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="1a5d5-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="1a5d5-126">_\<UPN\>_ è il proprio account in formato del nome dell'entità utente, (ad esempio `john@contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="1a5d5-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="1a5d5-127">Quando richiesto, accedere con le credenziali di amministratore tenant al tenant Microsoft 365 che ospita il calendario di prenotazione che si desidera eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="1a5d5-128">Terminata l'elaborazione di questo comando, immettere il comando seguente per ottenere un elenco delle cassette postali delle prenotazioni nel tenant:</span><span class="sxs-lookup"><span data-stu-id="1a5d5-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. <span data-ttu-id="1a5d5-129">Digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1a5d5-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="1a5d5-130">Fare attenzione a digitare il nome esatto dell'alias della cassetta postale di prenotazione che si desidera eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="1a5d5-131">Per verificare che il calendario sia stato eliminato, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1a5d5-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   <span data-ttu-id="1a5d5-132">Il calendario eliminato non verrà visualizzato nell'output.</span><span class="sxs-lookup"><span data-stu-id="1a5d5-132">The deleted calendar will not appear in the output.</span></span>
