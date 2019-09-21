---
title: Codice di previdenza sociale dell'Unione europea o ID equivalente
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando rileva il numero di previdenza sociale dell'Unione europea o il tipo di informazioni riservate ID equivalente. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: b42a8d927e18f813eb6ef6d1d55b2de15ea9dcd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083669"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="7eee3-104">Codice di previdenza sociale dell'Unione europea o ID equivalente</span><span class="sxs-lookup"><span data-stu-id="7eee3-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="7eee3-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP, Data Loss Prevention), quando viene rilevato il codice fiscale dell'Unione europea (SSN) o il tipo di informazioni sensibili ID equivalente.</span><span class="sxs-lookup"><span data-stu-id="7eee3-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="7eee3-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="7eee3-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="7eee3-107">Austria</span><span class="sxs-lookup"><span data-stu-id="7eee3-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="7eee3-108">Formato</span><span class="sxs-lookup"><span data-stu-id="7eee3-108">Format</span></span>

<span data-ttu-id="7eee3-109">10 cifre nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="7eee3-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7eee3-110">Modello</span><span class="sxs-lookup"><span data-stu-id="7eee3-110">Pattern</span></span>

<span data-ttu-id="7eee3-111">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="7eee3-111">10 digits:</span></span>
  
-  <span data-ttu-id="7eee3-112">Tre cifre che corrispondono a un numero di serie</span><span class="sxs-lookup"><span data-stu-id="7eee3-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="7eee3-113">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7eee3-113">One check digit</span></span>
    
- <span data-ttu-id="7eee3-114">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="7eee3-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7eee3-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="7eee3-115">Checksum</span></span>

<span data-ttu-id="7eee3-116">Sì</span><span class="sxs-lookup"><span data-stu-id="7eee3-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7eee3-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="7eee3-117">Definition</span></span>

<span data-ttu-id="7eee3-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-119">La funzione `Func_austria_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7eee3-120">Viene trovata una `Keywords_austria_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="7eee3-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7eee3-121">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-122">La funzione `Func_austria_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7eee3-123">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7eee3-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="7eee3-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7eee3-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7eee3-125">previdenza sociale No</span><span class="sxs-lookup"><span data-stu-id="7eee3-125">social security no</span></span>
  
<span data-ttu-id="7eee3-126">social security number</span><span class="sxs-lookup"><span data-stu-id="7eee3-126">social security number</span></span>
  
<span data-ttu-id="7eee3-127">social security code</span><span class="sxs-lookup"><span data-stu-id="7eee3-127">social security code</span></span>
  
<span data-ttu-id="7eee3-128">numero assicurativo</span><span class="sxs-lookup"><span data-stu-id="7eee3-128">insurance number</span></span>
  
<span data-ttu-id="7eee3-129">SSN austriaco</span><span class="sxs-lookup"><span data-stu-id="7eee3-129">austrian ssn</span></span>
  
<span data-ttu-id="7eee3-130">SSN #</span><span class="sxs-lookup"><span data-stu-id="7eee3-130">ssn#</span></span>
  
<span data-ttu-id="7eee3-131">SSN</span><span class="sxs-lookup"><span data-stu-id="7eee3-131">ssn</span></span>
  
<span data-ttu-id="7eee3-132">codice assicurativo</span><span class="sxs-lookup"><span data-stu-id="7eee3-132">insurance code</span></span>
  
<span data-ttu-id="7eee3-133">codice assicurativo #</span><span class="sxs-lookup"><span data-stu-id="7eee3-133">insurance code#</span></span>
  
<span data-ttu-id="7eee3-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="7eee3-134">socialsecurityno#</span></span>
  
<span data-ttu-id="7eee3-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="7eee3-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="7eee3-136">soziale Sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="7eee3-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="7eee3-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="7eee3-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="7eee3-138">Belgio</span><span class="sxs-lookup"><span data-stu-id="7eee3-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="7eee3-139">Formato</span><span class="sxs-lookup"><span data-stu-id="7eee3-139">Format</span></span>

<span data-ttu-id="7eee3-140">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="7eee3-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7eee3-141">Modello</span><span class="sxs-lookup"><span data-stu-id="7eee3-141">Pattern</span></span>

