---
title: Numero di passaporto EU
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
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 56eb79dd067ca89600f92ea57eaaf01e562f9388
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938740"
---
# <a name="eu-passport-number"></a><span data-ttu-id="49d24-104">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="49d24-104">EU Passport Number</span></span>

<span data-ttu-id="49d24-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="49d24-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="49d24-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="49d24-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="49d24-107">Austria</span><span class="sxs-lookup"><span data-stu-id="49d24-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="49d24-108">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-108">Format</span></span>

<span data-ttu-id="49d24-109">Una lettera seguita da uno spazio facoltativo e sette cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-110">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-110">Pattern</span></span>

<span data-ttu-id="49d24-111">Combinazione di una lettera, sette cifre e uno spazio:</span><span class="sxs-lookup"><span data-stu-id="49d24-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="49d24-112">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="49d24-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="49d24-113">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="49d24-113">One space (optional)</span></span>
    
- <span data-ttu-id="49d24-114">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49d24-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-115">Checksum</span></span>

<span data-ttu-id="49d24-116">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="49d24-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-117">Definition</span></span>

<span data-ttu-id="49d24-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-119">L'espressione `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-120">Viene trovata una `Keywords_austria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-121">Keywords</span></span>

<span data-ttu-id="49d24-122">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-122">| |</span></span>
|<span data-ttu-id="49d24-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-124">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-124">passport number</span></span>  <br/> <span data-ttu-id="49d24-125">numero di passaporto austriaco</span><span class="sxs-lookup"><span data-stu-id="49d24-125">austrian passport number</span></span>  <br/> <span data-ttu-id="49d24-126">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-126">passport no</span></span>  <br/> <span data-ttu-id="49d24-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="49d24-127">reisepass</span></span>  <br/> <span data-ttu-id="49d24-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="49d24-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="49d24-129">Belgio</span><span class="sxs-lookup"><span data-stu-id="49d24-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="49d24-130">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-130">Format</span></span>

<span data-ttu-id="49d24-131">Due lettere seguite da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-132">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-132">Pattern</span></span>

<span data-ttu-id="49d24-133">Due lettere e seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49d24-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-134">Checksum</span></span>

<span data-ttu-id="49d24-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="49d24-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-136">Definition</span></span>

<span data-ttu-id="49d24-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-138">L'espressione `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-139">Viene trovata una `Keywords_belgium_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-140">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-140">Keywords</span></span>

<span data-ttu-id="49d24-141">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-141">| |</span></span>
|<span data-ttu-id="49d24-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-143">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-143">passport number</span></span>  <br/> <span data-ttu-id="49d24-144">numero di passaporto belga</span><span class="sxs-lookup"><span data-stu-id="49d24-144">belgian passport number</span></span>  <br/> <span data-ttu-id="49d24-145">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-145">passport no</span></span>  <br/> <span data-ttu-id="49d24-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="49d24-146">paspoort</span></span>  <br/> <span data-ttu-id="49d24-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="49d24-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="49d24-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="49d24-148">reisepass kein</span></span>  <br/> <span data-ttu-id="49d24-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="49d24-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="49d24-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="49d24-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="49d24-151">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-151">Format</span></span>

<span data-ttu-id="49d24-152">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-153">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-153">Pattern</span></span>

 <span data-ttu-id="49d24-154">9 cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="49d24-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-155">Checksum</span></span>

<span data-ttu-id="49d24-156">No</span><span class="sxs-lookup"><span data-stu-id="49d24-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-157">Definition</span></span>

<span data-ttu-id="49d24-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-159">L'espressione `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-160">Viene trovata una `Keywords_bulgaria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-161">Keywords</span></span>

<span data-ttu-id="49d24-162">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-162">| |</span></span>
|<span data-ttu-id="49d24-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-164">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-164">passport number</span></span>  <br/> <span data-ttu-id="49d24-165">numero di passaporto bulgaro</span><span class="sxs-lookup"><span data-stu-id="49d24-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="49d24-166">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-166">passport no</span></span>  <br/> <span data-ttu-id="49d24-167">Номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="49d24-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="49d24-168">Croazia</span><span class="sxs-lookup"><span data-stu-id="49d24-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="49d24-169">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-169">Format</span></span>

