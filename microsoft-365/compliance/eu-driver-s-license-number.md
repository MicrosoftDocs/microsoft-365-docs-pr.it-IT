---
title: Numero della patente di guida dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083684"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="39ea3-104">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="39ea3-104">EU Driver's License Number</span></span>

<span data-ttu-id="39ea3-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="39ea3-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="39ea3-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="39ea3-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="39ea3-107">Austria</span><span class="sxs-lookup"><span data-stu-id="39ea3-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-108">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-108">Format</span></span>

<span data-ttu-id="39ea3-109">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="39ea3-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-110">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-110">Pattern</span></span>

<span data-ttu-id="39ea3-111">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="39ea3-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-112">Checksum</span></span>

<span data-ttu-id="39ea3-113">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-114">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-114">Definition</span></span>

<span data-ttu-id="39ea3-115">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-116">L'espressione `Regex_austria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-117">Viene trovata una `Keywords_austria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="39ea3-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-118">Keywords</span></span>

<span data-ttu-id="39ea3-119">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-119"></span></span>
|<span data-ttu-id="39ea3-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-121">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-121">dl#</span></span>  <br/> <span data-ttu-id="39ea3-122">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-122">driver license</span></span>  <br/> <span data-ttu-id="39ea3-123">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-123">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-124">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-124">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-125">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-125">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-126">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-127">driver's licence</span></span>  <br/> <span data-ttu-id="39ea3-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-128">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-129">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-129">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-130">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="39ea3-131">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-131">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-132">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="39ea3-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="39ea3-134">fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="39ea3-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="39ea3-135">Belgio</span><span class="sxs-lookup"><span data-stu-id="39ea3-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-136">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-136">Format</span></span>

<span data-ttu-id="39ea3-137">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="39ea3-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-138">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-138">Pattern</span></span>

<span data-ttu-id="39ea3-139">10 cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="39ea3-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-140">Checksum</span></span>

<span data-ttu-id="39ea3-141">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-142">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-142">Definition</span></span>

<span data-ttu-id="39ea3-143">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-144">L'espressione `Regex_belgium_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-145">Viene trovata una `Keywords_belgium_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="39ea3-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-146">Keywords</span></span>

<span data-ttu-id="39ea3-147">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-147"></span></span>
|<span data-ttu-id="39ea3-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-149">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-149">dl#</span></span>  <br/> <span data-ttu-id="39ea3-150">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-150">driver license</span></span>  <br/> <span data-ttu-id="39ea3-151">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-151">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-152">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-152">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-153">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-153">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-154">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-155">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-156">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-157">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-157">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-158">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-158">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-159">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="39ea3-160">rijbewijs</span></span>  <br/> <span data-ttu-id="39ea3-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="39ea3-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="39ea3-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="39ea3-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="39ea3-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="39ea3-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="39ea3-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="39ea3-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="39ea3-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="39ea3-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="39ea3-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="39ea3-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="39ea3-167">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="39ea3-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="39ea3-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="39ea3-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-169">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-169">Format</span></span>

<span data-ttu-id="39ea3-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="39ea3-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-171">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-171">Pattern</span></span>

<span data-ttu-id="39ea3-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="39ea3-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-173">Checksum</span></span>

<span data-ttu-id="39ea3-174">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-175">Definition</span></span>

<span data-ttu-id="39ea3-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-177">L'espressione `Regex_bulgaria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-178">Viene trovata una `Keywords_bulgaria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="39ea3-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-179">Keywords</span></span>

<span data-ttu-id="39ea3-180">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-180"></span></span>
|<span data-ttu-id="39ea3-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-182">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-182">dl#</span></span>  <br/> <span data-ttu-id="39ea3-183">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-183">driver license</span></span>  <br/> <span data-ttu-id="39ea3-184">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-184">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-185">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-185">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-186">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-186">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-187">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-188">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-189">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-190">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-190">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-191">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-191">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-192">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-192">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-193">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="39ea3-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="39ea3-195">свидетелство за управление на моторно превозно d'средство</span><span class="sxs-lookup"><span data-stu-id="39ea3-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="39ea3-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="39ea3-196">сумпс</span></span>  <br/> <span data-ttu-id="39ea3-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="39ea3-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="39ea3-198">Croazia</span><span class="sxs-lookup"><span data-stu-id="39ea3-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-199">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-199">Format</span></span>

