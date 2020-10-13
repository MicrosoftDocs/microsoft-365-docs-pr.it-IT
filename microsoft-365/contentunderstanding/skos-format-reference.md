---
title: Riferimento al formato SKOS per la tassonomia di SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Riferimento al formato SKOS per la tassonomia di SharePoint
ms.openlocfilehash: f81b618a7c302ce033c4e8ce2f7400e9616f2de0
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321326"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="481de-103">Riferimento al formato SKOS per la tassonomia di SharePoint</span><span class="sxs-lookup"><span data-stu-id="481de-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="481de-104">Questo articolo contiene il vocabolario RDF usato per rappresentare la [tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) e si basa su [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="481de-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="481de-105">Per la serializzazione della sintassi RDF, usare RDF [TURTLE](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="481de-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="481de-106">Nella tabella seguente sono illustrati gli equivalenti [SKOS](https://www.w3.org/TR/skos-primer/) per il vocabolario della [tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="481de-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="481de-107">SharePoint non supporta i valori [SKOS](https://www.w3.org/TR/skos-primer/) che non hanno alcun equivalente per la tassonomia di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="481de-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="481de-108">Tassonomia di SharePoint</span><span class="sxs-lookup"><span data-stu-id="481de-108">SharePoint taxonomy</span></span>|<span data-ttu-id="481de-109">Equivalente SKOS</span><span class="sxs-lookup"><span data-stu-id="481de-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="481de-110">sharepoint-taxonomy:Term</span><span class="sxs-lookup"><span data-stu-id="481de-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="481de-111">skos:Concept</span><span class="sxs-lookup"><span data-stu-id="481de-111">skos:Concept</span></span>|
|<span data-ttu-id="481de-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="481de-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="481de-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="481de-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="481de-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="481de-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="481de-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="481de-115">skos:inScheme</span></span>|
|<span data-ttu-id="481de-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="481de-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="481de-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="481de-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="481de-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="481de-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="481de-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="481de-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="481de-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="481de-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="481de-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="481de-121">skos:prefLabel</span></span>|
|<span data-ttu-id="481de-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="481de-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="481de-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="481de-123">skos:prefLabel</span></span>|
|<span data-ttu-id="481de-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="481de-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="481de-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="481de-125">skos:prefLabel</span></span>|
|<span data-ttu-id="481de-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="481de-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="481de-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="481de-127">skos:altLabel</span></span>|
|<span data-ttu-id="481de-128">sharepoint-taxonomy:description</span><span class="sxs-lookup"><span data-stu-id="481de-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="481de-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="481de-129">skos:definition</span></span>|
|<span data-ttu-id="481de-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="481de-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="481de-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="481de-131">skos:broader</span></span>|
|<span data-ttu-id="481de-132">sharepoint-taxonomy:child</span><span class="sxs-lookup"><span data-stu-id="481de-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="481de-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="481de-133">skos:narrower</span></span>|

<span data-ttu-id="481de-134">La tabella seguente mostra gli elementi del vocabolario per la tassonomia di SharePoint derivati da [OWL](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="481de-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="481de-135">Vocabolario per la tassonomia di SharePoint</span><span class="sxs-lookup"><span data-stu-id="481de-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="481de-136">Derivato da OWL</span><span class="sxs-lookup"><span data-stu-id="481de-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="481de-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="481de-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="481de-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="481de-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="481de-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="481de-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="481de-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="481de-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="481de-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="481de-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="481de-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="481de-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="481de-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="481de-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="481de-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="481de-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="481de-145">Vocabolario per la tassonomia di SharePoint</span><span class="sxs-lookup"><span data-stu-id="481de-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="481de-146">Una tassonomia è un sistema di classificazione formale.</span><span class="sxs-lookup"><span data-stu-id="481de-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="481de-147">Una tassonomia raggruppa parole, etichette e termini che descrivono qualcosa e quindi li organizza in gruppi all’interno di una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="481de-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="481de-148">**sharepoint-taxonomy:Term**</span><span class="sxs-lookup"><span data-stu-id="481de-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="481de-149">Rappresenta un termine o una parola chiave in una gerarchia di metadati gestiti.</span><span class="sxs-lookup"><span data-stu-id="481de-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="481de-150">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è l'unità atomica di un [archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="481de-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="481de-151">Ogni [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) appartiene a un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) che a sua volta appartiene a un [gruppo di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="481de-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="481de-152">La sintassi per definire un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è la seguente:</span><span class="sxs-lookup"><span data-stu-id="481de-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="481de-153">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) esiste tassativamente all'interno di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="481de-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="481de-154">Etichetta predefinita è il nome del [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) così come appare nella rappresentazione visiva.</span><span class="sxs-lookup"><span data-stu-id="481de-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="481de-155">I campi obbligatori per la definizione di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) includono:</span><span class="sxs-lookup"><span data-stu-id="481de-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="481de-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="481de-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="481de-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="481de-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="481de-158">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può:</span><span class="sxs-lookup"><span data-stu-id="481de-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="481de-159">Essere gerarchicamente correlato a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), entrambi i [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) devono appartenere allo stesso [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="481de-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="481de-160">Avere più [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) figlio, ma un singolo [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre.</span><span class="sxs-lookup"><span data-stu-id="481de-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="481de-161">Non avere un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre definito, se si tratta di un termine di primo livello di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="481de-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="481de-162">Avere un’etichetta predefinita, per ogni lingua di lavoro dell’[archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="481de-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="481de-163">Essere non esistente, se non contiene un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre e non è un termine di primo livello di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="481de-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="481de-164">Avere un’unica etichetta predefinita nello stesso livello gerarchico.</span><span class="sxs-lookup"><span data-stu-id="481de-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="481de-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="481de-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="481de-166">Rappresenta un set gerarchico o semplice di termini noto come "set di termini".</span><span class="sxs-lookup"><span data-stu-id="481de-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="481de-167">Come suggerisce il nome, il set di termini è un set di [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="481de-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="481de-168">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in un [archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) deve appartenere a un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="481de-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="481de-169">Nessun [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può essere esistere in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="481de-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="481de-170">La sintassi per definire un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) è la seguente:</span><span class="sxs-lookup"><span data-stu-id="481de-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="481de-171">I [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) sono raggruppati logicamente in [gruppi di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="481de-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="481de-172">Il campo obbligatorio per la definizione di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) è:</span><span class="sxs-lookup"><span data-stu-id="481de-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="481de-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="481de-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="481de-174">Nel caso il cui il nome del set di termini fornito non sia univoco all'interno del [gruppo di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint aggiunge un numero alla fine del nome per mantenere l'univocità del nome del set di termini.</span><span class="sxs-lookup"><span data-stu-id="481de-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="481de-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="481de-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="481de-176">SharePoint usa questa proprietà per mappare il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) di primo livello nel [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), ossia il punto di ingresso della gerarchia di [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="481de-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="481de-177">Si tratta di una relazione inversa rispetto a sharepoint-taxonomy:topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="481de-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="481de-178">La sintassi per definire questa relazione è:</span><span class="sxs-lookup"><span data-stu-id="481de-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="481de-179">Non è possibile definire il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) di primo livello di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre.</span><span class="sxs-lookup"><span data-stu-id="481de-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="481de-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="481de-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="481de-181">Sharepoint-taxonomy:topLevelTermOf è la relazione inversa rispetto a sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="481de-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="481de-182">La sintassi per definire questa relazione è:</span><span class="sxs-lookup"><span data-stu-id="481de-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="481de-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="481de-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="481de-184">Usare questa opzione per mappare un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="481de-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="481de-185">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può esistere soltanto in un singolo [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="481de-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="481de-186">SharePoint richiede questa proprietà per la [definizione di un termine](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="481de-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="481de-187">Etichette obbligatorie</span><span class="sxs-lookup"><span data-stu-id="481de-187">Required labels</span></span>

<span data-ttu-id="481de-188">È possibile che l'organizzazione intenda eseguire un'attenta pianificazione prima che sia possibile iniziare a usare i metadati gestiti.</span><span class="sxs-lookup"><span data-stu-id="481de-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="481de-189">La quantità di pianificazione da eseguire dipende da quanto è formale la tassonomia.</span><span class="sxs-lookup"><span data-stu-id="481de-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="481de-190">Dipende anche dalla quantità di controllo che si vuole stabilire sui metadati.</span><span class="sxs-lookup"><span data-stu-id="481de-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="481de-191">A ogni livello della gerarchia, è necessario configurare le etichette obbligatorie per un termine o un set di termini.</span><span class="sxs-lookup"><span data-stu-id="481de-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="481de-192">Un termine può avere una o più etichette nella lingua predefinita e zero o più etichette nella lingua non predefinita.</span><span class="sxs-lookup"><span data-stu-id="481de-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="481de-193">Se il termine dispone di etichette in una lingua, una delle etichette deve essere l'etichetta predefinita.</span><span class="sxs-lookup"><span data-stu-id="481de-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="481de-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="481de-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="481de-195">Usare questa etichetta lessicale predefinita per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), si tratta di un parametro obbligatorio per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="481de-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="481de-196">Da usare per rappresentare visivamente il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="481de-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="481de-197">La sintassi per definire un’etichetta predefinita è:</span><span class="sxs-lookup"><span data-stu-id="481de-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="481de-198">L’etichetta predefinita contiene due parti: la stringa e il tag lingua.</span><span class="sxs-lookup"><span data-stu-id="481de-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="481de-199">La lingua deve essere una delle lingue di lavoro dell’[archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="481de-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="481de-200">L’etichetta predefinita deve essere univoca per tutti i [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nello stesso [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), allo stesso livello gerarchico.</span><span class="sxs-lookup"><span data-stu-id="481de-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="481de-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="481de-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="481de-202">Ottiene e imposta il nome per il set di termini corrente.</span><span class="sxs-lookup"><span data-stu-id="481de-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="481de-203">Si tratta dell’etichetta lessicale per un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in una lingua di lavoro dell’[archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="481de-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="481de-204">Si tratta di un parametro obbligatorio per un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="481de-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="481de-205">Da usare per rappresentare visivamente un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="481de-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="481de-206">La sintassi per definire un nome del set di termini è:</span><span class="sxs-lookup"><span data-stu-id="481de-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="481de-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="481de-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="481de-208">Ottiene e imposta il nome proprietà per il set di termini corrente.</span><span class="sxs-lookup"><span data-stu-id="481de-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="481de-209">Si tratta dell'etichetta lessicale per sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in una lingua di lavoro dell’[archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="481de-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="481de-210">Il sharepoint-taxonomy:propertyName viene considerato come chiave della proprietà personalizzata.</span><span class="sxs-lookup"><span data-stu-id="481de-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="481de-211">La sintassi per definire un nome proprietà è:</span><span class="sxs-lookup"><span data-stu-id="481de-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="481de-212">Etichette facoltative</span><span class="sxs-lookup"><span data-stu-id="481de-212">Optional labels</span></span>

<span data-ttu-id="481de-213">È possibile aggiungere anche etichette facoltative alla tassonomia.</span><span class="sxs-lookup"><span data-stu-id="481de-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="481de-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="481de-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="481de-215">Si tratta dell'etichetta lessicale alternativa per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="481de-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="481de-216">La sintassi per definire un’etichetta alternativa è:</span><span class="sxs-lookup"><span data-stu-id="481de-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="481de-217">Relazioni semantiche</span><span class="sxs-lookup"><span data-stu-id="481de-217">Semantic relationships</span></span>

<span data-ttu-id="481de-218">Le tassonomie hanno relazioni gerarchiche e in alcuni casi relazioni associative semplici di "termini correlati", ma alcune hanno "relazioni semantiche" o relazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="481de-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="481de-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="481de-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="481de-220">In questo modo, un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è correlato gerarchicamente a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="481de-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="481de-221">Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può essere un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) di primo livello di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), ma in caso contrario deve avere un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre.</span><span class="sxs-lookup"><span data-stu-id="481de-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="481de-222">La sintassi per definire un termine padre è:</span><span class="sxs-lookup"><span data-stu-id="481de-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="481de-223">Ciò significa che termineA è il padre e  termineA è il figlio.</span><span class="sxs-lookup"><span data-stu-id="481de-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="481de-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="481de-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="481de-225">L'oggetto contiene uno o più elementi figlio di un set di termini, che è possibile utilizzare tramite la proprietà set di termini.</span><span class="sxs-lookup"><span data-stu-id="481de-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="481de-226">Questa classe fornisce anche metodi per la creazione di nuovi oggetti figlio di un set di termini.</span><span class="sxs-lookup"><span data-stu-id="481de-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="481de-227">Nel gruppo sono specificate le autorizzazioni per modificare il termine figlio e gli elementi di un set di termini.</span><span class="sxs-lookup"><span data-stu-id="481de-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="481de-228">In questo modo, un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è correlato gerarchicamente a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="481de-228">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="481de-229">La sintassi per definire un termine figlio è:</span><span class="sxs-lookup"><span data-stu-id="481de-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="481de-230">Ciò significa che termineA è il padre e  termineA è il figlio.</span><span class="sxs-lookup"><span data-stu-id="481de-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="481de-231">Note sulla documentazione</span><span class="sxs-lookup"><span data-stu-id="481de-231">Documentation notes</span></span>

