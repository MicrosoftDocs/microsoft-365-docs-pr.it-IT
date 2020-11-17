---
title: Riferimento al formato SKOS per la tassonomia di SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Riferimento al formato SKOS per la tassonomia di SharePoint
ms.openlocfilehash: 90c20ddb440e216941a5ea06f1aa815cb80102a9
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087281"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>Riferimento al formato SKOS per la tassonomia di SharePoint

Questo articolo contiene il vocabolario RDF usato per rappresentare la [tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) e si basa su [SKOS](https://www.w3.org/TR/skos-primer/). Per la serializzazione della sintassi RDF, usare RDF [TURTLE](https://www.w3.org/TR/turtle/).

Nella tabella seguente sono illustrati gli equivalenti [SKOS](https://www.w3.org/TR/skos-primer/) per il vocabolario della [tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy). SharePoint non supporta i valori [SKOS](https://www.w3.org/TR/skos-primer/) che non hanno alcun equivalente per la tassonomia di SharePoint.

|Tassonomia di SharePoint|Equivalente SKOS|
|:-----------------|:--------------|
|sharepoint-taxonomy:Term|skos:Concept|
|sharepoint-taxonomy:TermSet|skos:ConceptScheme|
|sharepoint-taxonomy:inTermSet|skos:inScheme|
|sharepoint-taxonomy:hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-taxonomy:topLevelTermOf|skos:topConceptOf|
|sharepoint-taxonomy:defaultLabel|skos:prefLabel|
|sharepoint-taxonomy:termSetName|skos:prefLabel|
|sharepoint-taxonomy:propertyName|skos:prefLabel|
|sharepoint-taxonomy:otherLabel|skos:altLabel|
|sharepoint-taxonomy:description|skos:definition|
|sharepoint-taxonomy:parent|skos:broader|
|sharepoint-taxonomy:child|skos:narrower|

La tabella seguente mostra gli elementi del vocabolario per la tassonomia di SharePoint derivati da [OWL](https://www.w3.org/TR/owl2-primer/).

|Vocabolario per la tassonomia di SharePoint|Derivato da OWL|
|:-----------------------------|:----------------------|
|sharepoint-taxonomy:isAvailableForTagging|owl:datatypeproperty|
|sharepoint-taxonomy:SharedCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:LocalCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>Vocabolario per la tassonomia di SharePoint

Una tassonomia è un sistema di classificazione formale. Una tassonomia raggruppa parole, etichette e termini che descrivono qualcosa e quindi li organizza in gruppi all’interno di una gerarchia.

**sharepoint-taxonomy:Term**

Rappresenta un termine o una parola chiave in una gerarchia di metadati gestiti.

Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è l'unità atomica di un [archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) di SharePoint. Ogni [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) appartiene a un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) che a sua volta appartiene a un [gruppo di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). 

La sintassi per definire un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è la seguente:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) esiste tassativamente all'interno di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Etichetta predefinita è il nome del [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) così come appare nella rappresentazione visiva. I campi obbligatori per la definizione di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) includono:

- sharepoint-taxonomy:defaultLabel
- sharepoint-taxonomy:inTermSet

Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può:

- Essere gerarchicamente correlato a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), entrambi i [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) devono appartenere allo stesso [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Avere più [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) figlio, ma un singolo [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre.
- Non avere un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre definito, se si tratta di un termine di primo livello di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Avere un’etichetta predefinita, per ogni lingua di lavoro dell’[archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).
- Essere non esistente, se non contiene un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre e non è un termine di primo livello di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). 
- Avere un’unica etichetta predefinita nello stesso livello gerarchico.

**sharepoint-taxonomy:TermSet**

Rappresenta un set gerarchico o semplice di termini noto come "set di termini".

Come suggerisce il nome, il set di termini è un set di [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in un [archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) deve appartenere a un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Nessun [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può essere esistere in modo indipendente. 

La sintassi per definire un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) è la seguente:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

I [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) sono raggruppati logicamente in [gruppi di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). Il campo obbligatorio per la definizione di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) è:

- sharepoint-taxonomy:termSetName

Nel caso il cui il nome del set di termini fornito non sia univoco all'interno del [gruppo di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint aggiunge un numero alla fine del nome per mantenere l'univocità del nome del set di termini.

**sharepoint-taxonomy:hasTopLevelTerm**

SharePoint usa questa proprietà per mappare il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) di primo livello nel [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), ossia il punto di ingresso della gerarchia di [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Si tratta di una relazione inversa rispetto a sharepoint-taxonomy:topLevelTermOf. 

La sintassi per definire questa relazione è:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> Non è possibile definire il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) di primo livello di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre.

**sharepoint-taxonomy:topLevelTermOf**

Sharepoint-taxonomy:topLevelTermOf è la relazione inversa rispetto a sharepoint-taxonomy:hasTopLevelTerm

La sintassi per definire questa relazione è:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

Usare questa opzione per mappare un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può esistere soltanto in un singolo [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint richiede questa proprietà per la [definizione di un termine](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Etichette obbligatorie

È possibile che l'organizzazione intenda eseguire un'attenta pianificazione prima che sia possibile iniziare a usare i metadati gestiti. La quantità di pianificazione da eseguire dipende da quanto è formale la tassonomia. Dipende anche dalla quantità di controllo che si vuole stabilire sui metadati. A ogni livello della gerarchia, è necessario configurare le etichette obbligatorie per un termine o un set di termini.

Un termine può avere una o più etichette nella lingua predefinita e zero o più etichette nella lingua non predefinita. Se il termine dispone di etichette in una lingua, una delle etichette deve essere l'etichetta predefinita.

**sharepoint-taxonomy:defaultLabel**

Usare questa etichetta lessicale predefinita per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), si tratta di un parametro obbligatorio per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Da usare per rappresentare visivamente il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintassi per definire un’etichetta predefinita è:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

L’etichetta predefinita contiene due parti: la stringa e il tag lingua. La lingua deve essere una delle lingue di lavoro dell’[archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). L’etichetta predefinita deve essere univoca per tutti i [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nello stesso [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), allo stesso livello gerarchico.

**sharepoint-taxonomy:termSetName**

Ottiene e imposta il nome per il set di termini corrente.

Si tratta dell’etichetta lessicale per un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in una lingua di lavoro dell’[archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Si tratta di un parametro obbligatorio per un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Da usare per rappresentare visivamente un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).

La sintassi per definire un nome del set di termini è:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

Ottiene e imposta il nome proprietà per il set di termini corrente.

Si tratta dell'etichetta lessicale per sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in una lingua di lavoro dell’[archivio termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).

Il sharepoint-taxonomy:propertyName viene considerato come chiave della proprietà personalizzata.

La sintassi per definire un nome proprietà è:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Etichette facoltative

È possibile aggiungere anche etichette facoltative alla tassonomia.

**sharepoint-taxonomy:otherLabel**

Si tratta dell'etichetta lessicale alternativa per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

La sintassi per definire un’etichetta alternativa è:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Relazioni semantiche

Le tassonomie hanno relazioni gerarchiche e in alcuni casi relazioni associative semplici di "termini correlati", ma alcune hanno "relazioni semantiche" o relazioni personalizzate. 

**sharepoint-taxonomy:parent**

In questo modo, un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è correlato gerarchicamente a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può essere un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) di primo livello di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), ma in caso contrario deve avere un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre. 

La sintassi per definire un termine padre è:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Ciò significa che termineA è il padre e  termineA è il figlio.

**sharepoint-taxonomy:child**

L'oggetto contiene uno o più elementi figlio di un set di termini, che è possibile utilizzare tramite la proprietà set di termini. Questa classe fornisce anche metodi per la creazione di nuovi oggetti figlio di un set di termini. Nel gruppo sono specificate le autorizzazioni per modificare il termine figlio e gli elementi di un set di termini. 

In questo modo, un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è correlato gerarchicamente a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintassi per definire un termine figlio è:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Ciò significa che termineA è il padre e  termineA è il figlio.

## <a name="documentation-notes"></a>Note sulla documentazione

Questa sezione riguarda la tassonomia dettagliata in Microsoft.SharePoint.Taxonomy Namespace.

**sharepoint-taxonomy:description**

Si tratta di una spiegazione dettagliata di tutti gli elementi del vocabolario per la [tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy). 

La sintassi per aggiungere una descrizione è:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Proprietà personalizzate

Ottiene la raccolta delle proprietà personalizzate per il termine corrente dal dizionario di sola lettura.

Le proprietà personalizzate sono coppie di chiave-valori che possono essere definite per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), per agevolare la descrizione del [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o di un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint specifica la chiave della proprietà personalizzata con l'aiuto di propertyName.

**sharepoint-taxonomy:CustomPropertyForTermSet**

La sintassi per definire questa relazione è:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

Se la proprietà personalizzata per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) deve essere trasmessa con il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) quando il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) viene riutilizzato altrove, è necessario definirla in SharedCustomPropertyForTerm.

