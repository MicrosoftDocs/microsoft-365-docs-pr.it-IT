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
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>Riferimento al formato SKOS per la tassonomia di SharePoint

Questo articolo include il vocabolario RDF utilizzato per rappresentare la [Tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) e si basa su [SKOS](https://www.w3.org/TR/skos-primer/). Per la serializzazione di questa sintassi RDF, usare la [tartaruga](https://www.w3.org/TR/turtle/)RDF.

Nella tabella seguente vengono illustrati gli equivalenti di [SKOS](https://www.w3.org/TR/skos-primer/) per il vocabolario della [Tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) . SharePoint non supporta i valori di [SKOS](https://www.w3.org/TR/skos-primer/) che non dispongono di una tassonomia di SharePoint equivalente.

|Tassonomia di SharePoint|SKOS equivalente|
|:-----------------|:--------------|
|SharePoint-tassonomia: termine|skos: Concept|
|SharePoint-tassonomia: termini|skos: ConceptScheme|
|SharePoint-tassonomia: indicizzazione|skos: inscheme|
|SharePoint-tassonomia: hasTopLevelTerm|skos: hasTopConcept|
|SharePoint-tassonomia: topLevelTermOf|skos: topConceptOf|
|SharePoint-tassonomia: defaultLabel|skos: prefLabel|
|SharePoint-tassonomia: termSetName|skos: prefLabel|
|SharePoint-tassonomia: propertyName|skos: prefLabel|
|SharePoint-tassonomia: otherLabel|skos: altLabel|
|SharePoint-tassonomia: Descrizione|skos: definizione|
|SharePoint-tassonomia: padre|skos: più ampio|
|SharePoint-tassonomia: figlio|skos: più stretto|

Nella tabella seguente vengono mostrate le entità del vocabolario di tassonomia di SharePoint derivato da [Owl](https://www.w3.org/TR/owl2-primer/).

|Vocabolario della tassonomia di SharePoint|Derivato da OWL|
|:-----------------------------|:----------------------|
|SharePoint-tassonomia: isAvailableForTagging|Gufo: datatypeproperty|
|SharePoint-tassonomia: SharedCustomPropertyForTerm|Gufo: ObjectProperty|
|SharePoint-tassonomia: LocalCustomPropertyForTerm|Gufo: ObjectProperty|
|SharePoint-tassonomia: CustomPropertyForTermSet|Gufo: ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>Vocabolario della tassonomia di SharePoint

Una tassonomia è un sistema di classificazione formale. Una tassonomia raggruppa le parole, le etichette e i termini che descrivono qualcosa, quindi dispone i gruppi in una gerarchia.

**SharePoint-tassonomia: termine**

Rappresenta un termine o una parola chiave in una gerarchia di metadati gestiti.

Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è l'unità atomica di una [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)di SharePoint. Ogni [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) appartiene a un [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) che appartiene a un [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). 

La sintassi per definire un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) è la seguente:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) obbligatoriamente esiste all'interno di un [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). DefaultLabel è il nome del [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) così come viene visualizzato nella rappresentazione visiva. I campi obbligatori per la definizione di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) includono:

- SharePoint-tassonomia: defaultLabel
- SharePoint-tassonomia: indicizzazione

Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può:

- Essere gerarchicamente correlato a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) che viene fornito entrambi i [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) appartengono allo stesso [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Sono presenti più [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)figlio, ma solo un singolo [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)padre.
- Non è stato definito un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) padre, se si tratta [di un topLevelTermOf a.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)
- Disporre di un defaultLabel, per lingua di lavoro [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .
- Non esiste se non contiene un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)padre, né il topLevelTermOf è un [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). 
- Dispongono di un solo defaultLabel univoco nello stesso livello gerarchico.

**SharePoint-tassonomia: termini**

Rappresenta un insieme gerarchico o flat di oggetti term noti come "set di termini".

Come suggerisce il nome, il set di termini è un insieme di [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in un [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) deve appartenere a un [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Nessun [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può esistere in modo indipendente. 

La sintassi per definire un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) è la seguente:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

Le [TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) sono raggruppate logicamente in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). Il campo obbligatorio per la definizione di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) è il seguente:

- SharePoint-tassonomia: termSetName

Nel caso di termSetName specificato non è univoco all'interno di [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint aggiunge un numero alla fine del nome per mantenere l'univocità di termSetName.

**SharePoint-tassonomia: hasTopLevelTerm**