<span data-ttu-id="7eee3-142">11 cifre</span><span class="sxs-lookup"><span data-stu-id="7eee3-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7eee3-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="7eee3-143">Checksum</span></span>

<span data-ttu-id="7eee3-144">Sì</span><span class="sxs-lookup"><span data-stu-id="7eee3-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7eee3-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="7eee3-145">Definition</span></span>

<span data-ttu-id="7eee3-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-147">La funzione `Func_belgium_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7eee3-148">Viene trovata una `Keywords_belgium_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="7eee3-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7eee3-149">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-150">La funzione `Func_belgium_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7eee3-151">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7eee3-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="7eee3-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7eee3-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7eee3-153">numero nazionale belga</span><span class="sxs-lookup"><span data-stu-id="7eee3-153">belgian national number</span></span>
  
<span data-ttu-id="7eee3-154">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="7eee3-154">national number</span></span>
  
<span data-ttu-id="7eee3-155">social security number</span><span class="sxs-lookup"><span data-stu-id="7eee3-155">social security number</span></span>
  
<span data-ttu-id="7eee3-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="7eee3-156">nationalnumber#</span></span>
  
<span data-ttu-id="7eee3-157">SSN #</span><span class="sxs-lookup"><span data-stu-id="7eee3-157">ssn#</span></span>
  
<span data-ttu-id="7eee3-158">SSN</span><span class="sxs-lookup"><span data-stu-id="7eee3-158">ssn</span></span>
  
<span data-ttu-id="7eee3-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="7eee3-159">nationalnumber</span></span>
  
<span data-ttu-id="7eee3-160">BNN #</span><span class="sxs-lookup"><span data-stu-id="7eee3-160">bnn#</span></span>
  
<span data-ttu-id="7eee3-161">BNN</span><span class="sxs-lookup"><span data-stu-id="7eee3-161">bnn</span></span>
  
<span data-ttu-id="7eee3-162">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="7eee3-162">personal id number</span></span>
  
<span data-ttu-id="7eee3-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="7eee3-163">personalidnumber#</span></span>
  
<span data-ttu-id="7eee3-164">numéro nazionale</span><span class="sxs-lookup"><span data-stu-id="7eee3-164">numéro national</span></span>
  
<span data-ttu-id="7eee3-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="7eee3-165">numéro de sécurité</span></span>
  
<span data-ttu-id="7eee3-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="7eee3-166">numéro d'assuré</span></span>
  
<span data-ttu-id="7eee3-167">identificazione nazionale</span><span class="sxs-lookup"><span data-stu-id="7eee3-167">identifiant national</span></span>
  
<span data-ttu-id="7eee3-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="7eee3-168">identifiantnational#</span></span>
  
<span data-ttu-id="7eee3-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="7eee3-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="7eee3-170">Croazia</span><span class="sxs-lookup"><span data-stu-id="7eee3-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="7eee3-171">Formato</span><span class="sxs-lookup"><span data-stu-id="7eee3-171">Format</span></span>

<span data-ttu-id="7eee3-172">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="7eee3-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7eee3-173">Modello</span><span class="sxs-lookup"><span data-stu-id="7eee3-173">Pattern</span></span>

 <span data-ttu-id="7eee3-174">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="7eee3-174">11 digits:</span></span> 
  
-  <span data-ttu-id="7eee3-175">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="7eee3-175">Ten digits</span></span> 
    
- <span data-ttu-id="7eee3-176">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7eee3-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7eee3-177">Checksum</span><span class="sxs-lookup"><span data-stu-id="7eee3-177">Checksum</span></span>

<span data-ttu-id="7eee3-178">Sì</span><span class="sxs-lookup"><span data-stu-id="7eee3-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7eee3-179">Definizione</span><span class="sxs-lookup"><span data-stu-id="7eee3-179">Definition</span></span>

<span data-ttu-id="7eee3-180">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-181">La funzione `Func_croatia_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7eee3-182">Viene trovata una `Keywords_croatia_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="7eee3-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7eee3-183">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-184">La funzione `Func_croatia_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7eee3-185">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7eee3-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="7eee3-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7eee3-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7eee3-187">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="7eee3-187">personal identification number</span></span>
  
