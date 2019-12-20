---
title: Numero di passaporto EU
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 4afcf7b764eb8976e0588464515256f7cb1bdb8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805949"
---
# <a name="eu-passport-number"></a><span data-ttu-id="1c36b-104">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="1c36b-104">EU Passport Number</span></span>

<span data-ttu-id="1c36b-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="1c36b-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="1c36b-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="1c36b-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="1c36b-107">Austria</span><span class="sxs-lookup"><span data-stu-id="1c36b-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-108">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-108">Format</span></span>

<span data-ttu-id="1c36b-109">Una lettera seguita da uno spazio facoltativo e sette cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-110">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-110">Pattern</span></span>

<span data-ttu-id="1c36b-111">Combinazione di una lettera, sette cifre e uno spazio:</span><span class="sxs-lookup"><span data-stu-id="1c36b-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="1c36b-112">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="1c36b-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="1c36b-113">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="1c36b-113">One space (optional)</span></span>
    
- <span data-ttu-id="1c36b-114">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1c36b-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-115">Checksum</span></span>

<span data-ttu-id="1c36b-116">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="1c36b-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-117">Definition</span></span>

<span data-ttu-id="1c36b-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-119">L'espressione `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-120">Viene trovata una `Keywords_austria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-121">Keywords</span></span>

<span data-ttu-id="1c36b-122">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-122"></span></span>
|<span data-ttu-id="1c36b-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-124">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-124">passport number</span></span>  <br/> <span data-ttu-id="1c36b-125">numero di passaporto austriaco</span><span class="sxs-lookup"><span data-stu-id="1c36b-125">austrian passport number</span></span>  <br/> <span data-ttu-id="1c36b-126">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-126">passport no</span></span>  <br/> <span data-ttu-id="1c36b-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="1c36b-127">reisepass</span></span>  <br/> <span data-ttu-id="1c36b-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="1c36b-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="1c36b-129">Belgio</span><span class="sxs-lookup"><span data-stu-id="1c36b-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-130">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-130">Format</span></span>

<span data-ttu-id="1c36b-131">Due lettere seguite da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-132">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-132">Pattern</span></span>

<span data-ttu-id="1c36b-133">Due lettere e seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1c36b-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-134">Checksum</span></span>

<span data-ttu-id="1c36b-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="1c36b-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-136">Definition</span></span>

<span data-ttu-id="1c36b-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-138">L'espressione `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-139">Viene trovata una `Keywords_belgium_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-140">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-140">Keywords</span></span>

<span data-ttu-id="1c36b-141">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-141"></span></span>
|<span data-ttu-id="1c36b-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-143">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-143">passport number</span></span>  <br/> <span data-ttu-id="1c36b-144">numero di passaporto belga</span><span class="sxs-lookup"><span data-stu-id="1c36b-144">belgian passport number</span></span>  <br/> <span data-ttu-id="1c36b-145">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-145">passport no</span></span>  <br/> <span data-ttu-id="1c36b-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="1c36b-146">paspoort</span></span>  <br/> <span data-ttu-id="1c36b-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1c36b-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="1c36b-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="1c36b-148">reisepass kein</span></span>  <br/> <span data-ttu-id="1c36b-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="1c36b-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="1c36b-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="1c36b-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-151">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-151">Format</span></span>

<span data-ttu-id="1c36b-152">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-153">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-153">Pattern</span></span>

 <span data-ttu-id="1c36b-154">9 cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1c36b-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-155">Checksum</span></span>

<span data-ttu-id="1c36b-156">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-157">Definition</span></span>

<span data-ttu-id="1c36b-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-159">L'espressione `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-160">Viene trovata una `Keywords_bulgaria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-161">Keywords</span></span>

<span data-ttu-id="1c36b-162">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-162"></span></span>
|<span data-ttu-id="1c36b-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-164">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-164">passport number</span></span>  <br/> <span data-ttu-id="1c36b-165">numero di passaporto bulgaro</span><span class="sxs-lookup"><span data-stu-id="1c36b-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="1c36b-166">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-166">passport no</span></span>  <br/> <span data-ttu-id="1c36b-167">Номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="1c36b-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="1c36b-168">Croazia</span><span class="sxs-lookup"><span data-stu-id="1c36b-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-169">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-169">Format</span></span>