SharePoint utilizza questa proprietà per mappare la parte superiore del [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nel [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), che è il punto di ingresso alla gerarchia dei [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) [in un termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Si tratta di una relazione inversa con la tassonomia di SharePoint: topLevelTermOf. 

La sintassi da definire è la seguente:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> Non è possibile definire il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) di primo livello di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)padre.

**SharePoint-tassonomia: topLevelTermOf**

SharePoint-tassonomia: topLevelTermOf è l'inverso di SharePoint-tassonomia: hasTopLevelTerm

La sintassi da definire è la seguente:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**SharePoint-tassonomia: indicizzazione**

Utilizzare questa funzione per mappare un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a un [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) può esistere solo in un singolo [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint richiede questa proprietà quando si [definisce un termine](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Etichette obbligatorie

L'organizzazione potrebbe voler fare un'attenta pianificazione prima di iniziare a utilizzare i metadati gestiti. La quantità di pianificazione che è necessario eseguire dipende dalla modalità formale di tassonomia. Dipende anche dalla quantità di controllo che si desidera imporre ai metadati. A ogni livello della gerarchia, è necessario configurare le etichette obbligatorie per un termine o un punto di riferimento.

Un termine può avere una o più etichette nella lingua predefinita e zero o più etichette nella lingua non predefinita. Se il termine contiene etichette in una lingua, è necessario che una delle etichette sia l'etichetta predefinita.

**SharePoint-tassonomia: defaultLabel**

Utilizzare questa etichetta lessicale predefinita per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) che è un parametro obbligatorio per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Utilizzato per rappresentare visivamente il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintassi per definire un defaultLabel è la seguente:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

La defaultLabel contiene due parti: la stringa e il tag lingua. La lingua deve essere una delle lingue di lavoro di [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) . DefaultLabel deve essere univoco per tutti i [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) nello stesso [punto di riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), allo stesso livello gerarchico.

**SharePoint-tassonomia: termSetName**

Ottiene e imposta il nome per l'oggetto set di termini corrente.

Questa è l'etichetta lessicale di un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in una lingua di lavoro di [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) . Questo è un parametro obbligatorio per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Consente di rappresentare visivamente un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).

La sintassi per definire un termSetName è la seguente:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**SharePoint-tassonomia: propertyName**

Ottiene e imposta il nome della proprietà per l'oggetto set di termini corrente.

Questa è l'etichetta lessicale per una tassonomia di SharePoint: SharedCustomPropertyForTerm, SharePoint-tassonomia: LocalCustomPropertyForTerm e SharePoint-tassonomia: CustomPropertyForTermSet in una lingua di lavoro [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .

La tassonomia di SharePoint: propertyName viene trattata come la chiave di CustomProperty.

La sintassi per definire un propetyName è la seguente:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Etichette facoltative

È inoltre possibile aggiungere etichette facoltative alla tassonomia.

**SharePoint-tassonomia: otherLabel**

Si tratta dell'etichetta lessicale alternativa per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

La sintassi per definire un otherLabel è la seguente:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Relazioni semantiche

Le tassonomie hanno una relazione associativa gerarchica e talvolta semplice "correlata", ma alcune hanno "relazioni semantiche" o relazioni personalizzate. 

**SharePoint-tassonomia: padre**

Questo collega gerarchicamente un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) potrebbe essere un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) di primo livello di un [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), ma in caso contrario deve avere un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)padre. 

La sintassi per la definizione di un elemento padre è la seguente:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Questo significa che TermA1 ha una parola padre. Inversamente, significa anche che TermA1 è il figlio di terma. La relazione padre-figlio è una relazione inversible.

**SharePoint-tassonomia: figlio**

L'oggetto contiene una o più istanze di termini figlio, che possono essere accessibili tramite la proprietà TermSets. Questa classe fornisce anche metodi per la creazione di nuovi oggetti di termini figlio. Le autorizzazioni per la modifica delle istanze di termini e clausole figlio sono specificate nel gruppo. 

