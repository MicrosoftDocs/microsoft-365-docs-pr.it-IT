---
title: Numero di identificazione fiscale dell'Unione europea
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 5f779974266045d7099b599700c7168162d9d81e
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938672"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="05ba7-104">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="05ba7-104">EU Tax Identification Number</span></span>

<span data-ttu-id="05ba7-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale (TIN) dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="05ba7-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="05ba7-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="05ba7-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="05ba7-107">Austria</span><span class="sxs-lookup"><span data-stu-id="05ba7-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-108">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-108">Format</span></span>

<span data-ttu-id="05ba7-109">Nove cifre con trattino e barra di inoltro opzionali</span><span class="sxs-lookup"><span data-stu-id="05ba7-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-110">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-110">Pattern</span></span>

<span data-ttu-id="05ba7-111">Nove cifre con trattino e barra di inoltro facoltativi:</span><span class="sxs-lookup"><span data-stu-id="05ba7-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="05ba7-112">Due cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-112">Two digits</span></span> 
    
- <span data-ttu-id="05ba7-113">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="05ba7-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="05ba7-114">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-114">Three digits</span></span>
    
- <span data-ttu-id="05ba7-115">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="05ba7-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="05ba7-116">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-117">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-117">Checksum</span></span>

<span data-ttu-id="05ba7-118">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-119">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-119">Definition</span></span>

<span data-ttu-id="05ba7-120">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-121">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-122">Viene trovata una `Keywords_austria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-123">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-124">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-125">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="05ba7-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-127">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-127">tax number</span></span>
  
<span data-ttu-id="05ba7-128">numero</span><span class="sxs-lookup"><span data-stu-id="05ba7-128">number</span></span>
  
<span data-ttu-id="05ba7-129">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-129">tax registration number</span></span>
  
<span data-ttu-id="05ba7-130">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-130">tax id</span></span>
  
<span data-ttu-id="05ba7-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="05ba7-131">st.nr.</span></span>
  
<span data-ttu-id="05ba7-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="05ba7-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="05ba7-133">Belgio</span><span class="sxs-lookup"><span data-stu-id="05ba7-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-134">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-134">Format</span></span>

<span data-ttu-id="05ba7-135">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-136">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-136">Pattern</span></span>

<span data-ttu-id="05ba7-137">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="05ba7-137">11 digits:</span></span>
  
- <span data-ttu-id="05ba7-138">Due cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-138">Two digits</span></span>
    
- <span data-ttu-id="05ba7-139">"0" o "1"</span><span class="sxs-lookup"><span data-stu-id="05ba7-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="05ba7-140">Una cifra</span><span class="sxs-lookup"><span data-stu-id="05ba7-140">One digit</span></span>
    
- <span data-ttu-id="05ba7-141">"0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="05ba7-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="05ba7-142">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-143">Checksum</span></span>

<span data-ttu-id="05ba7-144">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="05ba7-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-145">Definition</span></span>

<span data-ttu-id="05ba7-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-147">L'espressione `Regex_belgium_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-148">Viene trovata una `Keywords_belgium_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05ba7-149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="05ba7-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-151">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-151">tax number</span></span>
  
<span data-ttu-id="05ba7-152">numero di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="05ba7-152">national registration number</span></span>
  
<span data-ttu-id="05ba7-153">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-153">tax registration number</span></span>
  
<span data-ttu-id="05ba7-154">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-154">tax id</span></span>
  
<span data-ttu-id="05ba7-155">NIF</span><span class="sxs-lookup"><span data-stu-id="05ba7-155">nif</span></span>
  
<span data-ttu-id="05ba7-156">NIF #</span><span class="sxs-lookup"><span data-stu-id="05ba7-156">nif#</span></span>
  
<span data-ttu-id="05ba7-157">numéro de Registre National</span><span class="sxs-lookup"><span data-stu-id="05ba7-157">numéro de registre national</span></span>
  
<span data-ttu-id="05ba7-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="05ba7-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="05ba7-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-160">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-160">Format</span></span>

<span data-ttu-id="05ba7-161">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-162">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-162">Pattern</span></span>

<span data-ttu-id="05ba7-163">10 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05ba7-164">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-164">Checksum</span></span>

<span data-ttu-id="05ba7-165">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-166">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-166">Definition</span></span>

<span data-ttu-id="05ba7-167">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-168">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-169">Viene trovata una `Keywords_bulgaria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-170">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-171">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-172">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="05ba7-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-174">bucn</span><span class="sxs-lookup"><span data-stu-id="05ba7-174">bucn</span></span>
  
<span data-ttu-id="05ba7-175">numero civile uniforme</span><span class="sxs-lookup"><span data-stu-id="05ba7-175">uniform civil number</span></span>
  
<span data-ttu-id="05ba7-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="05ba7-176">bucn#</span></span>
  
<span data-ttu-id="05ba7-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="05ba7-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="05ba7-178">ID civile uniforme</span><span class="sxs-lookup"><span data-stu-id="05ba7-178">uniform civil id</span></span>
  
<span data-ttu-id="05ba7-179">uniforme civile No</span><span class="sxs-lookup"><span data-stu-id="05ba7-179">uniform civil no</span></span>
  
<span data-ttu-id="05ba7-180">EGN</span><span class="sxs-lookup"><span data-stu-id="05ba7-180">egn</span></span>
  
<span data-ttu-id="05ba7-181">numero civile uniforme bulgaro</span><span class="sxs-lookup"><span data-stu-id="05ba7-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="05ba7-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-182">uniformcivilno#</span></span>
  
<span data-ttu-id="05ba7-183">EGN #</span><span class="sxs-lookup"><span data-stu-id="05ba7-183">egn#</span></span>
  
<span data-ttu-id="05ba7-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="05ba7-184">униформ граждански номер</span></span>
  
<span data-ttu-id="05ba7-185">ID униформ</span><span class="sxs-lookup"><span data-stu-id="05ba7-185">униформ id</span></span>
  
<span data-ttu-id="05ba7-186">ID граждански униформ</span><span class="sxs-lookup"><span data-stu-id="05ba7-186">униформ граждански id</span></span>
  
<span data-ttu-id="05ba7-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="05ba7-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="05ba7-188">Croazia</span><span class="sxs-lookup"><span data-stu-id="05ba7-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-189">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-189">Format</span></span>

<span data-ttu-id="05ba7-190">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-191">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-191">Pattern</span></span>

<span data-ttu-id="05ba7-192">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="05ba7-192">11 digits:</span></span>
  
- <span data-ttu-id="05ba7-193">Dieci cifre, scelte casualmente</span><span class="sxs-lookup"><span data-stu-id="05ba7-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="05ba7-194">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="05ba7-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-195">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-195">Checksum</span></span>

<span data-ttu-id="05ba7-196">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-197">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-197">Definition</span></span>

<span data-ttu-id="05ba7-198">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-199">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-200">Viene trovata una `Keywords_croatia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-202">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-203">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="05ba7-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-205">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-205">tax number</span></span>
  
<span data-ttu-id="05ba7-206">imposte</span><span class="sxs-lookup"><span data-stu-id="05ba7-206">tax</span></span>
  
<span data-ttu-id="05ba7-207">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-207">tax id</span></span>
  
<span data-ttu-id="05ba7-208">OID</span><span class="sxs-lookup"><span data-stu-id="05ba7-208">oid</span></span>
  
<span data-ttu-id="05ba7-209">OID #</span><span class="sxs-lookup"><span data-stu-id="05ba7-209">oid#</span></span>
  
<span data-ttu-id="05ba7-210">Porezni broj</span><span class="sxs-lookup"><span data-stu-id="05ba7-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="05ba7-211">Cipro</span><span class="sxs-lookup"><span data-stu-id="05ba7-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-212">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-212">Format</span></span>