<span data-ttu-id="49d24-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-171">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-171">Pattern</span></span>

 <span data-ttu-id="49d24-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="49d24-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-173">Checksum</span></span>

<span data-ttu-id="49d24-174">No</span><span class="sxs-lookup"><span data-stu-id="49d24-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-175">Definition</span></span>

<span data-ttu-id="49d24-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-177">L'espressione `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-178">Viene trovata una `Keywords_croatia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-179">Keywords</span></span>

<span data-ttu-id="49d24-180">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-180">| |</span></span>
|<span data-ttu-id="49d24-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-182">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-182">passport number</span></span>  <br/> <span data-ttu-id="49d24-183">numero di passaporto croato</span><span class="sxs-lookup"><span data-stu-id="49d24-183">croatian passport number</span></span>  <br/> <span data-ttu-id="49d24-184">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-184">passport no</span></span>  <br/> <span data-ttu-id="49d24-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="49d24-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="49d24-186">Cipro</span><span class="sxs-lookup"><span data-stu-id="49d24-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="49d24-187">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-187">Format</span></span>

<span data-ttu-id="49d24-188">Una lettera seguita da 6-8 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-189">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-189">Pattern</span></span>

<span data-ttu-id="49d24-190">Una lettera seguita da sei a otto cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49d24-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-191">Checksum</span></span>

<span data-ttu-id="49d24-192">No</span><span class="sxs-lookup"><span data-stu-id="49d24-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-193">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-193">Definition</span></span>

<span data-ttu-id="49d24-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-195">L'espressione `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-196">Viene trovata una `Keywords_cyprus_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-197">Keywords</span></span>

<span data-ttu-id="49d24-198">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-198">| |</span></span>
|<span data-ttu-id="49d24-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-200">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-200">passport number</span></span>  <br/> <span data-ttu-id="49d24-201">numero di passaporto di Cipro</span><span class="sxs-lookup"><span data-stu-id="49d24-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="49d24-202">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-202">passport no</span></span>  <br/> <span data-ttu-id="49d24-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="49d24-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="49d24-204">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="49d24-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="49d24-205">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-205">Format</span></span>

<span data-ttu-id="49d24-206">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-207">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-207">Pattern</span></span>

<span data-ttu-id="49d24-208">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49d24-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-209">Checksum</span></span>

<span data-ttu-id="49d24-210">No</span><span class="sxs-lookup"><span data-stu-id="49d24-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-211">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-211">Definition</span></span>

<span data-ttu-id="49d24-212">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-213">L'espressione `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-214">Viene trovata una `Keywords_czech_republic_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-215">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-215">Keywords</span></span>

<span data-ttu-id="49d24-216">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-216">| |</span></span>
|<span data-ttu-id="49d24-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-218">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-218">passport number</span></span>  <br/> <span data-ttu-id="49d24-219">numero di passaporto ceco</span><span class="sxs-lookup"><span data-stu-id="49d24-219">czech passport number</span></span>  <br/> <span data-ttu-id="49d24-220">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-220">passport no</span></span>  <br/> <span data-ttu-id="49d24-221">Cestovní pas</span><span class="sxs-lookup"><span data-stu-id="49d24-221">cestovní pas</span></span>  <br/> <span data-ttu-id="49d24-222">pas</span><span class="sxs-lookup"><span data-stu-id="49d24-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="49d24-223">Danimarca</span><span class="sxs-lookup"><span data-stu-id="49d24-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="49d24-224">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-224">Format</span></span>

<span data-ttu-id="49d24-225">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-226">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-226">Pattern</span></span>

 <span data-ttu-id="49d24-227">9 cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="49d24-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-228">Checksum</span></span>

<span data-ttu-id="49d24-229">No</span><span class="sxs-lookup"><span data-stu-id="49d24-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-230">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-230">Definition</span></span>

<span data-ttu-id="49d24-231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-232">L'espressione `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-233">Viene trovata una `Keywords_denmark_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-234">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-234">Keywords</span></span>

