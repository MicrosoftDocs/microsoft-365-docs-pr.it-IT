---
title: Dettagli e risultati di un'indagine automatizzata
description: Visualizzare i risultati e i risultati principali dell'indagine automatizzata in Microsoft 365 Defender
keywords: automatizzata, indagine, risultati, analizzare, dettagli, correzione, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: ad774fc36f4f167cb7a4e695b9f572ceb55b968b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274677"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="8cf1d-104">Dettagli e risultati di un'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="8cf1d-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8cf1d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8cf1d-105">**Applies to:**</span></span>
- <span data-ttu-id="8cf1d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8cf1d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8cf1d-107">Con Microsoft 365 Defender, quando viene eseguita un'indagine automatizzata, i dettagli su tale indagine sono disponibili sia durante che dopo il processo di indagine automatizzata. [](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="8cf1d-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="8cf1d-108">Se di dispone delle [autorizzazioni necessarie](m365d-action-center.md#required-permissions-for-action-center-tasks), è possibile visualizzare i dettagli in una visualizzazione dei dettagli dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="8cf1d-109">Questa visualizzazione offre lo stato aggiornato e la possibilità di approvare eventuali azioni in sospeso.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-109">This view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Dettagli indagine](../../media/mtp-air-investdetails.png)

## <a name="new-unified-investigation-page"></a><span data-ttu-id="8cf1d-111">(NEW!) Pagina analisi unificata</span><span class="sxs-lookup"><span data-stu-id="8cf1d-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="8cf1d-112">La pagina di indagine è stata aggiornata di recente per includere informazioni su dispositivi, posta elettronica e contenuti di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="8cf1d-113">La nuova pagina di indagine unificata definisce un linguaggio comune e offre un'esperienza unificata per le indagini automatiche in [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) e Microsoft Defender per Office [365.](../office-365-security/defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="8cf1d-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="8cf1d-114">Per accedere alla pagina di indagine unificata, seleziona il collegamento nel banner giallo che vedrai in:</span><span class="sxs-lookup"><span data-stu-id="8cf1d-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>

- <span data-ttu-id="8cf1d-115">Qualsiasi pagina di indagine nel Centro sicurezza & e conformità di Office 365 ( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="8cf1d-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="8cf1d-116">Qualsiasi pagina di indagine in Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="8cf1d-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="8cf1d-117">Qualsiasi evento imprevisto o centro notifiche nel Centro sicurezza Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) )</span><span class="sxs-lookup"><span data-stu-id="8cf1d-117">Any incident or Action center experience in the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="8cf1d-118">Aprire la visualizzazione dei dettagli dell'indagine</span><span class="sxs-lookup"><span data-stu-id="8cf1d-118">Open the investigation details view</span></span>

<span data-ttu-id="8cf1d-119">È possibile aprire la visualizzazione dei dettagli dell'indagine utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cf1d-119">You can open the investigation details view by using one of the following methods:</span></span>

