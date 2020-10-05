---
title: Tipi di spiegazione
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informazioni sui tipi di spiegazione in Microsoft SharePoint Syntex
ms.openlocfilehash: 43272504912451e4690cb8b7fe351462371bb252
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350304"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="bf20a-103">Introduzione ai tipi di spiegazione</span><span class="sxs-lookup"><span data-stu-id="bf20a-103">Introduction to explanation types</span></span>

<span data-ttu-id="bf20a-104">Le spiegazioni vengono usate per definire meglio le informazioni da etichettare ed estrarre nei modelli di analisi dei documenti in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="bf20a-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="bf20a-105">Quando si crea una spiegazione, è necessario selezionare un tipo di spiegazione.</span><span class="sxs-lookup"><span data-stu-id="bf20a-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="bf20a-106">Questo articolo contiene informazioni utili per comprendere meglio i diversi tipi di spiegazione e come vengono usati.</span><span class="sxs-lookup"><span data-stu-id="bf20a-106">This article will help you learn more to better understand the different explanation types and how they are used.</span></span> 

   ![Tipi di spiegazione](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="bf20a-108">Sono disponibili questi tipi di spiegazione:</span><span class="sxs-lookup"><span data-stu-id="bf20a-108">These explanation types are available:</span></span>

- <span data-ttu-id="bf20a-109">**Elenco frasi**: elenco di parole, frasi, numeri o altri caratteri che è possibile usare nel documento o nelle informazioni che si stanno estraendo.</span><span class="sxs-lookup"><span data-stu-id="bf20a-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="bf20a-110">Ad esempio, la stringa di testo **Medico richiedente** è inclusa in tutti i documenti di richiesta di visita specialistica che si stanno identificando.</span><span class="sxs-lookup"><span data-stu-id="bf20a-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="bf20a-111">**Elenco criteri**: elenco di criteri di numeri, lettere o altri caratteri usati per identificare le informazioni che si stanno estraendo.</span><span class="sxs-lookup"><span data-stu-id="bf20a-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="bf20a-112">Ad esempio, è possibile estrarre il **numero di telefono** del medico richiedente da tutti i documenti di richiesta di visita specialistica che si stanno identificando.</span><span class="sxs-lookup"><span data-stu-id="bf20a-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="bf20a-113">**Prossimità**: descrive la relazione di prossimità tra le spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="bf20a-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="bf20a-114">Ad esempio, un elenco criteri *numero civico* precede immediatamente l'elenco di frasi *nome della via*, senza token intermedi (i token verranno illustrati più avanti in questo articolo).</span><span class="sxs-lookup"><span data-stu-id="bf20a-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="bf20a-115">Se si usa il tipo di prossimità, il modello deve includere almeno due spiegazioni, altrimenti l'opzione verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="bf20a-115">Using the proximity type requires you to have at least two explanations in your model, or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="bf20a-116">Elenco frasi</span><span class="sxs-lookup"><span data-stu-id="bf20a-116">Phrase list</span></span>

<span data-ttu-id="bf20a-117">Il tipo di spiegazione elenco frasi viene usato generalmente per identificare e classificare un documento tramite il modello.</span><span class="sxs-lookup"><span data-stu-id="bf20a-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="bf20a-118">Come descritto nell'esempio di etichetta *Medico richiedente*, si tratta di una stringa di parole, frasi, numeri o caratteri presente costantemente nei documenti che si stanno identificando.</span><span class="sxs-lookup"><span data-stu-id="bf20a-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="bf20a-119">Anche se non è necessario, la spiegazione risulta più efficace se la frase acquisita si trova in una posizione ricorrente nel documento.</span><span class="sxs-lookup"><span data-stu-id="bf20a-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="bf20a-120">Ad esempio, l'etichetta *Medico richiedente* potrebbe essere situata sempre nel primo paragrafo del documento.</span><span class="sxs-lookup"><span data-stu-id="bf20a-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="bf20a-121">Se la distinzione tra maiuscole e minuscole è un requisito per identificare l'etichetta, il tipo elenco frasi consente di specificarlo nella spiegazione selezionando la casella di controllo **Solo le maiuscole esatte**.</span><span class="sxs-lookup"><span data-stu-id="bf20a-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Distinzione tra maiuscole e minuscole](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="bf20a-123">Elenchi di criteri</span><span class="sxs-lookup"><span data-stu-id="bf20a-123">Pattern lists</span></span>

<span data-ttu-id="bf20a-124">Il tipo elenco criteri risulta particolarmente utile quando si crea una spiegazione che identifica ed estrae informazioni da un documento.</span><span class="sxs-lookup"><span data-stu-id="bf20a-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="bf20a-125">Generalmente viene presentato in vari formati, come date, numeri di telefono o numeri di carte di credito.</span><span class="sxs-lookup"><span data-stu-id="bf20a-125">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="bf20a-126">Ad esempio, una data può essere visualizzata in diversi formati (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 gen 2020 e così via).</span><span class="sxs-lookup"><span data-stu-id="bf20a-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="bf20a-127">La definizione di un elenco di criteri rende più efficace la spiegazione attraverso l'acquisizione di tutte le possibili varianti nei dati che si sta provando a identificare ed estrarre.</span><span class="sxs-lookup"><span data-stu-id="bf20a-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="bf20a-128">Per l'esempio relativo al **numero di telefono**, estrarre il numero di telefono per ogni medico richiedente da tutti i documenti di richiesta di visita specialistica identificati dal modello.</span><span class="sxs-lookup"><span data-stu-id="bf20a-128">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="bf20a-129">Quando si crea la spiegazione, selezionare il tipo Elenco criteri affinché vengano restituiti i vari formati previsti.</span><span class="sxs-lookup"><span data-stu-id="bf20a-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Elenco criteri numero di telefono](../media/content-understanding/pattern-list.png)

<span data-ttu-id="bf20a-131">Per questo esempio, selezionare la casella di controllo **Qualsiasi cifra da 0 a 9**.</span><span class="sxs-lookup"><span data-stu-id="bf20a-131">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="bf20a-132">Se si seleziona questa opzione, ogni valore "0" usato nell'elenco di criteri verrà riconosciuto come qualsiasi cifra compresa tra 0 e 9.</span><span class="sxs-lookup"><span data-stu-id="bf20a-132">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Qualsiasi cifra da 0 a 9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="bf20a-134">Analogamente, se si crea un elenco di criteri che include caratteri di testo, selezionare la casella di controllo **Qualsiasi lettera dalla a alla z**.</span><span class="sxs-lookup"><span data-stu-id="bf20a-134">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="bf20a-135">Se si seleziona questa opzione, ogni carattere "a" usato nell'elenco di criteri verrà riconosciuto come qualsiasi carattere dalla "a" alla "z".</span><span class="sxs-lookup"><span data-stu-id="bf20a-135">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="bf20a-136">Ad esempio, se si crea un elenco di criteri **Data** e si vuole fare in modo che venga riconosciuto un formato di data come *1 gen 2020*, è necessario:</span><span class="sxs-lookup"><span data-stu-id="bf20a-136">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="bf20a-137">Aggiungere *0 aaa 0000* e *00 aaa 0000* all'elenco criteri.</span><span class="sxs-lookup"><span data-stu-id="bf20a-137">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="bf20a-138">Assicurarsi che sia selezionata anche l'opzione **Qualsiasi lettera dalla a alla z**.</span><span class="sxs-lookup"><span data-stu-id="bf20a-138">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Qualsiasi lettera dalla a alla z](../media/content-understanding/any-letter.png)

