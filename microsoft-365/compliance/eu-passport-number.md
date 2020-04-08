---
title: Numero di passaporto EU
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 0032d3e50d7dab0b696d9000242e70956469052e
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "41592117"
---
# <a name="eu-passport-number"></a><span data-ttu-id="09c2e-104">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="09c2e-104">EU Passport Number</span></span>

<span data-ttu-id="09c2e-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="09c2e-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="09c2e-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="09c2e-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="09c2e-107">Austria</span><span class="sxs-lookup"><span data-stu-id="09c2e-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-108">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-108">Format</span></span>

<span data-ttu-id="09c2e-109">Una lettera seguita da uno spazio facoltativo e sette cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-110">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-110">Pattern</span></span>

<span data-ttu-id="09c2e-111">Combinazione di una lettera, sette cifre e uno spazio:</span><span class="sxs-lookup"><span data-stu-id="09c2e-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="09c2e-112">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="09c2e-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="09c2e-113">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="09c2e-113">One space (optional)</span></span>
    
- <span data-ttu-id="09c2e-114">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09c2e-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-115">Checksum</span></span>

<span data-ttu-id="09c2e-116">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="09c2e-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-117">Definition</span></span>

<span data-ttu-id="09c2e-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-119">L'espressione `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-120">Viene trovata una `Keywords_austria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-121">Keywords</span></span>

<span data-ttu-id="09c2e-122">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-122">| |</span></span>
|<span data-ttu-id="09c2e-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-124">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-124">passport number</span></span>  <br/> <span data-ttu-id="09c2e-125">numero di passaporto austriaco</span><span class="sxs-lookup"><span data-stu-id="09c2e-125">austrian passport number</span></span>  <br/> <span data-ttu-id="09c2e-126">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-126">passport no</span></span>  <br/> <span data-ttu-id="09c2e-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="09c2e-127">reisepass</span></span>  <br/> <span data-ttu-id="09c2e-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="09c2e-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="09c2e-129">Belgio</span><span class="sxs-lookup"><span data-stu-id="09c2e-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-130">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-130">Format</span></span>

<span data-ttu-id="09c2e-131">Due lettere seguite da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-132">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-132">Pattern</span></span>

<span data-ttu-id="09c2e-133">Due lettere e seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09c2e-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-134">Checksum</span></span>

<span data-ttu-id="09c2e-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="09c2e-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-136">Definition</span></span>

<span data-ttu-id="09c2e-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-138">L'espressione `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-139">Viene trovata una `Keywords_belgium_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-140">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-140">Keywords</span></span>

<span data-ttu-id="09c2e-141">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-141">| |</span></span>
|<span data-ttu-id="09c2e-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-143">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-143">passport number</span></span>  <br/> <span data-ttu-id="09c2e-144">numero di passaporto belga</span><span class="sxs-lookup"><span data-stu-id="09c2e-144">belgian passport number</span></span>  <br/> <span data-ttu-id="09c2e-145">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-145">passport no</span></span>  <br/> <span data-ttu-id="09c2e-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="09c2e-146">paspoort</span></span>  <br/> <span data-ttu-id="09c2e-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="09c2e-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="09c2e-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="09c2e-148">reisepass kein</span></span>  <br/> <span data-ttu-id="09c2e-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="09c2e-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="09c2e-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="09c2e-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-151">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-151">Format</span></span>

<span data-ttu-id="09c2e-152">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-153">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-153">Pattern</span></span>

 <span data-ttu-id="09c2e-154">9 cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="09c2e-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-155">Checksum</span></span>

<span data-ttu-id="09c2e-156">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-157">Definition</span></span>

<span data-ttu-id="09c2e-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-159">L'espressione `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-160">Viene trovata una `Keywords_bulgaria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-161">Keywords</span></span>

<span data-ttu-id="09c2e-162">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-162">| |</span></span>
|<span data-ttu-id="09c2e-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-164">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-164">passport number</span></span>  <br/> <span data-ttu-id="09c2e-165">numero di passaporto bulgaro</span><span class="sxs-lookup"><span data-stu-id="09c2e-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="09c2e-166">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-166">passport no</span></span>  <br/> <span data-ttu-id="09c2e-167">Номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="09c2e-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="09c2e-168">Croazia</span><span class="sxs-lookup"><span data-stu-id="09c2e-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-169">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-169">Format</span></span>

