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
# <a name="custom-sensitive-information-type-filters-reference"></a><span data-ttu-id="e61d4-103">Informazioni di riferimento sui filtri dei tipi di informazioni riservate personalizzate</span><span class="sxs-lookup"><span data-stu-id="e61d4-103">Custom sensitive information type filters reference</span></span>

<span data-ttu-id="e61d4-104">In Microsoft è possibile definire filtri o controlli aggiuntivi durante la creazione di tipi di informazioni riservate personalizzati (SIT).</span><span class="sxs-lookup"><span data-stu-id="e61d4-104">In Microsoft you can define filters or additional checks while creating a custom sensitive information types (SIT).</span></span>

## <a name="list-of-supported-filters-and-use-cases"></a><span data-ttu-id="e61d4-105">Elenco dei filtri e dei casi d'uso supportati</span><span class="sxs-lookup"><span data-stu-id="e61d4-105">List of supported filters and use cases</span></span>

### <a name="alldigitssame-exclude"></a><span data-ttu-id="e61d4-106">AllDigitsSame Exclude</span><span class="sxs-lookup"><span data-stu-id="e61d4-106">AllDigitsSame Exclude</span></span>

<span data-ttu-id="e61d4-107">Descrizione: consente di escludere corrispondenze con tutte le cifre come cifre duplicate, ad esempio 111111111 o 111-111-111</span><span class="sxs-lookup"><span data-stu-id="e61d4-107">Description: Allows you to exclude matches which have all digits as duplicate digits, like 111111111 or 111-111-111</span></span>

<span data-ttu-id="e61d4-108">Definizione dei filtri</span><span class="sxs-lookup"><span data-stu-id="e61d4-108">Defining filters</span></span>
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

<span data-ttu-id="e61d4-109">Uso nel pacchetto di regole a livello di entità</span><span class="sxs-lookup"><span data-stu-id="e61d4-109">Using it in rule package at the entity level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

<span data-ttu-id="e61d4-110">Uso nel pacchetto di regole a livello di modello</span><span class="sxs-lookup"><span data-stu-id="e61d4-110">Using it in rule package at the pattern level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a><span data-ttu-id="e61d4-111">TextMatchFilter StartsWith</span><span class="sxs-lookup"><span data-stu-id="e61d4-111">TextMatchFilter StartsWith</span></span> 

<span data-ttu-id="e61d4-112">Descrizione: consente di definire i caratteri di partenza per l'entità.</span><span class="sxs-lookup"><span data-stu-id="e61d4-112">Description: Allows you to define the starting characters for the entity.</span></span> <span data-ttu-id="e61d4-113">Ha due varianti, include ed escludi.</span><span class="sxs-lookup"><span data-stu-id="e61d4-113">It has two variants, include and exclude.</span></span>

<span data-ttu-id="e61d4-114">Ad esempio, per escludere i numeri che iniziano con 0500, 91, 091, 010 in un elenco simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e61d4-114">For example to exclude the numbers starting with 0500, 91, 091, 010 in a list like this:</span></span>

- <span data-ttu-id="e61d4-115">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="e61d4-115">0500-4500-027</span></span>
- <span data-ttu-id="e61d4-116">91564721450</span><span class="sxs-lookup"><span data-stu-id="e61d4-116">91564721450</span></span>
- <span data-ttu-id="e61d4-117">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="e61d4-117">91-8523697410</span></span>
- <span data-ttu-id="e61d4-118">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="e61d4-118">700-8956-7844</span></span>
- <span data-ttu-id="e61d4-119">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="e61d4-119">1000-3265-9874</span></span>
- <span data-ttu-id="e61d4-120">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="e61d4-120">0100-7892-3012</span></span>

<span data-ttu-id="e61d4-121">è possibile usare questo xml</span><span class="sxs-lookup"><span data-stu-id="e61d4-121">you can use this xml</span></span>

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
<span data-ttu-id="e61d4-122">Ad esempio, per includere i numeri che iniziano con 0500, 91, 091, 0100 in un elenco simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e61d4-122">For example, to include the numbers starting with 0500, 91, 091, 0100 in a list like this:</span></span> 

- <span data-ttu-id="e61d4-123">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="e61d4-123">0500-4500-027</span></span>
- <span data-ttu-id="e61d4-124">91564721450</span><span class="sxs-lookup"><span data-stu-id="e61d4-124">91564721450</span></span>
- <span data-ttu-id="e61d4-125">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="e61d4-125">91-8523697410</span></span>
- <span data-ttu-id="e61d4-126">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="e61d4-126">700-8956-7844</span></span>
- <span data-ttu-id="e61d4-127">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="e61d4-127">1000-3265-9874</span></span>
- <span data-ttu-id="e61d4-128">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="e61d4-128">0100-7892-3012</span></span>