<span data-ttu-id="7eee3-188">numero di cittadino Master</span><span class="sxs-lookup"><span data-stu-id="7eee3-188">master citizen number</span></span>
  
<span data-ttu-id="7eee3-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="7eee3-189">national identification number</span></span>
  
<span data-ttu-id="7eee3-190">social security number</span><span class="sxs-lookup"><span data-stu-id="7eee3-190">social security number</span></span>
  
<span data-ttu-id="7eee3-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="7eee3-191">nationalnumber#</span></span>
  
<span data-ttu-id="7eee3-192">SSN #</span><span class="sxs-lookup"><span data-stu-id="7eee3-192">ssn#</span></span>
  
<span data-ttu-id="7eee3-193">SSN</span><span class="sxs-lookup"><span data-stu-id="7eee3-193">ssn</span></span>
  
<span data-ttu-id="7eee3-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="7eee3-194">nationalnumber</span></span>
  
<span data-ttu-id="7eee3-195">BNN #</span><span class="sxs-lookup"><span data-stu-id="7eee3-195">bnn#</span></span>
  
<span data-ttu-id="7eee3-196">BNN</span><span class="sxs-lookup"><span data-stu-id="7eee3-196">bnn</span></span>
  
<span data-ttu-id="7eee3-197">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="7eee3-197">personal id number</span></span>
  
<span data-ttu-id="7eee3-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="7eee3-198">personalidnumber#</span></span>
  
<span data-ttu-id="7eee3-199">OIB</span><span class="sxs-lookup"><span data-stu-id="7eee3-199">oib</span></span>
  
<span data-ttu-id="7eee3-200">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="7eee3-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="7eee3-201">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="7eee3-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="7eee3-202">Formato</span><span class="sxs-lookup"><span data-stu-id="7eee3-202">Format</span></span>

<span data-ttu-id="7eee3-203">Dieci cifre e una barra rovesciata nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="7eee3-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7eee3-204">Modello</span><span class="sxs-lookup"><span data-stu-id="7eee3-204">Pattern</span></span>

<span data-ttu-id="7eee3-205">Dieci cifre e una barra rovesciata:</span><span class="sxs-lookup"><span data-stu-id="7eee3-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="7eee3-206">Sei cifre che corrispondono alla data di nascita (AAMMGG):</span><span class="sxs-lookup"><span data-stu-id="7eee3-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="7eee3-207">Una barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="7eee3-207">A backslash</span></span>
    
- <span data-ttu-id="7eee3-208">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="7eee3-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="7eee3-209">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7eee3-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7eee3-210">Checksum</span><span class="sxs-lookup"><span data-stu-id="7eee3-210">Checksum</span></span>

<span data-ttu-id="7eee3-211">Sì</span><span class="sxs-lookup"><span data-stu-id="7eee3-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7eee3-212">Definizione</span><span class="sxs-lookup"><span data-stu-id="7eee3-212">Definition</span></span>

<span data-ttu-id="7eee3-213">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-214">La funzione `Func_czech_republic_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7eee3-215">Viene trovata una `Keywords_czech_republic_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="7eee3-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7eee3-216">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-217">La funzione `Func_czech_republic_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7eee3-218">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7eee3-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="7eee3-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7eee3-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7eee3-220">numero di nascita</span><span class="sxs-lookup"><span data-stu-id="7eee3-220">birth number</span></span>
  
<span data-ttu-id="7eee3-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="7eee3-221">national identification number</span></span>
  
<span data-ttu-id="7eee3-222">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="7eee3-222">personal identification number</span></span>
  
<span data-ttu-id="7eee3-223">social security number</span><span class="sxs-lookup"><span data-stu-id="7eee3-223">social security number</span></span>
  
<span data-ttu-id="7eee3-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="7eee3-224">nationalnumber#</span></span>
  
<span data-ttu-id="7eee3-225">SSN #</span><span class="sxs-lookup"><span data-stu-id="7eee3-225">ssn#</span></span>
  