<span data-ttu-id="481de-232">Questa sezione riguarda la tassonomia dettagliata in Microsoft.SharePoint.Taxonomy Namespace.</span><span class="sxs-lookup"><span data-stu-id="481de-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="481de-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="481de-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="481de-234">Si tratta di una spiegazione dettagliata di tutti gli elementi del vocabolario per la [tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="481de-234">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="481de-235">La sintassi per aggiungere una descrizione è:</span><span class="sxs-lookup"><span data-stu-id="481de-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="481de-236">Proprietà personalizzate</span><span class="sxs-lookup"><span data-stu-id="481de-236">Custom properties</span></span>

<span data-ttu-id="481de-237">Ottiene la raccolta delle proprietà personalizzate per il termine corrente dal dizionario di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="481de-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="481de-238">Le proprietà personalizzate sono coppie di chiave-valori che possono essere definite per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), per agevolare la descrizione del [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="481de-238">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="481de-239">SharePoint specifica la chiave della proprietà personalizzata con l'aiuto di propertyName.</span><span class="sxs-lookup"><span data-stu-id="481de-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="481de-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="481de-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="481de-241">La sintassi per definire questa relazione è:</span><span class="sxs-lookup"><span data-stu-id="481de-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="481de-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="481de-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="481de-243">Se la proprietà personalizzata per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) deve essere trasmessa con il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) quando il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) viene riutilizzato altrove, è necessario definirla in SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="481de-243">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="481de-244">La sintassi per definire questa relazione è:</span><span class="sxs-lookup"><span data-stu-id="481de-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="481de-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="481de-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="481de-246">Se la proprietà personalizzata per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) non deve essere trasmessa con il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) quando il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) viene riutilizzato altrove, è necessario definirla in LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="481de-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="481de-247">La sintassi per definire questa relazione è:</span><span class="sxs-lookup"><span data-stu-id="481de-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="481de-248">Proprietà dei dati</span><span class="sxs-lookup"><span data-stu-id="481de-248">Data properties</span></span>