<span data-ttu-id="09c2e-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-171">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-171">Pattern</span></span>

 <span data-ttu-id="09c2e-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="09c2e-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-173">Checksum</span></span>

<span data-ttu-id="09c2e-174">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-175">Definition</span></span>

<span data-ttu-id="09c2e-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-177">L'espressione `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-178">Viene trovata una `Keywords_croatia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-179">Keywords</span></span>

<span data-ttu-id="09c2e-180">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-180">| |</span></span>
|<span data-ttu-id="09c2e-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-182">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-182">passport number</span></span>  <br/> <span data-ttu-id="09c2e-183">numero di passaporto croato</span><span class="sxs-lookup"><span data-stu-id="09c2e-183">croatian passport number</span></span>  <br/> <span data-ttu-id="09c2e-184">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-184">passport no</span></span>  <br/> <span data-ttu-id="09c2e-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="09c2e-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="09c2e-186">Cipro</span><span class="sxs-lookup"><span data-stu-id="09c2e-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-187">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-187">Format</span></span>

<span data-ttu-id="09c2e-188">Una lettera seguita da 6-8 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-189">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-189">Pattern</span></span>

<span data-ttu-id="09c2e-190">Una lettera seguita da sei a otto cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09c2e-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-191">Checksum</span></span>

<span data-ttu-id="09c2e-192">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-193">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-193">Definition</span></span>

<span data-ttu-id="09c2e-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-195">L'espressione `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-196">Viene trovata una `Keywords_cyprus_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-197">Keywords</span></span>

<span data-ttu-id="09c2e-198">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-198">| |</span></span>
|<span data-ttu-id="09c2e-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-200">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-200">passport number</span></span>  <br/> <span data-ttu-id="09c2e-201">numero di passaporto di Cipro</span><span class="sxs-lookup"><span data-stu-id="09c2e-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="09c2e-202">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-202">passport no</span></span>  <br/> <span data-ttu-id="09c2e-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="09c2e-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="09c2e-204">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="09c2e-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-205">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-205">Format</span></span>

<span data-ttu-id="09c2e-206">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-207">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-207">Pattern</span></span>

<span data-ttu-id="09c2e-208">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09c2e-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-209">Checksum</span></span>

<span data-ttu-id="09c2e-210">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-211">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-211">Definition</span></span>

<span data-ttu-id="09c2e-212">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-213">L'espressione `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-214">Viene trovata una `Keywords_czech_republic_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-215">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-215">Keywords</span></span>

<span data-ttu-id="09c2e-216">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-216">| |</span></span>
|<span data-ttu-id="09c2e-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-218">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-218">passport number</span></span>  <br/> <span data-ttu-id="09c2e-219">numero di passaporto ceco</span><span class="sxs-lookup"><span data-stu-id="09c2e-219">czech passport number</span></span>  <br/> <span data-ttu-id="09c2e-220">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-220">passport no</span></span>  <br/> <span data-ttu-id="09c2e-221">Cestovní pas</span><span class="sxs-lookup"><span data-stu-id="09c2e-221">cestovní pas</span></span>  <br/> <span data-ttu-id="09c2e-222">pas</span><span class="sxs-lookup"><span data-stu-id="09c2e-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="09c2e-223">Danimarca</span><span class="sxs-lookup"><span data-stu-id="09c2e-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-224">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-224">Format</span></span>

<span data-ttu-id="09c2e-225">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-226">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-226">Pattern</span></span>

 <span data-ttu-id="09c2e-227">9 cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="09c2e-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-228">Checksum</span></span>

<span data-ttu-id="09c2e-229">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-230">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-230">Definition</span></span>

<span data-ttu-id="09c2e-231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-232">L'espressione `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-233">Viene trovata una `Keywords_denmark_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-234">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-234">Keywords</span></span>