<span data-ttu-id="1c36b-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-171">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-171">Pattern</span></span>

 <span data-ttu-id="1c36b-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1c36b-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-173">Checksum</span></span>

<span data-ttu-id="1c36b-174">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-175">Definition</span></span>

<span data-ttu-id="1c36b-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-177">L'espressione `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-178">Viene trovata una `Keywords_croatia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-179">Keywords</span></span>

<span data-ttu-id="1c36b-180">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-180"></span></span>
|<span data-ttu-id="1c36b-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-182">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-182">passport number</span></span>  <br/> <span data-ttu-id="1c36b-183">numero di passaporto croato</span><span class="sxs-lookup"><span data-stu-id="1c36b-183">croatian passport number</span></span>  <br/> <span data-ttu-id="1c36b-184">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-184">passport no</span></span>  <br/> <span data-ttu-id="1c36b-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="1c36b-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="1c36b-186">Cipro</span><span class="sxs-lookup"><span data-stu-id="1c36b-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-187">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-187">Format</span></span>

<span data-ttu-id="1c36b-188">Una lettera seguita da 6-8 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-189">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-189">Pattern</span></span>

<span data-ttu-id="1c36b-190">Una lettera seguita da sei a otto cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1c36b-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-191">Checksum</span></span>

<span data-ttu-id="1c36b-192">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-193">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-193">Definition</span></span>

<span data-ttu-id="1c36b-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-195">L'espressione `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-196">Viene trovata una `Keywords_cyprus_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-197">Keywords</span></span>

<span data-ttu-id="1c36b-198">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-198"></span></span>
|<span data-ttu-id="1c36b-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-200">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-200">passport number</span></span>  <br/> <span data-ttu-id="1c36b-201">numero di passaporto di Cipro</span><span class="sxs-lookup"><span data-stu-id="1c36b-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="1c36b-202">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-202">passport no</span></span>  <br/> <span data-ttu-id="1c36b-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="1c36b-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="1c36b-204">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="1c36b-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-205">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-205">Format</span></span>

<span data-ttu-id="1c36b-206">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-207">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-207">Pattern</span></span>

<span data-ttu-id="1c36b-208">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1c36b-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-209">Checksum</span></span>

<span data-ttu-id="1c36b-210">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-211">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-211">Definition</span></span>

<span data-ttu-id="1c36b-212">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-213">L'espressione `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-214">Viene trovata una `Keywords_czech_republic_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-215">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-215">Keywords</span></span>

<span data-ttu-id="1c36b-216">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-216"></span></span>
|<span data-ttu-id="1c36b-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-218">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-218">passport number</span></span>  <br/> <span data-ttu-id="1c36b-219">numero di passaporto ceco</span><span class="sxs-lookup"><span data-stu-id="1c36b-219">czech passport number</span></span>  <br/> <span data-ttu-id="1c36b-220">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-220">passport no</span></span>  <br/> <span data-ttu-id="1c36b-221">Cestovní pas</span><span class="sxs-lookup"><span data-stu-id="1c36b-221">cestovní pas</span></span>  <br/> <span data-ttu-id="1c36b-222">pas</span><span class="sxs-lookup"><span data-stu-id="1c36b-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="1c36b-223">Danimarca</span><span class="sxs-lookup"><span data-stu-id="1c36b-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-224">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-224">Format</span></span>

<span data-ttu-id="1c36b-225">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-226">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-226">Pattern</span></span>

 <span data-ttu-id="1c36b-227">9 cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1c36b-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-228">Checksum</span></span>

<span data-ttu-id="1c36b-229">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-230">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-230">Definition</span></span>

<span data-ttu-id="1c36b-231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-232">L'espressione `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-233">Viene trovata una `Keywords_denmark_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-234">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-234">Keywords</span></span>

