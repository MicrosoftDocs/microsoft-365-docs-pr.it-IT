---
title: Numero della patente di guida dell'Unione europea
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592657"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="0ef3f-104">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="0ef3f-104">EU Driver's License Number</span></span>

<span data-ttu-id="0ef3f-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="0ef3f-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="0ef3f-107">Austria</span><span class="sxs-lookup"><span data-stu-id="0ef3f-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-108">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-108">Format</span></span>

<span data-ttu-id="0ef3f-109">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="0ef3f-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-110">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-110">Pattern</span></span>

<span data-ttu-id="0ef3f-111">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0ef3f-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-112">Checksum</span></span>

<span data-ttu-id="0ef3f-113">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-114">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-114">Definition</span></span>

<span data-ttu-id="0ef3f-115">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-116">L'espressione `Regex_austria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-117">Viene trovata una `Keywords_austria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="0ef3f-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-118">Keywords</span></span>

<span data-ttu-id="0ef3f-119">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-119">| |</span></span>
|<span data-ttu-id="0ef3f-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-121">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-121">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-122">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-122">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-123">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-123">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-124">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-124">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-125">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-125">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-126">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-127">driver's licence</span></span>  <br/> <span data-ttu-id="0ef3f-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-128">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-129">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-129">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-130">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="0ef3f-131">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-131">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-132">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="0ef3f-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="0ef3f-134">fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="0ef3f-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="0ef3f-135">Belgio</span><span class="sxs-lookup"><span data-stu-id="0ef3f-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-136">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-136">Format</span></span>

<span data-ttu-id="0ef3f-137">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="0ef3f-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-138">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-138">Pattern</span></span>

<span data-ttu-id="0ef3f-139">10 cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0ef3f-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-140">Checksum</span></span>

<span data-ttu-id="0ef3f-141">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-142">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-142">Definition</span></span>

<span data-ttu-id="0ef3f-143">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-144">L'espressione `Regex_belgium_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-145">Viene trovata una `Keywords_belgium_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="0ef3f-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-146">Keywords</span></span>

<span data-ttu-id="0ef3f-147">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-147">| |</span></span>
|<span data-ttu-id="0ef3f-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-149">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-149">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-150">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-150">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-151">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-151">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-152">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-152">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-153">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-153">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-154">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-155">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-156">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-157">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-157">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-158">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-158">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-159">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="0ef3f-160">rijbewijs</span></span>  <br/> <span data-ttu-id="0ef3f-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="0ef3f-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="0ef3f-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="0ef3f-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="0ef3f-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="0ef3f-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="0ef3f-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="0ef3f-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="0ef3f-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="0ef3f-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="0ef3f-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="0ef3f-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="0ef3f-167">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="0ef3f-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="0ef3f-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="0ef3f-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-169">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-169">Format</span></span>

<span data-ttu-id="0ef3f-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="0ef3f-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-171">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-171">Pattern</span></span>

<span data-ttu-id="0ef3f-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0ef3f-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-173">Checksum</span></span>

<span data-ttu-id="0ef3f-174">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-175">Definition</span></span>

<span data-ttu-id="0ef3f-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-177">L'espressione `Regex_bulgaria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-178">Viene trovata una `Keywords_bulgaria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="0ef3f-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-179">Keywords</span></span>

<span data-ttu-id="0ef3f-180">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-180">| |</span></span>
|<span data-ttu-id="0ef3f-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-182">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-182">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-183">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-183">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-184">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-184">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-185">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-185">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-186">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-186">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-187">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-188">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-189">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-190">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-190">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-191">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-191">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-192">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-192">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-193">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="0ef3f-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="0ef3f-195">свидетелство за управление на моторно превозно d'средство</span><span class="sxs-lookup"><span data-stu-id="0ef3f-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="0ef3f-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="0ef3f-196">сумпс</span></span>  <br/> <span data-ttu-id="0ef3f-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="0ef3f-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="0ef3f-198">Croazia</span><span class="sxs-lookup"><span data-stu-id="0ef3f-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-199">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-199">Format</span></span>