<span data-ttu-id="09c2e-235">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-235">| |</span></span>
|<span data-ttu-id="09c2e-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-237">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-237">passport number</span></span>  <br/> <span data-ttu-id="09c2e-238">numero di passaporto danese</span><span class="sxs-lookup"><span data-stu-id="09c2e-238">danish passport number</span></span>  <br/> <span data-ttu-id="09c2e-239">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-239">passport no</span></span>  <br/> <span data-ttu-id="09c2e-240">pas</span><span class="sxs-lookup"><span data-stu-id="09c2e-240">pas</span></span>  <br/> <span data-ttu-id="09c2e-241">Pasnummer</span><span class="sxs-lookup"><span data-stu-id="09c2e-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="09c2e-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="09c2e-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-243">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-243">Format</span></span>

<span data-ttu-id="09c2e-244">Una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-245">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-245">Pattern</span></span>

<span data-ttu-id="09c2e-246">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09c2e-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-247">Checksum</span></span>

<span data-ttu-id="09c2e-248">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-249">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-249">Definition</span></span>

<span data-ttu-id="09c2e-250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-251">L'espressione `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-252">Viene trovata una `Keywords_estonia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-253">Keywords</span></span>

<span data-ttu-id="09c2e-254">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-254">| |</span></span>
|<span data-ttu-id="09c2e-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-256">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-256">passport number</span></span>  <br/> <span data-ttu-id="09c2e-257">numero di passaporto estone</span><span class="sxs-lookup"><span data-stu-id="09c2e-257">estonian passport number</span></span>  <br/> <span data-ttu-id="09c2e-258">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-258">passport no</span></span>  <br/> <span data-ttu-id="09c2e-259">passaggio kodaniku Eesti</span><span class="sxs-lookup"><span data-stu-id="09c2e-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="09c2e-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="09c2e-260">Finland</span></span>

<span data-ttu-id="09c2e-261">Per informazioni dettagliate, vedere la sezione "Finlandia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="09c2e-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="09c2e-262">Francia</span><span class="sxs-lookup"><span data-stu-id="09c2e-262">France</span></span>

<span data-ttu-id="09c2e-263">Per informazioni dettagliate, vedere la sezione "Francia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="09c2e-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="09c2e-264">Germania</span><span class="sxs-lookup"><span data-stu-id="09c2e-264">Germany</span></span>

<span data-ttu-id="09c2e-265">Per informazioni dettagliate, vedere la sezione "numero di passaporto tedesco" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="09c2e-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="09c2e-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="09c2e-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-267">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-267">Format</span></span>

<span data-ttu-id="09c2e-268">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-269">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-269">Pattern</span></span>

<span data-ttu-id="09c2e-270">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09c2e-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-271">Checksum</span></span>

<span data-ttu-id="09c2e-272">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-273">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-273">Definition</span></span>

<span data-ttu-id="09c2e-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-275">L'espressione `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-276">Viene trovata una `Keywords_greece_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-277">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-277">Keywords</span></span>

<span data-ttu-id="09c2e-278">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-278">| |</span></span>
|<span data-ttu-id="09c2e-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-280">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-280">passport number</span></span>  <br/> <span data-ttu-id="09c2e-281">numero di passaporto greco</span><span class="sxs-lookup"><span data-stu-id="09c2e-281">greek passport number</span></span>  <br/> <span data-ttu-id="09c2e-282">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-282">passport no</span></span>  <br/> <span data-ttu-id="09c2e-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="09c2e-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="09c2e-284">Ungheria</span><span class="sxs-lookup"><span data-stu-id="09c2e-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-285">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-285">Format</span></span>

<span data-ttu-id="09c2e-286">Due lettere seguite da sei o sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-287">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-287">Pattern</span></span>

<span data-ttu-id="09c2e-288">Due lettere seguite da sei o sette cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09c2e-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-289">Checksum</span></span>

<span data-ttu-id="09c2e-290">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-291">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-291">Definition</span></span>

<span data-ttu-id="09c2e-292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-293">L'espressione `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-294">Viene trovata una `Keywords_hungary_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-295">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-295">Keywords</span></span>

<span data-ttu-id="09c2e-296">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-296">| |</span></span>
|<span data-ttu-id="09c2e-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-298">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-298">passport number</span></span>  <br/> <span data-ttu-id="09c2e-299">numero di passaporto ungherese</span><span class="sxs-lookup"><span data-stu-id="09c2e-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="09c2e-300">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-300">passport no</span></span>  <br/> <span data-ttu-id="09c2e-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="09c2e-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="09c2e-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="09c2e-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-303">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-303">Format</span></span>