<span data-ttu-id="7eee3-226">SSN</span><span class="sxs-lookup"><span data-stu-id="7eee3-226">ssn</span></span>
  
<span data-ttu-id="7eee3-227">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="7eee3-227">national number</span></span>
  
<span data-ttu-id="7eee3-228">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="7eee3-228">personal id number</span></span>
  
<span data-ttu-id="7eee3-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="7eee3-229">personalidnumber#</span></span>
  
<span data-ttu-id="7eee3-230">rč</span><span class="sxs-lookup"><span data-stu-id="7eee3-230">rč</span></span>
  
<span data-ttu-id="7eee3-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="7eee3-231">rodné číslo</span></span>
  
<span data-ttu-id="7eee3-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="7eee3-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="7eee3-233">Danimarca</span><span class="sxs-lookup"><span data-stu-id="7eee3-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="7eee3-234">Formato</span><span class="sxs-lookup"><span data-stu-id="7eee3-234">Format</span></span>

<span data-ttu-id="7eee3-235">Dieci cifre e un trattino nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="7eee3-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7eee3-236">Modello</span><span class="sxs-lookup"><span data-stu-id="7eee3-236">Pattern</span></span>

<span data-ttu-id="7eee3-237">Dieci cifre e un trattino:</span><span class="sxs-lookup"><span data-stu-id="7eee3-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="7eee3-238">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="7eee3-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="7eee3-239">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7eee3-239">A hyphen</span></span>
    
- <span data-ttu-id="7eee3-240">Quattro cifre che corrispondono a un numero di sequenza</span><span class="sxs-lookup"><span data-stu-id="7eee3-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7eee3-241">Checksum</span><span class="sxs-lookup"><span data-stu-id="7eee3-241">Checksum</span></span>

<span data-ttu-id="7eee3-242">Sì</span><span class="sxs-lookup"><span data-stu-id="7eee3-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7eee3-243">Definizione</span><span class="sxs-lookup"><span data-stu-id="7eee3-243">Definition</span></span>

<span data-ttu-id="7eee3-244">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-245">La funzione `Func_denmark_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7eee3-246">Viene trovata una `Keywords_denmark_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="7eee3-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7eee3-247">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-248">La funzione `Func_denmark_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7eee3-249">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7eee3-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="7eee3-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7eee3-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7eee3-251">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="7eee3-251">personal identification number</span></span>
  
<span data-ttu-id="7eee3-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="7eee3-252">national identification number</span></span>
  
<span data-ttu-id="7eee3-253">social security number</span><span class="sxs-lookup"><span data-stu-id="7eee3-253">social security number</span></span>
  
<span data-ttu-id="7eee3-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="7eee3-254">nationalnumber#</span></span>
  
<span data-ttu-id="7eee3-255">SSN #</span><span class="sxs-lookup"><span data-stu-id="7eee3-255">ssn#</span></span>
  
<span data-ttu-id="7eee3-256">SSN</span><span class="sxs-lookup"><span data-stu-id="7eee3-256">ssn</span></span>
  
<span data-ttu-id="7eee3-257">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="7eee3-257">national number</span></span>
  
<span data-ttu-id="7eee3-258">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="7eee3-258">personal id number</span></span>
  
<span data-ttu-id="7eee3-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="7eee3-259">personalidnumber#</span></span>
  
<span data-ttu-id="7eee3-260">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="7eee3-260">cpr-nummer</span></span>
  
<span data-ttu-id="7eee3-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="7eee3-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="7eee3-262">Finlandia</span><span class="sxs-lookup"><span data-stu-id="7eee3-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="7eee3-263">Formato</span><span class="sxs-lookup"><span data-stu-id="7eee3-263">Format</span></span>

<span data-ttu-id="7eee3-264">Una combinazione di 11 caratteri nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="7eee3-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7eee3-265">Modello</span><span class="sxs-lookup"><span data-stu-id="7eee3-265">Pattern</span></span>

<span data-ttu-id="7eee3-266">Una combinazione di 11 caratteri nel formato specificato:</span><span class="sxs-lookup"><span data-stu-id="7eee3-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="7eee3-267">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="7eee3-267">Six digits</span></span> 
    
