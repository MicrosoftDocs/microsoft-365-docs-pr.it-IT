---
title: Numero di identificazione fiscale dell'Unione europea
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 0ee76fa46bb22b2754098d053ab769b862fdd3f2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805849"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="b60ec-104">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="b60ec-104">EU Tax Identification Number</span></span>

<span data-ttu-id="b60ec-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale (TIN) dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="b60ec-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="b60ec-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="b60ec-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="b60ec-107">Austria</span><span class="sxs-lookup"><span data-stu-id="b60ec-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-108">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-108">Format</span></span>

<span data-ttu-id="b60ec-109">Nove cifre con trattino e barra di inoltro opzionali</span><span class="sxs-lookup"><span data-stu-id="b60ec-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-110">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-110">Pattern</span></span>

<span data-ttu-id="b60ec-111">Nove cifre con trattino e barra di inoltro facoltativi:</span><span class="sxs-lookup"><span data-stu-id="b60ec-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="b60ec-112">Due cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-112">Two digits</span></span> 
    
- <span data-ttu-id="b60ec-113">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="b60ec-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="b60ec-114">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-114">Three digits</span></span>
    
- <span data-ttu-id="b60ec-115">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="b60ec-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="b60ec-116">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-117">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-117">Checksum</span></span>

<span data-ttu-id="b60ec-118">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-119">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-119">Definition</span></span>

<span data-ttu-id="b60ec-120">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-121">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-122">Viene trovata una `Keywords_austria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-123">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-124">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-125">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="b60ec-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-127">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-127">tax number</span></span>
  
<span data-ttu-id="b60ec-128">numero</span><span class="sxs-lookup"><span data-stu-id="b60ec-128">number</span></span>
  
<span data-ttu-id="b60ec-129">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-129">tax registration number</span></span>
  
<span data-ttu-id="b60ec-130">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-130">tax id</span></span>
  
<span data-ttu-id="b60ec-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="b60ec-131">st.nr.</span></span>
  
<span data-ttu-id="b60ec-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="b60ec-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="b60ec-133">Belgio</span><span class="sxs-lookup"><span data-stu-id="b60ec-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-134">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-134">Format</span></span>

<span data-ttu-id="b60ec-135">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-136">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-136">Pattern</span></span>

<span data-ttu-id="b60ec-137">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="b60ec-137">11 digits:</span></span>
  
- <span data-ttu-id="b60ec-138">Due cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-138">Two digits</span></span>
    
- <span data-ttu-id="b60ec-139">"0" o "1"</span><span class="sxs-lookup"><span data-stu-id="b60ec-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="b60ec-140">Una cifra</span><span class="sxs-lookup"><span data-stu-id="b60ec-140">One digit</span></span>
    
- <span data-ttu-id="b60ec-141">"0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="b60ec-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="b60ec-142">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-143">Checksum</span></span>

<span data-ttu-id="b60ec-144">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="b60ec-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-145">Definition</span></span>

<span data-ttu-id="b60ec-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-147">L'espressione `Regex_belgium_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-148">Viene trovata una `Keywords_belgium_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b60ec-149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="b60ec-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-151">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-151">tax number</span></span>
  
<span data-ttu-id="b60ec-152">numero di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="b60ec-152">national registration number</span></span>
  
<span data-ttu-id="b60ec-153">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-153">tax registration number</span></span>
  
<span data-ttu-id="b60ec-154">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-154">tax id</span></span>
  
<span data-ttu-id="b60ec-155">NIF</span><span class="sxs-lookup"><span data-stu-id="b60ec-155">nif</span></span>
  
<span data-ttu-id="b60ec-156">NIF #</span><span class="sxs-lookup"><span data-stu-id="b60ec-156">nif#</span></span>
  
<span data-ttu-id="b60ec-157">numéro de Registre National</span><span class="sxs-lookup"><span data-stu-id="b60ec-157">numéro de registre national</span></span>
  
<span data-ttu-id="b60ec-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="b60ec-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="b60ec-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-160">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-160">Format</span></span>

<span data-ttu-id="b60ec-161">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-162">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-162">Pattern</span></span>

<span data-ttu-id="b60ec-163">10 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b60ec-164">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-164">Checksum</span></span>

<span data-ttu-id="b60ec-165">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-166">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-166">Definition</span></span>

<span data-ttu-id="b60ec-167">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-168">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-169">Viene trovata una `Keywords_bulgaria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-170">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-171">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-172">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="b60ec-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-174">bucn</span><span class="sxs-lookup"><span data-stu-id="b60ec-174">bucn</span></span>
  
<span data-ttu-id="b60ec-175">numero civile uniforme</span><span class="sxs-lookup"><span data-stu-id="b60ec-175">uniform civil number</span></span>
  
<span data-ttu-id="b60ec-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="b60ec-176">bucn#</span></span>
  
<span data-ttu-id="b60ec-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="b60ec-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="b60ec-178">ID civile uniforme</span><span class="sxs-lookup"><span data-stu-id="b60ec-178">uniform civil id</span></span>
  
<span data-ttu-id="b60ec-179">uniforme civile No</span><span class="sxs-lookup"><span data-stu-id="b60ec-179">uniform civil no</span></span>
  
<span data-ttu-id="b60ec-180">EGN</span><span class="sxs-lookup"><span data-stu-id="b60ec-180">egn</span></span>
  
<span data-ttu-id="b60ec-181">numero civile uniforme bulgaro</span><span class="sxs-lookup"><span data-stu-id="b60ec-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="b60ec-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-182">uniformcivilno#</span></span>
  
<span data-ttu-id="b60ec-183">EGN #</span><span class="sxs-lookup"><span data-stu-id="b60ec-183">egn#</span></span>
  
<span data-ttu-id="b60ec-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="b60ec-184">униформ граждански номер</span></span>
  
<span data-ttu-id="b60ec-185">ID униформ</span><span class="sxs-lookup"><span data-stu-id="b60ec-185">униформ id</span></span>
  
<span data-ttu-id="b60ec-186">ID граждански униформ</span><span class="sxs-lookup"><span data-stu-id="b60ec-186">униформ граждански id</span></span>
  
<span data-ttu-id="b60ec-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="b60ec-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="b60ec-188">Croazia</span><span class="sxs-lookup"><span data-stu-id="b60ec-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-189">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-189">Format</span></span>

<span data-ttu-id="b60ec-190">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-191">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-191">Pattern</span></span>

<span data-ttu-id="b60ec-192">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="b60ec-192">11 digits:</span></span>
  
- <span data-ttu-id="b60ec-193">Dieci cifre, scelte casualmente</span><span class="sxs-lookup"><span data-stu-id="b60ec-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="b60ec-194">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="b60ec-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-195">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-195">Checksum</span></span>

<span data-ttu-id="b60ec-196">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-197">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-197">Definition</span></span>

<span data-ttu-id="b60ec-198">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-199">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-200">Viene trovata una `Keywords_croatia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-202">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-203">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="b60ec-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-205">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-205">tax number</span></span>
  
<span data-ttu-id="b60ec-206">imposte</span><span class="sxs-lookup"><span data-stu-id="b60ec-206">tax</span></span>
  
<span data-ttu-id="b60ec-207">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-207">tax id</span></span>
  
<span data-ttu-id="b60ec-208">OID</span><span class="sxs-lookup"><span data-stu-id="b60ec-208">oid</span></span>
  
<span data-ttu-id="b60ec-209">OID #</span><span class="sxs-lookup"><span data-stu-id="b60ec-209">oid#</span></span>
  
<span data-ttu-id="b60ec-210">Porezni broj</span><span class="sxs-lookup"><span data-stu-id="b60ec-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="b60ec-211">Cipro</span><span class="sxs-lookup"><span data-stu-id="b60ec-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-212">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-212">Format</span></span>

