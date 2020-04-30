---
title: Numero della patente di guida dell'Unione europea
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 2e75a8724dc91ef2d895c977fdd5fcc21e7a1da4
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938830"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="91f2c-104">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="91f2c-104">EU Driver's License Number</span></span>

<span data-ttu-id="91f2c-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="91f2c-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="91f2c-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="91f2c-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="91f2c-107">Austria</span><span class="sxs-lookup"><span data-stu-id="91f2c-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-108">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-108">Format</span></span>

<span data-ttu-id="91f2c-109">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="91f2c-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-110">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-110">Pattern</span></span>

<span data-ttu-id="91f2c-111">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="91f2c-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-112">Checksum</span></span>

<span data-ttu-id="91f2c-113">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-114">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-114">Definition</span></span>

<span data-ttu-id="91f2c-115">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-116">L'espressione `Regex_austria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-117">Viene trovata una `Keywords_austria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="91f2c-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-118">Keywords</span></span>

<span data-ttu-id="91f2c-119">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-119">| |</span></span>
|<span data-ttu-id="91f2c-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-121">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-121">dl#</span></span>  <br/> <span data-ttu-id="91f2c-122">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-122">driver license</span></span>  <br/> <span data-ttu-id="91f2c-123">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-123">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-124">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-124">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-125">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-125">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-126">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-127">driver's licence</span></span>  <br/> <span data-ttu-id="91f2c-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-128">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-129">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-129">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-130">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="91f2c-131">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-131">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-132">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="91f2c-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="91f2c-134">fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="91f2c-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="91f2c-135">Belgio</span><span class="sxs-lookup"><span data-stu-id="91f2c-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-136">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-136">Format</span></span>

<span data-ttu-id="91f2c-137">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="91f2c-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-138">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-138">Pattern</span></span>

<span data-ttu-id="91f2c-139">10 cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="91f2c-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-140">Checksum</span></span>

<span data-ttu-id="91f2c-141">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-142">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-142">Definition</span></span>

<span data-ttu-id="91f2c-143">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-144">L'espressione `Regex_belgium_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-145">Viene trovata una `Keywords_belgium_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="91f2c-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-146">Keywords</span></span>

<span data-ttu-id="91f2c-147">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-147">| |</span></span>
|<span data-ttu-id="91f2c-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-149">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-149">dl#</span></span>  <br/> <span data-ttu-id="91f2c-150">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-150">driver license</span></span>  <br/> <span data-ttu-id="91f2c-151">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-151">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-152">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-152">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-153">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-153">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-154">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-155">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-156">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-157">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-157">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-158">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-158">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-159">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="91f2c-160">rijbewijs</span></span>  <br/> <span data-ttu-id="91f2c-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="91f2c-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="91f2c-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="91f2c-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="91f2c-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="91f2c-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="91f2c-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="91f2c-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="91f2c-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="91f2c-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="91f2c-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="91f2c-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="91f2c-167">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="91f2c-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="91f2c-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="91f2c-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-169">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-169">Format</span></span>

<span data-ttu-id="91f2c-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="91f2c-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-171">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-171">Pattern</span></span>

<span data-ttu-id="91f2c-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="91f2c-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-173">Checksum</span></span>

<span data-ttu-id="91f2c-174">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-175">Definition</span></span>

<span data-ttu-id="91f2c-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-177">L'espressione `Regex_bulgaria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-178">Viene trovata una `Keywords_bulgaria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="91f2c-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-179">Keywords</span></span>

<span data-ttu-id="91f2c-180">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-180">| |</span></span>
|<span data-ttu-id="91f2c-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-182">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-182">dl#</span></span>  <br/> <span data-ttu-id="91f2c-183">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-183">driver license</span></span>  <br/> <span data-ttu-id="91f2c-184">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-184">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-185">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-185">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-186">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-186">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-187">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-188">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-189">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-190">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-190">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-191">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-191">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-192">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-192">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-193">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="91f2c-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="91f2c-195">свидетелство за управление на моторно превозно d'средство</span><span class="sxs-lookup"><span data-stu-id="91f2c-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="91f2c-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="91f2c-196">сумпс</span></span>  <br/> <span data-ttu-id="91f2c-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="91f2c-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="91f2c-198">Croazia</span><span class="sxs-lookup"><span data-stu-id="91f2c-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-199">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-199">Format</span></span>

