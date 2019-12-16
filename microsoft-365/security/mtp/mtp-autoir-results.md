---
title: Visualizzare i dettagli e i risultati di un'indagine automatizzata
description: Durante e dopo un'indagine automatizzata, è possibile visualizzare i risultati principali
keywords: automatizzata, indagine, risultati, analizzare, dettagli, correzione, autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 7d3923a3032653f9bfc4a59dc98fe06953975bac
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: MT + HT Review
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967919"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a><span data-ttu-id="1d466-104">Visualizzare i dettagli e i risultati di un'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="1d466-104">View the details and results of an automated investigation</span></span>

<span data-ttu-id="1d466-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1d466-105">**Applies to:**</span></span>
- <span data-ttu-id="1d466-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1d466-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="1d466-107">Quando si verifica un'indagine automatizzata in Microsoft Threat Protection, i dettagli di tale indagine sono disponibili durante e dopo il processo di indagine automatizzata.</span><span class="sxs-lookup"><span data-stu-id="1d466-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="1d466-108">Se di dispone delle [autorizzazioni necessarie](mtp-action-center.md#required-permissions-for-action-center-tasks), è possibile visualizzare i dettagli in una visualizzazione dei dettagli dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="1d466-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="1d466-109">La vista dei dettagli dell'indagine consente di avere uno stato aggiornato e la possibilità di approvare eventuali azioni in sospeso.</span><span class="sxs-lookup"><span data-stu-id="1d466-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Dettagli indagine](../images/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="1d466-111">Aprire la visualizzazione dei dettagli dell'indagine</span><span class="sxs-lookup"><span data-stu-id="1d466-111">Open the investigation details view</span></span>

<span data-ttu-id="1d466-112">È possibile aprire la visualizzazione dei dettagli dell'indagine utilizzando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d466-112">You can identify the subscription by using one of the following methods:</span></span>
- [<span data-ttu-id="1d466-113">Selezionare un elemento nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="1d466-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="1d466-114">Selezionare un'indagine dalla pagina dei dettagli dell'incidente</span><span class="sxs-lookup"><span data-stu-id="1d466-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="1d466-115">Selezionare un elemento nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="1d466-115">Select an item in the Action center</span></span>

<span data-ttu-id="1d466-116">Usare il centro notifiche per visualizzare le azioni in attesa di approvazione (nella scheda **In sospeso**) o quelle già approvate (nella scheda **Cronologia**).</span><span class="sxs-lookup"><span data-stu-id="1d466-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="1d466-117">Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1d466-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in with an admin account.</span></span> 

2. <span data-ttu-id="1d466-118">Nel riquadro di spostamento, scegliere **Centro notifiche**.</span><span class="sxs-lookup"><span data-stu-id="1d466-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="1d466-119">Nella scheda **In sospeso** o **Cronologia**, selezionare un elemento.</span><span class="sxs-lookup"><span data-stu-id="1d466-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="1d466-120">Se si dispone delle [autorizzazioni necessarie](mtp-action-center.md#required-permissions-for-action-center-tasks), è possibile approvare (o rifiutare) le azioni in sospeso.</span><span class="sxs-lookup"><span data-stu-id="1d466-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="1d466-121">Aprire un'indagine dalla pagina dei dettagli dell'incidente</span><span class="sxs-lookup"><span data-stu-id="1d466-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="1d466-122">Utilizzare una pagina dei dettagli di un incidente per visualizzare informazioni dettagliate relative a un incidente, inclusi gli avvisi che sono stati attivati, le informazioni su eventuali dispositivi, gli account utente o le cassette postali interessati.</span><span class="sxs-lookup"><span data-stu-id="1d466-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="1d466-123">Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1d466-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in with an admin account.</span></span> 

2. <span data-ttu-id="1d466-124">Nel riquadro di spostamento, scegliere **Incidenti**.</span><span class="sxs-lookup"><span data-stu-id="1d466-124">In the navigation pane, choose **Custom report**.</span></span> 

3. <span data-ttu-id="1d466-125">Selezionare un elemento nell'elenco per aprire la visualizzazione dei dettagli dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1d466-125">Select an item in the list to open the incident details view.</span></span><br/>![Dettagli incidente](../images/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="1d466-127">Nella scheda **Indagini**, selezionare un'indagine nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1d466-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="1d466-128">Dettagli indagine</span><span class="sxs-lookup"><span data-stu-id="1d466-128">Investigation details</span></span>

<span data-ttu-id="1d466-129">Utilizzare la vista dei dettagli dell'indagine per visualizzare le attività passate, attuali e in sospeso relative a un'indagine.</span><span class="sxs-lookup"><span data-stu-id="1d466-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="1d466-130">La visualizzazione dei dettagli dell'indagine è simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="1d466-130">The investigation details view resembles the following image:</span></span>

![Dettagli indagine](../images/mtp-air-investdetails.png)

<span data-ttu-id="1d466-132">Nella visualizzazione dei dettagli dell'indagine, è possibile vedere le informazioni nelle schede **Grafico dell'indagine**, **Avvisi**, **Dispositivi**, **Identità**, **Risultati principali**, **Entità**, **Log**, e **Azioni in sospeso**, descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1d466-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="1d466-133">Scheda</span><span class="sxs-lookup"><span data-stu-id="1d466-133">Recovery Tab</span></span>    |<span data-ttu-id="1d466-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d466-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="1d466-135">Grafico dell'indagine</span><span class="sxs-lookup"><span data-stu-id="1d466-135">Investigation graph</span></span>    |<span data-ttu-id="1d466-136">Fornisce una rappresentazione visiva dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="1d466-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="1d466-137">Descrive le entità ed elenca le minacce rilevate, insieme agli avvisi e alle eventuali azioni ancora in fase di approvazione.</span><span class="sxs-lookup"><span data-stu-id="1d466-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="1d466-138">È possibile fare clic su un elemento del grafico per visualizzare ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="1d466-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="1d466-139">Ad esempio, facendo clic sull'icona **Minacce rilevate** si verrà indirizzati alla scheda **Risultati principali**.</span><span class="sxs-lookup"><span data-stu-id="1d466-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="1d466-140">Avvisi</span><span class="sxs-lookup"><span data-stu-id="1d466-140">Alerts</span></span> |<span data-ttu-id="1d466-141">Elenca gli avvisi associati all'indagine.</span><span class="sxs-lookup"><span data-stu-id="1d466-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="1d466-142">Gli avvisi possono provenire dalle funzionalità di protezione dalle minacce sul computer di un utente, dalle app di Office, da Cloud App Security e da altre funzionalità di protezione dalle minacce di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1d466-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="1d466-143">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="1d466-143">Devices</span></span>|<span data-ttu-id="1d466-144">Elenca i computer inclusi nell'indagine insieme al livello di correzione.</span><span class="sxs-lookup"><span data-stu-id="1d466-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="1d466-145">Risultati principali</span><span class="sxs-lookup"><span data-stu-id="1d466-145">Key findings</span></span>   |<span data-ttu-id="1d466-146">Elenca i risultati dell'indagine, insieme allo stato e alle azioni eseguite o in sospeso.</span><span class="sxs-lookup"><span data-stu-id="1d466-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="1d466-147">In questa scheda è possibile approvare le azioni in sospeso per dispositivi e identità.</span><span class="sxs-lookup"><span data-stu-id="1d466-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="1d466-148">Entità</span><span class="sxs-lookup"><span data-stu-id="1d466-148">Managed Entities</span></span>   |<span data-ttu-id="1d466-149">Elenca le attività dell'utente, i file, i processi, i servizi, i driver, gli indirizzi IP e i metodi di persistenza associati all'indagine, insieme allo stato e alle azioni eseguite.</span><span class="sxs-lookup"><span data-stu-id="1d466-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="1d466-150">Log</span><span class="sxs-lookup"><span data-stu-id="1d466-150">Log On</span></span>    |<span data-ttu-id="1d466-151">Fornisce una visualizzazione dettagliata di tutti i passaggi seguiti durante l'indagine, insieme allo stato.</span><span class="sxs-lookup"><span data-stu-id="1d466-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="1d466-152">Azioni in sospeso</span><span class="sxs-lookup"><span data-stu-id="1d466-152">Pending actions</span></span>    |<span data-ttu-id="1d466-153">Elenca gli elementi che richiedono l'approvazione per continuare.</span><span class="sxs-lookup"><span data-stu-id="1d466-153">Lists items that require approval to proceed.</span></span>|

## <a name="remediation-actions-following-automated-investigation"></a><span data-ttu-id="1d466-154">Azioni correttive in seguito all'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="1d466-154">Remediation actions following automated investigation</span></span>

<span data-ttu-id="1d466-155">Una volta completata un'indagine automatizzata, viene emesso un verdetto per ogni prova inclusa e vengono identificate le azioni correttive.</span><span class="sxs-lookup"><span data-stu-id="1d466-155">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="1d466-156">In alcuni casi, le azioni correttive vengono eseguite automaticamente; in altri casi, invece, è necessario approvarle.</span><span class="sxs-lookup"><span data-stu-id="1d466-156">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="1d466-157">Nella tabella seguente sono elencati i possibili verdetti e i risultati:</span><span class="sxs-lookup"><span data-stu-id="1d466-157">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="1d466-158">Verdetto</span><span class="sxs-lookup"><span data-stu-id="1d466-158">5. Verdict</span></span>    |<span data-ttu-id="1d466-159">Area</span><span class="sxs-lookup"><span data-stu-id="1d466-159">Area</span></span>   |<span data-ttu-id="1d466-160">Risultati</span><span class="sxs-lookup"><span data-stu-id="1d466-160">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="1d466-161">Dannosa</span><span class="sxs-lookup"><span data-stu-id="1d466-161">Malicious</span></span>  |<span data-ttu-id="1d466-162">Dispositivi (endpoint)</span><span class="sxs-lookup"><span data-stu-id="1d466-162">Devices (endpoints)</span></span>    |<span data-ttu-id="1d466-163">Le azioni correttive vengono eseguite automaticamente</span><span class="sxs-lookup"><span data-stu-id="1d466-163">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="1d466-164">Dannosa</span><span class="sxs-lookup"><span data-stu-id="1d466-164">Malicious</span></span>  |<span data-ttu-id="1d466-165">Contenuto della posta elettronica (URL o allegati)</span><span class="sxs-lookup"><span data-stu-id="1d466-165">Email content (URLs or attachments)</span></span> | <span data-ttu-id="1d466-166">Le azioni correttive consigliate sono in attesa di approvazione</span><span class="sxs-lookup"><span data-stu-id="1d466-166">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="1d466-167">Sospetta</span><span class="sxs-lookup"><span data-stu-id="1d466-167">Suspicious</span></span> |<span data-ttu-id="1d466-168">Dispositivi o contenuto della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="1d466-168">Devices or email content</span></span> |<span data-ttu-id="1d466-169">Le azioni correttive consigliate sono in attesa di approvazione</span><span class="sxs-lookup"><span data-stu-id="1d466-169">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="1d466-170">Pulita</span><span class="sxs-lookup"><span data-stu-id="1d466-170">Clean Method</span></span>  |<span data-ttu-id="1d466-171">Dispositivi o contenuto della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="1d466-171">Devices or email content</span></span>   |<span data-ttu-id="1d466-172">Non sono necessarie azioni correttive</span><span class="sxs-lookup"><span data-stu-id="1d466-172">No remediation actions are needed</span></span>|

[<span data-ttu-id="1d466-173">Rivedere un'azione in sospeso nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="1d466-173">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

## <a name="next-steps"></a><span data-ttu-id="1d466-174">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1d466-174">Next steps</span></span>

- [<span data-ttu-id="1d466-175">Panoramica delle autorizzazioni del centro notifiche</span><span class="sxs-lookup"><span data-stu-id="1d466-175">Get an overview of Action center permissions</span></span>](mtp-action-center.md#required-permissions-for-action-center-tasks)
- [<span data-ttu-id="1d466-176">Approvare o rifiutare le azioni relative all'indagine e reazione automatizzate</span><span class="sxs-lookup"><span data-stu-id="1d466-176">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

