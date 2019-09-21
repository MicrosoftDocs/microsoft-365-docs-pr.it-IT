---
title: Numero di passaporto EU
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083672"
---
# <a name="eu-passport-number"></a><span data-ttu-id="a7a12-104">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="a7a12-104">EU Passport Number</span></span>

<span data-ttu-id="a7a12-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="a7a12-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="a7a12-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="a7a12-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="a7a12-107">Austria</span><span class="sxs-lookup"><span data-stu-id="a7a12-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-108">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-108">Format</span></span>

<span data-ttu-id="a7a12-109">Una lettera seguita da uno spazio facoltativo e sette cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-110">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-110">Pattern</span></span>

<span data-ttu-id="a7a12-111">Combinazione di una lettera, sette cifre e uno spazio:</span><span class="sxs-lookup"><span data-stu-id="a7a12-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="a7a12-112">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="a7a12-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="a7a12-113">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="a7a12-113">One space (optional)</span></span>
    
- <span data-ttu-id="a7a12-114">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7a12-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-115">Checksum</span></span>

<span data-ttu-id="a7a12-116">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a7a12-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-117">Definition</span></span>

<span data-ttu-id="a7a12-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-119">L'espressione `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-120">Viene trovata una `Keywords_austria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-121">Keywords</span></span>

<span data-ttu-id="a7a12-122">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-122"></span></span>
|<span data-ttu-id="a7a12-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-124">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-124">passport number</span></span>  <br/> <span data-ttu-id="a7a12-125">numero di passaporto austriaco</span><span class="sxs-lookup"><span data-stu-id="a7a12-125">austrian passport number</span></span>  <br/> <span data-ttu-id="a7a12-126">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-126">passport no</span></span>  <br/> <span data-ttu-id="a7a12-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="a7a12-127">reisepass</span></span>  <br/> <span data-ttu-id="a7a12-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="a7a12-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="a7a12-129">Belgio</span><span class="sxs-lookup"><span data-stu-id="a7a12-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-130">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-130">Format</span></span>

<span data-ttu-id="a7a12-131">Due lettere seguite da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-132">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-132">Pattern</span></span>

<span data-ttu-id="a7a12-133">Due lettere e seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7a12-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-134">Checksum</span></span>

<span data-ttu-id="a7a12-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a7a12-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-136">Definition</span></span>

<span data-ttu-id="a7a12-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-138">L'espressione `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-139">Viene trovata una `Keywords_belgium_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-140">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-140">Keywords</span></span>

<span data-ttu-id="a7a12-141">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-141"></span></span>
|<span data-ttu-id="a7a12-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-143">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-143">passport number</span></span>  <br/> <span data-ttu-id="a7a12-144">numero di passaporto belga</span><span class="sxs-lookup"><span data-stu-id="a7a12-144">belgian passport number</span></span>  <br/> <span data-ttu-id="a7a12-145">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-145">passport no</span></span>  <br/> <span data-ttu-id="a7a12-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="a7a12-146">paspoort</span></span>  <br/> <span data-ttu-id="a7a12-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a7a12-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="a7a12-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="a7a12-148">reisepass kein</span></span>  <br/> <span data-ttu-id="a7a12-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="a7a12-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="a7a12-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="a7a12-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-151">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-151">Format</span></span>

<span data-ttu-id="a7a12-152">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-153">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-153">Pattern</span></span>

 <span data-ttu-id="a7a12-154">9 cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a7a12-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-155">Checksum</span></span>

<span data-ttu-id="a7a12-156">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-157">Definition</span></span>

<span data-ttu-id="a7a12-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-159">L'espressione `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-160">Viene trovata una `Keywords_bulgaria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-161">Keywords</span></span>

<span data-ttu-id="a7a12-162">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-162"></span></span>
|<span data-ttu-id="a7a12-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-164">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-164">passport number</span></span>  <br/> <span data-ttu-id="a7a12-165">numero di passaporto bulgaro</span><span class="sxs-lookup"><span data-stu-id="a7a12-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="a7a12-166">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-166">passport no</span></span>  <br/> <span data-ttu-id="a7a12-167">Номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="a7a12-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="a7a12-168">Croazia</span><span class="sxs-lookup"><span data-stu-id="a7a12-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-169">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-169">Format</span></span>