<span data-ttu-id="e61d4-129">è possibile usare questo xml</span><span class="sxs-lookup"><span data-stu-id="e61d4-129">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a><span data-ttu-id="e61d4-130">TextMatchFilter EndsWith</span><span class="sxs-lookup"><span data-stu-id="e61d4-130">TextMatchFilter EndsWith</span></span> 

<span data-ttu-id="e61d4-131">Descrizione: consente di definire i caratteri finali per l'entità.</span><span class="sxs-lookup"><span data-stu-id="e61d4-131">Description: Allows you to define the ending characters for the entity.</span></span> 

<span data-ttu-id="e61d4-132">Ad esempio, per escludere i numeri che terminano con 0500,91,091, 0100 in un elenco simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e61d4-132">For example, to exclude the numbers ending with 0500,91,091, 0100 in a list like this:</span></span>

- <span data-ttu-id="e61d4-133">1234567891</span><span class="sxs-lookup"><span data-stu-id="e61d4-133">1234567891</span></span>
- <span data-ttu-id="e61d4-134">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="e61d4-134">1234-5678-0091</span></span>
- <span data-ttu-id="e61d4-135">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="e61d4-135">1234.4567.7091</span></span>
- <span data-ttu-id="e61d4-136">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="e61d4-136">1234-8091-4564</span></span>

<span data-ttu-id="e61d4-137">è possibile usare questo xml</span><span class="sxs-lookup"><span data-stu-id="e61d4-137">you can use this xml</span></span>

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

<span data-ttu-id="e61d4-138">Ad esempio, per includere i numeri che terminano con 0500, 91, 091, 0100, in un elenco simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e61d4-138">For example, to include the numbers ending with 0500, 91, 091, 0100, in a list like this:</span></span>

- <span data-ttu-id="e61d4-139">1234567891</span><span class="sxs-lookup"><span data-stu-id="e61d4-139">1234567891</span></span>
- <span data-ttu-id="e61d4-140">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="e61d4-140">1234-5678-0091</span></span>
- <span data-ttu-id="e61d4-141">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="e61d4-141">1234.4567.7091</span></span>
- <span data-ttu-id="e61d4-142">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="e61d4-142">1234-8091-4564</span></span>

<span data-ttu-id="e61d4-143">è possibile usare questo xml</span><span class="sxs-lookup"><span data-stu-id="e61d4-143">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a><span data-ttu-id="e61d4-144">TextMatchFilter Full</span><span class="sxs-lookup"><span data-stu-id="e61d4-144">TextMatchFilter Full</span></span>

<span data-ttu-id="e61d4-145">Descrizione: consente di proibire determinate corrispondenze per impedire loro di attivare la regola.</span><span class="sxs-lookup"><span data-stu-id="e61d4-145">Description: Allows you to prohibit certain matches to prevent them from triggering the rule.</span></span> <span data-ttu-id="e61d4-146">Ad esempio, escludere 41111111111111 dall'elenco delle corrispondenze valide con carta di credito.</span><span class="sxs-lookup"><span data-stu-id="e61d4-146">For example, exclude 4111111111111111 from the list of valid credit card matches.</span></span>

<span data-ttu-id="e61d4-147">Ad esempio, per escludere numeri di carta di credito come 411111111111111 e 3241891031113111 in un elenco simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e61d4-147">For example, to exclude credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="e61d4-148">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="e61d4-148">4485 3647 3952 7352</span></span>
- <span data-ttu-id="e61d4-149">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="e61d4-149">4111111111111111</span></span>
- <span data-ttu-id="e61d4-150">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="e61d4-150">3241891031113111</span></span>

<span data-ttu-id="e61d4-151">è possibile usare questo xml</span><span class="sxs-lookup"><span data-stu-id="e61d4-151">you can use this xml</span></span>

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

<span data-ttu-id="e61d4-152">Ad esempio, per includere numeri di carta di credito come 411111111111111 e 3241891031113111 in un elenco simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e61d4-152">For example, to include credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="e61d4-153">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="e61d4-153">4485 3647 3952 7352</span></span>
- <span data-ttu-id="e61d4-154">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="e61d4-154">4111111111111111</span></span>
- <span data-ttu-id="e61d4-155">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="e61d4-155">3241891031113111</span></span>

