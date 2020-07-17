---
title: Visualizzare l'utilizzo delle etichette con Analisi delle etichette
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come visualizzare rapidamente le etichette di conservazione e di riservatezza usate più di frequente, e su dove vengono applicate.
ms.openlocfilehash: 89ccdce54b0d7e6146260037b8dcb085631b408e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817505"
---
# <a name="view-label-usage-with-label-analytics"></a><span data-ttu-id="f3873-103">Visualizzare l'utilizzo delle etichette con Analisi delle etichette</span><span class="sxs-lookup"><span data-stu-id="f3873-103">View label usage with label analytics</span></span>

<span data-ttu-id="f3873-104">Dopo aver creato le etichette di conservazione e le etichette di riservatezza, è opportuno verificare l'utilizzo nel tenant.</span><span class="sxs-lookup"><span data-stu-id="f3873-104">After you create your retention labels and sensitivity labels, you’ll want to see how they’re being used across your tenant.</span></span> <span data-ttu-id="f3873-105">Con Analisi delle etichette, disponibile nel Centro conformità Microsoft 365 e nel Centro sicurezza Microsoft 365, è possibile visualizzare rapidamente le etichette usate più di frequente e sapere dove vengono applicate.</span><span class="sxs-lookup"><span data-stu-id="f3873-105">With label analytics in the Microsoft 365 compliance center and Microsoft 365 security center, you can quickly see which labels are used the most and where they’re being applied.</span></span>

<span data-ttu-id="f3873-106">Ad esempio, con Analisi delle etichette è possibile visualizzare:</span><span class="sxs-lookup"><span data-stu-id="f3873-106">For example, with label analytics, you can view the:</span></span>

- <span data-ttu-id="f3873-107">Il numero totale di etichette di conservazione e di etichette di riservatezza applicate al contenuto.</span><span class="sxs-lookup"><span data-stu-id="f3873-107">Total number of retention labels and sensitivity labels applied to content.</span></span>
- <span data-ttu-id="f3873-108">Le etichette principali e il numero di volte in cui è stata applicata ogni etichetta.</span><span class="sxs-lookup"><span data-stu-id="f3873-108">Top labels and the count of how many times each label was applied.</span></span>
- <span data-ttu-id="f3873-109">Le posizioni in cui vengono applicate le etichette e il conteggio relativo a ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="f3873-109">Locations where labels are applied and the count for each location.</span></span>
- <span data-ttu-id="f3873-110">Il conteggio del numero di file e cartelle di cui è stata modificata o rimossa l'etichetta di conservazione.</span><span class="sxs-lookup"><span data-stu-id="f3873-110">Count for how many files and folders had their retention label changed or removed.</span></span>

