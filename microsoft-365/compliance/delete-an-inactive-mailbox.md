---
title: Eliminare una cassetta postale inattiva
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
ms.openlocfilehash: 94a20bee1ca3d11a193a25efeb6d73f356e1d58d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909926"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="13559-103">Eliminare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="13559-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="13559-104">Una cassetta postale inattiva viene utilizzata per conservare la posta elettronica di un ex dipendente dopo l'uscita dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="13559-104">An inactive mailbox is used to preserve a former employee's email after they leave your organization.</span></span> <span data-ttu-id="13559-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span><span class="sxs-lookup"><span data-stu-id="13559-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="13559-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="13559-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="13559-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span><span class="sxs-lookup"><span data-stu-id="13559-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="13559-108">Inoltre, un criterio di conservazione (creato nel Centro sicurezza e conformità in Office 365 o Microsoft 365) potrebbe essere applicato alla cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="13559-109">È necessario rimuovere tutti i blocchi e i criteri di conservazione da una cassetta postale inattiva per eliminarla.</span><span class="sxs-lookup"><span data-stu-id="13559-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="13559-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span><span class="sxs-lookup"><span data-stu-id="13559-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="13559-111">Continuando a investire in modi diversi per conservare il contenuto delle cassette postali, stiamo annunciando il ritiro delle In-Place esenzioni nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="13559-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="13559-112">Ciò significa che è consigliabile utilizzare i blocchi per controversia legale e i criteri di conservazione per creare una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="13559-113">A partire dal 1° luglio 2020 non sarà possibile creare nuovi blocchi In-Place in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="13559-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="13559-114">Tuttavia, sarà comunque possibile modificare la durata del blocco di un'In-Place di archiviazione posta su una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="13559-115">Tuttavia, a partire dal 1° ottobre 2020, non sarà possibile modificare la durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="13559-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="13559-116">Sarà possibile eliminare una cassetta postale inattiva solo rimuovendo l'In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="13559-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="13559-117">Le cassette postali inattive esistenti In-Place conservazione verranno mantenute finché il blocco non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="13559-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="13559-118">Per ulteriori informazioni sul ritiro delle In-Place, vedere [Ritiro degli strumenti di eDiscovery legacy.](legacy-ediscovery-retirement.md)</span><span class="sxs-lookup"><span data-stu-id="13559-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="13559-119">Vedere la sezione [Ulteriori informazioni](#more-information) per una descrizione di cosa succede dopo che i blocchi vengono rimossi da una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="13559-120">Prima di eliminare una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="13559-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="13559-121">È necessario utilizzare Exchange Online PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="13559-122">Non è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="13559-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="13559-123">Per istruzioni dettagliate, vedere [Connettersi a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="13559-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="13559-124">È possibile copiare i contenuti di una cassetta postale inattiva in un'altra cassetta postale prima di rimuovere il blocco ed eliminare una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-124">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="13559-125">Per informazioni dettagliate, vedere [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="13559-125">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="13559-126">Se si rimuove il blocco o il criterio di conservazione da una cassetta postale inattiva e il periodo di conservazione della cassetta postale eliminata temporaneamente per la cassetta postale è scaduto, la cassetta postale verrà eliminata definitivamente.</span><span class="sxs-lookup"><span data-stu-id="13559-126">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="13559-127">Una volta eliminata, non è possibile recuperarla.</span><span class="sxs-lookup"><span data-stu-id="13559-127">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="13559-128">Prima di rimuovere il blocco, assicurarsi che il contenuto della cassetta postale non sia più necessario.</span><span class="sxs-lookup"><span data-stu-id="13559-128">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="13559-129">Se si desidera riattivare una cassetta postale inattiva, è possibile ripristinarla.</span><span class="sxs-lookup"><span data-stu-id="13559-129">If you want to reactivate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="13559-130">Per informazioni dettagliate, vedere [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="13559-130">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="13559-131">Per ulteriori informazioni sulle cassette postali inattive, vedere [Cassette postali inattive in Office 365.](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="13559-131">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="13559-132">Passaggio 1: identificare i blocchi su una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="13559-132">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="13559-133">Come indicato in precedenza, un blocco per controversia legale, In-Place blocco o un criterio di conservazione potrebbe essere posizionato su una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-133">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="13559-134">Il primo passaggio consiste nell'identificare i blocchi su una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-134">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="13559-135">Eseguire il seguente comando per visualizzare le informazioni sul blocco per tutte le cassette postali inattive dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="13559-135">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="13559-136">Il valore di **True** per la proprietà **LitigationHoldEnabled** indica che la cassetta postale inattiva ha un blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="13559-136">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="13559-137">Se in una cassetta postale inattiva è abilitato un blocco sul posto, il GUID del blocco viene visualizzato come il valore per la proprietà **InPlaceHolds**.</span><span class="sxs-lookup"><span data-stu-id="13559-137">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="13559-138">Ad esempio, i risultati seguenti per due cassette postali inattive mostrano che il blocco per controversia legale è stato posto su Ann Beebe e che un criterio di conservazione e blocco In-Place viene posizionato su Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="13559-138">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that an In-Place Hold and retention policy are placed on Pilar Pinilla.</span></span>
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="13559-139">Se molte In-Place esenzioni o criteri di conservazione vengono inseriti in una cassetta postale inattiva, non verranno visualizzati tutti In-Place GUID di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="13559-139">If a lot of In-Place Holds or retention policies are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="13559-140">È possibile eseguire il comando seguente per visualizzare tutti i GUID nella proprietà InPlaceHolds:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="13559-140">You can run the following command to display all the GUIDs in the InPlaceHolds property:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
<span data-ttu-id="13559-141">Per ulteriori informazioni sull'identificazione dei blocchi, vedere [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="13559-141">For more information about identify holds, see [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="13559-142">Passaggio 2: Rimuovere un blocco da una cassetta postale inattiva</span><span class="sxs-lookup"><span data-stu-id="13559-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="13559-p109">Dopo aver identificato il tipo di blocco applicato alla cassetta postale inattiva (e se sono presenti più blocchi), il passaggio successivo consiste nel rimuovere i blocchi sulla cassetta postale. Come descritto in precedenza, è necessario rimuovere tutti i blocchi per eliminare definitivamente una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-p109">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span>
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="13559-145">Rimozione di un blocco per controversia legale</span><span class="sxs-lookup"><span data-stu-id="13559-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="13559-p110">Come descritto in precedenza, è necessario utilizzare Windows PowerShell per rimuovere un blocco per controversia legale da una cassetta postale inattiva. Non è possibile usare l'interfaccia di amministrazione di Exchange. Eseguire il comando riportato di seguito per rimuovere un blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="13559-p110">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="13559-p111">Il modo migliore per identificare una cassetta postale inattiva è utilizzando il valore del relativo nome distinto o del GUID di Exchange. L'utilizzo di uno di questi valori consente di non specificare accidentalmente la cassetta postale errata.</span><span class="sxs-lookup"><span data-stu-id="13559-p111">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a><span data-ttu-id="13559-151">Rimuovere una cassetta postale inattiva da un criterio di conservazione</span><span class="sxs-lookup"><span data-stu-id="13559-151">Remove an inactive mailbox from a retention policy</span></span>