<span data-ttu-id="39ea3-200">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="39ea3-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-201">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-201">Pattern</span></span>

<span data-ttu-id="39ea3-202">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="39ea3-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-203">Checksum</span></span>

<span data-ttu-id="39ea3-204">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-205">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-205">Definition</span></span>

<span data-ttu-id="39ea3-206">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-207">L'espressione `Regex_croatia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-208">Viene trovata una `Keywords_croatia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="39ea3-209">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-209">Keywords</span></span>

<span data-ttu-id="39ea3-210">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-210"></span></span>
|<span data-ttu-id="39ea3-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-212">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-212">dl#</span></span>  <br/> <span data-ttu-id="39ea3-213">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-213">driver license</span></span>  <br/> <span data-ttu-id="39ea3-214">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-214">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-215">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-215">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-216">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-216">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-217">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-218">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-219">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-220">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-220">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-221">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-221">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-222">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-222">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-223">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="39ea3-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="39ea3-225">Cipro</span><span class="sxs-lookup"><span data-stu-id="39ea3-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-226">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-226">Format</span></span>

<span data-ttu-id="39ea3-227">12 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="39ea3-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-228">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-228">Pattern</span></span>

<span data-ttu-id="39ea3-229">12 cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="39ea3-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-230">Checksum</span></span>

<span data-ttu-id="39ea3-231">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-232">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-232">Definition</span></span>

<span data-ttu-id="39ea3-233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-234">L'espressione `Regex_cyprus_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-235">Viene trovata una `Keywords_cyprus_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-236">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-236">Keywords</span></span>

<span data-ttu-id="39ea3-237">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-237"></span></span>
|<span data-ttu-id="39ea3-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-239">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-239">dl#</span></span>  <br/> <span data-ttu-id="39ea3-240">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-240">driver license</span></span>  <br/> <span data-ttu-id="39ea3-241">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-241">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-242">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-242">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-243">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-243">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-244">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-245">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-246">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-246">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-247">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-247">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-248">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-248">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-249">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="39ea3-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="39ea3-251">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="39ea3-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-252">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-252">Format</span></span>

<span data-ttu-id="39ea3-253">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-254">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-254">Pattern</span></span>

<span data-ttu-id="39ea3-255">Otto lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="39ea3-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="39ea3-256">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="39ea3-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="39ea3-257">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="39ea3-257">A space (optional)</span></span>
    
- <span data-ttu-id="39ea3-258">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="39ea3-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-259">Checksum</span></span>

<span data-ttu-id="39ea3-260">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-261">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-261">Definition</span></span>

<span data-ttu-id="39ea3-262">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-263">L'espressione `Regex_czech_republic_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-264">Viene trovata una `Keywords_czech_republic_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="39ea3-265">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-265">Keywords</span></span>

<span data-ttu-id="39ea3-266">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-266"></span></span>
|<span data-ttu-id="39ea3-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-268">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-268">dl#</span></span>  <br/> <span data-ttu-id="39ea3-269">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-269">driver license</span></span>  <br/> <span data-ttu-id="39ea3-270">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-270">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-271">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-271">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-272">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-272">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-273">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-274">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-275">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-276">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-276">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-277">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-277">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-278">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-278">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-279">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-279">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-280">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="39ea3-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="39ea3-282">Danimarca</span><span class="sxs-lookup"><span data-stu-id="39ea3-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-283">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-283">Format</span></span>

<span data-ttu-id="39ea3-284">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="39ea3-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-285">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-285">Pattern</span></span>

<span data-ttu-id="39ea3-286">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="39ea3-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-287">Checksum</span></span>

<span data-ttu-id="39ea3-288">Sì</span><span class="sxs-lookup"><span data-stu-id="39ea3-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-289">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-289">Definition</span></span>

<span data-ttu-id="39ea3-290">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-291">L'espressione `Regex_denmark_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-292">Viene trovata una `Keywords_denmark_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="39ea3-293">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-293">Keywords</span></span>

<span data-ttu-id="39ea3-294">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-294"></span></span>
|<span data-ttu-id="39ea3-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-296">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-296">dl#</span></span>  <br/> <span data-ttu-id="39ea3-297">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-297">driver license</span></span>  <br/> <span data-ttu-id="39ea3-298">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-298">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-299">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-299">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-300">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-300">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-301">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-302">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-303">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-304">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-304">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-305">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-305">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-306">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-306">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-307">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="39ea3-308">kørekort</span></span>  <br/> <span data-ttu-id="39ea3-309">Kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="39ea3-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="39ea3-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="39ea3-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-311">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-311">Format</span></span>

