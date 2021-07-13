---
title: Ripristinare un gruppo Microsoft 365 eliminato
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Un gruppo eliminato viene conservato per 30 giorni ed è comunque possibile ripristinarlo. Dopo 30 giorni, il gruppo e il relativo contenuto vengono eliminati definitivamente.
ms.openlocfilehash: ddc3da57c05b7c5f54c10a0cc429c9a3f24b859c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394052"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="22ba4-104">Ripristinare un gruppo Microsoft 365 eliminato</span><span class="sxs-lookup"><span data-stu-id="22ba4-104">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="22ba4-105">Se un gruppo è stato eliminato, verrà conservato per 30 giorni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="22ba4-105">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="22ba4-106">Questo periodo di 30 giorni è considerato una "eliminazione recidiva" perché è comunque possibile ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="22ba4-106">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="22ba4-107">Dopo 30 giorni, il gruppo e il contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="22ba4-107">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="22ba4-108">Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:</span><span class="sxs-lookup"><span data-stu-id="22ba4-108">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="22ba4-109">Azure Active Directory (AD) Microsoft 365 gruppi, proprietà e membri.</span><span class="sxs-lookup"><span data-stu-id="22ba4-109">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="22ba4-110">Indirizzi di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="22ba4-110">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="22ba4-111">Exchange Online posta in arrivo e calendario condivisi.</span><span class="sxs-lookup"><span data-stu-id="22ba4-111">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="22ba4-112">SharePoint File e sito del team online.</span><span class="sxs-lookup"><span data-stu-id="22ba4-112">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="22ba4-113">Blocco appunti di OneNote</span><span class="sxs-lookup"><span data-stu-id="22ba4-113">OneNote notebook</span></span>
    
- <span data-ttu-id="22ba4-114">Planner</span><span class="sxs-lookup"><span data-stu-id="22ba4-114">Planner</span></span>
    
- <span data-ttu-id="22ba4-115">Teams</span><span class="sxs-lookup"><span data-stu-id="22ba4-115">Teams</span></span>

- <span data-ttu-id="22ba4-116">Yammer gruppo e gruppo (se il gruppo Microsoft 365 è stato creato da Yammer)</span><span class="sxs-lookup"><span data-stu-id="22ba4-116">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="22ba4-117">In questo articolo viene descritto il ripristino solo Microsoft 365 gruppi.</span><span class="sxs-lookup"><span data-stu-id="22ba4-117">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="22ba4-118">Non è possibile ripristinare tutti gli altri gruppi dopo l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="22ba4-118">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="22ba4-119">Ripristinare un gruppo</span><span class="sxs-lookup"><span data-stu-id="22ba4-119">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="22ba4-120">Outlook</span><span class="sxs-lookup"><span data-stu-id="22ba4-120">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="22ba4-121">Se si è il proprietario di un Microsoft 365, è possibile ripristinare il gruppo manualmente in Outlook sul web seguendo questa procedura:</span><span class="sxs-lookup"><span data-stu-id="22ba4-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="22ba4-122">Nella pagina Gruppi [eliminati](https://outlook.office.com/people/group/deleted)selezionare l'opzione  **Gestisci** gruppi nel nodo Gruppi e quindi scegliere **Eliminato.**</span><span class="sxs-lookup"><span data-stu-id="22ba4-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="22ba4-123">Fare clic **sulla scheda** Ripristina accanto al gruppo che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="22ba4-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="22ba4-124">Se il gruppo eliminato non viene visualizzato qui, contattare un amministratore.</span><span class="sxs-lookup"><span data-stu-id="22ba4-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="22ba4-125">Interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="22ba4-125">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="22ba4-126">Se si è un amministratore globale o un amministratore di gruppi, è possibile ripristinare un gruppo eliminato nell'interfaccia di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="22ba4-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="22ba4-127">Passare all'[interfaccia di amministrazione](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="22ba4-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="22ba4-128">Espandere **Gruppi** e quindi fare clic su **Gruppi eliminati.**</span><span class="sxs-lookup"><span data-stu-id="22ba4-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="22ba4-129">Selezionare il gruppo che si desidera ripristinare e quindi fare clic **su Ripristina gruppo.**</span><span class="sxs-lookup"><span data-stu-id="22ba4-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="22ba4-130">In alcuni casi, il ripristino del gruppo e di tutti i relativi dati può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="22ba4-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="22ba4-131">Hai domande su Microsoft 365 gruppi?</span><span class="sxs-lookup"><span data-stu-id="22ba4-131">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="22ba4-132">Visitare il [sito Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per inviare domande e partecipare a conversazioni su Microsoft 365 gruppi.</span><span class="sxs-lookup"><span data-stu-id="22ba4-132">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="22ba4-133">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="22ba4-133">Related content</span></span>

<span data-ttu-id="22ba4-134">[Gestire Microsoft 365 gruppi con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="22ba4-134">[Manage Microsoft 365 Groups with PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (article)</span></span>\
<span data-ttu-id="22ba4-135">[Eliminare gruppi utilizzando il cmdlet Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) (articolo)</span><span class="sxs-lookup"><span data-stu-id="22ba4-135">[Delete groups using the Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (article)</span></span>\
<span data-ttu-id="22ba4-136">[Gestire le impostazioni del sito del team](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) connesso al gruppo (articolo)</span><span class="sxs-lookup"><span data-stu-id="22ba4-136">[Manage your group-connected team site settings](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (article)</span></span>\
<span data-ttu-id="22ba4-137">[Eliminare un gruppo in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (articolo)</span><span class="sxs-lookup"><span data-stu-id="22ba4-137">[Delete a group in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (article)</span></span>