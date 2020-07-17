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
ms.custom:
- seo-marvel-apr2020
description: Informazioni sul funzionamento delle funzioni di prevenzione della perdita di dati (DLP), per comprendere come funzionano i tipi di informazioni riservate predefinite.
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819276"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="07d63-103">Elementi cercati dalle funzioni dei criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="07d63-103">What the DLP functions look for</span></span>

<span data-ttu-id="07d63-p101">Prevenzione della perdita di dati (DLP) include tipi di informazioni riservate, come il numero di carta di credito e il numero di carta di debito EU, pronti per essere utilizzati nei criteri DLP. Questi tipi di informazioni riservate cercano uno schema specifico e lo confermano assicurando la corretta formattazione, applicando checksum e individuando parole chiave specifiche o altre informazioni. Alcune di queste funzionalità vengono eseguite da funzioni interne. Ad esempio, il tipo di informazioni riservate relative al numero di carta di credito utilizza una funzione per cercare le date formattate come una data di scadenza, in modo da confermare che si tratta di un numero di carta di credito.</span><span class="sxs-lookup"><span data-stu-id="07d63-p101">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="07d63-108">In questo argomento viene descritto cosa viene cercato da queste funzioni per comprendere come funzionano i tipi di informazioni riservate predefiniti.</span><span class="sxs-lookup"><span data-stu-id="07d63-108">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="07d63-109">Per ulteriori informazioni, vedere [definizioni di entità per il tipo di informazioni riservate](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="07d63-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="07d63-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="07d63-110">Func_us_date</span></span>

<span data-ttu-id="07d63-111">Questa funzione Cerca una data nel formato comunemente utilizzato negli Stati Uniti. Sono inclusi i formati "month/day/year", "month-day-year" e "month day year".</span><span class="sxs-lookup"><span data-stu-id="07d63-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="07d63-112">I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="07d63-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="07d63-113">Esempi:</span><span class="sxs-lookup"><span data-stu-id="07d63-113">Examples:</span></span>
  
- <span data-ttu-id="07d63-114">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="07d63-114">December 2, 2016</span></span>
    
- <span data-ttu-id="07d63-115">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="07d63-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="07d63-116">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="07d63-116">dec 02 2016</span></span>
    
- <span data-ttu-id="07d63-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="07d63-117">12/2/2016</span></span>
    
- <span data-ttu-id="07d63-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="07d63-118">12/02/16</span></span>
    
- <span data-ttu-id="07d63-119">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="07d63-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="07d63-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="07d63-120">12-2-16</span></span>
    
<span data-ttu-id="07d63-121">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="07d63-121">Accepted month names:</span></span>
  
- <span data-ttu-id="07d63-122">English</span><span class="sxs-lookup"><span data-stu-id="07d63-122">English</span></span>
    
  - <span data-ttu-id="07d63-123">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="07d63-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="07d63-124">Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.</span><span class="sxs-lookup"><span data-stu-id="07d63-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="07d63-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="07d63-125">Func_eu_date</span></span>

<span data-ttu-id="07d63-p104">Questa funzione consente di cercare una data nel formato comunemente usato nell'UE e nella maggior parte delle aree geografiche al di fuori degli Stati Uniti. Sono inclusi i formati "giorno/mese/anno", "giorno-mese-anno" e "giorno mese anno". I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="07d63-p104">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="07d63-130">Esempi:</span><span class="sxs-lookup"><span data-stu-id="07d63-130">Examples:</span></span>
  
- <span data-ttu-id="07d63-131">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="07d63-131">2 Dec 2016</span></span>
    
- <span data-ttu-id="07d63-132">02 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="07d63-132">02 dec 2016</span></span>
    
- <span data-ttu-id="07d63-133">2 dicembre 16</span><span class="sxs-lookup"><span data-stu-id="07d63-133">2 Dec 16</span></span>
    
- <span data-ttu-id="07d63-134">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="07d63-134">2/12/2016</span></span>
    
- <span data-ttu-id="07d63-135">02/12/16</span><span class="sxs-lookup"><span data-stu-id="07d63-135">02/12/16</span></span>
    
- <span data-ttu-id="07d63-136">2-Dec-2016</span><span class="sxs-lookup"><span data-stu-id="07d63-136">2-Dec-2016</span></span>
    
- <span data-ttu-id="07d63-137">2-12-16</span><span class="sxs-lookup"><span data-stu-id="07d63-137">2-12-16</span></span>
    
<span data-ttu-id="07d63-138">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="07d63-138">Accepted month names:</span></span>
  
- <span data-ttu-id="07d63-139">English</span><span class="sxs-lookup"><span data-stu-id="07d63-139">English</span></span>
    
  - <span data-ttu-id="07d63-140">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="07d63-140">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="07d63-141">Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.</span><span class="sxs-lookup"><span data-stu-id="07d63-141">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="07d63-142">Dutch</span><span class="sxs-lookup"><span data-stu-id="07d63-142">Dutch</span></span>
    
  - <span data-ttu-id="07d63-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="07d63-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="07d63-144">Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec</span><span class="sxs-lookup"><span data-stu-id="07d63-144">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="07d63-145">French</span><span class="sxs-lookup"><span data-stu-id="07d63-145">French</span></span>
    
  - <span data-ttu-id="07d63-146">Janvier, février, Mars, avril, mai, Juin Juillet, août, septembre, Octobre, novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="07d63-146">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="07d63-147">janv.</span><span class="sxs-lookup"><span data-stu-id="07d63-147">janv.</span></span> <span data-ttu-id="07d63-148">févr.</span><span class="sxs-lookup"><span data-stu-id="07d63-148">févr.</span></span> <span data-ttu-id="07d63-149">Mars Avril mai juin juil.</span><span class="sxs-lookup"><span data-stu-id="07d63-149">mars avril mai juin juil.</span></span> <span data-ttu-id="07d63-150">août sett.</span><span class="sxs-lookup"><span data-stu-id="07d63-150">août sept.</span></span> <span data-ttu-id="07d63-151">personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="07d63-151">oct.</span></span> <span data-ttu-id="07d63-152">novembre.</span><span class="sxs-lookup"><span data-stu-id="07d63-152">nov.</span></span> <span data-ttu-id="07d63-153">déc.</span><span class="sxs-lookup"><span data-stu-id="07d63-153">déc.</span></span>
    
- <span data-ttu-id="07d63-154">German</span><span class="sxs-lookup"><span data-stu-id="07d63-154">German</span></span>
    
  - <span data-ttu-id="07d63-155">jänuar, febbraio, März, April, mai, Juni Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="07d63-155">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="07d63-156">Gen./Jän.</span><span class="sxs-lookup"><span data-stu-id="07d63-156">Jan./Jän.</span></span> <span data-ttu-id="07d63-157">Feb. März apr. mai Juni luglio Okt.</span><span class="sxs-lookup"><span data-stu-id="07d63-157">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="07d63-158">Nov. dic.</span><span class="sxs-lookup"><span data-stu-id="07d63-158">Nov. Dez.</span></span>
    
- <span data-ttu-id="07d63-159">Italian</span><span class="sxs-lookup"><span data-stu-id="07d63-159">Italian</span></span>
    
  - <span data-ttu-id="07d63-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="07d63-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="07d63-161">Genn.</span><span class="sxs-lookup"><span data-stu-id="07d63-161">genn.</span></span> <span data-ttu-id="07d63-162">febbr.</span><span class="sxs-lookup"><span data-stu-id="07d63-162">febbr.</span></span> <span data-ttu-id="07d63-163">mar.</span><span class="sxs-lookup"><span data-stu-id="07d63-163">mar.</span></span> <span data-ttu-id="07d63-164">apr.</span><span class="sxs-lookup"><span data-stu-id="07d63-164">apr.</span></span> <span data-ttu-id="07d63-165">magg.</span><span class="sxs-lookup"><span data-stu-id="07d63-165">magg.</span></span> <span data-ttu-id="07d63-166">giugno luglio AG.</span><span class="sxs-lookup"><span data-stu-id="07d63-166">giugno luglio ag.</span></span> <span data-ttu-id="07d63-167">ovvero.</span><span class="sxs-lookup"><span data-stu-id="07d63-167">sett.</span></span> <span data-ttu-id="07d63-168">ott.</span><span class="sxs-lookup"><span data-stu-id="07d63-168">ott.</span></span> <span data-ttu-id="07d63-169">novembre.</span><span class="sxs-lookup"><span data-stu-id="07d63-169">nov.</span></span> <span data-ttu-id="07d63-170">dic.</span><span class="sxs-lookup"><span data-stu-id="07d63-170">dic.</span></span>
    
- <span data-ttu-id="07d63-171">Portoghese</span><span class="sxs-lookup"><span data-stu-id="07d63-171">Portuguese</span></span>
    
  - <span data-ttu-id="07d63-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="07d63-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="07d63-173">Jan FEV Mar ABR mai Jun Jul ago set out nov dic</span><span class="sxs-lookup"><span data-stu-id="07d63-173">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="07d63-174">Spanish</span><span class="sxs-lookup"><span data-stu-id="07d63-174">Spanish</span></span>
    
  - <span data-ttu-id="07d63-175">enero, febrero, marzo, Abril, Mayo, Junio, Julio, agosto, Septiembre, Octubre, Noviembre, Diciembre</span><span class="sxs-lookup"><span data-stu-id="07d63-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="07d63-176">enero feb.</span><span class="sxs-lookup"><span data-stu-id="07d63-176">enero feb.</span></span> <span data-ttu-id="07d63-177">marzo ABR.</span><span class="sxs-lookup"><span data-stu-id="07d63-177">marzo abr.</span></span> <span data-ttu-id="07d63-178">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="07d63-178">mayo jun.</span></span> <span data-ttu-id="07d63-179">luglio.</span><span class="sxs-lookup"><span data-stu-id="07d63-179">jul.</span></span> <span data-ttu-id="07d63-180">agosto Sept/set.</span><span class="sxs-lookup"><span data-stu-id="07d63-180">agosto sept./set.</span></span> <span data-ttu-id="07d63-181">personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="07d63-181">oct.</span></span> <span data-ttu-id="07d63-182">novembre.</span><span class="sxs-lookup"><span data-stu-id="07d63-182">nov.</span></span> <span data-ttu-id="07d63-183">dic.</span><span class="sxs-lookup"><span data-stu-id="07d63-183">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="07d63-184">Func_eu_date1 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="07d63-184">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="07d63-185">Questa funzione è obsoleta perché supporta solo i nomi dei mesi portoghesi, che ora sono inclusi nella `Func_eu_date` funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="07d63-185">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="07d63-186">Questa funzione consente di cercare una data nel formato comunemente utilizzato in portoghese.</span><span class="sxs-lookup"><span data-stu-id="07d63-186">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="07d63-187">Il formato di questa funzione è lo stesso che `Func_eu_date` differisce solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="07d63-187">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="07d63-188">Esempi:</span><span class="sxs-lookup"><span data-stu-id="07d63-188">Examples:</span></span>
  
- <span data-ttu-id="07d63-189">2 (2016).</span><span class="sxs-lookup"><span data-stu-id="07d63-189">2 Dez 2016</span></span>
    
- <span data-ttu-id="07d63-190">02 (2016).</span><span class="sxs-lookup"><span data-stu-id="07d63-190">02 dez 2016</span></span>
    
- <span data-ttu-id="07d63-191">2 con il 16</span><span class="sxs-lookup"><span data-stu-id="07d63-191">2 Dez 16</span></span>
    
- <span data-ttu-id="07d63-192">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="07d63-192">2/12/2016</span></span>
    
- <span data-ttu-id="07d63-193">02/12/16</span><span class="sxs-lookup"><span data-stu-id="07d63-193">02/12/16</span></span>
    
- <span data-ttu-id="07d63-194">2-------2016</span><span class="sxs-lookup"><span data-stu-id="07d63-194">2-Dez-2016</span></span>
    
- <span data-ttu-id="07d63-195">2-12-16</span><span class="sxs-lookup"><span data-stu-id="07d63-195">2-12-16</span></span>
    
<span data-ttu-id="07d63-196">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="07d63-196">Accepted month names:</span></span>
  
- <span data-ttu-id="07d63-197">Portoghese</span><span class="sxs-lookup"><span data-stu-id="07d63-197">Portuguese</span></span>
    
  - <span data-ttu-id="07d63-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="07d63-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="07d63-199">Jan FEV Mar ABR mai Jun Jul ago set out nov dic</span><span class="sxs-lookup"><span data-stu-id="07d63-199">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="07d63-200">Func_eu_date2 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="07d63-200">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="07d63-201">Questa funzione è obsoleta perché supporta solo i nomi dei mesi olandesi, che ora sono inclusi nella `Func_eu_date` funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="07d63-201">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="07d63-202">Questa funzione consente di cercare una data nel formato comunemente utilizzato in olandese.</span><span class="sxs-lookup"><span data-stu-id="07d63-202">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="07d63-203">Il formato di questa funzione è lo stesso che `Func_eu_date` differisce solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="07d63-203">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="07d63-204">Esempi:</span><span class="sxs-lookup"><span data-stu-id="07d63-204">Examples:</span></span>
  
- <span data-ttu-id="07d63-205">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="07d63-205">2 Mei 2016</span></span>
    
- <span data-ttu-id="07d63-206">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="07d63-206">02 mei 2016</span></span>
    
- <span data-ttu-id="07d63-207">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="07d63-207">2 Mei 16</span></span>
    
- <span data-ttu-id="07d63-208">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="07d63-208">2/12/2016</span></span>
    
- <span data-ttu-id="07d63-209">02/12/16</span><span class="sxs-lookup"><span data-stu-id="07d63-209">02/12/16</span></span>
    
- <span data-ttu-id="07d63-210">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="07d63-210">2-Mei-2016</span></span>
    
- <span data-ttu-id="07d63-211">2-12-16</span><span class="sxs-lookup"><span data-stu-id="07d63-211">2-12-16</span></span>
    
<span data-ttu-id="07d63-212">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="07d63-212">Accepted month names:</span></span>
  
- <span data-ttu-id="07d63-213">Dutch</span><span class="sxs-lookup"><span data-stu-id="07d63-213">Dutch</span></span>
    
  - <span data-ttu-id="07d63-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="07d63-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="07d63-215">Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec</span><span class="sxs-lookup"><span data-stu-id="07d63-215">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="07d63-216">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="07d63-216">Func_expiration_date</span></span>

<span data-ttu-id="07d63-217">Questa funzione consente di cercare una data nei formati comunemente utilizzati da carte di credito e di debito, sostituendo i giorni con i mesi.</span><span class="sxs-lookup"><span data-stu-id="07d63-217">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="07d63-218">Questa funzione corrisponderà alle date nel formato "month/year", "month-year", "[Month Name] Year" e "[month abbreviation] Year".</span><span class="sxs-lookup"><span data-stu-id="07d63-218">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="07d63-219">I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="07d63-219">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="07d63-220">Esempi:</span><span class="sxs-lookup"><span data-stu-id="07d63-220">Examples:</span></span>
  
- <span data-ttu-id="07d63-221">MM/AA -- ad esempio, 01/11 o 1/11</span><span class="sxs-lookup"><span data-stu-id="07d63-221">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="07d63-222">MM/AAAA -- ad esempio, 01/2011 o 1/2011</span><span class="sxs-lookup"><span data-stu-id="07d63-222">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="07d63-223">MM-AA -- ad esempio, 01-22 o 1-11</span><span class="sxs-lookup"><span data-stu-id="07d63-223">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="07d63-224">MM-AAAA-- ad esempio, 01-2000 o 1-2000</span><span class="sxs-lookup"><span data-stu-id="07d63-224">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="07d63-225">I formati seguenti supportano AA o AAAA:</span><span class="sxs-lookup"><span data-stu-id="07d63-225">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="07d63-226">Mese-AAAA -- ad esempio, .Gen-2010 o gennaio-2010 o Gen-10 o gennaio-10</span><span class="sxs-lookup"><span data-stu-id="07d63-226">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="07d63-227">Mese AAAA -- ad esempio, "gennaio 2010" o "Gen 2010" o" gennaio 10" o "Gen 10"</span><span class="sxs-lookup"><span data-stu-id="07d63-227">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="07d63-228">MeseAAAA -- ad esempio, "gennaio2010" o "Gen2010" o "gennaio10" o "Gen10"</span><span class="sxs-lookup"><span data-stu-id="07d63-228">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="07d63-229">Mese/AAAA--ad esempio, "gennaio/2010" o "gen/2010" o "gennaio/10" o "gen/10"</span><span class="sxs-lookup"><span data-stu-id="07d63-229">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="07d63-230">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="07d63-230">Accepted month names:</span></span>
  
- <span data-ttu-id="07d63-231">English</span><span class="sxs-lookup"><span data-stu-id="07d63-231">English</span></span>
    
  - <span data-ttu-id="07d63-232">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="07d63-232">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="07d63-233">Gen feb mar apr maggio giugno luglio Aug settembre Ott Nov Dec</span><span class="sxs-lookup"><span data-stu-id="07d63-233">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="07d63-234">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="07d63-234">Func_us_address</span></span>

<span data-ttu-id="07d63-p112">Questa funzione cerca il nome di uno stato membro degli Stati Uniti o un'abbreviazione postale seguita da un CAP valido, esattamente come per gli indirizzi postali. Il CAP deve essere uno dei codici di avviamento postale corretti associati al nome o all'abbreviazione dello stato membro degli Stati Uniti. Il nome dello stato membro degli Stati Uniti e il CAP non possono essere separati da segni di punteggiatura o lettere.</span><span class="sxs-lookup"><span data-stu-id="07d63-p112">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="07d63-238">Esempi:</span><span class="sxs-lookup"><span data-stu-id="07d63-238">Examples:</span></span>
  
- <span data-ttu-id="07d63-239">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="07d63-239">Washington 98052</span></span>
    
- <span data-ttu-id="07d63-240">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="07d63-240">Washington 98052-9998</span></span>
    
- <span data-ttu-id="07d63-241">WA 98052</span><span class="sxs-lookup"><span data-stu-id="07d63-241">WA 98052</span></span>
    
- <span data-ttu-id="07d63-242">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="07d63-242">WA 98052-9998</span></span>
    