<span data-ttu-id="e61d4-156">è possibile usare questo xml</span><span class="sxs-lookup"><span data-stu-id="e61d4-156">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a><span data-ttu-id="e61d4-157">Prefisso TextMatchFilter</span><span class="sxs-lookup"><span data-stu-id="e61d4-157">TextMatchFilter Prefix</span></span>

<span data-ttu-id="e61d4-158">Descrizione: consente di definire i caratteri precedenti che devono essere sempre inclusi o esclusi.</span><span class="sxs-lookup"><span data-stu-id="e61d4-158">Description: Allows you to define the preceding characters that should be always included or excluded.</span></span> <span data-ttu-id="e61d4-159">Ad esempio, se il numero della carta di credito è preceduto da "ID ordine:" rimuovi la corrispondenza dalle corrispondenze valide.</span><span class="sxs-lookup"><span data-stu-id="e61d4-159">For example, if Credit card number is preceded by ‘Order ID:’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="e61d4-160">Ad esempio, per escludere le occorrenze di numeri di telefono che hanno un Telefono e **chiamarmi** alle stringhe prima del numero di telefono, in un elenco simile al seguente: </span><span class="sxs-lookup"><span data-stu-id="e61d4-160">For example, to exclude occurrences of phone numbers which have **Phone number** and **call me at** strings before the phone number, in a list like this:</span></span>

- <span data-ttu-id="e61d4-161">numero di telefono 091-8974-653278</span><span class="sxs-lookup"><span data-stu-id="e61d4-161">phone number 091-8974-653278</span></span>
- <span data-ttu-id="e61d4-162">Telefono 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="e61d4-162">Phone 45-124576532-123</span></span>
- <span data-ttu-id="e61d4-163">45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="e61d4-163">45-124576532-123</span></span>

<span data-ttu-id="e61d4-164">è possibile usare questo xml</span><span class="sxs-lookup"><span data-stu-id="e61d4-164">you can use this xml</span></span>

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

<span data-ttu-id="e61d4-165">Ad esempio, per includere  le occorrenze con stringhe con carta di credito e **carta #** prima del numero di carta di credito, in un elenco simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e61d4-165">For example, to include occurrences that have **credit card** and **card #** strings before the credit card number, in a list like this:</span></span>

- <span data-ttu-id="e61d4-166">Carta di credito 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="e61d4-166">Credit card 45-124576532-123</span></span> 
- <span data-ttu-id="e61d4-167">45-124576532-123 (che potrebbe essere il numero di telefono)</span><span class="sxs-lookup"><span data-stu-id="e61d4-167">45-124576532-123  (which could be phone number)</span></span>

<span data-ttu-id="e61d4-168">è possibile usare questo xml</span><span class="sxs-lookup"><span data-stu-id="e61d4-168">you can use this xml</span></span>

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

### <a name="textmatchfilter-suffix"></a><span data-ttu-id="e61d4-169">Suffisso TextMatchFilter</span><span class="sxs-lookup"><span data-stu-id="e61d4-169">TextMatchFilter Suffix</span></span>

<span data-ttu-id="e61d4-170">Descrizione: consente di definire i caratteri seguenti che devono essere sempre inclusi o esclusi.</span><span class="sxs-lookup"><span data-stu-id="e61d4-170">Description: Allows you to define the following characters that should be always included or excluded.</span></span> <span data-ttu-id="e61d4-171">Ad esempio, se il numero della carta di credito è seguito da '/xuid', rimuovi la corrispondenza dalle corrispondenze valide.</span><span class="sxs-lookup"><span data-stu-id="e61d4-171">For example, if Credit card number is followed by ‘/xuid’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="e61d4-172">Ad esempio, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span><span class="sxs-lookup"><span data-stu-id="e61d4-172">For example, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span></span>

- <span data-ttu-id="e61d4-173">1234-5678-9321 4500 9870 6321 48925566</span><span class="sxs-lookup"><span data-stu-id="e61d4-173">1234-5678-9321 4500 9870 6321 48925566</span></span>
- <span data-ttu-id="e61d4-174">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="e61d4-174">1234-5678-9321</span></span>

<span data-ttu-id="e61d4-175">è possibile usare questo xml</span><span class="sxs-lookup"><span data-stu-id="e61d4-175">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
<span data-ttu-id="e61d4-176">Ad esempio, per escludere le occorrenze se sono seguite da **/xuidsuffix**, come una in questo elenco:</span><span class="sxs-lookup"><span data-stu-id="e61d4-176">For example, to exclude occurrences if they are followed by **/xuidsuffix**, like one in this list:</span></span>

