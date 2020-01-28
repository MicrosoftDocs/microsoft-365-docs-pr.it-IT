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
ms.openlocfilehash: 64ee6d2c9887158939a87b9657b607bc9f323cec
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558483"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="d1c46-104">Inserire un blocco sul posto di una cassetta postale eliminata in modo reversibile in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d1c46-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="d1c46-105">Informazioni su come creare un blocco sul posto per una cassetta postale eliminata temporaneamente per renderla inattiva e conservarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="d1c46-105">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="d1c46-106">È quindi possibile utilizzare gli strumenti di Microsoft eDiscovery per cercare la cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="d1c46-106">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1c46-107">Continuando a investire in modi diversi per conservare il contenuto delle cassette postali, si annuncia la previdenza delle archiviazioni sul posto nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="d1c46-107">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="d1c46-108">A partire dal 1 ° aprile 2020 non è possibile creare nuove archiviazioni sul posto in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d1c46-108">Starting April 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="d1c46-109">Tuttavia, sarà comunque possibile gestire le archiviazioni sul posto in EAC o utilizzando il cmdlet **Set-MailboxSearch** in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c46-109">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="d1c46-110">Tuttavia, a partire dal 1 ° luglio 2020, non sarà possibile gestire le archiviazioni sul posto.</span><span class="sxs-lookup"><span data-stu-id="d1c46-110">However, starting July 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="d1c46-111">Verranno rimossi solo nell'interfaccia di amministrazione di Exchange o tramite il cmdlet **Remove-MailboxSearch** .</span><span class="sxs-lookup"><span data-stu-id="d1c46-111">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="d1c46-112">Per ulteriori informazioni sul pensionamento delle archiviazioni sul posto, vedere [pensionamento degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="d1c46-112">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="d1c46-113">Potrebbe verificarsi una situazione in cui una persona ha lasciato la propria organizzazione e l'account utente e la cassetta postale corrispondenti sono stati eliminati.</span><span class="sxs-lookup"><span data-stu-id="d1c46-113">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="d1c46-114">Successivamente, si rende conto che esistono informazioni nella cassetta postale che devono essere conservate.</span><span class="sxs-lookup"><span data-stu-id="d1c46-114">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="d1c46-115">Cosa potete fare?</span><span class="sxs-lookup"><span data-stu-id="d1c46-115">What can you do?</span></span> <span data-ttu-id="d1c46-116">Se il periodo di conservazione della cassetta postale eliminata non è scaduto, è possibile applicare un blocco sul posto alla cassetta postale eliminata (denominata cassetta postale eliminata temporaneamente) e renderla una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="d1c46-116">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="d1c46-117">Una *cassetta postale inattiva* viene utilizzata per mantenere la posta elettronica di un ex dipendente dopo che lui o lei lascia l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1c46-117">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="d1c46-118">I contenuti di una cassetta postale inattiva vengono conservati per la durata del blocco sul posto che è stato inserito nella cassetta postale eliminata temporaneamente quando è stato reso inattivo.</span><span class="sxs-lookup"><span data-stu-id="d1c46-118">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="d1c46-119">Dopo che la cassetta postale è stata resa inattiva, è possibile eseguire una ricerca nella cassetta postale utilizzando eDiscovery sul posto in Exchange Online, ricerca contenuto nel centro sicurezza & Compliance o eDiscovery Center in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d1c46-119">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d1c46-120">In Exchange Online, una cassetta postale con eliminazione temporanea è una cassetta postale che è stata eliminata, ma che può essere recuperata entro un periodo di conservazione specifico.</span><span class="sxs-lookup"><span data-stu-id="d1c46-120">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="d1c46-121">Il periodo di conservazione delle cassette postali con eliminazione temporanea in Exchange Online è pari a 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="d1c46-121">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="d1c46-122">Questo significa che la cassetta postale può essere recuperata (o resa una cassetta postale inattiva) entro 30 giorni dall'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="d1c46-122">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="d1c46-123">Dopo 30 giorni, una cassetta postale eliminata temporaneamente è contrassegnata per l'eliminazione definitiva e non può essere recuperata o resa inattiva.</span><span class="sxs-lookup"><span data-stu-id="d1c46-123">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="d1c46-124">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d1c46-124">Before you begin</span></span>

- <span data-ttu-id="d1c46-125">È necessario utilizzare il cmdlet **New-MailboxSearch** in Windows PowerShell per attivare il blocco sul posto di una cassetta postale eliminata temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d1c46-125">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="d1c46-126">Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o il centro eDiscovery in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d1c46-126">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="d1c46-127">Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="d1c46-127">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="d1c46-128">Eseguire il seguente comando per ottenere informazioni sull'identità delle cassette postali eliminate temporaneamente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1c46-128">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="d1c46-129">Per ulteriori informazioni sulle cassette postali inattive, vedere [Overview of inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="d1c46-129">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="d1c46-130">Inserire un blocco sul posto di una cassetta postale eliminata temporaneamente per renderla una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="d1c46-130">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="d1c46-131">Utilizzare il cmdlet **New-MailboxSearch** per rendere una cassetta postale eliminata in maniera reversibile una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="d1c46-131">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="d1c46-132">Per ulteriori informazioni, vedere [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span><span class="sxs-lookup"><span data-stu-id="d1c46-132">For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="d1c46-133">Creare una variabile che contiene le proprietà della cassetta postale eliminata temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d1c46-133">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="d1c46-134">Nel comando precedente, utilizzare il valore della proprietà **Distinguished** o **ExchangeGuid** per identificare la cassetta postale eliminata temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d1c46-134">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="d1c46-135">Queste proprietà sono univoche per ogni cassetta postale dell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale eliminata temporaneamente possano avere lo stesso indirizzo SMTP primario.</span><span class="sxs-lookup"><span data-stu-id="d1c46-135">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="d1c46-136">Creare un blocco sul posto e inserirlo nella cassetta postale eliminata temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d1c46-136">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="d1c46-137">In questo esempio non viene specificata alcuna durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="d1c46-137">In this example, no hold duration is specified.</span></span> <span data-ttu-id="d1c46-138">Questo significa che gli elementi vengono conservati a tempo indeterminato o fino a quando il blocco non viene rimosso dalla cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="d1c46-138">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="d1c46-139">È inoltre possibile specificare una durata del blocco quando si crea il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="d1c46-139">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="d1c46-140">In questo esempio vengono mantenute gli elementi della cassetta postale inattiva per circa 7 anni.</span><span class="sxs-lookup"><span data-stu-id="d1c46-140">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="d1c46-141">Dopo alcuni istanti, eseguire uno dei comandi seguenti per verificare che la cassetta postale eliminata temporaneamente sia una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="d1c46-141">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="d1c46-142">Oppure</span><span class="sxs-lookup"><span data-stu-id="d1c46-142">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="d1c46-143">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="d1c46-143">More information</span></span>

<span data-ttu-id="d1c46-144">Dopo aver reso una cassetta postale eliminata in maniera reversibile una cassetta postale inattiva, è possibile gestire la cassetta postale in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="d1c46-144">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="d1c46-145">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="d1c46-145">For more information, see:</span></span>
  
- [<span data-ttu-id="d1c46-146">Cambiare la durata del blocco per una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="d1c46-146">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="d1c46-147">Recuperare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="d1c46-147">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="d1c46-148">Ripristinare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="d1c46-148">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="d1c46-149">[Eliminare una cassetta postale inattiva](delete-an-inactive-mailbox.md) (rimuovendo il blocco)</span><span class="sxs-lookup"><span data-stu-id="d1c46-149">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
