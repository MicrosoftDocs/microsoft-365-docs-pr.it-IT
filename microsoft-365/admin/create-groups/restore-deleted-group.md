---
title: Ripristinare un gruppo eliminato
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Informazioni su come ripristinare un gruppo di Microsoft 365 eliminato.
ms.openlocfilehash: 30e267a149bc18c2425d4ea38423b887116794c6
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681647"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="a4344-103">Ripristinare un gruppo eliminato</span><span class="sxs-lookup"><span data-stu-id="a4344-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a4344-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="a4344-104">The admin center is changing.</span></span> <span data-ttu-id="a4344-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a4344-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

> [!NOTE]
> <span data-ttu-id="a4344-106">In questo articolo viene descritto come ripristinare solo i gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a4344-106">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="a4344-107">Non è possibile ripristinare tutti gli altri gruppi una volta eliminati.</span><span class="sxs-lookup"><span data-stu-id="a4344-107">All other groups cannot be restored once deleted.</span></span>

<span data-ttu-id="a4344-108">Se si è eliminato un gruppo, questo verrà mantenuto per 30 giorni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a4344-108">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="a4344-109">Questo periodo di 30 giorni è considerato "soft-delete" perché è ancora possibile ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="a4344-109">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="a4344-110">Dopo 30 giorni, il gruppo e il relativo contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="a4344-110">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="a4344-111">Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a4344-111">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="a4344-112">Oggetto, proprietà e membri di Azure Active Directory (AD) Microsoft 365 groups.</span><span class="sxs-lookup"><span data-stu-id="a4344-112">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="a4344-113">Indirizzi di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a4344-113">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="a4344-114">Posta in arrivo condivisa e calendario di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a4344-114">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="a4344-115">Sito e file del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a4344-115">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="a4344-116">Blocco appunti di OneNote</span><span class="sxs-lookup"><span data-stu-id="a4344-116">OneNote notebook</span></span>
    
- <span data-ttu-id="a4344-117">Planner</span><span class="sxs-lookup"><span data-stu-id="a4344-117">Planner</span></span>
    
- <span data-ttu-id="a4344-118">Teams</span><span class="sxs-lookup"><span data-stu-id="a4344-118">Teams</span></span>

- <span data-ttu-id="a4344-119">Gruppo di Yammer e contenuto del gruppo (se il gruppo Microsoft 365 è stato creato da Yammer)</span><span class="sxs-lookup"><span data-stu-id="a4344-119">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="a4344-120">Ripristinare un gruppo personalizzato tramite Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="a4344-120">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="a4344-121">Se si è il proprietario di un gruppo di Microsoft 365, è possibile ripristinare il gruppo manualmente in Outlook sul Web attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a4344-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="a4344-122">Nella [pagina Gruppi eliminati](https://outlook.office.com/people/group/deleted)selezionare l'opzione **Gestisci gruppi** nel nodo **gruppi** e quindi scegliere **eliminata**.</span><span class="sxs-lookup"><span data-stu-id="a4344-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="a4344-123">Fare clic sulla scheda **Ripristina** accanto al gruppo che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="a4344-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="a4344-124">Se il gruppo eliminato non viene visualizzato, contattare un amministratore.</span><span class="sxs-lookup"><span data-stu-id="a4344-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a4344-125">Ripristinare un gruppo nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a4344-125">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a4344-126">Se si è amministratori globali o amministratori di gruppi, è possibile ripristinare un gruppo eliminato nell'interfaccia di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="a4344-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="a4344-127">Passare all'[interfaccia di amministrazione](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a4344-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="a4344-128">Espandere **gruppi**e quindi fare clic su **gruppi eliminati**.</span><span class="sxs-lookup"><span data-stu-id="a4344-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="a4344-129">Selezionare il gruppo che si desidera ripristinare e quindi fare clic su **Ripristina gruppo**.</span><span class="sxs-lookup"><span data-stu-id="a4344-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="a4344-130">In alcuni casi, può richiedere fino a 24 ore prima che il gruppo e tutti i relativi dati vengano ripristinati.</span><span class="sxs-lookup"><span data-stu-id="a4344-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="a4344-131">Eliminare definitivamente un gruppo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a4344-131">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="a4344-132">A volte è possibile che si desideri eliminare definitivamente un gruppo senza attendere la scadenza del periodo di cancellazione di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="a4344-132">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="a4344-133">A tale scopo, avviare PowerShell ed eseguire questo comando per ottenere l'ID oggetto del gruppo:</span><span class="sxs-lookup"><span data-stu-id="a4344-133">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="a4344-134">Prendere nota dell'ID oggetto del gruppo o dei gruppi che si desidera eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="a4344-134">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a4344-135">Il gruppo e i dati che contiene vengono eliminati in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="a4344-135">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="a4344-136">Per eliminare il gruppo, eseguire questo comando in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a4344-136">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="a4344-p105">Per verificare che il gruppo sia stato eliminato correttamente, eseguire di nuovo il cmdlet  *Get-AzureADMSDeletedGroup*  per controllare che il gruppo non compaia più nell'elenco dei gruppi eliminati temporaneamente. In alcuni casi l'eliminazione definitiva del gruppo e di tutti i suoi dati può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="a4344-p105">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="a4344-139">Hai domande sui gruppi di Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="a4344-139">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="a4344-140">Visitare la [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per inviare domande e partecipare a conversazioni sui gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a4344-140">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="a4344-141">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="a4344-141">Related articles</span></span>

[<span data-ttu-id="a4344-142">Gestire i gruppi Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4344-142">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="a4344-143">Eliminare gruppi usando il cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="a4344-143">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="a4344-144">Gestire le impostazioni del sito del team connesso al gruppo</span><span class="sxs-lookup"><span data-stu-id="a4344-144">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="a4344-145">Eliminare un gruppo in Outlook</span><span class="sxs-lookup"><span data-stu-id="a4344-145">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