<span data-ttu-id="0ef3f-200">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="0ef3f-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-201">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-201">Pattern</span></span>

<span data-ttu-id="0ef3f-202">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0ef3f-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-203">Checksum</span></span>

<span data-ttu-id="0ef3f-204">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-205">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-205">Definition</span></span>

<span data-ttu-id="0ef3f-206">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-207">L'espressione `Regex_croatia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-208">Viene trovata una `Keywords_croatia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="0ef3f-209">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-209">Keywords</span></span>

<span data-ttu-id="0ef3f-210">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-210">| |</span></span>
|<span data-ttu-id="0ef3f-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-212">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-212">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-213">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-213">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-214">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-214">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-215">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-215">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-216">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-216">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-217">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-218">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-219">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-220">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-220">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-221">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-221">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-222">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-222">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-223">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="0ef3f-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="0ef3f-225">Cipro</span><span class="sxs-lookup"><span data-stu-id="0ef3f-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-226">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-226">Format</span></span>

<span data-ttu-id="0ef3f-227">12 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="0ef3f-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-228">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-228">Pattern</span></span>

<span data-ttu-id="0ef3f-229">12 cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0ef3f-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-230">Checksum</span></span>

<span data-ttu-id="0ef3f-231">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-232">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-232">Definition</span></span>

<span data-ttu-id="0ef3f-233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-234">L'espressione `Regex_cyprus_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-235">Viene trovata una `Keywords_cyprus_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-236">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-236">Keywords</span></span>

<span data-ttu-id="0ef3f-237">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-237">| |</span></span>
|<span data-ttu-id="0ef3f-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-239">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-239">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-240">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-240">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-241">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-241">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-242">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-242">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-243">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-243">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-244">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-245">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-246">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-246">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-247">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-247">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-248">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-248">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-249">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="0ef3f-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="0ef3f-251">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="0ef3f-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-252">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-252">Format</span></span>

<span data-ttu-id="0ef3f-253">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-254">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-254">Pattern</span></span>

<span data-ttu-id="0ef3f-255">Otto lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="0ef3f-256">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="0ef3f-257">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-257">A space (optional)</span></span>
    
- <span data-ttu-id="0ef3f-258">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-259">Checksum</span></span>

<span data-ttu-id="0ef3f-260">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-261">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-261">Definition</span></span>

<span data-ttu-id="0ef3f-262">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-263">L'espressione `Regex_czech_republic_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-264">Viene trovata una `Keywords_czech_republic_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="0ef3f-265">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-265">Keywords</span></span>

<span data-ttu-id="0ef3f-266">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-266">| |</span></span>
|<span data-ttu-id="0ef3f-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-268">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-268">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-269">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-269">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-270">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-270">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-271">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-271">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-272">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-272">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-273">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-274">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-275">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-276">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-276">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-277">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-277">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-278">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-278">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-279">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-279">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-280">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="0ef3f-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="0ef3f-282">Danimarca</span><span class="sxs-lookup"><span data-stu-id="0ef3f-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-283">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-283">Format</span></span>

<span data-ttu-id="0ef3f-284">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="0ef3f-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-285">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-285">Pattern</span></span>

<span data-ttu-id="0ef3f-286">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0ef3f-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-287">Checksum</span></span>

<span data-ttu-id="0ef3f-288">Sì</span><span class="sxs-lookup"><span data-stu-id="0ef3f-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-289">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-289">Definition</span></span>

<span data-ttu-id="0ef3f-290">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-291">L'espressione `Regex_denmark_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-292">Viene trovata una `Keywords_denmark_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="0ef3f-293">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-293">Keywords</span></span>

