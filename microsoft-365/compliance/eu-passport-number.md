---
title: Numero di passaporto EU
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 44ee6e7b46d79772bcd3aec0fd26265f58f6c4c6
ms.sourcegitcommit: 3fd6d175c1954ce463198e835d1d8f2f91d80d79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2019
ms.locfileid: "39662801"
---
# <a name="eu-passport-number"></a><span data-ttu-id="fc9ac-104">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="fc9ac-104">EU Passport Number</span></span>

<span data-ttu-id="fc9ac-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="fc9ac-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="fc9ac-107">Austria</span><span class="sxs-lookup"><span data-stu-id="fc9ac-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-108">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-108">Format</span></span>

<span data-ttu-id="fc9ac-109">Una lettera seguita da uno spazio facoltativo e sette cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-110">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-110">Pattern</span></span>

<span data-ttu-id="fc9ac-111">Combinazione di una lettera, sette cifre e uno spazio:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="fc9ac-112">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="fc9ac-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="fc9ac-113">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="fc9ac-113">One space (optional)</span></span>
    
- <span data-ttu-id="fc9ac-114">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fc9ac-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-115">Checksum</span></span>

<span data-ttu-id="fc9ac-116">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fc9ac-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-117">Definition</span></span>

<span data-ttu-id="fc9ac-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-119">L'espressione `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-120">Viene trovata una `Keywords_austria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-121">Keywords</span></span>

<span data-ttu-id="fc9ac-122">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-122"></span></span>
|<span data-ttu-id="fc9ac-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-124">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-124">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-125">numero di passaporto austriaco</span><span class="sxs-lookup"><span data-stu-id="fc9ac-125">austrian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-126">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-126">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="fc9ac-127">reisepass</span></span>  <br/> <span data-ttu-id="fc9ac-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="fc9ac-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="fc9ac-129">Belgio</span><span class="sxs-lookup"><span data-stu-id="fc9ac-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-130">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-130">Format</span></span>

<span data-ttu-id="fc9ac-131">Due lettere seguite da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-132">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-132">Pattern</span></span>

<span data-ttu-id="fc9ac-133">Due lettere e seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-134">Checksum</span></span>

<span data-ttu-id="fc9ac-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fc9ac-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-136">Definition</span></span>

<span data-ttu-id="fc9ac-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-138">L'espressione `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-139">Viene trovata una `Keywords_belgium_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-140">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-140">Keywords</span></span>

<span data-ttu-id="fc9ac-141">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-141"></span></span>
|<span data-ttu-id="fc9ac-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-143">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-143">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-144">numero di passaporto belga</span><span class="sxs-lookup"><span data-stu-id="fc9ac-144">belgian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-145">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-145">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="fc9ac-146">paspoort</span></span>  <br/> <span data-ttu-id="fc9ac-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="fc9ac-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="fc9ac-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="fc9ac-148">reisepass kein</span></span>  <br/> <span data-ttu-id="fc9ac-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="fc9ac-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="fc9ac-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="fc9ac-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-151">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-151">Format</span></span>

<span data-ttu-id="fc9ac-152">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-153">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-153">Pattern</span></span>

 <span data-ttu-id="fc9ac-154">9 cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-155">Checksum</span></span>

<span data-ttu-id="fc9ac-156">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-157">Definition</span></span>

<span data-ttu-id="fc9ac-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-159">L'espressione `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-160">Viene trovata una `Keywords_bulgaria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-161">Keywords</span></span>

<span data-ttu-id="fc9ac-162">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-162"></span></span>
|<span data-ttu-id="fc9ac-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-164">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-164">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-165">numero di passaporto bulgaro</span><span class="sxs-lookup"><span data-stu-id="fc9ac-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-166">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-166">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-167">Номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="fc9ac-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="fc9ac-168">Croazia</span><span class="sxs-lookup"><span data-stu-id="fc9ac-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-169">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-169">Format</span></span>

<span data-ttu-id="fc9ac-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-171">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-171">Pattern</span></span>

 <span data-ttu-id="fc9ac-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-173">Checksum</span></span>

<span data-ttu-id="fc9ac-174">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-175">Definition</span></span>

<span data-ttu-id="fc9ac-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-177">L'espressione `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-178">Viene trovata una `Keywords_croatia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-179">Keywords</span></span>

