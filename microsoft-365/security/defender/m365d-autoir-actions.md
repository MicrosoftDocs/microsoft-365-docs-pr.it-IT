---
title: Visualizzare e gestire le azioni nel centro notifiche
description: Utilizzare il Centro notifiche per visualizzare e gestire le azioni correttive
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7106f5d2e740d2b4cacbcaeb0b9391095bbeb356
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592025"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="74a43-104">Visualizzare e gestire le azioni nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="74a43-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="74a43-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="74a43-105">**Applies to:**</span></span>
- <span data-ttu-id="74a43-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74a43-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="74a43-107">Le funzionalità di protezione dalle minacce in Microsoft 365 Defender possono comportare determinate azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="74a43-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="74a43-108">Di seguito vengono descritti alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="74a43-108">Here are some examples:</span></span>
- <span data-ttu-id="74a43-109">[Le indagini automatizzate](m365d-autoir.md) possono comportare azioni di correzione eseguite automaticamente o in attesa di approvazione.</span><span class="sxs-lookup"><span data-stu-id="74a43-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await approval.</span></span>
- <span data-ttu-id="74a43-110">Antivirus, antimalware e altre funzionalità di protezione dalle minacce possono comportare azioni di correzione, ad esempio il blocco di un file, un URL o un processo o l'invio di un artefatto in quarantena.</span><span class="sxs-lookup"><span data-stu-id="74a43-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="74a43-111">Il team delle operazioni di sicurezza può eseguire [](advanced-hunting-overview.md) azioni di correzione manualmente, ad esempio durante la ricerca avanzata o durante l'analisi [di avvisi](investigate-alerts.md) [o incidenti.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="74a43-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="74a43-112">È necessario avere [autorizzazioni appropriate](m365d-action-center.md#required-permissions-for-action-center-tasks) per approvare o rifiutare azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="74a43-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="74a43-113">Per ulteriori informazioni, vedere [Prerequisites for automated investigation and response in Microsoft 365 Defender.](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="74a43-113">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="74a43-114">Esaminare le azioni in sospeso nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="74a43-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="74a43-115">È importante approvare (o rifiutare) le azioni in sospeso il prima possibile in modo che l’indagine automatizzata possa essere completata nel tempo previsto.</span><span class="sxs-lookup"><span data-stu-id="74a43-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

![Approvare o rifiutare un’azione](../../media/air-actioncenter-itemselected.png)

1. <span data-ttu-id="74a43-117">Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="74a43-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="74a43-118">Nel riquadro di spostamento fare clic su **Centro notifiche**.</span><span class="sxs-lookup"><span data-stu-id="74a43-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="74a43-119">Nel centro notifiche, nella scheda **In sospeso**, selezionare un elemento dall’elenco.</span><span class="sxs-lookup"><span data-stu-id="74a43-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="74a43-120">Verrà visualizzato il riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="74a43-120">Its flyout pane opens.</span></span>

4. <span data-ttu-id="74a43-121">Esaminare le informazioni nel riquadro a comparsa e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74a43-121">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="74a43-122">Selezionare **Apri pagina di indagine** per visualizzare ulteriori dettagli sull'indagine.</span><span class="sxs-lookup"><span data-stu-id="74a43-122">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="74a43-123">Selezionare **Approva** per avviare un'azione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="74a43-123">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="74a43-124">Selezionare **Rifiuta** per impedire l'esecuzione di un'azione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="74a43-124">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="74a43-125">Seleziona **Vai a ricerca** per passare a Ricerca [avanzata.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="74a43-125">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="74a43-126">Annullare le azioni completate</span><span class="sxs-lookup"><span data-stu-id="74a43-126">Undo completed actions</span></span>

<span data-ttu-id="74a43-127">Se hai determinato che un dispositivo o un file non è una minaccia, puoi annullare le azioni di correzione eseguite, indipendentemente dal fatto che tali azioni siano state eseguite automaticamente o manualmente.</span><span class="sxs-lookup"><span data-stu-id="74a43-127">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="74a43-128">Nel centro notifiche, nella **scheda Cronologia,** è possibile annullare una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74a43-128">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="74a43-129">Origine azione</span><span class="sxs-lookup"><span data-stu-id="74a43-129">Action source</span></span> | <span data-ttu-id="74a43-130">Azioni supportate</span><span class="sxs-lookup"><span data-stu-id="74a43-130">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="74a43-131">- Indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="74a43-131">- Automated investigation</span></span> <br/><span data-ttu-id="74a43-132">- Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="74a43-132">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="74a43-133">- Azioni di risposta manuale</span><span class="sxs-lookup"><span data-stu-id="74a43-133">- Manual response actions</span></span> | <span data-ttu-id="74a43-134">- Isola dispositivo</span><span class="sxs-lookup"><span data-stu-id="74a43-134">- Isolate device</span></span> <br/><span data-ttu-id="74a43-135">- Limitare l'esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="74a43-135">- Restrict code execution</span></span> <br/><span data-ttu-id="74a43-136">- Mettere in quarantena un file</span><span class="sxs-lookup"><span data-stu-id="74a43-136">- Quarantine a file</span></span> <br/><span data-ttu-id="74a43-137">- Rimuovere una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="74a43-137">- Remove a registry key</span></span> <br/><span data-ttu-id="74a43-138">- Arrestare un servizio</span><span class="sxs-lookup"><span data-stu-id="74a43-138">- Stop a service</span></span> <br/><span data-ttu-id="74a43-139">- Disabilitare un driver</span><span class="sxs-lookup"><span data-stu-id="74a43-139">- Disable a driver</span></span> <br/><span data-ttu-id="74a43-140">- Rimuovere un'attività pianificata</span><span class="sxs-lookup"><span data-stu-id="74a43-140">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="74a43-141">Annullare un'azione di correzione</span><span class="sxs-lookup"><span data-stu-id="74a43-141">Undo one remediation action</span></span>

1. <span data-ttu-id="74a43-142">Vai al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedi.</span><span class="sxs-lookup"><span data-stu-id="74a43-142">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="74a43-143">Nella scheda **Cronologia** selezionare un'azione che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="74a43-143">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="74a43-144">Nel riquadro sul lato destro dello schermo selezionare **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="74a43-144">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="74a43-145">Annullare più azioni di correzione</span><span class="sxs-lookup"><span data-stu-id="74a43-145">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="74a43-146">Passare al centro notifiche ( https://security.microsoft.com/action-center) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="74a43-146">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="74a43-147">Nella scheda **Cronologia** selezionare le azioni che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="74a43-147">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="74a43-148">Assicurarsi di selezionare gli elementi con lo stesso tipo di azione.</span><span class="sxs-lookup"><span data-stu-id="74a43-148">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="74a43-149">Verrà visualizzato un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="74a43-149">A flyout pane opens.</span></span>

3. <span data-ttu-id="74a43-150">Nel riquadro a comparsa selezionare **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="74a43-150">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="74a43-151">Per rimuovere un file dalla quarantena su più dispositivi</span><span class="sxs-lookup"><span data-stu-id="74a43-151">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="74a43-152">Vai al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedi.</span><span class="sxs-lookup"><span data-stu-id="74a43-152">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="74a43-153">Nella scheda **Cronologia** selezionare un file con il tipo di azione **File quarantena.**</span><span class="sxs-lookup"><span data-stu-id="74a43-153">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="74a43-154">Nel riquadro sul lato destro dello schermo, selezionare Applica a X altre istanze **del file** e quindi scegliere **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="74a43-154">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="74a43-155">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="74a43-155">Next steps</span></span>

- [<span data-ttu-id="74a43-156">Visualizzare i dettagli e i risultati di un'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="74a43-156">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="74a43-157">Scopri come gestire i falsi positivi/negativi (se ne ottieni uno)</span><span class="sxs-lookup"><span data-stu-id="74a43-157">Learn how to handle false positives/negatives (if you get one)</span></span>](m365d-autoir-report-false-positives-negatives.md)
