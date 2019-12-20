---
title: Numero della patente di guida dell'Unione europea
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
ms.openlocfilehash: 6df025caf8d06c617e09a3b53dc6c82d69aaf5a8
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805959"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="312ac-104">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="312ac-104">EU Driver's License Number</span></span>

<span data-ttu-id="312ac-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="312ac-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="312ac-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="312ac-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="312ac-107">Austria</span><span class="sxs-lookup"><span data-stu-id="312ac-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="312ac-108">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-108">Format</span></span>

<span data-ttu-id="312ac-109">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="312ac-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-110">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-110">Pattern</span></span>

<span data-ttu-id="312ac-111">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="312ac-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-112">Checksum</span></span>

<span data-ttu-id="312ac-113">No</span><span class="sxs-lookup"><span data-stu-id="312ac-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-114">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-114">Definition</span></span>

<span data-ttu-id="312ac-115">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-116">L'espressione `Regex_austria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-117">Viene trovata una `Keywords_austria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="312ac-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-118">Keywords</span></span>

<span data-ttu-id="312ac-119">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-119"></span></span>
|<span data-ttu-id="312ac-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-121">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-121">dl#</span></span>  <br/> <span data-ttu-id="312ac-122">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-122">driver license</span></span>  <br/> <span data-ttu-id="312ac-123">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-123">driver license number</span></span>  <br/> <span data-ttu-id="312ac-124">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-124">driver licence</span></span>  <br/> <span data-ttu-id="312ac-125">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-125">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-126">drivers license</span></span>  <br/> <span data-ttu-id="312ac-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="312ac-127">driver's licence</span></span>  <br/> <span data-ttu-id="312ac-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-128">driver's license</span></span>  <br/> <span data-ttu-id="312ac-129">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-129">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-130">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="312ac-131">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-131">driving license number</span></span>  <br/> <span data-ttu-id="312ac-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-132">dlno#</span></span>  <br/> <span data-ttu-id="312ac-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="312ac-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="312ac-134">fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="312ac-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="312ac-135">Belgio</span><span class="sxs-lookup"><span data-stu-id="312ac-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="312ac-136">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-136">Format</span></span>

<span data-ttu-id="312ac-137">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="312ac-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-138">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-138">Pattern</span></span>

<span data-ttu-id="312ac-139">10 cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="312ac-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-140">Checksum</span></span>

<span data-ttu-id="312ac-141">No</span><span class="sxs-lookup"><span data-stu-id="312ac-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-142">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-142">Definition</span></span>

<span data-ttu-id="312ac-143">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-144">L'espressione `Regex_belgium_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-145">Viene trovata una `Keywords_belgium_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="312ac-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-146">Keywords</span></span>

<span data-ttu-id="312ac-147">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-147"></span></span>
|<span data-ttu-id="312ac-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-149">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-149">dl#</span></span>  <br/> <span data-ttu-id="312ac-150">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-150">driver license</span></span>  <br/> <span data-ttu-id="312ac-151">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-151">driver license number</span></span>  <br/> <span data-ttu-id="312ac-152">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-152">driver licence</span></span>  <br/> <span data-ttu-id="312ac-153">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-153">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-154">drivers license</span></span>  <br/> <span data-ttu-id="312ac-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-155">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-156">driver's license</span></span>  <br/> <span data-ttu-id="312ac-157">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-157">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-158">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-158">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-159">dlno#</span></span>  <br/> <span data-ttu-id="312ac-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="312ac-160">rijbewijs</span></span>  <br/> <span data-ttu-id="312ac-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="312ac-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="312ac-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="312ac-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="312ac-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="312ac-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="312ac-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="312ac-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="312ac-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="312ac-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="312ac-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="312ac-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="312ac-167">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="312ac-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="312ac-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="312ac-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="312ac-169">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-169">Format</span></span>

<span data-ttu-id="312ac-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="312ac-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-171">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-171">Pattern</span></span>

<span data-ttu-id="312ac-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="312ac-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-173">Checksum</span></span>

<span data-ttu-id="312ac-174">No</span><span class="sxs-lookup"><span data-stu-id="312ac-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-175">Definition</span></span>

<span data-ttu-id="312ac-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-177">L'espressione `Regex_bulgaria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-178">Viene trovata una `Keywords_bulgaria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="312ac-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-179">Keywords</span></span>

<span data-ttu-id="312ac-180">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-180"></span></span>
|<span data-ttu-id="312ac-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-182">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-182">dl#</span></span>  <br/> <span data-ttu-id="312ac-183">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-183">driver license</span></span>  <br/> <span data-ttu-id="312ac-184">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-184">driver license number</span></span>  <br/> <span data-ttu-id="312ac-185">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-185">driver licence</span></span>  <br/> <span data-ttu-id="312ac-186">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-186">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-187">drivers license</span></span>  <br/> <span data-ttu-id="312ac-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-188">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-189">driver's license</span></span>  <br/> <span data-ttu-id="312ac-190">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-190">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-191">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-191">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-192">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-192">driving license number</span></span>  <br/> <span data-ttu-id="312ac-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-193">dlno#</span></span>  <br/> <span data-ttu-id="312ac-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="312ac-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="312ac-195">свидетелство за управление на моторно превозно d'средство</span><span class="sxs-lookup"><span data-stu-id="312ac-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="312ac-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="312ac-196">сумпс</span></span>  <br/> <span data-ttu-id="312ac-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="312ac-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="312ac-198">Croazia</span><span class="sxs-lookup"><span data-stu-id="312ac-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="312ac-199">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-199">Format</span></span>