<span data-ttu-id="39ea3-312">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-313">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-313">Pattern</span></span>

<span data-ttu-id="39ea3-314">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="39ea3-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="39ea3-315">Lettere "ET" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="39ea3-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="39ea3-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="39ea3-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-317">Checksum</span></span>

<span data-ttu-id="39ea3-318">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-319">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-319">Definition</span></span>

<span data-ttu-id="39ea3-320">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-321">L'espressione `Regex_estonia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-322">Viene trovata una `Keywords_estonia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-323">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-323">Keywords</span></span>

<span data-ttu-id="39ea3-324">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-324"></span></span>
|<span data-ttu-id="39ea3-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-326">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-326">dl#</span></span>  <br/> <span data-ttu-id="39ea3-327">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-327">driver license</span></span>  <br/> <span data-ttu-id="39ea3-328">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-328">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-329">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-329">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-330">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-330">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-331">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-331">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-332">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-333">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-334">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-335">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-335">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-336">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-336">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-337">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="39ea3-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="39ea3-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="39ea3-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-340">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-340">Format</span></span>

<span data-ttu-id="39ea3-341">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="39ea3-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-342">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-342">Pattern</span></span>

<span data-ttu-id="39ea3-343">10 cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="39ea3-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="39ea3-344">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-344">Six digits</span></span> 
    
- <span data-ttu-id="39ea3-345">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="39ea3-345">A hyphen</span></span>
    
-  <span data-ttu-id="39ea3-346">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="39ea3-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-347">Checksum</span></span>

<span data-ttu-id="39ea3-348">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-349">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-349">Definition</span></span>

<span data-ttu-id="39ea3-350">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-351">L'espressione `Regex_finland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-352">Viene trovata una `Keywords_finland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-353">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-353">Keywords</span></span>

<span data-ttu-id="39ea3-354">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-354"></span></span>
|<span data-ttu-id="39ea3-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-356">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-356">dl#</span></span>  <br/> <span data-ttu-id="39ea3-357">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-357">driver license</span></span>  <br/> <span data-ttu-id="39ea3-358">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-358">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-359">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-359">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-360">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-360">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-361">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-362">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-363">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-364">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-364">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-365">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-365">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-366">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-366">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-367">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="39ea3-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="39ea3-369">Francia</span><span class="sxs-lookup"><span data-stu-id="39ea3-369">France</span></span>

<span data-ttu-id="39ea3-370">Per informazioni dettagliate, vedere la sezione "numero della patente di Francia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="39ea3-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="39ea3-371">Germania</span><span class="sxs-lookup"><span data-stu-id="39ea3-371">Germany</span></span>

<span data-ttu-id="39ea3-372">Per informazioni dettagliate, vedere la sezione "numero di patente di guida tedesco" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="39ea3-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="39ea3-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="39ea3-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-374">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-374">Format</span></span>

<span data-ttu-id="39ea3-375">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="39ea3-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-376">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-376">Pattern</span></span>

 <span data-ttu-id="39ea3-377">9 cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="39ea3-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-378">Checksum</span></span>

<span data-ttu-id="39ea3-379">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-380">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-380">Definition</span></span>

<span data-ttu-id="39ea3-381">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-382">L'espressione `Regex_greece_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-383">Viene trovata una `Keywords_greece_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-384">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-384">Keywords</span></span>

<span data-ttu-id="39ea3-385">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-385"></span></span>
|<span data-ttu-id="39ea3-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-387">dlL#</span></span>  <br/> <span data-ttu-id="39ea3-388">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-388">driver license</span></span>  <br/> <span data-ttu-id="39ea3-389">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-389">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-390">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-390">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-391">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-391">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-392">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-393">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-394">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-395">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-395">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-396">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-396">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-397">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-397">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-398">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="39ea3-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="39ea3-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="39ea3-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="39ea3-401">Ungheria</span><span class="sxs-lookup"><span data-stu-id="39ea3-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-402">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-402">Format</span></span>

<span data-ttu-id="39ea3-403">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-404">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-404">Pattern</span></span>

<span data-ttu-id="39ea3-405">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="39ea3-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="39ea3-406">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="39ea3-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="39ea3-407">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="39ea3-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-408">Checksum</span></span>

<span data-ttu-id="39ea3-409">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-410">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-410">Definition</span></span>

<span data-ttu-id="39ea3-411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-412">L'espressione `Regex_hungary_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-413">Viene trovata una `Keywords_hungary_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-414">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-414">Keywords</span></span>

