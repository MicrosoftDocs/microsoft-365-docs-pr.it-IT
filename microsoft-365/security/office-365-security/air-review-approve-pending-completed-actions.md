---
title: Esaminare e gestire le azioni di correzione in Microsoft Defender per Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automatizzato, indagine, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Informazioni sulle azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 8fc01ab0dd5178032ea7b101f5361c25bb10bbea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028932"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="c74ce-104">Esaminare e gestire le azioni di correzione in Office 365</span><span class="sxs-lookup"><span data-stu-id="c74ce-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="c74ce-105">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="c74ce-105">**Applies to**</span></span>
- [<span data-ttu-id="c74ce-106">Microsoft Defender per Office 365 Piano 2</span><span class="sxs-lookup"><span data-stu-id="c74ce-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="c74ce-107">Poiché le indagini automatizzate sulla posta elettronica & contenuto di  collaborazione comportano verdetti, ad esempio dannosi o *sospetti,* vengono create determinate azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="c74ce-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="c74ce-108">In Microsoft Defender per Office 365, le azioni di correzione possono includere:</span><span class="sxs-lookup"><span data-stu-id="c74ce-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="c74ce-109">Eliminazione recisa dei messaggi di posta elettronica o dei cluster</span><span class="sxs-lookup"><span data-stu-id="c74ce-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="c74ce-110">Disattivazione dell'inoltro della posta esterna</span><span class="sxs-lookup"><span data-stu-id="c74ce-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="c74ce-111">Queste azioni di correzione non vengono eseguite a meno che il team delle operazioni di sicurezza non le approvi.</span><span class="sxs-lookup"><span data-stu-id="c74ce-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="c74ce-112">È consigliabile rivedere e approvare tutte le azioni in sospeso il prima possibile, in modo che le indagini automatizzate si completino in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="c74ce-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="c74ce-113">In alcuni casi, è possibile riconsiderare le azioni inviate.</span><span class="sxs-lookup"><span data-stu-id="c74ce-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="c74ce-114">È necessario essere parte del ruolo di & di eliminazione prima di eseguire qualsiasi azione.</span><span class="sxs-lookup"><span data-stu-id="c74ce-114">You need to be part of Search & purge role before taking any actions.</span></span>


## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="c74ce-115">Approvare (o rifiutare) le azioni in sospeso</span><span class="sxs-lookup"><span data-stu-id="c74ce-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="c74ce-116">Esistono quattro modi diversi per trovare ed eseguire azioni di indagine automatica:</span><span class="sxs-lookup"><span data-stu-id="c74ce-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="c74ce-117">Coda eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="c74ce-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="c74ce-118">Centro notifiche</span><span class="sxs-lookup"><span data-stu-id="c74ce-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="c74ce-119">Indagine stessa (accessibile tramite evento imprevisto o da un avviso)</span><span class="sxs-lookup"><span data-stu-id="c74ce-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="c74ce-120">Coda delle indagini di analisi e correzione</span><span class="sxs-lookup"><span data-stu-id="c74ce-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="c74ce-121">Coda eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="c74ce-121">Incident queue</span></span>
1. <span data-ttu-id="c74ce-122">Accedere al Centro [sicurezza Microsoft 365 e](https://security.microsoft.com) accedere.</span><span class="sxs-lookup"><span data-stu-id="c74ce-122">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="c74ce-123">Nel riquadro di spostamento selezionare **Eventi imprevisti & avvisi > eventi imprevisti**.</span><span class="sxs-lookup"><span data-stu-id="c74ce-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="c74ce-124">Selezionare il nome di un evento imprevisto per aprire la relativa pagina di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="c74ce-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="c74ce-125">Selezionare la **scheda Prova e** risposta.</span><span class="sxs-lookup"><span data-stu-id="c74ce-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="c74ce-126">Selezionare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c74ce-126">Select an item in the list.</span></span> <span data-ttu-id="c74ce-127">Viene aperto il riquadro laterale.</span><span class="sxs-lookup"><span data-stu-id="c74ce-127">Its side pane opens.</span></span>
6. <span data-ttu-id="c74ce-128">Nel riquadro laterale, eseguire le azioni di approvazione o rifiuto.</span><span class="sxs-lookup"><span data-stu-id="c74ce-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="c74ce-129">Coda di analisi</span><span class="sxs-lookup"><span data-stu-id="c74ce-129">Investigation queue</span></span> 
1. <span data-ttu-id="c74ce-130">Accedere al Centro [sicurezza Microsoft 365 e](https://security.microsoft.com) accedere.</span><span class="sxs-lookup"><span data-stu-id="c74ce-130">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="c74ce-131">Passare dalla pagina avvisi/eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="c74ce-131">Navigate from the alerts/incident page.</span></span> 
3. <span data-ttu-id="c74ce-132">Nella pagina Indagine passare alla scheda **Azioni in** sospeso.</span><span class="sxs-lookup"><span data-stu-id="c74ce-132">On the Investigation page, go to the **pending actions** tab.</span></span> 
4. <span data-ttu-id="c74ce-133">Selezionare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c74ce-133">Select an item in the list.</span></span> <span data-ttu-id="c74ce-134">Viene aperto il riquadro laterale.</span><span class="sxs-lookup"><span data-stu-id="c74ce-134">Its side pane opens.</span></span>  
5. <span data-ttu-id="c74ce-135">Nel riquadro laterale, eseguire le azioni di approvazione o rifiuto.</span><span class="sxs-lookup"><span data-stu-id="c74ce-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="c74ce-136">Centro notifiche</span><span class="sxs-lookup"><span data-stu-id="c74ce-136">Action center</span></span>
1. <span data-ttu-id="c74ce-137">Accedere al Centro [sicurezza Microsoft 365 e](https://security.microsoft.com) accedere.</span><span class="sxs-lookup"><span data-stu-id="c74ce-137">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="c74ce-138">Nel riquadro di spostamento selezionare **Centro notifiche.**</span><span class="sxs-lookup"><span data-stu-id="c74ce-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="c74ce-139">Nella scheda **In** sospeso esaminare l'elenco delle azioni in attesa di approvazione.</span><span class="sxs-lookup"><span data-stu-id="c74ce-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="c74ce-140">Selezionare **Apri pagina di indagine** per visualizzare ulteriori dettagli sull'indagine.</span><span class="sxs-lookup"><span data-stu-id="c74ce-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="c74ce-141">Selezionare **Approva** per avviare un'azione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="c74ce-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="c74ce-142">Selezionare **Rifiuta** per impedire l'esecuzione di un'azione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="c74ce-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="c74ce-143">Coda delle indagini di analisi e correzione</span><span class="sxs-lookup"><span data-stu-id="c74ce-143">Investigation and remediation investigations queue</span></span>
1. <span data-ttu-id="c74ce-144">Accedere al Centro [sicurezza Microsoft 365 e](https://security.microsoft.com) accedere.</span><span class="sxs-lookup"><span data-stu-id="c74ce-144">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="c74ce-145">Aprire indagini in sospeso.</span><span class="sxs-lookup"><span data-stu-id="c74ce-145">Open pending investigations.</span></span> 
3. <span data-ttu-id="c74ce-146">Nella pagina Indagine passare alla scheda **Azioni in** sospeso.</span><span class="sxs-lookup"><span data-stu-id="c74ce-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="c74ce-147">Selezionare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c74ce-147">Select an item in the list.</span></span> <span data-ttu-id="c74ce-148">Viene aperto il riquadro laterale.</span><span class="sxs-lookup"><span data-stu-id="c74ce-148">Its side pane opens.</span></span>  
5. <span data-ttu-id="c74ce-149">Nel riquadro laterale, eseguire le azioni di approvazione o rifiuto.</span><span class="sxs-lookup"><span data-stu-id="c74ce-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="c74ce-150">Modificare o annullare un'azione di correzione</span><span class="sxs-lookup"><span data-stu-id="c74ce-150">Change or undo one remediation action</span></span>

<span data-ttu-id="c74ce-151">Esistono due modi diversi per riconsiderare le azioni inviate:</span><span class="sxs-lookup"><span data-stu-id="c74ce-151">There are two different ways to reconsider submitted actions:</span></span>
   - <span data-ttu-id="c74ce-152">Tramite il [centro notifiche unificato](https://security.microsoft.com/action-center).</span><span class="sxs-lookup"><span data-stu-id="c74ce-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
   - <span data-ttu-id="c74ce-153">Anche se [il Office action center](https://security.microsoft.com/threatincidents).</span><span class="sxs-lookup"><span data-stu-id="c74ce-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>
   
## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="c74ce-154">Modificare o annullare il centro notifiche unificato</span><span class="sxs-lookup"><span data-stu-id="c74ce-154">Change or undo through the unified action center</span></span>
1. <span data-ttu-id="c74ce-155">Passare al [centro notifiche unificato](https://security.microsoft.com/action-center) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="c74ce-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="c74ce-156">Nella scheda **Cronologia** selezionare un'azione che si desidera modificare o annullare.</span><span class="sxs-lookup"><span data-stu-id="c74ce-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="c74ce-157">Nel riquadro sul lato destro dello schermo, selezionare l'azione appropriata **(** sposta nella posta in **arrivo,** sposta nella posta **indesiderata,** passa agli elementi eliminati, \*\*eliminazione recidiva o **elimina definitivamente**).</span><span class="sxs-lookup"><span data-stu-id="c74ce-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, \*\*soft delete", or **hard delete**).</span></span>

 ## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="c74ce-158">Modifica o annullamento tramite il Office notifiche</span><span class="sxs-lookup"><span data-stu-id="c74ce-158">Change or undo through the Office action center</span></span> 
1. <span data-ttu-id="c74ce-159">Accedere al Office [action center](https://security.microsoft.com/threatincidents) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="c74ce-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="c74ce-160">Selezionare la correzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="c74ce-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="c74ce-161">Nel riquadro laterale fare clic sulla voce relativa agli invii di posta e attendere il caricamento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c74ce-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span> 
4. <span data-ttu-id="c74ce-162">Attendere che il pulsante Azione nella parte superiore sia abilitato e selezionare il pulsante Azione per modificare il tipo di azione.</span><span class="sxs-lookup"><span data-stu-id="c74ce-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span> 
5. <span data-ttu-id="c74ce-163">Verranno create le azioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="c74ce-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c74ce-164">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c74ce-164">Next steps</span></span>

- [<span data-ttu-id="c74ce-165">Usare Esplora minacce</span><span class="sxs-lookup"><span data-stu-id="c74ce-165">Use Threat Explorer</span></span>](threat-explorer.md) 
- [<span data-ttu-id="c74ce-166">Admin /Manual Actions</span><span class="sxs-lookup"><span data-stu-id="c74ce-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="c74ce-167">Come segnalare falsi positivi/negativi nelle funzionalità di indagine e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="c74ce-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="c74ce-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c74ce-168">See also</span></span>

- [<span data-ttu-id="c74ce-169">Visualizzare i dettagli e i risultati di un'indagine automatizzata in Office 365</span><span class="sxs-lookup"><span data-stu-id="c74ce-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