<span data-ttu-id="312ac-200">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="312ac-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-201">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-201">Pattern</span></span>

<span data-ttu-id="312ac-202">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="312ac-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-203">Checksum</span></span>

<span data-ttu-id="312ac-204">No</span><span class="sxs-lookup"><span data-stu-id="312ac-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-205">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-205">Definition</span></span>

<span data-ttu-id="312ac-206">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-207">L'espressione `Regex_croatia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-208">Viene trovata una `Keywords_croatia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="312ac-209">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-209">Keywords</span></span>

<span data-ttu-id="312ac-210">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-210"></span></span>
|<span data-ttu-id="312ac-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-212">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-212">dl#</span></span>  <br/> <span data-ttu-id="312ac-213">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-213">driver license</span></span>  <br/> <span data-ttu-id="312ac-214">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-214">driver license number</span></span>  <br/> <span data-ttu-id="312ac-215">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-215">driver licence</span></span>  <br/> <span data-ttu-id="312ac-216">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-216">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-217">drivers license</span></span>  <br/> <span data-ttu-id="312ac-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-218">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-219">driver's license</span></span>  <br/> <span data-ttu-id="312ac-220">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-220">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-221">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-221">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-222">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-222">driving license number</span></span>  <br/> <span data-ttu-id="312ac-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-223">dlno#</span></span>  <br/> <span data-ttu-id="312ac-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="312ac-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="312ac-225">Cipro</span><span class="sxs-lookup"><span data-stu-id="312ac-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="312ac-226">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-226">Format</span></span>

<span data-ttu-id="312ac-227">12 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="312ac-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-228">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-228">Pattern</span></span>

<span data-ttu-id="312ac-229">12 cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="312ac-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-230">Checksum</span></span>

<span data-ttu-id="312ac-231">No</span><span class="sxs-lookup"><span data-stu-id="312ac-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-232">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-232">Definition</span></span>

<span data-ttu-id="312ac-233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-234">L'espressione `Regex_cyprus_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-235">Viene trovata una `Keywords_cyprus_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-236">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-236">Keywords</span></span>

<span data-ttu-id="312ac-237">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-237"></span></span>
|<span data-ttu-id="312ac-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-239">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-239">dl#</span></span>  <br/> <span data-ttu-id="312ac-240">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-240">driver license</span></span>  <br/> <span data-ttu-id="312ac-241">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-241">driver license number</span></span>  <br/> <span data-ttu-id="312ac-242">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-242">driver licence</span></span>  <br/> <span data-ttu-id="312ac-243">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-243">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-244">drivers license</span></span>  <br/> <span data-ttu-id="312ac-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-245">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-246">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-246">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-247">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-247">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-248">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-248">driving license number</span></span>  <br/> <span data-ttu-id="312ac-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-249">dlno#</span></span>  <br/> <span data-ttu-id="312ac-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="312ac-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="312ac-251">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="312ac-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="312ac-252">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-252">Format</span></span>

<span data-ttu-id="312ac-253">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-254">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-254">Pattern</span></span>

<span data-ttu-id="312ac-255">Otto lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="312ac-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="312ac-256">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="312ac-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="312ac-257">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="312ac-257">A space (optional)</span></span>
    
- <span data-ttu-id="312ac-258">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="312ac-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-259">Checksum</span></span>

<span data-ttu-id="312ac-260">No</span><span class="sxs-lookup"><span data-stu-id="312ac-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-261">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-261">Definition</span></span>

<span data-ttu-id="312ac-262">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-263">L'espressione `Regex_czech_republic_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-264">Viene trovata una `Keywords_czech_republic_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="312ac-265">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-265">Keywords</span></span>

<span data-ttu-id="312ac-266">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-266"></span></span>
|<span data-ttu-id="312ac-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-268">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-268">dl#</span></span>  <br/> <span data-ttu-id="312ac-269">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-269">driver license</span></span>  <br/> <span data-ttu-id="312ac-270">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-270">driver license number</span></span>  <br/> <span data-ttu-id="312ac-271">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-271">driver licence</span></span>  <br/> <span data-ttu-id="312ac-272">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-272">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-273">drivers license</span></span>  <br/> <span data-ttu-id="312ac-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-274">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-275">driver's license</span></span>  <br/> <span data-ttu-id="312ac-276">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-276">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-277">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-277">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-278">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-278">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-279">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-279">driving license number</span></span>  <br/> <span data-ttu-id="312ac-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-280">dlno#</span></span>  <br/> <span data-ttu-id="312ac-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="312ac-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="312ac-282">Danimarca</span><span class="sxs-lookup"><span data-stu-id="312ac-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="312ac-283">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-283">Format</span></span>

<span data-ttu-id="312ac-284">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="312ac-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-285">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-285">Pattern</span></span>

<span data-ttu-id="312ac-286">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="312ac-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-287">Checksum</span></span>

<span data-ttu-id="312ac-288">Sì</span><span class="sxs-lookup"><span data-stu-id="312ac-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-289">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-289">Definition</span></span>

<span data-ttu-id="312ac-290">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-291">L'espressione `Regex_denmark_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-292">Viene trovata una `Keywords_denmark_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="312ac-293">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-293">Keywords</span></span>