<span data-ttu-id="b60ec-213">Otto cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="b60ec-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-214">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-214">Pattern</span></span>

<span data-ttu-id="b60ec-215">Otto cifre e una lettera:</span><span class="sxs-lookup"><span data-stu-id="b60ec-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="b60ec-216">Un "0"</span><span class="sxs-lookup"><span data-stu-id="b60ec-216">A "0"</span></span> 
    
- <span data-ttu-id="b60ec-217">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-217">Seven digits</span></span>
    
- <span data-ttu-id="b60ec-218">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-219">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-219">Checksum</span></span>

<span data-ttu-id="b60ec-220">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="b60ec-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-221">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-221">Definition</span></span>

<span data-ttu-id="b60ec-222">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-223">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-224">Viene trovata una `Keywords_cyprus_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-225">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-226">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="b60ec-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-229">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-229">tax number</span></span>
  
<span data-ttu-id="b60ec-230">imposte</span><span class="sxs-lookup"><span data-stu-id="b60ec-230">tax</span></span>
  
<span data-ttu-id="b60ec-231">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-231">tax id</span></span>
  
<span data-ttu-id="b60ec-232">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-232">tax identification code</span></span>
  
<span data-ttu-id="b60ec-233">TIC</span><span class="sxs-lookup"><span data-stu-id="b60ec-233">tic</span></span>
  
<span data-ttu-id="b60ec-234">TIC #</span><span class="sxs-lookup"><span data-stu-id="b60ec-234">tic#</span></span>
  
<span data-ttu-id="b60ec-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="b60ec-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="b60ec-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="b60ec-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="b60ec-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="b60ec-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="b60ec-238">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="b60ec-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-239">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-239">Format</span></span>

<span data-ttu-id="b60ec-240">Nove o dieci cifre con una barra rovesciata facoltativa</span><span class="sxs-lookup"><span data-stu-id="b60ec-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-241">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-241">Pattern</span></span>

<span data-ttu-id="b60ec-242">Nove o dieci cifre con un backslash facoltativo:</span><span class="sxs-lookup"><span data-stu-id="b60ec-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="b60ec-243">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-243">Six digits</span></span> 
    
- <span data-ttu-id="b60ec-244">Una barra rovesciata (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="b60ec-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="b60ec-245">Tre o quattro cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-246">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-246">Checksum</span></span>

<span data-ttu-id="b60ec-247">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="b60ec-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-248">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-248">Definition</span></span>

<span data-ttu-id="b60ec-249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-250">L'espressione `Regex_czech_republic_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-251">Viene trovata una `Keywords_czech_republic_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b60ec-252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="b60ec-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-254">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-254">tax number</span></span>
  
<span data-ttu-id="b60ec-255">imposte</span><span class="sxs-lookup"><span data-stu-id="b60ec-255">tax</span></span>
  
<span data-ttu-id="b60ec-256">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-256">tax id</span></span>
  
<span data-ttu-id="b60ec-257">numero personale</span><span class="sxs-lookup"><span data-stu-id="b60ec-257">personal number</span></span>
  
<span data-ttu-id="b60ec-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="b60ec-258">daňové číslo</span></span>
  
<span data-ttu-id="b60ec-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="b60ec-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="b60ec-260">Danimarca</span><span class="sxs-lookup"><span data-stu-id="b60ec-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-261">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-261">Format</span></span>

<span data-ttu-id="b60ec-262">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="b60ec-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-263">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-263">Pattern</span></span>

<span data-ttu-id="b60ec-264">Dieci cifre contenenti un segno meno:</span><span class="sxs-lookup"><span data-stu-id="b60ec-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="b60ec-265">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="b60ec-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="b60ec-266">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="b60ec-266">A hyphen</span></span>
    
- <span data-ttu-id="b60ec-267">Quattro cifre che corrispondono a un numero di sequenza in cui la prima cifra corrisponde al secolo di nascita e l'ultima cifra corrisponde al sesso dell'individuo (dispari per il maschio e anche per le femmine)</span><span class="sxs-lookup"><span data-stu-id="b60ec-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-268">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-268">Checksum</span></span>

<span data-ttu-id="b60ec-269">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-270">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-270">Definition</span></span>

<span data-ttu-id="b60ec-271">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-272">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-273">Viene trovata una `Keywords_denmark_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-275">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-276">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="b60ec-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-278">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-278">tax number</span></span>
  
<span data-ttu-id="b60ec-279">imposte</span><span class="sxs-lookup"><span data-stu-id="b60ec-279">tax</span></span>
  
<span data-ttu-id="b60ec-280">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-280">tax id</span></span>
  
<span data-ttu-id="b60ec-281">numero CPR</span><span class="sxs-lookup"><span data-stu-id="b60ec-281">cpr number</span></span>
  
<span data-ttu-id="b60ec-282">CPR #</span><span class="sxs-lookup"><span data-stu-id="b60ec-282">cpr#</span></span>
  
<span data-ttu-id="b60ec-283">Nummer di pattinaggio</span><span class="sxs-lookup"><span data-stu-id="b60ec-283">skat nummer</span></span>
  
<span data-ttu-id="b60ec-284">ID pattina</span><span class="sxs-lookup"><span data-stu-id="b60ec-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="b60ec-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="b60ec-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-286">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-286">Format</span></span>

<span data-ttu-id="b60ec-287">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-288">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-288">Pattern</span></span>

<span data-ttu-id="b60ec-289">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="b60ec-289">11 digits:</span></span>
  
-  <span data-ttu-id="b60ec-290">Una cifra che corrisponde al sesso e al secolo del parto, in cui un numero dispari indica il maschio e il numero pari indica la femmina come segue: 1,2 per il XIX secolo; 3,4 per il XX secolo; e 5,6 per il XXI secolo</span><span class="sxs-lookup"><span data-stu-id="b60ec-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="b60ec-291">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="b60ec-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="b60ec-292">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="b60ec-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="b60ec-293">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="b60ec-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-294">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-294">Checksum</span></span>

<span data-ttu-id="b60ec-295">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-296">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-296">Definition</span></span>

<span data-ttu-id="b60ec-297">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-298">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-299">Viene trovata una `Keywords_estonia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-300">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-301">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-302">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="b60ec-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-304">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-304">tax number</span></span>
  
<span data-ttu-id="b60ec-305">imposte</span><span class="sxs-lookup"><span data-stu-id="b60ec-305">tax</span></span>
  
<span data-ttu-id="b60ec-306">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-306">tax id</span></span>
  
<span data-ttu-id="b60ec-307">codice personale</span><span class="sxs-lookup"><span data-stu-id="b60ec-307">personal code</span></span>
  
<span data-ttu-id="b60ec-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="b60ec-308">maksunumber</span></span>
  
<span data-ttu-id="b60ec-309">ID maksu</span><span class="sxs-lookup"><span data-stu-id="b60ec-309">maksu id</span></span>
  
<span data-ttu-id="b60ec-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="b60ec-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="b60ec-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="b60ec-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-312">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-312">Format</span></span>

<span data-ttu-id="b60ec-313">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno</span><span class="sxs-lookup"><span data-stu-id="b60ec-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-314">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-314">Pattern</span></span>

<span data-ttu-id="b60ec-315">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno:</span><span class="sxs-lookup"><span data-stu-id="b60ec-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="b60ec-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-316">Six digits</span></span>
    
- <span data-ttu-id="b60ec-317">Uno dei seguenti: un segno più, un segno di sottrazione o la lettera "A" (senza distinzione tra maiuscole/minuscole), in cui il segno più significa Nato tra 1800-1899, il segno meno significa Nato tra 1900-1999 e "A" significa Nato 2000 e dopo</span><span class="sxs-lookup"><span data-stu-id="b60ec-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="b60ec-318">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-318">Three digits</span></span>
    