<span data-ttu-id="91f2c-200">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="91f2c-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-201">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-201">Pattern</span></span>

<span data-ttu-id="91f2c-202">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="91f2c-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-203">Checksum</span></span>

<span data-ttu-id="91f2c-204">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-205">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-205">Definition</span></span>

<span data-ttu-id="91f2c-206">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-207">L'espressione `Regex_croatia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-208">Viene trovata una `Keywords_croatia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="91f2c-209">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-209">Keywords</span></span>

<span data-ttu-id="91f2c-210">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-210">| |</span></span>
|<span data-ttu-id="91f2c-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-212">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-212">dl#</span></span>  <br/> <span data-ttu-id="91f2c-213">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-213">driver license</span></span>  <br/> <span data-ttu-id="91f2c-214">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-214">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-215">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-215">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-216">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-216">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-217">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-218">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-219">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-220">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-220">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-221">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-221">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-222">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-222">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-223">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="91f2c-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="91f2c-225">Cipro</span><span class="sxs-lookup"><span data-stu-id="91f2c-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-226">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-226">Format</span></span>

<span data-ttu-id="91f2c-227">12 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="91f2c-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-228">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-228">Pattern</span></span>

<span data-ttu-id="91f2c-229">12 cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="91f2c-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-230">Checksum</span></span>

<span data-ttu-id="91f2c-231">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-232">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-232">Definition</span></span>

<span data-ttu-id="91f2c-233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-234">L'espressione `Regex_cyprus_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-235">Viene trovata una `Keywords_cyprus_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-236">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-236">Keywords</span></span>

<span data-ttu-id="91f2c-237">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-237">| |</span></span>
|<span data-ttu-id="91f2c-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-239">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-239">dl#</span></span>  <br/> <span data-ttu-id="91f2c-240">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-240">driver license</span></span>  <br/> <span data-ttu-id="91f2c-241">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-241">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-242">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-242">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-243">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-243">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-244">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-245">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-246">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-246">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-247">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-247">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-248">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-248">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-249">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="91f2c-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="91f2c-251">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="91f2c-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-252">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-252">Format</span></span>

<span data-ttu-id="91f2c-253">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-254">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-254">Pattern</span></span>

<span data-ttu-id="91f2c-255">Otto lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="91f2c-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="91f2c-256">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="91f2c-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="91f2c-257">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="91f2c-257">A space (optional)</span></span>
    
- <span data-ttu-id="91f2c-258">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="91f2c-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-259">Checksum</span></span>

<span data-ttu-id="91f2c-260">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-261">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-261">Definition</span></span>

<span data-ttu-id="91f2c-262">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-263">L'espressione `Regex_czech_republic_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-264">Viene trovata una `Keywords_czech_republic_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="91f2c-265">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-265">Keywords</span></span>

<span data-ttu-id="91f2c-266">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-266">| |</span></span>
|<span data-ttu-id="91f2c-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-268">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-268">dl#</span></span>  <br/> <span data-ttu-id="91f2c-269">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-269">driver license</span></span>  <br/> <span data-ttu-id="91f2c-270">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-270">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-271">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-271">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-272">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-272">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-273">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-274">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-275">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-276">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-276">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-277">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-277">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-278">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-278">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-279">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-279">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-280">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="91f2c-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="91f2c-282">Danimarca</span><span class="sxs-lookup"><span data-stu-id="91f2c-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-283">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-283">Format</span></span>

<span data-ttu-id="91f2c-284">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="91f2c-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-285">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-285">Pattern</span></span>

<span data-ttu-id="91f2c-286">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="91f2c-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-287">Checksum</span></span>

<span data-ttu-id="91f2c-288">Sì</span><span class="sxs-lookup"><span data-stu-id="91f2c-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-289">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-289">Definition</span></span>

<span data-ttu-id="91f2c-290">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-291">L'espressione `Regex_denmark_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-292">Viene trovata una `Keywords_denmark_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="91f2c-293">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-293">Keywords</span></span>

<span data-ttu-id="91f2c-294">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-294">| |</span></span>
|<span data-ttu-id="91f2c-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-296">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-296">dl#</span></span>  <br/> <span data-ttu-id="91f2c-297">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-297">driver license</span></span>  <br/> <span data-ttu-id="91f2c-298">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-298">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-299">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-299">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-300">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-300">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-301">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-302">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-303">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-304">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-304">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-305">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-305">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-306">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-306">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-307">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="91f2c-308">kørekort</span></span>  <br/> <span data-ttu-id="91f2c-309">Kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="91f2c-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="91f2c-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="91f2c-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-311">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-311">Format</span></span>

