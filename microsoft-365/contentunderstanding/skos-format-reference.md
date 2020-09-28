---
title: Riferimento al formato SKOS per la tassonomia di SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: Riferimento al formato SKOS per la tassonomia di SharePoint
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296080"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="0d9fe-103">Riferimento al formato SKOS per la tassonomia di SharePoint</span><span class="sxs-lookup"><span data-stu-id="0d9fe-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="0d9fe-104">Questo articolo include il vocabolario RDF utilizzato per rappresentare la [Tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) e si basa su [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="0d9fe-105">Per la serializzazione di questa sintassi RDF, usare la [tartaruga](https://www.w3.org/TR/turtle/)RDF.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="0d9fe-106">Nella tabella seguente vengono illustrati gli equivalenti di [SKOS](https://www.w3.org/TR/skos-primer/) per il vocabolario della [Tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) .</span><span class="sxs-lookup"><span data-stu-id="0d9fe-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="0d9fe-107">SharePoint non supporta i valori di [SKOS](https://www.w3.org/TR/skos-primer/) che non dispongono di una tassonomia di SharePoint equivalente.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="0d9fe-108">Tassonomia di SharePoint</span><span class="sxs-lookup"><span data-stu-id="0d9fe-108">SharePoint taxonomy</span></span>|<span data-ttu-id="0d9fe-109">SKOS equivalente</span><span class="sxs-lookup"><span data-stu-id="0d9fe-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="0d9fe-110">SharePoint-tassonomia: termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="0d9fe-111">skos: Concept</span><span class="sxs-lookup"><span data-stu-id="0d9fe-111">skos:Concept</span></span>|
|<span data-ttu-id="0d9fe-112">SharePoint-tassonomia: termini</span><span class="sxs-lookup"><span data-stu-id="0d9fe-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="0d9fe-113">skos: ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="0d9fe-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="0d9fe-114">SharePoint-tassonomia: indicizzazione</span><span class="sxs-lookup"><span data-stu-id="0d9fe-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="0d9fe-115">skos: inscheme</span><span class="sxs-lookup"><span data-stu-id="0d9fe-115">skos:inScheme</span></span>|
|<span data-ttu-id="0d9fe-116">SharePoint-tassonomia: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="0d9fe-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="0d9fe-117">skos: hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="0d9fe-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="0d9fe-118">SharePoint-tassonomia: topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="0d9fe-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="0d9fe-119">skos: topConceptOf</span><span class="sxs-lookup"><span data-stu-id="0d9fe-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="0d9fe-120">SharePoint-tassonomia: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="0d9fe-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="0d9fe-121">skos: prefLabel</span><span class="sxs-lookup"><span data-stu-id="0d9fe-121">skos:prefLabel</span></span>|
|<span data-ttu-id="0d9fe-122">SharePoint-tassonomia: termSetName</span><span class="sxs-lookup"><span data-stu-id="0d9fe-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="0d9fe-123">skos: prefLabel</span><span class="sxs-lookup"><span data-stu-id="0d9fe-123">skos:prefLabel</span></span>|
|<span data-ttu-id="0d9fe-124">SharePoint-tassonomia: propertyName</span><span class="sxs-lookup"><span data-stu-id="0d9fe-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="0d9fe-125">skos: prefLabel</span><span class="sxs-lookup"><span data-stu-id="0d9fe-125">skos:prefLabel</span></span>|
|<span data-ttu-id="0d9fe-126">SharePoint-tassonomia: otherLabel</span><span class="sxs-lookup"><span data-stu-id="0d9fe-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="0d9fe-127">skos: altLabel</span><span class="sxs-lookup"><span data-stu-id="0d9fe-127">skos:altLabel</span></span>|
|<span data-ttu-id="0d9fe-128">SharePoint-tassonomia: Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d9fe-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="0d9fe-129">skos: definizione</span><span class="sxs-lookup"><span data-stu-id="0d9fe-129">skos:definition</span></span>|
|<span data-ttu-id="0d9fe-130">SharePoint-tassonomia: padre</span><span class="sxs-lookup"><span data-stu-id="0d9fe-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="0d9fe-131">skos: più ampio</span><span class="sxs-lookup"><span data-stu-id="0d9fe-131">skos:broader</span></span>|
|<span data-ttu-id="0d9fe-132">SharePoint-tassonomia: figlio</span><span class="sxs-lookup"><span data-stu-id="0d9fe-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="0d9fe-133">skos: più stretto</span><span class="sxs-lookup"><span data-stu-id="0d9fe-133">skos:narrower</span></span>|

<span data-ttu-id="0d9fe-134">Nella tabella seguente vengono mostrate le entità del vocabolario di tassonomia di SharePoint derivato da [Owl](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="0d9fe-135">Vocabolario della tassonomia di SharePoint</span><span class="sxs-lookup"><span data-stu-id="0d9fe-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="0d9fe-136">Derivato da OWL</span><span class="sxs-lookup"><span data-stu-id="0d9fe-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="0d9fe-137">SharePoint-tassonomia: isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="0d9fe-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="0d9fe-138">Gufo: datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="0d9fe-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="0d9fe-139">SharePoint-tassonomia: SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="0d9fe-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="0d9fe-140">Gufo: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="0d9fe-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="0d9fe-141">SharePoint-tassonomia: LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="0d9fe-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="0d9fe-142">Gufo: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="0d9fe-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="0d9fe-143">SharePoint-tassonomia: CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="0d9fe-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="0d9fe-144">Gufo: ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="0d9fe-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="0d9fe-145">Vocabolario della tassonomia di SharePoint</span><span class="sxs-lookup"><span data-stu-id="0d9fe-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="0d9fe-146">Una tassonomia è un sistema di classificazione formale.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="0d9fe-147">Una tassonomia raggruppa le parole, le etichette e i termini che descrivono qualcosa, quindi dispone i gruppi in una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="0d9fe-148">**SharePoint-tassonomia: termine**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="0d9fe-149">Rappresenta un termine o una parola chiave in una gerarchia di metadati gestiti.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="0d9fe-150">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è l'unità atomica di una [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="0d9fe-151">Ogni [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) appartiene a un [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) che appartiene a un [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="0d9fe-152">La sintassi per definire un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="0d9fe-153">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) obbligatoriamente esiste all'interno di un [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0d9fe-154">DefaultLabel è il nome del [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) così come viene visualizzato nella rappresentazione visiva.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="0d9fe-155">I campi obbligatori per la definizione di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) includono:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="0d9fe-156">SharePoint-tassonomia: defaultLabel</span><span class="sxs-lookup"><span data-stu-id="0d9fe-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="0d9fe-157">SharePoint-tassonomia: indicizzazione</span><span class="sxs-lookup"><span data-stu-id="0d9fe-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="0d9fe-158">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="0d9fe-159">Essere gerarchicamente correlato a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) che viene fornito entrambi i [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) appartengono allo stesso [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="0d9fe-160">Sono presenti più [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)figlio, ma solo un singolo [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)padre.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="0d9fe-161">Non è stato definito un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre, se si tratta [di un topLevelTermOf a.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)</span><span class="sxs-lookup"><span data-stu-id="0d9fe-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="0d9fe-162">Disporre di un defaultLabel, per lingua di lavoro [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="0d9fe-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="0d9fe-163">Non esiste se non contiene un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)padre, né il topLevelTermOf è un [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="0d9fe-164">Dispongono di un solo defaultLabel univoco nello stesso livello gerarchico.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="0d9fe-165">**SharePoint-tassonomia: termini**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="0d9fe-166">Rappresenta un insieme gerarchico o flat di oggetti term noti come "set di termini".</span><span class="sxs-lookup"><span data-stu-id="0d9fe-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="0d9fe-167">Come suggerisce il nome, il set di termini è un insieme di [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="0d9fe-168">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in un [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) deve appartenere a un [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0d9fe-169">Nessun [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può esistere in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="0d9fe-170">La sintassi per definire un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="0d9fe-171">Le [TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) sono raggruppate logicamente in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="0d9fe-172">Il campo obbligatorio per la definizione di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) è il seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="0d9fe-173">SharePoint-tassonomia: termSetName</span><span class="sxs-lookup"><span data-stu-id="0d9fe-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="0d9fe-174">Nel caso di termSetName specificato non è univoco all'interno di [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint aggiunge un numero alla fine del nome per mantenere l'univocità di termSetName.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharPoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="0d9fe-175">**SharePoint-tassonomia: hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="0d9fe-176">SharePoint utilizza questa proprietà per mappare la parte superiore del [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nel [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), che è il punto di ingresso alla gerarchia dei [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) [in un termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0d9fe-177">Si tratta di una relazione inversa con la tassonomia di SharePoint: topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="0d9fe-178">La sintassi da definire è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="0d9fe-179">Non è possibile definire il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) di primo livello di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)padre.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="0d9fe-180">**SharePoint-tassonomia: topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="0d9fe-181">SharePoint-tassonomia: topLevelTermOf è l'inverso di SharePoint-tassonomia: hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="0d9fe-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="0d9fe-182">La sintassi da definire è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="0d9fe-183">**SharePoint-tassonomia: indicizzazione**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="0d9fe-184">Utilizzare questa funzione per mappare un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a un [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0d9fe-185">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può esistere solo in un singolo [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0d9fe-186">SharePoint richiede questa proprietà quando si [definisce un termine](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="0d9fe-187">Etichette obbligatorie</span><span class="sxs-lookup"><span data-stu-id="0d9fe-187">Required labels</span></span>

