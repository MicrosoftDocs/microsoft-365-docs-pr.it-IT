---
title: Numero di identificazione fiscale dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: adcd9be9b5f8775ad39010d771ff2ac214df1e17
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083664"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="fea10-104">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="fea10-104">EU Tax Identification Number</span></span>

<span data-ttu-id="fea10-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale (TIN) dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="fea10-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="fea10-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="fea10-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="fea10-107">Austria</span><span class="sxs-lookup"><span data-stu-id="fea10-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="fea10-108">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-108">Format</span></span>

<span data-ttu-id="fea10-109">Nove cifre con trattino e barra di inoltro opzionali</span><span class="sxs-lookup"><span data-stu-id="fea10-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-110">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-110">Pattern</span></span>

<span data-ttu-id="fea10-111">Nove cifre con trattino e barra di inoltro facoltativi:</span><span class="sxs-lookup"><span data-stu-id="fea10-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="fea10-112">Due cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-112">Two digits</span></span> 
    
- <span data-ttu-id="fea10-113">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="fea10-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="fea10-114">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-114">Three digits</span></span>
    
- <span data-ttu-id="fea10-115">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="fea10-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="fea10-116">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-117">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-117">Checksum</span></span>

<span data-ttu-id="fea10-118">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-119">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-119">Definition</span></span>

<span data-ttu-id="fea10-120">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-121">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-122">Viene trovata una `Keywords_austria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-123">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-124">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-125">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="fea10-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-127">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-127">tax number</span></span>
  
<span data-ttu-id="fea10-128">numero</span><span class="sxs-lookup"><span data-stu-id="fea10-128">number</span></span>
  
<span data-ttu-id="fea10-129">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-129">tax registration number</span></span>
  
<span data-ttu-id="fea10-130">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-130">tax id</span></span>
  
<span data-ttu-id="fea10-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="fea10-131">st.nr.</span></span>
  
<span data-ttu-id="fea10-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="fea10-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="fea10-133">Belgio</span><span class="sxs-lookup"><span data-stu-id="fea10-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="fea10-134">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-134">Format</span></span>

<span data-ttu-id="fea10-135">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-136">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-136">Pattern</span></span>

<span data-ttu-id="fea10-137">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="fea10-137">11 digits:</span></span>
  
- <span data-ttu-id="fea10-138">Due cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-138">Two digits</span></span>
    
- <span data-ttu-id="fea10-139">"0" o "1"</span><span class="sxs-lookup"><span data-stu-id="fea10-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="fea10-140">Una cifra</span><span class="sxs-lookup"><span data-stu-id="fea10-140">One digit</span></span>
    
- <span data-ttu-id="fea10-141">"0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="fea10-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="fea10-142">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-143">Checksum</span></span>

<span data-ttu-id="fea10-144">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fea10-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-145">Definition</span></span>

<span data-ttu-id="fea10-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-147">L'espressione `Regex_belgium_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-148">Viene trovata una `Keywords_belgium_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="fea10-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-151">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-151">tax number</span></span>
  
<span data-ttu-id="fea10-152">numero di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="fea10-152">national registration number</span></span>
  
<span data-ttu-id="fea10-153">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-153">tax registration number</span></span>
  
<span data-ttu-id="fea10-154">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-154">tax id</span></span>
  
<span data-ttu-id="fea10-155">NIF</span><span class="sxs-lookup"><span data-stu-id="fea10-155">nif</span></span>
  
<span data-ttu-id="fea10-156">NIF #</span><span class="sxs-lookup"><span data-stu-id="fea10-156">nif#</span></span>
  
<span data-ttu-id="fea10-157">numéro de Registre National</span><span class="sxs-lookup"><span data-stu-id="fea10-157">numéro de registre national</span></span>
  
<span data-ttu-id="fea10-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="fea10-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="fea10-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="fea10-160">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-160">Format</span></span>

<span data-ttu-id="fea10-161">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-162">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-162">Pattern</span></span>

<span data-ttu-id="fea10-163">10 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fea10-164">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-164">Checksum</span></span>

<span data-ttu-id="fea10-165">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-166">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-166">Definition</span></span>

<span data-ttu-id="fea10-167">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-168">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-169">Viene trovata una `Keywords_bulgaria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-170">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-171">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-172">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="fea10-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-174">bucn</span><span class="sxs-lookup"><span data-stu-id="fea10-174">bucn</span></span>
  
<span data-ttu-id="fea10-175">numero civile uniforme</span><span class="sxs-lookup"><span data-stu-id="fea10-175">uniform civil number</span></span>
  
<span data-ttu-id="fea10-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="fea10-176">bucn#</span></span>
  
<span data-ttu-id="fea10-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="fea10-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="fea10-178">ID civile uniforme</span><span class="sxs-lookup"><span data-stu-id="fea10-178">uniform civil id</span></span>
  
<span data-ttu-id="fea10-179">uniforme civile No</span><span class="sxs-lookup"><span data-stu-id="fea10-179">uniform civil no</span></span>
  
<span data-ttu-id="fea10-180">EGN</span><span class="sxs-lookup"><span data-stu-id="fea10-180">egn</span></span>
  
<span data-ttu-id="fea10-181">numero civile uniforme bulgaro</span><span class="sxs-lookup"><span data-stu-id="fea10-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="fea10-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="fea10-182">uniformcivilno#</span></span>
  
<span data-ttu-id="fea10-183">EGN #</span><span class="sxs-lookup"><span data-stu-id="fea10-183">egn#</span></span>
  
<span data-ttu-id="fea10-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="fea10-184">униформ граждански номер</span></span>
  
<span data-ttu-id="fea10-185">ID униформ</span><span class="sxs-lookup"><span data-stu-id="fea10-185">униформ id</span></span>
  
<span data-ttu-id="fea10-186">ID граждански униформ</span><span class="sxs-lookup"><span data-stu-id="fea10-186">униформ граждански id</span></span>
  
<span data-ttu-id="fea10-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="fea10-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="fea10-188">Croazia</span><span class="sxs-lookup"><span data-stu-id="fea10-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="fea10-189">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-189">Format</span></span>

<span data-ttu-id="fea10-190">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-191">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-191">Pattern</span></span>

<span data-ttu-id="fea10-192">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="fea10-192">11 digits:</span></span>
  
- <span data-ttu-id="fea10-193">Dieci cifre, scelte casualmente</span><span class="sxs-lookup"><span data-stu-id="fea10-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="fea10-194">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="fea10-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-195">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-195">Checksum</span></span>

<span data-ttu-id="fea10-196">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-197">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-197">Definition</span></span>

<span data-ttu-id="fea10-198">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-199">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-200">Viene trovata una `Keywords_croatia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-202">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-203">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="fea10-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-205">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-205">tax number</span></span>
  
<span data-ttu-id="fea10-206">imposte</span><span class="sxs-lookup"><span data-stu-id="fea10-206">tax</span></span>
  
<span data-ttu-id="fea10-207">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-207">tax id</span></span>
  
<span data-ttu-id="fea10-208">OID</span><span class="sxs-lookup"><span data-stu-id="fea10-208">oid</span></span>
  
<span data-ttu-id="fea10-209">OID #</span><span class="sxs-lookup"><span data-stu-id="fea10-209">oid#</span></span>
  
<span data-ttu-id="fea10-210">Porezni broj</span><span class="sxs-lookup"><span data-stu-id="fea10-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="fea10-211">Cipro</span><span class="sxs-lookup"><span data-stu-id="fea10-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="fea10-212">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-212">Format</span></span>

