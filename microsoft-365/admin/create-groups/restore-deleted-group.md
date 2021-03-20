---
title: Ripristinare un gruppo di Microsoft 365 eliminato
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910547"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="08656-103">Ripristinare un gruppo di Microsoft 365 eliminato</span><span class="sxs-lookup"><span data-stu-id="08656-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="08656-104">Se un gruppo è stato eliminato, verrà conservato per 30 giorni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="08656-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="08656-105">Questo periodo di 30 giorni è considerato una "eliminazione recidiva" perché è comunque possibile ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="08656-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="08656-106">Dopo 30 giorni, il gruppo e il contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="08656-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="08656-107">Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:</span><span class="sxs-lookup"><span data-stu-id="08656-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="08656-108">Oggetti, proprietà e membri di Azure Active Directory (AD) Gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08656-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="08656-109">Indirizzi di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="08656-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="08656-110">Posta in arrivo condivisa di Exchange Online e calendario.</span><span class="sxs-lookup"><span data-stu-id="08656-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="08656-111">File e sito del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="08656-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="08656-112">Blocco appunti di OneNote</span><span class="sxs-lookup"><span data-stu-id="08656-112">OneNote notebook</span></span>
    
- <span data-ttu-id="08656-113">Planner</span><span class="sxs-lookup"><span data-stu-id="08656-113">Planner</span></span>
    
- <span data-ttu-id="08656-114">Teams</span><span class="sxs-lookup"><span data-stu-id="08656-114">Teams</span></span>

- <span data-ttu-id="08656-115">Contenuto del gruppo e del gruppo di Yammer (se il gruppo di Microsoft 365 è stato creato da Yammer)</span><span class="sxs-lookup"><span data-stu-id="08656-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="08656-116">In questo articolo viene descritto il ripristino solo dei gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08656-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="08656-117">Non è possibile ripristinare tutti gli altri gruppi dopo l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="08656-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="08656-118">Ripristinare un gruppo</span><span class="sxs-lookup"><span data-stu-id="08656-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="08656-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="08656-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="08656-120">Se si è proprietari di un gruppo di Microsoft 365, è possibile ripristinare manualmente il gruppo in Outlook sul Web seguendo questa procedura:</span><span class="sxs-lookup"><span data-stu-id="08656-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="08656-121">Nella pagina Gruppi [eliminati](https://outlook.office.com/people/group/deleted)selezionare l'opzione  **Gestisci** gruppi nel nodo Gruppi e quindi scegliere **Eliminato.**</span><span class="sxs-lookup"><span data-stu-id="08656-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="08656-122">Fare clic **sulla scheda** Ripristina accanto al gruppo che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="08656-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="08656-123">Se il gruppo eliminato non viene visualizzato qui, contattare un amministratore.</span><span class="sxs-lookup"><span data-stu-id="08656-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="08656-124">Interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="08656-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="08656-125">Se si è un amministratore globale o un amministratore di gruppi, è possibile ripristinare un gruppo eliminato nell'interfaccia di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="08656-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="08656-126">Passare all'[interfaccia di amministrazione](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="08656-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="08656-127">Espandere **Gruppi** e quindi fare clic su **Gruppi eliminati.**</span><span class="sxs-lookup"><span data-stu-id="08656-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="08656-128">Selezionare il gruppo che si desidera ripristinare e quindi fare clic **su Ripristina gruppo.**</span><span class="sxs-lookup"><span data-stu-id="08656-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="08656-129">In alcuni casi, il ripristino del gruppo e di tutti i relativi dati può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="08656-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="08656-130">Domande sui gruppi di Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="08656-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="08656-131">Visitare la [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per inviare domande e partecipare a conversazioni sui gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08656-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="08656-132">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="08656-132">Related articles</span></span>

[<span data-ttu-id="08656-133">Gestire i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="08656-133">Manage Microsoft 365 Groups with PowerShell</span></span>](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[<span data-ttu-id="08656-134">Eliminare gruppi usando il cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="08656-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](/powershell/module/exchange/remove-unifiedgroup)
  
[<span data-ttu-id="08656-135">Gestire le impostazioni del sito del team connesso al gruppo</span><span class="sxs-lookup"><span data-stu-id="08656-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="08656-136">Eliminare un gruppo in Outlook</span><span class="sxs-lookup"><span data-stu-id="08656-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)