La sintassi per definire questa relazione è:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

Se la proprietà personalizzata per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) non deve essere trasmessa con il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) quando il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) viene riutilizzato altrove, è necessario definirla in LocalCustomPropertyForTerm.

La sintassi per definire questa relazione è:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Proprietà dei dati

A ogni livello della gerarchia, è necessario configurare le specifiche proprietà dei dati per un termine o un set di termini.

**sharepoint-taxonomy:isAvailableForTagging**

Usare questa opzione per specificare se un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [set di termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) è disponibile negli elenchi e nelle raccolte di SharePoint.  

La sintassi per questa operazione è:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Dominio e intervallo

La tabella seguente descrive il dominio e l'intervallo del vocabolario per la tassonomia di SharePoint.

|Predicati/verbi|Significato|Dominio|Intervallo|
|:--------------|:------|:-----|:----|
inTermSet|Nel set di termini|Termine|Set di termini|
inTermGroup|In un gruppo di termini|TermSet|TermGroup|
topLevelTermOf|È un termine di primo livello di|Termine|TermSet|
hasTopLevelTerm|Ha un termine di primo livello|Set di termini|Termine|
termSetName|Nome del set di termini|Termine|Letterale|
defaultLabel|Il termine ha un’etichetta predefinita|Termine|Letterale|
otherLabel|Il termine ha un'etichetta alternativa|Termine|Letterale|
propertyName|Ha un’etichetta proprietà|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolean, String, Integer, Decimal, Double|
|descrizione|Ha una descrizione|Tutto|Letterale|
|padre|Ha un padre|Termine|Termine|
|figlio|Ha un figlio|Termine|Termine|
|isAvailableForTagging|È disponibile per il tagging|Termine, Set di termini|Booleano|
|SharedCustomPropertyForTerm|Ha una proprietà personalizzata condivisa|Termine|Boolean, string, Integer, Decimal, Double|
|LocalCustomPropertyForTerm|Ha una proprietà personalizzata locale|Termine|Boolean, String, Integer, Decimal, Double|
|CustomPropertyForTermSet|Ha una proprietà personalizzata|TermSet|Boolean, String, Integer, Decimal, Double|

Scenari validi [SKOS](https://www.w3.org/TR/skos-primer/) che la [tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) non consente:

- Ridondanza gerarchica: un concetto [SKOS](https://www.w3.org/TR/skos-primer/) può essere associato a diversi concetti più ampi contemporaneamente, ma un sharepoint-taxonomy:Term può avere un solo sharepoint-taxonomy:parent, perciò la dipendenza ciclica dei termini non è consentita.
- I termini orfani non sono consentiti nella tassonomia di SharePoint. Ogni sharepoint-taxonomy:Term deve avere un sharepoint-taxonomy:parent o deve essere il sharepoint-taxonomy:topLevelTermOf un set di termini.
- La tassonomia di SharePoint non supporta le relazioni associative.
- La tassonomia di SharePoint consente solo due tipi di relazioni gerarchiche, ossia sharepoint-taxonomy:parent e sharepoint-Taxonomy:child. 
- Diversamente da [SKOS](https://www.w3.org/TR/skos-primer/), la relazione gerarchica nel vocabolario per la tassonomia di SharePoint può essere stabilita solo con termini che sono all'interno dello stesso set di termini.

## <a name="see-also"></a>Vedere anche

[Importare un set di termini con un formato basato su SKOS](import-term-set-skos.md)

