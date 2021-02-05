---
title: Tipi di spiegazione
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informazioni sui tipi di spiegazione in Microsoft SharePoint Syntex
ms.openlocfilehash: 2c2997fd165339cc43f7f007050f343794021a23
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080587"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="62e10-103">Introduzione ai tipi di spiegazione</span><span class="sxs-lookup"><span data-stu-id="62e10-103">Introduction to explanation types</span></span>

<span data-ttu-id="62e10-104">Le spiegazioni vengono usate per definire meglio le informazioni da etichettare ed estrarre nei modelli di analisi dei documenti in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="62e10-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="62e10-105">Quando si crea una spiegazione, è necessario selezionare un tipo di spiegazione.</span><span class="sxs-lookup"><span data-stu-id="62e10-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="62e10-106">Questo articolo contiene informazioni utili per comprendere i diversi tipi di spiegazione e come vengono usati.</span><span class="sxs-lookup"><span data-stu-id="62e10-106">This article helps you understand the different explanation types and how they are used.</span></span> 

   ![Tipi di spiegazione](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="62e10-108">Sono disponibili questi tipi di spiegazione:</span><span class="sxs-lookup"><span data-stu-id="62e10-108">These explanation types are available:</span></span>

- <span data-ttu-id="62e10-109">**Elenco frasi**: elenco di parole, frasi, numeri o altri caratteri che è possibile usare nel documento o nelle informazioni che si stanno estraendo.</span><span class="sxs-lookup"><span data-stu-id="62e10-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="62e10-110">Ad esempio, la stringa di testo **Medico richiedente** è inclusa in tutti i documenti di richiesta di visita specialistica che si stanno identificando.</span><span class="sxs-lookup"><span data-stu-id="62e10-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="62e10-111">**Elenco criteri**: elenco di criteri di numeri, lettere o altri caratteri usati per identificare le informazioni che si stanno estraendo.</span><span class="sxs-lookup"><span data-stu-id="62e10-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="62e10-112">Ad esempio, è possibile estrarre il **numero di telefono** del medico richiedente da tutti i documenti di richiesta di visita specialistica che si stanno identificando.</span><span class="sxs-lookup"><span data-stu-id="62e10-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="62e10-113">**Prossimità**: descrive la relazione di prossimità tra le spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="62e10-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="62e10-114">Ad esempio, un elenco criteri *numero civico* precede immediatamente l'elenco di frasi *nome della via*, senza token intermedi (i token verranno illustrati più avanti in questo articolo).</span><span class="sxs-lookup"><span data-stu-id="62e10-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="62e10-115">Se si usa il tipo di prossimità, il modello deve includere almeno due spiegazioni, altrimenti l'opzione verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="62e10-115">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="62e10-116">Elenco frasi</span><span class="sxs-lookup"><span data-stu-id="62e10-116">Phrase list</span></span>

<span data-ttu-id="62e10-117">Il tipo di spiegazione elenco frasi viene usato generalmente per identificare e classificare un documento tramite il modello.</span><span class="sxs-lookup"><span data-stu-id="62e10-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="62e10-118">Come descritto nell'esempio di etichetta *Medico richiedente*, si tratta di una stringa di parole, frasi, numeri o caratteri presente costantemente nei documenti che si stanno identificando.</span><span class="sxs-lookup"><span data-stu-id="62e10-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="62e10-119">Anche se non è necessario, la spiegazione risulta più efficace se la frase acquisita si trova in una posizione ricorrente nel documento.</span><span class="sxs-lookup"><span data-stu-id="62e10-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="62e10-120">Ad esempio, l'etichetta *Medico richiedente* potrebbe essere situata sempre nel primo paragrafo del documento.</span><span class="sxs-lookup"><span data-stu-id="62e10-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="62e10-121">Se la distinzione tra maiuscole e minuscole è un requisito per identificare l'etichetta, il tipo elenco frasi consente di specificarlo nella spiegazione selezionando la casella di controllo **Solo le maiuscole esatte**.</span><span class="sxs-lookup"><span data-stu-id="62e10-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Distinzione tra maiuscole e minuscole](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="62e10-123">Elenchi di criteri</span><span class="sxs-lookup"><span data-stu-id="62e10-123">Pattern lists</span></span>

<span data-ttu-id="62e10-124">Il tipo elenco criteri risulta particolarmente utile quando si crea una spiegazione che identifica ed estrae informazioni da un documento.</span><span class="sxs-lookup"><span data-stu-id="62e10-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="62e10-125">Generalmente viene presentato in vari formati, come date, numeri di telefono e numeri di carte di credito.</span><span class="sxs-lookup"><span data-stu-id="62e10-125">It is typically presented in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="62e10-126">Ad esempio, una data può essere visualizzata in diversi formati (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 gen 2020 e così via).</span><span class="sxs-lookup"><span data-stu-id="62e10-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="62e10-127">La definizione di un elenco di criteri rende più efficace la spiegazione attraverso l'acquisizione di tutte le possibili varianti nei dati che si sta provando a identificare ed estrarre.</span><span class="sxs-lookup"><span data-stu-id="62e10-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="62e10-128">Per l'esempio relativo al **numero di telefono**, estrarre il numero di telefono per ogni medico richiedente da tutti i documenti di richiesta di visita specialistica identificati dal modello.</span><span class="sxs-lookup"><span data-stu-id="62e10-128">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="62e10-129">Quando si crea la spiegazione, selezionare il tipo Elenco criteri affinché vengano restituiti i vari formati previsti.</span><span class="sxs-lookup"><span data-stu-id="62e10-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Elenco criteri numero di telefono](../media/content-understanding/pattern-list.png)

<span data-ttu-id="62e10-131">Nel caso di questo esempio, selezionare la casella di controllo **Qualsiasi cifra da 0 a 9** per riconoscere ogni valore "0" usato nell'elenco dei criteri come qualsiasi cifra da 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="62e10-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Qualsiasi cifra da 0 a 9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="62e10-133">Analogamente, se si crea un elenco di criteri che include caratteri di testo, selezionare la casella di controllo **Qualsiasi lettera dalla a alla z** per riconoscere ogni carattere "a" usato nell'elenco dei criteri per essere qualsiasi carattere compreso dalla "a" alla "z".</span><span class="sxs-lookup"><span data-stu-id="62e10-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="62e10-134">Ad esempio, se si crea un elenco di criteri **Data** e si vuole fare in modo che venga riconosciuto un formato di data come *1 gen 2020*, è necessario:</span><span class="sxs-lookup"><span data-stu-id="62e10-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="62e10-135">Aggiungere *0 aaa 0000* e *00 aaa 0000* all'elenco criteri.</span><span class="sxs-lookup"><span data-stu-id="62e10-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="62e10-136">Assicurarsi che sia selezionata anche l'opzione **Qualsiasi lettera dalla a alla z**.</span><span class="sxs-lookup"><span data-stu-id="62e10-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Qualsiasi lettera dalla a alla z](../media/content-understanding/any-letter.png)

<span data-ttu-id="62e10-138">Inoltre, se l'elenco criteri prevede requisiti per le maiuscole, è possibile selezionare la casella di controllo **Solo le maiuscole esatte**.</span><span class="sxs-lookup"><span data-stu-id="62e10-138">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="62e10-139">Per l'esempio relativo alla data, se il mese deve avere l'iniziale minuscola, è necessario:</span><span class="sxs-lookup"><span data-stu-id="62e10-139">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="62e10-140">Aggiungere *0 aaa 0000* e *00 aaa 0000* all'elenco criteri.</span><span class="sxs-lookup"><span data-stu-id="62e10-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="62e10-141">Assicurarsi che sia selezionata anche l'opzione **Solo le maiuscole esatte**.</span><span class="sxs-lookup"><span data-stu-id="62e10-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Solo le maiuscole esatte](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="62e10-143">Anziché creare manualmente una spiegazione elenco criteri, usare la [raccolta spiegazioni](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) per usare modelli di elenchi di criteri per elenchi di criteri comuni, quali *Data*, *Numero di telefono*, *Numero di carta di credito* e così via.</span><span class="sxs-lookup"><span data-stu-id="62e10-143">Instead of manually creating a pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="62e10-144">Prossimità</span><span class="sxs-lookup"><span data-stu-id="62e10-144">Proximity</span></span> 

<span data-ttu-id="62e10-145">Il tipo di spiegazione prossimità consente al modello di identificare i dati definendo il rapporto di prossimità rispetto ad altri dati.</span><span class="sxs-lookup"><span data-stu-id="62e10-145">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="62e10-146">Nel modello, ad esempio, sono state definite due spiegazioni che etichettano il *Numero civico* e il *Numero di telefono* del cliente.</span><span class="sxs-lookup"><span data-stu-id="62e10-146">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="62e10-147">Si nota anche che i numeri di telefono del cliente vengono sempre visualizzati sempre prima del numero civico.</span><span class="sxs-lookup"><span data-stu-id="62e10-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="62e10-148">Davide Milano</span><span class="sxs-lookup"><span data-stu-id="62e10-148">Alex Wilburn</span></span><br>
<span data-ttu-id="62e10-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="62e10-149">555-555-5555</span></span><br>
<span data-ttu-id="62e10-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="62e10-150">One Microsoft Way</span></span><br>
<span data-ttu-id="62e10-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="62e10-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="62e10-152">Usare la spiegazione di prossimità per definire quanto è lontana la spiegazione del numero di telefono, per identificare meglio il numero civico nei documenti.</span><span class="sxs-lookup"><span data-stu-id="62e10-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Spiegazione di prossimità](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="62e10-154">Che cosa sono i token?</span><span class="sxs-lookup"><span data-stu-id="62e10-154">What are tokens?</span></span>

<span data-ttu-id="62e10-155">Per usare il tipo di spiegazione di prossimità, è necessario comprendere che cos'è un token perché il numero di token è il sistema usato dalla spiegazione di prossimità per misurare la distanza tra una spiegazione e l'altra.</span><span class="sxs-lookup"><span data-stu-id="62e10-155">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="62e10-156">Un token è una serie continua di lettere e numeri, senza spazi o punteggiatura.</span><span class="sxs-lookup"><span data-stu-id="62e10-156">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="62e10-157">Nella tabella seguente sono illustrati alcuni esempi per determinare il numero di token in una frase.</span><span class="sxs-lookup"><span data-stu-id="62e10-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="62e10-158">Frase</span><span class="sxs-lookup"><span data-stu-id="62e10-158">Phrase</span></span>|<span data-ttu-id="62e10-159">Numero di token</span><span class="sxs-lookup"><span data-stu-id="62e10-159">Number of tokens</span></span>|<span data-ttu-id="62e10-160">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="62e10-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="62e10-161">1</span><span class="sxs-lookup"><span data-stu-id="62e10-161">1</span></span>|<span data-ttu-id="62e10-162">Una singola parola senza punteggiatura o spazi.</span><span class="sxs-lookup"><span data-stu-id="62e10-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="62e10-163">1</span><span class="sxs-lookup"><span data-stu-id="62e10-163">1</span></span>|<span data-ttu-id="62e10-164">Un numero di localizzazione record.</span><span class="sxs-lookup"><span data-stu-id="62e10-164">A record locator number.</span></span> <span data-ttu-id="62e10-165">Può includere numeri e lettere, ma non include segni di punteggiatura.</span><span class="sxs-lookup"><span data-stu-id="62e10-165">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="62e10-166">5</span><span class="sxs-lookup"><span data-stu-id="62e10-166">5</span></span>|<span data-ttu-id="62e10-167">Un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="62e10-167">A phone number.</span></span> <span data-ttu-id="62e10-168">Ogni segno di punteggiatura è un token, quindi `425-555-5555` corrisponde a 5 token:</span><span class="sxs-lookup"><span data-stu-id="62e10-168">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="62e10-169">7</span><span class="sxs-lookup"><span data-stu-id="62e10-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="62e10-170">Configurare il tipo di spiegazione di prossimità</span><span class="sxs-lookup"><span data-stu-id="62e10-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="62e10-171">Per questo esempio, configurare l'impostazione di prossimità in modo da poter definire l'intervallo del numero di token di distanza nella spiegazione *Numero di telefono* dalla spiegazione *Numero civico*.</span><span class="sxs-lookup"><span data-stu-id="62e10-171">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="62e10-172">Si noti che l'intervallo minimo dovrebbe risultare "0" perché non c'è nessun token tra il numero di telefono e il numero civico.</span><span class="sxs-lookup"><span data-stu-id="62e10-172">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="62e10-173">Dopo alcuni numeri di telefono nei documenti di esempio, invece, è presente la dicitura *(cellulare)*.</span><span class="sxs-lookup"><span data-stu-id="62e10-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="62e10-174">Luca Udinesi</span><span class="sxs-lookup"><span data-stu-id="62e10-174">Nestor Wilke</span></span><br>
<span data-ttu-id="62e10-175">111-111-1111 (cellulare)</span><span class="sxs-lookup"><span data-stu-id="62e10-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="62e10-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="62e10-176">One Microsoft Way</span></span><br>
<span data-ttu-id="62e10-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="62e10-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="62e10-178">In *(cellulare)* sono presenti tre token:</span><span class="sxs-lookup"><span data-stu-id="62e10-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="62e10-179">Frase</span><span class="sxs-lookup"><span data-stu-id="62e10-179">Phrase</span></span>|<span data-ttu-id="62e10-180">Numero di token</span><span class="sxs-lookup"><span data-stu-id="62e10-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="62e10-181">(</span><span class="sxs-lookup"><span data-stu-id="62e10-181">(</span></span>|<span data-ttu-id="62e10-182">1</span><span class="sxs-lookup"><span data-stu-id="62e10-182">1</span></span>|
|<span data-ttu-id="62e10-183">cellulare</span><span class="sxs-lookup"><span data-stu-id="62e10-183">mobile</span></span>|<span data-ttu-id="62e10-184">2</span><span class="sxs-lookup"><span data-stu-id="62e10-184">2</span></span>|
|<span data-ttu-id="62e10-185">)</span><span class="sxs-lookup"><span data-stu-id="62e10-185">)</span></span>|<span data-ttu-id="62e10-186">3</span><span class="sxs-lookup"><span data-stu-id="62e10-186">3</span></span>|

<span data-ttu-id="62e10-187">Configurare l'impostazione di prossimità su un intervallo compreso tra 0 e 3.</span><span class="sxs-lookup"><span data-stu-id="62e10-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Esempio di prossimità](../media/content-understanding/proximity-example.png)</br>


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="62e10-189">Configurare la posizione delle frasi nel documento</span><span class="sxs-lookup"><span data-stu-id="62e10-189">Configure where phrases occur in the document</span></span>

<span data-ttu-id="62e10-190">Quando si crea una spiegazione, per impostazione predefinita viene cercata nell'intero documento la frase che si vuole estrarre.</span><span class="sxs-lookup"><span data-stu-id="62e10-190">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="62e10-191">Tuttavia, è possibile usare l'impostazione avanzata <b>Dove si trovano queste frasi</b> per isolare una posizione specifica nel documento in cui si trova una frase.</span><span class="sxs-lookup"><span data-stu-id="62e10-191">However, you can use the <b>Where these phrases occur</b> advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="62e10-192">Questa funzione è utile nei casi in cui istanze simili di una frase potrebbero comparire in un altro punto del documento e si vuole verificare che sia selezionata quella corretta.</span><span class="sxs-lookup"><span data-stu-id="62e10-192">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="62e10-193">Facendo riferimento all'esempio relativo al documento di richiesta di visita specialistica il **medico richiedente** viene sempre menzionato nel primo paragrafo del documento.</span><span class="sxs-lookup"><span data-stu-id="62e10-193">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="62e10-194">Con l'impostazione <b>Dove si trovano queste frasi</b>, in questo esempio è possibile configurare la spiegazione per la ricerca di questa etichetta solo nella sezione iniziale del documento o in qualsiasi altra posizione in cui potrebbe essere presente.</span><span class="sxs-lookup"><span data-stu-id="62e10-194">With the <b>Where these phrases occur</b> setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

   ![Impostazione Dove si trovano queste frasi](../media/content-understanding/phrase-location.png)</br>

<span data-ttu-id="62e10-196">Per questa impostazione è possibile scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="62e10-196">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="62e10-197">Ovunque nel file: la frase viene cercata nell'intero documento.</span><span class="sxs-lookup"><span data-stu-id="62e10-197">Anywhere in the file: The entire document is searched for the phrase.</span></span>
- <span data-ttu-id="62e10-198">Inizio del file: la ricerca viene eseguita dall'inizio del documento fino alla posizione della frase.</span><span class="sxs-lookup"><span data-stu-id="62e10-198">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span></br> 
   <span data-ttu-id="62e10-199">![Inizio del file](../media/content-understanding/beginning-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="62e10-199">![Beginning of file](../media/content-understanding/beginning-of-file.png)</span></span></br>
<span data-ttu-id="62e10-200">Nel visualizzatore è possibile modificare manualmente la casella di selezione in modo da includere la posizione in cui si trova la fase.</span><span class="sxs-lookup"><span data-stu-id="62e10-200">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="62e10-201">Il valore <b>Posizione finale</b> verrà aggiornato per mostrare il numero di token inclusi nell'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="62e10-201">The <b>End position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="62e10-202">Si noti che è possibile aggiornare il valore Posizione finale anche per modificare l'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="62e10-202">Note that you can update the End position value as well to adjust the selected area.</span></span></br>
   <span data-ttu-id="62e10-203">![Casella con la posizione Inizio del file](../media/content-understanding/beginning-box.png)</span><span class="sxs-lookup"><span data-stu-id="62e10-203">![Beginning of file position box](../media/content-understanding/beginning-box.png)</span></span></br>

- <span data-ttu-id="62e10-204">Fine del file: la ricerca viene eseguita dalla fine del documento fino alla posizione della frase.</span><span class="sxs-lookup"><span data-stu-id="62e10-204">End of the file:  The document is searched from the end to the phrase location.</span></span></br> 
   <span data-ttu-id="62e10-205">![Fine del file](../media/content-understanding/end-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="62e10-205">![End of file](../media/content-understanding/end-of-file.png)</span></span></br>
<span data-ttu-id="62e10-206">Nel visualizzatore è possibile modificare manualmente la casella di selezione in modo da includere la posizione in cui si trova la fase.</span><span class="sxs-lookup"><span data-stu-id="62e10-206">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="62e10-207">Il valore <b>Posizione iniziale</b> verrà aggiornato per mostrare il numero di token inclusi nell'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="62e10-207">The <b>Starting position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="62e10-208">Si noti che è possibile aggiornare il valore Posizione iniziale anche per modificare l'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="62e10-208">Note that you can update the Starting position value as well to adjust the selected area.</span></span></br> 
   <span data-ttu-id="62e10-209">![Casella con la posizione Fine del file](../media/content-understanding/end-box.png)</span><span class="sxs-lookup"><span data-stu-id="62e10-209">![End of file end box](../media/content-understanding/end-box.png)</span></span></br>
- <span data-ttu-id="62e10-210">Intervallo personalizzato: la posizione della frase viene cercata in un intervallo specificato all’interno del documento.</span><span class="sxs-lookup"><span data-stu-id="62e10-210">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span></br> 
   <span data-ttu-id="62e10-211">![Intervallo personalizzato](../media/content-understanding/custom-file.png)</span><span class="sxs-lookup"><span data-stu-id="62e10-211">![Custom range](../media/content-understanding/custom-file.png)</span></span></br>
<span data-ttu-id="62e10-212">Nel visualizzatore è possibile modificare manualmente la casella di selezione in modo da includere la posizione in cui si trova la fase.</span><span class="sxs-lookup"><span data-stu-id="62e10-212">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="62e10-213">Per questa impostazione è necessario selezionare una posizione di <b>Inizio</b> e di <b>Fine</b>.</span><span class="sxs-lookup"><span data-stu-id="62e10-213">For this setting, you need to select a <b>Start</b> and an <b>End</b> position.</span></span> <span data-ttu-id="62e10-214">Questi valori rappresentano il numero di token dall'inizio del documento.</span><span class="sxs-lookup"><span data-stu-id="62e10-214">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="62e10-215">Anche se è possibile immettere manualmente questi valori, è più facile modificare manualmente la casella di selezione nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="62e10-215">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span></br> 
   


## <a name="use-explanation-templates"></a><span data-ttu-id="62e10-216">Usare modelli di spiegazione</span><span class="sxs-lookup"><span data-stu-id="62e10-216">Use explanation templates</span></span>

<span data-ttu-id="62e10-217">Anche se è possibile aggiungere manualmente vari valori dell'elenco di criteri per la spiegazione, può essere più semplice usare i modelli disponibili nella raccolta di spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="62e10-217">While you can manually add various pattern list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="62e10-218">Ad esempio, invece di aggiungere manualmente tutte le varianti per *Data*, è possibile usare il modello di elenco pattern per *Data*, poiché include già molti valori di elenchi di criteri:</span><span class="sxs-lookup"><span data-stu-id="62e10-218">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date* as it already includes a number of pattern lists values:</span></span></br>

   ![Raccolta di spiegazioni](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="62e10-220">La raccolta di spiegazioni include spiegazioni di elenchi di criteri di uso comune, tra cui:</span><span class="sxs-lookup"><span data-stu-id="62e10-220">The explanation library includes commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="62e10-221">Data</span><span class="sxs-lookup"><span data-stu-id="62e10-221">Date</span></span></br>
- <span data-ttu-id="62e10-222">Data (numerico)</span><span class="sxs-lookup"><span data-stu-id="62e10-222">Date (numeric)</span></span></br>
- <span data-ttu-id="62e10-223">Ora</span><span class="sxs-lookup"><span data-stu-id="62e10-223">Time</span></span></br>
- <span data-ttu-id="62e10-224">Numero</span><span class="sxs-lookup"><span data-stu-id="62e10-224">Number</span></span></br>
- <span data-ttu-id="62e10-225">Numero di telefono</span><span class="sxs-lookup"><span data-stu-id="62e10-225">Phone number</span></span></br>
- <span data-ttu-id="62e10-226">CAP</span><span class="sxs-lookup"><span data-stu-id="62e10-226">Zip code</span></span></br>
- <span data-ttu-id="62e10-227">Prima parola della frase</span><span class="sxs-lookup"><span data-stu-id="62e10-227">First word of sentence</span></span></br>
- <span data-ttu-id="62e10-228">Carta di credito</span><span class="sxs-lookup"><span data-stu-id="62e10-228">Credit card</span></span></br>
- <span data-ttu-id="62e10-229">Numero di previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="62e10-229">Social security number</span></span></br>

<span data-ttu-id="62e10-230">Si noti che la raccolta di spiegazioni include modelli per le spiegazioni elenco di frasi:</span><span class="sxs-lookup"><span data-stu-id="62e10-230">Note that the explanation library also includes templates for phrase list explanations:</span></span>
- <span data-ttu-id="62e10-231">Fine della frase</span><span class="sxs-lookup"><span data-stu-id="62e10-231">End of sentence</span></span>
- <span data-ttu-id="62e10-232">Valuta</span><span class="sxs-lookup"><span data-stu-id="62e10-232">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="62e10-233">Per usare un modello dalla raccolta di spiegazioni</span><span class="sxs-lookup"><span data-stu-id="62e10-233">To use a template from the explanation library</span></span>

1. <span data-ttu-id="62e10-234">Nella sezione **Spiegazioni** della pagina **Avvia training** del modello selezionare **Nuovo**, quindi **Da un modello**.</span><span class="sxs-lookup"><span data-stu-id="62e10-234">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Crea da modello](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="62e10-236">Nella pagina **Modelli di spiegazione** selezionare la spiegazione da usare, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="62e10-236">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![Selezionare un modello](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="62e10-238">Le informazioni relative al modello selezionato sono visualizzate nella pagina **Crea spiegazione**.</span><span class="sxs-lookup"><span data-stu-id="62e10-238">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="62e10-239">Se necessario, modificare il nome della spiegazione e aggiungere o rimuovere voci nell'elenco criteri.</span><span class="sxs-lookup"><span data-stu-id="62e10-239">If needed, edit the explanation name and add or remove items from the pattern list.</span></span> </br> 

   ![Modifica modello](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="62e10-241">Al termine, selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="62e10-241">When finished, select **Save**.</span></span>