- <span data-ttu-id="b60ec-319">Una lettera o un numero</span><span class="sxs-lookup"><span data-stu-id="b60ec-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-320">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-320">Checksum</span></span>

<span data-ttu-id="b60ec-321">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-322">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-322">Definition</span></span>

<span data-ttu-id="b60ec-323">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-324">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-325">Viene trovata una `Keywords_finland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-326">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-327">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-328">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="b60ec-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-330">identification number</span><span class="sxs-lookup"><span data-stu-id="b60ec-330">identification number</span></span>
  
<span data-ttu-id="b60ec-331">ID personale</span><span class="sxs-lookup"><span data-stu-id="b60ec-331">personal id</span></span>
  
<span data-ttu-id="b60ec-332">numero di identità</span><span class="sxs-lookup"><span data-stu-id="b60ec-332">identity number</span></span>
  
<span data-ttu-id="b60ec-333">numero di identificazione nazionale finlandese</span><span class="sxs-lookup"><span data-stu-id="b60ec-333">finnish national id number</span></span>
  
<span data-ttu-id="b60ec-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="b60ec-334">personalidnumber#</span></span>
  
<span data-ttu-id="b60ec-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="b60ec-335">national identification number</span></span>
  
<span data-ttu-id="b60ec-336">numero ID</span><span class="sxs-lookup"><span data-stu-id="b60ec-336">id number</span></span>
  
<span data-ttu-id="b60ec-337">ID nazionale No.</span><span class="sxs-lookup"><span data-stu-id="b60ec-337">national id no.</span></span>
  
<span data-ttu-id="b60ec-338">numero ID nazionale</span><span class="sxs-lookup"><span data-stu-id="b60ec-338">national id number</span></span>
  
<span data-ttu-id="b60ec-339">ID No</span><span class="sxs-lookup"><span data-stu-id="b60ec-339">id no</span></span>
  
<span data-ttu-id="b60ec-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="b60ec-340">tunnistenumero</span></span>
  
<span data-ttu-id="b60ec-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="b60ec-341">henkilötunnus</span></span>
  
<span data-ttu-id="b60ec-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="b60ec-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="b60ec-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="b60ec-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="b60ec-344">numero identiteetti</span><span class="sxs-lookup"><span data-stu-id="b60ec-344">identiteetti numero</span></span>
  
<span data-ttu-id="b60ec-345">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="b60ec-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="b60ec-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="b60ec-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="b60ec-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="b60ec-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="b60ec-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="b60ec-348">tunnusnumero</span></span>
  
<span data-ttu-id="b60ec-349">Kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="b60ec-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="b60ec-350">Francia</span><span class="sxs-lookup"><span data-stu-id="b60ec-350">France</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-351">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-351">Format</span></span>

<span data-ttu-id="b60ec-352">13 cifre per gli utenti e nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="b60ec-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-353">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-353">Pattern</span></span>

<span data-ttu-id="b60ec-354">13 cifre per gli utenti:</span><span class="sxs-lookup"><span data-stu-id="b60ec-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="b60ec-355">Una cifra che deve essere 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="b60ec-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="b60ec-356">12 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-356">12 digits</span></span>
    
<span data-ttu-id="b60ec-357">Nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="b60ec-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b60ec-358">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-358">Checksum</span></span>

<span data-ttu-id="b60ec-359">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="b60ec-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-360">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-360">Definition</span></span>

<span data-ttu-id="b60ec-361">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-362">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-363">Viene trovata una `Keywords_france_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-365">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-366">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="b60ec-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-368">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-368">tax identification number</span></span>
  
<span data-ttu-id="b60ec-369">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-369">tax number</span></span>
  
<span data-ttu-id="b60ec-370">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-370">tax id</span></span>
  
<span data-ttu-id="b60ec-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="b60ec-372">Germania</span><span class="sxs-lookup"><span data-stu-id="b60ec-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-373">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-373">Format</span></span>

<span data-ttu-id="b60ec-374">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-375">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-375">Pattern</span></span>

<span data-ttu-id="b60ec-376">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="b60ec-376">11 digits :</span></span>
  
-  <span data-ttu-id="b60ec-377">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-377">Ten digits</span></span> 
    
- <span data-ttu-id="b60ec-378">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="b60ec-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-379">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-379">Checksum</span></span>

<span data-ttu-id="b60ec-380">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-381">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-381">Definition</span></span>

<span data-ttu-id="b60ec-382">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-383">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-384">Viene trovata una `Keywords_germany_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-385">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-386">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="b60ec-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-389">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-389">tax number</span></span>
  
<span data-ttu-id="b60ec-390">tassa no.</span><span class="sxs-lookup"><span data-stu-id="b60ec-390">tax no.</span></span>
  
<span data-ttu-id="b60ec-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-391">taxno#</span></span>
  
<span data-ttu-id="b60ec-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b60ec-392">taxnumber#</span></span>
  
<span data-ttu-id="b60ec-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b60ec-393">taxnumber</span></span>
  
<span data-ttu-id="b60ec-394">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-394">tax id</span></span>
  
<span data-ttu-id="b60ec-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-395">taxid#</span></span>
  
<span data-ttu-id="b60ec-396">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-396">tax identification number</span></span>
  
<span data-ttu-id="b60ec-397">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="b60ec-397">tax identification no.</span></span>
  
<span data-ttu-id="b60ec-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="b60ec-398">steuernummer</span></span>
  
<span data-ttu-id="b60ec-399">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="b60ec-399">steuer id</span></span>
  
<span data-ttu-id="b60ec-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="b60ec-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="b60ec-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="b60ec-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-402">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-402">Format</span></span>

<span data-ttu-id="b60ec-403">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-404">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-404">Pattern</span></span>

<span data-ttu-id="b60ec-405">9 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b60ec-406">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-406">Checksum</span></span>

<span data-ttu-id="b60ec-407">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="b60ec-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-408">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-408">Definition</span></span>

<span data-ttu-id="b60ec-409">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-410">L'espressione `Regex_greece_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-411">Viene trovata una `Keywords_greece_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b60ec-412">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="b60ec-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-414">AFM</span><span class="sxs-lookup"><span data-stu-id="b60ec-414">afm</span></span>
  
<span data-ttu-id="b60ec-415">latta</span><span class="sxs-lookup"><span data-stu-id="b60ec-415">tin</span></span>
  
<span data-ttu-id="b60ec-416">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="b60ec-416">tax id no.</span></span>
  
<span data-ttu-id="b60ec-417">ID IVA No</span><span class="sxs-lookup"><span data-stu-id="b60ec-417">tax id no</span></span>
  
<span data-ttu-id="b60ec-418">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-418">tax identification number</span></span>
  
<span data-ttu-id="b60ec-419">numero del registro di sistema fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-419">tax registry number</span></span>
  
<span data-ttu-id="b60ec-420">Registro fiscale No.</span><span class="sxs-lookup"><span data-stu-id="b60ec-420">tax registry no.</span></span>
  
<span data-ttu-id="b60ec-421">AFM #</span><span class="sxs-lookup"><span data-stu-id="b60ec-421">afm#</span></span>
  
<span data-ttu-id="b60ec-422">latta #</span><span class="sxs-lookup"><span data-stu-id="b60ec-422">tin#</span></span>
  
<span data-ttu-id="b60ec-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-423">taxidno#</span></span>
  
<span data-ttu-id="b60ec-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-424">taxregistryno#</span></span>
  
<span data-ttu-id="b60ec-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="b60ec-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="b60ec-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="b60ec-426">aφμ</span></span>
  
