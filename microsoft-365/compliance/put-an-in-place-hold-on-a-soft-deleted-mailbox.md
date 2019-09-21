---
title: Inserire un blocco sul posto di una cassetta postale eliminata in modo reversibile in Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: Informazioni su come creare un blocco sul posto per una cassetta postale eliminata temporaneamente per renderla inattiva e conservarne il contenuto. È quindi possibile utilizzare gli strumenti di Microsoft eDiscovery per cercare la cassetta postale inattiva.
ms.openlocfilehash: ce4121e6187a765b5a9e23d6e6e11d8cc2640161
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084403"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="357ed-104">Inserire un blocco sul posto di una cassetta postale eliminata in modo reversibile in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="357ed-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="357ed-105">Informazioni su come creare un blocco sul posto per una cassetta postale eliminata temporaneamente per renderla inattiva e conservarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="357ed-105">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="357ed-106">È quindi possibile utilizzare gli strumenti di Microsoft eDiscovery per cercare la cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="357ed-106">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>
  
> [!NOTE]
> <span data-ttu-id="357ed-107">È stata posticipata la data di scadenza per la creazione di nuove archiviazioni sul posto in Exchange Online (nei piani autonomi di Office 365 e Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="357ed-107">We've postponed the deadline for creating new In-Place Holds in Exchange Online (in Office 365 and Exchange Online standalone plans).</span></span> <span data-ttu-id="357ed-108">Tuttavia, più avanti nel corso di questo anno o all'inizio del prossimo, non sarà più possibile creare blocchi sul posto in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="357ed-108">But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="357ed-109">In alternativa all'utilizzo delle archiviazioni sul posto, è possibile utilizzare i criteri di [conservazione](https://go.microsoft.com/fwlink/?linkid=827811) o i [casi di eDiscovery](https://go.microsoft.com/fwlink/?linkid=780738) nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="357ed-109">As an alternative to using In-Place Holds, you can use [eDiscovery cases](https://go.microsoft.com/fwlink/?linkid=780738) or [retention policies](https://go.microsoft.com/fwlink/?linkid=827811) in the Security & Compliance Center.</span></span> <span data-ttu-id="357ed-110">Dopo la rimozione di nuove esenzioni sul posto, sarà comunque possibile modificare le esenzioni sul posto esistenti e creare nuove archiviazioni sul posto in Exchange Server 2013 e le distribuzioni ibride di Exchange continueranno a essere supportate.</span><span class="sxs-lookup"><span data-stu-id="357ed-110">After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported.</span></span> <span data-ttu-id="357ed-111">Inoltre, sarà ancora possibile applicare un blocco per controversia legale alle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="357ed-111">And, you'll still be able to place mailboxes on Litigation Hold.</span></span> 
  
<span data-ttu-id="357ed-112">Potrebbe verificarsi una situazione in cui una persona ha lasciato la propria organizzazione e l'account utente e la cassetta postale corrispondenti sono stati eliminati.</span><span class="sxs-lookup"><span data-stu-id="357ed-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="357ed-113">Successivamente, si rende conto che esistono informazioni nella cassetta postale che devono essere conservate.</span><span class="sxs-lookup"><span data-stu-id="357ed-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="357ed-114">Cosa potete fare?</span><span class="sxs-lookup"><span data-stu-id="357ed-114">What can you do?</span></span> <span data-ttu-id="357ed-115">Se il periodo di conservazione della cassetta postale eliminata non è scaduto, è possibile applicare un blocco sul posto alla cassetta postale eliminata (denominata cassetta postale eliminata temporaneamente) e renderla una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="357ed-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="357ed-116">Una *cassetta postale inattiva* viene utilizzata per mantenere la posta elettronica di un ex dipendente dopo che lui o lei lascia l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="357ed-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="357ed-117">I contenuti di una cassetta postale inattiva vengono conservati per la durata del blocco sul posto che è stato inserito nella cassetta postale eliminata temporaneamente quando è stato reso inattivo.</span><span class="sxs-lookup"><span data-stu-id="357ed-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="357ed-118">Dopo che la cassetta postale è stata resa inattiva, è possibile eseguire una ricerca nella cassetta postale utilizzando eDiscovery sul posto in Exchange Online, ricerca contenuto nel centro sicurezza & Compliance o eDiscovery Center in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="357ed-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="357ed-119">In Exchange Online, una cassetta postale con eliminazione temporanea è una cassetta postale che è stata eliminata, ma che può essere recuperata entro un periodo di conservazione specifico.</span><span class="sxs-lookup"><span data-stu-id="357ed-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="357ed-120">Il periodo di conservazione delle cassette postali con eliminazione temporanea in Exchange Online è pari a 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="357ed-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="357ed-121">Questo significa che la cassetta postale può essere recuperata (o resa una cassetta postale inattiva) entro 30 giorni dall'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="357ed-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="357ed-122">Dopo 30 giorni, una cassetta postale eliminata temporaneamente è contrassegnata per l'eliminazione definitiva e non può essere recuperata o resa inattiva.</span><span class="sxs-lookup"><span data-stu-id="357ed-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="357ed-123">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="357ed-123">Before you begin</span></span>

- <span data-ttu-id="357ed-124">È necessario utilizzare il cmdlet **New-MailboxSearch** in Windows PowerShell per attivare il blocco sul posto di una cassetta postale eliminata temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="357ed-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="357ed-125">Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o il centro eDiscovery in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="357ed-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 
    
- <span data-ttu-id="357ed-126">Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="357ed-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="357ed-127">Eseguire il seguente comando per ottenere informazioni sull'identità delle cassette postali eliminate temporaneamente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="357ed-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="357ed-128">Per ulteriori informazioni sulle cassette postali inattive, vedere [Overview of inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="357ed-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="357ed-129">Inserire un blocco sul posto di una cassetta postale eliminata temporaneamente per renderla una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="357ed-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="357ed-130">Utilizzare il cmdlet **New-MailboxSearch** per rendere una cassetta postale eliminata in maniera reversibile una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="357ed-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="357ed-131">Per ulteriori informazioni, vedere [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span><span class="sxs-lookup"><span data-stu-id="357ed-131">For more information, see [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="357ed-132">Creare una variabile che contiene le proprietà della cassetta postale eliminata temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="357ed-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span> 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="357ed-133">Nel comando precedente, utilizzare il valore della proprietà **Distinguished** o **ExchangeGuid** per identificare la cassetta postale eliminata temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="357ed-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="357ed-134">Queste proprietà sono univoche per ogni cassetta postale dell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale eliminata temporaneamente possano avere lo stesso indirizzo SMTP primario.</span><span class="sxs-lookup"><span data-stu-id="357ed-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="357ed-135">Creare un blocco sul posto e inserirlo nella cassetta postale eliminata temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="357ed-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="357ed-136">In questo esempio non viene specificata alcuna durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="357ed-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="357ed-137">Questo significa che gli elementi vengono conservati a tempo indeterminato o fino a quando il blocco non viene rimosso dalla cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="357ed-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   <span data-ttu-id="357ed-138">È inoltre possibile specificare una durata del blocco quando si crea il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="357ed-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="357ed-139">In questo esempio vengono mantenute gli elementi della cassetta postale inattiva per circa 7 anni.</span><span class="sxs-lookup"><span data-stu-id="357ed-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="357ed-140">Dopo alcuni istanti, eseguire uno dei comandi seguenti per verificare che la cassetta postale eliminata temporaneamente sia una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="357ed-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="357ed-141">Oppure</span><span class="sxs-lookup"><span data-stu-id="357ed-141">Or</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="357ed-142">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="357ed-142">More information</span></span>

<span data-ttu-id="357ed-143">Dopo aver reso una cassetta postale eliminata in maniera reversibile una cassetta postale inattiva, è possibile gestire la cassetta postale in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="357ed-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="357ed-144">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="357ed-144">For more information, see:</span></span>
  
- [<span data-ttu-id="357ed-145">Cambiare la durata del blocco per una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="357ed-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [<span data-ttu-id="357ed-146">Recuperare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="357ed-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)
    
- [<span data-ttu-id="357ed-147">Ripristinare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="357ed-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)
    
- <span data-ttu-id="357ed-148">[Eliminare una cassetta postale inattiva](delete-an-inactive-mailbox.md) (rimuovendo l'esenzione)</span><span class="sxs-lookup"><span data-stu-id="357ed-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