<span data-ttu-id="91f2c-312">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-313">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-313">Pattern</span></span>

<span data-ttu-id="91f2c-314">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="91f2c-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="91f2c-315">Lettere "ET" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="91f2c-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="91f2c-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="91f2c-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-317">Checksum</span></span>

<span data-ttu-id="91f2c-318">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-319">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-319">Definition</span></span>

<span data-ttu-id="91f2c-320">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-321">L'espressione `Regex_estonia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-322">Viene trovata una `Keywords_estonia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-323">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-323">Keywords</span></span>

<span data-ttu-id="91f2c-324">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-324">| |</span></span>
|<span data-ttu-id="91f2c-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-326">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-326">dl#</span></span>  <br/> <span data-ttu-id="91f2c-327">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-327">driver license</span></span>  <br/> <span data-ttu-id="91f2c-328">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-328">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-329">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-329">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-330">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-330">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-331">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-331">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-332">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-333">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-334">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-335">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-335">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-336">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-336">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-337">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="91f2c-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="91f2c-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="91f2c-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-340">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-340">Format</span></span>

<span data-ttu-id="91f2c-341">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="91f2c-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-342">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-342">Pattern</span></span>

<span data-ttu-id="91f2c-343">10 cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="91f2c-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="91f2c-344">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-344">Six digits</span></span> 
    
- <span data-ttu-id="91f2c-345">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="91f2c-345">A hyphen</span></span>
    
-  <span data-ttu-id="91f2c-346">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="91f2c-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-347">Checksum</span></span>

<span data-ttu-id="91f2c-348">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-349">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-349">Definition</span></span>

<span data-ttu-id="91f2c-350">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-351">L'espressione `Regex_finland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-352">Viene trovata una `Keywords_finland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-353">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-353">Keywords</span></span>

<span data-ttu-id="91f2c-354">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-354">| |</span></span>
|<span data-ttu-id="91f2c-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-356">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-356">dl#</span></span>  <br/> <span data-ttu-id="91f2c-357">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-357">driver license</span></span>  <br/> <span data-ttu-id="91f2c-358">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-358">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-359">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-359">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-360">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-360">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-361">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-362">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-363">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-364">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-364">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-365">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-365">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-366">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-366">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-367">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="91f2c-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="91f2c-369">Francia</span><span class="sxs-lookup"><span data-stu-id="91f2c-369">France</span></span>

<span data-ttu-id="91f2c-370">Per informazioni dettagliate, vedere la sezione "numero della patente di Francia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="91f2c-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="91f2c-371">Germania</span><span class="sxs-lookup"><span data-stu-id="91f2c-371">Germany</span></span>

<span data-ttu-id="91f2c-372">Per informazioni dettagliate, vedere la sezione "numero di patente di guida tedesco" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="91f2c-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="91f2c-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="91f2c-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-374">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-374">Format</span></span>

<span data-ttu-id="91f2c-375">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="91f2c-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-376">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-376">Pattern</span></span>

 <span data-ttu-id="91f2c-377">9 cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="91f2c-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-378">Checksum</span></span>

<span data-ttu-id="91f2c-379">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-380">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-380">Definition</span></span>

<span data-ttu-id="91f2c-381">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-382">L'espressione `Regex_greece_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-383">Viene trovata una `Keywords_greece_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-384">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-384">Keywords</span></span>

<span data-ttu-id="91f2c-385">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-385">| |</span></span>
|<span data-ttu-id="91f2c-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-387">dlL#</span></span>  <br/> <span data-ttu-id="91f2c-388">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-388">driver license</span></span>  <br/> <span data-ttu-id="91f2c-389">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-389">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-390">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-390">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-391">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-391">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-392">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-393">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-394">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-395">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-395">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-396">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-396">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-397">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-397">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-398">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="91f2c-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="91f2c-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="91f2c-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="91f2c-401">Ungheria</span><span class="sxs-lookup"><span data-stu-id="91f2c-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-402">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-402">Format</span></span>

<span data-ttu-id="91f2c-403">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-404">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-404">Pattern</span></span>

<span data-ttu-id="91f2c-405">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="91f2c-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="91f2c-406">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="91f2c-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="91f2c-407">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="91f2c-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-408">Checksum</span></span>

<span data-ttu-id="91f2c-409">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-410">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-410">Definition</span></span>

<span data-ttu-id="91f2c-411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-412">L'espressione `Regex_hungary_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-413">Viene trovata una `Keywords_hungary_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-414">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-414">Keywords</span></span>