<span data-ttu-id="fea10-213">Otto cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="fea10-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-214">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-214">Pattern</span></span>

<span data-ttu-id="fea10-215">Otto cifre e una lettera:</span><span class="sxs-lookup"><span data-stu-id="fea10-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="fea10-216">Un "0"</span><span class="sxs-lookup"><span data-stu-id="fea10-216">A "0"</span></span> 
    
- <span data-ttu-id="fea10-217">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-217">Seven digits</span></span>
    
- <span data-ttu-id="fea10-218">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-219">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-219">Checksum</span></span>

<span data-ttu-id="fea10-220">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fea10-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-221">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-221">Definition</span></span>

<span data-ttu-id="fea10-222">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-223">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-224">Viene trovata una `Keywords_cyprus_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-225">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-226">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="fea10-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-229">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-229">tax number</span></span>
  
<span data-ttu-id="fea10-230">imposte</span><span class="sxs-lookup"><span data-stu-id="fea10-230">tax</span></span>
  
<span data-ttu-id="fea10-231">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-231">tax id</span></span>
  
<span data-ttu-id="fea10-232">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-232">tax identification code</span></span>
  
<span data-ttu-id="fea10-233">TIC</span><span class="sxs-lookup"><span data-stu-id="fea10-233">tic</span></span>
  
<span data-ttu-id="fea10-234">TIC #</span><span class="sxs-lookup"><span data-stu-id="fea10-234">tic#</span></span>
  
<span data-ttu-id="fea10-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="fea10-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="fea10-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="fea10-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="fea10-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="fea10-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="fea10-238">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="fea10-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="fea10-239">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-239">Format</span></span>

<span data-ttu-id="fea10-240">Nove o dieci cifre con una barra rovesciata facoltativa</span><span class="sxs-lookup"><span data-stu-id="fea10-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-241">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-241">Pattern</span></span>

<span data-ttu-id="fea10-242">Nove o dieci cifre con un backslash facoltativo:</span><span class="sxs-lookup"><span data-stu-id="fea10-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="fea10-243">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-243">Six digits</span></span> 
    
- <span data-ttu-id="fea10-244">Una barra rovesciata (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="fea10-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="fea10-245">Tre o quattro cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-246">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-246">Checksum</span></span>

<span data-ttu-id="fea10-247">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fea10-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-248">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-248">Definition</span></span>

<span data-ttu-id="fea10-249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-250">L'espressione `Regex_czech_republic_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-251">Viene trovata una `Keywords_czech_republic_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="fea10-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-254">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-254">tax number</span></span>
  
<span data-ttu-id="fea10-255">imposte</span><span class="sxs-lookup"><span data-stu-id="fea10-255">tax</span></span>
  
<span data-ttu-id="fea10-256">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-256">tax id</span></span>
  
<span data-ttu-id="fea10-257">numero personale</span><span class="sxs-lookup"><span data-stu-id="fea10-257">personal number</span></span>
  
<span data-ttu-id="fea10-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="fea10-258">daňové číslo</span></span>
  
<span data-ttu-id="fea10-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="fea10-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="fea10-260">Danimarca</span><span class="sxs-lookup"><span data-stu-id="fea10-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="fea10-261">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-261">Format</span></span>

<span data-ttu-id="fea10-262">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="fea10-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-263">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-263">Pattern</span></span>

<span data-ttu-id="fea10-264">Dieci cifre contenenti un segno meno:</span><span class="sxs-lookup"><span data-stu-id="fea10-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="fea10-265">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="fea10-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="fea10-266">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="fea10-266">A hyphen</span></span>
    
- <span data-ttu-id="fea10-267">Quattro cifre che corrispondono a un numero di sequenza in cui la prima cifra corrisponde al secolo di nascita e l'ultima cifra corrisponde al sesso dell'individuo (dispari per il maschio e anche per le femmine)</span><span class="sxs-lookup"><span data-stu-id="fea10-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-268">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-268">Checksum</span></span>

<span data-ttu-id="fea10-269">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-270">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-270">Definition</span></span>

<span data-ttu-id="fea10-271">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-272">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-273">Viene trovata una `Keywords_denmark_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-275">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-276">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="fea10-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-278">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-278">tax number</span></span>
  
<span data-ttu-id="fea10-279">imposte</span><span class="sxs-lookup"><span data-stu-id="fea10-279">tax</span></span>
  
<span data-ttu-id="fea10-280">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-280">tax id</span></span>
  
<span data-ttu-id="fea10-281">numero CPR</span><span class="sxs-lookup"><span data-stu-id="fea10-281">cpr number</span></span>
  
<span data-ttu-id="fea10-282">CPR #</span><span class="sxs-lookup"><span data-stu-id="fea10-282">cpr#</span></span>
  
<span data-ttu-id="fea10-283">Nummer di pattinaggio</span><span class="sxs-lookup"><span data-stu-id="fea10-283">skat nummer</span></span>
  
<span data-ttu-id="fea10-284">ID pattina</span><span class="sxs-lookup"><span data-stu-id="fea10-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="fea10-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="fea10-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="fea10-286">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-286">Format</span></span>

<span data-ttu-id="fea10-287">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-288">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-288">Pattern</span></span>

<span data-ttu-id="fea10-289">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="fea10-289">11 digits:</span></span>
  
-  <span data-ttu-id="fea10-290">Una cifra che corrisponde al sesso e al secolo del parto, in cui un numero dispari indica il maschio e il numero pari indica la femmina come segue: 1,2 per il XIX secolo; 3,4 per il XX secolo; e 5,6 per il XXI secolo</span><span class="sxs-lookup"><span data-stu-id="fea10-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="fea10-291">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="fea10-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="fea10-292">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="fea10-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="fea10-293">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="fea10-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-294">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-294">Checksum</span></span>

<span data-ttu-id="fea10-295">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-296">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-296">Definition</span></span>

<span data-ttu-id="fea10-297">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-298">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-299">Viene trovata una `Keywords_estonia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-300">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-301">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-302">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="fea10-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-304">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-304">tax number</span></span>
  
<span data-ttu-id="fea10-305">imposte</span><span class="sxs-lookup"><span data-stu-id="fea10-305">tax</span></span>
  
<span data-ttu-id="fea10-306">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-306">tax id</span></span>
  
<span data-ttu-id="fea10-307">codice personale</span><span class="sxs-lookup"><span data-stu-id="fea10-307">personal code</span></span>
  
<span data-ttu-id="fea10-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="fea10-308">maksunumber</span></span>
  
<span data-ttu-id="fea10-309">ID maksu</span><span class="sxs-lookup"><span data-stu-id="fea10-309">maksu id</span></span>
  
<span data-ttu-id="fea10-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="fea10-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="fea10-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="fea10-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="fea10-312">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-312">Format</span></span>

<span data-ttu-id="fea10-313">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno</span><span class="sxs-lookup"><span data-stu-id="fea10-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-314">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-314">Pattern</span></span>

<span data-ttu-id="fea10-315">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno:</span><span class="sxs-lookup"><span data-stu-id="fea10-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="fea10-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-316">Six digits</span></span>
    
- <span data-ttu-id="fea10-317">Uno dei seguenti: un segno più, un segno di sottrazione o la lettera "A" (senza distinzione tra maiuscole/minuscole), in cui il segno più significa Nato tra 1800-1899, il segno meno significa Nato tra 1900-1999 e "A" significa Nato 2000 e dopo</span><span class="sxs-lookup"><span data-stu-id="fea10-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="fea10-318">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-318">Three digits</span></span>
    