- [<span data-ttu-id="8cf1d-120">Selezionare un elemento nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="8cf1d-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="8cf1d-121">Selezionare un'indagine dalla pagina dei dettagli dell'incidente</span><span class="sxs-lookup"><span data-stu-id="8cf1d-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="8cf1d-122">Selezionare un elemento nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="8cf1d-122">Select an item in the Action center</span></span>

<span data-ttu-id="8cf1d-123">Il centro [notifiche migliorato](m365d-action-center.md) ( ) riunisce le azioni di correzione nei dispositivi, nella posta elettronica & contenuti di [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) collaborazione e identità. [](m365d-remediation-actions.md)</span><span class="sxs-lookup"><span data-stu-id="8cf1d-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="8cf1d-124">Le azioni elencate includono le azioni di correzione eseguite automaticamente o manualmente.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="8cf1d-125">Nel centro notifiche è possibile visualizzare le azioni in attesa di approvazione e le azioni già approvate o completate.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="8cf1d-126">Puoi anche passare a ulteriori dettagli, ad esempio una pagina di indagine.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="8cf1d-127">È necessario disporre [di determinate autorizzazioni](m365d-action-center.md#required-permissions-for-action-center-tasks) per approvare, rifiutare o annullare azioni.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="8cf1d-128">Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="8cf1d-129">Nel riquadro di spostamento, scegliere **Centro notifiche**.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-129">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="8cf1d-130">Nella scheda **In sospeso** o **Cronologia**, selezionare un elemento.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="8cf1d-131">Verrà visualizzato il riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-131">Its flyout pane opens.</span></span>

4. <span data-ttu-id="8cf1d-132">Esaminare le informazioni nel riquadro a comparsa e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cf1d-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="8cf1d-133">Selezionare **Apri pagina di indagine** per visualizzare ulteriori dettagli sull'indagine.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="8cf1d-134">Selezionare **Approva** per avviare un'azione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="8cf1d-135">Selezionare **Rifiuta** per impedire l'esecuzione di un'azione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="8cf1d-136">Seleziona **Vai a ricerca** per passare a Ricerca [avanzata.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8cf1d-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="8cf1d-137">Aprire un'indagine dalla pagina dei dettagli dell'incidente</span><span class="sxs-lookup"><span data-stu-id="8cf1d-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="8cf1d-138">Utilizzare una pagina dei dettagli di un incidente per visualizzare informazioni dettagliate relative a un incidente, inclusi gli avvisi che sono stati attivati, le informazioni su eventuali dispositivi, gli account utente o le cassette postali interessati.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="8cf1d-139">Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-139">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="8cf1d-140">Nel riquadro di spostamento scegliere **Eventi imprevisti & avvisi** Eventi  >  **imprevisti**.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-140">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 

3. <span data-ttu-id="8cf1d-141">Selezionare un elemento nell'elenco e quindi scegliere **Apri pagina evento imprevisto.**</span><span class="sxs-lookup"><span data-stu-id="8cf1d-141">Select an item in the list, and then choose **Open incident page**.</span></span>

4. <span data-ttu-id="8cf1d-142">Selezionare la **scheda Indagini** e quindi selezionare un'indagine nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-142">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="8cf1d-143">Verrà visualizzato il riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-143">Its flyout pane opens.</span></span>

5. <span data-ttu-id="8cf1d-144">Selezionare **Apri pagina di analisi**.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-144">Select **Open investigation page**.</span></span> 

<span data-ttu-id="8cf1d-145">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-145">Here's an example.</span></span>

![Dettagli incidente](../../media/mtp-incidentdetails-tabs.png)

## <a name="investigation-details"></a><span data-ttu-id="8cf1d-147">Dettagli indagine</span><span class="sxs-lookup"><span data-stu-id="8cf1d-147">Investigation details</span></span>

<span data-ttu-id="8cf1d-148">Utilizzare la vista dei dettagli dell'indagine per visualizzare le attività passate, attuali e in sospeso relative a un'indagine.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-148">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="8cf1d-149">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-149">Here's an example.</span></span>

![Dettagli indagine](../../media/mtp-air-investdetails.png)

<span data-ttu-id="8cf1d-151">Nella visualizzazione dei dettagli dell'indagine, è possibile vedere le informazioni nelle schede **Grafico dell'indagine**, **Avvisi**, **Dispositivi**, **Identità**, **Risultati principali**, **Entità**, **Log**, e **Azioni in sospeso**, descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-151">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf1d-152">Le schede specifiche visualizzate in una pagina dei dettagli dell'indagine dipendono da ciò che include l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-152">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="8cf1d-153">Ad esempio, se l'abbonamento non include Microsoft Defender per Office 365 Piano 2, non verrà visualizzata una **scheda Cassette** postali.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-153">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="8cf1d-154">Scheda</span><span class="sxs-lookup"><span data-stu-id="8cf1d-154">Tab</span></span> | <span data-ttu-id="8cf1d-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8cf1d-155">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="8cf1d-156">**Grafico dell'indagine**</span><span class="sxs-lookup"><span data-stu-id="8cf1d-156">**Investigation graph**</span></span>   | <span data-ttu-id="8cf1d-157">Fornisce una rappresentazione visiva dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-157">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="8cf1d-158">Descrive le entità ed elenca le minacce rilevate, insieme agli avvisi e alle eventuali azioni ancora in fase di approvazione.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-158">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="8cf1d-159">È possibile selezionare un elemento nel grafico per visualizzare ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-159">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="8cf1d-160">Ad esempio, selezionando **l'icona**  Prova si visualizza la scheda Prova, in cui è possibile visualizzare le entità rilevate e i relativi verdetti.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-160">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="8cf1d-161">**Avvisi**</span><span class="sxs-lookup"><span data-stu-id="8cf1d-161">**Alerts**</span></span>    | <span data-ttu-id="8cf1d-162">Elenca gli avvisi associati all'indagine.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-162">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="8cf1d-163">Gli avvisi possono derivare dalle funzionalità di protezione dalle minacce nel dispositivo di un utente, nelle app di Office, in Microsoft Cloud App Security e in altre funzionalità di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-163">Alerts can come from threat protection features on a user's device, in Office apps, Microsoft Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="8cf1d-164">**Dispositivi**</span><span class="sxs-lookup"><span data-stu-id="8cf1d-164">**Devices**</span></span> | <span data-ttu-id="8cf1d-165">Elenca i dispositivi inclusi nell'indagine insieme al relativo livello di correzione.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-165">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="8cf1d-166">I livelli di correzione corrispondono al [livello di automazione per i gruppi di dispositivi.](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)</span><span class="sxs-lookup"><span data-stu-id="8cf1d-166">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="8cf1d-167">**Cassette postali**</span><span class="sxs-lookup"><span data-stu-id="8cf1d-167">**Mailboxes**</span></span> |<span data-ttu-id="8cf1d-168">Elenca le cassette postali che sono influenzate dalle minacce rilevate.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-168">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="8cf1d-169">**Utenti**</span><span class="sxs-lookup"><span data-stu-id="8cf1d-169">**Users**</span></span>  | <span data-ttu-id="8cf1d-170">Elenca gli account utente che sono influenzati dalle minacce rilevate.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-170">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="8cf1d-171">**Prova**</span><span class="sxs-lookup"><span data-stu-id="8cf1d-171">**Evidence**</span></span> | <span data-ttu-id="8cf1d-172">Elenca le prove generate da avvisi o indagini.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-172">Lists pieces of evidence raised by alerts or investigations.</span></span> <span data-ttu-id="8cf1d-173">Include i verdetti (*Dannoso,* *Sospetto,* *Sconosciuto* *o* Nessuna minaccia trovata) e lo stato di correzione.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-173">Includes verdicts (*Malicious*, *Suspicious*, *Unknown*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="8cf1d-174">**Entità**</span><span class="sxs-lookup"><span data-stu-id="8cf1d-174">**Entities**</span></span>  | <span data-ttu-id="8cf1d-175">Fornisce informazioni dettagliate su ogni entità analizzata, incluso un verdetto per ogni tipo di entità (*Dannoso,* *Sospetto* o *Nessuna minaccia trovata).*</span><span class="sxs-lookup"><span data-stu-id="8cf1d-175">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="8cf1d-176">**Log**</span><span class="sxs-lookup"><span data-stu-id="8cf1d-176">**Log**</span></span>    | <span data-ttu-id="8cf1d-177">Fornisce una visualizzazione cronologica dettagliata di tutte le azioni di indagine eseguite dopo l'attivazione di un avviso.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-177">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="8cf1d-178">**Cronologia azioni in sospeso**</span><span class="sxs-lookup"><span data-stu-id="8cf1d-178">**Pending actions history**</span></span> | <span data-ttu-id="8cf1d-179">Elenca gli elementi che richiedono l'approvazione per continuare.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-179">Lists items that require approval to proceed.</span></span> <span data-ttu-id="8cf1d-180">Passare al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) per approvare le azioni in sospeso.</span><span class="sxs-lookup"><span data-stu-id="8cf1d-180">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="8cf1d-181">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8cf1d-181">Next steps</span></span>

- [<span data-ttu-id="8cf1d-182">Visualizzare e gestire le azioni correttive</span><span class="sxs-lookup"><span data-stu-id="8cf1d-182">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="8cf1d-183">Ulteriori informazioni sulle azioni di correzione</span><span class="sxs-lookup"><span data-stu-id="8cf1d-183">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)