<span data-ttu-id="05ba7-213">Otto cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="05ba7-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-214">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-214">Pattern</span></span>

<span data-ttu-id="05ba7-215">Otto cifre e una lettera:</span><span class="sxs-lookup"><span data-stu-id="05ba7-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="05ba7-216">Un "0"</span><span class="sxs-lookup"><span data-stu-id="05ba7-216">A "0"</span></span> 
    
- <span data-ttu-id="05ba7-217">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-217">Seven digits</span></span>
    
- <span data-ttu-id="05ba7-218">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-219">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-219">Checksum</span></span>

<span data-ttu-id="05ba7-220">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="05ba7-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-221">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-221">Definition</span></span>

<span data-ttu-id="05ba7-222">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-223">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-224">Viene trovata una `Keywords_cyprus_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-225">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-226">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="05ba7-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-229">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-229">tax number</span></span>
  
<span data-ttu-id="05ba7-230">imposte</span><span class="sxs-lookup"><span data-stu-id="05ba7-230">tax</span></span>
  
<span data-ttu-id="05ba7-231">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-231">tax id</span></span>
  
<span data-ttu-id="05ba7-232">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-232">tax identification code</span></span>
  
<span data-ttu-id="05ba7-233">TIC</span><span class="sxs-lookup"><span data-stu-id="05ba7-233">tic</span></span>
  
<span data-ttu-id="05ba7-234">TIC #</span><span class="sxs-lookup"><span data-stu-id="05ba7-234">tic#</span></span>
  
<span data-ttu-id="05ba7-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="05ba7-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="05ba7-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="05ba7-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="05ba7-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="05ba7-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="05ba7-238">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="05ba7-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-239">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-239">Format</span></span>

<span data-ttu-id="05ba7-240">Nove o dieci cifre con una barra rovesciata facoltativa</span><span class="sxs-lookup"><span data-stu-id="05ba7-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-241">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-241">Pattern</span></span>

<span data-ttu-id="05ba7-242">Nove o dieci cifre con un backslash facoltativo:</span><span class="sxs-lookup"><span data-stu-id="05ba7-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="05ba7-243">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-243">Six digits</span></span> 
    
- <span data-ttu-id="05ba7-244">Una barra rovesciata (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="05ba7-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="05ba7-245">Tre o quattro cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-246">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-246">Checksum</span></span>

<span data-ttu-id="05ba7-247">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="05ba7-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-248">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-248">Definition</span></span>

<span data-ttu-id="05ba7-249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-250">L'espressione `Regex_czech_republic_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-251">Viene trovata una `Keywords_czech_republic_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05ba7-252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="05ba7-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-254">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-254">tax number</span></span>
  
<span data-ttu-id="05ba7-255">imposte</span><span class="sxs-lookup"><span data-stu-id="05ba7-255">tax</span></span>
  
<span data-ttu-id="05ba7-256">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-256">tax id</span></span>
  
<span data-ttu-id="05ba7-257">numero personale</span><span class="sxs-lookup"><span data-stu-id="05ba7-257">personal number</span></span>
  
<span data-ttu-id="05ba7-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="05ba7-258">daňové číslo</span></span>
  
<span data-ttu-id="05ba7-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="05ba7-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="05ba7-260">Danimarca</span><span class="sxs-lookup"><span data-stu-id="05ba7-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-261">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-261">Format</span></span>

<span data-ttu-id="05ba7-262">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="05ba7-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-263">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-263">Pattern</span></span>

<span data-ttu-id="05ba7-264">Dieci cifre contenenti un segno meno:</span><span class="sxs-lookup"><span data-stu-id="05ba7-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="05ba7-265">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="05ba7-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="05ba7-266">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="05ba7-266">A hyphen</span></span>
    
- <span data-ttu-id="05ba7-267">Quattro cifre che corrispondono a un numero di sequenza in cui la prima cifra corrisponde al secolo di nascita e l'ultima cifra corrisponde al sesso dell'individuo (dispari per il maschio e anche per le femmine)</span><span class="sxs-lookup"><span data-stu-id="05ba7-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-268">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-268">Checksum</span></span>

<span data-ttu-id="05ba7-269">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-270">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-270">Definition</span></span>

<span data-ttu-id="05ba7-271">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-272">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-273">Viene trovata una `Keywords_denmark_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-275">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-276">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="05ba7-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-278">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-278">tax number</span></span>
  
<span data-ttu-id="05ba7-279">imposte</span><span class="sxs-lookup"><span data-stu-id="05ba7-279">tax</span></span>
  
<span data-ttu-id="05ba7-280">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-280">tax id</span></span>
  
<span data-ttu-id="05ba7-281">numero CPR</span><span class="sxs-lookup"><span data-stu-id="05ba7-281">cpr number</span></span>
  
<span data-ttu-id="05ba7-282">CPR #</span><span class="sxs-lookup"><span data-stu-id="05ba7-282">cpr#</span></span>
  
<span data-ttu-id="05ba7-283">Nummer di pattinaggio</span><span class="sxs-lookup"><span data-stu-id="05ba7-283">skat nummer</span></span>
  
<span data-ttu-id="05ba7-284">ID pattina</span><span class="sxs-lookup"><span data-stu-id="05ba7-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="05ba7-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="05ba7-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-286">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-286">Format</span></span>

<span data-ttu-id="05ba7-287">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-288">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-288">Pattern</span></span>

<span data-ttu-id="05ba7-289">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="05ba7-289">11 digits:</span></span>
  
-  <span data-ttu-id="05ba7-290">Una cifra che corrisponde al sesso e al secolo del parto, in cui un numero dispari indica il maschio e il numero pari indica la femmina come segue: 1,2 per il XIX secolo; 3,4 per il XX secolo; e 5,6 per il XXI secolo</span><span class="sxs-lookup"><span data-stu-id="05ba7-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="05ba7-291">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="05ba7-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="05ba7-292">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="05ba7-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="05ba7-293">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="05ba7-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-294">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-294">Checksum</span></span>

<span data-ttu-id="05ba7-295">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-296">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-296">Definition</span></span>

<span data-ttu-id="05ba7-297">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-298">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-299">Viene trovata una `Keywords_estonia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-300">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-301">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-302">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="05ba7-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-304">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-304">tax number</span></span>
  
<span data-ttu-id="05ba7-305">imposte</span><span class="sxs-lookup"><span data-stu-id="05ba7-305">tax</span></span>
  
<span data-ttu-id="05ba7-306">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-306">tax id</span></span>
  
<span data-ttu-id="05ba7-307">codice personale</span><span class="sxs-lookup"><span data-stu-id="05ba7-307">personal code</span></span>
  
<span data-ttu-id="05ba7-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="05ba7-308">maksunumber</span></span>
  
<span data-ttu-id="05ba7-309">ID maksu</span><span class="sxs-lookup"><span data-stu-id="05ba7-309">maksu id</span></span>
  
<span data-ttu-id="05ba7-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="05ba7-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="05ba7-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="05ba7-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-312">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-312">Format</span></span>

<span data-ttu-id="05ba7-313">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno</span><span class="sxs-lookup"><span data-stu-id="05ba7-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-314">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-314">Pattern</span></span>

<span data-ttu-id="05ba7-315">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno:</span><span class="sxs-lookup"><span data-stu-id="05ba7-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="05ba7-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-316">Six digits</span></span>
    
- <span data-ttu-id="05ba7-317">Uno dei seguenti: un segno più, un segno di sottrazione o la lettera "A" (senza distinzione tra maiuscole/minuscole), in cui il segno più significa Nato tra 1800-1899, il segno meno significa Nato tra 1900-1999 e "A" significa Nato 2000 e dopo</span><span class="sxs-lookup"><span data-stu-id="05ba7-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="05ba7-318">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-318">Three digits</span></span>
    