<span data-ttu-id="312ac-294">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-294"></span></span>
|<span data-ttu-id="312ac-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-296">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-296">dl#</span></span>  <br/> <span data-ttu-id="312ac-297">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-297">driver license</span></span>  <br/> <span data-ttu-id="312ac-298">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-298">driver license number</span></span>  <br/> <span data-ttu-id="312ac-299">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-299">driver licence</span></span>  <br/> <span data-ttu-id="312ac-300">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-300">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-301">drivers license</span></span>  <br/> <span data-ttu-id="312ac-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-302">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-303">driver's license</span></span>  <br/> <span data-ttu-id="312ac-304">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-304">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-305">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-305">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-306">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-306">driving license number</span></span>  <br/> <span data-ttu-id="312ac-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-307">dlno#</span></span>  <br/> <span data-ttu-id="312ac-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="312ac-308">kørekort</span></span>  <br/> <span data-ttu-id="312ac-309">Kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="312ac-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="312ac-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="312ac-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="312ac-311">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-311">Format</span></span>

<span data-ttu-id="312ac-312">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-313">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-313">Pattern</span></span>

<span data-ttu-id="312ac-314">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="312ac-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="312ac-315">Lettere "ET" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="312ac-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="312ac-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="312ac-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-317">Checksum</span></span>

<span data-ttu-id="312ac-318">No</span><span class="sxs-lookup"><span data-stu-id="312ac-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-319">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-319">Definition</span></span>

<span data-ttu-id="312ac-320">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-321">L'espressione `Regex_estonia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-322">Viene trovata una `Keywords_estonia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-323">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-323">Keywords</span></span>

<span data-ttu-id="312ac-324">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-324"></span></span>
|<span data-ttu-id="312ac-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-326">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-326">dl#</span></span>  <br/> <span data-ttu-id="312ac-327">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-327">driver license</span></span>  <br/> <span data-ttu-id="312ac-328">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-328">driver license number</span></span>  <br/> <span data-ttu-id="312ac-329">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-329">driver license number</span></span>  <br/> <span data-ttu-id="312ac-330">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-330">driver licence</span></span>  <br/> <span data-ttu-id="312ac-331">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-331">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-332">drivers license</span></span>  <br/> <span data-ttu-id="312ac-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-333">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-334">driver's license</span></span>  <br/> <span data-ttu-id="312ac-335">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-335">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-336">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-336">driving license number</span></span>  <br/> <span data-ttu-id="312ac-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-337">dlno#</span></span>  <br/> <span data-ttu-id="312ac-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="312ac-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="312ac-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="312ac-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="312ac-340">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-340">Format</span></span>

<span data-ttu-id="312ac-341">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="312ac-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-342">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-342">Pattern</span></span>

<span data-ttu-id="312ac-343">10 cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="312ac-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="312ac-344">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-344">Six digits</span></span> 
    
- <span data-ttu-id="312ac-345">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="312ac-345">A hyphen</span></span>
    
-  <span data-ttu-id="312ac-346">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="312ac-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-347">Checksum</span></span>

<span data-ttu-id="312ac-348">No</span><span class="sxs-lookup"><span data-stu-id="312ac-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-349">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-349">Definition</span></span>

<span data-ttu-id="312ac-350">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-351">L'espressione `Regex_finland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-352">Viene trovata una `Keywords_finland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-353">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-353">Keywords</span></span>

<span data-ttu-id="312ac-354">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-354"></span></span>
|<span data-ttu-id="312ac-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-356">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-356">dl#</span></span>  <br/> <span data-ttu-id="312ac-357">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-357">driver license</span></span>  <br/> <span data-ttu-id="312ac-358">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-358">driver license number</span></span>  <br/> <span data-ttu-id="312ac-359">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-359">driver licence</span></span>  <br/> <span data-ttu-id="312ac-360">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-360">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-361">drivers license</span></span>  <br/> <span data-ttu-id="312ac-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-362">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-363">driver's license</span></span>  <br/> <span data-ttu-id="312ac-364">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-364">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-365">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-365">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-366">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-366">driving license number</span></span>  <br/> <span data-ttu-id="312ac-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-367">dlno#</span></span>  <br/> <span data-ttu-id="312ac-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="312ac-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="312ac-369">Francia</span><span class="sxs-lookup"><span data-stu-id="312ac-369">France</span></span>

<span data-ttu-id="312ac-370">Per informazioni dettagliate, vedere la sezione "numero della patente di Francia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="312ac-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="312ac-371">Germania</span><span class="sxs-lookup"><span data-stu-id="312ac-371">Germany</span></span>

<span data-ttu-id="312ac-372">Per informazioni dettagliate, vedere la sezione "numero di patente di guida tedesco" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="312ac-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="312ac-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="312ac-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="312ac-374">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-374">Format</span></span>

<span data-ttu-id="312ac-375">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="312ac-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-376">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-376">Pattern</span></span>

 <span data-ttu-id="312ac-377">9 cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="312ac-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-378">Checksum</span></span>

<span data-ttu-id="312ac-379">No</span><span class="sxs-lookup"><span data-stu-id="312ac-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-380">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-380">Definition</span></span>