Questo collega gerarchicamente un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) a un altro [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

La sintassi per la definizione di un elemento figlio è la seguente:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Questo significa che terma ha un figlio TermA1. Inversamente, significa anche che il termine è l'elemento padre della relazione padre-figlio di TermA1 è una relazione di inversible.

## <a name="documentation-notes"></a>Note sulla documentazione

In questa sezione viene illustrata la tassonomia descritta nello spazio dei nomi Microsoft. SharePoint. tassonomia.

**SharePoint-tassonomia: Descrizione**

Si tratta di una spiegazione dettagliata di qualsiasi entità del vocabolario della [Tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) . 

La sintassi per aggiungere una descrizione è la seguente:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Proprietà personalizzate

Ottiene l'insieme di oggetti Property personalizzati per l'oggetto term corrente dal dizionario di sola lettura.

Le proprietà personalizzate sono coppie di valori chiave che è possibile definire per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [punto di vista](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), per ulteriori informazioni sulla descrizione del [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o su un punto di [riferimento](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint specifica la chiave della proprietà personalizzata con l'ausilio di propertyName.

**SharePoint-tassonomia: CustomPropertyForTermSet**

La sintassi da definire è la seguente:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**SharePoint-tassonomia: SharedCustomPropertyForTerm**

Se la proprietà personalizzata per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) deve essere eseguita insieme al [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando si riutilizza il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) da un'altra posizione, è necessario definirlo in SharedCustomPropertyForTerm.

La sintassi da definire è la seguente:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**SharePoint-tassonomia: LocalCustomPropertyForTerm**

Se non è necessario che la proprietà personalizzata per un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) venga eseguita insieme al [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), quando si riutilizza il [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in un'altra posizione, è necessario definirlo in LocalCustomPropertyForTerm.

La sintassi da definire è la seguente:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Proprietà dei dati

A ogni livello della gerarchia è possibile configurare specifiche proprietà dei dati per un termine o un punto di riferimento.

**SharePoint-tassonomia: isAvailableForTagging**

Utilizzare questa impostazione per specificare se un [termine](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) o un [termini](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) sono disponibili negli elenchi e nelle raccolte di SharePoint.  

La sintassi di questo è:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Dominio e intervallo

Nella tabella seguente vengono descritti il dominio e l'intervallo di terminologia della tassonomia di SharePoint.

|Predicati/verbo|Significato|Dominio|Range|
|:--------------|:------|:-----|:----|
intermini|Set di termini|Termine|Set di termini|
inTermGroup|In gruppo di termini|Termini|TermGroup|
topLevelTermOf|È il termine di primo livello di|Termine|Termini|
hasTopLevelTerm|Ha un termine di primo livello|Set di termini|Termine|
termSetName|Il set di termini ha il nome|Termine|Valore letterale normale|
defaultLabel|Il termine è etichetta predefinita|Termine|Valore letterale normale|
otherLabel|Il termine ha un'altra etichetta|Termine|Valore letterale normale|
propertyName|Etichetta di proprietà|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolean, String, Integer, Decimal, Double|
|descrizione|Contiene una descrizione|Tutti|Valore letterale normale|
|padre|Ha padre|Termine|Termine|
|bambino|Ha un figlio|Termine|Termine|
|isAvailableForTagging|È disponibile per il tagging|Termini, set di termini|Booleano|
|SharedCustomPropertyForTerm|Ha una proprietà personalizzata condivisa|Termine|Boolean, String, Integer, Decimal, Double|
|LocalCustomPropertyForTerm|Dispone di una proprietà personalizzata locale|Termine|Boolean, String, Integer, Decimal, Double|
|CustomPropertyForTermSet|Ha una proprietà personalizzata|Termini|Boolean, String, Integer, Decimal, Double|

[SKOS](https://www.w3.org/TR/skos-primer/) scenari validi che la [Tassonomia di SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) non consente:

- Ridondanza gerarchica-un concetto di [SKOS](https://www.w3.org/TR/skos-primer/) può essere associato a più concetti più ampi contemporaneamente, ma un termine per la tassonomia di SharePoint può avere una sola tassonomia di SharePoint: non è consentita anche la dipendenza a livello di padre e quindi ciclica.
- I termini orfani non sono consentiti nella tassonomia di SharePoint. Ogni tipo di tassonomia di SharePoint: il termine deve disporre di una tassonomia di SharePoint: padre o deve essere la tassonomia di SharePoint: topLevelTermOf un punto di riferimento.
- La tassonomia di SharePoint non supporta le relazioni associative.
- La tassonomia di SharePoint consente solo 2 tipi di relazioni gerarchiche – la tassonomia di SharePoint: padre e SharePoint-tassonomia: figlio. 
- A differenza di [SKOS](https://www.w3.org/TR/skos-primer/) la relazione gerarchica nel vocabolario della tassonomia di SharePoint, può essere stabilita solo con termini all'interno dello stesso termini.

## <a name="see-also"></a>Vedere anche

[Importare un set di termini utilizzando un formato basato su SKOS](import-term-set-skos.md)