<span data-ttu-id="a7a12-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-171">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-171">Pattern</span></span>

 <span data-ttu-id="a7a12-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a7a12-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-173">Checksum</span></span>

<span data-ttu-id="a7a12-174">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-175">Definition</span></span>

<span data-ttu-id="a7a12-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-177">L'espressione `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-178">Viene trovata una `Keywords_croatia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-179">Keywords</span></span>

<span data-ttu-id="a7a12-180">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-180"></span></span>
|<span data-ttu-id="a7a12-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-182">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-182">passport number</span></span>  <br/> <span data-ttu-id="a7a12-183">numero di passaporto croato</span><span class="sxs-lookup"><span data-stu-id="a7a12-183">croatian passport number</span></span>  <br/> <span data-ttu-id="a7a12-184">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-184">passport no</span></span>  <br/> <span data-ttu-id="a7a12-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="a7a12-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="a7a12-186">Cipro</span><span class="sxs-lookup"><span data-stu-id="a7a12-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-187">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-187">Format</span></span>

<span data-ttu-id="a7a12-188">Una lettera seguita da 6-8 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-189">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-189">Pattern</span></span>

<span data-ttu-id="a7a12-190">Una lettera seguita da sei a otto cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7a12-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-191">Checksum</span></span>

<span data-ttu-id="a7a12-192">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-193">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-193">Definition</span></span>

<span data-ttu-id="a7a12-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-195">L'espressione `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-196">Viene trovata una `Keywords_cyprus_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-197">Keywords</span></span>

<span data-ttu-id="a7a12-198">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-198"></span></span>
|<span data-ttu-id="a7a12-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-200">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-200">passport number</span></span>  <br/> <span data-ttu-id="a7a12-201">numero di passaporto di Cipro</span><span class="sxs-lookup"><span data-stu-id="a7a12-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="a7a12-202">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-202">passport no</span></span>  <br/> <span data-ttu-id="a7a12-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="a7a12-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="a7a12-204">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="a7a12-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-205">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-205">Format</span></span>

<span data-ttu-id="a7a12-206">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-207">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-207">Pattern</span></span>

<span data-ttu-id="a7a12-208">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7a12-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-209">Checksum</span></span>

<span data-ttu-id="a7a12-210">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-211">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-211">Definition</span></span>

<span data-ttu-id="a7a12-212">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-213">L'espressione `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-214">Viene trovata una `Keywords_czech_republic_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-215">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-215">Keywords</span></span>

<span data-ttu-id="a7a12-216">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-216"></span></span>
|<span data-ttu-id="a7a12-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-218">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-218">passport number</span></span>  <br/> <span data-ttu-id="a7a12-219">numero di passaporto ceco</span><span class="sxs-lookup"><span data-stu-id="a7a12-219">czech passport number</span></span>  <br/> <span data-ttu-id="a7a12-220">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-220">passport no</span></span>  <br/> <span data-ttu-id="a7a12-221">Cestovní pas</span><span class="sxs-lookup"><span data-stu-id="a7a12-221">cestovní pas</span></span>  <br/> <span data-ttu-id="a7a12-222">pas</span><span class="sxs-lookup"><span data-stu-id="a7a12-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="a7a12-223">Danimarca</span><span class="sxs-lookup"><span data-stu-id="a7a12-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-224">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-224">Format</span></span>

<span data-ttu-id="a7a12-225">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-226">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-226">Pattern</span></span>

 <span data-ttu-id="a7a12-227">9 cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a7a12-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-228">Checksum</span></span>

<span data-ttu-id="a7a12-229">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-230">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-230">Definition</span></span>

<span data-ttu-id="a7a12-231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-232">L'espressione `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-233">Viene trovata una `Keywords_denmark_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-234">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-234">Keywords</span></span>