- <span data-ttu-id="fea10-319">Una lettera o un numero</span><span class="sxs-lookup"><span data-stu-id="fea10-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-320">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-320">Checksum</span></span>

<span data-ttu-id="fea10-321">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-322">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-322">Definition</span></span>

<span data-ttu-id="fea10-323">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-324">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-325">Viene trovata una `Keywords_finland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-326">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-327">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-328">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="fea10-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-330">identification number</span><span class="sxs-lookup"><span data-stu-id="fea10-330">identification number</span></span>
  
<span data-ttu-id="fea10-331">ID personale</span><span class="sxs-lookup"><span data-stu-id="fea10-331">personal id</span></span>
  
<span data-ttu-id="fea10-332">numero di identità</span><span class="sxs-lookup"><span data-stu-id="fea10-332">identity number</span></span>
  
<span data-ttu-id="fea10-333">numero di identificazione nazionale finlandese</span><span class="sxs-lookup"><span data-stu-id="fea10-333">finnish national id number</span></span>
  
<span data-ttu-id="fea10-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="fea10-334">personalidnumber#</span></span>
  
<span data-ttu-id="fea10-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="fea10-335">national identification number</span></span>
  
<span data-ttu-id="fea10-336">numero ID</span><span class="sxs-lookup"><span data-stu-id="fea10-336">id number</span></span>
  
<span data-ttu-id="fea10-337">ID nazionale No.</span><span class="sxs-lookup"><span data-stu-id="fea10-337">national id no.</span></span>
  
<span data-ttu-id="fea10-338">numero ID nazionale</span><span class="sxs-lookup"><span data-stu-id="fea10-338">national id number</span></span>
  
<span data-ttu-id="fea10-339">ID No</span><span class="sxs-lookup"><span data-stu-id="fea10-339">id no</span></span>
  
<span data-ttu-id="fea10-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="fea10-340">tunnistenumero</span></span>
  
<span data-ttu-id="fea10-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="fea10-341">henkilötunnus</span></span>
  
<span data-ttu-id="fea10-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="fea10-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="fea10-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="fea10-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="fea10-344">numero identiteetti</span><span class="sxs-lookup"><span data-stu-id="fea10-344">identiteetti numero</span></span>
  
<span data-ttu-id="fea10-345">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="fea10-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="fea10-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="fea10-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="fea10-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="fea10-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="fea10-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="fea10-348">tunnusnumero</span></span>
  
<span data-ttu-id="fea10-349">Kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="fea10-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="fea10-350">Francia</span><span class="sxs-lookup"><span data-stu-id="fea10-350">France</span></span>

### <a name="format"></a><span data-ttu-id="fea10-351">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-351">Format</span></span>

<span data-ttu-id="fea10-352">13 cifre per gli utenti e nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="fea10-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-353">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-353">Pattern</span></span>

<span data-ttu-id="fea10-354">13 cifre per gli utenti:</span><span class="sxs-lookup"><span data-stu-id="fea10-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="fea10-355">Una cifra che deve essere 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="fea10-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="fea10-356">12 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-356">12 digits</span></span>
    
<span data-ttu-id="fea10-357">Nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="fea10-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fea10-358">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-358">Checksum</span></span>

<span data-ttu-id="fea10-359">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fea10-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-360">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-360">Definition</span></span>

<span data-ttu-id="fea10-361">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-362">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-363">Viene trovata una `Keywords_france_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-365">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-366">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="fea10-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-368">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-368">tax identification number</span></span>
  
<span data-ttu-id="fea10-369">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-369">tax number</span></span>
  
<span data-ttu-id="fea10-370">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-370">tax id</span></span>
  
<span data-ttu-id="fea10-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="fea10-372">Germania</span><span class="sxs-lookup"><span data-stu-id="fea10-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="fea10-373">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-373">Format</span></span>

<span data-ttu-id="fea10-374">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-375">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-375">Pattern</span></span>

<span data-ttu-id="fea10-376">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="fea10-376">11 digits :</span></span>
  
-  <span data-ttu-id="fea10-377">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-377">Ten digits</span></span> 
    
- <span data-ttu-id="fea10-378">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="fea10-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-379">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-379">Checksum</span></span>

<span data-ttu-id="fea10-380">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-381">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-381">Definition</span></span>

<span data-ttu-id="fea10-382">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-383">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-384">Viene trovata una `Keywords_germany_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-385">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-386">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="fea10-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-389">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-389">tax number</span></span>
  
<span data-ttu-id="fea10-390">tassa no.</span><span class="sxs-lookup"><span data-stu-id="fea10-390">tax no.</span></span>
  
<span data-ttu-id="fea10-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="fea10-391">taxno#</span></span>
  
<span data-ttu-id="fea10-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="fea10-392">taxnumber#</span></span>
  
<span data-ttu-id="fea10-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fea10-393">taxnumber</span></span>
  
<span data-ttu-id="fea10-394">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-394">tax id</span></span>
  
<span data-ttu-id="fea10-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-395">taxid#</span></span>
  
<span data-ttu-id="fea10-396">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-396">tax identification number</span></span>
  
<span data-ttu-id="fea10-397">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="fea10-397">tax identification no.</span></span>
  
<span data-ttu-id="fea10-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="fea10-398">steuernummer</span></span>
  
<span data-ttu-id="fea10-399">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="fea10-399">steuer id</span></span>
  
<span data-ttu-id="fea10-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="fea10-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="fea10-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="fea10-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="fea10-402">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-402">Format</span></span>

<span data-ttu-id="fea10-403">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-404">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-404">Pattern</span></span>

<span data-ttu-id="fea10-405">9 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fea10-406">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-406">Checksum</span></span>

<span data-ttu-id="fea10-407">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fea10-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-408">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-408">Definition</span></span>

<span data-ttu-id="fea10-409">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-410">L'espressione `Regex_greece_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-411">Viene trovata una `Keywords_greece_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-412">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="fea10-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-414">AFM</span><span class="sxs-lookup"><span data-stu-id="fea10-414">afm</span></span>
  
<span data-ttu-id="fea10-415">latta</span><span class="sxs-lookup"><span data-stu-id="fea10-415">tin</span></span>
  
<span data-ttu-id="fea10-416">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="fea10-416">tax id no.</span></span>
  
<span data-ttu-id="fea10-417">ID IVA No</span><span class="sxs-lookup"><span data-stu-id="fea10-417">tax id no</span></span>
  
<span data-ttu-id="fea10-418">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-418">tax identification number</span></span>
  
<span data-ttu-id="fea10-419">numero del registro di sistema fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-419">tax registry number</span></span>
  
<span data-ttu-id="fea10-420">Registro fiscale No.</span><span class="sxs-lookup"><span data-stu-id="fea10-420">tax registry no.</span></span>
  
<span data-ttu-id="fea10-421">AFM #</span><span class="sxs-lookup"><span data-stu-id="fea10-421">afm#</span></span>
  
<span data-ttu-id="fea10-422">latta #</span><span class="sxs-lookup"><span data-stu-id="fea10-422">tin#</span></span>
  
<span data-ttu-id="fea10-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="fea10-423">taxidno#</span></span>
  
<span data-ttu-id="fea10-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="fea10-424">taxregistryno#</span></span>
  
<span data-ttu-id="fea10-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="fea10-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="fea10-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="fea10-426">aφμ</span></span>
  