<span data-ttu-id="fc9ac-180">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-180"></span></span>
|<span data-ttu-id="fc9ac-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-182">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-182">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-183">numero di passaporto croato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-183">croatian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-184">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-184">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="fc9ac-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="fc9ac-186">Cipro</span><span class="sxs-lookup"><span data-stu-id="fc9ac-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-187">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-187">Format</span></span>

<span data-ttu-id="fc9ac-188">Una lettera seguita da 6-8 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-189">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-189">Pattern</span></span>

<span data-ttu-id="fc9ac-190">Una lettera seguita da sei a otto cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-191">Checksum</span></span>

<span data-ttu-id="fc9ac-192">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-193">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-193">Definition</span></span>

<span data-ttu-id="fc9ac-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-195">L'espressione `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-196">Viene trovata una `Keywords_cyprus_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-197">Keywords</span></span>

<span data-ttu-id="fc9ac-198">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-198"></span></span>
|<span data-ttu-id="fc9ac-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-200">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-200">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-201">numero di passaporto di Cipro</span><span class="sxs-lookup"><span data-stu-id="fc9ac-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="fc9ac-202">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-202">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="fc9ac-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="fc9ac-204">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="fc9ac-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-205">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-205">Format</span></span>

<span data-ttu-id="fc9ac-206">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-207">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-207">Pattern</span></span>

<span data-ttu-id="fc9ac-208">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-209">Checksum</span></span>

<span data-ttu-id="fc9ac-210">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-211">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-211">Definition</span></span>

<span data-ttu-id="fc9ac-212">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-213">L'espressione `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-214">Viene trovata una `Keywords_czech_republic_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-215">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-215">Keywords</span></span>

<span data-ttu-id="fc9ac-216">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-216"></span></span>
|<span data-ttu-id="fc9ac-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-218">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-218">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-219">numero di passaporto ceco</span><span class="sxs-lookup"><span data-stu-id="fc9ac-219">czech passport number</span></span>  <br/> <span data-ttu-id="fc9ac-220">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-220">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-221">Cestovní pas</span><span class="sxs-lookup"><span data-stu-id="fc9ac-221">cestovní pas</span></span>  <br/> <span data-ttu-id="fc9ac-222">pas</span><span class="sxs-lookup"><span data-stu-id="fc9ac-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="fc9ac-223">Danimarca</span><span class="sxs-lookup"><span data-stu-id="fc9ac-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-224">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-224">Format</span></span>

<span data-ttu-id="fc9ac-225">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-226">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-226">Pattern</span></span>

 <span data-ttu-id="fc9ac-227">9 cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-228">Checksum</span></span>

<span data-ttu-id="fc9ac-229">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-230">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-230">Definition</span></span>

<span data-ttu-id="fc9ac-231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-232">L'espressione `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-233">Viene trovata una `Keywords_denmark_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-234">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-234">Keywords</span></span>

<span data-ttu-id="fc9ac-235">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-235"></span></span>
|<span data-ttu-id="fc9ac-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-237">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-237">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-238">numero di passaporto danese</span><span class="sxs-lookup"><span data-stu-id="fc9ac-238">danish passport number</span></span>  <br/> <span data-ttu-id="fc9ac-239">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-239">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-240">pas</span><span class="sxs-lookup"><span data-stu-id="fc9ac-240">pas</span></span>  <br/> <span data-ttu-id="fc9ac-241">Pasnummer</span><span class="sxs-lookup"><span data-stu-id="fc9ac-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="fc9ac-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="fc9ac-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-243">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-243">Format</span></span>

<span data-ttu-id="fc9ac-244">Una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-245">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-245">Pattern</span></span>

<span data-ttu-id="fc9ac-246">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-247">Checksum</span></span>

<span data-ttu-id="fc9ac-248">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-249">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-249">Definition</span></span>

<span data-ttu-id="fc9ac-250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-251">L'espressione `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-252">Viene trovata una `Keywords_estonia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-253">Keywords</span></span>

<span data-ttu-id="fc9ac-254">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-254"></span></span>
|<span data-ttu-id="fc9ac-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-256">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-256">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-257">numero di passaporto estone</span><span class="sxs-lookup"><span data-stu-id="fc9ac-257">estonian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-258">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-258">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-259">passaggio kodaniku Eesti</span><span class="sxs-lookup"><span data-stu-id="fc9ac-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="fc9ac-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="fc9ac-260">Finland</span></span>