- <span data-ttu-id="05ba7-319">Una lettera o un numero</span><span class="sxs-lookup"><span data-stu-id="05ba7-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-320">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-320">Checksum</span></span>

<span data-ttu-id="05ba7-321">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-322">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-322">Definition</span></span>

<span data-ttu-id="05ba7-323">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-324">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-325">Viene trovata una `Keywords_finland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-326">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-327">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-328">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="05ba7-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-330">identification number</span><span class="sxs-lookup"><span data-stu-id="05ba7-330">identification number</span></span>
  
<span data-ttu-id="05ba7-331">ID personale</span><span class="sxs-lookup"><span data-stu-id="05ba7-331">personal id</span></span>
  
<span data-ttu-id="05ba7-332">numero di identità</span><span class="sxs-lookup"><span data-stu-id="05ba7-332">identity number</span></span>
  
<span data-ttu-id="05ba7-333">numero di identificazione nazionale finlandese</span><span class="sxs-lookup"><span data-stu-id="05ba7-333">finnish national id number</span></span>
  
<span data-ttu-id="05ba7-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="05ba7-334">personalidnumber#</span></span>
  
<span data-ttu-id="05ba7-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="05ba7-335">national identification number</span></span>
  
<span data-ttu-id="05ba7-336">numero ID</span><span class="sxs-lookup"><span data-stu-id="05ba7-336">id number</span></span>
  
<span data-ttu-id="05ba7-337">ID nazionale No.</span><span class="sxs-lookup"><span data-stu-id="05ba7-337">national id no.</span></span>
  
<span data-ttu-id="05ba7-338">numero ID nazionale</span><span class="sxs-lookup"><span data-stu-id="05ba7-338">national id number</span></span>
  
<span data-ttu-id="05ba7-339">ID No</span><span class="sxs-lookup"><span data-stu-id="05ba7-339">id no</span></span>
  
<span data-ttu-id="05ba7-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="05ba7-340">tunnistenumero</span></span>
  
<span data-ttu-id="05ba7-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="05ba7-341">henkilötunnus</span></span>
  
<span data-ttu-id="05ba7-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="05ba7-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="05ba7-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="05ba7-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="05ba7-344">numero identiteetti</span><span class="sxs-lookup"><span data-stu-id="05ba7-344">identiteetti numero</span></span>
  
<span data-ttu-id="05ba7-345">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="05ba7-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="05ba7-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="05ba7-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="05ba7-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="05ba7-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="05ba7-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="05ba7-348">tunnusnumero</span></span>
  
<span data-ttu-id="05ba7-349">Kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="05ba7-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="05ba7-350">Francia</span><span class="sxs-lookup"><span data-stu-id="05ba7-350">France</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-351">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-351">Format</span></span>

<span data-ttu-id="05ba7-352">13 cifre per gli utenti e nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="05ba7-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-353">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-353">Pattern</span></span>

<span data-ttu-id="05ba7-354">13 cifre per gli utenti:</span><span class="sxs-lookup"><span data-stu-id="05ba7-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="05ba7-355">Una cifra che deve essere 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="05ba7-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="05ba7-356">12 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-356">12 digits</span></span>
    
<span data-ttu-id="05ba7-357">Nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="05ba7-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05ba7-358">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-358">Checksum</span></span>

<span data-ttu-id="05ba7-359">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="05ba7-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-360">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-360">Definition</span></span>

<span data-ttu-id="05ba7-361">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-362">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-363">Viene trovata una `Keywords_france_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-365">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-366">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="05ba7-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-368">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-368">tax identification number</span></span>
  
<span data-ttu-id="05ba7-369">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-369">tax number</span></span>
  
<span data-ttu-id="05ba7-370">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-370">tax id</span></span>
  
<span data-ttu-id="05ba7-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="05ba7-372">Germania</span><span class="sxs-lookup"><span data-stu-id="05ba7-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-373">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-373">Format</span></span>

<span data-ttu-id="05ba7-374">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-375">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-375">Pattern</span></span>

<span data-ttu-id="05ba7-376">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="05ba7-376">11 digits :</span></span>
  
-  <span data-ttu-id="05ba7-377">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-377">Ten digits</span></span> 
    
- <span data-ttu-id="05ba7-378">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="05ba7-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-379">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-379">Checksum</span></span>

<span data-ttu-id="05ba7-380">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-381">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-381">Definition</span></span>

<span data-ttu-id="05ba7-382">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-383">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-384">Viene trovata una `Keywords_germany_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-385">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-386">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="05ba7-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-389">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-389">tax number</span></span>
  
<span data-ttu-id="05ba7-390">tassa no.</span><span class="sxs-lookup"><span data-stu-id="05ba7-390">tax no.</span></span>
  
<span data-ttu-id="05ba7-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-391">taxno#</span></span>
  
<span data-ttu-id="05ba7-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="05ba7-392">taxnumber#</span></span>
  
<span data-ttu-id="05ba7-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="05ba7-393">taxnumber</span></span>
  
<span data-ttu-id="05ba7-394">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-394">tax id</span></span>
  
<span data-ttu-id="05ba7-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-395">taxid#</span></span>
  
<span data-ttu-id="05ba7-396">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-396">tax identification number</span></span>
  
<span data-ttu-id="05ba7-397">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="05ba7-397">tax identification no.</span></span>
  
<span data-ttu-id="05ba7-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="05ba7-398">steuernummer</span></span>
  
<span data-ttu-id="05ba7-399">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="05ba7-399">steuer id</span></span>
  
<span data-ttu-id="05ba7-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="05ba7-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="05ba7-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="05ba7-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-402">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-402">Format</span></span>

<span data-ttu-id="05ba7-403">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-404">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-404">Pattern</span></span>

<span data-ttu-id="05ba7-405">9 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05ba7-406">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-406">Checksum</span></span>

<span data-ttu-id="05ba7-407">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="05ba7-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-408">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-408">Definition</span></span>

<span data-ttu-id="05ba7-409">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-410">L'espressione `Regex_greece_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-411">Viene trovata una `Keywords_greece_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05ba7-412">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="05ba7-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-414">AFM</span><span class="sxs-lookup"><span data-stu-id="05ba7-414">afm</span></span>
  
<span data-ttu-id="05ba7-415">latta</span><span class="sxs-lookup"><span data-stu-id="05ba7-415">tin</span></span>
  
<span data-ttu-id="05ba7-416">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="05ba7-416">tax id no.</span></span>
  
<span data-ttu-id="05ba7-417">ID IVA No</span><span class="sxs-lookup"><span data-stu-id="05ba7-417">tax id no</span></span>
  
<span data-ttu-id="05ba7-418">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-418">tax identification number</span></span>
  
<span data-ttu-id="05ba7-419">numero del registro di sistema fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-419">tax registry number</span></span>
  
<span data-ttu-id="05ba7-420">Registro fiscale No.</span><span class="sxs-lookup"><span data-stu-id="05ba7-420">tax registry no.</span></span>
  
<span data-ttu-id="05ba7-421">AFM #</span><span class="sxs-lookup"><span data-stu-id="05ba7-421">afm#</span></span>
  
<span data-ttu-id="05ba7-422">latta #</span><span class="sxs-lookup"><span data-stu-id="05ba7-422">tin#</span></span>
  
<span data-ttu-id="05ba7-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-423">taxidno#</span></span>
  
<span data-ttu-id="05ba7-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-424">taxregistryno#</span></span>
  
<span data-ttu-id="05ba7-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="05ba7-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="05ba7-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="05ba7-426">aφμ</span></span>
  