<span data-ttu-id="fea10-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="fea10-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="fea10-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="fea10-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="fea10-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="fea10-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="fea10-430">Ungheria</span><span class="sxs-lookup"><span data-stu-id="fea10-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="fea10-431">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-431">Format</span></span>

<span data-ttu-id="fea10-432">Dieci cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-433">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-433">Pattern</span></span>

<span data-ttu-id="fea10-434">Dieci cifre:</span><span class="sxs-lookup"><span data-stu-id="fea10-434">Ten digits:</span></span>
  
-  <span data-ttu-id="fea10-435">Una cifra che deve essere "8"</span><span class="sxs-lookup"><span data-stu-id="fea10-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="fea10-436">Cinque cifre che corrispondono al numero di giorni compresi tra la data 01/01/1867 e la data di nascita dell'individuo</span><span class="sxs-lookup"><span data-stu-id="fea10-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="fea10-437">Tre cifre che corrispondono al numero generato dalla possibilità di distinguere gli individui nati nello stesso giorno</span><span class="sxs-lookup"><span data-stu-id="fea10-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="fea10-438">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="fea10-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-439">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-439">Checksum</span></span>

<span data-ttu-id="fea10-440">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-441">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-441">Definition</span></span>

<span data-ttu-id="fea10-442">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-443">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-444">Viene trovata una `Keywords_hungary_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-445">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-446">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-447">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="fea10-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-449">numero di identificazione fiscale ungherese</span><span class="sxs-lookup"><span data-stu-id="fea10-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="fea10-450">Tin ungherese</span><span class="sxs-lookup"><span data-stu-id="fea10-450">hungarian tin</span></span>
  
<span data-ttu-id="fea10-451">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-451">tax id number</span></span>
  
<span data-ttu-id="fea10-452">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="fea10-452">vat number</span></span>
  
<span data-ttu-id="fea10-453">autorità tributaria No</span><span class="sxs-lookup"><span data-stu-id="fea10-453">tax authority no</span></span>
  
<span data-ttu-id="fea10-454">numero dell'identità fiscale dell'ID fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-454">tax id tax identity number</span></span>
  
<span data-ttu-id="fea10-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="fea10-455">taxidnumber#</span></span>
  
<span data-ttu-id="fea10-456">latta #</span><span class="sxs-lookup"><span data-stu-id="fea10-456">tin#</span></span>
  
<span data-ttu-id="fea10-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="fea10-457">hungatiantin#</span></span>
  
<span data-ttu-id="fea10-458">identificazione fiscale No</span><span class="sxs-lookup"><span data-stu-id="fea10-458">tax identification no</span></span>
  
<span data-ttu-id="fea10-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="fea10-459">taxidno#</span></span>
  
<span data-ttu-id="fea10-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="fea10-460">adóazonosító szám</span></span>
  
<span data-ttu-id="fea10-461">adószám</span><span class="sxs-lookup"><span data-stu-id="fea10-461">adószám</span></span>
  
<span data-ttu-id="fea10-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="fea10-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="fea10-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="fea10-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="fea10-464">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-464">Format</span></span>

<span data-ttu-id="fea10-465">Sette cifre seguite da una lettera senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-466">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-466">Pattern</span></span>

<span data-ttu-id="fea10-467">Sette cifre seguite da una lettera:</span><span class="sxs-lookup"><span data-stu-id="fea10-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="fea10-468">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-468">Seven digits</span></span> 
    
- <span data-ttu-id="fea10-469">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-470">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-470">Checksum</span></span>

<span data-ttu-id="fea10-471">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fea10-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-472">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-472">Definition</span></span>

<span data-ttu-id="fea10-473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-474">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-475">Viene trovata una `Keywords_ireland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-476">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-477">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="fea10-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-480">servizio pubblico no</span><span class="sxs-lookup"><span data-stu-id="fea10-480">public service no</span></span>
  
<span data-ttu-id="fea10-481">servizio pubblico personale No</span><span class="sxs-lookup"><span data-stu-id="fea10-481">personal public service no</span></span>
  
<span data-ttu-id="fea10-482">PPS No</span><span class="sxs-lookup"><span data-stu-id="fea10-482">pps no</span></span>
  
<span data-ttu-id="fea10-483">servizio personale No</span><span class="sxs-lookup"><span data-stu-id="fea10-483">personal service no</span></span>
  
<span data-ttu-id="fea10-484">servizio PPS No</span><span class="sxs-lookup"><span data-stu-id="fea10-484">pps service no</span></span>
  
<span data-ttu-id="fea10-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="fea10-485">ppsno#</span></span>
  
<span data-ttu-id="fea10-486">Irish PPS No</span><span class="sxs-lookup"><span data-stu-id="fea10-486">irish pps no</span></span>
  
<span data-ttu-id="fea10-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="fea10-487">publicserviceno#</span></span>
  
<span data-ttu-id="fea10-488">numero di servizio pubblico personale</span><span class="sxs-lookup"><span data-stu-id="fea10-488">personal public service number</span></span>
  
<span data-ttu-id="fea10-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="fea10-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="fea10-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="fea10-490">pps uimh</span></span>
  
<span data-ttu-id="fea10-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="fea10-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="fea10-492">Italia</span><span class="sxs-lookup"><span data-stu-id="fea10-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="fea10-493">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-493">Format</span></span>

<span data-ttu-id="fea10-494">16 lettere e cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="fea10-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-495">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-495">Pattern</span></span>

<span data-ttu-id="fea10-496">16 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="fea10-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="fea10-497">Tre lettere che corrispondono alle prime tre consonanti del nome di famiglia</span><span class="sxs-lookup"><span data-stu-id="fea10-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="fea10-498">Tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome</span><span class="sxs-lookup"><span data-stu-id="fea10-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="fea10-499">Due cifre che corrispondono alle ultime cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="fea10-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="fea10-500">Una cifra corrispondente al mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)</span><span class="sxs-lookup"><span data-stu-id="fea10-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="fea10-501">Due cifre che corrispondono al giorno del mese di nascita in cui 40 viene aggiunto al giorno di nascita per le femmine per differenziare dai maschi</span><span class="sxs-lookup"><span data-stu-id="fea10-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="fea10-502">Quattro cifre che corrispondono a un codice di area specifico per il comune in cui è nata la persona: vengono utilizzati codici a livello nazionale per i paesi esteri</span><span class="sxs-lookup"><span data-stu-id="fea10-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="fea10-503">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="fea10-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-504">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-504">Checksum</span></span>

<span data-ttu-id="fea10-505">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-506">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-506">Definition</span></span>