<span data-ttu-id="0ef3f-294">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-294">| |</span></span>
|<span data-ttu-id="0ef3f-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-296">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-296">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-297">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-297">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-298">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-298">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-299">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-299">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-300">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-300">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-301">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-302">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-303">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-304">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-304">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-305">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-305">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-306">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-306">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-307">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="0ef3f-308">kørekort</span></span>  <br/> <span data-ttu-id="0ef3f-309">Kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="0ef3f-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="0ef3f-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="0ef3f-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-311">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-311">Format</span></span>

<span data-ttu-id="0ef3f-312">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-313">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-313">Pattern</span></span>

<span data-ttu-id="0ef3f-314">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="0ef3f-315">Lettere "ET" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="0ef3f-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-317">Checksum</span></span>

<span data-ttu-id="0ef3f-318">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-319">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-319">Definition</span></span>

<span data-ttu-id="0ef3f-320">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-321">L'espressione `Regex_estonia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-322">Viene trovata una `Keywords_estonia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-323">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-323">Keywords</span></span>

<span data-ttu-id="0ef3f-324">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-324">| |</span></span>
|<span data-ttu-id="0ef3f-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-326">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-326">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-327">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-327">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-328">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-328">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-329">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-329">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-330">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-330">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-331">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-331">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-332">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-333">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-334">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-335">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-335">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-336">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-336">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-337">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="0ef3f-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="0ef3f-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="0ef3f-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-340">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-340">Format</span></span>

<span data-ttu-id="0ef3f-341">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="0ef3f-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-342">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-342">Pattern</span></span>

<span data-ttu-id="0ef3f-343">10 cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="0ef3f-344">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-344">Six digits</span></span> 
    
- <span data-ttu-id="0ef3f-345">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0ef3f-345">A hyphen</span></span>
    
-  <span data-ttu-id="0ef3f-346">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-347">Checksum</span></span>

<span data-ttu-id="0ef3f-348">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-349">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-349">Definition</span></span>

<span data-ttu-id="0ef3f-350">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-351">L'espressione `Regex_finland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-352">Viene trovata una `Keywords_finland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-353">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-353">Keywords</span></span>

<span data-ttu-id="0ef3f-354">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-354">| |</span></span>
|<span data-ttu-id="0ef3f-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-356">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-356">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-357">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-357">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-358">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-358">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-359">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-359">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-360">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-360">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-361">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-362">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-363">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-364">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-364">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-365">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-365">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-366">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-366">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-367">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="0ef3f-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="0ef3f-369">Francia</span><span class="sxs-lookup"><span data-stu-id="0ef3f-369">France</span></span>

<span data-ttu-id="0ef3f-370">Per informazioni dettagliate, vedere la sezione "numero della patente di Francia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="0ef3f-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="0ef3f-371">Germania</span><span class="sxs-lookup"><span data-stu-id="0ef3f-371">Germany</span></span>

<span data-ttu-id="0ef3f-372">Per informazioni dettagliate, vedere la sezione "numero di patente di guida tedesco" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="0ef3f-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="0ef3f-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="0ef3f-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-374">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-374">Format</span></span>

<span data-ttu-id="0ef3f-375">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="0ef3f-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-376">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-376">Pattern</span></span>

 <span data-ttu-id="0ef3f-377">9 cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="0ef3f-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-378">Checksum</span></span>

<span data-ttu-id="0ef3f-379">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-380">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-380">Definition</span></span>

<span data-ttu-id="0ef3f-381">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-382">L'espressione `Regex_greece_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-383">Viene trovata una `Keywords_greece_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-384">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-384">Keywords</span></span>

<span data-ttu-id="0ef3f-385">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-385">| |</span></span>
|<span data-ttu-id="0ef3f-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-387">dlL#</span></span>  <br/> <span data-ttu-id="0ef3f-388">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-388">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-389">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-389">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-390">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-390">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-391">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-391">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-392">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-393">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-394">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-395">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-395">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-396">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-396">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-397">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-397">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-398">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="0ef3f-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="0ef3f-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="0ef3f-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="0ef3f-401">Ungheria</span><span class="sxs-lookup"><span data-stu-id="0ef3f-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-402">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-402">Format</span></span>

<span data-ttu-id="0ef3f-403">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-404">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-404">Pattern</span></span>

<span data-ttu-id="0ef3f-405">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="0ef3f-406">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="0ef3f-407">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-408">Checksum</span></span>

<span data-ttu-id="0ef3f-409">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-410">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-410">Definition</span></span>

<span data-ttu-id="0ef3f-411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-412">L'espressione `Regex_hungary_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-413">Viene trovata una `Keywords_hungary_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-414">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-414">Keywords</span></span>

