---
title: Ripristinare un gruppo di Office 365 eliminato
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
description: Informazioni su come ripristinare un gruppo di Office 365 eliminato.
ms.openlocfilehash: 31d6481f87d7da219e042eefa8f004425caee133
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583163"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="a7ce2-103">Ripristinare un gruppo di Office 365 eliminato</span><span class="sxs-lookup"><span data-stu-id="a7ce2-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="a7ce2-104">Se si è eliminato un gruppo, questo verrà mantenuto per 30 giorni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="a7ce2-105">Questo periodo di 30 giorni è considerato "soft-delete" perché è ancora possibile ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="a7ce2-106">Dopo 30 giorni, il gruppo e il relativo contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="a7ce2-107">Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7ce2-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="a7ce2-108">Gli oggetti, le proprietà e i membri di Azure Active Directory (AD) Office 365 gruppi.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-108">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="a7ce2-109">Indirizzi di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="a7ce2-110">Posta in arrivo condivisa e calendario di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="a7ce2-111">Sito e file del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="a7ce2-112">Blocco appunti di OneNote</span><span class="sxs-lookup"><span data-stu-id="a7ce2-112">OneNote notebook</span></span>
    
- <span data-ttu-id="a7ce2-113">Planner</span><span class="sxs-lookup"><span data-stu-id="a7ce2-113">Planner</span></span>
    
- <span data-ttu-id="a7ce2-114">Teams</span><span class="sxs-lookup"><span data-stu-id="a7ce2-114">Teams</span></span>

- <span data-ttu-id="a7ce2-115">Gruppo di Yammer e contenuto del gruppo (se il gruppo di Office 365 è stato creato da Yammer)</span><span class="sxs-lookup"><span data-stu-id="a7ce2-115">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="a7ce2-116">Ripristinare un gruppo personalizzato tramite Outlook</span><span class="sxs-lookup"><span data-stu-id="a7ce2-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="a7ce2-117">Se si è il proprietario di un gruppo di Office 365, è possibile ripristinare il gruppo manualmente in Outlook attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a7ce2-117">If you are the owner of an Office 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="a7ce2-118">Nella [pagina Gruppi eliminati](https://outlook.office.com/people/group/deleted)selezionare l'opzione **Gestisci gruppi** nel nodo **gruppi** e quindi scegliere **eliminata**.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="a7ce2-119">Fare clic sulla scheda **Ripristina** accanto al gruppo che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="a7ce2-120">Se il gruppo eliminato non viene visualizzato, contattare un amministratore.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a7ce2-121">Ripristinare un gruppo nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7ce2-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a7ce2-122">Se si è amministratori globali o gruppi, è possibile ripristinare un gruppo eliminato nell'interfaccia di amministrazione di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="a7ce2-122">If you are a global administrator or a groups admin, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="a7ce2-123">Passare all’interfaccia di amministrazione su [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a7ce2-123">Go to the admin center at [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="a7ce2-124">Espandere **gruppi**e quindi fare clic su **gruppi eliminati**.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="a7ce2-125">Selezionare il gruppo che si desidera ripristinare e quindi fare clic su **Ripristina gruppo**.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="a7ce2-126">Eliminare definitivamente un gruppo di Office 365</span><span class="sxs-lookup"><span data-stu-id="a7ce2-126">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="a7ce2-127">A volte è possibile che si desideri eliminare definitivamente un gruppo senza attendere la scadenza del periodo di cancellazione di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="a7ce2-128">A tale scopo, avviare PowerShell ed eseguire questo comando per ottenere l'ID oggetto del gruppo:</span><span class="sxs-lookup"><span data-stu-id="a7ce2-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="a7ce2-129">Prendere nota dell'ID oggetto del gruppo o dei gruppi che si desidera eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a7ce2-130">Il gruppo e i dati che contiene vengono eliminati in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="a7ce2-131">Per eliminare il gruppo, eseguire questo comando in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a7ce2-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="a7ce2-p103">Per verificare che il gruppo sia stato eliminato correttamente, eseguire di nuovo il cmdlet  *Get-AzureADMSDeletedGroup*  per controllare che il gruppo non compaia più nell'elenco dei gruppi eliminati temporaneamente. In alcuni casi l'eliminazione definitiva del gruppo e di tutti i suoi dati può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="a7ce2-134">Domande su Gruppi di Office 365?</span><span class="sxs-lookup"><span data-stu-id="a7ce2-134">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="a7ce2-135">Visitare la [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per inviare domande e partecipare a conversazioni sui gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a7ce2-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="a7ce2-136">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="a7ce2-136">Related articles</span></span>

[<span data-ttu-id="a7ce2-137">Gestire Gruppi di Office 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7ce2-137">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="a7ce2-138">Eliminare gruppi usando il cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="a7ce2-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="a7ce2-139">Gestire le impostazioni del sito del team connesso al gruppo</span><span class="sxs-lookup"><span data-stu-id="a7ce2-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="a7ce2-140">Eliminare un gruppo in Outlook</span><span class="sxs-lookup"><span data-stu-id="a7ce2-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