<span data-ttu-id="91f2c-415">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-415">| |</span></span>
|<span data-ttu-id="91f2c-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-417">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-417">dl#</span></span>  <br/> <span data-ttu-id="91f2c-418">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-418">driver license</span></span>  <br/> <span data-ttu-id="91f2c-419">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-419">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-420">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-420">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-421">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-421">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-422">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-423">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-424">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-425">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-425">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-426">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-426">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-427">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-427">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-428">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="91f2c-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="91f2c-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="91f2c-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-431">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-431">Format</span></span>

<span data-ttu-id="91f2c-432">Sei cifre seguite da quattro lettere</span><span class="sxs-lookup"><span data-stu-id="91f2c-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-433">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-433">Pattern</span></span>

<span data-ttu-id="91f2c-434">Sei cifre e quattro lettere:</span><span class="sxs-lookup"><span data-stu-id="91f2c-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="91f2c-435">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-435">Six digits</span></span>
    
- <span data-ttu-id="91f2c-436">Quattro lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="91f2c-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="91f2c-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-437">Checksum</span></span>

<span data-ttu-id="91f2c-438">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-439">Definition</span></span>

<span data-ttu-id="91f2c-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-441">L'espressione `Regex_ireland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-442">Viene trovata una `Keywords_ireland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-443">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-443">Keywords</span></span>

<span data-ttu-id="91f2c-444">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-444">| |</span></span>
|<span data-ttu-id="91f2c-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-446">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-446">dl#</span></span>  <br/> <span data-ttu-id="91f2c-447">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-447">driver license</span></span>  <br/> <span data-ttu-id="91f2c-448">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-448">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-449">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-449">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-450">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-450">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-451">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-452">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-453">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-454">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-454">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-455">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-455">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-456">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-456">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-457">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="91f2c-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="91f2c-459">Italia</span><span class="sxs-lookup"><span data-stu-id="91f2c-459">Italy</span></span>

<span data-ttu-id="91f2c-460">Per informazioni dettagliate, vedere la sezione "numero di licenza del conducente italiano" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="91f2c-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="91f2c-461">Lettonia</span><span class="sxs-lookup"><span data-stu-id="91f2c-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-462">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-462">Format</span></span>

<span data-ttu-id="91f2c-463">Tre lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-464">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-464">Pattern</span></span>

<span data-ttu-id="91f2c-465">Tre lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="91f2c-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="91f2c-466">Tre lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="91f2c-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="91f2c-467">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="91f2c-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-468">Checksum</span></span>

<span data-ttu-id="91f2c-469">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-470">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-470">Definition</span></span>

<span data-ttu-id="91f2c-471">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-472">L'espressione `Regex_latvia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-473">Viene trovata una `Keywords_latvia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-474">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-474">Keywords</span></span>

<span data-ttu-id="91f2c-475">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-475">| |</span></span>
|<span data-ttu-id="91f2c-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-477">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-477">dl#</span></span>  <br/> <span data-ttu-id="91f2c-478">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-478">driver license</span></span>  <br/> <span data-ttu-id="91f2c-479">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-479">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-480">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-480">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-481">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-481">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-482">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-483">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-484">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-485">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-485">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-486">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-486">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-487">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-487">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-488">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="91f2c-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="91f2c-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="91f2c-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-491">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-491">Format</span></span>

<span data-ttu-id="91f2c-492">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="91f2c-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-493">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-493">Pattern</span></span>

 <span data-ttu-id="91f2c-494">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="91f2c-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-495">Checksum</span></span>

<span data-ttu-id="91f2c-496">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-497">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-497">Definition</span></span>

<span data-ttu-id="91f2c-498">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-499">L'espressione `Regex_lithuania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-500">Viene trovata una `Keywords_lithuania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-501">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-501">Keywords</span></span>