<span data-ttu-id="0ef3f-415">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-415">| |</span></span>
|<span data-ttu-id="0ef3f-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-417">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-417">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-418">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-418">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-419">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-419">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-420">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-420">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-421">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-421">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-422">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-423">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-424">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-425">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-425">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-426">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-426">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-427">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-427">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-428">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="0ef3f-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="0ef3f-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="0ef3f-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-431">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-431">Format</span></span>

<span data-ttu-id="0ef3f-432">Sei cifre seguite da quattro lettere</span><span class="sxs-lookup"><span data-stu-id="0ef3f-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-433">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-433">Pattern</span></span>

<span data-ttu-id="0ef3f-434">Sei cifre e quattro lettere:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="0ef3f-435">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-435">Six digits</span></span>
    
- <span data-ttu-id="0ef3f-436">Quattro lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-437">Checksum</span></span>

<span data-ttu-id="0ef3f-438">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-439">Definition</span></span>

<span data-ttu-id="0ef3f-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-441">L'espressione `Regex_ireland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-442">Viene trovata una `Keywords_ireland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-443">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-443">Keywords</span></span>

<span data-ttu-id="0ef3f-444">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-444">| |</span></span>
|<span data-ttu-id="0ef3f-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-446">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-446">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-447">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-447">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-448">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-448">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-449">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-449">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-450">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-450">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-451">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-452">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-453">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-454">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-454">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-455">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-455">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-456">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-456">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-457">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="0ef3f-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="0ef3f-459">Italia</span><span class="sxs-lookup"><span data-stu-id="0ef3f-459">Italy</span></span>

<span data-ttu-id="0ef3f-460">Per informazioni dettagliate, vedere la sezione "numero di licenza del conducente italiano" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="0ef3f-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="0ef3f-461">Lettonia</span><span class="sxs-lookup"><span data-stu-id="0ef3f-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-462">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-462">Format</span></span>

<span data-ttu-id="0ef3f-463">Tre lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-464">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-464">Pattern</span></span>

<span data-ttu-id="0ef3f-465">Tre lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="0ef3f-466">Tre lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="0ef3f-467">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-468">Checksum</span></span>

<span data-ttu-id="0ef3f-469">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-470">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-470">Definition</span></span>

<span data-ttu-id="0ef3f-471">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-472">L'espressione `Regex_latvia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-473">Viene trovata una `Keywords_latvia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-474">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-474">Keywords</span></span>

<span data-ttu-id="0ef3f-475">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-475">| |</span></span>
|<span data-ttu-id="0ef3f-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-477">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-477">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-478">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-478">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-479">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-479">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-480">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-480">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-481">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-481">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-482">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-483">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-484">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-485">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-485">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-486">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-486">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-487">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-487">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-488">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="0ef3f-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="0ef3f-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="0ef3f-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-491">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-491">Format</span></span>

<span data-ttu-id="0ef3f-492">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="0ef3f-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-493">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-493">Pattern</span></span>

 <span data-ttu-id="0ef3f-494">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="0ef3f-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-495">Checksum</span></span>

<span data-ttu-id="0ef3f-496">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-497">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-497">Definition</span></span>

<span data-ttu-id="0ef3f-498">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-499">L'espressione `Regex_lithuania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-500">Viene trovata una `Keywords_lithuania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-501">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-501">Keywords</span></span>

