---
title: Numero di identificazione nazionale dell'Unione europea
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
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione nazionale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: c83644fc8870975634651e44e114f2a8e0cf7692
ms.sourcegitcommit: a2dd93943f68362220b123e3e4b0f7b3facbdd03
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "43955303"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="d60ef-104">Numero di identificazione nazionale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="d60ef-104">EU National Identification Number</span></span>

<span data-ttu-id="d60ef-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione nazionale dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="d60ef-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="d60ef-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="d60ef-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="d60ef-107">Austria</span><span class="sxs-lookup"><span data-stu-id="d60ef-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-108">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-108">Format</span></span>

<span data-ttu-id="d60ef-109">Combinazione a 24 caratteri di lettere, cifre e caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="d60ef-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-110">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-110">Pattern</span></span>

<span data-ttu-id="d60ef-111">24 caratteri:</span><span class="sxs-lookup"><span data-stu-id="d60ef-111">24 characters:</span></span>
  
-  <span data-ttu-id="d60ef-112">22 lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre o segni più</span><span class="sxs-lookup"><span data-stu-id="d60ef-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="d60ef-113">Due lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre, segni più o segni uguali</span><span class="sxs-lookup"><span data-stu-id="d60ef-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-114">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-114">Checksum</span></span>

<span data-ttu-id="d60ef-115">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d60ef-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-116">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-116">Definition</span></span>

<span data-ttu-id="d60ef-117">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-118">L'espressione `Regex_austria_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-119">Viene trovata una `Keywords_austria_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-120">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-120">Keywords</span></span>

#### <a name="keywords_austria_eu_national_id_card"></a><span data-ttu-id="d60ef-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-122">numero d'identità austriaco</span><span class="sxs-lookup"><span data-stu-id="d60ef-122">austrian identity number</span></span>
  
<span data-ttu-id="d60ef-123">numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="d60ef-123">national identity number</span></span>
  
<span data-ttu-id="d60ef-124">numero di identità</span><span class="sxs-lookup"><span data-stu-id="d60ef-124">identity number</span></span>
  
<span data-ttu-id="d60ef-125">national id</span><span class="sxs-lookup"><span data-stu-id="d60ef-125">national id</span></span>
  
<span data-ttu-id="d60ef-126">Personalausweis Republik Österreich</span><span class="sxs-lookup"><span data-stu-id="d60ef-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="d60ef-127">Belgio</span><span class="sxs-lookup"><span data-stu-id="d60ef-127">Belgium</span></span>

<span data-ttu-id="d60ef-128">Per informazioni dettagliate, vedere la sezione "numero nazionale belga" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d60ef-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="d60ef-129">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="d60ef-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-130">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-130">Format</span></span>

<span data-ttu-id="d60ef-131">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="d60ef-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-132">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-132">Pattern</span></span>

<span data-ttu-id="d60ef-133">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="d60ef-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="d60ef-134">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="d60ef-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="d60ef-135">Due cifre che corrispondono all'ordine di nascita</span><span class="sxs-lookup"><span data-stu-id="d60ef-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="d60ef-136">Una cifra che corrisponde al sesso: una cifra pari per il maschio e una cifra dispari per la femmina</span><span class="sxs-lookup"><span data-stu-id="d60ef-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="d60ef-137">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="d60ef-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-138">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-138">Checksum</span></span>

<span data-ttu-id="d60ef-139">Sì</span><span class="sxs-lookup"><span data-stu-id="d60ef-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-140">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-140">Definition</span></span>

<span data-ttu-id="d60ef-141">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-142">La funzione `Func_bulgaria_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-142">The function  `Func_bulgaria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-143">Viene trovata una `Keywords_bulgaria_national_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="d60ef-144">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-145">La funzione `Func_bulgaria_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-145">The function  `Func_bulgaria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-146">Keywords</span></span>

#### <a name="keywords_bulgaria_national_number"></a><span data-ttu-id="d60ef-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="d60ef-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="d60ef-148">EGN</span><span class="sxs-lookup"><span data-stu-id="d60ef-148">egn</span></span>
  
<span data-ttu-id="d60ef-149">EGN #</span><span class="sxs-lookup"><span data-stu-id="d60ef-149">egn#</span></span>
  
<span data-ttu-id="d60ef-150">numero nazionale bulgaro</span><span class="sxs-lookup"><span data-stu-id="d60ef-150">bulgarian national number</span></span>
  
<span data-ttu-id="d60ef-151">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="d60ef-151">national number</span></span>
  
<span data-ttu-id="d60ef-152">social security number</span><span class="sxs-lookup"><span data-stu-id="d60ef-152">social security number</span></span>
  
<span data-ttu-id="d60ef-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="d60ef-153">nationalnumber#</span></span>
  
<span data-ttu-id="d60ef-154">SSN #</span><span class="sxs-lookup"><span data-stu-id="d60ef-154">ssn#</span></span>
  
<span data-ttu-id="d60ef-155">SSN</span><span class="sxs-lookup"><span data-stu-id="d60ef-155">ssn</span></span>
  
<span data-ttu-id="d60ef-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="d60ef-156">nationalnumber</span></span>
  
<span data-ttu-id="d60ef-157">BNN #</span><span class="sxs-lookup"><span data-stu-id="d60ef-157">bnn#</span></span>
  