<span data-ttu-id="05ba7-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="05ba7-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="05ba7-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="05ba7-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="05ba7-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="05ba7-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="05ba7-430">Ungheria</span><span class="sxs-lookup"><span data-stu-id="05ba7-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-431">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-431">Format</span></span>

<span data-ttu-id="05ba7-432">Dieci cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-433">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-433">Pattern</span></span>

<span data-ttu-id="05ba7-434">Dieci cifre:</span><span class="sxs-lookup"><span data-stu-id="05ba7-434">Ten digits:</span></span>
  
-  <span data-ttu-id="05ba7-435">Una cifra che deve essere "8"</span><span class="sxs-lookup"><span data-stu-id="05ba7-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="05ba7-436">Cinque cifre che corrispondono al numero di giorni compresi tra la data 01/01/1867 e la data di nascita dell'individuo</span><span class="sxs-lookup"><span data-stu-id="05ba7-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="05ba7-437">Tre cifre che corrispondono al numero generato dalla possibilità di distinguere gli individui nati nello stesso giorno</span><span class="sxs-lookup"><span data-stu-id="05ba7-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="05ba7-438">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="05ba7-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-439">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-439">Checksum</span></span>

<span data-ttu-id="05ba7-440">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-441">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-441">Definition</span></span>

<span data-ttu-id="05ba7-442">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-443">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-444">Viene trovata una `Keywords_hungary_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-445">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-446">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-447">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="05ba7-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-449">numero di identificazione fiscale ungherese</span><span class="sxs-lookup"><span data-stu-id="05ba7-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="05ba7-450">Tin ungherese</span><span class="sxs-lookup"><span data-stu-id="05ba7-450">hungarian tin</span></span>
  
<span data-ttu-id="05ba7-451">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-451">tax id number</span></span>
  
<span data-ttu-id="05ba7-452">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="05ba7-452">vat number</span></span>
  
<span data-ttu-id="05ba7-453">autorità tributaria No</span><span class="sxs-lookup"><span data-stu-id="05ba7-453">tax authority no</span></span>
  
<span data-ttu-id="05ba7-454">numero dell'identità fiscale dell'ID fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-454">tax id tax identity number</span></span>
  
<span data-ttu-id="05ba7-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="05ba7-455">taxidnumber#</span></span>
  
<span data-ttu-id="05ba7-456">latta #</span><span class="sxs-lookup"><span data-stu-id="05ba7-456">tin#</span></span>
  
<span data-ttu-id="05ba7-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="05ba7-457">hungatiantin#</span></span>
  
<span data-ttu-id="05ba7-458">identificazione fiscale No</span><span class="sxs-lookup"><span data-stu-id="05ba7-458">tax identification no</span></span>
  
<span data-ttu-id="05ba7-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-459">taxidno#</span></span>
  
<span data-ttu-id="05ba7-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="05ba7-460">adóazonosító szám</span></span>
  
<span data-ttu-id="05ba7-461">adószám</span><span class="sxs-lookup"><span data-stu-id="05ba7-461">adószám</span></span>
  
<span data-ttu-id="05ba7-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="05ba7-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="05ba7-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="05ba7-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-464">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-464">Format</span></span>

<span data-ttu-id="05ba7-465">Sette cifre seguite da una lettera senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-466">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-466">Pattern</span></span>

<span data-ttu-id="05ba7-467">Sette cifre seguite da una lettera:</span><span class="sxs-lookup"><span data-stu-id="05ba7-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="05ba7-468">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-468">Seven digits</span></span> 
    
- <span data-ttu-id="05ba7-469">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-470">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-470">Checksum</span></span>

<span data-ttu-id="05ba7-471">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="05ba7-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-472">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-472">Definition</span></span>

<span data-ttu-id="05ba7-473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-474">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-475">Viene trovata una `Keywords_ireland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-476">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-477">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="05ba7-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-480">servizio pubblico no</span><span class="sxs-lookup"><span data-stu-id="05ba7-480">public service no</span></span>
  
<span data-ttu-id="05ba7-481">servizio pubblico personale No</span><span class="sxs-lookup"><span data-stu-id="05ba7-481">personal public service no</span></span>
  
<span data-ttu-id="05ba7-482">PPS No</span><span class="sxs-lookup"><span data-stu-id="05ba7-482">pps no</span></span>
  
<span data-ttu-id="05ba7-483">servizio personale No</span><span class="sxs-lookup"><span data-stu-id="05ba7-483">personal service no</span></span>
  
<span data-ttu-id="05ba7-484">servizio PPS No</span><span class="sxs-lookup"><span data-stu-id="05ba7-484">pps service no</span></span>
  
<span data-ttu-id="05ba7-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-485">ppsno#</span></span>
  
<span data-ttu-id="05ba7-486">Irish PPS No</span><span class="sxs-lookup"><span data-stu-id="05ba7-486">irish pps no</span></span>
  
<span data-ttu-id="05ba7-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-487">publicserviceno#</span></span>
  
<span data-ttu-id="05ba7-488">numero di servizio pubblico personale</span><span class="sxs-lookup"><span data-stu-id="05ba7-488">personal public service number</span></span>
  
<span data-ttu-id="05ba7-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="05ba7-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="05ba7-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="05ba7-490">pps uimh</span></span>
  
<span data-ttu-id="05ba7-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="05ba7-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="05ba7-492">Italia</span><span class="sxs-lookup"><span data-stu-id="05ba7-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-493">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-493">Format</span></span>

<span data-ttu-id="05ba7-494">16 lettere e cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="05ba7-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-495">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-495">Pattern</span></span>

<span data-ttu-id="05ba7-496">16 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="05ba7-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="05ba7-497">Tre lettere che corrispondono alle prime tre consonanti del nome di famiglia</span><span class="sxs-lookup"><span data-stu-id="05ba7-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="05ba7-498">Tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome</span><span class="sxs-lookup"><span data-stu-id="05ba7-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="05ba7-499">Due cifre che corrispondono alle ultime cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="05ba7-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="05ba7-500">Una cifra corrispondente al mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)</span><span class="sxs-lookup"><span data-stu-id="05ba7-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="05ba7-501">Due cifre che corrispondono al giorno del mese di nascita in cui 40 viene aggiunto al giorno di nascita per le femmine per differenziare dai maschi</span><span class="sxs-lookup"><span data-stu-id="05ba7-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="05ba7-502">Quattro cifre che corrispondono a un codice di area specifico per il comune in cui è nata la persona: vengono utilizzati codici a livello nazionale per i paesi esteri</span><span class="sxs-lookup"><span data-stu-id="05ba7-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="05ba7-503">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="05ba7-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-504">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-504">Checksum</span></span>

<span data-ttu-id="05ba7-505">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-506">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-506">Definition</span></span>

<span data-ttu-id="05ba7-507">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-508">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-509">Viene trovata una `Keywords_italy_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-510">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-511">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-512">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="05ba7-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-514">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-514">tax number</span></span>
  
<span data-ttu-id="05ba7-515">tassa no.</span><span class="sxs-lookup"><span data-stu-id="05ba7-515">tax no.</span></span>
  
<span data-ttu-id="05ba7-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-516">taxno#</span></span>
  
<span data-ttu-id="05ba7-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="05ba7-517">taxnumber#</span></span>
  
<span data-ttu-id="05ba7-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="05ba7-518">taxnumber</span></span>
  
<span data-ttu-id="05ba7-519">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-519">tax id</span></span>
  
<span data-ttu-id="05ba7-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-520">taxid#</span></span>
  
<span data-ttu-id="05ba7-521">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-521">fiscal code</span></span>
  
<span data-ttu-id="05ba7-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="05ba7-523">Lettonia</span><span class="sxs-lookup"><span data-stu-id="05ba7-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-524">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-524">Format</span></span>

<span data-ttu-id="05ba7-525">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-526">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-526">Pattern</span></span>

<span data-ttu-id="05ba7-527">11 cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="05ba7-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="05ba7-528">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="05ba7-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="05ba7-529">Una cifra che corrisponde al secolo di nascita dove "0" corrisponde al XIX secolo, "1" corrisponde al 20 ° secolo e "2" corrisponde al XXI secolo</span><span class="sxs-lookup"><span data-stu-id="05ba7-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="05ba7-530">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-531">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-531">Checksum</span></span>

<span data-ttu-id="05ba7-532">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-533">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-533">Definition</span></span>

<span data-ttu-id="05ba7-534">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-535">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-536">Viene trovata una `Keywords_latvia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-537">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-538">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-539">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="05ba7-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-541">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-541">tax number</span></span>
  