<span data-ttu-id="a7a12-235">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-235"></span></span>
|<span data-ttu-id="a7a12-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-237">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-237">passport number</span></span>  <br/> <span data-ttu-id="a7a12-238">numero di passaporto danese</span><span class="sxs-lookup"><span data-stu-id="a7a12-238">danish passport number</span></span>  <br/> <span data-ttu-id="a7a12-239">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-239">passport no</span></span>  <br/> <span data-ttu-id="a7a12-240">pas</span><span class="sxs-lookup"><span data-stu-id="a7a12-240">pas</span></span>  <br/> <span data-ttu-id="a7a12-241">Pasnummer</span><span class="sxs-lookup"><span data-stu-id="a7a12-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="a7a12-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="a7a12-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-243">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-243">Format</span></span>

<span data-ttu-id="a7a12-244">Una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-245">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-245">Pattern</span></span>

<span data-ttu-id="a7a12-246">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7a12-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-247">Checksum</span></span>

<span data-ttu-id="a7a12-248">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-249">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-249">Definition</span></span>

<span data-ttu-id="a7a12-250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-251">L'espressione `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-252">Viene trovata una `Keywords_estonia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-253">Keywords</span></span>

<span data-ttu-id="a7a12-254">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-254"></span></span>
|<span data-ttu-id="a7a12-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-256">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-256">passport number</span></span>  <br/> <span data-ttu-id="a7a12-257">numero di passaporto estone</span><span class="sxs-lookup"><span data-stu-id="a7a12-257">estonian passport number</span></span>  <br/> <span data-ttu-id="a7a12-258">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-258">passport no</span></span>  <br/> <span data-ttu-id="a7a12-259">passaggio kodaniku Eesti</span><span class="sxs-lookup"><span data-stu-id="a7a12-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="a7a12-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="a7a12-260">Finland</span></span>

<span data-ttu-id="a7a12-261">Per informazioni dettagliate, vedere la sezione "Finlandia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a7a12-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="a7a12-262">Francia</span><span class="sxs-lookup"><span data-stu-id="a7a12-262">France</span></span>

<span data-ttu-id="a7a12-263">Per informazioni dettagliate, vedere la sezione "Francia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a7a12-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="a7a12-264">Germania</span><span class="sxs-lookup"><span data-stu-id="a7a12-264">Germany</span></span>

<span data-ttu-id="a7a12-265">Per informazioni dettagliate, vedere la sezione "Germania Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a7a12-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="a7a12-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="a7a12-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-267">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-267">Format</span></span>

<span data-ttu-id="a7a12-268">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-269">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-269">Pattern</span></span>

<span data-ttu-id="a7a12-270">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7a12-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-271">Checksum</span></span>

<span data-ttu-id="a7a12-272">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-273">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-273">Definition</span></span>

<span data-ttu-id="a7a12-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-275">L'espressione `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-276">Viene trovata una `Keywords_greece_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-277">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-277">Keywords</span></span>

<span data-ttu-id="a7a12-278">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-278"></span></span>
|<span data-ttu-id="a7a12-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-280">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-280">passport number</span></span>  <br/> <span data-ttu-id="a7a12-281">numero di passaporto greco</span><span class="sxs-lookup"><span data-stu-id="a7a12-281">greek passport number</span></span>  <br/> <span data-ttu-id="a7a12-282">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-282">passport no</span></span>  <br/> <span data-ttu-id="a7a12-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="a7a12-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="a7a12-284">Ungheria</span><span class="sxs-lookup"><span data-stu-id="a7a12-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-285">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-285">Format</span></span>

<span data-ttu-id="a7a12-286">Due lettere seguite da sei o sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-287">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-287">Pattern</span></span>

<span data-ttu-id="a7a12-288">Due lettere seguite da sei o sette cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7a12-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-289">Checksum</span></span>

<span data-ttu-id="a7a12-290">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-291">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-291">Definition</span></span>

<span data-ttu-id="a7a12-292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-293">L'espressione `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-294">Viene trovata una `Keywords_hungary_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-295">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-295">Keywords</span></span>

<span data-ttu-id="a7a12-296">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-296"></span></span>
|<span data-ttu-id="a7a12-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-298">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-298">passport number</span></span>  <br/> <span data-ttu-id="a7a12-299">numero di passaporto ungherese</span><span class="sxs-lookup"><span data-stu-id="a7a12-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="a7a12-300">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-300">passport no</span></span>  <br/> <span data-ttu-id="a7a12-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="a7a12-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="a7a12-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="a7a12-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-303">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-303">Format</span></span>

