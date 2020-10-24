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
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753244"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="43635-103">Ripristinare un gruppo di Microsoft 365 eliminato</span><span class="sxs-lookup"><span data-stu-id="43635-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="43635-104">Se si è eliminato un gruppo, questo verrà mantenuto per 30 giorni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="43635-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="43635-105">Questo periodo di 30 giorni è considerato "soft-delete" perché è ancora possibile ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="43635-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="43635-106">Dopo 30 giorni, il gruppo e il relativo contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="43635-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="43635-107">Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:</span><span class="sxs-lookup"><span data-stu-id="43635-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="43635-108">Oggetto, proprietà e membri di Azure Active Directory (AD) Microsoft 365 groups.</span><span class="sxs-lookup"><span data-stu-id="43635-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="43635-109">Indirizzi di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="43635-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="43635-110">Posta in arrivo condivisa e calendario di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="43635-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="43635-111">Sito e file del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="43635-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="43635-112">Blocco appunti di OneNote</span><span class="sxs-lookup"><span data-stu-id="43635-112">OneNote notebook</span></span>
    
- <span data-ttu-id="43635-113">Planner</span><span class="sxs-lookup"><span data-stu-id="43635-113">Planner</span></span>
    
- <span data-ttu-id="43635-114">Teams</span><span class="sxs-lookup"><span data-stu-id="43635-114">Teams</span></span>

- <span data-ttu-id="43635-115">Gruppo di Yammer e contenuto del gruppo (se il gruppo Microsoft 365 è stato creato da Yammer)</span><span class="sxs-lookup"><span data-stu-id="43635-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="43635-116">In questo articolo viene descritto come ripristinare solo i gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43635-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="43635-117">Non è possibile ripristinare tutti gli altri gruppi una volta eliminati.</span><span class="sxs-lookup"><span data-stu-id="43635-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="43635-118">Ripristinare un gruppo</span><span class="sxs-lookup"><span data-stu-id="43635-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="43635-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="43635-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="43635-120">Se si è il proprietario di un gruppo di Microsoft 365, è possibile ripristinare il gruppo manualmente in Outlook sul Web attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="43635-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="43635-121">Nella [pagina Gruppi eliminati](https://outlook.office.com/people/group/deleted)selezionare l'opzione **Gestisci gruppi** nel nodo **gruppi** e quindi scegliere **eliminata**.</span><span class="sxs-lookup"><span data-stu-id="43635-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="43635-122">Fare clic sulla scheda **Ripristina** accanto al gruppo che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="43635-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="43635-123">Se il gruppo eliminato non viene visualizzato, contattare un amministratore.</span><span class="sxs-lookup"><span data-stu-id="43635-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="43635-124">Interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="43635-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="43635-125">Se si è amministratori globali o amministratori di gruppi, è possibile ripristinare un gruppo eliminato nell'interfaccia di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="43635-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="43635-126">Passare all'[interfaccia di amministrazione](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="43635-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="43635-127">Espandere **gruppi**e quindi fare clic su **gruppi eliminati**.</span><span class="sxs-lookup"><span data-stu-id="43635-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="43635-128">Selezionare il gruppo che si desidera ripristinare e quindi fare clic su **Ripristina gruppo**.</span><span class="sxs-lookup"><span data-stu-id="43635-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="43635-129">In alcuni casi, può richiedere fino a 24 ore prima che il gruppo e tutti i relativi dati vengano ripristinati.</span><span class="sxs-lookup"><span data-stu-id="43635-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="43635-130">Hai domande sui gruppi di Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="43635-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="43635-131">Visitare la [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per inviare domande e partecipare a conversazioni sui gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43635-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="43635-132">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="43635-132">Related articles</span></span>

[<span data-ttu-id="43635-133">Gestire i gruppi Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="43635-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="43635-134">Eliminare gruppi usando il cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="43635-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="43635-135">Gestire le impostazioni del sito del team connesso al gruppo</span><span class="sxs-lookup"><span data-stu-id="43635-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="43635-136">Eliminare un gruppo in Outlook</span><span class="sxs-lookup"><span data-stu-id="43635-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
