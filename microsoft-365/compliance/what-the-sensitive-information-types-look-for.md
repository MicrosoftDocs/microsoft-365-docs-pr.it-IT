---
title: Tipi di informazioni riservate disponibili da cercare
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
description: La prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365 include 80 tipi di informazioni riservate pronte per l'uso nei criteri DLP. In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.
ms.openlocfilehash: 820bab0a128f952cf5d96208f5d561f4994bd859
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084242"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="294e1-104">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="294e1-104">What the sensitive information types look for</span></span>

<span data-ttu-id="294e1-105">La prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365 include numerosi tipi di informazioni riservate pronte per l'uso nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="294e1-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="294e1-106">In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="294e1-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="294e1-107">Una tipologia di informazioni riservate viene definita da un modello identificato da un'espressione regolare o da una funzione.</span><span class="sxs-lookup"><span data-stu-id="294e1-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="294e1-108">Inoltre, è possibile utilizzare elementi probatori, ad esempio, parole chiave e checksum per identificare una tipologia di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="294e1-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="294e1-109">In questa procedura di valutazione vengono usati anche il livello di probabilità e la prossimità.</span><span class="sxs-lookup"><span data-stu-id="294e1-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="294e1-110">Numero di registrazione ABA</span><span class="sxs-lookup"><span data-stu-id="294e1-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-111">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-111">Format</span></span>

<span data-ttu-id="294e1-112">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="294e1-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-113">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-113">Pattern</span></span>

<span data-ttu-id="294e1-114">Formattato</span><span class="sxs-lookup"><span data-stu-id="294e1-114">Formatted:</span></span>
- <span data-ttu-id="294e1-115">Quattro cifre che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="294e1-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="294e1-116">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-116">A hyphen</span></span>
- <span data-ttu-id="294e1-117">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-117">Four digits</span></span>
- <span data-ttu-id="294e1-118">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-118">A hyphen</span></span>
- <span data-ttu-id="294e1-119">Una cifra</span><span class="sxs-lookup"><span data-stu-id="294e1-119">A digit</span></span>

<span data-ttu-id="294e1-120">Non formattato: 9 cifre consecutive che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="294e1-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="294e1-121">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-121">Checksum</span></span>

<span data-ttu-id="294e1-122">No</span><span class="sxs-lookup"><span data-stu-id="294e1-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-123">Definition</span></span>

<span data-ttu-id="294e1-124">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-125">La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-126">Viene trovata una parola chiave da Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="294e1-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="294e1-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="294e1-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="294e1-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="294e1-129">ABA</span><span class="sxs-lookup"><span data-stu-id="294e1-129">aba</span></span>
- <span data-ttu-id="294e1-130">aba #</span><span class="sxs-lookup"><span data-stu-id="294e1-130">aba #</span></span>
- <span data-ttu-id="294e1-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="294e1-131">aba routing #</span></span>
- <span data-ttu-id="294e1-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="294e1-132">aba routing number</span></span>
- <span data-ttu-id="294e1-133">ABA #</span><span class="sxs-lookup"><span data-stu-id="294e1-133">aba#</span></span>
- <span data-ttu-id="294e1-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="294e1-134">abarouting#</span></span>
- <span data-ttu-id="294e1-135">aba number</span><span class="sxs-lookup"><span data-stu-id="294e1-135">aba number</span></span>
- <span data-ttu-id="294e1-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-136">abaroutingnumber</span></span>
- <span data-ttu-id="294e1-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="294e1-137">american bank association routing #</span></span>
- <span data-ttu-id="294e1-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="294e1-138">american bank association routing number</span></span>
- <span data-ttu-id="294e1-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="294e1-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="294e1-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="294e1-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="294e1-141">bank routing number</span></span>
- <span data-ttu-id="294e1-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="294e1-142">bankrouting#</span></span>
- <span data-ttu-id="294e1-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-143">bankroutingnumber</span></span>
- <span data-ttu-id="294e1-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="294e1-144">routing transit number</span></span>
- <span data-ttu-id="294e1-145">RTN</span><span class="sxs-lookup"><span data-stu-id="294e1-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="294e1-146">Argentina - Numero di identità nazionale (DNI)</span><span class="sxs-lookup"><span data-stu-id="294e1-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-147">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-147">Format</span></span>

<span data-ttu-id="294e1-148">Otto cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="294e1-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-149">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-149">Pattern</span></span>

<span data-ttu-id="294e1-150">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-150">Eight digits:</span></span>
- <span data-ttu-id="294e1-151">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-151">Two digits</span></span>
- <span data-ttu-id="294e1-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="294e1-152">A period</span></span>
- <span data-ttu-id="294e1-153">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-153">Three digits</span></span>
- <span data-ttu-id="294e1-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="294e1-154">A period</span></span>
- <span data-ttu-id="294e1-155">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-156">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-156">Checksum</span></span>

<span data-ttu-id="294e1-157">No</span><span class="sxs-lookup"><span data-stu-id="294e1-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-158">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-158">Definition</span></span>

<span data-ttu-id="294e1-159">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-160">L'espressione regolare Regex_argentina_national_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-161">Viene trovata una parola chiave da Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="294e1-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-162">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="294e1-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="294e1-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="294e1-164">Argentina - Numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="294e1-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="294e1-165">Identità</span><span class="sxs-lookup"><span data-stu-id="294e1-165">Identity</span></span> 
- <span data-ttu-id="294e1-166">Carta di identità nazionale di identificazione</span><span class="sxs-lookup"><span data-stu-id="294e1-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="294e1-167">DNI</span><span class="sxs-lookup"><span data-stu-id="294e1-167">DNI</span></span> 
- <span data-ttu-id="294e1-168">Registro nazionale delle persone di NIC</span><span class="sxs-lookup"><span data-stu-id="294e1-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="294e1-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="294e1-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="294e1-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="294e1-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="294e1-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="294e1-171">Identidad</span></span> 
- <span data-ttu-id="294e1-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="294e1-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="294e1-173">Australia - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="294e1-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-174">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-174">Format</span></span>

<span data-ttu-id="294e1-175">6-10 cifre con o senza un numero BSB (Bank/State/Branch)</span><span class="sxs-lookup"><span data-stu-id="294e1-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-176">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-176">Pattern</span></span>

<span data-ttu-id="294e1-177">Il numero di conto comprende 6-10 cifre.</span><span class="sxs-lookup"><span data-stu-id="294e1-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="294e1-178">Numero BSB australiano:</span><span class="sxs-lookup"><span data-stu-id="294e1-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="294e1-179">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-179">Three digits</span></span> 
- <span data-ttu-id="294e1-180">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-180">A hyphen</span></span> 
- <span data-ttu-id="294e1-181">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-182">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-182">Checksum</span></span>

<span data-ttu-id="294e1-183">No</span><span class="sxs-lookup"><span data-stu-id="294e1-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-184">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-184">Definition</span></span>

<span data-ttu-id="294e1-185">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-186">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="294e1-187">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="294e1-188">L'espressione regolare Regex_australia_bank_account_number_bsb restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="294e1-189">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-190">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="294e1-191">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-192">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="294e1-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="294e1-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="294e1-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="294e1-194">swift bank code</span></span>
- <span data-ttu-id="294e1-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="294e1-195">correspondent bank</span></span>
- <span data-ttu-id="294e1-196">base currency</span><span class="sxs-lookup"><span data-stu-id="294e1-196">base currency</span></span>
- <span data-ttu-id="294e1-197">usa account</span><span class="sxs-lookup"><span data-stu-id="294e1-197">usa account</span></span>
- <span data-ttu-id="294e1-198">holder address</span><span class="sxs-lookup"><span data-stu-id="294e1-198">holder address</span></span>
- <span data-ttu-id="294e1-199">bank address</span><span class="sxs-lookup"><span data-stu-id="294e1-199">bank address</span></span>
- <span data-ttu-id="294e1-200">information account</span><span class="sxs-lookup"><span data-stu-id="294e1-200">information account</span></span>
- <span data-ttu-id="294e1-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="294e1-201">fund transfers</span></span>
- <span data-ttu-id="294e1-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="294e1-202">bank charges</span></span>
- <span data-ttu-id="294e1-203">bank details</span><span class="sxs-lookup"><span data-stu-id="294e1-203">bank details</span></span>
- <span data-ttu-id="294e1-204">banking information</span><span class="sxs-lookup"><span data-stu-id="294e1-204">banking information</span></span>
- <span data-ttu-id="294e1-205">full names</span><span class="sxs-lookup"><span data-stu-id="294e1-205">full names</span></span>
- <span data-ttu-id="294e1-206">AIEA</span><span class="sxs-lookup"><span data-stu-id="294e1-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="294e1-207">Australia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="294e1-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-208">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-208">Format</span></span>

<span data-ttu-id="294e1-209">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="294e1-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-210">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-210">Pattern</span></span>

<span data-ttu-id="294e1-211">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="294e1-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="294e1-212">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="294e1-213">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-213">Two digits</span></span> 
- <span data-ttu-id="294e1-214">Cinque cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="294e1-215">O</span><span class="sxs-lookup"><span data-stu-id="294e1-215">OR</span></span>

- <span data-ttu-id="294e1-216">1-2 lettere facoltative (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="294e1-217">4-9 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-217">4-9 digits</span></span>

<span data-ttu-id="294e1-218">O</span><span class="sxs-lookup"><span data-stu-id="294e1-218">OR</span></span>

- <span data-ttu-id="294e1-219">Nove cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-220">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-220">Checksum</span></span>

<span data-ttu-id="294e1-221">No</span><span class="sxs-lookup"><span data-stu-id="294e1-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-222">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-222">Definition</span></span>

<span data-ttu-id="294e1-223">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-224">L'espressione regolare Regex_australia_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-225">Viene trovata una parola chiave da Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="294e1-226">Non vengono trovate parole chiava da Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="294e1-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="294e1-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="294e1-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="294e1-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="294e1-229">international driving permits</span></span>
- <span data-ttu-id="294e1-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="294e1-230">australian automobile association</span></span>
- <span data-ttu-id="294e1-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="294e1-231">international driving permit</span></span>
- <span data-ttu-id="294e1-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="294e1-232">DriverLicence</span></span>
- <span data-ttu-id="294e1-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="294e1-233">DriverLicences</span></span>
- <span data-ttu-id="294e1-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-234">Driver Lic</span></span>
- <span data-ttu-id="294e1-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-235">Driver Licence</span></span>
- <span data-ttu-id="294e1-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-236">Driver Licences</span></span>
- <span data-ttu-id="294e1-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="294e1-237">DriversLic</span></span>
- <span data-ttu-id="294e1-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="294e1-238">DriversLicence</span></span>
- <span data-ttu-id="294e1-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="294e1-239">DriversLicences</span></span>
- <span data-ttu-id="294e1-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-240">Drivers Lic</span></span>
- <span data-ttu-id="294e1-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="294e1-241">Drivers Lics</span></span>
- <span data-ttu-id="294e1-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-242">Drivers Licence</span></span>
- <span data-ttu-id="294e1-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-243">Drivers Licences</span></span>
- <span data-ttu-id="294e1-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-244">Driver'Lic</span></span>
- <span data-ttu-id="294e1-245">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="294e1-245">Driver'Lics</span></span>
- <span data-ttu-id="294e1-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-246">Driver'Licence</span></span>
- <span data-ttu-id="294e1-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-247">Driver'Licences</span></span>
- <span data-ttu-id="294e1-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-248">Driver' Lic</span></span>
- <span data-ttu-id="294e1-249">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="294e1-249">Driver' Lics</span></span>
- <span data-ttu-id="294e1-250">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-250">Driver' Licence</span></span>
- <span data-ttu-id="294e1-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-251">Driver' Licences</span></span>
- <span data-ttu-id="294e1-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="294e1-252">Driver'sLic</span></span>
- <span data-ttu-id="294e1-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="294e1-253">Driver'sLics</span></span>
- <span data-ttu-id="294e1-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="294e1-254">Driver'sLicence</span></span>
- <span data-ttu-id="294e1-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="294e1-255">Driver'sLicences</span></span>
- <span data-ttu-id="294e1-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-256">Driver's Lic</span></span>
- <span data-ttu-id="294e1-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="294e1-257">Driver's Lics</span></span>
- <span data-ttu-id="294e1-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-258">Driver's Licence</span></span>
- <span data-ttu-id="294e1-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-259">Driver's Licences</span></span>
- <span data-ttu-id="294e1-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="294e1-260">DriverLic#</span></span>
- <span data-ttu-id="294e1-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="294e1-261">DriverLics#</span></span>
- <span data-ttu-id="294e1-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="294e1-262">DriverLicence#</span></span>
- <span data-ttu-id="294e1-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="294e1-263">DriverLicences#</span></span>
- <span data-ttu-id="294e1-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-264">Driver Lic#</span></span>
- <span data-ttu-id="294e1-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-265">Driver Lics#</span></span>
- <span data-ttu-id="294e1-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="294e1-266">Driver Licence#</span></span>
- <span data-ttu-id="294e1-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="294e1-267">Driver Licences#</span></span>
- <span data-ttu-id="294e1-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="294e1-268">DriversLic#</span></span>
- <span data-ttu-id="294e1-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="294e1-269">DriversLics#</span></span>
- <span data-ttu-id="294e1-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="294e1-270">DriversLicence#</span></span>
- <span data-ttu-id="294e1-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="294e1-271">DriversLicences#</span></span>
- <span data-ttu-id="294e1-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-272">Drivers Lic#</span></span>
- <span data-ttu-id="294e1-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-273">Drivers Lics#</span></span>
- <span data-ttu-id="294e1-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="294e1-274">Drivers Licence#</span></span>
- <span data-ttu-id="294e1-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="294e1-275">Drivers Licences#</span></span>
- <span data-ttu-id="294e1-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="294e1-276">Driver'Lic#</span></span>
- <span data-ttu-id="294e1-277">Driver ' LiCS #</span><span class="sxs-lookup"><span data-stu-id="294e1-277">Driver'Lics#</span></span>
- <span data-ttu-id="294e1-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="294e1-278">Driver'Licence#</span></span>
- <span data-ttu-id="294e1-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="294e1-279">Driver'Licences#</span></span>
- <span data-ttu-id="294e1-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-280">Driver' Lic#</span></span>
- <span data-ttu-id="294e1-281">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-281">Driver' Lics#</span></span>
- <span data-ttu-id="294e1-282">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="294e1-282">Driver' Licence#</span></span>
- <span data-ttu-id="294e1-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="294e1-283">Driver' Licences#</span></span>
- <span data-ttu-id="294e1-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="294e1-284">Driver'sLic#</span></span>
- <span data-ttu-id="294e1-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="294e1-285">Driver'sLics#</span></span>
- <span data-ttu-id="294e1-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="294e1-286">Driver'sLicence#</span></span>
- <span data-ttu-id="294e1-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="294e1-287">Driver'sLicences#</span></span>
- <span data-ttu-id="294e1-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-288">Driver's Lic#</span></span>
- <span data-ttu-id="294e1-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-289">Driver's Lics#</span></span>
- <span data-ttu-id="294e1-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="294e1-290">Driver's Licence#</span></span>
- <span data-ttu-id="294e1-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="294e1-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="294e1-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="294e1-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="294e1-293">AAA</span><span class="sxs-lookup"><span data-stu-id="294e1-293">aaa</span></span>
- <span data-ttu-id="294e1-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="294e1-294">DriverLicense</span></span>
- <span data-ttu-id="294e1-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="294e1-295">DriverLicenses</span></span>
- <span data-ttu-id="294e1-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="294e1-296">Driver License</span></span>
- <span data-ttu-id="294e1-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-297">Driver Licenses</span></span>
- <span data-ttu-id="294e1-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="294e1-298">DriversLicense</span></span>
- <span data-ttu-id="294e1-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="294e1-299">DriversLicenses</span></span>
- <span data-ttu-id="294e1-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="294e1-300">Drivers License</span></span>
- <span data-ttu-id="294e1-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-301">Drivers Licenses</span></span>
- <span data-ttu-id="294e1-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="294e1-302">Driver'License</span></span>
- <span data-ttu-id="294e1-303">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-303">Driver'Licenses</span></span>
- <span data-ttu-id="294e1-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="294e1-304">Driver' License</span></span>
- <span data-ttu-id="294e1-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-305">Driver' Licenses</span></span>
- <span data-ttu-id="294e1-306">Secondola</span><span class="sxs-lookup"><span data-stu-id="294e1-306">Driver'sLicense</span></span>
- <span data-ttu-id="294e1-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="294e1-307">Driver'sLicenses</span></span>
- <span data-ttu-id="294e1-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="294e1-308">Driver's License</span></span>
- <span data-ttu-id="294e1-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-309">Driver's Licenses</span></span>
- <span data-ttu-id="294e1-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="294e1-310">DriverLicense#</span></span>
- <span data-ttu-id="294e1-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-311">DriverLicenses#</span></span>
- <span data-ttu-id="294e1-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="294e1-312">Driver License#</span></span>
- <span data-ttu-id="294e1-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-313">Driver Licenses#</span></span>
- <span data-ttu-id="294e1-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="294e1-314">DriversLicense#</span></span>
- <span data-ttu-id="294e1-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-315">DriversLicenses#</span></span>
- <span data-ttu-id="294e1-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="294e1-316">Drivers License#</span></span>
- <span data-ttu-id="294e1-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-317">Drivers Licenses#</span></span>
- <span data-ttu-id="294e1-318">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="294e1-318">Driver'License#</span></span>
- <span data-ttu-id="294e1-319">Driver ' licenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-319">Driver'Licenses#</span></span>
- <span data-ttu-id="294e1-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="294e1-320">Driver' License#</span></span>
- <span data-ttu-id="294e1-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-321">Driver' Licenses#</span></span>
- <span data-ttu-id="294e1-322">Secondola #</span><span class="sxs-lookup"><span data-stu-id="294e1-322">Driver'sLicense#</span></span>
- <span data-ttu-id="294e1-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="294e1-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="294e1-324">Driver's License#</span></span>
- <span data-ttu-id="294e1-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="294e1-326">Australia - Numero di tessera sanitaria</span><span class="sxs-lookup"><span data-stu-id="294e1-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-327">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-327">Format</span></span>

<span data-ttu-id="294e1-328">10-11 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-329">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-329">Pattern</span></span>

<span data-ttu-id="294e1-330">10-11 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-330">10-11 digits:</span></span>
- <span data-ttu-id="294e1-331">La prima cifra è compresa nell'intervallo 2-6</span><span class="sxs-lookup"><span data-stu-id="294e1-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="294e1-332">La nona cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="294e1-333">La decima cifra è la cifra del problema</span><span class="sxs-lookup"><span data-stu-id="294e1-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="294e1-334">L'undicesima cifra (facoltativa) è il numero singolo</span><span class="sxs-lookup"><span data-stu-id="294e1-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-335">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-335">Checksum</span></span>

<span data-ttu-id="294e1-336">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-337">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-337">Definition</span></span>

<span data-ttu-id="294e1-338">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-339">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-340">Viene trovata una parola chiave da Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="294e1-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="294e1-341">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-341">The checksum passes.</span></span>

<span data-ttu-id="294e1-342">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-343">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-344">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-345">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="294e1-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="294e1-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="294e1-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="294e1-347">bank account details</span></span>
- <span data-ttu-id="294e1-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="294e1-348">medicare payments</span></span>
- <span data-ttu-id="294e1-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="294e1-349">mortgage account</span></span>
- <span data-ttu-id="294e1-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="294e1-350">bank payments</span></span>
- <span data-ttu-id="294e1-351">information branch</span><span class="sxs-lookup"><span data-stu-id="294e1-351">information branch</span></span>
- <span data-ttu-id="294e1-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="294e1-352">credit card loan</span></span>
- <span data-ttu-id="294e1-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="294e1-353">department of human services</span></span>
- <span data-ttu-id="294e1-354">local service</span><span class="sxs-lookup"><span data-stu-id="294e1-354">local service</span></span>
- <span data-ttu-id="294e1-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="294e1-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="294e1-356">Australia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-357">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-357">Format</span></span>

<span data-ttu-id="294e1-358">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-359">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-359">Pattern</span></span>

<span data-ttu-id="294e1-360">Una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-361">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-361">Checksum</span></span>

<span data-ttu-id="294e1-362">No</span><span class="sxs-lookup"><span data-stu-id="294e1-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-363">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-363">Definition</span></span>

<span data-ttu-id="294e1-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-365">L'espressione regolare Regex_australia_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-366">Viene trovata una parola chiave da Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-367">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="294e1-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="294e1-368">Keyword_passport</span></span>

- <span data-ttu-id="294e1-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="294e1-369">Passport Number</span></span>
- <span data-ttu-id="294e1-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="294e1-370">Passport No</span></span>
- <span data-ttu-id="294e1-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="294e1-371">Passport #</span></span>
- <span data-ttu-id="294e1-372">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="294e1-372">Passport#</span></span>
- <span data-ttu-id="294e1-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="294e1-373">PassportID</span></span>
- <span data-ttu-id="294e1-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="294e1-374">Passportno</span></span>
- <span data-ttu-id="294e1-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-375">passportnumber</span></span>
- <span data-ttu-id="294e1-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="294e1-376">パスポート</span></span>
- <span data-ttu-id="294e1-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="294e1-377">パスポート番号</span></span>
- <span data-ttu-id="294e1-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="294e1-378">パスポートのNum</span></span>
- <span data-ttu-id="294e1-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="294e1-379">パスポート ＃</span></span> 
- <span data-ttu-id="294e1-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="294e1-380">Numéro de passeport</span></span>
- <span data-ttu-id="294e1-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="294e1-381">Passeport n °</span></span>
- <span data-ttu-id="294e1-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="294e1-382">Passeport Non</span></span>
- <span data-ttu-id="294e1-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="294e1-383">Passeport #</span></span>
- <span data-ttu-id="294e1-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="294e1-384">Passeport#</span></span>
- <span data-ttu-id="294e1-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="294e1-385">PasseportNon</span></span>
- <span data-ttu-id="294e1-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="294e1-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="294e1-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="294e1-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="294e1-388">passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-388">passport</span></span>
- <span data-ttu-id="294e1-389">passport details</span><span class="sxs-lookup"><span data-stu-id="294e1-389">passport details</span></span>
- <span data-ttu-id="294e1-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="294e1-390">immigration and citizenship</span></span>
- <span data-ttu-id="294e1-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="294e1-391">commonwealth of australia</span></span>
- <span data-ttu-id="294e1-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="294e1-392">department of immigration</span></span>
- <span data-ttu-id="294e1-393">residential address</span><span class="sxs-lookup"><span data-stu-id="294e1-393">residential address</span></span>
- <span data-ttu-id="294e1-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="294e1-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="294e1-395">esempio</span><span class="sxs-lookup"><span data-stu-id="294e1-395">visa</span></span>
- <span data-ttu-id="294e1-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="294e1-396">national identity card</span></span>
- <span data-ttu-id="294e1-397">passport number</span><span class="sxs-lookup"><span data-stu-id="294e1-397">passport number</span></span>
- <span data-ttu-id="294e1-398">travel document</span><span class="sxs-lookup"><span data-stu-id="294e1-398">travel document</span></span>
- <span data-ttu-id="294e1-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="294e1-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="294e1-400">Australia - Identificativo fiscale</span><span class="sxs-lookup"><span data-stu-id="294e1-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-401">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-401">Format</span></span>

<span data-ttu-id="294e1-402">8-9 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-403">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-403">Pattern</span></span>

<span data-ttu-id="294e1-404">8-9 cifre in genere presentate con spazi, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="294e1-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="294e1-405">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-405">Three digits</span></span> 
- <span data-ttu-id="294e1-406">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="294e1-406">An optional space</span></span> 
- <span data-ttu-id="294e1-407">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-407">Three digits</span></span> 
- <span data-ttu-id="294e1-408">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="294e1-408">An optional space</span></span> 
- <span data-ttu-id="294e1-409">2-3 cifre e l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-410">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-410">Checksum</span></span>

<span data-ttu-id="294e1-411">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-412">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-412">Definition</span></span>

<span data-ttu-id="294e1-413">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-414">La funzione Func_australian_tax_file_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-415">Non vengono trovate parole chiave da Keyword_Australia_Tax_File_Number o da Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="294e1-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="294e1-416">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="294e1-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="294e1-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="294e1-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="294e1-419">australian business number</span></span>
- <span data-ttu-id="294e1-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="294e1-420">marginal tax rate</span></span>
- <span data-ttu-id="294e1-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="294e1-421">medicare levy</span></span>
- <span data-ttu-id="294e1-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="294e1-422">portfolio number</span></span>
- <span data-ttu-id="294e1-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="294e1-423">service veterans</span></span>
- <span data-ttu-id="294e1-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="294e1-424">withholding tax</span></span>
- <span data-ttu-id="294e1-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="294e1-425">individual tax return</span></span>
- <span data-ttu-id="294e1-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="294e1-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="294e1-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="294e1-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="294e1-428">00000000</span><span class="sxs-lookup"><span data-stu-id="294e1-428">00000000</span></span>
- <span data-ttu-id="294e1-429">11111111</span><span class="sxs-lookup"><span data-stu-id="294e1-429">11111111</span></span>
- <span data-ttu-id="294e1-430">22222222</span><span class="sxs-lookup"><span data-stu-id="294e1-430">22222222</span></span>
- <span data-ttu-id="294e1-431">33333333</span><span class="sxs-lookup"><span data-stu-id="294e1-431">33333333</span></span>
- <span data-ttu-id="294e1-432">44444444</span><span class="sxs-lookup"><span data-stu-id="294e1-432">44444444</span></span>
- <span data-ttu-id="294e1-433">55555555</span><span class="sxs-lookup"><span data-stu-id="294e1-433">55555555</span></span>
- <span data-ttu-id="294e1-434">66666666</span><span class="sxs-lookup"><span data-stu-id="294e1-434">66666666</span></span>
- <span data-ttu-id="294e1-435">77777777</span><span class="sxs-lookup"><span data-stu-id="294e1-435">77777777</span></span>
- <span data-ttu-id="294e1-436">88888888</span><span class="sxs-lookup"><span data-stu-id="294e1-436">88888888</span></span>
- <span data-ttu-id="294e1-437">99999999</span><span class="sxs-lookup"><span data-stu-id="294e1-437">99999999</span></span>
- <span data-ttu-id="294e1-438">000000000</span><span class="sxs-lookup"><span data-stu-id="294e1-438">000000000</span></span>
- <span data-ttu-id="294e1-439">111111111</span><span class="sxs-lookup"><span data-stu-id="294e1-439">111111111</span></span>
- <span data-ttu-id="294e1-440">222222222</span><span class="sxs-lookup"><span data-stu-id="294e1-440">222222222</span></span>
- <span data-ttu-id="294e1-441">333333333</span><span class="sxs-lookup"><span data-stu-id="294e1-441">333333333</span></span>
- <span data-ttu-id="294e1-442">444444444</span><span class="sxs-lookup"><span data-stu-id="294e1-442">444444444</span></span>
- <span data-ttu-id="294e1-443">555555555</span><span class="sxs-lookup"><span data-stu-id="294e1-443">555555555</span></span>
- <span data-ttu-id="294e1-444">666666666</span><span class="sxs-lookup"><span data-stu-id="294e1-444">666666666</span></span>
- <span data-ttu-id="294e1-445">777777777</span><span class="sxs-lookup"><span data-stu-id="294e1-445">777777777</span></span>
- <span data-ttu-id="294e1-446">888888888</span><span class="sxs-lookup"><span data-stu-id="294e1-446">888888888</span></span>
- <span data-ttu-id="294e1-447">999999999</span><span class="sxs-lookup"><span data-stu-id="294e1-447">999999999</span></span>
- <span data-ttu-id="294e1-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="294e1-448">0000000000</span></span>
- <span data-ttu-id="294e1-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="294e1-449">1111111111</span></span>
- <span data-ttu-id="294e1-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="294e1-450">2222222222</span></span>
- <span data-ttu-id="294e1-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="294e1-451">3333333333</span></span>
- <span data-ttu-id="294e1-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="294e1-452">4444444444</span></span>
- <span data-ttu-id="294e1-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="294e1-453">5555555555</span></span>
- <span data-ttu-id="294e1-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="294e1-454">6666666666</span></span>
- <span data-ttu-id="294e1-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="294e1-455">7777777777</span></span>
- <span data-ttu-id="294e1-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="294e1-456">8888888888</span></span>
- <span data-ttu-id="294e1-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="294e1-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="294e1-458">Chiave di autenticazione di DocumentDB di Azure</span><span class="sxs-lookup"><span data-stu-id="294e1-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="294e1-459">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-459">Format</span></span>

<span data-ttu-id="294e1-460">La stringa "DocumentDb" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="294e1-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-461">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-461">Pattern</span></span>

- <span data-ttu-id="294e1-462">La stringa "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="294e1-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="294e1-463">Qualsiasi combinazione tra 3-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="294e1-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="294e1-464">Un simbolo maggiore di (>), un segno di uguale (=), un segno di virgolette (") oppure un apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="294e1-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="294e1-465">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="294e1-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="294e1-466">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-467">Checksum</span></span>

<span data-ttu-id="294e1-468">No</span><span class="sxs-lookup"><span data-stu-id="294e1-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-469">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-469">Definition</span></span>

<span data-ttu-id="294e1-470">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-471">L'espressione regolare CEP_Regex_AzureDocumentDBAuthKey trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-472">L'espressione regolare CEP_CommonExampleKeywords non **trova contenuto** corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-473">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="294e1-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="294e1-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="294e1-475">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="294e1-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="294e1-476">contoso</span><span class="sxs-lookup"><span data-stu-id="294e1-476">contoso</span></span>
- <span data-ttu-id="294e1-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="294e1-477">fabrikam</span></span>
- <span data-ttu-id="294e1-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="294e1-478">northwind</span></span>
- <span data-ttu-id="294e1-479">sandbox</span><span class="sxs-lookup"><span data-stu-id="294e1-479">sandbox</span></span>
- <span data-ttu-id="294e1-480">OneBox</span><span class="sxs-lookup"><span data-stu-id="294e1-480">onebox</span></span>
- <span data-ttu-id="294e1-481">localhost</span><span class="sxs-lookup"><span data-stu-id="294e1-481">localhost</span></span>
- <span data-ttu-id="294e1-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="294e1-482">127.0.0.1</span></span>
- <span data-ttu-id="294e1-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="294e1-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-484">com</span><span class="sxs-lookup"><span data-stu-id="294e1-484">com</span></span>
- <span data-ttu-id="294e1-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="294e1-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-486">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="294e1-487">Stringa di connessione del database di Azure IAAS e stringa di connessione SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="294e1-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="294e1-488">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-488">Format</span></span>

<span data-ttu-id="294e1-489">Stringa "Server", "Server" o "Data Source" seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="294e1-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-490">com "o" cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="294e1-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-491">NET "o" database. Windows.</span><span class="sxs-lookup"><span data-stu-id="294e1-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-492">NET "e la stringa" password "o" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="294e1-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-493">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-493">Pattern</span></span>

- <span data-ttu-id="294e1-494">La stringa "Server", "Server" o "Data Source"</span><span class="sxs-lookup"><span data-stu-id="294e1-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="294e1-495">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-496">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-496">An equal sign (=)</span></span>
- <span data-ttu-id="294e1-497">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-498">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="294e1-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="294e1-499">La stringa "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="294e1-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-500">com "," cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="294e1-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-501">NET "o" database. Windows.</span><span class="sxs-lookup"><span data-stu-id="294e1-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-502">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-502">net"</span></span>
- <span data-ttu-id="294e1-503">Qualsiasi combinazione tra 1-300 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="294e1-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="294e1-504">La stringa "password", "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="294e1-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="294e1-505">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-506">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-506">An equal sign (=)</span></span>
- <span data-ttu-id="294e1-507">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-508">Uno o più caratteri non costituiti da un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="294e1-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="294e1-509">Un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="294e1-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-510">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-510">Checksum</span></span>

<span data-ttu-id="294e1-511">No</span><span class="sxs-lookup"><span data-stu-id="294e1-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-512">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-512">Definition</span></span>

<span data-ttu-id="294e1-513">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-514">L'espressione regolare CEP_Regex_AzureConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-515">L'espressione regolare CEP_CommonExampleKeywords non **trova contenuto** corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-516">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="294e1-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="294e1-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="294e1-518">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="294e1-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="294e1-519">contoso</span><span class="sxs-lookup"><span data-stu-id="294e1-519">contoso</span></span>
- <span data-ttu-id="294e1-520">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="294e1-520">fabrikam</span></span>
- <span data-ttu-id="294e1-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="294e1-521">northwind</span></span>
- <span data-ttu-id="294e1-522">sandbox</span><span class="sxs-lookup"><span data-stu-id="294e1-522">sandbox</span></span>
- <span data-ttu-id="294e1-523">OneBox</span><span class="sxs-lookup"><span data-stu-id="294e1-523">onebox</span></span>
- <span data-ttu-id="294e1-524">localhost</span><span class="sxs-lookup"><span data-stu-id="294e1-524">localhost</span></span>
- <span data-ttu-id="294e1-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="294e1-525">127.0.0.1</span></span>
- <span data-ttu-id="294e1-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="294e1-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-527">com</span><span class="sxs-lookup"><span data-stu-id="294e1-527">com</span></span>
- <span data-ttu-id="294e1-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="294e1-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-529">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="294e1-530">Stringa di connessione di Azure.</span><span class="sxs-lookup"><span data-stu-id="294e1-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="294e1-531">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-531">Format</span></span>

<span data-ttu-id="294e1-532">La stringa "HostName" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="294e1-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-533">NET "e" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="294e1-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-534">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-534">Pattern</span></span>

- <span data-ttu-id="294e1-535">La stringa "HostName"</span><span class="sxs-lookup"><span data-stu-id="294e1-535">The string "HostName"</span></span>
- <span data-ttu-id="294e1-536">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-537">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-537">An equal sign (=)</span></span>
- <span data-ttu-id="294e1-538">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-539">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="294e1-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="294e1-540">La stringa "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="294e1-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-541">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-541">net"</span></span>
- <span data-ttu-id="294e1-542">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="294e1-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="294e1-543">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="294e1-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="294e1-544">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-545">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-545">An equal sign (=)</span></span>
- <span data-ttu-id="294e1-546">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-547">Qualsiasi combinazione di 43 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="294e1-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="294e1-548">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-549">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-549">Checksum</span></span>

<span data-ttu-id="294e1-550">No</span><span class="sxs-lookup"><span data-stu-id="294e1-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-551">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-551">Definition</span></span>

<span data-ttu-id="294e1-552">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-553">L'espressione regolare CEP_Regex_AzureIoTConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-554">L'espressione regolare CEP_CommonExampleKeywords non **trova contenuto** corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-555">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="294e1-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="294e1-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="294e1-557">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="294e1-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="294e1-558">contoso</span><span class="sxs-lookup"><span data-stu-id="294e1-558">contoso</span></span>
- <span data-ttu-id="294e1-559">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="294e1-559">fabrikam</span></span>
- <span data-ttu-id="294e1-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="294e1-560">northwind</span></span>
- <span data-ttu-id="294e1-561">sandbox</span><span class="sxs-lookup"><span data-stu-id="294e1-561">sandbox</span></span>
- <span data-ttu-id="294e1-562">OneBox</span><span class="sxs-lookup"><span data-stu-id="294e1-562">onebox</span></span>
- <span data-ttu-id="294e1-563">localhost</span><span class="sxs-lookup"><span data-stu-id="294e1-563">localhost</span></span>
- <span data-ttu-id="294e1-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="294e1-564">127.0.0.1</span></span>
- <span data-ttu-id="294e1-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="294e1-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-566">com</span><span class="sxs-lookup"><span data-stu-id="294e1-566">com</span></span>
- <span data-ttu-id="294e1-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="294e1-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-568">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="294e1-569">Password per l'impostazione di pubblicazione di Azure</span><span class="sxs-lookup"><span data-stu-id="294e1-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="294e1-570">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-570">Format</span></span>