<span data-ttu-id="b60ec-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="b60ec-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="b60ec-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="b60ec-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="b60ec-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="b60ec-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="b60ec-430">Ungheria</span><span class="sxs-lookup"><span data-stu-id="b60ec-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-431">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-431">Format</span></span>

<span data-ttu-id="b60ec-432">Dieci cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-433">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-433">Pattern</span></span>

<span data-ttu-id="b60ec-434">Dieci cifre:</span><span class="sxs-lookup"><span data-stu-id="b60ec-434">Ten digits:</span></span>
  
-  <span data-ttu-id="b60ec-435">Una cifra che deve essere "8"</span><span class="sxs-lookup"><span data-stu-id="b60ec-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="b60ec-436">Cinque cifre che corrispondono al numero di giorni compresi tra la data 01/01/1867 e la data di nascita dell'individuo</span><span class="sxs-lookup"><span data-stu-id="b60ec-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="b60ec-437">Tre cifre che corrispondono al numero generato dalla possibilità di distinguere gli individui nati nello stesso giorno</span><span class="sxs-lookup"><span data-stu-id="b60ec-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="b60ec-438">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="b60ec-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-439">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-439">Checksum</span></span>

<span data-ttu-id="b60ec-440">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-441">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-441">Definition</span></span>

<span data-ttu-id="b60ec-442">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-443">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-444">Viene trovata una `Keywords_hungary_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-445">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-446">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-447">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="b60ec-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-449">numero di identificazione fiscale ungherese</span><span class="sxs-lookup"><span data-stu-id="b60ec-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="b60ec-450">Tin ungherese</span><span class="sxs-lookup"><span data-stu-id="b60ec-450">hungarian tin</span></span>
  
<span data-ttu-id="b60ec-451">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-451">tax id number</span></span>
  
<span data-ttu-id="b60ec-452">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="b60ec-452">vat number</span></span>
  
<span data-ttu-id="b60ec-453">autorità tributaria No</span><span class="sxs-lookup"><span data-stu-id="b60ec-453">tax authority no</span></span>
  
<span data-ttu-id="b60ec-454">numero dell'identità fiscale dell'ID fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-454">tax id tax identity number</span></span>
  
<span data-ttu-id="b60ec-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="b60ec-455">taxidnumber#</span></span>
  
<span data-ttu-id="b60ec-456">latta #</span><span class="sxs-lookup"><span data-stu-id="b60ec-456">tin#</span></span>
  
<span data-ttu-id="b60ec-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="b60ec-457">hungatiantin#</span></span>
  
<span data-ttu-id="b60ec-458">identificazione fiscale No</span><span class="sxs-lookup"><span data-stu-id="b60ec-458">tax identification no</span></span>
  
<span data-ttu-id="b60ec-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-459">taxidno#</span></span>
  
<span data-ttu-id="b60ec-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="b60ec-460">adóazonosító szám</span></span>
  
<span data-ttu-id="b60ec-461">adószám</span><span class="sxs-lookup"><span data-stu-id="b60ec-461">adószám</span></span>
  
<span data-ttu-id="b60ec-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="b60ec-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="b60ec-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="b60ec-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-464">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-464">Format</span></span>

<span data-ttu-id="b60ec-465">Sette cifre seguite da una lettera senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-466">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-466">Pattern</span></span>

<span data-ttu-id="b60ec-467">Sette cifre seguite da una lettera:</span><span class="sxs-lookup"><span data-stu-id="b60ec-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="b60ec-468">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-468">Seven digits</span></span> 
    
- <span data-ttu-id="b60ec-469">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-470">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-470">Checksum</span></span>

<span data-ttu-id="b60ec-471">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="b60ec-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-472">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-472">Definition</span></span>

<span data-ttu-id="b60ec-473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-474">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-475">Viene trovata una `Keywords_ireland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-476">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-477">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="b60ec-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-480">servizio pubblico no</span><span class="sxs-lookup"><span data-stu-id="b60ec-480">public service no</span></span>
  
<span data-ttu-id="b60ec-481">servizio pubblico personale No</span><span class="sxs-lookup"><span data-stu-id="b60ec-481">personal public service no</span></span>
  
<span data-ttu-id="b60ec-482">PPS No</span><span class="sxs-lookup"><span data-stu-id="b60ec-482">pps no</span></span>
  
<span data-ttu-id="b60ec-483">servizio personale No</span><span class="sxs-lookup"><span data-stu-id="b60ec-483">personal service no</span></span>
  
<span data-ttu-id="b60ec-484">servizio PPS No</span><span class="sxs-lookup"><span data-stu-id="b60ec-484">pps service no</span></span>
  
<span data-ttu-id="b60ec-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-485">ppsno#</span></span>
  
<span data-ttu-id="b60ec-486">Irish PPS No</span><span class="sxs-lookup"><span data-stu-id="b60ec-486">irish pps no</span></span>
  
<span data-ttu-id="b60ec-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-487">publicserviceno#</span></span>
  
<span data-ttu-id="b60ec-488">numero di servizio pubblico personale</span><span class="sxs-lookup"><span data-stu-id="b60ec-488">personal public service number</span></span>
  
<span data-ttu-id="b60ec-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="b60ec-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="b60ec-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="b60ec-490">pps uimh</span></span>
  
<span data-ttu-id="b60ec-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="b60ec-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="b60ec-492">Italia</span><span class="sxs-lookup"><span data-stu-id="b60ec-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-493">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-493">Format</span></span>

<span data-ttu-id="b60ec-494">16 lettere e cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="b60ec-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-495">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-495">Pattern</span></span>

<span data-ttu-id="b60ec-496">16 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="b60ec-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="b60ec-497">Tre lettere che corrispondono alle prime tre consonanti del nome di famiglia</span><span class="sxs-lookup"><span data-stu-id="b60ec-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="b60ec-498">Tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome</span><span class="sxs-lookup"><span data-stu-id="b60ec-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="b60ec-499">Due cifre che corrispondono alle ultime cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="b60ec-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="b60ec-500">Una cifra corrispondente al mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)</span><span class="sxs-lookup"><span data-stu-id="b60ec-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="b60ec-501">Due cifre che corrispondono al giorno del mese di nascita in cui 40 viene aggiunto al giorno di nascita per le femmine per differenziare dai maschi</span><span class="sxs-lookup"><span data-stu-id="b60ec-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="b60ec-502">Quattro cifre che corrispondono a un codice di area specifico per il comune in cui è nata la persona: vengono utilizzati codici a livello nazionale per i paesi esteri</span><span class="sxs-lookup"><span data-stu-id="b60ec-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="b60ec-503">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="b60ec-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-504">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-504">Checksum</span></span>

<span data-ttu-id="b60ec-505">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-506">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-506">Definition</span></span>

<span data-ttu-id="b60ec-507">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-508">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-509">Viene trovata una `Keywords_italy_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-510">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-511">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-512">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="b60ec-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-514">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-514">tax number</span></span>
  
<span data-ttu-id="b60ec-515">tassa no.</span><span class="sxs-lookup"><span data-stu-id="b60ec-515">tax no.</span></span>
  
<span data-ttu-id="b60ec-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-516">taxno#</span></span>
  
<span data-ttu-id="b60ec-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b60ec-517">taxnumber#</span></span>
  
<span data-ttu-id="b60ec-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b60ec-518">taxnumber</span></span>
  
<span data-ttu-id="b60ec-519">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-519">tax id</span></span>
  
<span data-ttu-id="b60ec-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-520">taxid#</span></span>
  
<span data-ttu-id="b60ec-521">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-521">fiscal code</span></span>
  
<span data-ttu-id="b60ec-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="b60ec-523">Lettonia</span><span class="sxs-lookup"><span data-stu-id="b60ec-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-524">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-524">Format</span></span>

<span data-ttu-id="b60ec-525">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-526">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-526">Pattern</span></span>

<span data-ttu-id="b60ec-527">11 cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="b60ec-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="b60ec-528">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="b60ec-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="b60ec-529">Una cifra che corrisponde al secolo di nascita dove "0" corrisponde al XIX secolo, "1" corrisponde al 20 ° secolo e "2" corrisponde al XXI secolo</span><span class="sxs-lookup"><span data-stu-id="b60ec-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="b60ec-530">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-531">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-531">Checksum</span></span>

<span data-ttu-id="b60ec-532">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-533">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-533">Definition</span></span>

<span data-ttu-id="b60ec-534">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-535">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-536">Viene trovata una `Keywords_latvia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-537">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-538">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-539">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="b60ec-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-541">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-541">tax number</span></span>
  