<span data-ttu-id="f3873-111">La funzionalità Analisi delle etichette è disponibile nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/labelanalytics)o nel [Centro sicurezza Microsoft 365](https://security.microsoft.com/labelanalytics) > **Classificazione** > **Analisi delle etichette**.</span><span class="sxs-lookup"><span data-stu-id="f3873-111">You can find label analytics in the [Microsoft 365 compliance center](https://compliance.microsoft.com/labelanalytics) or [Microsoft 365 security center](https://security.microsoft.com/labelanalytics) > **Classification** > **Label analytics**.</span></span>

![Pagina di >Analisi delle etichette](../media/label-analytics-page.png)

## <a name="sensitivity-label-usage"></a><span data-ttu-id="f3873-113">Utilizzo dell'etichetta di riservatezza</span><span class="sxs-lookup"><span data-stu-id="f3873-113">Sensitivity label usage</span></span>

<span data-ttu-id="f3873-114">I dati relativi all'utilizzo dell'etichetta di riservatezza vengono estratti dai report di Azure Information Protection. Per altre informazioni, vedere [Reporting centralizzato per Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span><span class="sxs-lookup"><span data-stu-id="f3873-114">The data on sensitivity label usage is pulled from the reports for Azure Information Protection – for more information, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="f3873-115">Tenere presente che i [prerequisiti](/azure/information-protection/reports-aip#prerequisites) dei report di Azure Information Protection si applicano anche ad Analisi delle etichette per le etichette di riservatezza nel Centro conformità Microsoft 365 e nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3873-115">Note that the Azure Information Protection reports have [prerequisites](/azure/information-protection/reports-aip#prerequisites) that also apply to label analytics on sensitivity labels in the Microsoft 365 compliance center and Microsoft 365 security center.</span></span> <span data-ttu-id="f3873-116">È ad esempio necessaria una sottoscrizione di Azure che include Log Analytics perché questi report vengono generati in seguito all'invio di eventi di controllo per la protezione delle informazioni da client e scanner di Azure Information Protection a una posizione centralizzata basata sul servizio Azure Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="f3873-116">For example, you need an Azure subscription that includes the Log Analytics because these reports are a result of sending information protection audit events from Azure Information Protection clients and scanners to a centralized location based on Azure Log Analytics service.</span></span>

<span data-ttu-id="f3873-117">Per l'utilizzo delle etichette di riservatezza:</span><span class="sxs-lookup"><span data-stu-id="f3873-117">For sensitivity label usage:</span></span>

- <span data-ttu-id="f3873-118">Non è prevista latenza nei dati.</span><span class="sxs-lookup"><span data-stu-id="f3873-118">There is no latency in the data.</span></span> <span data-ttu-id="f3873-119">Si tratta di un report in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="f3873-119">This is a real-time report.</span></span>
- <span data-ttu-id="f3873-120">Per visualizzare il conteggio per ogni etichetta principale, selezionare il grafico a barre e leggere la descrizione comando visualizzata.</span><span class="sxs-lookup"><span data-stu-id="f3873-120">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="f3873-121">Il report mostra la posizione in cui sono applicate le etichette di riservatezza in base all'app (mentre le etichette di conservazione vengono visualizzate in base alla posizione).</span><span class="sxs-lookup"><span data-stu-id="f3873-121">The report shows where sensitivity labels are applied per app (whereas retention labels are shown per location).</span></span>

![Report sull'utilizzo delle etichetta di riservatezza](../media/sensitivity-label-usage-report.png)

## <a name="retention-label-usage"></a><span data-ttu-id="f3873-123">Utilizzo delle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="f3873-123">Retention label usage</span></span>

<span data-ttu-id="f3873-124">Questo report mostra un'anteprima rapida delle etichette principali e della posizione in cui vengono applicate.</span><span class="sxs-lookup"><span data-stu-id="f3873-124">This report shows a quick view of what the top labels are and where they’re applied.</span></span> <span data-ttu-id="f3873-125">Per informazioni più dettagliate sulla modalità di applicazione delle etichette al contenuto in SharePoint e OneDrive, vedere [Visualizzare le attività con etichette per i documenti](view-label-activity-for-documents.md).</span><span class="sxs-lookup"><span data-stu-id="f3873-125">For more detailed information on how content in SharePoint and OneDrive is labeled, see [View label activity for documents](view-label-activity-for-documents.md).</span></span>

<span data-ttu-id="f3873-126">Per l'utilizzo delle etichette di conservazione:</span><span class="sxs-lookup"><span data-stu-id="f3873-126">For retention label usage:</span></span>

- <span data-ttu-id="f3873-127">I dati vengono aggregati settimanalmente, quindi la visualizzazione dei dati nel report può richiedere fino a sette giorni.</span><span class="sxs-lookup"><span data-stu-id="f3873-127">Data is aggregated weekly, so it may take up to seven days for data to appear in the report.</span></span>
- <span data-ttu-id="f3873-128">Per visualizzare il conteggio per ogni etichetta principale, selezionare il grafico a barre e leggere la descrizione comando visualizzata.</span><span class="sxs-lookup"><span data-stu-id="f3873-128">To see the count for each top label, point to the bar graph and read the tool tip that appears.</span></span>
- <span data-ttu-id="f3873-129">Il report mostra la posizione in cui sono applicate le etichette di conservazione in base alla posizione (mentre le etichette di riservatezza vengono visualizzate in base all'app).</span><span class="sxs-lookup"><span data-stu-id="f3873-129">The report shows where retention labels are applied per location (whereas sensitivity labels are shown per app).</span></span>
- <span data-ttu-id="f3873-130">Per le etichette di conservazione si tratta di un riepilogo di tutti i dati del tenant non filtrati in base a un intervallo di date specifico.</span><span class="sxs-lookup"><span data-stu-id="f3873-130">For retention labels, this is a summary of the all-time data in your tenant; it’s not filtered to a specific date range.</span></span> <span data-ttu-id="f3873-131">Con [Explorer attività etichette](view-label-activity-for-documents.md) sono invece visualizzati solo i dati relativi agli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f3873-131">By contrast, the [Label Activity Explorer](view-label-activity-for-documents.md) shows data from only the past 30 days.</span></span>

![Report sull'utilizzo delle etichette di conservazione](../media/retention-label-usage-report.png)

## <a name="view-all-content-with-a-specific-retention-label"></a><span data-ttu-id="f3873-133">Visualizzare tutto il contenuto con una specifica etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="f3873-133">View all content with a specific retention label</span></span>

<span data-ttu-id="f3873-134">Dal report sull'utilizzo delle etichette di conservazione è possibile esplorare rapidamente tutto il contenuto a cui è applicata una data etichetta.</span><span class="sxs-lookup"><span data-stu-id="f3873-134">From the retention label usage report, you can quickly explore all content with that label applied.</span></span> <span data-ttu-id="f3873-135">Questa funzionalità è attualmente in corso di modifica per consentire di ridurre il numero di passaggi necessari per visualizzare tutto il contenuto con etichetta.</span><span class="sxs-lookup"><span data-stu-id="f3873-135">(Note that we're currently working on this feature, so that it will take fewer steps to view all the labeled content.)</span></span>

<span data-ttu-id="f3873-136">Scegliere prima di tutto **Visualizza dettagli** nella parte inferiore del report.</span><span class="sxs-lookup"><span data-stu-id="f3873-136">First, choose **View Details** at the bottom of the report.</span></span>

![Opzione Visualizza dettagli nella parte inferiore del report sull'utilizzo delle etichette di conservazione](../media/retention-label-usage-view-details.png)

<span data-ttu-id="f3873-138">Scegliere quindi un'etichetta di conservazione > **Esplora gli elementi** nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="f3873-138">Then choose a retention label > **Explore items** in the right pane.</span></span>

![Opzione Esplorare gli elementi nel riquadro destro](../media/retention-label-usage-explore-items.png)

<span data-ttu-id="f3873-140">Per tale etichetta è possibile scegliere la scheda **Attività** per visualizzare il numero di elementi che includono l'etichetta in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="f3873-140">For that label, you can choose the **Activity** tab to view a count of items with that label by location.</span></span>

![Scheda Attività per un'etichetta di conservazione](../media/retention-label-usage-activity-tab.png)

<span data-ttu-id="f3873-142">È anche possibile scegliere la scheda **Elementi con questa etichetta** per accedere a posizioni specifiche:</span><span class="sxs-lookup"><span data-stu-id="f3873-142">You can also choose the **Items with this label** tab. Then you can drill into specific locations:</span></span>

- <span data-ttu-id="f3873-143">Per Exchange Online viene visualizzato un elenco di cassette postali con il conteggio degli elementi con etichetta in ogni cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="f3873-143">For Exchange Online, you see a list of mailboxes with the count of labeled items in each mailbox.</span></span>
- <span data-ttu-id="f3873-144">Per SharePoint Online e OneDrive for Business viene visualizzato un elenco di raccolte siti e account di OneDrive con il conteggio degli elementi con etichetta in ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="f3873-144">For SharePoint Online and OneDrive for Business, you see a list of site collections and OneDrive accounts with the count of labeled items in each location.</span></span>

<span data-ttu-id="f3873-145">Quando si sceglie una cassetta postale o una raccolta siti, è possibile visualizzare un elenco degli elementi con tale etichetta di conservazione nella posizione specifica.</span><span class="sxs-lookup"><span data-stu-id="f3873-145">When you choose a mailbox or site collection, you can view a list of items with that retention label in that location.</span></span>

![Scheda Elementi con questa etichetta che mostra tutti gli elementi con l'etichetta di conservazione specificata](../media/retention-label-usage-content-explorer.png)

## <a name="permissions"></a><span data-ttu-id="f3873-147">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f3873-147">Permissions</span></span>

<span data-ttu-id="f3873-148">Per visualizzare l'analisi delle etichette, è necessario disporre di uno dei ruoli seguenti in Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="f3873-148">To view label analytics, you must be assigned one of the following roles in Azure Active Directory:</span></span>

- <span data-ttu-id="f3873-149">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="f3873-149">Global administrator</span></span>
- <span data-ttu-id="f3873-150">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="f3873-150">Compliance administrator</span></span>
- <span data-ttu-id="f3873-151">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="f3873-151">Security administrator</span></span>
- <span data-ttu-id="f3873-152">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="f3873-152">Security reader</span></span>

<span data-ttu-id="f3873-153">Con questi report viene inoltre usato Monitoraggio di Azure per archiviare i dati in un'area di lavoro Log Analytics di proprietà dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f3873-153">In addition, note these reports use Azure Monitor to store the data in a Log Analytics workspace that your organization owns.</span></span> <span data-ttu-id="f3873-154">È quindi opportuno aggiungere l'utente come lettore all'area di lavoro di Monitoraggio di Azure in cui sono archiviati i dati. Per altre informazioni, vedere [Autorizzazioni necessarie per la funzionalità di analisi di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span><span class="sxs-lookup"><span data-stu-id="f3873-154">Therefore, the user should be added as a reader to the Azure Monitoring workspace that holds the data - for more information, see [Permissions required for Azure Information Protection analytics](https://docs.microsoft.com/azure/information-protection/reports-aip#permissions-required-for-azure-information-protection-analytics).</span></span>