<span data-ttu-id="1c36b-235">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-235"></span></span>
|<span data-ttu-id="1c36b-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-237">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-237">passport number</span></span>  <br/> <span data-ttu-id="1c36b-238">numero di passaporto danese</span><span class="sxs-lookup"><span data-stu-id="1c36b-238">danish passport number</span></span>  <br/> <span data-ttu-id="1c36b-239">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-239">passport no</span></span>  <br/> <span data-ttu-id="1c36b-240">pas</span><span class="sxs-lookup"><span data-stu-id="1c36b-240">pas</span></span>  <br/> <span data-ttu-id="1c36b-241">Pasnummer</span><span class="sxs-lookup"><span data-stu-id="1c36b-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="1c36b-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="1c36b-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-243">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-243">Format</span></span>

<span data-ttu-id="1c36b-244">Una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-245">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-245">Pattern</span></span>

<span data-ttu-id="1c36b-246">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1c36b-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-247">Checksum</span></span>

<span data-ttu-id="1c36b-248">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-249">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-249">Definition</span></span>

<span data-ttu-id="1c36b-250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-251">L'espressione `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-252">Viene trovata una `Keywords_estonia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-253">Keywords</span></span>

<span data-ttu-id="1c36b-254">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-254"></span></span>
|<span data-ttu-id="1c36b-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-256">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-256">passport number</span></span>  <br/> <span data-ttu-id="1c36b-257">numero di passaporto estone</span><span class="sxs-lookup"><span data-stu-id="1c36b-257">estonian passport number</span></span>  <br/> <span data-ttu-id="1c36b-258">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-258">passport no</span></span>  <br/> <span data-ttu-id="1c36b-259">passaggio kodaniku Eesti</span><span class="sxs-lookup"><span data-stu-id="1c36b-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="1c36b-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="1c36b-260">Finland</span></span>

<span data-ttu-id="1c36b-261">Per informazioni dettagliate, vedere la sezione "Finlandia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1c36b-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="1c36b-262">Francia</span><span class="sxs-lookup"><span data-stu-id="1c36b-262">France</span></span>

<span data-ttu-id="1c36b-263">Per informazioni dettagliate, vedere la sezione "Francia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1c36b-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="1c36b-264">Germania</span><span class="sxs-lookup"><span data-stu-id="1c36b-264">Germany</span></span>

<span data-ttu-id="1c36b-265">Per informazioni dettagliate, vedere la sezione "numero di passaporto tedesco" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1c36b-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="1c36b-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="1c36b-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-267">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-267">Format</span></span>

<span data-ttu-id="1c36b-268">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-269">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-269">Pattern</span></span>

<span data-ttu-id="1c36b-270">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1c36b-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-271">Checksum</span></span>

<span data-ttu-id="1c36b-272">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-273">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-273">Definition</span></span>

<span data-ttu-id="1c36b-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-275">L'espressione `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-276">Viene trovata una `Keywords_greece_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-277">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-277">Keywords</span></span>

<span data-ttu-id="1c36b-278">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-278"></span></span>
|<span data-ttu-id="1c36b-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-280">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-280">passport number</span></span>  <br/> <span data-ttu-id="1c36b-281">numero di passaporto greco</span><span class="sxs-lookup"><span data-stu-id="1c36b-281">greek passport number</span></span>  <br/> <span data-ttu-id="1c36b-282">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-282">passport no</span></span>  <br/> <span data-ttu-id="1c36b-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="1c36b-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="1c36b-284">Ungheria</span><span class="sxs-lookup"><span data-stu-id="1c36b-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-285">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-285">Format</span></span>

<span data-ttu-id="1c36b-286">Due lettere seguite da sei o sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-287">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-287">Pattern</span></span>

<span data-ttu-id="1c36b-288">Due lettere seguite da sei o sette cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1c36b-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-289">Checksum</span></span>

<span data-ttu-id="1c36b-290">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-291">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-291">Definition</span></span>

<span data-ttu-id="1c36b-292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-293">L'espressione `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-294">Viene trovata una `Keywords_hungary_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-295">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-295">Keywords</span></span>