<span data-ttu-id="49d24-235">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-235">| |</span></span>
|<span data-ttu-id="49d24-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-237">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-237">passport number</span></span>  <br/> <span data-ttu-id="49d24-238">numero di passaporto danese</span><span class="sxs-lookup"><span data-stu-id="49d24-238">danish passport number</span></span>  <br/> <span data-ttu-id="49d24-239">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-239">passport no</span></span>  <br/> <span data-ttu-id="49d24-240">pas</span><span class="sxs-lookup"><span data-stu-id="49d24-240">pas</span></span>  <br/> <span data-ttu-id="49d24-241">Pasnummer</span><span class="sxs-lookup"><span data-stu-id="49d24-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="49d24-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="49d24-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="49d24-243">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-243">Format</span></span>

<span data-ttu-id="49d24-244">Una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-245">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-245">Pattern</span></span>

<span data-ttu-id="49d24-246">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49d24-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-247">Checksum</span></span>

<span data-ttu-id="49d24-248">No</span><span class="sxs-lookup"><span data-stu-id="49d24-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-249">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-249">Definition</span></span>

<span data-ttu-id="49d24-250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-251">L'espressione `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-252">Viene trovata una `Keywords_estonia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-253">Keywords</span></span>

<span data-ttu-id="49d24-254">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-254">| |</span></span>
|<span data-ttu-id="49d24-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-256">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-256">passport number</span></span>  <br/> <span data-ttu-id="49d24-257">numero di passaporto estone</span><span class="sxs-lookup"><span data-stu-id="49d24-257">estonian passport number</span></span>  <br/> <span data-ttu-id="49d24-258">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-258">passport no</span></span>  <br/> <span data-ttu-id="49d24-259">passaggio kodaniku Eesti</span><span class="sxs-lookup"><span data-stu-id="49d24-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="49d24-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="49d24-260">Finland</span></span>

<span data-ttu-id="49d24-261">Per informazioni dettagliate, vedere la sezione "Finlandia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="49d24-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="49d24-262">Francia</span><span class="sxs-lookup"><span data-stu-id="49d24-262">France</span></span>

<span data-ttu-id="49d24-263">Per informazioni dettagliate, vedere la sezione "Francia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="49d24-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="49d24-264">Germania</span><span class="sxs-lookup"><span data-stu-id="49d24-264">Germany</span></span>

<span data-ttu-id="49d24-265">Per informazioni dettagliate, vedere la sezione "numero di passaporto tedesco" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="49d24-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="49d24-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="49d24-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="49d24-267">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-267">Format</span></span>

<span data-ttu-id="49d24-268">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-269">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-269">Pattern</span></span>

<span data-ttu-id="49d24-270">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49d24-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-271">Checksum</span></span>

<span data-ttu-id="49d24-272">No</span><span class="sxs-lookup"><span data-stu-id="49d24-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-273">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-273">Definition</span></span>

<span data-ttu-id="49d24-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-275">L'espressione `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-276">Viene trovata una `Keywords_greece_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-277">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-277">Keywords</span></span>

<span data-ttu-id="49d24-278">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-278">| |</span></span>
|<span data-ttu-id="49d24-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-280">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-280">passport number</span></span>  <br/> <span data-ttu-id="49d24-281">numero di passaporto greco</span><span class="sxs-lookup"><span data-stu-id="49d24-281">greek passport number</span></span>  <br/> <span data-ttu-id="49d24-282">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-282">passport no</span></span>  <br/> <span data-ttu-id="49d24-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="49d24-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="49d24-284">Ungheria</span><span class="sxs-lookup"><span data-stu-id="49d24-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="49d24-285">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-285">Format</span></span>

<span data-ttu-id="49d24-286">Due lettere seguite da sei o sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-287">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-287">Pattern</span></span>

<span data-ttu-id="49d24-288">Due lettere seguite da sei o sette cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49d24-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-289">Checksum</span></span>

<span data-ttu-id="49d24-290">No</span><span class="sxs-lookup"><span data-stu-id="49d24-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-291">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-291">Definition</span></span>

<span data-ttu-id="49d24-292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-293">L'espressione `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-294">Viene trovata una `Keywords_hungary_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-295">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-295">Keywords</span></span>