<span data-ttu-id="91f2c-502">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-502">| |</span></span>
|<span data-ttu-id="91f2c-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-504">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-504">dl#</span></span>  <br/> <span data-ttu-id="91f2c-505">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-505">driver license</span></span>  <br/> <span data-ttu-id="91f2c-506">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-506">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-507">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-507">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-508">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-508">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-509">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-510">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-511">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-512">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-512">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-513">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-513">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-514">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-514">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-515">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="91f2c-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="91f2c-517">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="91f2c-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-518">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-518">Format</span></span>

<span data-ttu-id="91f2c-519">Sei cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="91f2c-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-520">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-520">Pattern</span></span>

 <span data-ttu-id="91f2c-521">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="91f2c-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-522">Checksum</span></span>

<span data-ttu-id="91f2c-523">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-524">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-524">Definition</span></span>

<span data-ttu-id="91f2c-525">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-526">L'espressione `Regex_luxemburg_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-527">Viene trovata una `Keywords_luxemburg_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-528">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-528">Keywords</span></span>

<span data-ttu-id="91f2c-529">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-529">| |</span></span>
|<span data-ttu-id="91f2c-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-531">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-531">dl#</span></span>  <br/> <span data-ttu-id="91f2c-532">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-532">driver license</span></span>  <br/> <span data-ttu-id="91f2c-533">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-533">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-534">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-534">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-535">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-535">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-536">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-537">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-538">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-539">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-539">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-540">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-540">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-541">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-541">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-542">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="91f2c-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="91f2c-544">Malta</span><span class="sxs-lookup"><span data-stu-id="91f2c-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-545">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-545">Format</span></span>

<span data-ttu-id="91f2c-546">Combinazione di due caratteri e di sei cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="91f2c-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-547">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-547">Pattern</span></span>

<span data-ttu-id="91f2c-548">Combinazione di due caratteri e di sei cifre:</span><span class="sxs-lookup"><span data-stu-id="91f2c-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="91f2c-549">Due caratteri (cifre o lettere, non con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="91f2c-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="91f2c-550">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="91f2c-550">A space (optional)</span></span>
    
- <span data-ttu-id="91f2c-551">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-551">Three digits</span></span>
    
- <span data-ttu-id="91f2c-552">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="91f2c-552">A space (optional)</span></span>
    
- <span data-ttu-id="91f2c-553">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="91f2c-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-554">Checksum</span></span>

<span data-ttu-id="91f2c-555">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-556">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-556">Definition</span></span>

<span data-ttu-id="91f2c-557">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-558">L'espressione `Regex_malta_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-559">Viene trovata una `Keywords_malta_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-560">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-560">Keywords</span></span>

<span data-ttu-id="91f2c-561">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-561">| |</span></span>
|<span data-ttu-id="91f2c-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-563">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-563">dl#</span></span>  <br/> <span data-ttu-id="91f2c-564">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-564">driver license</span></span>  <br/> <span data-ttu-id="91f2c-565">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-565">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-566">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-566">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-567">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-567">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-568">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-569">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-570">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-571">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-571">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-572">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-572">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-573">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-573">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-574">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-575">Liċenzja TAS-sewqan</span><span class="sxs-lookup"><span data-stu-id="91f2c-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="91f2c-576">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="91f2c-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-577">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-577">Format</span></span>

<span data-ttu-id="91f2c-578">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="91f2c-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-579">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-579">Pattern</span></span>

<span data-ttu-id="91f2c-580">10 cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="91f2c-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-581">Checksum</span></span>

<span data-ttu-id="91f2c-582">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-583">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-583">Definition</span></span>