<span data-ttu-id="a7a12-304">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-305">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-305">Pattern</span></span>

<span data-ttu-id="a7a12-306">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="a7a12-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a7a12-307">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="a7a12-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a7a12-308">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7a12-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-309">Checksum</span></span>

<span data-ttu-id="a7a12-310">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-311">Definition</span></span>

<span data-ttu-id="a7a12-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-313">L'espressione `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-314">Viene trovata una `Keywords_ireland_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-315">Keywords</span></span>

<span data-ttu-id="a7a12-316">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-316"></span></span>
|<span data-ttu-id="a7a12-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-318">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-318">passport number</span></span>  <br/> <span data-ttu-id="a7a12-319">numero di passaporto irlandese</span><span class="sxs-lookup"><span data-stu-id="a7a12-319">irish passport number</span></span>  <br/> <span data-ttu-id="a7a12-320">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-320">passport no</span></span>  <br/> <span data-ttu-id="a7a12-321">pas</span><span class="sxs-lookup"><span data-stu-id="a7a12-321">pas</span></span>  <br/> <span data-ttu-id="a7a12-322">passaporto</span><span class="sxs-lookup"><span data-stu-id="a7a12-322">passport</span></span>  <br/> <span data-ttu-id="a7a12-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="a7a12-323">passeport</span></span>  <br/> <span data-ttu-id="a7a12-324">numero Passeport</span><span class="sxs-lookup"><span data-stu-id="a7a12-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="a7a12-325">Italia</span><span class="sxs-lookup"><span data-stu-id="a7a12-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-326">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-326">Format</span></span>

<span data-ttu-id="a7a12-327">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-328">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-328">Pattern</span></span>

<span data-ttu-id="a7a12-329">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="a7a12-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a7a12-330">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="a7a12-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a7a12-331">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7a12-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-332">Checksum</span></span>

<span data-ttu-id="a7a12-333">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a7a12-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-334">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-334">Definition</span></span>

<span data-ttu-id="a7a12-335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-336">L'espressione `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-337">Viene trovata una `Keywords_italy_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-338">Keywords</span></span>

<span data-ttu-id="a7a12-339">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-339"></span></span>
|<span data-ttu-id="a7a12-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-341">numero di passaporto italiano</span><span class="sxs-lookup"><span data-stu-id="a7a12-341">italian passport number</span></span>  <br/> <span data-ttu-id="a7a12-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="a7a12-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="a7a12-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="a7a12-343">passaporto</span></span>  <br/> <span data-ttu-id="a7a12-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="a7a12-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="a7a12-345">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-345">passport number</span></span>  <br/> <span data-ttu-id="a7a12-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="a7a12-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="a7a12-347">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="a7a12-347">passaporto numero</span></span>  <br/> <span data-ttu-id="a7a12-348">numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="a7a12-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="a7a12-349">numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="a7a12-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="a7a12-350">Lettonia</span><span class="sxs-lookup"><span data-stu-id="a7a12-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-351">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-351">Format</span></span>

<span data-ttu-id="a7a12-352">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-353">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-353">Pattern</span></span>

<span data-ttu-id="a7a12-354">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="a7a12-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a7a12-355">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="a7a12-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a7a12-356">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7a12-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-357">Checksum</span></span>

<span data-ttu-id="a7a12-358">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-359">Definition</span></span>

<span data-ttu-id="a7a12-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-361">L'espressione `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-362">Viene trovata una `Keywords_latvia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-363">Keywords</span></span>

<span data-ttu-id="a7a12-364">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-364"></span></span>
|<span data-ttu-id="a7a12-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-366">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-366">passport number</span></span>  <br/> <span data-ttu-id="a7a12-367">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="a7a12-367">latvian passport number</span></span>  <br/> <span data-ttu-id="a7a12-368">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-368">passport no</span></span>  <br/> <span data-ttu-id="a7a12-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="a7a12-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="a7a12-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="a7a12-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-371">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-371">Format</span></span>