<span data-ttu-id="1c36b-296">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-296"></span></span>
|<span data-ttu-id="1c36b-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-298">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-298">passport number</span></span>  <br/> <span data-ttu-id="1c36b-299">numero di passaporto ungherese</span><span class="sxs-lookup"><span data-stu-id="1c36b-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="1c36b-300">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-300">passport no</span></span>  <br/> <span data-ttu-id="1c36b-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="1c36b-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="1c36b-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="1c36b-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-303">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-303">Format</span></span>

<span data-ttu-id="1c36b-304">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-305">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-305">Pattern</span></span>

<span data-ttu-id="1c36b-306">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="1c36b-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1c36b-307">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="1c36b-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1c36b-308">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1c36b-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-309">Checksum</span></span>

<span data-ttu-id="1c36b-310">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-311">Definition</span></span>

<span data-ttu-id="1c36b-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-313">L'espressione `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-314">Viene trovata una `Keywords_ireland_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-315">Keywords</span></span>

<span data-ttu-id="1c36b-316">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-316"></span></span>
|<span data-ttu-id="1c36b-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-318">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-318">passport number</span></span>  <br/> <span data-ttu-id="1c36b-319">numero di passaporto irlandese</span><span class="sxs-lookup"><span data-stu-id="1c36b-319">irish passport number</span></span>  <br/> <span data-ttu-id="1c36b-320">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-320">passport no</span></span>  <br/> <span data-ttu-id="1c36b-321">pas</span><span class="sxs-lookup"><span data-stu-id="1c36b-321">pas</span></span>  <br/> <span data-ttu-id="1c36b-322">passaporto</span><span class="sxs-lookup"><span data-stu-id="1c36b-322">passport</span></span>  <br/> <span data-ttu-id="1c36b-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="1c36b-323">passeport</span></span>  <br/> <span data-ttu-id="1c36b-324">numero Passeport</span><span class="sxs-lookup"><span data-stu-id="1c36b-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="1c36b-325">Italia</span><span class="sxs-lookup"><span data-stu-id="1c36b-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-326">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-326">Format</span></span>

<span data-ttu-id="1c36b-327">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-328">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-328">Pattern</span></span>

<span data-ttu-id="1c36b-329">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="1c36b-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1c36b-330">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="1c36b-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1c36b-331">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1c36b-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-332">Checksum</span></span>

<span data-ttu-id="1c36b-333">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="1c36b-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-334">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-334">Definition</span></span>

<span data-ttu-id="1c36b-335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-336">L'espressione `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-337">Viene trovata una `Keywords_italy_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-338">Keywords</span></span>

<span data-ttu-id="1c36b-339">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-339"></span></span>
|<span data-ttu-id="1c36b-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-341">numero di passaporto italiano</span><span class="sxs-lookup"><span data-stu-id="1c36b-341">italian passport number</span></span>  <br/> <span data-ttu-id="1c36b-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="1c36b-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="1c36b-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="1c36b-343">passaporto</span></span>  <br/> <span data-ttu-id="1c36b-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="1c36b-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="1c36b-345">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-345">passport number</span></span>  <br/> <span data-ttu-id="1c36b-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="1c36b-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="1c36b-347">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="1c36b-347">passaporto numero</span></span>  <br/> <span data-ttu-id="1c36b-348">numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="1c36b-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="1c36b-349">numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="1c36b-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="1c36b-350">Lettonia</span><span class="sxs-lookup"><span data-stu-id="1c36b-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-351">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-351">Format</span></span>

<span data-ttu-id="1c36b-352">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-353">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-353">Pattern</span></span>

<span data-ttu-id="1c36b-354">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="1c36b-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1c36b-355">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="1c36b-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1c36b-356">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1c36b-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-357">Checksum</span></span>

<span data-ttu-id="1c36b-358">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-359">Definition</span></span>

<span data-ttu-id="1c36b-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-361">L'espressione `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-362">Viene trovata una `Keywords_latvia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-363">Keywords</span></span>

<span data-ttu-id="1c36b-364">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-364"></span></span>
|<span data-ttu-id="1c36b-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-366">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-366">passport number</span></span>  <br/> <span data-ttu-id="1c36b-367">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="1c36b-367">latvian passport number</span></span>  <br/> <span data-ttu-id="1c36b-368">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-368">passport no</span></span>  <br/> <span data-ttu-id="1c36b-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="1c36b-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="1c36b-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="1c36b-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-371">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-371">Format</span></span>

