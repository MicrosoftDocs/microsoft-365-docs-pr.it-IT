---
title: Approvare o rifiutare le azioni in sospeso dopo un'analisi automatizzata
description: Utilizzare il centro notifiche per gestire le azioni relative all’analisi e alla risposta automatizzate
keywords: azione, centro, autoair, automatizzato, indagine, risposta, correzione
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: dd7ded318c5ab0cf9aad47054ac04d5a2d353943
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199806"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="4000c-104">Approvare o rifiutare le azioni in sospeso dopo un'analisi automatizzata</span><span class="sxs-lookup"><span data-stu-id="4000c-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4000c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4000c-105">**Applies to:**</span></span>
- <span data-ttu-id="4000c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4000c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4000c-107">Quando viene eseguita un’indagine automatizzata, può dare come risultato una o più [azioni di correzione](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) che richiedono l’approvazione prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="4000c-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="4000c-108">Ad esempio, potrebbe essere necessario eliminare un gruppo di email o potrebbe essere necessario eliminare un file in quarantena.</span><span class="sxs-lookup"><span data-stu-id="4000c-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="4000c-109">È importante approvare (o rifiutare) le azioni in sospeso il prima possibile in modo che l’indagine automatizzata possa essere completata nel tempo previsto.</span><span class="sxs-lookup"><span data-stu-id="4000c-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="4000c-110">Se si pensa che qualcosa è stato perso o rilevato erroneamente dalle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection, fatecelo sapere!</span><span class="sxs-lookup"><span data-stu-id="4000c-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="4000c-111">Vedere [How to report false positives/negatives in Automatic Investigation and Response (Air) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="4000c-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="4000c-112">Le azioni in sospeso possono essere esaminate e approvate tramite il [Centro azioni](#review-a-pending-action-in-the-action-center) o la [visualizzazione dettagli analisi](#review-a-pending-action-in-the-investigation-details-view).</span><span class="sxs-lookup"><span data-stu-id="4000c-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="4000c-113">È necessario avere [autorizzazioni appropriate](mtp-action-center.md#required-permissions-for-action-center-tasks) per approvare o rifiutare azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="4000c-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="4000c-114">Rivedere un'azione in sospeso nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="4000c-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="4000c-115">Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l’accesso.</span><span class="sxs-lookup"><span data-stu-id="4000c-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="4000c-116">Nel riquadro di spostamento fare clic su **Centro notifiche**.</span><span class="sxs-lookup"><span data-stu-id="4000c-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="4000c-117">Nel centro notifiche, nella scheda **In sospeso**, selezionare un elemento dall’elenco.</span><span class="sxs-lookup"><span data-stu-id="4000c-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="4000c-118">Se si seleziona un elemento nella colonna **Numero indagine**, verrà visualizzata la pagina con i dettagli sulle indagini.</span><span class="sxs-lookup"><span data-stu-id="4000c-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="4000c-119">In questa pagina è possibile visualizzare i risultati dell'indagine e quindi approvare o rifiutare l'azione consigliata.</span><span class="sxs-lookup"><span data-stu-id="4000c-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="4000c-120">Se si seleziona una riga nell'elenco, verrà visualizzato un riquadro a comparsa, in cui sarà possibile vedere le informazioni su quell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4000c-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Approvare o rifiutare un’azione](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="4000c-122">Utilizzare i collegamenti per visualizzare un avviso associato o un’indagine e approvare o rifiutare l’azione.</span><span class="sxs-lookup"><span data-stu-id="4000c-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="4000c-123">Rivedere un'azione in sospeso nella visualizzazione dettagli indagini</span><span class="sxs-lookup"><span data-stu-id="4000c-123">Review a pending action in the investigation details view</span></span>

![Dettagli indagine](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="4000c-125">In una pagina di [investigazione dettagli](mtp-autoir-results.md), selezionare la scheda **azioni in sospeso** (o **Azioni**). Gli elementi in attesa di approvazione sono elencati in questa scheda.</span><span class="sxs-lookup"><span data-stu-id="4000c-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="4000c-126">Selezionare un elemento nella lista, quindi scegliere **Approva** o **Rifiuta**.</span><span class="sxs-lookup"><span data-stu-id="4000c-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4000c-127">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4000c-127">Next steps</span></span>

- [<span data-ttu-id="4000c-128">Visualizzare i dettagli e i risultati di un'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="4000c-128">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="4000c-129">Gestire i falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="4000c-129">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