- <span data-ttu-id="7eee3-268">Un'istanza di una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7eee3-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="7eee3-269">Segno più</span><span class="sxs-lookup"><span data-stu-id="7eee3-269">Plus symbol</span></span>
    
  - <span data-ttu-id="7eee3-270">Segno meno</span><span class="sxs-lookup"><span data-stu-id="7eee3-270">Minus symbol</span></span>
    
  - <span data-ttu-id="7eee3-271">La lettera "A" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="7eee3-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="7eee3-272">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7eee3-272">Three digits</span></span>
    
- <span data-ttu-id="7eee3-273">Una lettera o una cifra</span><span class="sxs-lookup"><span data-stu-id="7eee3-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7eee3-274">Checksum</span><span class="sxs-lookup"><span data-stu-id="7eee3-274">Checksum</span></span>

<span data-ttu-id="7eee3-275">Sì</span><span class="sxs-lookup"><span data-stu-id="7eee3-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7eee3-276">Definizione</span><span class="sxs-lookup"><span data-stu-id="7eee3-276">Definition</span></span>

<span data-ttu-id="7eee3-277">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-278">La funzione `Func_finland_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7eee3-279">Viene trovata una `Keywords_finland_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="7eee3-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7eee3-280">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-281">La funzione `Func_finland_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7eee3-282">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7eee3-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="7eee3-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7eee3-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7eee3-284">identification number</span><span class="sxs-lookup"><span data-stu-id="7eee3-284">identification number</span></span>
  
<span data-ttu-id="7eee3-285">ID personale</span><span class="sxs-lookup"><span data-stu-id="7eee3-285">personal id</span></span>
  
<span data-ttu-id="7eee3-286">numero di identità</span><span class="sxs-lookup"><span data-stu-id="7eee3-286">identity number</span></span>
  
<span data-ttu-id="7eee3-287">numero di identificazione nazionale finlandese</span><span class="sxs-lookup"><span data-stu-id="7eee3-287">finnish national id number</span></span>
  
<span data-ttu-id="7eee3-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="7eee3-288">personalidnumber#</span></span>
  
<span data-ttu-id="7eee3-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="7eee3-289">national identification number</span></span>
  
<span data-ttu-id="7eee3-290">numero ID</span><span class="sxs-lookup"><span data-stu-id="7eee3-290">id number</span></span>
  
<span data-ttu-id="7eee3-291">ID nazionale No.</span><span class="sxs-lookup"><span data-stu-id="7eee3-291">national id no.</span></span>
  
<span data-ttu-id="7eee3-292">numero ID nazionale</span><span class="sxs-lookup"><span data-stu-id="7eee3-292">national id number</span></span>
  
<span data-ttu-id="7eee3-293">ID No</span><span class="sxs-lookup"><span data-stu-id="7eee3-293">id no</span></span>
  
<span data-ttu-id="7eee3-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="7eee3-294">tunnistenumero</span></span>
  
<span data-ttu-id="7eee3-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="7eee3-295">henkilötunnus</span></span>
  
<span data-ttu-id="7eee3-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="7eee3-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="7eee3-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="7eee3-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="7eee3-298">numero identiteetti</span><span class="sxs-lookup"><span data-stu-id="7eee3-298">identiteetti numero</span></span>
  
<span data-ttu-id="7eee3-299">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="7eee3-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="7eee3-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="7eee3-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="7eee3-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="7eee3-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="7eee3-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="7eee3-302">tunnusnumero</span></span>
  
<span data-ttu-id="7eee3-303">Kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="7eee3-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="7eee3-304">hetu</span><span class="sxs-lookup"><span data-stu-id="7eee3-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="7eee3-305">Francia</span><span class="sxs-lookup"><span data-stu-id="7eee3-305">France</span></span>

<span data-ttu-id="7eee3-306">Per informazioni dettagliate, vedere la sezione "Francia social previdenza (INSEE)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7eee3-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="7eee3-307">Germania</span><span class="sxs-lookup"><span data-stu-id="7eee3-307">Germany</span></span>

