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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 382cfd374c40d0c5a0dd7d7705281bd56263d8b8
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430824"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="47282-104">Assegnare priorità agli eventi imprevisti in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="47282-104">Prioritize incidents in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="47282-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="47282-105">**Applies to:**</span></span>
- <span data-ttu-id="47282-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="47282-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="47282-107">Microsoft Threat Protection applica analisi di correlazione e aggrega tutti gli avvisi e le indagini correlate di prodotti diversi in un unico evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="47282-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="47282-108">Microsoft Threat Protection genera inoltre avvisi univoci sulle attività che possono essere identificate solo come dannose, data la visibilità end-to-end che Microsoft Threat Protection ha su tutta la struttura e la famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="47282-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="47282-109">In questo modo, Microsoft Threat Protection agisce in un ambito di attacco più ampio e consente agli analisti delle operazioni di sicurezza di comprendere e gestire minacce complesse nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="47282-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="47282-110">La **coda degli eventi imprevisti** mostra una raccolta di eventi imprevisti contrassegnati da diversi dispositivi, utenti e cassette postali.</span><span class="sxs-lookup"><span data-stu-id="47282-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="47282-111">Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.</span><span class="sxs-lookup"><span data-stu-id="47282-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Immagine della coda eventi imprevisti](../../media/incidents-queue.png) 