<span data-ttu-id="39ea3-415">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-415"></span></span>
|<span data-ttu-id="39ea3-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-417">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-417">dl#</span></span>  <br/> <span data-ttu-id="39ea3-418">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-418">driver license</span></span>  <br/> <span data-ttu-id="39ea3-419">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-419">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-420">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-420">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-421">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-421">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-422">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-423">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-424">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-425">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-425">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-426">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-426">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-427">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-427">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-428">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="39ea3-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="39ea3-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="39ea3-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-431">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-431">Format</span></span>

<span data-ttu-id="39ea3-432">Sei cifre seguite da quattro lettere</span><span class="sxs-lookup"><span data-stu-id="39ea3-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-433">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-433">Pattern</span></span>

<span data-ttu-id="39ea3-434">Sei cifre e quattro lettere:</span><span class="sxs-lookup"><span data-stu-id="39ea3-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="39ea3-435">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-435">Six digits</span></span>
    
- <span data-ttu-id="39ea3-436">Quattro lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="39ea3-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="39ea3-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-437">Checksum</span></span>

<span data-ttu-id="39ea3-438">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-439">Definition</span></span>

<span data-ttu-id="39ea3-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-441">L'espressione `Regex_ireland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-442">Viene trovata una `Keywords_ireland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-443">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-443">Keywords</span></span>

<span data-ttu-id="39ea3-444">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-444"></span></span>
|<span data-ttu-id="39ea3-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-446">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-446">dl#</span></span>  <br/> <span data-ttu-id="39ea3-447">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-447">driver license</span></span>  <br/> <span data-ttu-id="39ea3-448">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-448">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-449">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-449">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-450">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-450">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-451">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-452">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-453">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-454">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-454">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-455">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-455">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-456">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-456">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-457">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="39ea3-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="39ea3-459">Italia</span><span class="sxs-lookup"><span data-stu-id="39ea3-459">Italy</span></span>

<span data-ttu-id="39ea3-460">Per informazioni dettagliate, vedere la sezione "numero di licenza del conducente italiano" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="39ea3-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="39ea3-461">Lettonia</span><span class="sxs-lookup"><span data-stu-id="39ea3-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-462">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-462">Format</span></span>

<span data-ttu-id="39ea3-463">Tre lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-464">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-464">Pattern</span></span>

<span data-ttu-id="39ea3-465">Tre lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="39ea3-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="39ea3-466">Tre lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="39ea3-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="39ea3-467">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="39ea3-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-468">Checksum</span></span>

<span data-ttu-id="39ea3-469">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-470">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-470">Definition</span></span>

<span data-ttu-id="39ea3-471">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-472">L'espressione `Regex_latvia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-473">Viene trovata una `Keywords_latvia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-474">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-474">Keywords</span></span>

<span data-ttu-id="39ea3-475">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-475"></span></span>
|<span data-ttu-id="39ea3-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-477">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-477">dl#</span></span>  <br/> <span data-ttu-id="39ea3-478">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-478">driver license</span></span>  <br/> <span data-ttu-id="39ea3-479">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-479">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-480">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-480">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-481">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-481">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-482">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-483">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-484">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-485">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-485">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-486">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-486">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-487">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-487">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-488">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="39ea3-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="39ea3-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="39ea3-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-491">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-491">Format</span></span>

<span data-ttu-id="39ea3-492">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="39ea3-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-493">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-493">Pattern</span></span>

 <span data-ttu-id="39ea3-494">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="39ea3-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-495">Checksum</span></span>

<span data-ttu-id="39ea3-496">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-497">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-497">Definition</span></span>

<span data-ttu-id="39ea3-498">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-499">L'espressione `Regex_lithuania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-500">Viene trovata una `Keywords_lithuania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-501">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-501">Keywords</span></span>

