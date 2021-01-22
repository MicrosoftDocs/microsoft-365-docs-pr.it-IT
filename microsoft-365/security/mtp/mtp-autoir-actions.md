---
title: Approvare o rifiutare le azioni in sospeso in seguito a un'indagine automatizzata
description: Utilizzare il centro notifiche per gestire le azioni relative all’analisi e alla risposta automatizzate
keywords: azione, centro, autoair, automatizzato, indagine, risposta, correzione
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930379"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="383ac-104">Approvare o rifiutare le azioni in sospeso in seguito a un'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="383ac-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="383ac-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="383ac-105">**Applies to:**</span></span>
- <span data-ttu-id="383ac-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="383ac-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="383ac-107">Quando viene eseguita un’indagine automatizzata, può dare come risultato una o più [azioni di correzione](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) che richiedono l’approvazione prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="383ac-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="383ac-108">Ad esempio, potrebbe essere necessario eliminare un gruppo di email o potrebbe essere necessario eliminare un file in quarantena.</span><span class="sxs-lookup"><span data-stu-id="383ac-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="383ac-109">È importante approvare (o rifiutare) le azioni in sospeso il prima possibile in modo che l’indagine automatizzata possa essere completata nel tempo previsto.</span><span class="sxs-lookup"><span data-stu-id="383ac-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="383ac-110">Se ritieni che qualcosa sia stato perso o rilevato in modo errato dalle funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender, contattaci.</span><span class="sxs-lookup"><span data-stu-id="383ac-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="383ac-111">Vedere Come segnalare falsi positivi/negativi nelle funzionalità di analisi e risposta [automatizzate (AIR) in Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="383ac-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="383ac-112">Le azioni in sospeso possono essere esaminate e approvate utilizzando il centro [notifiche](#review-a-pending-action-in-the-action-center) o la [visualizzazione dei dettagli dell'indagine.](#review-a-pending-action-in-the-investigation-details-view)</span><span class="sxs-lookup"><span data-stu-id="383ac-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="383ac-113">È necessario avere [autorizzazioni appropriate](mtp-action-center.md#required-permissions-for-action-center-tasks) per approvare o rifiutare azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="383ac-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="383ac-114">Per ulteriori informazioni, vedere [Prerequisiti per l'analisi e la risposta automatizzate in Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="383ac-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="383ac-115">Rivedere un'azione in sospeso nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="383ac-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="383ac-116">Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l’accesso.</span><span class="sxs-lookup"><span data-stu-id="383ac-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="383ac-117">Nel riquadro di spostamento fare clic su **Centro notifiche**.</span><span class="sxs-lookup"><span data-stu-id="383ac-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="383ac-118">Nel centro notifiche, nella scheda **In sospeso**, selezionare un elemento dall’elenco.</span><span class="sxs-lookup"><span data-stu-id="383ac-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="383ac-119">Se si seleziona un elemento nella colonna **Numero indagine**, verrà visualizzata la pagina con i dettagli sulle indagini.</span><span class="sxs-lookup"><span data-stu-id="383ac-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="383ac-120">In questa pagina è possibile visualizzare i risultati dell'indagine e quindi approvare o rifiutare l'azione consigliata.</span><span class="sxs-lookup"><span data-stu-id="383ac-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="383ac-121">Se si seleziona una riga nell'elenco, verrà visualizzato un riquadro a comparsa, in cui sarà possibile vedere le informazioni su quell'elemento.</span><span class="sxs-lookup"><span data-stu-id="383ac-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Approvare o rifiutare un’azione](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="383ac-123">Utilizzare i collegamenti per visualizzare un avviso associato o un’indagine e approvare o rifiutare l’azione.</span><span class="sxs-lookup"><span data-stu-id="383ac-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="383ac-124">Rivedere un'azione in sospeso nella visualizzazione dettagli indagini</span><span class="sxs-lookup"><span data-stu-id="383ac-124">Review a pending action in the investigation details view</span></span>

![Dettagli indagine](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="383ac-126">In una pagina di [investigazione dettagli](mtp-autoir-results.md), selezionare la scheda **azioni in sospeso** (o **Azioni**). Gli elementi in attesa di approvazione sono elencati in questa scheda.</span><span class="sxs-lookup"><span data-stu-id="383ac-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="383ac-127">Selezionare un elemento nella lista, quindi scegliere **Approva** o **Rifiuta**.</span><span class="sxs-lookup"><span data-stu-id="383ac-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="undo-completed-actions"></a><span data-ttu-id="383ac-128">Annullamento delle azioni completate</span><span class="sxs-lookup"><span data-stu-id="383ac-128">Undo completed actions</span></span>

<span data-ttu-id="383ac-129">Se hai determinato che un dispositivo o un file non è una minaccia, puoi annullare le azioni di correzione eseguite, indipendentemente dal fatto che siano state eseguite automaticamente o manualmente.</span><span class="sxs-lookup"><span data-stu-id="383ac-129">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="383ac-130">Nella scheda Cronologia del  centro notifiche è possibile annullare una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="383ac-130">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="383ac-131">Origine azione</span><span class="sxs-lookup"><span data-stu-id="383ac-131">Action source</span></span> | <span data-ttu-id="383ac-132">Azioni supportate</span><span class="sxs-lookup"><span data-stu-id="383ac-132">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="383ac-133">- Indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="383ac-133">- Automated investigation</span></span> <br/><span data-ttu-id="383ac-134">- Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="383ac-134">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="383ac-135">- Azioni di risposta manuali</span><span class="sxs-lookup"><span data-stu-id="383ac-135">- Manual response actions</span></span> | <span data-ttu-id="383ac-136">- Isolare il dispositivo</span><span class="sxs-lookup"><span data-stu-id="383ac-136">- Isolate device</span></span> <br/><span data-ttu-id="383ac-137">- Limitare l'esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="383ac-137">- Restrict code execution</span></span> <br/><span data-ttu-id="383ac-138">- Mettere in quarantena un file</span><span class="sxs-lookup"><span data-stu-id="383ac-138">- Quarantine a file</span></span> <br/><span data-ttu-id="383ac-139">- Rimuovere una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="383ac-139">- Remove a registry key</span></span> <br/><span data-ttu-id="383ac-140">- Arrestare un servizio</span><span class="sxs-lookup"><span data-stu-id="383ac-140">- Stop a service</span></span> <br/><span data-ttu-id="383ac-141">- Disabilitare un driver</span><span class="sxs-lookup"><span data-stu-id="383ac-141">- Disable a driver</span></span> <br/><span data-ttu-id="383ac-142">- Rimuovere un'attività pianificata</span><span class="sxs-lookup"><span data-stu-id="383ac-142">- Remove a scheduled task</span></span> |

### <a name="to-undo-a-remediation-action"></a><span data-ttu-id="383ac-143">Per annullare un'azione correttiva</span><span class="sxs-lookup"><span data-stu-id="383ac-143">To undo a remediation action</span></span>

1. <span data-ttu-id="383ac-144">Accedere al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="383ac-144">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="383ac-145">Nella scheda **Cronologia** selezionare un'azione che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="383ac-145">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="383ac-146">Nel riquadro sul lato destro dello schermo selezionare **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="383ac-146">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="383ac-147">Per rimuovere un file dalla quarantena su più dispositivi</span><span class="sxs-lookup"><span data-stu-id="383ac-147">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="383ac-148">Accedere al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="383ac-148">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="383ac-149">Nella scheda **Cronologia** selezionare un file con il tipo di azione **File quarantena.**</span><span class="sxs-lookup"><span data-stu-id="383ac-149">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="383ac-150">Nel riquadro sul lato destro dello schermo, selezionare Applica a X altre istanze del **file,** quindi scegliere **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="383ac-150">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="383ac-151">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="383ac-151">Next steps</span></span>

- [<span data-ttu-id="383ac-152">Visualizzare i dettagli e i risultati di un'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="383ac-152">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="383ac-153">Gestire falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="383ac-153">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
