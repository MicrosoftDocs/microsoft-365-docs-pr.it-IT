---
title: Analizzare gli avvisi in Microsoft 365 Defender
description: Analizzare gli avvisi visualizzati su dispositivi, utenti e cassette postali.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
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
ms.openlocfilehash: 77b30e8a8eee70470115bcd61f081863fa5a41ee
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862007"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="bb91b-104">Analizzare gli avvisi in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb91b-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bb91b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="bb91b-105">**Applies to:**</span></span>
- <span data-ttu-id="bb91b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb91b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bb91b-107">Gli avvisi sono alla base di tutti gli eventi imprevisti e indicano il verificarsi di eventi dannosi o sospetti nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="bb91b-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="bb91b-108">Gli avvisi fanno in genere parte di un attacco più ampio e forniscono indicazioni su un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="bb91b-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="bb91b-109">In Microsoft 365 Defender, gli avvisi correlati vengono aggregati insieme per formare [eventi imprevisti.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bb91b-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="bb91b-110">Gli incidenti forniscono sempre il contesto più ampio di un attacco, tuttavia, l'analisi degli avvisi può essere utile quando è necessaria un'analisi più approfondita.</span><span class="sxs-lookup"><span data-stu-id="bb91b-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="bb91b-111">La **coda Avvisi** mostra il set corrente di avvisi.</span><span class="sxs-lookup"><span data-stu-id="bb91b-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="bb91b-112">Si arriva alla coda degli avvisi da **Eventi imprevisti & avvisi > avvisi** sulla barra di avvio veloce del Centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="bb91b-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Esempio di coda degli avvisi":::

<span data-ttu-id="bb91b-114">Gli avvisi di diverse soluzioni di sicurezza Microsoft come Microsoft Defender for Endpoint, Microsoft Defender per Office 365 e Microsoft 365 Defender vengono visualizzati qui.</span><span class="sxs-lookup"><span data-stu-id="bb91b-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="bb91b-115">Per impostazione predefinita, nella coda degli avvisi nel Centro sicurezza Microsoft 365 vengono visualizzati gli avvisi nuovi e in corso degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="bb91b-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="bb91b-116">L'avviso più recente si trova all'inizio dell'elenco in modo da poterlo visualizzare per primo.</span><span class="sxs-lookup"><span data-stu-id="bb91b-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="bb91b-117">Dalla coda degli avvisi predefinita, è  possibile selezionare **Filtri** per visualizzare un riquadro Filtri, da cui è possibile specificare un sottoinsieme degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="bb91b-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="bb91b-118">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="bb91b-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Esempio del riquadro dei filtri per la coda degli avvisi":::

<span data-ttu-id="bb91b-120">È possibile filtrare gli avvisi in base ai criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb91b-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="bb91b-121">Gravità</span><span class="sxs-lookup"><span data-stu-id="bb91b-121">Severity</span></span>
- <span data-ttu-id="bb91b-122">Stato</span><span class="sxs-lookup"><span data-stu-id="bb91b-122">Status</span></span>
- <span data-ttu-id="bb91b-123">Categoria</span><span class="sxs-lookup"><span data-stu-id="bb91b-123">Category</span></span>
- <span data-ttu-id="bb91b-124">Origine di rilevamento</span><span class="sxs-lookup"><span data-stu-id="bb91b-124">Detection source</span></span>
- <span data-ttu-id="bb91b-125">Tag</span><span class="sxs-lookup"><span data-stu-id="bb91b-125">Tags</span></span>
- <span data-ttu-id="bb91b-126">Criteri</span><span class="sxs-lookup"><span data-stu-id="bb91b-126">Policy</span></span>
- <span data-ttu-id="bb91b-127">Asset influenzati</span><span class="sxs-lookup"><span data-stu-id="bb91b-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="bb91b-128">Analizzare un avviso</span><span class="sxs-lookup"><span data-stu-id="bb91b-128">Analyze an alert</span></span>

<span data-ttu-id="bb91b-129">Per visualizzare la pagina di avviso principale, selezionare il nome dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="bb91b-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="bb91b-130">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="bb91b-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Esempio della pagina dei dettagli di un avviso nel Centro sicurezza Microsoft 365":::

<span data-ttu-id="bb91b-132">È inoltre possibile selezionare **l'azione Apri la pagina di avviso** principale nel riquadro **Gestisci** avviso.</span><span class="sxs-lookup"><span data-stu-id="bb91b-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="bb91b-133">Una pagina di avviso è composta da queste sezioni:</span><span class="sxs-lookup"><span data-stu-id="bb91b-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="bb91b-134">Alert story</span><span class="sxs-lookup"><span data-stu-id="bb91b-134">Alert story</span></span>
- <span data-ttu-id="bb91b-135">Azioni intraprese (incluse le risorse influenzate)</span><span class="sxs-lookup"><span data-stu-id="bb91b-135">Actions taken (including impacted assets)</span></span>
- <span data-ttu-id="bb91b-136">Eventi correlati</span><span class="sxs-lookup"><span data-stu-id="bb91b-136">Related events</span></span>
- <span data-ttu-id="bb91b-137">Dettagli di riepilogo</span><span class="sxs-lookup"><span data-stu-id="bb91b-137">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Esempio della pagina dei dettagli di un avviso nel Centro sicurezza Microsoft 365":::

<span data-ttu-id="bb91b-139">In tutta una pagina di avviso, puoi selezionare i puntini di sospensione (**...**) accanto a qualsiasi entità per visualizzare le azioni disponibili, ad esempio l'apertura della pagina di asset specifica o la procedura di correzione specifica.</span><span class="sxs-lookup"><span data-stu-id="bb91b-139">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the specific asset page or taking specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="bb91b-140">Analizzare gli asset interessati</span><span class="sxs-lookup"><span data-stu-id="bb91b-140">Analyze affected assets</span></span>

<span data-ttu-id="bb91b-141">La **sezione Azioni eseguite** contiene un elenco di asset interessati, ad esempio cassette postali, dispositivi e utenti interessati da questo avviso.</span><span class="sxs-lookup"><span data-stu-id="bb91b-141">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="bb91b-142">È inoltre possibile selezionare **Visualizza nel centro notifiche** per visualizzare la scheda **Cronologia** del **centro** notifiche nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb91b-142">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="bb91b-143">Tracciare il ruolo di un avviso nella storia di avviso</span><span class="sxs-lookup"><span data-stu-id="bb91b-143">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="bb91b-144">La storia dell'avviso visualizza tutti gli asset o le entità correlati all'avviso in una visualizzazione albero del processo.</span><span class="sxs-lookup"><span data-stu-id="bb91b-144">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="bb91b-145">L'avviso nel titolo è quello a fuoco quando si atterra per la prima volta nella pagina dell'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="bb91b-145">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="bb91b-146">Gli asset nella storia di avviso sono espandibili e selezionabili.</span><span class="sxs-lookup"><span data-stu-id="bb91b-146">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="bb91b-147">Forniscono informazioni aggiuntive e velocizzano la risposta consentendoti di intervenire direttamente nel contesto della pagina di avviso.</span><span class="sxs-lookup"><span data-stu-id="bb91b-147">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="bb91b-148">La sezione della storia dell'avviso può contenere più di un avviso, con altri avvisi correlati allo stesso albero di esecuzione visualizzati prima o dopo l'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="bb91b-148">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="bb91b-149">Visualizzare ulteriori informazioni sugli avvisi nella pagina dei dettagli</span><span class="sxs-lookup"><span data-stu-id="bb91b-149">View more alert information on the details page</span></span>

<span data-ttu-id="bb91b-150">La pagina dei dettagli mostra i dettagli dell'avviso selezionato, con i dettagli e le azioni ad esso correlati.</span><span class="sxs-lookup"><span data-stu-id="bb91b-150">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="bb91b-151">Se si seleziona una delle risorse o entità interessate nella storia di avviso, la pagina dei dettagli cambia per fornire informazioni contestuali e azioni per l'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="bb91b-151">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="bb91b-152">Dopo aver selezionato un'entità di interesse, la pagina dei dettagli cambia per visualizzare le informazioni sul tipo di entità selezionato, le informazioni storiche quando sono disponibili e le opzioni per eseguire un'azione su questa entità direttamente dalla pagina di avviso.</span><span class="sxs-lookup"><span data-stu-id="bb91b-152">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="bb91b-153">Gestire gli avvisi</span><span class="sxs-lookup"><span data-stu-id="bb91b-153">Manage alerts</span></span>

<span data-ttu-id="bb91b-154">Per gestire un avviso, selezionare l'avviso nella coda degli avvisi nella riga corrispondente per visualizzare un **riquadro Gestisci** avviso.</span><span class="sxs-lookup"><span data-stu-id="bb91b-154">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="bb91b-155">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="bb91b-155">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Esempio del riquadro di riepilogo per un avviso":::

<span data-ttu-id="bb91b-157">Il **riquadro Gestisci** avviso consente di specificare:</span><span class="sxs-lookup"><span data-stu-id="bb91b-157">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="bb91b-158">Stato dell'avviso (Nuovo, Risolto, In corso).</span><span class="sxs-lookup"><span data-stu-id="bb91b-158">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="bb91b-159">Classificazione dell'avviso (Non impostato, True alert, False Alert).</span><span class="sxs-lookup"><span data-stu-id="bb91b-159">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="bb91b-160">Per la classificazione come avviso vero, il tipo di minaccia per l'avviso nel **campo Determinazione.**</span><span class="sxs-lookup"><span data-stu-id="bb91b-160">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="bb91b-161">Commento sull'avviso.</span><span class="sxs-lookup"><span data-stu-id="bb91b-161">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="bb91b-162">Un modo per gestire gli avvisi tramite l'uso di tag.</span><span class="sxs-lookup"><span data-stu-id="bb91b-162">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="bb91b-163">La funzionalità di tagging per Microsoft Defender per Office 365 è in fase di implementazione incrementale ed è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="bb91b-163">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="bb91b-164">Attualmente, i nomi dei tag modificati vengono applicati solo agli avvisi creati *dopo l'aggiornamento.*</span><span class="sxs-lookup"><span data-stu-id="bb91b-164">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="bb91b-165">Gli avvisi generati prima della modifica non rifletteranno il nome del tag aggiornato.</span><span class="sxs-lookup"><span data-stu-id="bb91b-165">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="bb91b-166">Da questo riquadro è inoltre possibile eseguire queste azioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="bb91b-166">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="bb91b-167">Aprire la pagina di avviso principale</span><span class="sxs-lookup"><span data-stu-id="bb91b-167">Open the main alert page</span></span>
- <span data-ttu-id="bb91b-168">Consultare un esperto di minacce Microsoft</span><span class="sxs-lookup"><span data-stu-id="bb91b-168">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="bb91b-169">Visualizzare l'invio</span><span class="sxs-lookup"><span data-stu-id="bb91b-169">View submission</span></span>
- <span data-ttu-id="bb91b-170">Collegamento a un altro evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="bb91b-170">Link to another incident</span></span>
- <span data-ttu-id="bb91b-171">Visualizzare l'avviso in una sequenza temporale</span><span class="sxs-lookup"><span data-stu-id="bb91b-171">See the alert in a timeline</span></span>
- <span data-ttu-id="bb91b-172">Creare una regola di eliminazione</span><span class="sxs-lookup"><span data-stu-id="bb91b-172">Create a suppression rule</span></span>

<span data-ttu-id="bb91b-173">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="bb91b-173">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Esempio di azioni su un avviso nel Centro sicurezza Microsoft 365":::

<span data-ttu-id="bb91b-175">L'elenco delle azioni aggiuntive dipende dal tipo di avviso.</span><span class="sxs-lookup"><span data-stu-id="bb91b-175">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="bb91b-176">Risolvere un avviso</span><span class="sxs-lookup"><span data-stu-id="bb91b-176">Resolve an alert</span></span>

<span data-ttu-id="bb91b-177">Una volta completata l'analisi di un avviso e  può essere risolto, passare al  riquadro Gestisci avviso per l'avviso e contrassegnarlo come Risolto e classificarlo come **avviso False** o **True.**</span><span class="sxs-lookup"><span data-stu-id="bb91b-177">Once you're done investigating an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="bb91b-178">Per gli avvisi veri, specificare il tipo di minaccia dell'avviso nel **campo Determinazione.**</span><span class="sxs-lookup"><span data-stu-id="bb91b-178">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="bb91b-179">Classificare gli avvisi e specificarne la determinazione aiuta a ottimizzare Microsoft 365 Defender per fornire avvisi più veri e meno falsi.</span><span class="sxs-lookup"><span data-stu-id="bb91b-179">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb91b-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb91b-180">See also</span></span>

- [<span data-ttu-id="bb91b-181">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="bb91b-181">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="bb91b-182">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="bb91b-182">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="bb91b-183">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="bb91b-183">Manage incidents</span></span>](manage-incidents.md)