<span data-ttu-id="fc9ac-261">Per informazioni dettagliate, vedere la sezione "Finlandia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="fc9ac-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="fc9ac-262">Francia</span><span class="sxs-lookup"><span data-stu-id="fc9ac-262">France</span></span>

<span data-ttu-id="fc9ac-263">Per informazioni dettagliate, vedere la sezione "Francia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="fc9ac-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="fc9ac-264">Germania</span><span class="sxs-lookup"><span data-stu-id="fc9ac-264">Germany</span></span>

<span data-ttu-id="fc9ac-265">Per informazioni dettagliate, vedere la sezione "numero di passaporto tedesco" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="fc9ac-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="fc9ac-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="fc9ac-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-267">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-267">Format</span></span>

<span data-ttu-id="fc9ac-268">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-269">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-269">Pattern</span></span>

<span data-ttu-id="fc9ac-270">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-271">Checksum</span></span>

<span data-ttu-id="fc9ac-272">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-273">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-273">Definition</span></span>

<span data-ttu-id="fc9ac-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-275">L'espressione `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-276">Viene trovata una `Keywords_greece_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-277">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-277">Keywords</span></span>

<span data-ttu-id="fc9ac-278">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-278"></span></span>
|<span data-ttu-id="fc9ac-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-280">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-280">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-281">numero di passaporto greco</span><span class="sxs-lookup"><span data-stu-id="fc9ac-281">greek passport number</span></span>  <br/> <span data-ttu-id="fc9ac-282">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-282">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="fc9ac-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="fc9ac-284">Ungheria</span><span class="sxs-lookup"><span data-stu-id="fc9ac-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-285">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-285">Format</span></span>

<span data-ttu-id="fc9ac-286">Due lettere seguite da sei o sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-287">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-287">Pattern</span></span>

<span data-ttu-id="fc9ac-288">Due lettere seguite da sei o sette cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-289">Checksum</span></span>

<span data-ttu-id="fc9ac-290">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-291">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-291">Definition</span></span>

<span data-ttu-id="fc9ac-292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-293">L'espressione `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-294">Viene trovata una `Keywords_hungary_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-295">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-295">Keywords</span></span>

<span data-ttu-id="fc9ac-296">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-296"></span></span>
|<span data-ttu-id="fc9ac-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-298">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-298">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-299">numero di passaporto ungherese</span><span class="sxs-lookup"><span data-stu-id="fc9ac-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-300">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-300">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="fc9ac-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="fc9ac-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="fc9ac-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-303">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-303">Format</span></span>

<span data-ttu-id="fc9ac-304">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-305">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-305">Pattern</span></span>

<span data-ttu-id="fc9ac-306">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="fc9ac-307">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="fc9ac-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="fc9ac-308">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fc9ac-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-309">Checksum</span></span>

<span data-ttu-id="fc9ac-310">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-311">Definition</span></span>

<span data-ttu-id="fc9ac-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-313">L'espressione `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-314">Viene trovata una `Keywords_ireland_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-315">Keywords</span></span>

<span data-ttu-id="fc9ac-316">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-316"></span></span>
|<span data-ttu-id="fc9ac-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-318">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-318">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-319">numero di passaporto irlandese</span><span class="sxs-lookup"><span data-stu-id="fc9ac-319">irish passport number</span></span>  <br/> <span data-ttu-id="fc9ac-320">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-320">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-321">pas</span><span class="sxs-lookup"><span data-stu-id="fc9ac-321">pas</span></span>  <br/> <span data-ttu-id="fc9ac-322">passaporto</span><span class="sxs-lookup"><span data-stu-id="fc9ac-322">passport</span></span>  <br/> <span data-ttu-id="fc9ac-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="fc9ac-323">passeport</span></span>  <br/> <span data-ttu-id="fc9ac-324">numero Passeport</span><span class="sxs-lookup"><span data-stu-id="fc9ac-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="fc9ac-325">Italia</span><span class="sxs-lookup"><span data-stu-id="fc9ac-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-326">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-326">Format</span></span>

<span data-ttu-id="fc9ac-327">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-328">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-328">Pattern</span></span>

<span data-ttu-id="fc9ac-329">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="fc9ac-330">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="fc9ac-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="fc9ac-331">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fc9ac-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-332">Checksum</span></span>

<span data-ttu-id="fc9ac-333">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fc9ac-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-334">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-334">Definition</span></span>