<span data-ttu-id="0d9fe-188">L'organizzazione potrebbe voler fare un'attenta pianificazione prima di iniziare a utilizzare i metadati gestiti.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="0d9fe-189">La quantità di pianificazione che è necessario eseguire dipende dalla modalità formale di tassonomia.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="0d9fe-190">Dipende anche dalla quantità di controllo che si desidera imporre ai metadati.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="0d9fe-191">A ogni livello della gerarchia, è necessario configurare le etichette obbligatorie per un termine o un punto di riferimento.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-191">At each level of the hierarchy, you need to configure required lables for a Term or TermSet.</span></span>

<span data-ttu-id="0d9fe-192">Un termine può avere una o più etichette nella lingua predefinita e zero o più etichette nella lingua non predefinita.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="0d9fe-193">Se il termine contiene etichette in una lingua, è necessario che una delle etichette sia l'etichetta predefinita.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="0d9fe-194">**SharePoint-tassonomia: defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="0d9fe-195">Utilizzare questa etichetta lessicale predefinita per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) che è un parametro obbligatorio per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="0d9fe-196">Utilizzato per rappresentare visivamente il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="0d9fe-197">La sintassi per definire un defaultLabel è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="0d9fe-198">La defaultLabel contiene due parti: la stringa e il tag lingua.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="0d9fe-199">La lingua deve essere una delle lingue di lavoro di [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="0d9fe-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="0d9fe-200">DefaultLabel deve essere univoco per tutti i [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nello stesso [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), allo stesso livello gerarchico.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="0d9fe-201">**SharePoint-tassonomia: termSetName**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="0d9fe-202">Ottiene e imposta il nome per l'oggetto set di termini corrente.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="0d9fe-203">Questa è l'etichetta lessicale di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in una lingua di lavoro di [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="0d9fe-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="0d9fe-204">Questo è un parametro obbligatorio per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0d9fe-205">Consente di rappresentare visivamente un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="0d9fe-206">La sintassi per definire un termSetName è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="0d9fe-207">**SharePoint-tassonomia: propertyName**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="0d9fe-208">Ottiene e imposta il nome della proprietà per l'oggetto set di termini corrente.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="0d9fe-209">Questa è l'etichetta lessicale per una tassonomia di SharePoint: SharedCustomPropertyForTerm, SharePoint-tassonomia: LocalCustomPropertyForTerm e SharePoint-tassonomia: CustomPropertyForTermSet in una lingua di lavoro [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="0d9fe-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="0d9fe-210">La tassonomia di SharePoint: propertyName viene trattata come la chiave di CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="0d9fe-211">La sintassi per definire un propetyName è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="0d9fe-212">Etichette facoltative</span><span class="sxs-lookup"><span data-stu-id="0d9fe-212">Optional labels</span></span>