<span data-ttu-id="d60ef-158">BNN</span><span class="sxs-lookup"><span data-stu-id="d60ef-158">bnn</span></span>
  
<span data-ttu-id="d60ef-159">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-159">personal id number</span></span>
  
<span data-ttu-id="d60ef-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d60ef-160">personalidnumber#</span></span>
  
<span data-ttu-id="d60ef-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="d60ef-161">единен граждански номер</span></span>
  
<span data-ttu-id="d60ef-162">grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="d60ef-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="d60ef-163">егн</span><span class="sxs-lookup"><span data-stu-id="d60ef-163">егн</span></span>
  
<span data-ttu-id="d60ef-164">егн #</span><span class="sxs-lookup"><span data-stu-id="d60ef-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="d60ef-165">Croazia</span><span class="sxs-lookup"><span data-stu-id="d60ef-165">Croatia</span></span>

<span data-ttu-id="d60ef-166">Per informazioni dettagliate, vedere la sezione "numero di identità della Croazia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d60ef-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="d60ef-167">Cipro</span><span class="sxs-lookup"><span data-stu-id="d60ef-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-168">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-168">Format</span></span>

<span data-ttu-id="d60ef-169">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="d60ef-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-170">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-170">Pattern</span></span>

 <span data-ttu-id="d60ef-171">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="d60ef-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d60ef-172">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-172">Checksum</span></span>

<span data-ttu-id="d60ef-173">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d60ef-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-174">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-174">Definition</span></span>

<span data-ttu-id="d60ef-175">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-176">L'espressione `Regex_cyprus_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-177">Viene trovata una `Keywords_cyprus_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-178">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-178">Keywords</span></span>

#### <a name="keywords_cyprus_eu_national_id_card"></a><span data-ttu-id="d60ef-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-180">numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="d60ef-180">id card number</span></span>
  
<span data-ttu-id="d60ef-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="d60ef-181">national identification number</span></span>
  
<span data-ttu-id="d60ef-182">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-182">personal id number</span></span>
  
<span data-ttu-id="d60ef-183">numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="d60ef-183">identity card number</span></span>
  
<span data-ttu-id="d60ef-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="d60ef-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="d60ef-185">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="d60ef-185">Czech Republic</span></span>

<span data-ttu-id="d60ef-186">Per informazioni dettagliate, vedere la sezione "numero di identità nazionale ceco" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d60ef-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="d60ef-187">Danimarca</span><span class="sxs-lookup"><span data-stu-id="d60ef-187">Denmark</span></span>

<span data-ttu-id="d60ef-188">Per informazioni dettagliate, vedere la sezione "numero di identificazione personale danese" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d60ef-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="d60ef-189">Estonia</span><span class="sxs-lookup"><span data-stu-id="d60ef-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-190">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-190">Format</span></span>

<span data-ttu-id="d60ef-191">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="d60ef-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-192">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-192">Pattern</span></span>

<span data-ttu-id="d60ef-193">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="d60ef-193">11 digits:</span></span>
  
- <span data-ttu-id="d60ef-194">Una cifra che corrisponde al sesso e al secolo di nascita (numero dispari maschio, anche numero femmina; 1-2: XIX secolo; 3-4: XX secolo; 5-6: XXI secolo)</span><span class="sxs-lookup"><span data-stu-id="d60ef-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="d60ef-195">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="d60ef-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="d60ef-196">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="d60ef-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="d60ef-197">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="d60ef-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-198">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-198">Checksum</span></span>

<span data-ttu-id="d60ef-199">Sì</span><span class="sxs-lookup"><span data-stu-id="d60ef-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-200">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-200">Definition</span></span>

<span data-ttu-id="d60ef-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-202">La funzione `Func_estonia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-203">Viene trovata una `Keywords_estonia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d60ef-204">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-205">La funzione `Func_estonia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-206">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-206">Keywords</span></span>

#### <a name="keywords_estonia_eu_national_id_card"></a><span data-ttu-id="d60ef-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-208">codice di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-208">personal identification code</span></span>
  
<span data-ttu-id="d60ef-209">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-209">personal identification number</span></span>
  
<span data-ttu-id="d60ef-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="d60ef-210">national identification number</span></span>
  
<span data-ttu-id="d60ef-211">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="d60ef-211">national number</span></span>
  
<span data-ttu-id="d60ef-212">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-212">personal id number</span></span>
  
<span data-ttu-id="d60ef-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d60ef-213">personalidnumber#</span></span>
  
<span data-ttu-id="d60ef-214">IK</span><span class="sxs-lookup"><span data-stu-id="d60ef-214">ik</span></span>
  
<span data-ttu-id="d60ef-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="d60ef-215">isikukood</span></span>
  
<span data-ttu-id="d60ef-216">ID-kaart</span><span class="sxs-lookup"><span data-stu-id="d60ef-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="d60ef-217">Finlandia</span><span class="sxs-lookup"><span data-stu-id="d60ef-217">Finland</span></span>

<span data-ttu-id="d60ef-218">Per informazioni dettagliate, vedere la sezione "Finlandia National ID" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d60ef-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="d60ef-219">Francia</span><span class="sxs-lookup"><span data-stu-id="d60ef-219">France</span></span>

<span data-ttu-id="d60ef-220">Per informazioni dettagliate, vedere la sezione "Francia National ID Card (CNI)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d60ef-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="d60ef-221">Germania</span><span class="sxs-lookup"><span data-stu-id="d60ef-221">Germany</span></span>

