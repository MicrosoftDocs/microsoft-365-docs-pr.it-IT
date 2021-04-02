---
title: Visualizzare e organizzare la coda degli incidenti
ms.reviewer: ''
description: Vedi l'elenco degli eventi imprevisti e scopri come applicare filtri per limitare l'elenco e ottenere una visualizzazione più mirata.
keywords: visualizzazione, organizzazione, eventi imprevisti, aggregazione, indagini, coda, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93aa685f12e0241758bf86d3aa956717db052e5f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499929"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="829a4-104">Visualizzare e organizzare la coda eventi imprevisti di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="829a4-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="829a4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="829a4-105">**Applies to:**</span></span>
- [<span data-ttu-id="829a4-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="829a4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="829a4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="829a4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="829a4-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="829a4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="829a4-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="829a4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="829a4-110">La **coda Eventi imprevisti** mostra una raccolta di eventi imprevisti contrassegnati dai dispositivi della rete.</span><span class="sxs-lookup"><span data-stu-id="829a4-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="829a4-111">Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata.</span><span class="sxs-lookup"><span data-stu-id="829a4-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="829a4-112">Per impostazione predefinita, nella coda vengono visualizzati gli eventi imprevisti visualizzati negli ultimi 30 giorni, con l'evento imprevisto più recente visualizzato all'inizio dell'elenco, consentendo di visualizzare prima gli eventi imprevisti più recenti.</span><span class="sxs-lookup"><span data-stu-id="829a4-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="829a4-113">Sono disponibili diverse opzioni tra cui scegliere per personalizzare la visualizzazione della coda eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="829a4-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="829a4-114">Nella barra di spostamento superiore è possibile:</span><span class="sxs-lookup"><span data-stu-id="829a4-114">On the top navigation you can:</span></span>
- <span data-ttu-id="829a4-115">Personalizzare le colonne per aggiungere o rimuovere colonne</span><span class="sxs-lookup"><span data-stu-id="829a4-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="829a4-116">Modificare il numero di elementi da visualizzare per pagina</span><span class="sxs-lookup"><span data-stu-id="829a4-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="829a4-117">Selezionare gli elementi da visualizzare per pagina</span><span class="sxs-lookup"><span data-stu-id="829a4-117">Select the items to show per page</span></span>
- <span data-ttu-id="829a4-118">Selezionare in batch gli eventi imprevisti da assegnare</span><span class="sxs-lookup"><span data-stu-id="829a4-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="829a4-119">Spostarsi tra le pagine</span><span class="sxs-lookup"><span data-stu-id="829a4-119">Navigate between pages</span></span>
- <span data-ttu-id="829a4-120">Applicazione di filtri</span><span class="sxs-lookup"><span data-stu-id="829a4-120">Apply filters</span></span>

![Immagine della coda eventi imprevisti](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="829a4-122">Ordinare e filtrare la coda degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="829a4-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="829a4-123">È possibile applicare i filtri seguenti per limitare l'elenco degli eventi imprevisti e ottenere una visualizzazione più mirata.</span><span class="sxs-lookup"><span data-stu-id="829a4-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="829a4-124">Gravità</span><span class="sxs-lookup"><span data-stu-id="829a4-124">Severity</span></span>

<span data-ttu-id="829a4-125">Gravità evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="829a4-125">Incident severity</span></span> | <span data-ttu-id="829a4-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="829a4-126">Description</span></span>
:---|:---
<span data-ttu-id="829a4-127">Alta</span><span class="sxs-lookup"><span data-stu-id="829a4-127">High</span></span> </br><span data-ttu-id="829a4-128">(Rosso)</span><span class="sxs-lookup"><span data-stu-id="829a4-128">(Red)</span></span> | <span data-ttu-id="829a4-129">Minacce spesso associate a minacce persistenti avanzate (APT).</span><span class="sxs-lookup"><span data-stu-id="829a4-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="829a4-130">Questi eventi imprevisti indicano un rischio elevato a causa della gravità dei danni che possono infliggere ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="829a4-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="829a4-131">Medio</span><span class="sxs-lookup"><span data-stu-id="829a4-131">Medium</span></span> </br><span data-ttu-id="829a4-132">(Arancione)</span><span class="sxs-lookup"><span data-stu-id="829a4-132">(Orange)</span></span> | <span data-ttu-id="829a4-133">Minacce raramente osservate nell'organizzazione, ad esempio modifiche anomali del Registro di sistema, esecuzione di file sospetti e comportamenti osservati tipici delle fasi di attacco.</span><span class="sxs-lookup"><span data-stu-id="829a4-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="829a4-134">Bassa</span><span class="sxs-lookup"><span data-stu-id="829a4-134">Low</span></span> </br><span data-ttu-id="829a4-135">(Giallo)</span><span class="sxs-lookup"><span data-stu-id="829a4-135">(Yellow)</span></span> | <span data-ttu-id="829a4-136">Minacce associate a malware e strumenti di hacking prevalenti che non indicano necessariamente una minaccia avanzata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="829a4-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="829a4-137">Informativo</span><span class="sxs-lookup"><span data-stu-id="829a4-137">Informational</span></span> </br><span data-ttu-id="829a4-138">(Grigio)</span><span class="sxs-lookup"><span data-stu-id="829a4-138">(Grey)</span></span> | <span data-ttu-id="829a4-139">Gli incidenti in informazioni potrebbero non essere considerati dannosi per la rete, ma potrebbero essere utili da tenere traccia.</span><span class="sxs-lookup"><span data-stu-id="829a4-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="829a4-140">Assegnata a</span><span class="sxs-lookup"><span data-stu-id="829a4-140">Assigned to</span></span>
<span data-ttu-id="829a4-141">Puoi scegliere di filtrare l'elenco selezionando gli eventi assegnati a un altro utente o quelli assegnati a te.</span><span class="sxs-lookup"><span data-stu-id="829a4-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="829a4-142">Categoria</span><span class="sxs-lookup"><span data-stu-id="829a4-142">Category</span></span>
<span data-ttu-id="829a4-143">Gli incidenti vengono categorizzati in base alla descrizione della fase in cui si trova la catena di kill chain della sicurezza informatica.</span><span class="sxs-lookup"><span data-stu-id="829a4-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="829a4-144">Questa visualizzazione consente all'analista delle minacce di determinare la priorità, l'urgenza e la strategia di risposta corrispondente da distribuire in base al contesto.</span><span class="sxs-lookup"><span data-stu-id="829a4-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="829a4-145">Stato</span><span class="sxs-lookup"><span data-stu-id="829a4-145">Status</span></span>
<span data-ttu-id="829a4-146">Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti.</span><span class="sxs-lookup"><span data-stu-id="829a4-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="829a4-147">Riservatezza dei dati</span><span class="sxs-lookup"><span data-stu-id="829a4-147">Data sensitivity</span></span>
<span data-ttu-id="829a4-148">Utilizzare questo filtro per visualizzare gli eventi imprevisti che contengono etichette di riservatezza.</span><span class="sxs-lookup"><span data-stu-id="829a4-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="829a4-149">Denominazione degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="829a4-149">Incident naming</span></span>

<span data-ttu-id="829a4-150">Per comprendere a colpo d'occhio l'ambito dell'evento imprevisto, i nomi degli eventi imprevisti vengono generati automaticamente in base agli attributi di avviso, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie.</span><span class="sxs-lookup"><span data-stu-id="829a4-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="829a4-151">Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*</span><span class="sxs-lookup"><span data-stu-id="829a4-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="829a4-152">Gli eventi imprevisti esistenti prima dell'implementazione della denominazione automatica degli eventi imprevisti manterranno il nome.</span><span class="sxs-lookup"><span data-stu-id="829a4-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="829a4-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="829a4-153">See also</span></span>
- [<span data-ttu-id="829a4-154">Coda incidenti</span><span class="sxs-lookup"><span data-stu-id="829a4-154">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="829a4-155">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="829a4-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="829a4-156">Indagare sugli incidenti</span><span class="sxs-lookup"><span data-stu-id="829a4-156">Investigate incidents</span></span>](investigate-incidents.md)