<span data-ttu-id="312ac-381">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-382">L'espressione `Regex_greece_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-383">Viene trovata una `Keywords_greece_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-384">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-384">Keywords</span></span>

<span data-ttu-id="312ac-385">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-385"></span></span>
|<span data-ttu-id="312ac-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="312ac-387">dlL#</span></span>  <br/> <span data-ttu-id="312ac-388">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-388">driver license</span></span>  <br/> <span data-ttu-id="312ac-389">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-389">driver license number</span></span>  <br/> <span data-ttu-id="312ac-390">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-390">driver licence</span></span>  <br/> <span data-ttu-id="312ac-391">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-391">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-392">drivers license</span></span>  <br/> <span data-ttu-id="312ac-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-393">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-394">driver's license</span></span>  <br/> <span data-ttu-id="312ac-395">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-395">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-396">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-396">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-397">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-397">driving license number</span></span>  <br/> <span data-ttu-id="312ac-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-398">dlno#</span></span>  <br/> <span data-ttu-id="312ac-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="312ac-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="312ac-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="312ac-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="312ac-401">Ungheria</span><span class="sxs-lookup"><span data-stu-id="312ac-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="312ac-402">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-402">Format</span></span>

<span data-ttu-id="312ac-403">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-404">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-404">Pattern</span></span>

<span data-ttu-id="312ac-405">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="312ac-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="312ac-406">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="312ac-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="312ac-407">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="312ac-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-408">Checksum</span></span>

<span data-ttu-id="312ac-409">No</span><span class="sxs-lookup"><span data-stu-id="312ac-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-410">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-410">Definition</span></span>

<span data-ttu-id="312ac-411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-412">L'espressione `Regex_hungary_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-413">Viene trovata una `Keywords_hungary_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-414">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-414">Keywords</span></span>

<span data-ttu-id="312ac-415">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-415"></span></span>
|<span data-ttu-id="312ac-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-417">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-417">dl#</span></span>  <br/> <span data-ttu-id="312ac-418">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-418">driver license</span></span>  <br/> <span data-ttu-id="312ac-419">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-419">driver license number</span></span>  <br/> <span data-ttu-id="312ac-420">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-420">driver licence</span></span>  <br/> <span data-ttu-id="312ac-421">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-421">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-422">drivers license</span></span>  <br/> <span data-ttu-id="312ac-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-423">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-424">driver's license</span></span>  <br/> <span data-ttu-id="312ac-425">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-425">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-426">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-426">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-427">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-427">driving license number</span></span>  <br/> <span data-ttu-id="312ac-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-428">dlno#</span></span>  <br/> <span data-ttu-id="312ac-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="312ac-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="312ac-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="312ac-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="312ac-431">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-431">Format</span></span>

<span data-ttu-id="312ac-432">Sei cifre seguite da quattro lettere</span><span class="sxs-lookup"><span data-stu-id="312ac-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-433">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-433">Pattern</span></span>

<span data-ttu-id="312ac-434">Sei cifre e quattro lettere:</span><span class="sxs-lookup"><span data-stu-id="312ac-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="312ac-435">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-435">Six digits</span></span>
    
- <span data-ttu-id="312ac-436">Quattro lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="312ac-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="312ac-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-437">Checksum</span></span>

<span data-ttu-id="312ac-438">No</span><span class="sxs-lookup"><span data-stu-id="312ac-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-439">Definition</span></span>

<span data-ttu-id="312ac-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-441">L'espressione `Regex_ireland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-442">Viene trovata una `Keywords_ireland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-443">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-443">Keywords</span></span>

<span data-ttu-id="312ac-444">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-444"></span></span>
|<span data-ttu-id="312ac-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-446">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-446">dl#</span></span>  <br/> <span data-ttu-id="312ac-447">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-447">driver license</span></span>  <br/> <span data-ttu-id="312ac-448">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-448">driver license number</span></span>  <br/> <span data-ttu-id="312ac-449">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-449">driver licence</span></span>  <br/> <span data-ttu-id="312ac-450">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-450">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-451">drivers license</span></span>  <br/> <span data-ttu-id="312ac-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-452">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-453">driver's license</span></span>  <br/> <span data-ttu-id="312ac-454">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-454">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-455">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-455">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-456">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-456">driving license number</span></span>  <br/> <span data-ttu-id="312ac-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-457">dlno#</span></span>  <br/> <span data-ttu-id="312ac-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="312ac-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="312ac-459">Italia</span><span class="sxs-lookup"><span data-stu-id="312ac-459">Italy</span></span>

<span data-ttu-id="312ac-460">Per informazioni dettagliate, vedere la sezione "numero di licenza del conducente italiano" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="312ac-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="312ac-461">Lettonia</span><span class="sxs-lookup"><span data-stu-id="312ac-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="312ac-462">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-462">Format</span></span>

<span data-ttu-id="312ac-463">Tre lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-464">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-464">Pattern</span></span>

<span data-ttu-id="312ac-465">Tre lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="312ac-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="312ac-466">Tre lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="312ac-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="312ac-467">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="312ac-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-468">Checksum</span></span>

<span data-ttu-id="312ac-469">No</span><span class="sxs-lookup"><span data-stu-id="312ac-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-470">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-470">Definition</span></span>

<span data-ttu-id="312ac-471">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-472">L'espressione `Regex_latvia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-473">Viene trovata una `Keywords_latvia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-474">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-474">Keywords</span></span>

<span data-ttu-id="312ac-475">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-475"></span></span>
|<span data-ttu-id="312ac-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-477">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-477">dl#</span></span>  <br/> <span data-ttu-id="312ac-478">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-478">driver license</span></span>  <br/> <span data-ttu-id="312ac-479">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-479">driver license number</span></span>  <br/> <span data-ttu-id="312ac-480">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-480">driver licence</span></span>  <br/> <span data-ttu-id="312ac-481">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-481">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-482">drivers license</span></span>  <br/> <span data-ttu-id="312ac-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-483">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-484">driver's license</span></span>  <br/> <span data-ttu-id="312ac-485">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-485">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-486">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-486">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-487">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-487">driving license number</span></span>  <br/> <span data-ttu-id="312ac-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-488">dlno#</span></span>  <br/> <span data-ttu-id="312ac-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="312ac-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="312ac-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="312ac-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="312ac-491">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-491">Format</span></span>

<span data-ttu-id="312ac-492">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="312ac-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-493">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-493">Pattern</span></span>

 <span data-ttu-id="312ac-494">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="312ac-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-495">Checksum</span></span>

<span data-ttu-id="312ac-496">No</span><span class="sxs-lookup"><span data-stu-id="312ac-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-497">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-497">Definition</span></span>

<span data-ttu-id="312ac-498">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-499">L'espressione `Regex_lithuania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-500">Viene trovata una `Keywords_lithuania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-501">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-501">Keywords</span></span>