<span data-ttu-id="0ef3f-502">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-502">| |</span></span>
|<span data-ttu-id="0ef3f-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-504">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-504">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-505">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-505">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-506">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-506">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-507">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-507">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-508">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-508">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-509">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-510">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-511">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-512">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-512">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-513">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-513">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-514">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-514">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-515">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="0ef3f-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="0ef3f-517">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="0ef3f-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-518">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-518">Format</span></span>

<span data-ttu-id="0ef3f-519">Sei cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="0ef3f-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-520">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-520">Pattern</span></span>

 <span data-ttu-id="0ef3f-521">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="0ef3f-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-522">Checksum</span></span>

<span data-ttu-id="0ef3f-523">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-524">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-524">Definition</span></span>

<span data-ttu-id="0ef3f-525">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-526">L'espressione `Regex_luxemburg_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-527">Viene trovata una `Keywords_luxemburg_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-528">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-528">Keywords</span></span>

<span data-ttu-id="0ef3f-529">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-529">| |</span></span>
|<span data-ttu-id="0ef3f-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-531">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-531">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-532">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-532">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-533">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-533">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-534">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-534">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-535">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-535">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-536">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-537">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-538">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-539">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-539">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-540">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-540">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-541">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-541">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-542">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="0ef3f-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="0ef3f-544">Malta</span><span class="sxs-lookup"><span data-stu-id="0ef3f-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-545">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-545">Format</span></span>

<span data-ttu-id="0ef3f-546">Combinazione di due caratteri e di sei cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-547">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-547">Pattern</span></span>

<span data-ttu-id="0ef3f-548">Combinazione di due caratteri e di sei cifre:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="0ef3f-549">Due caratteri (cifre o lettere, non con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="0ef3f-550">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-550">A space (optional)</span></span>
    
- <span data-ttu-id="0ef3f-551">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-551">Three digits</span></span>
    
- <span data-ttu-id="0ef3f-552">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-552">A space (optional)</span></span>
    
- <span data-ttu-id="0ef3f-553">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-554">Checksum</span></span>

<span data-ttu-id="0ef3f-555">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-556">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-556">Definition</span></span>

<span data-ttu-id="0ef3f-557">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-558">L'espressione `Regex_malta_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-559">Viene trovata una `Keywords_malta_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-560">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-560">Keywords</span></span>

<span data-ttu-id="0ef3f-561">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-561">| |</span></span>
|<span data-ttu-id="0ef3f-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-563">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-563">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-564">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-564">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-565">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-565">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-566">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-566">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-567">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-567">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-568">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-569">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-570">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-571">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-571">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-572">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-572">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-573">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-573">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-574">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-575">Liċenzja TAS-sewqan</span><span class="sxs-lookup"><span data-stu-id="0ef3f-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="0ef3f-576">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="0ef3f-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-577">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-577">Format</span></span>

<span data-ttu-id="0ef3f-578">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="0ef3f-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-579">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-579">Pattern</span></span>

<span data-ttu-id="0ef3f-580">10 cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0ef3f-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-581">Checksum</span></span>

<span data-ttu-id="0ef3f-582">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-583">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-583">Definition</span></span>

<span data-ttu-id="0ef3f-584">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-585">L'espressione `Regex_netherlands_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-586">Viene trovata una `Keywords_netherlands_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-587">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-587">Keywords</span></span>

<span data-ttu-id="0ef3f-588">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-588">| |</span></span>
|<span data-ttu-id="0ef3f-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-590">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-590">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-591">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-591">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-592">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-592">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-593">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-593">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-594">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-594">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-595">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-596">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-597">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-598">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-598">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-599">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-599">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-600">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-600">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-601">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="0ef3f-602">permis de conduire</span></span>  <br/> <span data-ttu-id="0ef3f-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="0ef3f-603">rijbewijs</span></span>  <br/> <span data-ttu-id="0ef3f-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="0ef3f-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="0ef3f-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="0ef3f-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-606">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-606">Format</span></span>

<span data-ttu-id="0ef3f-607">14 cifre contenenti 2 barre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-608">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-608">Pattern</span></span>

<span data-ttu-id="0ef3f-609">14 cifre e 2 barre:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="0ef3f-610">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-610">Five digits</span></span> 
    
- <span data-ttu-id="0ef3f-611">Una barra</span><span class="sxs-lookup"><span data-stu-id="0ef3f-611">A forward slash</span></span>
    
- <span data-ttu-id="0ef3f-612">Due cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-612">Two digits</span></span>
    
- <span data-ttu-id="0ef3f-613">Una barra</span><span class="sxs-lookup"><span data-stu-id="0ef3f-613">A forward slash</span></span>
    
- <span data-ttu-id="0ef3f-614">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-615">Checksum</span></span>

<span data-ttu-id="0ef3f-616">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-617">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-617">Definition</span></span>

<span data-ttu-id="0ef3f-618">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-619">L'espressione `Regex_poland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-620">Viene trovata una `Keywords_poland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-621">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-621">Keywords</span></span>

