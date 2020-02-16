---
title: Assegnare priorità agli eventi imprevisti in Microsoft Threat Protection
description: Come assegnare priorità agli eventi imprevisti nella relativa coda in Microsoft Threat Protection
keywords: evento imprevisto, coda, panoramica, dispositivi, identità, utenti, cassetta postale, posta elettronica, eventi imprevisti
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 90f7aaf7eb4425dadeb27699654656c86d2b6263
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087301"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="b042c-104">Assegnare priorità agli eventi imprevisti in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b042c-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="b042c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b042c-105">**Applies to:**</span></span>
- <span data-ttu-id="b042c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b042c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b042c-107">Microsoft Threat Protection applica analisi di correlazione e aggrega tutti gli avvisi e le indagini correlate di prodotti diversi in un unico evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="b042c-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="b042c-108">Microsoft Threat Protection genera inoltre avvisi univoci sulle attività che possono essere identificate solo come dannose, data la visibilità end-to-end che Microsoft Threat Protection ha su tutta la struttura e la famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="b042c-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="b042c-109">In questo modo, Microsoft Threat Protection agisce in un ambito di attacco più ampio e consente agli analisti delle operazioni di sicurezza di comprendere e gestire minacce complesse nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b042c-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="b042c-110">La **coda degli eventi imprevisti** mostra una raccolta di eventi imprevisti contrassegnati da diversi dispositivi, utenti e cassette postali.</span><span class="sxs-lookup"><span data-stu-id="b042c-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="b042c-111">Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.</span><span class="sxs-lookup"><span data-stu-id="b042c-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Immagine della coda eventi imprevisti](../../media/incidents-queue.png) 

<span data-ttu-id="b042c-113">Per impostazione predefinita, la coda disponibile nel Centro sicurezza Microsoft 365 mostra gli eventi imprevisti verificatisi negli ultimi 30 giorni, con l'evento più recente visualizzato in testa all'elenco, consentendoti quindi di visualizzare prima gli eventi più recenti.</span><span class="sxs-lookup"><span data-stu-id="b042c-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="b042c-114">La coda degli eventi imprevisti dispone di colonne personalizzabili che rendono visibili le diverse caratteristiche dell'evento o delle entità che questo contiene e ti aiuta a scegliere in modo mirato gli eventi imprevisti a cui dare la priorità.</span><span class="sxs-lookup"><span data-stu-id="b042c-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span> 

<span data-ttu-id="b042c-115">La coda dispone anche di più opzioni di filtro, che, se applicate, consentono di avere un’idea globale di tutti gli eventi esistenti nell'ambiente o di concentrarsi su uno scenario o una minaccia specifici.</span><span class="sxs-lookup"><span data-stu-id="b042c-115">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="b042c-116">Applicando i filtri a una coda di eventi imprevisti puoi determinare quale evento richiede un’attenzione immediata.</span><span class="sxs-lookup"><span data-stu-id="b042c-116">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="b042c-117">Filtri disponibili</span><span class="sxs-lookup"><span data-stu-id="b042c-117">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="b042c-118">Stato</span><span class="sxs-lookup"><span data-stu-id="b042c-118">Status</span></span>
<span data-ttu-id="b042c-119">Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti.</span><span class="sxs-lookup"><span data-stu-id="b042c-119">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="b042c-120">Gravità</span><span class="sxs-lookup"><span data-stu-id="b042c-120">Severity</span></span>
<span data-ttu-id="b042c-121">Il livello di gravità di un evento indica l'impatto che questo può avere sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="b042c-121">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="b042c-122">Maggiore sarà la gravità, maggiore sarà l'impatto e in genere l’evento richiederà quindi attenzione immediata.</span><span class="sxs-lookup"><span data-stu-id="b042c-122">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="b042c-123">Assegnato a (proprietario)</span><span class="sxs-lookup"><span data-stu-id="b042c-123">Assigned to (owner)</span></span>
<span data-ttu-id="b042c-124">Puoi scegliere di filtrare l'elenco selezionando gli eventi assegnati a un altro utente o quelli assegnati a te.</span><span class="sxs-lookup"><span data-stu-id="b042c-124">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="b042c-125">Più avvisi</span><span class="sxs-lookup"><span data-stu-id="b042c-125">Multiple alerts</span></span> 
<span data-ttu-id="b042c-126">Applica un filtro per visualizzare solo gli eventi imprevisti che contengono più di un avviso.</span><span class="sxs-lookup"><span data-stu-id="b042c-126">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="b042c-127">Potrebbe indicare un attacco più complesso o a uno stadio più avanzato nella kill chain.</span><span class="sxs-lookup"><span data-stu-id="b042c-127">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="b042c-128">Più servizi di origine</span><span class="sxs-lookup"><span data-stu-id="b042c-128">Multiple service sources</span></span> 
<span data-ttu-id="b042c-129">Filtra in modo da visualizzare solo gli eventi che contengono avvisi provenienti da diverse origini (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="b042c-129">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="b042c-130">Servizi di origine</span><span class="sxs-lookup"><span data-stu-id="b042c-130">Service sources</span></span>
<span data-ttu-id="b042c-131">Scegliendo un’origine specifica puoi concentrarti sugli eventi imprevisti che contengono almeno un avviso dall'origine selezionata.</span><span class="sxs-lookup"><span data-stu-id="b042c-131">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="b042c-132">Più categorie</span><span class="sxs-lookup"><span data-stu-id="b042c-132">Multiple categories</span></span> 
<span data-ttu-id="b042c-133">Puoi scegliere di visualizzare solo gli eventi imprevisti associati a più categorie della kill chain e che potenzialmente possono causare più danni.</span><span class="sxs-lookup"><span data-stu-id="b042c-133">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="b042c-134">Categorie</span><span class="sxs-lookup"><span data-stu-id="b042c-134">Categories</span></span>
<span data-ttu-id="b042c-135">Scegli delle categorie specifiche per concentrarti su un passaggio specifico della kill chain.</span><span class="sxs-lookup"><span data-stu-id="b042c-135">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="b042c-136">Riservatezza dei dati</span><span class="sxs-lookup"><span data-stu-id="b042c-136">Data sensitivity</span></span>
<span data-ttu-id="b042c-137">Alcuni attacchi sono incentrati sull’estrazione di dati riservati o di valore.</span><span class="sxs-lookup"><span data-stu-id="b042c-137">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="b042c-138">Applicando un filtro per vedere se sono coinvolte informazioni riservate nell'evento, puoi determinare rapidamente se le informazioni riservate sono potenzialmente compromesse e assegnare priorità all'intervento.</span><span class="sxs-lookup"><span data-stu-id="b042c-138">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="b042c-139">Applicabile solo se Microsoft Information Protection è attivo.</span><span class="sxs-lookup"><span data-stu-id="b042c-139">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="b042c-140">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b042c-140">Next steps</span></span>
<span data-ttu-id="b042c-141">Dopo aver individuato l'evento che richiede maggiore priorità, puoi continuare eseguendo ulteriori operazioni di indagine su un evento.</span><span class="sxs-lookup"><span data-stu-id="b042c-141">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="b042c-142">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="b042c-142">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="b042c-143">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b042c-143">Related topics</span></span>
- [<span data-ttu-id="b042c-144">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="b042c-144">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b042c-145">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="b042c-145">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="b042c-146">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="b042c-146">Manage incidents</span></span>](manage-incidents.md)