<span data-ttu-id="0d9fe-213">È inoltre possibile aggiungere etichette facoltative alla tassonomia.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="0d9fe-214">**SharePoint-tassonomia: otherLabel**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="0d9fe-215">Si tratta dell'etichetta lessicale alternativa per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="0d9fe-216">La sintassi per definire un otherLabel è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="0d9fe-217">Relazioni semantiche</span><span class="sxs-lookup"><span data-stu-id="0d9fe-217">Semantic relationships</span></span>

<span data-ttu-id="0d9fe-218">Le tassonomie hanno una relazione associativa gerarchica e talvolta semplice "correlata", ma alcune hanno "relazioni semantiche" o relazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="0d9fe-219">**SharePoint-tassonomia: padre**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="0d9fe-220">Questo collega gerarchicamente un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="0d9fe-221">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) potrebbe essere un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) di primo livello di un [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), ma in caso contrario deve avere un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)padre.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="0d9fe-222">La sintassi per la definizione di un elemento padre è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="0d9fe-223">Questo significa che TermA1 ha una parola padre.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-223">This means that TermA1 has parent TermA.</span></span> <span data-ttu-id="0d9fe-224">Inversamente, significa anche che TermA1 è il figlio di terma.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-224">Inversely it also means that TermA1 is the child of TermA.</span></span> <span data-ttu-id="0d9fe-225">La relazione padre-figlio è una relazione inversible.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-225">Parent-child relationship is an inversible relationship.</span></span>