<span data-ttu-id="b60ec-542">tassa no.</span><span class="sxs-lookup"><span data-stu-id="b60ec-542">tax no.</span></span>
  
<span data-ttu-id="b60ec-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-543">taxno#</span></span>
  
<span data-ttu-id="b60ec-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b60ec-544">taxnumber#</span></span>
  
<span data-ttu-id="b60ec-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b60ec-545">taxnumber</span></span>
  
<span data-ttu-id="b60ec-546">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-546">tax id</span></span>
  
<span data-ttu-id="b60ec-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-547">taxid#</span></span>
  
<span data-ttu-id="b60ec-548">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-548">tax identification number</span></span>
  
<span data-ttu-id="b60ec-549">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="b60ec-549">tax identification no.</span></span>
  
<span data-ttu-id="b60ec-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="b60ec-550">nodokļa numurs</span></span>
  
<span data-ttu-id="b60ec-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="b60ec-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="b60ec-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="b60ec-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="b60ec-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="b60ec-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-554">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-554">Format</span></span>

<span data-ttu-id="b60ec-555">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-556">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-556">Pattern</span></span>

<span data-ttu-id="b60ec-557">11 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b60ec-558">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-558">Checksum</span></span>

<span data-ttu-id="b60ec-559">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="b60ec-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-560">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-560">Definition</span></span>

<span data-ttu-id="b60ec-561">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-562">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-563">Viene trovata una `Keywords_lithuania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-564">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-565">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-566">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="b60ec-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-568">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-568">tax number</span></span>
  
<span data-ttu-id="b60ec-569">tassa no.</span><span class="sxs-lookup"><span data-stu-id="b60ec-569">tax no.</span></span>
  
<span data-ttu-id="b60ec-570">tax no #</span><span class="sxs-lookup"><span data-stu-id="b60ec-570">tax no#</span></span>
  
<span data-ttu-id="b60ec-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b60ec-571">taxnumber#</span></span>
  
<span data-ttu-id="b60ec-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b60ec-572">taxnumber</span></span>
  
<span data-ttu-id="b60ec-573">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-573">tax id</span></span>
  
<span data-ttu-id="b60ec-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-574">taxid#</span></span>
  
<span data-ttu-id="b60ec-575">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-575">tax identification number</span></span>
  
<span data-ttu-id="b60ec-576">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="b60ec-576">tax identification no.</span></span>
  
<span data-ttu-id="b60ec-577">ID mokesčių</span><span class="sxs-lookup"><span data-stu-id="b60ec-577">mokesčių id</span></span>
  
<span data-ttu-id="b60ec-578">numeri mokesčių</span><span class="sxs-lookup"><span data-stu-id="b60ec-578">mokesčių numeris</span></span>
  
<span data-ttu-id="b60ec-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="b60ec-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="b60ec-580">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="b60ec-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-581">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-581">Format</span></span>

<span data-ttu-id="b60ec-582">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-583">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-583">Pattern</span></span>

<span data-ttu-id="b60ec-584">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="b60ec-584">13 digits:</span></span>
  
-  <span data-ttu-id="b60ec-585">11 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-585">11 digits</span></span> 
    
- <span data-ttu-id="b60ec-586">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="b60ec-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-587">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-587">Checksum</span></span>

<span data-ttu-id="b60ec-588">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-589">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-589">Definition</span></span>

<span data-ttu-id="b60ec-590">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-591">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-592">Viene trovata una `Keywords_luxemburg_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-593">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-594">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-595">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="b60ec-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-597">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-597">tax number</span></span>
  
<span data-ttu-id="b60ec-598">tassa no.</span><span class="sxs-lookup"><span data-stu-id="b60ec-598">tax no.</span></span>
  
<span data-ttu-id="b60ec-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-599">taxno#</span></span>
  
<span data-ttu-id="b60ec-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b60ec-600">taxnumber#</span></span>
  
<span data-ttu-id="b60ec-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b60ec-601">taxnumber</span></span>
  
<span data-ttu-id="b60ec-602">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-602">tax id</span></span>
  
<span data-ttu-id="b60ec-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-603">taxid#</span></span>
  
<span data-ttu-id="b60ec-604">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-604">tax identification number</span></span>
  
<span data-ttu-id="b60ec-605">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="b60ec-605">tax identification no.</span></span>
  
<span data-ttu-id="b60ec-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="b60ec-606">steuernummer</span></span>
  
<span data-ttu-id="b60ec-607">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="b60ec-607">steuer id</span></span>
  
<span data-ttu-id="b60ec-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="b60ec-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="b60ec-609">Malta</span><span class="sxs-lookup"><span data-stu-id="b60ec-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-610">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-610">Format</span></span>

<span data-ttu-id="b60ec-611">Per cittadini maltesi: 7 cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="b60ec-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="b60ec-612">Nazionali non maltesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-613">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-613">Pattern</span></span>

<span data-ttu-id="b60ec-614">Cittadini maltesi: 7 cifre e una lettera</span><span class="sxs-lookup"><span data-stu-id="b60ec-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="b60ec-615">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-615">Seven digits</span></span> 
    
- <span data-ttu-id="b60ec-616">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="b60ec-617">Nazionali non maltesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="b60ec-618">9 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="b60ec-619">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-619">Checksum</span></span>

<span data-ttu-id="b60ec-620">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="b60ec-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-621">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-621">Definition</span></span>

<span data-ttu-id="b60ec-622">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-623">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-624">Viene trovata una `Keywords_malta_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-625">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-626">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-627">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="b60ec-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-629">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-629">tax number</span></span>
  
<span data-ttu-id="b60ec-630">tassa no.</span><span class="sxs-lookup"><span data-stu-id="b60ec-630">tax no.</span></span>
  
<span data-ttu-id="b60ec-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-631">taxno#</span></span>
  
<span data-ttu-id="b60ec-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b60ec-632">taxnumber#</span></span>
  
<span data-ttu-id="b60ec-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b60ec-633">taxnumber</span></span>
  
<span data-ttu-id="b60ec-634">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-634">tax id</span></span>
  
<span data-ttu-id="b60ec-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-635">taxid#</span></span>
  
<span data-ttu-id="b60ec-636">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-636">tax identification number</span></span>
  
<span data-ttu-id="b60ec-637">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="b60ec-637">tax identification no.</span></span>
  
<span data-ttu-id="b60ec-638">numru Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="b60ec-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="b60ec-639">ID Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="b60ec-639">id tat-taxxa</span></span>
  
<span data-ttu-id="b60ec-640">numru ta ' identifikazzjoni Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="b60ec-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="b60ec-641">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="b60ec-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-642">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-642">Format</span></span>

<span data-ttu-id="b60ec-643">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-644">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-644">Pattern</span></span>

<span data-ttu-id="b60ec-645">9 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="b60ec-646">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-646">Checksum</span></span>

<span data-ttu-id="b60ec-647">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-648">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-648">Definition</span></span>

<span data-ttu-id="b60ec-649">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-650">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-651">Viene trovata una `Keywords_netherlands_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-652">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-653">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-654">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="b60ec-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-656">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="b60ec-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="b60ec-657">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="b60ec-657">netherlands tax identification</span></span>
  