<span data-ttu-id="1c36b-372">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-373">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-373">Pattern</span></span>

<span data-ttu-id="1c36b-374">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="1c36b-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1c36b-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-375">Checksum</span></span>

<span data-ttu-id="1c36b-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="1c36b-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-377">Definition</span></span>

<span data-ttu-id="1c36b-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-379">L'espressione `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-380">Viene trovata una `Keywords_lithuania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-381">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-381">Keywords</span></span>

<span data-ttu-id="1c36b-382">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-382"></span></span>
|<span data-ttu-id="1c36b-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-384">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-384">passport number</span></span>  <br/> <span data-ttu-id="1c36b-385">numero di passaporto di lithunian</span><span class="sxs-lookup"><span data-stu-id="1c36b-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="1c36b-386">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-386">passport no</span></span>  <br/> <span data-ttu-id="1c36b-387">numero di Paso</span><span class="sxs-lookup"><span data-stu-id="1c36b-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="1c36b-388">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="1c36b-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-389">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-389">Format</span></span>

<span data-ttu-id="1c36b-390">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-391">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-391">Pattern</span></span>

<span data-ttu-id="1c36b-392">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="1c36b-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1c36b-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-393">Checksum</span></span>

<span data-ttu-id="1c36b-394">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-395">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-395">Definition</span></span>

<span data-ttu-id="1c36b-396">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-397">L'espressione `Regex_nation_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-398">Viene trovata una `Keywords_nation_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-399">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-399">Keywords</span></span>

<span data-ttu-id="1c36b-400">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-400"></span></span>
|<span data-ttu-id="1c36b-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-402">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-402">passport number</span></span>  <br/> <span data-ttu-id="1c36b-403">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="1c36b-403">latvian passport number</span></span>  <br/> <span data-ttu-id="1c36b-404">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-404">passport no</span></span>  <br/> <span data-ttu-id="1c36b-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="1c36b-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="1c36b-406">Malta</span><span class="sxs-lookup"><span data-stu-id="1c36b-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-407">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-407">Format</span></span>

<span data-ttu-id="1c36b-408">Sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-409">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-409">Pattern</span></span>

 <span data-ttu-id="1c36b-410">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1c36b-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-411">Checksum</span></span>

<span data-ttu-id="1c36b-412">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-413">Definition</span></span>

<span data-ttu-id="1c36b-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-415">L'espressione `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-416">Viene trovata una `Keywords_malta_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-417">Keywords</span></span>

<span data-ttu-id="1c36b-418">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-418"></span></span>
|<span data-ttu-id="1c36b-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-420">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-420">passport number</span></span>  <br/> <span data-ttu-id="1c36b-421">numero di passaporto maltese</span><span class="sxs-lookup"><span data-stu-id="1c36b-421">maltese passport number</span></span>  <br/> <span data-ttu-id="1c36b-422">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-422">passport no</span></span>  <br/> <span data-ttu-id="1c36b-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="1c36b-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="1c36b-424">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="1c36b-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-425">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-425">Format</span></span>

<span data-ttu-id="1c36b-426">Nove lettere o cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-427">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-427">Pattern</span></span>

<span data-ttu-id="1c36b-428">Nove lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1c36b-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-429">Checksum</span></span>

<span data-ttu-id="1c36b-430">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="1c36b-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-431">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-431">Definition</span></span>