<span data-ttu-id="0d9fe-226">**SharePoint-tassonomia: figlio**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-226">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="0d9fe-227">L'oggetto contiene una o più istanze di termini figlio, che possono essere accessibili tramite la proprietà TermSets.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-227">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="0d9fe-228">Questa classe fornisce anche metodi per la creazione di nuovi oggetti di termini figlio.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-228">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="0d9fe-229">Le autorizzazioni per la modifica delle istanze di termini e clausole figlio sono specificate nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-229">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="0d9fe-230">Questo collega gerarchicamente un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-230">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="0d9fe-231">La sintassi per la definizione di un elemento figlio è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-231">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="0d9fe-232">Questo significa che terma ha un figlio TermA1.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-232">This means that TermA has child TermA1.</span></span> <span data-ttu-id="0d9fe-233">Inversamente, significa anche che il termine è l'elemento padre della relazione padre-figlio di TermA1 è una relazione di inversible.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-233">Inversely it also means that TermA is the parent of TermA1 parent-child relationship is an inversible relationship.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="0d9fe-234">Note sulla documentazione</span><span class="sxs-lookup"><span data-stu-id="0d9fe-234">Documentation notes</span></span>

<span data-ttu-id="0d9fe-235">In questa sezione viene illustrata la tassonomia descritta nello spazio dei nomi Microsoft. SharePoint. tassonomia.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-235">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="0d9fe-236">**SharePoint-tassonomia: Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-236">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="0d9fe-237">Si tratta di una spiegazione dettagliata di qualsiasi entità del vocabolario della [Tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) .</span><span class="sxs-lookup"><span data-stu-id="0d9fe-237">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="0d9fe-238">La sintassi per aggiungere una descrizione è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-238">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="0d9fe-239">Proprietà personalizzate</span><span class="sxs-lookup"><span data-stu-id="0d9fe-239">Custom properties</span></span>

