---
title: Tipi di informazioni riservate disponibili da cercare
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: La prevenzione della perdita di dati (DLP) &amp; nel centro sicurezza e conformità include 80 tipi di informazioni riservate pronte per l'uso nei criteri DLP. In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.
ms.openlocfilehash: 9b863e231cd4b576999885ae3f0b5b6792c37150
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626252"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="ecdf4-104">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="ecdf4-104">What the sensitive information types look for</span></span>

<span data-ttu-id="ecdf4-105">La prevenzione della perdita di dati (DLP) &amp; nel centro sicurezza e conformità include numerosi tipi di informazioni riservate pronte per l'uso nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-105">Data loss prevention (DLP) in the Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="ecdf4-106">In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="ecdf4-107">Una tipologia di informazioni riservate viene definita da un modello identificato da un'espressione regolare o da una funzione.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="ecdf4-108">Inoltre, è possibile utilizzare elementi probatori, ad esempio, parole chiave e checksum per identificare una tipologia di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="ecdf4-109">In questa procedura di valutazione vengono usati anche il livello di probabilità e la prossimità.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="ecdf4-110">Numero di registrazione ABA</span><span class="sxs-lookup"><span data-stu-id="ecdf4-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-111">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-111">Format</span></span>

<span data-ttu-id="ecdf4-112">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-113">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-113">Pattern</span></span>

<span data-ttu-id="ecdf4-114">Formattato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-114">Formatted:</span></span>
- <span data-ttu-id="ecdf4-115">Quattro cifre che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="ecdf4-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="ecdf4-116">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-116">A hyphen</span></span>
- <span data-ttu-id="ecdf4-117">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-117">Four digits</span></span>
- <span data-ttu-id="ecdf4-118">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-118">A hyphen</span></span>
- <span data-ttu-id="ecdf4-119">Una cifra</span><span class="sxs-lookup"><span data-stu-id="ecdf4-119">A digit</span></span>

<span data-ttu-id="ecdf4-120">Non formattato: 9 cifre consecutive che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="ecdf4-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="ecdf4-121">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-121">Checksum</span></span>

<span data-ttu-id="ecdf4-122">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-123">Definition</span></span>

<span data-ttu-id="ecdf4-124">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-125">La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-126">Viene trovata una parola chiave da Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="ecdf4-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="ecdf4-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="ecdf4-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="ecdf4-129">ABA</span><span class="sxs-lookup"><span data-stu-id="ecdf4-129">aba</span></span>
- <span data-ttu-id="ecdf4-130">aba #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-130">aba #</span></span>
- <span data-ttu-id="ecdf4-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-131">aba routing #</span></span>
- <span data-ttu-id="ecdf4-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-132">aba routing number</span></span>
- <span data-ttu-id="ecdf4-133">ABA #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-133">aba#</span></span>
- <span data-ttu-id="ecdf4-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-134">abarouting#</span></span>
- <span data-ttu-id="ecdf4-135">aba number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-135">aba number</span></span>
- <span data-ttu-id="ecdf4-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-136">abaroutingnumber</span></span>
- <span data-ttu-id="ecdf4-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-137">american bank association routing #</span></span>
- <span data-ttu-id="ecdf4-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-138">american bank association routing number</span></span>
- <span data-ttu-id="ecdf4-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="ecdf4-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="ecdf4-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-141">bank routing number</span></span>
- <span data-ttu-id="ecdf4-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-142">bankrouting#</span></span>
- <span data-ttu-id="ecdf4-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-143">bankroutingnumber</span></span>
- <span data-ttu-id="ecdf4-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-144">routing transit number</span></span>
- <span data-ttu-id="ecdf4-145">RTN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="ecdf4-146">Argentina - Numero di identità nazionale (DNI)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-147">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-147">Format</span></span>

<span data-ttu-id="ecdf4-148">Otto cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="ecdf4-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-149">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-149">Pattern</span></span>

<span data-ttu-id="ecdf4-150">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-150">Eight digits:</span></span>
- <span data-ttu-id="ecdf4-151">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-151">Two digits</span></span>
- <span data-ttu-id="ecdf4-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="ecdf4-152">A period</span></span>
- <span data-ttu-id="ecdf4-153">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-153">Three digits</span></span>
- <span data-ttu-id="ecdf4-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="ecdf4-154">A period</span></span>
- <span data-ttu-id="ecdf4-155">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-156">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-156">Checksum</span></span>

<span data-ttu-id="ecdf4-157">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-158">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-158">Definition</span></span>

<span data-ttu-id="ecdf4-159">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-160">L'espressione regolare Regex_argentina_national_id trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-161">Viene trovata una parola chiave da Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-162">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="ecdf4-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="ecdf4-164">Argentina - Numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="ecdf4-165">Identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-165">Identity</span></span> 
- <span data-ttu-id="ecdf4-166">Carta di identità nazionale di identificazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="ecdf4-167">DNI</span><span class="sxs-lookup"><span data-stu-id="ecdf4-167">DNI</span></span> 
- <span data-ttu-id="ecdf4-168">Registro nazionale delle persone di NIC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="ecdf4-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="ecdf4-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="ecdf4-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="ecdf4-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="ecdf4-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="ecdf4-171">Identidad</span></span> 
- <span data-ttu-id="ecdf4-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="ecdf4-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="ecdf4-173">Australia - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="ecdf4-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-174">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-174">Format</span></span>

<span data-ttu-id="ecdf4-175">6-10 cifre con o senza un numero BSB (Bank/State/Branch)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-176">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-176">Pattern</span></span>

<span data-ttu-id="ecdf4-177">Il numero di conto comprende 6-10 cifre.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="ecdf4-178">Numero BSB australiano:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="ecdf4-179">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-179">Three digits</span></span> 
- <span data-ttu-id="ecdf4-180">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-180">A hyphen</span></span> 
- <span data-ttu-id="ecdf4-181">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-182">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-182">Checksum</span></span>

<span data-ttu-id="ecdf4-183">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-184">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-184">Definition</span></span>

<span data-ttu-id="ecdf4-185">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-186">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="ecdf4-187">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="ecdf4-188">L'espressione regolare Regex_australia_bank_account_number_bsb restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="ecdf4-189">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-190">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="ecdf4-191">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-192">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="ecdf4-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="ecdf4-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="ecdf4-194">swift bank code</span></span>
- <span data-ttu-id="ecdf4-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="ecdf4-195">correspondent bank</span></span>
- <span data-ttu-id="ecdf4-196">base currency</span><span class="sxs-lookup"><span data-stu-id="ecdf4-196">base currency</span></span>
- <span data-ttu-id="ecdf4-197">usa account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-197">usa account</span></span>
- <span data-ttu-id="ecdf4-198">holder address</span><span class="sxs-lookup"><span data-stu-id="ecdf4-198">holder address</span></span>
- <span data-ttu-id="ecdf4-199">bank address</span><span class="sxs-lookup"><span data-stu-id="ecdf4-199">bank address</span></span>
- <span data-ttu-id="ecdf4-200">information account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-200">information account</span></span>
- <span data-ttu-id="ecdf4-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-201">fund transfers</span></span>
- <span data-ttu-id="ecdf4-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="ecdf4-202">bank charges</span></span>
- <span data-ttu-id="ecdf4-203">bank details</span><span class="sxs-lookup"><span data-stu-id="ecdf4-203">bank details</span></span>
- <span data-ttu-id="ecdf4-204">banking information</span><span class="sxs-lookup"><span data-stu-id="ecdf4-204">banking information</span></span>
- <span data-ttu-id="ecdf4-205">full names</span><span class="sxs-lookup"><span data-stu-id="ecdf4-205">full names</span></span>
- <span data-ttu-id="ecdf4-206">AIEA</span><span class="sxs-lookup"><span data-stu-id="ecdf4-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="ecdf4-207">Australia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="ecdf4-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-208">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-208">Format</span></span>

<span data-ttu-id="ecdf4-209">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="ecdf4-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-210">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-210">Pattern</span></span>

<span data-ttu-id="ecdf4-211">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="ecdf4-212">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-213">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-213">Two digits</span></span> 
- <span data-ttu-id="ecdf4-214">Cinque cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="ecdf4-215">OPPURE</span><span class="sxs-lookup"><span data-stu-id="ecdf4-215">OR</span></span>

- <span data-ttu-id="ecdf4-216">1-2 lettere facoltative (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-217">4-9 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-217">4-9 digits</span></span>

<span data-ttu-id="ecdf4-218">OPPURE</span><span class="sxs-lookup"><span data-stu-id="ecdf4-218">OR</span></span>

- <span data-ttu-id="ecdf4-219">Nove cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-220">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-220">Checksum</span></span>

<span data-ttu-id="ecdf4-221">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-222">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-222">Definition</span></span>

<span data-ttu-id="ecdf4-223">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-224">L'espressione regolare Regex_australia_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-225">Viene trovata una parola chiave da Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="ecdf4-226">Non vengono trovate parole chiava da Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="ecdf4-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="ecdf4-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="ecdf4-229">international driving permits</span></span>
- <span data-ttu-id="ecdf4-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="ecdf4-230">australian automobile association</span></span>
- <span data-ttu-id="ecdf4-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-231">international driving permit</span></span>
- <span data-ttu-id="ecdf4-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-232">DriverLicence</span></span>
- <span data-ttu-id="ecdf4-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-233">DriverLicences</span></span>
- <span data-ttu-id="ecdf4-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-234">Driver Lic</span></span>
- <span data-ttu-id="ecdf4-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-235">Driver Licence</span></span>
- <span data-ttu-id="ecdf4-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-236">Driver Licences</span></span>
- <span data-ttu-id="ecdf4-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-237">DriversLic</span></span>
- <span data-ttu-id="ecdf4-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-238">DriversLicence</span></span>
- <span data-ttu-id="ecdf4-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-239">DriversLicences</span></span>
- <span data-ttu-id="ecdf4-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-240">Drivers Lic</span></span>
- <span data-ttu-id="ecdf4-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-241">Drivers Lics</span></span>
- <span data-ttu-id="ecdf4-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-242">Drivers Licence</span></span>
- <span data-ttu-id="ecdf4-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-243">Drivers Licences</span></span>
- <span data-ttu-id="ecdf4-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-244">Driver'Lic</span></span>
- <span data-ttu-id="ecdf4-245">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-245">Driver'Lics</span></span>
- <span data-ttu-id="ecdf4-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-246">Driver'Licence</span></span>
- <span data-ttu-id="ecdf4-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-247">Driver'Licences</span></span>
- <span data-ttu-id="ecdf4-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-248">Driver' Lic</span></span>
- <span data-ttu-id="ecdf4-249">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-249">Driver' Lics</span></span>
- <span data-ttu-id="ecdf4-250">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-250">Driver' Licence</span></span>
- <span data-ttu-id="ecdf4-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-251">Driver' Licences</span></span>
- <span data-ttu-id="ecdf4-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-252">Driver'sLic</span></span>
- <span data-ttu-id="ecdf4-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-253">Driver'sLics</span></span>
- <span data-ttu-id="ecdf4-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-254">Driver'sLicence</span></span>
- <span data-ttu-id="ecdf4-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-255">Driver'sLicences</span></span>
- <span data-ttu-id="ecdf4-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-256">Driver's Lic</span></span>
- <span data-ttu-id="ecdf4-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-257">Driver's Lics</span></span>
- <span data-ttu-id="ecdf4-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-258">Driver's Licence</span></span>
- <span data-ttu-id="ecdf4-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-259">Driver's Licences</span></span>
- <span data-ttu-id="ecdf4-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-260">DriverLic#</span></span>
- <span data-ttu-id="ecdf4-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-261">DriverLics#</span></span>
- <span data-ttu-id="ecdf4-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-262">DriverLicence#</span></span>
- <span data-ttu-id="ecdf4-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-263">DriverLicences#</span></span>
- <span data-ttu-id="ecdf4-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-264">Driver Lic#</span></span>
- <span data-ttu-id="ecdf4-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-265">Driver Lics#</span></span>
- <span data-ttu-id="ecdf4-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-266">Driver Licence#</span></span>
- <span data-ttu-id="ecdf4-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-267">Driver Licences#</span></span>
- <span data-ttu-id="ecdf4-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-268">DriversLic#</span></span>
- <span data-ttu-id="ecdf4-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-269">DriversLics#</span></span>
- <span data-ttu-id="ecdf4-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-270">DriversLicence#</span></span>
- <span data-ttu-id="ecdf4-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-271">DriversLicences#</span></span>
- <span data-ttu-id="ecdf4-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-272">Drivers Lic#</span></span>
- <span data-ttu-id="ecdf4-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-273">Drivers Lics#</span></span>
- <span data-ttu-id="ecdf4-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-274">Drivers Licence#</span></span>
- <span data-ttu-id="ecdf4-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-275">Drivers Licences#</span></span>
- <span data-ttu-id="ecdf4-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-276">Driver'Lic#</span></span>
- <span data-ttu-id="ecdf4-277">Driver ' LiCS #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-277">Driver'Lics#</span></span>
- <span data-ttu-id="ecdf4-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-278">Driver'Licence#</span></span>
- <span data-ttu-id="ecdf4-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-279">Driver'Licences#</span></span>
- <span data-ttu-id="ecdf4-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-280">Driver' Lic#</span></span>
- <span data-ttu-id="ecdf4-281">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-281">Driver' Lics#</span></span>
- <span data-ttu-id="ecdf4-282">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-282">Driver' Licence#</span></span>
- <span data-ttu-id="ecdf4-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-283">Driver' Licences#</span></span>
- <span data-ttu-id="ecdf4-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-284">Driver'sLic#</span></span>
- <span data-ttu-id="ecdf4-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-285">Driver'sLics#</span></span>
- <span data-ttu-id="ecdf4-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-286">Driver'sLicence#</span></span>
- <span data-ttu-id="ecdf4-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-287">Driver'sLicences#</span></span>
- <span data-ttu-id="ecdf4-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-288">Driver's Lic#</span></span>
- <span data-ttu-id="ecdf4-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-289">Driver's Lics#</span></span>
- <span data-ttu-id="ecdf4-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-290">Driver's Licence#</span></span>
- <span data-ttu-id="ecdf4-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="ecdf4-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="ecdf4-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="ecdf4-293">AAA</span><span class="sxs-lookup"><span data-stu-id="ecdf4-293">aaa</span></span>
- <span data-ttu-id="ecdf4-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="ecdf4-294">DriverLicense</span></span>
- <span data-ttu-id="ecdf4-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-295">DriverLicenses</span></span>
- <span data-ttu-id="ecdf4-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-296">Driver License</span></span>
- <span data-ttu-id="ecdf4-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-297">Driver Licenses</span></span>
- <span data-ttu-id="ecdf4-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="ecdf4-298">DriversLicense</span></span>
- <span data-ttu-id="ecdf4-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-299">DriversLicenses</span></span>
- <span data-ttu-id="ecdf4-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-300">Drivers License</span></span>
- <span data-ttu-id="ecdf4-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-301">Drivers Licenses</span></span>
- <span data-ttu-id="ecdf4-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-302">Driver'License</span></span>
- <span data-ttu-id="ecdf4-303">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-303">Driver'Licenses</span></span>
- <span data-ttu-id="ecdf4-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-304">Driver' License</span></span>
- <span data-ttu-id="ecdf4-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-305">Driver' Licenses</span></span>
- <span data-ttu-id="ecdf4-306">Secondola</span><span class="sxs-lookup"><span data-stu-id="ecdf4-306">Driver'sLicense</span></span>
- <span data-ttu-id="ecdf4-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-307">Driver'sLicenses</span></span>
- <span data-ttu-id="ecdf4-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-308">Driver's License</span></span>
- <span data-ttu-id="ecdf4-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-309">Driver's Licenses</span></span>
- <span data-ttu-id="ecdf4-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-310">DriverLicense#</span></span>
- <span data-ttu-id="ecdf4-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-311">DriverLicenses#</span></span>
- <span data-ttu-id="ecdf4-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-312">Driver License#</span></span>
- <span data-ttu-id="ecdf4-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-313">Driver Licenses#</span></span>
- <span data-ttu-id="ecdf4-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-314">DriversLicense#</span></span>
- <span data-ttu-id="ecdf4-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-315">DriversLicenses#</span></span>
- <span data-ttu-id="ecdf4-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-316">Drivers License#</span></span>
- <span data-ttu-id="ecdf4-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-317">Drivers Licenses#</span></span>
- <span data-ttu-id="ecdf4-318">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-318">Driver'License#</span></span>
- <span data-ttu-id="ecdf4-319">Driver ' licenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-319">Driver'Licenses#</span></span>
- <span data-ttu-id="ecdf4-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-320">Driver' License#</span></span>
- <span data-ttu-id="ecdf4-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-321">Driver' Licenses#</span></span>
- <span data-ttu-id="ecdf4-322">Secondola #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-322">Driver'sLicense#</span></span>
- <span data-ttu-id="ecdf4-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="ecdf4-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-324">Driver's License#</span></span>
- <span data-ttu-id="ecdf4-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="ecdf4-326">Australia - Numero di tessera sanitaria</span><span class="sxs-lookup"><span data-stu-id="ecdf4-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-327">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-327">Format</span></span>

<span data-ttu-id="ecdf4-328">10-11 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-329">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-329">Pattern</span></span>

<span data-ttu-id="ecdf4-330">10-11 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-330">10-11 digits:</span></span>
- <span data-ttu-id="ecdf4-331">La prima cifra è compresa nell'intervallo 2-6</span><span class="sxs-lookup"><span data-stu-id="ecdf4-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="ecdf4-332">La nona cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="ecdf4-333">La decima cifra è la cifra del problema</span><span class="sxs-lookup"><span data-stu-id="ecdf4-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="ecdf4-334">L'undicesima cifra (facoltativa) è il numero singolo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-335">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-335">Checksum</span></span>

<span data-ttu-id="ecdf4-336">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-337">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-337">Definition</span></span>

<span data-ttu-id="ecdf4-338">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-339">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-340">Viene trovata una parola chiave da Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="ecdf4-341">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-341">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-342">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-343">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-344">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-344">The checksum passes.</span></span>

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-345">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="ecdf4-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="ecdf4-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="ecdf4-347">bank account details</span></span>
- <span data-ttu-id="ecdf4-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="ecdf4-348">medicare payments</span></span>
- <span data-ttu-id="ecdf4-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-349">mortgage account</span></span>
- <span data-ttu-id="ecdf4-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="ecdf4-350">bank payments</span></span>
- <span data-ttu-id="ecdf4-351">information branch</span><span class="sxs-lookup"><span data-stu-id="ecdf4-351">information branch</span></span>
- <span data-ttu-id="ecdf4-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="ecdf4-352">credit card loan</span></span>
- <span data-ttu-id="ecdf4-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="ecdf4-353">department of human services</span></span>
- <span data-ttu-id="ecdf4-354">local service</span><span class="sxs-lookup"><span data-stu-id="ecdf4-354">local service</span></span>
- <span data-ttu-id="ecdf4-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="ecdf4-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="ecdf4-356">Australia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-357">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-357">Format</span></span>

<span data-ttu-id="ecdf4-358">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-359">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-359">Pattern</span></span>

<span data-ttu-id="ecdf4-360">Una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-361">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-361">Checksum</span></span>

<span data-ttu-id="ecdf4-362">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-363">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-363">Definition</span></span>

<span data-ttu-id="ecdf4-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-365">L'espressione regolare Regex_australia_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-366">Viene trovata una parola chiave da Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-367">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="ecdf4-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-368">Keyword_passport</span></span>

- <span data-ttu-id="ecdf4-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-369">Passport Number</span></span>
- <span data-ttu-id="ecdf4-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-370">Passport No</span></span>
- <span data-ttu-id="ecdf4-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-371">Passport #</span></span>
- <span data-ttu-id="ecdf4-372">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-372">Passport#</span></span>
- <span data-ttu-id="ecdf4-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-373">PassportID</span></span>
- <span data-ttu-id="ecdf4-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-374">Passportno</span></span>
- <span data-ttu-id="ecdf4-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-375">passportnumber</span></span>
- <span data-ttu-id="ecdf4-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="ecdf4-376">パスポート</span></span>
- <span data-ttu-id="ecdf4-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-377">パスポート番号</span></span>
- <span data-ttu-id="ecdf4-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-378">パスポートのNum</span></span>
- <span data-ttu-id="ecdf4-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-379">パスポート ＃</span></span> 
- <span data-ttu-id="ecdf4-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-380">Numéro de passeport</span></span>
- <span data-ttu-id="ecdf4-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="ecdf4-381">Passeport n °</span></span>
- <span data-ttu-id="ecdf4-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="ecdf4-382">Passeport Non</span></span>
- <span data-ttu-id="ecdf4-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-383">Passeport #</span></span>
- <span data-ttu-id="ecdf4-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-384">Passeport#</span></span>
- <span data-ttu-id="ecdf4-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="ecdf4-385">PasseportNon</span></span>
- <span data-ttu-id="ecdf4-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="ecdf4-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="ecdf4-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="ecdf4-388">passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-388">passport</span></span>
- <span data-ttu-id="ecdf4-389">passport details</span><span class="sxs-lookup"><span data-stu-id="ecdf4-389">passport details</span></span>
- <span data-ttu-id="ecdf4-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="ecdf4-390">immigration and citizenship</span></span>
- <span data-ttu-id="ecdf4-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="ecdf4-391">commonwealth of australia</span></span>
- <span data-ttu-id="ecdf4-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="ecdf4-392">department of immigration</span></span>
- <span data-ttu-id="ecdf4-393">residential address</span><span class="sxs-lookup"><span data-stu-id="ecdf4-393">residential address</span></span>
- <span data-ttu-id="ecdf4-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="ecdf4-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="ecdf4-395">esempio</span><span class="sxs-lookup"><span data-stu-id="ecdf4-395">visa</span></span>
- <span data-ttu-id="ecdf4-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-396">national identity card</span></span>
- <span data-ttu-id="ecdf4-397">passport number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-397">passport number</span></span>
- <span data-ttu-id="ecdf4-398">travel document</span><span class="sxs-lookup"><span data-stu-id="ecdf4-398">travel document</span></span>
- <span data-ttu-id="ecdf4-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="ecdf4-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="ecdf4-400">Australia - Identificativo fiscale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-401">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-401">Format</span></span>

<span data-ttu-id="ecdf4-402">8-9 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-403">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-403">Pattern</span></span>

<span data-ttu-id="ecdf4-404">8-9 cifre in genere presentate con spazi, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="ecdf4-405">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-405">Three digits</span></span> 
- <span data-ttu-id="ecdf4-406">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-406">An optional space</span></span> 
- <span data-ttu-id="ecdf4-407">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-407">Three digits</span></span> 
- <span data-ttu-id="ecdf4-408">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-408">An optional space</span></span> 
- <span data-ttu-id="ecdf4-409">2-3 cifre e l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-410">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-410">Checksum</span></span>

<span data-ttu-id="ecdf4-411">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-412">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-412">Definition</span></span>

<span data-ttu-id="ecdf4-413">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-414">La funzione Func_australian_tax_file_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-415">Non vengono trovate parole chiave da Keyword_Australia_Tax_File_Number o da Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="ecdf4-416">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="ecdf4-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="ecdf4-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-419">australian business number</span></span>
- <span data-ttu-id="ecdf4-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="ecdf4-420">marginal tax rate</span></span>
- <span data-ttu-id="ecdf4-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="ecdf4-421">medicare levy</span></span>
- <span data-ttu-id="ecdf4-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-422">portfolio number</span></span>
- <span data-ttu-id="ecdf4-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="ecdf4-423">service veterans</span></span>
- <span data-ttu-id="ecdf4-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="ecdf4-424">withholding tax</span></span>
- <span data-ttu-id="ecdf4-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="ecdf4-425">individual tax return</span></span>
- <span data-ttu-id="ecdf4-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="ecdf4-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="ecdf4-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="ecdf4-428">00000000</span><span class="sxs-lookup"><span data-stu-id="ecdf4-428">00000000</span></span>
- <span data-ttu-id="ecdf4-429">11111111</span><span class="sxs-lookup"><span data-stu-id="ecdf4-429">11111111</span></span>
- <span data-ttu-id="ecdf4-430">22222222</span><span class="sxs-lookup"><span data-stu-id="ecdf4-430">22222222</span></span>
- <span data-ttu-id="ecdf4-431">33333333</span><span class="sxs-lookup"><span data-stu-id="ecdf4-431">33333333</span></span>
- <span data-ttu-id="ecdf4-432">44444444</span><span class="sxs-lookup"><span data-stu-id="ecdf4-432">44444444</span></span>
- <span data-ttu-id="ecdf4-433">55555555</span><span class="sxs-lookup"><span data-stu-id="ecdf4-433">55555555</span></span>
- <span data-ttu-id="ecdf4-434">66666666</span><span class="sxs-lookup"><span data-stu-id="ecdf4-434">66666666</span></span>
- <span data-ttu-id="ecdf4-435">77777777</span><span class="sxs-lookup"><span data-stu-id="ecdf4-435">77777777</span></span>
- <span data-ttu-id="ecdf4-436">88888888</span><span class="sxs-lookup"><span data-stu-id="ecdf4-436">88888888</span></span>
- <span data-ttu-id="ecdf4-437">99999999</span><span class="sxs-lookup"><span data-stu-id="ecdf4-437">99999999</span></span>
- <span data-ttu-id="ecdf4-438">000000000</span><span class="sxs-lookup"><span data-stu-id="ecdf4-438">000000000</span></span>
- <span data-ttu-id="ecdf4-439">111111111</span><span class="sxs-lookup"><span data-stu-id="ecdf4-439">111111111</span></span>
- <span data-ttu-id="ecdf4-440">222222222</span><span class="sxs-lookup"><span data-stu-id="ecdf4-440">222222222</span></span>
- <span data-ttu-id="ecdf4-441">333333333</span><span class="sxs-lookup"><span data-stu-id="ecdf4-441">333333333</span></span>
- <span data-ttu-id="ecdf4-442">444444444</span><span class="sxs-lookup"><span data-stu-id="ecdf4-442">444444444</span></span>
- <span data-ttu-id="ecdf4-443">555555555</span><span class="sxs-lookup"><span data-stu-id="ecdf4-443">555555555</span></span>
- <span data-ttu-id="ecdf4-444">666666666</span><span class="sxs-lookup"><span data-stu-id="ecdf4-444">666666666</span></span>
- <span data-ttu-id="ecdf4-445">777777777</span><span class="sxs-lookup"><span data-stu-id="ecdf4-445">777777777</span></span>
- <span data-ttu-id="ecdf4-446">888888888</span><span class="sxs-lookup"><span data-stu-id="ecdf4-446">888888888</span></span>
- <span data-ttu-id="ecdf4-447">999999999</span><span class="sxs-lookup"><span data-stu-id="ecdf4-447">999999999</span></span>
- <span data-ttu-id="ecdf4-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="ecdf4-448">0000000000</span></span>
- <span data-ttu-id="ecdf4-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="ecdf4-449">1111111111</span></span>
- <span data-ttu-id="ecdf4-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="ecdf4-450">2222222222</span></span>
- <span data-ttu-id="ecdf4-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="ecdf4-451">3333333333</span></span>
- <span data-ttu-id="ecdf4-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="ecdf4-452">4444444444</span></span>
- <span data-ttu-id="ecdf4-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="ecdf4-453">5555555555</span></span>
- <span data-ttu-id="ecdf4-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="ecdf4-454">6666666666</span></span>
- <span data-ttu-id="ecdf4-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="ecdf4-455">7777777777</span></span>
- <span data-ttu-id="ecdf4-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="ecdf4-456">8888888888</span></span>
- <span data-ttu-id="ecdf4-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="ecdf4-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="ecdf4-458">Chiave di autenticazione di DocumentDB di Azure</span><span class="sxs-lookup"><span data-stu-id="ecdf4-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-459">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-459">Format</span></span>

<span data-ttu-id="ecdf4-460">La stringa "DocumentDb" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-461">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-461">Pattern</span></span>

- <span data-ttu-id="ecdf4-462">La stringa "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="ecdf4-463">Qualsiasi combinazione tra 3-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ecdf4-464">Un simbolo maggiore di (>), un segno di uguale (=), un segno di virgolette (") oppure un apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="ecdf4-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="ecdf4-465">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ecdf4-466">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-467">Checksum</span></span>

<span data-ttu-id="ecdf4-468">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-469">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-469">Definition</span></span>

<span data-ttu-id="ecdf4-470">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-471">L'espressione regolare CEP_Regex_AzureDocumentDBAuthKey trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-472">L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-473">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ecdf4-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ecdf4-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ecdf4-475">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ecdf4-476">contoso</span><span class="sxs-lookup"><span data-stu-id="ecdf4-476">contoso</span></span>
- <span data-ttu-id="ecdf4-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="ecdf4-477">fabrikam</span></span>
- <span data-ttu-id="ecdf4-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="ecdf4-478">northwind</span></span>
- <span data-ttu-id="ecdf4-479">sandbox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-479">sandbox</span></span>
- <span data-ttu-id="ecdf4-480">OneBox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-480">onebox</span></span>
- <span data-ttu-id="ecdf4-481">localhost</span><span class="sxs-lookup"><span data-stu-id="ecdf4-481">localhost</span></span>
- <span data-ttu-id="ecdf4-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ecdf4-482">127.0.0.1</span></span>
- <span data-ttu-id="ecdf4-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-484">com</span><span class="sxs-lookup"><span data-stu-id="ecdf4-484">com</span></span>
- <span data-ttu-id="ecdf4-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-486">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="ecdf4-487">Stringa di connessione del database di Azure IAAS e stringa di connessione SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="ecdf4-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-488">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-488">Format</span></span>

<span data-ttu-id="ecdf4-489">Stringa "Server", "Server" o "Data Source" seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-490">com "o" cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-491">NET "o" database. Windows.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-492">NET "e la stringa" password "o" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="ecdf4-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-493">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-493">Pattern</span></span>

- <span data-ttu-id="ecdf4-494">La stringa "Server", "Server" o "Data Source"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="ecdf4-495">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-496">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-496">An equal sign (=)</span></span>
- <span data-ttu-id="ecdf4-497">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-498">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ecdf4-499">La stringa "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-500">com "," cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-501">NET "o" database. Windows.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-502">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-502">net"</span></span>
- <span data-ttu-id="ecdf4-503">Qualsiasi combinazione tra 1-300 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ecdf4-504">La stringa "password", "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="ecdf4-505">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-506">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-506">An equal sign (=)</span></span>
- <span data-ttu-id="ecdf4-507">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-508">Uno o più caratteri non costituiti da un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="ecdf4-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="ecdf4-509">Un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="ecdf4-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-510">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-510">Checksum</span></span>

<span data-ttu-id="ecdf4-511">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-512">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-512">Definition</span></span>

<span data-ttu-id="ecdf4-513">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-514">L'espressione regolare CEP_Regex_AzureConnectionString trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-515">L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-516">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ecdf4-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ecdf4-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ecdf4-518">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ecdf4-519">contoso</span><span class="sxs-lookup"><span data-stu-id="ecdf4-519">contoso</span></span>
- <span data-ttu-id="ecdf4-520">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="ecdf4-520">fabrikam</span></span>
- <span data-ttu-id="ecdf4-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="ecdf4-521">northwind</span></span>
- <span data-ttu-id="ecdf4-522">sandbox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-522">sandbox</span></span>
- <span data-ttu-id="ecdf4-523">OneBox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-523">onebox</span></span>
- <span data-ttu-id="ecdf4-524">localhost</span><span class="sxs-lookup"><span data-stu-id="ecdf4-524">localhost</span></span>
- <span data-ttu-id="ecdf4-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ecdf4-525">127.0.0.1</span></span>
- <span data-ttu-id="ecdf4-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-527">com</span><span class="sxs-lookup"><span data-stu-id="ecdf4-527">com</span></span>
- <span data-ttu-id="ecdf4-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-529">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="ecdf4-530">Stringa di connessione di Azure.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-531">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-531">Format</span></span>

<span data-ttu-id="ecdf4-532">La stringa "HostName" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-533">NET "e" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="ecdf4-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-534">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-534">Pattern</span></span>

- <span data-ttu-id="ecdf4-535">La stringa "HostName"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-535">The string "HostName"</span></span>
- <span data-ttu-id="ecdf4-536">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-537">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-537">An equal sign (=)</span></span>
- <span data-ttu-id="ecdf4-538">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-539">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ecdf4-540">La stringa "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-541">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-541">net"</span></span>
- <span data-ttu-id="ecdf4-542">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ecdf4-543">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="ecdf4-544">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-545">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-545">An equal sign (=)</span></span>
- <span data-ttu-id="ecdf4-546">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-547">Qualsiasi combinazione di 43 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ecdf4-548">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-549">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-549">Checksum</span></span>

<span data-ttu-id="ecdf4-550">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-551">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-551">Definition</span></span>

<span data-ttu-id="ecdf4-552">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-553">L'espressione regolare CEP_Regex_AzureIoTConnectionString trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-554">L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-555">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ecdf4-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ecdf4-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ecdf4-557">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ecdf4-558">contoso</span><span class="sxs-lookup"><span data-stu-id="ecdf4-558">contoso</span></span>
- <span data-ttu-id="ecdf4-559">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="ecdf4-559">fabrikam</span></span>
- <span data-ttu-id="ecdf4-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="ecdf4-560">northwind</span></span>
- <span data-ttu-id="ecdf4-561">sandbox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-561">sandbox</span></span>
- <span data-ttu-id="ecdf4-562">OneBox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-562">onebox</span></span>
- <span data-ttu-id="ecdf4-563">localhost</span><span class="sxs-lookup"><span data-stu-id="ecdf4-563">localhost</span></span>
- <span data-ttu-id="ecdf4-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ecdf4-564">127.0.0.1</span></span>
- <span data-ttu-id="ecdf4-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-566">com</span><span class="sxs-lookup"><span data-stu-id="ecdf4-566">com</span></span>
- <span data-ttu-id="ecdf4-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-568">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="ecdf4-569">Password per l'impostazione di pubblicazione di Azure</span><span class="sxs-lookup"><span data-stu-id="ecdf4-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-570">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-570">Format</span></span>

<span data-ttu-id="ecdf4-571">La stringa "UserPwd =" seguita da una stringa alfanumerica.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-572">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-572">Pattern</span></span>

- <span data-ttu-id="ecdf4-573">La stringa "UserPwd ="</span><span class="sxs-lookup"><span data-stu-id="ecdf4-573">The string "userpwd="</span></span>
- <span data-ttu-id="ecdf4-574">Qualsiasi combinazione di lettere o cifre minuscole di 60</span><span class="sxs-lookup"><span data-stu-id="ecdf4-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="ecdf4-575">Virgolette (")</span><span class="sxs-lookup"><span data-stu-id="ecdf4-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-576">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-576">Checksum</span></span>

<span data-ttu-id="ecdf4-577">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-578">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-578">Definition</span></span>

<span data-ttu-id="ecdf4-579">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-580">L'espressione regolare CEP_Regex_AzurePublishSettingPasswords trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-581">L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-582">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ecdf4-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ecdf4-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ecdf4-584">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ecdf4-585">contoso</span><span class="sxs-lookup"><span data-stu-id="ecdf4-585">contoso</span></span>
- <span data-ttu-id="ecdf4-586">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="ecdf4-586">fabrikam</span></span>
- <span data-ttu-id="ecdf4-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="ecdf4-587">northwind</span></span>
- <span data-ttu-id="ecdf4-588">sandbox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-588">sandbox</span></span>
- <span data-ttu-id="ecdf4-589">OneBox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-589">onebox</span></span>
- <span data-ttu-id="ecdf4-590">localhost</span><span class="sxs-lookup"><span data-stu-id="ecdf4-590">localhost</span></span>
- <span data-ttu-id="ecdf4-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ecdf4-591">127.0.0.1</span></span>
- <span data-ttu-id="ecdf4-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-593">com</span><span class="sxs-lookup"><span data-stu-id="ecdf4-593">com</span></span>
- <span data-ttu-id="ecdf4-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-595">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="ecdf4-596">Stringa di connessione della cache di Azure Redis</span><span class="sxs-lookup"><span data-stu-id="ecdf4-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-597">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-597">Format</span></span>

<span data-ttu-id="ecdf4-598">La stringa "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-599">NET "seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="ecdf4-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-600">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-600">Pattern</span></span>

- <span data-ttu-id="ecdf4-601">La stringa "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-602">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-602">net"</span></span>
- <span data-ttu-id="ecdf4-603">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ecdf4-604">La stringa "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="ecdf4-605">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-606">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-606">An equal sign (=)</span></span>
- <span data-ttu-id="ecdf4-607">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-608">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ecdf4-609">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-610">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-610">Checksum</span></span>

<span data-ttu-id="ecdf4-611">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-612">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-612">Definition</span></span>

<span data-ttu-id="ecdf4-613">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-614">L'espressione regolare CEP_Regex_AzureRedisCacheConnectionString trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="ecdf4-615">L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-616">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ecdf4-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ecdf4-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ecdf4-618">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ecdf4-619">contoso</span><span class="sxs-lookup"><span data-stu-id="ecdf4-619">contoso</span></span>
- <span data-ttu-id="ecdf4-620">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="ecdf4-620">fabrikam</span></span>
- <span data-ttu-id="ecdf4-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="ecdf4-621">northwind</span></span>
- <span data-ttu-id="ecdf4-622">sandbox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-622">sandbox</span></span>
- <span data-ttu-id="ecdf4-623">OneBox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-623">onebox</span></span>
- <span data-ttu-id="ecdf4-624">localhost</span><span class="sxs-lookup"><span data-stu-id="ecdf4-624">localhost</span></span>
- <span data-ttu-id="ecdf4-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ecdf4-625">127.0.0.1</span></span>
- <span data-ttu-id="ecdf4-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-627">com</span><span class="sxs-lookup"><span data-stu-id="ecdf4-627">com</span></span>
- <span data-ttu-id="ecdf4-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-629">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="ecdf4-630">SAS di Azure</span><span class="sxs-lookup"><span data-stu-id="ecdf4-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-631">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-631">Format</span></span>

<span data-ttu-id="ecdf4-632">La stringa "sig" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-633">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-633">Pattern</span></span>

- <span data-ttu-id="ecdf4-634">La stringa "sig"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-634">The string "sig"</span></span>
- <span data-ttu-id="ecdf4-635">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-636">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-636">An equal sign (=)</span></span>
- <span data-ttu-id="ecdf4-637">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-638">Qualsiasi combinazione tra 43-53 caratteri che sono minuscoli o maiuscoli, cifre o il segno di percentuale (%)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="ecdf4-639">La stringa "% 3D"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-639">The string "%3d"</span></span>
- <span data-ttu-id="ecdf4-640">Qualsiasi carattere che non sia una lettera, una cifra o un segno di percentuale inferiore o maiuscolo (%)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-641">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-641">Checksum</span></span>

<span data-ttu-id="ecdf4-642">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-643">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-643">Definition</span></span>

<span data-ttu-id="ecdf4-644">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-645">L'espressione regolare CEP_Regex_AzureSAS trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="ecdf4-646">Stringa di connessione bus di servizio di Azure</span><span class="sxs-lookup"><span data-stu-id="ecdf4-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-647">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-647">Format</span></span>

<span data-ttu-id="ecdf4-648">Stringa "EndPoint" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-649">NET "e" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="ecdf4-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-650">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-650">Pattern</span></span>

- <span data-ttu-id="ecdf4-651">La stringa "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-651">The string "EndPoint"</span></span>
- <span data-ttu-id="ecdf4-652">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-653">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-653">An equal sign (=)</span></span>
- <span data-ttu-id="ecdf4-654">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-655">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ecdf4-656">La stringa "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-657">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-657">net"</span></span>
- <span data-ttu-id="ecdf4-658">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ecdf4-659">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="ecdf4-660">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-661">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-661">An equal sign (=)</span></span>
- <span data-ttu-id="ecdf4-662">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-663">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ecdf4-664">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-665">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-665">Checksum</span></span>

<span data-ttu-id="ecdf4-666">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-667">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-667">Definition</span></span>

<span data-ttu-id="ecdf4-668">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-669">L'espressione regolare CEP_Regex_AzureServiceBusConnectionString trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="ecdf4-670">L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-671">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ecdf4-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ecdf4-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ecdf4-673">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ecdf4-674">contoso</span><span class="sxs-lookup"><span data-stu-id="ecdf4-674">contoso</span></span>
- <span data-ttu-id="ecdf4-675">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="ecdf4-675">fabrikam</span></span>
- <span data-ttu-id="ecdf4-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="ecdf4-676">northwind</span></span>
- <span data-ttu-id="ecdf4-677">sandbox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-677">sandbox</span></span>
- <span data-ttu-id="ecdf4-678">OneBox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-678">onebox</span></span>
- <span data-ttu-id="ecdf4-679">localhost</span><span class="sxs-lookup"><span data-stu-id="ecdf4-679">localhost</span></span>
- <span data-ttu-id="ecdf4-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ecdf4-680">127.0.0.1</span></span>
- <span data-ttu-id="ecdf4-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-682">com</span><span class="sxs-lookup"><span data-stu-id="ecdf4-682">com</span></span>
- <span data-ttu-id="ecdf4-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-684">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="ecdf4-685">Chiave dell'account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="ecdf4-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-686">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-686">Format</span></span>

<span data-ttu-id="ecdf4-687">La stringa "DefaultEndpointsProtocol" seguita dai caratteri e dalle stringhe delineate nel modello seguente, inclusa la stringa "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="ecdf4-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-688">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-688">Pattern</span></span>

- <span data-ttu-id="ecdf4-689">La stringa "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="ecdf4-690">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-691">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-691">An equal sign (=)</span></span>
- <span data-ttu-id="ecdf4-692">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-693">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ecdf4-694">La stringa "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-694">The string "AccountKey"</span></span>
- <span data-ttu-id="ecdf4-695">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-696">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-696">An equal sign (=)</span></span>
- <span data-ttu-id="ecdf4-697">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="ecdf4-698">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ecdf4-699">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-700">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-700">Checksum</span></span>

<span data-ttu-id="ecdf4-701">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-702">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-702">Definition</span></span>

<span data-ttu-id="ecdf4-703">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-704">L'espressione regolare CEP_Regex_AzureStorageAccountKey trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-705">L'espressione regolare CEP_AzureEmulatorStorageAccountFilter **non** trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-706">L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-707">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="ecdf4-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="ecdf4-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="ecdf4-709">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ecdf4-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="ecdf4-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ecdf4-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ecdf4-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ecdf4-712">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ecdf4-713">contoso</span><span class="sxs-lookup"><span data-stu-id="ecdf4-713">contoso</span></span>
- <span data-ttu-id="ecdf4-714">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="ecdf4-714">fabrikam</span></span>
- <span data-ttu-id="ecdf4-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="ecdf4-715">northwind</span></span>
- <span data-ttu-id="ecdf4-716">sandbox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-716">sandbox</span></span>
- <span data-ttu-id="ecdf4-717">OneBox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-717">onebox</span></span>
- <span data-ttu-id="ecdf4-718">localhost</span><span class="sxs-lookup"><span data-stu-id="ecdf4-718">localhost</span></span>
- <span data-ttu-id="ecdf4-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ecdf4-719">127.0.0.1</span></span>
- <span data-ttu-id="ecdf4-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-721">com</span><span class="sxs-lookup"><span data-stu-id="ecdf4-721">com</span></span>
- <span data-ttu-id="ecdf4-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-723">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="ecdf4-724">Chiave dell'account di archiviazione di Azure (generico)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-725">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-725">Format</span></span>

<span data-ttu-id="ecdf4-726">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+), preceduto o seguito dai caratteri delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-727">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-727">Pattern</span></span>

