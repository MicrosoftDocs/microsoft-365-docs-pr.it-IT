---
title: Cosa individuano le funzioni DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: I tipi di informazioni riservate cercano un modello specifico e lo confermano assicurando la corretta formattazione, l'applicazione di checksum e la ricerca di parole chiave rilevanti o altre informazioni. Alcune di queste funzionalità vengono eseguite da funzioni interne. In questo argomento viene descritto cosa viene cercato da queste funzioni per comprendere come funzionano i tipi di informazioni riservate predefiniti.
ms.openlocfilehash: 710cd371cbf67a03d75a928baab4b63587cdcfc1
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327748"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="c0817-105">Elementi cercati dalle funzioni dei criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="c0817-105">What the DLP functions look for</span></span>

<span data-ttu-id="c0817-p102">Prevenzione della perdita di dati (DLP) include tipi di informazioni riservate, come il numero di carta di credito e il numero di carta di debito EU, pronti per essere utilizzati nei criteri DLP. Questi tipi di informazioni riservate cercano uno schema specifico e lo confermano assicurando la corretta formattazione, applicando checksum e individuando parole chiave specifiche o altre informazioni. Alcune di queste funzionalità vengono eseguite da funzioni interne. Ad esempio, il tipo di informazioni riservate relative al numero di carta di credito utilizza una funzione per cercare le date formattate come una data di scadenza, in modo da confermare che si tratta di un numero di carta di credito.</span><span class="sxs-lookup"><span data-stu-id="c0817-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="c0817-110">In questo argomento viene descritto cosa viene cercato da queste funzioni per comprendere come funzionano i tipi di informazioni riservate predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c0817-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="c0817-111">Per ulteriori informazioni, vedere [definizioni di entità per il tipo di informazioni riservate](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="c0817-111">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="c0817-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="c0817-112">Func_us_date</span></span>

<span data-ttu-id="c0817-113">Questa funzione Cerca una data nel formato comunemente utilizzato negli Stati Uniti. Sono inclusi i formati "month/day/year", "month-day-year" e "month day year".</span><span class="sxs-lookup"><span data-stu-id="c0817-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="c0817-114">I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c0817-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="c0817-115">Esempi:</span><span class="sxs-lookup"><span data-stu-id="c0817-115">Examples:</span></span>
  
- <span data-ttu-id="c0817-116">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="c0817-116">December 2, 2016</span></span>
    
- <span data-ttu-id="c0817-117">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="c0817-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="c0817-118">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="c0817-118">dec 02 2016</span></span>
    
- <span data-ttu-id="c0817-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="c0817-119">12/2/2016</span></span>
    
- <span data-ttu-id="c0817-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="c0817-120">12/02/16</span></span>
    
- <span data-ttu-id="c0817-121">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="c0817-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="c0817-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="c0817-122">12-2-16</span></span>
    
<span data-ttu-id="c0817-123">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="c0817-123">Accepted month names:</span></span>
  
- <span data-ttu-id="c0817-124">Inglese</span><span class="sxs-lookup"><span data-stu-id="c0817-124">English</span></span>
    
  - <span data-ttu-id="c0817-125">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="c0817-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="c0817-126">Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.</span><span class="sxs-lookup"><span data-stu-id="c0817-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="c0817-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="c0817-127">Func_eu_date</span></span>

<span data-ttu-id="c0817-p105">Questa funzione consente di cercare una data nel formato comunemente usato nell'UE e nella maggior parte delle aree geografiche al di fuori degli Stati Uniti. Sono inclusi i formati "giorno/mese/anno", "giorno-mese-anno" e "giorno mese anno". I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c0817-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="c0817-132">Esempi:</span><span class="sxs-lookup"><span data-stu-id="c0817-132">Examples:</span></span>
  
- <span data-ttu-id="c0817-133">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="c0817-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="c0817-134">02 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="c0817-134">02 dec 2016</span></span>
    
- <span data-ttu-id="c0817-135">2 dicembre 16</span><span class="sxs-lookup"><span data-stu-id="c0817-135">2 Dec 16</span></span>
    
- <span data-ttu-id="c0817-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="c0817-136">2/12/2016</span></span>
    
- <span data-ttu-id="c0817-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="c0817-137">02/12/16</span></span>
    
- <span data-ttu-id="c0817-138">2-Dec-2016</span><span class="sxs-lookup"><span data-stu-id="c0817-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="c0817-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="c0817-139">2-12-16</span></span>
    
