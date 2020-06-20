---
title: Eliminare una cassetta postale inattiva
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Quando non è più necessario conservare il contenuto di una cassetta postale inattiva di Microsoft 365, è possibile eliminare definitivamente la cassetta postale inattiva.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817895"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="eeabe-103">Eliminare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="eeabe-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="eeabe-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="eeabe-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="eeabe-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span><span class="sxs-lookup"><span data-stu-id="eeabe-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="eeabe-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="eeabe-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="eeabe-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span><span class="sxs-lookup"><span data-stu-id="eeabe-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="eeabe-108">Inoltre, è possibile applicare un criterio di conservazione (creato nel centro sicurezza e conformità di Office 365 o Microsoft 365) alla cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="eeabe-109">È necessario rimuovere tutte le esenzioni e i criteri di conservazione da una cassetta postale inattiva per eliminarla.</span><span class="sxs-lookup"><span data-stu-id="eeabe-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="eeabe-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span><span class="sxs-lookup"><span data-stu-id="eeabe-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eeabe-111">Continuando a investire in modi diversi per conservare il contenuto delle cassette postali, si annuncia la prepensionamento delle archiviazioni sul posto nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="eeabe-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="eeabe-112">Per creare una cassetta postale inattiva, è necessario utilizzare i criteri di conservazione per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="eeabe-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="eeabe-113">A partire dal 1 ° luglio 2020 non è possibile creare nuove archiviazioni sul posto in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="eeabe-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="eeabe-114">Tuttavia, sarà comunque possibile modificare la durata del blocco di un blocco sul posto posto in una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="eeabe-115">Tuttavia, a partire dal 1 ° ottobre 2020, non sarà possibile modificare la durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="eeabe-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="eeabe-116">È possibile eliminare una cassetta postale inattiva solo rimuovendo il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="eeabe-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="eeabe-117">Le cassette postali inattive esistenti che si trovano sul blocco sul posto continueranno a essere conservate finché il blocco non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="eeabe-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="eeabe-118">Per ulteriori informazioni sul pensionamento delle archiviazioni sul posto, vedere [pensionamento degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="eeabe-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="eeabe-119">Vedere la sezione [Ulteriori informazioni](#more-information) per una descrizione di cosa succede dopo che i blocchi vengono rimossi da una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="eeabe-120">Prima di eliminare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="eeabe-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="eeabe-121">È necessario utilizzare Exchange Online PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="eeabe-122">Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="eeabe-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="eeabe-123">Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="eeabe-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="eeabe-124">È possibile utilizzare Exchange Online PowerShell o l'interfaccia di amministrazione di Exchange (EAC) per rimuovere un blocco sul posto da una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-124">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="eeabe-125">È possibile copiare i contenuti di una cassetta postale inattiva in un'altra cassetta postale prima di rimuovere il blocco ed eliminare una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-125">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="eeabe-126">Per ulteriori informazioni, vedere [ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="eeabe-126">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="eeabe-127">Se si rimuove il blocco o il criterio di conservazione da una cassetta postale inattiva e il periodo di conservazione delle cassette postali eliminate temporaneamente per la cassetta postale è scaduto, la cassetta postale viene eliminata definitivamente.</span><span class="sxs-lookup"><span data-stu-id="eeabe-127">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="eeabe-128">Una volta eliminata, non è possibile recuperarla.</span><span class="sxs-lookup"><span data-stu-id="eeabe-128">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="eeabe-129">Prima di rimuovere il blocco, assicurarsi che il contenuto della cassetta postale non sia più necessario.</span><span class="sxs-lookup"><span data-stu-id="eeabe-129">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="eeabe-130">Se si desidera attivare nuovamente una cassetta postale inattiva, è possibile recuperarla.</span><span class="sxs-lookup"><span data-stu-id="eeabe-130">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="eeabe-131">Per ulteriori informazioni, vedere [recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="eeabe-131">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="eeabe-132">Per ulteriori informazioni sulle cassette postali inattive, vedere [inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="eeabe-132">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="eeabe-133">Passaggio 1: identificare i blocchi su una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="eeabe-133">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="eeabe-134">Come indicato in precedenza, un blocco per controversia legale, un blocco sul posto o un criterio di conservazione potrebbe essere posizionato su una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-134">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="eeabe-135">Il primo passaggio consiste nell'identificare i blocchi su una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-135">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="eeabe-136">Eseguire il seguente comando per visualizzare le informazioni sul blocco per tutte le cassette postali inattive dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eeabe-136">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="eeabe-137">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span><span class="sxs-lookup"><span data-stu-id="eeabe-137">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="eeabe-138">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span><span class="sxs-lookup"><span data-stu-id="eeabe-138">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="eeabe-139">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="eeabe-139">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="eeabe-140">Se sono abilitati numerosi blocchi sul posto per una cassetta postale inattiva, non vengono visualizzati tutti i GUID dei blocchi sul posto.</span><span class="sxs-lookup"><span data-stu-id="eeabe-140">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="eeabe-141">È possibile eseguire il comando seguente per visualizzare tutti i GUID del blocco sul posto:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="eeabe-141">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="eeabe-142">Passaggio 2: Rimuovere un blocco da una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="eeabe-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="eeabe-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span><span class="sxs-lookup"><span data-stu-id="eeabe-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="eeabe-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="eeabe-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="eeabe-145">Rimozione di un blocco per controversia legale</span><span class="sxs-lookup"><span data-stu-id="eeabe-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="eeabe-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="eeabe-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="eeabe-147">You can't use the EAC.</span><span class="sxs-lookup"><span data-stu-id="eeabe-147">You can't use the EAC.</span></span> <span data-ttu-id="eeabe-148">Run the following command to remove a Litigation Hold.</span><span class="sxs-lookup"><span data-stu-id="eeabe-148">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="eeabe-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span><span class="sxs-lookup"><span data-stu-id="eeabe-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="eeabe-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span><span class="sxs-lookup"><span data-stu-id="eeabe-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="eeabe-151">Rimozione dei blocchi sul posto</span><span class="sxs-lookup"><span data-stu-id="eeabe-151">Remove In-Place Holds</span></span>

 <span data-ttu-id="eeabe-152">Esistono due modi per rimuovere un blocco sul posto da una cassetta postale inattiva:</span><span class="sxs-lookup"><span data-stu-id="eeabe-152">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="eeabe-153">**Eliminare l'oggetto blocco sul posto** Se la cassetta postale inattiva che si desidera eliminare in modo definitivo è l'unica cassetta postale di origine per un blocco sul posto, è possibile eliminare l'oggetto blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="eeabe-153">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="eeabe-154">You have to disable the hold before you can delete an In-Place Hold object.</span><span class="sxs-lookup"><span data-stu-id="eeabe-154">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="eeabe-155">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span><span class="sxs-lookup"><span data-stu-id="eeabe-155">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="eeabe-156">**Rimuovere la cassetta postale inattiva come cassetta postale di origine di un blocco sul posto** Se si desidera mantenere altre cassette postali di origine per un blocco sul posto, è possibile rimuovere la cassetta postale inattiva dall'elenco di cassette postali di origine e conservare l'oggetto blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="eeabe-156">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="eeabe-157">Utilizzare EAC per eliminare un blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="eeabe-157">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="eeabe-158">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span><span class="sxs-lookup"><span data-stu-id="eeabe-158">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span></span> <span data-ttu-id="eeabe-159">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span><span class="sxs-lookup"><span data-stu-id="eeabe-159">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span></span> <span data-ttu-id="eeabe-160">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="eeabe-160">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="eeabe-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="eeabe-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="eeabe-162">Selezionare il blocco sul posto che si desidera eliminare, quindi fare clic su **modifica** ![ icona modifica ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="eeabe-162">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="eeabe-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="eeabe-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="eeabe-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span><span class="sxs-lookup"><span data-stu-id="eeabe-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="eeabe-165">Nell'avviso, fare clic su **Sì** per eliminare il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="eeabe-165">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="eeabe-166">Utilizzare PowerShell di Exchange Online per eliminare un blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="eeabe-166">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="eeabe-167">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span><span class="sxs-lookup"><span data-stu-id="eeabe-167">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="eeabe-168">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="eeabe-168">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="eeabe-169">Disattivare il blocco in Blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="eeabe-169">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="eeabe-170">Eliminare il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="eeabe-170">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="eeabe-171">Usare EAC per rimuovere una cassetta postale inattiva da un blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="eeabe-171">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="eeabe-172">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span><span class="sxs-lookup"><span data-stu-id="eeabe-172">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span></span> <span data-ttu-id="eeabe-173">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span><span class="sxs-lookup"><span data-stu-id="eeabe-173">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span></span> <span data-ttu-id="eeabe-174">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="eeabe-174">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="eeabe-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="eeabe-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="eeabe-176">Selezionare il blocco sul posto applicato alla cassetta postale inattiva, quindi fare clic su **modifica** ![ icona modifica ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="eeabe-176">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="eeabe-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span><span class="sxs-lookup"><span data-stu-id="eeabe-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="eeabe-178">Nell'elenco delle cassette postali di origine, fare clic sul nome della cassetta postale inattiva che si desidera rimuovere, quindi fare clic su **Rimuovi**![Icona Rimuovi](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span><span class="sxs-lookup"><span data-stu-id="eeabe-178">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="eeabe-179">Click **Save** to save the change.</span><span class="sxs-lookup"><span data-stu-id="eeabe-179">Click **Save** to save the change.</span></span> <span data-ttu-id="eeabe-180">A message is displayed saying the operation was successfully completed.</span><span class="sxs-lookup"><span data-stu-id="eeabe-180">A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="eeabe-181">Ripetere i passaggi da 1 a 6 per rimuovere altri blocchi sul posto applicati alla cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-181">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="eeabe-182">Utilizzare PowerShell di Exchange Online per rimuovere una cassetta postale inattiva da un blocco sul posto</span><span class="sxs-lookup"><span data-stu-id="eeabe-182">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="eeabe-183">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span><span class="sxs-lookup"><span data-stu-id="eeabe-183">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="eeabe-184">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="eeabe-184">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="eeabe-185">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="eeabe-185">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="eeabe-186">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="eeabe-186">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="eeabe-187">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="eeabe-187">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="eeabe-188">Verificare che la cassetta postale inattiva sia elencata come cassetta postale di origine per il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="eeabe-188">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="eeabe-189">**Nota:** La proprietà *Sources* del blocco sul posto identifica le cassette postali di origine in base alle rispettive proprietà *legacyExchangeDN* .</span><span class="sxs-lookup"><span data-stu-id="eeabe-189">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="eeabe-190">Poiché questa proprietà identifica le cassette postali inattive in modo univoco, l'utilizzo della proprietà *Sources* dal blocco sul posto consente di evitare la rimozione della cassetta postale errata.</span><span class="sxs-lookup"><span data-stu-id="eeabe-190">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="eeabe-191">Ciò consente inoltre di evitare problemi se due cassette postali hanno lo stesso alias o indirizzo SMTP.</span><span class="sxs-lookup"><span data-stu-id="eeabe-191">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="eeabe-192">Remove the inactive mailbox from the list of source mailboxes in the variable.</span><span class="sxs-lookup"><span data-stu-id="eeabe-192">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="eeabe-193">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span><span class="sxs-lookup"><span data-stu-id="eeabe-193">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="eeabe-194">Ad esempio, il seguente comando consente di rimuovere la cassetta postale inattiva per Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="eeabe-194">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="eeabe-195">Verificare che la cassetta postale inattiva venga rimossa dall'elenco delle cassette postali di origine nella variabile.</span><span class="sxs-lookup"><span data-stu-id="eeabe-195">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="eeabe-196">Modificare il blocco sul posto con l'elenco aggiornato delle cassette postali di origine, che non include la cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-196">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="eeabe-197">Verificare che la cassetta postale inattiva venga rimossa dall'elenco delle cassette postali di origine per il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="eeabe-197">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="eeabe-198">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="eeabe-198">More information</span></span>

- <span data-ttu-id="eeabe-199">**An inactive mailbox is a type of soft-deleted mailbox.**</span><span class="sxs-lookup"><span data-stu-id="eeabe-199">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="eeabe-200">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span><span class="sxs-lookup"><span data-stu-id="eeabe-200">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="eeabe-201">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span><span class="sxs-lookup"><span data-stu-id="eeabe-201">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="eeabe-202">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span><span class="sxs-lookup"><span data-stu-id="eeabe-202">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="eeabe-203">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span><span class="sxs-lookup"><span data-stu-id="eeabe-203">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="eeabe-204">**Cosa succede dopo aver rimosso il blocco su una cassetta postale inattiva?**</span><span class="sxs-lookup"><span data-stu-id="eeabe-204">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="eeabe-205">La cassetta postale viene considerata come altre cassette postali con eliminazione temporanea e viene contrassegnata per l'eliminazione definitiva alla scadenza del periodo di conservazione di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="eeabe-205">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="eeabe-206">Questo periodo di conservazione inizia alla data in cui la cassetta postale viene resa inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-206">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="eeabe-207">Questa data è nota come la data di eliminazione temporanea, ovvero la data in cui l'account utente corrispondente è stato eliminato o quando la cassetta postale di Exchange Online è stata eliminata con il cmdlet **Remove-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="eeabe-207">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="eeabe-208">La data di eliminazione temporanea non è la data in cui si rimuove il blocco.</span><span class="sxs-lookup"><span data-stu-id="eeabe-208">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="eeabe-209">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span><span class="sxs-lookup"><span data-stu-id="eeabe-209">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="eeabe-210">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span><span class="sxs-lookup"><span data-stu-id="eeabe-210">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="eeabe-211">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span><span class="sxs-lookup"><span data-stu-id="eeabe-211">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="eeabe-212">**In che modo il periodo di conservazione delle cassette postali con eliminazione temporanea influisce sulle cassette postali inattive?**</span><span class="sxs-lookup"><span data-stu-id="eeabe-212">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="eeabe-213">Se la data di eliminazione temporanea di una cassetta postale inattiva risale a più di 30 giorni prima della data in cui è stato rimosso il blocco, la cassetta postale viene contrassegnata per l'eliminazione definitiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-213">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="eeabe-214">Tuttavia, se una cassetta postale inattiva ha una data di eliminazione temporanea entro gli ultimi 30 giorni e si rimuove il blocco, è possibile ripristinare la cassetta postale fino a quando non scade il periodo di conservazione delle cassette postali con eliminazione temporanea.</span><span class="sxs-lookup"><span data-stu-id="eeabe-214">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="eeabe-215">Per ulteriori dettagli, vedere [Eliminare o ripristinare le cassette postali utente in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span><span class="sxs-lookup"><span data-stu-id="eeabe-215">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="eeabe-216">Alla scadenza del periodo di conservazione delle cassette postali con eliminazione temporanea, è necessario seguire le procedure per il ripristino di una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="eeabe-216">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="eeabe-217">Per ulteriori informazioni, vedere [recuperare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="eeabe-217">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="eeabe-218">**Come vengono visualizzate le informazioni su una cassetta postale inattiva dopo la rimozione del blocco?**</span><span class="sxs-lookup"><span data-stu-id="eeabe-218">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="eeabe-219">Dopo la rimozione di un'esenzione e la cassetta postale inattiva viene ripristinata a una cassetta postale eliminata temporaneamente, non verrà restituita utilizzando il parametro *InactiveMailboxOnly* con il cmdlet **Get-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="eeabe-219">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="eeabe-220">Tuttavia, è possibile visualizzare le informazioni sulla cassetta postale utilizzando il comando **Get-Mailbox -SoftDeletedMailbox**.</span><span class="sxs-lookup"><span data-stu-id="eeabe-220">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="eeabe-221">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="eeabe-221">For example:</span></span> 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  <span data-ttu-id="eeabe-222">Nell'esempio precedente, la proprietà *WhenSoftDeleted* identifica la data di eliminazione temporanea, che in questo esempio è il 30 ottobre 2014.</span><span class="sxs-lookup"><span data-stu-id="eeabe-222">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="eeabe-223">Se questa cassetta postale eliminata temporaneamente è stata precedentemente una cassetta postale inattiva per la quale è stato rimosso il blocco, verrà eliminato definitivamente 30 giorni dopo il valore della proprietà *WhenSoftDeleted* .</span><span class="sxs-lookup"><span data-stu-id="eeabe-223">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="eeabe-224">In questo caso, la cassetta postale viene eliminata definitivamente dopo il 30 novembre 2014.</span><span class="sxs-lookup"><span data-stu-id="eeabe-224">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