- <span data-ttu-id="e61d4-177">1234-5678-9321 /xuid</span><span class="sxs-lookup"><span data-stu-id="e61d4-177">1234-5678-9321 /xuid</span></span>
- <span data-ttu-id="e61d4-178">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="e61d4-178">1234-5678-9321</span></span>

<span data-ttu-id="e61d4-179">è possibile usare questo xml</span><span class="sxs-lookup"><span data-stu-id="e61d4-179">you can use this xml</span></span>

<span data-ttu-id="e61d4-180">''xml <Filters id="cc_number_filters_exc"></span><span class="sxs-lookup"><span data-stu-id="e61d4-180">\`\`xml <Filters id="cc_number_filters_exc"></span></span>
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <span data-ttu-id="e61d4-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span><span class="sxs-lookup"><span data-stu-id="e61d4-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span></span><Term><span data-ttu-id="e61d4-182">/xuid</span><span class="sxs-lookup"><span data-stu-id="e61d4-182">/xuid</span></span></Term>
    <span data-ttu-id="e61d4-183"></Group> </Keyword></span><span class="sxs-lookup"><span data-stu-id="e61d4-183"></Group> </Keyword></span></span>
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

## <a name="using-filters-in-rule-packages"></a><span data-ttu-id="e61d4-184">Utilizzo di filtri nei pacchetti di regole</span><span class="sxs-lookup"><span data-stu-id="e61d4-184">Using filters in rule packages</span></span>

<span data-ttu-id="e61d4-185">I filtri possono essere definiti sull'intero SIT o su un motivo.</span><span class="sxs-lookup"><span data-stu-id="e61d4-185">Filters can be defined on the entire SIT or on a pattern.</span></span> <span data-ttu-id="e61d4-186">Ecco alcuni esempi di frammenti di codice.</span><span class="sxs-lookup"><span data-stu-id="e61d4-186">Here are some code snippets examples.</span></span> 

### <a name="at-sensitive-information-type-level"></a><span data-ttu-id="e61d4-187">A livello di tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="e61d4-187">At sensitive information type level</span></span>

<span data-ttu-id="e61d4-188">Filtri nell'entità: verranno applicati tutti i modelli figlio</span><span class="sxs-lookup"><span data-stu-id="e61d4-188">Filters at Entity - will cover all child patterns</span></span>

<span data-ttu-id="e61d4-189">I filtri verranno applicati a **tutte le** istanze classificate da uno dei modelli in tale entità/tipo riservato</span><span class="sxs-lookup"><span data-stu-id="e61d4-189">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a><span data-ttu-id="e61d4-190">A livello individuale del tipo di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="e61d4-190">At the individual pattern of the sensitive information type level</span></span>

<span data-ttu-id="e61d4-191">Filtra solo a livello di motivo.</span><span class="sxs-lookup"><span data-stu-id="e61d4-191">Filters only at the pattern level.</span></span>

<span data-ttu-id="e61d4-192">Il filtro verrà applicato alle istanze corrispondenti al modello.</span><span class="sxs-lookup"><span data-stu-id="e61d4-192">The filter will be applied on the instances matched by the pattern.</span></span>

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a><span data-ttu-id="e61d4-193">A livello di tipo di informazioni riservate e un filtro aggiuntivo su alcuni dei modelli di tale entità</span><span class="sxs-lookup"><span data-stu-id="e61d4-193">At sensitive information type level and an additional filter on some of the patterns of that entity</span></span>

<span data-ttu-id="e61d4-194">Filtri in entity + pattern</span><span class="sxs-lookup"><span data-stu-id="e61d4-194">Filters at Entity + pattern</span></span>

<span data-ttu-id="e61d4-195">I filtri verranno applicati a **tutte le** istanze classificate da uno dei modelli in tale entità/tipo riservato.</span><span class="sxs-lookup"><span data-stu-id="e61d4-195">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type.</span></span> <span data-ttu-id="e61d4-196">Il filtro a livello di modello filtra le istanze corrispondenti a tale modello.</span><span class="sxs-lookup"><span data-stu-id="e61d4-196">The pattern level filter will filter the instances matched by that pattern.</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a><span data-ttu-id="e61d4-197">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="e61d4-197">More information</span></span>

- [<span data-ttu-id="e61d4-198">Informazioni sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="e61d4-198">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="e61d4-199">Definizioni delle entità tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="e61d4-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="e61d4-200">Cosa individuano le funzioni di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="e61d4-200">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