<span data-ttu-id="05ba7-542">tassa no.</span><span class="sxs-lookup"><span data-stu-id="05ba7-542">tax no.</span></span>
  
<span data-ttu-id="05ba7-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-543">taxno#</span></span>
  
<span data-ttu-id="05ba7-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="05ba7-544">taxnumber#</span></span>
  
<span data-ttu-id="05ba7-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="05ba7-545">taxnumber</span></span>
  
<span data-ttu-id="05ba7-546">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-546">tax id</span></span>
  
<span data-ttu-id="05ba7-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-547">taxid#</span></span>
  
<span data-ttu-id="05ba7-548">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-548">tax identification number</span></span>
  
<span data-ttu-id="05ba7-549">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="05ba7-549">tax identification no.</span></span>
  
<span data-ttu-id="05ba7-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="05ba7-550">nodokļa numurs</span></span>
  
<span data-ttu-id="05ba7-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="05ba7-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="05ba7-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="05ba7-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="05ba7-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="05ba7-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-554">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-554">Format</span></span>

<span data-ttu-id="05ba7-555">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-556">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-556">Pattern</span></span>

<span data-ttu-id="05ba7-557">11 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05ba7-558">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-558">Checksum</span></span>

<span data-ttu-id="05ba7-559">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="05ba7-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-560">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-560">Definition</span></span>

<span data-ttu-id="05ba7-561">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-562">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-563">Viene trovata una `Keywords_lithuania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-564">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-565">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-566">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="05ba7-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-568">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-568">tax number</span></span>
  
<span data-ttu-id="05ba7-569">tassa no.</span><span class="sxs-lookup"><span data-stu-id="05ba7-569">tax no.</span></span>
  
<span data-ttu-id="05ba7-570">tax no #</span><span class="sxs-lookup"><span data-stu-id="05ba7-570">tax no#</span></span>
  
<span data-ttu-id="05ba7-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="05ba7-571">taxnumber#</span></span>
  
<span data-ttu-id="05ba7-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="05ba7-572">taxnumber</span></span>
  
<span data-ttu-id="05ba7-573">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-573">tax id</span></span>
  
<span data-ttu-id="05ba7-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-574">taxid#</span></span>
  
<span data-ttu-id="05ba7-575">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-575">tax identification number</span></span>
  
<span data-ttu-id="05ba7-576">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="05ba7-576">tax identification no.</span></span>
  
<span data-ttu-id="05ba7-577">ID mokesčių</span><span class="sxs-lookup"><span data-stu-id="05ba7-577">mokesčių id</span></span>
  
<span data-ttu-id="05ba7-578">numeri mokesčių</span><span class="sxs-lookup"><span data-stu-id="05ba7-578">mokesčių numeris</span></span>
  
<span data-ttu-id="05ba7-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="05ba7-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="05ba7-580">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="05ba7-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-581">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-581">Format</span></span>

<span data-ttu-id="05ba7-582">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-583">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-583">Pattern</span></span>

<span data-ttu-id="05ba7-584">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="05ba7-584">13 digits:</span></span>
  
-  <span data-ttu-id="05ba7-585">11 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-585">11 digits</span></span> 
    
- <span data-ttu-id="05ba7-586">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="05ba7-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-587">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-587">Checksum</span></span>

<span data-ttu-id="05ba7-588">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-589">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-589">Definition</span></span>

<span data-ttu-id="05ba7-590">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-591">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-592">Viene trovata una `Keywords_luxemburg_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-593">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-594">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-595">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="05ba7-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-597">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-597">tax number</span></span>
  
<span data-ttu-id="05ba7-598">tassa no.</span><span class="sxs-lookup"><span data-stu-id="05ba7-598">tax no.</span></span>
  
<span data-ttu-id="05ba7-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-599">taxno#</span></span>
  
<span data-ttu-id="05ba7-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="05ba7-600">taxnumber#</span></span>
  
<span data-ttu-id="05ba7-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="05ba7-601">taxnumber</span></span>
  
<span data-ttu-id="05ba7-602">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-602">tax id</span></span>
  
<span data-ttu-id="05ba7-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-603">taxid#</span></span>
  
<span data-ttu-id="05ba7-604">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-604">tax identification number</span></span>
  
<span data-ttu-id="05ba7-605">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="05ba7-605">tax identification no.</span></span>
  
<span data-ttu-id="05ba7-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="05ba7-606">steuernummer</span></span>
  
<span data-ttu-id="05ba7-607">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="05ba7-607">steuer id</span></span>
  
<span data-ttu-id="05ba7-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="05ba7-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="05ba7-609">Malta</span><span class="sxs-lookup"><span data-stu-id="05ba7-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-610">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-610">Format</span></span>

<span data-ttu-id="05ba7-611">Per cittadini maltesi: 7 cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="05ba7-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="05ba7-612">Nazionali non maltesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-613">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-613">Pattern</span></span>

<span data-ttu-id="05ba7-614">Cittadini maltesi: 7 cifre e una lettera</span><span class="sxs-lookup"><span data-stu-id="05ba7-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="05ba7-615">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-615">Seven digits</span></span> 
    
- <span data-ttu-id="05ba7-616">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="05ba7-617">Nazionali non maltesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="05ba7-618">9 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="05ba7-619">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-619">Checksum</span></span>

<span data-ttu-id="05ba7-620">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="05ba7-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-621">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-621">Definition</span></span>

<span data-ttu-id="05ba7-622">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-623">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-624">Viene trovata una `Keywords_malta_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-625">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-626">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-627">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="05ba7-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-629">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-629">tax number</span></span>
  
<span data-ttu-id="05ba7-630">tassa no.</span><span class="sxs-lookup"><span data-stu-id="05ba7-630">tax no.</span></span>
  
<span data-ttu-id="05ba7-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-631">taxno#</span></span>
  
<span data-ttu-id="05ba7-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="05ba7-632">taxnumber#</span></span>
  
<span data-ttu-id="05ba7-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="05ba7-633">taxnumber</span></span>
  
<span data-ttu-id="05ba7-634">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-634">tax id</span></span>
  
<span data-ttu-id="05ba7-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-635">taxid#</span></span>
  
<span data-ttu-id="05ba7-636">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-636">tax identification number</span></span>
  
<span data-ttu-id="05ba7-637">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="05ba7-637">tax identification no.</span></span>
  
<span data-ttu-id="05ba7-638">numru Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="05ba7-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="05ba7-639">ID Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="05ba7-639">id tat-taxxa</span></span>
  
<span data-ttu-id="05ba7-640">numru ta ' identifikazzjoni Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="05ba7-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="05ba7-641">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="05ba7-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-642">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-642">Format</span></span>

<span data-ttu-id="05ba7-643">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-644">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-644">Pattern</span></span>

<span data-ttu-id="05ba7-645">9 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="05ba7-646">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-646">Checksum</span></span>

<span data-ttu-id="05ba7-647">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-648">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-648">Definition</span></span>

<span data-ttu-id="05ba7-649">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-650">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-651">Viene trovata una `Keywords_netherlands_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-652">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-653">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-654">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="05ba7-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-656">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="05ba7-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="05ba7-657">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="05ba7-657">netherlands tax identification</span></span>
  