<span data-ttu-id="c0817-140">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="c0817-140">Accepted month names:</span></span>
  
- <span data-ttu-id="c0817-141">Inglese</span><span class="sxs-lookup"><span data-stu-id="c0817-141">English</span></span>
    
  - <span data-ttu-id="c0817-142">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="c0817-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="c0817-143">Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.</span><span class="sxs-lookup"><span data-stu-id="c0817-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="c0817-144">Olandese</span><span class="sxs-lookup"><span data-stu-id="c0817-144">Dutch</span></span>
    
  - <span data-ttu-id="c0817-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="c0817-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="c0817-146">Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec</span><span class="sxs-lookup"><span data-stu-id="c0817-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="c0817-147">Francese</span><span class="sxs-lookup"><span data-stu-id="c0817-147">French</span></span>
    
  - <span data-ttu-id="c0817-148">Janvier, février, Mars, avril, mai, Juin Juillet, août, septembre, Octobre, novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="c0817-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="c0817-149">janv.</span><span class="sxs-lookup"><span data-stu-id="c0817-149">janv.</span></span> <span data-ttu-id="c0817-150">févr.</span><span class="sxs-lookup"><span data-stu-id="c0817-150">févr.</span></span> <span data-ttu-id="c0817-151">Mars Avril mai juin juil.</span><span class="sxs-lookup"><span data-stu-id="c0817-151">mars avril mai juin juil.</span></span> <span data-ttu-id="c0817-152">août sett.</span><span class="sxs-lookup"><span data-stu-id="c0817-152">août sept.</span></span> <span data-ttu-id="c0817-153">personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="c0817-153">oct.</span></span> <span data-ttu-id="c0817-154">novembre.</span><span class="sxs-lookup"><span data-stu-id="c0817-154">nov.</span></span> <span data-ttu-id="c0817-155">déc.</span><span class="sxs-lookup"><span data-stu-id="c0817-155">déc.</span></span>
    
- <span data-ttu-id="c0817-156">Tedesco</span><span class="sxs-lookup"><span data-stu-id="c0817-156">German</span></span>
    
  - <span data-ttu-id="c0817-157">jänuar, febbraio, März, April, mai, Juni Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="c0817-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="c0817-158">Gen./Jän.</span><span class="sxs-lookup"><span data-stu-id="c0817-158">Jan./Jän.</span></span> <span data-ttu-id="c0817-159">Feb. März apr. mai Juni luglio Okt.</span><span class="sxs-lookup"><span data-stu-id="c0817-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="c0817-160">Nov. dic.</span><span class="sxs-lookup"><span data-stu-id="c0817-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="c0817-161">Italiano</span><span class="sxs-lookup"><span data-stu-id="c0817-161">Italian</span></span>
    
  - <span data-ttu-id="c0817-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="c0817-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="c0817-163">Genn.</span><span class="sxs-lookup"><span data-stu-id="c0817-163">genn.</span></span> <span data-ttu-id="c0817-164">febbr.</span><span class="sxs-lookup"><span data-stu-id="c0817-164">febbr.</span></span> <span data-ttu-id="c0817-165">mar.</span><span class="sxs-lookup"><span data-stu-id="c0817-165">mar.</span></span> <span data-ttu-id="c0817-166">apr.</span><span class="sxs-lookup"><span data-stu-id="c0817-166">apr.</span></span> <span data-ttu-id="c0817-167">magg.</span><span class="sxs-lookup"><span data-stu-id="c0817-167">magg.</span></span> <span data-ttu-id="c0817-168">giugno luglio AG.</span><span class="sxs-lookup"><span data-stu-id="c0817-168">giugno luglio ag.</span></span> <span data-ttu-id="c0817-169">ovvero.</span><span class="sxs-lookup"><span data-stu-id="c0817-169">sett.</span></span> <span data-ttu-id="c0817-170">ott.</span><span class="sxs-lookup"><span data-stu-id="c0817-170">ott.</span></span> <span data-ttu-id="c0817-171">novembre.</span><span class="sxs-lookup"><span data-stu-id="c0817-171">nov.</span></span> <span data-ttu-id="c0817-172">dic.</span><span class="sxs-lookup"><span data-stu-id="c0817-172">dic.</span></span>
    