<span data-ttu-id="fea10-507">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-508">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-509">Viene trovata una `Keywords_italy_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-510">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-511">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-512">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="fea10-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-514">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-514">tax number</span></span>
  
<span data-ttu-id="fea10-515">tassa no.</span><span class="sxs-lookup"><span data-stu-id="fea10-515">tax no.</span></span>
  
<span data-ttu-id="fea10-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="fea10-516">taxno#</span></span>
  
<span data-ttu-id="fea10-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="fea10-517">taxnumber#</span></span>
  
<span data-ttu-id="fea10-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fea10-518">taxnumber</span></span>
  
<span data-ttu-id="fea10-519">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-519">tax id</span></span>
  
<span data-ttu-id="fea10-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-520">taxid#</span></span>
  
<span data-ttu-id="fea10-521">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-521">fiscal code</span></span>
  
<span data-ttu-id="fea10-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="fea10-523">Lettonia</span><span class="sxs-lookup"><span data-stu-id="fea10-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="fea10-524">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-524">Format</span></span>

<span data-ttu-id="fea10-525">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-526">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-526">Pattern</span></span>

<span data-ttu-id="fea10-527">11 cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="fea10-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="fea10-528">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="fea10-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="fea10-529">Una cifra che corrisponde al secolo di nascita dove "0" corrisponde al XIX secolo, "1" corrisponde al 20 ° secolo e "2" corrisponde al XXI secolo</span><span class="sxs-lookup"><span data-stu-id="fea10-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="fea10-530">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-531">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-531">Checksum</span></span>

<span data-ttu-id="fea10-532">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-533">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-533">Definition</span></span>

<span data-ttu-id="fea10-534">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-535">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-536">Viene trovata una `Keywords_latvia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-537">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-538">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-539">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="fea10-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-541">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-541">tax number</span></span>
  
<span data-ttu-id="fea10-542">tassa no.</span><span class="sxs-lookup"><span data-stu-id="fea10-542">tax no.</span></span>
  
<span data-ttu-id="fea10-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="fea10-543">taxno#</span></span>
  
<span data-ttu-id="fea10-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="fea10-544">taxnumber#</span></span>
  
<span data-ttu-id="fea10-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fea10-545">taxnumber</span></span>
  
<span data-ttu-id="fea10-546">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-546">tax id</span></span>
  
<span data-ttu-id="fea10-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-547">taxid#</span></span>
  
<span data-ttu-id="fea10-548">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-548">tax identification number</span></span>
  
<span data-ttu-id="fea10-549">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="fea10-549">tax identification no.</span></span>
  
<span data-ttu-id="fea10-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="fea10-550">nodokļa numurs</span></span>
  
<span data-ttu-id="fea10-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="fea10-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="fea10-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="fea10-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="fea10-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="fea10-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="fea10-554">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-554">Format</span></span>

<span data-ttu-id="fea10-555">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-556">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-556">Pattern</span></span>

<span data-ttu-id="fea10-557">11 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fea10-558">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-558">Checksum</span></span>

<span data-ttu-id="fea10-559">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fea10-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-560">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-560">Definition</span></span>

<span data-ttu-id="fea10-561">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-562">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-563">Viene trovata una `Keywords_lithuania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-564">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-565">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-566">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="fea10-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-568">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-568">tax number</span></span>
  
<span data-ttu-id="fea10-569">tassa no.</span><span class="sxs-lookup"><span data-stu-id="fea10-569">tax no.</span></span>
  
<span data-ttu-id="fea10-570">tax no #</span><span class="sxs-lookup"><span data-stu-id="fea10-570">tax no#</span></span>
  
<span data-ttu-id="fea10-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="fea10-571">taxnumber#</span></span>
  
<span data-ttu-id="fea10-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fea10-572">taxnumber</span></span>
  
<span data-ttu-id="fea10-573">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-573">tax id</span></span>
  
<span data-ttu-id="fea10-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-574">taxid#</span></span>
  
<span data-ttu-id="fea10-575">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-575">tax identification number</span></span>
  
<span data-ttu-id="fea10-576">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="fea10-576">tax identification no.</span></span>
  
<span data-ttu-id="fea10-577">ID mokesčių</span><span class="sxs-lookup"><span data-stu-id="fea10-577">mokesčių id</span></span>
  
<span data-ttu-id="fea10-578">numeri mokesčių</span><span class="sxs-lookup"><span data-stu-id="fea10-578">mokesčių numeris</span></span>
  
<span data-ttu-id="fea10-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="fea10-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="fea10-580">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="fea10-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="fea10-581">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-581">Format</span></span>

<span data-ttu-id="fea10-582">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-583">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-583">Pattern</span></span>

<span data-ttu-id="fea10-584">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="fea10-584">13 digits:</span></span>
  
-  <span data-ttu-id="fea10-585">11 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-585">11 digits</span></span> 
    
- <span data-ttu-id="fea10-586">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="fea10-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-587">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-587">Checksum</span></span>

<span data-ttu-id="fea10-588">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-589">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-589">Definition</span></span>

<span data-ttu-id="fea10-590">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-591">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-592">Viene trovata una `Keywords_luxemburg_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-593">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-594">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-595">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="fea10-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-597">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-597">tax number</span></span>
  
<span data-ttu-id="fea10-598">tassa no.</span><span class="sxs-lookup"><span data-stu-id="fea10-598">tax no.</span></span>
  
<span data-ttu-id="fea10-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="fea10-599">taxno#</span></span>
  
<span data-ttu-id="fea10-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="fea10-600">taxnumber#</span></span>
  
<span data-ttu-id="fea10-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fea10-601">taxnumber</span></span>
  
<span data-ttu-id="fea10-602">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-602">tax id</span></span>
  
<span data-ttu-id="fea10-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-603">taxid#</span></span>
  
<span data-ttu-id="fea10-604">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-604">tax identification number</span></span>
  
<span data-ttu-id="fea10-605">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="fea10-605">tax identification no.</span></span>
  
<span data-ttu-id="fea10-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="fea10-606">steuernummer</span></span>
  
<span data-ttu-id="fea10-607">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="fea10-607">steuer id</span></span>
  
<span data-ttu-id="fea10-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="fea10-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="fea10-609">Malta</span><span class="sxs-lookup"><span data-stu-id="fea10-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="fea10-610">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-610">Format</span></span>

<span data-ttu-id="fea10-611">Per cittadini maltesi: 7 cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="fea10-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="fea10-612">Nazionali non maltesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-613">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-613">Pattern</span></span>

<span data-ttu-id="fea10-614">Cittadini maltesi: 7 cifre e una lettera</span><span class="sxs-lookup"><span data-stu-id="fea10-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="fea10-615">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-615">Seven digits</span></span> 
    
- <span data-ttu-id="fea10-616">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="fea10-617">Nazionali non maltesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="fea10-618">9 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="fea10-619">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-619">Checksum</span></span>

<span data-ttu-id="fea10-620">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fea10-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-621">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-621">Definition</span></span>

<span data-ttu-id="fea10-622">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-623">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-624">Viene trovata una `Keywords_malta_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-625">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-626">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-627">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="fea10-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-629">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-629">tax number</span></span>
  
<span data-ttu-id="fea10-630">tassa no.</span><span class="sxs-lookup"><span data-stu-id="fea10-630">tax no.</span></span>
  
<span data-ttu-id="fea10-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="fea10-631">taxno#</span></span>
  
<span data-ttu-id="fea10-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="fea10-632">taxnumber#</span></span>
  
<span data-ttu-id="fea10-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fea10-633">taxnumber</span></span>
  
<span data-ttu-id="fea10-634">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-634">tax id</span></span>
  
<span data-ttu-id="fea10-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-635">taxid#</span></span>
  
<span data-ttu-id="fea10-636">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-636">tax identification number</span></span>
  
<span data-ttu-id="fea10-637">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="fea10-637">tax identification no.</span></span>
  
<span data-ttu-id="fea10-638">numru Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="fea10-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="fea10-639">ID Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="fea10-639">id tat-taxxa</span></span>
  
<span data-ttu-id="fea10-640">numru ta ' identifikazzjoni Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="fea10-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="fea10-641">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="fea10-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="fea10-642">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-642">Format</span></span>

<span data-ttu-id="fea10-643">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-644">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-644">Pattern</span></span>

<span data-ttu-id="fea10-645">9 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="fea10-646">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-646">Checksum</span></span>

<span data-ttu-id="fea10-647">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-648">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-648">Definition</span></span>

<span data-ttu-id="fea10-649">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-650">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-651">Viene trovata una `Keywords_netherlands_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-652">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-653">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-654">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="fea10-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-656">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="fea10-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="fea10-657">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="fea10-657">netherlands tax identification</span></span>
  