<span data-ttu-id="fc9ac-335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-336">L'espressione `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-337">Viene trovata una `Keywords_italy_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-338">Keywords</span></span>

<span data-ttu-id="fc9ac-339">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-339"></span></span>
|<span data-ttu-id="fc9ac-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-341">numero di passaporto italiano</span><span class="sxs-lookup"><span data-stu-id="fc9ac-341">italian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="fc9ac-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="fc9ac-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="fc9ac-343">passaporto</span></span>  <br/> <span data-ttu-id="fc9ac-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="fc9ac-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="fc9ac-345">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-345">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="fc9ac-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="fc9ac-347">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="fc9ac-347">passaporto numero</span></span>  <br/> <span data-ttu-id="fc9ac-348">numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="fc9ac-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="fc9ac-349">numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="fc9ac-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="fc9ac-350">Lettonia</span><span class="sxs-lookup"><span data-stu-id="fc9ac-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-351">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-351">Format</span></span>

<span data-ttu-id="fc9ac-352">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-353">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-353">Pattern</span></span>

<span data-ttu-id="fc9ac-354">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="fc9ac-355">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="fc9ac-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="fc9ac-356">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fc9ac-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-357">Checksum</span></span>

<span data-ttu-id="fc9ac-358">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-359">Definition</span></span>

<span data-ttu-id="fc9ac-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-361">L'espressione `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-362">Viene trovata una `Keywords_latvia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-363">Keywords</span></span>

<span data-ttu-id="fc9ac-364">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-364"></span></span>
|<span data-ttu-id="fc9ac-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-366">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-366">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-367">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="fc9ac-367">latvian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-368">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-368">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="fc9ac-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="fc9ac-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="fc9ac-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-371">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-371">Format</span></span>

<span data-ttu-id="fc9ac-372">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-373">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-373">Pattern</span></span>

<span data-ttu-id="fc9ac-374">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fc9ac-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-375">Checksum</span></span>

<span data-ttu-id="fc9ac-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fc9ac-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-377">Definition</span></span>

<span data-ttu-id="fc9ac-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-379">L'espressione `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-380">Viene trovata una `Keywords_lithuania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-381">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-381">Keywords</span></span>

<span data-ttu-id="fc9ac-382">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-382"></span></span>
|<span data-ttu-id="fc9ac-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-384">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-384">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-385">numero di passaporto di lithunian</span><span class="sxs-lookup"><span data-stu-id="fc9ac-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-386">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-386">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-387">numero di Paso</span><span class="sxs-lookup"><span data-stu-id="fc9ac-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="fc9ac-388">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="fc9ac-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-389">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-389">Format</span></span>

<span data-ttu-id="fc9ac-390">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-391">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-391">Pattern</span></span>

<span data-ttu-id="fc9ac-392">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="fc9ac-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-393">Checksum</span></span>

<span data-ttu-id="fc9ac-394">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-395">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-395">Definition</span></span>

<span data-ttu-id="fc9ac-396">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-397">L'espressione `Regex_nation_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-398">Viene trovata una `Keywords_nation_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-399">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-399">Keywords</span></span>

<span data-ttu-id="fc9ac-400">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-400"></span></span>
|<span data-ttu-id="fc9ac-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-402">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-402">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-403">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="fc9ac-403">latvian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-404">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-404">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="fc9ac-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="fc9ac-406">Malta</span><span class="sxs-lookup"><span data-stu-id="fc9ac-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-407">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-407">Format</span></span>

<span data-ttu-id="fc9ac-408">Sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-409">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-409">Pattern</span></span>

 <span data-ttu-id="fc9ac-410">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-411">Checksum</span></span>

<span data-ttu-id="fc9ac-412">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-413">Definition</span></span>

<span data-ttu-id="fc9ac-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-415">L'espressione `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-416">Viene trovata una `Keywords_malta_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-417">Keywords</span></span>

<span data-ttu-id="fc9ac-418">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-418"></span></span>
|<span data-ttu-id="fc9ac-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-420">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-420">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-421">numero di passaporto maltese</span><span class="sxs-lookup"><span data-stu-id="fc9ac-421">maltese passport number</span></span>  <br/> <span data-ttu-id="fc9ac-422">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-422">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="fc9ac-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="fc9ac-424">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="fc9ac-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-425">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-425">Format</span></span>