<span data-ttu-id="0d9fe-240">Ottiene l'insieme di oggetti Property personalizzati per l'oggetto term corrente dal dizionario di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-240">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="0d9fe-241">Le proprietà personalizzate sono coppie di valori chiave che è possibile definire per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [punto di vista](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), per ulteriori informazioni sulla descrizione del [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o su un punto di [riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="0d9fe-241">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="0d9fe-242">SharePoint specifica la chiave della proprietà personalizzata con l'ausilio di propertyName.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-242">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="0d9fe-243">**SharePoint-tassonomia: CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-243">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="0d9fe-244">La sintassi da definire è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-244">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="0d9fe-245">**SharePoint-tassonomia: SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-245">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="0d9fe-246">Se la proprietà personalizzata per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) deve essere eseguita insieme al [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando si riutilizza il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) da un'altra posizione, è necessario definirlo in SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="0d9fe-247">La sintassi da definire è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-247">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="0d9fe-248">**SharePoint-tassonomia: LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-248">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="0d9fe-249">Se non è necessario che la proprietà personalizzata per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) venga eseguita insieme al [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando si riutilizza il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in un'altra posizione, è necessario definirlo in LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-249">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="0d9fe-250">La sintassi da definire è la seguente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-250">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="0d9fe-251">Proprietà dei dati</span><span class="sxs-lookup"><span data-stu-id="0d9fe-251">Data properties</span></span>

<span data-ttu-id="0d9fe-252">A ogni livello della gerarchia è possibile configurare specifiche proprietà dei dati per un termine o un punto di riferimento.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-252">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="0d9fe-253">**SharePoint-tassonomia: isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="0d9fe-253">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="0d9fe-254">Utilizzare questa impostazione per specificare se un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) sono disponibili negli elenchi e nelle raccolte di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-254">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="0d9fe-255">La sintassi di questo è:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-255">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="0d9fe-256">Dominio e intervallo</span><span class="sxs-lookup"><span data-stu-id="0d9fe-256">Domain and range</span></span>

