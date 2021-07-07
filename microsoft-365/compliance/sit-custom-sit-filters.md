---
title: Informazioni di riferimento sui filtri dei tipi di informazioni riservate personalizzate
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: In questo articolo viene presentato un elenco dei filtri che possono essere codificati in tipi di informazioni riservate personalizzati.
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322701"
---
# <a name="custom-sensitive-information-type-filters-reference"></a>Informazioni di riferimento sui filtri dei tipi di informazioni riservate personalizzate

In Microsoft è possibile definire filtri o controlli aggiuntivi durante la creazione di tipi di informazioni riservate personalizzati (SIT).

## <a name="list-of-supported-filters-and-use-cases"></a>Elenco dei filtri e dei casi d'uso supportati

### <a name="alldigitssame-exclude"></a>AllDigitsSame Exclude

Descrizione: consente di escludere corrispondenze con tutte le cifre come cifre duplicate, ad esempio 111111111 o 111-111-111

Definizione dei filtri
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

Uso nel pacchetto di regole a livello di entità
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

Uso nel pacchetto di regole a livello di modello
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a>TextMatchFilter StartsWith 

Descrizione: consente di definire i caratteri di partenza per l'entità. Ha due varianti, include ed escludi.

Ad esempio, per escludere i numeri che iniziano con 0500, 91, 091, 010 in un elenco simile al seguente:

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

è possibile usare questo xml

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
Ad esempio, per includere i numeri che iniziano con 0500, 91, 091, 0100 in un elenco simile al seguente: 

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

è possibile usare questo xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a>TextMatchFilter EndsWith 

Descrizione: consente di definire i caratteri finali per l'entità. 

Ad esempio, per escludere i numeri che terminano con 0500,91,091, 0100 in un elenco simile al seguente:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

è possibile usare questo xml

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

Ad esempio, per includere i numeri che terminano con 0500, 91, 091, 0100, in un elenco simile al seguente:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

è possibile usare questo xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a>TextMatchFilter Full

Descrizione: consente di proibire determinate corrispondenze per impedire loro di attivare la regola. Ad esempio, escludere 41111111111111 dall'elenco delle corrispondenze valide con carta di credito.

Ad esempio, per escludere numeri di carta di credito come 411111111111111 e 3241891031113111 in un elenco simile al seguente:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

è possibile usare questo xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

Ad esempio, per includere numeri di carta di credito come 411111111111111 e 3241891031113111 in un elenco simile al seguente:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

è possibile usare questo xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a>Prefisso TextMatchFilter

Descrizione: consente di definire i caratteri precedenti che devono essere sempre inclusi o esclusi. Ad esempio, se il numero della carta di credito è preceduto da "ID ordine:" rimuovi la corrispondenza dalle corrispondenze valide.

Ad esempio, per escludere le occorrenze di numeri di telefono che hanno un Telefono e **chiamarmi** alle stringhe prima del numero di telefono, in un elenco simile al seguente: 

- numero di telefono 091-8974-653278
- Telefono 45-124576532-123
- 45-124576532-123

è possibile usare questo xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

Ad esempio, per includere  le occorrenze con stringhe con carta di credito e **carta #** prima del numero di carta di credito, in un elenco simile al seguente:

- Carta di credito 45-124576532-123 
- 45-124576532-123 (che potrebbe essere il numero di telefono)

è possibile usare questo xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a>Suffisso TextMatchFilter

Descrizione: consente di definire i caratteri seguenti che devono essere sempre inclusi o esclusi. Ad esempio, se il numero della carta di credito è seguito da '/xuid', rimuovi la corrispondenza dalle corrispondenze valide.

Ad esempio, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:

- 1234-5678-9321 4500 9870 6321 48925566
- 1234-5678-9321

è possibile usare questo xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
Ad esempio, per escludere le occorrenze se sono seguite da **/xuidsuffix**, come una in questo elenco:

- 1234-5678-9321 /xuid
- 1234-5678-9321

è possibile usare questo xml

''xml <Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      <Term>/xuid</Term>
    </Group> </Keyword>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a>Utilizzo di filtri nei pacchetti di regole

I filtri possono essere definiti sull'intero SIT o su un motivo. Ecco alcuni esempi di frammenti di codice. 

### <a name="at-sensitive-information-type-level"></a>A livello di tipo di informazioni riservate

Filtri nell'entità: verranno applicati tutti i modelli figlio

I filtri verranno applicati a **tutte le** istanze classificate da uno dei modelli in tale entità/tipo riservato

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a>A livello individuale del tipo di informazioni riservate

Filtra solo a livello di motivo.

Il filtro verrà applicato alle istanze corrispondenti al modello.

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a>A livello di tipo di informazioni riservate e un filtro aggiuntivo su alcuni dei modelli di tale entità

Filtri in entity + pattern

I filtri verranno applicati a **tutte le** istanze classificate da uno dei modelli in tale entità/tipo riservato. Il filtro a livello di modello filtra le istanze corrispondenti a tale modello.

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a>Ulteriori informazioni

- [Informazioni sulla prevenzione della perdita dei dati](dlp-learn-about-dlp.md)

- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)

- [Cosa individuano le funzioni di prevenzione della perdita dei dati](what-the-dlp-functions-look-for.md)