<span data-ttu-id="b60ec-658">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="b60ec-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="b60ec-659">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="b60ec-659">netherland's tax identification</span></span>
  
<span data-ttu-id="b60ec-660">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-660">tax identification number</span></span>
  
<span data-ttu-id="b60ec-661">ID delle tasse olandesi</span><span class="sxs-lookup"><span data-stu-id="b60ec-661">dutch tax id</span></span>
  
<span data-ttu-id="b60ec-662">numero di identificazione fiscale olandese</span><span class="sxs-lookup"><span data-stu-id="b60ec-662">dutch tax identification number</span></span>
  
<span data-ttu-id="b60ec-663">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-663">tax id</span></span>
  
<span data-ttu-id="b60ec-664">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="b60ec-664">tax id#</span></span>
  
<span data-ttu-id="b60ec-665">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-665">tax number</span></span>
  
<span data-ttu-id="b60ec-666">tax no #</span><span class="sxs-lookup"><span data-stu-id="b60ec-666">tax no#</span></span>
  
<span data-ttu-id="b60ec-667">imposte #</span><span class="sxs-lookup"><span data-stu-id="b60ec-667">tax#</span></span>
  
<span data-ttu-id="b60ec-668">latta</span><span class="sxs-lookup"><span data-stu-id="b60ec-668">tin</span></span>
  
<span data-ttu-id="b60ec-669">latta #</span><span class="sxs-lookup"><span data-stu-id="b60ec-669">tin#</span></span>
  
<span data-ttu-id="b60ec-670">Tin olandesi</span><span class="sxs-lookup"><span data-stu-id="b60ec-670">netherlands tin</span></span>
  
<span data-ttu-id="b60ec-671">stagno degli olandesi</span><span class="sxs-lookup"><span data-stu-id="b60ec-671">netherland's tin</span></span>
  
<span data-ttu-id="b60ec-672">Nederlands identificatienummer di recente</span><span class="sxs-lookup"><span data-stu-id="b60ec-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="b60ec-673">identificatienummer van delasting</span><span class="sxs-lookup"><span data-stu-id="b60ec-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="b60ec-674">identificatienummer che dura</span><span class="sxs-lookup"><span data-stu-id="b60ec-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="b60ec-675">Nederlands identificatie di recente</span><span class="sxs-lookup"><span data-stu-id="b60ec-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="b60ec-676">l'ID di Nummer del Nederlands</span><span class="sxs-lookup"><span data-stu-id="b60ec-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="b60ec-677">Nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="b60ec-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="b60ec-678">BTW nummer</span><span class="sxs-lookup"><span data-stu-id="b60ec-678">btw nummer</span></span>
  
<span data-ttu-id="b60ec-679">Nederlandse che durerà identificatie</span><span class="sxs-lookup"><span data-stu-id="b60ec-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="b60ec-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="b60ec-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-681">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-681">Format</span></span>

<span data-ttu-id="b60ec-682">Undici cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-683">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-683">Pattern</span></span>

<span data-ttu-id="b60ec-684">Undici cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b60ec-685">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-685">Checksum</span></span>

<span data-ttu-id="b60ec-686">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-687">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-687">Definition</span></span>

<span data-ttu-id="b60ec-688">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-689">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-690">Viene trovata una `Keywords_poland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-691">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-692">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-693">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="b60ec-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-695">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-695">tax number</span></span>
  
<span data-ttu-id="b60ec-696">tassa no.</span><span class="sxs-lookup"><span data-stu-id="b60ec-696">tax no.</span></span>
  
<span data-ttu-id="b60ec-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-697">taxno#</span></span>
  
<span data-ttu-id="b60ec-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b60ec-698">taxnumber#</span></span>
  
<span data-ttu-id="b60ec-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b60ec-699">taxnumber</span></span>
  
<span data-ttu-id="b60ec-700">NIP</span><span class="sxs-lookup"><span data-stu-id="b60ec-700">nip</span></span>
  
<span data-ttu-id="b60ec-701">NIP #</span><span class="sxs-lookup"><span data-stu-id="b60ec-701">nip#</span></span>
  
<span data-ttu-id="b60ec-702">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-702">tax id</span></span>
  
<span data-ttu-id="b60ec-703">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="b60ec-703">tax id#</span></span>
  
<span data-ttu-id="b60ec-704">ID NIP</span><span class="sxs-lookup"><span data-stu-id="b60ec-704">nip id</span></span>
  
<span data-ttu-id="b60ec-705">ID NIP #</span><span class="sxs-lookup"><span data-stu-id="b60ec-705">nip id#</span></span>
  
<span data-ttu-id="b60ec-706">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-706">tax identification number</span></span>
  
<span data-ttu-id="b60ec-707">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="b60ec-707">tax identification no.</span></span>
  
<span data-ttu-id="b60ec-708">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="b60ec-708">vat number</span></span>
  
<span data-ttu-id="b60ec-709">IVA No.</span><span class="sxs-lookup"><span data-stu-id="b60ec-709">vat no.</span></span>
  
<span data-ttu-id="b60ec-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-710">vatno#</span></span>
  
<span data-ttu-id="b60ec-711">ID partita IVA</span><span class="sxs-lookup"><span data-stu-id="b60ec-711">vat id</span></span>
  
<span data-ttu-id="b60ec-712">ID partita IVA #</span><span class="sxs-lookup"><span data-stu-id="b60ec-712">vat id#</span></span>
  
<span data-ttu-id="b60ec-713">numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="b60ec-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="b60ec-714">Polski numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="b60ec-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="b60ec-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="b60ec-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="b60ec-716">Portogallo</span><span class="sxs-lookup"><span data-stu-id="b60ec-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-717">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-717">Format</span></span>

<span data-ttu-id="b60ec-718">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-719">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-719">Pattern</span></span>

<span data-ttu-id="b60ec-720">9 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b60ec-721">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-721">Checksum</span></span>

<span data-ttu-id="b60ec-722">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-723">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-723">Definition</span></span>

<span data-ttu-id="b60ec-724">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-725">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-726">Viene trovata una `Keywords_portugal_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-727">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-728">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-729">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="b60ec-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-731">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-731">tax number</span></span>
  
<span data-ttu-id="b60ec-732">tassa no.</span><span class="sxs-lookup"><span data-stu-id="b60ec-732">tax no.</span></span>
  
<span data-ttu-id="b60ec-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-733">taxno#</span></span>
  
<span data-ttu-id="b60ec-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b60ec-734">taxnumber#</span></span>
  
<span data-ttu-id="b60ec-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b60ec-735">taxnumber</span></span>
  
<span data-ttu-id="b60ec-736">NIF</span><span class="sxs-lookup"><span data-stu-id="b60ec-736">nif</span></span>
  
<span data-ttu-id="b60ec-737">NIF #</span><span class="sxs-lookup"><span data-stu-id="b60ec-737">nif#</span></span>
  
<span data-ttu-id="b60ec-738">numero fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-738">numero fiscal</span></span>
  
<span data-ttu-id="b60ec-739">número de identificação Fiscal</span><span class="sxs-lookup"><span data-stu-id="b60ec-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="b60ec-740">Romania</span><span class="sxs-lookup"><span data-stu-id="b60ec-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-741">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-741">Format</span></span>

<span data-ttu-id="b60ec-742">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-743">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-743">Pattern</span></span>