<span data-ttu-id="481de-249">A ogni livello della gerarchia, è necessario configurare le specifiche proprietà dei dati per un termine o un set di termini.</span><span class="sxs-lookup"><span data-stu-id="481de-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="481de-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="481de-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="481de-251">Usare questa opzione per specificare se un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) è disponibile negli elenchi e nelle raccolte di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="481de-251">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="481de-252">La sintassi per questa operazione è:</span><span class="sxs-lookup"><span data-stu-id="481de-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="481de-253">Dominio e intervallo</span><span class="sxs-lookup"><span data-stu-id="481de-253">Domain and range</span></span>

<span data-ttu-id="481de-254">La tabella seguente descrive il dominio e l'intervallo del vocabolario per la tassonomia di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="481de-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="481de-255">Predicati/verbi</span><span class="sxs-lookup"><span data-stu-id="481de-255">Predicates/verb</span></span>|<span data-ttu-id="481de-256">Significato</span><span class="sxs-lookup"><span data-stu-id="481de-256">Meaning</span></span>|<span data-ttu-id="481de-257">Dominio</span><span class="sxs-lookup"><span data-stu-id="481de-257">Domain</span></span>|<span data-ttu-id="481de-258">Intervallo</span><span class="sxs-lookup"><span data-stu-id="481de-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="481de-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="481de-259">inTermSet</span></span>|<span data-ttu-id="481de-260">Nel set di termini</span><span class="sxs-lookup"><span data-stu-id="481de-260">In term set</span></span>|<span data-ttu-id="481de-261">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-261">Term</span></span>|<span data-ttu-id="481de-262">Set di termini</span><span class="sxs-lookup"><span data-stu-id="481de-262">Term Set</span></span>|
<span data-ttu-id="481de-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="481de-263">inTermGroup</span></span>|<span data-ttu-id="481de-264">In un gruppo di termini</span><span class="sxs-lookup"><span data-stu-id="481de-264">In term group</span></span>|<span data-ttu-id="481de-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="481de-265">TermSet</span></span>|<span data-ttu-id="481de-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="481de-266">TermGroup</span></span>|
<span data-ttu-id="481de-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="481de-267">topLevelTermOf</span></span>|<span data-ttu-id="481de-268">È un termine di primo livello di</span><span class="sxs-lookup"><span data-stu-id="481de-268">Is Top Level Term Of</span></span>|<span data-ttu-id="481de-269">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-269">Term</span></span>|<span data-ttu-id="481de-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="481de-270">TermSet</span></span>|
<span data-ttu-id="481de-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="481de-271">hasTopLevelTerm</span></span>|<span data-ttu-id="481de-272">Ha un termine di primo livello</span><span class="sxs-lookup"><span data-stu-id="481de-272">Has top level term</span></span>|<span data-ttu-id="481de-273">Set di termini</span><span class="sxs-lookup"><span data-stu-id="481de-273">Term Set</span></span>|<span data-ttu-id="481de-274">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-274">Term</span></span>|
<span data-ttu-id="481de-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="481de-275">termSetName</span></span>|<span data-ttu-id="481de-276">Nome del set di termini</span><span class="sxs-lookup"><span data-stu-id="481de-276">Term set has Name</span></span>|<span data-ttu-id="481de-277">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-277">Term</span></span>|<span data-ttu-id="481de-278">Letterale</span><span class="sxs-lookup"><span data-stu-id="481de-278">Plain literal</span></span>|
<span data-ttu-id="481de-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="481de-279">defaultLabel</span></span>|<span data-ttu-id="481de-280">Il termine ha un’etichetta predefinita</span><span class="sxs-lookup"><span data-stu-id="481de-280">Term has default label</span></span>|<span data-ttu-id="481de-281">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-281">Term</span></span>|<span data-ttu-id="481de-282">Letterale</span><span class="sxs-lookup"><span data-stu-id="481de-282">Plain literal</span></span>|
<span data-ttu-id="481de-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="481de-283">otherLabel</span></span>|<span data-ttu-id="481de-284">Il termine ha un'etichetta alternativa</span><span class="sxs-lookup"><span data-stu-id="481de-284">Term has other label</span></span>|<span data-ttu-id="481de-285">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-285">Term</span></span>|<span data-ttu-id="481de-286">Letterale</span><span class="sxs-lookup"><span data-stu-id="481de-286">Plain literal</span></span>|
<span data-ttu-id="481de-287">propertyName</span><span class="sxs-lookup"><span data-stu-id="481de-287">propertyName</span></span>|<span data-ttu-id="481de-288">Ha un’etichetta proprietà</span><span class="sxs-lookup"><span data-stu-id="481de-288">Has Property Label</span></span>|<span data-ttu-id="481de-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="481de-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="481de-290">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="481de-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="481de-291">descrizione</span><span class="sxs-lookup"><span data-stu-id="481de-291">description</span></span>|<span data-ttu-id="481de-292">Ha una descrizione</span><span class="sxs-lookup"><span data-stu-id="481de-292">Has Description</span></span>|<span data-ttu-id="481de-293">Tutto</span><span class="sxs-lookup"><span data-stu-id="481de-293">All</span></span>|<span data-ttu-id="481de-294">Letterale</span><span class="sxs-lookup"><span data-stu-id="481de-294">Plain literal</span></span>|
|<span data-ttu-id="481de-295">padre</span><span class="sxs-lookup"><span data-stu-id="481de-295">parent</span></span>|<span data-ttu-id="481de-296">Ha un padre</span><span class="sxs-lookup"><span data-stu-id="481de-296">Has parent</span></span>|<span data-ttu-id="481de-297">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-297">Term</span></span>|<span data-ttu-id="481de-298">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-298">Term</span></span>|
|<span data-ttu-id="481de-299">figlio</span><span class="sxs-lookup"><span data-stu-id="481de-299">child</span></span>|<span data-ttu-id="481de-300">Ha un figlio</span><span class="sxs-lookup"><span data-stu-id="481de-300">Has Child</span></span>|<span data-ttu-id="481de-301">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-301">Term</span></span>|<span data-ttu-id="481de-302">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-302">Term</span></span>|
|<span data-ttu-id="481de-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="481de-303">isAvailableForTagging</span></span>|<span data-ttu-id="481de-304">È disponibile per il tagging</span><span class="sxs-lookup"><span data-stu-id="481de-304">Is available for tagging</span></span>|<span data-ttu-id="481de-305">Termine, Set di termini</span><span class="sxs-lookup"><span data-stu-id="481de-305">Term, Term Set</span></span>|<span data-ttu-id="481de-306">Booleano</span><span class="sxs-lookup"><span data-stu-id="481de-306">Boolean</span></span>|
|<span data-ttu-id="481de-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="481de-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="481de-308">Ha una proprietà personalizzata condivisa</span><span class="sxs-lookup"><span data-stu-id="481de-308">Has shared custom property</span></span>|<span data-ttu-id="481de-309">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-309">Term</span></span>|<span data-ttu-id="481de-310">Boolean, string, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="481de-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="481de-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="481de-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="481de-312">Ha una proprietà personalizzata locale</span><span class="sxs-lookup"><span data-stu-id="481de-312">Has local custom property</span></span>|<span data-ttu-id="481de-313">Termine</span><span class="sxs-lookup"><span data-stu-id="481de-313">Term</span></span>|<span data-ttu-id="481de-314">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="481de-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="481de-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="481de-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="481de-316">Ha una proprietà personalizzata</span><span class="sxs-lookup"><span data-stu-id="481de-316">Has Custom Property</span></span>|<span data-ttu-id="481de-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="481de-317">TermSet</span></span>|<span data-ttu-id="481de-318">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="481de-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="481de-319">Scenari validi [SKOS](https://www.w3.org/TR/skos-primer/) che la [tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) non consente:</span><span class="sxs-lookup"><span data-stu-id="481de-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="481de-320">Ridondanza gerarchica: un concetto [SKOS](https://www.w3.org/TR/skos-primer/) può essere associato a diversi concetti più ampi contemporaneamente, ma un sharepoint-taxonomy:Term può avere un solo sharepoint-taxonomy:parent, perciò la dipendenza ciclica dei termini non è consentita.</span><span class="sxs-lookup"><span data-stu-id="481de-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="481de-321">I termini orfani non sono consentiti nella tassonomia di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="481de-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="481de-322">Ogni sharepoint-taxonomy:Term deve avere un sharepoint-taxonomy:parent o deve essere il sharepoint-taxonomy:topLevelTermOf un set di termini.</span><span class="sxs-lookup"><span data-stu-id="481de-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="481de-323">La tassonomia di SharePoint non supporta le relazioni associative.</span><span class="sxs-lookup"><span data-stu-id="481de-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="481de-324">La tassonomia di SharePoint consente solo due tipi di relazioni gerarchiche, ossia sharepoint-taxonomy:parent e sharepoint-Taxonomy:child.</span><span class="sxs-lookup"><span data-stu-id="481de-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="481de-325">Diversamente da [SKOS](https://www.w3.org/TR/skos-primer/), la relazione gerarchica nel vocabolario per la tassonomia di SharePoint può essere stabilita solo con termini che sono all'interno dello stesso set di termini.</span><span class="sxs-lookup"><span data-stu-id="481de-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="481de-326">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="481de-326">See also</span></span>

[<span data-ttu-id="481de-327">Importare un set di termini con un formato basato su SKOS</span><span class="sxs-lookup"><span data-stu-id="481de-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)