<span data-ttu-id="39ea3-502">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-502"></span></span>
|<span data-ttu-id="39ea3-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-504">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-504">dl#</span></span>  <br/> <span data-ttu-id="39ea3-505">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-505">driver license</span></span>  <br/> <span data-ttu-id="39ea3-506">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-506">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-507">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-507">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-508">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-508">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-509">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-510">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-511">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-512">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-512">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-513">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-513">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-514">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-514">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-515">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="39ea3-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="39ea3-517">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="39ea3-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-518">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-518">Format</span></span>

<span data-ttu-id="39ea3-519">Sei cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="39ea3-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-520">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-520">Pattern</span></span>

 <span data-ttu-id="39ea3-521">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="39ea3-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-522">Checksum</span></span>

<span data-ttu-id="39ea3-523">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-524">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-524">Definition</span></span>

<span data-ttu-id="39ea3-525">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-526">L'espressione `Regex_luxemburg_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-527">Viene trovata una `Keywords_luxemburg_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-528">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-528">Keywords</span></span>

<span data-ttu-id="39ea3-529">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-529"></span></span>
|<span data-ttu-id="39ea3-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-531">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-531">dl#</span></span>  <br/> <span data-ttu-id="39ea3-532">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-532">driver license</span></span>  <br/> <span data-ttu-id="39ea3-533">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-533">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-534">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-534">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-535">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-535">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-536">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-537">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-538">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-539">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-539">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-540">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-540">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-541">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-541">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-542">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="39ea3-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="39ea3-544">Malta</span><span class="sxs-lookup"><span data-stu-id="39ea3-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-545">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-545">Format</span></span>

<span data-ttu-id="39ea3-546">Combinazione di due caratteri e di sei cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="39ea3-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-547">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-547">Pattern</span></span>

<span data-ttu-id="39ea3-548">Combinazione di due caratteri e di sei cifre:</span><span class="sxs-lookup"><span data-stu-id="39ea3-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="39ea3-549">Due caratteri (cifre o lettere, non con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="39ea3-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="39ea3-550">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="39ea3-550">A space (optional)</span></span>
    
- <span data-ttu-id="39ea3-551">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-551">Three digits</span></span>
    
- <span data-ttu-id="39ea3-552">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="39ea3-552">A space (optional)</span></span>
    
- <span data-ttu-id="39ea3-553">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="39ea3-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-554">Checksum</span></span>

<span data-ttu-id="39ea3-555">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-556">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-556">Definition</span></span>

<span data-ttu-id="39ea3-557">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-558">L'espressione `Regex_malta_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-559">Viene trovata una `Keywords_malta_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-560">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-560">Keywords</span></span>

<span data-ttu-id="39ea3-561">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-561"></span></span>
|<span data-ttu-id="39ea3-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-563">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-563">dl#</span></span>  <br/> <span data-ttu-id="39ea3-564">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-564">driver license</span></span>  <br/> <span data-ttu-id="39ea3-565">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-565">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-566">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-566">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-567">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-567">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-568">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-569">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-570">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-571">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-571">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-572">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-572">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-573">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-573">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-574">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-575">Liċenzja TAS-sewqan</span><span class="sxs-lookup"><span data-stu-id="39ea3-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="39ea3-576">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="39ea3-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-577">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-577">Format</span></span>

<span data-ttu-id="39ea3-578">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="39ea3-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-579">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-579">Pattern</span></span>

<span data-ttu-id="39ea3-580">10 cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="39ea3-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-581">Checksum</span></span>

<span data-ttu-id="39ea3-582">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-583">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-583">Definition</span></span>