- <span data-ttu-id="ecdf4-728">0-1 del simbolo maggiore di (>), apostrofo ('), segno di uguale (=), virgolette (") o segno numerico (#)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="ecdf4-729">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="ecdf4-730">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="ecdf4-731">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-731">Checksum</span></span>

<span data-ttu-id="ecdf4-732">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-733">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-733">Definition</span></span>

<span data-ttu-id="ecdf4-734">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-735">L'espressione regolare CEP_Regex_AzureStorageAccountKeyGeneric trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="ecdf4-736">Belgio - Numero nazionale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-737">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-737">Format</span></span>

<span data-ttu-id="ecdf4-738">11 cifre più delimitatori</span><span class="sxs-lookup"><span data-stu-id="ecdf4-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-739">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-739">Pattern</span></span>

<span data-ttu-id="ecdf4-740">11 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="ecdf4-741">Sei cifre e due punti nel formato AA.MM.GG per data di nascita </span><span class="sxs-lookup"><span data-stu-id="ecdf4-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="ecdf4-742">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-742">A hyphen</span></span> 
- <span data-ttu-id="ecdf4-743">Tre cifre sequenziali (dispari sia per uomini che per donne) </span><span class="sxs-lookup"><span data-stu-id="ecdf4-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="ecdf4-744">Un punto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-744">A period</span></span> 
- <span data-ttu-id="ecdf4-745">Due cifre, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-746">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-746">Checksum</span></span>

<span data-ttu-id="ecdf4-747">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-748">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-748">Definition</span></span>

<span data-ttu-id="ecdf4-749">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-750">La funzione Func_belgium_national_number trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-751">Viene trovata una parola chiave da Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="ecdf4-752">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-753">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="ecdf4-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="ecdf4-755">Identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-755">Identity</span></span>
- <span data-ttu-id="ecdf4-756">Registrazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-756">Registration</span></span>
- <span data-ttu-id="ecdf4-757">Identificazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-757">Identification</span></span> 
- <span data-ttu-id="ecdf4-758">ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-758">ID</span></span> 
- <span data-ttu-id="ecdf4-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="ecdf4-759">Identiteitskaart</span></span>
- <span data-ttu-id="ecdf4-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-760">Registratie nummer</span></span> 
- <span data-ttu-id="ecdf4-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-761">Identificatie nummer</span></span> 
- <span data-ttu-id="ecdf4-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-762">Identiteit</span></span>
- <span data-ttu-id="ecdf4-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="ecdf4-763">Registratie</span></span>
- <span data-ttu-id="ecdf4-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="ecdf4-764">Identificatie</span></span> 
- <span data-ttu-id="ecdf4-765">Carte d'identité</span><span class="sxs-lookup"><span data-stu-id="ecdf4-765">Carte d'identité</span></span> 
- <span data-ttu-id="ecdf4-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="ecdf4-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="ecdf4-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="ecdf4-767">numéro d'identification</span></span>
- <span data-ttu-id="ecdf4-768">identité</span><span class="sxs-lookup"><span data-stu-id="ecdf4-768">identité</span></span> 
- <span data-ttu-id="ecdf4-769">iscrizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-769">inscription</span></span> 
- <span data-ttu-id="ecdf4-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="ecdf4-770">Identifikation</span></span>
- <span data-ttu-id="ecdf4-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="ecdf4-771">Identifizierung</span></span>
- <span data-ttu-id="ecdf4-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-772">Identifikationsnummer</span></span>
- <span data-ttu-id="ecdf4-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="ecdf4-773">Personalausweis</span></span>
- <span data-ttu-id="ecdf4-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="ecdf4-774">Registrierung</span></span>
- <span data-ttu-id="ecdf4-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="ecdf4-776">Numero CPF Brasile</span><span class="sxs-lookup"><span data-stu-id="ecdf4-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-777">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-777">Format</span></span>

<span data-ttu-id="ecdf4-778">11 cifre che includono una cifra di controllo e possono essere formattate o non formattate</span><span class="sxs-lookup"><span data-stu-id="ecdf4-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-779">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-779">Pattern</span></span>

<span data-ttu-id="ecdf4-780">Formattato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-780">Formatted:</span></span>
- <span data-ttu-id="ecdf4-781">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-781">Three digits</span></span> 
- <span data-ttu-id="ecdf4-782">Un punto </span><span class="sxs-lookup"><span data-stu-id="ecdf4-782">A period</span></span> 
- <span data-ttu-id="ecdf4-783">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-783">Three digits</span></span> 
- <span data-ttu-id="ecdf4-784">Un punto </span><span class="sxs-lookup"><span data-stu-id="ecdf4-784">A period</span></span> 
- <span data-ttu-id="ecdf4-785">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-785">Three digits</span></span> 
- <span data-ttu-id="ecdf4-786">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-786">A hyphen</span></span> 
- <span data-ttu-id="ecdf4-787">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-787">Two digits which are check digits</span></span>

<span data-ttu-id="ecdf4-788">Formattato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-788">Unformatted:</span></span>
- <span data-ttu-id="ecdf4-789">11 cifre dove le ultime due sono cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-790">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-790">Checksum</span></span>

<span data-ttu-id="ecdf4-791">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-792">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-792">Definition</span></span>

<span data-ttu-id="ecdf4-793">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-794">La funzione Func_brazil_cpf trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-795">Viene trovata una parola chiave da Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="ecdf4-796">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-796">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-797">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-798">La funzione Func_brazil_cpf trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-799">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-799">The checksum passes.</span></span>

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-800">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="ecdf4-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="ecdf4-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="ecdf4-802">CPF</span><span class="sxs-lookup"><span data-stu-id="ecdf4-802">CPF</span></span>
- <span data-ttu-id="ecdf4-803">Identificazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-803">Identification</span></span>
- <span data-ttu-id="ecdf4-804">Registrazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-804">Registration</span></span>
- <span data-ttu-id="ecdf4-805">Entrate</span><span class="sxs-lookup"><span data-stu-id="ecdf4-805">Revenue</span></span>
- <span data-ttu-id="ecdf4-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="ecdf4-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="ecdf4-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-807">Imposto</span></span> 
- <span data-ttu-id="ecdf4-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="ecdf4-808">Identificação</span></span> 
- <span data-ttu-id="ecdf4-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="ecdf4-809">Inscrição</span></span> 
- <span data-ttu-id="ecdf4-810">Receita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="ecdf4-811">Brasile - Codice fiscale persone giuridiche (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-812">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-812">Format</span></span>

<span data-ttu-id="ecdf4-813">14 cifre che includono il numero di registrazione, il codice della filiale, le cifre di controllo e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="ecdf4-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-814">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-814">Pattern</span></span>
<span data-ttu-id="ecdf4-815">14 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="ecdf4-816">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-816">Two digits</span></span> 
- <span data-ttu-id="ecdf4-817">Un punto </span><span class="sxs-lookup"><span data-stu-id="ecdf4-817">A period</span></span> 
- <span data-ttu-id="ecdf4-818">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-818">Three digits</span></span> 
- <span data-ttu-id="ecdf4-819">Un punto </span><span class="sxs-lookup"><span data-stu-id="ecdf4-819">A period</span></span> 
- <span data-ttu-id="ecdf4-820">Tre cifre (le prime otto sono il numero di registrazione) </span><span class="sxs-lookup"><span data-stu-id="ecdf4-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="ecdf4-821">Una barra</span><span class="sxs-lookup"><span data-stu-id="ecdf4-821">A forward slash</span></span> 
- <span data-ttu-id="ecdf4-822">Numero del ramo a quattro cifre </span><span class="sxs-lookup"><span data-stu-id="ecdf4-822">Four-digit branch number</span></span> 
- <span data-ttu-id="ecdf4-823">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-823">A hyphen</span></span> 
- <span data-ttu-id="ecdf4-824">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-825">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-825">Checksum</span></span>

<span data-ttu-id="ecdf4-826">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-827">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-827">Definition</span></span>

<span data-ttu-id="ecdf4-828">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-829">La funzione Func_brazil_cnpj trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-830">Viene trovata una parola chiave da Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="ecdf4-831">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-831">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-832">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-833">La funzione Func_brazil_cnpj trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-834">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-834">The checksum passes.</span></span>

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-835">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="ecdf4-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="ecdf4-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="ecdf4-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="ecdf4-837">CNPJ</span></span> 
- <span data-ttu-id="ecdf4-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="ecdf4-838">CNPJ/MF</span></span> 
- <span data-ttu-id="ecdf4-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="ecdf4-839">CNPJ-MF</span></span> 
- <span data-ttu-id="ecdf4-840">Codice fiscale persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="ecdf4-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="ecdf4-841">Registro contribuenti</span><span class="sxs-lookup"><span data-stu-id="ecdf4-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="ecdf4-842">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="ecdf4-842">Legal entity</span></span> 
- <span data-ttu-id="ecdf4-843">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="ecdf4-843">Legal entities</span></span> 
- <span data-ttu-id="ecdf4-844">Stato della registrazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-844">Registration Status</span></span> 
- <span data-ttu-id="ecdf4-845">Business</span><span class="sxs-lookup"><span data-stu-id="ecdf4-845">Business</span></span> 
- <span data-ttu-id="ecdf4-846">Company</span><span class="sxs-lookup"><span data-stu-id="ecdf4-846">Company</span></span>
- <span data-ttu-id="ecdf4-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="ecdf4-847">CNPJ</span></span> 
- <span data-ttu-id="ecdf4-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="ecdf4-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="ecdf4-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="ecdf4-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="ecdf4-850">CGC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-850">CGC</span></span> 
- <span data-ttu-id="ecdf4-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="ecdf4-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="ecdf4-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="ecdf4-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="ecdf4-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="ecdf4-853">Situação cadastral</span></span> 
- <span data-ttu-id="ecdf4-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="ecdf4-854">Inscrição</span></span> 
- <span data-ttu-id="ecdf4-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="ecdf4-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="ecdf4-856">	Carta d'identità (Brasile) (RG)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-857">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-857">Format</span></span>

<span data-ttu-id="ecdf4-858">Registro Geral (formato precedente): nove cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="ecdf4-859">Registro de Identidade (RIC) (nuovo formato): 11 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-860">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-860">Pattern</span></span>

<span data-ttu-id="ecdf4-861">Registro Geral (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="ecdf4-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="ecdf4-862">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-862">Two digits</span></span> 
- <span data-ttu-id="ecdf4-863">Un punto </span><span class="sxs-lookup"><span data-stu-id="ecdf4-863">A period</span></span> 
- <span data-ttu-id="ecdf4-864">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-864">Three digits</span></span> 
- <span data-ttu-id="ecdf4-865">Un punto </span><span class="sxs-lookup"><span data-stu-id="ecdf4-865">A period</span></span> 
- <span data-ttu-id="ecdf4-866">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-866">Three digits</span></span> 
- <span data-ttu-id="ecdf4-867">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-867">A hyphen</span></span> 
- <span data-ttu-id="ecdf4-868">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-868">One digit which is a check digit</span></span>

<span data-ttu-id="ecdf4-869">Registro de Identidade (RIC) (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="ecdf4-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="ecdf4-870">10 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-870">10 digits</span></span> 
- <span data-ttu-id="ecdf4-871">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-871">A hyphen</span></span> 
- <span data-ttu-id="ecdf4-872">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-873">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-873">Checksum</span></span>

<span data-ttu-id="ecdf4-874">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-875">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-875">Definition</span></span>

<span data-ttu-id="ecdf4-876">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-877">La funzione Func_brazil_rg trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-878">Viene trovata una parola chiave da Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="ecdf4-879">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-879">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-880">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-881">La funzione Func_brazil_rg trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-882">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-882">The checksum passes.</span></span>

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-883">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="ecdf4-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="ecdf4-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="ecdf4-885">Cédula de Identidade identità Card National ID número de rregistro Registro de Iidentidade registro Geral RG (questa parola chiave è distinzione tra maiuscole e minuscole) RIC (questa parola chiave è distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="ecdf4-886">Canada - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="ecdf4-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-887">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-887">Format</span></span>

<span data-ttu-id="ecdf4-888">7 o 12 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-889">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-889">Pattern</span></span>

<span data-ttu-id="ecdf4-890">Un numero di conto corrente canadese comprende 7 o 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="ecdf4-891">Un numero di transito bancario canadese comprende:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="ecdf4-892">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-892">Five digits</span></span> 
- <span data-ttu-id="ecdf4-893">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-893">A hyphen</span></span> 
- <span data-ttu-id="ecdf4-894">Tre cifre o</span><span class="sxs-lookup"><span data-stu-id="ecdf4-894">Three digits OR</span></span>
- <span data-ttu-id="ecdf4-895">Uno zero "0"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-895">A zero "0"</span></span> 
- <span data-ttu-id="ecdf4-896">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-897">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-897">Checksum</span></span>

<span data-ttu-id="ecdf4-898">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-899">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-899">Definition</span></span>

<span data-ttu-id="ecdf4-900">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-901">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-902">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="ecdf4-903">L'espressione regolare Regex_canada_bank_account_transit_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="ecdf4-904">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-905">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-906">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-907">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="ecdf4-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="ecdf4-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="ecdf4-909">canada savings bonds</span></span>
- <span data-ttu-id="ecdf4-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="ecdf4-910">canada revenue agency</span></span>
- <span data-ttu-id="ecdf4-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="ecdf4-911">canadian financial institution</span></span>
- <span data-ttu-id="ecdf4-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="ecdf4-912">direct deposit form</span></span>
- <span data-ttu-id="ecdf4-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="ecdf4-913">canadian citizen</span></span>
- <span data-ttu-id="ecdf4-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="ecdf4-914">legal representative</span></span>
- <span data-ttu-id="ecdf4-915">notary public</span><span class="sxs-lookup"><span data-stu-id="ecdf4-915">notary public</span></span>
- <span data-ttu-id="ecdf4-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="ecdf4-916">commissioner for oaths</span></span>
- <span data-ttu-id="ecdf4-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-917">child care benefit</span></span>
- <span data-ttu-id="ecdf4-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="ecdf4-918">universal child care</span></span>
- <span data-ttu-id="ecdf4-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-919">canada child tax benefit</span></span>
- <span data-ttu-id="ecdf4-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-920">income tax benefit</span></span>
- <span data-ttu-id="ecdf4-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="ecdf4-921">harmonized sales tax</span></span>
- <span data-ttu-id="ecdf4-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-922">social insurance number</span></span>
- <span data-ttu-id="ecdf4-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="ecdf4-923">income tax refund</span></span>
- <span data-ttu-id="ecdf4-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-924">child tax benefit</span></span>
- <span data-ttu-id="ecdf4-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="ecdf4-925">territorial payments</span></span>
- <span data-ttu-id="ecdf4-926">institution number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-926">institution number</span></span>
- <span data-ttu-id="ecdf4-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="ecdf4-927">deposit request</span></span>
- <span data-ttu-id="ecdf4-928">banking information</span><span class="sxs-lookup"><span data-stu-id="ecdf4-928">banking information</span></span>
- <span data-ttu-id="ecdf4-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="ecdf4-930">Canada - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="ecdf4-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-931">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-931">Format</span></span>

<span data-ttu-id="ecdf4-932">Varia in base alla provincia</span><span class="sxs-lookup"><span data-stu-id="ecdf4-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-933">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-933">Pattern</span></span>

<span data-ttu-id="ecdf4-934">Vari modelli per Alberta, Columbia Britannica, Manitoba, Nuovo Brunswick, Terranova e Labrador, Nuova Scozia, Ontario, Isola del Principe Edoardo, Quebec e Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="ecdf4-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-935">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-935">Checksum</span></span>

<span data-ttu-id="ecdf4-936">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-937">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-937">Definition</span></span>

<span data-ttu-id="ecdf4-938">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-939">La funzione Func_[province_name]_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-940">Viene trovata una parola chiave da Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="ecdf4-941">Viene trovata una parola chiave da Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-942">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="ecdf4-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="ecdf4-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="ecdf4-944">L'abbreviazione della provincia, ad esempio, AB</span><span class="sxs-lookup"><span data-stu-id="ecdf4-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="ecdf4-945">Il nome della provincia, ad esempio, Alberta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="ecdf4-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="ecdf4-947">DL</span><span class="sxs-lookup"><span data-stu-id="ecdf4-947">DL</span></span>
- <span data-ttu-id="ecdf4-948">DLS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-948">DLS</span></span>
- <span data-ttu-id="ecdf4-949">CDL</span><span class="sxs-lookup"><span data-stu-id="ecdf4-949">CDL</span></span>
- <span data-ttu-id="ecdf4-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-950">CDLS</span></span>
- <span data-ttu-id="ecdf4-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-951">DriverLic</span></span>
- <span data-ttu-id="ecdf4-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-952">DriverLics</span></span>
- <span data-ttu-id="ecdf4-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="ecdf4-953">DriverLicense</span></span>
- <span data-ttu-id="ecdf4-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-954">DriverLicenses</span></span>
- <span data-ttu-id="ecdf4-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-955">DriverLicence</span></span>
- <span data-ttu-id="ecdf4-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-956">DriverLicences</span></span>
- <span data-ttu-id="ecdf4-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-957">Driver Lic</span></span>
- <span data-ttu-id="ecdf4-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-958">Driver Lics</span></span>
- <span data-ttu-id="ecdf4-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-959">Driver License</span></span>
- <span data-ttu-id="ecdf4-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-960">Driver Licenses</span></span>
- <span data-ttu-id="ecdf4-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-961">Driver Licence</span></span>
- <span data-ttu-id="ecdf4-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-962">Driver Licences</span></span>
- <span data-ttu-id="ecdf4-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-963">DriversLic</span></span>
- <span data-ttu-id="ecdf4-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-964">DriversLics</span></span>
- <span data-ttu-id="ecdf4-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-965">DriversLicence</span></span>
- <span data-ttu-id="ecdf4-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-966">DriversLicences</span></span>
- <span data-ttu-id="ecdf4-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="ecdf4-967">DriversLicense</span></span>
- <span data-ttu-id="ecdf4-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-968">DriversLicenses</span></span>
- <span data-ttu-id="ecdf4-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-969">Drivers Lic</span></span>
- <span data-ttu-id="ecdf4-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-970">Drivers Lics</span></span>
- <span data-ttu-id="ecdf4-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-971">Drivers License</span></span>
- <span data-ttu-id="ecdf4-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-972">Drivers Licenses</span></span>
- <span data-ttu-id="ecdf4-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-973">Drivers Licence</span></span>
- <span data-ttu-id="ecdf4-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-974">Drivers Licences</span></span>
- <span data-ttu-id="ecdf4-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-975">Driver'Lic</span></span>
- <span data-ttu-id="ecdf4-976">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-976">Driver'Lics</span></span>
- <span data-ttu-id="ecdf4-977">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-977">Driver'License</span></span>
- <span data-ttu-id="ecdf4-978">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-978">Driver'Licenses</span></span>
- <span data-ttu-id="ecdf4-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-979">Driver'Licence</span></span>
- <span data-ttu-id="ecdf4-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-980">Driver'Licences</span></span>
- <span data-ttu-id="ecdf4-981">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-981">Driver' Lic</span></span>
- <span data-ttu-id="ecdf4-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-982">Driver' Lics</span></span>
- <span data-ttu-id="ecdf4-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-983">Driver' License</span></span>
- <span data-ttu-id="ecdf4-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-984">Driver' Licenses</span></span>
- <span data-ttu-id="ecdf4-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-985">Driver' Licence</span></span>
- <span data-ttu-id="ecdf4-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-986">Driver' Licences</span></span>
- <span data-ttu-id="ecdf4-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-987">Driver'sLic</span></span>
- <span data-ttu-id="ecdf4-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-988">Driver'sLics</span></span>
- <span data-ttu-id="ecdf4-989">Secondola</span><span class="sxs-lookup"><span data-stu-id="ecdf4-989">Driver'sLicense</span></span>
- <span data-ttu-id="ecdf4-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-990">Driver'sLicenses</span></span>
- <span data-ttu-id="ecdf4-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-991">Driver'sLicence</span></span>
- <span data-ttu-id="ecdf4-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-992">Driver'sLicences</span></span>
- <span data-ttu-id="ecdf4-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-993">Driver's Lic</span></span>
- <span data-ttu-id="ecdf4-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-994">Driver's Lics</span></span>
- <span data-ttu-id="ecdf4-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-995">Driver's License</span></span>
- <span data-ttu-id="ecdf4-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-996">Driver's Licenses</span></span>
- <span data-ttu-id="ecdf4-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-997">Driver's Licence</span></span>
- <span data-ttu-id="ecdf4-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-998">Driver's Licences</span></span>
- <span data-ttu-id="ecdf4-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="ecdf4-999">Permis de Conduire</span></span>
- <span data-ttu-id="ecdf4-1000">id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1000">id</span></span>
- <span data-ttu-id="ecdf4-1001">ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1001">ids</span></span>
- <span data-ttu-id="ecdf4-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1002">idcard number</span></span>
- <span data-ttu-id="ecdf4-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1003">idcard numbers</span></span>
- <span data-ttu-id="ecdf4-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1004">idcard #</span></span>
- <span data-ttu-id="ecdf4-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1005">idcard #s</span></span>
- <span data-ttu-id="ecdf4-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1006">idcard card</span></span>
- <span data-ttu-id="ecdf4-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1007">idcard cards</span></span>
- <span data-ttu-id="ecdf4-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1008">idcard</span></span>
- <span data-ttu-id="ecdf4-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1009">identification number</span></span>
- <span data-ttu-id="ecdf4-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1010">identification numbers</span></span>
- <span data-ttu-id="ecdf4-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1011">identification #</span></span>
- <span data-ttu-id="ecdf4-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1012">identification #s</span></span>
- <span data-ttu-id="ecdf4-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1013">identification card</span></span>
- <span data-ttu-id="ecdf4-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1014">identification cards</span></span>
- <span data-ttu-id="ecdf4-1015">identificazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1015">identification</span></span> 
- <span data-ttu-id="ecdf4-1016">DL #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1016">DL#</span></span>
- <span data-ttu-id="ecdf4-1017">DLS #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1017">DLS#</span></span> 
- <span data-ttu-id="ecdf4-1018">CDL #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1018">CDL#</span></span> 
- <span data-ttu-id="ecdf4-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1019">CDLS#</span></span> 
- <span data-ttu-id="ecdf4-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1020">DriverLic#</span></span> 
- <span data-ttu-id="ecdf4-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1021">DriverLics#</span></span> 
- <span data-ttu-id="ecdf4-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1022">DriverLicense#</span></span> 
- <span data-ttu-id="ecdf4-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="ecdf4-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1024">DriverLicence#</span></span> 
- <span data-ttu-id="ecdf4-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1025">DriverLicences#</span></span> 
- <span data-ttu-id="ecdf4-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1026">Driver Lic#</span></span>
- <span data-ttu-id="ecdf4-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1027">Driver Lics#</span></span> 
- <span data-ttu-id="ecdf4-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1028">Driver License#</span></span> 
- <span data-ttu-id="ecdf4-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="ecdf4-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1030">Driver License#</span></span> 
- <span data-ttu-id="ecdf4-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1031">Driver Licences#</span></span> 
- <span data-ttu-id="ecdf4-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1032">DriversLic#</span></span> 
- <span data-ttu-id="ecdf4-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1033">DriversLics#</span></span> 
- <span data-ttu-id="ecdf4-1034">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1034">DriversLicense#</span></span> 
- <span data-ttu-id="ecdf4-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="ecdf4-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1036">DriversLicence#</span></span> 
- <span data-ttu-id="ecdf4-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1037">DriversLicences#</span></span> 
- <span data-ttu-id="ecdf4-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="ecdf4-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="ecdf4-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1040">Drivers License#</span></span> 
- <span data-ttu-id="ecdf4-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="ecdf4-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="ecdf4-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="ecdf4-1044">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="ecdf4-1045">Driver ' LiCS #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="ecdf4-1046">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1046">Driver'License#</span></span> 
- <span data-ttu-id="ecdf4-1047">Driver ' licenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="ecdf4-1048">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="ecdf4-1049">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="ecdf4-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="ecdf4-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="ecdf4-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1052">Driver' License#</span></span> 
- <span data-ttu-id="ecdf4-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="ecdf4-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="ecdf4-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="ecdf4-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="ecdf4-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="ecdf4-1058">Secondola #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="ecdf4-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="ecdf4-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="ecdf4-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="ecdf4-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="ecdf4-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="ecdf4-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1064">Driver's License#</span></span> 
- <span data-ttu-id="ecdf4-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="ecdf4-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="ecdf4-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="ecdf4-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="ecdf4-1069">ID #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1069">id#</span></span> 
- <span data-ttu-id="ecdf4-1070">ID #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1070">ids#</span></span> 
- <span data-ttu-id="ecdf4-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1071">idcard card#</span></span> 
- <span data-ttu-id="ecdf4-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1072">idcard cards#</span></span> 
- <span data-ttu-id="ecdf4-1073">idcard #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1073">idcard#</span></span> 
- <span data-ttu-id="ecdf4-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1074">identification card#</span></span> 
- <span data-ttu-id="ecdf4-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1075">identification cards#</span></span> 
- <span data-ttu-id="ecdf4-1076">identificazione #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="ecdf4-1077">Canada - Codice del servizio sanitario</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1078">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1078">Format</span></span>

<span data-ttu-id="ecdf4-1079">10 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1080">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1080">Pattern</span></span>

<span data-ttu-id="ecdf4-1081">10 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1082">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1082">Checksum</span></span>

<span data-ttu-id="ecdf4-1083">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1084">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1084">Definition</span></span>

<span data-ttu-id="ecdf4-1085">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1086">L'espressione regolare Regex_canada_health_service_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1087">Viene trovata una parola chiave da Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1088">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="ecdf4-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="ecdf4-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1090">personal health number</span></span>
- <span data-ttu-id="ecdf4-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1091">patient information</span></span>
- <span data-ttu-id="ecdf4-1092">health services</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1092">health services</span></span>
- <span data-ttu-id="ecdf4-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1093">speciality services</span></span>
- <span data-ttu-id="ecdf4-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1094">automobile accident</span></span>
- <span data-ttu-id="ecdf4-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1095">patient hospital</span></span>
- <span data-ttu-id="ecdf4-1096">psichiatra</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1096">psychiatrist</span></span>
- <span data-ttu-id="ecdf4-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1097">workers compensation</span></span>
- <span data-ttu-id="ecdf4-1098">Disability</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="ecdf4-1099">Canada - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1100">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1100">Format</span></span>

<span data-ttu-id="ecdf4-1101">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1102">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1102">Pattern</span></span>

<span data-ttu-id="ecdf4-1103">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1104">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1104">Checksum</span></span>

<span data-ttu-id="ecdf4-1105">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1106">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1106">Definition</span></span>

<span data-ttu-id="ecdf4-1107">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1108">L'espressione regolare Regex_canada_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1109">Viene trovata una parola chiave da Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1110">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="ecdf4-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="ecdf4-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1112">canadian citizenship</span></span>
- <span data-ttu-id="ecdf4-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1113">canadian passport</span></span>
- <span data-ttu-id="ecdf4-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1114">passport application</span></span>
- <span data-ttu-id="ecdf4-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1115">passport photos</span></span>
- <span data-ttu-id="ecdf4-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1116">certified translator</span></span>
- <span data-ttu-id="ecdf4-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1117">canadian citizens</span></span>
- <span data-ttu-id="ecdf4-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1118">processing times</span></span>
- <span data-ttu-id="ecdf4-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="ecdf4-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1120">Keyword_passport</span></span>

- <span data-ttu-id="ecdf4-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1121">Passport Number</span></span>
- <span data-ttu-id="ecdf4-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1122">Passport No</span></span>
- <span data-ttu-id="ecdf4-1123">Passport#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1123">Passport #</span></span>
- <span data-ttu-id="ecdf4-1124">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1124">Passport#</span></span>
- <span data-ttu-id="ecdf4-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1125">PassportID</span></span>
- <span data-ttu-id="ecdf4-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1126">Passportno</span></span>
- <span data-ttu-id="ecdf4-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1127">passportnumber</span></span>
- <span data-ttu-id="ecdf4-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1128">パスポート</span></span>
- <span data-ttu-id="ecdf4-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1129">パスポート番号</span></span>
- <span data-ttu-id="ecdf4-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1130">パスポートのNum</span></span>
- <span data-ttu-id="ecdf4-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1131">パスポート＃</span></span>
- <span data-ttu-id="ecdf4-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1132">Numéro de passeport</span></span>
- <span data-ttu-id="ecdf4-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1133">Passeport n °</span></span>
- <span data-ttu-id="ecdf4-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1134">Passeport Non</span></span>
- <span data-ttu-id="ecdf4-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1135">Passeport #</span></span>
- <span data-ttu-id="ecdf4-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1136">Passeport#</span></span>
- <span data-ttu-id="ecdf4-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1137">PasseportNon</span></span>
- <span data-ttu-id="ecdf4-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="ecdf4-1139">Canada - Numero di identificazione sanitaria personale (PHIN)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1140">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1140">Format</span></span>

<span data-ttu-id="ecdf4-1141">9 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1142">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1142">Pattern</span></span>

<span data-ttu-id="ecdf4-1143">9 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1144">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1144">Checksum</span></span>

<span data-ttu-id="ecdf4-1145">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1146">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1146">Definition</span></span>

<span data-ttu-id="ecdf4-1147">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_canada_phin trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="ecdf4-1148">Sono state trovate almeno due parole chiave provenienti da Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="ecdf4-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="ecdf4-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1151">social insurance number</span></span>
- <span data-ttu-id="ecdf4-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1152">health information act</span></span>
- <span data-ttu-id="ecdf4-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1153">income tax information</span></span>
- <span data-ttu-id="ecdf4-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1154">manitoba health</span></span>
- <span data-ttu-id="ecdf4-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1155">health registration</span></span>
- <span data-ttu-id="ecdf4-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1156">prescription purchases</span></span>
- <span data-ttu-id="ecdf4-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1157">benefit eligibility</span></span>
- <span data-ttu-id="ecdf4-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1158">personal health</span></span>
- <span data-ttu-id="ecdf4-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1159">power of attorney</span></span>
- <span data-ttu-id="ecdf4-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1160">registration number</span></span>
- <span data-ttu-id="ecdf4-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1161">personal health number</span></span>
- <span data-ttu-id="ecdf4-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1162">practitioner referral</span></span>
- <span data-ttu-id="ecdf4-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1163">wellness professional</span></span>
- <span data-ttu-id="ecdf4-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1164">patient referral</span></span>
- <span data-ttu-id="ecdf4-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="ecdf4-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="ecdf4-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1167">Nunavut</span></span>
- <span data-ttu-id="ecdf4-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1168">Quebec</span></span>
- <span data-ttu-id="ecdf4-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1169">Northwest Territories</span></span>
- <span data-ttu-id="ecdf4-1170">Ontario</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1170">Ontario</span></span>
- <span data-ttu-id="ecdf4-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1171">British Columbia</span></span>
- <span data-ttu-id="ecdf4-1172">Filippa</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1172">Alberta</span></span>
- <span data-ttu-id="ecdf4-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1173">Saskatchewan</span></span>
- <span data-ttu-id="ecdf4-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1174">Manitoba</span></span>
- <span data-ttu-id="ecdf4-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1175">Yukon</span></span>
- <span data-ttu-id="ecdf4-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="ecdf4-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1177">New Brunswick</span></span>
- <span data-ttu-id="ecdf4-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1178">Nova Scotia</span></span>
- <span data-ttu-id="ecdf4-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1179">Prince Edward Island</span></span>
- <span data-ttu-id="ecdf4-1180">Canada</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="ecdf4-1181">Canada - Numero di assicurazione sociale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1182">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1182">Format</span></span>

<span data-ttu-id="ecdf4-1183">9 cifre con spazi o lineette facoltativi</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1184">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1184">Pattern</span></span>

<span data-ttu-id="ecdf4-1185">Formattato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1185">Formatted:</span></span>
- <span data-ttu-id="ecdf4-1186">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1186">Three digits</span></span> 
- <span data-ttu-id="ecdf4-1187">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1187">A hyphen or space</span></span> 
- <span data-ttu-id="ecdf4-1188">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1188">Three digits</span></span> 
- <span data-ttu-id="ecdf4-1189">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1189">A hyphen or space</span></span> 
- <span data-ttu-id="ecdf4-1190">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1190">Three digits</span></span>

<span data-ttu-id="ecdf4-1191">Non formattato: nove cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1192">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1192">Checksum</span></span>

<span data-ttu-id="ecdf4-1193">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1194">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1194">Definition</span></span>

<span data-ttu-id="ecdf4-1195">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1196">La funzione Func_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1197">Almeno due delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="ecdf4-1198">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="ecdf4-1199">Viene trovata una parola chiave da Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="ecdf4-1200">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="ecdf4-1201">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1201">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-1202">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1203">La funzione Func_unformatted_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1204">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="ecdf4-1205">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1205">The checksum passes.</span></span>

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1206">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="ecdf4-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1207">Keyword_sin</span></span>

- <span data-ttu-id="ecdf4-1208">sin</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1208">sin</span></span> 
- <span data-ttu-id="ecdf4-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1209">social insurance</span></span> 
- <span data-ttu-id="ecdf4-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="ecdf4-1211">peccati</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1211">sins</span></span> 
- <span data-ttu-id="ecdf4-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1212">ssn</span></span> 
- <span data-ttu-id="ecdf4-1213">SNSS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1213">ssns</span></span> 
- <span data-ttu-id="ecdf4-1214">social security</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1214">social security</span></span> 
- <span data-ttu-id="ecdf4-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="ecdf4-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1216">national identification number</span></span> 
- <span data-ttu-id="ecdf4-1217">national id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1217">national id</span></span> 
- <span data-ttu-id="ecdf4-1218">sin #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1218">sin#</span></span> 
- <span data-ttu-id="ecdf4-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1219">soc ins</span></span> 
- <span data-ttu-id="ecdf4-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="ecdf4-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="ecdf4-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1222">driver's license</span></span> 
- <span data-ttu-id="ecdf4-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1223">drivers license</span></span> 
- <span data-ttu-id="ecdf4-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1224">driver's licence</span></span> 
- <span data-ttu-id="ecdf4-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1225">drivers licence</span></span> 
- <span data-ttu-id="ecdf4-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1226">DOB</span></span> 
- <span data-ttu-id="ecdf4-1227">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1227">Birthdate</span></span> 
- <span data-ttu-id="ecdf4-1228">Compleanno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1228">Birthday</span></span> 
- <span data-ttu-id="ecdf4-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="ecdf4-1230">	Cile - Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1231">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1231">Format</span></span>

<span data-ttu-id="ecdf4-1232">7-8 cifre più delimitatori una cifra di controllo o una lettera</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1233">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1233">Pattern</span></span>

<span data-ttu-id="ecdf4-1234">7-8 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="ecdf4-1235">1-2 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1235">1-2 digits</span></span> 
- <span data-ttu-id="ecdf4-1236">Un punto </span><span class="sxs-lookup"><span data-stu-id="ecdf4-1236">A period</span></span> 
- <span data-ttu-id="ecdf4-1237">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1237">Three digits</span></span> 
- <span data-ttu-id="ecdf4-1238">Un punto </span><span class="sxs-lookup"><span data-stu-id="ecdf4-1238">A period</span></span> 
- <span data-ttu-id="ecdf4-1239">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1239">Three digits</span></span> 
- <span data-ttu-id="ecdf4-1240">Un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1240">A dash</span></span> 
- <span data-ttu-id="ecdf4-1241">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1242">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1242">Checksum</span></span>

<span data-ttu-id="ecdf4-1243">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1244">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1244">Definition</span></span>

<span data-ttu-id="ecdf4-1245">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1246">La funzione Func_chile_id_card trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1247">Viene trovata una parola chiave da Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="ecdf4-1248">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1248">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-1249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1250">La funzione Func_chile_id_card trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1251">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1251">The checksum passes.</span></span>

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="ecdf4-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="ecdf4-1254">Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1254">National Identification Number</span></span> 
- <span data-ttu-id="ecdf4-1255">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1255">Identity card</span></span> 
- <span data-ttu-id="ecdf4-1256">ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1256">ID</span></span> 
- <span data-ttu-id="ecdf4-1257">Identificazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1257">Identification</span></span> 
- <span data-ttu-id="ecdf4-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="ecdf4-1259">Correre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1259">RUN</span></span> 
- <span data-ttu-id="ecdf4-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="ecdf4-1261">CARREGGIATA</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1261">RUT</span></span> 
- <span data-ttu-id="ecdf4-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="ecdf4-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="ecdf4-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="ecdf4-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="ecdf4-1266">	Numero carta di identità per residenti in Cina (RPC)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1267">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1267">Format</span></span>

<span data-ttu-id="ecdf4-1268">18 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1269">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1269">Pattern</span></span>

<span data-ttu-id="ecdf4-1270">18 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1270">18 digits:</span></span>
- <span data-ttu-id="ecdf4-1271">Sei cifre, ovvero un codice indirizzo </span><span class="sxs-lookup"><span data-stu-id="ecdf4-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="ecdf4-1272">Otto cifre nel formato AAAAMMGG, ovvero la data di nascita </span><span class="sxs-lookup"><span data-stu-id="ecdf4-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="ecdf4-1273">Tre cifre, ovvero un codice di ordine </span><span class="sxs-lookup"><span data-stu-id="ecdf4-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="ecdf4-1274">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1275">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1275">Checksum</span></span>

<span data-ttu-id="ecdf4-1276">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1277">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1277">Definition</span></span>

<span data-ttu-id="ecdf4-1278">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1279">La funzione Func_china_resident_id trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1280">Viene trovata una parola chiave da Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="ecdf4-1281">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1281">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-1282">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1283">La funzione Func_china_resident_id trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1284">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1284">The checksum passes.</span></span>

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1285">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="ecdf4-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="ecdf4-1287">Carta d’identità per residenti</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="ecdf4-1288">RPC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1288">PRC</span></span> 
- <span data-ttu-id="ecdf4-1289">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1289">National Identification Card</span></span> 
- <span data-ttu-id="ecdf4-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1290">身份证</span></span> 
- <span data-ttu-id="ecdf4-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1291">居民 身份证</span></span> 
- <span data-ttu-id="ecdf4-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1292">居民身份证</span></span> 
- <span data-ttu-id="ecdf4-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1293">鉴定</span></span> 
- <span data-ttu-id="ecdf4-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1294">身分證</span></span> 
- <span data-ttu-id="ecdf4-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1295">居民 身份證</span></span>
- <span data-ttu-id="ecdf4-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="ecdf4-1297">Credit Card Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1298">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1298">Format</span></span>

<span data-ttu-id="ecdf4-1299">da 14 a 16 cifre che possono essere formattate o non formattate (dddddddddddddddd) e che devono superare il test di Luhn.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1299">14 to 16 digits which can be formatted or unformatted (dddddddddddddddd) and which must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1300">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1300">Pattern</span></span>

<span data-ttu-id="ecdf4-1301">Modello molto complesso e solido che rileva carte di credito dei maggiori circuiti del mondo, ad esempio, Visa, MasterCard, Discover Card, JCB, American Express, nonché carte regalo e ticket restaurant.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1302">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1302">Checksum</span></span>

<span data-ttu-id="ecdf4-1303">Yes, il checksum Luhn</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1304">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1304">Definition</span></span>

<span data-ttu-id="ecdf4-1305">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1306">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1307">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1307">One of the following is true:</span></span>
    - <span data-ttu-id="ecdf4-1308">Viene trovata una parola chiave da Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="ecdf4-1309">Viene trovata una parola chiave da Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="ecdf4-1310">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="ecdf4-1311">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1311">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-1312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1313">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1314">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1314">The checksum passes.</span></span>

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="ecdf4-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="ecdf4-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1317">card verification</span></span>
- <span data-ttu-id="ecdf4-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1318">card identification number</span></span>
- <span data-ttu-id="ecdf4-1319">CVN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1319">cvn</span></span>
- <span data-ttu-id="ecdf4-1320">ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1320">cid</span></span>
- <span data-ttu-id="ecdf4-1321">CVC2</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1321">cvc2</span></span>
- <span data-ttu-id="ecdf4-1322">CVV2</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1322">cvv2</span></span>
- <span data-ttu-id="ecdf4-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1323">pin block</span></span>
- <span data-ttu-id="ecdf4-1324">security code</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1324">security code</span></span>
- <span data-ttu-id="ecdf4-1325">security number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1325">security number</span></span>
- <span data-ttu-id="ecdf4-1326">security no</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1326">security no</span></span>
- <span data-ttu-id="ecdf4-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1327">issue number</span></span>
- <span data-ttu-id="ecdf4-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1328">issue no</span></span>
- <span data-ttu-id="ecdf4-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1329">cryptogramme</span></span>
- <span data-ttu-id="ecdf4-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1330">numéro de sécurité</span></span>
- <span data-ttu-id="ecdf4-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1331">numero de securite</span></span>
- <span data-ttu-id="ecdf4-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="ecdf4-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="ecdf4-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1334">prüfziffer</span></span>
- <span data-ttu-id="ecdf4-1335">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1335">prufziffer</span></span>
- <span data-ttu-id="ecdf4-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1336">sicherheits Kode</span></span>
- <span data-ttu-id="ecdf4-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1337">sicherheitscode</span></span>
- <span data-ttu-id="ecdf4-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="ecdf4-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1339">verfalldatum</span></span>
- <span data-ttu-id="ecdf4-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1340">codice di verifica</span></span>
- <span data-ttu-id="ecdf4-1341">Cod.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1341">cod.</span></span> <span data-ttu-id="ecdf4-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1342">sicurezza</span></span>
- <span data-ttu-id="ecdf4-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1343">cod sicurezza</span></span>
- <span data-ttu-id="ecdf4-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1344">n autorizzazione</span></span>
- <span data-ttu-id="ecdf4-1345">Código</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1345">código</span></span>
- <span data-ttu-id="ecdf4-1346">Codigo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1346">codigo</span></span>
- <span data-ttu-id="ecdf4-1347">Cod.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1347">cod.</span></span> <span data-ttu-id="ecdf4-1348">SEG</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1348">seg</span></span>
- <span data-ttu-id="ecdf4-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1349">cod seg</span></span>
- <span data-ttu-id="ecdf4-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1350">código de segurança</span></span>
- <span data-ttu-id="ecdf4-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1351">codigo de seguranca</span></span>
- <span data-ttu-id="ecdf4-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1352">codigo de segurança</span></span>
- <span data-ttu-id="ecdf4-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1353">código de seguranca</span></span>
- <span data-ttu-id="ecdf4-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1354">cód.</span></span> <span data-ttu-id="ecdf4-1355">Segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1355">segurança</span></span>
- <span data-ttu-id="ecdf4-1356">Cod.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1356">cod.</span></span> <span data-ttu-id="ecdf4-1357">SEGURANCA Cod.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1357">seguranca cod.</span></span> <span data-ttu-id="ecdf4-1358">Segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1358">segurança</span></span>
- <span data-ttu-id="ecdf4-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1359">cód.</span></span> <span data-ttu-id="ecdf4-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1360">seguranca</span></span>
- <span data-ttu-id="ecdf4-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1361">cód segurança</span></span>
- <span data-ttu-id="ecdf4-1362">Cod SEGURANCA Cod Segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="ecdf4-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1363">cód seguranca</span></span>
- <span data-ttu-id="ecdf4-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1364">número de verificação</span></span>
- <span data-ttu-id="ecdf4-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1365">numero de verificacao</span></span>
- <span data-ttu-id="ecdf4-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1366">ablauf</span></span>
- <span data-ttu-id="ecdf4-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1367">gültig bis</span></span>
- <span data-ttu-id="ecdf4-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="ecdf4-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1369">gultig bis</span></span>
- <span data-ttu-id="ecdf4-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="ecdf4-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1371">scadenza</span></span>
- <span data-ttu-id="ecdf4-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1372">data scad</span></span>
- <span data-ttu-id="ecdf4-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1373">fecha de expiracion</span></span>
- <span data-ttu-id="ecdf4-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1374">fecha de venc</span></span>
- <span data-ttu-id="ecdf4-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1375">vencimiento</span></span>
- <span data-ttu-id="ecdf4-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1376">válido hasta</span></span>
- <span data-ttu-id="ecdf4-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1377">valido hasta</span></span>
- <span data-ttu-id="ecdf4-1378">VTO</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1378">vto</span></span>
- <span data-ttu-id="ecdf4-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1379">data de expiração</span></span>
- <span data-ttu-id="ecdf4-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1380">data de expiracao</span></span>
- <span data-ttu-id="ecdf4-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1381">data em que expira</span></span>
- <span data-ttu-id="ecdf4-1382">validade</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1382">validade</span></span>
- <span data-ttu-id="ecdf4-1383">Valor</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1383">valor</span></span>
- <span data-ttu-id="ecdf4-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1384">vencimento</span></span>
- <span data-ttu-id="ecdf4-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="ecdf4-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="ecdf4-1387">Amex</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1387">amex</span></span>
- <span data-ttu-id="ecdf4-1388">american express</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1388">american express</span></span>
- <span data-ttu-id="ecdf4-1389">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1389">americanexpress</span></span>
- <span data-ttu-id="ecdf4-1390">Esempio</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1390">Visa</span></span>
- <span data-ttu-id="ecdf4-1391">Mastercard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1391">mastercard</span></span>
- <span data-ttu-id="ecdf4-1392">master card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1392">master card</span></span>
- <span data-ttu-id="ecdf4-1393">MC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1393">mc</span></span> 
- <span data-ttu-id="ecdf4-1394">Mastercard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1394">mastercards</span></span>
- <span data-ttu-id="ecdf4-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1395">master cards</span></span>
- <span data-ttu-id="ecdf4-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1396">diner's Club</span></span>
- <span data-ttu-id="ecdf4-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1397">diners club</span></span>
- <span data-ttu-id="ecdf4-1398">DinersClub</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1398">dinersclub</span></span>
- <span data-ttu-id="ecdf4-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1399">discover card</span></span>
- <span data-ttu-id="ecdf4-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1400">discovercard</span></span>
- <span data-ttu-id="ecdf4-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1401">discover cards</span></span>
- <span data-ttu-id="ecdf4-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1402">JCB</span></span>
- <span data-ttu-id="ecdf4-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1403">japanese card bureau</span></span>
- <span data-ttu-id="ecdf4-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1404">carte blanche</span></span>
- <span data-ttu-id="ecdf4-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1405">carteblanche</span></span>
- <span data-ttu-id="ecdf4-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1406">credit card</span></span>
- <span data-ttu-id="ecdf4-1407">CC #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1407">cc#</span></span>
- <span data-ttu-id="ecdf4-1408">CC #:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1408">cc#:</span></span>
- <span data-ttu-id="ecdf4-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1409">expiration date</span></span>
- <span data-ttu-id="ecdf4-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1410">exp date</span></span>
- <span data-ttu-id="ecdf4-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1411">expiry date</span></span>
- <span data-ttu-id="ecdf4-1412">Data d'expiration</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1412">date d'expiration</span></span>
- <span data-ttu-id="ecdf4-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1413">date d'exp</span></span>
- <span data-ttu-id="ecdf4-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1414">date expiration</span></span>
- <span data-ttu-id="ecdf4-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1415">bank card</span></span>
- <span data-ttu-id="ecdf4-1416">Bankcard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1416">bankcard</span></span>
- <span data-ttu-id="ecdf4-1417">card number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1417">card number</span></span>
- <span data-ttu-id="ecdf4-1418">card num</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1418">card num</span></span>
- <span data-ttu-id="ecdf4-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1419">cardnumber</span></span>
- <span data-ttu-id="ecdf4-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1420">cardnumbers</span></span>
- <span data-ttu-id="ecdf4-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1421">card numbers</span></span>
- <span data-ttu-id="ecdf4-1422">CreditCard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1422">creditcard</span></span>
- <span data-ttu-id="ecdf4-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1423">credit cards</span></span>
- <span data-ttu-id="ecdf4-1424">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1424">creditcards</span></span>
- <span data-ttu-id="ecdf4-1425">Ccn</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1425">ccn</span></span>
- <span data-ttu-id="ecdf4-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1426">card holder</span></span>
- <span data-ttu-id="ecdf4-1427">titolare</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1427">cardholder</span></span>
- <span data-ttu-id="ecdf4-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1428">card holders</span></span>
- <span data-ttu-id="ecdf4-1429">titolari</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1429">cardholders</span></span>
- <span data-ttu-id="ecdf4-1430">check card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1430">check card</span></span>
- <span data-ttu-id="ecdf4-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1431">checkcard</span></span>
- <span data-ttu-id="ecdf4-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1432">check cards</span></span>
- <span data-ttu-id="ecdf4-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1433">checkcards</span></span>
- <span data-ttu-id="ecdf4-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1434">debit card</span></span>
- <span data-ttu-id="ecdf4-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1435">debitcard</span></span>
- <span data-ttu-id="ecdf4-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1436">debit cards</span></span>
- <span data-ttu-id="ecdf4-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1437">debitcards</span></span>
- <span data-ttu-id="ecdf4-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1438">atm card</span></span>
- <span data-ttu-id="ecdf4-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1439">atmcard</span></span>
- <span data-ttu-id="ecdf4-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1440">atm cards</span></span>
- <span data-ttu-id="ecdf4-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1441">atmcards</span></span>
- <span data-ttu-id="ecdf4-1442">Enroute</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1442">enroute</span></span>
- <span data-ttu-id="ecdf4-1443">en route</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1443">en route</span></span>
- <span data-ttu-id="ecdf4-1444">card type</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1444">card type</span></span>
- <span data-ttu-id="ecdf4-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1445">carte bancaire</span></span>
- <span data-ttu-id="ecdf4-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1446">carte de crédit</span></span>
- <span data-ttu-id="ecdf4-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1447">carte de credit</span></span>
- <span data-ttu-id="ecdf4-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1448">numéro de carte</span></span>
- <span data-ttu-id="ecdf4-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1449">numero de carte</span></span>
- <span data-ttu-id="ecdf4-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1450">nº de la carte</span></span>
- <span data-ttu-id="ecdf4-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1451">nº de carte</span></span>
- <span data-ttu-id="ecdf4-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1452">kreditkarte</span></span>
- <span data-ttu-id="ecdf4-1453">Karte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1453">karte</span></span>
- <span data-ttu-id="ecdf4-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1454">karteninhaber</span></span>
- <span data-ttu-id="ecdf4-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1455">karteninhabers</span></span>
- <span data-ttu-id="ecdf4-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="ecdf4-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="ecdf4-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1458">kreditkartentyp</span></span>
- <span data-ttu-id="ecdf4-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1459">eigentümername</span></span>
- <span data-ttu-id="ecdf4-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1460">kartennr</span></span> 
- <span data-ttu-id="ecdf4-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1461">kartennummer</span></span>
- <span data-ttu-id="ecdf4-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1462">kreditkartennummer</span></span>
- <span data-ttu-id="ecdf4-1463">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="ecdf4-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1464">carta di credito</span></span>
- <span data-ttu-id="ecdf4-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1465">carta credito</span></span>
- <span data-ttu-id="ecdf4-1466">carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1466">carta</span></span>
- <span data-ttu-id="ecdf4-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1467">n carta</span></span>
- <span data-ttu-id="ecdf4-1468">Nr.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1468">nr.</span></span> <span data-ttu-id="ecdf4-1469">carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1469">carta</span></span>
- <span data-ttu-id="ecdf4-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1470">nr carta</span></span>
- <span data-ttu-id="ecdf4-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1471">numero carta</span></span>
- <span data-ttu-id="ecdf4-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1472">numero della carta</span></span>
- <span data-ttu-id="ecdf4-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1473">numero di carta</span></span>
- <span data-ttu-id="ecdf4-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1474">tarjeta credito</span></span>
- <span data-ttu-id="ecdf4-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1475">tarjeta de credito</span></span>
- <span data-ttu-id="ecdf4-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1476">tarjeta crédito</span></span>
- <span data-ttu-id="ecdf4-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="ecdf4-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1478">tarjeta de atm</span></span>
- <span data-ttu-id="ecdf4-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1479">tarjeta atm</span></span>
- <span data-ttu-id="ecdf4-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1480">tarjeta debito</span></span>
- <span data-ttu-id="ecdf4-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1481">tarjeta de debito</span></span>
- <span data-ttu-id="ecdf4-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1482">tarjeta débito</span></span>
- <span data-ttu-id="ecdf4-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1483">tarjeta de débito</span></span>
- <span data-ttu-id="ecdf4-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1484">nº de tarjeta</span></span>
- <span data-ttu-id="ecdf4-1485">No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1485">no.</span></span> <span data-ttu-id="ecdf4-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1486">de tarjeta</span></span>
- <span data-ttu-id="ecdf4-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1487">no de tarjeta</span></span>
- <span data-ttu-id="ecdf4-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1488">numero de tarjeta</span></span>
- <span data-ttu-id="ecdf4-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1489">número de tarjeta</span></span>
- <span data-ttu-id="ecdf4-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1490">tarjeta no</span></span>
- <span data-ttu-id="ecdf4-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1491">tarjetahabiente</span></span>
- <span data-ttu-id="ecdf4-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1492">cartão de crédito</span></span>
- <span data-ttu-id="ecdf4-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1493">cartão de credito</span></span>
- <span data-ttu-id="ecdf4-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1494">cartao de crédito</span></span>
- <span data-ttu-id="ecdf4-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1495">cartao de credito</span></span>
- <span data-ttu-id="ecdf4-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1496">cartão de débito</span></span>
- <span data-ttu-id="ecdf4-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1497">cartao de débito</span></span>
- <span data-ttu-id="ecdf4-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1498">cartão de debito</span></span>
- <span data-ttu-id="ecdf4-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1499">cartao de debito</span></span>
- <span data-ttu-id="ecdf4-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1500">débito automático</span></span>
- <span data-ttu-id="ecdf4-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1501">debito automatico</span></span>
- <span data-ttu-id="ecdf4-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1502">número do cartão</span></span>
- <span data-ttu-id="ecdf4-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1503">numero do cartão</span></span> 
- <span data-ttu-id="ecdf4-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1504">número do cartao</span></span>
- <span data-ttu-id="ecdf4-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1505">numero do cartao</span></span>
- <span data-ttu-id="ecdf4-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1506">número de cartão</span></span>
- <span data-ttu-id="ecdf4-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1507">numero de cartão</span></span>
- <span data-ttu-id="ecdf4-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1508">número de cartao</span></span>
- <span data-ttu-id="ecdf4-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1509">numero de cartao</span></span>
- <span data-ttu-id="ecdf4-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1510">nº do cartão</span></span>
- <span data-ttu-id="ecdf4-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1511">nº do cartao</span></span>
- <span data-ttu-id="ecdf4-1512">n º.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1512">nº.</span></span> <span data-ttu-id="ecdf4-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1513">do cartão</span></span>
- <span data-ttu-id="ecdf4-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1514">no do cartão</span></span>
- <span data-ttu-id="ecdf4-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1515">no do cartao</span></span>
- <span data-ttu-id="ecdf4-1516">No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1516">no.</span></span> <span data-ttu-id="ecdf4-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1517">do cartão</span></span>
- <span data-ttu-id="ecdf4-1518">No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1518">no.</span></span> <span data-ttu-id="ecdf4-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="ecdf4-1520">Numero di carta di identità della Croazia</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1521">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1521">Format</span></span>

<span data-ttu-id="ecdf4-1522">9 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1523">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1523">Pattern</span></span>

<span data-ttu-id="ecdf4-1524">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1525">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1525">Checksum</span></span>

<span data-ttu-id="ecdf4-1526">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1527">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1527">Definition</span></span>

<span data-ttu-id="ecdf4-1528">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1529">La funzione Func_croatia_id_card trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1530">Viene trovata una parola chiave da Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1531">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="ecdf4-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="ecdf4-1533">Carta d’identità croata</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1533">Croatian identity card</span></span>
- <span data-ttu-id="ecdf4-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="ecdf4-1535">Numero di identificazione personale (OIB) - Croazia</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1536">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1536">Format</span></span>

<span data-ttu-id="ecdf4-1537">11 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1538">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1538">Pattern</span></span>

<span data-ttu-id="ecdf4-1539">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1539">11 digits:</span></span>
- <span data-ttu-id="ecdf4-1540">10 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1540">10 digits</span></span> 
- <span data-ttu-id="ecdf4-1541">La cifra finale è una cifra di controllo ai fini dello scambio di dati internazionali, le lettere HR vengono aggiunte prima delle undici cifre.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1542">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1542">Checksum</span></span>

<span data-ttu-id="ecdf4-1543">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1544">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1544">Definition</span></span>

<span data-ttu-id="ecdf4-1545">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1546">La funzione Func_croatia_oib_number trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1547">Viene trovata una parola chiave da Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="ecdf4-1548">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1548">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-1549">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1550">La funzione Func_croatia_oib_number trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1551">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1551">The checksum passes.</span></span>

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1552">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="ecdf4-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="ecdf4-1554">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1554">Personal Identification Number</span></span>
- <span data-ttu-id="ecdf4-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="ecdf4-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="ecdf4-1557">Numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1558">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1558">Format</span></span>

<span data-ttu-id="ecdf4-1559">Nove cifre con Slash opzionale (formato precedente) 10 cifre con barra di inoltro facoltativa (nuovo formato)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1560">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1560">Pattern</span></span>

<span data-ttu-id="ecdf4-1561">Nove cifre (formato obsoleto):</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="ecdf4-1562">9 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1562">Nine digits</span></span>

<span data-ttu-id="ecdf4-1563">OPPURE</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1563">OR</span></span>

- <span data-ttu-id="ecdf4-1564">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="ecdf4-1565">Una barra</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1565">A forward slash</span></span>
- <span data-ttu-id="ecdf4-1566">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1566">Three digits</span></span>

<span data-ttu-id="ecdf4-1567">10 cifre (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1567">10 digits (new format):</span></span>
- <span data-ttu-id="ecdf4-1568">10 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1568">10 digits</span></span>

<span data-ttu-id="ecdf4-1569">OPPURE</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1569">OR</span></span>

- <span data-ttu-id="ecdf4-1570">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="ecdf4-1571">Una barra</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1571">A forward slash</span></span> 
- <span data-ttu-id="ecdf4-1572">Quattro cifre in cui l'ultima cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1573">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1573">Checksum</span></span>

<span data-ttu-id="ecdf4-1574">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1575">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1575">Definition</span></span>

<span data-ttu-id="ecdf4-1576">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_czech_id_card trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="ecdf4-1577">Viene trovata una parola chiave da Keyword_czech_id_card.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="ecdf4-1578">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="ecdf4-1579">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1579">Keywords</span></span>

- <span data-ttu-id="ecdf4-1580">numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1580">czech personal identity number</span></span>
- <span data-ttu-id="ecdf4-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="ecdf4-1582">Codice PIN - Danimarca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1583">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1583">Format</span></span>

<span data-ttu-id="ecdf4-1584">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1585">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1585">Pattern</span></span>

<span data-ttu-id="ecdf4-1586">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1586">10 digits:</span></span>
- <span data-ttu-id="ecdf4-1587">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="ecdf4-1588">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1588">A hyphen</span></span> 
- <span data-ttu-id="ecdf4-1589">Quattro cifre, dove l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1590">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1590">Checksum</span></span>

<span data-ttu-id="ecdf4-1591">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1592">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1592">Definition</span></span>

<span data-ttu-id="ecdf4-1593">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_denmark_id trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="ecdf4-1594">Viene trovata una parola chiave da Keyword_denmark_id.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="ecdf4-1595">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1596">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="ecdf4-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="ecdf4-1598">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1598">Personal Identification Number</span></span>
- <span data-ttu-id="ecdf4-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1599">CPR</span></span>
- <span data-ttu-id="ecdf4-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="ecdf4-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="ecdf4-1602">Numero della Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1603">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1603">Format</span></span>

<span data-ttu-id="ecdf4-1604">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1605">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1605">Pattern</span></span>

<span data-ttu-id="ecdf4-1606">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="ecdf4-1607">Una lettera (senza distinzione tra maiuscole/minuscole) da questo gruppo di lettere: abcdefghjklmnprstux, ovvero un codice registrante</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="ecdf4-1608">Una lettera (senza distinzione tra maiuscole/minuscole), ovvero la prima lettera del cognome del registrante</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="ecdf4-1609">7 cifre e l'ultima è quella di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1610">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1610">Checksum</span></span>

<span data-ttu-id="ecdf4-1611">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1612">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1612">Definition</span></span>

<span data-ttu-id="ecdf4-1613">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1614">La funzione Func_dea_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1615">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1616">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1616">Keywords</span></span>

<span data-ttu-id="ecdf4-1617">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="ecdf4-1618">Unione Europea - Numero di carta di debito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1619">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1619">Format</span></span>

<span data-ttu-id="ecdf4-1620">16 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1621">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1621">Pattern</span></span>

<span data-ttu-id="ecdf4-1622">Modello molto complesso e solido</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1623">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1623">Checksum</span></span>

<span data-ttu-id="ecdf4-1624">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1625">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1625">Definition</span></span>

<span data-ttu-id="ecdf4-1626">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1627">La funzione Func_eu_debit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1628">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="ecdf4-1629">Viene trovata una parola chiave da Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="ecdf4-1630">Viene trovata una parola chiave da Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="ecdf4-1631">Viene trovata una parola chiave da Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="ecdf4-1632">Viene trovata una parola chiave da Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="ecdf4-1633">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="ecdf4-1634">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1634">The checksum passes.</span></span>

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1635">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="ecdf4-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="ecdf4-1637">account number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1637">account number</span></span> 
- <span data-ttu-id="ecdf4-1638">card number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1638">card number</span></span> 
- <span data-ttu-id="ecdf4-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1639">card no.</span></span> 
- <span data-ttu-id="ecdf4-1640">security number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1640">security number</span></span> 
- <span data-ttu-id="ecdf4-1641">CC #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="ecdf4-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="ecdf4-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1643">acct nbr</span></span> 
- <span data-ttu-id="ecdf4-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1644">acct num</span></span> 
- <span data-ttu-id="ecdf4-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1645">acct no</span></span> 
- <span data-ttu-id="ecdf4-1646">american express</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1646">american express</span></span> 
- <span data-ttu-id="ecdf4-1647">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1647">americanexpress</span></span> 
- <span data-ttu-id="ecdf4-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1648">americano espresso</span></span> 
- <span data-ttu-id="ecdf4-1649">Amex</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1649">amex</span></span> 
- <span data-ttu-id="ecdf4-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1650">atm card</span></span> 
- <span data-ttu-id="ecdf4-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1651">atm cards</span></span> 
- <span data-ttu-id="ecdf4-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1652">atm kaart</span></span> 
- <span data-ttu-id="ecdf4-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1653">atmcard</span></span> 
- <span data-ttu-id="ecdf4-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1654">atmcards</span></span> 
- <span data-ttu-id="ecdf4-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1655">atmkaart</span></span> 
- <span data-ttu-id="ecdf4-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1656">atmkaarten</span></span> 
- <span data-ttu-id="ecdf4-1657">Bancontact</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1657">bancontact</span></span> 
- <span data-ttu-id="ecdf4-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1658">bank card</span></span> 
- <span data-ttu-id="ecdf4-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1659">bankkaart</span></span> 
- <span data-ttu-id="ecdf4-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1660">card holder</span></span> 
- <span data-ttu-id="ecdf4-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1661">card holders</span></span> 
- <span data-ttu-id="ecdf4-1662">card num</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1662">card num</span></span> 
- <span data-ttu-id="ecdf4-1663">card number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1663">card number</span></span> 
- <span data-ttu-id="ecdf4-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1664">card numbers</span></span> 
- <span data-ttu-id="ecdf4-1665">card type</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1665">card type</span></span> 
- <span data-ttu-id="ecdf4-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1666">cardano numerico</span></span> 
- <span data-ttu-id="ecdf4-1667">titolare</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1667">cardholder</span></span> 
- <span data-ttu-id="ecdf4-1668">titolari</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1668">cardholders</span></span> 
- <span data-ttu-id="ecdf4-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1669">cardnumber</span></span> 
- <span data-ttu-id="ecdf4-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1670">cardnumbers</span></span> 
- <span data-ttu-id="ecdf4-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1671">carta bianca</span></span> 
- <span data-ttu-id="ecdf4-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1672">carta credito</span></span> 
- <span data-ttu-id="ecdf4-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1673">carta di credito</span></span> 
- <span data-ttu-id="ecdf4-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1674">cartao de credito</span></span> 
- <span data-ttu-id="ecdf4-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1675">cartao de crédito</span></span> 
- <span data-ttu-id="ecdf4-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1676">cartao de debito</span></span> 
- <span data-ttu-id="ecdf4-1677">○cartao de débito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1677">cartao de débito</span></span> 
- <span data-ttu-id="ecdf4-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1678">carte bancaire</span></span> 
- <span data-ttu-id="ecdf4-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1679">carte blanche</span></span> 
- <span data-ttu-id="ecdf4-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1680">carte bleue</span></span> 
- <span data-ttu-id="ecdf4-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1681">carte de credit</span></span> 
- <span data-ttu-id="ecdf4-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1682">carte de crédit</span></span> 
- <span data-ttu-id="ecdf4-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1683">carte di credito</span></span> 
- <span data-ttu-id="ecdf4-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1684">carteblanche</span></span> 
- <span data-ttu-id="ecdf4-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1685">cartão de credito</span></span> 
- <span data-ttu-id="ecdf4-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1686">cartão de crédito</span></span> 
- <span data-ttu-id="ecdf4-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1687">cartão de debito</span></span> 
- <span data-ttu-id="ecdf4-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1688">cartão de débito</span></span> 
- <span data-ttu-id="ecdf4-1689">CB</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1689">cb</span></span> 
- <span data-ttu-id="ecdf4-1690">Ccn</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1690">ccn</span></span> 
- <span data-ttu-id="ecdf4-1691">check card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1691">check card</span></span> 
- <span data-ttu-id="ecdf4-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1692">check cards</span></span> 
- <span data-ttu-id="ecdf4-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1693">checkcard</span></span>
- <span data-ttu-id="ecdf4-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1694">checkcards</span></span> 
- <span data-ttu-id="ecdf4-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1695">chequekaart</span></span> 
- <span data-ttu-id="ecdf4-1696">Cirrus</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1696">cirrus</span></span> 
- <span data-ttu-id="ecdf4-1697">Cirrus-Edc-Maestro</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="ecdf4-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1698">controlekaart</span></span> 
- <span data-ttu-id="ecdf4-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1699">controlekaarten</span></span> 
- <span data-ttu-id="ecdf4-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1700">credit card</span></span> 
- <span data-ttu-id="ecdf4-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1701">credit cards</span></span> 
- <span data-ttu-id="ecdf4-1702">CreditCard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1702">creditcard</span></span> 
- <span data-ttu-id="ecdf4-1703">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1703">creditcards</span></span> 
- <span data-ttu-id="ecdf4-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1704">debetkaart</span></span> 
- <span data-ttu-id="ecdf4-1705">carte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1705">debetkaarten</span></span> 
- <span data-ttu-id="ecdf4-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1706">debit card</span></span> 
- <span data-ttu-id="ecdf4-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1707">debit cards</span></span> 
- <span data-ttu-id="ecdf4-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1708">debitcard</span></span> 
- <span data-ttu-id="ecdf4-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1709">debitcards</span></span> 
- <span data-ttu-id="ecdf4-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1710">debito automatico</span></span> 
- <span data-ttu-id="ecdf4-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1711">diners club</span></span> 
- <span data-ttu-id="ecdf4-1712">DinersClub</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1712">dinersclub</span></span> 
- <span data-ttu-id="ecdf4-1713">individuare</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1713">discover</span></span> 
- <span data-ttu-id="ecdf4-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1714">discover card</span></span> 
- <span data-ttu-id="ecdf4-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1715">discover cards</span></span> 
- <span data-ttu-id="ecdf4-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1716">discovercard</span></span> 
- <span data-ttu-id="ecdf4-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1717">discovercards</span></span> 
- <span data-ttu-id="ecdf4-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1718">débito automático</span></span>
- <span data-ttu-id="ecdf4-1719">EDC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1719">edc</span></span> 
- <span data-ttu-id="ecdf4-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1720">eigentümername</span></span> 
- <span data-ttu-id="ecdf4-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1721">european debit card</span></span> 
- <span data-ttu-id="ecdf4-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1722">hoofdkaart</span></span> 
- <span data-ttu-id="ecdf4-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="ecdf4-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1724">in viaggio</span></span> 
- <span data-ttu-id="ecdf4-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1725">japanese card bureau</span></span> 
- <span data-ttu-id="ecdf4-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="ecdf4-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1727">jcb</span></span> 
- <span data-ttu-id="ecdf4-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1728">kaart</span></span> 
- <span data-ttu-id="ecdf4-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1729">kaart num</span></span> 
- <span data-ttu-id="ecdf4-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1730">kaartaantal</span></span> 
- <span data-ttu-id="ecdf4-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1731">kaartaantallen</span></span> 
- <span data-ttu-id="ecdf4-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1732">kaarthouder</span></span> 
- <span data-ttu-id="ecdf4-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1733">kaarthouders</span></span> 
- <span data-ttu-id="ecdf4-1734">Karte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1734">karte</span></span>  
- <span data-ttu-id="ecdf4-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1735">karteninhaber</span></span> 
- <span data-ttu-id="ecdf4-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1736">karteninhabers</span></span>
- <span data-ttu-id="ecdf4-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1737">kartennr</span></span> 
- <span data-ttu-id="ecdf4-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1738">kartennummer</span></span> 
- <span data-ttu-id="ecdf4-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1739">kreditkarte</span></span> 
- <span data-ttu-id="ecdf4-1740">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="ecdf4-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="ecdf4-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="ecdf4-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="ecdf4-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="ecdf4-1745">Maestro</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1745">maestro</span></span> 
- <span data-ttu-id="ecdf4-1746">master card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1746">master card</span></span> 
- <span data-ttu-id="ecdf4-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1747">master cards</span></span> 
- <span data-ttu-id="ecdf4-1748">Mastercard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1748">mastercard</span></span> 
- <span data-ttu-id="ecdf4-1749">Mastercard</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1749">mastercards</span></span> 
- <span data-ttu-id="ecdf4-1750">MC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1750">mc</span></span> 
- <span data-ttu-id="ecdf4-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1751">mister cash</span></span> 
- <span data-ttu-id="ecdf4-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1752">n carta</span></span> 
- <span data-ttu-id="ecdf4-1753">carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1753">carta</span></span> 
- <span data-ttu-id="ecdf4-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1754">no de tarjeta</span></span> 
- <span data-ttu-id="ecdf4-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1755">no do cartao</span></span> 
- <span data-ttu-id="ecdf4-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1756">no do cartão</span></span> 
- <span data-ttu-id="ecdf4-1757">No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1757">no.</span></span> <span data-ttu-id="ecdf4-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1758">de tarjeta</span></span> 
- <span data-ttu-id="ecdf4-1759">No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1759">no.</span></span> <span data-ttu-id="ecdf4-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1760">do cartao</span></span> 
- <span data-ttu-id="ecdf4-1761">No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1761">no.</span></span> <span data-ttu-id="ecdf4-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1762">do cartão</span></span> 
- <span data-ttu-id="ecdf4-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1763">nr carta</span></span> 
- <span data-ttu-id="ecdf4-1764">Nr.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1764">nr.</span></span> <span data-ttu-id="ecdf4-1765">carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1765">carta</span></span> 
- <span data-ttu-id="ecdf4-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1766">numeri di scheda</span></span> 
- <span data-ttu-id="ecdf4-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1767">numero carta</span></span> 
- <span data-ttu-id="ecdf4-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1768">numero de cartao</span></span> 
- <span data-ttu-id="ecdf4-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1769">numero de carte</span></span> 
- <span data-ttu-id="ecdf4-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1770">numero de cartão</span></span> 
- <span data-ttu-id="ecdf4-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1771">numero de tarjeta</span></span>
- <span data-ttu-id="ecdf4-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1772">numero della carta</span></span> 
- <span data-ttu-id="ecdf4-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1773">numero di carta</span></span> 
- <span data-ttu-id="ecdf4-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1774">numero di scheda</span></span> 
- <span data-ttu-id="ecdf4-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1775">numero do cartao</span></span> 
- <span data-ttu-id="ecdf4-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1776">numero do cartão</span></span> 
- <span data-ttu-id="ecdf4-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1777">numéro de carte</span></span> 
- <span data-ttu-id="ecdf4-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1778">nº carta</span></span> 
- <span data-ttu-id="ecdf4-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1779">nº de carte</span></span> 
- <span data-ttu-id="ecdf4-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1780">nº de la carte</span></span> 
- <span data-ttu-id="ecdf4-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="ecdf4-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1782">nº do cartao</span></span> 
- <span data-ttu-id="ecdf4-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1783">nº do cartão</span></span> 
- <span data-ttu-id="ecdf4-1784">n º.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1784">nº.</span></span> <span data-ttu-id="ecdf4-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1785">do cartão</span></span> 
- <span data-ttu-id="ecdf4-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1786">número de cartao</span></span> 
- <span data-ttu-id="ecdf4-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1787">número de cartão</span></span> 
- <span data-ttu-id="ecdf4-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1788">número de tarjeta</span></span> 
- <span data-ttu-id="ecdf4-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1789">número do cartao</span></span> 
- <span data-ttu-id="ecdf4-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="ecdf4-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="ecdf4-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="ecdf4-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1793">scheda della banca</span></span> 
- <span data-ttu-id="ecdf4-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1794">scheda di controllo</span></span> 
- <span data-ttu-id="ecdf4-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1795">scheda di debito</span></span> 
- <span data-ttu-id="ecdf4-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1796">scheda matrice</span></span> 
- <span data-ttu-id="ecdf4-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="ecdf4-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1798">schede di controllo</span></span> 
- <span data-ttu-id="ecdf4-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1799">schede di debito</span></span> 
- <span data-ttu-id="ecdf4-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1800">schede matrici</span></span> 
- <span data-ttu-id="ecdf4-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="ecdf4-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1802">scoprono le schede</span></span> 
- <span data-ttu-id="ecdf4-1803">solo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1803">solo</span></span> 
- <span data-ttu-id="ecdf4-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1804">supporti di scheda</span></span> 
- <span data-ttu-id="ecdf4-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1805">supporto di scheda</span></span> 
- <span data-ttu-id="ecdf4-1806">opzione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1806">switch</span></span> 
- <span data-ttu-id="ecdf4-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1807">tarjeta atm</span></span> 
- <span data-ttu-id="ecdf4-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1808">tarjeta credito</span></span> 
- <span data-ttu-id="ecdf4-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="ecdf4-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="ecdf4-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="ecdf4-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1812">tarjeta debito</span></span> 
- <span data-ttu-id="ecdf4-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1813">tarjeta no</span></span>
- <span data-ttu-id="ecdf4-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="ecdf4-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1815">tipo della scheda</span></span> 
- <span data-ttu-id="ecdf4-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="ecdf4-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1817">scheda</span></span> 
- <span data-ttu-id="ecdf4-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1818">v pay</span></span> 
- <span data-ttu-id="ecdf4-1819">v-pay</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1819">v-pay</span></span> 
- <span data-ttu-id="ecdf4-1820">esempio</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1820">visa</span></span> 
- <span data-ttu-id="ecdf4-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1821">visa plus</span></span> 
- <span data-ttu-id="ecdf4-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1822">visa electron</span></span> 
- <span data-ttu-id="ecdf4-1823">visto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1823">visto</span></span> 
- <span data-ttu-id="ecdf4-1824">Visum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1824">visum</span></span> 
- <span data-ttu-id="ecdf4-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="ecdf4-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="ecdf4-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1827">card identification number</span></span>
- <span data-ttu-id="ecdf4-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1828">card verification</span></span> 
- <span data-ttu-id="ecdf4-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1829">cardi la verifica</span></span> 
- <span data-ttu-id="ecdf4-1830">ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1830">cid</span></span> 
- <span data-ttu-id="ecdf4-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1831">cod seg</span></span> 
- <span data-ttu-id="ecdf4-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1832">cod seguranca</span></span> 
- <span data-ttu-id="ecdf4-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1833">cod segurança</span></span> 
- <span data-ttu-id="ecdf4-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1834">cod sicurezza</span></span> 
- <span data-ttu-id="ecdf4-1835">Cod.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1835">cod.</span></span> <span data-ttu-id="ecdf4-1836">SEG</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1836">seg</span></span> 
- <span data-ttu-id="ecdf4-1837">Cod.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1837">cod.</span></span> <span data-ttu-id="ecdf4-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1838">seguranca</span></span> 
- <span data-ttu-id="ecdf4-1839">Cod.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1839">cod.</span></span> <span data-ttu-id="ecdf4-1840">Segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1840">segurança</span></span> 
- <span data-ttu-id="ecdf4-1841">Cod.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1841">cod.</span></span> <span data-ttu-id="ecdf4-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1842">sicurezza</span></span> 
- <span data-ttu-id="ecdf4-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="ecdf4-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1844">codice di verifica</span></span> 
- <span data-ttu-id="ecdf4-1845">Codigo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1845">codigo</span></span> 
- <span data-ttu-id="ecdf4-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="ecdf4-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1847">codigo de segurança</span></span> 
- <span data-ttu-id="ecdf4-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1848">crittogramma</span></span> 
- <span data-ttu-id="ecdf4-1849">crittogramma</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1849">cryptogram</span></span> 
- <span data-ttu-id="ecdf4-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1850">cryptogramme</span></span> 
- <span data-ttu-id="ecdf4-1851">CV2</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1851">cv2</span></span> 
- <span data-ttu-id="ecdf4-1852">CVC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1852">cvc</span></span> 
- <span data-ttu-id="ecdf4-1853">CVC2</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1853">cvc2</span></span> 
- <span data-ttu-id="ecdf4-1854">CVN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1854">cvn</span></span> 
- <span data-ttu-id="ecdf4-1855">CVV</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1855">cvv</span></span> 
- <span data-ttu-id="ecdf4-1856">CVV2</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1856">cvv2</span></span> 
- <span data-ttu-id="ecdf4-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1857">cód seguranca</span></span> 
- <span data-ttu-id="ecdf4-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1858">cód segurança</span></span> 
- <span data-ttu-id="ecdf4-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1859">cód.</span></span> <span data-ttu-id="ecdf4-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1860">seguranca</span></span> 
- <span data-ttu-id="ecdf4-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1861">cód.</span></span> <span data-ttu-id="ecdf4-1862">Segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1862">segurança</span></span> 
- <span data-ttu-id="ecdf4-1863">Código</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1863">código</span></span> 
- <span data-ttu-id="ecdf4-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1864">código de seguranca</span></span> 
- <span data-ttu-id="ecdf4-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1865">código de segurança</span></span> 
- <span data-ttu-id="ecdf4-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1866">de kaart controle</span></span> 
- <span data-ttu-id="ecdf4-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1867">geeft nr uit</span></span> 
- <span data-ttu-id="ecdf4-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1868">issue no</span></span> 
- <span data-ttu-id="ecdf4-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1869">issue number</span></span> 
- <span data-ttu-id="ecdf4-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="ecdf4-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="ecdf4-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="ecdf4-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1873">kwestieaantal</span></span> 
- <span data-ttu-id="ecdf4-1874">No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1874">no.</span></span> <span data-ttu-id="ecdf4-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1875">dell'edizione</span></span> 
- <span data-ttu-id="ecdf4-1876">No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1876">no.</span></span> <span data-ttu-id="ecdf4-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1877">di sicurezza</span></span> 
- <span data-ttu-id="ecdf4-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1878">numero de securite</span></span> 
- <span data-ttu-id="ecdf4-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1879">numero de verificacao</span></span> 
- <span data-ttu-id="ecdf4-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="ecdf4-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="ecdf4-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1882">scheda</span></span> 
- <span data-ttu-id="ecdf4-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="ecdf4-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="ecdf4-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="ecdf4-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="ecdf4-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1887">número de verificação</span></span> 
- <span data-ttu-id="ecdf4-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1888">perno il blocco</span></span> 
- <span data-ttu-id="ecdf4-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1889">pin block</span></span> 
- <span data-ttu-id="ecdf4-1890">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1890">prufziffer</span></span> 
- <span data-ttu-id="ecdf4-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1891">prüfziffer</span></span> 
- <span data-ttu-id="ecdf4-1892">security code</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1892">security code</span></span> 
- <span data-ttu-id="ecdf4-1893">security no</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1893">security no</span></span> 
- <span data-ttu-id="ecdf4-1894">security number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1894">security number</span></span> 
- <span data-ttu-id="ecdf4-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1895">sicherheits kode</span></span> 
- <span data-ttu-id="ecdf4-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1896">sicherheitscode</span></span> 
- <span data-ttu-id="ecdf4-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="ecdf4-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1898">speldblok</span></span> 
- <span data-ttu-id="ecdf4-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1899">veiligheid nr</span></span> 
- <span data-ttu-id="ecdf4-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="ecdf4-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1901">veiligheidscode</span></span> 
- <span data-ttu-id="ecdf4-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="ecdf4-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="ecdf4-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="ecdf4-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1905">ablauf</span></span> 
- <span data-ttu-id="ecdf4-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1906">data de expiracao</span></span> 
- <span data-ttu-id="ecdf4-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1907">data de expiração</span></span> 
- <span data-ttu-id="ecdf4-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1908">data del exp</span></span> 
- <span data-ttu-id="ecdf4-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1909">data di exp</span></span> 
- <span data-ttu-id="ecdf4-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1910">data di scadenza</span></span> 
- <span data-ttu-id="ecdf4-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1911">data em que expira</span></span> 
- <span data-ttu-id="ecdf4-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1912">data scad</span></span> 
- <span data-ttu-id="ecdf4-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1913">data scadenza</span></span> 
- <span data-ttu-id="ecdf4-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1914">date de validité</span></span> 
- <span data-ttu-id="ecdf4-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1915">datum afloop</span></span> 
- <span data-ttu-id="ecdf4-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1916">datum van exp</span></span> 
- <span data-ttu-id="ecdf4-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1917">de afloop</span></span> 
- <span data-ttu-id="ecdf4-1918">espira</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1918">espira</span></span> 
- <span data-ttu-id="ecdf4-1919">espira</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1919">espira</span></span> 
- <span data-ttu-id="ecdf4-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1920">exp date</span></span> 
- <span data-ttu-id="ecdf4-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1921">exp datum</span></span> 
- <span data-ttu-id="ecdf4-1922">scadenza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1922">expiration</span></span> 
- <span data-ttu-id="ecdf4-1923">scadenza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1923">expire</span></span> 
- <span data-ttu-id="ecdf4-1924">scade</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1924">expires</span></span> 
- <span data-ttu-id="ecdf4-1925">scadenza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1925">expiry</span></span> 
- <span data-ttu-id="ecdf4-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="ecdf4-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1927">fecha de venc</span></span> 
- <span data-ttu-id="ecdf4-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1928">gultig bis</span></span> 
- <span data-ttu-id="ecdf4-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="ecdf4-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1930">gültig bis</span></span> 
- <span data-ttu-id="ecdf4-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="ecdf4-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1932">la scadenza</span></span> 
- <span data-ttu-id="ecdf4-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1933">scadenza</span></span> 
- <span data-ttu-id="ecdf4-1934">valable</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1934">valable</span></span> 
- <span data-ttu-id="ecdf4-1935">validade</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1935">validade</span></span> 
- <span data-ttu-id="ecdf4-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1936">valido hasta</span></span> 
- <span data-ttu-id="ecdf4-1937">Valor</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1937">valor</span></span> 
- <span data-ttu-id="ecdf4-1938">venc</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1938">venc</span></span> 
- <span data-ttu-id="ecdf4-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1939">vencimento</span></span> 
- <span data-ttu-id="ecdf4-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1940">vencimiento</span></span> 
- <span data-ttu-id="ecdf4-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1941">verloopt</span></span> 
- <span data-ttu-id="ecdf4-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1942">vervaldag</span></span> 
- <span data-ttu-id="ecdf4-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1943">vervaldatum</span></span> 
- <span data-ttu-id="ecdf4-1944">VTO</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1944">vto</span></span> 
- <span data-ttu-id="ecdf4-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="ecdf4-1946">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1946">EU Driver's License Number</span></span>

<span data-ttu-id="ecdf4-1947">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di patente dell'Unione europea](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="ecdf4-1948">Numero di identificazione nazionale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1948">EU National Identification Number</span></span>

<span data-ttu-id="ecdf4-1949">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione nazionale dell'Unione europea](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="ecdf4-1950">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1950">EU Passport Number</span></span>

<span data-ttu-id="ecdf4-1951">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di passaporto dell'Unione europea](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="ecdf4-1952">Codice di previdenza sociale dell'Unione europea o ID equivalente</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="ecdf4-1953">Per ulteriori informazioni, vedere [codice di previdenza sociale dell'Unione europea o tipo di dati sensibili ID equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="ecdf4-1954">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="ecdf4-1955">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione fiscale dell'Unione europea](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="ecdf4-1956">Finland National ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1957">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1957">Format</span></span>

<span data-ttu-id="ecdf4-1958">6 cifre, un carattere di indicazione del secolo, tre cifre più una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1959">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1959">Pattern</span></span>

<span data-ttu-id="ecdf4-1960">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="ecdf4-1961">Sei cifre nel formato DDMMYY che corrisponde alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="ecdf4-1962">Indicatore del secolo ("-", "+" o "a")</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="ecdf4-1963">Codice PIN di 3 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="ecdf4-1964">Una cifra o una lettera (con distinzione tra maiuscole/minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1965">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1965">Checksum</span></span>

<span data-ttu-id="ecdf4-1966">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1967">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1967">Definition</span></span>

<span data-ttu-id="ecdf4-1968">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1969">La funzione Func_finnish_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1970">Viene trovata una parola chiave da Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="ecdf4-1971">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-1972">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1972">Keywords</span></span>

- <span data-ttu-id="ecdf4-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="ecdf4-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="ecdf4-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="ecdf4-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1976">Personbeteckning</span></span>
- <span data-ttu-id="ecdf4-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="ecdf4-1978">Finlandia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1978">Finland Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1979">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1979">Format</span></span>
<span data-ttu-id="ecdf4-1980">Una combinazione di nove lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1980">Combination of nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1981">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1981">Pattern</span></span>
<span data-ttu-id="ecdf4-1982">Combinazione di nove lettere e cifre: due lettere (senza distinzione tra maiuscole e minuscole) sette cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1982">Combination of nine letters and digits: Two letters (not case sensitive) Seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1983">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1983">Checksum</span></span>
<span data-ttu-id="ecdf4-1984">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1984">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-1985">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1985">Definition</span></span>
<span data-ttu-id="ecdf4-1986">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-1987">L'espressione regolare Regex_finland_passport_number trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1987">The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-1988">Viene trovata una parola chiave da Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1988">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
```xml
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="ecdf4-1989">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1989">Keywords</span></span>
- <span data-ttu-id="ecdf4-1990">Keyword_finland_passport_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1990">Keyword_finland_passport_number</span></span>
- <span data-ttu-id="ecdf4-1991">Passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1991">Passport</span></span>
- <span data-ttu-id="ecdf4-1992">Passi</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1992">Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="ecdf4-1993">Francia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1993">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-1994">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1994">Format</span></span>

<span data-ttu-id="ecdf4-1995">12 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1995">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-1996">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1996">Pattern</span></span>

<span data-ttu-id="ecdf4-1997">12 cifre con convalida per scontare modelli analoghi, ad esempio, quello dei numeri telefonici francesi</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1997">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-1998">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1998">Checksum</span></span>

<span data-ttu-id="ecdf4-1999">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-1999">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2000">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2000">Definition</span></span>

<span data-ttu-id="ecdf4-2001">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2001">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2002">La funzione Func_french_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2002">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2003">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2003">At least one of the following is true:</span></span>
- <span data-ttu-id="ecdf4-2004">Viene trovata una parola chiave da Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2004">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="ecdf4-2005">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2005">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2006">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2006">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="ecdf4-2007">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2007">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="ecdf4-2008">drivers licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2008">drivers licence</span></span>
- <span data-ttu-id="ecdf4-2009">drivers license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2009">drivers license</span></span>
- <span data-ttu-id="ecdf4-2010">driving licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2010">driving licence</span></span>
- <span data-ttu-id="ecdf4-2011">driving license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2011">driving license</span></span>
- <span data-ttu-id="ecdf4-2012">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2012">permis de conduire</span></span>
- <span data-ttu-id="ecdf4-2013">licence number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2013">licence number</span></span>
- <span data-ttu-id="ecdf4-2014">license number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2014">license number</span></span>
- <span data-ttu-id="ecdf4-2015">licence numbers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2015">licence numbers</span></span>
- <span data-ttu-id="ecdf4-2016">license numbers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2016">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="ecdf4-2017">Francia - Carta d'identità nazionale (CNI)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2017">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2018">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2018">Format</span></span>

<span data-ttu-id="ecdf4-2019">12 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2019">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2020">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2020">Pattern</span></span>

<span data-ttu-id="ecdf4-2021">12 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2021">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2022">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2022">Checksum</span></span>

<span data-ttu-id="ecdf4-2023">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2023">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2024">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2024">Definition</span></span>

<span data-ttu-id="ecdf4-2025">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2025">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2026">L'espressione regolare Regex_france_cni restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2026">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2027">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2027">Keywords</span></span>

<span data-ttu-id="ecdf4-2028">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2028">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="ecdf4-2029">Francia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2029">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2030">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2030">Format</span></span>

<span data-ttu-id="ecdf4-2031">Nove cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2031">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2032">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2032">Pattern</span></span>

<span data-ttu-id="ecdf4-2033">Nove cifre e lettere:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2033">Nine digits and letters:</span></span>
- <span data-ttu-id="ecdf4-2034">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2034">Two digits</span></span> 
- <span data-ttu-id="ecdf4-2035">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2035">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-2036">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2036">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2037">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2037">Checksum</span></span>

<span data-ttu-id="ecdf4-2038">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2038">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2039">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2039">Definition</span></span>

<span data-ttu-id="ecdf4-2040">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2040">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2041">La funzione Func_fr_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2041">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2042">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2042">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2043">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2043">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="ecdf4-2044">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2044">Keyword_passport</span></span>

- <span data-ttu-id="ecdf4-2045">Passport Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2045">Passport Number</span></span>
- <span data-ttu-id="ecdf4-2046">Passport No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2046">Passport No</span></span>
- <span data-ttu-id="ecdf4-2047">Passport#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2047">Passport #</span></span>
- <span data-ttu-id="ecdf4-2048">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2048">Passport#</span></span>
- <span data-ttu-id="ecdf4-2049">PassportID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2049">PassportID</span></span>
- <span data-ttu-id="ecdf4-2050">Passportno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2050">Passportno</span></span>
- <span data-ttu-id="ecdf4-2051">passportnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2051">passportnumber</span></span>
- <span data-ttu-id="ecdf4-2052">パスポート</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2052">パスポート</span></span>
- <span data-ttu-id="ecdf4-2053">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2053">パスポート番号</span></span>
- <span data-ttu-id="ecdf4-2054">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2054">パスポートのNum</span></span>
- <span data-ttu-id="ecdf4-2055">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2055">パスポート ＃</span></span> 
- <span data-ttu-id="ecdf4-2056">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2056">Numéro de passeport</span></span>
- <span data-ttu-id="ecdf4-2057">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2057">Passeport n °</span></span>
- <span data-ttu-id="ecdf4-2058">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2058">Passeport Non</span></span>
- <span data-ttu-id="ecdf4-2059">Passeport#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2059">Passeport #</span></span>
- <span data-ttu-id="ecdf4-2060">Passeport #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2060">Passeport#</span></span>
- <span data-ttu-id="ecdf4-2061">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2061">PasseportNon</span></span>
- <span data-ttu-id="ecdf4-2062">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2062">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="ecdf4-2063">Francia - Numero di previdenza sociale (INSEE)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2063">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2064">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2064">Format</span></span>

<span data-ttu-id="ecdf4-2065">15 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2065">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2066">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2066">Pattern</span></span>

<span data-ttu-id="ecdf4-2067">Deve corrispondere a uno di questi due modelli:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2067">Must match one of two patterns:</span></span>
- <span data-ttu-id="ecdf4-2068">13 cifre seguite da uno spazio seguito da due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2068">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="ecdf4-2069">oppure</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2069">or</span></span>
- <span data-ttu-id="ecdf4-2070">15 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2070">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2071">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2071">Checksum</span></span>

<span data-ttu-id="ecdf4-2072">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2072">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2073">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2073">Definition</span></span>

<span data-ttu-id="ecdf4-2074">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2074">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2075">La funzione Func_french_insee o Func_fr_insee trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2075">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2076">Viene trovata una parola chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2076">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="ecdf4-2077">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2077">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-2078">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2078">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2079">La funzione Func_french_insee o Func_fr_insee trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2079">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2080">Non vengono trovate parole chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2080">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="ecdf4-2081">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2081">The checksum passes.</span></span>

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2082">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2082">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="ecdf4-2083">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2083">Keyword_fr_insee</span></span>

- <span data-ttu-id="ecdf4-2084">INSEE</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2084">insee</span></span>
- <span data-ttu-id="ecdf4-2085">securité sociale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2085">securité sociale</span></span>
- <span data-ttu-id="ecdf4-2086">securite sociale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2086">securite sociale</span></span>
- <span data-ttu-id="ecdf4-2087">national id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2087">national id</span></span>
- <span data-ttu-id="ecdf4-2088">national identification</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2088">national identification</span></span>
- <span data-ttu-id="ecdf4-2089">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2089">numéro d'identité</span></span>
- <span data-ttu-id="ecdf4-2090">no d'identité</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2090">no d'identité</span></span>
- <span data-ttu-id="ecdf4-2091">No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2091">no.</span></span> <span data-ttu-id="ecdf4-2092">d'identité</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2092">d'identité</span></span>
- <span data-ttu-id="ecdf4-2093">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2093">numero d'identite</span></span>
- <span data-ttu-id="ecdf4-2094">no d'identite</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2094">no d'identite</span></span>
- <span data-ttu-id="ecdf4-2095">No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2095">no.</span></span> <span data-ttu-id="ecdf4-2096">d'identite</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2096">d'identite</span></span>
- <span data-ttu-id="ecdf4-2097">social security number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2097">social security number</span></span>
- <span data-ttu-id="ecdf4-2098">social security code</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2098">social security code</span></span>
- <span data-ttu-id="ecdf4-2099">social insurance number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2099">social insurance number</span></span>
- <span data-ttu-id="ecdf4-2100">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2100">le numéro d'identification nationale</span></span>
- <span data-ttu-id="ecdf4-2101">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2101">d'identité nationale</span></span>
- <span data-ttu-id="ecdf4-2102">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2102">numéro de sécurité sociale</span></span>
- <span data-ttu-id="ecdf4-2103">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2103">le code de la sécurité sociale</span></span>
- <span data-ttu-id="ecdf4-2104">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2104">numéro d'assurance sociale</span></span>
- <span data-ttu-id="ecdf4-2105">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2105">numéro de sécu</span></span>
- <span data-ttu-id="ecdf4-2106">code sécu</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2106">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="ecdf4-2107">Germania - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2107">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2108">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2108">Format</span></span>

<span data-ttu-id="ecdf4-2109">Combinazione di 11 cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2109">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2110">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2110">Pattern</span></span>

<span data-ttu-id="ecdf4-2111">11 cifre e lettere (senza distinzione tra maiuscole/minuscole):</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2111">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="ecdf4-2112">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2112">A digit or letter</span></span> 
- <span data-ttu-id="ecdf4-2113">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2113">Two digits</span></span> 
- <span data-ttu-id="ecdf4-2114">Sei cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2114">Six digits or letters</span></span> 
- <span data-ttu-id="ecdf4-2115">Una cifra</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2115">A digit</span></span> 
- <span data-ttu-id="ecdf4-2116">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2116">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2117">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2117">Checksum</span></span>

<span data-ttu-id="ecdf4-2118">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2118">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2119">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2119">Definition</span></span>

<span data-ttu-id="ecdf4-2120">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2120">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2121">La funzione Func_german_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2121">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2122">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2122">At least one of the following is true:</span></span>
    - <span data-ttu-id="ecdf4-2123">Viene trovata una parola chiave da Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2123">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="ecdf4-2124">Viene trovata una parola chiave da Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2124">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="ecdf4-2125">Viene trovata una parola chiave da Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2125">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="ecdf4-2126">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2126">The checksum passes.</span></span>

```xml
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2127">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="ecdf4-2128">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2128">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="ecdf4-2129">Führerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2129">Führerschein</span></span>
- <span data-ttu-id="ecdf4-2130">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2130">Fuhrerschein</span></span>
- <span data-ttu-id="ecdf4-2131">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2131">Fuehrerschein</span></span>
- <span data-ttu-id="ecdf4-2132">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2132">Führerscheinnummer</span></span>
- <span data-ttu-id="ecdf4-2133">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2133">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="ecdf4-2134">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2134">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="ecdf4-2135">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2135">Führerschein-</span></span> 
- <span data-ttu-id="ecdf4-2136">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2136">Fuhrerschein-</span></span> 
- <span data-ttu-id="ecdf4-2137">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2137">Fuehrerschein-</span></span> 
- <span data-ttu-id="ecdf4-2138">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2138">FührerscheinnummerNr</span></span>
- <span data-ttu-id="ecdf4-2139">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2139">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="ecdf4-2140">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2140">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="ecdf4-2141">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2141">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="ecdf4-2142">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2142">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="ecdf4-2143">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2143">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="ecdf4-2144">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2144">Führerschein- Nr</span></span>
- <span data-ttu-id="ecdf4-2145">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2145">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="ecdf4-2146">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2146">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="ecdf4-2147">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2147">Führerschein- Klasse</span></span> 
- <span data-ttu-id="ecdf4-2148">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2148">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="ecdf4-2149">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2149">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="ecdf4-2150">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2150">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="ecdf4-2151">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2151">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="ecdf4-2152">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2152">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="ecdf4-2153">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2153">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="ecdf4-2154">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2154">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="ecdf4-2155">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2155">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="ecdf4-2156">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2156">Führerschein- Nr</span></span> 
- <span data-ttu-id="ecdf4-2157">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2157">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="ecdf4-2158">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2158">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="ecdf4-2159">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2159">Führerschein- Klasse</span></span> 
- <span data-ttu-id="ecdf4-2160">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2160">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="ecdf4-2161">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2161">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="ecdf4-2162">DL</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2162">DL</span></span> 
- <span data-ttu-id="ecdf4-2163">DLS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2163">DLS</span></span>
- <span data-ttu-id="ecdf4-2164">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2164">Driv Lic</span></span> 
- <span data-ttu-id="ecdf4-2165">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2165">Driv Licen</span></span> 
- <span data-ttu-id="ecdf4-2166">Driv License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2166">Driv License</span></span>
- <span data-ttu-id="ecdf4-2167">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2167">Driv Licenses</span></span> 
- <span data-ttu-id="ecdf4-2168">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2168">Driv Licence</span></span> 
- <span data-ttu-id="ecdf4-2169">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2169">Driv Licences</span></span> 
- <span data-ttu-id="ecdf4-2170">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2170">Driv Lic</span></span> 
- <span data-ttu-id="ecdf4-2171">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2171">Driver Licen</span></span> 
- <span data-ttu-id="ecdf4-2172">Driver License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2172">Driver License</span></span> 
- <span data-ttu-id="ecdf4-2173">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2173">Driver Licenses</span></span> 
- <span data-ttu-id="ecdf4-2174">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2174">Driver Licence</span></span> 
- <span data-ttu-id="ecdf4-2175">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2175">Driver Licences</span></span> 
- <span data-ttu-id="ecdf4-2176">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2176">Drivers Lic</span></span> 
- <span data-ttu-id="ecdf4-2177">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2177">Drivers Licen</span></span> 
- <span data-ttu-id="ecdf4-2178">Drivers License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2178">Drivers License</span></span> 
- <span data-ttu-id="ecdf4-2179">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2179">Drivers Licenses</span></span> 
- <span data-ttu-id="ecdf4-2180">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2180">Drivers Licence</span></span> 
- <span data-ttu-id="ecdf4-2181">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2181">Drivers Licences</span></span> 
- <span data-ttu-id="ecdf4-2182">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2182">Driver's Lic</span></span> 
- <span data-ttu-id="ecdf4-2183">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2183">Driver's Licen</span></span> 
- <span data-ttu-id="ecdf4-2184">Driver's License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2184">Driver's License</span></span> 
- <span data-ttu-id="ecdf4-2185">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2185">Driver's Licenses</span></span> 
- <span data-ttu-id="ecdf4-2186">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2186">Driver's Licence</span></span> 
- <span data-ttu-id="ecdf4-2187">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2187">Driver's Licences</span></span> 
- <span data-ttu-id="ecdf4-2188">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2188">Driving Lic</span></span> 
- <span data-ttu-id="ecdf4-2189">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2189">Driving Licen</span></span> 
- <span data-ttu-id="ecdf4-2190">Driving License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2190">Driving License</span></span> 
- <span data-ttu-id="ecdf4-2191">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2191">Driving Licenses</span></span> 
- <span data-ttu-id="ecdf4-2192">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2192">Driving Licence</span></span> 
- <span data-ttu-id="ecdf4-2193">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2193">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="ecdf4-2194">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2194">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="ecdf4-2195">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2195">Nr-Führerschein</span></span> 
- <span data-ttu-id="ecdf4-2196">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2196">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="ecdf4-2197">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2197">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="ecdf4-2198">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2198">No-Führerschein</span></span> 
- <span data-ttu-id="ecdf4-2199">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2199">No-Fuhrerschein</span></span> 
- <span data-ttu-id="ecdf4-2200">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2200">No-Fuehrerschein</span></span> 
- <span data-ttu-id="ecdf4-2201">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2201">N-Führerschein</span></span> 
- <span data-ttu-id="ecdf4-2202">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2202">N-Fuhrerschein</span></span> 
- <span data-ttu-id="ecdf4-2203">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2203">N-Fuehrerschein</span></span>
- <span data-ttu-id="ecdf4-2204">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2204">Nr-Führerschein</span></span> 
- <span data-ttu-id="ecdf4-2205">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2205">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="ecdf4-2206">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2206">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="ecdf4-2207">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2207">No-Führerschein</span></span> 
- <span data-ttu-id="ecdf4-2208">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2208">No-Fuhrerschein</span></span> 
- <span data-ttu-id="ecdf4-2209">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2209">No-Fuehrerschein</span></span> 
- <span data-ttu-id="ecdf4-2210">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2210">N-Führerschein</span></span> 
- <span data-ttu-id="ecdf4-2211">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2211">N-Fuhrerschein</span></span> 
- <span data-ttu-id="ecdf4-2212">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2212">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="ecdf4-2213">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2213">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="ecdf4-2214">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2214">ausstellungsdatum</span></span>
- <span data-ttu-id="ecdf4-2215">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2215">ausstellungsort</span></span>
- <span data-ttu-id="ecdf4-2216">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2216">ausstellende behöde</span></span>
- <span data-ttu-id="ecdf4-2217">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2217">ausstellende behorde</span></span>
- <span data-ttu-id="ecdf4-2218">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2218">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="ecdf4-2219">Germania - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2219">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2220">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2220">Format</span></span>

<span data-ttu-id="ecdf4-2221">10 cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2221">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2222">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2222">Pattern</span></span>

<span data-ttu-id="ecdf4-2223">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2223">Pattern must include all of the following:</span></span>
- <span data-ttu-id="ecdf4-2224">Il primo carattere è una cifra o una lettera del gruppo seguente: C, F, G, H, J, K</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2224">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="ecdf4-2225">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2225">Three digits</span></span> 
- <span data-ttu-id="ecdf4-2226">Cinque cifre o lettere del gruppo seguente: C, -H, J-N, P, R, T, V-Z</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2226">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="ecdf4-2227">Una cifra</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2227">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2228">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2228">Checksum</span></span>

<span data-ttu-id="ecdf4-2229">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2229">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2230">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2230">Definition</span></span>

<span data-ttu-id="ecdf4-2231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2231">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2232">La funzione Func_german_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2232">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2233">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2233">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="ecdf4-2234">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2234">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-2235">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2236">La funzione Func_german_passport_data restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2236">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2237">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2237">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="ecdf4-2238">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2238">The checksum passes.</span></span>

```xml
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2239">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2239">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="ecdf4-2240">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2240">Keyword_german_passport</span></span>

- <span data-ttu-id="ecdf4-2241">reisepass</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2241">reisepass</span></span>
- <span data-ttu-id="ecdf4-2242">reisepasse</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2242">reisepasse</span></span>
- <span data-ttu-id="ecdf4-2243">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2243">reisepassnummer</span></span>
- <span data-ttu-id="ecdf4-2244">passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2244">passport</span></span>
- <span data-ttu-id="ecdf4-2245">passaporti</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2245">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="ecdf4-2246">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2246">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="ecdf4-2247">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2247">geburtsdatum</span></span>
- <span data-ttu-id="ecdf4-2248">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2248">ausstellungsdatum</span></span>
- <span data-ttu-id="ecdf4-2249">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2249">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="ecdf4-2250">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2250">Keyword_german_passport_number</span></span>

<span data-ttu-id="ecdf4-2251">No-Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2251">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="ecdf4-2252">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2252">Keyword_german_passport1</span></span>

<span data-ttu-id="ecdf4-2253">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2253">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="ecdf4-2254">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2254">Keyword_german_passport2</span></span>

<span data-ttu-id="ecdf4-2255">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2255">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="ecdf4-2256">Germania - Numero carta di identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2256">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2257">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2257">Format</span></span>

<span data-ttu-id="ecdf4-2258">Dal 1 ° novembre 2010: nove lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2258">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="ecdf4-2259">Dal 1 ° aprile 1987 al 31 ottobre 2010:10 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2259">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2260">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2260">Pattern</span></span>

<span data-ttu-id="ecdf4-2261">A partire dal 1° novembre 2010:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2261">Since 1 November 2010:</span></span>
- <span data-ttu-id="ecdf4-2262">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2262">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-2263">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2263">Eight digits</span></span>

<span data-ttu-id="ecdf4-2264">Dal 1 ° aprile 1987 al 31 ottobre 2010:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2264">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="ecdf4-2265">10 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2265">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2266">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2266">Checksum</span></span>

<span data-ttu-id="ecdf4-2267">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2267">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2268">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2268">Definition</span></span>

<span data-ttu-id="ecdf4-2269">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2269">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2270">L'espressione regolare Regex_germany_id_card trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2270">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2271">Viene trovata una parola chiave da Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2271">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2272">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2272">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="ecdf4-2273">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2273">Keyword_germany_id_card</span></span>

- <span data-ttu-id="ecdf4-2274">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2274">Identity Card</span></span>
- <span data-ttu-id="ecdf4-2275">ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2275">ID</span></span>
- <span data-ttu-id="ecdf4-2276">Identificazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2276">Identification</span></span>
- <span data-ttu-id="ecdf4-2277">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2277">Personalausweis</span></span>
- <span data-ttu-id="ecdf4-2278">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2278">Identifizierungsnummer</span></span>
- <span data-ttu-id="ecdf4-2279">Ausweis</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2279">Ausweis</span></span>
- <span data-ttu-id="ecdf4-2280">Identifikation</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2280">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="ecdf4-2281">Carta d'identità (Grecia)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2281">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2282">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2282">Format</span></span>

<span data-ttu-id="ecdf4-2283">Combinazione di 7-8 lettere e numeri, oltre a un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2283">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2284">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2284">Pattern</span></span>

<span data-ttu-id="ecdf4-2285">Sette lettere e numeri (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2285">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="ecdf4-2286">Una lettera (qualsiasi lettera dell'alfabeto greco) </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2286">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="ecdf4-2287">Un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2287">A dash</span></span> 
- <span data-ttu-id="ecdf4-2288">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2288">Six digits</span></span>

<span data-ttu-id="ecdf4-2289">Otto lettere e numeri (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2289">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="ecdf4-2290">Due lettere in maiuscolo sia in alfabeto latino che greco (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2290">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="ecdf4-2291">Un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2291">A dash</span></span> 
- <span data-ttu-id="ecdf4-2292">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2292">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2293">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2293">Checksum</span></span>

<span data-ttu-id="ecdf4-2294">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2294">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2295">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2295">Definition</span></span>

<span data-ttu-id="ecdf4-2296">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2297">L'espressione regolare Regex_greece_id_card trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2297">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2298">Viene trovata una parola chiave da Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2298">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2299">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2299">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="ecdf4-2300">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2300">Keyword_greece_id_card</span></span>

- <span data-ttu-id="ecdf4-2301">Carta d’identità greca</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2301">Greek identity Card</span></span>
- <span data-ttu-id="ecdf4-2302">Tautotita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2302">Tautotita</span></span>
- <span data-ttu-id="ecdf4-2303">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2303">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="ecdf4-2304">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2304">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="ecdf4-2305">Hong Kong - Numero di carta di identità (HKID)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2305">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2306">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2306">Format</span></span>

<span data-ttu-id="ecdf4-2307">Combinazione di 8-9 lettere e numeri. Facoltativamente, l’ultimo carattere può essere racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2307">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2308">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2308">Pattern</span></span>

<span data-ttu-id="ecdf4-2309">Combinazione di 8-9 lettere:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2309">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="ecdf4-2310">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2310">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-2311">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2311">Six digits</span></span> 
- <span data-ttu-id="ecdf4-2312">L'ultimo carattere (qualsiasi cifra o la lettera A), è rappresentato dal numero di controllo. Facoltativamente, può essere racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2312">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2313">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2313">Checksum</span></span>

<span data-ttu-id="ecdf4-2314">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2314">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2315">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2315">Definition</span></span>

<span data-ttu-id="ecdf4-2316">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2317">La funzione Func_hong_kong_id_card trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2317">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2318">Viene trovata una parola chiave da Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2318">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="ecdf4-2319">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2319">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-2320">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2320">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2321">La funzione Func_hong_kong_id_card trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2321">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2322">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2322">The checksum passes.</span></span>

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2323">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2323">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="ecdf4-2324">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2324">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="ecdf4-2325">carta di identità di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2325">hong kong identity card</span></span>
- <span data-ttu-id="ecdf4-2326">HKIDC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2326">HKIDC</span></span>
- <span data-ttu-id="ecdf4-2327">id card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2327">id card</span></span>
- <span data-ttu-id="ecdf4-2328">carta di identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2328">identity card</span></span>
- <span data-ttu-id="ecdf4-2329">carta di identità HK</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2329">hk identity card</span></span>
- <span data-ttu-id="ecdf4-2330">ID Hong Kong</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2330">hong kong id</span></span>
- <span data-ttu-id="ecdf4-2331">香港身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2331">香港身份證</span></span>
- <span data-ttu-id="ecdf4-2332">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2332">香港永久性居民身份證</span></span>
- <span data-ttu-id="ecdf4-2333">身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2333">身份證</span></span>
- <span data-ttu-id="ecdf4-2334">身份証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2334">身份証</span></span>
- <span data-ttu-id="ecdf4-2335">身分證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2335">身分證</span></span>
- <span data-ttu-id="ecdf4-2336">身分証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2336">身分証</span></span>
- <span data-ttu-id="ecdf4-2337">香港身份証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2337">香港身份証</span></span>
- <span data-ttu-id="ecdf4-2338">香港身分證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2338">香港身分證</span></span>
- <span data-ttu-id="ecdf4-2339">香港身分証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2339">香港身分証</span></span>
- <span data-ttu-id="ecdf4-2340">香港身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2340">香港身份證</span></span>
- <span data-ttu-id="ecdf4-2341">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2341">香港居民身份證</span></span>
- <span data-ttu-id="ecdf4-2342">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2342">香港居民身份証</span></span>
- <span data-ttu-id="ecdf4-2343">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2343">香港居民身分證</span></span>
- <span data-ttu-id="ecdf4-2344">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2344">香港居民身分証</span></span>
- <span data-ttu-id="ecdf4-2345">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2345">香港永久性居民身份証</span></span>
- <span data-ttu-id="ecdf4-2346">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2346">香港永久性居民身分證</span></span>
- <span data-ttu-id="ecdf4-2347">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2347">香港永久性居民身分証</span></span>
- <span data-ttu-id="ecdf4-2348">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2348">香港永久性居民身份證</span></span>
- <span data-ttu-id="ecdf4-2349">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2349">香港非永久性居民身份證</span></span>
- <span data-ttu-id="ecdf4-2350">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2350">香港非永久性居民身份証</span></span>
- <span data-ttu-id="ecdf4-2351">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2351">香港非永久性居民身分證</span></span>
- <span data-ttu-id="ecdf4-2352">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2352">香港非永久性居民身分証</span></span>
- <span data-ttu-id="ecdf4-2353">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2353">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="ecdf4-2354">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2354">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="ecdf4-2355">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2355">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="ecdf4-2356">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2356">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="ecdf4-2357">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2357">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="ecdf4-2358">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2358">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="ecdf4-2359">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2359">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="ecdf4-2360">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2360">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="ecdf4-2361">India - Numero di conto permanente (PAN)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2361">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2362">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2362">Format</span></span>

<span data-ttu-id="ecdf4-2363">10 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2363">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2364">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2364">Pattern</span></span>

<span data-ttu-id="ecdf4-2365">10 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2365">10 letters or digits:</span></span>
- <span data-ttu-id="ecdf4-2366">Cinque lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2366">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-2367">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2367">Four digits</span></span> 
- <span data-ttu-id="ecdf4-2368">Una lettera, ovvero una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2368">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2369">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2369">Checksum</span></span>

<span data-ttu-id="ecdf4-2370">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2370">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2371">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2371">Definition</span></span>

<span data-ttu-id="ecdf4-2372">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2372">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2373">L'espressione regolare Regex_india_permanent_account_number trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2373">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2374">Viene trovata una parola chiave da Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2374">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="ecdf4-2375">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2375">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2376">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2376">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="ecdf4-2377">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2377">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="ecdf4-2378">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2378">Permanent Account Number</span></span> 
- <span data-ttu-id="ecdf4-2379">PAN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2379">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="ecdf4-2380">India - Numero di identificazione univoco (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2380">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2381">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2381">Format</span></span>

<span data-ttu-id="ecdf4-2382">12 cifre contenenti spazi o trattini facoltativi </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2382">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2383">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2383">Pattern</span></span>

<span data-ttu-id="ecdf4-2384">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2384">12 digits:</span></span>
- <span data-ttu-id="ecdf4-2385">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2385">Four digits</span></span> 
- <span data-ttu-id="ecdf4-2386">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2386">An optional space or dash</span></span> 
- <span data-ttu-id="ecdf4-2387">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2387">Four digits</span></span> 
- <span data-ttu-id="ecdf4-2388">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2388">An optional space or dash</span></span> 
- <span data-ttu-id="ecdf4-2389">L'ultimo carattere, ovvero il numero di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2389">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2390">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2390">Checksum</span></span>

<span data-ttu-id="ecdf4-2391">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2391">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2392">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2392">Definition</span></span>

<span data-ttu-id="ecdf4-2393">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2393">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="ecdf4-2394">Viene trovata una parola chiave da Keyword_india_aadhar.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2394">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="ecdf4-2395">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2395">The checksum passes.</span></span>
<span data-ttu-id="ecdf4-2396">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="ecdf4-2397">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2397">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="ecdf4-2398">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2398">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="ecdf4-2399">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2399">Keyword_india_aadhar</span></span>
- <span data-ttu-id="ecdf4-2400">Aadhar</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2400">Aadhar</span></span>
- <span data-ttu-id="ecdf4-2401">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2401">Aadhaar</span></span>
- <span data-ttu-id="ecdf4-2402">UID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2402">UID</span></span>
- <span data-ttu-id="ecdf4-2403">आधार</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2403">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="ecdf4-2404">Indonesia - Numero di carta di identità (KTP)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2404">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2405">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2405">Format</span></span>

<span data-ttu-id="ecdf4-2406">16 cifre contenenti punti facoltativi </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2406">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2407">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2407">Pattern</span></span>

<span data-ttu-id="ecdf4-2408">16 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2408">16 digits:</span></span>
- <span data-ttu-id="ecdf4-2409">Codice provincia a due cifre </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2409">Two-digit province code</span></span> 
- <span data-ttu-id="ecdf4-2410">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2410">A period (optional)</span></span> 
- <span data-ttu-id="ecdf4-2411">Codice città o area a due cifre </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2411">Two-digit regency or city code</span></span> 
- <span data-ttu-id="ecdf4-2412">Codice sotto-distretto a due cifre </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2412">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="ecdf4-2413">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2413">A period (optional)</span></span> 
- <span data-ttu-id="ecdf4-2414">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2414">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="ecdf4-2415">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2415">A period (optional)</span></span> 
- <span data-ttu-id="ecdf4-2416">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2416">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2417">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2417">Checksum</span></span>

<span data-ttu-id="ecdf4-2418">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2419">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2419">Definition</span></span>

<span data-ttu-id="ecdf4-2420">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2421">L'espressione regolare Regex_indonesia_id_card trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2421">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2422">Viene trovata una parola chiave da Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2422">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="ecdf4-2423">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2423">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2424">L'espressione regolare Regex_indonesia_id_card trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2424">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2425">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2425">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="ecdf4-2426">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2426">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="ecdf4-2427">KTP</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2427">KTP</span></span>
- <span data-ttu-id="ecdf4-2428">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2428">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="ecdf4-2429">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2429">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="ecdf4-2430">Numero di conto bancario internazionale (IBAN)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2430">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2431">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2431">Format</span></span>

<span data-ttu-id="ecdf4-2432">Codice paese (due lettere) più cifre di controllo (due cifre) più numero BBAN (fino a 30 caratteri)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2432">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2433">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2433">Pattern</span></span>

<span data-ttu-id="ecdf4-2434">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2434">Pattern must include all of the following:</span></span>

- <span data-ttu-id="ecdf4-2435">Codice paese a due lettere</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2435">Two-letter country code</span></span>
- <span data-ttu-id="ecdf4-2436">Due cifre di controllo (seguite da uno spazio facoltativo)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2436">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="ecdf4-2437">1-7 gruppi di quattro lettere o cifre (possono essere separati da spazi)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2437">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="ecdf4-2438">1-3 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2438">1-3 letters or digits</span></span>

<span data-ttu-id="ecdf4-2439">Il formato di ogni paese è leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2439">The format for each country is slightly different.</span></span> <span data-ttu-id="ecdf4-2440">Il tipo di informazioni riservate IBAN copre questi 60 paesi:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2440">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="ecdf4-2441">ad, AE, al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, do, EE, es, Fi, fo, fr, GB, GE, Gi, GL, gr, HR, HU, IE, il, is, it, kW, KZ, lb, li, LT, Lu, LV, MC, MD, me, MK, Mr, MT, MU, NL, no, pl, PT, ro, RS, SA, se, si, SK, SM, TN, TR, VG</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2441">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2442">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2442">Checksum</span></span>

<span data-ttu-id="ecdf4-2443">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2443">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2444">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2444">Definition</span></span>

<span data-ttu-id="ecdf4-2445">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2445">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2446">La funzione Func_iban restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2446">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2447">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2447">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2448">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2448">Keywords</span></span>

<span data-ttu-id="ecdf4-2449">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2449">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="ecdf4-2450">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2450">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2451">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2451">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="ecdf4-2452">IPv4</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2452">IPv4:</span></span>
<span data-ttu-id="ecdf4-2453">Modello complesso che rappresenta le versioni formattate (punti) e quelle non formattate (senza punti) degli indirizzi IPv4</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2453">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="ecdf4-2454">IPv6</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2454">IPv6:</span></span>
<span data-ttu-id="ecdf4-2455">Modello complesso che rappresenta i numeri dell'indirizzo IPv6 non formattati (include i due punti)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2455">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2456">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2456">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2457">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2457">Checksum</span></span>

<span data-ttu-id="ecdf4-2458">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2458">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2459">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2459">Definition</span></span>

<span data-ttu-id="ecdf4-2460">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2460">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2461">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2461">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2462">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2462">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="ecdf4-2463">Nel caso di IPv4, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2463">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2464">L'espressione regolare Regex_ipv4_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2464">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2465">Viene trovata una parola chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2465">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="ecdf4-2466">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2466">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2467">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2467">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2468">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2468">No keyword from Keyword_ipaddress is found.</span></span>

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2469">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2469">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="ecdf4-2470">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2470">Keyword_ipaddress</span></span>

- <span data-ttu-id="ecdf4-2471">IP (per questa parola chiave viene fatta distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2471">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="ecdf4-2472">ip address</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2472">ip address</span></span> 
- <span data-ttu-id="ecdf4-2473">Indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2473">ip addresses</span></span>
- <span data-ttu-id="ecdf4-2474">internet protocol</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2474">internet protocol</span></span>
- <span data-ttu-id="ecdf4-2475">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2475">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="ecdf4-2476">Classificazione internazionale delle malattie (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2476">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2477">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2477">Format</span></span>

<span data-ttu-id="ecdf4-2478">Dizionario</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2478">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2479">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2479">Pattern</span></span>

<span data-ttu-id="ecdf4-2480">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2480">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2481">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2481">Checksum</span></span>

<span data-ttu-id="ecdf4-2482">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2482">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2483">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2483">Definition</span></span>

<span data-ttu-id="ecdf4-2484">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2485">Viene trovata una parola chiave da Dictionary_icd_10_updated.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2485">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="ecdf4-2486">Viene trovata una parola chiave da Dictionary_icd_10_codes.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2486">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="ecdf4-2487">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2487">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2488">Viene trovata una parola chiave da Dictionary_icd_10_ aggiornata.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2488">A keyword from Dictionary_icd_10_ updated is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

<span data-ttu-id="ecdf4-2489">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2489">Keywords</span></span>

<span data-ttu-id="ecdf4-2490">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_10_updated, basato sulla [classificazione internazionale delle malattie, la decima revisione, la modifica clinica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2490">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="ecdf4-2491">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2491">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="ecdf4-2492">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_10_codes, basato sulla [classificazione internazionale delle malattie, la decima revisione, la modifica clinica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2492">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="ecdf4-2493">Questo tipo di ricerca è solo per i codici assicurativi, non per la descrizione.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2493">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="ecdf4-2494">Classificazione internazionale delle malattie (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2494">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2495">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2495">Format</span></span>

<span data-ttu-id="ecdf4-2496">Dizionario</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2496">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2497">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2497">Pattern</span></span>

<span data-ttu-id="ecdf4-2498">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2498">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2499">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2499">Checksum</span></span>

<span data-ttu-id="ecdf4-2500">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2500">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2501">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2501">Definition</span></span>

<span data-ttu-id="ecdf4-2502">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2502">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2503">Viene trovata una parola chiave da Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2503">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="ecdf4-2504">Viene trovata una parola chiave da Dictionary_icd_9_codes.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2504">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="ecdf4-2505">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2505">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2506">Viene trovata una parola chiave da Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2506">A keyword from Dictionary_icd_9_updated is found.</span></span>

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2507">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2507">Keywords</span></span>

<span data-ttu-id="ecdf4-2508">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_9_updated, basato sulla [classificazione internazionale delle malattie, la nona revisione, la modifica clinica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2508">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="ecdf4-2509">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2509">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="ecdf4-2510">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_9_codes, basato sulla [classificazione internazionale delle malattie, la nona revisione, la modifica clinica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2510">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="ecdf4-2511">Questo tipo di ricerca è solo per i codici assicurativi, non per la descrizione.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2511">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="ecdf4-2512">Irlanda - Numero personale di servizio pubblico (PPS)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2512">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2513">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2513">Format</span></span>

<span data-ttu-id="ecdf4-2514">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2514">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="ecdf4-2515">Sette cifre seguite da 1-2 lettere </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2515">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="ecdf4-2516">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2516">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="ecdf4-2517">Sette cifre seguite da due lettere</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2517">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2518">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2518">Pattern</span></span>

<span data-ttu-id="ecdf4-2519">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2519">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="ecdf4-2520">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2520">Seven digits</span></span> 
- <span data-ttu-id="ecdf4-2521">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2521">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="ecdf4-2522">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2522">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="ecdf4-2523">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2523">Seven digits</span></span> 
- <span data-ttu-id="ecdf4-2524">Una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo alfabetica </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2524">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="ecdf4-2525">La lettera "A" o "H" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2525">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2526">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2526">Checksum</span></span>

<span data-ttu-id="ecdf4-2527">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2527">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2528">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2528">Definition</span></span>

<span data-ttu-id="ecdf4-2529">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2530">La funzione Func_ireland_pps trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2530">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2531">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2531">One of the following is true:</span></span>
    - <span data-ttu-id="ecdf4-2532">Viene trovata una parola chiave da Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2532">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="ecdf4-2533">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2533">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="ecdf4-2534">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2534">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-2535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2535">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2536">La funzione Func_ireland_pps trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2536">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2537">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2537">The checksum passes.</span></span>

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2538">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="ecdf4-2539">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2539">Keyword_ireland_pps</span></span>

- <span data-ttu-id="ecdf4-2540">Numero personale di servizio pubblico</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2540">Personal Public Service Number</span></span> 
- <span data-ttu-id="ecdf4-2541">Numero PPS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2541">PPS Number</span></span> 
- <span data-ttu-id="ecdf4-2542">Num. PPS
</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2542">PPS Num</span></span> 
- <span data-ttu-id="ecdf4-2543">N° PPS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2543">PPS No.</span></span> 
- <span data-ttu-id="ecdf4-2544">PPS #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2544">PPS #</span></span> 
- <span data-ttu-id="ecdf4-2545">PPS #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2545">PPS#</span></span> 
- <span data-ttu-id="ecdf4-2546">PPSN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2546">PPSN</span></span> 
- <span data-ttu-id="ecdf4-2547">Scheda servizi pubblici</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2547">Public Services Card</span></span> 
- <span data-ttu-id="ecdf4-2548">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2548">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="ecdf4-2549">Uimh.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2549">Uimh.</span></span> <span data-ttu-id="ecdf4-2550">PSP</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2550">PSP</span></span> 
- <span data-ttu-id="ecdf4-2551">PSP</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2551">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="ecdf4-2552">Israele - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2552">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2553">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2553">Format</span></span>

<span data-ttu-id="ecdf4-2554">13 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2554">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2555">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2555">Pattern</span></span>

<span data-ttu-id="ecdf4-2556">Formattato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2556">Formatted:</span></span>
- <span data-ttu-id="ecdf4-2557">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2557">Two digits</span></span> 
- <span data-ttu-id="ecdf4-2558">Un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2558">A dash</span></span> 
- <span data-ttu-id="ecdf4-2559">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2559">Three digits</span></span> 
- <span data-ttu-id="ecdf4-2560">Un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2560">A dash</span></span> 
- <span data-ttu-id="ecdf4-2561">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2561">Eight digits</span></span>

<span data-ttu-id="ecdf4-2562">Formattato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2562">Unformatted:</span></span>
- <span data-ttu-id="ecdf4-2563">13 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2563">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2564">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2564">Checksum</span></span>

<span data-ttu-id="ecdf4-2565">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2565">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2566">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2566">Definition</span></span>

<span data-ttu-id="ecdf4-2567">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2568">L'espressione regolare Regex_israel_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2568">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2569">Viene trovata una parola chiave da Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2569">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2570">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2570">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="ecdf4-2571">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2571">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="ecdf4-2572">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2572">Bank Account Number</span></span> 
- <span data-ttu-id="ecdf4-2573">Bank Account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2573">Bank Account</span></span> 
- <span data-ttu-id="ecdf4-2574">Account Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2574">Account Number</span></span> 
- <span data-ttu-id="ecdf4-2575">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2575">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="ecdf4-2576">Carta di identità (Israele)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2576">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2577">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2577">Format</span></span>

<span data-ttu-id="ecdf4-2578">9 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2578">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2579">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2579">Pattern</span></span>

<span data-ttu-id="ecdf4-2580">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2580">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2581">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2581">Checksum</span></span>

<span data-ttu-id="ecdf4-2582">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2582">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2583">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2583">Definition</span></span>

<span data-ttu-id="ecdf4-2584">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2585">La funzione Func_israeli_national_id_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2585">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2586">Viene trovata una parola chiave da Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2586">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="ecdf4-2587">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2587">The checksum passes.</span></span>

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2588">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2588">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="ecdf4-2589">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2589">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="ecdf4-2590">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2590">מספר זהות</span></span> 
- <span data-ttu-id="ecdf4-2591">National ID Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2591">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="ecdf4-2592">Italia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2592">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2593">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2593">Format</span></span>

<span data-ttu-id="ecdf4-2594">Una combinazione di 10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2594">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2595">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2595">Pattern</span></span>

- <span data-ttu-id="ecdf4-2596">Una combinazione di 10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2596">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="ecdf4-2597">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2597">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-2598">La lettera "A" o "V" (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2598">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-2599">7 lettere (senza distinzione tra maiuscole/minuscole), cifre o carattere di sottolineatura</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2599">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="ecdf4-2600">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2600">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2601">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2601">Checksum</span></span>

<span data-ttu-id="ecdf4-2602">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2602">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2603">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2603">Definition</span></span>

<span data-ttu-id="ecdf4-2604">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2604">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2605">L'espressione regolare Regex_italy_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2605">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2606">Viene trovata una parola chiave da Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2606">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2607">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2607">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="ecdf4-2608">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2608">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="ecdf4-2609">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2609">numero di patente di guida</span></span> 
- <span data-ttu-id="ecdf4-2610">patente di guida</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2610">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="ecdf4-2611">Giappone - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2611">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2612">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2612">Format</span></span>

<span data-ttu-id="ecdf4-2613">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2613">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2614">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2614">Pattern</span></span>

<span data-ttu-id="ecdf4-2615">Numero di conto corrente:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2615">Bank account number:</span></span>
- <span data-ttu-id="ecdf4-2616">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2616">Seven or eight digits</span></span>
- <span data-ttu-id="ecdf4-2617">Codice della filiale del conto corrente:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2617">Bank account branch code:</span></span>
- <span data-ttu-id="ecdf4-2618">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2618">Four digits</span></span> 
- <span data-ttu-id="ecdf4-2619">Uno spazio o un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2619">A space or dash (optional)</span></span> 
- <span data-ttu-id="ecdf4-2620">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2620">Three digits</span></span>

<span data-ttu-id="ecdf4-2621">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2621">Checksum</span></span>

<span data-ttu-id="ecdf4-2622">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2622">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2623">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2623">Definition</span></span>

<span data-ttu-id="ecdf4-2624">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2625">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2625">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2626">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2626">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="ecdf4-2627">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2627">One of the following is true:</span></span>
- <span data-ttu-id="ecdf4-2628">La funzione Func_jp_bank_account_branch_code restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2628">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2629">Viene trovata una parola chiave da Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2629">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="ecdf4-2630">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2630">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2631">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2631">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2632">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2632">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2633">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2633">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="ecdf4-2634">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2634">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="ecdf4-2635">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2635">Checking Account Number</span></span> 
- <span data-ttu-id="ecdf4-2636">Checking Account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2636">Checking Account</span></span> 
- <span data-ttu-id="ecdf4-2637">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2637">Checking Account #</span></span> 
- <span data-ttu-id="ecdf4-2638">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2638">Checking Acct Number</span></span> 
- <span data-ttu-id="ecdf4-2639">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2639">Checking Acct #</span></span> 
- <span data-ttu-id="ecdf4-2640">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2640">Checking Acct No.</span></span> 
- <span data-ttu-id="ecdf4-2641">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2641">Checking Account No.</span></span> 
- <span data-ttu-id="ecdf4-2642">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2642">Bank Account Number</span></span> 
- <span data-ttu-id="ecdf4-2643">Bank Account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2643">Bank Account</span></span> 
- <span data-ttu-id="ecdf4-2644">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2644">Bank Account #</span></span> 
- <span data-ttu-id="ecdf4-2645">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2645">Bank Acct Number</span></span> 
- <span data-ttu-id="ecdf4-2646">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2646">Bank Acct #</span></span> 
- <span data-ttu-id="ecdf4-2647">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2647">Bank Acct No.</span></span> 
- <span data-ttu-id="ecdf4-2648">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2648">Bank Account No.</span></span> 
- <span data-ttu-id="ecdf4-2649">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2649">Savings Account Number</span></span> 
- <span data-ttu-id="ecdf4-2650">Savings Account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2650">Savings Account</span></span> 
- <span data-ttu-id="ecdf4-2651">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2651">Savings Account #</span></span> 
- <span data-ttu-id="ecdf4-2652">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2652">Savings Acct Number</span></span> 
- <span data-ttu-id="ecdf4-2653">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2653">Savings Acct #</span></span> 
- <span data-ttu-id="ecdf4-2654">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2654">Savings Acct No.</span></span> 
- <span data-ttu-id="ecdf4-2655">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2655">Savings Account No.</span></span> 
- <span data-ttu-id="ecdf4-2656">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2656">Debit Account Number</span></span> 
- <span data-ttu-id="ecdf4-2657">Debit Account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2657">Debit Account</span></span> 
- <span data-ttu-id="ecdf4-2658">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2658">Debit Account #</span></span> 
- <span data-ttu-id="ecdf4-2659">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2659">Debit Acct Number</span></span> 
- <span data-ttu-id="ecdf4-2660">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2660">Debit Acct #</span></span> 
- <span data-ttu-id="ecdf4-2661">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2661">Debit Acct No.</span></span> 
- <span data-ttu-id="ecdf4-2662">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2662">Debit Account No.</span></span> 
- <span data-ttu-id="ecdf4-2663">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2663">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="ecdf4-2664">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2664">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="ecdf4-2665">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2665">＃勘定の確認</span></span> 
- <span data-ttu-id="ecdf4-2666">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2666">勘定番号の確認</span></span> 
- <span data-ttu-id="ecdf4-2667">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2667">口座番号の確認</span></span> 
- <span data-ttu-id="ecdf4-2668">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2668">銀行口座番号</span></span> 
- <span data-ttu-id="ecdf4-2669">銀行口座</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2669">銀行口座</span></span> 
- <span data-ttu-id="ecdf4-2670">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2670">銀行口座＃</span></span> 
- <span data-ttu-id="ecdf4-2671">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2671">銀行の勘定番号</span></span> 
- <span data-ttu-id="ecdf4-2672">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2672">銀行のacct＃</span></span> 
- <span data-ttu-id="ecdf4-2673">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2673">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="ecdf4-2674">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2674">銀行口座番号</span></span>
- <span data-ttu-id="ecdf4-2675">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2675">普通預金口座番号</span></span> 
- <span data-ttu-id="ecdf4-2676">預金口座</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2676">預金口座</span></span> 
- <span data-ttu-id="ecdf4-2677">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2677">貯蓄口座＃</span></span> 
- <span data-ttu-id="ecdf4-2678">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2678">貯蓄勘定の数</span></span> 
- <span data-ttu-id="ecdf4-2679">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2679">貯蓄勘定＃</span></span> 
- <span data-ttu-id="ecdf4-2680">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2680">貯蓄勘定番号</span></span> 
- <span data-ttu-id="ecdf4-2681">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2681">普通預金口座番号</span></span> 
- <span data-ttu-id="ecdf4-2682">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2682">引き落とし口座番号</span></span> 
- <span data-ttu-id="ecdf4-2683">口座番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2683">口座番号</span></span> 
- <span data-ttu-id="ecdf4-2684">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2684">口座番号＃</span></span> 
- <span data-ttu-id="ecdf4-2685">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2685">デビットのacct番号</span></span> 
- <span data-ttu-id="ecdf4-2686">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2686">デビット勘定＃</span></span> 
- <span data-ttu-id="ecdf4-2687">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2687">デビットACCTの番号</span></span> 
- <span data-ttu-id="ecdf4-2688">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2688">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="ecdf4-2689">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2689">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="ecdf4-2690">Otemachi</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2690">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="ecdf4-2691">Giappone - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2691">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2692">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2692">Format</span></span>

<span data-ttu-id="ecdf4-2693">12 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2693">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2694">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2694">Pattern</span></span>

<span data-ttu-id="ecdf4-2695">12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2695">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2696">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2696">Checksum</span></span>

<span data-ttu-id="ecdf4-2697">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2697">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2698">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2698">Definition</span></span>

<span data-ttu-id="ecdf4-2699">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2699">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2700">La funzione Func_jp_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2700">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2701">Viene trovata una parola chiave da Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2701">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2702">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2702">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="ecdf4-2703">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2703">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="ecdf4-2704">DL #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2704">dl#</span></span> 
- <span data-ttu-id="ecdf4-2705">DL</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2705">DL＃</span></span> 
- <span data-ttu-id="ecdf4-2706">DLS #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2706">dls#</span></span> 
- <span data-ttu-id="ecdf4-2707">DLS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2707">DLS＃</span></span> 
- <span data-ttu-id="ecdf4-2708">driver license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2708">driver license</span></span> 
- <span data-ttu-id="ecdf4-2709">driver licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2709">driver licenses</span></span> 
- <span data-ttu-id="ecdf4-2710">drivers license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2710">drivers license</span></span> 
- <span data-ttu-id="ecdf4-2711">driver's license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2711">driver's license</span></span> 
- <span data-ttu-id="ecdf4-2712">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2712">drivers licenses</span></span> 
- <span data-ttu-id="ecdf4-2713">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2713">driver's licenses</span></span> 
- <span data-ttu-id="ecdf4-2714">driving licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2714">driving licence</span></span> 
- <span data-ttu-id="ecdf4-2715">driver'lic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2715">lic#</span></span> 
- <span data-ttu-id="ecdf4-2716">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2716">LIC＃</span></span> 
- <span data-ttu-id="ecdf4-2717">driver'lics #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2717">lics#</span></span> 
- <span data-ttu-id="ecdf4-2718">state id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2718">state id</span></span> 
- <span data-ttu-id="ecdf4-2719">state identification</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2719">state identification</span></span> 
- <span data-ttu-id="ecdf4-2720">state identification number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2720">state identification number</span></span> 
- <span data-ttu-id="ecdf4-2721">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2721">低所得国＃</span></span> 
- <span data-ttu-id="ecdf4-2722">免許証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2722">免許証</span></span> 
- <span data-ttu-id="ecdf4-2723">状態ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2723">状態ID</span></span>
- <span data-ttu-id="ecdf4-2724">状態の識別</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2724">状態の識別</span></span> 
- <span data-ttu-id="ecdf4-2725">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2725">状態の識別番号</span></span> 
- <span data-ttu-id="ecdf4-2726">運転免許</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2726">運転免許</span></span> 
- <span data-ttu-id="ecdf4-2727">運転免許証</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2727">運転免許証</span></span> 
- <span data-ttu-id="ecdf4-2728">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2728">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="ecdf4-2729">Giappone - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2729">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2730">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2730">Format</span></span>

<span data-ttu-id="ecdf4-2731">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2731">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2732">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2732">Pattern</span></span>

<span data-ttu-id="ecdf4-2733">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2733">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2734">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2734">Checksum</span></span>

<span data-ttu-id="ecdf4-2735">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2736">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2736">Definition</span></span>

<span data-ttu-id="ecdf4-2737">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2737">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2738">La funzione Func_jp_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2738">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2739">Viene trovata una parola chiave da Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2739">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2740">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2740">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="ecdf4-2741">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2741">Keyword_jp_passport</span></span>

- <span data-ttu-id="ecdf4-2742">パスポート</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2742">パスポート</span></span> 
- <span data-ttu-id="ecdf4-2743">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2743">パスポート番号</span></span> 
- <span data-ttu-id="ecdf4-2744">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2744">パスポートのNum</span></span> 
- <span data-ttu-id="ecdf4-2745">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2745">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="ecdf4-2746">Giappone - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2746">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2747">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2747">Format</span></span>

<span data-ttu-id="ecdf4-2748">11 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2748">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2749">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2749">Pattern</span></span>

<span data-ttu-id="ecdf4-2750">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2750">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2751">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2751">Checksum</span></span>

<span data-ttu-id="ecdf4-2752">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2752">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2753">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2753">Definition</span></span>

<span data-ttu-id="ecdf4-2754">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2755">La funzione Func_jp_resident_registration_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2755">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2756">Viene trovata una parola chiave da Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2756">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2757">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2757">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="ecdf4-2758">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2758">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="ecdf4-2759">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2759">Resident Registration Number</span></span>
- <span data-ttu-id="ecdf4-2760">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2760">Resident Register Number</span></span> 
- <span data-ttu-id="ecdf4-2761">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2761">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="ecdf4-2762">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2762">Resident Registration No.</span></span> 
- <span data-ttu-id="ecdf4-2763">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2763">Resident Register No.</span></span> 
- <span data-ttu-id="ecdf4-2764">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2764">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="ecdf4-2765">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2765">Basic Resident Register No.</span></span> 
- <span data-ttu-id="ecdf4-2766">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2766">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="ecdf4-2767">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2767">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="ecdf4-2768">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2768">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="ecdf4-2769">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2769">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="ecdf4-2770">Giappone - Numero di assicurazione sociale (SIN)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2770">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2771">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2771">Format</span></span>

<span data-ttu-id="ecdf4-2772">7-12 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2772">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2773">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2773">Pattern</span></span>

<span data-ttu-id="ecdf4-2774">7-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2774">7-12 digits:</span></span>
- <span data-ttu-id="ecdf4-2775">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2775">Four digits</span></span> 
- <span data-ttu-id="ecdf4-2776">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2776">A hyphen (optional)</span></span> 
- <span data-ttu-id="ecdf4-2777">Sei cifre o</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2777">Six digits OR</span></span>
- <span data-ttu-id="ecdf4-2778">7-12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2778">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2779">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2779">Checksum</span></span>

<span data-ttu-id="ecdf4-2780">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2780">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2781">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2781">Definition</span></span>

<span data-ttu-id="ecdf4-2782">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2782">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2783">La funzione Func_jp_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2783">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2784">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2784">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="ecdf4-2785">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2785">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2786">La funzione Func_jp_sin_pre_1997 restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2786">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2787">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2787">A keyword from Keyword_jp_sin is found.</span></span>

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2788">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2788">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="ecdf4-2789">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2789">Keyword_jp_sin</span></span>

- <span data-ttu-id="ecdf4-2790">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2790">Social Insurance No.</span></span> 
- <span data-ttu-id="ecdf4-2791">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2791">Social Insurance Num</span></span> 
- <span data-ttu-id="ecdf4-2792">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2792">Social Insurance Number</span></span> 
- <span data-ttu-id="ecdf4-2793">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2793">社会保険のテンキー</span></span> 
- <span data-ttu-id="ecdf4-2794">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2794">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="ecdf4-2795">Numero di carta di soggiorno giapponese</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2795">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2796">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2796">Format</span></span>

<span data-ttu-id="ecdf4-2797">12 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2797">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2798">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2798">Pattern</span></span>

<span data-ttu-id="ecdf4-2799">12 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2799">12 letters and digits:</span></span>
- <span data-ttu-id="ecdf4-2800">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2800">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="ecdf4-2801">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2801">Eight digits</span></span> 
- <span data-ttu-id="ecdf4-2802">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2802">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2803">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2803">Checksum</span></span>

<span data-ttu-id="ecdf4-2804">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2804">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2805">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2805">Definition</span></span>

<span data-ttu-id="ecdf4-2806">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2807">L'espressione regolare Regex_jp_residence_card_number trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2807">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2808">Viene trovata una parola chiave da Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2808">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2809">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2809">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="ecdf4-2810">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2810">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="ecdf4-2811">Numero di carta di soggiorno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2811">Residence card number</span></span>
- <span data-ttu-id="ecdf4-2812">Carta di soggiorno No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2812">Residence card no</span></span>
- <span data-ttu-id="ecdf4-2813">Carta di soggiorno #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2813">Residence card #</span></span>
- <span data-ttu-id="ecdf4-2814">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2814">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="ecdf4-2815">Malesia - Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2815">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2816">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2816">Format</span></span>

<span data-ttu-id="ecdf4-2817">12 cifre contenenti lineette facoltative</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2817">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2818">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2818">Pattern</span></span>

<span data-ttu-id="ecdf4-2819">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2819">12 digits:</span></span>
- <span data-ttu-id="ecdf4-2820">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2820">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="ecdf4-2821">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2821">A dash (optional)</span></span> 
- <span data-ttu-id="ecdf4-2822">Codice luogo di nascita a due lettere </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2822">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="ecdf4-2823">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2823">A dash (optional)</span></span> 
- <span data-ttu-id="ecdf4-2824">Tre cifre casuali </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2824">Three random digits</span></span> 
- <span data-ttu-id="ecdf4-2825">Codice genere a una cifra singola</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2825">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2826">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2826">Checksum</span></span>

<span data-ttu-id="ecdf4-2827">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2827">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2828">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2828">Definition</span></span>

<span data-ttu-id="ecdf4-2829">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2829">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2830">L'espressione regolare Regex_malaysia_id_card_number trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2830">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2831">Viene trovata una parola chiave da Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2831">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2832">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2832">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="ecdf4-2833">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2833">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="ecdf4-2834">scheda dell'applicazione digitale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2834">digital application card</span></span>
- <span data-ttu-id="ecdf4-2835">i/c</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2835">i/c</span></span>
- <span data-ttu-id="ecdf4-2836">i/c no</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2836">i/c no</span></span>
- <span data-ttu-id="ecdf4-2837">IC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2837">ic</span></span>
- <span data-ttu-id="ecdf4-2838">IC No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2838">ic no</span></span>
- <span data-ttu-id="ecdf4-2839">id card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2839">id card</span></span>
- <span data-ttu-id="ecdf4-2840">Scheda di identificazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2840">identification Card</span></span>
- <span data-ttu-id="ecdf4-2841">carta di identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2841">identity card</span></span>
- <span data-ttu-id="ecdf4-2842">k/p</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2842">k/p</span></span>
- <span data-ttu-id="ecdf4-2843">k/p no</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2843">k/p no</span></span>
- <span data-ttu-id="ecdf4-2844">diri akuan Kad</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2844">kad akuan diri</span></span>
- <span data-ttu-id="ecdf4-2845">Kad Aplikasi digitale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2845">kad aplikasi digital</span></span>
- <span data-ttu-id="ecdf4-2846">Kad Pengenalan Malaysia</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2846">kad pengenalan malaysia</span></span>
- <span data-ttu-id="ecdf4-2847">KP</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2847">kp</span></span>
- <span data-ttu-id="ecdf4-2848">KP No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2848">kp no</span></span>
- <span data-ttu-id="ecdf4-2849">MyKad</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2849">mykad</span></span>
- <span data-ttu-id="ecdf4-2850">MYKAS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2850">mykas</span></span>
- <span data-ttu-id="ecdf4-2851">mykid</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2851">mykid</span></span>
- <span data-ttu-id="ecdf4-2852">mypr</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2852">mypr</span></span>
- <span data-ttu-id="ecdf4-2853">mytentera</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2853">mytentera</span></span>
- <span data-ttu-id="ecdf4-2854">carta di identità Malaysia</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2854">malaysia identity card</span></span>
- <span data-ttu-id="ecdf4-2855">carta di identità malaysiana</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2855">malaysian identity card</span></span>
- <span data-ttu-id="ecdf4-2856">NRIC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2856">nric</span></span>
- <span data-ttu-id="ecdf4-2857">scheda di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2857">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="ecdf4-2858">Paesi Bassi - Numero di servizio cittadino (BSN)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2858">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2859">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2859">Format</span></span>

<span data-ttu-id="ecdf4-2860">8-9 cifre contenenti spazi facoltativi </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2860">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2861">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2861">Pattern</span></span>

<span data-ttu-id="ecdf4-2862">8-9 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2862">8-9 digits:</span></span>
- <span data-ttu-id="ecdf4-2863">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2863">Three digits</span></span> 
- <span data-ttu-id="ecdf4-2864">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2864">A space (optional)</span></span> 
- <span data-ttu-id="ecdf4-2865">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2865">Three digits</span></span> 
- <span data-ttu-id="ecdf4-2866">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2866">A space (optional)</span></span> 
- <span data-ttu-id="ecdf4-2867">2-3 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2867">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2868">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2868">Checksum</span></span>

<span data-ttu-id="ecdf4-2869">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2869">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2870">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2870">Definition</span></span>

<span data-ttu-id="ecdf4-2871">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2871">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2872">La funzione Func_netherlands_bsn trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2872">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2873">Viene trovata una parola chiave da Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2873">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="ecdf4-2874">La funzione Func_eu_date2 trova una data nel formato di data appropriato.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2874">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="ecdf4-2875">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2875">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2876">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2876">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="ecdf4-2877">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2877">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="ecdf4-2878">Numero di servizio cittadino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2878">Citizen service number</span></span> 
- <span data-ttu-id="ecdf4-2879">BSN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2879">BSN</span></span> 
- <span data-ttu-id="ecdf4-2880">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2880">Burgerservicenummer</span></span> 
- <span data-ttu-id="ecdf4-2881">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2881">Sofinummer</span></span> 
- <span data-ttu-id="ecdf4-2882">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2882">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="ecdf4-2883">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2883">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="ecdf4-2884">Nuova Zelanda - Numero del Ministero della Sanità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2884">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2885">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2885">Format</span></span>

<span data-ttu-id="ecdf4-2886">Tre lettere, uno spazio (facoltativo) e quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2886">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2887">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2887">Pattern</span></span>

<span data-ttu-id="ecdf4-2888">Tre lettere (senza distinzione tra maiuscole/minuscole) uno spazio (facoltativo) quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2888">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2889">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2889">Checksum</span></span>

<span data-ttu-id="ecdf4-2890">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2890">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2891">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2891">Definition</span></span>

<span data-ttu-id="ecdf4-2892">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2892">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2893">La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2893">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2894">Viene trovata una parola chiave da Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2894">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="ecdf4-2895">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2895">The checksum passes.</span></span>

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="ecdf4-2896">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2896">Keywords</span></span>

<span data-ttu-id="ecdf4-2897">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2897">Keyword_nz_terms</span></span>

- <span data-ttu-id="ecdf4-2898">NHI</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2898">NHI</span></span> 
- <span data-ttu-id="ecdf4-2899">New Zealand</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2899">New Zealand</span></span> 
- <span data-ttu-id="ecdf4-2900">Sanità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2900">Health</span></span> 
- <span data-ttu-id="ecdf4-2901">trattamento</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2901">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="ecdf4-2902">Norvegia - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2902">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2903">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2903">Format</span></span>

<span data-ttu-id="ecdf4-2904">11 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2904">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2905">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2905">Pattern</span></span>

<span data-ttu-id="ecdf4-2906">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2906">11 digits:</span></span>
- <span data-ttu-id="ecdf4-2907">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2907">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="ecdf4-2908">Numero individuale composto da tre cifre </span><span class="sxs-lookup"><span data-stu-id="ecdf4-2908">Three-digit individual number</span></span> 
- <span data-ttu-id="ecdf4-2909">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2909">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2910">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2910">Checksum</span></span>

<span data-ttu-id="ecdf4-2911">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2912">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2912">Definition</span></span>

<span data-ttu-id="ecdf4-2913">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2913">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2914">La funzione Func_norway_id_number trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2914">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2915">Viene trovata una parola chiave da Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2915">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="ecdf4-2916">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2916">The checksum passes.</span></span>
- <span data-ttu-id="ecdf4-2917">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2917">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2918">La funzione Func_norway_id_numbe trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2918">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2919">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2919">The checksum passes.</span></span>

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2920">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2920">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="ecdf4-2921">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2921">Keyword_norway_id_number</span></span>

- <span data-ttu-id="ecdf4-2922">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2922">Personal identification number</span></span>
- <span data-ttu-id="ecdf4-2923">Numero ID norvegese</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2923">Norwegian ID Number</span></span>
- <span data-ttu-id="ecdf4-2924">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2924">ID Number</span></span>
- <span data-ttu-id="ecdf4-2925">Identificazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2925">Identification</span></span>
- <span data-ttu-id="ecdf4-2926">Personnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2926">Personnummer</span></span>
- <span data-ttu-id="ecdf4-2927">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2927">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="ecdf4-2928">Filippine - Numero ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2928">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2929">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2929">Format</span></span>

<span data-ttu-id="ecdf4-2930">12 cifre separate da dei segni meno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2930">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2931">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2931">Pattern</span></span>

<span data-ttu-id="ecdf4-2932">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2932">12 digits:</span></span>
- <span data-ttu-id="ecdf4-2933">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2933">Four digits</span></span> 
- <span data-ttu-id="ecdf4-2934">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2934">A hyphen</span></span> 
- <span data-ttu-id="ecdf4-2935">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2935">Seven digits</span></span> 
- <span data-ttu-id="ecdf4-2936">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2936">A hyphen</span></span> 
- <span data-ttu-id="ecdf4-2937">Una cifra</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2937">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2938">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2938">Checksum</span></span>

<span data-ttu-id="ecdf4-2939">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2939">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2940">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2940">Definition</span></span>

<span data-ttu-id="ecdf4-2941">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2942">L'espressione regolare Regex_philippines_unified_id trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2942">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2943">Viene trovata una parola chiave da Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2943">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2944">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2944">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="ecdf4-2945">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2945">Keyword_philippines_id</span></span>

- <span data-ttu-id="ecdf4-2946">ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2946">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="ecdf4-2947">UMID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2947">UMID</span></span> 
- <span data-ttu-id="ecdf4-2948">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2948">Identity Card</span></span> 
- <span data-ttu-id="ecdf4-2949">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2949">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="ecdf4-2950">Carta di identita - Polonia</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2950">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2951">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2951">Format</span></span>

<span data-ttu-id="ecdf4-2952">Tre lettere e sei cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2952">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2953">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2953">Pattern</span></span>

<span data-ttu-id="ecdf4-2954">Tre lettere (senza distinzione tra maiuscole/minuscole) seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2954">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2955">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2955">Checksum</span></span>

<span data-ttu-id="ecdf4-2956">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2956">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2957">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2957">Definition</span></span>

<span data-ttu-id="ecdf4-2958">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_polish_national_id trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2958">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="ecdf4-2959">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2959">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="ecdf4-2960">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2960">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2961">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2961">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="ecdf4-2962">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2962">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="ecdf4-2963">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2963">Dowód osobisty</span></span>
- <span data-ttu-id="ecdf4-2964">Numero dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2964">Numer dowodu osobistego</span></span>
- <span data-ttu-id="ecdf4-2965">Nazwa i numeri dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2965">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="ecdf4-2966">Nazwa i Nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2966">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="ecdf4-2967">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2967">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="ecdf4-2968">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2968">Dowód Tożsamości</span></span>
- <span data-ttu-id="ecdf4-2969">Dow.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2969">dow.</span></span> <span data-ttu-id="ecdf4-2970">OS.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2970">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="ecdf4-2971">ID nazionale Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2971">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2972">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2972">Format</span></span>

<span data-ttu-id="ecdf4-2973">11 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2973">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2974">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2974">Pattern</span></span>

<span data-ttu-id="ecdf4-2975">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2975">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2976">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2976">Checksum</span></span>

<span data-ttu-id="ecdf4-2977">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2977">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2978">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2978">Definition</span></span>

<span data-ttu-id="ecdf4-2979">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2979">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2980">La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2980">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2981">Viene trovata una parola chiave da Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2981">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="ecdf4-2982">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2982">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2983">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2983">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="ecdf4-2984">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2984">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="ecdf4-2985">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2985">Nr PESEL</span></span>
- <span data-ttu-id="ecdf4-2986">PESEL</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2986">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="ecdf4-2987">Passaporto Polonia</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2987">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-2988">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2988">Format</span></span>

<span data-ttu-id="ecdf4-2989">Due lettere e sette cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2989">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-2990">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2990">Pattern</span></span>

<span data-ttu-id="ecdf4-2991">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2991">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-2992">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2992">Checksum</span></span>

<span data-ttu-id="ecdf4-2993">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2993">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-2994">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2994">Definition</span></span>

<span data-ttu-id="ecdf4-2995">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2995">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-2996">La funzione Func_polish_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2996">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-2997">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2997">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="ecdf4-2998">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2998">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-2999">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-2999">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="ecdf4-3000">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3000">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="ecdf4-3001">Numero Paszportu</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3001">Numer paszportu</span></span>
- <span data-ttu-id="ecdf4-3002">Nr.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3002">Nr.</span></span> <span data-ttu-id="ecdf4-3003">Paszportu</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3003">Paszportu</span></span>
- <span data-ttu-id="ecdf4-3004">Paszport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3004">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="ecdf4-3005">Portogallo - Numero di carta del cittadino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3005">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3006">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3006">Format</span></span>

<span data-ttu-id="ecdf4-3007">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3007">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3008">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3008">Pattern</span></span>

<span data-ttu-id="ecdf4-3009">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3009">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3010">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3010">Checksum</span></span>

<span data-ttu-id="ecdf4-3011">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3011">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3012">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3012">Definition</span></span>

<span data-ttu-id="ecdf4-3013">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3013">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3014">L'espressione regolare Regex_portugal_citizen_card trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3014">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3015">Viene trovata una parola chiave da Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3015">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3016">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3016">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="ecdf4-3017">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3017">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="ecdf4-3018">Scheda cittadino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3018">Citizen Card</span></span>
- <span data-ttu-id="ecdf4-3019">Carta ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3019">National ID Card</span></span>
- <span data-ttu-id="ecdf4-3020">CC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3020">CC</span></span>
- <span data-ttu-id="ecdf4-3021">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3021">Cartão de Cidadão</span></span>
- <span data-ttu-id="ecdf4-3022">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3022">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="ecdf4-3023">Arabia Saudita - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3023">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3024">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3024">Format</span></span>

<span data-ttu-id="ecdf4-3025">10 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3025">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3026">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3026">Pattern</span></span>

<span data-ttu-id="ecdf4-3027">10 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3027">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3028">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3028">Checksum</span></span>

<span data-ttu-id="ecdf4-3029">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3029">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3030">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3030">Definition</span></span>

<span data-ttu-id="ecdf4-3031">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3031">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3032">L'espressione regolare Regex_saudi_arabia_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3032">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3033">Viene trovata una parola chiave da Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3033">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3034">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3034">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="ecdf4-3035">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3035">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="ecdf4-3036">Identification Card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3036">Identification Card</span></span> 
- <span data-ttu-id="ecdf4-3037">I card number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3037">I card number</span></span> 
- <span data-ttu-id="ecdf4-3038">ID number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3038">ID number</span></span> 
- <span data-ttu-id="ecdf4-3039">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3039">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="ecdf4-3040">Singapore - Numero di carta di identità di registrazione nazionale (NRIC)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3040">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3041">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3041">Format</span></span>

<span data-ttu-id="ecdf4-3042">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3042">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3043">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3043">Pattern</span></span>

- <span data-ttu-id="ecdf4-3044">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3044">Nine letters and digits:</span></span>
- <span data-ttu-id="ecdf4-3045">La lettera "F", "G", "S" o "T" (senza distinzione tra maiuscole e minuscole) </span><span class="sxs-lookup"><span data-stu-id="ecdf4-3045">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-3046">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3046">Seven digits</span></span> 
- <span data-ttu-id="ecdf4-3047">Una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3047">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3048">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3048">Checksum</span></span>

<span data-ttu-id="ecdf4-3049">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3049">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3050">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3050">Definition</span></span>

<span data-ttu-id="ecdf4-3051">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3051">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3052">L'espressione regolare Regex_singapore_nric trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3052">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3053">Viene trovata una parola chiave da Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3053">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="ecdf4-3054">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3054">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-3055">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3055">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3056">L'espressione regolare Regex_singapore_nric trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3056">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3057">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3057">The checksum passes.</span></span>

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3058">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3058">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="ecdf4-3059">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3059">Keyword_singapore_nric</span></span>

- <span data-ttu-id="ecdf4-3060">Carta di identità di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3060">National Registration Identity Card</span></span> 
- <span data-ttu-id="ecdf4-3061">Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3061">Identity Card Number</span></span> 
- <span data-ttu-id="ecdf4-3062">NRIC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3062">NRIC</span></span> 
- <span data-ttu-id="ecdf4-3063">IC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3063">IC</span></span> 
- <span data-ttu-id="ecdf4-3064">Numero di identificazione per stranieri</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3064">Foreign Identification Number</span></span> 
- <span data-ttu-id="ecdf4-3065">FIN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3065">FIN</span></span> 
- <span data-ttu-id="ecdf4-3066">身份证</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3066">身份证</span></span> 
- <span data-ttu-id="ecdf4-3067">身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3067">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="ecdf4-3068">Sudafrica - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3068">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3069">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3069">Format</span></span>

<span data-ttu-id="ecdf4-3070">13 cifre che possono contenere spazi</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3070">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3071">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3071">Pattern</span></span>

<span data-ttu-id="ecdf4-3072">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3072">13 digits:</span></span>
- <span data-ttu-id="ecdf4-3073">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3073">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="ecdf4-3074">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3074">Four digits</span></span> 
- <span data-ttu-id="ecdf4-3075">Un indicatore di cittadinanza a una cifra </span><span class="sxs-lookup"><span data-stu-id="ecdf4-3075">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="ecdf4-3076">La cifra "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="ecdf4-3076">The digit "8" or "9"</span></span> 
- <span data-ttu-id="ecdf4-3077">Una cifra, ovvero una cifra di checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3077">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3078">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3078">Checksum</span></span>

<span data-ttu-id="ecdf4-3079">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3079">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3080">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3080">Definition</span></span>

<span data-ttu-id="ecdf4-3081">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3081">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3082">La funzione Func_south_africa_identification_number trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3082">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3083">Viene trovata una parola chiave da Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3083">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="ecdf4-3084">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3084">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3085">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3085">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="ecdf4-3086">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3086">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="ecdf4-3087">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3087">Identity card</span></span>
- <span data-ttu-id="ecdf4-3088">ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3088">ID</span></span>
- <span data-ttu-id="ecdf4-3089">Identificazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3089">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="ecdf4-3090">Corea del Sud - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3090">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3091">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3091">Format</span></span>

<span data-ttu-id="ecdf4-3092">13 cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3092">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3093">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3093">Pattern</span></span>

<span data-ttu-id="ecdf4-3094">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3094">13 digits:</span></span>
- <span data-ttu-id="ecdf4-3095">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3095">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="ecdf4-3096">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3096">A hyphen</span></span> 
- <span data-ttu-id="ecdf4-3097">Una cifra determinata dal secolo e dal sesso </span><span class="sxs-lookup"><span data-stu-id="ecdf4-3097">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="ecdf4-3098">Codice di quattro cifre dell’area geografica di nascita </span><span class="sxs-lookup"><span data-stu-id="ecdf4-3098">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="ecdf4-3099">Una cifra utilizzata per distinguere persone i cui numeri precedenti sono uguali </span><span class="sxs-lookup"><span data-stu-id="ecdf4-3099">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="ecdf4-3100">Una cifra di controllo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3100">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3101">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3101">Checksum</span></span>

<span data-ttu-id="ecdf4-3102">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3102">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3103">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3103">Definition</span></span>

<span data-ttu-id="ecdf4-3104">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3104">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3105">La funzione Func_south_korea_resident_number trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3105">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3106">Viene trovata una parola chiave da Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3106">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="ecdf4-3107">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3107">The checksum passes.</span></span>

<span data-ttu-id="ecdf4-3108">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3108">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3109">La funzione Func_south_korea_resident_number trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3109">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3110">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3110">The checksum passes.</span></span>

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3111">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3111">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="ecdf4-3112">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3112">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="ecdf4-3113">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3113">National ID card</span></span> 
- <span data-ttu-id="ecdf4-3114">Numero di registrazione del cittadino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3114">Citizen's Registration Number</span></span> 
- <span data-ttu-id="ecdf4-3115">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3115">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="ecdf4-3116">RRN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3116">RRN</span></span> 
- <span data-ttu-id="ecdf4-3117">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3117">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="ecdf4-3118">Spagna - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3118">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3119">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3119">Format</span></span>

<span data-ttu-id="ecdf4-3120">11-12 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3120">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3121">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3121">Pattern</span></span>

<span data-ttu-id="ecdf4-3122">11-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3122">11-12 digits:</span></span>
- <span data-ttu-id="ecdf4-3123">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3123">Two digits</span></span> 
- <span data-ttu-id="ecdf4-3124">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3124">A forward slash (optional)</span></span> 
- <span data-ttu-id="ecdf4-3125">7-8 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3125">7-8 digits</span></span> 
- <span data-ttu-id="ecdf4-3126">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3126">A forward slash (optional)</span></span> 
- <span data-ttu-id="ecdf4-3127">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3127">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3128">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3128">Checksum</span></span>

<span data-ttu-id="ecdf4-3129">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3129">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3130">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3130">Definition</span></span>

<span data-ttu-id="ecdf4-3131">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3132">La funzione Func_spanish_social_security_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3132">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3133">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3133">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3134">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3134">Keywords</span></span>

<span data-ttu-id="ecdf4-3135">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3135">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="ecdf4-3136">Stringa di connessione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3136">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3137">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3137">Format</span></span>

<span data-ttu-id="ecdf4-3138">Stringa "ID utente", "ID utente", "UID" o "UserId" seguito dai caratteri e dalle stringhe delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3138">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3139">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3139">Pattern</span></span>

- <span data-ttu-id="ecdf4-3140">Stringa "ID utente", "ID utente", "UID" o "UserId"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3140">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="ecdf4-3141">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3141">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="ecdf4-3142">La stringa "password" o "pwd", dove "pwd" non è preceduta da una lettera minuscola</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3142">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="ecdf4-3143">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3143">An equal sign (=)</span></span>
- <span data-ttu-id="ecdf4-3144">Qualsiasi carattere che non sia un segno di dollaro ($), un simbolo di percentuale (%), un simbolo maggiore di (>), il simbolo (@), le virgolette ("), il punto e virgola (;), parentesi graffa sinistra ([) o parentesi quadra sinistra ({)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3144">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="ecdf4-3145">Qualsiasi combinazione di 7-128 caratteri che non sono un punto e virgola (;), barra (/) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3145">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="ecdf4-3146">Un punto e virgola (;) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3146">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3147">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3147">Checksum</span></span>

<span data-ttu-id="ecdf4-3148">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3148">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3149">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3149">Definition</span></span>

<span data-ttu-id="ecdf4-3150">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3150">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3151">L'espressione regolare CEP_Regex_SQLServerConnectionString trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3151">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3152">**Non** viene trovata una parola chiave da CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3152">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="ecdf4-3153">L'espressione regolare CEP_PasswordPlaceHolder **non** trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3153">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3154">L'espressione regolare CEP_CommonExampleKeywords **non** trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3154">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3155">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3155">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="ecdf4-3156">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3156">CEP_GlobalFilter</span></span>

- <span data-ttu-id="ecdf4-3157">some-password</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3157">some-password</span></span>
- <span data-ttu-id="ecdf4-3158">somepassword</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3158">somepassword</span></span>
- <span data-ttu-id="ecdf4-3159">secretPassword</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3159">secretPassword</span></span>
- <span data-ttu-id="ecdf4-3160">esempio</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3160">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="ecdf4-3161">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3161">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="ecdf4-3162">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3162">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ecdf4-3163">Password o pwd seguito da 0-2 spazi, un segno di uguale (=), 0-2 spazi e un asterisco (\*)-----------------</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3163">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="ecdf4-3164">Password o pwd seguito da:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3164">Password or pwd followed by:</span></span>
    - <span data-ttu-id="ecdf4-3165">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3165">Equal sign (=)</span></span>
    - <span data-ttu-id="ecdf4-3166">Meno di simbolo (<)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3166">Less than symbol (<)</span></span>
    - <span data-ttu-id="ecdf4-3167">Qualsiasi combinazione di 1-200 caratteri che sono lettere maiuscole o minuscole, cifre, asterisco (\*), segno meno (-), sottolineatura (_) o carattere dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3167">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="ecdf4-3168">Valore maggiore di Symbol (>)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3168">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="ecdf4-3169">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3169">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="ecdf4-3170">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3170">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="ecdf4-3171">contoso</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3171">contoso</span></span>
- <span data-ttu-id="ecdf4-3172">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3172">fabrikam</span></span>
- <span data-ttu-id="ecdf4-3173">Northwind</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3173">northwind</span></span>
- <span data-ttu-id="ecdf4-3174">sandbox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3174">sandbox</span></span>
- <span data-ttu-id="ecdf4-3175">OneBox</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3175">onebox</span></span>
- <span data-ttu-id="ecdf4-3176">localhost</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3176">localhost</span></span>
- <span data-ttu-id="ecdf4-3177">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3177">127.0.0.1</span></span>
- <span data-ttu-id="ecdf4-3178">testacs.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3178">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-3179">com</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3179">com</span></span>
- <span data-ttu-id="ecdf4-3180">s-int.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3180">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="ecdf4-3181">NET</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3181">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="ecdf4-3182">Svezia - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3182">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3183">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3183">Format</span></span>

<span data-ttu-id="ecdf4-3184">10 o 12 cifre e un delimitatore facoltativo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3184">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3185">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3185">Pattern</span></span>

<span data-ttu-id="ecdf4-3186">10 o 12 cifre e un delimitatore facoltativo:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3186">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="ecdf4-3187">2-4 cifre (facoltative)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3187">2-4 digits (optional)</span></span> 
- <span data-ttu-id="ecdf4-3188">Sei cifre nel formato data AAMMGG</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3188">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="ecdf4-3189">Delimitatore di "-" o "+" (facoltativo) più</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3189">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="ecdf4-3190">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3190">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3191">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3191">Checksum</span></span>

<span data-ttu-id="ecdf4-3192">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3192">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3193">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3193">Definition</span></span>

<span data-ttu-id="ecdf4-3194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3194">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3195">La funzione Func_swedish_national_identifier restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3195">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3196">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3196">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3197">Keywords</span></span>

<span data-ttu-id="ecdf4-3198">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3198">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="ecdf4-3199">Svezia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3199">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3200">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3200">Format</span></span>

<span data-ttu-id="ecdf4-3201">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3201">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3202">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3202">Pattern</span></span>

<span data-ttu-id="ecdf4-3203">Otto cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3203">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3204">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3204">Checksum</span></span>

<span data-ttu-id="ecdf4-3205">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3205">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3206">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3206">Definition</span></span>

<span data-ttu-id="ecdf4-3207">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3208">L'espressione regolare Regex_sweden_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3208">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3209">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3209">One of the following is true:</span></span>
    - <span data-ttu-id="ecdf4-3210">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3210">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="ecdf4-3211">Viene trovata una parola chiave da Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3211">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3212">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3212">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="ecdf4-3213">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3213">Keyword_sweden_passport</span></span>

- <span data-ttu-id="ecdf4-3214">visa requirements</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3214">visa requirements</span></span> 
- <span data-ttu-id="ecdf4-3215">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3215">Alien Registration Card</span></span> 
- <span data-ttu-id="ecdf4-3216">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3216">Schengen visas</span></span> 
- <span data-ttu-id="ecdf4-3217">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3217">Schengen visa</span></span> 
- <span data-ttu-id="ecdf4-3218">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3218">Visa Processing</span></span> 
- <span data-ttu-id="ecdf4-3219">Visa Type</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3219">Visa Type</span></span> 
- <span data-ttu-id="ecdf4-3220">Single Entry</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3220">Single Entry</span></span> 
- <span data-ttu-id="ecdf4-3221">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3221">Multiple Entry</span></span> 
- <span data-ttu-id="ecdf4-3222">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3222">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="ecdf4-3223">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3223">Keyword_passport</span></span>

- <span data-ttu-id="ecdf4-3224">Passport Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3224">Passport Number</span></span> 
- <span data-ttu-id="ecdf4-3225">Passport No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3225">Passport No</span></span> 
- <span data-ttu-id="ecdf4-3226">Passport#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3226">Passport #</span></span> 
- <span data-ttu-id="ecdf4-3227">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3227">Passport#</span></span> 
- <span data-ttu-id="ecdf4-3228">PassportID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3228">PassportID</span></span> 
- <span data-ttu-id="ecdf4-3229">Passportno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3229">Passportno</span></span> 
- <span data-ttu-id="ecdf4-3230">passportnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3230">passportnumber</span></span> 
- <span data-ttu-id="ecdf4-3231">パスポート</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3231">パスポート</span></span> 
- <span data-ttu-id="ecdf4-3232">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3232">パスポート番号</span></span> 
- <span data-ttu-id="ecdf4-3233">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3233">パスポートのNum</span></span> 
- <span data-ttu-id="ecdf4-3234">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3234">パスポート＃</span></span> 
- <span data-ttu-id="ecdf4-3235">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3235">Numéro de passeport</span></span> 
- <span data-ttu-id="ecdf4-3236">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3236">Passeport n °</span></span> 
- <span data-ttu-id="ecdf4-3237">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3237">Passeport Non</span></span> 
- <span data-ttu-id="ecdf4-3238">Passeport#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3238">Passeport #</span></span> 
- <span data-ttu-id="ecdf4-3239">Passeport #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3239">Passeport#</span></span> 
- <span data-ttu-id="ecdf4-3240">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3240">PasseportNon</span></span> 
- <span data-ttu-id="ecdf4-3241">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3241">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="ecdf4-3242">Codice SWIFT</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3242">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3243">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3243">Format</span></span>

<span data-ttu-id="ecdf4-3244">Quattro lettere seguite da 5-31 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3244">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3245">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3245">Pattern</span></span>

<span data-ttu-id="ecdf4-3246">Quattro lettere seguite da 5-31 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3246">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="ecdf4-3247">Codice ABI di quattro cifre (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3247">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-3248">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3248">An optional space</span></span> 
- <span data-ttu-id="ecdf4-3249">4-28 lettere o cifre (BBAN)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3249">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="ecdf4-3250">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3250">An optional space</span></span> 
- <span data-ttu-id="ecdf4-3251">1-3 lettere o cifre (resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3251">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3252">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3252">Checksum</span></span>

<span data-ttu-id="ecdf4-3253">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3253">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3254">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3254">Definition</span></span>

<span data-ttu-id="ecdf4-3255">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3256">L'espressione regolare Regex_swift restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3256">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3257">Viene trovata una parola chiave da Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3257">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3258">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3258">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="ecdf4-3259">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3259">Keyword_swift</span></span>

- <span data-ttu-id="ecdf4-3260">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3260">international organization for standardization 9362</span></span> 
- <span data-ttu-id="ecdf4-3261">iso 9362</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3261">iso 9362</span></span> 
- <span data-ttu-id="ecdf4-3262">iso9362</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3262">iso9362</span></span> 
- <span data-ttu-id="ecdf4-3263">Swift\#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3263">swift\#</span></span> 
- <span data-ttu-id="ecdf4-3264">swiftcode</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3264">swiftcode</span></span> 
- <span data-ttu-id="ecdf4-3265">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3265">swiftnumber</span></span> 
- <span data-ttu-id="ecdf4-3266">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3266">swiftroutingnumber</span></span> 
- <span data-ttu-id="ecdf4-3267">swift code</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3267">swift code</span></span> 
- <span data-ttu-id="ecdf4-3268">swift number #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3268">swift number #</span></span> 
- <span data-ttu-id="ecdf4-3269">swift routing number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3269">swift routing number</span></span> 
- <span data-ttu-id="ecdf4-3270">bic number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3270">bic number</span></span> 
- <span data-ttu-id="ecdf4-3271">bic code</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3271">bic code</span></span> 
- <span data-ttu-id="ecdf4-3272">BIC\#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3272">bic \#</span></span> 
- <span data-ttu-id="ecdf4-3273">BIC\#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3273">bic\#</span></span> 
- <span data-ttu-id="ecdf4-3274">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3274">bank identifier code</span></span> 
- <span data-ttu-id="ecdf4-3275">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3275">標準化9362</span></span> 
- <span data-ttu-id="ecdf4-3276">迅速＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3276">迅速＃</span></span> 
- <span data-ttu-id="ecdf4-3277">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3277">SWIFTコード</span></span> 
- <span data-ttu-id="ecdf4-3278">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3278">SWIFT番号</span></span> 
- <span data-ttu-id="ecdf4-3279">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3279">迅速なルーティング番号</span></span> 
- <span data-ttu-id="ecdf4-3280">BIC番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3280">BIC番号</span></span> 
- <span data-ttu-id="ecdf4-3281">BICコード</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3281">BICコード</span></span> 
- <span data-ttu-id="ecdf4-3282">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3282">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="ecdf4-3283">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3283">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="ecdf4-3284">rapide\#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3284">rapide \#</span></span> 
- <span data-ttu-id="ecdf4-3285">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3285">code SWIFT</span></span> 
- <span data-ttu-id="ecdf4-3286">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3286">le numéro de swift</span></span> 
- <span data-ttu-id="ecdf4-3287">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3287">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="ecdf4-3288">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3288">le numéro BIC</span></span> 
- <span data-ttu-id="ecdf4-3289">\#BIC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3289">\# BIC</span></span> 
- <span data-ttu-id="ecdf4-3290">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3290">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="ecdf4-3291">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3291">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3292">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3292">Format</span></span>

<span data-ttu-id="ecdf4-3293">Una lettera (in lingua inglese) seguita da nove cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3293">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3294">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3294">Pattern</span></span>

<span data-ttu-id="ecdf4-3295">Una lettera (in lingua inglese) seguita da nove cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3295">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="ecdf4-3296">Una lettera (in inglese, senza distinzione tra tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3296">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-3297">La cifra "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3297">The digit "1" or "2"</span></span> 
- <span data-ttu-id="ecdf4-3298">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3298">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3299">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3299">Checksum</span></span>

<span data-ttu-id="ecdf4-3300">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3300">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3301">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3301">Definition</span></span>

<span data-ttu-id="ecdf4-3302">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3302">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3303">La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3303">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3304">Viene trovata una parola chiave da Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3304">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="ecdf4-3305">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3305">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3306">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3306">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="ecdf4-3307">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3307">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="ecdf4-3308">身份證字號</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3308">身份證字號</span></span> 
- <span data-ttu-id="ecdf4-3309">身份證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3309">身份證</span></span> 
- <span data-ttu-id="ecdf4-3310">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3310">身份證號碼</span></span> 
- <span data-ttu-id="ecdf4-3311">身份證號</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3311">身份證號</span></span> 
- <span data-ttu-id="ecdf4-3312">身分證字號</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3312">身分證字號</span></span> 
- <span data-ttu-id="ecdf4-3313">身分證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3313">身分證</span></span> 
- <span data-ttu-id="ecdf4-3314">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3314">身分證號碼</span></span> 
- <span data-ttu-id="ecdf4-3315">身份證號</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3315">身份證號</span></span> 
- <span data-ttu-id="ecdf4-3316">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3316">身分證統一編號</span></span> 
- <span data-ttu-id="ecdf4-3317">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3317">國民身分證統一編號</span></span> 
- <span data-ttu-id="ecdf4-3318">簽名</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3318">簽名</span></span> 
- <span data-ttu-id="ecdf4-3319">蓋章</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3319">蓋章</span></span> 
- <span data-ttu-id="ecdf4-3320">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3320">簽名或蓋章</span></span> 
- <span data-ttu-id="ecdf4-3321">簽章</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3321">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="ecdf4-3322">	Taiwan - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3322">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3323">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3323">Format</span></span>

- <span data-ttu-id="ecdf4-3324">Numero di passaporto biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3324">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="ecdf4-3325">Numero di passaporto non biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3325">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3326">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3326">Pattern</span></span>
<span data-ttu-id="ecdf4-3327">Numero di passaporto biometrico:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3327">Biometric passport number:</span></span>
- <span data-ttu-id="ecdf4-3328">La cifra "3" </span><span class="sxs-lookup"><span data-stu-id="ecdf4-3328">The digit "3"</span></span> 
- <span data-ttu-id="ecdf4-3329">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3329">Eight digits</span></span>

<span data-ttu-id="ecdf4-3330">Numero di passaporto non biometrico:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3330">Non-biometric passport number:</span></span>
- <span data-ttu-id="ecdf4-3331">9 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3331">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3332">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3332">Checksum</span></span>

<span data-ttu-id="ecdf4-3333">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3333">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3334">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3334">Definition</span></span>

<span data-ttu-id="ecdf4-3335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3336">L'espressione regolare Regex_taiwan_passport trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3336">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3337">Viene trovata una parola chiave da Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3337">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3338">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="ecdf4-3339">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3339">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="ecdf4-3340">Numero passaporto ROC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3340">ROC passport number</span></span> 
- <span data-ttu-id="ecdf4-3341">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3341">Passport number</span></span> 
- <span data-ttu-id="ecdf4-3342">N° passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3342">Passport no</span></span> 
- <span data-ttu-id="ecdf4-3343">Num. passaporto
</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3343">Passport Num</span></span> 
- <span data-ttu-id="ecdf4-3344">Passport #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3344">Passport #</span></span> 
- <span data-ttu-id="ecdf4-3345">护照</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3345">护照</span></span> 
- <span data-ttu-id="ecdf4-3346">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3346">中華民國護照</span></span> 
- <span data-ttu-id="ecdf4-3347">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3347">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="ecdf4-3348">Taiwan - Numero certificato di residenza (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3348">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3349">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3349">Format</span></span>

<span data-ttu-id="ecdf4-3350">10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3350">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3351">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3351">Pattern</span></span>

<span data-ttu-id="ecdf4-3352">10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3352">10 letters and digits:</span></span>
- <span data-ttu-id="ecdf4-3353">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3353">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="ecdf4-3354">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3354">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3355">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3355">Checksum</span></span>

<span data-ttu-id="ecdf4-3356">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3356">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3357">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3357">Definition</span></span>

<span data-ttu-id="ecdf4-3358">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3358">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3359">L'espressione regolare Regex_taiwan_resident_certificate trova contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3359">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3360">Viene trovata una parola chiave da Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3360">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3361">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3361">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="ecdf4-3362">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3362">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="ecdf4-3363">Certificato di residenza</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3363">Resident Certificate</span></span> 
- <span data-ttu-id="ecdf4-3364">Cert. di resid
</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3364">Resident Cert</span></span> 
- <span data-ttu-id="ecdf4-3365">Cert. di resid.
</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3365">Resident Cert.</span></span> 
- <span data-ttu-id="ecdf4-3366">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3366">Identification card</span></span> 
- <span data-ttu-id="ecdf4-3367">Certificato residente straniero</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3367">Alien Resident Certificate</span></span> 
- <span data-ttu-id="ecdf4-3368">ARC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3368">ARC</span></span> 
- <span data-ttu-id="ecdf4-3369">Certificato residente nell’area di Taiwan</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3369">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="ecdf4-3370">TARC Tax</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3370">TARC</span></span> 
- <span data-ttu-id="ecdf4-3371">居留證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3371">居留證</span></span> 
- <span data-ttu-id="ecdf4-3372">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3372">外僑居留證</span></span> 
- <span data-ttu-id="ecdf4-3373">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3373">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="ecdf4-3374">Codice di identificazione della popolazione tailandese</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3374">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3375">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3375">Format</span></span>

<span data-ttu-id="ecdf4-3376">13 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3376">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3377">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3377">Pattern</span></span>

<span data-ttu-id="ecdf4-3378">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3378">13 digits:</span></span>
- <span data-ttu-id="ecdf4-3379">La prima cifra non è 0 o 9</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3379">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="ecdf4-3380">12 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3380">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3381">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3381">Checksum</span></span>

<span data-ttu-id="ecdf4-3382">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3382">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3383">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3383">Definition</span></span>

<span data-ttu-id="ecdf4-3384">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3384">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3385">La funzione Func_Thai_Citizen_Id trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3385">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3386">Viene trovata una parola chiave da Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3386">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="ecdf4-3387">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3387">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3388">La funzione Func_Thai_Citizen_Id trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3388">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3389">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3389">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="ecdf4-3390">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3390">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="ecdf4-3391">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3391">ID Number</span></span>
- <span data-ttu-id="ecdf4-3392">Numero di identificazione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3392">Identification Number</span></span>
- <span data-ttu-id="ecdf4-3393">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3393">บัตรประชาชน</span></span>
- <span data-ttu-id="ecdf4-3394">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3394">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="ecdf4-3395">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3395">บัตรประชาชน</span></span>
- <span data-ttu-id="ecdf4-3396">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3396">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="ecdf4-3397">Numero di identificazione nazionale turco</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3397">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3398">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3398">Format</span></span>

<span data-ttu-id="ecdf4-3399">11 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3399">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3400">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3400">Pattern</span></span>

<span data-ttu-id="ecdf4-3401">11 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3401">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3402">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3402">Checksum</span></span>

<span data-ttu-id="ecdf4-3403">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3403">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3404">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3404">Definition</span></span>

<span data-ttu-id="ecdf4-3405">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3405">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3406">La funzione Func_Turkish_National_Id trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3406">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3407">Viene trovata una parola chiave da Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3407">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="ecdf4-3408">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3408">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3409">La funzione Func_Turkish_National_Id trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3409">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3410">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3410">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="ecdf4-3411">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3411">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="ecdf4-3412">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3412">TC Kimlik No</span></span>
- <span data-ttu-id="ecdf4-3413">Numarası Kimlik TC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3413">TC Kimlik numarası</span></span>
- <span data-ttu-id="ecdf4-3414">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3414">Vatandaşlık numarası</span></span>
- <span data-ttu-id="ecdf4-3415">Vatandaşlık No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3415">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="ecdf4-p142">Regno Unito - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="ecdf4-p142">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3418">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3418">Format</span></span>

<span data-ttu-id="ecdf4-3419">Combinazione di 18 lettere e numeri nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3419">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3420">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3420">Pattern</span></span>

<span data-ttu-id="ecdf4-3421">18 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3421">18 letters and digits:</span></span>
- <span data-ttu-id="ecdf4-3422">Cinque lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3422">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="ecdf4-3423">Una cifra</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3423">One digit</span></span> 
- <span data-ttu-id="ecdf4-3424">Cinque cifre nel formato data MMDDY per data di nascita (il settimo carattere viene incrementato di 50 se il driver è di tipo femminile, ovvero 51 a 62 invece di 01 a 12)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3424">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="ecdf4-3425">Due lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3425">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="ecdf4-3426">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3426">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3427">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3427">Checksum</span></span>

<span data-ttu-id="ecdf4-3428">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3428">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3429">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3429">Definition</span></span>

<span data-ttu-id="ecdf4-3430">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3430">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3431">La funzione Func_uk_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3431">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3432">Viene trovata una parola chiave da Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3432">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="ecdf4-3433">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3433">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3434">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3434">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="ecdf4-3435">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3435">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="ecdf4-3436">DVLA</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3436">DVLA</span></span> 
- <span data-ttu-id="ecdf4-3437">light vans</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3437">light vans</span></span> 
- <span data-ttu-id="ecdf4-3438">quadbikes</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3438">quadbikes</span></span> 
- <span data-ttu-id="ecdf4-3439">motor cars</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3439">motor cars</span></span> 
- <span data-ttu-id="ecdf4-3440">125cc</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3440">125cc</span></span> 
- <span data-ttu-id="ecdf4-3441">sidecar</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3441">sidecar</span></span> 
- <span data-ttu-id="ecdf4-3442">tricicli</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3442">tricycles</span></span> 
- <span data-ttu-id="ecdf4-3443">moto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3443">motorcycles</span></span> 
- <span data-ttu-id="ecdf4-3444">photocard licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3444">photocard licence</span></span> 
- <span data-ttu-id="ecdf4-3445">learner drivers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3445">learner drivers</span></span> 
- <span data-ttu-id="ecdf4-3446">licence holder</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3446">licence holder</span></span> 
- <span data-ttu-id="ecdf4-3447">licence holders</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3447">licence holders</span></span> 
- <span data-ttu-id="ecdf4-3448">driving licences</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3448">driving licences</span></span> 
- <span data-ttu-id="ecdf4-3449">driving licence</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3449">driving licence</span></span> 
- <span data-ttu-id="ecdf4-3450">dual control car</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3450">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="ecdf4-p143">Regno Unito - Numero di iscrizione alle liste elettorali</span><span class="sxs-lookup"><span data-stu-id="ecdf4-p143">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3453">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3453">Format</span></span>

<span data-ttu-id="ecdf4-3454">Due lettere seguite da 1-4 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3454">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3455">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3455">Pattern</span></span>

<span data-ttu-id="ecdf4-3456">Due lettere (senza distinzione fra maiuscole/minuscole) seguite da 1-4 numeri</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3456">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3457">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3457">Checksum</span></span>

<span data-ttu-id="ecdf4-3458">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3458">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3459">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3459">Definition</span></span>

<span data-ttu-id="ecdf4-3460">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3460">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3461">L'espressione regolare Regex_uk_electoral restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3461">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3462">Viene trovata una parola chiave da Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3462">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3463">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3463">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="ecdf4-3464">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3464">Keyword_uk_electoral</span></span>

- <span data-ttu-id="ecdf4-3465">council nomination</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3465">council nomination</span></span> 
- <span data-ttu-id="ecdf4-3466">nomination form</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3466">nomination form</span></span> 
- <span data-ttu-id="ecdf4-3467">electoral register</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3467">electoral register</span></span> 
- <span data-ttu-id="ecdf4-3468">electoral roll</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3468">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="ecdf4-p144">Regno Unito - Codice del servizio sanitario nazionale</span><span class="sxs-lookup"><span data-stu-id="ecdf4-p144">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3471">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3471">Format</span></span>

<span data-ttu-id="ecdf4-3472">10-17 cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3472">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3473">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3473">Pattern</span></span>

<span data-ttu-id="ecdf4-3474">10-17 cifre:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3474">10-17 digits:</span></span>
- <span data-ttu-id="ecdf4-3475">3 o 10 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3475">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="ecdf4-3476">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3476">A space</span></span> 
- <span data-ttu-id="ecdf4-3477">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3477">Three digits</span></span> 
- <span data-ttu-id="ecdf4-3478">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3478">A space</span></span> 
- <span data-ttu-id="ecdf4-3479">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3479">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3480">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3480">Checksum</span></span>

<span data-ttu-id="ecdf4-3481">Sì</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3481">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3482">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3482">Definition</span></span>

<span data-ttu-id="ecdf4-3483">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3483">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3484">La funzione Func_uk_nhs_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3484">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3485">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3485">One of the following is true:</span></span>
    - <span data-ttu-id="ecdf4-3486">Viene trovata una parola chiave da Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3486">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="ecdf4-3487">Viene trovata una parola chiave da Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3487">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="ecdf4-3488">Viene trovata una parola chiave da Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3488">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="ecdf4-3489">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3489">The checksum passes.</span></span>

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3490">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3490">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="ecdf4-3491">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3491">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="ecdf4-3492">national health service</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3492">national health service</span></span> 
- <span data-ttu-id="ecdf4-3493">NHS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3493">nhs</span></span> 
- <span data-ttu-id="ecdf4-3494">health services authority</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3494">health services authority</span></span> 
- <span data-ttu-id="ecdf4-3495">health authority</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3495">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="ecdf4-3496">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3496">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="ecdf4-3497">patient id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3497">patient id</span></span> 
- <span data-ttu-id="ecdf4-3498">patient identification</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3498">patient identification</span></span> 
- <span data-ttu-id="ecdf4-3499">patient no</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3499">patient no</span></span> 
- <span data-ttu-id="ecdf4-3500">patient number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3500">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="ecdf4-3501">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3501">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="ecdf4-3502">GP</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3502">GP</span></span> 
- <span data-ttu-id="ecdf4-3503">DOB</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3503">DOB</span></span> 
- <span data-ttu-id="ecdf4-3504">D. O. B</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3504">D.O.B</span></span> 
- <span data-ttu-id="ecdf4-3505">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3505">Date of Birth</span></span> 
- <span data-ttu-id="ecdf4-3506">Birth Date</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3506">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="ecdf4-p145">Regno Unito - Numero di assicurazione nazionale (NINO)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-p145">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3509">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3509">Format</span></span>

<span data-ttu-id="ecdf4-3510">7 caratteri o 9 caratteri separati da spazi o trattini</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3510">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3511">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3511">Pattern</span></span>

<span data-ttu-id="ecdf4-3512">Due modelli possibili:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3512">Two possible patterns:</span></span>

- <span data-ttu-id="ecdf4-3513">Due lettere (NINOs valido utilizza solo alcuni caratteri in questo prefisso, che questo modello convalida; senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3513">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="ecdf4-3514">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3514">Six digits</span></span>
- <span data-ttu-id="ecdf4-3515">' A ',' B ',' c'o ' d'(come il prefisso, solo alcuni caratteri sono consentiti nel suffisso, senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3515">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="ecdf4-3516">OPPURE</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3516">OR</span></span>

- <span data-ttu-id="ecdf4-3517">Due lettere</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3517">Two letters</span></span>
- <span data-ttu-id="ecdf4-3518">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3518">A space or dash</span></span>
- <span data-ttu-id="ecdf4-3519">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3519">Two digits</span></span>
- <span data-ttu-id="ecdf4-3520">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3520">A space or dash</span></span>
- <span data-ttu-id="ecdf4-3521">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3521">Two digits</span></span>
- <span data-ttu-id="ecdf4-3522">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3522">A space or dash</span></span>
- <span data-ttu-id="ecdf4-3523">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3523">Two digits</span></span>
- <span data-ttu-id="ecdf4-3524">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3524">A space or dash</span></span>
- <span data-ttu-id="ecdf4-3525">' A ',' B ',' c'o ' d'</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3525">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3526">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3526">Checksum</span></span>

<span data-ttu-id="ecdf4-3527">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3527">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3528">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3528">Definition</span></span>

<span data-ttu-id="ecdf4-3529">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3529">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3530">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3530">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3531">Viene trovata una parola chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3531">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="ecdf4-3532">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3532">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3533">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3533">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3534">Non vengono trovate parole chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3534">No keyword from Keyword_uk_nino is found.</span></span>

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3535">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3535">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="ecdf4-3536">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3536">Keyword_uk_nino</span></span>

- <span data-ttu-id="ecdf4-3537">national insurance number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3537">national insurance number</span></span> 
- <span data-ttu-id="ecdf4-3538">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3538">national insurance contributions</span></span> 
- <span data-ttu-id="ecdf4-3539">protection act</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3539">protection act</span></span> 
- <span data-ttu-id="ecdf4-3540">Insurance</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3540">insurance</span></span> 
- <span data-ttu-id="ecdf4-3541">social security number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3541">social security number</span></span> 
- <span data-ttu-id="ecdf4-3542">insurance application</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3542">insurance application</span></span> 
- <span data-ttu-id="ecdf4-3543">medical application</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3543">medical application</span></span> 
- <span data-ttu-id="ecdf4-3544">social insurance</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3544">social insurance</span></span> 
- <span data-ttu-id="ecdf4-3545">medical attention</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3545">medical attention</span></span> 
- <span data-ttu-id="ecdf4-3546">social security</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3546">social security</span></span> 
- <span data-ttu-id="ecdf4-3547">great britain</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3547">great britain</span></span> 
- <span data-ttu-id="ecdf4-3548">Insurance</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3548">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="ecdf4-p146">Stati Uniti/Regno Unito - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="ecdf4-p146">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3551">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3551">Format</span></span>

<span data-ttu-id="ecdf4-3552">9 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3552">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3553">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3553">Pattern</span></span>

<span data-ttu-id="ecdf4-3554">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3554">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3555">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3555">Checksum</span></span>

<span data-ttu-id="ecdf4-3556">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3556">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3557">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3557">Definition</span></span>

<span data-ttu-id="ecdf4-3558">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3558">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3559">La funzione Func_usa_uk_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3559">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3560">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3560">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3561">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3561">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="ecdf4-3562">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3562">Keyword_passport</span></span>

- <span data-ttu-id="ecdf4-3563">Passport Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3563">Passport Number</span></span> 
- <span data-ttu-id="ecdf4-3564">Passport No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3564">Passport No</span></span> 
- <span data-ttu-id="ecdf4-3565">Passport#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3565">Passport #</span></span> 
- <span data-ttu-id="ecdf4-3566">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3566">Passport#</span></span> 
- <span data-ttu-id="ecdf4-3567">PassportID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3567">PassportID</span></span> 
- <span data-ttu-id="ecdf4-3568">Passportno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3568">Passportno</span></span> 
- <span data-ttu-id="ecdf4-3569">passportnumber</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3569">passportnumber</span></span> 
- <span data-ttu-id="ecdf4-3570">パスポート</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3570">パスポート</span></span> 
- <span data-ttu-id="ecdf4-3571">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3571">パスポート番号</span></span> 
- <span data-ttu-id="ecdf4-3572">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3572">パスポートのNum</span></span> 
- <span data-ttu-id="ecdf4-3573">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3573">パスポート＃</span></span> 
- <span data-ttu-id="ecdf4-3574">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3574">Numéro de passeport</span></span> 
- <span data-ttu-id="ecdf4-3575">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3575">Passeport n °</span></span> 
- <span data-ttu-id="ecdf4-3576">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3576">Passeport Non</span></span> 
- <span data-ttu-id="ecdf4-3577">Passeport#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3577">Passeport #</span></span> 
- <span data-ttu-id="ecdf4-3578">Passeport #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3578">Passeport#</span></span> 
- <span data-ttu-id="ecdf4-3579">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3579">PasseportNon</span></span> 
- <span data-ttu-id="ecdf4-3580">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3580">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="ecdf4-3581">Stati Uniti - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3581">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3582">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3582">Format</span></span>

<span data-ttu-id="ecdf4-3583">8-17 cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3583">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3584">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3584">Pattern</span></span>

<span data-ttu-id="ecdf4-3585">8-17 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3585">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3586">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3586">Checksum</span></span>

<span data-ttu-id="ecdf4-3587">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3587">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3588">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3588">Definition</span></span>

<span data-ttu-id="ecdf4-3589">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3589">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3590">L'espressione regolare Regex_usa_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3590">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3591">Viene trovata una parola chiave da Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3591">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3592">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3592">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="ecdf4-3593">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3593">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="ecdf4-3594">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3594">Checking Account Number</span></span> 
- <span data-ttu-id="ecdf4-3595">Checking Account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3595">Checking Account</span></span> 
- <span data-ttu-id="ecdf4-3596">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3596">Checking Account #</span></span> 
- <span data-ttu-id="ecdf4-3597">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3597">Checking Acct Number</span></span> 
- <span data-ttu-id="ecdf4-3598">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3598">Checking Acct #</span></span> 
- <span data-ttu-id="ecdf4-3599">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3599">Checking Acct No.</span></span> 
- <span data-ttu-id="ecdf4-3600">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3600">Checking Account No.</span></span> 
- <span data-ttu-id="ecdf4-3601">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3601">Bank Account Number</span></span> 
- <span data-ttu-id="ecdf4-3602">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3602">Bank Account #</span></span> 
- <span data-ttu-id="ecdf4-3603">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3603">Bank Acct Number</span></span> 
- <span data-ttu-id="ecdf4-3604">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3604">Bank Acct #</span></span> 
- <span data-ttu-id="ecdf4-3605">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3605">Bank Acct No.</span></span> 
- <span data-ttu-id="ecdf4-3606">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3606">Bank Account No.</span></span> 
- <span data-ttu-id="ecdf4-3607">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3607">Savings Account Number</span></span> 
- <span data-ttu-id="ecdf4-3608">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3608">Savings Account.</span></span> 
- <span data-ttu-id="ecdf4-3609">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3609">Savings Account #</span></span> 
- <span data-ttu-id="ecdf4-3610">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3610">Savings Acct Number</span></span> 
- <span data-ttu-id="ecdf4-3611">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3611">Savings Acct #</span></span> 
- <span data-ttu-id="ecdf4-3612">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3612">Savings Acct No.</span></span> 
- <span data-ttu-id="ecdf4-3613">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3613">Savings Account No.</span></span> 
- <span data-ttu-id="ecdf4-3614">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3614">Debit Account Number</span></span> 
- <span data-ttu-id="ecdf4-3615">Debit Account</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3615">Debit Account</span></span> 
- <span data-ttu-id="ecdf4-3616">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3616">Debit Account #</span></span> 
- <span data-ttu-id="ecdf4-3617">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3617">Debit Acct Number</span></span> 
- <span data-ttu-id="ecdf4-3618">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3618">Debit Acct #</span></span> 
- <span data-ttu-id="ecdf4-3619">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3619">Debit Acct No.</span></span> 
- <span data-ttu-id="ecdf4-3620">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3620">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="ecdf4-3621">Stati Uniti - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3621">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3622">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3622">Format</span></span>

<span data-ttu-id="ecdf4-3623">Varia in base allo stato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3623">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3624">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3624">Pattern</span></span>

<span data-ttu-id="ecdf4-3625">Varia in base allo stato. Ad esempio, per New York:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3625">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="ecdf4-3626">Nove cifre formattate come ddd ddd ddd corrisponderanno.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3626">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="ecdf4-3627">Nove cifre come ddddddddd non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3627">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3628">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3628">Checksum</span></span>

<span data-ttu-id="ecdf4-3629">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3629">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3630">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3630">Definition</span></span>

<span data-ttu-id="ecdf4-3631">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3631">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3632">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3632">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3633">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3633">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="ecdf4-3634">Viene trovata una parola chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3634">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="ecdf4-3635">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3635">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3636">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3636">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3637">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3637">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="ecdf4-3638">Viene trovata una parola chiave da Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3638">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="ecdf4-3639">Non vengono trovate parole chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3639">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3640">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3640">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="ecdf4-3641">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3641">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="ecdf4-3642">DL</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3642">DL</span></span> 
- <span data-ttu-id="ecdf4-3643">DLS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3643">DLS</span></span> 
- <span data-ttu-id="ecdf4-3644">CDL</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3644">CDL</span></span> 
- <span data-ttu-id="ecdf4-3645">CDLS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3645">CDLS</span></span> 
- <span data-ttu-id="ecdf4-3646">ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3646">ID</span></span> 
- <span data-ttu-id="ecdf4-3647">ID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3647">IDs</span></span> 
- <span data-ttu-id="ecdf4-3648">DL #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3648">DL#</span></span> 
- <span data-ttu-id="ecdf4-3649">DLS #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3649">DLS#</span></span> 
- <span data-ttu-id="ecdf4-3650">CDL #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3650">CDL#</span></span> 
- <span data-ttu-id="ecdf4-3651">CDLS #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3651">CDLS#</span></span> 
- <span data-ttu-id="ecdf4-3652">ID #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3652">ID#</span></span>
- <span data-ttu-id="ecdf4-3653">ID #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3653">IDs#</span></span> 
- <span data-ttu-id="ecdf4-3654">ID number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3654">ID number</span></span> 
- <span data-ttu-id="ecdf4-3655">ID numbers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3655">ID numbers</span></span> 
- <span data-ttu-id="ecdf4-3656">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3656">LIC</span></span> 
- <span data-ttu-id="ecdf4-3657">DRIVER'LIC #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3657">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="ecdf4-3658">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3658">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="ecdf4-3659">DriverLic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3659">DriverLic</span></span> 
- <span data-ttu-id="ecdf4-3660">DriverLics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3660">DriverLics</span></span> 
- <span data-ttu-id="ecdf4-3661">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3661">DriverLicense</span></span> 
- <span data-ttu-id="ecdf4-3662">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3662">DriverLicenses</span></span> 
- <span data-ttu-id="ecdf4-3663">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3663">Driver Lic</span></span> 
- <span data-ttu-id="ecdf4-3664">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3664">Driver Lics</span></span> 
- <span data-ttu-id="ecdf4-3665">Driver License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3665">Driver License</span></span> 
- <span data-ttu-id="ecdf4-3666">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3666">Driver Licenses</span></span> 
- <span data-ttu-id="ecdf4-3667">DriversLic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3667">DriversLic</span></span> 
- <span data-ttu-id="ecdf4-3668">DriversLics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3668">DriversLics</span></span> 
- <span data-ttu-id="ecdf4-3669">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3669">DriversLicense</span></span> 
- <span data-ttu-id="ecdf4-3670">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3670">DriversLicenses</span></span> 
- <span data-ttu-id="ecdf4-3671">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3671">Drivers Lic</span></span> 
- <span data-ttu-id="ecdf4-3672">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3672">Drivers Lics</span></span> 
- <span data-ttu-id="ecdf4-3673">Drivers License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3673">Drivers License</span></span> 
- <span data-ttu-id="ecdf4-3674">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3674">Drivers Licenses</span></span> 
- <span data-ttu-id="ecdf4-3675">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3675">Driver'Lic</span></span> 
- <span data-ttu-id="ecdf4-3676">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3676">Driver'Lics</span></span> 
- <span data-ttu-id="ecdf4-3677">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3677">Driver'License</span></span> 
- <span data-ttu-id="ecdf4-3678">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3678">Driver'Licenses</span></span> 
- <span data-ttu-id="ecdf4-3679">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3679">Driver' Lic</span></span> 
- <span data-ttu-id="ecdf4-3680">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3680">Driver' Lics</span></span> 
- <span data-ttu-id="ecdf4-3681">Driver' License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3681">Driver' License</span></span> 
- <span data-ttu-id="ecdf4-3682">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3682">Driver' Licenses</span></span>
- <span data-ttu-id="ecdf4-3683">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3683">Driver'sLic</span></span> 
- <span data-ttu-id="ecdf4-3684">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3684">Driver'sLics</span></span> 
- <span data-ttu-id="ecdf4-3685">Secondola</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3685">Driver'sLicense</span></span> 
- <span data-ttu-id="ecdf4-3686">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3686">Driver'sLicenses</span></span> 
- <span data-ttu-id="ecdf4-3687">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3687">Driver's Lic</span></span> 
- <span data-ttu-id="ecdf4-3688">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3688">Driver's Lics</span></span> 
- <span data-ttu-id="ecdf4-3689">Driver's License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3689">Driver's License</span></span> 
- <span data-ttu-id="ecdf4-3690">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3690">Driver's Licenses</span></span> 
- <span data-ttu-id="ecdf4-3691">identification number</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3691">identification number</span></span> 
- <span data-ttu-id="ecdf4-3692">identification numbers</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3692">identification numbers</span></span> 
- <span data-ttu-id="ecdf4-3693">identification#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3693">identification #</span></span> 
- <span data-ttu-id="ecdf4-3694">id card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3694">id card</span></span> 
- <span data-ttu-id="ecdf4-3695">id cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3695">id cards</span></span> 
- <span data-ttu-id="ecdf4-3696">identification card</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3696">identification card</span></span> 
- <span data-ttu-id="ecdf4-3697">identification cards</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3697">identification cards</span></span> 
- <span data-ttu-id="ecdf4-3698">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3698">DriverLic#</span></span> 
- <span data-ttu-id="ecdf4-3699">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3699">DriverLics#</span></span> 
- <span data-ttu-id="ecdf4-3700">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3700">DriverLicense#</span></span> 
- <span data-ttu-id="ecdf4-3701">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3701">DriverLicenses#</span></span> 
- <span data-ttu-id="ecdf4-3702">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3702">Driver Lic#</span></span> 
- <span data-ttu-id="ecdf4-3703">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3703">Driver Lics#</span></span> 
- <span data-ttu-id="ecdf4-3704">Driver License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3704">Driver License#</span></span> 
- <span data-ttu-id="ecdf4-3705">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3705">Driver Licenses#</span></span> 
- <span data-ttu-id="ecdf4-3706">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3706">DriversLic#</span></span> 
- <span data-ttu-id="ecdf4-3707">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3707">DriversLics#</span></span> 
- <span data-ttu-id="ecdf4-3708">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3708">DriversLicense#</span></span> 
- <span data-ttu-id="ecdf4-3709">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3709">DriversLicenses#</span></span> 
- <span data-ttu-id="ecdf4-3710">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3710">Drivers Lic#</span></span> 
- <span data-ttu-id="ecdf4-3711">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3711">Drivers Lics#</span></span> 
- <span data-ttu-id="ecdf4-3712">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3712">Drivers License#</span></span> 
- <span data-ttu-id="ecdf4-3713">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3713">Drivers Licenses#</span></span> 
- <span data-ttu-id="ecdf4-3714">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3714">Driver'Lic#</span></span> 
- <span data-ttu-id="ecdf4-3715">Driver ' LiCS #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3715">Driver'Lics#</span></span> 
- <span data-ttu-id="ecdf4-3716">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3716">Driver'License#</span></span> 
- <span data-ttu-id="ecdf4-3717">Driver ' licenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3717">Driver'Licenses#</span></span> 
- <span data-ttu-id="ecdf4-3718">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3718">Driver' Lic#</span></span> 
- <span data-ttu-id="ecdf4-3719">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3719">Driver' Lics#</span></span> 
- <span data-ttu-id="ecdf4-3720">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3720">Driver' License#</span></span> 
- <span data-ttu-id="ecdf4-3721">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3721">Driver' Licenses#</span></span> 
- <span data-ttu-id="ecdf4-3722">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3722">Driver'sLic#</span></span> 
- <span data-ttu-id="ecdf4-3723">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3723">Driver'sLics#</span></span> 
- <span data-ttu-id="ecdf4-3724">Secondola #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3724">Driver'sLicense#</span></span> 
- <span data-ttu-id="ecdf4-3725">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3725">Driver'sLicenses#</span></span> 
- <span data-ttu-id="ecdf4-3726">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3726">Driver's Lic#</span></span> 
- <span data-ttu-id="ecdf4-3727">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3727">Driver's Lics#</span></span> 
- <span data-ttu-id="ecdf4-3728">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3728">Driver's License#</span></span> 
- <span data-ttu-id="ecdf4-3729">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3729">Driver's Licenses#</span></span> 
- <span data-ttu-id="ecdf4-3730">id card#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3730">id card#</span></span> 
- <span data-ttu-id="ecdf4-3731">id cards#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3731">id cards#</span></span> 
- <span data-ttu-id="ecdf4-3732">identification card#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3732">identification card#</span></span> 
- <span data-ttu-id="ecdf4-3733">identification cards#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3733">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="ecdf4-3734">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3734">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="ecdf4-3735">Abbreviazione dello stato (ad esempio, "NY")</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3735">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="ecdf4-3736">Nome dello stato (ad esempio, "New York")</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3736">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="ecdf4-3737">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3737">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3738">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3738">Format</span></span>

<span data-ttu-id="ecdf4-3739">Nove cifre che iniziano con "9" e contengono un "7" o un "8" come quarta cifra. Può essere formattato con spazi e trattini (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3739">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3740">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3740">Pattern</span></span>

<span data-ttu-id="ecdf4-3741">Formattato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3741">Formatted:</span></span>
- <span data-ttu-id="ecdf4-3742">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3742">The digit "9"</span></span> 
- <span data-ttu-id="ecdf4-3743">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3743">Two digits</span></span> 
- <span data-ttu-id="ecdf4-3744">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3744">A space or dash</span></span> 
- <span data-ttu-id="ecdf4-3745">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3745">A "7" or "8"</span></span> 
- <span data-ttu-id="ecdf4-3746">Una cifra</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3746">A digit</span></span> 
- <span data-ttu-id="ecdf4-3747">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3747">A space, or dash</span></span> 
- <span data-ttu-id="ecdf4-3748">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3748">Four digits</span></span>

<span data-ttu-id="ecdf4-3749">Formattato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3749">Unformatted:</span></span>
- <span data-ttu-id="ecdf4-3750">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3750">The digit "9"</span></span> 
- <span data-ttu-id="ecdf4-3751">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3751">Two digits</span></span> 
- <span data-ttu-id="ecdf4-3752">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3752">A "7" or "8"</span></span> 
- <span data-ttu-id="ecdf4-3753">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3753">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3754">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3754">Checksum</span></span>

<span data-ttu-id="ecdf4-3755">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3755">No</span></span>

### <a name="definition"></a><span data-ttu-id="ecdf4-3756">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3756">Definition</span></span>

<span data-ttu-id="ecdf4-3757">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3757">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3758">La funzione Func_formatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3758">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3759">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3759">At least one of the following is true:</span></span>
    - <span data-ttu-id="ecdf4-3760">Viene trovata una parola chiave da Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3760">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="ecdf4-3761">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3761">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="ecdf4-3762">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3762">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="ecdf4-3763">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3763">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="ecdf4-3764">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3765">La funzione Func_unformatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3765">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3766">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3766">At least one of the following is true:</span></span>
    - <span data-ttu-id="ecdf4-3767">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3767">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="ecdf4-3768">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3768">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="ecdf4-3769">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3769">The function Func_us_date finds a date in the right date format.</span></span>

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3770">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3770">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="ecdf4-3771">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3771">Keyword_itin</span></span>

- <span data-ttu-id="ecdf4-3772">contribuente</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3772">taxpayer</span></span> 
- <span data-ttu-id="ecdf4-3773">tax id</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3773">tax id</span></span> 
- <span data-ttu-id="ecdf4-3774">tax identification</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3774">tax identification</span></span> 
- <span data-ttu-id="ecdf4-3775">Itin</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3775">itin</span></span> 
- <span data-ttu-id="ecdf4-3776">SSN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3776">ssn</span></span> 
- <span data-ttu-id="ecdf4-3777">latta</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3777">tin</span></span> 
- <span data-ttu-id="ecdf4-3778">social security</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3778">social security</span></span> 
- <span data-ttu-id="ecdf4-3779">tax payer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3779">tax payer</span></span> 
- <span data-ttu-id="ecdf4-3780">itins</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3780">itins</span></span> 
- <span data-ttu-id="ecdf4-3781">taxid</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3781">taxid</span></span> 
- <span data-ttu-id="ecdf4-3782">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3782">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="ecdf4-3783">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3783">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="ecdf4-3784">License</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3784">License</span></span> 
- <span data-ttu-id="ecdf4-3785">DL</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3785">DL</span></span> 
- <span data-ttu-id="ecdf4-3786">DOB</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3786">DOB</span></span> 
- <span data-ttu-id="ecdf4-3787">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3787">Birthdate</span></span> 
- <span data-ttu-id="ecdf4-3788">Compleanno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3788">Birthday</span></span> 
- <span data-ttu-id="ecdf4-3789">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3789">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="ecdf4-3790">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3790">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="ecdf4-3791">Formato</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3791">Format</span></span>

<span data-ttu-id="ecdf4-3792">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3792">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="ecdf4-3793">Se emesso prima della metà del 2011, un SSN ha una formattazione complessa in cui alcune parti del numero devono rientrare in alcuni intervalli per essere valide (ma non c'è nessun checksum).</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3793">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="ecdf4-3794">Modello</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3794">Pattern</span></span>

<span data-ttu-id="ecdf4-3795">Quattro funzioni cercano SNSS in quattro modelli diversi:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3795">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="ecdf4-3796">Func_ssn trova SNSS con una formattazione complessa pre2011 formattata con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3796">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="ecdf4-3797">Func_unformatted_ssn trova SNSS con una formattazione complessa pre2011 che non è formattata come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3797">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="ecdf4-3798">Func_randomized_formatted_ssn trova post-2011 SNSS formattati con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3798">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="ecdf4-3799">Func_randomized_unformatted_ssn trova post-2011 SNSS che non sono formattati come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3799">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="ecdf4-3800">Checksum</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3800">Checksum</span></span>

<span data-ttu-id="ecdf4-3801">No</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3801">No</span></span>


### <a name="definition"></a><span data-ttu-id="ecdf4-3802">Definizione</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3802">Definition</span></span>

<span data-ttu-id="ecdf4-3803">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3803">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3804">La funzione Func_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3804">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3805">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3805">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="ecdf4-3806">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3807">La funzione Func_unformatted_ssn trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3807">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3808">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3808">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="ecdf4-3809">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3809">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3810">La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3810">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3811">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3811">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="ecdf4-3812">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 55%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3812">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="ecdf4-3813">La funzione Func_randomized_unformatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3813">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="ecdf4-3814">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3814">A keyword from Keyword_ssn is found.</span></span>


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a><span data-ttu-id="ecdf4-3815">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3815">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="ecdf4-3816">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3816">Keyword_ssn</span></span>

- <span data-ttu-id="ecdf4-3817">Social Security</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3817">Social Security</span></span> 
- <span data-ttu-id="ecdf4-3818">Social Security#</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3818">Social Security#</span></span> 
- <span data-ttu-id="ecdf4-3819">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3819">Soc Sec</span></span> 
- <span data-ttu-id="ecdf4-3820">SSN</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3820">SSN</span></span> 
- <span data-ttu-id="ecdf4-3821">SNSS</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3821">SSNS</span></span> 
- <span data-ttu-id="ecdf4-3822">SSN #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3822">SSN#</span></span> 
- <span data-ttu-id="ecdf4-3823">SS #</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3823">SS#</span></span> 
- <span data-ttu-id="ecdf4-3824">SSID</span><span class="sxs-lookup"><span data-stu-id="ecdf4-3824">SSID</span></span> 
   