<span data-ttu-id="fc9ac-426">Nove lettere o cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-427">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-427">Pattern</span></span>

<span data-ttu-id="fc9ac-428">Nove lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-429">Checksum</span></span>

<span data-ttu-id="fc9ac-430">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fc9ac-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-431">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-431">Definition</span></span>

<span data-ttu-id="fc9ac-432">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-433">L'espressione `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-434">Viene trovata una `Keywords_netherlands_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-435">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-435">Keywords</span></span>

<span data-ttu-id="fc9ac-436">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-436"></span></span>
|<span data-ttu-id="fc9ac-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-438">numero di passaporto olandese</span><span class="sxs-lookup"><span data-stu-id="fc9ac-438">dutch passport number</span></span>  <br/> <span data-ttu-id="fc9ac-439">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-439">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-440">numero di passaporto per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="fc9ac-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="fc9ac-441">Nederlanden PASPOORT Nummer</span><span class="sxs-lookup"><span data-stu-id="fc9ac-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="fc9ac-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="fc9ac-442">paspoort</span></span>  <br/> <span data-ttu-id="fc9ac-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="fc9ac-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="fc9ac-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="fc9ac-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="fc9ac-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="fc9ac-445">Poland</span></span>

<span data-ttu-id="fc9ac-446">Per informazioni dettagliate, vedere la sezione "Poland Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="fc9ac-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="fc9ac-447">Portogallo</span><span class="sxs-lookup"><span data-stu-id="fc9ac-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-448">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-448">Format</span></span>

<span data-ttu-id="fc9ac-449">Una lettera seguita da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-450">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-450">Pattern</span></span>

<span data-ttu-id="fc9ac-451">Una lettera seguita da sei cifre:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="fc9ac-452">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="fc9ac-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="fc9ac-453">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fc9ac-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-454">Checksum</span></span>

<span data-ttu-id="fc9ac-455">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-456">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-456">Definition</span></span>

<span data-ttu-id="fc9ac-457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-458">L'espressione `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-459">Viene trovata una `Keywords_portugal_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-460">Keywords</span></span>

<span data-ttu-id="fc9ac-461">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-461"></span></span>
|<span data-ttu-id="fc9ac-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-463">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-463">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-464">numero di passaporto portoghese</span><span class="sxs-lookup"><span data-stu-id="fc9ac-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="fc9ac-465">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-465">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="fc9ac-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="fc9ac-467">Romania</span><span class="sxs-lookup"><span data-stu-id="fc9ac-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-468">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-468">Format</span></span>

<span data-ttu-id="fc9ac-469">Otto o nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-470">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-470">Pattern</span></span>

<span data-ttu-id="fc9ac-471">Otto o nove cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-472">Checksum</span></span>

<span data-ttu-id="fc9ac-473">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-474">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-474">Definition</span></span>

<span data-ttu-id="fc9ac-475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-476">L'espressione `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-477">Viene trovata una `Keywords_romania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-478">Keywords</span></span>

<span data-ttu-id="fc9ac-479">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-479"></span></span>
|<span data-ttu-id="fc9ac-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-481">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-481">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-482">numero di passaporto rumeno</span><span class="sxs-lookup"><span data-stu-id="fc9ac-482">romanian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-483">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-483">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="fc9ac-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="fc9ac-485">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="fc9ac-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-486">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-486">Format</span></span>

<span data-ttu-id="fc9ac-487">Una cifra o una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-488">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-488">Pattern</span></span>

<span data-ttu-id="fc9ac-489">Una cifra o una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="fc9ac-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-490">Checksum</span></span>

<span data-ttu-id="fc9ac-491">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-492">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-492">Definition</span></span>

<span data-ttu-id="fc9ac-493">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-494">L'espressione `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-495">Viene trovata una `Keywords_slovakia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-496">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-496">Keywords</span></span>

<span data-ttu-id="fc9ac-497">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-497"></span></span>
|<span data-ttu-id="fc9ac-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-499">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-499">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-500">numero di passaporto slovacco</span><span class="sxs-lookup"><span data-stu-id="fc9ac-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-501">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-501">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="fc9ac-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="fc9ac-503">Slovenia</span><span class="sxs-lookup"><span data-stu-id="fc9ac-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-504">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-504">Format</span></span>

<span data-ttu-id="fc9ac-505">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-506">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-506">Pattern</span></span>

<span data-ttu-id="fc9ac-507">Due lettere seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="fc9ac-508">La lettera "P"</span><span class="sxs-lookup"><span data-stu-id="fc9ac-508">The letter "P"</span></span>
    
- <span data-ttu-id="fc9ac-509">Una lettera maiuscola</span><span class="sxs-lookup"><span data-stu-id="fc9ac-509">One uppercase letter</span></span>
    
- <span data-ttu-id="fc9ac-510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fc9ac-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-511">Checksum</span></span>

<span data-ttu-id="fc9ac-512">No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-513">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-513">Definition</span></span>

<span data-ttu-id="fc9ac-514">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-515">L'espressione `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-516">Viene trovata una `Keywords_slovenia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-517">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-517">Keywords</span></span>