<span data-ttu-id="49d24-296">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-296">| |</span></span>
|<span data-ttu-id="49d24-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-298">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-298">passport number</span></span>  <br/> <span data-ttu-id="49d24-299">numero di passaporto ungherese</span><span class="sxs-lookup"><span data-stu-id="49d24-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="49d24-300">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-300">passport no</span></span>  <br/> <span data-ttu-id="49d24-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="49d24-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="49d24-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="49d24-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="49d24-303">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-303">Format</span></span>

<span data-ttu-id="49d24-304">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-305">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-305">Pattern</span></span>

<span data-ttu-id="49d24-306">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="49d24-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="49d24-307">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="49d24-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="49d24-308">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49d24-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-309">Checksum</span></span>

<span data-ttu-id="49d24-310">No</span><span class="sxs-lookup"><span data-stu-id="49d24-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-311">Definition</span></span>

<span data-ttu-id="49d24-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-313">L'espressione `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-314">Viene trovata una `Keywords_ireland_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-315">Keywords</span></span>

<span data-ttu-id="49d24-316">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-316">| |</span></span>
|<span data-ttu-id="49d24-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-318">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-318">passport number</span></span>  <br/> <span data-ttu-id="49d24-319">numero di passaporto irlandese</span><span class="sxs-lookup"><span data-stu-id="49d24-319">irish passport number</span></span>  <br/> <span data-ttu-id="49d24-320">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-320">passport no</span></span>  <br/> <span data-ttu-id="49d24-321">pas</span><span class="sxs-lookup"><span data-stu-id="49d24-321">pas</span></span>  <br/> <span data-ttu-id="49d24-322">passaporto</span><span class="sxs-lookup"><span data-stu-id="49d24-322">passport</span></span>  <br/> <span data-ttu-id="49d24-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="49d24-323">passeport</span></span>  <br/> <span data-ttu-id="49d24-324">numero Passeport</span><span class="sxs-lookup"><span data-stu-id="49d24-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="49d24-325">Italia</span><span class="sxs-lookup"><span data-stu-id="49d24-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="49d24-326">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-326">Format</span></span>

<span data-ttu-id="49d24-327">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-328">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-328">Pattern</span></span>

<span data-ttu-id="49d24-329">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="49d24-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="49d24-330">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="49d24-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="49d24-331">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49d24-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-332">Checksum</span></span>

<span data-ttu-id="49d24-333">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="49d24-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-334">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-334">Definition</span></span>

<span data-ttu-id="49d24-335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-336">L'espressione `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-337">Viene trovata una `Keywords_italy_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-338">Keywords</span></span>

<span data-ttu-id="49d24-339">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-339">| |</span></span>
|<span data-ttu-id="49d24-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-341">numero di passaporto italiano</span><span class="sxs-lookup"><span data-stu-id="49d24-341">italian passport number</span></span>  <br/> <span data-ttu-id="49d24-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="49d24-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="49d24-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="49d24-343">passaporto</span></span>  <br/> <span data-ttu-id="49d24-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="49d24-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="49d24-345">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-345">passport number</span></span>  <br/> <span data-ttu-id="49d24-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="49d24-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="49d24-347">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="49d24-347">passaporto numero</span></span>  <br/> <span data-ttu-id="49d24-348">numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="49d24-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="49d24-349">numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="49d24-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="49d24-350">Lettonia</span><span class="sxs-lookup"><span data-stu-id="49d24-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="49d24-351">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-351">Format</span></span>

<span data-ttu-id="49d24-352">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-353">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-353">Pattern</span></span>

<span data-ttu-id="49d24-354">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="49d24-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="49d24-355">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="49d24-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="49d24-356">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49d24-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-357">Checksum</span></span>

<span data-ttu-id="49d24-358">No</span><span class="sxs-lookup"><span data-stu-id="49d24-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-359">Definition</span></span>

<span data-ttu-id="49d24-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-361">L'espressione `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-362">Viene trovata una `Keywords_latvia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-363">Keywords</span></span>

<span data-ttu-id="49d24-364">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-364">| |</span></span>
|<span data-ttu-id="49d24-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-366">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-366">passport number</span></span>  <br/> <span data-ttu-id="49d24-367">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="49d24-367">latvian passport number</span></span>  <br/> <span data-ttu-id="49d24-368">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-368">passport no</span></span>  <br/> <span data-ttu-id="49d24-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="49d24-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="49d24-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="49d24-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="49d24-371">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-371">Format</span></span>