<span data-ttu-id="47282-113">Per impostazione predefinita, la coda disponibile nel Centro sicurezza Microsoft 365 mostra gli eventi imprevisti verificatisi negli ultimi 30 giorni, con l'evento più recente visualizzato in testa all'elenco, consentendoti quindi di visualizzare prima gli eventi più recenti.</span><span class="sxs-lookup"><span data-stu-id="47282-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="47282-114">La coda degli eventi imprevisti dispone di colonne personalizzabili che rendono visibili le diverse caratteristiche dell'evento o delle entità che questo contiene e ti aiuta a scegliere in modo mirato gli eventi imprevisti a cui dare la priorità.</span><span class="sxs-lookup"><span data-stu-id="47282-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="47282-115">Per una maggiore visibilità a colpo d'occhio, la denominazione degli incidenti automatici genera nomi degli incidenti in base agli attributi di avviso, ad esempio il numero di endpoint coinvolti, gli utenti coinvolti, le origini di rilevamento o le categorie.</span><span class="sxs-lookup"><span data-stu-id="47282-115">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="47282-116">In questo modo è possibile comprendere rapidamente l'ambito dell'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="47282-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="47282-117">Ad esempio: *eventi a più fasi su più endpoint segnalati da più origini.*</span><span class="sxs-lookup"><span data-stu-id="47282-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="47282-118">Gli incidenti che sono stati precedenti all'implementazione della denominazione degli incidenti automatici non avranno il nome modificato.</span><span class="sxs-lookup"><span data-stu-id="47282-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="47282-119">La coda dispone anche di più opzioni di filtro, che, se applicate, consentono di avere un’idea globale di tutti gli eventi esistenti nell'ambiente o di concentrarsi su uno scenario o una minaccia specifici.</span><span class="sxs-lookup"><span data-stu-id="47282-119">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="47282-120">Applicando i filtri a una coda di eventi imprevisti puoi determinare quale evento richiede un’attenzione immediata.</span><span class="sxs-lookup"><span data-stu-id="47282-120">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="47282-121">Filtri disponibili</span><span class="sxs-lookup"><span data-stu-id="47282-121">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="47282-122">Stato</span><span class="sxs-lookup"><span data-stu-id="47282-122">Status</span></span>
<span data-ttu-id="47282-123">Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti.</span><span class="sxs-lookup"><span data-stu-id="47282-123">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="47282-124">Gravità</span><span class="sxs-lookup"><span data-stu-id="47282-124">Severity</span></span>
<span data-ttu-id="47282-125">Il livello di gravità di un evento indica l'impatto che questo può avere sulle risorse.</span><span class="sxs-lookup"><span data-stu-id="47282-125">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="47282-126">Maggiore sarà la gravità, maggiore sarà l'impatto e in genere l’evento richiederà quindi attenzione immediata.</span><span class="sxs-lookup"><span data-stu-id="47282-126">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="47282-127">Assegnato a (proprietario)</span><span class="sxs-lookup"><span data-stu-id="47282-127">Assigned to (owner)</span></span>
<span data-ttu-id="47282-128">Puoi scegliere di filtrare l'elenco selezionando gli eventi assegnati a un altro utente o quelli assegnati a te.</span><span class="sxs-lookup"><span data-stu-id="47282-128">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="47282-129">Più avvisi</span><span class="sxs-lookup"><span data-stu-id="47282-129">Multiple alerts</span></span> 
<span data-ttu-id="47282-130">Applica un filtro per visualizzare solo gli eventi imprevisti che contengono più di un avviso.</span><span class="sxs-lookup"><span data-stu-id="47282-130">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="47282-131">Potrebbe indicare un attacco più complesso o a uno stadio più avanzato nella kill chain.</span><span class="sxs-lookup"><span data-stu-id="47282-131">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="47282-132">Più servizi di origine</span><span class="sxs-lookup"><span data-stu-id="47282-132">Multiple service sources</span></span> 
<span data-ttu-id="47282-133">Filtra in modo da visualizzare solo gli eventi che contengono avvisi provenienti da diverse origini (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="47282-133">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="47282-134">Servizi di origine</span><span class="sxs-lookup"><span data-stu-id="47282-134">Service sources</span></span>
<span data-ttu-id="47282-135">Scegliendo un’origine specifica puoi concentrarti sugli eventi imprevisti che contengono almeno un avviso dall'origine selezionata.</span><span class="sxs-lookup"><span data-stu-id="47282-135">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="47282-136">Più categorie</span><span class="sxs-lookup"><span data-stu-id="47282-136">Multiple categories</span></span> 
<span data-ttu-id="47282-137">Puoi scegliere di visualizzare solo gli eventi imprevisti associati a più categorie della kill chain e che potenzialmente possono causare più danni.</span><span class="sxs-lookup"><span data-stu-id="47282-137">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="47282-138">Categorie</span><span class="sxs-lookup"><span data-stu-id="47282-138">Categories</span></span>
<span data-ttu-id="47282-139">Scegli delle categorie specifiche per concentrarti su un passaggio specifico della kill chain.</span><span class="sxs-lookup"><span data-stu-id="47282-139">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="47282-140">Riservatezza dei dati</span><span class="sxs-lookup"><span data-stu-id="47282-140">Data sensitivity</span></span>
<span data-ttu-id="47282-141">Alcuni attacchi sono incentrati sull’estrazione di dati riservati o di valore.</span><span class="sxs-lookup"><span data-stu-id="47282-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="47282-142">Applicando un filtro per vedere se sono coinvolte informazioni riservate nell'evento, puoi determinare rapidamente se le informazioni riservate sono potenzialmente compromesse e assegnare priorità all'intervento.</span><span class="sxs-lookup"><span data-stu-id="47282-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="47282-143">Applicabile solo se Microsoft Information Protection è attivo.</span><span class="sxs-lookup"><span data-stu-id="47282-143">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="47282-144">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="47282-144">Next steps</span></span>
<span data-ttu-id="47282-145">Dopo aver individuato l'evento che richiede maggiore priorità, puoi continuare eseguendo ulteriori operazioni di indagine su un evento.</span><span class="sxs-lookup"><span data-stu-id="47282-145">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="47282-146">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="47282-146">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="47282-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="47282-147">Related topics</span></span>
- [<span data-ttu-id="47282-148">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="47282-148">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="47282-149">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="47282-149">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="47282-150">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="47282-150">Manage incidents</span></span>](manage-incidents.md)