<span data-ttu-id="fea10-658">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="fea10-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="fea10-659">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="fea10-659">netherland's tax identification</span></span>
  
<span data-ttu-id="fea10-660">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-660">tax identification number</span></span>
  
<span data-ttu-id="fea10-661">ID delle tasse olandesi</span><span class="sxs-lookup"><span data-stu-id="fea10-661">dutch tax id</span></span>
  
<span data-ttu-id="fea10-662">numero di identificazione fiscale olandese</span><span class="sxs-lookup"><span data-stu-id="fea10-662">dutch tax identification number</span></span>
  
<span data-ttu-id="fea10-663">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-663">tax id</span></span>
  
<span data-ttu-id="fea10-664">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="fea10-664">tax id#</span></span>
  
<span data-ttu-id="fea10-665">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-665">tax number</span></span>
  
<span data-ttu-id="fea10-666">tax no #</span><span class="sxs-lookup"><span data-stu-id="fea10-666">tax no#</span></span>
  
<span data-ttu-id="fea10-667">imposte #</span><span class="sxs-lookup"><span data-stu-id="fea10-667">tax#</span></span>
  
<span data-ttu-id="fea10-668">latta</span><span class="sxs-lookup"><span data-stu-id="fea10-668">tin</span></span>
  
<span data-ttu-id="fea10-669">latta #</span><span class="sxs-lookup"><span data-stu-id="fea10-669">tin#</span></span>
  
<span data-ttu-id="fea10-670">Tin olandesi</span><span class="sxs-lookup"><span data-stu-id="fea10-670">netherlands tin</span></span>
  
<span data-ttu-id="fea10-671">stagno degli olandesi</span><span class="sxs-lookup"><span data-stu-id="fea10-671">netherland's tin</span></span>
  
<span data-ttu-id="fea10-672">Nederlands identificatienummer di recente</span><span class="sxs-lookup"><span data-stu-id="fea10-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="fea10-673">identificatienummer van delasting</span><span class="sxs-lookup"><span data-stu-id="fea10-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="fea10-674">identificatienummer che dura</span><span class="sxs-lookup"><span data-stu-id="fea10-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="fea10-675">Nederlands identificatie di recente</span><span class="sxs-lookup"><span data-stu-id="fea10-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="fea10-676">l'ID di Nummer del Nederlands</span><span class="sxs-lookup"><span data-stu-id="fea10-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="fea10-677">Nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="fea10-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="fea10-678">BTW nummer</span><span class="sxs-lookup"><span data-stu-id="fea10-678">btw nummer</span></span>
  
<span data-ttu-id="fea10-679">Nederlandse che durerà identificatie</span><span class="sxs-lookup"><span data-stu-id="fea10-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="fea10-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="fea10-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="fea10-681">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-681">Format</span></span>

<span data-ttu-id="fea10-682">Undici cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-683">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-683">Pattern</span></span>

<span data-ttu-id="fea10-684">Undici cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fea10-685">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-685">Checksum</span></span>

<span data-ttu-id="fea10-686">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-687">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-687">Definition</span></span>

<span data-ttu-id="fea10-688">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-689">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-690">Viene trovata una `Keywords_poland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-691">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-692">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-693">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="fea10-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-695">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-695">tax number</span></span>
  
<span data-ttu-id="fea10-696">tassa no.</span><span class="sxs-lookup"><span data-stu-id="fea10-696">tax no.</span></span>
  
<span data-ttu-id="fea10-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="fea10-697">taxno#</span></span>
  
<span data-ttu-id="fea10-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="fea10-698">taxnumber#</span></span>
  
<span data-ttu-id="fea10-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fea10-699">taxnumber</span></span>
  
<span data-ttu-id="fea10-700">NIP</span><span class="sxs-lookup"><span data-stu-id="fea10-700">nip</span></span>
  
<span data-ttu-id="fea10-701">NIP #</span><span class="sxs-lookup"><span data-stu-id="fea10-701">nip#</span></span>
  
<span data-ttu-id="fea10-702">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-702">tax id</span></span>
  
<span data-ttu-id="fea10-703">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="fea10-703">tax id#</span></span>
  
<span data-ttu-id="fea10-704">ID NIP</span><span class="sxs-lookup"><span data-stu-id="fea10-704">nip id</span></span>
  
<span data-ttu-id="fea10-705">ID NIP #</span><span class="sxs-lookup"><span data-stu-id="fea10-705">nip id#</span></span>
  
<span data-ttu-id="fea10-706">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-706">tax identification number</span></span>
  
<span data-ttu-id="fea10-707">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="fea10-707">tax identification no.</span></span>
  
<span data-ttu-id="fea10-708">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="fea10-708">vat number</span></span>
  
<span data-ttu-id="fea10-709">IVA No.</span><span class="sxs-lookup"><span data-stu-id="fea10-709">vat no.</span></span>
  
<span data-ttu-id="fea10-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="fea10-710">vatno#</span></span>
  
<span data-ttu-id="fea10-711">ID partita IVA</span><span class="sxs-lookup"><span data-stu-id="fea10-711">vat id</span></span>
  
<span data-ttu-id="fea10-712">ID partita IVA #</span><span class="sxs-lookup"><span data-stu-id="fea10-712">vat id#</span></span>
  
<span data-ttu-id="fea10-713">numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="fea10-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="fea10-714">Polski numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="fea10-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="fea10-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="fea10-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="fea10-716">Portogallo</span><span class="sxs-lookup"><span data-stu-id="fea10-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="fea10-717">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-717">Format</span></span>

<span data-ttu-id="fea10-718">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-719">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-719">Pattern</span></span>

<span data-ttu-id="fea10-720">9 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fea10-721">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-721">Checksum</span></span>

<span data-ttu-id="fea10-722">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-723">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-723">Definition</span></span>

<span data-ttu-id="fea10-724">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-725">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-726">Viene trovata una `Keywords_portugal_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-727">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-728">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-729">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="fea10-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-731">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-731">tax number</span></span>
  
<span data-ttu-id="fea10-732">tassa no.</span><span class="sxs-lookup"><span data-stu-id="fea10-732">tax no.</span></span>
  
<span data-ttu-id="fea10-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="fea10-733">taxno#</span></span>
  
<span data-ttu-id="fea10-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="fea10-734">taxnumber#</span></span>
  
<span data-ttu-id="fea10-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="fea10-735">taxnumber</span></span>
  
<span data-ttu-id="fea10-736">NIF</span><span class="sxs-lookup"><span data-stu-id="fea10-736">nif</span></span>
  
<span data-ttu-id="fea10-737">NIF #</span><span class="sxs-lookup"><span data-stu-id="fea10-737">nif#</span></span>
  
<span data-ttu-id="fea10-738">numero fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-738">numero fiscal</span></span>
  
<span data-ttu-id="fea10-739">número de identificação Fiscal</span><span class="sxs-lookup"><span data-stu-id="fea10-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="fea10-740">Romania</span><span class="sxs-lookup"><span data-stu-id="fea10-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="fea10-741">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-741">Format</span></span>