<span data-ttu-id="d60ef-222">Per informazioni dettagliate, vedere la sezione "Germania identità numero di carta" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d60ef-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="d60ef-223">Grecia</span><span class="sxs-lookup"><span data-stu-id="d60ef-223">Greece</span></span>

<span data-ttu-id="d60ef-224">Per informazioni dettagliate, vedere la sezione "Grecia National ID Card" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d60ef-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="d60ef-225">Ungheria</span><span class="sxs-lookup"><span data-stu-id="d60ef-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-226">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-226">Format</span></span>

<span data-ttu-id="d60ef-227">11 cifre</span><span class="sxs-lookup"><span data-stu-id="d60ef-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-228">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-228">Pattern</span></span>

<span data-ttu-id="d60ef-229">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="d60ef-229">11 digits:</span></span>
  
-  <span data-ttu-id="d60ef-230">Una cifra che corrisponde al sesso (1-maschio, 2-Femmina, altri numeri sono possibili anche per i cittadini nati prima del 1900 o cittadini con doppia cittadinanza)</span><span class="sxs-lookup"><span data-stu-id="d60ef-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="d60ef-231">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="d60ef-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="d60ef-232">Tre cifre che corrispondono a un numero di serie</span><span class="sxs-lookup"><span data-stu-id="d60ef-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="d60ef-233">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="d60ef-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-234">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-234">Checksum</span></span>

<span data-ttu-id="d60ef-235">Sì</span><span class="sxs-lookup"><span data-stu-id="d60ef-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-236">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-236">Definition</span></span>

<span data-ttu-id="d60ef-237">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-238">La funzione `Func_hungary_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-239">Viene trovata una `Keywords_hungary_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d60ef-240">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-241">La funzione `Func_hungary_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-242">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-242">Keywords</span></span>

#### <a name="keywords_hungary_eu_national_id_card"></a><span data-ttu-id="d60ef-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-244">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-244">personal identification number</span></span>
  
<span data-ttu-id="d60ef-245">identification number</span><span class="sxs-lookup"><span data-stu-id="d60ef-245">identification number</span></span>
  
<span data-ttu-id="d60ef-246">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-246">personal id number</span></span>
  
<span data-ttu-id="d60ef-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="d60ef-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="d60ef-248">Irlanda</span><span class="sxs-lookup"><span data-stu-id="d60ef-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-249">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-249">Format</span></span>

<span data-ttu-id="d60ef-250">Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="d60ef-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-251">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-251">Pattern</span></span>

<span data-ttu-id="d60ef-252">Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="d60ef-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="d60ef-253">Dal 01 gennaio 2013 a oggi:</span><span class="sxs-lookup"><span data-stu-id="d60ef-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="d60ef-254">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="d60ef-254">Seven digits</span></span> 
    
- <span data-ttu-id="d60ef-255">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="d60ef-255">One check digit</span></span>
    