<span data-ttu-id="294e1-571">La stringa "UserPwd =" seguita da una stringa alfanumerica.</span><span class="sxs-lookup"><span data-stu-id="294e1-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-572">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-572">Pattern</span></span>

- <span data-ttu-id="294e1-573">La stringa "UserPwd ="</span><span class="sxs-lookup"><span data-stu-id="294e1-573">The string "userpwd="</span></span>
- <span data-ttu-id="294e1-574">Qualsiasi combinazione di lettere o cifre minuscole di 60</span><span class="sxs-lookup"><span data-stu-id="294e1-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="294e1-575">Virgolette (")</span><span class="sxs-lookup"><span data-stu-id="294e1-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-576">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-576">Checksum</span></span>

<span data-ttu-id="294e1-577">No</span><span class="sxs-lookup"><span data-stu-id="294e1-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-578">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-578">Definition</span></span>

<span data-ttu-id="294e1-579">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-580">L'espressione regolare CEP_Regex_AzurePublishSettingPasswords trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-581">L'espressione regolare CEP_CommonExampleKeywords non **trova contenuto** corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="294e1-582">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="294e1-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="294e1-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="294e1-584">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="294e1-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="294e1-585">contoso</span><span class="sxs-lookup"><span data-stu-id="294e1-585">contoso</span></span>
- <span data-ttu-id="294e1-586">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="294e1-586">fabrikam</span></span>
- <span data-ttu-id="294e1-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="294e1-587">northwind</span></span>
- <span data-ttu-id="294e1-588">sandbox</span><span class="sxs-lookup"><span data-stu-id="294e1-588">sandbox</span></span>
- <span data-ttu-id="294e1-589">OneBox</span><span class="sxs-lookup"><span data-stu-id="294e1-589">onebox</span></span>
- <span data-ttu-id="294e1-590">localhost</span><span class="sxs-lookup"><span data-stu-id="294e1-590">localhost</span></span>
- <span data-ttu-id="294e1-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="294e1-591">127.0.0.1</span></span>
- <span data-ttu-id="294e1-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="294e1-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-593">com</span><span class="sxs-lookup"><span data-stu-id="294e1-593">com</span></span>
- <span data-ttu-id="294e1-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="294e1-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-595">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="294e1-596">Stringa di connessione della cache di Azure Redis</span><span class="sxs-lookup"><span data-stu-id="294e1-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="294e1-597">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-597">Format</span></span>

<span data-ttu-id="294e1-598">La stringa "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="294e1-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-599">NET "seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="294e1-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-600">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-600">Pattern</span></span>

- <span data-ttu-id="294e1-601">La stringa "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="294e1-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-602">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-602">net"</span></span>
- <span data-ttu-id="294e1-603">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="294e1-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="294e1-604">La stringa "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="294e1-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="294e1-605">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-606">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-606">An equal sign (=)</span></span>
- <span data-ttu-id="294e1-607">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-608">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="294e1-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="294e1-609">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-610">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-610">Checksum</span></span>

<span data-ttu-id="294e1-611">No</span><span class="sxs-lookup"><span data-stu-id="294e1-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-612">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-612">Definition</span></span>

<span data-ttu-id="294e1-613">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-614">L'espressione regolare CEP_Regex_AzureRedisCacheConnectionString trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="294e1-615">L'espressione regolare CEP_CommonExampleKeywords non **trova contenuto** corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-616">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="294e1-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="294e1-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="294e1-618">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="294e1-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="294e1-619">contoso</span><span class="sxs-lookup"><span data-stu-id="294e1-619">contoso</span></span>
- <span data-ttu-id="294e1-620">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="294e1-620">fabrikam</span></span>
- <span data-ttu-id="294e1-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="294e1-621">northwind</span></span>
- <span data-ttu-id="294e1-622">sandbox</span><span class="sxs-lookup"><span data-stu-id="294e1-622">sandbox</span></span>
- <span data-ttu-id="294e1-623">OneBox</span><span class="sxs-lookup"><span data-stu-id="294e1-623">onebox</span></span>
- <span data-ttu-id="294e1-624">localhost</span><span class="sxs-lookup"><span data-stu-id="294e1-624">localhost</span></span>
- <span data-ttu-id="294e1-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="294e1-625">127.0.0.1</span></span>
- <span data-ttu-id="294e1-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="294e1-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-627">com</span><span class="sxs-lookup"><span data-stu-id="294e1-627">com</span></span>
- <span data-ttu-id="294e1-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="294e1-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-629">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="294e1-630">SAS di Azure</span><span class="sxs-lookup"><span data-stu-id="294e1-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="294e1-631">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-631">Format</span></span>

<span data-ttu-id="294e1-632">La stringa "sig" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="294e1-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-633">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-633">Pattern</span></span>

- <span data-ttu-id="294e1-634">La stringa "sig"</span><span class="sxs-lookup"><span data-stu-id="294e1-634">The string "sig"</span></span>
- <span data-ttu-id="294e1-635">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-636">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-636">An equal sign (=)</span></span>
- <span data-ttu-id="294e1-637">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-638">Qualsiasi combinazione tra 43-53 caratteri che sono minuscoli o maiuscoli, cifre o il segno di percentuale (%)</span><span class="sxs-lookup"><span data-stu-id="294e1-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="294e1-639">La stringa "% 3D"</span><span class="sxs-lookup"><span data-stu-id="294e1-639">The string "%3d"</span></span>
- <span data-ttu-id="294e1-640">Qualsiasi carattere che non sia una lettera, una cifra o un segno di percentuale inferiore o maiuscolo (%)</span><span class="sxs-lookup"><span data-stu-id="294e1-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-641">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-641">Checksum</span></span>

<span data-ttu-id="294e1-642">No</span><span class="sxs-lookup"><span data-stu-id="294e1-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-643">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-643">Definition</span></span>

<span data-ttu-id="294e1-644">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-645">L'espressione regolare CEP_Regex_AzureSAS trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="294e1-646">Stringa di connessione bus di servizio di Azure</span><span class="sxs-lookup"><span data-stu-id="294e1-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="294e1-647">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-647">Format</span></span>

<span data-ttu-id="294e1-648">Stringa "EndPoint" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="294e1-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-649">NET "e" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="294e1-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-650">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-650">Pattern</span></span>

- <span data-ttu-id="294e1-651">La stringa "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="294e1-651">The string "EndPoint"</span></span>
- <span data-ttu-id="294e1-652">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-653">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-653">An equal sign (=)</span></span>
- <span data-ttu-id="294e1-654">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-655">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="294e1-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="294e1-656">La stringa "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="294e1-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-657">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-657">net"</span></span>
- <span data-ttu-id="294e1-658">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="294e1-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="294e1-659">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="294e1-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="294e1-660">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-661">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-661">An equal sign (=)</span></span>
- <span data-ttu-id="294e1-662">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-663">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="294e1-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="294e1-664">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-665">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-665">Checksum</span></span>

<span data-ttu-id="294e1-666">No</span><span class="sxs-lookup"><span data-stu-id="294e1-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-667">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-667">Definition</span></span>

<span data-ttu-id="294e1-668">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-669">L'espressione regolare CEP_Regex_AzureServiceBusConnectionString trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="294e1-670">L'espressione regolare CEP_CommonExampleKeywords non **trova contenuto** corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-671">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="294e1-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="294e1-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="294e1-673">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="294e1-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="294e1-674">contoso</span><span class="sxs-lookup"><span data-stu-id="294e1-674">contoso</span></span>
- <span data-ttu-id="294e1-675">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="294e1-675">fabrikam</span></span>
- <span data-ttu-id="294e1-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="294e1-676">northwind</span></span>
- <span data-ttu-id="294e1-677">sandbox</span><span class="sxs-lookup"><span data-stu-id="294e1-677">sandbox</span></span>
- <span data-ttu-id="294e1-678">OneBox</span><span class="sxs-lookup"><span data-stu-id="294e1-678">onebox</span></span>
- <span data-ttu-id="294e1-679">localhost</span><span class="sxs-lookup"><span data-stu-id="294e1-679">localhost</span></span>
- <span data-ttu-id="294e1-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="294e1-680">127.0.0.1</span></span>
- <span data-ttu-id="294e1-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="294e1-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-682">com</span><span class="sxs-lookup"><span data-stu-id="294e1-682">com</span></span>
- <span data-ttu-id="294e1-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="294e1-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-684">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="294e1-685">Chiave dell'account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="294e1-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="294e1-686">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-686">Format</span></span>

<span data-ttu-id="294e1-687">La stringa "DefaultEndpointsProtocol" seguita dai caratteri e dalle stringhe delineate nel modello seguente, inclusa la stringa "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="294e1-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-688">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-688">Pattern</span></span>

- <span data-ttu-id="294e1-689">La stringa "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="294e1-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="294e1-690">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-691">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-691">An equal sign (=)</span></span>
- <span data-ttu-id="294e1-692">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-693">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="294e1-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="294e1-694">La stringa "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="294e1-694">The string "AccountKey"</span></span>
- <span data-ttu-id="294e1-695">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-696">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-696">An equal sign (=)</span></span>
- <span data-ttu-id="294e1-697">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="294e1-698">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="294e1-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="294e1-699">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-700">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-700">Checksum</span></span>

<span data-ttu-id="294e1-701">No</span><span class="sxs-lookup"><span data-stu-id="294e1-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-702">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-702">Definition</span></span>

<span data-ttu-id="294e1-703">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-704">L'espressione regolare CEP_Regex_AzureStorageAccountKey trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-705">L'espressione regolare CEP_AzureEmulatorStorageAccountFilter non **trova contenuto** corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-706">L'espressione regolare CEP_CommonExampleKeywords non **trova contenuto** corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-707">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="294e1-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="294e1-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="294e1-709">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="294e1-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="294e1-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="294e1-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="294e1-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="294e1-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="294e1-712">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="294e1-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="294e1-713">contoso</span><span class="sxs-lookup"><span data-stu-id="294e1-713">contoso</span></span>
- <span data-ttu-id="294e1-714">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="294e1-714">fabrikam</span></span>
- <span data-ttu-id="294e1-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="294e1-715">northwind</span></span>
- <span data-ttu-id="294e1-716">sandbox</span><span class="sxs-lookup"><span data-stu-id="294e1-716">sandbox</span></span>
- <span data-ttu-id="294e1-717">OneBox</span><span class="sxs-lookup"><span data-stu-id="294e1-717">onebox</span></span>
- <span data-ttu-id="294e1-718">localhost</span><span class="sxs-lookup"><span data-stu-id="294e1-718">localhost</span></span>
- <span data-ttu-id="294e1-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="294e1-719">127.0.0.1</span></span>
- <span data-ttu-id="294e1-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="294e1-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-721">com</span><span class="sxs-lookup"><span data-stu-id="294e1-721">com</span></span>
- <span data-ttu-id="294e1-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="294e1-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-723">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="294e1-724">Chiave dell'account di archiviazione di Azure (generico)</span><span class="sxs-lookup"><span data-stu-id="294e1-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-725">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-725">Format</span></span>

<span data-ttu-id="294e1-726">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+), preceduto o seguito dai caratteri delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="294e1-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-727">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-727">Pattern</span></span>