<span data-ttu-id="bf20a-140">Inoltre, se l'elenco criteri prevede requisiti per le maiuscole, è possibile selezionare la casella di controllo **Solo le maiuscole esatte**.</span><span class="sxs-lookup"><span data-stu-id="bf20a-140">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="bf20a-141">Per l'esempio relativo alla data, se il mese deve avere l'iniziale minuscola, è necessario:</span><span class="sxs-lookup"><span data-stu-id="bf20a-141">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="bf20a-142">Aggiungere *0 aaa 0000* e *00 aaa 0000* all'elenco criteri.</span><span class="sxs-lookup"><span data-stu-id="bf20a-142">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="bf20a-143">Assicurarsi che sia selezionata anche l'opzione **Solo le maiuscole esatte**.</span><span class="sxs-lookup"><span data-stu-id="bf20a-143">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Solo le maiuscole esatte](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="bf20a-145">Anziché creare manualmente una spiegazione elenco criteri, usare la [raccolta spiegazioni](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) per usare modelli di elenchi di criteri predefiniti per elenchi di criteri comuni, quali *data*, *numero di telefono*, *numero di carta di credito* e così via.</span><span class="sxs-lookup"><span data-stu-id="bf20a-145">Instead of manually creating pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="bf20a-146">Prossimità</span><span class="sxs-lookup"><span data-stu-id="bf20a-146">Proximity</span></span> 