<span data-ttu-id="0ef3f-622">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-622">| |</span></span>
|<span data-ttu-id="0ef3f-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-624">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-624">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-625">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-625">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-626">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-626">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-627">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-627">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-628">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-628">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-629">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-630">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-631">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-632">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-632">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-633">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-633">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-634">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-634">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-635">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="0ef3f-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="0ef3f-637">Portogallo</span><span class="sxs-lookup"><span data-stu-id="0ef3f-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-638">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-638">Format</span></span>

<span data-ttu-id="0ef3f-639">Due lettere seguite da un numero di sette numeri nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-640">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-640">Pattern</span></span>

<span data-ttu-id="0ef3f-641">Due lettere seguite da sette numeri con caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="0ef3f-642">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="0ef3f-643">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0ef3f-643">A hyphen</span></span>
    
- <span data-ttu-id="0ef3f-644">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-644">Six digits</span></span>
    
- <span data-ttu-id="0ef3f-645">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="0ef3f-645">A space</span></span>
    
- <span data-ttu-id="0ef3f-646">Una cifra</span><span class="sxs-lookup"><span data-stu-id="0ef3f-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-647">Checksum</span></span>

<span data-ttu-id="0ef3f-648">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-649">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-649">Definition</span></span>

<span data-ttu-id="0ef3f-650">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-651">L'espressione `Regex_portugal_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-652">Viene trovata una `Keywords_portugal_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-653">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-653">Keywords</span></span>

<span data-ttu-id="0ef3f-654">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-654">| |</span></span>
|<span data-ttu-id="0ef3f-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-656">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-656">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-657">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-657">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-658">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-658">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-659">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-659">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-660">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-660">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-661">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-662">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-663">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-664">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-664">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-665">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-665">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-666">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-666">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-667">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="0ef3f-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="0ef3f-669">Romania</span><span class="sxs-lookup"><span data-stu-id="0ef3f-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-670">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-670">Format</span></span>

<span data-ttu-id="0ef3f-671">Un carattere seguito da otto cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-672">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-672">Pattern</span></span>

<span data-ttu-id="0ef3f-673">Un carattere seguito da otto cifre:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="0ef3f-674">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="0ef3f-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="0ef3f-675">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-676">Checksum</span></span>

<span data-ttu-id="0ef3f-677">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-678">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-678">Definition</span></span>

<span data-ttu-id="0ef3f-679">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-680">L'espressione `Regex_romania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-681">Viene trovata una `Keywords_romania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-682">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-682">Keywords</span></span>

<span data-ttu-id="0ef3f-683">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-683">| |</span></span>
|<span data-ttu-id="0ef3f-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-685">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-685">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-686">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-686">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-687">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-687">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-688">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-688">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-689">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-689">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-690">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-691">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-692">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-693">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-693">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-694">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-694">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-695">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-695">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-696">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-697">Permis de conducere</span><span class="sxs-lookup"><span data-stu-id="0ef3f-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="0ef3f-698">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="0ef3f-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-699">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-699">Format</span></span>

