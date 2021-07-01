---
title: Inserire un In-Place blocco su una cassetta postale eliminata in Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come creare un blocco In-Place per una cassetta postale eliminata in modo resciso per renderla inattiva e conservarne il contenuto.
ms.openlocfilehash: d72a5407bfafabed30466447e404cdd4196678ae
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226096"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="78455-103">Inserire un In-Place blocco su una cassetta postale eliminata in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="78455-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="78455-104">Informazioni su come creare un blocco In-Place per una cassetta postale eliminata in modo resciso per renderla inattiva e conservarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="78455-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="78455-105">È quindi possibile utilizzare gli strumenti di Microsoft eDiscovery per eseguire ricerche nella cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="78455-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78455-106">Mentre continuiamo a investire in modi diversi per conservare il contenuto delle cassette postali, annunciamo il ritiro delle esenzioni In-Place nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="78455-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="78455-107">A partire dal 1° luglio 2020 non sarà possibile creare nuove esenzioni In-Place in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78455-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="78455-108">Tuttavia, sarà comunque possibile gestire In-Place blocchi nell'interfaccia di amministrazione di Exchange o utilizzando il cmdlet **Set-MailboxSearch** in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78455-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="78455-109">Tuttavia, a partire dal 1° ottobre 2020, non sarà possibile gestire le In-Place esenzioni.</span><span class="sxs-lookup"><span data-stu-id="78455-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="78455-110">Sarà possibile rimuoverli solo nell'interfaccia di amministrazione di Exchange o utilizzando il cmdlet **Remove-MailboxSearch.**</span><span class="sxs-lookup"><span data-stu-id="78455-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="78455-111">Per ulteriori informazioni sul ritiro delle In-Place, vedere [Ritiro degli strumenti di eDiscovery legacy.](legacy-ediscovery-retirement.md)</span><span class="sxs-lookup"><span data-stu-id="78455-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>

<span data-ttu-id="78455-112">Potrebbe verificarsi una situazione in cui una persona ha lasciato l'organizzazione e l'account utente e la cassetta postale corrispondenti sono stati eliminati.</span><span class="sxs-lookup"><span data-stu-id="78455-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="78455-113">In seguito, ci si rende conto che nella cassetta postale sono presenti informazioni che devono essere conservate.</span><span class="sxs-lookup"><span data-stu-id="78455-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="78455-114">Cosa potete fare?</span><span class="sxs-lookup"><span data-stu-id="78455-114">What can you do?</span></span> <span data-ttu-id="78455-115">Se il periodo di conservazione della cassetta postale eliminata non è scaduto, è possibile impostare un blocco In-Place sulla cassetta postale eliminata (denominata cassetta postale eliminata in modo reversivi) e renderla una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="78455-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a soft-deleted mailbox) and make it an inactive mailbox.</span></span> <span data-ttu-id="78455-116">Una  *cassetta postale inattiva*  viene utilizzata per conservare la posta elettronica di un ex dipendente dopo aver lasciato l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78455-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="78455-117">Il contenuto di una cassetta postale inattiva viene conservato per tutta la durata del blocco In-Place che è stato inserito nella cassetta postale eliminata in modo reversivo quando è stata resa inattiva.</span><span class="sxs-lookup"><span data-stu-id="78455-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="78455-118">Dopo aver reso inattiva la cassetta postale, è possibile eseguire ricerche nella cassetta postale utilizzando In-Place eDiscovery in Exchange Online, Ricerca contenuto nel Centro sicurezza & conformità o centro eDiscovery in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="78455-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span>

> [!NOTE]
> <span data-ttu-id="78455-119">In Exchange Online, una cassetta postale con eliminazione temporanea è una cassetta postale che è stata eliminata, ma che può essere recuperata entro un periodo di conservazione specifico.</span><span class="sxs-lookup"><span data-stu-id="78455-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="78455-120">Il periodo di conservazione delle cassette postali con eliminazione temporanea in Exchange Online è pari a 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="78455-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="78455-121">Ciò significa che la cassetta postale può essere recuperata (o resa una cassetta postale inattiva) entro 30 giorni dall'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="78455-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="78455-122">Dopo 30 giorni, una cassetta postale eliminata definitivamente viene contrassegnata per l'eliminazione permanente e non può essere ripristinata o resa inattiva.</span><span class="sxs-lookup"><span data-stu-id="78455-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span>

## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="78455-123">Requisiti per le In-Place di archiviazione</span><span class="sxs-lookup"><span data-stu-id="78455-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="78455-124">È necessario utilizzare il cmdlet **New-MailboxSearch** in Windows PowerShell per In-Place blocco su una cassetta postale eliminata in modo recidiva.</span><span class="sxs-lookup"><span data-stu-id="78455-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="78455-125">Non è possibile utilizzare l'interfaccia Exchange (EAC) o il Centro eDiscovery in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="78455-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span>

- <span data-ttu-id="78455-126">Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="78455-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="78455-127">Eseguire il comando seguente per ottenere informazioni sull'identità delle cassette postali con eliminazione recidiva nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78455-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span>

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="78455-128">Per ulteriori informazioni sulle cassette postali inattive, vedere [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="78455-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="78455-129">Inserire un In-Place blocco su una cassetta postale eliminata in modo resciso per renderla una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="78455-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="78455-130">Utilizzare il cmdlet **New-MailboxSearch** per fare in modo che una cassetta postale eliminata in modo resciso sia una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="78455-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="78455-131">Per ulteriori informazioni, vedere [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span><span class="sxs-lookup"><span data-stu-id="78455-131">For more information, see [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span></span>

1. <span data-ttu-id="78455-132">Creare una variabile contenente le proprietà della cassetta postale eliminata in modo recidiva.</span><span class="sxs-lookup"><span data-stu-id="78455-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="78455-133">Nel comando precedente, utilizzare il valore della **proprietà DistinguishedName** o **ExchangeGuid** per identificare la cassetta postale eliminata in modo recidiva.</span><span class="sxs-lookup"><span data-stu-id="78455-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="78455-134">Queste proprietà sono univoche per ogni cassetta postale dell'organizzazione, mentre è possibile che una cassetta postale attiva e una cassetta postale eliminata in modo reciso abbia lo stesso indirizzo SMTP primario.</span><span class="sxs-lookup"><span data-stu-id="78455-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="78455-135">Creare un In-Place e posizionarlo nella cassetta postale eliminata in modo recidiva.</span><span class="sxs-lookup"><span data-stu-id="78455-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="78455-136">In questo esempio non viene specificata alcuna durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="78455-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="78455-137">Ciò significa che gli elementi verranno mantenuti a tempo indeterminato o finché il blocco non viene rimosso dalla cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="78455-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="78455-138">È inoltre possibile specificare una durata del blocco quando si crea l'In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="78455-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="78455-139">In questo esempio vengono conservati gli elementi nella cassetta postale inattiva per circa 7 anni.</span><span class="sxs-lookup"><span data-stu-id="78455-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="78455-140">Dopo alcuni istanti, eseguire uno dei comandi seguenti per verificare che la cassetta postale eliminata in modo reversibili sia una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="78455-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="78455-141">Oppure</span><span class="sxs-lookup"><span data-stu-id="78455-141">Or</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="78455-142">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="78455-142">More information</span></span>

<span data-ttu-id="78455-143">Dopo aver fatto di una cassetta postale eliminata in modo recidiva una cassetta postale inattiva, è possibile gestire la cassetta postale in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="78455-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="78455-144">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="78455-144">For more information, see:</span></span>

- [<span data-ttu-id="78455-145">Cambiare la durata del blocco per una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="78455-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="78455-146">Recuperare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="78455-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="78455-147">Ripristinare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="78455-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="78455-148">[Eliminare una cassetta postale inattiva](delete-an-inactive-mailbox.md) (rimuovendo il blocco)</span><span class="sxs-lookup"><span data-stu-id="78455-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>