- <span data-ttu-id="d60ef-256">Uno spazio o la lettera maiuscola "W" (distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="d60ef-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="d60ef-257">Prima del 1 ° gennaio 2013:</span><span class="sxs-lookup"><span data-stu-id="d60ef-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="d60ef-258">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="d60ef-258">Seven digits</span></span> 
    
- <span data-ttu-id="d60ef-259">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="d60ef-259">One check digit</span></span>
    
- <span data-ttu-id="d60ef-260">Uno spazio o una lettera maiuscola (distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="d60ef-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-261">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-261">Checksum</span></span>

<span data-ttu-id="d60ef-262">Sì</span><span class="sxs-lookup"><span data-stu-id="d60ef-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-263">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-263">Definition</span></span>

<span data-ttu-id="d60ef-264">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-265">La funzione trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="d60ef-266">Viene trovata una parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-266">A keyword from is found.</span></span>
    
<span data-ttu-id="d60ef-267">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-268">La funzione trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-268">The function finds content that matches the pattern.</span></span>
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-269">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-269">Keywords</span></span>

#### <a name="keywords_ireland_eu_national_id_card"></a><span data-ttu-id="d60ef-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-271">numero di servizio pubblico personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-271">personal public service number</span></span>
  
<span data-ttu-id="d60ef-272">PPS No</span><span class="sxs-lookup"><span data-stu-id="d60ef-272">pps no</span></span>
  
<span data-ttu-id="d60ef-273">reddito e numero di previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="d60ef-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="d60ef-274">RSI No</span><span class="sxs-lookup"><span data-stu-id="d60ef-274">rsi no</span></span>
  
<span data-ttu-id="d60ef-275">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-275">personal identification number</span></span>
  
<span data-ttu-id="d60ef-276">identification number</span><span class="sxs-lookup"><span data-stu-id="d60ef-276">identification number</span></span>
  
<span data-ttu-id="d60ef-277">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-277">personal id number</span></span>
  
<span data-ttu-id="d60ef-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="d60ef-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="d60ef-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="d60ef-279">uimh.</span></span> <span data-ttu-id="d60ef-280">PSP</span><span class="sxs-lookup"><span data-stu-id="d60ef-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="d60ef-281">Italia</span><span class="sxs-lookup"><span data-stu-id="d60ef-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-282">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-282">Format</span></span>

<span data-ttu-id="d60ef-283">Una combinazione di 16 caratteri di lettere e cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="d60ef-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-284">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-284">Pattern</span></span>

<span data-ttu-id="d60ef-285">Combinazione di lettere e cifre di 16 caratteri:</span><span class="sxs-lookup"><span data-stu-id="d60ef-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="d60ef-286">Tre lettere che corrispondono alle prime tre consonanti del nome di famiglia</span><span class="sxs-lookup"><span data-stu-id="d60ef-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="d60ef-287">Tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome</span><span class="sxs-lookup"><span data-stu-id="d60ef-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="d60ef-288">Due cifre che corrispondono alle ultime cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="d60ef-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="d60ef-289">Una lettera che corrisponde alla lettera per il mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)</span><span class="sxs-lookup"><span data-stu-id="d60ef-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="d60ef-290">Due cifre che corrispondono al giorno del mese di nascita, al fine di distinguere tra i sessi, 40 viene aggiunto al giorno di nascita per le donne</span><span class="sxs-lookup"><span data-stu-id="d60ef-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="d60ef-291">Quattro cifre che corrispondono al codice di area specifico per il comune in cui è nata la persona (i codici a livello nazionale vengono utilizzati per i paesi esteri)</span><span class="sxs-lookup"><span data-stu-id="d60ef-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="d60ef-292">Una cifra di parità</span><span class="sxs-lookup"><span data-stu-id="d60ef-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-293">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-293">Checksum</span></span>

<span data-ttu-id="d60ef-294">Sì</span><span class="sxs-lookup"><span data-stu-id="d60ef-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-295">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-295">Definition</span></span>

<span data-ttu-id="d60ef-296">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-297">La funzione `Func_italy_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-298">Viene trovata una `Keywords_italy_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d60ef-299">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-300">La funzione `Func_italy_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-301">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-301">Keywords</span></span>

#### <a name="keywords_italy_eu_national_id_card"></a><span data-ttu-id="d60ef-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-303">codice personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-303">personal code</span></span>
  
<span data-ttu-id="d60ef-304">numero di codice personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-304">personal code number</span></span>
  
<span data-ttu-id="d60ef-305">numero di certificato personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-305">personal certificate number</span></span>
  
<span data-ttu-id="d60ef-306">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="d60ef-306">fiscal code</span></span>
  
<span data-ttu-id="d60ef-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="d60ef-307">personalcodeno#</span></span>
  
<span data-ttu-id="d60ef-308">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-308">personal id number</span></span>
  
<span data-ttu-id="d60ef-309">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-309">personal id code</span></span>
  
<span data-ttu-id="d60ef-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-310">codice personale</span></span>
  
<span data-ttu-id="d60ef-311">Numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-311">numero certificato personale</span></span>
  
<span data-ttu-id="d60ef-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-312">numero personale</span></span>
  
<span data-ttu-id="d60ef-313">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-313">numero id personale</span></span>
  
<span data-ttu-id="d60ef-314">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-314">codice id personale</span></span>
  
<span data-ttu-id="d60ef-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="d60ef-315">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="d60ef-316">Lettonia</span><span class="sxs-lookup"><span data-stu-id="d60ef-316">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-317">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-317">Format</span></span>

<span data-ttu-id="d60ef-318">11 cifre e un trattino nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="d60ef-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-319">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-319">Pattern</span></span>

<span data-ttu-id="d60ef-320">11 cifre e un trattino:</span><span class="sxs-lookup"><span data-stu-id="d60ef-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="d60ef-321">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="d60ef-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="d60ef-322">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="d60ef-322">A hyphen</span></span>
    
- <span data-ttu-id="d60ef-323">Una cifra che corrisponde al secolo di nascita ("0" per il XIX secolo, "1" per il XX secolo e "2" per il XXI secolo)</span><span class="sxs-lookup"><span data-stu-id="d60ef-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="d60ef-324">Quattro cifre, generate in modo casuale</span><span class="sxs-lookup"><span data-stu-id="d60ef-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-325">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-325">Checksum</span></span>

<span data-ttu-id="d60ef-326">Sì</span><span class="sxs-lookup"><span data-stu-id="d60ef-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-327">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-327">Definition</span></span>

<span data-ttu-id="d60ef-328">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-329">La funzione `Func_latvia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-330">Viene trovata una `Keywords_latvia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d60ef-331">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-332">La funzione `Func_latvia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-333">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-333">Keywords</span></span>

#### <a name="keywords_latvia_eu_national_id_card"></a><span data-ttu-id="d60ef-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-335">codice personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-335">personal code</span></span>
  
<span data-ttu-id="d60ef-336">numero di codice personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-336">personal code number</span></span>
  
<span data-ttu-id="d60ef-337">numero di certificato personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-337">personal certificate number</span></span>
  
<span data-ttu-id="d60ef-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="d60ef-338">personalcodeno#</span></span>
  
<span data-ttu-id="d60ef-339">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-339">personal id number</span></span>
  
<span data-ttu-id="d60ef-340">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-340">personal id code</span></span>
  
<span data-ttu-id="d60ef-341">personas Kods</span><span class="sxs-lookup"><span data-stu-id="d60ef-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="d60ef-342">Lituania</span><span class="sxs-lookup"><span data-stu-id="d60ef-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-343">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-343">Format</span></span>

<span data-ttu-id="d60ef-344">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="d60ef-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-345">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-345">Pattern</span></span>

<span data-ttu-id="d60ef-346">11 cifre senza spazi e delimitatori:</span><span class="sxs-lookup"><span data-stu-id="d60ef-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="d60ef-347">Una cifra corrispondente al sesso e al secolo della nascita della persona</span><span class="sxs-lookup"><span data-stu-id="d60ef-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="d60ef-348">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="d60ef-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="d60ef-349">Tre cifre che corrispondono al numero di serie della data di nascita</span><span class="sxs-lookup"><span data-stu-id="d60ef-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="d60ef-350">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="d60ef-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-351">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-351">Checksum</span></span>

<span data-ttu-id="d60ef-352">Sì</span><span class="sxs-lookup"><span data-stu-id="d60ef-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-353">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-353">Definition</span></span>

<span data-ttu-id="d60ef-354">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-355">La funzione `Func_lithuania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-356">Viene trovata una `Keywords_lithuania_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d60ef-357">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-358">La funzione `Func_lithuania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-359">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-359">Keywords</span></span>

#### <a name="keywords_lithuania_eu_national_id_card"></a><span data-ttu-id="d60ef-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-361">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-361">personal numeric code</span></span>
  
<span data-ttu-id="d60ef-362">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-362">unique identification number</span></span>
  
<span data-ttu-id="d60ef-363">numero di servizio Citizen</span><span class="sxs-lookup"><span data-stu-id="d60ef-363">citizen service number</span></span>
  
<span data-ttu-id="d60ef-364">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-364">unique identity number</span></span>
  
<span data-ttu-id="d60ef-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d60ef-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="d60ef-366">codice personale.</span><span class="sxs-lookup"><span data-stu-id="d60ef-366">personal code.</span></span>
  
<span data-ttu-id="d60ef-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="d60ef-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="d60ef-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="d60ef-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="d60ef-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="d60ef-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="d60ef-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="d60ef-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="d60ef-371">asmens kodas.</span><span class="sxs-lookup"><span data-stu-id="d60ef-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="d60ef-372">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="d60ef-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-373">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-373">Format</span></span>

<span data-ttu-id="d60ef-374">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="d60ef-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-375">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-375">Pattern</span></span>

<span data-ttu-id="d60ef-376">11 cifre</span><span class="sxs-lookup"><span data-stu-id="d60ef-376">11 digits</span></span>
  
- <span data-ttu-id="d60ef-377">Una cifra corrispondente al sesso e al secolo della nascita della persona</span><span class="sxs-lookup"><span data-stu-id="d60ef-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="d60ef-378">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="d60ef-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="d60ef-379">Tre cifre che corrispondono al numero di serie della data di nascita</span><span class="sxs-lookup"><span data-stu-id="d60ef-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="d60ef-380">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="d60ef-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-381">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-381">Checksum</span></span>

<span data-ttu-id="d60ef-382">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d60ef-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-383">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-383">Definition</span></span>

<span data-ttu-id="d60ef-384">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-385">L'espressione `Regex_luxemburg_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-386">Viene trovata una `Keywords_luxemburg_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-387">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_national_id_card"></a><span data-ttu-id="d60ef-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-389">ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-389">personal id</span></span>
  
<span data-ttu-id="d60ef-390">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-390">personal id number</span></span>
  
<span data-ttu-id="d60ef-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="d60ef-391">personalidno#</span></span>
  
<span data-ttu-id="d60ef-392">numero ID univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-392">unique id number</span></span>
  
<span data-ttu-id="d60ef-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d60ef-393">personalidnumber#</span></span>
  
<span data-ttu-id="d60ef-394">chiave ID univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-394">unique id key</span></span>
  
<span data-ttu-id="d60ef-395">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-395">personal id code</span></span>
  
<span data-ttu-id="d60ef-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="d60ef-396">uniqueidkey#</span></span>
  
<span data-ttu-id="d60ef-397">codice singolo</span><span class="sxs-lookup"><span data-stu-id="d60ef-397">individual code</span></span>
  
<span data-ttu-id="d60ef-398">ID individuale</span><span class="sxs-lookup"><span data-stu-id="d60ef-398">individual id</span></span>
  
<span data-ttu-id="d60ef-399">ID eindeutige-Nummer</span><span class="sxs-lookup"><span data-stu-id="d60ef-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="d60ef-400">ID eindeutige</span><span class="sxs-lookup"><span data-stu-id="d60ef-400">eindeutige id</span></span>
  
<span data-ttu-id="d60ef-401">ID personnelle</span><span class="sxs-lookup"><span data-stu-id="d60ef-401">id personnelle</span></span>
  
<span data-ttu-id="d60ef-402">personale di Numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="d60ef-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="d60ef-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="d60ef-403">idpersonnelle#</span></span>
  
<span data-ttu-id="d60ef-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="d60ef-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="d60ef-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="d60ef-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="d60ef-406">Malta</span><span class="sxs-lookup"><span data-stu-id="d60ef-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-407">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-407">Format</span></span>

<span data-ttu-id="d60ef-408">Sette cifre seguite da una lettera</span><span class="sxs-lookup"><span data-stu-id="d60ef-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-409">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-409">Pattern</span></span>

<span data-ttu-id="d60ef-410">Sette cifre seguite da una lettera:</span><span class="sxs-lookup"><span data-stu-id="d60ef-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="d60ef-411">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="d60ef-411">Seven digits</span></span> 
    
- <span data-ttu-id="d60ef-412">Una lettera maiuscola (distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="d60ef-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-413">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-413">Checksum</span></span>

<span data-ttu-id="d60ef-414">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d60ef-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-415">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-415">Definition</span></span>

<span data-ttu-id="d60ef-416">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-417">L'espressione `Regex_malta_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-418">Viene trovata una `Keywords_malta_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d60ef-419">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-420">L'espressione `Regex_malta_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-421">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-421">Keywords</span></span>

#### <a name="keywords_malta_eu_national_id_card"></a><span data-ttu-id="d60ef-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-423">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-423">personal numeric code</span></span>
  
<span data-ttu-id="d60ef-424">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-424">unique identification number</span></span>
  
<span data-ttu-id="d60ef-425">numero di servizio Citizen</span><span class="sxs-lookup"><span data-stu-id="d60ef-425">citizen service number</span></span>
  
<span data-ttu-id="d60ef-426">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-426">unique identity number</span></span>
  
<span data-ttu-id="d60ef-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d60ef-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="d60ef-428">Kodiċi numerai personali</span><span class="sxs-lookup"><span data-stu-id="d60ef-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="d60ef-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="d60ef-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="d60ef-430">numru TAS-Servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="d60ef-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="d60ef-431">numru ta ' identità uniku</span><span class="sxs-lookup"><span data-stu-id="d60ef-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="d60ef-432">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="d60ef-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-433">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-433">Format</span></span>

<span data-ttu-id="d60ef-434">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d60ef-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-435">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-435">Pattern</span></span>

<span data-ttu-id="d60ef-436">9 cifre</span><span class="sxs-lookup"><span data-stu-id="d60ef-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d60ef-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-437">Checksum</span></span>

<span data-ttu-id="d60ef-438">Sì</span><span class="sxs-lookup"><span data-stu-id="d60ef-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-439">Definition</span></span>

<span data-ttu-id="d60ef-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-441">La funzione `Func_netherlands_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-442">Viene trovata una parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-442">A keyword from is found.</span></span>
    
<span data-ttu-id="d60ef-443">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-444">La funzione `Func_netherlands_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-445">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-445">Keywords</span></span>

#### <a name="keywords_netherlands_eu_national_id_card"></a><span data-ttu-id="d60ef-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-447">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-447">personal numeric code</span></span>
  
<span data-ttu-id="d60ef-448">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-448">unique identification number</span></span>
  
<span data-ttu-id="d60ef-449">numero di servizio Citizen</span><span class="sxs-lookup"><span data-stu-id="d60ef-449">citizen service number</span></span>
  
<span data-ttu-id="d60ef-450">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-450">unique identity number</span></span>
  
<span data-ttu-id="d60ef-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d60ef-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="d60ef-452">BSN</span><span class="sxs-lookup"><span data-stu-id="d60ef-452">bsn</span></span>
  
<span data-ttu-id="d60ef-453">BSN #</span><span class="sxs-lookup"><span data-stu-id="d60ef-453">bsn#</span></span>
  
<span data-ttu-id="d60ef-454">codice Numerieke di persoonlijke</span><span class="sxs-lookup"><span data-stu-id="d60ef-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="d60ef-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="d60ef-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="d60ef-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="d60ef-456">burgerservicenummer</span></span>
  
<span data-ttu-id="d60ef-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="d60ef-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="d60ef-458">Polonia</span><span class="sxs-lookup"><span data-stu-id="d60ef-458">Poland</span></span>

<span data-ttu-id="d60ef-459">Per informazioni dettagliate, vedere la sezione "Poland National ID (PESEL)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d60ef-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="d60ef-460">Portogallo</span><span class="sxs-lookup"><span data-stu-id="d60ef-460">Portugal</span></span>

<span data-ttu-id="d60ef-461">Per informazioni dettagliate, vedere la sezione "Portugal Citizen Card Number" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d60ef-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="d60ef-462">Romania</span><span class="sxs-lookup"><span data-stu-id="d60ef-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-463">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-463">Format</span></span>

<span data-ttu-id="d60ef-464">13 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="d60ef-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-465">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-465">Pattern</span></span>

<span data-ttu-id="d60ef-466">13 cifre</span><span class="sxs-lookup"><span data-stu-id="d60ef-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d60ef-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-467">Checksum</span></span>

<span data-ttu-id="d60ef-468">Sì</span><span class="sxs-lookup"><span data-stu-id="d60ef-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-469">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-469">Definition</span></span>

<span data-ttu-id="d60ef-470">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-471">La funzione `Func_romania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-472">Viene trovata una `Keywords_romania_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d60ef-473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-474">La funzione `Func_romania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-475">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-475">Keywords</span></span>

#### <a name="keywords_romania_eu_national_id_card"></a><span data-ttu-id="d60ef-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-477">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-477">personal numeric code</span></span>
  
<span data-ttu-id="d60ef-478">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-478">unique identification number</span></span>
  
<span data-ttu-id="d60ef-479">CNP</span><span class="sxs-lookup"><span data-stu-id="d60ef-479">cnp</span></span>
  
<span data-ttu-id="d60ef-480">CNP #</span><span class="sxs-lookup"><span data-stu-id="d60ef-480">cnp#</span></span>
  
<span data-ttu-id="d60ef-481">pin</span><span class="sxs-lookup"><span data-stu-id="d60ef-481">pin</span></span>
  
<span data-ttu-id="d60ef-482">pin #</span><span class="sxs-lookup"><span data-stu-id="d60ef-482">pin#</span></span>
  
<span data-ttu-id="d60ef-483">numero assicurativo</span><span class="sxs-lookup"><span data-stu-id="d60ef-483">insurance number</span></span>
  
<span data-ttu-id="d60ef-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="d60ef-484">insurancenumber#</span></span>
  
<span data-ttu-id="d60ef-485">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-485">unique identity number</span></span>
  
<span data-ttu-id="d60ef-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d60ef-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="d60ef-487">Cod numerico personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-487">cod numeric personal</span></span>
  
<span data-ttu-id="d60ef-488">Cod identificare Personal</span><span class="sxs-lookup"><span data-stu-id="d60ef-488">cod identificare personal</span></span>
  
<span data-ttu-id="d60ef-489">Cod Unic identificare</span><span class="sxs-lookup"><span data-stu-id="d60ef-489">cod unic identificare</span></span>
  
<span data-ttu-id="d60ef-490">Număr personale Unic</span><span class="sxs-lookup"><span data-stu-id="d60ef-490">număr personal unic</span></span>
  
<span data-ttu-id="d60ef-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="d60ef-491">număr identitate</span></span>
  
<span data-ttu-id="d60ef-492">Număr identificare Personal</span><span class="sxs-lookup"><span data-stu-id="d60ef-492">număr identificare personal</span></span>
  
<span data-ttu-id="d60ef-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="d60ef-493">număridentitate#</span></span>
  
<span data-ttu-id="d60ef-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="d60ef-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="d60ef-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="d60ef-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="d60ef-496">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="d60ef-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-497">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-497">Format</span></span>

<span data-ttu-id="d60ef-498">Dieci cifre contenenti una barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="d60ef-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-499">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-499">Pattern</span></span>

<span data-ttu-id="d60ef-500">Dieci cifre che contengono una barra rovesciata:</span><span class="sxs-lookup"><span data-stu-id="d60ef-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d60ef-501">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-501">Checksum</span></span>

<span data-ttu-id="d60ef-502">Sì</span><span class="sxs-lookup"><span data-stu-id="d60ef-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-503">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-503">Definition</span></span>

<span data-ttu-id="d60ef-504">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-505">La funzione `Func_slovakia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-506">Viene trovata una `Keywords_slovakia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d60ef-507">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-508">La funzione `Func_slovakia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-509">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-509">Keywords</span></span>

#### <a name="keywords_slovakia_eu_national_id_card"></a><span data-ttu-id="d60ef-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-511">numero di nascita</span><span class="sxs-lookup"><span data-stu-id="d60ef-511">birth number</span></span>
  
<span data-ttu-id="d60ef-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="d60ef-512">national identification number</span></span>
  
<span data-ttu-id="d60ef-513">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-513">personal identification number</span></span>
  
<span data-ttu-id="d60ef-514">social security number</span><span class="sxs-lookup"><span data-stu-id="d60ef-514">social security number</span></span>
  
<span data-ttu-id="d60ef-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="d60ef-515">nationalnumber#</span></span>
  
<span data-ttu-id="d60ef-516">SSN #</span><span class="sxs-lookup"><span data-stu-id="d60ef-516">ssn#</span></span>
  
<span data-ttu-id="d60ef-517">SSN</span><span class="sxs-lookup"><span data-stu-id="d60ef-517">ssn</span></span>
  
<span data-ttu-id="d60ef-518">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="d60ef-518">national number</span></span>
  
<span data-ttu-id="d60ef-519">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-519">personal id number</span></span>
  
<span data-ttu-id="d60ef-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="d60ef-520">personalidnumber#</span></span>
  
<span data-ttu-id="d60ef-521">rč</span><span class="sxs-lookup"><span data-stu-id="d60ef-521">rč</span></span>
  
<span data-ttu-id="d60ef-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="d60ef-522">rodné číslo</span></span>
  
<span data-ttu-id="d60ef-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="d60ef-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="d60ef-524">Slovenia</span><span class="sxs-lookup"><span data-stu-id="d60ef-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-525">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-525">Format</span></span>

<span data-ttu-id="d60ef-526">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d60ef-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-527">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-527">Pattern</span></span>

<span data-ttu-id="d60ef-528">13 cifre nel modello specificato:</span><span class="sxs-lookup"><span data-stu-id="d60ef-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="d60ef-529">Sette cifre che corrispondono alla data di nascita (DDMMLLL), dove "LLL" corrisponde alle ultime tre cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="d60ef-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="d60ef-530">Due cifre che corrispondono all'area di nascita</span><span class="sxs-lookup"><span data-stu-id="d60ef-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="d60ef-531">Tre cifre che corrispondono a una combinazione di genere e numero di serie per le persone nate nello stesso giorno (000-499 per il maschio e 500-999 per le femmine)</span><span class="sxs-lookup"><span data-stu-id="d60ef-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="d60ef-532">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="d60ef-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-533">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-533">Checksum</span></span>

<span data-ttu-id="d60ef-534">Sì</span><span class="sxs-lookup"><span data-stu-id="d60ef-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-535">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-535">Definition</span></span>

<span data-ttu-id="d60ef-536">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-537">La funzione `Func_slovenia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-538">Viene trovata una `Keywords_slovenia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="d60ef-539">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-540">La funzione `Func_slovenia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-541">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-541">Keywords</span></span>

#### <a name="keywords_slovenia_eu_national_id_card"></a><span data-ttu-id="d60ef-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-543">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-543">personal numeric code</span></span>
  
<span data-ttu-id="d60ef-544">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-544">unique identification number</span></span>
  
<span data-ttu-id="d60ef-545">numero di registrazione univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-545">unique registration number</span></span>
  
<span data-ttu-id="d60ef-546">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-546">unique identity number</span></span>
  
<span data-ttu-id="d60ef-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d60ef-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="d60ef-548">numero di cittadino Master univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-548">unique master citizen number</span></span>
  
<span data-ttu-id="d60ef-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="d60ef-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="d60ef-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="d60ef-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="d60ef-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="d60ef-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="d60ef-552">emšo</span><span class="sxs-lookup"><span data-stu-id="d60ef-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="d60ef-553">Spagna</span><span class="sxs-lookup"><span data-stu-id="d60ef-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="d60ef-554">Formato</span><span class="sxs-lookup"><span data-stu-id="d60ef-554">Format</span></span>

<span data-ttu-id="d60ef-555">Sette cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="d60ef-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d60ef-556">Modello</span><span class="sxs-lookup"><span data-stu-id="d60ef-556">Pattern</span></span>

<span data-ttu-id="d60ef-557">Sette cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="d60ef-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="d60ef-558">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="d60ef-558">Seven digits</span></span>
    
- <span data-ttu-id="d60ef-559">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="d60ef-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d60ef-560">Checksum</span><span class="sxs-lookup"><span data-stu-id="d60ef-560">Checksum</span></span>

<span data-ttu-id="d60ef-561">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d60ef-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d60ef-562">Definizione</span><span class="sxs-lookup"><span data-stu-id="d60ef-562">Definition</span></span>

<span data-ttu-id="d60ef-563">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d60ef-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d60ef-564">L'espressione `Regex_spain_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d60ef-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d60ef-565">Viene trovata una `Keywords_spain_eu_national_id_card"` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d60ef-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d60ef-566">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d60ef-566">Keywords</span></span>

#### <a name="keywords_spain_eu_national_id_card"></a><span data-ttu-id="d60ef-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="d60ef-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="d60ef-568">DNI</span><span class="sxs-lookup"><span data-stu-id="d60ef-568">dni</span></span>
  
<span data-ttu-id="d60ef-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="d60ef-569">national identification number</span></span>
  
<span data-ttu-id="d60ef-570">numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="d60ef-570">national identity number</span></span>
  
<span data-ttu-id="d60ef-571">numero assicurativo</span><span class="sxs-lookup"><span data-stu-id="d60ef-571">insurance number</span></span>
  
<span data-ttu-id="d60ef-572">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="d60ef-572">personal identification number</span></span>
  
<span data-ttu-id="d60ef-573">identità nazionale</span><span class="sxs-lookup"><span data-stu-id="d60ef-573">national identity</span></span>
  
<span data-ttu-id="d60ef-574">identità personale No</span><span class="sxs-lookup"><span data-stu-id="d60ef-574">personal identity no</span></span>
  
<span data-ttu-id="d60ef-575">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="d60ef-575">unique identity number</span></span>
  
<span data-ttu-id="d60ef-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="d60ef-576">nationalidno#</span></span>
  
<span data-ttu-id="d60ef-577">UniqueId #</span><span class="sxs-lookup"><span data-stu-id="d60ef-577">uniqueid#</span></span>
  
<span data-ttu-id="d60ef-578">DNI #</span><span class="sxs-lookup"><span data-stu-id="d60ef-578">dni#</span></span>
  
<span data-ttu-id="d60ef-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="d60ef-579">nationalid#</span></span>
  
<span data-ttu-id="d60ef-580">nie #</span><span class="sxs-lookup"><span data-stu-id="d60ef-580">nie#</span></span>
  
<span data-ttu-id="d60ef-581">nie</span><span class="sxs-lookup"><span data-stu-id="d60ef-581">nie</span></span>
  
<span data-ttu-id="d60ef-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="d60ef-582">nienúmero#</span></span>
  
<span data-ttu-id="d60ef-583">nie número</span><span class="sxs-lookup"><span data-stu-id="d60ef-583">nie número</span></span>
  
<span data-ttu-id="d60ef-584">documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="d60ef-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="d60ef-585">Identidad único</span><span class="sxs-lookup"><span data-stu-id="d60ef-585">identidad único</span></span>
  
<span data-ttu-id="d60ef-586">número Nacional Identidad</span><span class="sxs-lookup"><span data-stu-id="d60ef-586">número nacional identidad</span></span>
  
<span data-ttu-id="d60ef-587">DNI número</span><span class="sxs-lookup"><span data-stu-id="d60ef-587">dni número</span></span>
  
<span data-ttu-id="d60ef-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="d60ef-588">dninúmero#</span></span>
  
<span data-ttu-id="d60ef-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="d60ef-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="d60ef-590">Svezia</span><span class="sxs-lookup"><span data-stu-id="d60ef-590">Sweden</span></span>

<span data-ttu-id="d60ef-591">Per informazioni dettagliate, vedere la sezione "Sweden National ID" per [individuare i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d60ef-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d60ef-592">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d60ef-592">See also</span></span>

[<span data-ttu-id="d60ef-593">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="d60ef-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