<span data-ttu-id="39ea3-584">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-585">L'espressione `Regex_netherlands_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-586">Viene trovata una `Keywords_netherlands_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-587">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-587">Keywords</span></span>

<span data-ttu-id="39ea3-588">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-588"></span></span>
|<span data-ttu-id="39ea3-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-590">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-590">dl#</span></span>  <br/> <span data-ttu-id="39ea3-591">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-591">driver license</span></span>  <br/> <span data-ttu-id="39ea3-592">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-592">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-593">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-593">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-594">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-594">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-595">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-596">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-597">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-598">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-598">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-599">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-599">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-600">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-600">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-601">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="39ea3-602">permis de conduire</span></span>  <br/> <span data-ttu-id="39ea3-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="39ea3-603">rijbewijs</span></span>  <br/> <span data-ttu-id="39ea3-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="39ea3-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="39ea3-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="39ea3-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-606">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-606">Format</span></span>

<span data-ttu-id="39ea3-607">14 cifre contenenti 2 barre</span><span class="sxs-lookup"><span data-stu-id="39ea3-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-608">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-608">Pattern</span></span>

<span data-ttu-id="39ea3-609">14 cifre e 2 barre:</span><span class="sxs-lookup"><span data-stu-id="39ea3-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="39ea3-610">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-610">Five digits</span></span> 
    
- <span data-ttu-id="39ea3-611">Una barra</span><span class="sxs-lookup"><span data-stu-id="39ea3-611">A forward slash</span></span>
    
- <span data-ttu-id="39ea3-612">Due cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-612">Two digits</span></span>
    
- <span data-ttu-id="39ea3-613">Una barra</span><span class="sxs-lookup"><span data-stu-id="39ea3-613">A forward slash</span></span>
    
- <span data-ttu-id="39ea3-614">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="39ea3-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-615">Checksum</span></span>

<span data-ttu-id="39ea3-616">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-617">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-617">Definition</span></span>

<span data-ttu-id="39ea3-618">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-619">L'espressione `Regex_poland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-620">Viene trovata una `Keywords_poland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-621">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-621">Keywords</span></span>

<span data-ttu-id="39ea3-622">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-622"></span></span>
|<span data-ttu-id="39ea3-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-624">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-624">dl#</span></span>  <br/> <span data-ttu-id="39ea3-625">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-625">driver license</span></span>  <br/> <span data-ttu-id="39ea3-626">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-626">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-627">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-627">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-628">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-628">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-629">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-630">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-631">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-632">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-632">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-633">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-633">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-634">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-634">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-635">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="39ea3-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="39ea3-637">Portogallo</span><span class="sxs-lookup"><span data-stu-id="39ea3-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-638">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-638">Format</span></span>

<span data-ttu-id="39ea3-639">Due lettere seguite da un numero di sette numeri nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="39ea3-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-640">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-640">Pattern</span></span>

<span data-ttu-id="39ea3-641">Due lettere seguite da sette numeri con caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="39ea3-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="39ea3-642">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="39ea3-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="39ea3-643">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="39ea3-643">A hyphen</span></span>
    
- <span data-ttu-id="39ea3-644">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-644">Six digits</span></span>
    
- <span data-ttu-id="39ea3-645">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="39ea3-645">A space</span></span>
    
- <span data-ttu-id="39ea3-646">Una cifra</span><span class="sxs-lookup"><span data-stu-id="39ea3-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="39ea3-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-647">Checksum</span></span>

<span data-ttu-id="39ea3-648">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-649">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-649">Definition</span></span>

<span data-ttu-id="39ea3-650">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-651">L'espressione `Regex_portugal_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-652">Viene trovata una `Keywords_portugal_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-653">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-653">Keywords</span></span>

<span data-ttu-id="39ea3-654">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-654"></span></span>
|<span data-ttu-id="39ea3-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-656">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-656">dl#</span></span>  <br/> <span data-ttu-id="39ea3-657">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-657">driver license</span></span>  <br/> <span data-ttu-id="39ea3-658">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-658">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-659">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-659">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-660">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-660">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-661">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-662">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-663">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-664">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-664">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-665">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-665">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-666">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-666">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-667">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="39ea3-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="39ea3-669">Romania</span><span class="sxs-lookup"><span data-stu-id="39ea3-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-670">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-670">Format</span></span>

<span data-ttu-id="39ea3-671">Un carattere seguito da otto cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-672">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-672">Pattern</span></span>

<span data-ttu-id="39ea3-673">Un carattere seguito da otto cifre:</span><span class="sxs-lookup"><span data-stu-id="39ea3-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="39ea3-674">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="39ea3-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="39ea3-675">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="39ea3-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-676">Checksum</span></span>

<span data-ttu-id="39ea3-677">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-678">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-678">Definition</span></span>

<span data-ttu-id="39ea3-679">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-680">L'espressione `Regex_romania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-681">Viene trovata una `Keywords_romania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-682">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-682">Keywords</span></span>

<span data-ttu-id="39ea3-683">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-683"></span></span>
|<span data-ttu-id="39ea3-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-685">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-685">dl#</span></span>  <br/> <span data-ttu-id="39ea3-686">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-686">driver license</span></span>  <br/> <span data-ttu-id="39ea3-687">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-687">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-688">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-688">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-689">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-689">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-690">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-691">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-692">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-693">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-693">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-694">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-694">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-695">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-695">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-696">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-697">Permis de conducere</span><span class="sxs-lookup"><span data-stu-id="39ea3-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="39ea3-698">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="39ea3-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-699">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-699">Format</span></span>