<span data-ttu-id="312ac-502">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-502"></span></span>
|<span data-ttu-id="312ac-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-504">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-504">dl#</span></span>  <br/> <span data-ttu-id="312ac-505">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-505">driver license</span></span>  <br/> <span data-ttu-id="312ac-506">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-506">driver license number</span></span>  <br/> <span data-ttu-id="312ac-507">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-507">driver licence</span></span>  <br/> <span data-ttu-id="312ac-508">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-508">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-509">drivers license</span></span>  <br/> <span data-ttu-id="312ac-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-510">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-511">driver's license</span></span>  <br/> <span data-ttu-id="312ac-512">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-512">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-513">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-513">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-514">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-514">driving license number</span></span>  <br/> <span data-ttu-id="312ac-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-515">dlno#</span></span>  <br/> <span data-ttu-id="312ac-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="312ac-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="312ac-517">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="312ac-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="312ac-518">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-518">Format</span></span>

<span data-ttu-id="312ac-519">Sei cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="312ac-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-520">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-520">Pattern</span></span>

 <span data-ttu-id="312ac-521">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="312ac-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-522">Checksum</span></span>

<span data-ttu-id="312ac-523">No</span><span class="sxs-lookup"><span data-stu-id="312ac-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-524">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-524">Definition</span></span>

<span data-ttu-id="312ac-525">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-526">L'espressione `Regex_luxemburg_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-527">Viene trovata una `Keywords_luxemburg_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-528">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-528">Keywords</span></span>

<span data-ttu-id="312ac-529">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-529"></span></span>
|<span data-ttu-id="312ac-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-531">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-531">dl#</span></span>  <br/> <span data-ttu-id="312ac-532">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-532">driver license</span></span>  <br/> <span data-ttu-id="312ac-533">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-533">driver license number</span></span>  <br/> <span data-ttu-id="312ac-534">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-534">driver licence</span></span>  <br/> <span data-ttu-id="312ac-535">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-535">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-536">drivers license</span></span>  <br/> <span data-ttu-id="312ac-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-537">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-538">driver's license</span></span>  <br/> <span data-ttu-id="312ac-539">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-539">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-540">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-540">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-541">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-541">driving license number</span></span>  <br/> <span data-ttu-id="312ac-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-542">dlno#</span></span>  <br/> <span data-ttu-id="312ac-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="312ac-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="312ac-544">Malta</span><span class="sxs-lookup"><span data-stu-id="312ac-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="312ac-545">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-545">Format</span></span>

<span data-ttu-id="312ac-546">Combinazione di due caratteri e di sei cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="312ac-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-547">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-547">Pattern</span></span>

<span data-ttu-id="312ac-548">Combinazione di due caratteri e di sei cifre:</span><span class="sxs-lookup"><span data-stu-id="312ac-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="312ac-549">Due caratteri (cifre o lettere, non con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="312ac-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="312ac-550">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="312ac-550">A space (optional)</span></span>
    
- <span data-ttu-id="312ac-551">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-551">Three digits</span></span>
    
- <span data-ttu-id="312ac-552">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="312ac-552">A space (optional)</span></span>
    
- <span data-ttu-id="312ac-553">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="312ac-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-554">Checksum</span></span>

<span data-ttu-id="312ac-555">No</span><span class="sxs-lookup"><span data-stu-id="312ac-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-556">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-556">Definition</span></span>

<span data-ttu-id="312ac-557">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-558">L'espressione `Regex_malta_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-559">Viene trovata una `Keywords_malta_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-560">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-560">Keywords</span></span>

<span data-ttu-id="312ac-561">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-561"></span></span>
|<span data-ttu-id="312ac-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-563">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-563">dl#</span></span>  <br/> <span data-ttu-id="312ac-564">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-564">driver license</span></span>  <br/> <span data-ttu-id="312ac-565">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-565">driver license number</span></span>  <br/> <span data-ttu-id="312ac-566">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-566">driver licence</span></span>  <br/> <span data-ttu-id="312ac-567">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-567">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-568">drivers license</span></span>  <br/> <span data-ttu-id="312ac-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-569">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-570">driver's license</span></span>  <br/> <span data-ttu-id="312ac-571">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-571">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-572">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-572">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-573">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-573">driving license number</span></span>  <br/> <span data-ttu-id="312ac-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-574">dlno#</span></span>  <br/> <span data-ttu-id="312ac-575">Liċenzja TAS-sewqan</span><span class="sxs-lookup"><span data-stu-id="312ac-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="312ac-576">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="312ac-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="312ac-577">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-577">Format</span></span>

<span data-ttu-id="312ac-578">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="312ac-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-579">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-579">Pattern</span></span>

<span data-ttu-id="312ac-580">10 cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="312ac-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-581">Checksum</span></span>

<span data-ttu-id="312ac-582">No</span><span class="sxs-lookup"><span data-stu-id="312ac-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-583">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-583">Definition</span></span>