<span data-ttu-id="91f2c-584">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-585">L'espressione `Regex_netherlands_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-586">Viene trovata una `Keywords_netherlands_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-587">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-587">Keywords</span></span>

<span data-ttu-id="91f2c-588">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-588">| |</span></span>
|<span data-ttu-id="91f2c-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-590">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-590">dl#</span></span>  <br/> <span data-ttu-id="91f2c-591">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-591">driver license</span></span>  <br/> <span data-ttu-id="91f2c-592">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-592">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-593">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-593">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-594">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-594">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-595">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-596">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-597">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-598">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-598">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-599">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-599">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-600">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-600">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-601">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="91f2c-602">permis de conduire</span></span>  <br/> <span data-ttu-id="91f2c-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="91f2c-603">rijbewijs</span></span>  <br/> <span data-ttu-id="91f2c-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="91f2c-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="91f2c-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="91f2c-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-606">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-606">Format</span></span>

<span data-ttu-id="91f2c-607">14 cifre contenenti 2 barre</span><span class="sxs-lookup"><span data-stu-id="91f2c-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-608">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-608">Pattern</span></span>

<span data-ttu-id="91f2c-609">14 cifre e 2 barre:</span><span class="sxs-lookup"><span data-stu-id="91f2c-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="91f2c-610">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-610">Five digits</span></span> 
    
- <span data-ttu-id="91f2c-611">Una barra</span><span class="sxs-lookup"><span data-stu-id="91f2c-611">A forward slash</span></span>
    
- <span data-ttu-id="91f2c-612">Due cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-612">Two digits</span></span>
    
- <span data-ttu-id="91f2c-613">Una barra</span><span class="sxs-lookup"><span data-stu-id="91f2c-613">A forward slash</span></span>
    
- <span data-ttu-id="91f2c-614">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="91f2c-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-615">Checksum</span></span>

<span data-ttu-id="91f2c-616">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-617">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-617">Definition</span></span>

<span data-ttu-id="91f2c-618">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-619">L'espressione `Regex_poland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-620">Viene trovata una `Keywords_poland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-621">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-621">Keywords</span></span>

<span data-ttu-id="91f2c-622">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-622">| |</span></span>
|<span data-ttu-id="91f2c-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-624">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-624">dl#</span></span>  <br/> <span data-ttu-id="91f2c-625">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-625">driver license</span></span>  <br/> <span data-ttu-id="91f2c-626">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-626">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-627">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-627">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-628">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-628">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-629">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-630">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-631">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-632">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-632">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-633">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-633">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-634">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-634">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-635">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="91f2c-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="91f2c-637">Portogallo</span><span class="sxs-lookup"><span data-stu-id="91f2c-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-638">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-638">Format</span></span>

<span data-ttu-id="91f2c-639">Due lettere seguite da un numero di sette numeri nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="91f2c-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-640">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-640">Pattern</span></span>

<span data-ttu-id="91f2c-641">Due lettere seguite da sette numeri con caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="91f2c-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="91f2c-642">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="91f2c-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="91f2c-643">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="91f2c-643">A hyphen</span></span>
    
- <span data-ttu-id="91f2c-644">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-644">Six digits</span></span>
    
- <span data-ttu-id="91f2c-645">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="91f2c-645">A space</span></span>
    
- <span data-ttu-id="91f2c-646">Una cifra</span><span class="sxs-lookup"><span data-stu-id="91f2c-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="91f2c-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-647">Checksum</span></span>

<span data-ttu-id="91f2c-648">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-649">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-649">Definition</span></span>

<span data-ttu-id="91f2c-650">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-651">L'espressione `Regex_portugal_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-652">Viene trovata una `Keywords_portugal_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-653">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-653">Keywords</span></span>

<span data-ttu-id="91f2c-654">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-654">| |</span></span>
|<span data-ttu-id="91f2c-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-656">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-656">dl#</span></span>  <br/> <span data-ttu-id="91f2c-657">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-657">driver license</span></span>  <br/> <span data-ttu-id="91f2c-658">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-658">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-659">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-659">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-660">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-660">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-661">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-662">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-663">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-664">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-664">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-665">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-665">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-666">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-666">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-667">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="91f2c-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="91f2c-669">Romania</span><span class="sxs-lookup"><span data-stu-id="91f2c-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-670">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-670">Format</span></span>

<span data-ttu-id="91f2c-671">Un carattere seguito da otto cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-672">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-672">Pattern</span></span>

<span data-ttu-id="91f2c-673">Un carattere seguito da otto cifre:</span><span class="sxs-lookup"><span data-stu-id="91f2c-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="91f2c-674">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="91f2c-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="91f2c-675">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="91f2c-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-676">Checksum</span></span>

<span data-ttu-id="91f2c-677">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-678">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-678">Definition</span></span>

<span data-ttu-id="91f2c-679">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-680">L'espressione `Regex_romania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-681">Viene trovata una `Keywords_romania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-682">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-682">Keywords</span></span>

<span data-ttu-id="91f2c-683">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-683">| |</span></span>
|<span data-ttu-id="91f2c-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-685">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-685">dl#</span></span>  <br/> <span data-ttu-id="91f2c-686">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-686">driver license</span></span>  <br/> <span data-ttu-id="91f2c-687">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-687">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-688">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-688">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-689">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-689">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-690">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-691">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-692">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-693">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-693">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-694">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-694">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-695">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-695">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-696">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-697">Permis de conducere</span><span class="sxs-lookup"><span data-stu-id="91f2c-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="91f2c-698">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="91f2c-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-699">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-699">Format</span></span>

