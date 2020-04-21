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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Informazioni su come ripristinare un gruppo di Microsoft 365 eliminato.
ms.openlocfilehash: a0e7aef090528b3fa183fe08f9c4d06c86f94a10
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630032"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="4e28f-103">Ripristinare un gruppo eliminato</span><span class="sxs-lookup"><span data-stu-id="4e28f-103">Restore a deleted Group</span></span>

<span data-ttu-id="4e28f-104">Se si è eliminato un gruppo, questo verrà mantenuto per 30 giorni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4e28f-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="4e28f-105">Questo periodo di 30 giorni è considerato "soft-delete" perché è ancora possibile ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="4e28f-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="4e28f-106">Dopo 30 giorni, il gruppo e il relativo contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="4e28f-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="4e28f-107">Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e28f-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="4e28f-108">Oggetto, proprietà e membri di Azure Active Directory (AD) Microsoft 365 groups.</span><span class="sxs-lookup"><span data-stu-id="4e28f-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="4e28f-109">Indirizzi di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4e28f-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="4e28f-110">Posta in arrivo condivisa e calendario di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4e28f-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="4e28f-111">Sito e file del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4e28f-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="4e28f-112">Blocco appunti di OneNote</span><span class="sxs-lookup"><span data-stu-id="4e28f-112">OneNote notebook</span></span>
    
- <span data-ttu-id="4e28f-113">Planner</span><span class="sxs-lookup"><span data-stu-id="4e28f-113">Planner</span></span>
    
- <span data-ttu-id="4e28f-114">Teams</span><span class="sxs-lookup"><span data-stu-id="4e28f-114">Teams</span></span>

- <span data-ttu-id="4e28f-115">Gruppo di Yammer e contenuto del gruppo (se il gruppo Microsoft 365 è stato creato da Yammer)</span><span class="sxs-lookup"><span data-stu-id="4e28f-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="4e28f-116">Ripristinare un gruppo personalizzato tramite Outlook</span><span class="sxs-lookup"><span data-stu-id="4e28f-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="4e28f-117">Se si è il proprietario di un gruppo di Microsoft 365, è possibile ripristinare il gruppo manualmente in Outlook attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="4e28f-117">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="4e28f-118">Nella [pagina Gruppi eliminati](https://outlook.office.com/people/group/deleted)selezionare l'opzione **Gestisci gruppi** nel nodo **gruppi** e quindi scegliere **eliminata**.</span><span class="sxs-lookup"><span data-stu-id="4e28f-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="4e28f-119">Fare clic sulla scheda **Ripristina** accanto al gruppo che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="4e28f-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="4e28f-120">Se il gruppo eliminato non viene visualizzato, contattare un amministratore.</span><span class="sxs-lookup"><span data-stu-id="4e28f-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="4e28f-121">Ripristinare un gruppo nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e28f-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="4e28f-122">Se si è amministratori globali o amministratori di gruppi, è possibile ripristinare un gruppo eliminato nell'interfaccia di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="4e28f-122">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="4e28f-123">Accedere all'interfaccia di [Amministrazione](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4e28f-123">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="4e28f-124">Espandere **gruppi**e quindi fare clic su **gruppi eliminati**.</span><span class="sxs-lookup"><span data-stu-id="4e28f-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="4e28f-125">Selezionare il gruppo che si desidera ripristinare e quindi fare clic su **Ripristina gruppo**.</span><span class="sxs-lookup"><span data-stu-id="4e28f-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="4e28f-126">Eliminare definitivamente un gruppo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e28f-126">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="4e28f-127">A volte è possibile che si desideri eliminare definitivamente un gruppo senza attendere la scadenza del periodo di cancellazione di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="4e28f-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="4e28f-128">A tale scopo, avviare PowerShell ed eseguire questo comando per ottenere l'ID oggetto del gruppo:</span><span class="sxs-lookup"><span data-stu-id="4e28f-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="4e28f-129">Prendere nota dell'ID oggetto del gruppo o dei gruppi che si desidera eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="4e28f-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4e28f-130">Il gruppo e i dati che contiene vengono eliminati in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="4e28f-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="4e28f-131">Per eliminare il gruppo, eseguire questo comando in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4e28f-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="4e28f-p103">Per verificare che il gruppo sia stato eliminato correttamente, eseguire di nuovo il cmdlet  *Get-AzureADMSDeletedGroup*  per controllare che il gruppo non compaia più nell'elenco dei gruppi eliminati temporaneamente. In alcuni casi l'eliminazione definitiva del gruppo e di tutti i suoi dati può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="4e28f-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="4e28f-134">Hai domande sui gruppi di Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="4e28f-134">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="4e28f-135">Visitare la [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per inviare domande e partecipare a conversazioni sui gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e28f-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="4e28f-136">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="4e28f-136">Related articles</span></span>

[<span data-ttu-id="4e28f-137">Gestire i gruppi Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e28f-137">Manage Microsoft 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="4e28f-138">Eliminare gruppi usando il cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="4e28f-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="4e28f-139">Gestire le impostazioni del sito del team connesso al gruppo</span><span class="sxs-lookup"><span data-stu-id="4e28f-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="4e28f-140">Eliminare un gruppo in Outlook</span><span class="sxs-lookup"><span data-stu-id="4e28f-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