<span data-ttu-id="bf20a-147">Il tipo di spiegazione prossimità consente al modello di identificare i dati definendo il rapporto di prossimità rispetto ad altri dati.</span><span class="sxs-lookup"><span data-stu-id="bf20a-147">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="bf20a-148">Nel modello, ad esempio, sono state definite due spiegazioni che etichettano il *Numero civico* e il *Numero di telefono* del cliente.</span><span class="sxs-lookup"><span data-stu-id="bf20a-148">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="bf20a-149">Si nota anche che i numeri di telefono del cliente vengono sempre visualizzati sempre prima del numero civico.</span><span class="sxs-lookup"><span data-stu-id="bf20a-149">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="bf20a-150">Davide Milano</span><span class="sxs-lookup"><span data-stu-id="bf20a-150">Alex Wilburn</span></span><br>
<span data-ttu-id="bf20a-151">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="bf20a-151">555-555-5555</span></span><br>
<span data-ttu-id="bf20a-152">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="bf20a-152">One Microsoft Way</span></span><br>
<span data-ttu-id="bf20a-153">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="bf20a-153">Redmond, WA 98034</span></span><br>

<span data-ttu-id="bf20a-154">Usare la spiegazione di prossimità per definire quanto è lontana la spiegazione del numero di telefono, per identificare meglio il numero civico nei documenti.</span><span class="sxs-lookup"><span data-stu-id="bf20a-154">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Spiegazione di prossimità](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="bf20a-156">Che cosa sono i token?</span><span class="sxs-lookup"><span data-stu-id="bf20a-156">What are tokens?</span></span>

<span data-ttu-id="bf20a-157">Per usare il tipo di spiegazione di prossimità, è necessario comprendere che cos'è un token perché il numero di token è il sistema usato dalla spiegazione di prossimità per misurare la distanza tra una spiegazione e l'altra.</span><span class="sxs-lookup"><span data-stu-id="bf20a-157">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="bf20a-158">Un token è una serie continua di lettere e numeri, senza spazi o punteggiatura.</span><span class="sxs-lookup"><span data-stu-id="bf20a-158">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="bf20a-159">Uno spazio NON è un token.</span><span class="sxs-lookup"><span data-stu-id="bf20a-159">A space is NOT a token.</span></span> <span data-ttu-id="bf20a-160">Ogni segno di punteggiatura è un token.</span><span class="sxs-lookup"><span data-stu-id="bf20a-160">Each punctuation character is a token.</span></span> <span data-ttu-id="bf20a-161">Nella tabella seguente sono illustrati alcuni esempi per determinare il numero di token in una frase.</span><span class="sxs-lookup"><span data-stu-id="bf20a-161">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="bf20a-162">Frase</span><span class="sxs-lookup"><span data-stu-id="bf20a-162">Phrase</span></span>|<span data-ttu-id="bf20a-163">Numero di token</span><span class="sxs-lookup"><span data-stu-id="bf20a-163">Number of tokens</span></span>|<span data-ttu-id="bf20a-164">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="bf20a-164">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="bf20a-165">1</span><span class="sxs-lookup"><span data-stu-id="bf20a-165">1</span></span>|<span data-ttu-id="bf20a-166">Una singola parola senza punteggiatura o spazi.</span><span class="sxs-lookup"><span data-stu-id="bf20a-166">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="bf20a-167">1</span><span class="sxs-lookup"><span data-stu-id="bf20a-167">1</span></span>|<span data-ttu-id="bf20a-168">Un numero di localizzazione record.</span><span class="sxs-lookup"><span data-stu-id="bf20a-168">A record locator number.</span></span> <span data-ttu-id="bf20a-169">Può contenere numeri e lettere, ma non include segni di punteggiatura.</span><span class="sxs-lookup"><span data-stu-id="bf20a-169">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="bf20a-170">5</span><span class="sxs-lookup"><span data-stu-id="bf20a-170">5</span></span>|<span data-ttu-id="bf20a-171">Un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="bf20a-171">A phone number.</span></span> <span data-ttu-id="bf20a-172">Ogni segno di punteggiatura è un token, quindi `425-555-5555` corrisponderebbe a 5 token:</span><span class="sxs-lookup"><span data-stu-id="bf20a-172">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="bf20a-173">7</span><span class="sxs-lookup"><span data-stu-id="bf20a-173">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="bf20a-174">Configurare il tipo di spiegazione di prossimità</span><span class="sxs-lookup"><span data-stu-id="bf20a-174">Configure the proximity explanation type</span></span>

<span data-ttu-id="bf20a-175">Per l'esempio, configurare l'impostazione di prossimità in modo da poter definire l'intervallo del numero di token di distanza tra la spiegazione *Numero di telefono* e la spiegazione *Numero civico*.</span><span class="sxs-lookup"><span data-stu-id="bf20a-175">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="bf20a-176">L'intervallo minimo dovrebbe risultare "0" perché non c'è nessun token tra il numero di telefono e il numero civico.</span><span class="sxs-lookup"><span data-stu-id="bf20a-176">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="bf20a-177">Dopo alcuni numeri di telefono nei documenti di esempio, invece, è presente la dicitura *(cellulare)*.</span><span class="sxs-lookup"><span data-stu-id="bf20a-177">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="bf20a-178">Luca Udinesi</span><span class="sxs-lookup"><span data-stu-id="bf20a-178">Nestor Wilke</span></span><br>
<span data-ttu-id="bf20a-179">111-111-1111 (cellulare)</span><span class="sxs-lookup"><span data-stu-id="bf20a-179">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="bf20a-180">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="bf20a-180">One Microsoft Way</span></span><br>
<span data-ttu-id="bf20a-181">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="bf20a-181">Redmond, WA 98034</span></span><br>

<span data-ttu-id="bf20a-182">In *(cellulare)* sono presenti tre token:</span><span class="sxs-lookup"><span data-stu-id="bf20a-182">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="bf20a-183">Frase</span><span class="sxs-lookup"><span data-stu-id="bf20a-183">Phrase</span></span>|<span data-ttu-id="bf20a-184">Numero di token</span><span class="sxs-lookup"><span data-stu-id="bf20a-184">Token count</span></span>|
|--|--|
|<span data-ttu-id="bf20a-185">(</span><span class="sxs-lookup"><span data-stu-id="bf20a-185">(</span></span>|<span data-ttu-id="bf20a-186">1</span><span class="sxs-lookup"><span data-stu-id="bf20a-186">1</span></span>|
|<span data-ttu-id="bf20a-187">cellulare</span><span class="sxs-lookup"><span data-stu-id="bf20a-187">mobile</span></span>|<span data-ttu-id="bf20a-188">2</span><span class="sxs-lookup"><span data-stu-id="bf20a-188">2</span></span>|
|<span data-ttu-id="bf20a-189">)</span><span class="sxs-lookup"><span data-stu-id="bf20a-189">)</span></span>|<span data-ttu-id="bf20a-190">3</span><span class="sxs-lookup"><span data-stu-id="bf20a-190">3</span></span>|

<span data-ttu-id="bf20a-191">Configurare l'impostazione di prossimità su un intervallo compreso tra 0 e 3.</span><span class="sxs-lookup"><span data-stu-id="bf20a-191">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Esempio di prossimità](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="bf20a-193">Usare modelli di spiegazione</span><span class="sxs-lookup"><span data-stu-id="bf20a-193">Use explanation templates</span></span>

<span data-ttu-id="bf20a-194">Anche se è possibile aggiungere manualmente vari valori dell'elenco di criteri per la spiegazione, può essere molto più semplice usare i modelli predefiniti disponibili nella raccolta di spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="bf20a-194">While you can manually add various pattern list values for your explanation, it can be much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="bf20a-195">Ad esempio, invece di aggiungere manualmente tutte le varianti per *Data*, è possibile usare il modello di elenco pattern per *Data*, che include già molti valori di elenchi di criteri:</span><span class="sxs-lookup"><span data-stu-id="bf20a-195">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Raccolta di spiegazioni](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="bf20a-197">La raccolta di spiegazioni include una serie di spiegazioni elenco di criteri di uso comune, tra cui:</span><span class="sxs-lookup"><span data-stu-id="bf20a-197">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="bf20a-198">Data</span><span class="sxs-lookup"><span data-stu-id="bf20a-198">Date</span></span></br>
- <span data-ttu-id="bf20a-199">Data (numerico)</span><span class="sxs-lookup"><span data-stu-id="bf20a-199">Date (numeric)</span></span></br>
- <span data-ttu-id="bf20a-200">Ora</span><span class="sxs-lookup"><span data-stu-id="bf20a-200">Time</span></span></br>
- <span data-ttu-id="bf20a-201">Numero</span><span class="sxs-lookup"><span data-stu-id="bf20a-201">Number</span></span></br>
- <span data-ttu-id="bf20a-202">Numero di telefono</span><span class="sxs-lookup"><span data-stu-id="bf20a-202">Phone number</span></span></br>
- <span data-ttu-id="bf20a-203">CAP</span><span class="sxs-lookup"><span data-stu-id="bf20a-203">Zip code</span></span></br>
- <span data-ttu-id="bf20a-204">Prima parola della frase</span><span class="sxs-lookup"><span data-stu-id="bf20a-204">First word of sentence</span></span></br>
- <span data-ttu-id="bf20a-205">Carta di credito</span><span class="sxs-lookup"><span data-stu-id="bf20a-205">Credit card</span></span></br>
- <span data-ttu-id="bf20a-206">Numero di previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="bf20a-206">Social security number</span></span></br>

<span data-ttu-id="bf20a-207">Si noti che la raccolta di spiegazioni include anche modelli per le spiegazioni elenco di frasi, tra cui:</span><span class="sxs-lookup"><span data-stu-id="bf20a-207">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="bf20a-208">Fine della frase</span><span class="sxs-lookup"><span data-stu-id="bf20a-208">End of sentence</span></span>
- <span data-ttu-id="bf20a-209">Valuta</span><span class="sxs-lookup"><span data-stu-id="bf20a-209">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="bf20a-210">Per usare un modello dalla raccolta di spiegazioni</span><span class="sxs-lookup"><span data-stu-id="bf20a-210">To use a template from the explanation library</span></span>

1. <span data-ttu-id="bf20a-211">Nella sezione **Spiegazioni** della pagina **Avvia training** del modello selezionare **Nuovo**, quindi **Da un modello**.</span><span class="sxs-lookup"><span data-stu-id="bf20a-211">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Crea da modello](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="bf20a-213">Nella pagina **Modelli di spiegazione** selezionare la spiegazione da usare, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bf20a-213">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Selezionare un modello](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="bf20a-215">Le informazioni relative al modello selezionato verranno visualizzate nella pagina **Crea spiegazione**.</span><span class="sxs-lookup"><span data-stu-id="bf20a-215">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="bf20a-216">Se necessario, modificare il nome della spiegazione e aggiungere o rimuovere voci nell'elenco criteri.</span><span class="sxs-lookup"><span data-stu-id="bf20a-216">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Modifica modello](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="bf20a-218">Al termine, selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bf20a-218">When finished, select **Save**.</span></span>