<span data-ttu-id="fea10-742">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-743">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-743">Pattern</span></span>

<span data-ttu-id="fea10-744">13 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fea10-745">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-745">Checksum</span></span>

<span data-ttu-id="fea10-746">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fea10-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-747">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-747">Definition</span></span>

<span data-ttu-id="fea10-748">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-749">L'espressione `Regex_romania_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-750">Viene trovata una `Keywords_romania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-751">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="fea10-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-753">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-753">tax id</span></span>
  
<span data-ttu-id="fea10-754">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-754">tax id number</span></span>
  
<span data-ttu-id="fea10-755">Tax File No</span><span class="sxs-lookup"><span data-stu-id="fea10-755">tax file no</span></span>
  
<span data-ttu-id="fea10-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="fea10-756">tax file number</span></span>
  
<span data-ttu-id="fea10-757">tax no</span><span class="sxs-lookup"><span data-stu-id="fea10-757">tax no</span></span>
  
<span data-ttu-id="fea10-758">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-758">tax number</span></span>
  
<span data-ttu-id="fea10-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-759">taxid#</span></span>
  
<span data-ttu-id="fea10-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="fea10-760">taxno#</span></span>
  
<span data-ttu-id="fea10-761">ID-ul taxei</span><span class="sxs-lookup"><span data-stu-id="fea10-761">id-ul taxei</span></span>
  
<span data-ttu-id="fea10-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="fea10-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="fea10-763">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="fea10-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="fea10-764">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-764">Format</span></span>

<span data-ttu-id="fea10-765">10 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-766">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-766">Pattern</span></span>

<span data-ttu-id="fea10-767">10 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fea10-768">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-768">Checksum</span></span>

<span data-ttu-id="fea10-769">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fea10-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-770">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-770">Definition</span></span>

<span data-ttu-id="fea10-771">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-772">L'espressione `Regex_slovakia_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-773">Viene trovata una `Keywords_slovakia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-774">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="fea10-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-776">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-776">tax id</span></span>
  
<span data-ttu-id="fea10-777">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-777">tax id number</span></span>
  
<span data-ttu-id="fea10-778">ID Tin</span><span class="sxs-lookup"><span data-stu-id="fea10-778">tin id</span></span>
  
<span data-ttu-id="fea10-779">Tin No</span><span class="sxs-lookup"><span data-stu-id="fea10-779">tin no</span></span>
  
<span data-ttu-id="fea10-780">ID Tin slovacco</span><span class="sxs-lookup"><span data-stu-id="fea10-780">slovakian tin id</span></span>
  
<span data-ttu-id="fea10-781">latta</span><span class="sxs-lookup"><span data-stu-id="fea10-781">tin</span></span>
  
<span data-ttu-id="fea10-782">Tax File No</span><span class="sxs-lookup"><span data-stu-id="fea10-782">tax file no</span></span>
  
<span data-ttu-id="fea10-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="fea10-783">tax file number</span></span>
  
<span data-ttu-id="fea10-784">tax no</span><span class="sxs-lookup"><span data-stu-id="fea10-784">tax no</span></span>
  
<span data-ttu-id="fea10-785">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-785">tax number</span></span>
  
<span data-ttu-id="fea10-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-786">taxid#</span></span>
  
<span data-ttu-id="fea10-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="fea10-787">taxno#</span></span>
  
<span data-ttu-id="fea10-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="fea10-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="fea10-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="fea10-789">daňové číslo</span></span>
  
<span data-ttu-id="fea10-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="fea10-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="fea10-791">Slovenia</span><span class="sxs-lookup"><span data-stu-id="fea10-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="fea10-792">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-792">Format</span></span>

<span data-ttu-id="fea10-793">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-794">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-794">Pattern</span></span>

<span data-ttu-id="fea10-795">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fea10-796">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-796">Checksum</span></span>

<span data-ttu-id="fea10-797">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-798">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-798">Definition</span></span>

<span data-ttu-id="fea10-799">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-800">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-801">Viene trovata una `Keywords_slovenia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-802">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-803">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-804">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="fea10-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-806">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-806">tax id</span></span>
  
<span data-ttu-id="fea10-807">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-807">tax id number</span></span>
  
<span data-ttu-id="fea10-808">ID Tin</span><span class="sxs-lookup"><span data-stu-id="fea10-808">tin id</span></span>
  
<span data-ttu-id="fea10-809">Tin No</span><span class="sxs-lookup"><span data-stu-id="fea10-809">tin no</span></span>
  
<span data-ttu-id="fea10-810">ID Tin sloveno</span><span class="sxs-lookup"><span data-stu-id="fea10-810">slovenian tin id</span></span>
  
<span data-ttu-id="fea10-811">latta</span><span class="sxs-lookup"><span data-stu-id="fea10-811">tin</span></span>
  
<span data-ttu-id="fea10-812">Tax File No</span><span class="sxs-lookup"><span data-stu-id="fea10-812">tax file no</span></span>
  
<span data-ttu-id="fea10-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="fea10-813">tax file number</span></span>
  
<span data-ttu-id="fea10-814">tax no</span><span class="sxs-lookup"><span data-stu-id="fea10-814">tax no</span></span>
  
<span data-ttu-id="fea10-815">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-815">tax number</span></span>
  
<span data-ttu-id="fea10-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-816">taxid#</span></span>
  
<span data-ttu-id="fea10-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="fea10-817">taxno#</span></span>
  
<span data-ttu-id="fea10-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="fea10-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="fea10-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="fea10-819">davčna številka</span></span>
  
<span data-ttu-id="fea10-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="fea10-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="fea10-821">Spagna</span><span class="sxs-lookup"><span data-stu-id="fea10-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="fea10-822">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-822">Format</span></span>

<span data-ttu-id="fea10-823">Sette o otto cifre e una o due lettere nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="fea10-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-824">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-824">Pattern</span></span>

<span data-ttu-id="fea10-825">Persone fisiche spagnole con carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="fea10-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="fea10-826">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-826">Eight digits</span></span> 
    
- <span data-ttu-id="fea10-827">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="fea10-828">Spagnoli non residenti senza una carta d'identità nazionale spagnola</span><span class="sxs-lookup"><span data-stu-id="fea10-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="fea10-829">Una lettera maiuscola "L" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="fea10-830">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-830">Seven digits</span></span>
    
- <span data-ttu-id="fea10-831">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="fea10-832">Spagnoli residenti di età inferiore ai 14 anni senza una carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="fea10-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="fea10-833">Una lettera maiuscola "K" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="fea10-834">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-834">Seven digits</span></span> 
    
- <span data-ttu-id="fea10-835">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="fea10-836">Stranieri con il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="fea10-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="fea10-837">Una lettera maiuscola che è "X", "Y" o "Z" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="fea10-838">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-838">Seven digits</span></span>
    
- <span data-ttu-id="fea10-839">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="fea10-840">Stranieri senza il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="fea10-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="fea10-841">Una lettera maiuscola che è "M" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="fea10-842">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-842">Seven digits</span></span>
    
- <span data-ttu-id="fea10-843">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fea10-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="fea10-844">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-844">Checksum</span></span>

<span data-ttu-id="fea10-845">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-846">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-846">Definition</span></span>

<span data-ttu-id="fea10-847">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-848">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-849">Viene trovata una `Keywords_spain_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-850">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-851">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-852">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="fea10-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-854">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-854">tax id</span></span>
  
<span data-ttu-id="fea10-855">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-855">tax id number</span></span>
  