<span data-ttu-id="a7a12-372">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-373">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-373">Pattern</span></span>

<span data-ttu-id="a7a12-374">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="a7a12-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7a12-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-375">Checksum</span></span>

<span data-ttu-id="a7a12-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a7a12-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-377">Definition</span></span>

<span data-ttu-id="a7a12-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-379">L'espressione `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-380">Viene trovata una `Keywords_lithuania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-381">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-381">Keywords</span></span>

<span data-ttu-id="a7a12-382">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-382"></span></span>
|<span data-ttu-id="a7a12-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-384">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-384">passport number</span></span>  <br/> <span data-ttu-id="a7a12-385">numero di passaporto di lithunian</span><span class="sxs-lookup"><span data-stu-id="a7a12-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="a7a12-386">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-386">passport no</span></span>  <br/> <span data-ttu-id="a7a12-387">numero di Paso</span><span class="sxs-lookup"><span data-stu-id="a7a12-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="a7a12-388">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="a7a12-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-389">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-389">Format</span></span>

<span data-ttu-id="a7a12-390">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-391">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-391">Pattern</span></span>

<span data-ttu-id="a7a12-392">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="a7a12-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7a12-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-393">Checksum</span></span>

<span data-ttu-id="a7a12-394">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-395">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-395">Definition</span></span>

<span data-ttu-id="a7a12-396">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-397">L'espressione `Regex_nation_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-398">Viene trovata una `Keywords_nation_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-399">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-399">Keywords</span></span>

<span data-ttu-id="a7a12-400">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-400"></span></span>
|<span data-ttu-id="a7a12-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-402">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-402">passport number</span></span>  <br/> <span data-ttu-id="a7a12-403">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="a7a12-403">latvian passport number</span></span>  <br/> <span data-ttu-id="a7a12-404">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-404">passport no</span></span>  <br/> <span data-ttu-id="a7a12-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="a7a12-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="a7a12-406">Malta</span><span class="sxs-lookup"><span data-stu-id="a7a12-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-407">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-407">Format</span></span>

<span data-ttu-id="a7a12-408">Sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-409">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-409">Pattern</span></span>

 <span data-ttu-id="a7a12-410">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a7a12-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-411">Checksum</span></span>

<span data-ttu-id="a7a12-412">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-413">Definition</span></span>

<span data-ttu-id="a7a12-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-415">L'espressione `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-416">Viene trovata una `Keywords_malta_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-417">Keywords</span></span>

<span data-ttu-id="a7a12-418">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-418"></span></span>
|<span data-ttu-id="a7a12-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-420">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-420">passport number</span></span>  <br/> <span data-ttu-id="a7a12-421">numero di passaporto maltese</span><span class="sxs-lookup"><span data-stu-id="a7a12-421">maltese passport number</span></span>  <br/> <span data-ttu-id="a7a12-422">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-422">passport no</span></span>  <br/> <span data-ttu-id="a7a12-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="a7a12-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="a7a12-424">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="a7a12-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-425">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-425">Format</span></span>

<span data-ttu-id="a7a12-426">Nove lettere o cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-427">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-427">Pattern</span></span>

<span data-ttu-id="a7a12-428">Nove lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7a12-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-429">Checksum</span></span>

<span data-ttu-id="a7a12-430">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a7a12-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-431">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-431">Definition</span></span>