- <span data-ttu-id="294e1-728">0-1 del simbolo maggiore di (>), apostrofo ('), segno di uguale (=), virgolette (") o segno numerico (#)</span><span class="sxs-lookup"><span data-stu-id="294e1-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="294e1-729">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="294e1-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="294e1-730">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="294e1-731">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-731">Checksum</span></span>

<span data-ttu-id="294e1-732">No</span><span class="sxs-lookup"><span data-stu-id="294e1-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-733">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-733">Definition</span></span>

<span data-ttu-id="294e1-734">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-735">L'espressione regolare CEP_Regex_AzureStorageAccountKeyGeneric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="294e1-736">Belgio - Numero nazionale</span><span class="sxs-lookup"><span data-stu-id="294e1-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-737">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-737">Format</span></span>

<span data-ttu-id="294e1-738">11 cifre più delimitatori</span><span class="sxs-lookup"><span data-stu-id="294e1-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-739">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-739">Pattern</span></span>

<span data-ttu-id="294e1-740">11 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="294e1-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="294e1-741">Sei cifre e due punti nel formato AA.MM.GG per data di nascita </span><span class="sxs-lookup"><span data-stu-id="294e1-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="294e1-742">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-742">A hyphen</span></span> 
- <span data-ttu-id="294e1-743">Tre cifre sequenziali (dispari sia per uomini che per donne) </span><span class="sxs-lookup"><span data-stu-id="294e1-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="294e1-744">Un punto</span><span class="sxs-lookup"><span data-stu-id="294e1-744">A period</span></span> 
- <span data-ttu-id="294e1-745">Due cifre, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-746">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-746">Checksum</span></span>

<span data-ttu-id="294e1-747">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-748">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-748">Definition</span></span>

<span data-ttu-id="294e1-749">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-750">La funzione Func_belgium_national_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-751">Viene trovata una parola chiave da Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="294e1-752">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-753">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="294e1-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="294e1-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="294e1-755">Identità</span><span class="sxs-lookup"><span data-stu-id="294e1-755">Identity</span></span>
- <span data-ttu-id="294e1-756">Registrazione</span><span class="sxs-lookup"><span data-stu-id="294e1-756">Registration</span></span>
- <span data-ttu-id="294e1-757">Identificazione</span><span class="sxs-lookup"><span data-stu-id="294e1-757">Identification</span></span> 
- <span data-ttu-id="294e1-758">ID</span><span class="sxs-lookup"><span data-stu-id="294e1-758">ID</span></span> 
- <span data-ttu-id="294e1-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="294e1-759">Identiteitskaart</span></span>
- <span data-ttu-id="294e1-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="294e1-760">Registratie nummer</span></span> 
- <span data-ttu-id="294e1-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="294e1-761">Identificatie nummer</span></span> 
- <span data-ttu-id="294e1-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="294e1-762">Identiteit</span></span>
- <span data-ttu-id="294e1-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="294e1-763">Registratie</span></span>
- <span data-ttu-id="294e1-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="294e1-764">Identificatie</span></span> 
- <span data-ttu-id="294e1-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="294e1-765">Carte d’identité</span></span> 
- <span data-ttu-id="294e1-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="294e1-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="294e1-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="294e1-767">numéro d'identification</span></span>
- <span data-ttu-id="294e1-768">identité</span><span class="sxs-lookup"><span data-stu-id="294e1-768">identité</span></span> 
- <span data-ttu-id="294e1-769">iscrizione</span><span class="sxs-lookup"><span data-stu-id="294e1-769">inscription</span></span> 
- <span data-ttu-id="294e1-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="294e1-770">Identifikation</span></span>
- <span data-ttu-id="294e1-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="294e1-771">Identifizierung</span></span>
- <span data-ttu-id="294e1-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-772">Identifikationsnummer</span></span>
- <span data-ttu-id="294e1-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="294e1-773">Personalausweis</span></span>
- <span data-ttu-id="294e1-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="294e1-774">Registrierung</span></span>
- <span data-ttu-id="294e1-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="294e1-776">Numero CPF Brasile</span><span class="sxs-lookup"><span data-stu-id="294e1-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-777">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-777">Format</span></span>

<span data-ttu-id="294e1-778">11 cifre che includono una cifra di controllo e possono essere formattate o non formattate</span><span class="sxs-lookup"><span data-stu-id="294e1-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-779">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-779">Pattern</span></span>

<span data-ttu-id="294e1-780">Formattato</span><span class="sxs-lookup"><span data-stu-id="294e1-780">Formatted:</span></span>
- <span data-ttu-id="294e1-781">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-781">Three digits</span></span> 
- <span data-ttu-id="294e1-782">Un punto </span><span class="sxs-lookup"><span data-stu-id="294e1-782">A period</span></span> 
- <span data-ttu-id="294e1-783">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-783">Three digits</span></span> 
- <span data-ttu-id="294e1-784">Un punto </span><span class="sxs-lookup"><span data-stu-id="294e1-784">A period</span></span> 
- <span data-ttu-id="294e1-785">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-785">Three digits</span></span> 
- <span data-ttu-id="294e1-786">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-786">A hyphen</span></span> 
- <span data-ttu-id="294e1-787">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-787">Two digits which are check digits</span></span>

<span data-ttu-id="294e1-788">Formattato</span><span class="sxs-lookup"><span data-stu-id="294e1-788">Unformatted:</span></span>
- <span data-ttu-id="294e1-789">11 cifre dove le ultime due sono cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-790">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-790">Checksum</span></span>

<span data-ttu-id="294e1-791">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-792">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-792">Definition</span></span>

<span data-ttu-id="294e1-793">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-794">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-795">Viene trovata una parola chiave da Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="294e1-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="294e1-796">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-796">The checksum passes.</span></span>

<span data-ttu-id="294e1-797">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-798">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-799">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-800">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="294e1-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="294e1-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="294e1-802">CPF</span><span class="sxs-lookup"><span data-stu-id="294e1-802">CPF</span></span>
- <span data-ttu-id="294e1-803">Identificazione</span><span class="sxs-lookup"><span data-stu-id="294e1-803">Identification</span></span>
- <span data-ttu-id="294e1-804">Registrazione</span><span class="sxs-lookup"><span data-stu-id="294e1-804">Registration</span></span>
- <span data-ttu-id="294e1-805">Entrate</span><span class="sxs-lookup"><span data-stu-id="294e1-805">Revenue</span></span>
- <span data-ttu-id="294e1-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="294e1-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="294e1-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="294e1-807">Imposto</span></span> 
- <span data-ttu-id="294e1-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="294e1-808">Identificação</span></span> 
- <span data-ttu-id="294e1-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="294e1-809">Inscrição</span></span> 
- <span data-ttu-id="294e1-810">Receita</span><span class="sxs-lookup"><span data-stu-id="294e1-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="294e1-811">Brasile - Codice fiscale persone giuridiche (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="294e1-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-812">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-812">Format</span></span>

<span data-ttu-id="294e1-813">14 cifre che includono il numero di registrazione, il codice della filiale, le cifre di controllo e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="294e1-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-814">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-814">Pattern</span></span>
<span data-ttu-id="294e1-815">14 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="294e1-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="294e1-816">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-816">Two digits</span></span> 
- <span data-ttu-id="294e1-817">Un punto </span><span class="sxs-lookup"><span data-stu-id="294e1-817">A period</span></span> 
- <span data-ttu-id="294e1-818">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-818">Three digits</span></span> 
- <span data-ttu-id="294e1-819">Un punto </span><span class="sxs-lookup"><span data-stu-id="294e1-819">A period</span></span> 
- <span data-ttu-id="294e1-820">Tre cifre (le prime otto sono il numero di registrazione) </span><span class="sxs-lookup"><span data-stu-id="294e1-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="294e1-821">Una barra</span><span class="sxs-lookup"><span data-stu-id="294e1-821">A forward slash</span></span> 
- <span data-ttu-id="294e1-822">Numero del ramo a quattro cifre </span><span class="sxs-lookup"><span data-stu-id="294e1-822">Four-digit branch number</span></span> 
- <span data-ttu-id="294e1-823">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-823">A hyphen</span></span> 
- <span data-ttu-id="294e1-824">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-825">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-825">Checksum</span></span>

<span data-ttu-id="294e1-826">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-827">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-827">Definition</span></span>

<span data-ttu-id="294e1-828">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-829">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-830">Viene trovata una parola chiave da Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="294e1-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="294e1-831">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-831">The checksum passes.</span></span>

<span data-ttu-id="294e1-832">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-833">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-834">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-835">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="294e1-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="294e1-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="294e1-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="294e1-837">CNPJ</span></span> 
- <span data-ttu-id="294e1-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="294e1-838">CNPJ/MF</span></span> 
- <span data-ttu-id="294e1-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="294e1-839">CNPJ-MF</span></span> 
- <span data-ttu-id="294e1-840">Codice fiscale persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="294e1-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="294e1-841">Registro contribuenti</span><span class="sxs-lookup"><span data-stu-id="294e1-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="294e1-842">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="294e1-842">Legal entity</span></span> 
- <span data-ttu-id="294e1-843">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="294e1-843">Legal entities</span></span> 
- <span data-ttu-id="294e1-844">Stato della registrazione</span><span class="sxs-lookup"><span data-stu-id="294e1-844">Registration Status</span></span> 
- <span data-ttu-id="294e1-845">Business</span><span class="sxs-lookup"><span data-stu-id="294e1-845">Business</span></span> 
- <span data-ttu-id="294e1-846">Company</span><span class="sxs-lookup"><span data-stu-id="294e1-846">Company</span></span>
- <span data-ttu-id="294e1-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="294e1-847">CNPJ</span></span> 
- <span data-ttu-id="294e1-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="294e1-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="294e1-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="294e1-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="294e1-850">CGC</span><span class="sxs-lookup"><span data-stu-id="294e1-850">CGC</span></span> 
- <span data-ttu-id="294e1-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="294e1-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="294e1-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="294e1-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="294e1-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="294e1-853">Situação cadastral</span></span> 
- <span data-ttu-id="294e1-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="294e1-854">Inscrição</span></span> 
- <span data-ttu-id="294e1-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="294e1-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="294e1-856">	Carta d'identità (Brasile) (RG)</span><span class="sxs-lookup"><span data-stu-id="294e1-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-857">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-857">Format</span></span>

<span data-ttu-id="294e1-858">Registro Geral (formato precedente): nove cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="294e1-859">Registro de Identidade (RIC) (nuovo formato): 11 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-860">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-860">Pattern</span></span>

<span data-ttu-id="294e1-861">Registro Geral (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="294e1-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="294e1-862">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-862">Two digits</span></span> 
- <span data-ttu-id="294e1-863">Un punto </span><span class="sxs-lookup"><span data-stu-id="294e1-863">A period</span></span> 
- <span data-ttu-id="294e1-864">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-864">Three digits</span></span> 
- <span data-ttu-id="294e1-865">Un punto </span><span class="sxs-lookup"><span data-stu-id="294e1-865">A period</span></span> 
- <span data-ttu-id="294e1-866">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-866">Three digits</span></span> 
- <span data-ttu-id="294e1-867">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-867">A hyphen</span></span> 
- <span data-ttu-id="294e1-868">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-868">One digit which is a check digit</span></span>

<span data-ttu-id="294e1-869">Registro de Identidade (RIC) (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="294e1-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="294e1-870">10 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-870">10 digits</span></span> 
- <span data-ttu-id="294e1-871">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-871">A hyphen</span></span> 
- <span data-ttu-id="294e1-872">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-873">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-873">Checksum</span></span>

<span data-ttu-id="294e1-874">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-875">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-875">Definition</span></span>

<span data-ttu-id="294e1-876">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-877">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-878">Viene trovata una parola chiave da Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="294e1-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="294e1-879">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-879">The checksum passes.</span></span>

<span data-ttu-id="294e1-880">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-881">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-882">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-883">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="294e1-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="294e1-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="294e1-885">Cédula de Identidade identità Card National ID número de rregistro Registro de Iidentidade registro Geral RG (questa parola chiave è distinzione tra maiuscole e minuscole) RIC (questa parola chiave è distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="294e1-886">Canada - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="294e1-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-887">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-887">Format</span></span>

<span data-ttu-id="294e1-888">7 o 12 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-889">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-889">Pattern</span></span>

<span data-ttu-id="294e1-890">Un numero di conto corrente canadese comprende 7 o 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="294e1-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="294e1-891">Un numero di transito bancario canadese comprende:</span><span class="sxs-lookup"><span data-stu-id="294e1-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="294e1-892">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-892">Five digits</span></span> 
- <span data-ttu-id="294e1-893">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-893">A hyphen</span></span> 
- <span data-ttu-id="294e1-894">Tre cifre o</span><span class="sxs-lookup"><span data-stu-id="294e1-894">Three digits OR</span></span>
- <span data-ttu-id="294e1-895">Uno zero "0"</span><span class="sxs-lookup"><span data-stu-id="294e1-895">A zero "0"</span></span> 
- <span data-ttu-id="294e1-896">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-897">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-897">Checksum</span></span>

<span data-ttu-id="294e1-898">No</span><span class="sxs-lookup"><span data-stu-id="294e1-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-899">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-899">Definition</span></span>

<span data-ttu-id="294e1-900">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-901">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-902">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="294e1-903">L'espressione regolare Regex_canada_bank_account_transit_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="294e1-904">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-905">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-906">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-907">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="294e1-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="294e1-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="294e1-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="294e1-909">canada savings bonds</span></span>
- <span data-ttu-id="294e1-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="294e1-910">canada revenue agency</span></span>
- <span data-ttu-id="294e1-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="294e1-911">canadian financial institution</span></span>
- <span data-ttu-id="294e1-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="294e1-912">direct deposit form</span></span>
- <span data-ttu-id="294e1-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="294e1-913">canadian citizen</span></span>
- <span data-ttu-id="294e1-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="294e1-914">legal representative</span></span>
- <span data-ttu-id="294e1-915">notary public</span><span class="sxs-lookup"><span data-stu-id="294e1-915">notary public</span></span>
- <span data-ttu-id="294e1-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="294e1-916">commissioner for oaths</span></span>
- <span data-ttu-id="294e1-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="294e1-917">child care benefit</span></span>
- <span data-ttu-id="294e1-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="294e1-918">universal child care</span></span>
- <span data-ttu-id="294e1-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="294e1-919">canada child tax benefit</span></span>
- <span data-ttu-id="294e1-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="294e1-920">income tax benefit</span></span>
- <span data-ttu-id="294e1-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="294e1-921">harmonized sales tax</span></span>
- <span data-ttu-id="294e1-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="294e1-922">social insurance number</span></span>
- <span data-ttu-id="294e1-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="294e1-923">income tax refund</span></span>
- <span data-ttu-id="294e1-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="294e1-924">child tax benefit</span></span>
- <span data-ttu-id="294e1-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="294e1-925">territorial payments</span></span>
- <span data-ttu-id="294e1-926">institution number</span><span class="sxs-lookup"><span data-stu-id="294e1-926">institution number</span></span>
- <span data-ttu-id="294e1-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="294e1-927">deposit request</span></span>
- <span data-ttu-id="294e1-928">banking information</span><span class="sxs-lookup"><span data-stu-id="294e1-928">banking information</span></span>
- <span data-ttu-id="294e1-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="294e1-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="294e1-930">Canada - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="294e1-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-931">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-931">Format</span></span>

<span data-ttu-id="294e1-932">Varia in base alla provincia</span><span class="sxs-lookup"><span data-stu-id="294e1-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-933">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-933">Pattern</span></span>

<span data-ttu-id="294e1-934">Vari modelli per Alberta, Columbia Britannica, Manitoba, Nuovo Brunswick, Terranova e Labrador, Nuova Scozia, Ontario, Isola del Principe Edoardo, Quebec e Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="294e1-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-935">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-935">Checksum</span></span>

<span data-ttu-id="294e1-936">No</span><span class="sxs-lookup"><span data-stu-id="294e1-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-937">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-937">Definition</span></span>

<span data-ttu-id="294e1-938">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-939">La funzione Func_[province_name]_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-940">Viene trovata una parola chiave da Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="294e1-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="294e1-941">Viene trovata una parola chiave da Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="294e1-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-942">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="294e1-943">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="294e1-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="294e1-944">L'abbreviazione della provincia, ad esempio, AB</span><span class="sxs-lookup"><span data-stu-id="294e1-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="294e1-945">Il nome della provincia, ad esempio, Alberta</span><span class="sxs-lookup"><span data-stu-id="294e1-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="294e1-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="294e1-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="294e1-947">DL</span><span class="sxs-lookup"><span data-stu-id="294e1-947">DL</span></span>
- <span data-ttu-id="294e1-948">DLS</span><span class="sxs-lookup"><span data-stu-id="294e1-948">DLS</span></span>
- <span data-ttu-id="294e1-949">CDL</span><span class="sxs-lookup"><span data-stu-id="294e1-949">CDL</span></span>
- <span data-ttu-id="294e1-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="294e1-950">CDLS</span></span>
- <span data-ttu-id="294e1-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="294e1-951">DriverLic</span></span>
- <span data-ttu-id="294e1-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="294e1-952">DriverLics</span></span>
- <span data-ttu-id="294e1-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="294e1-953">DriverLicense</span></span>
- <span data-ttu-id="294e1-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="294e1-954">DriverLicenses</span></span>
- <span data-ttu-id="294e1-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="294e1-955">DriverLicence</span></span>
- <span data-ttu-id="294e1-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="294e1-956">DriverLicences</span></span>
- <span data-ttu-id="294e1-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-957">Driver Lic</span></span>
- <span data-ttu-id="294e1-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="294e1-958">Driver Lics</span></span>
- <span data-ttu-id="294e1-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="294e1-959">Driver License</span></span>
- <span data-ttu-id="294e1-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-960">Driver Licenses</span></span>
- <span data-ttu-id="294e1-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-961">Driver Licence</span></span>
- <span data-ttu-id="294e1-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-962">Driver Licences</span></span>
- <span data-ttu-id="294e1-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="294e1-963">DriversLic</span></span>
- <span data-ttu-id="294e1-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="294e1-964">DriversLics</span></span>
- <span data-ttu-id="294e1-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="294e1-965">DriversLicence</span></span>
- <span data-ttu-id="294e1-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="294e1-966">DriversLicences</span></span>
- <span data-ttu-id="294e1-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="294e1-967">DriversLicense</span></span>
- <span data-ttu-id="294e1-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="294e1-968">DriversLicenses</span></span>
- <span data-ttu-id="294e1-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-969">Drivers Lic</span></span>
- <span data-ttu-id="294e1-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="294e1-970">Drivers Lics</span></span>
- <span data-ttu-id="294e1-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="294e1-971">Drivers License</span></span>
- <span data-ttu-id="294e1-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-972">Drivers Licenses</span></span>
- <span data-ttu-id="294e1-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-973">Drivers Licence</span></span>
- <span data-ttu-id="294e1-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-974">Drivers Licences</span></span>
- <span data-ttu-id="294e1-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-975">Driver'Lic</span></span>
- <span data-ttu-id="294e1-976">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="294e1-976">Driver'Lics</span></span>
- <span data-ttu-id="294e1-977">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="294e1-977">Driver'License</span></span>
- <span data-ttu-id="294e1-978">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-978">Driver'Licenses</span></span>
- <span data-ttu-id="294e1-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-979">Driver'Licence</span></span>
- <span data-ttu-id="294e1-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-980">Driver'Licences</span></span>
- <span data-ttu-id="294e1-981">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-981">Driver' Lic</span></span>
- <span data-ttu-id="294e1-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="294e1-982">Driver' Lics</span></span>
- <span data-ttu-id="294e1-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="294e1-983">Driver' License</span></span>
- <span data-ttu-id="294e1-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-984">Driver' Licenses</span></span>
- <span data-ttu-id="294e1-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-985">Driver' Licence</span></span>
- <span data-ttu-id="294e1-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-986">Driver' Licences</span></span>
- <span data-ttu-id="294e1-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="294e1-987">Driver'sLic</span></span>
- <span data-ttu-id="294e1-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="294e1-988">Driver'sLics</span></span>
- <span data-ttu-id="294e1-989">Secondola</span><span class="sxs-lookup"><span data-stu-id="294e1-989">Driver'sLicense</span></span>
- <span data-ttu-id="294e1-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="294e1-990">Driver'sLicenses</span></span>
- <span data-ttu-id="294e1-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="294e1-991">Driver'sLicence</span></span>
- <span data-ttu-id="294e1-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="294e1-992">Driver'sLicences</span></span>
- <span data-ttu-id="294e1-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-993">Driver's Lic</span></span>
- <span data-ttu-id="294e1-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="294e1-994">Driver's Lics</span></span>
- <span data-ttu-id="294e1-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="294e1-995">Driver's License</span></span>
- <span data-ttu-id="294e1-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-996">Driver's Licenses</span></span>
- <span data-ttu-id="294e1-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-997">Driver's Licence</span></span>
- <span data-ttu-id="294e1-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-998">Driver's Licences</span></span>
- <span data-ttu-id="294e1-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="294e1-999">Permis de Conduire</span></span>
- <span data-ttu-id="294e1-1000">id</span><span class="sxs-lookup"><span data-stu-id="294e1-1000">id</span></span>
- <span data-ttu-id="294e1-1001">ID</span><span class="sxs-lookup"><span data-stu-id="294e1-1001">ids</span></span>
- <span data-ttu-id="294e1-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="294e1-1002">idcard number</span></span>
- <span data-ttu-id="294e1-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="294e1-1003">idcard numbers</span></span>
- <span data-ttu-id="294e1-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="294e1-1004">idcard #</span></span>
- <span data-ttu-id="294e1-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="294e1-1005">idcard #s</span></span>
- <span data-ttu-id="294e1-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="294e1-1006">idcard card</span></span>
- <span data-ttu-id="294e1-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1007">idcard cards</span></span>
- <span data-ttu-id="294e1-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="294e1-1008">idcard</span></span>
- <span data-ttu-id="294e1-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="294e1-1009">identification number</span></span>
- <span data-ttu-id="294e1-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="294e1-1010">identification numbers</span></span>
- <span data-ttu-id="294e1-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="294e1-1011">identification #</span></span>
- <span data-ttu-id="294e1-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="294e1-1012">identification #s</span></span>
- <span data-ttu-id="294e1-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="294e1-1013">identification card</span></span>
- <span data-ttu-id="294e1-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1014">identification cards</span></span>
- <span data-ttu-id="294e1-1015">identificazione</span><span class="sxs-lookup"><span data-stu-id="294e1-1015">identification</span></span> 
- <span data-ttu-id="294e1-1016">DL #</span><span class="sxs-lookup"><span data-stu-id="294e1-1016">DL#</span></span>
- <span data-ttu-id="294e1-1017">DLS #</span><span class="sxs-lookup"><span data-stu-id="294e1-1017">DLS#</span></span> 
- <span data-ttu-id="294e1-1018">CDL #</span><span class="sxs-lookup"><span data-stu-id="294e1-1018">CDL#</span></span> 
- <span data-ttu-id="294e1-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="294e1-1019">CDLS#</span></span> 
- <span data-ttu-id="294e1-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="294e1-1020">DriverLic#</span></span> 
- <span data-ttu-id="294e1-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="294e1-1021">DriverLics#</span></span> 
- <span data-ttu-id="294e1-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="294e1-1022">DriverLicense#</span></span> 
- <span data-ttu-id="294e1-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="294e1-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="294e1-1024">DriverLicence#</span></span> 
- <span data-ttu-id="294e1-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="294e1-1025">DriverLicences#</span></span> 
- <span data-ttu-id="294e1-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-1026">Driver Lic#</span></span>
- <span data-ttu-id="294e1-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-1027">Driver Lics#</span></span> 
- <span data-ttu-id="294e1-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="294e1-1028">Driver License#</span></span> 
- <span data-ttu-id="294e1-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="294e1-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="294e1-1030">Driver License#</span></span> 
- <span data-ttu-id="294e1-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="294e1-1031">Driver Licences#</span></span> 
- <span data-ttu-id="294e1-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="294e1-1032">DriversLic#</span></span> 
- <span data-ttu-id="294e1-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="294e1-1033">DriversLics#</span></span> 
- <span data-ttu-id="294e1-1034">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="294e1-1034">DriversLicense#</span></span> 
- <span data-ttu-id="294e1-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="294e1-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="294e1-1036">DriversLicence#</span></span> 
- <span data-ttu-id="294e1-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="294e1-1037">DriversLicences#</span></span> 
- <span data-ttu-id="294e1-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="294e1-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="294e1-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="294e1-1040">Drivers License#</span></span> 
- <span data-ttu-id="294e1-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="294e1-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="294e1-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="294e1-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="294e1-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="294e1-1044">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="294e1-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="294e1-1045">Driver ' LiCS #</span><span class="sxs-lookup"><span data-stu-id="294e1-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="294e1-1046">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="294e1-1046">Driver'License#</span></span> 
- <span data-ttu-id="294e1-1047">Driver ' licenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="294e1-1048">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="294e1-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="294e1-1049">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="294e1-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="294e1-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="294e1-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="294e1-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="294e1-1052">Driver' License#</span></span> 
- <span data-ttu-id="294e1-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="294e1-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="294e1-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="294e1-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="294e1-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="294e1-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="294e1-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="294e1-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="294e1-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="294e1-1058">Secondola #</span><span class="sxs-lookup"><span data-stu-id="294e1-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="294e1-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="294e1-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="294e1-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="294e1-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="294e1-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="294e1-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="294e1-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="294e1-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="294e1-1064">Driver's License#</span></span> 
- <span data-ttu-id="294e1-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="294e1-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="294e1-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="294e1-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="294e1-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="294e1-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="294e1-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="294e1-1069">ID #</span><span class="sxs-lookup"><span data-stu-id="294e1-1069">id#</span></span> 
- <span data-ttu-id="294e1-1070">ID #</span><span class="sxs-lookup"><span data-stu-id="294e1-1070">ids#</span></span> 
- <span data-ttu-id="294e1-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="294e1-1071">idcard card#</span></span> 
- <span data-ttu-id="294e1-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="294e1-1072">idcard cards#</span></span> 
- <span data-ttu-id="294e1-1073">idcard #</span><span class="sxs-lookup"><span data-stu-id="294e1-1073">idcard#</span></span> 
- <span data-ttu-id="294e1-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="294e1-1074">identification card#</span></span> 
- <span data-ttu-id="294e1-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="294e1-1075">identification cards#</span></span> 
- <span data-ttu-id="294e1-1076">identificazione #</span><span class="sxs-lookup"><span data-stu-id="294e1-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="294e1-1077">Canada - Codice del servizio sanitario</span><span class="sxs-lookup"><span data-stu-id="294e1-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1078">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1078">Format</span></span>

<span data-ttu-id="294e1-1079">10 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1080">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1080">Pattern</span></span>

<span data-ttu-id="294e1-1081">10 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1082">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1082">Checksum</span></span>

<span data-ttu-id="294e1-1083">No</span><span class="sxs-lookup"><span data-stu-id="294e1-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1084">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1084">Definition</span></span>

<span data-ttu-id="294e1-1085">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1086">L'espressione regolare Regex_canada_health_service_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1087">Viene trovata una parola chiave da Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-1088">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="294e1-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="294e1-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="294e1-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="294e1-1090">personal health number</span></span>
- <span data-ttu-id="294e1-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="294e1-1091">patient information</span></span>
- <span data-ttu-id="294e1-1092">health services</span><span class="sxs-lookup"><span data-stu-id="294e1-1092">health services</span></span>
- <span data-ttu-id="294e1-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="294e1-1093">speciality services</span></span>
- <span data-ttu-id="294e1-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="294e1-1094">automobile accident</span></span>
- <span data-ttu-id="294e1-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="294e1-1095">patient hospital</span></span>
- <span data-ttu-id="294e1-1096">psichiatra</span><span class="sxs-lookup"><span data-stu-id="294e1-1096">psychiatrist</span></span>
- <span data-ttu-id="294e1-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="294e1-1097">workers compensation</span></span>
- <span data-ttu-id="294e1-1098">Disability</span><span class="sxs-lookup"><span data-stu-id="294e1-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="294e1-1099">Canada - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1100">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1100">Format</span></span>

<span data-ttu-id="294e1-1101">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1102">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1102">Pattern</span></span>

<span data-ttu-id="294e1-1103">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1104">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1104">Checksum</span></span>

<span data-ttu-id="294e1-1105">No</span><span class="sxs-lookup"><span data-stu-id="294e1-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1106">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1106">Definition</span></span>

<span data-ttu-id="294e1-1107">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1108">L'espressione regolare Regex_canada_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1109">Viene trovata una parola chiave da Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="294e1-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-1110">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="294e1-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="294e1-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="294e1-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="294e1-1112">canadian citizenship</span></span>
- <span data-ttu-id="294e1-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="294e1-1113">canadian passport</span></span>
- <span data-ttu-id="294e1-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="294e1-1114">passport application</span></span>
- <span data-ttu-id="294e1-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="294e1-1115">passport photos</span></span>
- <span data-ttu-id="294e1-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="294e1-1116">certified translator</span></span>
- <span data-ttu-id="294e1-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="294e1-1117">canadian citizens</span></span>
- <span data-ttu-id="294e1-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="294e1-1118">processing times</span></span>
- <span data-ttu-id="294e1-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="294e1-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="294e1-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="294e1-1120">Keyword_passport</span></span>

- <span data-ttu-id="294e1-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="294e1-1121">Passport Number</span></span>
- <span data-ttu-id="294e1-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="294e1-1122">Passport No</span></span>
- <span data-ttu-id="294e1-1123">Passport#</span><span class="sxs-lookup"><span data-stu-id="294e1-1123">Passport #</span></span>
- <span data-ttu-id="294e1-1124">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="294e1-1124">Passport#</span></span>
- <span data-ttu-id="294e1-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="294e1-1125">PassportID</span></span>
- <span data-ttu-id="294e1-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="294e1-1126">Passportno</span></span>
- <span data-ttu-id="294e1-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-1127">passportnumber</span></span>
- <span data-ttu-id="294e1-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="294e1-1128">パスポート</span></span>
- <span data-ttu-id="294e1-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="294e1-1129">パスポート番号</span></span>
- <span data-ttu-id="294e1-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="294e1-1130">パスポートのNum</span></span>
- <span data-ttu-id="294e1-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="294e1-1131">パスポート＃</span></span>
- <span data-ttu-id="294e1-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="294e1-1132">Numéro de passeport</span></span>
- <span data-ttu-id="294e1-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="294e1-1133">Passeport n °</span></span>
- <span data-ttu-id="294e1-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="294e1-1134">Passeport Non</span></span>
- <span data-ttu-id="294e1-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="294e1-1135">Passeport #</span></span>
- <span data-ttu-id="294e1-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="294e1-1136">Passeport#</span></span>
- <span data-ttu-id="294e1-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="294e1-1137">PasseportNon</span></span>
- <span data-ttu-id="294e1-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="294e1-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="294e1-1139">Canada - Numero di identificazione sanitaria personale (PHIN)</span><span class="sxs-lookup"><span data-stu-id="294e1-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1140">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1140">Format</span></span>

<span data-ttu-id="294e1-1141">9 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1142">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1142">Pattern</span></span>

<span data-ttu-id="294e1-1143">9 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1144">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1144">Checksum</span></span>

<span data-ttu-id="294e1-1145">No</span><span class="sxs-lookup"><span data-stu-id="294e1-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1146">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1146">Definition</span></span>

<span data-ttu-id="294e1-1147">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_canada_phin trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="294e1-1148">Sono state trovate almeno due parole chiave di Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="294e1-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-1149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="294e1-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="294e1-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="294e1-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="294e1-1151">social insurance number</span></span>
- <span data-ttu-id="294e1-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="294e1-1152">health information act</span></span>
- <span data-ttu-id="294e1-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="294e1-1153">income tax information</span></span>
- <span data-ttu-id="294e1-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="294e1-1154">manitoba health</span></span>
- <span data-ttu-id="294e1-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="294e1-1155">health registration</span></span>
- <span data-ttu-id="294e1-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="294e1-1156">prescription purchases</span></span>
- <span data-ttu-id="294e1-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="294e1-1157">benefit eligibility</span></span>
- <span data-ttu-id="294e1-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="294e1-1158">personal health</span></span>
- <span data-ttu-id="294e1-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="294e1-1159">power of attorney</span></span>
- <span data-ttu-id="294e1-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="294e1-1160">registration number</span></span>
- <span data-ttu-id="294e1-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="294e1-1161">personal health number</span></span>
- <span data-ttu-id="294e1-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="294e1-1162">practitioner referral</span></span>
- <span data-ttu-id="294e1-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="294e1-1163">wellness professional</span></span>
- <span data-ttu-id="294e1-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="294e1-1164">patient referral</span></span>
- <span data-ttu-id="294e1-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="294e1-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="294e1-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="294e1-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="294e1-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="294e1-1167">Nunavut</span></span>
- <span data-ttu-id="294e1-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="294e1-1168">Quebec</span></span>
- <span data-ttu-id="294e1-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="294e1-1169">Northwest Territories</span></span>
- <span data-ttu-id="294e1-1170">Ontario</span><span class="sxs-lookup"><span data-stu-id="294e1-1170">Ontario</span></span>
- <span data-ttu-id="294e1-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="294e1-1171">British Columbia</span></span>
- <span data-ttu-id="294e1-1172">Filippa</span><span class="sxs-lookup"><span data-stu-id="294e1-1172">Alberta</span></span>
- <span data-ttu-id="294e1-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="294e1-1173">Saskatchewan</span></span>
- <span data-ttu-id="294e1-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="294e1-1174">Manitoba</span></span>
- <span data-ttu-id="294e1-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="294e1-1175">Yukon</span></span>
- <span data-ttu-id="294e1-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="294e1-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="294e1-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="294e1-1177">New Brunswick</span></span>
- <span data-ttu-id="294e1-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="294e1-1178">Nova Scotia</span></span>
- <span data-ttu-id="294e1-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="294e1-1179">Prince Edward Island</span></span>
- <span data-ttu-id="294e1-1180">Canada</span><span class="sxs-lookup"><span data-stu-id="294e1-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="294e1-1181">Canada - Numero di assicurazione sociale</span><span class="sxs-lookup"><span data-stu-id="294e1-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1182">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1182">Format</span></span>

<span data-ttu-id="294e1-1183">9 cifre con spazi o lineette facoltativi</span><span class="sxs-lookup"><span data-stu-id="294e1-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1184">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1184">Pattern</span></span>

<span data-ttu-id="294e1-1185">Formattato</span><span class="sxs-lookup"><span data-stu-id="294e1-1185">Formatted:</span></span>
- <span data-ttu-id="294e1-1186">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1186">Three digits</span></span> 
- <span data-ttu-id="294e1-1187">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="294e1-1187">A hyphen or space</span></span> 
- <span data-ttu-id="294e1-1188">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1188">Three digits</span></span> 
- <span data-ttu-id="294e1-1189">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="294e1-1189">A hyphen or space</span></span> 
- <span data-ttu-id="294e1-1190">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1190">Three digits</span></span>

<span data-ttu-id="294e1-1191">Non formattato: nove cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1192">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1192">Checksum</span></span>

<span data-ttu-id="294e1-1193">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1194">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1194">Definition</span></span>

<span data-ttu-id="294e1-1195">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1196">La funzione Func_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1197">Almeno due delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="294e1-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="294e1-1198">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="294e1-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="294e1-1199">Viene trovata una parola chiave da Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="294e1-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="294e1-1200">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="294e1-1201">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1201">The checksum passes.</span></span>

<span data-ttu-id="294e1-1202">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1203">La funzione Func_unformatted_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1204">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="294e1-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="294e1-1205">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-1206">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="294e1-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="294e1-1207">Keyword_sin</span></span>

- <span data-ttu-id="294e1-1208">sin</span><span class="sxs-lookup"><span data-stu-id="294e1-1208">sin</span></span> 
- <span data-ttu-id="294e1-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="294e1-1209">social insurance</span></span> 
- <span data-ttu-id="294e1-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="294e1-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="294e1-1211">peccati</span><span class="sxs-lookup"><span data-stu-id="294e1-1211">sins</span></span> 
- <span data-ttu-id="294e1-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="294e1-1212">ssn</span></span> 
- <span data-ttu-id="294e1-1213">SNSS</span><span class="sxs-lookup"><span data-stu-id="294e1-1213">ssns</span></span> 
- <span data-ttu-id="294e1-1214">social security</span><span class="sxs-lookup"><span data-stu-id="294e1-1214">social security</span></span> 
- <span data-ttu-id="294e1-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="294e1-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="294e1-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="294e1-1216">national identification number</span></span> 
- <span data-ttu-id="294e1-1217">national id</span><span class="sxs-lookup"><span data-stu-id="294e1-1217">national id</span></span> 
- <span data-ttu-id="294e1-1218">sin #</span><span class="sxs-lookup"><span data-stu-id="294e1-1218">sin#</span></span> 
- <span data-ttu-id="294e1-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="294e1-1219">soc ins</span></span> 
- <span data-ttu-id="294e1-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="294e1-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="294e1-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="294e1-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="294e1-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="294e1-1222">driver's license</span></span> 
- <span data-ttu-id="294e1-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="294e1-1223">drivers license</span></span> 
- <span data-ttu-id="294e1-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="294e1-1224">driver's licence</span></span> 
- <span data-ttu-id="294e1-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="294e1-1225">drivers licence</span></span> 
- <span data-ttu-id="294e1-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="294e1-1226">DOB</span></span> 
- <span data-ttu-id="294e1-1227">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-1227">Birthdate</span></span> 
- <span data-ttu-id="294e1-1228">Compleanno</span><span class="sxs-lookup"><span data-stu-id="294e1-1228">Birthday</span></span> 
- <span data-ttu-id="294e1-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="294e1-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="294e1-1230">	Cile - Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="294e1-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1231">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1231">Format</span></span>

<span data-ttu-id="294e1-1232">7-8 cifre più delimitatori una cifra di controllo o una lettera</span><span class="sxs-lookup"><span data-stu-id="294e1-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1233">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1233">Pattern</span></span>

<span data-ttu-id="294e1-1234">7-8 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="294e1-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="294e1-1235">1-2 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1235">1-2 digits</span></span> 
- <span data-ttu-id="294e1-1236">Un punto </span><span class="sxs-lookup"><span data-stu-id="294e1-1236">A period</span></span> 
- <span data-ttu-id="294e1-1237">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1237">Three digits</span></span> 
- <span data-ttu-id="294e1-1238">Un punto </span><span class="sxs-lookup"><span data-stu-id="294e1-1238">A period</span></span> 
- <span data-ttu-id="294e1-1239">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1239">Three digits</span></span> 
- <span data-ttu-id="294e1-1240">Un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-1240">A dash</span></span> 
- <span data-ttu-id="294e1-1241">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1242">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1242">Checksum</span></span>

<span data-ttu-id="294e1-1243">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1244">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1244">Definition</span></span>

<span data-ttu-id="294e1-1245">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1246">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1247">Viene trovata una parola chiave da Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="294e1-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="294e1-1248">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1248">The checksum passes.</span></span>

<span data-ttu-id="294e1-1249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1250">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1251">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-1252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="294e1-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="294e1-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="294e1-1254">Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="294e1-1254">National Identification Number</span></span> 
- <span data-ttu-id="294e1-1255">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="294e1-1255">Identity card</span></span> 
- <span data-ttu-id="294e1-1256">ID</span><span class="sxs-lookup"><span data-stu-id="294e1-1256">ID</span></span> 
- <span data-ttu-id="294e1-1257">Identificazione</span><span class="sxs-lookup"><span data-stu-id="294e1-1257">Identification</span></span> 
- <span data-ttu-id="294e1-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="294e1-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="294e1-1259">Correre</span><span class="sxs-lookup"><span data-stu-id="294e1-1259">RUN</span></span> 
- <span data-ttu-id="294e1-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="294e1-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="294e1-1261">CARREGGIATA</span><span class="sxs-lookup"><span data-stu-id="294e1-1261">RUT</span></span> 
- <span data-ttu-id="294e1-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="294e1-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="294e1-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="294e1-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="294e1-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="294e1-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="294e1-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="294e1-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="294e1-1266">	Numero carta di identità per residenti in Cina (RPC)</span><span class="sxs-lookup"><span data-stu-id="294e1-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1267">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1267">Format</span></span>

<span data-ttu-id="294e1-1268">18 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1269">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1269">Pattern</span></span>

<span data-ttu-id="294e1-1270">18 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-1270">18 digits:</span></span>
- <span data-ttu-id="294e1-1271">Sei cifre, ovvero un codice indirizzo </span><span class="sxs-lookup"><span data-stu-id="294e1-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="294e1-1272">Otto cifre nel formato AAAAMMGG, ovvero la data di nascita </span><span class="sxs-lookup"><span data-stu-id="294e1-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="294e1-1273">Tre cifre, ovvero un codice di ordine </span><span class="sxs-lookup"><span data-stu-id="294e1-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="294e1-1274">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1275">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1275">Checksum</span></span>

<span data-ttu-id="294e1-1276">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1277">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1277">Definition</span></span>

<span data-ttu-id="294e1-1278">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1279">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1280">Viene trovata una parola chiave da Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="294e1-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="294e1-1281">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1281">The checksum passes.</span></span>

<span data-ttu-id="294e1-1282">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1283">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1284">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-1285">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="294e1-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="294e1-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="294e1-1287">Carta d’identità per residenti</span><span class="sxs-lookup"><span data-stu-id="294e1-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="294e1-1288">RPC</span><span class="sxs-lookup"><span data-stu-id="294e1-1288">PRC</span></span> 
- <span data-ttu-id="294e1-1289">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="294e1-1289">National Identification Card</span></span> 
- <span data-ttu-id="294e1-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="294e1-1290">身份证</span></span> 
- <span data-ttu-id="294e1-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="294e1-1291">居民 身份证</span></span> 
- <span data-ttu-id="294e1-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="294e1-1292">居民身份证</span></span> 
- <span data-ttu-id="294e1-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="294e1-1293">鉴定</span></span> 
- <span data-ttu-id="294e1-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="294e1-1294">身分證</span></span> 
- <span data-ttu-id="294e1-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-1295">居民 身份證</span></span>
- <span data-ttu-id="294e1-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="294e1-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="294e1-1297">Credit Card Number</span><span class="sxs-lookup"><span data-stu-id="294e1-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1298">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1298">Format</span></span>

<span data-ttu-id="294e1-1299">16 cifre che possono essere formattate o non formattate (dddddddddddddddd) e devono superare il test di Luhn.</span><span class="sxs-lookup"><span data-stu-id="294e1-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1300">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1300">Pattern</span></span>

<span data-ttu-id="294e1-1301">Modello molto complesso e solido che rileva carte di credito dei maggiori circuiti del mondo, ad esempio, Visa, MasterCard, Discover Card, JCB, American Express, nonché carte regalo e ticket restaurant.</span><span class="sxs-lookup"><span data-stu-id="294e1-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1302">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1302">Checksum</span></span>

<span data-ttu-id="294e1-1303">Yes, il checksum Luhn</span><span class="sxs-lookup"><span data-stu-id="294e1-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1304">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1304">Definition</span></span>

<span data-ttu-id="294e1-1305">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1306">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1307">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-1307">One of the following is true:</span></span>
    - <span data-ttu-id="294e1-1308">Viene trovata una parola chiave da Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="294e1-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="294e1-1309">Viene trovata una parola chiave da Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="294e1-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="294e1-1310">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="294e1-1311">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1311">The checksum passes.</span></span>

<span data-ttu-id="294e1-1312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1313">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1314">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-1315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="294e1-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="294e1-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="294e1-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="294e1-1317">card verification</span></span>
- <span data-ttu-id="294e1-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="294e1-1318">card identification number</span></span>
- <span data-ttu-id="294e1-1319">CVN</span><span class="sxs-lookup"><span data-stu-id="294e1-1319">cvn</span></span>
- <span data-ttu-id="294e1-1320">ID</span><span class="sxs-lookup"><span data-stu-id="294e1-1320">cid</span></span>
- <span data-ttu-id="294e1-1321">CVC2</span><span class="sxs-lookup"><span data-stu-id="294e1-1321">cvc2</span></span>
- <span data-ttu-id="294e1-1322">CVV2</span><span class="sxs-lookup"><span data-stu-id="294e1-1322">cvv2</span></span>
- <span data-ttu-id="294e1-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="294e1-1323">pin block</span></span>
- <span data-ttu-id="294e1-1324">security code</span><span class="sxs-lookup"><span data-stu-id="294e1-1324">security code</span></span>
- <span data-ttu-id="294e1-1325">security number</span><span class="sxs-lookup"><span data-stu-id="294e1-1325">security number</span></span>
- <span data-ttu-id="294e1-1326">security no</span><span class="sxs-lookup"><span data-stu-id="294e1-1326">security no</span></span>
- <span data-ttu-id="294e1-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="294e1-1327">issue number</span></span>
- <span data-ttu-id="294e1-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="294e1-1328">issue no</span></span>
- <span data-ttu-id="294e1-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="294e1-1329">cryptogramme</span></span>
- <span data-ttu-id="294e1-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="294e1-1330">numéro de sécurité</span></span>
- <span data-ttu-id="294e1-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="294e1-1331">numero de securite</span></span>
- <span data-ttu-id="294e1-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="294e1-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="294e1-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="294e1-1334">prüfziffer</span></span>
- <span data-ttu-id="294e1-1335">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="294e1-1335">prufziffer</span></span>
- <span data-ttu-id="294e1-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="294e1-1336">sicherheits Kode</span></span>
- <span data-ttu-id="294e1-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="294e1-1337">sicherheitscode</span></span>
- <span data-ttu-id="294e1-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="294e1-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="294e1-1339">verfalldatum</span></span>
- <span data-ttu-id="294e1-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="294e1-1340">codice di verifica</span></span>
- <span data-ttu-id="294e1-1341">Cod.</span><span class="sxs-lookup"><span data-stu-id="294e1-1341">cod.</span></span> <span data-ttu-id="294e1-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="294e1-1342">sicurezza</span></span>
- <span data-ttu-id="294e1-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="294e1-1343">cod sicurezza</span></span>
- <span data-ttu-id="294e1-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="294e1-1344">n autorizzazione</span></span>
- <span data-ttu-id="294e1-1345">Código</span><span class="sxs-lookup"><span data-stu-id="294e1-1345">código</span></span>
- <span data-ttu-id="294e1-1346">Codigo</span><span class="sxs-lookup"><span data-stu-id="294e1-1346">codigo</span></span>
- <span data-ttu-id="294e1-1347">Cod.</span><span class="sxs-lookup"><span data-stu-id="294e1-1347">cod.</span></span> <span data-ttu-id="294e1-1348">SEG</span><span class="sxs-lookup"><span data-stu-id="294e1-1348">seg</span></span>
- <span data-ttu-id="294e1-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="294e1-1349">cod seg</span></span>
- <span data-ttu-id="294e1-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1350">código de segurança</span></span>
- <span data-ttu-id="294e1-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="294e1-1351">codigo de seguranca</span></span>
- <span data-ttu-id="294e1-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1352">codigo de segurança</span></span>
- <span data-ttu-id="294e1-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="294e1-1353">código de seguranca</span></span>
- <span data-ttu-id="294e1-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="294e1-1354">cód.</span></span> <span data-ttu-id="294e1-1355">Segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1355">segurança</span></span>
- <span data-ttu-id="294e1-1356">Cod.</span><span class="sxs-lookup"><span data-stu-id="294e1-1356">cod.</span></span> <span data-ttu-id="294e1-1357">SEGURANCA Cod.</span><span class="sxs-lookup"><span data-stu-id="294e1-1357">seguranca cod.</span></span> <span data-ttu-id="294e1-1358">Segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1358">segurança</span></span>
- <span data-ttu-id="294e1-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="294e1-1359">cód.</span></span> <span data-ttu-id="294e1-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="294e1-1360">seguranca</span></span>
- <span data-ttu-id="294e1-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1361">cód segurança</span></span>
- <span data-ttu-id="294e1-1362">Cod SEGURANCA Cod Segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="294e1-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="294e1-1363">cód seguranca</span></span>
- <span data-ttu-id="294e1-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="294e1-1364">número de verificação</span></span>
- <span data-ttu-id="294e1-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="294e1-1365">numero de verificacao</span></span>
- <span data-ttu-id="294e1-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="294e1-1366">ablauf</span></span>
- <span data-ttu-id="294e1-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="294e1-1367">gültig bis</span></span>
- <span data-ttu-id="294e1-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="294e1-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="294e1-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="294e1-1369">gultig bis</span></span>
- <span data-ttu-id="294e1-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="294e1-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="294e1-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="294e1-1371">scadenza</span></span>
- <span data-ttu-id="294e1-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="294e1-1372">data scad</span></span>
- <span data-ttu-id="294e1-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="294e1-1373">fecha de expiracion</span></span>
- <span data-ttu-id="294e1-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="294e1-1374">fecha de venc</span></span>
- <span data-ttu-id="294e1-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="294e1-1375">vencimiento</span></span>
- <span data-ttu-id="294e1-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="294e1-1376">válido hasta</span></span>
- <span data-ttu-id="294e1-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="294e1-1377">valido hasta</span></span>
- <span data-ttu-id="294e1-1378">VTO</span><span class="sxs-lookup"><span data-stu-id="294e1-1378">vto</span></span>
- <span data-ttu-id="294e1-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="294e1-1379">data de expiração</span></span>
- <span data-ttu-id="294e1-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="294e1-1380">data de expiracao</span></span>
- <span data-ttu-id="294e1-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="294e1-1381">data em que expira</span></span>
- <span data-ttu-id="294e1-1382">validade</span><span class="sxs-lookup"><span data-stu-id="294e1-1382">validade</span></span>
- <span data-ttu-id="294e1-1383">Valor</span><span class="sxs-lookup"><span data-stu-id="294e1-1383">valor</span></span>
- <span data-ttu-id="294e1-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="294e1-1384">vencimento</span></span>
- <span data-ttu-id="294e1-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="294e1-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="294e1-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="294e1-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="294e1-1387">Amex</span><span class="sxs-lookup"><span data-stu-id="294e1-1387">amex</span></span>
- <span data-ttu-id="294e1-1388">american express</span><span class="sxs-lookup"><span data-stu-id="294e1-1388">american express</span></span>
- <span data-ttu-id="294e1-1389">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="294e1-1389">americanexpress</span></span>
- <span data-ttu-id="294e1-1390">Esempio</span><span class="sxs-lookup"><span data-stu-id="294e1-1390">Visa</span></span>
- <span data-ttu-id="294e1-1391">Mastercard</span><span class="sxs-lookup"><span data-stu-id="294e1-1391">mastercard</span></span>
- <span data-ttu-id="294e1-1392">master card</span><span class="sxs-lookup"><span data-stu-id="294e1-1392">master card</span></span>
- <span data-ttu-id="294e1-1393">MC</span><span class="sxs-lookup"><span data-stu-id="294e1-1393">mc</span></span> 
- <span data-ttu-id="294e1-1394">Mastercard</span><span class="sxs-lookup"><span data-stu-id="294e1-1394">mastercards</span></span>
- <span data-ttu-id="294e1-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1395">master cards</span></span>
- <span data-ttu-id="294e1-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="294e1-1396">diner's Club</span></span>
- <span data-ttu-id="294e1-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="294e1-1397">diners club</span></span>
- <span data-ttu-id="294e1-1398">DinersClub</span><span class="sxs-lookup"><span data-stu-id="294e1-1398">dinersclub</span></span>
- <span data-ttu-id="294e1-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="294e1-1399">discover card</span></span>
- <span data-ttu-id="294e1-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="294e1-1400">discovercard</span></span>
- <span data-ttu-id="294e1-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1401">discover cards</span></span>
- <span data-ttu-id="294e1-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="294e1-1402">JCB</span></span>
- <span data-ttu-id="294e1-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="294e1-1403">japanese card bureau</span></span>
- <span data-ttu-id="294e1-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="294e1-1404">carte blanche</span></span>
- <span data-ttu-id="294e1-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="294e1-1405">carteblanche</span></span>
- <span data-ttu-id="294e1-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="294e1-1406">credit card</span></span>
- <span data-ttu-id="294e1-1407">CC #</span><span class="sxs-lookup"><span data-stu-id="294e1-1407">cc#</span></span>
- <span data-ttu-id="294e1-1408">CC #:</span><span class="sxs-lookup"><span data-stu-id="294e1-1408">cc#:</span></span>
- <span data-ttu-id="294e1-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="294e1-1409">expiration date</span></span>
- <span data-ttu-id="294e1-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="294e1-1410">exp date</span></span>
- <span data-ttu-id="294e1-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="294e1-1411">expiry date</span></span>
- <span data-ttu-id="294e1-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="294e1-1412">date d’expiration</span></span>
- <span data-ttu-id="294e1-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="294e1-1413">date d'exp</span></span>
- <span data-ttu-id="294e1-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="294e1-1414">date expiration</span></span>
- <span data-ttu-id="294e1-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="294e1-1415">bank card</span></span>
- <span data-ttu-id="294e1-1416">Bankcard</span><span class="sxs-lookup"><span data-stu-id="294e1-1416">bankcard</span></span>
- <span data-ttu-id="294e1-1417">card number</span><span class="sxs-lookup"><span data-stu-id="294e1-1417">card number</span></span>
- <span data-ttu-id="294e1-1418">card num</span><span class="sxs-lookup"><span data-stu-id="294e1-1418">card num</span></span>
- <span data-ttu-id="294e1-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-1419">cardnumber</span></span>
- <span data-ttu-id="294e1-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="294e1-1420">cardnumbers</span></span>
- <span data-ttu-id="294e1-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="294e1-1421">card numbers</span></span>
- <span data-ttu-id="294e1-1422">CreditCard</span><span class="sxs-lookup"><span data-stu-id="294e1-1422">creditcard</span></span>
- <span data-ttu-id="294e1-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1423">credit cards</span></span>
- <span data-ttu-id="294e1-1424">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="294e1-1424">creditcards</span></span>
- <span data-ttu-id="294e1-1425">Ccn</span><span class="sxs-lookup"><span data-stu-id="294e1-1425">ccn</span></span>
- <span data-ttu-id="294e1-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="294e1-1426">card holder</span></span>
- <span data-ttu-id="294e1-1427">titolare</span><span class="sxs-lookup"><span data-stu-id="294e1-1427">cardholder</span></span>
- <span data-ttu-id="294e1-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="294e1-1428">card holders</span></span>
- <span data-ttu-id="294e1-1429">titolari</span><span class="sxs-lookup"><span data-stu-id="294e1-1429">cardholders</span></span>
- <span data-ttu-id="294e1-1430">check card</span><span class="sxs-lookup"><span data-stu-id="294e1-1430">check card</span></span>
- <span data-ttu-id="294e1-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="294e1-1431">checkcard</span></span>
- <span data-ttu-id="294e1-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1432">check cards</span></span>
- <span data-ttu-id="294e1-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="294e1-1433">checkcards</span></span>
- <span data-ttu-id="294e1-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="294e1-1434">debit card</span></span>
- <span data-ttu-id="294e1-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="294e1-1435">debitcard</span></span>
- <span data-ttu-id="294e1-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1436">debit cards</span></span>
- <span data-ttu-id="294e1-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="294e1-1437">debitcards</span></span>
- <span data-ttu-id="294e1-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="294e1-1438">atm card</span></span>
- <span data-ttu-id="294e1-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="294e1-1439">atmcard</span></span>
- <span data-ttu-id="294e1-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1440">atm cards</span></span>
- <span data-ttu-id="294e1-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="294e1-1441">atmcards</span></span>
- <span data-ttu-id="294e1-1442">Enroute</span><span class="sxs-lookup"><span data-stu-id="294e1-1442">enroute</span></span>
- <span data-ttu-id="294e1-1443">en route</span><span class="sxs-lookup"><span data-stu-id="294e1-1443">en route</span></span>
- <span data-ttu-id="294e1-1444">card type</span><span class="sxs-lookup"><span data-stu-id="294e1-1444">card type</span></span>
- <span data-ttu-id="294e1-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="294e1-1445">carte bancaire</span></span>
- <span data-ttu-id="294e1-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="294e1-1446">carte de crédit</span></span>
- <span data-ttu-id="294e1-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="294e1-1447">carte de credit</span></span>
- <span data-ttu-id="294e1-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="294e1-1448">numéro de carte</span></span>
- <span data-ttu-id="294e1-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="294e1-1449">numero de carte</span></span>
- <span data-ttu-id="294e1-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="294e1-1450">nº de la carte</span></span>
- <span data-ttu-id="294e1-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="294e1-1451">nº de carte</span></span>
- <span data-ttu-id="294e1-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="294e1-1452">kreditkarte</span></span>
- <span data-ttu-id="294e1-1453">Karte</span><span class="sxs-lookup"><span data-stu-id="294e1-1453">karte</span></span>
- <span data-ttu-id="294e1-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="294e1-1454">karteninhaber</span></span>
- <span data-ttu-id="294e1-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="294e1-1455">karteninhabers</span></span>
- <span data-ttu-id="294e1-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="294e1-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="294e1-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="294e1-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="294e1-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="294e1-1458">kreditkartentyp</span></span>
- <span data-ttu-id="294e1-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="294e1-1459">eigentümername</span></span>
- <span data-ttu-id="294e1-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="294e1-1460">kartennr</span></span> 
- <span data-ttu-id="294e1-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1461">kartennummer</span></span>
- <span data-ttu-id="294e1-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1462">kreditkartennummer</span></span>
- <span data-ttu-id="294e1-1463">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="294e1-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1464">carta di credito</span></span>
- <span data-ttu-id="294e1-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1465">carta credito</span></span>
- <span data-ttu-id="294e1-1466">carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1466">carta</span></span>
- <span data-ttu-id="294e1-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1467">n carta</span></span>
- <span data-ttu-id="294e1-1468">Nr.</span><span class="sxs-lookup"><span data-stu-id="294e1-1468">nr.</span></span> <span data-ttu-id="294e1-1469">carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1469">carta</span></span>
- <span data-ttu-id="294e1-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1470">nr carta</span></span>
- <span data-ttu-id="294e1-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1471">numero carta</span></span>
- <span data-ttu-id="294e1-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1472">numero della carta</span></span>
- <span data-ttu-id="294e1-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1473">numero di carta</span></span>
- <span data-ttu-id="294e1-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1474">tarjeta credito</span></span>
- <span data-ttu-id="294e1-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1475">tarjeta de credito</span></span>
- <span data-ttu-id="294e1-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="294e1-1476">tarjeta crédito</span></span>
- <span data-ttu-id="294e1-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="294e1-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="294e1-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="294e1-1478">tarjeta de atm</span></span>
- <span data-ttu-id="294e1-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="294e1-1479">tarjeta atm</span></span>
- <span data-ttu-id="294e1-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="294e1-1480">tarjeta debito</span></span>
- <span data-ttu-id="294e1-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="294e1-1481">tarjeta de debito</span></span>
- <span data-ttu-id="294e1-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="294e1-1482">tarjeta débito</span></span>
- <span data-ttu-id="294e1-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="294e1-1483">tarjeta de débito</span></span>
- <span data-ttu-id="294e1-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="294e1-1484">nº de tarjeta</span></span>
- <span data-ttu-id="294e1-1485">No.</span><span class="sxs-lookup"><span data-stu-id="294e1-1485">no.</span></span> <span data-ttu-id="294e1-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="294e1-1486">de tarjeta</span></span>
- <span data-ttu-id="294e1-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="294e1-1487">no de tarjeta</span></span>
- <span data-ttu-id="294e1-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="294e1-1488">numero de tarjeta</span></span>
- <span data-ttu-id="294e1-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="294e1-1489">número de tarjeta</span></span>
- <span data-ttu-id="294e1-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="294e1-1490">tarjeta no</span></span>
- <span data-ttu-id="294e1-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="294e1-1491">tarjetahabiente</span></span>
- <span data-ttu-id="294e1-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="294e1-1492">cartão de crédito</span></span>
- <span data-ttu-id="294e1-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1493">cartão de credito</span></span>
- <span data-ttu-id="294e1-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="294e1-1494">cartao de crédito</span></span>
- <span data-ttu-id="294e1-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1495">cartao de credito</span></span>
- <span data-ttu-id="294e1-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="294e1-1496">cartão de débito</span></span>
- <span data-ttu-id="294e1-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="294e1-1497">cartao de débito</span></span>
- <span data-ttu-id="294e1-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="294e1-1498">cartão de debito</span></span>
- <span data-ttu-id="294e1-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="294e1-1499">cartao de debito</span></span>
- <span data-ttu-id="294e1-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="294e1-1500">débito automático</span></span>
- <span data-ttu-id="294e1-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="294e1-1501">debito automatico</span></span>
- <span data-ttu-id="294e1-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1502">número do cartão</span></span>
- <span data-ttu-id="294e1-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1503">numero do cartão</span></span> 
- <span data-ttu-id="294e1-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1504">número do cartao</span></span>
- <span data-ttu-id="294e1-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1505">numero do cartao</span></span>
- <span data-ttu-id="294e1-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1506">número de cartão</span></span>
- <span data-ttu-id="294e1-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1507">numero de cartão</span></span>
- <span data-ttu-id="294e1-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1508">número de cartao</span></span>
- <span data-ttu-id="294e1-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1509">numero de cartao</span></span>
- <span data-ttu-id="294e1-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1510">nº do cartão</span></span>
- <span data-ttu-id="294e1-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1511">nº do cartao</span></span>
- <span data-ttu-id="294e1-1512">n º.</span><span class="sxs-lookup"><span data-stu-id="294e1-1512">nº.</span></span> <span data-ttu-id="294e1-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1513">do cartão</span></span>
- <span data-ttu-id="294e1-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1514">no do cartão</span></span>
- <span data-ttu-id="294e1-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1515">no do cartao</span></span>
- <span data-ttu-id="294e1-1516">No.</span><span class="sxs-lookup"><span data-stu-id="294e1-1516">no.</span></span> <span data-ttu-id="294e1-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1517">do cartão</span></span>
- <span data-ttu-id="294e1-1518">No.</span><span class="sxs-lookup"><span data-stu-id="294e1-1518">no.</span></span> <span data-ttu-id="294e1-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="294e1-1520">Numero di carta di identità della Croazia</span><span class="sxs-lookup"><span data-stu-id="294e1-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1521">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1521">Format</span></span>

<span data-ttu-id="294e1-1522">9 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1523">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1523">Pattern</span></span>

<span data-ttu-id="294e1-1524">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1525">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1525">Checksum</span></span>

<span data-ttu-id="294e1-1526">No</span><span class="sxs-lookup"><span data-stu-id="294e1-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1527">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1527">Definition</span></span>

<span data-ttu-id="294e1-1528">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1529">La funzione Func_croatia_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1530">Viene trovata una parola chiave da Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="294e1-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-1531">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="294e1-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="294e1-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="294e1-1533">Carta d’identità croata</span><span class="sxs-lookup"><span data-stu-id="294e1-1533">Croatian identity card</span></span>
- <span data-ttu-id="294e1-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="294e1-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="294e1-1535">Numero di identificazione personale (OIB) - Croazia</span><span class="sxs-lookup"><span data-stu-id="294e1-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1536">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1536">Format</span></span>

<span data-ttu-id="294e1-1537">11 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1538">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1538">Pattern</span></span>

<span data-ttu-id="294e1-1539">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-1539">11 digits:</span></span>
- <span data-ttu-id="294e1-1540">10 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1540">10 digits</span></span> 
- <span data-ttu-id="294e1-1541">La cifra finale è una cifra di controllo ai fini dello scambio di dati internazionali, le lettere HR vengono aggiunte prima delle undici cifre.</span><span class="sxs-lookup"><span data-stu-id="294e1-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1542">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1542">Checksum</span></span>

<span data-ttu-id="294e1-1543">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1544">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1544">Definition</span></span>

<span data-ttu-id="294e1-1545">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1546">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1547">Viene trovata una parola chiave da Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="294e1-1548">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1548">The checksum passes.</span></span>

<span data-ttu-id="294e1-1549">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1550">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1551">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-1552">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="294e1-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="294e1-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="294e1-1554">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="294e1-1554">Personal Identification Number</span></span>
- <span data-ttu-id="294e1-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="294e1-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="294e1-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="294e1-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="294e1-1557">Numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="294e1-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1558">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1558">Format</span></span>

<span data-ttu-id="294e1-1559">Nove cifre con Slash opzionale (formato precedente) 10 cifre con barra di inoltro facoltativa (nuovo formato)</span><span class="sxs-lookup"><span data-stu-id="294e1-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1560">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1560">Pattern</span></span>

<span data-ttu-id="294e1-1561">Nove cifre (formato obsoleto):</span><span class="sxs-lookup"><span data-stu-id="294e1-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="294e1-1562">9 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1562">Nine digits</span></span>

<span data-ttu-id="294e1-1563">O</span><span class="sxs-lookup"><span data-stu-id="294e1-1563">OR</span></span>

- <span data-ttu-id="294e1-1564">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="294e1-1565">Una barra</span><span class="sxs-lookup"><span data-stu-id="294e1-1565">A forward slash</span></span>
- <span data-ttu-id="294e1-1566">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1566">Three digits</span></span>

<span data-ttu-id="294e1-1567">10 cifre (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="294e1-1567">10 digits (new format):</span></span>
- <span data-ttu-id="294e1-1568">10 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1568">10 digits</span></span>

<span data-ttu-id="294e1-1569">O</span><span class="sxs-lookup"><span data-stu-id="294e1-1569">OR</span></span>

- <span data-ttu-id="294e1-1570">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="294e1-1571">Una barra</span><span class="sxs-lookup"><span data-stu-id="294e1-1571">A forward slash</span></span> 
- <span data-ttu-id="294e1-1572">Quattro cifre in cui l'ultima cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1573">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1573">Checksum</span></span>

<span data-ttu-id="294e1-1574">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1575">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1575">Definition</span></span>

<span data-ttu-id="294e1-1576">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_czech_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="294e1-1577">Viene trovata una parola chiave da Keyword_czech_id_card.</span><span class="sxs-lookup"><span data-stu-id="294e1-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="294e1-1578">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="294e1-1579">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1579">Keywords</span></span>

- <span data-ttu-id="294e1-1580">numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="294e1-1580">czech personal identity number</span></span>
- <span data-ttu-id="294e1-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="294e1-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="294e1-1582">Codice PIN - Danimarca</span><span class="sxs-lookup"><span data-stu-id="294e1-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1583">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1583">Format</span></span>

<span data-ttu-id="294e1-1584">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1585">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1585">Pattern</span></span>

<span data-ttu-id="294e1-1586">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-1586">10 digits:</span></span>
- <span data-ttu-id="294e1-1587">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="294e1-1588">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-1588">A hyphen</span></span> 
- <span data-ttu-id="294e1-1589">Quattro cifre, dove l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1590">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1590">Checksum</span></span>

<span data-ttu-id="294e1-1591">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1592">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1592">Definition</span></span>

<span data-ttu-id="294e1-1593">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_denmark_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="294e1-1594">Viene trovata una parola chiave da Keyword_denmark_id.</span><span class="sxs-lookup"><span data-stu-id="294e1-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="294e1-1595">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-1596">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="294e1-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="294e1-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="294e1-1598">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="294e1-1598">Personal Identification Number</span></span>
- <span data-ttu-id="294e1-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="294e1-1599">CPR</span></span>
- <span data-ttu-id="294e1-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="294e1-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="294e1-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="294e1-1602">Numero della Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="294e1-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1603">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1603">Format</span></span>

<span data-ttu-id="294e1-1604">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1605">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1605">Pattern</span></span>

<span data-ttu-id="294e1-1606">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="294e1-1607">Una lettera (senza distinzione tra maiuscole/minuscole) da questo gruppo di lettere: abcdefghjklmnprstux, ovvero un codice registrante</span><span class="sxs-lookup"><span data-stu-id="294e1-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="294e1-1608">Una lettera (senza distinzione tra maiuscole/minuscole), ovvero la prima lettera del cognome del registrante</span><span class="sxs-lookup"><span data-stu-id="294e1-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="294e1-1609">7 cifre e l'ultima è quella di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1610">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1610">Checksum</span></span>

<span data-ttu-id="294e1-1611">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1612">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1612">Definition</span></span>

<span data-ttu-id="294e1-1613">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1614">La funzione Func_dea_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1615">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-1616">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1616">Keywords</span></span>

<span data-ttu-id="294e1-1617">Nessuno</span><span class="sxs-lookup"><span data-stu-id="294e1-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="294e1-1618">Unione Europea - Numero di carta di debito</span><span class="sxs-lookup"><span data-stu-id="294e1-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1619">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1619">Format</span></span>

<span data-ttu-id="294e1-1620">16 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1621">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1621">Pattern</span></span>

<span data-ttu-id="294e1-1622">Modello molto complesso e solido</span><span class="sxs-lookup"><span data-stu-id="294e1-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1623">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1623">Checksum</span></span>

<span data-ttu-id="294e1-1624">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1625">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1625">Definition</span></span>

<span data-ttu-id="294e1-1626">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1627">La funzione Func_eu_debit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1628">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="294e1-1629">Viene trovata una parola chiave da Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="294e1-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="294e1-1630">Viene trovata una parola chiave da Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="294e1-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="294e1-1631">Viene trovata una parola chiave da Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="294e1-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="294e1-1632">Viene trovata una parola chiave da Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="294e1-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="294e1-1633">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="294e1-1634">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-1635">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="294e1-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="294e1-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="294e1-1637">account number</span><span class="sxs-lookup"><span data-stu-id="294e1-1637">account number</span></span> 
- <span data-ttu-id="294e1-1638">card number</span><span class="sxs-lookup"><span data-stu-id="294e1-1638">card number</span></span> 
- <span data-ttu-id="294e1-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="294e1-1639">card no.</span></span> 
- <span data-ttu-id="294e1-1640">security number</span><span class="sxs-lookup"><span data-stu-id="294e1-1640">security number</span></span> 
- <span data-ttu-id="294e1-1641">CC #</span><span class="sxs-lookup"><span data-stu-id="294e1-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="294e1-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="294e1-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="294e1-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="294e1-1643">acct nbr</span></span> 
- <span data-ttu-id="294e1-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="294e1-1644">acct num</span></span> 
- <span data-ttu-id="294e1-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="294e1-1645">acct no</span></span> 
- <span data-ttu-id="294e1-1646">american express</span><span class="sxs-lookup"><span data-stu-id="294e1-1646">american express</span></span> 
- <span data-ttu-id="294e1-1647">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="294e1-1647">americanexpress</span></span> 
- <span data-ttu-id="294e1-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="294e1-1648">americano espresso</span></span> 
- <span data-ttu-id="294e1-1649">Amex</span><span class="sxs-lookup"><span data-stu-id="294e1-1649">amex</span></span> 
- <span data-ttu-id="294e1-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="294e1-1650">atm card</span></span> 
- <span data-ttu-id="294e1-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1651">atm cards</span></span> 
- <span data-ttu-id="294e1-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="294e1-1652">atm kaart</span></span> 
- <span data-ttu-id="294e1-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="294e1-1653">atmcard</span></span> 
- <span data-ttu-id="294e1-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="294e1-1654">atmcards</span></span> 
- <span data-ttu-id="294e1-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="294e1-1655">atmkaart</span></span> 
- <span data-ttu-id="294e1-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="294e1-1656">atmkaarten</span></span> 
- <span data-ttu-id="294e1-1657">Bancontact</span><span class="sxs-lookup"><span data-stu-id="294e1-1657">bancontact</span></span> 
- <span data-ttu-id="294e1-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="294e1-1658">bank card</span></span> 
- <span data-ttu-id="294e1-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="294e1-1659">bankkaart</span></span> 
- <span data-ttu-id="294e1-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="294e1-1660">card holder</span></span> 
- <span data-ttu-id="294e1-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="294e1-1661">card holders</span></span> 
- <span data-ttu-id="294e1-1662">card num</span><span class="sxs-lookup"><span data-stu-id="294e1-1662">card num</span></span> 
- <span data-ttu-id="294e1-1663">card number</span><span class="sxs-lookup"><span data-stu-id="294e1-1663">card number</span></span> 
- <span data-ttu-id="294e1-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="294e1-1664">card numbers</span></span> 
- <span data-ttu-id="294e1-1665">card type</span><span class="sxs-lookup"><span data-stu-id="294e1-1665">card type</span></span> 
- <span data-ttu-id="294e1-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="294e1-1666">cardano numerico</span></span> 
- <span data-ttu-id="294e1-1667">titolare</span><span class="sxs-lookup"><span data-stu-id="294e1-1667">cardholder</span></span> 
- <span data-ttu-id="294e1-1668">titolari</span><span class="sxs-lookup"><span data-stu-id="294e1-1668">cardholders</span></span> 
- <span data-ttu-id="294e1-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-1669">cardnumber</span></span> 
- <span data-ttu-id="294e1-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="294e1-1670">cardnumbers</span></span> 
- <span data-ttu-id="294e1-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="294e1-1671">carta bianca</span></span> 
- <span data-ttu-id="294e1-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1672">carta credito</span></span> 
- <span data-ttu-id="294e1-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1673">carta di credito</span></span> 
- <span data-ttu-id="294e1-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1674">cartao de credito</span></span> 
- <span data-ttu-id="294e1-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="294e1-1675">cartao de crédito</span></span> 
- <span data-ttu-id="294e1-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="294e1-1676">cartao de debito</span></span> 
- <span data-ttu-id="294e1-1677">○cartao de débito</span><span class="sxs-lookup"><span data-stu-id="294e1-1677">cartao de débito</span></span> 
- <span data-ttu-id="294e1-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="294e1-1678">carte bancaire</span></span> 
- <span data-ttu-id="294e1-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="294e1-1679">carte blanche</span></span> 
- <span data-ttu-id="294e1-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="294e1-1680">carte bleue</span></span> 
- <span data-ttu-id="294e1-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="294e1-1681">carte de credit</span></span> 
- <span data-ttu-id="294e1-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="294e1-1682">carte de crédit</span></span> 
- <span data-ttu-id="294e1-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1683">carte di credito</span></span> 
- <span data-ttu-id="294e1-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="294e1-1684">carteblanche</span></span> 
- <span data-ttu-id="294e1-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1685">cartão de credito</span></span> 
- <span data-ttu-id="294e1-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="294e1-1686">cartão de crédito</span></span> 
- <span data-ttu-id="294e1-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="294e1-1687">cartão de debito</span></span> 
- <span data-ttu-id="294e1-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="294e1-1688">cartão de débito</span></span> 
- <span data-ttu-id="294e1-1689">CB</span><span class="sxs-lookup"><span data-stu-id="294e1-1689">cb</span></span> 
- <span data-ttu-id="294e1-1690">Ccn</span><span class="sxs-lookup"><span data-stu-id="294e1-1690">ccn</span></span> 
- <span data-ttu-id="294e1-1691">check card</span><span class="sxs-lookup"><span data-stu-id="294e1-1691">check card</span></span> 
- <span data-ttu-id="294e1-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1692">check cards</span></span> 
- <span data-ttu-id="294e1-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="294e1-1693">checkcard</span></span>
- <span data-ttu-id="294e1-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="294e1-1694">checkcards</span></span> 
- <span data-ttu-id="294e1-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="294e1-1695">chequekaart</span></span> 
- <span data-ttu-id="294e1-1696">Cirrus</span><span class="sxs-lookup"><span data-stu-id="294e1-1696">cirrus</span></span> 
- <span data-ttu-id="294e1-1697">Cirrus-Edc-Maestro</span><span class="sxs-lookup"><span data-stu-id="294e1-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="294e1-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="294e1-1698">controlekaart</span></span> 
- <span data-ttu-id="294e1-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="294e1-1699">controlekaarten</span></span> 
- <span data-ttu-id="294e1-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="294e1-1700">credit card</span></span> 
- <span data-ttu-id="294e1-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1701">credit cards</span></span> 
- <span data-ttu-id="294e1-1702">CreditCard</span><span class="sxs-lookup"><span data-stu-id="294e1-1702">creditcard</span></span> 
- <span data-ttu-id="294e1-1703">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="294e1-1703">creditcards</span></span> 
- <span data-ttu-id="294e1-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="294e1-1704">debetkaart</span></span> 
- <span data-ttu-id="294e1-1705">carte</span><span class="sxs-lookup"><span data-stu-id="294e1-1705">debetkaarten</span></span> 
- <span data-ttu-id="294e1-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="294e1-1706">debit card</span></span> 
- <span data-ttu-id="294e1-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1707">debit cards</span></span> 
- <span data-ttu-id="294e1-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="294e1-1708">debitcard</span></span> 
- <span data-ttu-id="294e1-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="294e1-1709">debitcards</span></span> 
- <span data-ttu-id="294e1-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="294e1-1710">debito automatico</span></span> 
- <span data-ttu-id="294e1-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="294e1-1711">diners club</span></span> 
- <span data-ttu-id="294e1-1712">DinersClub</span><span class="sxs-lookup"><span data-stu-id="294e1-1712">dinersclub</span></span> 
- <span data-ttu-id="294e1-1713">individuare</span><span class="sxs-lookup"><span data-stu-id="294e1-1713">discover</span></span> 
- <span data-ttu-id="294e1-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="294e1-1714">discover card</span></span> 
- <span data-ttu-id="294e1-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1715">discover cards</span></span> 
- <span data-ttu-id="294e1-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="294e1-1716">discovercard</span></span> 
- <span data-ttu-id="294e1-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="294e1-1717">discovercards</span></span> 
- <span data-ttu-id="294e1-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="294e1-1718">débito automático</span></span>
- <span data-ttu-id="294e1-1719">EDC</span><span class="sxs-lookup"><span data-stu-id="294e1-1719">edc</span></span> 
- <span data-ttu-id="294e1-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="294e1-1720">eigentümername</span></span> 
- <span data-ttu-id="294e1-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="294e1-1721">european debit card</span></span> 
- <span data-ttu-id="294e1-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="294e1-1722">hoofdkaart</span></span> 
- <span data-ttu-id="294e1-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="294e1-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="294e1-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="294e1-1724">in viaggio</span></span> 
- <span data-ttu-id="294e1-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="294e1-1725">japanese card bureau</span></span> 
- <span data-ttu-id="294e1-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="294e1-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="294e1-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="294e1-1727">jcb</span></span> 
- <span data-ttu-id="294e1-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="294e1-1728">kaart</span></span> 
- <span data-ttu-id="294e1-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="294e1-1729">kaart num</span></span> 
- <span data-ttu-id="294e1-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="294e1-1730">kaartaantal</span></span> 
- <span data-ttu-id="294e1-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="294e1-1731">kaartaantallen</span></span> 
- <span data-ttu-id="294e1-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="294e1-1732">kaarthouder</span></span> 
- <span data-ttu-id="294e1-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="294e1-1733">kaarthouders</span></span> 
- <span data-ttu-id="294e1-1734">Karte</span><span class="sxs-lookup"><span data-stu-id="294e1-1734">karte</span></span>  
- <span data-ttu-id="294e1-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="294e1-1735">karteninhaber</span></span> 
- <span data-ttu-id="294e1-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="294e1-1736">karteninhabers</span></span>
- <span data-ttu-id="294e1-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="294e1-1737">kartennr</span></span> 
- <span data-ttu-id="294e1-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1738">kartennummer</span></span> 
- <span data-ttu-id="294e1-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="294e1-1739">kreditkarte</span></span> 
- <span data-ttu-id="294e1-1740">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="294e1-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="294e1-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="294e1-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="294e1-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="294e1-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="294e1-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="294e1-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="294e1-1745">Maestro</span><span class="sxs-lookup"><span data-stu-id="294e1-1745">maestro</span></span> 
- <span data-ttu-id="294e1-1746">master card</span><span class="sxs-lookup"><span data-stu-id="294e1-1746">master card</span></span> 
- <span data-ttu-id="294e1-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="294e1-1747">master cards</span></span> 
- <span data-ttu-id="294e1-1748">Mastercard</span><span class="sxs-lookup"><span data-stu-id="294e1-1748">mastercard</span></span> 
- <span data-ttu-id="294e1-1749">Mastercard</span><span class="sxs-lookup"><span data-stu-id="294e1-1749">mastercards</span></span> 
- <span data-ttu-id="294e1-1750">MC</span><span class="sxs-lookup"><span data-stu-id="294e1-1750">mc</span></span> 
- <span data-ttu-id="294e1-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="294e1-1751">mister cash</span></span> 
- <span data-ttu-id="294e1-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1752">n carta</span></span> 
- <span data-ttu-id="294e1-1753">carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1753">carta</span></span> 
- <span data-ttu-id="294e1-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="294e1-1754">no de tarjeta</span></span> 
- <span data-ttu-id="294e1-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1755">no do cartao</span></span> 
- <span data-ttu-id="294e1-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1756">no do cartão</span></span> 
- <span data-ttu-id="294e1-1757">No.</span><span class="sxs-lookup"><span data-stu-id="294e1-1757">no.</span></span> <span data-ttu-id="294e1-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="294e1-1758">de tarjeta</span></span> 
- <span data-ttu-id="294e1-1759">No.</span><span class="sxs-lookup"><span data-stu-id="294e1-1759">no.</span></span> <span data-ttu-id="294e1-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1760">do cartao</span></span> 
- <span data-ttu-id="294e1-1761">No.</span><span class="sxs-lookup"><span data-stu-id="294e1-1761">no.</span></span> <span data-ttu-id="294e1-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1762">do cartão</span></span> 
- <span data-ttu-id="294e1-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1763">nr carta</span></span> 
- <span data-ttu-id="294e1-1764">Nr.</span><span class="sxs-lookup"><span data-stu-id="294e1-1764">nr.</span></span> <span data-ttu-id="294e1-1765">carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1765">carta</span></span> 
- <span data-ttu-id="294e1-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="294e1-1766">numeri di scheda</span></span> 
- <span data-ttu-id="294e1-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1767">numero carta</span></span> 
- <span data-ttu-id="294e1-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1768">numero de cartao</span></span> 
- <span data-ttu-id="294e1-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="294e1-1769">numero de carte</span></span> 
- <span data-ttu-id="294e1-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1770">numero de cartão</span></span> 
- <span data-ttu-id="294e1-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="294e1-1771">numero de tarjeta</span></span>
- <span data-ttu-id="294e1-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1772">numero della carta</span></span> 
- <span data-ttu-id="294e1-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1773">numero di carta</span></span> 
- <span data-ttu-id="294e1-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="294e1-1774">numero di scheda</span></span> 
- <span data-ttu-id="294e1-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1775">numero do cartao</span></span> 
- <span data-ttu-id="294e1-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1776">numero do cartão</span></span> 
- <span data-ttu-id="294e1-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="294e1-1777">numéro de carte</span></span> 
- <span data-ttu-id="294e1-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="294e1-1778">nº carta</span></span> 
- <span data-ttu-id="294e1-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="294e1-1779">nº de carte</span></span> 
- <span data-ttu-id="294e1-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="294e1-1780">nº de la carte</span></span> 
- <span data-ttu-id="294e1-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="294e1-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="294e1-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1782">nº do cartao</span></span> 
- <span data-ttu-id="294e1-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1783">nº do cartão</span></span> 
- <span data-ttu-id="294e1-1784">n º.</span><span class="sxs-lookup"><span data-stu-id="294e1-1784">nº.</span></span> <span data-ttu-id="294e1-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1785">do cartão</span></span> 
- <span data-ttu-id="294e1-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1786">número de cartao</span></span> 
- <span data-ttu-id="294e1-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="294e1-1787">número de cartão</span></span> 
- <span data-ttu-id="294e1-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="294e1-1788">número de tarjeta</span></span> 
- <span data-ttu-id="294e1-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="294e1-1789">número do cartao</span></span> 
- <span data-ttu-id="294e1-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="294e1-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="294e1-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="294e1-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="294e1-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="294e1-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="294e1-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="294e1-1793">scheda della banca</span></span> 
- <span data-ttu-id="294e1-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-1794">scheda di controllo</span></span> 
- <span data-ttu-id="294e1-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="294e1-1795">scheda di debito</span></span> 
- <span data-ttu-id="294e1-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="294e1-1796">scheda matrice</span></span> 
- <span data-ttu-id="294e1-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="294e1-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="294e1-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-1798">schede di controllo</span></span> 
- <span data-ttu-id="294e1-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="294e1-1799">schede di debito</span></span> 
- <span data-ttu-id="294e1-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="294e1-1800">schede matrici</span></span> 
- <span data-ttu-id="294e1-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="294e1-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="294e1-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="294e1-1802">scoprono le schede</span></span> 
- <span data-ttu-id="294e1-1803">solo</span><span class="sxs-lookup"><span data-stu-id="294e1-1803">solo</span></span> 
- <span data-ttu-id="294e1-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="294e1-1804">supporti di scheda</span></span> 
- <span data-ttu-id="294e1-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="294e1-1805">supporto di scheda</span></span> 
- <span data-ttu-id="294e1-1806">opzione</span><span class="sxs-lookup"><span data-stu-id="294e1-1806">switch</span></span> 
- <span data-ttu-id="294e1-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="294e1-1807">tarjeta atm</span></span> 
- <span data-ttu-id="294e1-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1808">tarjeta credito</span></span> 
- <span data-ttu-id="294e1-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="294e1-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="294e1-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="294e1-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="294e1-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="294e1-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="294e1-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="294e1-1812">tarjeta debito</span></span> 
- <span data-ttu-id="294e1-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="294e1-1813">tarjeta no</span></span>
- <span data-ttu-id="294e1-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="294e1-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="294e1-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="294e1-1815">tipo della scheda</span></span> 
- <span data-ttu-id="294e1-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="294e1-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="294e1-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="294e1-1817">scheda</span></span> 
- <span data-ttu-id="294e1-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="294e1-1818">v pay</span></span> 
- <span data-ttu-id="294e1-1819">v-pay</span><span class="sxs-lookup"><span data-stu-id="294e1-1819">v-pay</span></span> 
- <span data-ttu-id="294e1-1820">esempio</span><span class="sxs-lookup"><span data-stu-id="294e1-1820">visa</span></span> 
- <span data-ttu-id="294e1-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="294e1-1821">visa plus</span></span> 
- <span data-ttu-id="294e1-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="294e1-1822">visa electron</span></span> 
- <span data-ttu-id="294e1-1823">visto</span><span class="sxs-lookup"><span data-stu-id="294e1-1823">visto</span></span> 
- <span data-ttu-id="294e1-1824">Visum</span><span class="sxs-lookup"><span data-stu-id="294e1-1824">visum</span></span> 
- <span data-ttu-id="294e1-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="294e1-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="294e1-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="294e1-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="294e1-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="294e1-1827">card identification number</span></span>
- <span data-ttu-id="294e1-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="294e1-1828">card verification</span></span> 
- <span data-ttu-id="294e1-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="294e1-1829">cardi la verifica</span></span> 
- <span data-ttu-id="294e1-1830">ID</span><span class="sxs-lookup"><span data-stu-id="294e1-1830">cid</span></span> 
- <span data-ttu-id="294e1-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="294e1-1831">cod seg</span></span> 
- <span data-ttu-id="294e1-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="294e1-1832">cod seguranca</span></span> 
- <span data-ttu-id="294e1-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1833">cod segurança</span></span> 
- <span data-ttu-id="294e1-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="294e1-1834">cod sicurezza</span></span> 
- <span data-ttu-id="294e1-1835">Cod.</span><span class="sxs-lookup"><span data-stu-id="294e1-1835">cod.</span></span> <span data-ttu-id="294e1-1836">SEG</span><span class="sxs-lookup"><span data-stu-id="294e1-1836">seg</span></span> 
- <span data-ttu-id="294e1-1837">Cod.</span><span class="sxs-lookup"><span data-stu-id="294e1-1837">cod.</span></span> <span data-ttu-id="294e1-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="294e1-1838">seguranca</span></span> 
- <span data-ttu-id="294e1-1839">Cod.</span><span class="sxs-lookup"><span data-stu-id="294e1-1839">cod.</span></span> <span data-ttu-id="294e1-1840">Segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1840">segurança</span></span> 
- <span data-ttu-id="294e1-1841">Cod.</span><span class="sxs-lookup"><span data-stu-id="294e1-1841">cod.</span></span> <span data-ttu-id="294e1-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="294e1-1842">sicurezza</span></span> 
- <span data-ttu-id="294e1-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="294e1-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="294e1-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="294e1-1844">codice di verifica</span></span> 
- <span data-ttu-id="294e1-1845">Codigo</span><span class="sxs-lookup"><span data-stu-id="294e1-1845">codigo</span></span> 
- <span data-ttu-id="294e1-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="294e1-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="294e1-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1847">codigo de segurança</span></span> 
- <span data-ttu-id="294e1-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="294e1-1848">crittogramma</span></span> 
- <span data-ttu-id="294e1-1849">crittogramma</span><span class="sxs-lookup"><span data-stu-id="294e1-1849">cryptogram</span></span> 
- <span data-ttu-id="294e1-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="294e1-1850">cryptogramme</span></span> 
- <span data-ttu-id="294e1-1851">CV2</span><span class="sxs-lookup"><span data-stu-id="294e1-1851">cv2</span></span> 
- <span data-ttu-id="294e1-1852">CVC</span><span class="sxs-lookup"><span data-stu-id="294e1-1852">cvc</span></span> 
- <span data-ttu-id="294e1-1853">CVC2</span><span class="sxs-lookup"><span data-stu-id="294e1-1853">cvc2</span></span> 
- <span data-ttu-id="294e1-1854">CVN</span><span class="sxs-lookup"><span data-stu-id="294e1-1854">cvn</span></span> 
- <span data-ttu-id="294e1-1855">CVV</span><span class="sxs-lookup"><span data-stu-id="294e1-1855">cvv</span></span> 
- <span data-ttu-id="294e1-1856">CVV2</span><span class="sxs-lookup"><span data-stu-id="294e1-1856">cvv2</span></span> 
- <span data-ttu-id="294e1-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="294e1-1857">cód seguranca</span></span> 
- <span data-ttu-id="294e1-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1858">cód segurança</span></span> 
- <span data-ttu-id="294e1-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="294e1-1859">cód.</span></span> <span data-ttu-id="294e1-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="294e1-1860">seguranca</span></span> 
- <span data-ttu-id="294e1-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="294e1-1861">cód.</span></span> <span data-ttu-id="294e1-1862">Segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1862">segurança</span></span> 
- <span data-ttu-id="294e1-1863">Código</span><span class="sxs-lookup"><span data-stu-id="294e1-1863">código</span></span> 
- <span data-ttu-id="294e1-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="294e1-1864">código de seguranca</span></span> 
- <span data-ttu-id="294e1-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="294e1-1865">código de segurança</span></span> 
- <span data-ttu-id="294e1-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="294e1-1866">de kaart controle</span></span> 
- <span data-ttu-id="294e1-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="294e1-1867">geeft nr uit</span></span> 
- <span data-ttu-id="294e1-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="294e1-1868">issue no</span></span> 
- <span data-ttu-id="294e1-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="294e1-1869">issue number</span></span> 
- <span data-ttu-id="294e1-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="294e1-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="294e1-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="294e1-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="294e1-1873">kwestieaantal</span></span> 
- <span data-ttu-id="294e1-1874">No.</span><span class="sxs-lookup"><span data-stu-id="294e1-1874">no.</span></span> <span data-ttu-id="294e1-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1875">dell'edizione</span></span> 
- <span data-ttu-id="294e1-1876">No.</span><span class="sxs-lookup"><span data-stu-id="294e1-1876">no.</span></span> <span data-ttu-id="294e1-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="294e1-1877">di sicurezza</span></span> 
- <span data-ttu-id="294e1-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="294e1-1878">numero de securite</span></span> 
- <span data-ttu-id="294e1-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="294e1-1879">numero de verificacao</span></span> 
- <span data-ttu-id="294e1-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="294e1-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="294e1-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="294e1-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="294e1-1882">scheda</span></span> 
- <span data-ttu-id="294e1-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="294e1-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="294e1-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="294e1-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="294e1-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="294e1-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="294e1-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="294e1-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="294e1-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="294e1-1887">número de verificação</span></span> 
- <span data-ttu-id="294e1-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="294e1-1888">perno il blocco</span></span> 
- <span data-ttu-id="294e1-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="294e1-1889">pin block</span></span> 
- <span data-ttu-id="294e1-1890">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="294e1-1890">prufziffer</span></span> 
- <span data-ttu-id="294e1-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="294e1-1891">prüfziffer</span></span> 
- <span data-ttu-id="294e1-1892">security code</span><span class="sxs-lookup"><span data-stu-id="294e1-1892">security code</span></span> 
- <span data-ttu-id="294e1-1893">security no</span><span class="sxs-lookup"><span data-stu-id="294e1-1893">security no</span></span> 
- <span data-ttu-id="294e1-1894">security number</span><span class="sxs-lookup"><span data-stu-id="294e1-1894">security number</span></span> 
- <span data-ttu-id="294e1-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="294e1-1895">sicherheits kode</span></span> 
- <span data-ttu-id="294e1-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="294e1-1896">sicherheitscode</span></span> 
- <span data-ttu-id="294e1-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="294e1-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="294e1-1898">speldblok</span></span> 
- <span data-ttu-id="294e1-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="294e1-1899">veiligheid nr</span></span> 
- <span data-ttu-id="294e1-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="294e1-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="294e1-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="294e1-1901">veiligheidscode</span></span> 
- <span data-ttu-id="294e1-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="294e1-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="294e1-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="294e1-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="294e1-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="294e1-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="294e1-1905">ablauf</span></span> 
- <span data-ttu-id="294e1-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="294e1-1906">data de expiracao</span></span> 
- <span data-ttu-id="294e1-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="294e1-1907">data de expiração</span></span> 
- <span data-ttu-id="294e1-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="294e1-1908">data del exp</span></span> 
- <span data-ttu-id="294e1-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="294e1-1909">data di exp</span></span> 
- <span data-ttu-id="294e1-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="294e1-1910">data di scadenza</span></span> 
- <span data-ttu-id="294e1-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="294e1-1911">data em que expira</span></span> 
- <span data-ttu-id="294e1-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="294e1-1912">data scad</span></span> 
- <span data-ttu-id="294e1-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="294e1-1913">data scadenza</span></span> 
- <span data-ttu-id="294e1-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="294e1-1914">date de validité</span></span> 
- <span data-ttu-id="294e1-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="294e1-1915">datum afloop</span></span> 
- <span data-ttu-id="294e1-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="294e1-1916">datum van exp</span></span> 
- <span data-ttu-id="294e1-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="294e1-1917">de afloop</span></span> 
- <span data-ttu-id="294e1-1918">espira</span><span class="sxs-lookup"><span data-stu-id="294e1-1918">espira</span></span> 
- <span data-ttu-id="294e1-1919">espira</span><span class="sxs-lookup"><span data-stu-id="294e1-1919">espira</span></span> 
- <span data-ttu-id="294e1-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="294e1-1920">exp date</span></span> 
- <span data-ttu-id="294e1-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="294e1-1921">exp datum</span></span> 
- <span data-ttu-id="294e1-1922">scadenza</span><span class="sxs-lookup"><span data-stu-id="294e1-1922">expiration</span></span> 
- <span data-ttu-id="294e1-1923">scadenza</span><span class="sxs-lookup"><span data-stu-id="294e1-1923">expire</span></span> 
- <span data-ttu-id="294e1-1924">scade</span><span class="sxs-lookup"><span data-stu-id="294e1-1924">expires</span></span> 
- <span data-ttu-id="294e1-1925">scadenza</span><span class="sxs-lookup"><span data-stu-id="294e1-1925">expiry</span></span> 
- <span data-ttu-id="294e1-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="294e1-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="294e1-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="294e1-1927">fecha de venc</span></span> 
- <span data-ttu-id="294e1-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="294e1-1928">gultig bis</span></span> 
- <span data-ttu-id="294e1-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="294e1-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="294e1-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="294e1-1930">gültig bis</span></span> 
- <span data-ttu-id="294e1-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="294e1-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="294e1-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="294e1-1932">la scadenza</span></span> 
- <span data-ttu-id="294e1-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="294e1-1933">scadenza</span></span> 
- <span data-ttu-id="294e1-1934">valable</span><span class="sxs-lookup"><span data-stu-id="294e1-1934">valable</span></span> 
- <span data-ttu-id="294e1-1935">validade</span><span class="sxs-lookup"><span data-stu-id="294e1-1935">validade</span></span> 
- <span data-ttu-id="294e1-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="294e1-1936">valido hasta</span></span> 
- <span data-ttu-id="294e1-1937">Valor</span><span class="sxs-lookup"><span data-stu-id="294e1-1937">valor</span></span> 
- <span data-ttu-id="294e1-1938">venc</span><span class="sxs-lookup"><span data-stu-id="294e1-1938">venc</span></span> 
- <span data-ttu-id="294e1-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="294e1-1939">vencimento</span></span> 
- <span data-ttu-id="294e1-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="294e1-1940">vencimiento</span></span> 
- <span data-ttu-id="294e1-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="294e1-1941">verloopt</span></span> 
- <span data-ttu-id="294e1-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="294e1-1942">vervaldag</span></span> 
- <span data-ttu-id="294e1-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="294e1-1943">vervaldatum</span></span> 
- <span data-ttu-id="294e1-1944">VTO</span><span class="sxs-lookup"><span data-stu-id="294e1-1944">vto</span></span> 
- <span data-ttu-id="294e1-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="294e1-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="294e1-1946">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="294e1-1946">EU Driver's License Number</span></span>

<span data-ttu-id="294e1-1947">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di patente dell'Unione europea](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="294e1-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="294e1-1948">Numero di identificazione nazionale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="294e1-1948">EU National Identification Number</span></span>

<span data-ttu-id="294e1-1949">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione nazionale dell'Unione europea](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="294e1-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="294e1-1950">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="294e1-1950">EU Passport Number</span></span>

<span data-ttu-id="294e1-1951">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di passaporto dell'Unione europea](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="294e1-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="294e1-1952">Codice di previdenza sociale dell'Unione europea o ID equivalente</span><span class="sxs-lookup"><span data-stu-id="294e1-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="294e1-1953">Per ulteriori informazioni, vedere [codice di previdenza sociale dell'Unione europea o tipo di dati sensibili ID equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="294e1-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="294e1-1954">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="294e1-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="294e1-1955">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione fiscale dell'Unione europea](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="294e1-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="294e1-1956">Finland National ID</span><span class="sxs-lookup"><span data-stu-id="294e1-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1957">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1957">Format</span></span>

<span data-ttu-id="294e1-1958">6 cifre, un carattere di indicazione del secolo, tre cifre più una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1959">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1959">Pattern</span></span>

<span data-ttu-id="294e1-1960">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="294e1-1961">Sei cifre nel formato DDMMYY che corrisponde alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="294e1-1962">Indicatore del secolo ("-", "+" o "a")</span><span class="sxs-lookup"><span data-stu-id="294e1-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="294e1-1963">Codice PIN di 3 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="294e1-1964">Una cifra o una lettera (con distinzione tra maiuscole/minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1965">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1965">Checksum</span></span>

<span data-ttu-id="294e1-1966">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1967">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1967">Definition</span></span>

<span data-ttu-id="294e1-1968">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1969">La funzione Func_finnish_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1970">Viene trovata una parola chiave da Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="294e1-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="294e1-1971">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-1972">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1972">Keywords</span></span>

- <span data-ttu-id="294e1-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="294e1-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="294e1-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="294e1-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="294e1-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="294e1-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="294e1-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="294e1-1976">Personbeteckning</span></span>
- <span data-ttu-id="294e1-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="294e1-1978">Finlandia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-1978">Finland Passport Number</span></span>

<span data-ttu-id="294e1-1979">Combinazione di formato di nove lettere e combinazioni di caratteri di nove lettere e cifre: due lettere (senza distinzione tra maiuscole/minuscole) sette cifre checksum nessuna definizione un criterio DLP è 75% sicuro che sia stato rilevato questo tipo di informazioni riservate se, all'interno di un prossimità di 300 caratteri: l'espressione regolare Regex_finland_passport_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="294e1-1980">Viene trovata una parola chiave da Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="294e1-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="294e1-1981"></span></span>
<span data-ttu-id="294e1-1982">Parole chiave Keyword_finland_passport_number passaporto passi</span><span class="sxs-lookup"><span data-stu-id="294e1-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="294e1-1983">Francia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="294e1-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-1984">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-1984">Format</span></span>

<span data-ttu-id="294e1-1985">12 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-1986">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-1986">Pattern</span></span>

<span data-ttu-id="294e1-1987">12 cifre con convalida per scontare modelli analoghi, ad esempio, quello dei numeri telefonici francesi</span><span class="sxs-lookup"><span data-stu-id="294e1-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-1988">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-1988">Checksum</span></span>

<span data-ttu-id="294e1-1989">No</span><span class="sxs-lookup"><span data-stu-id="294e1-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-1990">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-1990">Definition</span></span>

<span data-ttu-id="294e1-1991">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-1992">La funzione Func_french_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-1993">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="294e1-1994">Viene trovata una parola chiave da Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="294e1-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="294e1-1995">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-1996">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="294e1-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="294e1-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="294e1-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="294e1-1998">drivers licence</span></span>
- <span data-ttu-id="294e1-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="294e1-1999">drivers license</span></span>
- <span data-ttu-id="294e1-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="294e1-2000">driving licence</span></span>
- <span data-ttu-id="294e1-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="294e1-2001">driving license</span></span>
- <span data-ttu-id="294e1-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="294e1-2002">permis de conduire</span></span>
- <span data-ttu-id="294e1-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="294e1-2003">licence number</span></span>
- <span data-ttu-id="294e1-2004">license number</span><span class="sxs-lookup"><span data-stu-id="294e1-2004">license number</span></span>
- <span data-ttu-id="294e1-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="294e1-2005">licence numbers</span></span>
- <span data-ttu-id="294e1-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="294e1-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="294e1-2007">Francia - Carta d'identità nazionale (CNI)</span><span class="sxs-lookup"><span data-stu-id="294e1-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2008">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2008">Format</span></span>

<span data-ttu-id="294e1-2009">12 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2010">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2010">Pattern</span></span>

<span data-ttu-id="294e1-2011">12 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2012">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2012">Checksum</span></span>

<span data-ttu-id="294e1-2013">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2014">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2014">Definition</span></span>

<span data-ttu-id="294e1-2015">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2016">L'espressione regolare Regex_france_cni restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2017">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2017">Keywords</span></span>

<span data-ttu-id="294e1-2018">Nessuno</span><span class="sxs-lookup"><span data-stu-id="294e1-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="294e1-2019">Francia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2020">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2020">Format</span></span>

<span data-ttu-id="294e1-2021">Nove cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="294e1-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2022">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2022">Pattern</span></span>

<span data-ttu-id="294e1-2023">Nove cifre e lettere:</span><span class="sxs-lookup"><span data-stu-id="294e1-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="294e1-2024">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2024">Two digits</span></span> 
- <span data-ttu-id="294e1-2025">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="294e1-2026">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2027">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2027">Checksum</span></span>

<span data-ttu-id="294e1-2028">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2029">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2029">Definition</span></span>

<span data-ttu-id="294e1-2030">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2031">La funzione Func_fr_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2032">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="294e1-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2033">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="294e1-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="294e1-2034">Keyword_passport</span></span>

- <span data-ttu-id="294e1-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2035">Passport Number</span></span>
- <span data-ttu-id="294e1-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="294e1-2036">Passport No</span></span>
- <span data-ttu-id="294e1-2037">Passport#</span><span class="sxs-lookup"><span data-stu-id="294e1-2037">Passport #</span></span>
- <span data-ttu-id="294e1-2038">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="294e1-2038">Passport#</span></span>
- <span data-ttu-id="294e1-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="294e1-2039">PassportID</span></span>
- <span data-ttu-id="294e1-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="294e1-2040">Passportno</span></span>
- <span data-ttu-id="294e1-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-2041">passportnumber</span></span>
- <span data-ttu-id="294e1-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="294e1-2042">パスポート</span></span>
- <span data-ttu-id="294e1-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2043">パスポート番号</span></span>
- <span data-ttu-id="294e1-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="294e1-2044">パスポートのNum</span></span>
- <span data-ttu-id="294e1-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="294e1-2045">パスポート ＃</span></span> 
- <span data-ttu-id="294e1-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="294e1-2046">Numéro de passeport</span></span>
- <span data-ttu-id="294e1-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="294e1-2047">Passeport n °</span></span>
- <span data-ttu-id="294e1-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="294e1-2048">Passeport Non</span></span>
- <span data-ttu-id="294e1-2049">Passeport#</span><span class="sxs-lookup"><span data-stu-id="294e1-2049">Passeport #</span></span>
- <span data-ttu-id="294e1-2050">Passeport #</span><span class="sxs-lookup"><span data-stu-id="294e1-2050">Passeport#</span></span>
- <span data-ttu-id="294e1-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="294e1-2051">PasseportNon</span></span>
- <span data-ttu-id="294e1-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="294e1-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="294e1-2053">Francia - Numero di previdenza sociale (INSEE)</span><span class="sxs-lookup"><span data-stu-id="294e1-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2054">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2054">Format</span></span>

<span data-ttu-id="294e1-2055">15 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2056">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2056">Pattern</span></span>

<span data-ttu-id="294e1-2057">Deve corrispondere a uno di questi due modelli:</span><span class="sxs-lookup"><span data-stu-id="294e1-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="294e1-2058">13 cifre seguite da uno spazio seguito da due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="294e1-2059">oppure</span><span class="sxs-lookup"><span data-stu-id="294e1-2059">or</span></span>
- <span data-ttu-id="294e1-2060">15 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2061">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2061">Checksum</span></span>

<span data-ttu-id="294e1-2062">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2063">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2063">Definition</span></span>

<span data-ttu-id="294e1-2064">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2065">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2066">Viene trovata una parola chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="294e1-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="294e1-2067">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2067">The checksum passes.</span></span>

<span data-ttu-id="294e1-2068">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2069">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2070">Non vengono trovate parole chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="294e1-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="294e1-2071">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2072">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="294e1-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="294e1-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="294e1-2074">INSEE</span><span class="sxs-lookup"><span data-stu-id="294e1-2074">insee</span></span>
- <span data-ttu-id="294e1-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="294e1-2075">securité sociale</span></span>
- <span data-ttu-id="294e1-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="294e1-2076">securite sociale</span></span>
- <span data-ttu-id="294e1-2077">national id</span><span class="sxs-lookup"><span data-stu-id="294e1-2077">national id</span></span>
- <span data-ttu-id="294e1-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="294e1-2078">national identification</span></span>
- <span data-ttu-id="294e1-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="294e1-2079">numéro d'identité</span></span>
- <span data-ttu-id="294e1-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="294e1-2080">no d'identité</span></span>
- <span data-ttu-id="294e1-2081">No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2081">no.</span></span> <span data-ttu-id="294e1-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="294e1-2082">d'identité</span></span>
- <span data-ttu-id="294e1-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="294e1-2083">numero d'identite</span></span>
- <span data-ttu-id="294e1-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="294e1-2084">no d'identite</span></span>
- <span data-ttu-id="294e1-2085">No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2085">no.</span></span> <span data-ttu-id="294e1-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="294e1-2086">d'identite</span></span>
- <span data-ttu-id="294e1-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="294e1-2087">social security number</span></span>
- <span data-ttu-id="294e1-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="294e1-2088">social security code</span></span>
- <span data-ttu-id="294e1-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="294e1-2089">social insurance number</span></span>
- <span data-ttu-id="294e1-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="294e1-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="294e1-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="294e1-2091">d'identité nationale</span></span>
- <span data-ttu-id="294e1-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="294e1-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="294e1-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="294e1-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="294e1-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="294e1-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="294e1-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="294e1-2095">numéro de sécu</span></span>
- <span data-ttu-id="294e1-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="294e1-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="294e1-2097">Germania - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="294e1-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2098">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2098">Format</span></span>

<span data-ttu-id="294e1-2099">Combinazione di 11 cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="294e1-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2100">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2100">Pattern</span></span>

<span data-ttu-id="294e1-2101">11 cifre e lettere (senza distinzione tra maiuscole/minuscole):</span><span class="sxs-lookup"><span data-stu-id="294e1-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="294e1-2102">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="294e1-2102">A digit or letter</span></span> 
- <span data-ttu-id="294e1-2103">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2103">Two digits</span></span> 
- <span data-ttu-id="294e1-2104">Sei cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="294e1-2104">Six digits or letters</span></span> 
- <span data-ttu-id="294e1-2105">Una cifra</span><span class="sxs-lookup"><span data-stu-id="294e1-2105">A digit</span></span> 
- <span data-ttu-id="294e1-2106">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="294e1-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2107">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2107">Checksum</span></span>

<span data-ttu-id="294e1-2108">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2109">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2109">Definition</span></span>

<span data-ttu-id="294e1-2110">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2111">La funzione Func_german_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2112">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="294e1-2113">Viene trovata una parola chiave da Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="294e1-2114">Viene trovata una parola chiave da Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="294e1-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="294e1-2115">Viene trovata una parola chiave da Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="294e1-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="294e1-2116">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2117">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="294e1-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="294e1-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2119">Führerschein</span></span>
- <span data-ttu-id="294e1-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2120">Fuhrerschein</span></span>
- <span data-ttu-id="294e1-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2121">Fuehrerschein</span></span>
- <span data-ttu-id="294e1-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="294e1-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="294e1-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="294e1-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="294e1-2125">Führerschein-</span></span> 
- <span data-ttu-id="294e1-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="294e1-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="294e1-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="294e1-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="294e1-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="294e1-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="294e1-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="294e1-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="294e1-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="294e1-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="294e1-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="294e1-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="294e1-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="294e1-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="294e1-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="294e1-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="294e1-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="294e1-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="294e1-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="294e1-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="294e1-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="294e1-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="294e1-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="294e1-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="294e1-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="294e1-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="294e1-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="294e1-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="294e1-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="294e1-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="294e1-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="294e1-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="294e1-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="294e1-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="294e1-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="294e1-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="294e1-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="294e1-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="294e1-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="294e1-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="294e1-2152">DL</span><span class="sxs-lookup"><span data-stu-id="294e1-2152">DL</span></span> 
- <span data-ttu-id="294e1-2153">DLS</span><span class="sxs-lookup"><span data-stu-id="294e1-2153">DLS</span></span>
- <span data-ttu-id="294e1-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-2154">Driv Lic</span></span> 
- <span data-ttu-id="294e1-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="294e1-2155">Driv Licen</span></span> 
- <span data-ttu-id="294e1-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="294e1-2156">Driv License</span></span>
- <span data-ttu-id="294e1-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-2157">Driv Licenses</span></span> 
- <span data-ttu-id="294e1-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-2158">Driv Licence</span></span> 
- <span data-ttu-id="294e1-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-2159">Driv Licences</span></span> 
- <span data-ttu-id="294e1-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-2160">Driv Lic</span></span> 
- <span data-ttu-id="294e1-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="294e1-2161">Driver Licen</span></span> 
- <span data-ttu-id="294e1-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="294e1-2162">Driver License</span></span> 
- <span data-ttu-id="294e1-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-2163">Driver Licenses</span></span> 
- <span data-ttu-id="294e1-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-2164">Driver Licence</span></span> 
- <span data-ttu-id="294e1-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-2165">Driver Licences</span></span> 
- <span data-ttu-id="294e1-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-2166">Drivers Lic</span></span> 
- <span data-ttu-id="294e1-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="294e1-2167">Drivers Licen</span></span> 
- <span data-ttu-id="294e1-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="294e1-2168">Drivers License</span></span> 
- <span data-ttu-id="294e1-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="294e1-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-2170">Drivers Licence</span></span> 
- <span data-ttu-id="294e1-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-2171">Drivers Licences</span></span> 
- <span data-ttu-id="294e1-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-2172">Driver's Lic</span></span> 
- <span data-ttu-id="294e1-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="294e1-2173">Driver's Licen</span></span> 
- <span data-ttu-id="294e1-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="294e1-2174">Driver's License</span></span> 
- <span data-ttu-id="294e1-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="294e1-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-2176">Driver's Licence</span></span> 
- <span data-ttu-id="294e1-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-2177">Driver's Licences</span></span> 
- <span data-ttu-id="294e1-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-2178">Driving Lic</span></span> 
- <span data-ttu-id="294e1-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="294e1-2179">Driving Licen</span></span> 
- <span data-ttu-id="294e1-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="294e1-2180">Driving License</span></span> 
- <span data-ttu-id="294e1-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-2181">Driving Licenses</span></span> 
- <span data-ttu-id="294e1-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="294e1-2182">Driving Licence</span></span> 
- <span data-ttu-id="294e1-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="294e1-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="294e1-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="294e1-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="294e1-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="294e1-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="294e1-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="294e1-2188">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2188">No-Führerschein</span></span> 
- <span data-ttu-id="294e1-2189">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="294e1-2190">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="294e1-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2191">N-Führerschein</span></span> 
- <span data-ttu-id="294e1-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="294e1-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="294e1-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="294e1-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="294e1-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="294e1-2197">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2197">No-Führerschein</span></span> 
- <span data-ttu-id="294e1-2198">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="294e1-2199">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="294e1-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2200">N-Führerschein</span></span> 
- <span data-ttu-id="294e1-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="294e1-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="294e1-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="294e1-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="294e1-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="294e1-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="294e1-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="294e1-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="294e1-2205">ausstellungsort</span></span>
- <span data-ttu-id="294e1-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="294e1-2206">ausstellende behöde</span></span>
- <span data-ttu-id="294e1-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="294e1-2207">ausstellende behorde</span></span>
- <span data-ttu-id="294e1-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="294e1-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="294e1-2209">Germania - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2210">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2210">Format</span></span>

<span data-ttu-id="294e1-2211">10 cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="294e1-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2212">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2212">Pattern</span></span>

<span data-ttu-id="294e1-2213">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="294e1-2214">Il primo carattere è una cifra o una lettera del gruppo seguente: C, F, G, H, J, K</span><span class="sxs-lookup"><span data-stu-id="294e1-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="294e1-2215">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2215">Three digits</span></span> 
- <span data-ttu-id="294e1-2216">Cinque cifre o lettere del gruppo seguente: C, -H, J-N, P, R, T, V-Z</span><span class="sxs-lookup"><span data-stu-id="294e1-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="294e1-2217">Una cifra</span><span class="sxs-lookup"><span data-stu-id="294e1-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2218">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2218">Checksum</span></span>

<span data-ttu-id="294e1-2219">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2220">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2220">Definition</span></span>

<span data-ttu-id="294e1-2221">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2222">La funzione Func_german_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2223">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="294e1-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="294e1-2224">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2224">The checksum passes.</span></span>

<span data-ttu-id="294e1-2225">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2226">La funzione Func_german_passport_data restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2227">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="294e1-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="294e1-2228">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2229">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="294e1-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="294e1-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="294e1-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="294e1-2231">reisepass</span></span>
- <span data-ttu-id="294e1-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="294e1-2232">reisepasse</span></span>
- <span data-ttu-id="294e1-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-2233">reisepassnummer</span></span>
- <span data-ttu-id="294e1-2234">passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-2234">passport</span></span>
- <span data-ttu-id="294e1-2235">passaporti</span><span class="sxs-lookup"><span data-stu-id="294e1-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="294e1-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="294e1-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="294e1-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="294e1-2237">geburtsdatum</span></span>
- <span data-ttu-id="294e1-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="294e1-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="294e1-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="294e1-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="294e1-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="294e1-2241">No-Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="294e1-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="294e1-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="294e1-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="294e1-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="294e1-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="294e1-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="294e1-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="294e1-2245">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="294e1-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="294e1-2246">Germania - Numero carta di identità</span><span class="sxs-lookup"><span data-stu-id="294e1-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2247">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2247">Format</span></span>

<span data-ttu-id="294e1-2248">Dal 1 ° novembre 2010: nove lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="294e1-2249">Dal 1 ° aprile 1987 al 31 ottobre 2010:10 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2250">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2250">Pattern</span></span>

<span data-ttu-id="294e1-2251">A partire dal 1° novembre 2010:</span><span class="sxs-lookup"><span data-stu-id="294e1-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="294e1-2252">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="294e1-2253">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2253">Eight digits</span></span>

<span data-ttu-id="294e1-2254">Dal 1 ° aprile 1987 al 31 ottobre 2010:</span><span class="sxs-lookup"><span data-stu-id="294e1-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="294e1-2255">10 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2256">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2256">Checksum</span></span>

<span data-ttu-id="294e1-2257">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2258">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2258">Definition</span></span>

<span data-ttu-id="294e1-2259">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2260">L'espressione regolare Regex_germany_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2261">Viene trovata una parola chiave da Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="294e1-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2262">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="294e1-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="294e1-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="294e1-2264">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="294e1-2264">Identity Card</span></span>
- <span data-ttu-id="294e1-2265">ID</span><span class="sxs-lookup"><span data-stu-id="294e1-2265">ID</span></span>
- <span data-ttu-id="294e1-2266">Identificazione</span><span class="sxs-lookup"><span data-stu-id="294e1-2266">Identification</span></span>
- <span data-ttu-id="294e1-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="294e1-2267">Personalausweis</span></span>
- <span data-ttu-id="294e1-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="294e1-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="294e1-2269">Ausweis</span></span>
- <span data-ttu-id="294e1-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="294e1-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="294e1-2271">Carta d'identità (Grecia)</span><span class="sxs-lookup"><span data-stu-id="294e1-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2272">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2272">Format</span></span>

<span data-ttu-id="294e1-2273">Combinazione di 7-8 lettere e numeri, oltre a un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2274">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2274">Pattern</span></span>

<span data-ttu-id="294e1-2275">Sette lettere e numeri (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="294e1-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="294e1-2276">Una lettera (qualsiasi lettera dell'alfabeto greco) </span><span class="sxs-lookup"><span data-stu-id="294e1-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="294e1-2277">Un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-2277">A dash</span></span> 
- <span data-ttu-id="294e1-2278">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2278">Six digits</span></span>

<span data-ttu-id="294e1-2279">Otto lettere e numeri (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="294e1-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="294e1-2280">Due lettere in maiuscolo sia in alfabeto latino che greco (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="294e1-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="294e1-2281">Un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-2281">A dash</span></span> 
- <span data-ttu-id="294e1-2282">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2283">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2283">Checksum</span></span>

<span data-ttu-id="294e1-2284">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2285">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2285">Definition</span></span>

<span data-ttu-id="294e1-2286">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2287">L'espressione regolare Regex_greece_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2288">Viene trovata una parola chiave da Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="294e1-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2289">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="294e1-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="294e1-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="294e1-2291">Carta d’identità greca</span><span class="sxs-lookup"><span data-stu-id="294e1-2291">Greek identity Card</span></span>
- <span data-ttu-id="294e1-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="294e1-2292">Tautotita</span></span>
- <span data-ttu-id="294e1-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="294e1-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="294e1-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="294e1-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="294e1-2295">Hong Kong - Numero di carta di identità (HKID)</span><span class="sxs-lookup"><span data-stu-id="294e1-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2296">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2296">Format</span></span>

<span data-ttu-id="294e1-2297">Combinazione di 8-9 lettere e numeri. Facoltativamente, l’ultimo carattere può essere racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="294e1-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2298">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2298">Pattern</span></span>

<span data-ttu-id="294e1-2299">Combinazione di 8-9 lettere:</span><span class="sxs-lookup"><span data-stu-id="294e1-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="294e1-2300">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="294e1-2301">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2301">Six digits</span></span> 
- <span data-ttu-id="294e1-2302">L'ultimo carattere (qualsiasi cifra o la lettera A), è rappresentato dal numero di controllo. Facoltativamente, può essere racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="294e1-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2303">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2303">Checksum</span></span>

<span data-ttu-id="294e1-2304">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2305">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2305">Definition</span></span>

<span data-ttu-id="294e1-2306">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2307">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2308">Viene trovata una parola chiave da Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="294e1-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="294e1-2309">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2309">The checksum passes.</span></span>

<span data-ttu-id="294e1-2310">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2311">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2312">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2313">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="294e1-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="294e1-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="294e1-2315">carta di identità di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="294e1-2315">hong kong identity card</span></span>
- <span data-ttu-id="294e1-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="294e1-2316">HKIDC</span></span>
- <span data-ttu-id="294e1-2317">id card</span><span class="sxs-lookup"><span data-stu-id="294e1-2317">id card</span></span>
- <span data-ttu-id="294e1-2318">carta di identità</span><span class="sxs-lookup"><span data-stu-id="294e1-2318">identity card</span></span>
- <span data-ttu-id="294e1-2319">carta di identità HK</span><span class="sxs-lookup"><span data-stu-id="294e1-2319">hk identity card</span></span>
- <span data-ttu-id="294e1-2320">ID Hong Kong</span><span class="sxs-lookup"><span data-stu-id="294e1-2320">hong kong id</span></span>
- <span data-ttu-id="294e1-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-2321">香港身份證</span></span>
- <span data-ttu-id="294e1-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="294e1-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-2323">身份證</span></span>
- <span data-ttu-id="294e1-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="294e1-2324">身份証</span></span>
- <span data-ttu-id="294e1-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="294e1-2325">身分證</span></span>
- <span data-ttu-id="294e1-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="294e1-2326">身分証</span></span>
- <span data-ttu-id="294e1-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="294e1-2327">香港身份証</span></span>
- <span data-ttu-id="294e1-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="294e1-2328">香港身分證</span></span>
- <span data-ttu-id="294e1-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="294e1-2329">香港身分証</span></span>
- <span data-ttu-id="294e1-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-2330">香港身份證</span></span>
- <span data-ttu-id="294e1-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-2331">香港居民身份證</span></span>
- <span data-ttu-id="294e1-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="294e1-2332">香港居民身份証</span></span>
- <span data-ttu-id="294e1-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="294e1-2333">香港居民身分證</span></span>
- <span data-ttu-id="294e1-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="294e1-2334">香港居民身分証</span></span>
- <span data-ttu-id="294e1-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="294e1-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="294e1-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="294e1-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="294e1-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="294e1-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="294e1-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="294e1-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="294e1-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="294e1-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="294e1-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="294e1-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="294e1-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="294e1-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="294e1-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="294e1-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="294e1-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="294e1-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="294e1-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="294e1-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="294e1-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="294e1-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="294e1-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="294e1-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="294e1-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="294e1-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="294e1-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="294e1-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="294e1-2351">India - Numero di conto permanente (PAN)</span><span class="sxs-lookup"><span data-stu-id="294e1-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2352">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2352">Format</span></span>

<span data-ttu-id="294e1-2353">10 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2354">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2354">Pattern</span></span>

<span data-ttu-id="294e1-2355">10 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-2355">10 letters or digits:</span></span>
- <span data-ttu-id="294e1-2356">Cinque lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="294e1-2357">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2357">Four digits</span></span> 
- <span data-ttu-id="294e1-2358">Una lettera, ovvero una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="294e1-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2359">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2359">Checksum</span></span>

<span data-ttu-id="294e1-2360">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2361">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2361">Definition</span></span>

<span data-ttu-id="294e1-2362">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2363">L'espressione regolare Regex_india_permanent_account_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2364">Viene trovata una parola chiave da Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="294e1-2365">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2366">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="294e1-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="294e1-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="294e1-2369">PAN</span><span class="sxs-lookup"><span data-stu-id="294e1-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="294e1-2370">India - Numero di identificazione univoco (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="294e1-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2371">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2371">Format</span></span>

<span data-ttu-id="294e1-2372">12 cifre contenenti spazi o trattini facoltativi </span><span class="sxs-lookup"><span data-stu-id="294e1-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2373">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2373">Pattern</span></span>

<span data-ttu-id="294e1-2374">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-2374">12 digits:</span></span>
- <span data-ttu-id="294e1-2375">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2375">Four digits</span></span> 
- <span data-ttu-id="294e1-2376">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="294e1-2376">An optional space or dash</span></span> 
- <span data-ttu-id="294e1-2377">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2377">Four digits</span></span> 
- <span data-ttu-id="294e1-2378">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="294e1-2378">An optional space or dash</span></span> 
- <span data-ttu-id="294e1-2379">L'ultimo carattere, ovvero il numero di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2380">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2380">Checksum</span></span>

<span data-ttu-id="294e1-2381">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2382">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2382">Definition</span></span>

<span data-ttu-id="294e1-2383">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="294e1-2384">Viene trovata una parola chiave da Keyword_india_aadhar.</span><span class="sxs-lookup"><span data-stu-id="294e1-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="294e1-2385">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2385">The checksum passes.</span></span>
<span data-ttu-id="294e1-2386">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="294e1-2387">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2387">The checksum passes.</span></span>
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
### <a name="keywords"></a><span data-ttu-id="294e1-2388">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="294e1-2389">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="294e1-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="294e1-2390">Aadhar</span><span class="sxs-lookup"><span data-stu-id="294e1-2390">Aadhar</span></span>
- <span data-ttu-id="294e1-2391">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="294e1-2391">Aadhaar</span></span>
- <span data-ttu-id="294e1-2392">UID</span><span class="sxs-lookup"><span data-stu-id="294e1-2392">UID</span></span>
- <span data-ttu-id="294e1-2393">आधार</span><span class="sxs-lookup"><span data-stu-id="294e1-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="294e1-2394">Indonesia - Numero di carta di identità (KTP)</span><span class="sxs-lookup"><span data-stu-id="294e1-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2395">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2395">Format</span></span>

<span data-ttu-id="294e1-2396">16 cifre contenenti punti facoltativi </span><span class="sxs-lookup"><span data-stu-id="294e1-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2397">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2397">Pattern</span></span>

<span data-ttu-id="294e1-2398">16 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-2398">16 digits:</span></span>
- <span data-ttu-id="294e1-2399">Codice provincia a due cifre </span><span class="sxs-lookup"><span data-stu-id="294e1-2399">Two-digit province code</span></span> 
- <span data-ttu-id="294e1-2400">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="294e1-2400">A period (optional)</span></span> 
- <span data-ttu-id="294e1-2401">Codice città o area a due cifre </span><span class="sxs-lookup"><span data-stu-id="294e1-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="294e1-2402">Codice sotto-distretto a due cifre </span><span class="sxs-lookup"><span data-stu-id="294e1-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="294e1-2403">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="294e1-2403">A period (optional)</span></span> 
- <span data-ttu-id="294e1-2404">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="294e1-2405">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="294e1-2405">A period (optional)</span></span> 
- <span data-ttu-id="294e1-2406">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2407">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2407">Checksum</span></span>

<span data-ttu-id="294e1-2408">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2409">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2409">Definition</span></span>

<span data-ttu-id="294e1-2410">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2411">L'espressione regolare Regex_indonesia_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2412">Viene trovata una parola chiave da Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="294e1-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="294e1-2413">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2414">L'espressione regolare Regex_indonesia_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2415">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="294e1-2416">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="294e1-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="294e1-2417">KTP</span><span class="sxs-lookup"><span data-stu-id="294e1-2417">KTP</span></span>
- <span data-ttu-id="294e1-2418">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="294e1-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="294e1-2419">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="294e1-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="294e1-2420">Numero di conto bancario internazionale (IBAN)</span><span class="sxs-lookup"><span data-stu-id="294e1-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2421">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2421">Format</span></span>

<span data-ttu-id="294e1-2422">Codice paese (due lettere) più cifre di controllo (due cifre) più numero BBAN (fino a 30 caratteri)</span><span class="sxs-lookup"><span data-stu-id="294e1-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2423">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2423">Pattern</span></span>

<span data-ttu-id="294e1-2424">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="294e1-2425">Codice paese a due lettere</span><span class="sxs-lookup"><span data-stu-id="294e1-2425">Two-letter country code</span></span>
- <span data-ttu-id="294e1-2426">Due cifre di controllo (seguite da uno spazio facoltativo)</span><span class="sxs-lookup"><span data-stu-id="294e1-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="294e1-2427">1-7 gruppi di quattro lettere o cifre (possono essere separati da spazi)</span><span class="sxs-lookup"><span data-stu-id="294e1-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="294e1-2428">1-3 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2428">1-3 letters or digits</span></span>

<span data-ttu-id="294e1-2429">Il formato di ogni paese è leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="294e1-2429">The format for each country is slightly different.</span></span> <span data-ttu-id="294e1-2430">Il tipo di informazioni riservate IBAN copre questi 60 paesi:</span><span class="sxs-lookup"><span data-stu-id="294e1-2430">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="294e1-2431">ad, AE, al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, do, EE, es, Fi, fo, fr, GB, GE, Gi, GL, gr, HR, HU, IE, il, is, it, kW, KZ, lb, li, LT, Lu, LV, MC, MD, me, MK, Mr, MT, MU , NL, no, pl, PT, ro, RS, SA, se, si, SK, SM, TN, TR, VG</span><span class="sxs-lookup"><span data-stu-id="294e1-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2432">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2432">Checksum</span></span>

<span data-ttu-id="294e1-2433">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2434">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2434">Definition</span></span>

<span data-ttu-id="294e1-2435">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2436">La funzione Func_iban restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2437">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2438">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2438">Keywords</span></span>

<span data-ttu-id="294e1-2439">Nessuno</span><span class="sxs-lookup"><span data-stu-id="294e1-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="294e1-2440">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="294e1-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2441">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="294e1-2442">IPv4</span><span class="sxs-lookup"><span data-stu-id="294e1-2442">IPv4:</span></span>
<span data-ttu-id="294e1-2443">Modello complesso che rappresenta le versioni formattate (punti) e quelle non formattate (senza punti) degli indirizzi IPv4</span><span class="sxs-lookup"><span data-stu-id="294e1-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="294e1-2444">IPv6</span><span class="sxs-lookup"><span data-stu-id="294e1-2444">IPv6:</span></span>
<span data-ttu-id="294e1-2445">Modello complesso che rappresenta i numeri dell'indirizzo IPv6 non formattati (include i due punti)</span><span class="sxs-lookup"><span data-stu-id="294e1-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2446">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2447">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2447">Checksum</span></span>

<span data-ttu-id="294e1-2448">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2449">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2449">Definition</span></span>

<span data-ttu-id="294e1-2450">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2451">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2452">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="294e1-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="294e1-2453">Nel caso di IPv4, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2454">L'espressione regolare Regex_ipv4_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2455">Viene trovata una parola chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="294e1-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="294e1-2456">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2457">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2458">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="294e1-2458">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2459">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="294e1-2460">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="294e1-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="294e1-2461">IP (per questa parola chiave viene fatta distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="294e1-2462">ip address</span><span class="sxs-lookup"><span data-stu-id="294e1-2462">ip address</span></span> 
- <span data-ttu-id="294e1-2463">Indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="294e1-2463">ip addresses</span></span>
- <span data-ttu-id="294e1-2464">internet protocol</span><span class="sxs-lookup"><span data-stu-id="294e1-2464">internet protocol</span></span>
- <span data-ttu-id="294e1-2465">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="294e1-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="294e1-2466">Classificazione internazionale delle malattie (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="294e1-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2467">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2467">Format</span></span>

<span data-ttu-id="294e1-2468">Dizionario</span><span class="sxs-lookup"><span data-stu-id="294e1-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2469">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2469">Pattern</span></span>

<span data-ttu-id="294e1-2470">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2471">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2471">Checksum</span></span>

<span data-ttu-id="294e1-2472">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2473">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2473">Definition</span></span>

<span data-ttu-id="294e1-2474">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2475">Viene trovata una parola chiave da Dictionary_icd_10_updated.</span><span class="sxs-lookup"><span data-stu-id="294e1-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="294e1-2476">Viene trovata una parola chiave da Dictionary_icd_10_codes.</span><span class="sxs-lookup"><span data-stu-id="294e1-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="294e1-2477">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2478">Viene trovata una parola chiave da Dictionary_icd_10_.</span><span class="sxs-lookup"><span data-stu-id="294e1-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

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

<span data-ttu-id="294e1-2479">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2479">Keywords</span></span>

<span data-ttu-id="294e1-2480">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_10_updated, basato sulla [classificazione internazionale delle malattie, la decima revisione, la modifica clinica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="294e1-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="294e1-2481">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="294e1-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="294e1-2482">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_10_codes, basato sulla [classificazione internazionale delle malattie, la decima revisione, la modifica clinica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="294e1-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="294e1-2483">Questo tipo di ricerca è solo per i codici assicurativi, non per la descrizione.</span><span class="sxs-lookup"><span data-stu-id="294e1-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="294e1-2484">Classificazione internazionale delle malattie (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="294e1-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2485">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2485">Format</span></span>

<span data-ttu-id="294e1-2486">Dizionario</span><span class="sxs-lookup"><span data-stu-id="294e1-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2487">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2487">Pattern</span></span>

<span data-ttu-id="294e1-2488">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2489">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2489">Checksum</span></span>

<span data-ttu-id="294e1-2490">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2491">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2491">Definition</span></span>

<span data-ttu-id="294e1-2492">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2493">Viene trovata una parola chiave da Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="294e1-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="294e1-2494">Viene trovata una parola chiave da Dictionary_icd_9_codes.</span><span class="sxs-lookup"><span data-stu-id="294e1-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="294e1-2495">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2496">Viene trovata una parola chiave da Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="294e1-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2497">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2497">Keywords</span></span>

<span data-ttu-id="294e1-2498">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_9_updated, basato sulla [classificazione internazionale delle malattie, la nona revisione, la modifica clinica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="294e1-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="294e1-2499">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="294e1-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="294e1-2500">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_9_codes, basato sulla [classificazione internazionale delle malattie, la nona revisione, la modifica clinica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="294e1-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="294e1-2501">Questo tipo di ricerca è solo per i codici assicurativi, non per la descrizione.</span><span class="sxs-lookup"><span data-stu-id="294e1-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="294e1-2502">Irlanda - Numero personale di servizio pubblico (PPS)</span><span class="sxs-lookup"><span data-stu-id="294e1-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2503">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2503">Format</span></span>

<span data-ttu-id="294e1-2504">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="294e1-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="294e1-2505">Sette cifre seguite da 1-2 lettere </span><span class="sxs-lookup"><span data-stu-id="294e1-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="294e1-2506">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="294e1-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="294e1-2507">Sette cifre seguite da due lettere</span><span class="sxs-lookup"><span data-stu-id="294e1-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2508">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2508">Pattern</span></span>

<span data-ttu-id="294e1-2509">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="294e1-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="294e1-2510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2510">Seven digits</span></span> 
- <span data-ttu-id="294e1-2511">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="294e1-2512">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="294e1-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="294e1-2513">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2513">Seven digits</span></span> 
- <span data-ttu-id="294e1-2514">Una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo alfabetica </span><span class="sxs-lookup"><span data-stu-id="294e1-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="294e1-2515">La lettera "A" o "H" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2516">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2516">Checksum</span></span>

<span data-ttu-id="294e1-2517">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2518">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2518">Definition</span></span>

<span data-ttu-id="294e1-2519">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2520">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2521">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-2521">One of the following is true:</span></span>
    - <span data-ttu-id="294e1-2522">Viene trovata una parola chiave da Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="294e1-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="294e1-2523">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="294e1-2524">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2524">The checksum passes.</span></span>

<span data-ttu-id="294e1-2525">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2526">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2527">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2527">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2528">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="294e1-2529">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="294e1-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="294e1-2530">Numero personale di servizio pubblico</span><span class="sxs-lookup"><span data-stu-id="294e1-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="294e1-2531">Numero PPS</span><span class="sxs-lookup"><span data-stu-id="294e1-2531">PPS Number</span></span> 
- <span data-ttu-id="294e1-2532">Num. PPS
</span><span class="sxs-lookup"><span data-stu-id="294e1-2532">PPS Num</span></span> 
- <span data-ttu-id="294e1-2533">N° PPS</span><span class="sxs-lookup"><span data-stu-id="294e1-2533">PPS No.</span></span> 
- <span data-ttu-id="294e1-2534">PPS #</span><span class="sxs-lookup"><span data-stu-id="294e1-2534">PPS #</span></span> 
- <span data-ttu-id="294e1-2535">PPS #</span><span class="sxs-lookup"><span data-stu-id="294e1-2535">PPS#</span></span> 
- <span data-ttu-id="294e1-2536">PPSN</span><span class="sxs-lookup"><span data-stu-id="294e1-2536">PPSN</span></span> 
- <span data-ttu-id="294e1-2537">Scheda servizi pubblici</span><span class="sxs-lookup"><span data-stu-id="294e1-2537">Public Services Card</span></span> 
- <span data-ttu-id="294e1-2538">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="294e1-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="294e1-2539">Uimh.</span><span class="sxs-lookup"><span data-stu-id="294e1-2539">Uimh.</span></span> <span data-ttu-id="294e1-2540">PSP</span><span class="sxs-lookup"><span data-stu-id="294e1-2540">PSP</span></span> 
- <span data-ttu-id="294e1-2541">PSP</span><span class="sxs-lookup"><span data-stu-id="294e1-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="294e1-2542">Israele - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="294e1-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2543">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2543">Format</span></span>

<span data-ttu-id="294e1-2544">13 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2545">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2545">Pattern</span></span>

<span data-ttu-id="294e1-2546">Formattato</span><span class="sxs-lookup"><span data-stu-id="294e1-2546">Formatted:</span></span>
- <span data-ttu-id="294e1-2547">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2547">Two digits</span></span> 
- <span data-ttu-id="294e1-2548">Un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-2548">A dash</span></span> 
- <span data-ttu-id="294e1-2549">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2549">Three digits</span></span> 
- <span data-ttu-id="294e1-2550">Un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-2550">A dash</span></span> 
- <span data-ttu-id="294e1-2551">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2551">Eight digits</span></span>

<span data-ttu-id="294e1-2552">Formattato</span><span class="sxs-lookup"><span data-stu-id="294e1-2552">Unformatted:</span></span>
- <span data-ttu-id="294e1-2553">13 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2554">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2554">Checksum</span></span>

<span data-ttu-id="294e1-2555">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2556">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2556">Definition</span></span>

<span data-ttu-id="294e1-2557">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2558">L'espressione regolare Regex_israel_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2559">Viene trovata una parola chiave da Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2560">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="294e1-2561">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="294e1-2562">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2562">Bank Account Number</span></span> 
- <span data-ttu-id="294e1-2563">Bank Account</span><span class="sxs-lookup"><span data-stu-id="294e1-2563">Bank Account</span></span> 
- <span data-ttu-id="294e1-2564">Account Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2564">Account Number</span></span> 
- <span data-ttu-id="294e1-2565">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="294e1-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="294e1-2566">Carta di identità (Israele)</span><span class="sxs-lookup"><span data-stu-id="294e1-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2567">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2567">Format</span></span>

<span data-ttu-id="294e1-2568">9 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2569">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2569">Pattern</span></span>

<span data-ttu-id="294e1-2570">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2571">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2571">Checksum</span></span>

<span data-ttu-id="294e1-2572">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2573">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2573">Definition</span></span>

<span data-ttu-id="294e1-2574">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2575">La funzione Func_israeli_national_id_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2576">Viene trovata una parola chiave da Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="294e1-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="294e1-2577">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2577">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2578">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="294e1-2579">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="294e1-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="294e1-2580">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="294e1-2580">מספר זהות</span></span> 
- <span data-ttu-id="294e1-2581">National ID Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="294e1-2582">Italia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="294e1-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2583">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2583">Format</span></span>

<span data-ttu-id="294e1-2584">Una combinazione di 10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2585">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2585">Pattern</span></span>

- <span data-ttu-id="294e1-2586">Una combinazione di 10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="294e1-2587">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="294e1-2588">La lettera "A" o "V" (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="294e1-2589">7 lettere (senza distinzione tra maiuscole/minuscole), cifre o carattere di sottolineatura</span><span class="sxs-lookup"><span data-stu-id="294e1-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="294e1-2590">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2591">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2591">Checksum</span></span>

<span data-ttu-id="294e1-2592">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2593">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2593">Definition</span></span>

<span data-ttu-id="294e1-2594">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2595">L'espressione regolare Regex_italy_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2596">Viene trovata una parola chiave da Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2597">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="294e1-2598">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="294e1-2599">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="294e1-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="294e1-2600">patente di guida</span><span class="sxs-lookup"><span data-stu-id="294e1-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="294e1-2601">Giappone - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="294e1-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2602">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2602">Format</span></span>

<span data-ttu-id="294e1-2603">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2604">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2604">Pattern</span></span>

<span data-ttu-id="294e1-2605">Numero di conto corrente:</span><span class="sxs-lookup"><span data-stu-id="294e1-2605">Bank account number:</span></span>
- <span data-ttu-id="294e1-2606">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2606">Seven or eight digits</span></span>
- <span data-ttu-id="294e1-2607">Codice della filiale del conto corrente:</span><span class="sxs-lookup"><span data-stu-id="294e1-2607">Bank account branch code:</span></span>
- <span data-ttu-id="294e1-2608">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2608">Four digits</span></span> 
- <span data-ttu-id="294e1-2609">Uno spazio o un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="294e1-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="294e1-2610">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2610">Three digits</span></span>

<span data-ttu-id="294e1-2611">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2611">Checksum</span></span>

<span data-ttu-id="294e1-2612">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2613">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2613">Definition</span></span>

<span data-ttu-id="294e1-2614">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2615">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2616">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="294e1-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="294e1-2617">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-2617">One of the following is true:</span></span>
- <span data-ttu-id="294e1-2618">La funzione Func_jp_bank_account_branch_code restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2619">Viene trovata una parola chiave da Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="294e1-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="294e1-2620">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2621">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2622">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="294e1-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2623">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="294e1-2624">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="294e1-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="294e1-2625">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2625">Checking Account Number</span></span> 
- <span data-ttu-id="294e1-2626">Checking Account</span><span class="sxs-lookup"><span data-stu-id="294e1-2626">Checking Account</span></span> 
- <span data-ttu-id="294e1-2627">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="294e1-2627">Checking Account #</span></span> 
- <span data-ttu-id="294e1-2628">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="294e1-2629">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="294e1-2629">Checking Acct #</span></span> 
- <span data-ttu-id="294e1-2630">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="294e1-2631">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2631">Checking Account No.</span></span> 
- <span data-ttu-id="294e1-2632">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2632">Bank Account Number</span></span> 
- <span data-ttu-id="294e1-2633">Bank Account</span><span class="sxs-lookup"><span data-stu-id="294e1-2633">Bank Account</span></span> 
- <span data-ttu-id="294e1-2634">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="294e1-2634">Bank Account #</span></span> 
- <span data-ttu-id="294e1-2635">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="294e1-2636">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="294e1-2636">Bank Acct #</span></span> 
- <span data-ttu-id="294e1-2637">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="294e1-2638">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2638">Bank Account No.</span></span> 
- <span data-ttu-id="294e1-2639">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2639">Savings Account Number</span></span> 
- <span data-ttu-id="294e1-2640">Savings Account</span><span class="sxs-lookup"><span data-stu-id="294e1-2640">Savings Account</span></span> 
- <span data-ttu-id="294e1-2641">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="294e1-2641">Savings Account #</span></span> 
- <span data-ttu-id="294e1-2642">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="294e1-2643">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="294e1-2643">Savings Acct #</span></span> 
- <span data-ttu-id="294e1-2644">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="294e1-2645">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2645">Savings Account No.</span></span> 
- <span data-ttu-id="294e1-2646">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2646">Debit Account Number</span></span> 
- <span data-ttu-id="294e1-2647">Debit Account</span><span class="sxs-lookup"><span data-stu-id="294e1-2647">Debit Account</span></span> 
- <span data-ttu-id="294e1-2648">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="294e1-2648">Debit Account #</span></span> 
- <span data-ttu-id="294e1-2649">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="294e1-2650">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="294e1-2650">Debit Acct #</span></span> 
- <span data-ttu-id="294e1-2651">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="294e1-2652">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2652">Debit Account No.</span></span> 
- <span data-ttu-id="294e1-2653">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="294e1-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="294e1-2654">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="294e1-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="294e1-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="294e1-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="294e1-2656">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="294e1-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="294e1-2657">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="294e1-2657">口座番号の確認</span></span> 
- <span data-ttu-id="294e1-2658">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2658">銀行口座番号</span></span> 
- <span data-ttu-id="294e1-2659">銀行口座</span><span class="sxs-lookup"><span data-stu-id="294e1-2659">銀行口座</span></span> 
- <span data-ttu-id="294e1-2660">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="294e1-2660">銀行口座＃</span></span> 
- <span data-ttu-id="294e1-2661">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="294e1-2662">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="294e1-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="294e1-2663">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="294e1-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="294e1-2664">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2664">銀行口座番号</span></span>
- <span data-ttu-id="294e1-2665">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="294e1-2666">預金口座</span><span class="sxs-lookup"><span data-stu-id="294e1-2666">預金口座</span></span> 
- <span data-ttu-id="294e1-2667">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="294e1-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="294e1-2668">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="294e1-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="294e1-2669">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="294e1-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="294e1-2670">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="294e1-2671">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="294e1-2672">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="294e1-2673">口座番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2673">口座番号</span></span> 
- <span data-ttu-id="294e1-2674">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="294e1-2674">口座番号＃</span></span> 
- <span data-ttu-id="294e1-2675">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="294e1-2676">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="294e1-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="294e1-2677">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="294e1-2678">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="294e1-2679">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="294e1-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="294e1-2680">Otemachi</span><span class="sxs-lookup"><span data-stu-id="294e1-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="294e1-2681">Giappone - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="294e1-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2682">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2682">Format</span></span>

<span data-ttu-id="294e1-2683">12 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2684">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2684">Pattern</span></span>

<span data-ttu-id="294e1-2685">12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2686">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2686">Checksum</span></span>

<span data-ttu-id="294e1-2687">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2688">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2688">Definition</span></span>

<span data-ttu-id="294e1-2689">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2690">La funzione Func_jp_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2691">Viene trovata una parola chiave da Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2692">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="294e1-2693">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="294e1-2694">DL #</span><span class="sxs-lookup"><span data-stu-id="294e1-2694">dl#</span></span> 
- <span data-ttu-id="294e1-2695">DL</span><span class="sxs-lookup"><span data-stu-id="294e1-2695">DL＃</span></span> 
- <span data-ttu-id="294e1-2696">DLS #</span><span class="sxs-lookup"><span data-stu-id="294e1-2696">dls#</span></span> 
- <span data-ttu-id="294e1-2697">DLS</span><span class="sxs-lookup"><span data-stu-id="294e1-2697">DLS＃</span></span> 
- <span data-ttu-id="294e1-2698">driver license</span><span class="sxs-lookup"><span data-stu-id="294e1-2698">driver license</span></span> 
- <span data-ttu-id="294e1-2699">driver licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-2699">driver licenses</span></span> 
- <span data-ttu-id="294e1-2700">drivers license</span><span class="sxs-lookup"><span data-stu-id="294e1-2700">drivers license</span></span> 
- <span data-ttu-id="294e1-2701">driver's license</span><span class="sxs-lookup"><span data-stu-id="294e1-2701">driver's license</span></span> 
- <span data-ttu-id="294e1-2702">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-2702">drivers licenses</span></span> 
- <span data-ttu-id="294e1-2703">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-2703">driver's licenses</span></span> 
- <span data-ttu-id="294e1-2704">driving licence</span><span class="sxs-lookup"><span data-stu-id="294e1-2704">driving licence</span></span> 
- <span data-ttu-id="294e1-2705">driver'lic #</span><span class="sxs-lookup"><span data-stu-id="294e1-2705">lic#</span></span> 
- <span data-ttu-id="294e1-2706">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="294e1-2706">LIC＃</span></span> 
- <span data-ttu-id="294e1-2707">driver'lics #</span><span class="sxs-lookup"><span data-stu-id="294e1-2707">lics#</span></span> 
- <span data-ttu-id="294e1-2708">state id</span><span class="sxs-lookup"><span data-stu-id="294e1-2708">state id</span></span> 
- <span data-ttu-id="294e1-2709">state identification</span><span class="sxs-lookup"><span data-stu-id="294e1-2709">state identification</span></span> 
- <span data-ttu-id="294e1-2710">state identification number</span><span class="sxs-lookup"><span data-stu-id="294e1-2710">state identification number</span></span> 
- <span data-ttu-id="294e1-2711">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="294e1-2711">低所得国＃</span></span> 
- <span data-ttu-id="294e1-2712">免許証</span><span class="sxs-lookup"><span data-stu-id="294e1-2712">免許証</span></span> 
- <span data-ttu-id="294e1-2713">状態ID</span><span class="sxs-lookup"><span data-stu-id="294e1-2713">状態ID</span></span>
- <span data-ttu-id="294e1-2714">状態の識別</span><span class="sxs-lookup"><span data-stu-id="294e1-2714">状態の識別</span></span> 
- <span data-ttu-id="294e1-2715">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2715">状態の識別番号</span></span> 
- <span data-ttu-id="294e1-2716">運転免許</span><span class="sxs-lookup"><span data-stu-id="294e1-2716">運転免許</span></span> 
- <span data-ttu-id="294e1-2717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="294e1-2717">運転免許証</span></span> 
- <span data-ttu-id="294e1-2718">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="294e1-2719">Giappone - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2720">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2720">Format</span></span>

<span data-ttu-id="294e1-2721">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2722">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2722">Pattern</span></span>

<span data-ttu-id="294e1-2723">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2724">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2724">Checksum</span></span>

<span data-ttu-id="294e1-2725">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2726">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2726">Definition</span></span>

<span data-ttu-id="294e1-2727">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2728">La funzione Func_jp_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2729">Viene trovata una parola chiave da Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="294e1-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2730">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="294e1-2731">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="294e1-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="294e1-2732">パスポート</span><span class="sxs-lookup"><span data-stu-id="294e1-2732">パスポート</span></span> 
- <span data-ttu-id="294e1-2733">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2733">パスポート番号</span></span> 
- <span data-ttu-id="294e1-2734">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="294e1-2734">パスポートのNum</span></span> 
- <span data-ttu-id="294e1-2735">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="294e1-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="294e1-2736">Giappone - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="294e1-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2737">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2737">Format</span></span>

<span data-ttu-id="294e1-2738">11 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2739">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2739">Pattern</span></span>

<span data-ttu-id="294e1-2740">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2741">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2741">Checksum</span></span>

<span data-ttu-id="294e1-2742">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2743">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2743">Definition</span></span>

<span data-ttu-id="294e1-2744">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2745">La funzione Func_jp_resident_registration_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2746">Viene trovata una parola chiave da Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2747">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="294e1-2748">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="294e1-2749">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2749">Resident Registration Number</span></span>
- <span data-ttu-id="294e1-2750">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2750">Resident Register Number</span></span> 
- <span data-ttu-id="294e1-2751">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="294e1-2752">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="294e1-2753">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2753">Resident Register No.</span></span> 
- <span data-ttu-id="294e1-2754">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="294e1-2755">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="294e1-2756">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="294e1-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="294e1-2757">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="294e1-2758">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="294e1-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="294e1-2759">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="294e1-2760">Giappone - Numero di assicurazione sociale (SIN)</span><span class="sxs-lookup"><span data-stu-id="294e1-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2761">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2761">Format</span></span>

<span data-ttu-id="294e1-2762">7-12 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2763">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2763">Pattern</span></span>

<span data-ttu-id="294e1-2764">7-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-2764">7-12 digits:</span></span>
- <span data-ttu-id="294e1-2765">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2765">Four digits</span></span> 
- <span data-ttu-id="294e1-2766">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="294e1-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="294e1-2767">Sei cifre o</span><span class="sxs-lookup"><span data-stu-id="294e1-2767">Six digits OR</span></span>
- <span data-ttu-id="294e1-2768">7-12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2769">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2769">Checksum</span></span>

<span data-ttu-id="294e1-2770">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2771">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2771">Definition</span></span>

<span data-ttu-id="294e1-2772">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2773">La funzione Func_jp_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2774">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="294e1-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="294e1-2775">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2776">La funzione Func_jp_sin_pre_1997 restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2777">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="294e1-2777">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2778">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="294e1-2779">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="294e1-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="294e1-2780">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="294e1-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="294e1-2781">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="294e1-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="294e1-2782">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="294e1-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="294e1-2783">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="294e1-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="294e1-2784">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="294e1-2785">Numero di carta di soggiorno giapponese</span><span class="sxs-lookup"><span data-stu-id="294e1-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2786">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2786">Format</span></span>

<span data-ttu-id="294e1-2787">12 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2788">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2788">Pattern</span></span>

<span data-ttu-id="294e1-2789">12 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-2789">12 letters and digits:</span></span>
- <span data-ttu-id="294e1-2790">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="294e1-2791">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2791">Eight digits</span></span> 
- <span data-ttu-id="294e1-2792">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2793">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2793">Checksum</span></span>

<span data-ttu-id="294e1-2794">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2795">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2795">Definition</span></span>

<span data-ttu-id="294e1-2796">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2797">L'espressione regolare Regex_jp_residence_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2798">Viene trovata una parola chiave da Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2799">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="294e1-2800">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="294e1-2801">Numero di carta di soggiorno</span><span class="sxs-lookup"><span data-stu-id="294e1-2801">Residence card number</span></span>
- <span data-ttu-id="294e1-2802">Carta di soggiorno No</span><span class="sxs-lookup"><span data-stu-id="294e1-2802">Residence card no</span></span>
- <span data-ttu-id="294e1-2803">Carta di soggiorno #</span><span class="sxs-lookup"><span data-stu-id="294e1-2803">Residence card #</span></span>
- <span data-ttu-id="294e1-2804">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="294e1-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="294e1-2805">Malesia - Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="294e1-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2806">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2806">Format</span></span>

<span data-ttu-id="294e1-2807">12 cifre contenenti lineette facoltative</span><span class="sxs-lookup"><span data-stu-id="294e1-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2808">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2808">Pattern</span></span>

<span data-ttu-id="294e1-2809">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-2809">12 digits:</span></span>
- <span data-ttu-id="294e1-2810">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="294e1-2811">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="294e1-2811">A dash (optional)</span></span> 
- <span data-ttu-id="294e1-2812">Codice luogo di nascita a due lettere </span><span class="sxs-lookup"><span data-stu-id="294e1-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="294e1-2813">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="294e1-2813">A dash (optional)</span></span> 
- <span data-ttu-id="294e1-2814">Tre cifre casuali </span><span class="sxs-lookup"><span data-stu-id="294e1-2814">Three random digits</span></span> 
- <span data-ttu-id="294e1-2815">Codice genere a una cifra singola</span><span class="sxs-lookup"><span data-stu-id="294e1-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2816">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2816">Checksum</span></span>

<span data-ttu-id="294e1-2817">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2818">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2818">Definition</span></span>

<span data-ttu-id="294e1-2819">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2820">L'espressione regolare Regex_malaysia_id_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2821">Viene trovata una parola chiave da Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2822">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="294e1-2823">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="294e1-2824">scheda dell'applicazione digitale</span><span class="sxs-lookup"><span data-stu-id="294e1-2824">digital application card</span></span>
- <span data-ttu-id="294e1-2825">i/c</span><span class="sxs-lookup"><span data-stu-id="294e1-2825">i/c</span></span>
- <span data-ttu-id="294e1-2826">i/c no</span><span class="sxs-lookup"><span data-stu-id="294e1-2826">i/c no</span></span>
- <span data-ttu-id="294e1-2827">IC</span><span class="sxs-lookup"><span data-stu-id="294e1-2827">ic</span></span>
- <span data-ttu-id="294e1-2828">IC No</span><span class="sxs-lookup"><span data-stu-id="294e1-2828">ic no</span></span>
- <span data-ttu-id="294e1-2829">id card</span><span class="sxs-lookup"><span data-stu-id="294e1-2829">id card</span></span>
- <span data-ttu-id="294e1-2830">Scheda di identificazione</span><span class="sxs-lookup"><span data-stu-id="294e1-2830">identification Card</span></span>
- <span data-ttu-id="294e1-2831">carta di identità</span><span class="sxs-lookup"><span data-stu-id="294e1-2831">identity card</span></span>
- <span data-ttu-id="294e1-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="294e1-2832">k/p</span></span>
- <span data-ttu-id="294e1-2833">k/p no</span><span class="sxs-lookup"><span data-stu-id="294e1-2833">k/p no</span></span>
- <span data-ttu-id="294e1-2834">diri akuan Kad</span><span class="sxs-lookup"><span data-stu-id="294e1-2834">kad akuan diri</span></span>
- <span data-ttu-id="294e1-2835">Kad Aplikasi digitale</span><span class="sxs-lookup"><span data-stu-id="294e1-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="294e1-2836">Kad Pengenalan Malaysia</span><span class="sxs-lookup"><span data-stu-id="294e1-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="294e1-2837">KP</span><span class="sxs-lookup"><span data-stu-id="294e1-2837">kp</span></span>
- <span data-ttu-id="294e1-2838">KP No</span><span class="sxs-lookup"><span data-stu-id="294e1-2838">kp no</span></span>
- <span data-ttu-id="294e1-2839">MyKad</span><span class="sxs-lookup"><span data-stu-id="294e1-2839">mykad</span></span>
- <span data-ttu-id="294e1-2840">MYKAS</span><span class="sxs-lookup"><span data-stu-id="294e1-2840">mykas</span></span>
- <span data-ttu-id="294e1-2841">mykid</span><span class="sxs-lookup"><span data-stu-id="294e1-2841">mykid</span></span>
- <span data-ttu-id="294e1-2842">mypr</span><span class="sxs-lookup"><span data-stu-id="294e1-2842">mypr</span></span>
- <span data-ttu-id="294e1-2843">mytentera</span><span class="sxs-lookup"><span data-stu-id="294e1-2843">mytentera</span></span>
- <span data-ttu-id="294e1-2844">carta di identità Malaysia</span><span class="sxs-lookup"><span data-stu-id="294e1-2844">malaysia identity card</span></span>
- <span data-ttu-id="294e1-2845">carta di identità malaysiana</span><span class="sxs-lookup"><span data-stu-id="294e1-2845">malaysian identity card</span></span>
- <span data-ttu-id="294e1-2846">NRIC</span><span class="sxs-lookup"><span data-stu-id="294e1-2846">nric</span></span>
- <span data-ttu-id="294e1-2847">scheda di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="294e1-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="294e1-2848">Paesi Bassi - Numero di servizio cittadino (BSN)</span><span class="sxs-lookup"><span data-stu-id="294e1-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2849">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2849">Format</span></span>

<span data-ttu-id="294e1-2850">8-9 cifre contenenti spazi facoltativi </span><span class="sxs-lookup"><span data-stu-id="294e1-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2851">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2851">Pattern</span></span>

<span data-ttu-id="294e1-2852">8-9 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-2852">8-9 digits:</span></span>
- <span data-ttu-id="294e1-2853">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2853">Three digits</span></span> 
- <span data-ttu-id="294e1-2854">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="294e1-2854">A space (optional)</span></span> 
- <span data-ttu-id="294e1-2855">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2855">Three digits</span></span> 
- <span data-ttu-id="294e1-2856">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="294e1-2856">A space (optional)</span></span> 
- <span data-ttu-id="294e1-2857">2-3 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2858">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2858">Checksum</span></span>

<span data-ttu-id="294e1-2859">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2860">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2860">Definition</span></span>

<span data-ttu-id="294e1-2861">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2862">La funzione Func_netherlands_bsn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2863">Viene trovata una parola chiave da Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="294e1-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="294e1-2864">La funzione Func_eu_date2 rileva una data nel formato di data appropriato.</span><span class="sxs-lookup"><span data-stu-id="294e1-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="294e1-2865">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2865">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2866">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="294e1-2867">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="294e1-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="294e1-2868">Numero di servizio cittadino</span><span class="sxs-lookup"><span data-stu-id="294e1-2868">Citizen service number</span></span> 
- <span data-ttu-id="294e1-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="294e1-2869">BSN</span></span> 
- <span data-ttu-id="294e1-2870">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="294e1-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="294e1-2871">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="294e1-2871">Sofinummer</span></span> 
- <span data-ttu-id="294e1-2872">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="294e1-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="294e1-2873">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="294e1-2874">Nuova Zelanda - Numero del Ministero della Sanità</span><span class="sxs-lookup"><span data-stu-id="294e1-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2875">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2875">Format</span></span>

<span data-ttu-id="294e1-2876">Tre lettere, uno spazio (facoltativo) e quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2877">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2877">Pattern</span></span>

<span data-ttu-id="294e1-2878">Tre lettere (senza distinzione tra maiuscole/minuscole) uno spazio (facoltativo) quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2879">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2879">Checksum</span></span>

<span data-ttu-id="294e1-2880">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2881">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2881">Definition</span></span>

<span data-ttu-id="294e1-2882">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2883">La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2884">Viene trovata una parola chiave da Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="294e1-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="294e1-2885">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2885">The checksum passes.</span></span>

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

<span data-ttu-id="294e1-2886">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2886">Keywords</span></span>

<span data-ttu-id="294e1-2887">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="294e1-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="294e1-2888">NHI</span><span class="sxs-lookup"><span data-stu-id="294e1-2888">NHI</span></span> 
- <span data-ttu-id="294e1-2889">New Zealand</span><span class="sxs-lookup"><span data-stu-id="294e1-2889">New Zealand</span></span> 
- <span data-ttu-id="294e1-2890">Integrità</span><span class="sxs-lookup"><span data-stu-id="294e1-2890">Health</span></span> 
- <span data-ttu-id="294e1-2891">trattamento</span><span class="sxs-lookup"><span data-stu-id="294e1-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="294e1-2892">Norvegia - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="294e1-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2893">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2893">Format</span></span>

<span data-ttu-id="294e1-2894">11 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2895">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2895">Pattern</span></span>

<span data-ttu-id="294e1-2896">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-2896">11 digits:</span></span>
- <span data-ttu-id="294e1-2897">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="294e1-2898">Numero individuale composto da tre cifre </span><span class="sxs-lookup"><span data-stu-id="294e1-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="294e1-2899">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="294e1-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2900">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2900">Checksum</span></span>

<span data-ttu-id="294e1-2901">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2902">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2902">Definition</span></span>

<span data-ttu-id="294e1-2903">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2904">La funzione Func_norway_id_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2905">Viene trovata una parola chiave da Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="294e1-2906">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2906">The checksum passes.</span></span>
- <span data-ttu-id="294e1-2907">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2908">La funzione Func_norway_id_numbe trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2909">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2909">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2910">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="294e1-2911">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="294e1-2912">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="294e1-2912">Personal identification number</span></span>
- <span data-ttu-id="294e1-2913">Numero ID norvegese</span><span class="sxs-lookup"><span data-stu-id="294e1-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="294e1-2914">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="294e1-2914">ID Number</span></span>
- <span data-ttu-id="294e1-2915">Identificazione</span><span class="sxs-lookup"><span data-stu-id="294e1-2915">Identification</span></span>
- <span data-ttu-id="294e1-2916">Personnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-2916">Personnummer</span></span>
- <span data-ttu-id="294e1-2917">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="294e1-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="294e1-2918">Filippine - Numero ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="294e1-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2919">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2919">Format</span></span>

<span data-ttu-id="294e1-2920">12 cifre separate da dei segni meno</span><span class="sxs-lookup"><span data-stu-id="294e1-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2921">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2921">Pattern</span></span>

<span data-ttu-id="294e1-2922">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-2922">12 digits:</span></span>
- <span data-ttu-id="294e1-2923">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2923">Four digits</span></span> 
- <span data-ttu-id="294e1-2924">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-2924">A hyphen</span></span> 
- <span data-ttu-id="294e1-2925">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2925">Seven digits</span></span> 
- <span data-ttu-id="294e1-2926">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-2926">A hyphen</span></span> 
- <span data-ttu-id="294e1-2927">Una cifra</span><span class="sxs-lookup"><span data-stu-id="294e1-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2928">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2928">Checksum</span></span>

<span data-ttu-id="294e1-2929">No</span><span class="sxs-lookup"><span data-stu-id="294e1-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2930">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2930">Definition</span></span>

<span data-ttu-id="294e1-2931">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2932">L'espressione regolare Regex_philippines_unified_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2933">Viene trovata una parola chiave da Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="294e1-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2934">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="294e1-2935">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="294e1-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="294e1-2936">ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="294e1-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="294e1-2937">UMID</span><span class="sxs-lookup"><span data-stu-id="294e1-2937">UMID</span></span> 
- <span data-ttu-id="294e1-2938">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="294e1-2938">Identity Card</span></span> 
- <span data-ttu-id="294e1-2939">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="294e1-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="294e1-2940">Carta di identita - Polonia</span><span class="sxs-lookup"><span data-stu-id="294e1-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2941">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2941">Format</span></span>

<span data-ttu-id="294e1-2942">Tre lettere e sei cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2943">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2943">Pattern</span></span>

<span data-ttu-id="294e1-2944">Tre lettere (senza distinzione tra maiuscole/minuscole) seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2945">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2945">Checksum</span></span>

<span data-ttu-id="294e1-2946">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2947">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2947">Definition</span></span>

<span data-ttu-id="294e1-2948">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_polish_national_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="294e1-2949">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="294e1-2950">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2951">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="294e1-2952">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="294e1-2953">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="294e1-2953">Dowód osobisty</span></span>
- <span data-ttu-id="294e1-2954">Numero dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="294e1-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="294e1-2955">Nazwa i numeri dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="294e1-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="294e1-2956">Nazwa i Nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="294e1-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="294e1-2957">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="294e1-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="294e1-2958">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="294e1-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="294e1-2959">Dow.</span><span class="sxs-lookup"><span data-stu-id="294e1-2959">dow.</span></span> <span data-ttu-id="294e1-2960">OS.</span><span class="sxs-lookup"><span data-stu-id="294e1-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="294e1-2961">ID nazionale Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="294e1-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2962">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2962">Format</span></span>

<span data-ttu-id="294e1-2963">11 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2964">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2964">Pattern</span></span>

<span data-ttu-id="294e1-2965">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2966">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2966">Checksum</span></span>

<span data-ttu-id="294e1-2967">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2968">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2968">Definition</span></span>

<span data-ttu-id="294e1-2969">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2970">La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2971">Viene trovata una parola chiave da Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="294e1-2972">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-2973">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="294e1-2974">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="294e1-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="294e1-2975">Nr PESEL</span></span>
- <span data-ttu-id="294e1-2976">PESEL</span><span class="sxs-lookup"><span data-stu-id="294e1-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="294e1-2977">Passaporto Polonia</span><span class="sxs-lookup"><span data-stu-id="294e1-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2978">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2978">Format</span></span>

<span data-ttu-id="294e1-2979">Due lettere e sette cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2980">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2980">Pattern</span></span>

<span data-ttu-id="294e1-2981">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-2982">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-2982">Checksum</span></span>

<span data-ttu-id="294e1-2983">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-2984">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-2984">Definition</span></span>

<span data-ttu-id="294e1-2985">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-2986">La funzione Func_polish_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-2987">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="294e1-2988">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-2988">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-2989">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="294e1-2990">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="294e1-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="294e1-2991">Numero Paszportu</span><span class="sxs-lookup"><span data-stu-id="294e1-2991">Numer paszportu</span></span>
- <span data-ttu-id="294e1-2992">Nr.</span><span class="sxs-lookup"><span data-stu-id="294e1-2992">Nr.</span></span> <span data-ttu-id="294e1-2993">Paszportu</span><span class="sxs-lookup"><span data-stu-id="294e1-2993">Paszportu</span></span>
- <span data-ttu-id="294e1-2994">Paszport</span><span class="sxs-lookup"><span data-stu-id="294e1-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="294e1-2995">Portogallo - Numero di carta del cittadino</span><span class="sxs-lookup"><span data-stu-id="294e1-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-2996">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-2996">Format</span></span>

<span data-ttu-id="294e1-2997">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-2998">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-2998">Pattern</span></span>

<span data-ttu-id="294e1-2999">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3000">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3000">Checksum</span></span>

<span data-ttu-id="294e1-3001">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3002">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3002">Definition</span></span>

<span data-ttu-id="294e1-3003">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3004">L'espressione regolare Regex_portugal_citizen_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3005">Viene trovata una parola chiave da Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="294e1-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3006">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="294e1-3007">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="294e1-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="294e1-3008">Scheda cittadino</span><span class="sxs-lookup"><span data-stu-id="294e1-3008">Citizen Card</span></span>
- <span data-ttu-id="294e1-3009">Carta ID</span><span class="sxs-lookup"><span data-stu-id="294e1-3009">National ID Card</span></span>
- <span data-ttu-id="294e1-3010">CC</span><span class="sxs-lookup"><span data-stu-id="294e1-3010">CC</span></span>
- <span data-ttu-id="294e1-3011">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="294e1-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="294e1-3012">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="294e1-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="294e1-3013">Arabia Saudita - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="294e1-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3014">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3014">Format</span></span>

<span data-ttu-id="294e1-3015">10 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3016">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3016">Pattern</span></span>

<span data-ttu-id="294e1-3017">10 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3018">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3018">Checksum</span></span>

<span data-ttu-id="294e1-3019">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3020">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3020">Definition</span></span>

<span data-ttu-id="294e1-3021">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3022">L'espressione regolare Regex_saudi_arabia_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3023">Viene trovata una parola chiave da Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="294e1-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-3024">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="294e1-3025">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="294e1-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="294e1-3026">Identification Card</span><span class="sxs-lookup"><span data-stu-id="294e1-3026">Identification Card</span></span> 
- <span data-ttu-id="294e1-3027">I card number</span><span class="sxs-lookup"><span data-stu-id="294e1-3027">I card number</span></span> 
- <span data-ttu-id="294e1-3028">ID number</span><span class="sxs-lookup"><span data-stu-id="294e1-3028">ID number</span></span> 
- <span data-ttu-id="294e1-3029">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="294e1-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="294e1-3030">Singapore - Numero di carta di identità di registrazione nazionale (NRIC)</span><span class="sxs-lookup"><span data-stu-id="294e1-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3031">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3031">Format</span></span>

<span data-ttu-id="294e1-3032">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="294e1-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3033">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3033">Pattern</span></span>

- <span data-ttu-id="294e1-3034">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="294e1-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="294e1-3035">La lettera "F", "G", "S" o "T" (senza distinzione tra maiuscole e minuscole) </span><span class="sxs-lookup"><span data-stu-id="294e1-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="294e1-3036">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3036">Seven digits</span></span> 
- <span data-ttu-id="294e1-3037">Una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="294e1-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3038">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3038">Checksum</span></span>

<span data-ttu-id="294e1-3039">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3040">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3040">Definition</span></span>

<span data-ttu-id="294e1-3041">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3042">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3043">Viene trovata una parola chiave da Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="294e1-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="294e1-3044">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-3044">The checksum passes.</span></span>

<span data-ttu-id="294e1-3045">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3046">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3047">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-3047">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-3048">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="294e1-3049">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="294e1-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="294e1-3050">Carta di identità di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="294e1-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="294e1-3051">Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="294e1-3051">Identity Card Number</span></span> 
- <span data-ttu-id="294e1-3052">NRIC</span><span class="sxs-lookup"><span data-stu-id="294e1-3052">NRIC</span></span> 
- <span data-ttu-id="294e1-3053">IC</span><span class="sxs-lookup"><span data-stu-id="294e1-3053">IC</span></span> 
- <span data-ttu-id="294e1-3054">Numero di identificazione per stranieri</span><span class="sxs-lookup"><span data-stu-id="294e1-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="294e1-3055">FIN</span><span class="sxs-lookup"><span data-stu-id="294e1-3055">FIN</span></span> 
- <span data-ttu-id="294e1-3056">身份证</span><span class="sxs-lookup"><span data-stu-id="294e1-3056">身份证</span></span> 
- <span data-ttu-id="294e1-3057">身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="294e1-3058">Sudafrica - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="294e1-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3059">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3059">Format</span></span>

<span data-ttu-id="294e1-3060">13 cifre che possono contenere spazi</span><span class="sxs-lookup"><span data-stu-id="294e1-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3061">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3061">Pattern</span></span>

<span data-ttu-id="294e1-3062">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-3062">13 digits:</span></span>
- <span data-ttu-id="294e1-3063">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="294e1-3064">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3064">Four digits</span></span> 
- <span data-ttu-id="294e1-3065">Un indicatore di cittadinanza a una cifra </span><span class="sxs-lookup"><span data-stu-id="294e1-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="294e1-3066">La cifra "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="294e1-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="294e1-3067">Una cifra, ovvero una cifra di checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3068">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3068">Checksum</span></span>

<span data-ttu-id="294e1-3069">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3070">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3070">Definition</span></span>

<span data-ttu-id="294e1-3071">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3072">La funzione Func_south_africa_identification_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3073">Viene trovata una parola chiave da Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="294e1-3074">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3075">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="294e1-3076">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="294e1-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="294e1-3077">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="294e1-3077">Identity card</span></span>
- <span data-ttu-id="294e1-3078">ID</span><span class="sxs-lookup"><span data-stu-id="294e1-3078">ID</span></span>
- <span data-ttu-id="294e1-3079">Identificazione</span><span class="sxs-lookup"><span data-stu-id="294e1-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="294e1-3080">Corea del Sud - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="294e1-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3081">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3081">Format</span></span>

<span data-ttu-id="294e1-3082">13 cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="294e1-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3083">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3083">Pattern</span></span>

<span data-ttu-id="294e1-3084">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-3084">13 digits:</span></span>
- <span data-ttu-id="294e1-3085">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="294e1-3086">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="294e1-3086">A hyphen</span></span> 
- <span data-ttu-id="294e1-3087">Una cifra determinata dal secolo e dal sesso </span><span class="sxs-lookup"><span data-stu-id="294e1-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="294e1-3088">Codice di quattro cifre dell’area geografica di nascita </span><span class="sxs-lookup"><span data-stu-id="294e1-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="294e1-3089">Una cifra utilizzata per distinguere persone i cui numeri precedenti sono uguali </span><span class="sxs-lookup"><span data-stu-id="294e1-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="294e1-3090">Una cifra di controllo.</span><span class="sxs-lookup"><span data-stu-id="294e1-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3091">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3091">Checksum</span></span>

<span data-ttu-id="294e1-3092">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3093">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3093">Definition</span></span>

<span data-ttu-id="294e1-3094">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3095">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3096">Viene trovata una parola chiave da Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="294e1-3097">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-3097">The checksum passes.</span></span>

<span data-ttu-id="294e1-3098">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3099">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3100">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-3100">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-3101">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="294e1-3102">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="294e1-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="294e1-3103">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="294e1-3103">National ID card</span></span> 
- <span data-ttu-id="294e1-3104">Numero di registrazione del cittadino</span><span class="sxs-lookup"><span data-stu-id="294e1-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="294e1-3105">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="294e1-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="294e1-3106">RRN</span><span class="sxs-lookup"><span data-stu-id="294e1-3106">RRN</span></span> 
- <span data-ttu-id="294e1-3107">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="294e1-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="294e1-3108">Spagna - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="294e1-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3109">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3109">Format</span></span>

<span data-ttu-id="294e1-3110">11-12 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3111">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3111">Pattern</span></span>

<span data-ttu-id="294e1-3112">11-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-3112">11-12 digits:</span></span>
- <span data-ttu-id="294e1-3113">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3113">Two digits</span></span> 
- <span data-ttu-id="294e1-3114">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="294e1-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="294e1-3115">7-8 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3115">7-8 digits</span></span> 
- <span data-ttu-id="294e1-3116">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="294e1-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="294e1-3117">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3118">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3118">Checksum</span></span>

<span data-ttu-id="294e1-3119">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3120">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3120">Definition</span></span>

<span data-ttu-id="294e1-3121">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3122">La funzione Func_spanish_social_security_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3123">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3124">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3124">Keywords</span></span>

<span data-ttu-id="294e1-3125">Nessuno</span><span class="sxs-lookup"><span data-stu-id="294e1-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="294e1-3126">Stringa di connessione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="294e1-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3127">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3127">Format</span></span>

<span data-ttu-id="294e1-3128">Stringa "ID utente", "ID utente", "UID" o "UserId" seguito dai caratteri e dalle stringhe delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="294e1-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3129">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3129">Pattern</span></span>

- <span data-ttu-id="294e1-3130">Stringa "ID utente", "ID utente", "UID" o "UserId"</span><span class="sxs-lookup"><span data-stu-id="294e1-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="294e1-3131">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="294e1-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="294e1-3132">La stringa "password" o "pwd", dove "pwd" non è preceduta da una lettera minuscola</span><span class="sxs-lookup"><span data-stu-id="294e1-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="294e1-3133">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-3133">An equal sign (=)</span></span>
- <span data-ttu-id="294e1-3134">Qualsiasi carattere che non sia un segno di dollaro ($), un simbolo di percentuale (%), un simbolo maggiore di (>), il simbolo (@), le virgolette ("), il punto e virgola (;), parentesi graffa sinistra ([) o parentesi quadra sinistra ({)</span><span class="sxs-lookup"><span data-stu-id="294e1-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="294e1-3135">Qualsiasi combinazione di 7-128 caratteri che non sono un punto e virgola (;), barra (/) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="294e1-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="294e1-3136">Un punto e virgola (;) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="294e1-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3137">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3137">Checksum</span></span>

<span data-ttu-id="294e1-3138">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3139">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3139">Definition</span></span>

<span data-ttu-id="294e1-3140">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3141">L'espressione regolare CEP_Regex_SQLServerConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3142">**Non** viene trovata una parola chiave da CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="294e1-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="294e1-3143">L'espressione regolare CEP_PasswordPlaceHolder non **trova contenuto** corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3144">L'espressione regolare CEP_CommonExampleKeywords non **trova contenuto** corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-3145">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="294e1-3146">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="294e1-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="294e1-3147">some-password</span><span class="sxs-lookup"><span data-stu-id="294e1-3147">some-password</span></span>
- <span data-ttu-id="294e1-3148">somepassword</span><span class="sxs-lookup"><span data-stu-id="294e1-3148">somepassword</span></span>
- <span data-ttu-id="294e1-3149">secretPassword</span><span class="sxs-lookup"><span data-stu-id="294e1-3149">secretPassword</span></span>
- <span data-ttu-id="294e1-3150">esempio</span><span class="sxs-lookup"><span data-stu-id="294e1-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="294e1-3151">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="294e1-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="294e1-3152">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="294e1-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="294e1-3153">Password o pwd seguito da 0-2 spazi, un segno di uguale (=), 0-2 spazi e un asterisco (\*)-----------------</span><span class="sxs-lookup"><span data-stu-id="294e1-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="294e1-3154">Password o pwd seguito da:</span><span class="sxs-lookup"><span data-stu-id="294e1-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="294e1-3155">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="294e1-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="294e1-3156">Meno di simbolo (<)</span><span class="sxs-lookup"><span data-stu-id="294e1-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="294e1-3157">Qualsiasi combinazione di 1-200 caratteri che sono lettere maiuscole o minuscole, cifre, asterisco (\*), segno meno (-), sottolineatura (_) o carattere dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="294e1-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="294e1-3158">Valore maggiore di Symbol (>)</span><span class="sxs-lookup"><span data-stu-id="294e1-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="294e1-3159">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="294e1-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="294e1-3160">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="294e1-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="294e1-3161">contoso</span><span class="sxs-lookup"><span data-stu-id="294e1-3161">contoso</span></span>
- <span data-ttu-id="294e1-3162">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="294e1-3162">fabrikam</span></span>
- <span data-ttu-id="294e1-3163">Northwind</span><span class="sxs-lookup"><span data-stu-id="294e1-3163">northwind</span></span>
- <span data-ttu-id="294e1-3164">sandbox</span><span class="sxs-lookup"><span data-stu-id="294e1-3164">sandbox</span></span>
- <span data-ttu-id="294e1-3165">OneBox</span><span class="sxs-lookup"><span data-stu-id="294e1-3165">onebox</span></span>
- <span data-ttu-id="294e1-3166">localhost</span><span class="sxs-lookup"><span data-stu-id="294e1-3166">localhost</span></span>
- <span data-ttu-id="294e1-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="294e1-3167">127.0.0.1</span></span>
- <span data-ttu-id="294e1-3168">testacs.</span><span class="sxs-lookup"><span data-stu-id="294e1-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-3169">com</span><span class="sxs-lookup"><span data-stu-id="294e1-3169">com</span></span>
- <span data-ttu-id="294e1-3170">s-int.</span><span class="sxs-lookup"><span data-stu-id="294e1-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="294e1-3171">NET</span><span class="sxs-lookup"><span data-stu-id="294e1-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="294e1-3172">Svezia - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="294e1-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3173">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3173">Format</span></span>

<span data-ttu-id="294e1-3174">10 o 12 cifre e un delimitatore facoltativo</span><span class="sxs-lookup"><span data-stu-id="294e1-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3175">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3175">Pattern</span></span>

<span data-ttu-id="294e1-3176">10 o 12 cifre e un delimitatore facoltativo:</span><span class="sxs-lookup"><span data-stu-id="294e1-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="294e1-3177">2-4 cifre (facoltative)</span><span class="sxs-lookup"><span data-stu-id="294e1-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="294e1-3178">Sei cifre nel formato data AAMMGG</span><span class="sxs-lookup"><span data-stu-id="294e1-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="294e1-3179">Delimitatore di "-" o "+" (facoltativo) più</span><span class="sxs-lookup"><span data-stu-id="294e1-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="294e1-3180">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3181">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3181">Checksum</span></span>

<span data-ttu-id="294e1-3182">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3183">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3183">Definition</span></span>

<span data-ttu-id="294e1-3184">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3185">La funzione Func_swedish_national_identifier restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3186">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3187">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3187">Keywords</span></span>

<span data-ttu-id="294e1-3188">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="294e1-3189">Svezia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3190">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3190">Format</span></span>

<span data-ttu-id="294e1-3191">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3192">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3192">Pattern</span></span>

<span data-ttu-id="294e1-3193">Otto cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3194">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3194">Checksum</span></span>

<span data-ttu-id="294e1-3195">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3196">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3196">Definition</span></span>

<span data-ttu-id="294e1-3197">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3198">L'espressione regolare Regex_sweden_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3199">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-3199">One of the following is true:</span></span>
    - <span data-ttu-id="294e1-3200">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="294e1-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="294e1-3201">Viene trovata una parola chiave da Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="294e1-3201">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-3202">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="294e1-3203">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="294e1-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="294e1-3204">visa requirements</span><span class="sxs-lookup"><span data-stu-id="294e1-3204">visa requirements</span></span> 
- <span data-ttu-id="294e1-3205">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="294e1-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="294e1-3206">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="294e1-3206">Schengen visas</span></span> 
- <span data-ttu-id="294e1-3207">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="294e1-3207">Schengen visa</span></span> 
- <span data-ttu-id="294e1-3208">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="294e1-3208">Visa Processing</span></span> 
- <span data-ttu-id="294e1-3209">Visa Type</span><span class="sxs-lookup"><span data-stu-id="294e1-3209">Visa Type</span></span> 
- <span data-ttu-id="294e1-3210">Single Entry</span><span class="sxs-lookup"><span data-stu-id="294e1-3210">Single Entry</span></span> 
- <span data-ttu-id="294e1-3211">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="294e1-3211">Multiple Entry</span></span> 
- <span data-ttu-id="294e1-3212">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="294e1-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="294e1-3213">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="294e1-3213">Keyword_passport</span></span>

- <span data-ttu-id="294e1-3214">Passport Number</span><span class="sxs-lookup"><span data-stu-id="294e1-3214">Passport Number</span></span> 
- <span data-ttu-id="294e1-3215">Passport No</span><span class="sxs-lookup"><span data-stu-id="294e1-3215">Passport No</span></span> 
- <span data-ttu-id="294e1-3216">Passport#</span><span class="sxs-lookup"><span data-stu-id="294e1-3216">Passport #</span></span> 
- <span data-ttu-id="294e1-3217">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="294e1-3217">Passport#</span></span> 
- <span data-ttu-id="294e1-3218">PassportID</span><span class="sxs-lookup"><span data-stu-id="294e1-3218">PassportID</span></span> 
- <span data-ttu-id="294e1-3219">Passportno</span><span class="sxs-lookup"><span data-stu-id="294e1-3219">Passportno</span></span> 
- <span data-ttu-id="294e1-3220">passportnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-3220">passportnumber</span></span> 
- <span data-ttu-id="294e1-3221">パスポート</span><span class="sxs-lookup"><span data-stu-id="294e1-3221">パスポート</span></span> 
- <span data-ttu-id="294e1-3222">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="294e1-3222">パスポート番号</span></span> 
- <span data-ttu-id="294e1-3223">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="294e1-3223">パスポートのNum</span></span> 
- <span data-ttu-id="294e1-3224">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="294e1-3224">パスポート＃</span></span> 
- <span data-ttu-id="294e1-3225">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="294e1-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="294e1-3226">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="294e1-3226">Passeport n °</span></span> 
- <span data-ttu-id="294e1-3227">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="294e1-3227">Passeport Non</span></span> 
- <span data-ttu-id="294e1-3228">Passeport#</span><span class="sxs-lookup"><span data-stu-id="294e1-3228">Passeport #</span></span> 
- <span data-ttu-id="294e1-3229">Passeport #</span><span class="sxs-lookup"><span data-stu-id="294e1-3229">Passeport#</span></span> 
- <span data-ttu-id="294e1-3230">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="294e1-3230">PasseportNon</span></span> 
- <span data-ttu-id="294e1-3231">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="294e1-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="294e1-3232">Codice SWIFT</span><span class="sxs-lookup"><span data-stu-id="294e1-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3233">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3233">Format</span></span>

<span data-ttu-id="294e1-3234">Quattro lettere seguite da 5-31 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3235">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3235">Pattern</span></span>

<span data-ttu-id="294e1-3236">Quattro lettere seguite da 5-31 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="294e1-3237">Codice ABI di quattro cifre (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="294e1-3238">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="294e1-3238">An optional space</span></span> 
- <span data-ttu-id="294e1-3239">4-28 lettere o cifre (BBAN)</span><span class="sxs-lookup"><span data-stu-id="294e1-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="294e1-3240">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="294e1-3240">An optional space</span></span> 
- <span data-ttu-id="294e1-3241">1-3 lettere o cifre (resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="294e1-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3242">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3242">Checksum</span></span>

<span data-ttu-id="294e1-3243">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3244">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3244">Definition</span></span>

<span data-ttu-id="294e1-3245">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3246">L'espressione regolare Regex_swift restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3247">Viene trovata una parola chiave da Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="294e1-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3248">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="294e1-3249">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="294e1-3249">Keyword_swift</span></span>

- <span data-ttu-id="294e1-3250">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="294e1-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="294e1-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="294e1-3251">iso 9362</span></span> 
- <span data-ttu-id="294e1-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="294e1-3252">iso9362</span></span> 
- <span data-ttu-id="294e1-3253">Swift\#</span><span class="sxs-lookup"><span data-stu-id="294e1-3253">swift\#</span></span> 
- <span data-ttu-id="294e1-3254">swiftcode</span><span class="sxs-lookup"><span data-stu-id="294e1-3254">swiftcode</span></span> 
- <span data-ttu-id="294e1-3255">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-3255">swiftnumber</span></span> 
- <span data-ttu-id="294e1-3256">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="294e1-3257">swift code</span><span class="sxs-lookup"><span data-stu-id="294e1-3257">swift code</span></span> 
- <span data-ttu-id="294e1-3258">swift number #</span><span class="sxs-lookup"><span data-stu-id="294e1-3258">swift number #</span></span> 
- <span data-ttu-id="294e1-3259">swift routing number</span><span class="sxs-lookup"><span data-stu-id="294e1-3259">swift routing number</span></span> 
- <span data-ttu-id="294e1-3260">bic number</span><span class="sxs-lookup"><span data-stu-id="294e1-3260">bic number</span></span> 
- <span data-ttu-id="294e1-3261">bic code</span><span class="sxs-lookup"><span data-stu-id="294e1-3261">bic code</span></span> 
- <span data-ttu-id="294e1-3262">BIC\#</span><span class="sxs-lookup"><span data-stu-id="294e1-3262">bic \#</span></span> 
- <span data-ttu-id="294e1-3263">BIC\#</span><span class="sxs-lookup"><span data-stu-id="294e1-3263">bic\#</span></span> 
- <span data-ttu-id="294e1-3264">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="294e1-3264">bank identifier code</span></span> 
- <span data-ttu-id="294e1-3265">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="294e1-3265">標準化9362</span></span> 
- <span data-ttu-id="294e1-3266">迅速＃</span><span class="sxs-lookup"><span data-stu-id="294e1-3266">迅速＃</span></span> 
- <span data-ttu-id="294e1-3267">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="294e1-3267">SWIFTコード</span></span> 
- <span data-ttu-id="294e1-3268">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="294e1-3268">SWIFT番号</span></span> 
- <span data-ttu-id="294e1-3269">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="294e1-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="294e1-3270">BIC番号</span><span class="sxs-lookup"><span data-stu-id="294e1-3270">BIC番号</span></span> 
- <span data-ttu-id="294e1-3271">BICコード</span><span class="sxs-lookup"><span data-stu-id="294e1-3271">BICコード</span></span> 
- <span data-ttu-id="294e1-3272">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="294e1-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="294e1-3273">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="294e1-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="294e1-3274">rapide\#</span><span class="sxs-lookup"><span data-stu-id="294e1-3274">rapide \#</span></span> 
- <span data-ttu-id="294e1-3275">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="294e1-3275">code SWIFT</span></span> 
- <span data-ttu-id="294e1-3276">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="294e1-3276">le numéro de swift</span></span> 
- <span data-ttu-id="294e1-3277">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="294e1-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="294e1-3278">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="294e1-3278">le numéro BIC</span></span> 
- <span data-ttu-id="294e1-3279">\#BIC</span><span class="sxs-lookup"><span data-stu-id="294e1-3279">\# BIC</span></span> 
- <span data-ttu-id="294e1-3280">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="294e1-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="294e1-3281">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="294e1-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3282">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3282">Format</span></span>

<span data-ttu-id="294e1-3283">Una lettera (in lingua inglese) seguita da nove cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3284">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3284">Pattern</span></span>

<span data-ttu-id="294e1-3285">Una lettera (in lingua inglese) seguita da nove cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="294e1-3286">Una lettera (in inglese, senza distinzione tra tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="294e1-3287">La cifra "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="294e1-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="294e1-3288">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3289">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3289">Checksum</span></span>

<span data-ttu-id="294e1-3290">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3291">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3291">Definition</span></span>

<span data-ttu-id="294e1-3292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3293">La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3294">Viene trovata una parola chiave da Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="294e1-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="294e1-3295">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3296">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="294e1-3297">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="294e1-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="294e1-3298">身份證字號</span><span class="sxs-lookup"><span data-stu-id="294e1-3298">身份證字號</span></span> 
- <span data-ttu-id="294e1-3299">身份證</span><span class="sxs-lookup"><span data-stu-id="294e1-3299">身份證</span></span> 
- <span data-ttu-id="294e1-3300">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="294e1-3300">身份證號碼</span></span> 
- <span data-ttu-id="294e1-3301">身份證號</span><span class="sxs-lookup"><span data-stu-id="294e1-3301">身份證號</span></span> 
- <span data-ttu-id="294e1-3302">身分證字號</span><span class="sxs-lookup"><span data-stu-id="294e1-3302">身分證字號</span></span> 
- <span data-ttu-id="294e1-3303">身分證</span><span class="sxs-lookup"><span data-stu-id="294e1-3303">身分證</span></span> 
- <span data-ttu-id="294e1-3304">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="294e1-3304">身分證號碼</span></span> 
- <span data-ttu-id="294e1-3305">身份證號</span><span class="sxs-lookup"><span data-stu-id="294e1-3305">身份證號</span></span> 
- <span data-ttu-id="294e1-3306">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="294e1-3306">身分證統一編號</span></span> 
- <span data-ttu-id="294e1-3307">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="294e1-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="294e1-3308">簽名</span><span class="sxs-lookup"><span data-stu-id="294e1-3308">簽名</span></span> 
- <span data-ttu-id="294e1-3309">蓋章</span><span class="sxs-lookup"><span data-stu-id="294e1-3309">蓋章</span></span> 
- <span data-ttu-id="294e1-3310">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="294e1-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="294e1-3311">簽章</span><span class="sxs-lookup"><span data-stu-id="294e1-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="294e1-3312">	Taiwan - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3313">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3313">Format</span></span>

- <span data-ttu-id="294e1-3314">Numero di passaporto biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="294e1-3315">Numero di passaporto non biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3316">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3316">Pattern</span></span>
<span data-ttu-id="294e1-3317">Numero di passaporto biometrico:</span><span class="sxs-lookup"><span data-stu-id="294e1-3317">Biometric passport number:</span></span>
- <span data-ttu-id="294e1-3318">La cifra "3" </span><span class="sxs-lookup"><span data-stu-id="294e1-3318">The digit "3"</span></span> 
- <span data-ttu-id="294e1-3319">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3319">Eight digits</span></span>

<span data-ttu-id="294e1-3320">Numero di passaporto non biometrico:</span><span class="sxs-lookup"><span data-stu-id="294e1-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="294e1-3321">9 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3322">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3322">Checksum</span></span>

<span data-ttu-id="294e1-3323">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3324">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3324">Definition</span></span>

<span data-ttu-id="294e1-3325">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3326">L'espressione regolare Regex_taiwan_passport trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3327">Viene trovata una parola chiave da Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="294e1-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3328">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="294e1-3329">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="294e1-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="294e1-3330">Numero passaporto ROC</span><span class="sxs-lookup"><span data-stu-id="294e1-3330">ROC passport number</span></span> 
- <span data-ttu-id="294e1-3331">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-3331">Passport number</span></span> 
- <span data-ttu-id="294e1-3332">N° passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-3332">Passport no</span></span> 
- <span data-ttu-id="294e1-3333">Num. passaporto
</span><span class="sxs-lookup"><span data-stu-id="294e1-3333">Passport Num</span></span> 
- <span data-ttu-id="294e1-3334">Passport #</span><span class="sxs-lookup"><span data-stu-id="294e1-3334">Passport #</span></span> 
- <span data-ttu-id="294e1-3335">护照</span><span class="sxs-lookup"><span data-stu-id="294e1-3335">护照</span></span> 
- <span data-ttu-id="294e1-3336">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="294e1-3336">中華民國護照</span></span> 
- <span data-ttu-id="294e1-3337">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="294e1-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="294e1-3338">Taiwan - Numero certificato di residenza (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="294e1-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3339">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3339">Format</span></span>

<span data-ttu-id="294e1-3340">10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3341">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3341">Pattern</span></span>

<span data-ttu-id="294e1-3342">10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-3342">10 letters and digits:</span></span>
- <span data-ttu-id="294e1-3343">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="294e1-3344">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3345">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3345">Checksum</span></span>

<span data-ttu-id="294e1-3346">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3347">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3347">Definition</span></span>

<span data-ttu-id="294e1-3348">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3349">L'espressione regolare Regex_taiwan_resident_certificate trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3350">Viene trovata una parola chiave da Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="294e1-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3351">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="294e1-3352">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="294e1-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="294e1-3353">Certificato di residenza</span><span class="sxs-lookup"><span data-stu-id="294e1-3353">Resident Certificate</span></span> 
- <span data-ttu-id="294e1-3354">Cert. di resid
</span><span class="sxs-lookup"><span data-stu-id="294e1-3354">Resident Cert</span></span> 
- <span data-ttu-id="294e1-3355">Cert. di resid.
</span><span class="sxs-lookup"><span data-stu-id="294e1-3355">Resident Cert.</span></span> 
- <span data-ttu-id="294e1-3356">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="294e1-3356">Identification card</span></span> 
- <span data-ttu-id="294e1-3357">Certificato residente straniero</span><span class="sxs-lookup"><span data-stu-id="294e1-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="294e1-3358">ARCO</span><span class="sxs-lookup"><span data-stu-id="294e1-3358">ARC</span></span> 
- <span data-ttu-id="294e1-3359">Certificato residente nell’area di Taiwan</span><span class="sxs-lookup"><span data-stu-id="294e1-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="294e1-3360">TARC Tax</span><span class="sxs-lookup"><span data-stu-id="294e1-3360">TARC</span></span> 
- <span data-ttu-id="294e1-3361">居留證</span><span class="sxs-lookup"><span data-stu-id="294e1-3361">居留證</span></span> 
- <span data-ttu-id="294e1-3362">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="294e1-3362">外僑居留證</span></span> 
- <span data-ttu-id="294e1-3363">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="294e1-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="294e1-3364">Codice di identificazione della popolazione tailandese</span><span class="sxs-lookup"><span data-stu-id="294e1-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3365">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3365">Format</span></span>

<span data-ttu-id="294e1-3366">13 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3367">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3367">Pattern</span></span>

<span data-ttu-id="294e1-3368">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-3368">13 digits:</span></span>
- <span data-ttu-id="294e1-3369">La prima cifra non è 0 o 9</span><span class="sxs-lookup"><span data-stu-id="294e1-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="294e1-3370">12 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3371">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3371">Checksum</span></span>

<span data-ttu-id="294e1-3372">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3373">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3373">Definition</span></span>

<span data-ttu-id="294e1-3374">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3375">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3376">Viene trovata una parola chiave da Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="294e1-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="294e1-3377">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3378">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-3379">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="294e1-3380">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="294e1-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="294e1-3381">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="294e1-3381">ID Number</span></span>
- <span data-ttu-id="294e1-3382">Numero di identificazione</span><span class="sxs-lookup"><span data-stu-id="294e1-3382">Identification Number</span></span>
- <span data-ttu-id="294e1-3383">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="294e1-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="294e1-3384">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="294e1-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="294e1-3385">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="294e1-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="294e1-3386">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="294e1-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="294e1-3387">Numero di identificazione nazionale turco</span><span class="sxs-lookup"><span data-stu-id="294e1-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3388">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3388">Format</span></span>

<span data-ttu-id="294e1-3389">11 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3390">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3390">Pattern</span></span>

<span data-ttu-id="294e1-3391">11 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3392">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3392">Checksum</span></span>

<span data-ttu-id="294e1-3393">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3394">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3394">Definition</span></span>

<span data-ttu-id="294e1-3395">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3396">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3397">Viene trovata una parola chiave da Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="294e1-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="294e1-3398">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3399">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-3400">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="294e1-3401">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="294e1-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="294e1-3402">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="294e1-3402">TC Kimlik No</span></span>
- <span data-ttu-id="294e1-3403">Numarası Kimlik TC</span><span class="sxs-lookup"><span data-stu-id="294e1-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="294e1-3404">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="294e1-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="294e1-3405">Vatandaşlık No</span><span class="sxs-lookup"><span data-stu-id="294e1-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="294e1-p144">Regno Unito - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="294e1-p144">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3408">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3408">Format</span></span>

<span data-ttu-id="294e1-3409">Combinazione di 18 lettere e numeri nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="294e1-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3410">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3410">Pattern</span></span>

<span data-ttu-id="294e1-3411">18 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-3411">18 letters and digits:</span></span>
- <span data-ttu-id="294e1-3412">Cinque lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="294e1-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="294e1-3413">Una cifra</span><span class="sxs-lookup"><span data-stu-id="294e1-3413">One digit</span></span> 
- <span data-ttu-id="294e1-3414">5 cifre nel formato data GGMMA relativo alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-3414">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="294e1-3415">Due lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="294e1-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="294e1-3416">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3417">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3417">Checksum</span></span>

<span data-ttu-id="294e1-3418">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3419">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3419">Definition</span></span>

<span data-ttu-id="294e1-3420">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3421">La funzione Func_uk_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3422">Viene trovata una parola chiave da Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="294e1-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="294e1-3423">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3424">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="294e1-3425">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="294e1-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="294e1-3426">DVLA</span><span class="sxs-lookup"><span data-stu-id="294e1-3426">DVLA</span></span> 
- <span data-ttu-id="294e1-3427">light vans</span><span class="sxs-lookup"><span data-stu-id="294e1-3427">light vans</span></span> 
- <span data-ttu-id="294e1-3428">quadbikes</span><span class="sxs-lookup"><span data-stu-id="294e1-3428">quadbikes</span></span> 
- <span data-ttu-id="294e1-3429">motor cars</span><span class="sxs-lookup"><span data-stu-id="294e1-3429">motor cars</span></span> 
- <span data-ttu-id="294e1-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="294e1-3430">125cc</span></span> 
- <span data-ttu-id="294e1-3431">sidecar</span><span class="sxs-lookup"><span data-stu-id="294e1-3431">sidecar</span></span> 
- <span data-ttu-id="294e1-3432">tricicli</span><span class="sxs-lookup"><span data-stu-id="294e1-3432">tricycles</span></span> 
- <span data-ttu-id="294e1-3433">moto</span><span class="sxs-lookup"><span data-stu-id="294e1-3433">motorcycles</span></span> 
- <span data-ttu-id="294e1-3434">photocard licence</span><span class="sxs-lookup"><span data-stu-id="294e1-3434">photocard licence</span></span> 
- <span data-ttu-id="294e1-3435">learner drivers</span><span class="sxs-lookup"><span data-stu-id="294e1-3435">learner drivers</span></span> 
- <span data-ttu-id="294e1-3436">licence holder</span><span class="sxs-lookup"><span data-stu-id="294e1-3436">licence holder</span></span> 
- <span data-ttu-id="294e1-3437">licence holders</span><span class="sxs-lookup"><span data-stu-id="294e1-3437">licence holders</span></span> 
- <span data-ttu-id="294e1-3438">driving licences</span><span class="sxs-lookup"><span data-stu-id="294e1-3438">driving licences</span></span> 
- <span data-ttu-id="294e1-3439">driving licence</span><span class="sxs-lookup"><span data-stu-id="294e1-3439">driving licence</span></span> 
- <span data-ttu-id="294e1-3440">dual control car</span><span class="sxs-lookup"><span data-stu-id="294e1-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="294e1-p145">Regno Unito - Numero di iscrizione alle liste elettorali</span><span class="sxs-lookup"><span data-stu-id="294e1-p145">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3443">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3443">Format</span></span>

<span data-ttu-id="294e1-3444">Due lettere seguite da 1-4 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3445">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3445">Pattern</span></span>

<span data-ttu-id="294e1-3446">Due lettere (senza distinzione fra maiuscole/minuscole) seguite da 1-4 numeri</span><span class="sxs-lookup"><span data-stu-id="294e1-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3447">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3447">Checksum</span></span>

<span data-ttu-id="294e1-3448">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3449">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3449">Definition</span></span>

<span data-ttu-id="294e1-3450">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3451">L'espressione regolare Regex_uk_electoral restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3452">Viene trovata una parola chiave da Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="294e1-3452">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-3453">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="294e1-3454">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="294e1-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="294e1-3455">council nomination</span><span class="sxs-lookup"><span data-stu-id="294e1-3455">council nomination</span></span> 
- <span data-ttu-id="294e1-3456">nomination form</span><span class="sxs-lookup"><span data-stu-id="294e1-3456">nomination form</span></span> 
- <span data-ttu-id="294e1-3457">electoral register</span><span class="sxs-lookup"><span data-stu-id="294e1-3457">electoral register</span></span> 
- <span data-ttu-id="294e1-3458">electoral roll</span><span class="sxs-lookup"><span data-stu-id="294e1-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="294e1-p146">Regno Unito - Codice del servizio sanitario nazionale</span><span class="sxs-lookup"><span data-stu-id="294e1-p146">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3461">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3461">Format</span></span>

<span data-ttu-id="294e1-3462">10-17 cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="294e1-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3463">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3463">Pattern</span></span>

<span data-ttu-id="294e1-3464">10-17 cifre:</span><span class="sxs-lookup"><span data-stu-id="294e1-3464">10-17 digits:</span></span>
- <span data-ttu-id="294e1-3465">3 o 10 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="294e1-3466">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="294e1-3466">A space</span></span> 
- <span data-ttu-id="294e1-3467">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3467">Three digits</span></span> 
- <span data-ttu-id="294e1-3468">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="294e1-3468">A space</span></span> 
- <span data-ttu-id="294e1-3469">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3470">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3470">Checksum</span></span>

<span data-ttu-id="294e1-3471">Sì</span><span class="sxs-lookup"><span data-stu-id="294e1-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3472">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3472">Definition</span></span>

<span data-ttu-id="294e1-3473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3474">La funzione Func_uk_nhs_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3475">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-3475">One of the following is true:</span></span>
    - <span data-ttu-id="294e1-3476">Viene trovata una parola chiave da Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="294e1-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="294e1-3477">Viene trovata una parola chiave da Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="294e1-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="294e1-3478">Viene trovata una parola chiave da Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="294e1-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="294e1-3479">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="294e1-3479">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-3480">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="294e1-3481">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="294e1-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="294e1-3482">national health service</span><span class="sxs-lookup"><span data-stu-id="294e1-3482">national health service</span></span> 
- <span data-ttu-id="294e1-3483">NHS</span><span class="sxs-lookup"><span data-stu-id="294e1-3483">nhs</span></span> 
- <span data-ttu-id="294e1-3484">health services authority</span><span class="sxs-lookup"><span data-stu-id="294e1-3484">health services authority</span></span> 
- <span data-ttu-id="294e1-3485">health authority</span><span class="sxs-lookup"><span data-stu-id="294e1-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="294e1-3486">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="294e1-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="294e1-3487">patient id</span><span class="sxs-lookup"><span data-stu-id="294e1-3487">patient id</span></span> 
- <span data-ttu-id="294e1-3488">patient identification</span><span class="sxs-lookup"><span data-stu-id="294e1-3488">patient identification</span></span> 
- <span data-ttu-id="294e1-3489">patient no</span><span class="sxs-lookup"><span data-stu-id="294e1-3489">patient no</span></span> 
- <span data-ttu-id="294e1-3490">patient number</span><span class="sxs-lookup"><span data-stu-id="294e1-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="294e1-3491">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="294e1-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="294e1-3492">GP</span><span class="sxs-lookup"><span data-stu-id="294e1-3492">GP</span></span> 
- <span data-ttu-id="294e1-3493">DOB</span><span class="sxs-lookup"><span data-stu-id="294e1-3493">DOB</span></span> 
- <span data-ttu-id="294e1-3494">D. O. B</span><span class="sxs-lookup"><span data-stu-id="294e1-3494">D.O.B</span></span> 
- <span data-ttu-id="294e1-3495">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="294e1-3495">Date of Birth</span></span> 
- <span data-ttu-id="294e1-3496">Birth Date</span><span class="sxs-lookup"><span data-stu-id="294e1-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="294e1-p147">Regno Unito - Numero di assicurazione nazionale (NINO)</span><span class="sxs-lookup"><span data-stu-id="294e1-p147">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3499">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3499">Format</span></span>

<span data-ttu-id="294e1-3500">7 caratteri o 9 caratteri separati da spazi o trattini</span><span class="sxs-lookup"><span data-stu-id="294e1-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3501">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3501">Pattern</span></span>

<span data-ttu-id="294e1-3502">Due modelli possibili:</span><span class="sxs-lookup"><span data-stu-id="294e1-3502">Two possible patterns:</span></span>

- <span data-ttu-id="294e1-3503">Due lettere (NINOs valido utilizza solo alcuni caratteri in questo prefisso, che questo modello convalida; senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="294e1-3504">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3504">Six digits</span></span>
- <span data-ttu-id="294e1-3505">' A ',' B ',' c'o ' d'(come il prefisso, solo alcuni caratteri sono consentiti nel suffisso, senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="294e1-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="294e1-3506">O</span><span class="sxs-lookup"><span data-stu-id="294e1-3506">OR</span></span>

- <span data-ttu-id="294e1-3507">Due lettere</span><span class="sxs-lookup"><span data-stu-id="294e1-3507">Two letters</span></span>
- <span data-ttu-id="294e1-3508">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-3508">A space or dash</span></span>
- <span data-ttu-id="294e1-3509">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3509">Two digits</span></span>
- <span data-ttu-id="294e1-3510">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-3510">A space or dash</span></span>
- <span data-ttu-id="294e1-3511">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3511">Two digits</span></span>
- <span data-ttu-id="294e1-3512">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-3512">A space or dash</span></span>
- <span data-ttu-id="294e1-3513">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3513">Two digits</span></span>
- <span data-ttu-id="294e1-3514">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-3514">A space or dash</span></span>
- <span data-ttu-id="294e1-3515">' A ',' B ',' c'o ' d'</span><span class="sxs-lookup"><span data-stu-id="294e1-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3516">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3516">Checksum</span></span>

<span data-ttu-id="294e1-3517">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3518">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3518">Definition</span></span>

<span data-ttu-id="294e1-3519">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3520">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3521">Viene trovata una parola chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="294e1-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="294e1-3522">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3523">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3524">Non vengono trovate parole chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="294e1-3524">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-3525">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="294e1-3526">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="294e1-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="294e1-3527">national insurance number</span><span class="sxs-lookup"><span data-stu-id="294e1-3527">national insurance number</span></span> 
- <span data-ttu-id="294e1-3528">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="294e1-3528">national insurance contributions</span></span> 
- <span data-ttu-id="294e1-3529">protection act</span><span class="sxs-lookup"><span data-stu-id="294e1-3529">protection act</span></span> 
- <span data-ttu-id="294e1-3530">Insurance</span><span class="sxs-lookup"><span data-stu-id="294e1-3530">insurance</span></span> 
- <span data-ttu-id="294e1-3531">social security number</span><span class="sxs-lookup"><span data-stu-id="294e1-3531">social security number</span></span> 
- <span data-ttu-id="294e1-3532">insurance application</span><span class="sxs-lookup"><span data-stu-id="294e1-3532">insurance application</span></span> 
- <span data-ttu-id="294e1-3533">medical application</span><span class="sxs-lookup"><span data-stu-id="294e1-3533">medical application</span></span> 
- <span data-ttu-id="294e1-3534">social insurance</span><span class="sxs-lookup"><span data-stu-id="294e1-3534">social insurance</span></span> 
- <span data-ttu-id="294e1-3535">medical attention</span><span class="sxs-lookup"><span data-stu-id="294e1-3535">medical attention</span></span> 
- <span data-ttu-id="294e1-3536">social security</span><span class="sxs-lookup"><span data-stu-id="294e1-3536">social security</span></span> 
- <span data-ttu-id="294e1-3537">great britain</span><span class="sxs-lookup"><span data-stu-id="294e1-3537">great britain</span></span> 
- <span data-ttu-id="294e1-3538">Insurance</span><span class="sxs-lookup"><span data-stu-id="294e1-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="294e1-p148">Stati Uniti/Regno Unito - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="294e1-p148">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3541">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3541">Format</span></span>

<span data-ttu-id="294e1-3542">9 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3543">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3543">Pattern</span></span>

<span data-ttu-id="294e1-3544">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3545">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3545">Checksum</span></span>

<span data-ttu-id="294e1-3546">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3547">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3547">Definition</span></span>

<span data-ttu-id="294e1-3548">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3549">La funzione Func_usa_uk_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3550">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="294e1-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3551">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="294e1-3552">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="294e1-3552">Keyword_passport</span></span>

- <span data-ttu-id="294e1-3553">Passport Number</span><span class="sxs-lookup"><span data-stu-id="294e1-3553">Passport Number</span></span> 
- <span data-ttu-id="294e1-3554">Passport No</span><span class="sxs-lookup"><span data-stu-id="294e1-3554">Passport No</span></span> 
- <span data-ttu-id="294e1-3555">Passport#</span><span class="sxs-lookup"><span data-stu-id="294e1-3555">Passport #</span></span> 
- <span data-ttu-id="294e1-3556">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="294e1-3556">Passport#</span></span> 
- <span data-ttu-id="294e1-3557">PassportID</span><span class="sxs-lookup"><span data-stu-id="294e1-3557">PassportID</span></span> 
- <span data-ttu-id="294e1-3558">Passportno</span><span class="sxs-lookup"><span data-stu-id="294e1-3558">Passportno</span></span> 
- <span data-ttu-id="294e1-3559">passportnumber</span><span class="sxs-lookup"><span data-stu-id="294e1-3559">passportnumber</span></span> 
- <span data-ttu-id="294e1-3560">パスポート</span><span class="sxs-lookup"><span data-stu-id="294e1-3560">パスポート</span></span> 
- <span data-ttu-id="294e1-3561">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="294e1-3561">パスポート番号</span></span> 
- <span data-ttu-id="294e1-3562">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="294e1-3562">パスポートのNum</span></span> 
- <span data-ttu-id="294e1-3563">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="294e1-3563">パスポート＃</span></span> 
- <span data-ttu-id="294e1-3564">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="294e1-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="294e1-3565">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="294e1-3565">Passeport n °</span></span> 
- <span data-ttu-id="294e1-3566">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="294e1-3566">Passeport Non</span></span> 
- <span data-ttu-id="294e1-3567">Passeport#</span><span class="sxs-lookup"><span data-stu-id="294e1-3567">Passeport #</span></span> 
- <span data-ttu-id="294e1-3568">Passeport #</span><span class="sxs-lookup"><span data-stu-id="294e1-3568">Passeport#</span></span> 
- <span data-ttu-id="294e1-3569">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="294e1-3569">PasseportNon</span></span> 
- <span data-ttu-id="294e1-3570">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="294e1-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="294e1-3571">Stati Uniti - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="294e1-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3572">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3572">Format</span></span>

<span data-ttu-id="294e1-3573">8-17 cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3574">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3574">Pattern</span></span>

<span data-ttu-id="294e1-3575">8-17 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="294e1-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3576">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3576">Checksum</span></span>

<span data-ttu-id="294e1-3577">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3578">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3578">Definition</span></span>

<span data-ttu-id="294e1-3579">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3580">L'espressione regolare Regex_usa_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3581">Viene trovata una parola chiave da Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="294e1-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3582">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="294e1-3583">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="294e1-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="294e1-3584">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="294e1-3584">Checking Account Number</span></span> 
- <span data-ttu-id="294e1-3585">Checking Account</span><span class="sxs-lookup"><span data-stu-id="294e1-3585">Checking Account</span></span> 
- <span data-ttu-id="294e1-3586">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="294e1-3586">Checking Account #</span></span> 
- <span data-ttu-id="294e1-3587">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="294e1-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="294e1-3588">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="294e1-3588">Checking Acct #</span></span> 
- <span data-ttu-id="294e1-3589">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="294e1-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="294e1-3590">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="294e1-3590">Checking Account No.</span></span> 
- <span data-ttu-id="294e1-3591">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="294e1-3591">Bank Account Number</span></span> 
- <span data-ttu-id="294e1-3592">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="294e1-3592">Bank Account #</span></span> 
- <span data-ttu-id="294e1-3593">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="294e1-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="294e1-3594">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="294e1-3594">Bank Acct #</span></span> 
- <span data-ttu-id="294e1-3595">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="294e1-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="294e1-3596">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="294e1-3596">Bank Account No.</span></span> 
- <span data-ttu-id="294e1-3597">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="294e1-3597">Savings Account Number</span></span> 
- <span data-ttu-id="294e1-3598">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="294e1-3598">Savings Account.</span></span> 
- <span data-ttu-id="294e1-3599">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="294e1-3599">Savings Account #</span></span> 
- <span data-ttu-id="294e1-3600">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="294e1-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="294e1-3601">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="294e1-3601">Savings Acct #</span></span> 
- <span data-ttu-id="294e1-3602">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="294e1-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="294e1-3603">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="294e1-3603">Savings Account No.</span></span> 
- <span data-ttu-id="294e1-3604">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="294e1-3604">Debit Account Number</span></span> 
- <span data-ttu-id="294e1-3605">Debit Account</span><span class="sxs-lookup"><span data-stu-id="294e1-3605">Debit Account</span></span> 
- <span data-ttu-id="294e1-3606">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="294e1-3606">Debit Account #</span></span> 
- <span data-ttu-id="294e1-3607">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="294e1-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="294e1-3608">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="294e1-3608">Debit Acct #</span></span> 
- <span data-ttu-id="294e1-3609">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="294e1-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="294e1-3610">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="294e1-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="294e1-3611">Stati Uniti - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="294e1-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3612">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3612">Format</span></span>

<span data-ttu-id="294e1-3613">Varia in base allo stato</span><span class="sxs-lookup"><span data-stu-id="294e1-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3614">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3614">Pattern</span></span>

<span data-ttu-id="294e1-3615">Varia in base allo stato. Ad esempio, per New York:</span><span class="sxs-lookup"><span data-stu-id="294e1-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="294e1-3616">Nove cifre formattate come ddd ddd ddd corrisponderanno.</span><span class="sxs-lookup"><span data-stu-id="294e1-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="294e1-3617">Nove cifre come ddddddddd non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="294e1-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3618">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3618">Checksum</span></span>

<span data-ttu-id="294e1-3619">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3620">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3620">Definition</span></span>

<span data-ttu-id="294e1-3621">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3622">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3623">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="294e1-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="294e1-3624">Viene trovata una parola chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="294e1-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="294e1-3625">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3626">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3627">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="294e1-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="294e1-3628">Viene trovata una parola chiave da Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="294e1-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="294e1-3629">Non vengono trovate parole chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="294e1-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
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
```

### <a name="keywords"></a><span data-ttu-id="294e1-3630">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="294e1-3631">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="294e1-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="294e1-3632">DL</span><span class="sxs-lookup"><span data-stu-id="294e1-3632">DL</span></span> 
- <span data-ttu-id="294e1-3633">DLS</span><span class="sxs-lookup"><span data-stu-id="294e1-3633">DLS</span></span> 
- <span data-ttu-id="294e1-3634">CDL</span><span class="sxs-lookup"><span data-stu-id="294e1-3634">CDL</span></span> 
- <span data-ttu-id="294e1-3635">CDLS</span><span class="sxs-lookup"><span data-stu-id="294e1-3635">CDLS</span></span> 
- <span data-ttu-id="294e1-3636">ID</span><span class="sxs-lookup"><span data-stu-id="294e1-3636">ID</span></span> 
- <span data-ttu-id="294e1-3637">ID</span><span class="sxs-lookup"><span data-stu-id="294e1-3637">IDs</span></span> 
- <span data-ttu-id="294e1-3638">DL #</span><span class="sxs-lookup"><span data-stu-id="294e1-3638">DL#</span></span> 
- <span data-ttu-id="294e1-3639">DLS #</span><span class="sxs-lookup"><span data-stu-id="294e1-3639">DLS#</span></span> 
- <span data-ttu-id="294e1-3640">CDL #</span><span class="sxs-lookup"><span data-stu-id="294e1-3640">CDL#</span></span> 
- <span data-ttu-id="294e1-3641">CDLS #</span><span class="sxs-lookup"><span data-stu-id="294e1-3641">CDLS#</span></span> 
- <span data-ttu-id="294e1-3642">ID #</span><span class="sxs-lookup"><span data-stu-id="294e1-3642">ID#</span></span>
- <span data-ttu-id="294e1-3643">ID #</span><span class="sxs-lookup"><span data-stu-id="294e1-3643">IDs#</span></span> 
- <span data-ttu-id="294e1-3644">ID number</span><span class="sxs-lookup"><span data-stu-id="294e1-3644">ID number</span></span> 
- <span data-ttu-id="294e1-3645">ID numbers</span><span class="sxs-lookup"><span data-stu-id="294e1-3645">ID numbers</span></span> 
- <span data-ttu-id="294e1-3646">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="294e1-3646">LIC</span></span> 
- <span data-ttu-id="294e1-3647">DRIVER'LIC #</span><span class="sxs-lookup"><span data-stu-id="294e1-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="294e1-3648">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="294e1-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="294e1-3649">DriverLic</span><span class="sxs-lookup"><span data-stu-id="294e1-3649">DriverLic</span></span> 
- <span data-ttu-id="294e1-3650">DriverLics</span><span class="sxs-lookup"><span data-stu-id="294e1-3650">DriverLics</span></span> 
- <span data-ttu-id="294e1-3651">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="294e1-3651">DriverLicense</span></span> 
- <span data-ttu-id="294e1-3652">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="294e1-3652">DriverLicenses</span></span> 
- <span data-ttu-id="294e1-3653">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-3653">Driver Lic</span></span> 
- <span data-ttu-id="294e1-3654">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="294e1-3654">Driver Lics</span></span> 
- <span data-ttu-id="294e1-3655">Driver License</span><span class="sxs-lookup"><span data-stu-id="294e1-3655">Driver License</span></span> 
- <span data-ttu-id="294e1-3656">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-3656">Driver Licenses</span></span> 
- <span data-ttu-id="294e1-3657">DriversLic</span><span class="sxs-lookup"><span data-stu-id="294e1-3657">DriversLic</span></span> 
- <span data-ttu-id="294e1-3658">DriversLics</span><span class="sxs-lookup"><span data-stu-id="294e1-3658">DriversLics</span></span> 
- <span data-ttu-id="294e1-3659">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="294e1-3659">DriversLicense</span></span> 
- <span data-ttu-id="294e1-3660">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="294e1-3660">DriversLicenses</span></span> 
- <span data-ttu-id="294e1-3661">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-3661">Drivers Lic</span></span> 
- <span data-ttu-id="294e1-3662">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="294e1-3662">Drivers Lics</span></span> 
- <span data-ttu-id="294e1-3663">Drivers License</span><span class="sxs-lookup"><span data-stu-id="294e1-3663">Drivers License</span></span> 
- <span data-ttu-id="294e1-3664">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="294e1-3665">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-3665">Driver'Lic</span></span> 
- <span data-ttu-id="294e1-3666">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="294e1-3666">Driver'Lics</span></span> 
- <span data-ttu-id="294e1-3667">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="294e1-3667">Driver'License</span></span> 
- <span data-ttu-id="294e1-3668">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="294e1-3669">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-3669">Driver' Lic</span></span> 
- <span data-ttu-id="294e1-3670">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="294e1-3670">Driver' Lics</span></span> 
- <span data-ttu-id="294e1-3671">Driver' License</span><span class="sxs-lookup"><span data-stu-id="294e1-3671">Driver' License</span></span> 
- <span data-ttu-id="294e1-3672">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-3672">Driver' Licenses</span></span>
- <span data-ttu-id="294e1-3673">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="294e1-3673">Driver'sLic</span></span> 
- <span data-ttu-id="294e1-3674">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="294e1-3674">Driver'sLics</span></span> 
- <span data-ttu-id="294e1-3675">Secondola</span><span class="sxs-lookup"><span data-stu-id="294e1-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="294e1-3676">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="294e1-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="294e1-3677">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="294e1-3677">Driver's Lic</span></span> 
- <span data-ttu-id="294e1-3678">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="294e1-3678">Driver's Lics</span></span> 
- <span data-ttu-id="294e1-3679">Driver's License</span><span class="sxs-lookup"><span data-stu-id="294e1-3679">Driver's License</span></span> 
- <span data-ttu-id="294e1-3680">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="294e1-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="294e1-3681">identification number</span><span class="sxs-lookup"><span data-stu-id="294e1-3681">identification number</span></span> 
- <span data-ttu-id="294e1-3682">identification numbers</span><span class="sxs-lookup"><span data-stu-id="294e1-3682">identification numbers</span></span> 
- <span data-ttu-id="294e1-3683">identification#</span><span class="sxs-lookup"><span data-stu-id="294e1-3683">identification #</span></span> 
- <span data-ttu-id="294e1-3684">id card</span><span class="sxs-lookup"><span data-stu-id="294e1-3684">id card</span></span> 
- <span data-ttu-id="294e1-3685">id cards</span><span class="sxs-lookup"><span data-stu-id="294e1-3685">id cards</span></span> 
- <span data-ttu-id="294e1-3686">identification card</span><span class="sxs-lookup"><span data-stu-id="294e1-3686">identification card</span></span> 
- <span data-ttu-id="294e1-3687">identification cards</span><span class="sxs-lookup"><span data-stu-id="294e1-3687">identification cards</span></span> 
- <span data-ttu-id="294e1-3688">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="294e1-3688">DriverLic#</span></span> 
- <span data-ttu-id="294e1-3689">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="294e1-3689">DriverLics#</span></span> 
- <span data-ttu-id="294e1-3690">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="294e1-3690">DriverLicense#</span></span> 
- <span data-ttu-id="294e1-3691">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="294e1-3692">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-3692">Driver Lic#</span></span> 
- <span data-ttu-id="294e1-3693">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-3693">Driver Lics#</span></span> 
- <span data-ttu-id="294e1-3694">Driver License#</span><span class="sxs-lookup"><span data-stu-id="294e1-3694">Driver License#</span></span> 
- <span data-ttu-id="294e1-3695">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="294e1-3696">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="294e1-3696">DriversLic#</span></span> 
- <span data-ttu-id="294e1-3697">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="294e1-3697">DriversLics#</span></span> 
- <span data-ttu-id="294e1-3698">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="294e1-3698">DriversLicense#</span></span> 
- <span data-ttu-id="294e1-3699">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="294e1-3700">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="294e1-3701">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="294e1-3702">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="294e1-3702">Drivers License#</span></span> 
- <span data-ttu-id="294e1-3703">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="294e1-3704">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="294e1-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="294e1-3705">Driver ' LiCS #</span><span class="sxs-lookup"><span data-stu-id="294e1-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="294e1-3706">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="294e1-3706">Driver'License#</span></span> 
- <span data-ttu-id="294e1-3707">Driver ' licenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="294e1-3708">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="294e1-3709">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="294e1-3710">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="294e1-3710">Driver' License#</span></span> 
- <span data-ttu-id="294e1-3711">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="294e1-3712">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="294e1-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="294e1-3713">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="294e1-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="294e1-3714">Secondola #</span><span class="sxs-lookup"><span data-stu-id="294e1-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="294e1-3715">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="294e1-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="294e1-3716">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="294e1-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="294e1-3717">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="294e1-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="294e1-3718">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="294e1-3718">Driver's License#</span></span> 
- <span data-ttu-id="294e1-3719">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="294e1-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="294e1-3720">id card#</span><span class="sxs-lookup"><span data-stu-id="294e1-3720">id card#</span></span> 
- <span data-ttu-id="294e1-3721">id cards#</span><span class="sxs-lookup"><span data-stu-id="294e1-3721">id cards#</span></span> 
- <span data-ttu-id="294e1-3722">identification card#</span><span class="sxs-lookup"><span data-stu-id="294e1-3722">identification card#</span></span> 
- <span data-ttu-id="294e1-3723">identification cards#</span><span class="sxs-lookup"><span data-stu-id="294e1-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="294e1-3724">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="294e1-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="294e1-3725">Abbreviazione dello stato (ad esempio, "NY")</span><span class="sxs-lookup"><span data-stu-id="294e1-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="294e1-3726">Nome dello stato (ad esempio, "New York")</span><span class="sxs-lookup"><span data-stu-id="294e1-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="294e1-3727">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="294e1-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3728">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3728">Format</span></span>

<span data-ttu-id="294e1-3729">Nove cifre che iniziano con "9" e contengono un "7" o un "8" come quarta cifra. Può essere formattato con spazi e trattini (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="294e1-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3730">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3730">Pattern</span></span>

<span data-ttu-id="294e1-3731">Formattato</span><span class="sxs-lookup"><span data-stu-id="294e1-3731">Formatted:</span></span>
- <span data-ttu-id="294e1-3732">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="294e1-3732">The digit "9"</span></span> 
- <span data-ttu-id="294e1-3733">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3733">Two digits</span></span> 
- <span data-ttu-id="294e1-3734">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-3734">A space or dash</span></span> 
- <span data-ttu-id="294e1-3735">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="294e1-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="294e1-3736">Una cifra</span><span class="sxs-lookup"><span data-stu-id="294e1-3736">A digit</span></span> 
- <span data-ttu-id="294e1-3737">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="294e1-3737">A space, or dash</span></span> 
- <span data-ttu-id="294e1-3738">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3738">Four digits</span></span>

<span data-ttu-id="294e1-3739">Formattato</span><span class="sxs-lookup"><span data-stu-id="294e1-3739">Unformatted:</span></span>
- <span data-ttu-id="294e1-3740">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="294e1-3740">The digit "9"</span></span> 
- <span data-ttu-id="294e1-3741">Due cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3741">Two digits</span></span> 
- <span data-ttu-id="294e1-3742">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="294e1-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="294e1-3743">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="294e1-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3744">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3744">Checksum</span></span>

<span data-ttu-id="294e1-3745">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="294e1-3746">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3746">Definition</span></span>

<span data-ttu-id="294e1-3747">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3748">La funzione Func_formatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3749">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="294e1-3750">Viene trovata una parola chiave da Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="294e1-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="294e1-3751">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="294e1-3752">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="294e1-3753">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="294e1-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="294e1-3754">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3755">La funzione Func_unformatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3756">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294e1-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="294e1-3757">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="294e1-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="294e1-3758">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="294e1-3759">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3759">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="294e1-3760">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="294e1-3761">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="294e1-3761">Keyword_itin</span></span>

- <span data-ttu-id="294e1-3762">contribuente</span><span class="sxs-lookup"><span data-stu-id="294e1-3762">taxpayer</span></span> 
- <span data-ttu-id="294e1-3763">tax id</span><span class="sxs-lookup"><span data-stu-id="294e1-3763">tax id</span></span> 
- <span data-ttu-id="294e1-3764">tax identification</span><span class="sxs-lookup"><span data-stu-id="294e1-3764">tax identification</span></span> 
- <span data-ttu-id="294e1-3765">Itin</span><span class="sxs-lookup"><span data-stu-id="294e1-3765">itin</span></span> 
- <span data-ttu-id="294e1-3766">SSN</span><span class="sxs-lookup"><span data-stu-id="294e1-3766">ssn</span></span> 
- <span data-ttu-id="294e1-3767">latta</span><span class="sxs-lookup"><span data-stu-id="294e1-3767">tin</span></span> 
- <span data-ttu-id="294e1-3768">social security</span><span class="sxs-lookup"><span data-stu-id="294e1-3768">social security</span></span> 
- <span data-ttu-id="294e1-3769">tax payer</span><span class="sxs-lookup"><span data-stu-id="294e1-3769">tax payer</span></span> 
- <span data-ttu-id="294e1-3770">itins</span><span class="sxs-lookup"><span data-stu-id="294e1-3770">itins</span></span> 
- <span data-ttu-id="294e1-3771">taxid</span><span class="sxs-lookup"><span data-stu-id="294e1-3771">taxid</span></span> 
- <span data-ttu-id="294e1-3772">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="294e1-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="294e1-3773">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="294e1-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="294e1-3774">License</span><span class="sxs-lookup"><span data-stu-id="294e1-3774">License</span></span> 
- <span data-ttu-id="294e1-3775">DL</span><span class="sxs-lookup"><span data-stu-id="294e1-3775">DL</span></span> 
- <span data-ttu-id="294e1-3776">DOB</span><span class="sxs-lookup"><span data-stu-id="294e1-3776">DOB</span></span> 
- <span data-ttu-id="294e1-3777">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="294e1-3777">Birthdate</span></span> 
- <span data-ttu-id="294e1-3778">Compleanno</span><span class="sxs-lookup"><span data-stu-id="294e1-3778">Birthday</span></span> 
- <span data-ttu-id="294e1-3779">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="294e1-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="294e1-3780">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="294e1-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="294e1-3781">Formato</span><span class="sxs-lookup"><span data-stu-id="294e1-3781">Format</span></span>

<span data-ttu-id="294e1-3782">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="294e1-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="294e1-3783">Se emesso prima della metà del 2011, un SSN ha una formattazione complessa in cui alcune parti del numero devono rientrare in alcuni intervalli per essere valide (ma non c'è nessun checksum).</span><span class="sxs-lookup"><span data-stu-id="294e1-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="294e1-3784">Modello</span><span class="sxs-lookup"><span data-stu-id="294e1-3784">Pattern</span></span>

<span data-ttu-id="294e1-3785">Quattro funzioni cercano SNSS in quattro modelli diversi:</span><span class="sxs-lookup"><span data-stu-id="294e1-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="294e1-3786">Func_ssn trova SNSS con una formattazione complessa pre2011 che è formattata con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="294e1-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="294e1-3787">Func_unformatted_ssn trova SNSS con una formattazione complessa pre2011 che non è formattata come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="294e1-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="294e1-3788">Func_randomized_formatted_ssn trova post-2011 SNSS formattati con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="294e1-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="294e1-3789">Func_randomized_unformatted_ssn trova post-2011 SNSS che non sono formattati come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="294e1-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="294e1-3790">Checksum</span><span class="sxs-lookup"><span data-stu-id="294e1-3790">Checksum</span></span>

<span data-ttu-id="294e1-3791">No</span><span class="sxs-lookup"><span data-stu-id="294e1-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="294e1-3792">Definizione</span><span class="sxs-lookup"><span data-stu-id="294e1-3792">Definition</span></span>

<span data-ttu-id="294e1-3793">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3794">La funzione Func_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3795">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="294e1-3795">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="294e1-3796">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3796">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="294e1-3797">La funzione Func_us_address trova un indirizzo nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3797">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="294e1-3798">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3798">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3799">La funzione Func_unformatted_ssn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3799">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3800">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="294e1-3800">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="294e1-3801">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3801">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="294e1-3802">La funzione Func_us_address trova un indirizzo nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3802">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="294e1-3803">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3803">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3804">La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3804">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3805">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="294e1-3805">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="294e1-3806">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3806">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="294e1-3807">La funzione Func_us_address trova un indirizzo nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3807">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="294e1-3808">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 55%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="294e1-3808">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3809">La funzione Func_randomized_unformatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3809">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3810">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="294e1-3810">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="294e1-3811">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3811">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="294e1-3812">La funzione Func_us_address trova un indirizzo nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="294e1-3812">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="294e1-3813">Un criterio DLP è 40% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri:</span><span class="sxs-lookup"><span data-stu-id="294e1-3813">A DLP policy is 40% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="294e1-3814">La funzione Func_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3814">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3815">La funzione Func_unformatted_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3815">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3816">La funzione Func_randomized_unformatted_ssn non trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3816">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3817">Non viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="294e1-3817">A keyword from Keyword_ssn is not found.</span></span>
 
<span data-ttu-id="294e1-3818">Oppure</span><span class="sxs-lookup"><span data-stu-id="294e1-3818">Or</span></span>

- <span data-ttu-id="294e1-3819">La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3819">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3820">La funzione Func_unformatted_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3820">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3821">La funzione Func_randomized_unformatted_ssn non trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="294e1-3821">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="294e1-3822">Non viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="294e1-3822">A keyword from Keyword_ssn is not found.</span></span>

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="294e1-3823">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="294e1-3823">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="294e1-3824">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="294e1-3824">Keyword_ssn</span></span>

- <span data-ttu-id="294e1-3825">Social Security</span><span class="sxs-lookup"><span data-stu-id="294e1-3825">Social Security</span></span> 
- <span data-ttu-id="294e1-3826">Social Security#</span><span class="sxs-lookup"><span data-stu-id="294e1-3826">Social Security#</span></span> 
- <span data-ttu-id="294e1-3827">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="294e1-3827">Soc Sec</span></span> 
- <span data-ttu-id="294e1-3828">SSN</span><span class="sxs-lookup"><span data-stu-id="294e1-3828">SSN</span></span> 
- <span data-ttu-id="294e1-3829">SNSS</span><span class="sxs-lookup"><span data-stu-id="294e1-3829">SSNS</span></span> 
- <span data-ttu-id="294e1-3830">SSN #</span><span class="sxs-lookup"><span data-stu-id="294e1-3830">SSN#</span></span> 
- <span data-ttu-id="294e1-3831">SS #</span><span class="sxs-lookup"><span data-stu-id="294e1-3831">SS#</span></span> 
- <span data-ttu-id="294e1-3832">SSID</span><span class="sxs-lookup"><span data-stu-id="294e1-3832">SSID</span></span> 
   