<span data-ttu-id="09c2e-304">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-305">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-305">Pattern</span></span>

<span data-ttu-id="09c2e-306">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="09c2e-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="09c2e-307">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="09c2e-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="09c2e-308">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09c2e-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-309">Checksum</span></span>

<span data-ttu-id="09c2e-310">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-311">Definition</span></span>

<span data-ttu-id="09c2e-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-313">L'espressione `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-314">Viene trovata una `Keywords_ireland_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-315">Keywords</span></span>

<span data-ttu-id="09c2e-316">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-316">| |</span></span>
|<span data-ttu-id="09c2e-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-318">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-318">passport number</span></span>  <br/> <span data-ttu-id="09c2e-319">numero di passaporto irlandese</span><span class="sxs-lookup"><span data-stu-id="09c2e-319">irish passport number</span></span>  <br/> <span data-ttu-id="09c2e-320">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-320">passport no</span></span>  <br/> <span data-ttu-id="09c2e-321">pas</span><span class="sxs-lookup"><span data-stu-id="09c2e-321">pas</span></span>  <br/> <span data-ttu-id="09c2e-322">passaporto</span><span class="sxs-lookup"><span data-stu-id="09c2e-322">passport</span></span>  <br/> <span data-ttu-id="09c2e-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="09c2e-323">passeport</span></span>  <br/> <span data-ttu-id="09c2e-324">numero Passeport</span><span class="sxs-lookup"><span data-stu-id="09c2e-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="09c2e-325">Italia</span><span class="sxs-lookup"><span data-stu-id="09c2e-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-326">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-326">Format</span></span>

<span data-ttu-id="09c2e-327">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-328">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-328">Pattern</span></span>

<span data-ttu-id="09c2e-329">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="09c2e-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="09c2e-330">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="09c2e-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="09c2e-331">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09c2e-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-332">Checksum</span></span>

<span data-ttu-id="09c2e-333">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="09c2e-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-334">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-334">Definition</span></span>

<span data-ttu-id="09c2e-335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-336">L'espressione `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-337">Viene trovata una `Keywords_italy_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-338">Keywords</span></span>

<span data-ttu-id="09c2e-339">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-339">| |</span></span>
|<span data-ttu-id="09c2e-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-341">numero di passaporto italiano</span><span class="sxs-lookup"><span data-stu-id="09c2e-341">italian passport number</span></span>  <br/> <span data-ttu-id="09c2e-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="09c2e-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="09c2e-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="09c2e-343">passaporto</span></span>  <br/> <span data-ttu-id="09c2e-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="09c2e-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="09c2e-345">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-345">passport number</span></span>  <br/> <span data-ttu-id="09c2e-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="09c2e-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="09c2e-347">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="09c2e-347">passaporto numero</span></span>  <br/> <span data-ttu-id="09c2e-348">numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="09c2e-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="09c2e-349">numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="09c2e-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="09c2e-350">Lettonia</span><span class="sxs-lookup"><span data-stu-id="09c2e-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-351">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-351">Format</span></span>

<span data-ttu-id="09c2e-352">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-353">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-353">Pattern</span></span>

<span data-ttu-id="09c2e-354">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="09c2e-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="09c2e-355">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="09c2e-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="09c2e-356">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09c2e-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-357">Checksum</span></span>

<span data-ttu-id="09c2e-358">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-359">Definition</span></span>

<span data-ttu-id="09c2e-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-361">L'espressione `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-362">Viene trovata una `Keywords_latvia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-363">Keywords</span></span>

<span data-ttu-id="09c2e-364">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-364">| |</span></span>
|<span data-ttu-id="09c2e-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-366">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-366">passport number</span></span>  <br/> <span data-ttu-id="09c2e-367">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="09c2e-367">latvian passport number</span></span>  <br/> <span data-ttu-id="09c2e-368">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-368">passport no</span></span>  <br/> <span data-ttu-id="09c2e-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="09c2e-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="09c2e-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="09c2e-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-371">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-371">Format</span></span>