- <span data-ttu-id="c0817-173">Portoghese</span><span class="sxs-lookup"><span data-stu-id="c0817-173">Portuguese</span></span>
    
  - <span data-ttu-id="c0817-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="c0817-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="c0817-175">Jan FEV Mar ABR mai Jun Jul ago set out nov dic</span><span class="sxs-lookup"><span data-stu-id="c0817-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="c0817-176">Spagnolo</span><span class="sxs-lookup"><span data-stu-id="c0817-176">Spanish</span></span>
    
  - <span data-ttu-id="c0817-177">enero, febrero, marzo, Abril, Mayo, Junio, Julio, agosto, Septiembre, Octubre, Noviembre, Diciembre</span><span class="sxs-lookup"><span data-stu-id="c0817-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="c0817-178">enero feb.</span><span class="sxs-lookup"><span data-stu-id="c0817-178">enero feb.</span></span> <span data-ttu-id="c0817-179">marzo ABR.</span><span class="sxs-lookup"><span data-stu-id="c0817-179">marzo abr.</span></span> <span data-ttu-id="c0817-180">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="c0817-180">mayo jun.</span></span> <span data-ttu-id="c0817-181">luglio.</span><span class="sxs-lookup"><span data-stu-id="c0817-181">jul.</span></span> <span data-ttu-id="c0817-182">agosto Sept/set.</span><span class="sxs-lookup"><span data-stu-id="c0817-182">agosto sept./set.</span></span> <span data-ttu-id="c0817-183">personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="c0817-183">oct.</span></span> <span data-ttu-id="c0817-184">novembre.</span><span class="sxs-lookup"><span data-stu-id="c0817-184">nov.</span></span> <span data-ttu-id="c0817-185">dic.</span><span class="sxs-lookup"><span data-stu-id="c0817-185">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="c0817-186">Func_eu_date1 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="c0817-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="c0817-187">Questa funzione è obsoleta perché supporta solo i nomi dei mesi portoghesi, che ora sono inclusi nella `Func_eu_date` funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="c0817-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="c0817-188">Questa funzione consente di cercare una data nel formato comunemente utilizzato in portoghese.</span><span class="sxs-lookup"><span data-stu-id="c0817-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="c0817-189">Il formato di questa funzione è lo stesso che `Func_eu_date` differisce solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="c0817-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="c0817-190">Esempi:</span><span class="sxs-lookup"><span data-stu-id="c0817-190">Examples:</span></span>
  
- <span data-ttu-id="c0817-191">2 (2016).</span><span class="sxs-lookup"><span data-stu-id="c0817-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="c0817-192">02 (2016).</span><span class="sxs-lookup"><span data-stu-id="c0817-192">02 dez 2016</span></span>
    
- <span data-ttu-id="c0817-193">2 con il 16</span><span class="sxs-lookup"><span data-stu-id="c0817-193">2 Dez 16</span></span>
    
- <span data-ttu-id="c0817-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="c0817-194">2/12/2016</span></span>
    
- <span data-ttu-id="c0817-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="c0817-195">02/12/16</span></span>
    
- <span data-ttu-id="c0817-196">2-------2016</span><span class="sxs-lookup"><span data-stu-id="c0817-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="c0817-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="c0817-197">2-12-16</span></span>
    
<span data-ttu-id="c0817-198">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="c0817-198">Accepted month names:</span></span>
  
- <span data-ttu-id="c0817-199">Portoghese</span><span class="sxs-lookup"><span data-stu-id="c0817-199">Portuguese</span></span>
    
  - <span data-ttu-id="c0817-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="c0817-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="c0817-201">Jan FEV Mar ABR mai Jun Jul ago set out nov dic</span><span class="sxs-lookup"><span data-stu-id="c0817-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="c0817-202">Func_eu_date2 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="c0817-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="c0817-203">Questa funzione è obsoleta perché supporta solo i nomi dei mesi olandesi, che ora sono inclusi nella `Func_eu_date` funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="c0817-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="c0817-204">Questa funzione consente di cercare una data nel formato comunemente utilizzato in olandese.</span><span class="sxs-lookup"><span data-stu-id="c0817-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="c0817-205">Il formato di questa funzione è lo stesso che `Func_eu_date` differisce solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="c0817-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="c0817-206">Esempi:</span><span class="sxs-lookup"><span data-stu-id="c0817-206">Examples:</span></span>
  
- <span data-ttu-id="c0817-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="c0817-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="c0817-208">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="c0817-208">02 mei 2016</span></span>
    
- <span data-ttu-id="c0817-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="c0817-209">2 Mei 16</span></span>
    
- <span data-ttu-id="c0817-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="c0817-210">2/12/2016</span></span>
    