<span data-ttu-id="a7a12-432">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-433">L'espressione `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-434">Viene trovata una `Keywords_netherlands_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-435">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-435">Keywords</span></span>

<span data-ttu-id="a7a12-436">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-436"></span></span>
|<span data-ttu-id="a7a12-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-438">numero di passaporto olandese</span><span class="sxs-lookup"><span data-stu-id="a7a12-438">dutch passport number</span></span>  <br/> <span data-ttu-id="a7a12-439">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-439">passport number</span></span>  <br/> <span data-ttu-id="a7a12-440">numero di passaporto per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="a7a12-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="a7a12-441">Nederlanden PASPOORT Nummer</span><span class="sxs-lookup"><span data-stu-id="a7a12-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="a7a12-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="a7a12-442">paspoort</span></span>  <br/> <span data-ttu-id="a7a12-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a7a12-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="a7a12-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a7a12-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="a7a12-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="a7a12-445">Poland</span></span>

<span data-ttu-id="a7a12-446">Per informazioni dettagliate, vedere la sezione "Poland Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a7a12-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="a7a12-447">Portogallo</span><span class="sxs-lookup"><span data-stu-id="a7a12-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-448">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-448">Format</span></span>

<span data-ttu-id="a7a12-449">Una lettera seguita da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-450">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-450">Pattern</span></span>

<span data-ttu-id="a7a12-451">Una lettera seguita da sei cifre:</span><span class="sxs-lookup"><span data-stu-id="a7a12-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="a7a12-452">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="a7a12-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="a7a12-453">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7a12-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-454">Checksum</span></span>

<span data-ttu-id="a7a12-455">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-456">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-456">Definition</span></span>

<span data-ttu-id="a7a12-457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-458">L'espressione `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-459">Viene trovata una `Keywords_portugal_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-460">Keywords</span></span>

<span data-ttu-id="a7a12-461">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-461"></span></span>
|<span data-ttu-id="a7a12-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-463">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-463">passport number</span></span>  <br/> <span data-ttu-id="a7a12-464">numero di passaporto portoghese</span><span class="sxs-lookup"><span data-stu-id="a7a12-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="a7a12-465">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-465">passport no</span></span>  <br/> <span data-ttu-id="a7a12-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="a7a12-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="a7a12-467">Romania</span><span class="sxs-lookup"><span data-stu-id="a7a12-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-468">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-468">Format</span></span>

<span data-ttu-id="a7a12-469">Otto o nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-470">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-470">Pattern</span></span>

<span data-ttu-id="a7a12-471">Otto o nove cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7a12-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-472">Checksum</span></span>

<span data-ttu-id="a7a12-473">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-474">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-474">Definition</span></span>

<span data-ttu-id="a7a12-475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-476">L'espressione `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-477">Viene trovata una `Keywords_romania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-478">Keywords</span></span>

<span data-ttu-id="a7a12-479">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-479"></span></span>
|<span data-ttu-id="a7a12-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-481">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-481">passport number</span></span>  <br/> <span data-ttu-id="a7a12-482">numero di passaporto rumeno</span><span class="sxs-lookup"><span data-stu-id="a7a12-482">romanian passport number</span></span>  <br/> <span data-ttu-id="a7a12-483">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-483">passport no</span></span>  <br/> <span data-ttu-id="a7a12-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="a7a12-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="a7a12-485">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="a7a12-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-486">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-486">Format</span></span>

<span data-ttu-id="a7a12-487">Una cifra o una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-488">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-488">Pattern</span></span>

<span data-ttu-id="a7a12-489">Una cifra o una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7a12-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-490">Checksum</span></span>

<span data-ttu-id="a7a12-491">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-492">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-492">Definition</span></span>

<span data-ttu-id="a7a12-493">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-494">L'espressione `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-495">Viene trovata una `Keywords_slovakia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-496">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-496">Keywords</span></span>

<span data-ttu-id="a7a12-497">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-497"></span></span>
|<span data-ttu-id="a7a12-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-499">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-499">passport number</span></span>  <br/> <span data-ttu-id="a7a12-500">numero di passaporto slovacco</span><span class="sxs-lookup"><span data-stu-id="a7a12-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="a7a12-501">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-501">passport no</span></span>  <br/> <span data-ttu-id="a7a12-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="a7a12-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="a7a12-503">Slovenia</span><span class="sxs-lookup"><span data-stu-id="a7a12-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-504">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-504">Format</span></span>

<span data-ttu-id="a7a12-505">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-506">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-506">Pattern</span></span>

<span data-ttu-id="a7a12-507">Due lettere seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="a7a12-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="a7a12-508">La lettera "P"</span><span class="sxs-lookup"><span data-stu-id="a7a12-508">The letter "P"</span></span>
    
- <span data-ttu-id="a7a12-509">Una lettera maiuscola</span><span class="sxs-lookup"><span data-stu-id="a7a12-509">One uppercase letter</span></span>
    
- <span data-ttu-id="a7a12-510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7a12-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-511">Checksum</span></span>

<span data-ttu-id="a7a12-512">No</span><span class="sxs-lookup"><span data-stu-id="a7a12-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-513">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-513">Definition</span></span>

<span data-ttu-id="a7a12-514">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-515">L'espressione `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-516">Viene trovata una `Keywords_slovenia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-517">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-517">Keywords</span></span>