<span data-ttu-id="05ba7-658">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="05ba7-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="05ba7-659">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="05ba7-659">netherland's tax identification</span></span>
  
<span data-ttu-id="05ba7-660">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-660">tax identification number</span></span>
  
<span data-ttu-id="05ba7-661">ID delle tasse olandesi</span><span class="sxs-lookup"><span data-stu-id="05ba7-661">dutch tax id</span></span>
  
<span data-ttu-id="05ba7-662">numero di identificazione fiscale olandese</span><span class="sxs-lookup"><span data-stu-id="05ba7-662">dutch tax identification number</span></span>
  
<span data-ttu-id="05ba7-663">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-663">tax id</span></span>
  
<span data-ttu-id="05ba7-664">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="05ba7-664">tax id#</span></span>
  
<span data-ttu-id="05ba7-665">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-665">tax number</span></span>
  
<span data-ttu-id="05ba7-666">tax no #</span><span class="sxs-lookup"><span data-stu-id="05ba7-666">tax no#</span></span>
  
<span data-ttu-id="05ba7-667">imposte #</span><span class="sxs-lookup"><span data-stu-id="05ba7-667">tax#</span></span>
  
<span data-ttu-id="05ba7-668">latta</span><span class="sxs-lookup"><span data-stu-id="05ba7-668">tin</span></span>
  
<span data-ttu-id="05ba7-669">latta #</span><span class="sxs-lookup"><span data-stu-id="05ba7-669">tin#</span></span>
  
<span data-ttu-id="05ba7-670">Tin olandesi</span><span class="sxs-lookup"><span data-stu-id="05ba7-670">netherlands tin</span></span>
  
<span data-ttu-id="05ba7-671">stagno degli olandesi</span><span class="sxs-lookup"><span data-stu-id="05ba7-671">netherland's tin</span></span>
  
<span data-ttu-id="05ba7-672">Nederlands identificatienummer di recente</span><span class="sxs-lookup"><span data-stu-id="05ba7-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="05ba7-673">identificatienummer van delasting</span><span class="sxs-lookup"><span data-stu-id="05ba7-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="05ba7-674">identificatienummer che dura</span><span class="sxs-lookup"><span data-stu-id="05ba7-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="05ba7-675">Nederlands identificatie di recente</span><span class="sxs-lookup"><span data-stu-id="05ba7-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="05ba7-676">l'ID di Nummer del Nederlands</span><span class="sxs-lookup"><span data-stu-id="05ba7-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="05ba7-677">Nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="05ba7-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="05ba7-678">BTW nummer</span><span class="sxs-lookup"><span data-stu-id="05ba7-678">btw nummer</span></span>
  
<span data-ttu-id="05ba7-679">Nederlandse che durerà identificatie</span><span class="sxs-lookup"><span data-stu-id="05ba7-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="05ba7-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="05ba7-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-681">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-681">Format</span></span>

<span data-ttu-id="05ba7-682">Undici cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-683">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-683">Pattern</span></span>

<span data-ttu-id="05ba7-684">Undici cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05ba7-685">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-685">Checksum</span></span>

<span data-ttu-id="05ba7-686">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-687">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-687">Definition</span></span>

<span data-ttu-id="05ba7-688">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-689">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-690">Viene trovata una `Keywords_poland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-691">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-692">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-693">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="05ba7-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-695">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-695">tax number</span></span>
  
<span data-ttu-id="05ba7-696">tassa no.</span><span class="sxs-lookup"><span data-stu-id="05ba7-696">tax no.</span></span>
  
<span data-ttu-id="05ba7-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-697">taxno#</span></span>
  
<span data-ttu-id="05ba7-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="05ba7-698">taxnumber#</span></span>
  
<span data-ttu-id="05ba7-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="05ba7-699">taxnumber</span></span>
  
<span data-ttu-id="05ba7-700">NIP</span><span class="sxs-lookup"><span data-stu-id="05ba7-700">nip</span></span>
  
<span data-ttu-id="05ba7-701">NIP #</span><span class="sxs-lookup"><span data-stu-id="05ba7-701">nip#</span></span>
  
<span data-ttu-id="05ba7-702">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-702">tax id</span></span>
  
<span data-ttu-id="05ba7-703">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="05ba7-703">tax id#</span></span>
  
<span data-ttu-id="05ba7-704">ID NIP</span><span class="sxs-lookup"><span data-stu-id="05ba7-704">nip id</span></span>
  
<span data-ttu-id="05ba7-705">ID NIP #</span><span class="sxs-lookup"><span data-stu-id="05ba7-705">nip id#</span></span>
  
<span data-ttu-id="05ba7-706">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-706">tax identification number</span></span>
  
<span data-ttu-id="05ba7-707">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="05ba7-707">tax identification no.</span></span>
  
<span data-ttu-id="05ba7-708">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="05ba7-708">vat number</span></span>
  
<span data-ttu-id="05ba7-709">IVA No.</span><span class="sxs-lookup"><span data-stu-id="05ba7-709">vat no.</span></span>
  
<span data-ttu-id="05ba7-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-710">vatno#</span></span>
  
<span data-ttu-id="05ba7-711">ID partita IVA</span><span class="sxs-lookup"><span data-stu-id="05ba7-711">vat id</span></span>
  
<span data-ttu-id="05ba7-712">ID partita IVA #</span><span class="sxs-lookup"><span data-stu-id="05ba7-712">vat id#</span></span>
  
<span data-ttu-id="05ba7-713">numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="05ba7-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="05ba7-714">Polski numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="05ba7-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="05ba7-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="05ba7-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="05ba7-716">Portogallo</span><span class="sxs-lookup"><span data-stu-id="05ba7-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-717">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-717">Format</span></span>

<span data-ttu-id="05ba7-718">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-719">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-719">Pattern</span></span>

<span data-ttu-id="05ba7-720">9 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05ba7-721">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-721">Checksum</span></span>

<span data-ttu-id="05ba7-722">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-723">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-723">Definition</span></span>

<span data-ttu-id="05ba7-724">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-725">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-726">Viene trovata una `Keywords_portugal_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-727">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-728">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-729">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="05ba7-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-731">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-731">tax number</span></span>
  
<span data-ttu-id="05ba7-732">tassa no.</span><span class="sxs-lookup"><span data-stu-id="05ba7-732">tax no.</span></span>
  
<span data-ttu-id="05ba7-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-733">taxno#</span></span>
  
<span data-ttu-id="05ba7-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="05ba7-734">taxnumber#</span></span>
  
<span data-ttu-id="05ba7-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="05ba7-735">taxnumber</span></span>
  
<span data-ttu-id="05ba7-736">NIF</span><span class="sxs-lookup"><span data-stu-id="05ba7-736">nif</span></span>
  
<span data-ttu-id="05ba7-737">NIF #</span><span class="sxs-lookup"><span data-stu-id="05ba7-737">nif#</span></span>
  
<span data-ttu-id="05ba7-738">numero fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-738">numero fiscal</span></span>
  
<span data-ttu-id="05ba7-739">número de identificação Fiscal</span><span class="sxs-lookup"><span data-stu-id="05ba7-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="05ba7-740">Romania</span><span class="sxs-lookup"><span data-stu-id="05ba7-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-741">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-741">Format</span></span>

<span data-ttu-id="05ba7-742">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-743">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-743">Pattern</span></span>