<span data-ttu-id="b60ec-744">13 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b60ec-745">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-745">Checksum</span></span>

<span data-ttu-id="b60ec-746">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="b60ec-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-747">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-747">Definition</span></span>

<span data-ttu-id="b60ec-748">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-749">L'espressione `Regex_romania_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-750">Viene trovata una `Keywords_romania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b60ec-751">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="b60ec-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-753">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-753">tax id</span></span>
  
<span data-ttu-id="b60ec-754">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-754">tax id number</span></span>
  
<span data-ttu-id="b60ec-755">Tax File No</span><span class="sxs-lookup"><span data-stu-id="b60ec-755">tax file no</span></span>
  
<span data-ttu-id="b60ec-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="b60ec-756">tax file number</span></span>
  
<span data-ttu-id="b60ec-757">tax no</span><span class="sxs-lookup"><span data-stu-id="b60ec-757">tax no</span></span>
  
<span data-ttu-id="b60ec-758">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-758">tax number</span></span>
  
<span data-ttu-id="b60ec-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-759">taxid#</span></span>
  
<span data-ttu-id="b60ec-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-760">taxno#</span></span>
  
<span data-ttu-id="b60ec-761">ID-ul taxei</span><span class="sxs-lookup"><span data-stu-id="b60ec-761">id-ul taxei</span></span>
  
<span data-ttu-id="b60ec-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="b60ec-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="b60ec-763">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="b60ec-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-764">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-764">Format</span></span>

<span data-ttu-id="b60ec-765">10 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-766">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-766">Pattern</span></span>

<span data-ttu-id="b60ec-767">10 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b60ec-768">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-768">Checksum</span></span>

<span data-ttu-id="b60ec-769">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="b60ec-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-770">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-770">Definition</span></span>

<span data-ttu-id="b60ec-771">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-772">L'espressione `Regex_slovakia_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-773">Viene trovata una `Keywords_slovakia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b60ec-774">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="b60ec-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-776">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-776">tax id</span></span>
  
<span data-ttu-id="b60ec-777">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-777">tax id number</span></span>
  
<span data-ttu-id="b60ec-778">ID Tin</span><span class="sxs-lookup"><span data-stu-id="b60ec-778">tin id</span></span>
  
<span data-ttu-id="b60ec-779">Tin No</span><span class="sxs-lookup"><span data-stu-id="b60ec-779">tin no</span></span>
  
<span data-ttu-id="b60ec-780">ID Tin slovacco</span><span class="sxs-lookup"><span data-stu-id="b60ec-780">slovakian tin id</span></span>
  
<span data-ttu-id="b60ec-781">latta</span><span class="sxs-lookup"><span data-stu-id="b60ec-781">tin</span></span>
  
<span data-ttu-id="b60ec-782">Tax File No</span><span class="sxs-lookup"><span data-stu-id="b60ec-782">tax file no</span></span>
  
<span data-ttu-id="b60ec-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="b60ec-783">tax file number</span></span>
  
<span data-ttu-id="b60ec-784">tax no</span><span class="sxs-lookup"><span data-stu-id="b60ec-784">tax no</span></span>
  
<span data-ttu-id="b60ec-785">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-785">tax number</span></span>
  
<span data-ttu-id="b60ec-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-786">taxid#</span></span>
  
<span data-ttu-id="b60ec-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-787">taxno#</span></span>
  
<span data-ttu-id="b60ec-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="b60ec-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="b60ec-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="b60ec-789">daňové číslo</span></span>
  
<span data-ttu-id="b60ec-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="b60ec-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="b60ec-791">Slovenia</span><span class="sxs-lookup"><span data-stu-id="b60ec-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-792">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-792">Format</span></span>

<span data-ttu-id="b60ec-793">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-794">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-794">Pattern</span></span>

<span data-ttu-id="b60ec-795">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b60ec-796">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-796">Checksum</span></span>

<span data-ttu-id="b60ec-797">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-798">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-798">Definition</span></span>

<span data-ttu-id="b60ec-799">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-800">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-801">Viene trovata una `Keywords_slovenia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-802">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-803">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-804">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="b60ec-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-806">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-806">tax id</span></span>
  
<span data-ttu-id="b60ec-807">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-807">tax id number</span></span>
  
<span data-ttu-id="b60ec-808">ID Tin</span><span class="sxs-lookup"><span data-stu-id="b60ec-808">tin id</span></span>
  
<span data-ttu-id="b60ec-809">Tin No</span><span class="sxs-lookup"><span data-stu-id="b60ec-809">tin no</span></span>
  
<span data-ttu-id="b60ec-810">ID Tin sloveno</span><span class="sxs-lookup"><span data-stu-id="b60ec-810">slovenian tin id</span></span>
  
<span data-ttu-id="b60ec-811">latta</span><span class="sxs-lookup"><span data-stu-id="b60ec-811">tin</span></span>
  
<span data-ttu-id="b60ec-812">Tax File No</span><span class="sxs-lookup"><span data-stu-id="b60ec-812">tax file no</span></span>
  
<span data-ttu-id="b60ec-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="b60ec-813">tax file number</span></span>
  
<span data-ttu-id="b60ec-814">tax no</span><span class="sxs-lookup"><span data-stu-id="b60ec-814">tax no</span></span>
  
<span data-ttu-id="b60ec-815">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-815">tax number</span></span>
  
<span data-ttu-id="b60ec-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-816">taxid#</span></span>
  
<span data-ttu-id="b60ec-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-817">taxno#</span></span>
  
<span data-ttu-id="b60ec-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="b60ec-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="b60ec-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="b60ec-819">davčna številka</span></span>
  
<span data-ttu-id="b60ec-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="b60ec-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="b60ec-821">Spagna</span><span class="sxs-lookup"><span data-stu-id="b60ec-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-822">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-822">Format</span></span>

<span data-ttu-id="b60ec-823">Sette o otto cifre e una o due lettere nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="b60ec-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-824">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-824">Pattern</span></span>

<span data-ttu-id="b60ec-825">Persone fisiche spagnole con carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="b60ec-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="b60ec-826">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-826">Eight digits</span></span> 
    
- <span data-ttu-id="b60ec-827">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="b60ec-828">Spagnoli non residenti senza una carta d'identità nazionale spagnola</span><span class="sxs-lookup"><span data-stu-id="b60ec-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="b60ec-829">Una lettera maiuscola "L" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="b60ec-830">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-830">Seven digits</span></span>
    
- <span data-ttu-id="b60ec-831">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="b60ec-832">Spagnoli residenti di età inferiore ai 14 anni senza una carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="b60ec-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="b60ec-833">Una lettera maiuscola "K" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="b60ec-834">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-834">Seven digits</span></span> 
    
- <span data-ttu-id="b60ec-835">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="b60ec-836">Stranieri con il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="b60ec-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="b60ec-837">Una lettera maiuscola che è "X", "Y" o "Z" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="b60ec-838">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-838">Seven digits</span></span>
    
- <span data-ttu-id="b60ec-839">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="b60ec-840">Stranieri senza il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="b60ec-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="b60ec-841">Una lettera maiuscola che è "M" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="b60ec-842">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-842">Seven digits</span></span>
    
- <span data-ttu-id="b60ec-843">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="b60ec-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="b60ec-844">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-844">Checksum</span></span>

<span data-ttu-id="b60ec-845">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-846">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-846">Definition</span></span>

<span data-ttu-id="b60ec-847">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-848">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-849">Viene trovata una `Keywords_spain_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-850">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-851">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-852">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="b60ec-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-854">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-854">tax id</span></span>
  
<span data-ttu-id="b60ec-855">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-855">tax id number</span></span>
  