<span data-ttu-id="312ac-584">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-585">L'espressione `Regex_netherlands_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-586">Viene trovata una `Keywords_netherlands_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-587">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-587">Keywords</span></span>

<span data-ttu-id="312ac-588">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-588"></span></span>
|<span data-ttu-id="312ac-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-590">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-590">dl#</span></span>  <br/> <span data-ttu-id="312ac-591">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-591">driver license</span></span>  <br/> <span data-ttu-id="312ac-592">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-592">driver license number</span></span>  <br/> <span data-ttu-id="312ac-593">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-593">driver licence</span></span>  <br/> <span data-ttu-id="312ac-594">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-594">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-595">drivers license</span></span>  <br/> <span data-ttu-id="312ac-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-596">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-597">driver's license</span></span>  <br/> <span data-ttu-id="312ac-598">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-598">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-599">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-599">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-600">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-600">driving license number</span></span>  <br/> <span data-ttu-id="312ac-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-601">dlno#</span></span>  <br/> <span data-ttu-id="312ac-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="312ac-602">permis de conduire</span></span>  <br/> <span data-ttu-id="312ac-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="312ac-603">rijbewijs</span></span>  <br/> <span data-ttu-id="312ac-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="312ac-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="312ac-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="312ac-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="312ac-606">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-606">Format</span></span>

<span data-ttu-id="312ac-607">14 cifre contenenti 2 barre</span><span class="sxs-lookup"><span data-stu-id="312ac-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-608">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-608">Pattern</span></span>

<span data-ttu-id="312ac-609">14 cifre e 2 barre:</span><span class="sxs-lookup"><span data-stu-id="312ac-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="312ac-610">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-610">Five digits</span></span> 
    
- <span data-ttu-id="312ac-611">Una barra</span><span class="sxs-lookup"><span data-stu-id="312ac-611">A forward slash</span></span>
    
- <span data-ttu-id="312ac-612">Due cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-612">Two digits</span></span>
    
- <span data-ttu-id="312ac-613">Una barra</span><span class="sxs-lookup"><span data-stu-id="312ac-613">A forward slash</span></span>
    
- <span data-ttu-id="312ac-614">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="312ac-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-615">Checksum</span></span>

<span data-ttu-id="312ac-616">No</span><span class="sxs-lookup"><span data-stu-id="312ac-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-617">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-617">Definition</span></span>

<span data-ttu-id="312ac-618">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-619">L'espressione `Regex_poland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-620">Viene trovata una `Keywords_poland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-621">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-621">Keywords</span></span>

<span data-ttu-id="312ac-622">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-622"></span></span>
|<span data-ttu-id="312ac-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-624">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-624">dl#</span></span>  <br/> <span data-ttu-id="312ac-625">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-625">driver license</span></span>  <br/> <span data-ttu-id="312ac-626">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-626">driver license number</span></span>  <br/> <span data-ttu-id="312ac-627">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-627">driver licence</span></span>  <br/> <span data-ttu-id="312ac-628">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-628">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-629">drivers license</span></span>  <br/> <span data-ttu-id="312ac-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-630">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-631">driver's license</span></span>  <br/> <span data-ttu-id="312ac-632">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-632">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-633">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-633">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-634">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-634">driving license number</span></span>  <br/> <span data-ttu-id="312ac-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-635">dlno#</span></span>  <br/> <span data-ttu-id="312ac-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="312ac-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="312ac-637">Portogallo</span><span class="sxs-lookup"><span data-stu-id="312ac-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="312ac-638">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-638">Format</span></span>

<span data-ttu-id="312ac-639">Due lettere seguite da un numero di sette numeri nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="312ac-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-640">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-640">Pattern</span></span>

<span data-ttu-id="312ac-641">Due lettere seguite da sette numeri con caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="312ac-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="312ac-642">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="312ac-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="312ac-643">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="312ac-643">A hyphen</span></span>
    
- <span data-ttu-id="312ac-644">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-644">Six digits</span></span>
    
- <span data-ttu-id="312ac-645">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="312ac-645">A space</span></span>
    
- <span data-ttu-id="312ac-646">Una cifra</span><span class="sxs-lookup"><span data-stu-id="312ac-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="312ac-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-647">Checksum</span></span>

<span data-ttu-id="312ac-648">No</span><span class="sxs-lookup"><span data-stu-id="312ac-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-649">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-649">Definition</span></span>

<span data-ttu-id="312ac-650">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-651">L'espressione `Regex_portugal_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-652">Viene trovata una `Keywords_portugal_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-653">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-653">Keywords</span></span>

<span data-ttu-id="312ac-654">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-654"></span></span>
|<span data-ttu-id="312ac-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-656">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-656">dl#</span></span>  <br/> <span data-ttu-id="312ac-657">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-657">driver license</span></span>  <br/> <span data-ttu-id="312ac-658">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-658">driver license number</span></span>  <br/> <span data-ttu-id="312ac-659">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-659">driver licence</span></span>  <br/> <span data-ttu-id="312ac-660">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-660">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-661">drivers license</span></span>  <br/> <span data-ttu-id="312ac-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-662">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-663">driver's license</span></span>  <br/> <span data-ttu-id="312ac-664">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-664">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-665">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-665">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-666">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-666">driving license number</span></span>  <br/> <span data-ttu-id="312ac-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-667">dlno#</span></span>  <br/> <span data-ttu-id="312ac-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="312ac-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="312ac-669">Romania</span><span class="sxs-lookup"><span data-stu-id="312ac-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="312ac-670">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-670">Format</span></span>

<span data-ttu-id="312ac-671">Un carattere seguito da otto cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-672">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-672">Pattern</span></span>

<span data-ttu-id="312ac-673">Un carattere seguito da otto cifre:</span><span class="sxs-lookup"><span data-stu-id="312ac-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="312ac-674">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="312ac-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="312ac-675">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="312ac-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-676">Checksum</span></span>

<span data-ttu-id="312ac-677">No</span><span class="sxs-lookup"><span data-stu-id="312ac-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-678">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-678">Definition</span></span>

<span data-ttu-id="312ac-679">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-680">L'espressione `Regex_romania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-681">Viene trovata una `Keywords_romania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-682">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-682">Keywords</span></span>