<span data-ttu-id="fc9ac-518">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-518"></span></span>
|<span data-ttu-id="fc9ac-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-520">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-520">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-521">numero di passaporto sloveno</span><span class="sxs-lookup"><span data-stu-id="fc9ac-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="fc9ac-522">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-522">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="fc9ac-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="fc9ac-524">Spagna</span><span class="sxs-lookup"><span data-stu-id="fc9ac-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="fc9ac-525">Formato</span><span class="sxs-lookup"><span data-stu-id="fc9ac-525">Format</span></span>

<span data-ttu-id="fc9ac-526">Combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="fc9ac-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="fc9ac-527">Modello</span><span class="sxs-lookup"><span data-stu-id="fc9ac-527">Pattern</span></span>

<span data-ttu-id="fc9ac-528">Combinazione di lettere e numeri di otto o nove caratteri:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="fc9ac-529">Due cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="fc9ac-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="fc9ac-530">Una cifra o una lettera (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="fc9ac-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="fc9ac-531">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="fc9ac-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="fc9ac-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="fc9ac-532">Checksum</span></span>

<span data-ttu-id="fc9ac-533">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="fc9ac-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="fc9ac-534">Definizione</span><span class="sxs-lookup"><span data-stu-id="fc9ac-534">Definition</span></span>

<span data-ttu-id="fc9ac-535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="fc9ac-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="fc9ac-536">L'espressione `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="fc9ac-537">Viene trovata una `Keywords_spain_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="fc9ac-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="fc9ac-538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fc9ac-538">Keywords</span></span>

<span data-ttu-id="fc9ac-539">| |</span><span class="sxs-lookup"><span data-stu-id="fc9ac-539"></span></span>
|<span data-ttu-id="fc9ac-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="fc9ac-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="fc9ac-541">passaporto</span><span class="sxs-lookup"><span data-stu-id="fc9ac-541">passport</span></span>  <br/> <span data-ttu-id="fc9ac-542">passaporto della Spagna</span><span class="sxs-lookup"><span data-stu-id="fc9ac-542">spain passport</span></span>  <br/> <span data-ttu-id="fc9ac-543">libro del passaporto</span><span class="sxs-lookup"><span data-stu-id="fc9ac-543">passport book</span></span>  <br/> <span data-ttu-id="fc9ac-544">passport number</span><span class="sxs-lookup"><span data-stu-id="fc9ac-544">passport number</span></span>  <br/> <span data-ttu-id="fc9ac-545">Passport No</span><span class="sxs-lookup"><span data-stu-id="fc9ac-545">passport no</span></span>  <br/> <span data-ttu-id="fc9ac-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="fc9ac-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="fc9ac-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="fc9ac-547">número pasaporte</span></span>  <br/> <span data-ttu-id="fc9ac-548">pasaporte España</span><span class="sxs-lookup"><span data-stu-id="fc9ac-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="fc9ac-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="fc9ac-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="fc9ac-550">Svezia</span><span class="sxs-lookup"><span data-stu-id="fc9ac-550">Sweden</span></span>

<span data-ttu-id="fc9ac-551">Per informazioni dettagliate, vedere la sezione "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="fc9ac-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="fc9ac-552">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="fc9ac-552">UK</span></span>

<span data-ttu-id="fc9ac-553">Per informazioni dettagliate, vedere la sezione "Stati Uniti/Regno Unito</span><span class="sxs-lookup"><span data-stu-id="fc9ac-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="fc9ac-554">Numero di passaporto "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="fc9ac-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc9ac-555">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc9ac-555">See also</span></span>

[<span data-ttu-id="fc9ac-556">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="fc9ac-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