<span data-ttu-id="05ba7-744">13 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05ba7-745">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-745">Checksum</span></span>

<span data-ttu-id="05ba7-746">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="05ba7-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-747">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-747">Definition</span></span>

<span data-ttu-id="05ba7-748">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-749">L'espressione `Regex_romania_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-750">Viene trovata una `Keywords_romania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05ba7-751">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="05ba7-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-753">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-753">tax id</span></span>
  
<span data-ttu-id="05ba7-754">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-754">tax id number</span></span>
  
<span data-ttu-id="05ba7-755">Tax File No</span><span class="sxs-lookup"><span data-stu-id="05ba7-755">tax file no</span></span>
  
<span data-ttu-id="05ba7-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="05ba7-756">tax file number</span></span>
  
<span data-ttu-id="05ba7-757">tax no</span><span class="sxs-lookup"><span data-stu-id="05ba7-757">tax no</span></span>
  
<span data-ttu-id="05ba7-758">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-758">tax number</span></span>
  
<span data-ttu-id="05ba7-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-759">taxid#</span></span>
  
<span data-ttu-id="05ba7-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-760">taxno#</span></span>
  
<span data-ttu-id="05ba7-761">ID-ul taxei</span><span class="sxs-lookup"><span data-stu-id="05ba7-761">id-ul taxei</span></span>
  
<span data-ttu-id="05ba7-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="05ba7-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="05ba7-763">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="05ba7-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-764">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-764">Format</span></span>

<span data-ttu-id="05ba7-765">10 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-766">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-766">Pattern</span></span>

<span data-ttu-id="05ba7-767">10 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05ba7-768">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-768">Checksum</span></span>

<span data-ttu-id="05ba7-769">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="05ba7-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-770">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-770">Definition</span></span>

<span data-ttu-id="05ba7-771">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-772">L'espressione `Regex_slovakia_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-773">Viene trovata una `Keywords_slovakia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05ba7-774">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="05ba7-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-776">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-776">tax id</span></span>
  
<span data-ttu-id="05ba7-777">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-777">tax id number</span></span>
  
<span data-ttu-id="05ba7-778">ID Tin</span><span class="sxs-lookup"><span data-stu-id="05ba7-778">tin id</span></span>
  
<span data-ttu-id="05ba7-779">Tin No</span><span class="sxs-lookup"><span data-stu-id="05ba7-779">tin no</span></span>
  
<span data-ttu-id="05ba7-780">ID Tin slovacco</span><span class="sxs-lookup"><span data-stu-id="05ba7-780">slovakian tin id</span></span>
  
<span data-ttu-id="05ba7-781">latta</span><span class="sxs-lookup"><span data-stu-id="05ba7-781">tin</span></span>
  
<span data-ttu-id="05ba7-782">Tax File No</span><span class="sxs-lookup"><span data-stu-id="05ba7-782">tax file no</span></span>
  
<span data-ttu-id="05ba7-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="05ba7-783">tax file number</span></span>
  
<span data-ttu-id="05ba7-784">tax no</span><span class="sxs-lookup"><span data-stu-id="05ba7-784">tax no</span></span>
  
<span data-ttu-id="05ba7-785">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-785">tax number</span></span>
  
<span data-ttu-id="05ba7-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-786">taxid#</span></span>
  
<span data-ttu-id="05ba7-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-787">taxno#</span></span>
  
<span data-ttu-id="05ba7-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="05ba7-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="05ba7-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="05ba7-789">daňové číslo</span></span>
  
<span data-ttu-id="05ba7-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="05ba7-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="05ba7-791">Slovenia</span><span class="sxs-lookup"><span data-stu-id="05ba7-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-792">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-792">Format</span></span>

<span data-ttu-id="05ba7-793">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-794">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-794">Pattern</span></span>

<span data-ttu-id="05ba7-795">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05ba7-796">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-796">Checksum</span></span>

<span data-ttu-id="05ba7-797">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-798">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-798">Definition</span></span>

<span data-ttu-id="05ba7-799">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-800">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-801">Viene trovata una `Keywords_slovenia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-802">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-803">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-804">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="05ba7-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-806">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-806">tax id</span></span>
  
<span data-ttu-id="05ba7-807">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-807">tax id number</span></span>
  
<span data-ttu-id="05ba7-808">ID Tin</span><span class="sxs-lookup"><span data-stu-id="05ba7-808">tin id</span></span>
  
<span data-ttu-id="05ba7-809">Tin No</span><span class="sxs-lookup"><span data-stu-id="05ba7-809">tin no</span></span>
  
<span data-ttu-id="05ba7-810">ID Tin sloveno</span><span class="sxs-lookup"><span data-stu-id="05ba7-810">slovenian tin id</span></span>
  
<span data-ttu-id="05ba7-811">latta</span><span class="sxs-lookup"><span data-stu-id="05ba7-811">tin</span></span>
  
<span data-ttu-id="05ba7-812">Tax File No</span><span class="sxs-lookup"><span data-stu-id="05ba7-812">tax file no</span></span>
  
<span data-ttu-id="05ba7-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="05ba7-813">tax file number</span></span>
  
<span data-ttu-id="05ba7-814">tax no</span><span class="sxs-lookup"><span data-stu-id="05ba7-814">tax no</span></span>
  
<span data-ttu-id="05ba7-815">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-815">tax number</span></span>
  
<span data-ttu-id="05ba7-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-816">taxid#</span></span>
  
<span data-ttu-id="05ba7-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-817">taxno#</span></span>
  
<span data-ttu-id="05ba7-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="05ba7-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="05ba7-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="05ba7-819">davčna številka</span></span>
  
<span data-ttu-id="05ba7-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="05ba7-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="05ba7-821">Spagna</span><span class="sxs-lookup"><span data-stu-id="05ba7-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-822">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-822">Format</span></span>

<span data-ttu-id="05ba7-823">Sette o otto cifre e una o due lettere nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="05ba7-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-824">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-824">Pattern</span></span>

<span data-ttu-id="05ba7-825">Persone fisiche spagnole con carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="05ba7-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="05ba7-826">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-826">Eight digits</span></span> 
    
- <span data-ttu-id="05ba7-827">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="05ba7-828">Spagnoli non residenti senza una carta d'identità nazionale spagnola</span><span class="sxs-lookup"><span data-stu-id="05ba7-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="05ba7-829">Una lettera maiuscola "L" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="05ba7-830">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-830">Seven digits</span></span>
    
- <span data-ttu-id="05ba7-831">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="05ba7-832">Spagnoli residenti di età inferiore ai 14 anni senza una carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="05ba7-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="05ba7-833">Una lettera maiuscola "K" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="05ba7-834">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-834">Seven digits</span></span> 
    
- <span data-ttu-id="05ba7-835">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="05ba7-836">Stranieri con il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="05ba7-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="05ba7-837">Una lettera maiuscola che è "X", "Y" o "Z" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="05ba7-838">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-838">Seven digits</span></span>
    
- <span data-ttu-id="05ba7-839">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="05ba7-840">Stranieri senza il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="05ba7-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="05ba7-841">Una lettera maiuscola che è "M" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="05ba7-842">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-842">Seven digits</span></span>
    
- <span data-ttu-id="05ba7-843">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="05ba7-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="05ba7-844">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-844">Checksum</span></span>

<span data-ttu-id="05ba7-845">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-846">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-846">Definition</span></span>

<span data-ttu-id="05ba7-847">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-848">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-849">Viene trovata una `Keywords_spain_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-850">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-851">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-852">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="05ba7-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-854">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-854">tax id</span></span>
  
<span data-ttu-id="05ba7-855">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-855">tax id number</span></span>
  