<span data-ttu-id="49d24-372">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-373">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-373">Pattern</span></span>

<span data-ttu-id="49d24-374">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="49d24-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49d24-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-375">Checksum</span></span>

<span data-ttu-id="49d24-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="49d24-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-377">Definition</span></span>

<span data-ttu-id="49d24-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-379">L'espressione `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-380">Viene trovata una `Keywords_lithuania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-381">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-381">Keywords</span></span>

<span data-ttu-id="49d24-382">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-382">| |</span></span>
|<span data-ttu-id="49d24-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-384">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-384">passport number</span></span>  <br/> <span data-ttu-id="49d24-385">numero di passaporto di lithunian</span><span class="sxs-lookup"><span data-stu-id="49d24-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="49d24-386">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-386">passport no</span></span>  <br/> <span data-ttu-id="49d24-387">numero di Paso</span><span class="sxs-lookup"><span data-stu-id="49d24-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="49d24-388">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="49d24-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="49d24-389">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-389">Format</span></span>

<span data-ttu-id="49d24-390">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-391">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-391">Pattern</span></span>

<span data-ttu-id="49d24-392">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="49d24-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49d24-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-393">Checksum</span></span>

<span data-ttu-id="49d24-394">No</span><span class="sxs-lookup"><span data-stu-id="49d24-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-395">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-395">Definition</span></span>

<span data-ttu-id="49d24-396">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-397">L'espressione `Regex_nation_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-398">Viene trovata una `Keywords_nation_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-399">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-399">Keywords</span></span>

<span data-ttu-id="49d24-400">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-400">| |</span></span>
|<span data-ttu-id="49d24-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-402">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-402">passport number</span></span>  <br/> <span data-ttu-id="49d24-403">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="49d24-403">latvian passport number</span></span>  <br/> <span data-ttu-id="49d24-404">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-404">passport no</span></span>  <br/> <span data-ttu-id="49d24-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="49d24-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="49d24-406">Malta</span><span class="sxs-lookup"><span data-stu-id="49d24-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="49d24-407">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-407">Format</span></span>

<span data-ttu-id="49d24-408">Sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-409">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-409">Pattern</span></span>

 <span data-ttu-id="49d24-410">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="49d24-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-411">Checksum</span></span>

<span data-ttu-id="49d24-412">No</span><span class="sxs-lookup"><span data-stu-id="49d24-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-413">Definition</span></span>

<span data-ttu-id="49d24-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-415">L'espressione `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-416">Viene trovata una `Keywords_malta_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-417">Keywords</span></span>

<span data-ttu-id="49d24-418">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-418">| |</span></span>
|<span data-ttu-id="49d24-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-420">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-420">passport number</span></span>  <br/> <span data-ttu-id="49d24-421">numero di passaporto maltese</span><span class="sxs-lookup"><span data-stu-id="49d24-421">maltese passport number</span></span>  <br/> <span data-ttu-id="49d24-422">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-422">passport no</span></span>  <br/> <span data-ttu-id="49d24-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="49d24-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="49d24-424">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="49d24-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="49d24-425">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-425">Format</span></span>

<span data-ttu-id="49d24-426">Nove lettere o cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-427">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-427">Pattern</span></span>

<span data-ttu-id="49d24-428">Nove lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49d24-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-429">Checksum</span></span>

<span data-ttu-id="49d24-430">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="49d24-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-431">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-431">Definition</span></span>