<span data-ttu-id="1c36b-432">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-433">L'espressione `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-434">Viene trovata una `Keywords_netherlands_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-435">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-435">Keywords</span></span>

<span data-ttu-id="1c36b-436">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-436"></span></span>
|<span data-ttu-id="1c36b-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-438">numero di passaporto olandese</span><span class="sxs-lookup"><span data-stu-id="1c36b-438">dutch passport number</span></span>  <br/> <span data-ttu-id="1c36b-439">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-439">passport number</span></span>  <br/> <span data-ttu-id="1c36b-440">numero di passaporto per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="1c36b-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="1c36b-441">Nederlanden PASPOORT Nummer</span><span class="sxs-lookup"><span data-stu-id="1c36b-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="1c36b-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="1c36b-442">paspoort</span></span>  <br/> <span data-ttu-id="1c36b-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1c36b-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="1c36b-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1c36b-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="1c36b-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="1c36b-445">Poland</span></span>

<span data-ttu-id="1c36b-446">Per informazioni dettagliate, vedere la sezione "Poland Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1c36b-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="1c36b-447">Portogallo</span><span class="sxs-lookup"><span data-stu-id="1c36b-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-448">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-448">Format</span></span>

<span data-ttu-id="1c36b-449">Una lettera seguita da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-450">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-450">Pattern</span></span>

<span data-ttu-id="1c36b-451">Una lettera seguita da sei cifre:</span><span class="sxs-lookup"><span data-stu-id="1c36b-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="1c36b-452">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="1c36b-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="1c36b-453">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1c36b-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-454">Checksum</span></span>

<span data-ttu-id="1c36b-455">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-456">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-456">Definition</span></span>

<span data-ttu-id="1c36b-457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-458">L'espressione `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-459">Viene trovata una `Keywords_portugal_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-460">Keywords</span></span>

<span data-ttu-id="1c36b-461">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-461"></span></span>
|<span data-ttu-id="1c36b-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-463">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-463">passport number</span></span>  <br/> <span data-ttu-id="1c36b-464">numero di passaporto portoghese</span><span class="sxs-lookup"><span data-stu-id="1c36b-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="1c36b-465">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-465">passport no</span></span>  <br/> <span data-ttu-id="1c36b-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="1c36b-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="1c36b-467">Romania</span><span class="sxs-lookup"><span data-stu-id="1c36b-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-468">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-468">Format</span></span>

<span data-ttu-id="1c36b-469">Otto o nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-470">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-470">Pattern</span></span>

<span data-ttu-id="1c36b-471">Otto o nove cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1c36b-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-472">Checksum</span></span>

<span data-ttu-id="1c36b-473">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-474">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-474">Definition</span></span>

<span data-ttu-id="1c36b-475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-476">L'espressione `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-477">Viene trovata una `Keywords_romania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-478">Keywords</span></span>

<span data-ttu-id="1c36b-479">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-479"></span></span>
|<span data-ttu-id="1c36b-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-481">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-481">passport number</span></span>  <br/> <span data-ttu-id="1c36b-482">numero di passaporto rumeno</span><span class="sxs-lookup"><span data-stu-id="1c36b-482">romanian passport number</span></span>  <br/> <span data-ttu-id="1c36b-483">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-483">passport no</span></span>  <br/> <span data-ttu-id="1c36b-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="1c36b-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="1c36b-485">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="1c36b-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-486">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-486">Format</span></span>

<span data-ttu-id="1c36b-487">Una cifra o una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-488">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-488">Pattern</span></span>

<span data-ttu-id="1c36b-489">Una cifra o una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1c36b-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-490">Checksum</span></span>

<span data-ttu-id="1c36b-491">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-492">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-492">Definition</span></span>

<span data-ttu-id="1c36b-493">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-494">L'espressione `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-495">Viene trovata una `Keywords_slovakia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-496">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-496">Keywords</span></span>

<span data-ttu-id="1c36b-497">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-497"></span></span>
|<span data-ttu-id="1c36b-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-499">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-499">passport number</span></span>  <br/> <span data-ttu-id="1c36b-500">numero di passaporto slovacco</span><span class="sxs-lookup"><span data-stu-id="1c36b-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="1c36b-501">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-501">passport no</span></span>  <br/> <span data-ttu-id="1c36b-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="1c36b-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="1c36b-503">Slovenia</span><span class="sxs-lookup"><span data-stu-id="1c36b-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-504">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-504">Format</span></span>

<span data-ttu-id="1c36b-505">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-506">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-506">Pattern</span></span>

<span data-ttu-id="1c36b-507">Due lettere seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="1c36b-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="1c36b-508">La lettera "P"</span><span class="sxs-lookup"><span data-stu-id="1c36b-508">The letter "P"</span></span>
    
- <span data-ttu-id="1c36b-509">Una lettera maiuscola</span><span class="sxs-lookup"><span data-stu-id="1c36b-509">One uppercase letter</span></span>
    
- <span data-ttu-id="1c36b-510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1c36b-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-511">Checksum</span></span>

<span data-ttu-id="1c36b-512">No</span><span class="sxs-lookup"><span data-stu-id="1c36b-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-513">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-513">Definition</span></span>

<span data-ttu-id="1c36b-514">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-515">L'espressione `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-516">Viene trovata una `Keywords_slovenia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-517">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-517">Keywords</span></span>