<span data-ttu-id="7eee3-308">Per informazioni dettagliate, vedere la sezione "Germania identità numero di carta" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7eee3-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="7eee3-309">Grecia</span><span class="sxs-lookup"><span data-stu-id="7eee3-309">Greece</span></span>

<span data-ttu-id="7eee3-310">Per informazioni dettagliate, vedere la sezione "Grecia National ID Card" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7eee3-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="7eee3-311">Ungheria</span><span class="sxs-lookup"><span data-stu-id="7eee3-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="7eee3-312">Formato</span><span class="sxs-lookup"><span data-stu-id="7eee3-312">Format</span></span>

<span data-ttu-id="7eee3-313">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="7eee3-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7eee3-314">Modello</span><span class="sxs-lookup"><span data-stu-id="7eee3-314">Pattern</span></span>

<span data-ttu-id="7eee3-315">9 cifre</span><span class="sxs-lookup"><span data-stu-id="7eee3-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7eee3-316">Checksum</span><span class="sxs-lookup"><span data-stu-id="7eee3-316">Checksum</span></span>

<span data-ttu-id="7eee3-317">Sì</span><span class="sxs-lookup"><span data-stu-id="7eee3-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7eee3-318">Definizione</span><span class="sxs-lookup"><span data-stu-id="7eee3-318">Definition</span></span>

<span data-ttu-id="7eee3-319">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-320">La funzione `Func_hungary_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7eee3-321">Viene trovata una `Keywords_hungary_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="7eee3-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7eee3-322">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-323">La funzione `Func_hungary_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7eee3-324">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7eee3-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="7eee3-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7eee3-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7eee3-326">codice di previdenza sociale ungherese</span><span class="sxs-lookup"><span data-stu-id="7eee3-326">hungarian social security number</span></span>
  
<span data-ttu-id="7eee3-327">social security number</span><span class="sxs-lookup"><span data-stu-id="7eee3-327">social security number</span></span>
  
<span data-ttu-id="7eee3-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="7eee3-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="7eee3-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="7eee3-329">hssn#</span></span>
  
<span data-ttu-id="7eee3-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="7eee3-330">socialsecuritynno</span></span>
  
<span data-ttu-id="7eee3-331">hssn</span><span class="sxs-lookup"><span data-stu-id="7eee3-331">hssn</span></span>
  
<span data-ttu-id="7eee3-332">Taj</span><span class="sxs-lookup"><span data-stu-id="7eee3-332">taj</span></span>
  
<span data-ttu-id="7eee3-333">Taj #</span><span class="sxs-lookup"><span data-stu-id="7eee3-333">taj#</span></span>
  
<span data-ttu-id="7eee3-334">SSN</span><span class="sxs-lookup"><span data-stu-id="7eee3-334">ssn</span></span>
  
<span data-ttu-id="7eee3-335">SSN #</span><span class="sxs-lookup"><span data-stu-id="7eee3-335">ssn#</span></span>
  
<span data-ttu-id="7eee3-336">previdenza sociale No</span><span class="sxs-lookup"><span data-stu-id="7eee3-336">social security no</span></span>
  
<span data-ttu-id="7eee3-337">áfa</span><span class="sxs-lookup"><span data-stu-id="7eee3-337">áfa</span></span>
  
<span data-ttu-id="7eee3-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="7eee3-338">közösségi adószám</span></span>
  
<span data-ttu-id="7eee3-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="7eee3-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="7eee3-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="7eee3-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="7eee3-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="7eee3-341">áfa szám</span></span>
  
<span data-ttu-id="7eee3-342">Magyar ÁFA szám</span><span class="sxs-lookup"><span data-stu-id="7eee3-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="7eee3-343">Portogallo</span><span class="sxs-lookup"><span data-stu-id="7eee3-343">Portugal</span></span>

<span data-ttu-id="7eee3-344">Per informazioni dettagliate, vedere la sezione "Portugal Citizen Card Number" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7eee3-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="7eee3-345">Spagna</span><span class="sxs-lookup"><span data-stu-id="7eee3-345">Spain</span></span>

