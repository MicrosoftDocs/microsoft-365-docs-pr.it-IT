---
title: Cosa cercano le funzioni di prevenzione della perdita di dati (DLP)
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
description: Informazioni sulle funzioni di prevenzione della perdita di dati (DLP, Data Loss Prevention).
ms.openlocfilehash: ef87be7dde83b1e5ba12456e7801e0554bceb6ea
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536311"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="b3d7c-103">Elementi cercati dalle funzioni dei criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="b3d7c-103">What the DLP functions look for</span></span>

<span data-ttu-id="b3d7c-104">La prevenzione della perdita di dati (DLP) include tipi di informazioni riservate, ad esempio il numero di carta di credito e il numero di carta di debito dell'Unione europea, che sono pronti per l'utilizzo nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-104">Data loss prevention (DLP) includes sensitive information types, such as credit card Number and EU Debit card number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="b3d7c-105">Questi tipi di informazioni riservate cercano uno schema specifico e lo confermano assicurando la corretta formattazione, applicando checksum e individuando parole chiave specifiche o altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="b3d7c-106">Alcune di queste funzionalità vengono eseguite da funzioni interne.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="b3d7c-107">Ad esempio, il tipo di informazioni riservate relative al numero di carta di credito utilizza una funzione per cercare le date formattate come una data di scadenza, in modo da confermare che si tratta di un numero di carta di credito.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="b3d7c-108">In questo articolo vengono illustrate le funzionalità che devono essere cercate per comprendere il funzionamento dei tipi di informazioni riservate predefinite.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-108">This article explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="b3d7c-109">Per ulteriori informazioni, vedere [definizioni di entità per il tipo di informazioni riservate](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="b3d7c-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="b3d7c-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="b3d7c-110">Func_us_date</span></span>

<span data-ttu-id="b3d7c-111">Questa funzione Cerca una data nel formato comunemente utilizzato negli Stati Uniti. Sono inclusi i formati "month/day/year", "month-day-year" e "month day year".</span><span class="sxs-lookup"><span data-stu-id="b3d7c-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="b3d7c-112">I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="b3d7c-113">Esempi:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-113">Examples:</span></span>
  
- <span data-ttu-id="b3d7c-114">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-114">December 2, 2016</span></span>
    
- <span data-ttu-id="b3d7c-115">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="b3d7c-116">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-116">dec 02 2016</span></span>
    
- <span data-ttu-id="b3d7c-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-117">12/2/2016</span></span>
    
- <span data-ttu-id="b3d7c-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="b3d7c-118">12/02/16</span></span>
    
- <span data-ttu-id="b3d7c-119">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="b3d7c-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="b3d7c-120">12-2-16</span></span>
    
<span data-ttu-id="b3d7c-121">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-121">Accepted month names:</span></span>
  
- <span data-ttu-id="b3d7c-122">English</span><span class="sxs-lookup"><span data-stu-id="b3d7c-122">English</span></span>
    
  - <span data-ttu-id="b3d7c-123">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="b3d7c-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="b3d7c-124">Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="b3d7c-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="b3d7c-125">Func_eu_date</span></span>

<span data-ttu-id="b3d7c-126">Questa funzione Cerca una data nel formato comunemente utilizzato nell'Unione</span><span class="sxs-lookup"><span data-stu-id="b3d7c-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="b3d7c-127">(e la maggior parte delle posizioni al di fuori degli Stati Uniti), ad esempio "Day/Month/Year", "Day-Month-Year" e "Day Month Year".</span><span class="sxs-lookup"><span data-stu-id="b3d7c-127">(and most places outside the U.S.), such as "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="b3d7c-128">I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-128">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="b3d7c-129">Esempi:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-129">Examples:</span></span>
  
- <span data-ttu-id="b3d7c-130">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-130">2 Dec 2016</span></span>
    
- <span data-ttu-id="b3d7c-131">02 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-131">02 dec 2016</span></span>
    
- <span data-ttu-id="b3d7c-132">2 dicembre 16</span><span class="sxs-lookup"><span data-stu-id="b3d7c-132">2 Dec 16</span></span>
    
- <span data-ttu-id="b3d7c-133">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-133">2/12/2016</span></span>
    
- <span data-ttu-id="b3d7c-134">02/12/16</span><span class="sxs-lookup"><span data-stu-id="b3d7c-134">02/12/16</span></span>
    
- <span data-ttu-id="b3d7c-135">2-Dec-2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-135">2-Dec-2016</span></span>
    
- <span data-ttu-id="b3d7c-136">2-12-16</span><span class="sxs-lookup"><span data-stu-id="b3d7c-136">2-12-16</span></span>
    
<span data-ttu-id="b3d7c-137">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-137">Accepted month names:</span></span>
  
- <span data-ttu-id="b3d7c-138">English</span><span class="sxs-lookup"><span data-stu-id="b3d7c-138">English</span></span>
    
  - <span data-ttu-id="b3d7c-139">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="b3d7c-139">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="b3d7c-140">Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-140">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="b3d7c-141">Dutch</span><span class="sxs-lookup"><span data-stu-id="b3d7c-141">Dutch</span></span>
    
  - <span data-ttu-id="b3d7c-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="b3d7c-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="b3d7c-143">Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec</span><span class="sxs-lookup"><span data-stu-id="b3d7c-143">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="b3d7c-144">French</span><span class="sxs-lookup"><span data-stu-id="b3d7c-144">French</span></span>
    
  - <span data-ttu-id="b3d7c-145">Janvier, février, Mars, avril, mai, Juin Juillet, août, septembre, Octobre, novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="b3d7c-145">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="b3d7c-146">janv.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-146">janv.</span></span> <span data-ttu-id="b3d7c-147">févr.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-147">févr.</span></span> <span data-ttu-id="b3d7c-148">Mars Avril mai juin juil.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-148">mars avril mai juin juil.</span></span> <span data-ttu-id="b3d7c-149">août sett.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-149">août sept.</span></span> <span data-ttu-id="b3d7c-150">personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-150">oct.</span></span> <span data-ttu-id="b3d7c-151">novembre.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-151">nov.</span></span> <span data-ttu-id="b3d7c-152">déc.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-152">déc.</span></span>
    
- <span data-ttu-id="b3d7c-153">German</span><span class="sxs-lookup"><span data-stu-id="b3d7c-153">German</span></span>
    
  - <span data-ttu-id="b3d7c-154">jänuar, febbraio, März, April, mai, Juni Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="b3d7c-154">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="b3d7c-155">Gen./Jän.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-155">Jan./Jän.</span></span> <span data-ttu-id="b3d7c-156">Feb. März apr. mai Juni luglio Okt.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-156">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="b3d7c-157">Nov. dic.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-157">Nov. Dez.</span></span>
    
- <span data-ttu-id="b3d7c-158">Italian</span><span class="sxs-lookup"><span data-stu-id="b3d7c-158">Italian</span></span>
    
  - <span data-ttu-id="b3d7c-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="b3d7c-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="b3d7c-160">Genn.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-160">genn.</span></span> <span data-ttu-id="b3d7c-161">febbr.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-161">febbr.</span></span> <span data-ttu-id="b3d7c-162">mar.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-162">mar.</span></span> <span data-ttu-id="b3d7c-163">apr.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-163">apr.</span></span> <span data-ttu-id="b3d7c-164">magg.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-164">magg.</span></span> <span data-ttu-id="b3d7c-165">giugno luglio AG.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-165">giugno luglio ag.</span></span> <span data-ttu-id="b3d7c-166">ovvero.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-166">sett.</span></span> <span data-ttu-id="b3d7c-167">ott.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-167">ott.</span></span> <span data-ttu-id="b3d7c-168">novembre.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-168">nov.</span></span> <span data-ttu-id="b3d7c-169">dic.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-169">dic.</span></span>
    
- <span data-ttu-id="b3d7c-170">Portoghese</span><span class="sxs-lookup"><span data-stu-id="b3d7c-170">Portuguese</span></span>
    
  - <span data-ttu-id="b3d7c-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="b3d7c-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="b3d7c-172">Jan FEV Mar ABR mai Jun Jul ago set out nov dic</span><span class="sxs-lookup"><span data-stu-id="b3d7c-172">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="b3d7c-173">Spanish</span><span class="sxs-lookup"><span data-stu-id="b3d7c-173">Spanish</span></span>
    
  - <span data-ttu-id="b3d7c-174">enero, febrero, marzo, Abril, Mayo, Junio, Julio, agosto, Septiembre, Octubre, Noviembre, Diciembre</span><span class="sxs-lookup"><span data-stu-id="b3d7c-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="b3d7c-175">enero feb.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-175">enero feb.</span></span> <span data-ttu-id="b3d7c-176">marzo ABR.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-176">marzo abr.</span></span> <span data-ttu-id="b3d7c-177">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-177">mayo jun.</span></span> <span data-ttu-id="b3d7c-178">luglio.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-178">jul.</span></span> <span data-ttu-id="b3d7c-179">agosto Sept/set.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-179">agosto sept./set.</span></span> <span data-ttu-id="b3d7c-180">personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-180">oct.</span></span> <span data-ttu-id="b3d7c-181">novembre.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-181">nov.</span></span> <span data-ttu-id="b3d7c-182">dic.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-182">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="b3d7c-183">Func_eu_date1 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="b3d7c-183">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="b3d7c-184">Questa funzione è obsoleta perché supporta solo i nomi dei mesi portoghesi, che ora sono inclusi nella `Func_eu_date` funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-184">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="b3d7c-185">Questa funzione consente di cercare una data nel formato comunemente utilizzato in portoghese.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-185">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="b3d7c-186">Il formato di questa funzione è lo stesso che `Func_eu_date` differisce solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-186">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="b3d7c-187">Esempi:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-187">Examples:</span></span>
  
- <span data-ttu-id="b3d7c-188">2 (2016).</span><span class="sxs-lookup"><span data-stu-id="b3d7c-188">2 Dez 2016</span></span>
    
- <span data-ttu-id="b3d7c-189">02 (2016).</span><span class="sxs-lookup"><span data-stu-id="b3d7c-189">02 dez 2016</span></span>
    
- <span data-ttu-id="b3d7c-190">2 con il 16</span><span class="sxs-lookup"><span data-stu-id="b3d7c-190">2 Dez 16</span></span>
    
- <span data-ttu-id="b3d7c-191">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-191">2/12/2016</span></span>
    
- <span data-ttu-id="b3d7c-192">02/12/16</span><span class="sxs-lookup"><span data-stu-id="b3d7c-192">02/12/16</span></span>
    
- <span data-ttu-id="b3d7c-193">2-------2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-193">2-Dez-2016</span></span>
    
- <span data-ttu-id="b3d7c-194">2-12-16</span><span class="sxs-lookup"><span data-stu-id="b3d7c-194">2-12-16</span></span>
    
<span data-ttu-id="b3d7c-195">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-195">Accepted month names:</span></span>
  
- <span data-ttu-id="b3d7c-196">Portoghese</span><span class="sxs-lookup"><span data-stu-id="b3d7c-196">Portuguese</span></span>
    
  - <span data-ttu-id="b3d7c-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="b3d7c-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="b3d7c-198">Jan FEV Mar ABR mai Jun Jul ago set out nov dic</span><span class="sxs-lookup"><span data-stu-id="b3d7c-198">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="b3d7c-199">Func_eu_date2 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="b3d7c-199">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="b3d7c-200">Questa funzione è obsoleta perché supporta solo i nomi dei mesi olandesi, che ora sono inclusi nella `Func_eu_date` funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-200">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="b3d7c-201">Questa funzione consente di cercare una data nel formato comunemente utilizzato in olandese.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-201">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="b3d7c-202">Il formato di questa funzione è lo stesso che `Func_eu_date` differisce solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-202">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="b3d7c-203">Esempi:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-203">Examples:</span></span>
  
- <span data-ttu-id="b3d7c-204">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-204">2 Mei 2016</span></span>
    
- <span data-ttu-id="b3d7c-205">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-205">02 mei 2016</span></span>
    
- <span data-ttu-id="b3d7c-206">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="b3d7c-206">2 Mei 16</span></span>
    
- <span data-ttu-id="b3d7c-207">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-207">2/12/2016</span></span>
    
- <span data-ttu-id="b3d7c-208">02/12/16</span><span class="sxs-lookup"><span data-stu-id="b3d7c-208">02/12/16</span></span>
    
- <span data-ttu-id="b3d7c-209">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="b3d7c-209">2-Mei-2016</span></span>
    
- <span data-ttu-id="b3d7c-210">2-12-16</span><span class="sxs-lookup"><span data-stu-id="b3d7c-210">2-12-16</span></span>
    
<span data-ttu-id="b3d7c-211">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-211">Accepted month names:</span></span>
  
- <span data-ttu-id="b3d7c-212">Dutch</span><span class="sxs-lookup"><span data-stu-id="b3d7c-212">Dutch</span></span>
    
  - <span data-ttu-id="b3d7c-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="b3d7c-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="b3d7c-214">Jan Feb maart apr Mei giu lug Aug Sep set out Okt Nov Dec</span><span class="sxs-lookup"><span data-stu-id="b3d7c-214">jan feb maart apr mei jun jul aug sep sept out okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="b3d7c-215">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="b3d7c-215">Func_expiration_date</span></span>

<span data-ttu-id="b3d7c-216">Questa funzione consente di cercare una data nei formati comunemente utilizzati da carte di credito e di debito, sostituendo i giorni con i mesi.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-216">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="b3d7c-217">Questa funzione corrisponderà alle date nel formato "month/year", "month-year", "[Month Name] Year" e "[month abbreviation] Year".</span><span class="sxs-lookup"><span data-stu-id="b3d7c-217">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="b3d7c-218">I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-218">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="b3d7c-219">Esempi:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-219">Examples:</span></span>
  
- <span data-ttu-id="b3d7c-220">MM/AA -- ad esempio, 01/11 o 1/11</span><span class="sxs-lookup"><span data-stu-id="b3d7c-220">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="b3d7c-221">MM/AAAA -- ad esempio, 01/2011 o 1/2011</span><span class="sxs-lookup"><span data-stu-id="b3d7c-221">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="b3d7c-222">MM-AA -- ad esempio, 01-22 o 1-11</span><span class="sxs-lookup"><span data-stu-id="b3d7c-222">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="b3d7c-223">MM-AAAA-- ad esempio, 01-2000 o 1-2000</span><span class="sxs-lookup"><span data-stu-id="b3d7c-223">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="b3d7c-224">I formati seguenti supportano AA o AAAA:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-224">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="b3d7c-225">Mese-AAAA--ad esempio gen-2010 o gennaio-2010 o gen-10 o gennaio-10</span><span class="sxs-lookup"><span data-stu-id="b3d7c-225">Month-YYYY -- for example Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="b3d7c-226">Mese AAAA -- ad esempio, "gennaio 2010" o "Gen 2010" o" gennaio 10" o "Gen 10"</span><span class="sxs-lookup"><span data-stu-id="b3d7c-226">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="b3d7c-227">MeseAAAA -- ad esempio, "gennaio2010" o "Gen2010" o "gennaio10" o "Gen10"</span><span class="sxs-lookup"><span data-stu-id="b3d7c-227">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="b3d7c-228">Mese/AAAA--ad esempio, "gennaio/2010" o "gen/2010" o "gennaio/10" o "gen/10"</span><span class="sxs-lookup"><span data-stu-id="b3d7c-228">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="b3d7c-229">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-229">Accepted month names:</span></span>
  
- <span data-ttu-id="b3d7c-230">English</span><span class="sxs-lookup"><span data-stu-id="b3d7c-230">English</span></span>
    
  - <span data-ttu-id="b3d7c-231">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="b3d7c-231">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="b3d7c-232">Gen feb mar apr maggio giugno luglio Aug settembre Ott Nov Dec</span><span class="sxs-lookup"><span data-stu-id="b3d7c-232">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="b3d7c-233">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="b3d7c-233">Func_us_address</span></span>

<span data-ttu-id="b3d7c-234">Questa funzione consente di cercare un nome di stato americano o una sigla postale seguita da un CAP valido, così come viene utilizzato negli indirizzi postali.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-234">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they're used in postal addresses.</span></span> <span data-ttu-id="b3d7c-235">Il CAP deve essere uno dei codici di avviamento postale corretti associati al nome o all'abbreviazione dello stato membro degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-235">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="b3d7c-236">Il nome dello stato membro degli Stati Uniti e il CAP non possono essere separati da segni di punteggiatura o lettere.</span><span class="sxs-lookup"><span data-stu-id="b3d7c-236">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="b3d7c-237">Esempi:</span><span class="sxs-lookup"><span data-stu-id="b3d7c-237">Examples:</span></span>
  
- <span data-ttu-id="b3d7c-238">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="b3d7c-238">Washington 98052</span></span>
    
- <span data-ttu-id="b3d7c-239">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="b3d7c-239">Washington 98052-9998</span></span>
    
- <span data-ttu-id="b3d7c-240">WA 98052</span><span class="sxs-lookup"><span data-stu-id="b3d7c-240">WA 98052</span></span>
    
- <span data-ttu-id="b3d7c-241">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="b3d7c-241">WA 98052-9998</span></span>
    