<span data-ttu-id="0ef3f-700">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-701">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-701">Pattern</span></span>

<span data-ttu-id="0ef3f-702">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="0ef3f-703">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="0ef3f-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="0ef3f-704">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-705">Checksum</span></span>

<span data-ttu-id="0ef3f-706">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-707">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-707">Definition</span></span>

<span data-ttu-id="0ef3f-708">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-709">L'espressione `Regex_slovakia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-710">Viene trovata una `Keywords_slovakia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-711">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-711">Keywords</span></span>

<span data-ttu-id="0ef3f-712">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-712">| |</span></span>
|<span data-ttu-id="0ef3f-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-714">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-714">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-715">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-715">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-716">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-716">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-717">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-717">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-718">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-718">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-719">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-720">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-721">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-722">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-722">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-723">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-723">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-724">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-724">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-725">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="0ef3f-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="0ef3f-727">Slovenia</span><span class="sxs-lookup"><span data-stu-id="0ef3f-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-728">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-728">Format</span></span>

<span data-ttu-id="0ef3f-729">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="0ef3f-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-730">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-730">Pattern</span></span>

<span data-ttu-id="0ef3f-731">9 cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="0ef3f-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-732">Checksum</span></span>

<span data-ttu-id="0ef3f-733">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-734">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-734">Definition</span></span>

<span data-ttu-id="0ef3f-735">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-736">L'espressione `Regex_slovenia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-737">Viene trovata una `Keywords_slovenia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-738">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-738">Keywords</span></span>

<span data-ttu-id="0ef3f-739">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-739">| |</span></span>
|<span data-ttu-id="0ef3f-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-741">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-741">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-742">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-742">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-743">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-743">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-744">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-744">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-745">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-745">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-746">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-747">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-748">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-749">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-749">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-750">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-750">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-751">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-751">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-752">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="0ef3f-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="0ef3f-754">Spagna</span><span class="sxs-lookup"><span data-stu-id="0ef3f-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-755">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-755">Format</span></span>

<span data-ttu-id="0ef3f-756">Otto cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="0ef3f-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-757">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-757">Pattern</span></span>

<span data-ttu-id="0ef3f-758">Otto cifre seguite da un carattere:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="0ef3f-759">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-759">Eight digits</span></span> 
    
- <span data-ttu-id="0ef3f-760">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="0ef3f-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-761">Checksum</span></span>

<span data-ttu-id="0ef3f-762">Sì</span><span class="sxs-lookup"><span data-stu-id="0ef3f-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-763">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-763">Definition</span></span>