<span data-ttu-id="312ac-683">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-683"></span></span>
|<span data-ttu-id="312ac-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-685">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-685">dl#</span></span>  <br/> <span data-ttu-id="312ac-686">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-686">driver license</span></span>  <br/> <span data-ttu-id="312ac-687">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-687">driver license number</span></span>  <br/> <span data-ttu-id="312ac-688">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-688">driver licence</span></span>  <br/> <span data-ttu-id="312ac-689">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-689">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-690">drivers license</span></span>  <br/> <span data-ttu-id="312ac-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-691">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-692">driver's license</span></span>  <br/> <span data-ttu-id="312ac-693">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-693">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-694">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-694">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-695">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-695">driving license number</span></span>  <br/> <span data-ttu-id="312ac-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-696">dlno#</span></span>  <br/> <span data-ttu-id="312ac-697">Permis de conducere</span><span class="sxs-lookup"><span data-stu-id="312ac-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="312ac-698">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="312ac-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="312ac-699">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-699">Format</span></span>

<span data-ttu-id="312ac-700">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-701">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-701">Pattern</span></span>

<span data-ttu-id="312ac-702">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="312ac-703">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="312ac-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="312ac-704">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="312ac-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-705">Checksum</span></span>

<span data-ttu-id="312ac-706">No</span><span class="sxs-lookup"><span data-stu-id="312ac-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-707">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-707">Definition</span></span>

<span data-ttu-id="312ac-708">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-709">L'espressione `Regex_slovakia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-710">Viene trovata una `Keywords_slovakia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-711">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-711">Keywords</span></span>

<span data-ttu-id="312ac-712">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-712"></span></span>
|<span data-ttu-id="312ac-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-714">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-714">dl#</span></span>  <br/> <span data-ttu-id="312ac-715">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-715">driver license</span></span>  <br/> <span data-ttu-id="312ac-716">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-716">driver license number</span></span>  <br/> <span data-ttu-id="312ac-717">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-717">driver licence</span></span>  <br/> <span data-ttu-id="312ac-718">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-718">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-719">drivers license</span></span>  <br/> <span data-ttu-id="312ac-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-720">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-721">driver's license</span></span>  <br/> <span data-ttu-id="312ac-722">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-722">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-723">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-723">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-724">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-724">driving license number</span></span>  <br/> <span data-ttu-id="312ac-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-725">dlno#</span></span>  <br/> <span data-ttu-id="312ac-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="312ac-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="312ac-727">Slovenia</span><span class="sxs-lookup"><span data-stu-id="312ac-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="312ac-728">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-728">Format</span></span>

<span data-ttu-id="312ac-729">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="312ac-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-730">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-730">Pattern</span></span>

<span data-ttu-id="312ac-731">9 cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="312ac-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-732">Checksum</span></span>

<span data-ttu-id="312ac-733">No</span><span class="sxs-lookup"><span data-stu-id="312ac-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-734">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-734">Definition</span></span>

<span data-ttu-id="312ac-735">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-736">L'espressione `Regex_slovenia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-737">Viene trovata una `Keywords_slovenia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-738">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-738">Keywords</span></span>

<span data-ttu-id="312ac-739">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-739"></span></span>
|<span data-ttu-id="312ac-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-741">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-741">dl#</span></span>  <br/> <span data-ttu-id="312ac-742">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-742">driver license</span></span>  <br/> <span data-ttu-id="312ac-743">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-743">driver license number</span></span>  <br/> <span data-ttu-id="312ac-744">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-744">driver licence</span></span>  <br/> <span data-ttu-id="312ac-745">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-745">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-746">drivers license</span></span>  <br/> <span data-ttu-id="312ac-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-747">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-748">driver's license</span></span>  <br/> <span data-ttu-id="312ac-749">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-749">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-750">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-750">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-751">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-751">driving license number</span></span>  <br/> <span data-ttu-id="312ac-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-752">dlno#</span></span>  <br/> <span data-ttu-id="312ac-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="312ac-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="312ac-754">Spagna</span><span class="sxs-lookup"><span data-stu-id="312ac-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="312ac-755">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-755">Format</span></span>

<span data-ttu-id="312ac-756">Otto cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="312ac-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-757">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-757">Pattern</span></span>

<span data-ttu-id="312ac-758">Otto cifre seguite da un carattere:</span><span class="sxs-lookup"><span data-stu-id="312ac-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="312ac-759">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-759">Eight digits</span></span> 
    
- <span data-ttu-id="312ac-760">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="312ac-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="312ac-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-761">Checksum</span></span>

<span data-ttu-id="312ac-762">Sì</span><span class="sxs-lookup"><span data-stu-id="312ac-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-763">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-763">Definition</span></span>