<span data-ttu-id="91f2c-700">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-701">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-701">Pattern</span></span>

<span data-ttu-id="91f2c-702">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="91f2c-703">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="91f2c-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="91f2c-704">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="91f2c-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-705">Checksum</span></span>

<span data-ttu-id="91f2c-706">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-707">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-707">Definition</span></span>

<span data-ttu-id="91f2c-708">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-709">L'espressione `Regex_slovakia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-710">Viene trovata una `Keywords_slovakia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-711">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-711">Keywords</span></span>

<span data-ttu-id="91f2c-712">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-712">| |</span></span>
|<span data-ttu-id="91f2c-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-714">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-714">dl#</span></span>  <br/> <span data-ttu-id="91f2c-715">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-715">driver license</span></span>  <br/> <span data-ttu-id="91f2c-716">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-716">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-717">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-717">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-718">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-718">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-719">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-720">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-721">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-722">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-722">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-723">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-723">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-724">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-724">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-725">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="91f2c-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="91f2c-727">Slovenia</span><span class="sxs-lookup"><span data-stu-id="91f2c-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-728">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-728">Format</span></span>

<span data-ttu-id="91f2c-729">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="91f2c-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-730">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-730">Pattern</span></span>

<span data-ttu-id="91f2c-731">9 cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="91f2c-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-732">Checksum</span></span>

<span data-ttu-id="91f2c-733">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-734">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-734">Definition</span></span>

<span data-ttu-id="91f2c-735">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-736">L'espressione `Regex_slovenia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-737">Viene trovata una `Keywords_slovenia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-738">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-738">Keywords</span></span>

<span data-ttu-id="91f2c-739">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-739">| |</span></span>
|<span data-ttu-id="91f2c-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-741">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-741">dl#</span></span>  <br/> <span data-ttu-id="91f2c-742">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-742">driver license</span></span>  <br/> <span data-ttu-id="91f2c-743">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-743">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-744">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-744">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-745">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-745">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-746">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-747">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-748">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-749">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-749">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-750">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-750">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-751">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-751">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-752">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="91f2c-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="91f2c-754">Spagna</span><span class="sxs-lookup"><span data-stu-id="91f2c-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-755">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-755">Format</span></span>

<span data-ttu-id="91f2c-756">Otto cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="91f2c-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-757">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-757">Pattern</span></span>

<span data-ttu-id="91f2c-758">Otto cifre seguite da un carattere:</span><span class="sxs-lookup"><span data-stu-id="91f2c-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="91f2c-759">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-759">Eight digits</span></span> 
    
- <span data-ttu-id="91f2c-760">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="91f2c-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="91f2c-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-761">Checksum</span></span>

<span data-ttu-id="91f2c-762">Sì</span><span class="sxs-lookup"><span data-stu-id="91f2c-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-763">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-763">Definition</span></span>