<span data-ttu-id="0d9fe-257">Nella tabella seguente vengono descritti il dominio e l'intervallo di terminologia della tassonomia di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-257">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="0d9fe-258">Predicati/verbo</span><span class="sxs-lookup"><span data-stu-id="0d9fe-258">Predicates/verb</span></span>|<span data-ttu-id="0d9fe-259">Significato</span><span class="sxs-lookup"><span data-stu-id="0d9fe-259">Meaning</span></span>|<span data-ttu-id="0d9fe-260">Dominio</span><span class="sxs-lookup"><span data-stu-id="0d9fe-260">Domain</span></span>|<span data-ttu-id="0d9fe-261">Range</span><span class="sxs-lookup"><span data-stu-id="0d9fe-261">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="0d9fe-262">intermini</span><span class="sxs-lookup"><span data-stu-id="0d9fe-262">inTermSet</span></span>|<span data-ttu-id="0d9fe-263">Set di termini</span><span class="sxs-lookup"><span data-stu-id="0d9fe-263">In term set</span></span>|<span data-ttu-id="0d9fe-264">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-264">Term</span></span>|<span data-ttu-id="0d9fe-265">Set di termini</span><span class="sxs-lookup"><span data-stu-id="0d9fe-265">Term Set</span></span>|
<span data-ttu-id="0d9fe-266">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="0d9fe-266">inTermGroup</span></span>|<span data-ttu-id="0d9fe-267">In gruppo di termini</span><span class="sxs-lookup"><span data-stu-id="0d9fe-267">In term group</span></span>|<span data-ttu-id="0d9fe-268">Termini</span><span class="sxs-lookup"><span data-stu-id="0d9fe-268">TermSet</span></span>|<span data-ttu-id="0d9fe-269">TermGroup</span><span class="sxs-lookup"><span data-stu-id="0d9fe-269">TermGroup</span></span>|
<span data-ttu-id="0d9fe-270">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="0d9fe-270">topLevelTermOf</span></span>|<span data-ttu-id="0d9fe-271">È il termine di primo livello di</span><span class="sxs-lookup"><span data-stu-id="0d9fe-271">Is Top Level Term Of</span></span>|<span data-ttu-id="0d9fe-272">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-272">Term</span></span>|<span data-ttu-id="0d9fe-273">Termini</span><span class="sxs-lookup"><span data-stu-id="0d9fe-273">TermSet</span></span>|
<span data-ttu-id="0d9fe-274">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="0d9fe-274">hasTopLevelTerm</span></span>|<span data-ttu-id="0d9fe-275">Ha un termine di primo livello</span><span class="sxs-lookup"><span data-stu-id="0d9fe-275">Has top level term</span></span>|<span data-ttu-id="0d9fe-276">Set di termini</span><span class="sxs-lookup"><span data-stu-id="0d9fe-276">Term Set</span></span>|<span data-ttu-id="0d9fe-277">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-277">Term</span></span>|
<span data-ttu-id="0d9fe-278">termSetName</span><span class="sxs-lookup"><span data-stu-id="0d9fe-278">termSetName</span></span>|<span data-ttu-id="0d9fe-279">Il set di termini ha il nome</span><span class="sxs-lookup"><span data-stu-id="0d9fe-279">Term set has Name</span></span>|<span data-ttu-id="0d9fe-280">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-280">Term</span></span>|<span data-ttu-id="0d9fe-281">Valore letterale normale</span><span class="sxs-lookup"><span data-stu-id="0d9fe-281">Plain literal</span></span>|
<span data-ttu-id="0d9fe-282">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="0d9fe-282">defaultLabel</span></span>|<span data-ttu-id="0d9fe-283">Il termine è etichetta predefinita</span><span class="sxs-lookup"><span data-stu-id="0d9fe-283">Term has default label</span></span>|<span data-ttu-id="0d9fe-284">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-284">Term</span></span>|<span data-ttu-id="0d9fe-285">Valore letterale normale</span><span class="sxs-lookup"><span data-stu-id="0d9fe-285">Plain literal</span></span>|
<span data-ttu-id="0d9fe-286">otherLabel</span><span class="sxs-lookup"><span data-stu-id="0d9fe-286">otherLabel</span></span>|<span data-ttu-id="0d9fe-287">Il termine ha un'altra etichetta</span><span class="sxs-lookup"><span data-stu-id="0d9fe-287">Term has other label</span></span>|<span data-ttu-id="0d9fe-288">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-288">Term</span></span>|<span data-ttu-id="0d9fe-289">Valore letterale normale</span><span class="sxs-lookup"><span data-stu-id="0d9fe-289">Plain literal</span></span>|
<span data-ttu-id="0d9fe-290">propertyName</span><span class="sxs-lookup"><span data-stu-id="0d9fe-290">propertyName</span></span>|<span data-ttu-id="0d9fe-291">Etichetta di proprietà</span><span class="sxs-lookup"><span data-stu-id="0d9fe-291">Has Property Label</span></span>|<span data-ttu-id="0d9fe-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="0d9fe-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="0d9fe-293">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="0d9fe-293">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="0d9fe-294">descrizione</span><span class="sxs-lookup"><span data-stu-id="0d9fe-294">description</span></span>|<span data-ttu-id="0d9fe-295">Contiene una descrizione</span><span class="sxs-lookup"><span data-stu-id="0d9fe-295">Has Description</span></span>|<span data-ttu-id="0d9fe-296">Tutti</span><span class="sxs-lookup"><span data-stu-id="0d9fe-296">All</span></span>|<span data-ttu-id="0d9fe-297">Valore letterale normale</span><span class="sxs-lookup"><span data-stu-id="0d9fe-297">Plain literal</span></span>|
|<span data-ttu-id="0d9fe-298">padre</span><span class="sxs-lookup"><span data-stu-id="0d9fe-298">parent</span></span>|<span data-ttu-id="0d9fe-299">Ha padre</span><span class="sxs-lookup"><span data-stu-id="0d9fe-299">Has parent</span></span>|<span data-ttu-id="0d9fe-300">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-300">Term</span></span>|<span data-ttu-id="0d9fe-301">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-301">Term</span></span>|
|<span data-ttu-id="0d9fe-302">bambino</span><span class="sxs-lookup"><span data-stu-id="0d9fe-302">child</span></span>|<span data-ttu-id="0d9fe-303">Ha un figlio</span><span class="sxs-lookup"><span data-stu-id="0d9fe-303">Has Child</span></span>|<span data-ttu-id="0d9fe-304">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-304">Term</span></span>|<span data-ttu-id="0d9fe-305">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-305">Term</span></span>|
|<span data-ttu-id="0d9fe-306">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="0d9fe-306">isAvailableForTagging</span></span>|<span data-ttu-id="0d9fe-307">È disponibile per il tagging</span><span class="sxs-lookup"><span data-stu-id="0d9fe-307">Is available for tagging</span></span>|<span data-ttu-id="0d9fe-308">Termini, set di termini</span><span class="sxs-lookup"><span data-stu-id="0d9fe-308">Term, Term Set</span></span>|<span data-ttu-id="0d9fe-309">Booleano</span><span class="sxs-lookup"><span data-stu-id="0d9fe-309">Boolean</span></span>|
|<span data-ttu-id="0d9fe-310">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="0d9fe-310">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="0d9fe-311">Ha una proprietà personalizzata condivisa</span><span class="sxs-lookup"><span data-stu-id="0d9fe-311">Has shared custom property</span></span>|<span data-ttu-id="0d9fe-312">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-312">Term</span></span>|<span data-ttu-id="0d9fe-313">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="0d9fe-313">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="0d9fe-314">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="0d9fe-314">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="0d9fe-315">Dispone di una proprietà personalizzata locale</span><span class="sxs-lookup"><span data-stu-id="0d9fe-315">Has local custom property</span></span>|<span data-ttu-id="0d9fe-316">Termine</span><span class="sxs-lookup"><span data-stu-id="0d9fe-316">Term</span></span>|<span data-ttu-id="0d9fe-317">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="0d9fe-317">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="0d9fe-318">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="0d9fe-318">CustomPropertyForTermSet</span></span>|<span data-ttu-id="0d9fe-319">Ha una proprietà personalizzata</span><span class="sxs-lookup"><span data-stu-id="0d9fe-319">Has Custom Property</span></span>|<span data-ttu-id="0d9fe-320">Termini</span><span class="sxs-lookup"><span data-stu-id="0d9fe-320">TermSet</span></span>|<span data-ttu-id="0d9fe-321">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="0d9fe-321">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="0d9fe-322">[SKOS](https://www.w3.org/TR/skos-primer/) scenari validi che la [Tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) non consente:</span><span class="sxs-lookup"><span data-stu-id="0d9fe-322">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="0d9fe-323">Ridondanza gerarchica-un concetto di [SKOS](https://www.w3.org/TR/skos-primer/) può essere associato a più concetti più ampi contemporaneamente, ma un termine per la tassonomia di SharePoint può avere una sola tassonomia di SharePoint: non è consentita anche la dipendenza a livello di padre e quindi ciclica.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-323">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="0d9fe-324">I termini orfani non sono consentiti nella tassonomia di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-324">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="0d9fe-325">Ogni tipo di tassonomia di SharePoint: il termine deve disporre di una tassonomia di SharePoint: padre o deve essere la tassonomia di SharePoint: topLevelTermOf un punto di riferimento.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-325">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="0d9fe-326">La tassonomia di SharePoint non supporta le relazioni associative.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-326">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="0d9fe-327">La tassonomia di SharePoint consente solo 2 tipi di relazioni gerarchiche – la tassonomia di SharePoint: padre e SharePoint-tassonomia: figlio.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-327">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="0d9fe-328">A differenza di [SKOS](https://www.w3.org/TR/skos-primer/) la relazione gerarchica nel vocabolario della tassonomia di SharePoint, può essere stabilita solo con termini all'interno dello stesso termini.</span><span class="sxs-lookup"><span data-stu-id="0d9fe-328">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d9fe-329">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d9fe-329">See also</span></span>

[<span data-ttu-id="0d9fe-330">Importare un set di termini utilizzando un formato basato su SKOS</span><span class="sxs-lookup"><span data-stu-id="0d9fe-330">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