<span data-ttu-id="fea10-856">ID CIF</span><span class="sxs-lookup"><span data-stu-id="fea10-856">cif id</span></span>
  
<span data-ttu-id="fea10-857">CIF No</span><span class="sxs-lookup"><span data-stu-id="fea10-857">cif no</span></span>
  
<span data-ttu-id="fea10-858">ID CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="fea10-858">spanish cif id</span></span>
  
<span data-ttu-id="fea10-859">CIF</span><span class="sxs-lookup"><span data-stu-id="fea10-859">cif</span></span>
  
<span data-ttu-id="fea10-860">Tax File No</span><span class="sxs-lookup"><span data-stu-id="fea10-860">tax file no</span></span>
  
<span data-ttu-id="fea10-861">numero CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="fea10-861">spanish cif number</span></span>
  
<span data-ttu-id="fea10-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="fea10-862">tax file number</span></span>
  
<span data-ttu-id="fea10-863">Spagnolo CIF No</span><span class="sxs-lookup"><span data-stu-id="fea10-863">spanish cif no</span></span>
  
<span data-ttu-id="fea10-864">tax no</span><span class="sxs-lookup"><span data-stu-id="fea10-864">tax no</span></span>
  
<span data-ttu-id="fea10-865">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-865">tax number</span></span>
  
<span data-ttu-id="fea10-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-866">taxid#</span></span>
  
<span data-ttu-id="fea10-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="fea10-867">taxno#</span></span>
  
<span data-ttu-id="fea10-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="fea10-868">cifid#</span></span>
  
<span data-ttu-id="fea10-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="fea10-869">spanishcifid#</span></span>
  
<span data-ttu-id="fea10-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="fea10-870">spanishcifno#</span></span>
  
<span data-ttu-id="fea10-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="fea10-871">número de contribuyente</span></span>
  
<span data-ttu-id="fea10-872">número de Impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="fea10-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="fea10-873">número de Identificación Fiscal</span><span class="sxs-lookup"><span data-stu-id="fea10-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="fea10-874">número CIF</span><span class="sxs-lookup"><span data-stu-id="fea10-874">cif número</span></span>
  
<span data-ttu-id="fea10-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="fea10-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="fea10-876">Svezia</span><span class="sxs-lookup"><span data-stu-id="fea10-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="fea10-877">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-877">Format</span></span>

<span data-ttu-id="fea10-878">Dieci cifre e un simbolo nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="fea10-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-879">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-879">Pattern</span></span>

<span data-ttu-id="fea10-880">Dieci cifre e un simbolo:</span><span class="sxs-lookup"><span data-stu-id="fea10-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="fea10-881">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="fea10-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="fea10-882">Segno di addizione, segno meno o barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="fea10-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="fea10-883">Tre cifre che rendono il numero di identificazione univoco dove:</span><span class="sxs-lookup"><span data-stu-id="fea10-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="fea10-884">Per i numeri emessi prima del 1990, la settima e la terza cifra identificano la Contea di nascita o gli stranieri nati</span><span class="sxs-lookup"><span data-stu-id="fea10-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="fea10-885">La cifra nella nona posizione indica il sesso per il maschio o per la femmina.</span><span class="sxs-lookup"><span data-stu-id="fea10-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="fea10-886">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="fea10-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fea10-887">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-887">Checksum</span></span>

<span data-ttu-id="fea10-888">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-889">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-889">Definition</span></span>

<span data-ttu-id="fea10-890">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-891">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-892">Viene trovata una `Keywords_sweden_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="fea10-893">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-894">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-895">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="fea10-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-897">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-897">tax id</span></span>
  
<span data-ttu-id="fea10-898">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="fea10-898">tax id no.</span></span>
  
<span data-ttu-id="fea10-899">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-899">tax id number</span></span>
  
<span data-ttu-id="fea10-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="fea10-900">tax identification</span></span>
  
<span data-ttu-id="fea10-901">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="fea10-901">tax identification#</span></span>
  
<span data-ttu-id="fea10-902">tassa no.</span><span class="sxs-lookup"><span data-stu-id="fea10-902">tax no.</span></span>
  
<span data-ttu-id="fea10-903">imposte #</span><span class="sxs-lookup"><span data-stu-id="fea10-903">tax#</span></span>
  
<span data-ttu-id="fea10-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-904">taxid#</span></span>
  
<span data-ttu-id="fea10-905">file fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-905">tax file</span></span>
  
<span data-ttu-id="fea10-906">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="fea10-906">tax file no.</span></span>
  
<span data-ttu-id="fea10-907">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="fea10-907">personal id number</span></span>
  
<span data-ttu-id="fea10-908">ID pattinat Nummer</span><span class="sxs-lookup"><span data-stu-id="fea10-908">skatt id nummer</span></span>
  
<span data-ttu-id="fea10-909">Identifikation skatet</span><span class="sxs-lookup"><span data-stu-id="fea10-909">skatt identifikation</span></span>
  
<span data-ttu-id="fea10-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="fea10-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="fea10-911">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="fea10-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="fea10-912">Formato</span><span class="sxs-lookup"><span data-stu-id="fea10-912">Format</span></span>

<span data-ttu-id="fea10-913">Riferimento per i contribuenti unici (UTR): 10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="fea10-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="fea10-914">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="fea10-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="fea10-915">Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="fea10-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fea10-916">Modello</span><span class="sxs-lookup"><span data-stu-id="fea10-916">Pattern</span></span>

<span data-ttu-id="fea10-917">Riferimento per i contribuenti unici (UTR): 10 cifre</span><span class="sxs-lookup"><span data-stu-id="fea10-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="fea10-918">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="fea10-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="fea10-919">Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="fea10-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fea10-920">Checksum</span><span class="sxs-lookup"><span data-stu-id="fea10-920">Checksum</span></span>

<span data-ttu-id="fea10-921">Sì</span><span class="sxs-lookup"><span data-stu-id="fea10-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="fea10-922">Definizione</span><span class="sxs-lookup"><span data-stu-id="fea10-922">Definition</span></span>

<span data-ttu-id="fea10-923">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fea10-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fea10-924">La funzione `Func_uk_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fea10-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fea10-925">Viene trovata una `Keywords_uk_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fea10-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fea10-926">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fea10-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="fea10-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="fea10-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="fea10-928">tax id</span><span class="sxs-lookup"><span data-stu-id="fea10-928">tax id</span></span>
  
<span data-ttu-id="fea10-929">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="fea10-929">tax id no.</span></span>
  
<span data-ttu-id="fea10-930">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-930">tax id number</span></span>
  
<span data-ttu-id="fea10-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="fea10-931">tax identification</span></span>
  
<span data-ttu-id="fea10-932">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="fea10-932">tax identification#</span></span>
  
<span data-ttu-id="fea10-933">tassa no.</span><span class="sxs-lookup"><span data-stu-id="fea10-933">tax no.</span></span>
  
<span data-ttu-id="fea10-934">imposte #</span><span class="sxs-lookup"><span data-stu-id="fea10-934">tax#</span></span>
  
<span data-ttu-id="fea10-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="fea10-935">taxid#</span></span>
  
<span data-ttu-id="fea10-936">file fiscale</span><span class="sxs-lookup"><span data-stu-id="fea10-936">tax file</span></span>
  
<span data-ttu-id="fea10-937">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="fea10-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fea10-938">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fea10-938">See also</span></span>

[<span data-ttu-id="fea10-939">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="fea10-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