<span data-ttu-id="05ba7-856">ID CIF</span><span class="sxs-lookup"><span data-stu-id="05ba7-856">cif id</span></span>
  
<span data-ttu-id="05ba7-857">CIF No</span><span class="sxs-lookup"><span data-stu-id="05ba7-857">cif no</span></span>
  
<span data-ttu-id="05ba7-858">ID CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="05ba7-858">spanish cif id</span></span>
  
<span data-ttu-id="05ba7-859">CIF</span><span class="sxs-lookup"><span data-stu-id="05ba7-859">cif</span></span>
  
<span data-ttu-id="05ba7-860">Tax File No</span><span class="sxs-lookup"><span data-stu-id="05ba7-860">tax file no</span></span>
  
<span data-ttu-id="05ba7-861">numero CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="05ba7-861">spanish cif number</span></span>
  
<span data-ttu-id="05ba7-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="05ba7-862">tax file number</span></span>
  
<span data-ttu-id="05ba7-863">Spagnolo CIF No</span><span class="sxs-lookup"><span data-stu-id="05ba7-863">spanish cif no</span></span>
  
<span data-ttu-id="05ba7-864">tax no</span><span class="sxs-lookup"><span data-stu-id="05ba7-864">tax no</span></span>
  
<span data-ttu-id="05ba7-865">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-865">tax number</span></span>
  
<span data-ttu-id="05ba7-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-866">taxid#</span></span>
  
<span data-ttu-id="05ba7-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-867">taxno#</span></span>
  
<span data-ttu-id="05ba7-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-868">cifid#</span></span>
  
<span data-ttu-id="05ba7-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-869">spanishcifid#</span></span>
  
<span data-ttu-id="05ba7-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="05ba7-870">spanishcifno#</span></span>
  
<span data-ttu-id="05ba7-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="05ba7-871">número de contribuyente</span></span>
  
<span data-ttu-id="05ba7-872">número de Impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="05ba7-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="05ba7-873">número de Identificación Fiscal</span><span class="sxs-lookup"><span data-stu-id="05ba7-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="05ba7-874">número CIF</span><span class="sxs-lookup"><span data-stu-id="05ba7-874">cif número</span></span>
  
<span data-ttu-id="05ba7-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="05ba7-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="05ba7-876">Svezia</span><span class="sxs-lookup"><span data-stu-id="05ba7-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-877">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-877">Format</span></span>

<span data-ttu-id="05ba7-878">Dieci cifre e un simbolo nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="05ba7-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-879">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-879">Pattern</span></span>

<span data-ttu-id="05ba7-880">Dieci cifre e un simbolo:</span><span class="sxs-lookup"><span data-stu-id="05ba7-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="05ba7-881">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="05ba7-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="05ba7-882">Segno di addizione, segno meno o barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="05ba7-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="05ba7-883">Tre cifre che rendono il numero di identificazione univoco dove:</span><span class="sxs-lookup"><span data-stu-id="05ba7-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="05ba7-884">Per i numeri emessi prima del 1990, la settima e la terza cifra identificano la Contea di nascita o gli stranieri nati</span><span class="sxs-lookup"><span data-stu-id="05ba7-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="05ba7-885">La cifra nella nona posizione indica il sesso per il maschio o per la femmina.</span><span class="sxs-lookup"><span data-stu-id="05ba7-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="05ba7-886">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="05ba7-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="05ba7-887">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-887">Checksum</span></span>

<span data-ttu-id="05ba7-888">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-889">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-889">Definition</span></span>

<span data-ttu-id="05ba7-890">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-891">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-892">Viene trovata una `Keywords_sweden_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="05ba7-893">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-894">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="05ba7-895">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="05ba7-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-897">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-897">tax id</span></span>
  
<span data-ttu-id="05ba7-898">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="05ba7-898">tax id no.</span></span>
  
<span data-ttu-id="05ba7-899">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-899">tax id number</span></span>
  
<span data-ttu-id="05ba7-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="05ba7-900">tax identification</span></span>
  
<span data-ttu-id="05ba7-901">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="05ba7-901">tax identification#</span></span>
  
<span data-ttu-id="05ba7-902">tassa no.</span><span class="sxs-lookup"><span data-stu-id="05ba7-902">tax no.</span></span>
  
<span data-ttu-id="05ba7-903">imposte #</span><span class="sxs-lookup"><span data-stu-id="05ba7-903">tax#</span></span>
  
<span data-ttu-id="05ba7-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-904">taxid#</span></span>
  
<span data-ttu-id="05ba7-905">file fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-905">tax file</span></span>
  
<span data-ttu-id="05ba7-906">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="05ba7-906">tax file no.</span></span>
  
<span data-ttu-id="05ba7-907">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="05ba7-907">personal id number</span></span>
  
<span data-ttu-id="05ba7-908">ID pattinat Nummer</span><span class="sxs-lookup"><span data-stu-id="05ba7-908">skatt id nummer</span></span>
  
<span data-ttu-id="05ba7-909">Identifikation skatet</span><span class="sxs-lookup"><span data-stu-id="05ba7-909">skatt identifikation</span></span>
  
<span data-ttu-id="05ba7-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="05ba7-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="05ba7-911">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="05ba7-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="05ba7-912">Formato</span><span class="sxs-lookup"><span data-stu-id="05ba7-912">Format</span></span>

<span data-ttu-id="05ba7-913">Riferimento per i contribuenti unici (UTR): 10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="05ba7-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="05ba7-914">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="05ba7-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="05ba7-915">Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="05ba7-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="05ba7-916">Modello</span><span class="sxs-lookup"><span data-stu-id="05ba7-916">Pattern</span></span>

<span data-ttu-id="05ba7-917">Riferimento per i contribuenti unici (UTR): 10 cifre</span><span class="sxs-lookup"><span data-stu-id="05ba7-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="05ba7-918">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="05ba7-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="05ba7-919">Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="05ba7-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="05ba7-920">Checksum</span><span class="sxs-lookup"><span data-stu-id="05ba7-920">Checksum</span></span>

<span data-ttu-id="05ba7-921">Sì</span><span class="sxs-lookup"><span data-stu-id="05ba7-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="05ba7-922">Definizione</span><span class="sxs-lookup"><span data-stu-id="05ba7-922">Definition</span></span>

<span data-ttu-id="05ba7-923">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="05ba7-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="05ba7-924">La funzione `Func_uk_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="05ba7-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="05ba7-925">Viene trovata una `Keywords_uk_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="05ba7-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="05ba7-926">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="05ba7-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="05ba7-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="05ba7-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="05ba7-928">tax id</span><span class="sxs-lookup"><span data-stu-id="05ba7-928">tax id</span></span>
  
<span data-ttu-id="05ba7-929">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="05ba7-929">tax id no.</span></span>
  
<span data-ttu-id="05ba7-930">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-930">tax id number</span></span>
  
<span data-ttu-id="05ba7-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="05ba7-931">tax identification</span></span>
  
<span data-ttu-id="05ba7-932">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="05ba7-932">tax identification#</span></span>
  
<span data-ttu-id="05ba7-933">tassa no.</span><span class="sxs-lookup"><span data-stu-id="05ba7-933">tax no.</span></span>
  
<span data-ttu-id="05ba7-934">imposte #</span><span class="sxs-lookup"><span data-stu-id="05ba7-934">tax#</span></span>
  
<span data-ttu-id="05ba7-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="05ba7-935">taxid#</span></span>
  
<span data-ttu-id="05ba7-936">file fiscale</span><span class="sxs-lookup"><span data-stu-id="05ba7-936">tax file</span></span>
  
<span data-ttu-id="05ba7-937">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="05ba7-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="05ba7-938">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05ba7-938">See also</span></span>

[<span data-ttu-id="05ba7-939">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="05ba7-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