<span data-ttu-id="0ef3f-764">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-765">La funzione `Func_spain_eu_driver's_license_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-766">Viene trovata una `Keywords_spain_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-767">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-767">Keywords</span></span>

<span data-ttu-id="0ef3f-768">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-768">| |</span></span>
|<span data-ttu-id="0ef3f-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-770">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-771">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-771">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-772">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-772">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-773">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-773">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-774">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-774">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-775">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-776">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-777">driver's licence</span></span>  <br/> <span data-ttu-id="0ef3f-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-778">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-779">driving licence</span></span>  <br/> <span data-ttu-id="0ef3f-780">driving license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-780">driving license</span></span>  <br/> <span data-ttu-id="0ef3f-781">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-781">driver licence number</span></span>  <br/> <span data-ttu-id="0ef3f-782">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-782">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-783">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-783">drivers licence number</span></span>  <br/> <span data-ttu-id="0ef3f-784">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-784">drivers license number</span></span>  <br/> <span data-ttu-id="0ef3f-785">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-785">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-786">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-786">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-787">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-787">driving licence number</span></span>  <br/> <span data-ttu-id="0ef3f-788">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-788">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-789">permesso di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-789">driving permit</span></span>  <br/> <span data-ttu-id="0ef3f-790">numero di licenza di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-790">driving permit number</span></span>  <br/> <span data-ttu-id="0ef3f-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="0ef3f-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="0ef3f-792">Permiso conducción</span><span class="sxs-lookup"><span data-stu-id="0ef3f-792">permiso conducción</span></span>  <br/> <span data-ttu-id="0ef3f-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="0ef3f-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="0ef3f-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="0ef3f-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="0ef3f-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="0ef3f-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="0ef3f-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="0ef3f-796">licencia conducir</span></span>  <br/> <span data-ttu-id="0ef3f-797">número de Permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="0ef3f-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="0ef3f-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="0ef3f-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="0ef3f-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="0ef3f-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="0ef3f-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="0ef3f-800">permiso conducir</span></span>  <br/> <span data-ttu-id="0ef3f-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="0ef3f-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="0ef3f-802">El carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="0ef3f-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="0ef3f-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="0ef3f-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="0ef3f-804">Svezia</span><span class="sxs-lookup"><span data-stu-id="0ef3f-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="0ef3f-805">Formato</span><span class="sxs-lookup"><span data-stu-id="0ef3f-805">Format</span></span>

<span data-ttu-id="0ef3f-806">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="0ef3f-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="0ef3f-807">Modello</span><span class="sxs-lookup"><span data-stu-id="0ef3f-807">Pattern</span></span>

<span data-ttu-id="0ef3f-808">Dieci cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="0ef3f-809">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-809">Six digits</span></span> 
    
- <span data-ttu-id="0ef3f-810">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="0ef3f-810">A hyphen</span></span>
    
- <span data-ttu-id="0ef3f-811">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="0ef3f-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="0ef3f-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="0ef3f-812">Checksum</span></span>

<span data-ttu-id="0ef3f-813">No</span><span class="sxs-lookup"><span data-stu-id="0ef3f-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="0ef3f-814">Definizione</span><span class="sxs-lookup"><span data-stu-id="0ef3f-814">Definition</span></span>

<span data-ttu-id="0ef3f-815">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="0ef3f-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="0ef3f-816">L'espressione `Regex_sweden_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="0ef3f-817">Viene trovata una `Keywords_sweden_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="0ef3f-818">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0ef3f-818">Keywords</span></span>

<span data-ttu-id="0ef3f-819">| |</span><span class="sxs-lookup"><span data-stu-id="0ef3f-819">| |</span></span>
|<span data-ttu-id="0ef3f-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="0ef3f-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="0ef3f-821">DL #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-821">dl#</span></span>  <br/> <span data-ttu-id="0ef3f-822">driver license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-822">driver license</span></span>  <br/> <span data-ttu-id="0ef3f-823">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-823">driver license number</span></span>  <br/> <span data-ttu-id="0ef3f-824">patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-824">driver licence</span></span>  <br/> <span data-ttu-id="0ef3f-825">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="0ef3f-825">drivers lic.</span></span>  <br/> <span data-ttu-id="0ef3f-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-826">drivers license</span></span>  <br/> <span data-ttu-id="0ef3f-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="0ef3f-827">drivers licence</span></span>  <br/> <span data-ttu-id="0ef3f-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="0ef3f-828">driver's license</span></span>  <br/> <span data-ttu-id="0ef3f-829">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-829">driver's license number</span></span>  <br/> <span data-ttu-id="0ef3f-830">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="0ef3f-830">driver's licence number</span></span>  <br/> <span data-ttu-id="0ef3f-831">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="0ef3f-831">driving license number</span></span>  <br/> <span data-ttu-id="0ef3f-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="0ef3f-832">dlno#</span></span>  <br/> <span data-ttu-id="0ef3f-833">körkort</span><span class="sxs-lookup"><span data-stu-id="0ef3f-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="0ef3f-834">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="0ef3f-834">UK</span></span>

<span data-ttu-id="0ef3f-835">Per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="0ef3f-835">For details, see the section "U.K.</span></span> <span data-ttu-id="0ef3f-836">Numero della patente di guida "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="0ef3f-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0ef3f-837">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ef3f-837">See also</span></span>

[<span data-ttu-id="0ef3f-838">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="0ef3f-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