<span data-ttu-id="09c2e-372">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-373">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-373">Pattern</span></span>

<span data-ttu-id="09c2e-374">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="09c2e-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09c2e-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-375">Checksum</span></span>

<span data-ttu-id="09c2e-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="09c2e-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-377">Definition</span></span>

<span data-ttu-id="09c2e-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-379">L'espressione `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-380">Viene trovata una `Keywords_lithuania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-381">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-381">Keywords</span></span>

<span data-ttu-id="09c2e-382">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-382">| |</span></span>
|<span data-ttu-id="09c2e-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-384">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-384">passport number</span></span>  <br/> <span data-ttu-id="09c2e-385">numero di passaporto di lithunian</span><span class="sxs-lookup"><span data-stu-id="09c2e-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="09c2e-386">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-386">passport no</span></span>  <br/> <span data-ttu-id="09c2e-387">numero di Paso</span><span class="sxs-lookup"><span data-stu-id="09c2e-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="09c2e-388">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="09c2e-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-389">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-389">Format</span></span>

<span data-ttu-id="09c2e-390">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-391">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-391">Pattern</span></span>

<span data-ttu-id="09c2e-392">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="09c2e-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09c2e-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-393">Checksum</span></span>

<span data-ttu-id="09c2e-394">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-395">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-395">Definition</span></span>

<span data-ttu-id="09c2e-396">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-397">L'espressione `Regex_nation_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-398">Viene trovata una `Keywords_nation_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-399">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-399">Keywords</span></span>

<span data-ttu-id="09c2e-400">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-400">| |</span></span>
|<span data-ttu-id="09c2e-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-402">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-402">passport number</span></span>  <br/> <span data-ttu-id="09c2e-403">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="09c2e-403">latvian passport number</span></span>  <br/> <span data-ttu-id="09c2e-404">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-404">passport no</span></span>  <br/> <span data-ttu-id="09c2e-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="09c2e-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="09c2e-406">Malta</span><span class="sxs-lookup"><span data-stu-id="09c2e-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-407">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-407">Format</span></span>

<span data-ttu-id="09c2e-408">Sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-409">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-409">Pattern</span></span>

 <span data-ttu-id="09c2e-410">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="09c2e-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-411">Checksum</span></span>

<span data-ttu-id="09c2e-412">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-413">Definition</span></span>

<span data-ttu-id="09c2e-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-415">L'espressione `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-416">Viene trovata una `Keywords_malta_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-417">Keywords</span></span>

<span data-ttu-id="09c2e-418">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-418">| |</span></span>
|<span data-ttu-id="09c2e-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-420">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-420">passport number</span></span>  <br/> <span data-ttu-id="09c2e-421">numero di passaporto maltese</span><span class="sxs-lookup"><span data-stu-id="09c2e-421">maltese passport number</span></span>  <br/> <span data-ttu-id="09c2e-422">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-422">passport no</span></span>  <br/> <span data-ttu-id="09c2e-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="09c2e-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="09c2e-424">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="09c2e-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-425">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-425">Format</span></span>

<span data-ttu-id="09c2e-426">Nove lettere o cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-427">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-427">Pattern</span></span>

<span data-ttu-id="09c2e-428">Nove lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09c2e-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-429">Checksum</span></span>

<span data-ttu-id="09c2e-430">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="09c2e-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-431">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-431">Definition</span></span>