<span data-ttu-id="b60ec-856">ID CIF</span><span class="sxs-lookup"><span data-stu-id="b60ec-856">cif id</span></span>
  
<span data-ttu-id="b60ec-857">CIF No</span><span class="sxs-lookup"><span data-stu-id="b60ec-857">cif no</span></span>
  
<span data-ttu-id="b60ec-858">ID CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="b60ec-858">spanish cif id</span></span>
  
<span data-ttu-id="b60ec-859">CIF</span><span class="sxs-lookup"><span data-stu-id="b60ec-859">cif</span></span>
  
<span data-ttu-id="b60ec-860">Tax File No</span><span class="sxs-lookup"><span data-stu-id="b60ec-860">tax file no</span></span>
  
<span data-ttu-id="b60ec-861">numero CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="b60ec-861">spanish cif number</span></span>
  
<span data-ttu-id="b60ec-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="b60ec-862">tax file number</span></span>
  
<span data-ttu-id="b60ec-863">Spagnolo CIF No</span><span class="sxs-lookup"><span data-stu-id="b60ec-863">spanish cif no</span></span>
  
<span data-ttu-id="b60ec-864">tax no</span><span class="sxs-lookup"><span data-stu-id="b60ec-864">tax no</span></span>
  
<span data-ttu-id="b60ec-865">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-865">tax number</span></span>
  
<span data-ttu-id="b60ec-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-866">taxid#</span></span>
  
<span data-ttu-id="b60ec-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-867">taxno#</span></span>
  
<span data-ttu-id="b60ec-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-868">cifid#</span></span>
  
<span data-ttu-id="b60ec-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-869">spanishcifid#</span></span>
  
<span data-ttu-id="b60ec-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="b60ec-870">spanishcifno#</span></span>
  
<span data-ttu-id="b60ec-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="b60ec-871">número de contribuyente</span></span>
  
<span data-ttu-id="b60ec-872">número de Impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="b60ec-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="b60ec-873">número de Identificación Fiscal</span><span class="sxs-lookup"><span data-stu-id="b60ec-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="b60ec-874">número CIF</span><span class="sxs-lookup"><span data-stu-id="b60ec-874">cif número</span></span>
  
<span data-ttu-id="b60ec-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="b60ec-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="b60ec-876">Svezia</span><span class="sxs-lookup"><span data-stu-id="b60ec-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-877">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-877">Format</span></span>

<span data-ttu-id="b60ec-878">Dieci cifre e un simbolo nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="b60ec-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-879">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-879">Pattern</span></span>

<span data-ttu-id="b60ec-880">Dieci cifre e un simbolo:</span><span class="sxs-lookup"><span data-stu-id="b60ec-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="b60ec-881">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="b60ec-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="b60ec-882">Segno di addizione, segno meno o barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="b60ec-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="b60ec-883">Tre cifre che rendono il numero di identificazione univoco dove:</span><span class="sxs-lookup"><span data-stu-id="b60ec-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="b60ec-884">Per i numeri emessi prima del 1990, la settima e la terza cifra identificano la Contea di nascita o gli stranieri nati</span><span class="sxs-lookup"><span data-stu-id="b60ec-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="b60ec-885">La cifra nella nona posizione indica il sesso per il maschio o per la femmina.</span><span class="sxs-lookup"><span data-stu-id="b60ec-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="b60ec-886">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="b60ec-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b60ec-887">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-887">Checksum</span></span>

<span data-ttu-id="b60ec-888">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-889">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-889">Definition</span></span>

<span data-ttu-id="b60ec-890">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-891">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-892">Viene trovata una `Keywords_sweden_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b60ec-893">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-894">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="b60ec-895">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="b60ec-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-897">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-897">tax id</span></span>
  
<span data-ttu-id="b60ec-898">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="b60ec-898">tax id no.</span></span>
  
<span data-ttu-id="b60ec-899">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-899">tax id number</span></span>
  
<span data-ttu-id="b60ec-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="b60ec-900">tax identification</span></span>
  
<span data-ttu-id="b60ec-901">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="b60ec-901">tax identification#</span></span>
  
<span data-ttu-id="b60ec-902">tassa no.</span><span class="sxs-lookup"><span data-stu-id="b60ec-902">tax no.</span></span>
  
<span data-ttu-id="b60ec-903">imposte #</span><span class="sxs-lookup"><span data-stu-id="b60ec-903">tax#</span></span>
  
<span data-ttu-id="b60ec-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-904">taxid#</span></span>
  
<span data-ttu-id="b60ec-905">file fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-905">tax file</span></span>
  
<span data-ttu-id="b60ec-906">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="b60ec-906">tax file no.</span></span>
  
<span data-ttu-id="b60ec-907">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="b60ec-907">personal id number</span></span>
  
<span data-ttu-id="b60ec-908">ID pattinat Nummer</span><span class="sxs-lookup"><span data-stu-id="b60ec-908">skatt id nummer</span></span>
  
<span data-ttu-id="b60ec-909">Identifikation skatet</span><span class="sxs-lookup"><span data-stu-id="b60ec-909">skatt identifikation</span></span>
  
<span data-ttu-id="b60ec-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="b60ec-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="b60ec-911">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="b60ec-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="b60ec-912">Formato</span><span class="sxs-lookup"><span data-stu-id="b60ec-912">Format</span></span>

<span data-ttu-id="b60ec-913">Riferimento per i contribuenti unici (UTR): 10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="b60ec-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="b60ec-914">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="b60ec-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="b60ec-915">Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="b60ec-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b60ec-916">Modello</span><span class="sxs-lookup"><span data-stu-id="b60ec-916">Pattern</span></span>

<span data-ttu-id="b60ec-917">Riferimento per i contribuenti unici (UTR): 10 cifre</span><span class="sxs-lookup"><span data-stu-id="b60ec-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="b60ec-918">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="b60ec-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="b60ec-919">Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="b60ec-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b60ec-920">Checksum</span><span class="sxs-lookup"><span data-stu-id="b60ec-920">Checksum</span></span>

<span data-ttu-id="b60ec-921">Sì</span><span class="sxs-lookup"><span data-stu-id="b60ec-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b60ec-922">Definizione</span><span class="sxs-lookup"><span data-stu-id="b60ec-922">Definition</span></span>

<span data-ttu-id="b60ec-923">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="b60ec-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b60ec-924">La funzione `Func_uk_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="b60ec-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b60ec-925">Viene trovata una `Keywords_uk_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="b60ec-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b60ec-926">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b60ec-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="b60ec-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b60ec-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="b60ec-928">tax id</span><span class="sxs-lookup"><span data-stu-id="b60ec-928">tax id</span></span>
  
<span data-ttu-id="b60ec-929">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="b60ec-929">tax id no.</span></span>
  
<span data-ttu-id="b60ec-930">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-930">tax id number</span></span>
  
<span data-ttu-id="b60ec-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="b60ec-931">tax identification</span></span>
  
<span data-ttu-id="b60ec-932">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="b60ec-932">tax identification#</span></span>
  
<span data-ttu-id="b60ec-933">tassa no.</span><span class="sxs-lookup"><span data-stu-id="b60ec-933">tax no.</span></span>
  
<span data-ttu-id="b60ec-934">imposte #</span><span class="sxs-lookup"><span data-stu-id="b60ec-934">tax#</span></span>
  
<span data-ttu-id="b60ec-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="b60ec-935">taxid#</span></span>
  
<span data-ttu-id="b60ec-936">file fiscale</span><span class="sxs-lookup"><span data-stu-id="b60ec-936">tax file</span></span>
  
<span data-ttu-id="b60ec-937">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="b60ec-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b60ec-938">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b60ec-938">See also</span></span>

[<span data-ttu-id="b60ec-939">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="b60ec-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