- <span data-ttu-id="c0817-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="c0817-211">02/12/16</span></span>
    
- <span data-ttu-id="c0817-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="c0817-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="c0817-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="c0817-213">2-12-16</span></span>
    
<span data-ttu-id="c0817-214">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="c0817-214">Accepted month names:</span></span>
  
- <span data-ttu-id="c0817-215">Olandese</span><span class="sxs-lookup"><span data-stu-id="c0817-215">Dutch</span></span>
    
  - <span data-ttu-id="c0817-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="c0817-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="c0817-217">Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec</span><span class="sxs-lookup"><span data-stu-id="c0817-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="c0817-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="c0817-218">Func_expiration_date</span></span>

<span data-ttu-id="c0817-219">Questa funzione consente di cercare una data nei formati comunemente utilizzati da carte di credito e di debito, sostituendo i giorni con i mesi.</span><span class="sxs-lookup"><span data-stu-id="c0817-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="c0817-220">Questa funzione corrisponderà alle date nel formato "month/year", "month-year", "[Month Name] Year" e "[month abbreviation] Year".</span><span class="sxs-lookup"><span data-stu-id="c0817-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="c0817-221">I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c0817-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="c0817-222">Esempi:</span><span class="sxs-lookup"><span data-stu-id="c0817-222">Examples:</span></span>
  
- <span data-ttu-id="c0817-223">MM/AA -- ad esempio, 01/11 o 1/11</span><span class="sxs-lookup"><span data-stu-id="c0817-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="c0817-224">MM/AAAA -- ad esempio, 01/2011 o 1/2011</span><span class="sxs-lookup"><span data-stu-id="c0817-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="c0817-225">MM-AA -- ad esempio, 01-22 o 1-11</span><span class="sxs-lookup"><span data-stu-id="c0817-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="c0817-226">MM-AAAA-- ad esempio, 01-2000 o 1-2000</span><span class="sxs-lookup"><span data-stu-id="c0817-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="c0817-227">I formati seguenti supportano AA o AAAA:</span><span class="sxs-lookup"><span data-stu-id="c0817-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="c0817-228">Mese-AAAA -- ad esempio, .Gen-2010 o gennaio-2010 o Gen-10 o gennaio-10</span><span class="sxs-lookup"><span data-stu-id="c0817-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="c0817-229">Mese AAAA -- ad esempio, "gennaio 2010" o "Gen 2010" o" gennaio 10" o "Gen 10"</span><span class="sxs-lookup"><span data-stu-id="c0817-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="c0817-230">MeseAAAA -- ad esempio, "gennaio2010" o "Gen2010" o "gennaio10" o "Gen10"</span><span class="sxs-lookup"><span data-stu-id="c0817-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="c0817-231">Mese/AAAA--ad esempio, "gennaio/2010" o "gen/2010" o "gennaio/10" o "gen/10"</span><span class="sxs-lookup"><span data-stu-id="c0817-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="c0817-232">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="c0817-232">Accepted month names:</span></span>
  
- <span data-ttu-id="c0817-233">Inglese</span><span class="sxs-lookup"><span data-stu-id="c0817-233">English</span></span>
    
  - <span data-ttu-id="c0817-234">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="c0817-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="c0817-235">Gen feb mar apr maggio giugno luglio Aug settembre Ott Nov Dec</span><span class="sxs-lookup"><span data-stu-id="c0817-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="c0817-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="c0817-236">Func_us_address</span></span>

<span data-ttu-id="c0817-p113">Questa funzione cerca il nome di uno stato membro degli Stati Uniti o un'abbreviazione postale seguita da un CAP valido, esattamente come per gli indirizzi postali. Il CAP deve essere uno dei codici di avviamento postale corretti associati al nome o all'abbreviazione dello stato membro degli Stati Uniti. Il nome dello stato membro degli Stati Uniti e il CAP non possono essere separati da segni di punteggiatura o lettere.</span><span class="sxs-lookup"><span data-stu-id="c0817-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="c0817-240">Esempi:</span><span class="sxs-lookup"><span data-stu-id="c0817-240">Examples:</span></span>
  
- <span data-ttu-id="c0817-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="c0817-241">Washington 98052</span></span>
    
- <span data-ttu-id="c0817-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="c0817-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="c0817-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="c0817-243">WA 98052</span></span>
    
- <span data-ttu-id="c0817-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="c0817-244">WA 98052-9998</span></span>
    

