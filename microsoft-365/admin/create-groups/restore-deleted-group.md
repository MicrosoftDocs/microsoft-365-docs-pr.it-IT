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
ms.openlocfilehash: 8fb2cb3afdf390efae7854a040bb56df731cceaf
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307188"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="b3916-103">Ripristinare un gruppo eliminato</span><span class="sxs-lookup"><span data-stu-id="b3916-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b3916-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="b3916-104">The admin center is changing.</span></span> <span data-ttu-id="b3916-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="b3916-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b3916-106">Se si è eliminato un gruppo, questo verrà mantenuto per 30 giorni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b3916-106">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="b3916-107">Questo periodo di 30 giorni è considerato "soft-delete" perché è ancora possibile ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="b3916-107">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="b3916-108">Dopo 30 giorni, il gruppo e il relativo contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="b3916-108">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="b3916-109">Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3916-109">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="b3916-110">Oggetto, proprietà e membri di Azure Active Directory (AD) Microsoft 365 groups.</span><span class="sxs-lookup"><span data-stu-id="b3916-110">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="b3916-111">Indirizzi di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b3916-111">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="b3916-112">Posta in arrivo condivisa e calendario di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b3916-112">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="b3916-113">Sito e file del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b3916-113">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="b3916-114">Blocco appunti di OneNote</span><span class="sxs-lookup"><span data-stu-id="b3916-114">OneNote notebook</span></span>
    
- <span data-ttu-id="b3916-115">Planner</span><span class="sxs-lookup"><span data-stu-id="b3916-115">Planner</span></span>
    
- <span data-ttu-id="b3916-116">Teams</span><span class="sxs-lookup"><span data-stu-id="b3916-116">Teams</span></span>

- <span data-ttu-id="b3916-117">Gruppo di Yammer e contenuto del gruppo (se il gruppo Microsoft 365 è stato creato da Yammer)</span><span class="sxs-lookup"><span data-stu-id="b3916-117">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="b3916-118">Ripristinare un gruppo personalizzato tramite Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="b3916-118">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="b3916-119">Se si è il proprietario di un gruppo di Microsoft 365, è possibile ripristinare il gruppo manualmente in Outlook sul Web attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b3916-119">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="b3916-120">Nella [pagina Gruppi eliminati](https://outlook.office.com/people/group/deleted)selezionare l'opzione **Gestisci gruppi** nel nodo **gruppi** e quindi scegliere **eliminata**.</span><span class="sxs-lookup"><span data-stu-id="b3916-120">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="b3916-121">Fare clic sulla scheda **Ripristina** accanto al gruppo che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="b3916-121">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="b3916-122">Se il gruppo eliminato non viene visualizzato, contattare un amministratore.</span><span class="sxs-lookup"><span data-stu-id="b3916-122">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b3916-123">Ripristinare un gruppo nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3916-123">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b3916-124">Se si è amministratori globali o amministratori di gruppi, è possibile ripristinare un gruppo eliminato nell'interfaccia di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="b3916-124">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="b3916-125">Passare all'[interfaccia di amministrazione](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b3916-125">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="b3916-126">Espandere **gruppi**e quindi fare clic su **gruppi eliminati**.</span><span class="sxs-lookup"><span data-stu-id="b3916-126">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="b3916-127">Selezionare il gruppo che si desidera ripristinare e quindi fare clic su **Ripristina gruppo**.</span><span class="sxs-lookup"><span data-stu-id="b3916-127">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="b3916-128">In alcuni casi, può richiedere fino a 24 ore prima che il gruppo e tutti i relativi dati vengano ripristinati.</span><span class="sxs-lookup"><span data-stu-id="b3916-128">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="b3916-129">Eliminare definitivamente un gruppo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b3916-129">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="b3916-130">A volte è possibile che si desideri eliminare definitivamente un gruppo senza attendere la scadenza del periodo di cancellazione di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="b3916-130">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="b3916-131">A tale scopo, avviare PowerShell ed eseguire questo comando per ottenere l'ID oggetto del gruppo:</span><span class="sxs-lookup"><span data-stu-id="b3916-131">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="b3916-132">Prendere nota dell'ID oggetto del gruppo o dei gruppi che si desidera eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="b3916-132">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b3916-133">Il gruppo e i dati che contiene vengono eliminati in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="b3916-133">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="b3916-134">Per eliminare il gruppo, eseguire questo comando in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b3916-134">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="b3916-p104">Per verificare che il gruppo sia stato eliminato correttamente, eseguire di nuovo il cmdlet  *Get-AzureADMSDeletedGroup*  per controllare che il gruppo non compaia più nell'elenco dei gruppi eliminati temporaneamente. In alcuni casi l'eliminazione definitiva del gruppo e di tutti i suoi dati può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="b3916-p104">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="b3916-137">Hai domande sui gruppi di Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="b3916-137">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="b3916-138">Visitare la [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per inviare domande e partecipare a conversazioni sui gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3916-138">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="b3916-139">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b3916-139">Related articles</span></span>

[<span data-ttu-id="b3916-140">Gestire i gruppi Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3916-140">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="b3916-141">Eliminare gruppi usando il cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="b3916-141">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="b3916-142">Gestire le impostazioni del sito del team connesso al gruppo</span><span class="sxs-lookup"><span data-stu-id="b3916-142">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="b3916-143">Eliminare un gruppo in Outlook</span><span class="sxs-lookup"><span data-stu-id="b3916-143">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
