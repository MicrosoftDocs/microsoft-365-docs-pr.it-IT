---
title: Visualizzare e organizzare l'elenco di dispositivi Microsoft Defender for Endpoint
description: Informazioni sulle funzionalità disponibili che è possibile usare nell'elenco Dispositivi, ad esempio l'ordinamento, il filtro e l'esportazione dell'elenco per migliorare le indagini.
keywords: ordinare, filtrare, esportare, csv, nome del dispositivo, dominio, ultimo visto, IP interno, stato di integrità, avvisi attivi, rilevamenti di malware attivi, categoria di minacce, rivedere avvisi, rete, connessione, malware, tipo, furto di password, ransomware, exploit, minaccia, malware generale, software indesiderato
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a031a35929f319e87a9ad1a9ca48d6bf95a3ef72
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861576"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="f3a32-104">Visualizzare e organizzare l'elenco di Microsoft Defender per dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="f3a32-104">View and organize the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f3a32-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f3a32-105">**Applies to:**</span></span>
- [<span data-ttu-id="f3a32-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f3a32-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f3a32-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3a32-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f3a32-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f3a32-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f3a32-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f3a32-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


<span data-ttu-id="f3a32-110">**L'elenco Dispositivi** mostra un elenco dei dispositivi nella rete in cui sono stati generati gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="f3a32-110">The **Devices list** shows a list of the devices in your network where alerts were generated.</span></span> <span data-ttu-id="f3a32-111">Per impostazione predefinita, la coda visualizza i dispositivi visualizzati negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f3a32-111">By default, the queue displays devices seen in the last 30 days.</span></span>  

<span data-ttu-id="f3a32-112">A colpo d'occhio vedrai informazioni quali dominio, livello di rischio, piattaforma del sistema operativo e altri dettagli per una facile identificazione dei dispositivi più a rischio.</span><span class="sxs-lookup"><span data-stu-id="f3a32-112">At a glance you'll see information such as domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

<span data-ttu-id="f3a32-113">Puoi scegliere tra diverse opzioni per personalizzare la visualizzazione elenco dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f3a32-113">There are several options you can choose from to customize the devices list view.</span></span> <span data-ttu-id="f3a32-114">Nella barra di spostamento superiore è possibile:</span><span class="sxs-lookup"><span data-stu-id="f3a32-114">On the top navigation you can:</span></span>

- <span data-ttu-id="f3a32-115">Aggiungere o rimuovere colonne</span><span class="sxs-lookup"><span data-stu-id="f3a32-115">Add or remove columns</span></span>
- <span data-ttu-id="f3a32-116">Esportare l'intero elenco in formato CSV</span><span class="sxs-lookup"><span data-stu-id="f3a32-116">Export the entire list in CSV format</span></span>
- <span data-ttu-id="f3a32-117">Selezionare il numero di elementi da visualizzare per pagina</span><span class="sxs-lookup"><span data-stu-id="f3a32-117">Select the number of items to show per page</span></span>
- <span data-ttu-id="f3a32-118">Applicazione di filtri</span><span class="sxs-lookup"><span data-stu-id="f3a32-118">Apply filters</span></span>

<span data-ttu-id="f3a32-119">Durante il processo di onboarding, **l'elenco Dispositivi** viene gradualmente popolato con i dispositivi quando iniziano a segnalare i dati del sensore.</span><span class="sxs-lookup"><span data-stu-id="f3a32-119">During the onboarding process, the **Devices list** is gradually populated with devices as they begin to report sensor data.</span></span> <span data-ttu-id="f3a32-120">Usa questa visualizzazione per tenere traccia degli endpoint onboarded quando vengono online o scarica l'elenco completo degli endpoint come file CSV per l'analisi offline.</span><span class="sxs-lookup"><span data-stu-id="f3a32-120">Use this view to track your onboarded endpoints as they come online, or download the complete endpoint list as a CSV file for offline analysis.</span></span>

>[!NOTE]
> <span data-ttu-id="f3a32-121">Se esporti l'elenco dei dispositivi, conterrà tutti i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f3a32-121">If you export the device list, it will contain every device in your organization.</span></span> <span data-ttu-id="f3a32-122">Il download potrebbe richiedere molto tempo, a seconda delle dimensioni dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f3a32-122">It might take a significant amount of time to download, depending on how large your organization is.</span></span> <span data-ttu-id="f3a32-123">L'esportazione dell'elenco in formato CSV consente di visualizzare i dati in modo non filtrato.</span><span class="sxs-lookup"><span data-stu-id="f3a32-123">Exporting the list in CSV format displays the data in an unfiltered manner.</span></span> <span data-ttu-id="f3a32-124">Il file CSV includerà tutti i dispositivi nell'organizzazione, indipendentemente dal filtro applicato nella visualizzazione stessa.</span><span class="sxs-lookup"><span data-stu-id="f3a32-124">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself.</span></span>

![Immagine dell'elenco dei dispositivi con l'elenco dei dispositivi](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a><span data-ttu-id="f3a32-126">Ordinare e filtrare l'elenco dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="f3a32-126">Sort and filter the device list</span></span>

<span data-ttu-id="f3a32-127">È possibile applicare i filtri seguenti per limitare l'elenco degli avvisi e ottenere una visualizzazione più mirata.</span><span class="sxs-lookup"><span data-stu-id="f3a32-127">You can apply the following filters to limit the list of alerts and get a more focused view.</span></span>

### <a name="risk-level"></a><span data-ttu-id="f3a32-128">Livello di rischio</span><span class="sxs-lookup"><span data-stu-id="f3a32-128">Risk level</span></span>

<span data-ttu-id="f3a32-129">Il livello di rischio riflette la valutazione complessiva dei rischi del dispositivo in base a una combinazione di fattori, inclusi i tipi e la gravità degli avvisi attivi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f3a32-129">The risk level reflects the overall risk assessment of the device based on a combination of factors, including the types and severity of active alerts on the device.</span></span> <span data-ttu-id="f3a32-130">La risoluzione degli avvisi attivi, l'approvazione delle attività di correzione e l'eliminazione degli avvisi successivi possono ridurre il livello di rischio.</span><span class="sxs-lookup"><span data-stu-id="f3a32-130">Resolving active alerts, approving remediation activities, and suppressing subsequent alerts can lower the risk level.</span></span>

### <a name="exposure-level"></a><span data-ttu-id="f3a32-131">Livello di esposizione</span><span class="sxs-lookup"><span data-stu-id="f3a32-131">Exposure level</span></span>

<span data-ttu-id="f3a32-132">Il livello di esposizione riflette l'esposizione corrente del dispositivo in base all'impatto cumulativo delle raccomandazioni di sicurezza in sospeso.</span><span class="sxs-lookup"><span data-stu-id="f3a32-132">The exposure level reflects the current exposure of the device based on the cumulative impact of its pending security recommendations.</span></span> <span data-ttu-id="f3a32-133">I livelli possibili sono basso, medio e alto.</span><span class="sxs-lookup"><span data-stu-id="f3a32-133">The possible levels are low, medium, and high.</span></span> <span data-ttu-id="f3a32-134">Un'esposizione bassa significa che i dispositivi sono meno vulnerabili dallo sfruttamento.</span><span class="sxs-lookup"><span data-stu-id="f3a32-134">Low exposure means your devices are less vulnerable from exploitation.</span></span>

<span data-ttu-id="f3a32-135">Se il livello di esposizione indica "Nessun dato disponibile", esistono alcuni motivi per cui questo può essere il caso:</span><span class="sxs-lookup"><span data-stu-id="f3a32-135">If the exposure level says "No data available," there are a few reasons why this may be the case:</span></span>

- <span data-ttu-id="f3a32-136">Il dispositivo ha interrotto la segnalazione per più di 30 giorni, in questo caso è considerato inattivo e l'esposizione non viene calcolata</span><span class="sxs-lookup"><span data-stu-id="f3a32-136">Device stopped reporting for more than 30 days – in that case it is considered inactive, and the exposure isn't computed</span></span>
- <span data-ttu-id="f3a32-137">Sistema operativo del dispositivo non supportato: vedi [i requisiti minimi per Microsoft Defender per Endpoint](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="f3a32-137">Device OS not supported - see [minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)</span></span>
- <span data-ttu-id="f3a32-138">Dispositivo con agente obsoleto (molto improbabile)</span><span class="sxs-lookup"><span data-stu-id="f3a32-138">Device with stale agent (very unlikely)</span></span>

### <a name="os-platform"></a><span data-ttu-id="f3a32-139">Piattaforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="f3a32-139">OS Platform</span></span>

<span data-ttu-id="f3a32-140">Seleziona solo le piattaforme del sistema operativo che vuoi analizzare.</span><span class="sxs-lookup"><span data-stu-id="f3a32-140">Select only the OS platforms you're interested in investigating.</span></span>

### <a name="health-state"></a><span data-ttu-id="f3a32-141">Stato di integrità</span><span class="sxs-lookup"><span data-stu-id="f3a32-141">Health state</span></span>

<span data-ttu-id="f3a32-142">Filtra in base ai seguenti stati di integrità del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="f3a32-142">Filter by the following device health states:</span></span>

- <span data-ttu-id="f3a32-143">**Attivo:** dispositivi che segnalano attivamente i dati del sensore al servizio.</span><span class="sxs-lookup"><span data-stu-id="f3a32-143">**Active** – Devices that are actively reporting sensor data to the service.</span></span>
- <span data-ttu-id="f3a32-144">**Inattivo:** dispositivi che hanno interrotto completamente l'invio di segnali per più di 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="f3a32-144">**Inactive** – Devices that have completely stopped sending signals for more than 7 days.</span></span>
- <span data-ttu-id="f3a32-145">**Configurazione errata: i dispositivi** che hanno problemi di comunicazione con il servizio o non sono in grado di inviare dati del sensore.</span><span class="sxs-lookup"><span data-stu-id="f3a32-145">**Misconfigured** – Devices that have impaired communications with service or are unable to send sensor data.</span></span> <span data-ttu-id="f3a32-146">I dispositivi non configurati correttamente possono essere ulteriormente classificati in:</span><span class="sxs-lookup"><span data-stu-id="f3a32-146">Misconfigured devices can further be classified to:</span></span>
  - <span data-ttu-id="f3a32-147">Nessun dato sensore</span><span class="sxs-lookup"><span data-stu-id="f3a32-147">No sensor data</span></span>
  - <span data-ttu-id="f3a32-148">Comunicazioni con problemi</span><span class="sxs-lookup"><span data-stu-id="f3a32-148">Impaired communications</span></span>

  <span data-ttu-id="f3a32-149">Per altre informazioni su come risolvere i problemi relativi ai dispositivi non configurati correttamente, vedi Risolvere i sensori [non integri.](fix-unhealthy-sensors.md)</span><span class="sxs-lookup"><span data-stu-id="f3a32-149">For more information on how to address issues on misconfigured devices see, [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span></span>

### <a name="antivirus-status"></a><span data-ttu-id="f3a32-150">Stato antivirus</span><span class="sxs-lookup"><span data-stu-id="f3a32-150">Antivirus status</span></span>

<span data-ttu-id="f3a32-151">Filtrare i dispositivi in base allo stato antivirus.</span><span class="sxs-lookup"><span data-stu-id="f3a32-151">Filter devices by antivirus status.</span></span> <span data-ttu-id="f3a32-152">Si applica solo ai dispositivi Windows 10 attivi.</span><span class="sxs-lookup"><span data-stu-id="f3a32-152">Applies to active Windows 10 devices only.</span></span>

- <span data-ttu-id="f3a32-153">**Disabilitato:** la protezione da & virus è disattivata.</span><span class="sxs-lookup"><span data-stu-id="f3a32-153">**Disabled** - Virus & threat protection is turned off.</span></span>
- <span data-ttu-id="f3a32-154">**Not reporting** - Virus & threat protection is not reporting.</span><span class="sxs-lookup"><span data-stu-id="f3a32-154">**Not reporting** - Virus & threat protection is not reporting.</span></span>
- <span data-ttu-id="f3a32-155">**Non aggiornato:** la protezione da & virus non è aggiornata.</span><span class="sxs-lookup"><span data-stu-id="f3a32-155">**Not updated** - Virus & threat protection is not up to date.</span></span>

<span data-ttu-id="f3a32-156">Per ulteriori informazioni, vedere [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span><span class="sxs-lookup"><span data-stu-id="f3a32-156">For more information, see [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span></span>

### <a name="threat-mitigation-status"></a><span data-ttu-id="f3a32-157">Stato di mitigazione delle minacce</span><span class="sxs-lookup"><span data-stu-id="f3a32-157">Threat mitigation status</span></span>

<span data-ttu-id="f3a32-158">Per visualizzare i dispositivi che potrebbero essere interessati da una determinata minaccia, seleziona la minaccia dal menu a discesa e quindi seleziona l'aspetto di vulnerabilità da mitigare.</span><span class="sxs-lookup"><span data-stu-id="f3a32-158">To view devices that may be affected by a certain threat, select the threat from the dropdown menu, and then select what vulnerability aspect needs to be mitigated.</span></span>

<span data-ttu-id="f3a32-159">Per ulteriori informazioni su alcune minacce, vedere [Analisi delle minacce](threat-analytics.md).</span><span class="sxs-lookup"><span data-stu-id="f3a32-159">To learn more about certain threats, see [Threat analytics](threat-analytics.md).</span></span> <span data-ttu-id="f3a32-160">Per informazioni sulla mitigazione, vedere [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="f3a32-160">For mitigation information, see [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span>

### <a name="windows-10-version"></a><span data-ttu-id="f3a32-161">Versione di Windows 10</span><span class="sxs-lookup"><span data-stu-id="f3a32-161">Windows 10 version</span></span>

<span data-ttu-id="f3a32-162">Seleziona solo le versioni di Windows 10 che vuoi analizzare.</span><span class="sxs-lookup"><span data-stu-id="f3a32-162">Select only the Windows 10 versions you're interested in investigating.</span></span>

### <a name="tags--groups"></a><span data-ttu-id="f3a32-163">Tag & gruppi</span><span class="sxs-lookup"><span data-stu-id="f3a32-163">Tags & Groups</span></span>

<span data-ttu-id="f3a32-164">Filtra l'elenco in base al raggruppamento e al tagging che hai aggiunto ai singoli dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f3a32-164">Filter the list based on the grouping and tagging that you've added to individual devices.</span></span> <span data-ttu-id="f3a32-165">Vedi [Creare e gestire tag dispositivo](machine-tags.md) e Creare e gestire gruppi di [dispositivi.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="f3a32-165">See [Create and manage device tags](machine-tags.md) and [Create and manage device groups](machine-groups.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3a32-166">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f3a32-166">Related topics</span></span>

- [<span data-ttu-id="f3a32-167">Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="f3a32-167">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
