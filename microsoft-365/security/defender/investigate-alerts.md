---
title: Analizzare gli avvisi in Microsoft 365 Defender
description: Analizzare gli avvisi visualizzati su dispositivi, utenti e cassette postali.
keywords: incidenti, avvisi, analizzare, analizzare, risposta, correlazione, attacco, computer, dispositivi, utenti, identità, identità, identità, cassetta postale, posta elettronica, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: a6e11aea14a7b8d99c0098b68951790328ec593e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782910"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="b3b9f-104">Analizzare gli avvisi in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3b9f-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b3b9f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b3b9f-105">**Applies to:**</span></span>
- <span data-ttu-id="b3b9f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3b9f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b3b9f-107">Gli avvisi sono alla base di tutti gli eventi imprevisti e indicano il verificarsi di eventi dannosi o sospetti nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="b3b9f-108">Gli avvisi fanno in genere parte di un attacco più ampio e forniscono indicazioni su un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="b3b9f-109">In Microsoft 365 Defender, gli avvisi correlati vengono aggregati insieme per formare [eventi imprevisti.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b3b9f-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="b3b9f-110">Gli incidenti forniscono sempre il contesto più ampio di un attacco, tuttavia, l'analisi degli avvisi può essere utile quando è necessaria un'analisi più approfondita.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="b3b9f-111">La **coda Avvisi** mostra il set corrente di avvisi.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="b3b9f-112">Si arriva alla coda degli avvisi da **Eventi imprevisti & avvisi > avvisi** sulla barra di avvio veloce del centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="b3b9f-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Esempio di coda degli avvisi":::

<span data-ttu-id="b3b9f-114">Gli avvisi di diverse soluzioni di sicurezza Microsoft come Microsoft Defender for Endpoint, Microsoft Defender per Office 365 e Microsoft 365 Defender vengono visualizzati qui.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="b3b9f-115">Per impostazione predefinita, nella coda degli avvisi nel centro sicurezza Microsoft 365 vengono visualizzati gli avvisi nuovi e in corso degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="b3b9f-116">L'avviso più recente si trova all'inizio dell'elenco in modo da poterlo visualizzare per primo.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="b3b9f-117">Dalla coda degli avvisi predefinita, è  possibile selezionare **Filtri** per visualizzare un riquadro Filtri, da cui è possibile specificare un sottoinsieme degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="b3b9f-118">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Esempio del riquadro dei filtri per la coda degli avvisi":::

<span data-ttu-id="b3b9f-120">È possibile filtrare gli avvisi in base ai criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3b9f-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="b3b9f-121">Gravità</span><span class="sxs-lookup"><span data-stu-id="b3b9f-121">Severity</span></span>
- <span data-ttu-id="b3b9f-122">Stato</span><span class="sxs-lookup"><span data-stu-id="b3b9f-122">Status</span></span>
- <span data-ttu-id="b3b9f-123">Categoria</span><span class="sxs-lookup"><span data-stu-id="b3b9f-123">Category</span></span>
- <span data-ttu-id="b3b9f-124">Origine di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b3b9f-124">Detection source</span></span>
- <span data-ttu-id="b3b9f-125">Tag</span><span class="sxs-lookup"><span data-stu-id="b3b9f-125">Tags</span></span>
- <span data-ttu-id="b3b9f-126">Criterio</span><span class="sxs-lookup"><span data-stu-id="b3b9f-126">Policy</span></span>
- <span data-ttu-id="b3b9f-127">Asset influenzati</span><span class="sxs-lookup"><span data-stu-id="b3b9f-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="b3b9f-128">Analizzare un avviso</span><span class="sxs-lookup"><span data-stu-id="b3b9f-128">Analyze an alert</span></span>

<span data-ttu-id="b3b9f-129">Per visualizzare la pagina di avviso principale, selezionare il nome dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="b3b9f-130">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Esempio della pagina dei dettagli di un avviso nel centro sicurezza Microsoft 365 sicurezza":::

<span data-ttu-id="b3b9f-132">È inoltre possibile selezionare **l'azione Apri la pagina di avviso** principale nel riquadro **Gestisci** avviso.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="b3b9f-133">Una pagina di avviso è composta da queste sezioni:</span><span class="sxs-lookup"><span data-stu-id="b3b9f-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="b3b9f-134">Alert story, ovvero la catena di eventi e avvisi correlati a questo avviso in ordine cronologico</span><span class="sxs-lookup"><span data-stu-id="b3b9f-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="b3b9f-135">Dettagli di riepilogo</span><span class="sxs-lookup"><span data-stu-id="b3b9f-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Esempio della pagina dei dettagli di un avviso nel centro sicurezza Microsoft 365 sicurezza":::

<span data-ttu-id="b3b9f-137">In tutta una pagina di avviso, è possibile selezionare i puntini di sospensione (**...**) accanto a qualsiasi entità per visualizzare le azioni disponibili, ad esempio l'apertura della pagina di avviso o il collegamento dell'avviso a un altro evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="alert-sources"></a><span data-ttu-id="b3b9f-138">Origini degli avvisi</span><span class="sxs-lookup"><span data-stu-id="b3b9f-138">Alert sources</span></span>
<span data-ttu-id="b3b9f-139">Microsoft 365 Gli avvisi defender possono derivare da soluzioni come Microsoft Defender for Endpoint, Microsoft Defender per Office 365 e Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-139">Microsoft 365 Defender alerts may come from solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft Cloud App Security.</span></span> <span data-ttu-id="b3b9f-140">Potresti notare avvisi con caratteri anteposti nell'avviso.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-140">You may notice alerts with prepended characters in the alert.</span></span> <span data-ttu-id="b3b9f-141">Nella tabella seguente vengono fornite indicazioni per comprendere il mapping delle origini degli avvisi in base al carattere anteposto nell'avviso.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-141">The following table provides guidance to help you understand the mapping of alert sources based on the prepended character on the alert.</span></span>

> [!NOTE]
> - <span data-ttu-id="b3b9f-142">I GUID anteposti sono specifici solo per le esperienze unificate, ad esempio la coda degli avvisi unificati, la pagina degli avvisi unificati, l'indagine unificata e l'incidente unificato.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-142">The prepended GUIDs are specific only to unified experiences such as unified alerts queue, unified alerts page, unified investigation, and unified incident.</span></span><br>
> - <span data-ttu-id="b3b9f-143">Il carattere anteposto non modifica il GUID dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-143">The prepended character does not change the GUID of the alert.</span></span> <span data-ttu-id="b3b9f-144">L'unica modifica apportata al GUID è il componente anteposto.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-144">The only change to the GUID is the prepended component.</span></span><br>


<span data-ttu-id="b3b9f-145">Origine avviso</span><span class="sxs-lookup"><span data-stu-id="b3b9f-145">Alert source</span></span> | <span data-ttu-id="b3b9f-146">Carattere anteposto</span><span class="sxs-lookup"><span data-stu-id="b3b9f-146">Prepended character</span></span> 
:---|:---
<span data-ttu-id="b3b9f-147">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="b3b9f-147">Microsoft Defender for Office 365</span></span> | `fa{GUID}` <br> <span data-ttu-id="b3b9f-148">Esempio: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="b3b9f-148">Example: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="b3b9f-149">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b3b9f-149">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="b3b9f-150">`da` o `ed` per avvisi di rilevamento personalizzati</span><span class="sxs-lookup"><span data-stu-id="b3b9f-150">`da` or `ed` for custom detection alerts</span></span> <br> 
<span data-ttu-id="b3b9f-151">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="b3b9f-151">Microsoft Defender for Identity</span></span> | `aa{GUID}` <br> <span data-ttu-id="b3b9f-152">Esempio: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="b3b9f-152">Example: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="b3b9f-153">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b3b9f-153">Microsoft Cloud App Security</span></span> |`ca{GUID}` <br> <span data-ttu-id="b3b9f-154">Esempio: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="b3b9f-154">Example: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 



### <a name="analyze-affected-assets"></a><span data-ttu-id="b3b9f-155">Analizzare gli asset interessati</span><span class="sxs-lookup"><span data-stu-id="b3b9f-155">Analyze affected assets</span></span>

<span data-ttu-id="b3b9f-156">La **sezione Azioni eseguite** contiene un elenco di asset interessati, ad esempio cassette postali, dispositivi e utenti interessati da questo avviso.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-156">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="b3b9f-157">È inoltre possibile selezionare **Visualizza nel centro** notifiche  per visualizzare la scheda **Cronologia** del centro notifiche nel centro Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-157">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="b3b9f-158">Tracciare il ruolo di un avviso nella storia di avviso</span><span class="sxs-lookup"><span data-stu-id="b3b9f-158">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="b3b9f-159">La storia dell'avviso visualizza tutti gli asset o le entità correlati all'avviso in una visualizzazione albero del processo.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-159">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="b3b9f-160">L'avviso nel titolo è quello a fuoco quando si atterra per la prima volta nella pagina dell'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-160">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="b3b9f-161">Gli asset nella storia di avviso sono espandibili e selezionabili.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-161">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="b3b9f-162">Forniscono informazioni aggiuntive e velocizzano la risposta consentendoti di intervenire direttamente nel contesto della pagina di avviso.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-162">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="b3b9f-163">La sezione della storia dell'avviso può contenere più di un avviso, con altri avvisi correlati allo stesso albero di esecuzione visualizzati prima o dopo l'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-163">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="b3b9f-164">Visualizzare ulteriori informazioni sugli avvisi nella pagina dei dettagli</span><span class="sxs-lookup"><span data-stu-id="b3b9f-164">View more alert information on the details page</span></span>

<span data-ttu-id="b3b9f-165">La pagina dei dettagli mostra i dettagli dell'avviso selezionato, con i dettagli e le azioni ad esso correlati.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-165">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="b3b9f-166">Se si seleziona una delle risorse o entità interessate nella storia di avviso, la pagina dei dettagli cambia per fornire informazioni contestuali e azioni per l'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-166">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="b3b9f-167">Dopo aver selezionato un'entità di interesse, la pagina dei dettagli cambia per visualizzare le informazioni sul tipo di entità selezionato, le informazioni storiche quando sono disponibili e le opzioni per eseguire un'azione su questa entità direttamente dalla pagina di avviso.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-167">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="b3b9f-168">Gestire gli avvisi</span><span class="sxs-lookup"><span data-stu-id="b3b9f-168">Manage alerts</span></span>

<span data-ttu-id="b3b9f-169">Per gestire un avviso, selezionare l'avviso nella coda degli avvisi nella riga corrispondente per visualizzare un **riquadro Gestisci** avviso.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-169">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="b3b9f-170">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-170">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Esempio del riquadro di riepilogo per un avviso":::

<span data-ttu-id="b3b9f-172">Il **riquadro Gestisci** avviso consente di specificare:</span><span class="sxs-lookup"><span data-stu-id="b3b9f-172">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="b3b9f-173">Stato dell'avviso (Nuovo, Risolto, In corso).</span><span class="sxs-lookup"><span data-stu-id="b3b9f-173">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="b3b9f-174">Classificazione dell'avviso (Non impostato, True alert, False Alert).</span><span class="sxs-lookup"><span data-stu-id="b3b9f-174">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="b3b9f-175">Per la classificazione come avviso vero, il tipo di minaccia per l'avviso nel **campo Determinazione.**</span><span class="sxs-lookup"><span data-stu-id="b3b9f-175">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="b3b9f-176">Commento sull'avviso.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-176">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="b3b9f-177">Un modo per gestire gli avvisi tramite l'uso di tag.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-177">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="b3b9f-178">La funzionalità di tagging per Microsoft Defender per Office 365 è in fase di implementazione incrementale ed è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-178">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="b3b9f-179">Attualmente, i nomi dei tag modificati vengono applicati solo agli avvisi creati *dopo l'aggiornamento.*</span><span class="sxs-lookup"><span data-stu-id="b3b9f-179">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="b3b9f-180">Gli avvisi generati prima della modifica non rifletteranno il nome del tag aggiornato.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-180">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="b3b9f-181">Da questo riquadro è inoltre possibile eseguire queste azioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="b3b9f-181">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="b3b9f-182">Aprire la pagina di avviso principale</span><span class="sxs-lookup"><span data-stu-id="b3b9f-182">Open the main alert page</span></span>
- <span data-ttu-id="b3b9f-183">Consultare un esperto di minacce Microsoft</span><span class="sxs-lookup"><span data-stu-id="b3b9f-183">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="b3b9f-184">Visualizzare l'invio</span><span class="sxs-lookup"><span data-stu-id="b3b9f-184">View submission</span></span>
- <span data-ttu-id="b3b9f-185">Collegamento a un altro evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="b3b9f-185">Link to another incident</span></span>
- <span data-ttu-id="b3b9f-186">Visualizzare l'avviso in una sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="b3b9f-186">See the alert in a timeline</span></span>
- <span data-ttu-id="b3b9f-187">Creare una regola di eliminazione</span><span class="sxs-lookup"><span data-stu-id="b3b9f-187">Create a suppression rule</span></span>

<span data-ttu-id="b3b9f-188">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-188">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Esempio di azioni su un avviso nel Centro sicurezza Microsoft 365 sicurezza":::

<span data-ttu-id="b3b9f-190">L'elenco delle azioni aggiuntive dipende dal tipo di avviso.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-190">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="b3b9f-191">Risolvere un avviso</span><span class="sxs-lookup"><span data-stu-id="b3b9f-191">Resolve an alert</span></span>

<span data-ttu-id="b3b9f-192">Una volta completata l'analisi di un avviso e  può essere risolto, passare al riquadro  Gestisci avviso per l'avviso e contrassegnarlo come Risolto e classificarlo come avviso **False** o **True.**</span><span class="sxs-lookup"><span data-stu-id="b3b9f-192">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="b3b9f-193">Per gli avvisi veri, specificare il tipo di minaccia dell'avviso nel **campo Determinazione.**</span><span class="sxs-lookup"><span data-stu-id="b3b9f-193">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="b3b9f-194">Classificare gli avvisi e specificarne la determinazione aiuta a ottimizzare Microsoft 365 Defender per fornire avvisi più veri e meno falsi.</span><span class="sxs-lookup"><span data-stu-id="b3b9f-194">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3b9f-195">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b3b9f-195">Next steps</span></span>

<span data-ttu-id="b3b9f-196">In base alle esigenze per gli eventi imprevisti in-process, continuare [l'indagine.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="b3b9f-196">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b3b9f-197">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3b9f-197">See also</span></span>

- [<span data-ttu-id="b3b9f-198">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="b3b9f-198">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b3b9f-199">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="b3b9f-199">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="b3b9f-200">Indagare sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="b3b9f-200">Investigate incidents</span></span>](investigate-incidents.md)