<span data-ttu-id="1c36b-518">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-518"></span></span>
|<span data-ttu-id="1c36b-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-520">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-520">passport number</span></span>  <br/> <span data-ttu-id="1c36b-521">numero di passaporto sloveno</span><span class="sxs-lookup"><span data-stu-id="1c36b-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="1c36b-522">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-522">passport no</span></span>  <br/> <span data-ttu-id="1c36b-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="1c36b-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="1c36b-524">Spagna</span><span class="sxs-lookup"><span data-stu-id="1c36b-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="1c36b-525">Formato</span><span class="sxs-lookup"><span data-stu-id="1c36b-525">Format</span></span>

<span data-ttu-id="1c36b-526">Combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="1c36b-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1c36b-527">Modello</span><span class="sxs-lookup"><span data-stu-id="1c36b-527">Pattern</span></span>

<span data-ttu-id="1c36b-528">Combinazione di lettere e numeri di otto o nove caratteri:</span><span class="sxs-lookup"><span data-stu-id="1c36b-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="1c36b-529">Due cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="1c36b-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="1c36b-530">Una cifra o una lettera (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="1c36b-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="1c36b-531">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="1c36b-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1c36b-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="1c36b-532">Checksum</span></span>

<span data-ttu-id="1c36b-533">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="1c36b-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1c36b-534">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c36b-534">Definition</span></span>

<span data-ttu-id="1c36b-535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="1c36b-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1c36b-536">L'espressione `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="1c36b-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1c36b-537">Viene trovata una `Keywords_spain_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="1c36b-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1c36b-538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1c36b-538">Keywords</span></span>

<span data-ttu-id="1c36b-539">| |</span><span class="sxs-lookup"><span data-stu-id="1c36b-539"></span></span>
|<span data-ttu-id="1c36b-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1c36b-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1c36b-541">passaporto</span><span class="sxs-lookup"><span data-stu-id="1c36b-541">passport</span></span>  <br/> <span data-ttu-id="1c36b-542">passaporto della Spagna</span><span class="sxs-lookup"><span data-stu-id="1c36b-542">spain passport</span></span>  <br/> <span data-ttu-id="1c36b-543">libro del passaporto</span><span class="sxs-lookup"><span data-stu-id="1c36b-543">passport book</span></span>  <br/> <span data-ttu-id="1c36b-544">passport number</span><span class="sxs-lookup"><span data-stu-id="1c36b-544">passport number</span></span>  <br/> <span data-ttu-id="1c36b-545">Passport No</span><span class="sxs-lookup"><span data-stu-id="1c36b-545">passport no</span></span>  <br/> <span data-ttu-id="1c36b-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="1c36b-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="1c36b-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="1c36b-547">número pasaporte</span></span>  <br/> <span data-ttu-id="1c36b-548">pasaporte España</span><span class="sxs-lookup"><span data-stu-id="1c36b-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="1c36b-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="1c36b-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="1c36b-550">Svezia</span><span class="sxs-lookup"><span data-stu-id="1c36b-550">Sweden</span></span>

<span data-ttu-id="1c36b-551">Per informazioni dettagliate, vedere la sezione "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1c36b-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="1c36b-552">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="1c36b-552">UK</span></span>

<span data-ttu-id="1c36b-553">Per informazioni dettagliate, vedere la sezione "Stati Uniti/Regno Unito</span><span class="sxs-lookup"><span data-stu-id="1c36b-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="1c36b-554">Numero di passaporto "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1c36b-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c36b-555">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c36b-555">See also</span></span>

[<span data-ttu-id="1c36b-556">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="1c36b-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