<span data-ttu-id="39ea3-700">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-701">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-701">Pattern</span></span>

<span data-ttu-id="39ea3-702">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="39ea3-703">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="39ea3-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="39ea3-704">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="39ea3-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-705">Checksum</span></span>

<span data-ttu-id="39ea3-706">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-707">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-707">Definition</span></span>

<span data-ttu-id="39ea3-708">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-709">L'espressione `Regex_slovakia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-710">Viene trovata una `Keywords_slovakia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-711">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-711">Keywords</span></span>

<span data-ttu-id="39ea3-712">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-712"></span></span>
|<span data-ttu-id="39ea3-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-714">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-714">dl#</span></span>  <br/> <span data-ttu-id="39ea3-715">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-715">driver license</span></span>  <br/> <span data-ttu-id="39ea3-716">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-716">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-717">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-717">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-718">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-718">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-719">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-720">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-721">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-722">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-722">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-723">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-723">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-724">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-724">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-725">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="39ea3-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="39ea3-727">Slovenia</span><span class="sxs-lookup"><span data-stu-id="39ea3-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-728">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-728">Format</span></span>

<span data-ttu-id="39ea3-729">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="39ea3-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-730">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-730">Pattern</span></span>

<span data-ttu-id="39ea3-731">9 cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="39ea3-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-732">Checksum</span></span>

<span data-ttu-id="39ea3-733">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-734">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-734">Definition</span></span>

<span data-ttu-id="39ea3-735">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-736">L'espressione `Regex_slovenia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-737">Viene trovata una `Keywords_slovenia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-738">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-738">Keywords</span></span>

<span data-ttu-id="39ea3-739">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-739"></span></span>
|<span data-ttu-id="39ea3-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-741">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-741">dl#</span></span>  <br/> <span data-ttu-id="39ea3-742">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-742">driver license</span></span>  <br/> <span data-ttu-id="39ea3-743">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-743">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-744">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-744">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-745">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-745">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-746">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-747">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-748">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-749">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-749">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-750">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-750">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-751">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-751">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-752">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="39ea3-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="39ea3-754">Spagna</span><span class="sxs-lookup"><span data-stu-id="39ea3-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-755">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-755">Format</span></span>

<span data-ttu-id="39ea3-756">Otto cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="39ea3-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-757">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-757">Pattern</span></span>

<span data-ttu-id="39ea3-758">Otto cifre seguite da un carattere:</span><span class="sxs-lookup"><span data-stu-id="39ea3-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="39ea3-759">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-759">Eight digits</span></span> 
    
- <span data-ttu-id="39ea3-760">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="39ea3-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="39ea3-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-761">Checksum</span></span>

<span data-ttu-id="39ea3-762">Sì</span><span class="sxs-lookup"><span data-stu-id="39ea3-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-763">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-763">Definition</span></span>