<span data-ttu-id="a7a12-518">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-518"></span></span>
|<span data-ttu-id="a7a12-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-520">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-520">passport number</span></span>  <br/> <span data-ttu-id="a7a12-521">numero di passaporto sloveno</span><span class="sxs-lookup"><span data-stu-id="a7a12-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="a7a12-522">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-522">passport no</span></span>  <br/> <span data-ttu-id="a7a12-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="a7a12-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="a7a12-524">Spagna</span><span class="sxs-lookup"><span data-stu-id="a7a12-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="a7a12-525">Formato</span><span class="sxs-lookup"><span data-stu-id="a7a12-525">Format</span></span>

<span data-ttu-id="a7a12-526">Combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a7a12-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7a12-527">Modello</span><span class="sxs-lookup"><span data-stu-id="a7a12-527">Pattern</span></span>

<span data-ttu-id="a7a12-528">Combinazione di lettere e numeri di otto o nove caratteri:</span><span class="sxs-lookup"><span data-stu-id="a7a12-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="a7a12-529">Due cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="a7a12-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="a7a12-530">Una cifra o una lettera (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="a7a12-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="a7a12-531">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="a7a12-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7a12-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="a7a12-532">Checksum</span></span>

<span data-ttu-id="a7a12-533">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a7a12-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7a12-534">Definizione</span><span class="sxs-lookup"><span data-stu-id="a7a12-534">Definition</span></span>

<span data-ttu-id="a7a12-535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a7a12-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7a12-536">L'espressione `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a7a12-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7a12-537">Viene trovata una `Keywords_spain_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a7a12-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7a12-538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a7a12-538">Keywords</span></span>

<span data-ttu-id="a7a12-539">| |</span><span class="sxs-lookup"><span data-stu-id="a7a12-539"></span></span>
|<span data-ttu-id="a7a12-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a7a12-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a7a12-541">passaporto</span><span class="sxs-lookup"><span data-stu-id="a7a12-541">passport</span></span>  <br/> <span data-ttu-id="a7a12-542">passaporto della Spagna</span><span class="sxs-lookup"><span data-stu-id="a7a12-542">spain passport</span></span>  <br/> <span data-ttu-id="a7a12-543">libro del passaporto</span><span class="sxs-lookup"><span data-stu-id="a7a12-543">passport book</span></span>  <br/> <span data-ttu-id="a7a12-544">passport number</span><span class="sxs-lookup"><span data-stu-id="a7a12-544">passport number</span></span>  <br/> <span data-ttu-id="a7a12-545">Passport No</span><span class="sxs-lookup"><span data-stu-id="a7a12-545">passport no</span></span>  <br/> <span data-ttu-id="a7a12-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="a7a12-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="a7a12-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="a7a12-547">número pasaporte</span></span>  <br/> <span data-ttu-id="a7a12-548">pasaporte España</span><span class="sxs-lookup"><span data-stu-id="a7a12-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="a7a12-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="a7a12-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="a7a12-550">Svezia</span><span class="sxs-lookup"><span data-stu-id="a7a12-550">Sweden</span></span>

<span data-ttu-id="a7a12-551">Per informazioni dettagliate, vedere la sezione "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a7a12-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="a7a12-552">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="a7a12-552">UK</span></span>

<span data-ttu-id="a7a12-553">Per informazioni dettagliate, vedere la sezione "Stati Uniti/Regno Unito</span><span class="sxs-lookup"><span data-stu-id="a7a12-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="a7a12-554">Numero di passaporto "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a7a12-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7a12-555">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7a12-555">See also</span></span>

[<span data-ttu-id="a7a12-556">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="a7a12-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