<span data-ttu-id="09c2e-432">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-433">L'espressione `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-434">Viene trovata una `Keywords_netherlands_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-435">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-435">Keywords</span></span>

<span data-ttu-id="09c2e-436">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-436">| |</span></span>
|<span data-ttu-id="09c2e-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-438">numero di passaporto olandese</span><span class="sxs-lookup"><span data-stu-id="09c2e-438">dutch passport number</span></span>  <br/> <span data-ttu-id="09c2e-439">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-439">passport number</span></span>  <br/> <span data-ttu-id="09c2e-440">numero di passaporto per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="09c2e-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="09c2e-441">Nederlanden PASPOORT Nummer</span><span class="sxs-lookup"><span data-stu-id="09c2e-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="09c2e-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="09c2e-442">paspoort</span></span>  <br/> <span data-ttu-id="09c2e-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="09c2e-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="09c2e-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="09c2e-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="09c2e-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="09c2e-445">Poland</span></span>

<span data-ttu-id="09c2e-446">Per informazioni dettagliate, vedere la sezione "Poland Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="09c2e-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="09c2e-447">Portogallo</span><span class="sxs-lookup"><span data-stu-id="09c2e-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-448">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-448">Format</span></span>

<span data-ttu-id="09c2e-449">Una lettera seguita da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-450">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-450">Pattern</span></span>

<span data-ttu-id="09c2e-451">Una lettera seguita da sei cifre:</span><span class="sxs-lookup"><span data-stu-id="09c2e-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="09c2e-452">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="09c2e-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="09c2e-453">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09c2e-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-454">Checksum</span></span>

<span data-ttu-id="09c2e-455">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-456">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-456">Definition</span></span>

<span data-ttu-id="09c2e-457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-458">L'espressione `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-459">Viene trovata una `Keywords_portugal_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-460">Keywords</span></span>

<span data-ttu-id="09c2e-461">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-461">| |</span></span>
|<span data-ttu-id="09c2e-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-463">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-463">passport number</span></span>  <br/> <span data-ttu-id="09c2e-464">numero di passaporto portoghese</span><span class="sxs-lookup"><span data-stu-id="09c2e-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="09c2e-465">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-465">passport no</span></span>  <br/> <span data-ttu-id="09c2e-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="09c2e-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="09c2e-467">Romania</span><span class="sxs-lookup"><span data-stu-id="09c2e-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-468">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-468">Format</span></span>

<span data-ttu-id="09c2e-469">Otto o nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-470">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-470">Pattern</span></span>

<span data-ttu-id="09c2e-471">Otto o nove cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09c2e-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-472">Checksum</span></span>

<span data-ttu-id="09c2e-473">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-474">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-474">Definition</span></span>

<span data-ttu-id="09c2e-475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-476">L'espressione `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-477">Viene trovata una `Keywords_romania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-478">Keywords</span></span>

<span data-ttu-id="09c2e-479">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-479">| |</span></span>
|<span data-ttu-id="09c2e-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-481">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-481">passport number</span></span>  <br/> <span data-ttu-id="09c2e-482">numero di passaporto rumeno</span><span class="sxs-lookup"><span data-stu-id="09c2e-482">romanian passport number</span></span>  <br/> <span data-ttu-id="09c2e-483">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-483">passport no</span></span>  <br/> <span data-ttu-id="09c2e-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="09c2e-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="09c2e-485">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="09c2e-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-486">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-486">Format</span></span>

<span data-ttu-id="09c2e-487">Una cifra o una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-488">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-488">Pattern</span></span>

<span data-ttu-id="09c2e-489">Una cifra o una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="09c2e-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-490">Checksum</span></span>

<span data-ttu-id="09c2e-491">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-492">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-492">Definition</span></span>

<span data-ttu-id="09c2e-493">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-494">L'espressione `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-495">Viene trovata una `Keywords_slovakia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-496">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-496">Keywords</span></span>

<span data-ttu-id="09c2e-497">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-497">| |</span></span>
|<span data-ttu-id="09c2e-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-499">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-499">passport number</span></span>  <br/> <span data-ttu-id="09c2e-500">numero di passaporto slovacco</span><span class="sxs-lookup"><span data-stu-id="09c2e-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="09c2e-501">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-501">passport no</span></span>  <br/> <span data-ttu-id="09c2e-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="09c2e-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="09c2e-503">Slovenia</span><span class="sxs-lookup"><span data-stu-id="09c2e-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-504">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-504">Format</span></span>

<span data-ttu-id="09c2e-505">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-506">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-506">Pattern</span></span>

<span data-ttu-id="09c2e-507">Due lettere seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="09c2e-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="09c2e-508">La lettera "P"</span><span class="sxs-lookup"><span data-stu-id="09c2e-508">The letter "P"</span></span>
    
- <span data-ttu-id="09c2e-509">Una lettera maiuscola</span><span class="sxs-lookup"><span data-stu-id="09c2e-509">One uppercase letter</span></span>
    
- <span data-ttu-id="09c2e-510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09c2e-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-511">Checksum</span></span>

<span data-ttu-id="09c2e-512">No</span><span class="sxs-lookup"><span data-stu-id="09c2e-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-513">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-513">Definition</span></span>

<span data-ttu-id="09c2e-514">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-515">L'espressione `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-516">Viene trovata una `Keywords_slovenia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-517">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-517">Keywords</span></span>