<span data-ttu-id="312ac-764">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-765">La funzione `Func_spain_eu_driver's_license_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-766">Viene trovata una `Keywords_spain_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="312ac-767">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-767">Keywords</span></span>

<span data-ttu-id="312ac-768">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-768"></span></span>
|<span data-ttu-id="312ac-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-770">dlno#</span></span>  <br/> <span data-ttu-id="312ac-771">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-771">dl#</span></span>  <br/> <span data-ttu-id="312ac-772">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-772">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-773">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-773">driver licence</span></span>  <br/> <span data-ttu-id="312ac-774">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-774">driver license</span></span>  <br/> <span data-ttu-id="312ac-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-775">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-776">drivers license</span></span>  <br/> <span data-ttu-id="312ac-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="312ac-777">driver's licence</span></span>  <br/> <span data-ttu-id="312ac-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-778">driver's license</span></span>  <br/> <span data-ttu-id="312ac-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="312ac-779">driving licence</span></span>  <br/> <span data-ttu-id="312ac-780">driving license</span><span class="sxs-lookup"><span data-stu-id="312ac-780">driving license</span></span>  <br/> <span data-ttu-id="312ac-781">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-781">driver licence number</span></span>  <br/> <span data-ttu-id="312ac-782">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-782">driver license number</span></span>  <br/> <span data-ttu-id="312ac-783">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-783">drivers licence number</span></span>  <br/> <span data-ttu-id="312ac-784">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-784">drivers license number</span></span>  <br/> <span data-ttu-id="312ac-785">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-785">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-786">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-786">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-787">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-787">driving licence number</span></span>  <br/> <span data-ttu-id="312ac-788">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-788">driving license number</span></span>  <br/> <span data-ttu-id="312ac-789">permesso di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-789">driving permit</span></span>  <br/> <span data-ttu-id="312ac-790">numero di licenza di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-790">driving permit number</span></span>  <br/> <span data-ttu-id="312ac-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="312ac-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="312ac-792">Permiso conducción</span><span class="sxs-lookup"><span data-stu-id="312ac-792">permiso conducción</span></span>  <br/> <span data-ttu-id="312ac-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="312ac-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="312ac-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="312ac-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="312ac-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="312ac-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="312ac-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="312ac-796">licencia conducir</span></span>  <br/> <span data-ttu-id="312ac-797">número de Permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="312ac-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="312ac-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="312ac-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="312ac-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="312ac-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="312ac-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="312ac-800">permiso conducir</span></span>  <br/> <span data-ttu-id="312ac-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="312ac-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="312ac-802">El carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="312ac-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="312ac-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="312ac-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="312ac-804">Svezia</span><span class="sxs-lookup"><span data-stu-id="312ac-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="312ac-805">Formato</span><span class="sxs-lookup"><span data-stu-id="312ac-805">Format</span></span>

<span data-ttu-id="312ac-806">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="312ac-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="312ac-807">Modello</span><span class="sxs-lookup"><span data-stu-id="312ac-807">Pattern</span></span>

<span data-ttu-id="312ac-808">Dieci cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="312ac-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="312ac-809">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-809">Six digits</span></span> 
    
- <span data-ttu-id="312ac-810">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="312ac-810">A hyphen</span></span>
    
- <span data-ttu-id="312ac-811">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="312ac-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="312ac-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="312ac-812">Checksum</span></span>

<span data-ttu-id="312ac-813">No</span><span class="sxs-lookup"><span data-stu-id="312ac-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="312ac-814">Definizione</span><span class="sxs-lookup"><span data-stu-id="312ac-814">Definition</span></span>

<span data-ttu-id="312ac-815">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="312ac-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="312ac-816">L'espressione `Regex_sweden_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="312ac-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="312ac-817">Viene trovata una `Keywords_sweden_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="312ac-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="312ac-818">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="312ac-818">Keywords</span></span>

<span data-ttu-id="312ac-819">| |</span><span class="sxs-lookup"><span data-stu-id="312ac-819"></span></span>
|<span data-ttu-id="312ac-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="312ac-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="312ac-821">DL #</span><span class="sxs-lookup"><span data-stu-id="312ac-821">dl#</span></span>  <br/> <span data-ttu-id="312ac-822">driver license</span><span class="sxs-lookup"><span data-stu-id="312ac-822">driver license</span></span>  <br/> <span data-ttu-id="312ac-823">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-823">driver license number</span></span>  <br/> <span data-ttu-id="312ac-824">patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-824">driver licence</span></span>  <br/> <span data-ttu-id="312ac-825">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="312ac-825">drivers lic.</span></span>  <br/> <span data-ttu-id="312ac-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="312ac-826">drivers license</span></span>  <br/> <span data-ttu-id="312ac-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="312ac-827">drivers licence</span></span>  <br/> <span data-ttu-id="312ac-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="312ac-828">driver's license</span></span>  <br/> <span data-ttu-id="312ac-829">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-829">driver's license number</span></span>  <br/> <span data-ttu-id="312ac-830">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="312ac-830">driver's licence number</span></span>  <br/> <span data-ttu-id="312ac-831">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="312ac-831">driving license number</span></span>  <br/> <span data-ttu-id="312ac-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="312ac-832">dlno#</span></span>  <br/> <span data-ttu-id="312ac-833">körkort</span><span class="sxs-lookup"><span data-stu-id="312ac-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="312ac-834">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="312ac-834">UK</span></span>

<span data-ttu-id="312ac-835">Per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="312ac-835">For details, see the section "U.K.</span></span> <span data-ttu-id="312ac-836">Numero della patente di guida "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="312ac-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="312ac-837">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="312ac-837">See also</span></span>

[<span data-ttu-id="312ac-838">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="312ac-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