<span data-ttu-id="7eee3-346">Per informazioni dettagliate, vedere la sezione "Spagna Social previdenza sociale (SSN)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="7eee3-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="7eee3-347">Svezia</span><span class="sxs-lookup"><span data-stu-id="7eee3-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="7eee3-348">Formato</span><span class="sxs-lookup"><span data-stu-id="7eee3-348">Format</span></span>

<span data-ttu-id="7eee3-349">12 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="7eee3-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7eee3-350">Modello</span><span class="sxs-lookup"><span data-stu-id="7eee3-350">Pattern</span></span>

<span data-ttu-id="7eee3-351">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="7eee3-351">12 digits:</span></span>
  
-  <span data-ttu-id="7eee3-352">Otto cifre che corrispondono alla data di nascita (AAAAMMGG)</span><span class="sxs-lookup"><span data-stu-id="7eee3-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="7eee3-353">Tre cifre che corrispondono a un numero di serie in cui:</span><span class="sxs-lookup"><span data-stu-id="7eee3-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="7eee3-354">L'ultima cifra del numero di serie indica il sesso per l'assegnazione di un numero dispari per il maschio e per un numero pari per la femmina</span><span class="sxs-lookup"><span data-stu-id="7eee3-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="7eee3-355">Fino a 1990, l'assegnazione del numero di serie corrispondeva alla contea in cui è Nato il portatore del numero o (se è nato prima del 1947) dove viveva, secondo i registri delle tasse, il 1 ° gennaio 1947, con un codice speciale (solitamente 9 come settima cifra) per immigrati</span><span class="sxs-lookup"><span data-stu-id="7eee3-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="7eee3-356">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7eee3-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7eee3-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="7eee3-357">Checksum</span></span>

<span data-ttu-id="7eee3-358">Sì</span><span class="sxs-lookup"><span data-stu-id="7eee3-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7eee3-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="7eee3-359">Definition</span></span>

<span data-ttu-id="7eee3-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-361">La funzione `Func_sweden_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7eee3-362">Viene trovata una `Keywords_sweden_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="7eee3-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="7eee3-363">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7eee3-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7eee3-364">La funzione `Func_sweden_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7eee3-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7eee3-365">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7eee3-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="7eee3-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="7eee3-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="7eee3-367">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="7eee3-367">personal id number</span></span>
  
<span data-ttu-id="7eee3-368">identification number</span><span class="sxs-lookup"><span data-stu-id="7eee3-368">identification number</span></span>
  
<span data-ttu-id="7eee3-369">ID personale No</span><span class="sxs-lookup"><span data-stu-id="7eee3-369">personal id no</span></span>
  
<span data-ttu-id="7eee3-370">identità No</span><span class="sxs-lookup"><span data-stu-id="7eee3-370">identity no</span></span>
  
<span data-ttu-id="7eee3-371">identificazione no</span><span class="sxs-lookup"><span data-stu-id="7eee3-371">identification no</span></span>
  
<span data-ttu-id="7eee3-372">identificazione personale No</span><span class="sxs-lookup"><span data-stu-id="7eee3-372">personal identification no</span></span>
  
<span data-ttu-id="7eee3-373">ID personnummer</span><span class="sxs-lookup"><span data-stu-id="7eee3-373">personnummer id</span></span>
  
<span data-ttu-id="7eee3-374">ID personligt-Nummer</span><span class="sxs-lookup"><span data-stu-id="7eee3-374">personligt id-nummer</span></span>
  
<span data-ttu-id="7eee3-375">ID unikt-Nummer</span><span class="sxs-lookup"><span data-stu-id="7eee3-375">unikt id-nummer</span></span>
  
<span data-ttu-id="7eee3-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="7eee3-376">personnummer</span></span>
  
<span data-ttu-id="7eee3-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="7eee3-377">identifikationsnumret</span></span>
  
<span data-ttu-id="7eee3-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="7eee3-378">personnummer#</span></span>
  
<span data-ttu-id="7eee3-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="7eee3-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7eee3-380">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7eee3-380">See also</span></span>

[<span data-ttu-id="7eee3-381">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="7eee3-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