<span data-ttu-id="13559-152">La procedura per rimuovere una cassetta postale inattiva da un criterio di conservazione di Microsoft 365 dipende dal fatto che il criterio di conservazione assegnato alla cassetta postale inattiva sia a livello di organizzazione o esplicito.</span><span class="sxs-lookup"><span data-stu-id="13559-152">The procedure to remove an inactive mailbox from a Microsoft 365 retention policy depends whether the retention policy assigned to the inactive mailbox is organization-wide or explicit.</span></span> <span data-ttu-id="13559-153">sul tipo di criterio di conservazione assegnato alla cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-153">on the type of retention policy that's assigned to the inactive mailbox.</span></span>

- <span data-ttu-id="13559-154">Criteri di conservazione a livello di organizzazione assegnati a tutte le cassette postali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="13559-154">Organization-wide retention policies assigned to all mailboxes in the organization.</span></span> <span data-ttu-id="13559-155">Utilizzare il cmdlet **Get-OrganizationConfig** in PowerShell di Exchange Online per ottenere informazioni sui criteri di conservazione a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="13559-155">Use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>

- <span data-ttu-id="13559-156">Criteri di conservazione percorso specifici assegnati a cassette postali specifiche.</span><span class="sxs-lookup"><span data-stu-id="13559-156">Specific location retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="13559-157">Si tratta di criteri assegnati ai percorsi di contenuto di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="13559-157">These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="13559-158">Utilizzare il cmdlet **Get-Mailbox -IncludeInactiveMailbox** in PowerShell di Exchange Online per ottenere informazioni sui criteri di conservazione assegnati a cassette postali inattive specifiche.</span><span class="sxs-lookup"><span data-stu-id="13559-158">Use the **Get-Mailbox -IncludeInactiveMailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific inactive mailboxes.</span></span>

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a><span data-ttu-id="13559-159">Rimuovere una cassetta postale inattiva da un criterio di conservazione a livello di organizzazione</span><span class="sxs-lookup"><span data-stu-id="13559-159">Remove an inactive mailbox from an organization-wide retention policy</span></span>

