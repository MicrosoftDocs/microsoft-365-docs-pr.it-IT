---
title: Tipi di spiegazione
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Per ulteriori informazioni, vedere tipi di spiegazione in Microsoft SharePoint Syntex
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295994"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="faaa0-103">Introduzione ai tipi di spiegazione</span><span class="sxs-lookup"><span data-stu-id="faaa0-103">Introduction to explanation types</span></span>

<span data-ttu-id="faaa0-104">Utilizzare spiegazioni che consentono di definire le informazioni che si desidera etichettare ed estrarre nel documento i modelli di comprensione per Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="faaa0-104">Use explanations to help to define the information that you want to label, and extract in your document the understanding models for Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="faaa0-105">Quando si crea una spiegazione, assicurarsi di selezionare un tipo di spiegazione.</span><span class="sxs-lookup"><span data-stu-id="faaa0-105">When you create an explanation, be sure to select an explanation type.</span></span> 

<span data-ttu-id="faaa0-106">In questo articolo vengono fornite informazioni dettagliate sui diversi tipi di spiegazione e su come vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="faaa0-106">This article helps you understand the different explanation types and how they are used.</span></span>

   ![Tipi di spiegazione](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="faaa0-108">Sono disponibili i seguenti tipi di spiegazione:</span><span class="sxs-lookup"><span data-stu-id="faaa0-108">These explanation types are available:</span></span>

- <span data-ttu-id="faaa0-109">**Elenco**delle frasi: elenco di parole, frasi, numeri o altri caratteri che è possibile utilizzare nel documento o nelle informazioni che si stanno estraendo.</span><span class="sxs-lookup"><span data-stu-id="faaa0-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="faaa0-110">Ad esempio, la stringa di testo refering **Doctor** è presente in tutti i documenti di rinvio medici che si stanno identificando.</span><span class="sxs-lookup"><span data-stu-id="faaa0-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="faaa0-111">**Elenco pattern**: elenca i modelli di numeri, lettere o altri caratteri che è possibile utilizzare per identificare le informazioni che si stanno estraendo.</span><span class="sxs-lookup"><span data-stu-id="faaa0-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="faaa0-112">Ad esempio, è possibile estrarre il **numero di telefono** del refering Doctor da tutto il documento di riferimento medico che si sta identificando.</span><span class="sxs-lookup"><span data-stu-id="faaa0-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="faaa0-113">**Prossimità**: in questo articolo viene descritto il modo in cui le spiegazioni sono ravvicinate.</span><span class="sxs-lookup"><span data-stu-id="faaa0-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="faaa0-114">Ad esempio, un elenco dei *numeri di strada* viene visualizzato subito prima dell'elenco delle frasi del *nome della via* , senza alcun segno di interferenza (verranno illustrati i token più avanti in questo articolo).</span><span class="sxs-lookup"><span data-stu-id="faaa0-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="faaa0-115">Elenco delle frasi</span><span class="sxs-lookup"><span data-stu-id="faaa0-115">Phrase list</span></span>

<span data-ttu-id="faaa0-116">Un tipo di spiegazione per l'elenco delle frasi viene in genere utilizzato per identificare e classificare un documento tramite il modello.</span><span class="sxs-lookup"><span data-stu-id="faaa0-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="faaa0-117">Come descritto nell'esempio *relativo* all'etichetta del medico di riferimento, si tratta di una stringa di parole, frasi, numeri o caratteri che è coerente nei documenti che si stanno identificando.</span><span class="sxs-lookup"><span data-stu-id="faaa0-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="faaa0-118">Anche se non è un requisito, è possibile ottenere risultati migliori con la spiegazione se la frase che si sta acquisendo si trova in una posizione coerente nel documento.</span><span class="sxs-lookup"><span data-stu-id="faaa0-118">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="faaa0-119">Ad esempio, l'etichetta del *medico che fa riferimento* può essere posizionata in modo coerente nel primo paragrafo del documento.</span><span class="sxs-lookup"><span data-stu-id="faaa0-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="faaa0-120">Se la distinzione tra maiuscole e minuscole è un requisito per identificare l'etichetta, utilizzando il tipo di elenco delle frasi è possibile specificarlo nella spiegazione selezionando l'unica casella di controllo per la **capitalizzazione esatta** .</span><span class="sxs-lookup"><span data-stu-id="faaa0-120">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![Distinzione tra maiuscole e minuscole](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="faaa0-122">Elenchi di modelli</span><span class="sxs-lookup"><span data-stu-id="faaa0-122">Pattern lists</span></span>

<span data-ttu-id="faaa0-123">Un tipo di elenco dei modelli è particolarmente utile quando si crea una spiegazione che identifica ed estrae informazioni da un documento.</span><span class="sxs-lookup"><span data-stu-id="faaa0-123">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="faaa0-124">È in genere presentato in formati diversi, ad esempio date, numeri di telefono o numeri di carta di credito.</span><span class="sxs-lookup"><span data-stu-id="faaa0-124">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="faaa0-125">Ad esempio, è possibile visualizzare una data in vari formati (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, gen 1, 2020 e così via).</span><span class="sxs-lookup"><span data-stu-id="faaa0-125">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="faaa0-126">La definizione di un elenco di modelli rende più efficiente la spiegazione, acquisendo le possibili varianti nei dati che si sta tentando di identificare ed estrarre.</span><span class="sxs-lookup"><span data-stu-id="faaa0-126">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="faaa0-127">Per l'esempio di **numero di telefono** , estrarre il numero di telefono di ogni medico che fa riferimento a tutti i documenti di rinvio medici identificati dal modello.</span><span class="sxs-lookup"><span data-stu-id="faaa0-127">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="faaa0-128">Quando si crea la spiegazione, selezionare il tipo di elenco dei modelli per consentire i diversi formati che è possibile prevedere di restituire.</span><span class="sxs-lookup"><span data-stu-id="faaa0-128">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![Elenco dei numeri di telefono](../media/content-understanding/pattern-list.png)

<span data-ttu-id="faaa0-130">Per questo esempio, selezionare la casella **di controllo qualsiasi cifra da 0-9** .</span><span class="sxs-lookup"><span data-stu-id="faaa0-130">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="faaa0-131">Selezionando questa impostazione si riconosce che ogni valore di "0" utilizzato nell'elenco dei modelli è qualsiasi cifra compreso tra 0 e 9.</span><span class="sxs-lookup"><span data-stu-id="faaa0-131">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![Qualsiasi cifra da 0-9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="faaa0-133">Analogamente, se si crea un elenco di modelli che include caratteri di testo, selezionare la casella **di controllo qualsiasi lettera da a-z** .</span><span class="sxs-lookup"><span data-stu-id="faaa0-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="faaa0-134">Selezionando questa impostazione, tutti i caratteri "a" utilizzati nell'elenco dei modelli devono essere qualsiasi carattere da "a" a "z".</span><span class="sxs-lookup"><span data-stu-id="faaa0-134">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="faaa0-135">Ad esempio, se si crea un elenco di modelli di **Data** e si desidera verificare che venga riconosciuto un formato di data come *gen 1, 2020* , è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="faaa0-135">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="faaa0-136">Aggiungere *AAA 0, 0000* e *AAA 00, 0000* all'elenco dei modelli.</span><span class="sxs-lookup"><span data-stu-id="faaa0-136">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="faaa0-137">Verificare che sia selezionata anche **una lettera di a-z** .</span><span class="sxs-lookup"><span data-stu-id="faaa0-137">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![Qualsiasi lettera da a-z](../media/content-understanding/any-letter.png)

<span data-ttu-id="faaa0-139">Inoltre, se nell'elenco dei modelli sono presenti requisiti di capitalizzazione, è possibile selezionare l'unica casella di controllo per la **capitalizzazione esatta** .</span><span class="sxs-lookup"><span data-stu-id="faaa0-139">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="faaa0-140">Per l'esempio di data, se è necessaria la prima lettera del mese per la capitalizzazione, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="faaa0-140">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="faaa0-141">Aggiungere *AAA 0, 0000* e *AAA 00, 0000* all'elenco dei modelli.</span><span class="sxs-lookup"><span data-stu-id="faaa0-141">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="faaa0-142">Verificare che sia selezionata anche **solo la capitalizzazione esatta** .</span><span class="sxs-lookup"><span data-stu-id="faaa0-142">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![Solo lettere maiuscole esatte](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="faaa0-144">Invece di creare manualmente una spiegazione per l'elenco dei modelli, utilizzare la [raccolta delle spiegazioni]() per utilizzare il modello di elenco schemi precostituito per l'elenco dei pattern comuni, ad esempio *Data*, *numero di telefono*, numero di *carta di credito*e così via.</span><span class="sxs-lookup"><span data-stu-id="faaa0-144">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="faaa0-145">Prossimità</span><span class="sxs-lookup"><span data-stu-id="faaa0-145">Proximity</span></span> 

<span data-ttu-id="faaa0-146">Il tipo di spiegazione di prossimità aiuta il modello a identificare i dati, definendo la modalità di chiusura di un altro elemento di dati.</span><span class="sxs-lookup"><span data-stu-id="faaa0-146">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="faaa0-147">Ad esempio, nel modello sono state definite due spiegazioni che etichettano sia il numero di *Indirizzo* del cliente che il *numero di telefono*.</span><span class="sxs-lookup"><span data-stu-id="faaa0-147">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="faaa0-148">Si noti inoltre che i numeri di telefono dei clienti vengono sempre visualizzati prima del numero dell'indirizzo di strada.</span><span class="sxs-lookup"><span data-stu-id="faaa0-148">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="faaa0-149">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="faaa0-149">Alex Wilburn</span></span><br>
<span data-ttu-id="faaa0-150">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="faaa0-150">555-555-5555</span></span><br>
<span data-ttu-id="faaa0-151">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="faaa0-151">One Microsoft Way</span></span><br>
<span data-ttu-id="faaa0-152">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="faaa0-152">Redmond, WA 98034</span></span><br>

<span data-ttu-id="faaa0-153">Utilizzare la spiegazione di prossimità per definire la distanza tra la spiegazione del numero di telefono per identificare meglio il numero di indirizzo di strada nei documenti.</span><span class="sxs-lookup"><span data-stu-id="faaa0-153">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![Spiegazione di prossimità](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="faaa0-155">Che cosa sono i token?</span><span class="sxs-lookup"><span data-stu-id="faaa0-155">What are tokens?</span></span>

<span data-ttu-id="faaa0-156">Per utilizzare il tipo di spiegazione di prossimità, è necessario comprendere il valore di un token, in quanto il numero di token è il modo in cui la spiegazione di prossimità misura la distanza tra una spiegazione e un'altra.</span><span class="sxs-lookup"><span data-stu-id="faaa0-156">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="faaa0-157">Un token è un intervallo continuo (senza spazi o segni di punteggiatura) di lettere e numeri.</span><span class="sxs-lookup"><span data-stu-id="faaa0-157">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="faaa0-158">Uno spazio non è un token.</span><span class="sxs-lookup"><span data-stu-id="faaa0-158">A space is NOT a token.</span></span> <span data-ttu-id="faaa0-159">Ogni carattere di punteggiatura è un token.</span><span class="sxs-lookup"><span data-stu-id="faaa0-159">Each punctuation character is a token.</span></span> <span data-ttu-id="faaa0-160">Nella tabella seguente sono riportati alcuni esempi di come determinare il numero di token in una frase.</span><span class="sxs-lookup"><span data-stu-id="faaa0-160">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="faaa0-161">Frase</span><span class="sxs-lookup"><span data-stu-id="faaa0-161">Phrase</span></span>|<span data-ttu-id="faaa0-162">Numero di token</span><span class="sxs-lookup"><span data-stu-id="faaa0-162">Number of tokens</span></span>|<span data-ttu-id="faaa0-163">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="faaa0-163">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="faaa0-164">1 </span><span class="sxs-lookup"><span data-stu-id="faaa0-164">1</span></span>|<span data-ttu-id="faaa0-165">Una singola parola senza punteggiatura o spazi.</span><span class="sxs-lookup"><span data-stu-id="faaa0-165">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="faaa0-166">1 </span><span class="sxs-lookup"><span data-stu-id="faaa0-166">1</span></span>|<span data-ttu-id="faaa0-167">Numero di localizzatore record.</span><span class="sxs-lookup"><span data-stu-id="faaa0-167">A record locator number.</span></span> <span data-ttu-id="faaa0-168">Potrebbe avere numeri e lettere, ma non ha alcun segno di punteggiatura.</span><span class="sxs-lookup"><span data-stu-id="faaa0-168">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="faaa0-169">5 </span><span class="sxs-lookup"><span data-stu-id="faaa0-169">5</span></span>|<span data-ttu-id="faaa0-170">Un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="faaa0-170">A phone number.</span></span> <span data-ttu-id="faaa0-171">Ogni segno di punteggiatura è un singolo token, quindi costituito  `425-555-5555` da 5 token:</span><span class="sxs-lookup"><span data-stu-id="faaa0-171">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="faaa0-172">7 </span><span class="sxs-lookup"><span data-stu-id="faaa0-172">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="faaa0-173">Configurare il tipo di spiegazione di prossimità</span><span class="sxs-lookup"><span data-stu-id="faaa0-173">Configure the proximity explanation type</span></span>

<span data-ttu-id="faaa0-174">Per l'esempio, configurare l'impostazione di prossimità in modo che sia possibile definire l'intervallo del numero di token che la spiegazione del *numero di telefono* è dalla spiegazione del numero di *indirizzo di strada* .</span><span class="sxs-lookup"><span data-stu-id="faaa0-174">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="faaa0-175">Si dovrebbe vedere che l'intervallo minimo è "0" dato che non ci sono token tra il numero di telefono e l'indirizzo di via.</span><span class="sxs-lookup"><span data-stu-id="faaa0-175">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="faaa0-176">Tuttavia, alcuni numeri di telefono nei documenti di esempio vengono accodati con *(mobile)*.</span><span class="sxs-lookup"><span data-stu-id="faaa0-176">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="faaa0-177">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="faaa0-177">Nestor Wilke</span></span><br>
<span data-ttu-id="faaa0-178">111-111-1111 (cellulare)</span><span class="sxs-lookup"><span data-stu-id="faaa0-178">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="faaa0-179">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="faaa0-179">One Microsoft Way</span></span><br>
<span data-ttu-id="faaa0-180">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="faaa0-180">Redmond, WA 98034</span></span><br>

<span data-ttu-id="faaa0-181">Sono presenti tre token in *(mobile)*:</span><span class="sxs-lookup"><span data-stu-id="faaa0-181">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="faaa0-182">Frase</span><span class="sxs-lookup"><span data-stu-id="faaa0-182">Phrase</span></span>|<span data-ttu-id="faaa0-183">Conteggio token</span><span class="sxs-lookup"><span data-stu-id="faaa0-183">Token count</span></span>|
|--|--|
|<span data-ttu-id="faaa0-184">(</span><span class="sxs-lookup"><span data-stu-id="faaa0-184">(</span></span>|<span data-ttu-id="faaa0-185">1 </span><span class="sxs-lookup"><span data-stu-id="faaa0-185">1</span></span>|
|<span data-ttu-id="faaa0-186">Mobile</span><span class="sxs-lookup"><span data-stu-id="faaa0-186">mobile</span></span>|<span data-ttu-id="faaa0-187">2 </span><span class="sxs-lookup"><span data-stu-id="faaa0-187">2</span></span>|
|<span data-ttu-id="faaa0-188">)</span><span class="sxs-lookup"><span data-stu-id="faaa0-188">)</span></span>|<span data-ttu-id="faaa0-189">3 </span><span class="sxs-lookup"><span data-stu-id="faaa0-189">3</span></span>|

<span data-ttu-id="faaa0-190">Configurare l'impostazione di prossimità in modo che abbia un intervallo compreso tra 0 e 3.</span><span class="sxs-lookup"><span data-stu-id="faaa0-190">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![Esempio di prossimità](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a><span data-ttu-id="faaa0-192">Utilizzare la raccolta di spiegazioni</span><span class="sxs-lookup"><span data-stu-id="faaa0-192">Use the explanation library</span></span>

<span data-ttu-id="faaa0-193">Anche se è possibile aggiungere manualmente vari valori dell'elenco dei modelli per la spiegazione, è molto più facile usare i modelli creati in precedenza nella raccolta di spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="faaa0-193">While you can manually add various pattern list values for your explanation, it's much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="faaa0-194">Ad esempio, invece di aggiungere manualmente tutte le varianti per *date*, utilizzare il modello di elenco dei modelli per la *Data*, che include già numerosi valori degli elenchi di modelli:</span><span class="sxs-lookup"><span data-stu-id="faaa0-194">For example, instead of manually adding all the variations for *Date*, use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![Raccolta di spiegazioni](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="faaa0-196">La raccolta di spiegazioni include una serie di spiegazioni di elenco dei modelli di uso comune, tra cui:</span><span class="sxs-lookup"><span data-stu-id="faaa0-196">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="faaa0-197">Data</span><span class="sxs-lookup"><span data-stu-id="faaa0-197">Date</span></span></br>
- <span data-ttu-id="faaa0-198">Data (numerico)</span><span class="sxs-lookup"><span data-stu-id="faaa0-198">Date (numeric)</span></span></br>
- <span data-ttu-id="faaa0-199">Ora</span><span class="sxs-lookup"><span data-stu-id="faaa0-199">Time</span></span></br>
- <span data-ttu-id="faaa0-200">Numero </span><span class="sxs-lookup"><span data-stu-id="faaa0-200">Number</span></span></br>
- <span data-ttu-id="faaa0-201">Numero di telefono</span><span class="sxs-lookup"><span data-stu-id="faaa0-201">Phone number</span></span></br>
- <span data-ttu-id="faaa0-202">CAP</span><span class="sxs-lookup"><span data-stu-id="faaa0-202">Zip code</span></span></br>
- <span data-ttu-id="faaa0-203">Prima parola di frase</span><span class="sxs-lookup"><span data-stu-id="faaa0-203">First word of sentence</span></span></br>
- <span data-ttu-id="faaa0-204">Carta di credito</span><span class="sxs-lookup"><span data-stu-id="faaa0-204">Credit card</span></span></br>
- <span data-ttu-id="faaa0-205">Codice di previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="faaa0-205">Social security number</span></span></br>

<span data-ttu-id="faaa0-206">Si noti che la raccolta di spiegazioni include anche i modelli per le spiegazioni degli elenchi di frasi e, tra cui:</span><span class="sxs-lookup"><span data-stu-id="faaa0-206">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="faaa0-207">Fine della frase</span><span class="sxs-lookup"><span data-stu-id="faaa0-207">End of sentence</span></span>
- <span data-ttu-id="faaa0-208">Valuta</span><span class="sxs-lookup"><span data-stu-id="faaa0-208">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="faaa0-209">Per utilizzare un modello dalla raccolta di spiegazioni</span><span class="sxs-lookup"><span data-stu-id="faaa0-209">To use a template from the explanation library</span></span>

1. <span data-ttu-id="faaa0-210">Nella sezione **spiegazioni** della pagina del **treno** del modello selezionare **nuovo**e quindi selezionare **da un modello**.</span><span class="sxs-lookup"><span data-stu-id="faaa0-210">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![Crea da modello](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="faaa0-212">Nella pagina **modelli spiegazione** selezionare la spiegazione che si desidera utilizzare e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="faaa0-212">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![Selezionare un modello](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="faaa0-214">Le informazioni per il modello selezionato verranno visualizzate nella pagina **Crea una spiegazione** .</span><span class="sxs-lookup"><span data-stu-id="faaa0-214">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="faaa0-215">Se necessario, modificare il nome della spiegazione e aggiungere o rimuovere elementi dall'elenco dei modelli.</span><span class="sxs-lookup"><span data-stu-id="faaa0-215">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![Modifica modello](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="faaa0-217">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="faaa0-217">When finished, select **Save**.</span></span>