<span data-ttu-id="49d24-432">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-433">L'espressione `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-434">Viene trovata una `Keywords_netherlands_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-435">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-435">Keywords</span></span>

<span data-ttu-id="49d24-436">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-436">| |</span></span>
|<span data-ttu-id="49d24-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-438">numero di passaporto olandese</span><span class="sxs-lookup"><span data-stu-id="49d24-438">dutch passport number</span></span>  <br/> <span data-ttu-id="49d24-439">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-439">passport number</span></span>  <br/> <span data-ttu-id="49d24-440">numero di passaporto per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="49d24-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="49d24-441">Nederlanden PASPOORT Nummer</span><span class="sxs-lookup"><span data-stu-id="49d24-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="49d24-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="49d24-442">paspoort</span></span>  <br/> <span data-ttu-id="49d24-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="49d24-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="49d24-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="49d24-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="49d24-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="49d24-445">Poland</span></span>

<span data-ttu-id="49d24-446">Per informazioni dettagliate, vedere la sezione "Poland Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="49d24-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="49d24-447">Portogallo</span><span class="sxs-lookup"><span data-stu-id="49d24-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="49d24-448">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-448">Format</span></span>

<span data-ttu-id="49d24-449">Una lettera seguita da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-450">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-450">Pattern</span></span>

<span data-ttu-id="49d24-451">Una lettera seguita da sei cifre:</span><span class="sxs-lookup"><span data-stu-id="49d24-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="49d24-452">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="49d24-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="49d24-453">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49d24-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-454">Checksum</span></span>

<span data-ttu-id="49d24-455">No</span><span class="sxs-lookup"><span data-stu-id="49d24-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-456">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-456">Definition</span></span>

<span data-ttu-id="49d24-457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-458">L'espressione `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-459">Viene trovata una `Keywords_portugal_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-460">Keywords</span></span>

<span data-ttu-id="49d24-461">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-461">| |</span></span>
|<span data-ttu-id="49d24-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-463">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-463">passport number</span></span>  <br/> <span data-ttu-id="49d24-464">numero di passaporto portoghese</span><span class="sxs-lookup"><span data-stu-id="49d24-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="49d24-465">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-465">passport no</span></span>  <br/> <span data-ttu-id="49d24-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="49d24-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="49d24-467">Romania</span><span class="sxs-lookup"><span data-stu-id="49d24-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="49d24-468">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-468">Format</span></span>

<span data-ttu-id="49d24-469">Otto o nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-470">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-470">Pattern</span></span>

<span data-ttu-id="49d24-471">Otto o nove cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49d24-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-472">Checksum</span></span>

<span data-ttu-id="49d24-473">No</span><span class="sxs-lookup"><span data-stu-id="49d24-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-474">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-474">Definition</span></span>

<span data-ttu-id="49d24-475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-476">L'espressione `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-477">Viene trovata una `Keywords_romania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-478">Keywords</span></span>

<span data-ttu-id="49d24-479">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-479">| |</span></span>
|<span data-ttu-id="49d24-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-481">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-481">passport number</span></span>  <br/> <span data-ttu-id="49d24-482">numero di passaporto rumeno</span><span class="sxs-lookup"><span data-stu-id="49d24-482">romanian passport number</span></span>  <br/> <span data-ttu-id="49d24-483">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-483">passport no</span></span>  <br/> <span data-ttu-id="49d24-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="49d24-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="49d24-485">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="49d24-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="49d24-486">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-486">Format</span></span>

<span data-ttu-id="49d24-487">Una cifra o una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-488">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-488">Pattern</span></span>

<span data-ttu-id="49d24-489">Una cifra o una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49d24-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-490">Checksum</span></span>

<span data-ttu-id="49d24-491">No</span><span class="sxs-lookup"><span data-stu-id="49d24-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-492">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-492">Definition</span></span>

<span data-ttu-id="49d24-493">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-494">L'espressione `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-495">Viene trovata una `Keywords_slovakia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-496">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-496">Keywords</span></span>

<span data-ttu-id="49d24-497">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-497">| |</span></span>
|<span data-ttu-id="49d24-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-499">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-499">passport number</span></span>  <br/> <span data-ttu-id="49d24-500">numero di passaporto slovacco</span><span class="sxs-lookup"><span data-stu-id="49d24-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="49d24-501">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-501">passport no</span></span>  <br/> <span data-ttu-id="49d24-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="49d24-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="49d24-503">Slovenia</span><span class="sxs-lookup"><span data-stu-id="49d24-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="49d24-504">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-504">Format</span></span>

<span data-ttu-id="49d24-505">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-506">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-506">Pattern</span></span>

<span data-ttu-id="49d24-507">Due lettere seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="49d24-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="49d24-508">La lettera "P"</span><span class="sxs-lookup"><span data-stu-id="49d24-508">The letter "P"</span></span>
    
- <span data-ttu-id="49d24-509">Una lettera maiuscola</span><span class="sxs-lookup"><span data-stu-id="49d24-509">One uppercase letter</span></span>
    
- <span data-ttu-id="49d24-510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49d24-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-511">Checksum</span></span>

<span data-ttu-id="49d24-512">No</span><span class="sxs-lookup"><span data-stu-id="49d24-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-513">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-513">Definition</span></span>

<span data-ttu-id="49d24-514">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-515">L'espressione `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-516">Viene trovata una `Keywords_slovenia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-517">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-517">Keywords</span></span>