<span data-ttu-id="09c2e-518">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-518">| |</span></span>
|<span data-ttu-id="09c2e-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-520">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-520">passport number</span></span>  <br/> <span data-ttu-id="09c2e-521">numero di passaporto sloveno</span><span class="sxs-lookup"><span data-stu-id="09c2e-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="09c2e-522">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-522">passport no</span></span>  <br/> <span data-ttu-id="09c2e-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="09c2e-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="09c2e-524">Spagna</span><span class="sxs-lookup"><span data-stu-id="09c2e-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="09c2e-525">Formato</span><span class="sxs-lookup"><span data-stu-id="09c2e-525">Format</span></span>

<span data-ttu-id="09c2e-526">Combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="09c2e-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="09c2e-527">Modello</span><span class="sxs-lookup"><span data-stu-id="09c2e-527">Pattern</span></span>

<span data-ttu-id="09c2e-528">Combinazione di lettere e numeri di otto o nove caratteri:</span><span class="sxs-lookup"><span data-stu-id="09c2e-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="09c2e-529">Due cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="09c2e-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="09c2e-530">Una cifra o una lettera (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="09c2e-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="09c2e-531">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="09c2e-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="09c2e-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="09c2e-532">Checksum</span></span>

<span data-ttu-id="09c2e-533">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="09c2e-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="09c2e-534">Definizione</span><span class="sxs-lookup"><span data-stu-id="09c2e-534">Definition</span></span>

<span data-ttu-id="09c2e-535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="09c2e-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="09c2e-536">L'espressione `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="09c2e-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="09c2e-537">Viene trovata una `Keywords_spain_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="09c2e-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="09c2e-538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="09c2e-538">Keywords</span></span>

<span data-ttu-id="09c2e-539">| |</span><span class="sxs-lookup"><span data-stu-id="09c2e-539">| |</span></span>
|<span data-ttu-id="09c2e-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="09c2e-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="09c2e-541">passaporto</span><span class="sxs-lookup"><span data-stu-id="09c2e-541">passport</span></span>  <br/> <span data-ttu-id="09c2e-542">passaporto della Spagna</span><span class="sxs-lookup"><span data-stu-id="09c2e-542">spain passport</span></span>  <br/> <span data-ttu-id="09c2e-543">libro del passaporto</span><span class="sxs-lookup"><span data-stu-id="09c2e-543">passport book</span></span>  <br/> <span data-ttu-id="09c2e-544">passport number</span><span class="sxs-lookup"><span data-stu-id="09c2e-544">passport number</span></span>  <br/> <span data-ttu-id="09c2e-545">Passport No</span><span class="sxs-lookup"><span data-stu-id="09c2e-545">passport no</span></span>  <br/> <span data-ttu-id="09c2e-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="09c2e-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="09c2e-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="09c2e-547">número pasaporte</span></span>  <br/> <span data-ttu-id="09c2e-548">pasaporte España</span><span class="sxs-lookup"><span data-stu-id="09c2e-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="09c2e-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="09c2e-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="09c2e-550">Svezia</span><span class="sxs-lookup"><span data-stu-id="09c2e-550">Sweden</span></span>

<span data-ttu-id="09c2e-551">Per informazioni dettagliate, vedere la sezione "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="09c2e-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="09c2e-552">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="09c2e-552">UK</span></span>

<span data-ttu-id="09c2e-553">Per informazioni dettagliate, vedere la sezione "Stati Uniti/Regno Unito</span><span class="sxs-lookup"><span data-stu-id="09c2e-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="09c2e-554">Numero di passaporto "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="09c2e-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="09c2e-555">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09c2e-555">See also</span></span>

[<span data-ttu-id="09c2e-556">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="09c2e-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