<span data-ttu-id="39ea3-764">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-765">La funzione `Func_spain_eu_driver's_license_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-766">Viene trovata una `Keywords_spain_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="39ea3-767">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-767">Keywords</span></span>

<span data-ttu-id="39ea3-768">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-768"></span></span>
|<span data-ttu-id="39ea3-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-770">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-771">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-771">dl#</span></span>  <br/> <span data-ttu-id="39ea3-772">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-772">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-773">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-773">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-774">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-774">driver license</span></span>  <br/> <span data-ttu-id="39ea3-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-775">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-776">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-777">driver's licence</span></span>  <br/> <span data-ttu-id="39ea3-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-778">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-779">driving licence</span></span>  <br/> <span data-ttu-id="39ea3-780">driving license</span><span class="sxs-lookup"><span data-stu-id="39ea3-780">driving license</span></span>  <br/> <span data-ttu-id="39ea3-781">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-781">driver licence number</span></span>  <br/> <span data-ttu-id="39ea3-782">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-782">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-783">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-783">drivers licence number</span></span>  <br/> <span data-ttu-id="39ea3-784">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-784">drivers license number</span></span>  <br/> <span data-ttu-id="39ea3-785">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-785">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-786">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-786">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-787">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-787">driving licence number</span></span>  <br/> <span data-ttu-id="39ea3-788">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-788">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-789">permesso di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-789">driving permit</span></span>  <br/> <span data-ttu-id="39ea3-790">numero di licenza di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-790">driving permit number</span></span>  <br/> <span data-ttu-id="39ea3-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="39ea3-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="39ea3-792">Permiso conducción</span><span class="sxs-lookup"><span data-stu-id="39ea3-792">permiso conducción</span></span>  <br/> <span data-ttu-id="39ea3-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="39ea3-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="39ea3-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="39ea3-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="39ea3-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="39ea3-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="39ea3-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="39ea3-796">licencia conducir</span></span>  <br/> <span data-ttu-id="39ea3-797">número de Permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="39ea3-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="39ea3-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="39ea3-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="39ea3-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="39ea3-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="39ea3-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="39ea3-800">permiso conducir</span></span>  <br/> <span data-ttu-id="39ea3-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="39ea3-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="39ea3-802">El carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="39ea3-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="39ea3-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="39ea3-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="39ea3-804">Svezia</span><span class="sxs-lookup"><span data-stu-id="39ea3-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="39ea3-805">Formato</span><span class="sxs-lookup"><span data-stu-id="39ea3-805">Format</span></span>

<span data-ttu-id="39ea3-806">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="39ea3-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="39ea3-807">Modello</span><span class="sxs-lookup"><span data-stu-id="39ea3-807">Pattern</span></span>

<span data-ttu-id="39ea3-808">Dieci cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="39ea3-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="39ea3-809">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-809">Six digits</span></span> 
    
- <span data-ttu-id="39ea3-810">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="39ea3-810">A hyphen</span></span>
    
- <span data-ttu-id="39ea3-811">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="39ea3-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="39ea3-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="39ea3-812">Checksum</span></span>

<span data-ttu-id="39ea3-813">No</span><span class="sxs-lookup"><span data-stu-id="39ea3-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="39ea3-814">Definizione</span><span class="sxs-lookup"><span data-stu-id="39ea3-814">Definition</span></span>

<span data-ttu-id="39ea3-815">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="39ea3-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="39ea3-816">L'espressione `Regex_sweden_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="39ea3-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="39ea3-817">Viene trovata una `Keywords_sweden_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="39ea3-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="39ea3-818">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="39ea3-818">Keywords</span></span>

<span data-ttu-id="39ea3-819">| |</span><span class="sxs-lookup"><span data-stu-id="39ea3-819"></span></span>
|<span data-ttu-id="39ea3-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="39ea3-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="39ea3-821">DL #</span><span class="sxs-lookup"><span data-stu-id="39ea3-821">dl#</span></span>  <br/> <span data-ttu-id="39ea3-822">driver license</span><span class="sxs-lookup"><span data-stu-id="39ea3-822">driver license</span></span>  <br/> <span data-ttu-id="39ea3-823">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-823">driver license number</span></span>  <br/> <span data-ttu-id="39ea3-824">patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-824">driver licence</span></span>  <br/> <span data-ttu-id="39ea3-825">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="39ea3-825">drivers lic.</span></span>  <br/> <span data-ttu-id="39ea3-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="39ea3-826">drivers license</span></span>  <br/> <span data-ttu-id="39ea3-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="39ea3-827">drivers licence</span></span>  <br/> <span data-ttu-id="39ea3-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="39ea3-828">driver's license</span></span>  <br/> <span data-ttu-id="39ea3-829">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-829">driver's license number</span></span>  <br/> <span data-ttu-id="39ea3-830">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="39ea3-830">driver's licence number</span></span>  <br/> <span data-ttu-id="39ea3-831">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="39ea3-831">driving license number</span></span>  <br/> <span data-ttu-id="39ea3-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="39ea3-832">dlno#</span></span>  <br/> <span data-ttu-id="39ea3-833">körkort</span><span class="sxs-lookup"><span data-stu-id="39ea3-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="39ea3-834">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="39ea3-834">UK</span></span>

<span data-ttu-id="39ea3-835">Per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="39ea3-835">For details, see the section "U.K.</span></span> <span data-ttu-id="39ea3-836">Numero della patente di guida "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="39ea3-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="39ea3-837">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39ea3-837">See also</span></span>

[<span data-ttu-id="39ea3-838">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="39ea3-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