<span data-ttu-id="91f2c-764">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-765">La funzione `Func_spain_eu_driver's_license_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-766">Viene trovata una `Keywords_spain_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="91f2c-767">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-767">Keywords</span></span>

<span data-ttu-id="91f2c-768">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-768">| |</span></span>
|<span data-ttu-id="91f2c-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-770">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-771">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-771">dl#</span></span>  <br/> <span data-ttu-id="91f2c-772">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-772">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-773">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-773">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-774">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-774">driver license</span></span>  <br/> <span data-ttu-id="91f2c-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-775">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-776">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-777">driver's licence</span></span>  <br/> <span data-ttu-id="91f2c-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-778">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-779">driving licence</span></span>  <br/> <span data-ttu-id="91f2c-780">driving license</span><span class="sxs-lookup"><span data-stu-id="91f2c-780">driving license</span></span>  <br/> <span data-ttu-id="91f2c-781">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-781">driver licence number</span></span>  <br/> <span data-ttu-id="91f2c-782">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-782">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-783">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-783">drivers licence number</span></span>  <br/> <span data-ttu-id="91f2c-784">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-784">drivers license number</span></span>  <br/> <span data-ttu-id="91f2c-785">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-785">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-786">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-786">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-787">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-787">driving licence number</span></span>  <br/> <span data-ttu-id="91f2c-788">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-788">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-789">permesso di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-789">driving permit</span></span>  <br/> <span data-ttu-id="91f2c-790">numero di licenza di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-790">driving permit number</span></span>  <br/> <span data-ttu-id="91f2c-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="91f2c-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="91f2c-792">Permiso conducción</span><span class="sxs-lookup"><span data-stu-id="91f2c-792">permiso conducción</span></span>  <br/> <span data-ttu-id="91f2c-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="91f2c-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="91f2c-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="91f2c-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="91f2c-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="91f2c-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="91f2c-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="91f2c-796">licencia conducir</span></span>  <br/> <span data-ttu-id="91f2c-797">número de Permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="91f2c-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="91f2c-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="91f2c-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="91f2c-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="91f2c-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="91f2c-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="91f2c-800">permiso conducir</span></span>  <br/> <span data-ttu-id="91f2c-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="91f2c-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="91f2c-802">El carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="91f2c-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="91f2c-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="91f2c-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="91f2c-804">Svezia</span><span class="sxs-lookup"><span data-stu-id="91f2c-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="91f2c-805">Formato</span><span class="sxs-lookup"><span data-stu-id="91f2c-805">Format</span></span>

<span data-ttu-id="91f2c-806">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="91f2c-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="91f2c-807">Modello</span><span class="sxs-lookup"><span data-stu-id="91f2c-807">Pattern</span></span>

<span data-ttu-id="91f2c-808">Dieci cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="91f2c-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="91f2c-809">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-809">Six digits</span></span> 
    
- <span data-ttu-id="91f2c-810">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="91f2c-810">A hyphen</span></span>
    
- <span data-ttu-id="91f2c-811">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="91f2c-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="91f2c-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="91f2c-812">Checksum</span></span>

<span data-ttu-id="91f2c-813">No</span><span class="sxs-lookup"><span data-stu-id="91f2c-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="91f2c-814">Definizione</span><span class="sxs-lookup"><span data-stu-id="91f2c-814">Definition</span></span>

<span data-ttu-id="91f2c-815">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="91f2c-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="91f2c-816">L'espressione `Regex_sweden_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="91f2c-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="91f2c-817">Viene trovata una `Keywords_sweden_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="91f2c-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="91f2c-818">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="91f2c-818">Keywords</span></span>

<span data-ttu-id="91f2c-819">| |</span><span class="sxs-lookup"><span data-stu-id="91f2c-819">| |</span></span>
|<span data-ttu-id="91f2c-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="91f2c-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="91f2c-821">DL #</span><span class="sxs-lookup"><span data-stu-id="91f2c-821">dl#</span></span>  <br/> <span data-ttu-id="91f2c-822">driver license</span><span class="sxs-lookup"><span data-stu-id="91f2c-822">driver license</span></span>  <br/> <span data-ttu-id="91f2c-823">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-823">driver license number</span></span>  <br/> <span data-ttu-id="91f2c-824">patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-824">driver licence</span></span>  <br/> <span data-ttu-id="91f2c-825">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="91f2c-825">drivers lic.</span></span>  <br/> <span data-ttu-id="91f2c-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="91f2c-826">drivers license</span></span>  <br/> <span data-ttu-id="91f2c-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="91f2c-827">drivers licence</span></span>  <br/> <span data-ttu-id="91f2c-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="91f2c-828">driver's license</span></span>  <br/> <span data-ttu-id="91f2c-829">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-829">driver's license number</span></span>  <br/> <span data-ttu-id="91f2c-830">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="91f2c-830">driver's licence number</span></span>  <br/> <span data-ttu-id="91f2c-831">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="91f2c-831">driving license number</span></span>  <br/> <span data-ttu-id="91f2c-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="91f2c-832">dlno#</span></span>  <br/> <span data-ttu-id="91f2c-833">körkort</span><span class="sxs-lookup"><span data-stu-id="91f2c-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="91f2c-834">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="91f2c-834">UK</span></span>

<span data-ttu-id="91f2c-835">Per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="91f2c-835">For details, see the section "U.K.</span></span> <span data-ttu-id="91f2c-836">Numero della patente di guida "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="91f2c-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="91f2c-837">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91f2c-837">See also</span></span>

[<span data-ttu-id="91f2c-838">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="91f2c-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