<span data-ttu-id="49d24-518">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-518">| |</span></span>
|<span data-ttu-id="49d24-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-520">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-520">passport number</span></span>  <br/> <span data-ttu-id="49d24-521">numero di passaporto sloveno</span><span class="sxs-lookup"><span data-stu-id="49d24-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="49d24-522">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-522">passport no</span></span>  <br/> <span data-ttu-id="49d24-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="49d24-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="49d24-524">Spagna</span><span class="sxs-lookup"><span data-stu-id="49d24-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="49d24-525">Formato</span><span class="sxs-lookup"><span data-stu-id="49d24-525">Format</span></span>

<span data-ttu-id="49d24-526">Combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="49d24-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49d24-527">Modello</span><span class="sxs-lookup"><span data-stu-id="49d24-527">Pattern</span></span>

<span data-ttu-id="49d24-528">Combinazione di lettere e numeri di otto o nove caratteri:</span><span class="sxs-lookup"><span data-stu-id="49d24-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="49d24-529">Due cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="49d24-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="49d24-530">Una cifra o una lettera (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="49d24-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="49d24-531">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="49d24-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49d24-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="49d24-532">Checksum</span></span>

<span data-ttu-id="49d24-533">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="49d24-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="49d24-534">Definizione</span><span class="sxs-lookup"><span data-stu-id="49d24-534">Definition</span></span>

<span data-ttu-id="49d24-535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="49d24-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49d24-536">L'espressione `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="49d24-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49d24-537">Viene trovata una `Keywords_spain_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="49d24-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49d24-538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d24-538">Keywords</span></span>

<span data-ttu-id="49d24-539">| |</span><span class="sxs-lookup"><span data-stu-id="49d24-539">| |</span></span>
|<span data-ttu-id="49d24-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="49d24-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="49d24-541">passaporto</span><span class="sxs-lookup"><span data-stu-id="49d24-541">passport</span></span>  <br/> <span data-ttu-id="49d24-542">passaporto della Spagna</span><span class="sxs-lookup"><span data-stu-id="49d24-542">spain passport</span></span>  <br/> <span data-ttu-id="49d24-543">libro del passaporto</span><span class="sxs-lookup"><span data-stu-id="49d24-543">passport book</span></span>  <br/> <span data-ttu-id="49d24-544">passport number</span><span class="sxs-lookup"><span data-stu-id="49d24-544">passport number</span></span>  <br/> <span data-ttu-id="49d24-545">Passport No</span><span class="sxs-lookup"><span data-stu-id="49d24-545">passport no</span></span>  <br/> <span data-ttu-id="49d24-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="49d24-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="49d24-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="49d24-547">número pasaporte</span></span>  <br/> <span data-ttu-id="49d24-548">pasaporte España</span><span class="sxs-lookup"><span data-stu-id="49d24-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="49d24-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="49d24-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="49d24-550">Svezia</span><span class="sxs-lookup"><span data-stu-id="49d24-550">Sweden</span></span>

<span data-ttu-id="49d24-551">Per informazioni dettagliate, vedere la sezione "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="49d24-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="49d24-552">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="49d24-552">UK</span></span>

<span data-ttu-id="49d24-553">Per informazioni dettagliate, vedere la sezione "Stati Uniti/Regno Unito</span><span class="sxs-lookup"><span data-stu-id="49d24-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="49d24-554">Numero di passaporto "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="49d24-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="49d24-555">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49d24-555">See also</span></span>

[<span data-ttu-id="49d24-556">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="49d24-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