<span data-ttu-id="13559-160">Eseguire il comando seguente in PowerShell di Exchange Online per escludere una cassetta postale inattiva da un criterio di conservazione a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="13559-160">Run the following command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide retention policy.</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

<span data-ttu-id="13559-161">Per ulteriori informazioni sull'identificazione dei criteri di conservazione a livello di organizzazione applicati a una cassetta postale inattiva e sull'ottenimento del GUID per un criterio di conservazione, vedere la sezione "Get-OrganizationConfig" in Come identificare il tipo di blocco applicato [a](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="13559-161">For more information identifying organization-wide retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-OrganizationConfig" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span></span>

<span data-ttu-id="13559-162">In alternativa, è possibile eseguire il comando seguente per rimuovere la cassetta postale inattiva da tutti i criteri a livello di organizzazione:</span><span class="sxs-lookup"><span data-stu-id="13559-162">Alternatively, you can run the following command to remove the inactive mailbox from all organization-wide policies:</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a><span data-ttu-id="13559-163">Rimuovere una cassetta postale inattiva da un criterio di conservazione percorso specifico</span><span class="sxs-lookup"><span data-stu-id="13559-163">Remove an inactive mailbox from a specific location retention policy</span></span>

<span data-ttu-id="13559-164">Eseguire il comando seguente in [PowerShell &](/powershell/exchange/connect-to-scc-powershell) Centro sicurezza e conformità per rimuovere una cassetta postale inattiva da un criterio di conservazione esplicito.</span><span class="sxs-lookup"><span data-stu-id="13559-164">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to remove an inactive mailbox from an explicit retention policy.</span></span>

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

<span data-ttu-id="13559-165">Per ulteriori informazioni sull'identificazione di criteri di conservazione percorso specifici applicati a una cassetta postale inattiva e su come ottenere il GUID per un criterio di conservazione, vedere la sezione "Get-Mailbox" in Come identificare il tipo di blocco applicato [a](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="13559-165">For more information identifying specific location retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-Mailbox" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span></span>

### <a name="remove-in-place-holds"></a><span data-ttu-id="13559-166">Rimozione dei blocchi sul posto</span><span class="sxs-lookup"><span data-stu-id="13559-166">Remove In-Place Holds</span></span>

 <span data-ttu-id="13559-167">Esistono due modi per rimuovere un blocco sul posto da una cassetta postale inattiva:</span><span class="sxs-lookup"><span data-stu-id="13559-167">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="13559-168">**Eliminare l'In-Place blocco .**</span><span class="sxs-lookup"><span data-stu-id="13559-168">**Delete the In-Place Hold object**.</span></span> <span data-ttu-id="13559-169">Se la cassetta postale inattiva che si desidera eliminare definitivamente è l'unica cassetta postale di origine per un blocco In-Place, è possibile eliminare l'oggetto In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="13559-169">If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="13559-p116">È necessario disattivare il blocco prima di eliminare un oggetto blocco sul posto. Se si tenta di eliminare un oggetto blocco sul posto con il blocco abilitato, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="13559-p116">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="13559-172">**Rimuovere la cassetta postale inattiva come cassetta postale di origine di un In-Place blocco**.</span><span class="sxs-lookup"><span data-stu-id="13559-172">**Remove the inactive mailbox as a source mailbox of an In-Place Hold**.</span></span> <span data-ttu-id="13559-173">Se si desidera mantenere altre cassette postali di origine per un blocco sul posto, è possibile rimuovere la cassetta postale inattiva dall'elenco di cassette postali di origine e conservare l'oggetto blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="13559-173">If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span>

#### <a name="delete-an-in-place-hold"></a><span data-ttu-id="13559-174">Eliminare un blocco In-Place blocco</span><span class="sxs-lookup"><span data-stu-id="13559-174">Delete an In-Place Hold</span></span>

1. <span data-ttu-id="13559-p118">Creare una variabile che contiene le proprietà del blocco sul posto che si desidera eliminare. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="13559-p118">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="13559-177">Disattivare il blocco in Blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="13559-177">Disable the hold on the In-Place Hold.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="13559-178">Eliminare il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="13559-178">Delete the In-Place Hold.</span></span>

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="13559-179">Rimuovere una cassetta postale inattiva da un In-Place blocco</span><span class="sxs-lookup"><span data-stu-id="13559-179">Remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="13559-p119">Se il blocco sul posto contiene un numero elevato di cassette postali di origine, è possibile che la cassetta postale inattiva non sia riportata nella pagina **Origini** nell'interfaccia di amministrazione di Exchange. Vengono visualizzate fino a 3.000 cassette postali nella pagina **Origini** quando si modifica un blocco sul posto. Se una cassetta postale inattiva non è indicata nella pagina **Origini**, è possibile utilizzare PowerShell di Exchange Online per rimuoverla dal blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="13559-p119">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="13559-p120">Creare una variabile che contiene le proprietà del blocco sul posto applicato alla cassetta postale inattiva. Utilizzare il GUID del blocco sul posto che è stato acquisito nel [Passaggio 1: Identificare i blocchi su una cassetta postale inattiva](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="13559-p120">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="13559-185">Verificare che la cassetta postale inattiva sia elencata come cassetta postale di origine per il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="13559-185">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > <span data-ttu-id="13559-p121">La proprietà *Sources* del blocco sul posto consente di identificare le cassette postali di origine dalle loro proprietà *LegacyExchangeDN*. Poiché questa proprietà identifica le cassette postali inattive in modo univoco, l'utilizzo della proprietà *Sources* dal blocco sul posto consente di evitare la rimozione della cassetta postale errata. Ciò consente inoltre di evitare problemi se due cassette postali hanno lo stesso alias o indirizzo SMTP.</span><span class="sxs-lookup"><span data-stu-id="13559-p121">The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties. Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox. This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 

3. <span data-ttu-id="13559-p122">Rimuovere la cassetta postale inattiva dall'elenco delle cassette postali di origine nella variabile. Assicurarsi di usare il **LegacyExchangeDN** della cassetta postale inattiva restituito dal comando nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="13559-p122">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="13559-191">Ad esempio, il seguente comando consente di rimuovere la cassetta postale inattiva per Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="13559-191">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="13559-192">Verificare che la cassetta postale inattiva venga rimossa dall'elenco delle cassette postali di origine nella variabile.</span><span class="sxs-lookup"><span data-stu-id="13559-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>

   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="13559-193">Modificare il blocco sul posto con l'elenco aggiornato delle cassette postali di origine, che non include la cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="13559-194">Verificare che la cassetta postale inattiva venga rimossa dall'elenco delle cassette postali di origine per il blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="13559-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="13559-195">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="13559-195">More information</span></span>

- <span data-ttu-id="13559-p123">**Una cassetta postale inattiva è un tipo di cassetta postale con eliminazione temporanea.** In Exchange Online, una cassetta postale con eliminazione temporanea è una cassetta postale che è stata eliminata, ma che può essere recuperata entro un periodo di conservazione specifico. Il periodo di conservazione delle cassette postali con eliminazione temporanea in Exchange Online è pari a 30 giorni. Ciò significa che la cassetta postale può essere recuperata entro 30 giorni dall'eliminazione temporanea. Dopo 30 giorni, una cassetta postale con eliminazione temporanea viene contrassegnata per l'eliminazione definitiva e non può essere ripristinata.</span><span class="sxs-lookup"><span data-stu-id="13559-p123">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span>

- <span data-ttu-id="13559-201">**Cosa succede dopo aver rimosso il blocco su una cassetta postale inattiva?**</span><span class="sxs-lookup"><span data-stu-id="13559-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="13559-202">La cassetta postale viene considerata come altre cassette postali con eliminazione temporanea e viene contrassegnata per l'eliminazione definitiva alla scadenza del periodo di conservazione di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="13559-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="13559-203">Questo periodo di conservazione inizia alla data in cui la cassetta postale viene resa inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="13559-204">Questa data è nota come data di eliminazione recidiva, ovvero la data in cui l'account utente corrispondente è stato eliminato o quando la cassetta postale di Exchange Online è stata eliminata con il cmdlet **Remove-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="13559-204">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="13559-205">La data di eliminazione temporanea non è la data in cui si rimuove il blocco.</span><span class="sxs-lookup"><span data-stu-id="13559-205">The soft-deleted date isn't the date on which you remove the hold.</span></span>

- <span data-ttu-id="13559-p125">**Una cassetta postale inattiva viene eliminata definitivamente subito dopo la rimozione del blocco?** Se la data di eliminazione temporanea di una cassetta postale inattiva risale a più di 30 giorni prima, la cassetta postale non viene eliminata definitivamente non appena si rimuove il blocco. La cassetta postale viene contrassegnata per l'eliminazione definitiva e viene eliminata la volta successiva che viene elaborata.</span><span class="sxs-lookup"><span data-stu-id="13559-p125">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span>

- <span data-ttu-id="13559-209">**In che modo il periodo di conservazione delle cassette postali con eliminazione temporanea influisce sulle cassette postali inattive?**</span><span class="sxs-lookup"><span data-stu-id="13559-209">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="13559-210">Se la data di eliminazione temporanea di una cassetta postale inattiva risale a più di 30 giorni prima della data in cui è stato rimosso il blocco, la cassetta postale viene contrassegnata per l'eliminazione definitiva.</span><span class="sxs-lookup"><span data-stu-id="13559-210">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="13559-211">Tuttavia, se una cassetta postale inattiva ha una data di eliminazione temporanea entro gli ultimi 30 giorni e si rimuove il blocco, è possibile ripristinare la cassetta postale fino a quando non scade il periodo di conservazione delle cassette postali con eliminazione temporanea.</span><span class="sxs-lookup"><span data-stu-id="13559-211">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="13559-212">Per ulteriori dettagli, vedere [Eliminare o ripristinare le cassette postali utente in Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="13559-212">For details, see [Delete or restore user mailboxes in Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).</span></span> <span data-ttu-id="13559-213">Dopo la scadenza del periodo di conservazione della cassetta postale eliminata in modo reverso, è necessario seguire le procedure per il ripristino di una cassetta postale inattiva.</span><span class="sxs-lookup"><span data-stu-id="13559-213">After the soft-deleted mailbox retention period expires, you have to follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="13559-214">Per informazioni dettagliate, vedere [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="13559-214">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="13559-215">**Come vengono visualizzate le informazioni su una cassetta postale inattiva dopo la rimozione del blocco?**</span><span class="sxs-lookup"><span data-stu-id="13559-215">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="13559-216">Dopo che un blocco è stato rimosso e la cassetta postale inattiva viene ripristinata in una cassetta postale eliminata in modo recintato, non verrà restituita utilizzando il parametro *InactiveMailboxOnly* con il cmdlet **Get-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="13559-216">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="13559-217">Tuttavia, è possibile visualizzare le informazioni sulla cassetta postale utilizzando il comando **Get-Mailbox -SoftDeletedMailbox**.</span><span class="sxs-lookup"><span data-stu-id="13559-217">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="13559-218">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="13559-218">For example:</span></span>

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

  <span data-ttu-id="13559-219">Nell'esempio precedente, la *proprietà WhenSoftDeleted* identifica la data di eliminazione recidiva, che in questo esempio è il 30 ottobre 2014.</span><span class="sxs-lookup"><span data-stu-id="13559-219">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="13559-220">Se questa cassetta postale eliminata temporaneamente era in precedenza una cassetta postale inattiva per la quale è stato rimosso il blocco, verrà eliminata definitivamente 30 giorni dopo il valore della proprietà *WhenSoftDeleted.*</span><span class="sxs-lookup"><span data-stu-id="13559-220">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="13559-221">In questo caso, la cassetta postale viene eliminata definitivamente dopo il 30 novembre 2014.</span><span class="sxs-lookup"><span data-stu-id="13559-221">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>