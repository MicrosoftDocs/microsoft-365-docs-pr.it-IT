---
title: Informazioni sui tipi di spiegazione in Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Altre informazioni sui tipi di spiegazione in Microsoft SharePoint Syntex.
ms.openlocfilehash: 515fd8af289ec7c64e14eb6d54b236ba3a8aa9f6
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706563"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="9fe6b-103">Informazioni sui tipi di spiegazione in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="9fe6b-103">Explanation types in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="9fe6b-104">Le spiegazioni vengono usate per definire meglio le informazioni da etichettare ed estrarre nei modelli di analisi dei documenti in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="9fe6b-105">Quando si crea una spiegazione, è necessario selezionare un tipo di spiegazione.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-105">When you create an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="9fe6b-106">Questo articolo contiene informazioni utili per comprendere i diversi tipi di spiegazione e come vengono usati.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-106">This article helps you understand the different explanation types and how they're used.</span></span>

![Screenshot del pannello Crea una spiegazione che mostra i tre tipi di spiegazione.](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="9fe6b-108">Sono disponibili questi tipi di spiegazione:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-108">These explanation types are available:</span></span>

- <span data-ttu-id="9fe6b-109">[**Elenco frasi**](#phrase-list): elenco di parole, frasi, numeri o altri caratteri che è possibile usare nel documento o nelle informazioni che si stanno estraendo.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-109">[**Phrase list**](#phrase-list): List of words, phrases, numbers, or other characters you can use in the document or information that you're extracting.</span></span> <span data-ttu-id="9fe6b-110">Ad esempio, la stringa di testo *medico richiedente* è inclusa in tutti i documenti di richiesta di visita specialistica che si stanno identificando.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-110">For example, the text string *referring doctor* is in all Medical Referral documents you're identifying.</span></span> <span data-ttu-id="9fe6b-111">Oppure il *numero di telefono* del medico richiedente da tutti i documenti di richiesta di visita specialistica che si stanno identificando.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-111">Or the *phone number* of the referring doctor from all Medical Referral documents that you're identifying.</span></span>

- <span data-ttu-id="9fe6b-112">[**Espressione regolare**](#regular-expression): usa una notazione di corrispondenza dei criteri per trovare modelli di carattere specifici.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-112">[**Regular expression**](#regular-expression): Uses a pattern-matching notation to find specific character patterns.</span></span> <span data-ttu-id="9fe6b-113">Ad esempio, è possibile usare un'espressione regolare per trovare tutte le istanze di un criterio *indirizzo di posta elettronica di* in un set di documenti.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-113">For example, you can use a regular expression to find all instances of an *email address* pattern in a set of documents.</span></span>

- <span data-ttu-id="9fe6b-114">[**Prossimità**](#proximity): descrive la relazione di prossimità tra le spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-114">[**Proximity**](#proximity): Describes how close explanations are to each other.</span></span> <span data-ttu-id="9fe6b-115">Ad esempio, un elenco frasi *numero civico* precede immediatamente l'elenco frasi *nome della via*, senza token intermedi (i token verranno illustrati più avanti in questo articolo).</span><span class="sxs-lookup"><span data-stu-id="9fe6b-115">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="9fe6b-116">Se si usa il tipo di prossimità, il modello deve includere almeno due spiegazioni, altrimenti l'opzione verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-116">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 

## <a name="phrase-list"></a><span data-ttu-id="9fe6b-117">Elenco frasi</span><span class="sxs-lookup"><span data-stu-id="9fe6b-117">Phrase list</span></span>

<span data-ttu-id="9fe6b-118">Il tipo di spiegazione elenco frasi viene usato generalmente per identificare e classificare un documento tramite il modello.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-118">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="9fe6b-119">Come descritto nell'esempio di etichetta *medico richiedente*, si tratta di una stringa di parole, frasi, numeri o caratteri presente costantemente nei documenti che si stanno identificando.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-119">As described in the *referring doctor* label example, it's a string of words, phrases, numbers, or characters that is consistently in the documents that you're identifying.</span></span>

<span data-ttu-id="9fe6b-120">Anche se non è necessario, la spiegazione risulta più efficace se la frase acquisita si trova in una posizione ricorrente nel documento.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-120">While not a requirement, you can achieve better success with your explanation if the phrase you're capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="9fe6b-121">Ad esempio, l'etichetta *medico richiedente* potrebbe essere situata sempre nel primo paragrafo del documento.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-121">For example, the *referring doctor* label might be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="9fe6b-122">È possibile inoltre usare l'impostazione avanzata **[Configurare la posizione delle frasi nel documento](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** per selezionare aree specifiche in cui è posizionata la frase, soprattutto se la frase può essere presente in più posizioni nel documento.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-122">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there's a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="9fe6b-123">Se la distinzione tra maiuscole e minuscole è un requisito per identificare l'etichetta, il tipo elenco frasi consente di specificarlo nella spiegazione selezionando la casella di controllo **Solo le maiuscole esatte**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-123">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![Distinzione tra maiuscole e minuscole](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="9fe6b-125">Un tipo di frase è utile soprattutto quando si crea una spiegazione che identifichi ed estragga informazioni in formati diversi, come date, numeri di telefono e numeri di carte di credito.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-125">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="9fe6b-126">Ad esempio, una data può essere visualizzata in molti formati (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020 o 1 gen 2020).</span><span class="sxs-lookup"><span data-stu-id="9fe6b-126">For example, a date can be displayed in many different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, or Jan 1,2020).</span></span> <span data-ttu-id="9fe6b-127">La definizione di un elenco frasi rende più efficace la spiegazione attraverso l'acquisizione di tutte le possibili varianti nei dati che si sta provando a identificare ed estrarre.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-127">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you're trying to identify and extract.</span></span> 

<span data-ttu-id="9fe6b-128">Per l'esempio relativo al *numero di telefono*, estrarre il numero di telefono per ogni medico richiedente da tutti i documenti di richiesta di visita specialistica identificati dal modello.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-128">For the *phone number* example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="9fe6b-129">Quando si crea la spiegazione, digitare i vari formati in cui può essere visualizzato un numero di telefono nel documento, così da poter acquisire tutte le possibili variabili.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-129">When you create the explanation, type the different formats a phone number might display in your document so that you're able to capture possible variations.</span></span> 

![Modelli di frasi per il numero di telefono](../media/content-understanding/pattern-list.png)

<span data-ttu-id="9fe6b-131">Nel caso di questo esempio, in **Impostazioni avanzate** selezionare la casella di controllo **Qualsiasi cifra da 0 a 9** per riconoscere ogni valore "0" usato nell'elenco frasi come qualsiasi cifra da 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-131">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![Qualsiasi cifra da 0 a 9](../media/content-understanding/digit-identity.png)

<span data-ttu-id="9fe6b-133">Analogamente, se si crea un elenco frasi che include caratteri di testo, selezionare la casella di controllo **Qualsiasi lettera dalla a alla z** per riconoscere ogni carattere "a" usato nell'elenco di frasi per essere qualsiasi carattere compreso dalla "a" alla "z".</span><span class="sxs-lookup"><span data-stu-id="9fe6b-133">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="9fe6b-134">Ad esempio, se si crea un elenco frasi **Data** e si vuole fare in modo che venga riconosciuto un formato di data come *1 gen 2020*, è necessario:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-134">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>

- <span data-ttu-id="9fe6b-135">Aggiungere *0 aaa 0000* e *00 aaa 0000* all'elenco frasi.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="9fe6b-136">Assicurarsi che sia selezionata anche l'opzione **Qualsiasi lettera dalla a alla z**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-136">Make sure that **Any letter from a-z** is also selected.</span></span>

![Qualsiasi lettera dalla a alla z](../media/content-understanding/any-letter.png)

<span data-ttu-id="9fe6b-138">Se l'elenco frasi prevede requisiti per le maiuscole, è possibile selezionare la casella di controllo **Solo le maiuscole esatte**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-138">If you have capitalization requirements in your phrase list, you can select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="9fe6b-139">Per l'esempio relativo alla data, se il mese deve avere l'iniziale minuscola, è necessario:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-139">For the date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="9fe6b-140">Aggiungere *0 aaa 0000* e *00 aaa 0000* all'elenco frasi.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="9fe6b-141">Assicurarsi che sia selezionata anche l'opzione **Solo le maiuscole esatte**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-141">Make sure that **Only exact capitalization** is also selected.</span></span>

![Solo le maiuscole esatte](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="9fe6b-143">Anziché creare manualmente una spiegazione elenco frasi, usare la [raccolta spiegazioni](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) per usare modelli di elenchi frasi per elenchi frasi comuni, quali *data*, *numero di telefono* o *numero di carta di credito*.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-143">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, or *credit card number*.</span></span>

## <a name="regular-expression"></a><span data-ttu-id="9fe6b-144">Espressione regolare</span><span class="sxs-lookup"><span data-stu-id="9fe6b-144">Regular expression</span></span>

<span data-ttu-id="9fe6b-145">Un tipo di spiegazione di espressione regolare consente di creare criteri che consentono di trovare e identificare determinate stringhe di testo nei documenti.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-145">A regular expression explanation type allows you to create patterns that help find and identify certain text strings in documents.</span></span> <span data-ttu-id="9fe6b-146">È possibile usare le espressioni regolari per analizzare rapidamente grandi quantità di testo per:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-146">You can use regular expressions to quickly parse large amounts of text to:</span></span>

- <span data-ttu-id="9fe6b-147">Trovare criteri di caratteri specifici.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-147">Find specific character patterns.</span></span>
- <span data-ttu-id="9fe6b-148">Convalidare il testo per assicurarsi che corrisponda a un criterio predefinito, ad esempio un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-148">Validate text to ensure that it matches a predefined pattern (such as an email address).</span></span>
- <span data-ttu-id="9fe6b-149">Estrazione, modifica, sostituzione o eliminazione di sottostringhe di testo.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-149">Extract, edit, replace, or delete text substrings.</span></span>

<span data-ttu-id="9fe6b-150">Un’espressione regolare è utile soprattutto quando si crea una spiegazione che identifichi ed estragga informazioni in formati simili, ad esempio indirizzi di posta elettronica, numeri di conto corrente bancario o URL.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-150">A regular expression type is especially useful when you create an explanation that identifies and extracts information in similar formats, such as email addresses, bank account numbers, or URLs.</span></span> <span data-ttu-id="9fe6b-151">Ad esempio, un indirizzo di posta elettronica, come megan@contoso.com, viene visualizzato con un determinato modello ("megan" è la prima parte e "com" è l'ultima parte).</span><span class="sxs-lookup"><span data-stu-id="9fe6b-151">For example, an email address, such as megan@contoso.com, is displayed in a certain pattern ("megan" is the first part, and "com" is the last part).</span></span> 

<span data-ttu-id="9fe6b-152">L'espressione regolare per un indirizzo di posta elettronica è: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+. [A-Za-z]{2,6}**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-152">The regular expression for an email address is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span></span>

<span data-ttu-id="9fe6b-153">Questa espressione è costituita da cinque parti, in questo ordine:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-153">This expression consists of five parts, in this order:</span></span>

1. <span data-ttu-id="9fe6b-154">Qualsiasi dei caratteri speciali seguenti:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-154">Any amount of the following characters:</span></span>

   <span data-ttu-id="9fe6b-155">a.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-155">a.</span></span> <span data-ttu-id="9fe6b-156">Lettere dalla a alla z</span><span class="sxs-lookup"><span data-stu-id="9fe6b-156">Letters from a to z</span></span>

   <span data-ttu-id="9fe6b-157">b.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-157">b.</span></span> <span data-ttu-id="9fe6b-158">Numeri da 0 a 9</span><span class="sxs-lookup"><span data-stu-id="9fe6b-158">Numbers from 0-9</span></span>

   <span data-ttu-id="9fe6b-159">c.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-159">c.</span></span> <span data-ttu-id="9fe6b-160">Punto, trattino basso, percentuale o trattino</span><span class="sxs-lookup"><span data-stu-id="9fe6b-160">Period, underscore, percent, or dash</span></span>

2. <span data-ttu-id="9fe6b-161">Il simbolo @</span><span class="sxs-lookup"><span data-stu-id="9fe6b-161">The @ symbol</span></span>

3. <span data-ttu-id="9fe6b-162">Qualsiasi quantità di caratteri della prima parte dell'indirizzo di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="9fe6b-162">Any amount of the same characters as the first part of the email address</span></span>

4. <span data-ttu-id="9fe6b-163">Un punto</span><span class="sxs-lookup"><span data-stu-id="9fe6b-163">A period</span></span>

5. <span data-ttu-id="9fe6b-164">Da due a sei lettere</span><span class="sxs-lookup"><span data-stu-id="9fe6b-164">Two to six letters</span></span>

<span data-ttu-id="9fe6b-165">Per aggiungere un tipo di spiegazione di espressione regolare:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-165">To add a regular expression explanation type:</span></span>

1. <span data-ttu-id="9fe6b-166">Dal pannello **Crea una spiegazione**, in **Tipo di spiegazione**, selezionare **Espressione regolare**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-166">From the **Create an explanation** panel, under **Explanation type**, select **Regular expression**.</span></span>

   ![Screenshot che mostra il pannello Crea una spiegazione con l'opzione Espressione regolare selezionata.](../media/content-understanding/create-regular-expression.png)

2. <span data-ttu-id="9fe6b-168">È possibile digitare un'espressione nella casella di testo **Espressione regolare** o selezionare **Aggiungi un'espressione regolare da un modello**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-168">You can either type an expression in the **Regular expression** text box or select **Add a regular expression from a template**.</span></span>

   <span data-ttu-id="9fe6b-169">Quando si aggiunge un'espressione regolare usando un modello, il nome e l'espressione regolare vengono aggiunti automaticamente alla casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-169">When you add a regular expression by using a template, it automatically adds the name and the regular expression to the text box.</span></span> <span data-ttu-id="9fe6b-170">Ad esempio, se si sceglie il modello **Indirizzo di posta elettronica**, il pannello **Crea una spiegazione** verrà popolato.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-170">For example, if you choose the **Email address** template, the **Create an explanation** panel will be populated.</span></span>

   ![Screenshot che mostra il pannello Crea una spiegazione con il modello Indirizzo di posta elettronica applicato.](../media/content-understanding/create-regular-expression-email.png)

## <a name="proximity"></a><span data-ttu-id="9fe6b-172">Prossimità</span><span class="sxs-lookup"><span data-stu-id="9fe6b-172">Proximity</span></span> 

<span data-ttu-id="9fe6b-173">Il tipo di spiegazione prossimità consente al modello di identificare i dati definendo il rapporto di prossimità rispetto ad altri dati.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-173">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="9fe6b-174">Nel modello, ad esempio, sono state definite due spiegazioni che etichettano il *Numero civico* e il *Numero di telefono* del cliente.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-174">For example, in your model say you have defined two explanations that label both the customer *street address number* and *phone number*.</span></span> 

<span data-ttu-id="9fe6b-175">Si nota anche che i numeri di telefono del cliente vengono sempre visualizzati sempre prima del numero civico.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-175">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="9fe6b-176">Davide Milano</span><span class="sxs-lookup"><span data-stu-id="9fe6b-176">Alex Wilburn</span></span><br>
<span data-ttu-id="9fe6b-177">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="9fe6b-177">555-555-5555</span></span><br>
<span data-ttu-id="9fe6b-178">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="9fe6b-178">One Microsoft Way</span></span><br>
<span data-ttu-id="9fe6b-179">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="9fe6b-179">Redmond, WA 98034</span></span><br>

<span data-ttu-id="9fe6b-180">Usare la spiegazione di prossimità per definire quanto è lontana la spiegazione del numero di telefono, per identificare meglio il numero civico nei documenti.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-180">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![Spiegazione di prossimità](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="9fe6b-182">Che cosa sono i token?</span><span class="sxs-lookup"><span data-stu-id="9fe6b-182">What are tokens?</span></span>

<span data-ttu-id="9fe6b-183">Per usare il tipo di spiegazione di prossimità, è necessario comprendere che cos'è un token.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-183">To use the proximity explanation type, you need to understand what a token is.</span></span> <span data-ttu-id="9fe6b-184">Il numero di token è il sistema usato dalla spiegazione di prossimità per misurare la distanza tra una spiegazione e l'altra.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-184">The number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="9fe6b-185">Un token è una serie continua di lettere e numeri, senza spazi o punteggiatura.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-185">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="9fe6b-186">Nella tabella seguente sono illustrati alcuni esempi per determinare il numero di token in una frase.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-186">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="9fe6b-187">Frase</span><span class="sxs-lookup"><span data-stu-id="9fe6b-187">Phrase</span></span>|<span data-ttu-id="9fe6b-188">Numero di token</span><span class="sxs-lookup"><span data-stu-id="9fe6b-188">Number of tokens</span></span>|<span data-ttu-id="9fe6b-189">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="9fe6b-189">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="9fe6b-190">1</span><span class="sxs-lookup"><span data-stu-id="9fe6b-190">1</span></span>|<span data-ttu-id="9fe6b-191">Una singola parola senza punteggiatura o spazi.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-191">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="9fe6b-192">1</span><span class="sxs-lookup"><span data-stu-id="9fe6b-192">1</span></span>|<span data-ttu-id="9fe6b-193">Un numero di localizzazione record.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-193">A record locator number.</span></span> <span data-ttu-id="9fe6b-194">Può includere numeri e lettere, ma non include segni di punteggiatura.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-194">It might include numbers and letters, but doesn't have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="9fe6b-195">5</span><span class="sxs-lookup"><span data-stu-id="9fe6b-195">5</span></span>|<span data-ttu-id="9fe6b-196">Un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-196">A phone number.</span></span> <span data-ttu-id="9fe6b-197">Ogni segno di punteggiatura è un token, quindi `425-555-5555` corrisponde a 5 token:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-197">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="9fe6b-198">7</span><span class="sxs-lookup"><span data-stu-id="9fe6b-198">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="9fe6b-199">Configurare il tipo di spiegazione di prossimità</span><span class="sxs-lookup"><span data-stu-id="9fe6b-199">Configure the proximity explanation type</span></span>

<span data-ttu-id="9fe6b-200">Per questo esempio, configurare l'impostazione di prossimità in modo da poter definire l'intervallo del numero di token di distanza nella spiegazione *numero di telefono* dalla spiegazione *numero civico*.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-200">For the example, configure the proximity setting to define the range of the number of tokens in the *phone number* explanation from the *street address number* explanation.</span></span> <span data-ttu-id="9fe6b-201">Si noti che l'intervallo minimo dovrebbe risultare "0" perché non c'è nessun token tra il numero di telefono e il numero civico.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-201">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="9fe6b-202">Dopo alcuni numeri di telefono nei documenti di esempio, invece, è presente la dicitura *(cellulare)*.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-202">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="9fe6b-203">Luca Udinesi</span><span class="sxs-lookup"><span data-stu-id="9fe6b-203">Nestor Wilke</span></span><br>
<span data-ttu-id="9fe6b-204">111-111-1111 (cellulare)</span><span class="sxs-lookup"><span data-stu-id="9fe6b-204">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="9fe6b-205">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="9fe6b-205">One Microsoft Way</span></span><br>
<span data-ttu-id="9fe6b-206">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="9fe6b-206">Redmond, WA 98034</span></span><br>

<span data-ttu-id="9fe6b-207">In *(cellulare)* sono presenti tre token:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-207">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="9fe6b-208">Frase</span><span class="sxs-lookup"><span data-stu-id="9fe6b-208">Phrase</span></span>|<span data-ttu-id="9fe6b-209">Numero di token</span><span class="sxs-lookup"><span data-stu-id="9fe6b-209">Token count</span></span>|
|--|--|
|<span data-ttu-id="9fe6b-210">(</span><span class="sxs-lookup"><span data-stu-id="9fe6b-210">(</span></span>|<span data-ttu-id="9fe6b-211">1</span><span class="sxs-lookup"><span data-stu-id="9fe6b-211">1</span></span>|
|<span data-ttu-id="9fe6b-212">cellulare</span><span class="sxs-lookup"><span data-stu-id="9fe6b-212">mobile</span></span>|<span data-ttu-id="9fe6b-213">2</span><span class="sxs-lookup"><span data-stu-id="9fe6b-213">2</span></span>|
|<span data-ttu-id="9fe6b-214">)</span><span class="sxs-lookup"><span data-stu-id="9fe6b-214">)</span></span>|<span data-ttu-id="9fe6b-215">3</span><span class="sxs-lookup"><span data-stu-id="9fe6b-215">3</span></span>|

<span data-ttu-id="9fe6b-216">Configurare l'impostazione di prossimità su un intervallo compreso tra 0 e 3.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-216">Configure the proximity setting to have a range of 0 through 3.</span></span>

![Esempio di prossimità](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="9fe6b-218">Configurare la posizione delle frasi nel documento</span><span class="sxs-lookup"><span data-stu-id="9fe6b-218">Configure where phrases occur in the document</span></span>

<span data-ttu-id="9fe6b-219">Quando si crea una spiegazione, per impostazione predefinita viene cercata nell'intero documento la frase che si vuole estrarre.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-219">When you create an explanation, by default the entire document is searched for the phrase you're trying to extract.</span></span> <span data-ttu-id="9fe6b-220">Tuttavia, è possibile usare l'impostazione avanzata **Dove si trovano queste frasi** per isolare una posizione specifica nel documento in cui si trova una frase.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-220">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="9fe6b-221">Questa impostazione è utile nei casi in cui istanze simili di una frase potrebbero comparire in un altro punto del documento e si vuole verificare che sia selezionata quella corretta.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-221">This setting is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span>

<span data-ttu-id="9fe6b-222">Facendo riferimento all'esempio relativo al documento di richiesta di visita specialistica il *medico richiedente* viene sempre menzionato nel primo paragrafo del documento.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-222">Referring to our Medical Referral document example, the *referring doctor* is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="9fe6b-223">Con l'impostazione **Dove si trovano queste frasi**, in questo esempio è possibile configurare la spiegazione per la ricerca di questa etichetta solo nella sezione iniziale del documento o in qualsiasi altra posizione in cui potrebbe essere presente.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-223">With the **Where these phrases occur** setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![Impostazione Dove si trovano queste frasi](../media/content-understanding/phrase-location.png)

<span data-ttu-id="9fe6b-225">Per questa impostazione è possibile scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-225">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="9fe6b-226">Ovunque nel file: la frase viene cercata nell'intero documento.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-226">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="9fe6b-227">Inizio del file: la ricerca viene eseguita dall'inizio del documento fino alla posizione della frase.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-227">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![Inizio del file](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="9fe6b-229">Nel visualizzatore è possibile modificare manualmente la casella di selezione in modo da includere la posizione in cui si trova la fase.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-229">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="9fe6b-230">Il valore **Posizione finale** verrà aggiornato per mostrare il numero di token inclusi nell'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-230">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="9fe6b-231">È possibile aggiornare il valore **Posizione finale** anche per modificare l'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-231">You can update the **End position** value as well to adjust the selected area.</span></span>

   ![Casella con la posizione Inizio del file](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="9fe6b-233">Fine del file: la ricerca viene eseguita dalla fine del documento fino alla posizione della frase.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-233">End of the file: The document is searched from the end to the phrase location.</span></span>

   ![Fine del file](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="9fe6b-235">Nel visualizzatore è possibile modificare manualmente la casella di selezione in modo da includere la posizione in cui si trova la fase.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-235">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="9fe6b-236">Il valore **Posizione iniziale** verrà aggiornato per mostrare il numero di token inclusi nell'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-236">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="9fe6b-237">È possibile aggiornare il valore Posizione iniziale anche per modificare l'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-237">You can update the Starting position value as well to adjust the selected area.</span></span>

   ![Casella con la posizione Fine del file](../media/content-understanding/end-box.png)

- <span data-ttu-id="9fe6b-239">Intervallo personalizzato: la posizione della frase viene cercata entro un intervallo specificato all'interno del documento.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-239">Custom range: The document is searched within a specified range for the phrase location.</span></span>

   ![Intervallo personalizzato](../media/content-understanding/custom-file.png)

    <span data-ttu-id="9fe6b-241">Nel visualizzatore è possibile modificare manualmente la casella di selezione in modo da includere la posizione in cui si trova la fase.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-241">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="9fe6b-242">Per questa impostazione è necessario selezionare una posizione di **Inizio** e di **Fine**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-242">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="9fe6b-243">Questi valori rappresentano il numero di token dall'inizio del documento.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-243">These values represent the number of tokens from the beginning of the document.</span></span> <span data-ttu-id="9fe6b-244">Anche se è possibile immettere manualmente questi valori, è più facile modificare manualmente la casella di selezione nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-244">While you can manually enter in these values, it's easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="9fe6b-245">Usare modelli di spiegazione</span><span class="sxs-lookup"><span data-stu-id="9fe6b-245">Use explanation templates</span></span>

<span data-ttu-id="9fe6b-246">Anche se è possibile aggiungere manualmente vari valori dell'elenco frasi per la spiegazione, può essere più semplice usare i modelli disponibili nella raccolta di spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-246">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="9fe6b-247">Ad esempio, invece di aggiungere manualmente tutte le varianti per *data*, è possibile usare il modello con l’elenco frasi per *data*, poiché include già molti valori:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-247">For example, instead of manually adding all the variations for *date*, you can use the phrase list template for *date* because it already includes many phrase lists values:</span></span>

![Raccolta di spiegazioni](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="9fe6b-249&quot;>La raccolta di spiegazioni include spiegazioni di *elenchi frasi* di uso comune, tra cui:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;9fe6b-249&quot;>The explanation library includes commonly used *phrase list* explanations, including:</span></span>

- <span data-ttu-id=&quot;9fe6b-250&quot;>Data: date del Calendario, tutti i formati.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;9fe6b-250&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;9fe6b-251&quot;>Include testo e numeri, ad esempio &quot;9 dic 2020&quot;.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;9fe6b-251&quot;>Includes text and numbers (for example, &quot;Dec 9, 2020").</span></span>
- <span data-ttu-id="9fe6b-252">Data (numerica): date del Calendario, tutti i formati.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-252">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="9fe6b-253">Include numeri, (ad esempio 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="9fe6b-253">Includes numbers (for example, 1-11-2020).</span></span>
- <span data-ttu-id="9fe6b-254">Ora: formati a 12 e 24 ore.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-254">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="9fe6b-255">Numero: numeri positivi e negativi fino a 2 cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-255">Number: Positive and negative numbers up to two decimals.</span></span> 
- <span data-ttu-id="9fe6b-256">Percentuale: un elenco di criteri che rappresentano una percentuale.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-256">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="9fe6b-257">Ad esempio, 1%, 11%, 100%, o 11.11%.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-257">For example, 1%, 11%, 100%, or 11.11%.</span></span>
- <span data-ttu-id="9fe6b-258">Numero di telefono: formati comuni degli Stati Uniti e internazionali.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-258">Phone number: Common US and International formats.</span></span> <span data-ttu-id="9fe6b-259">Ad esempio, 000 000 0000, 000-000-0000, (000)000-0000, o (000) 000-0000.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-259">For example, 000 000 0000, 000-000-0000, (000)000-0000, or (000) 000-0000.</span></span>
- <span data-ttu-id="9fe6b-260">Codice postale ZIP: formati di codice postale ZIP degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-260">Zip code: US Zip code formats.</span></span> <span data-ttu-id="9fe6b-261">Ad esempio: 11111, 11111-1111.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-261">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="9fe6b-262">Prima parola della frase: criteri comuni per parole con un massimo di nove caratteri.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-262">First word of sentence: Common patterns for words up to nine characters.</span></span> 
- <span data-ttu-id="9fe6b-263">Fine della frase: punteggiatura comune per terminare una frase.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-263">End of sentence: Common punctuation for end of a sentence.</span></span>
- <span data-ttu-id="9fe6b-264">Carta di credito: formati comuni per i numeri di carta di credito.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-264">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="9fe6b-265">Ad esempio: 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-265">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="9fe6b-p132">Numero di previdenza sociale: formato del numero di previdenza sociale degli Stati Uniti, ad esempio 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-p132">Social security number: US Social Security Number format. For example, 111-11-1111.</span></span> 
- <span data-ttu-id="9fe6b-268">Casella di controllo: un elenco frasi che rappresenta le varianti di una casella di controllo spuntata.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-268">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="9fe6b-269">Ad esempio: _X_, _ _X_.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-269">For example, _X_, _ _X_.</span></span>
- <span data-ttu-id="9fe6b-270">Valuta: principali simboli internazionali.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-270">Currency: Major international symbols.</span></span> <span data-ttu-id="9fe6b-271">Ad esempio: $.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-271">For example, $.</span></span> 
- <span data-ttu-id="9fe6b-272">Cc del messaggio di posta elettronica: un elenco frasi con il termine "Cc:", spesso collocato accanto ai nomi o agli indirizzi di posta elettronica di altre persone o gruppi a cui è stato inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-272">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of other people or groups the message was sent to.</span></span>
- <span data-ttu-id="9fe6b-273">Data del messaggio di posta elettronica: un elenco frasi con il termine "Inviato il:", spesso collocato accanto alla data di invio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-273">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="9fe6b-274">Saluto del messaggio di posta elettronica: formule di apertura comuni per i messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-274">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="9fe6b-275">Destinatario del messaggio di posta elettronica: un elenco frasi con il termine "A:", spesso collocato accanto ai nomi o agli indirizzi di posta elettronica delle persone o dei gruppi a cui è stato inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-275">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="9fe6b-276">Mittente del messaggio di posta elettronica: un elenco frasi con il termine "Da:", spesso collocato accanto al nome o all'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-276">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="9fe6b-277">Oggetto del messaggio di posta elettronica: un elenco frasi con il termine "Oggetto:", spesso collocato accanto all'oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-277">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span>

<span data-ttu-id="9fe6b-278">La raccolta di spiegazioni include anche spiegazioni di *espressioni regolari* di uso comune, tra cui:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-278">The explanation library also includes commonly used *regular expression* explanations, including:</span></span>

- <span data-ttu-id="9fe6b-279">Numeri da 6 a 17 cifre: corrisponde a un numero qualsiasi di lunghezza compresa tra 6 e 17 cifre.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-279">6 to 17 digit numbers: Matches any number from 6 to 17 digits long.</span></span> <span data-ttu-id="9fe6b-280">I numeri di conto corrente bancario statunitense sono adatti a questo criterio.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-280">US bank account numbers fit this pattern.</span></span>
- <span data-ttu-id="9fe6b-281">Indirizzo di posta elettronica: corrisponde a un tipo comune di indirizzo di posta elettronica come meganb@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-281">Email address: Matches a common type of email address like meganb@contoso.com.</span></span>
- <span data-ttu-id="9fe6b-282">Codice identificativo del contribuente statunitense: corrisponde a un numero di tre cifre che inizia con 9 seguito da un numero di 6 cifre che inizia con 7 o 8.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-282">US taxpayer ID number: Matches a three-digit number starting with 9 followed by a 6 digit number starting with 7 or 8.</span></span> 
- <span data-ttu-id="9fe6b-283">Indirizzo Web (URL): corrisponde al formato di un indirizzo Web, a partire http:// o https://.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-283">Web address (URL): Matches the format of a web address, starting with http:// or https://.</span></span>

<span data-ttu-id="9fe6b-284">Inoltre, la raccolta di spiegazioni include tre tipi di modello automatico che funzionano con i dati etichettati nei file di esempio:</span><span class="sxs-lookup"><span data-stu-id="9fe6b-284">In addition, the explanation library includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="9fe6b-285">Dopo l'etichetta: le parole o i caratteri dopo le etichette nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-285">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="9fe6b-286">Prima dell'etichetta: le parole o i caratteri prima delle etichette nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-286">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="9fe6b-287">Etichette: fino alle prime 10 etichette dei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-287">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="9fe6b-288">Al fine di comprendere il funzionamento delle etichette, nell’esempio che segue verrà usato il modello di spiegazione Prima dell’etichetta che consente di fornire al modello altre informazioni per ottenere una corrispondenza più accurata.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-288">To give you an example of how automatic templates work, in the following example file, we'll use the Before label explanation template to help give the model more information to get a more accurate match.</span></span>

![File di esempio](../media/content-understanding/before-label.png)

<span data-ttu-id="9fe6b-290">Quando si seleziona il modello di spiegazione Prima dell'etichetta, questo cerca il primo set di parole visualizzato prima dell'etichetta nei file di esempio.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-290">When you select the Before label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="9fe6b-291">Le parole identificate nel primo file di esempio sono "Dal”.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-291">In the example, the words that are identified in the first example file is "As of".</span></span>

![Modello prima dell’etichetta](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="9fe6b-293">È possibile selezionare **Aggiungi** per creare una spiegazione del modello.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-293">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="9fe6b-294">Man mano che si aggiungono altri file di esempio, vengono identificate e aggiunte altre parole all'elenco frasi.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-294">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![Aggiungere l'etichetta](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="9fe6b-296">Per usare un modello dalla raccolta di spiegazioni</span><span class="sxs-lookup"><span data-stu-id="9fe6b-296">To use a template from the explanation library</span></span>

1. <span data-ttu-id="9fe6b-297">Nella sezione **Spiegazioni** della pagina **Avvia training** del modello selezionare **Nuovo**, quindi **Da un modello**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-297">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![Aggiungere prima dell'etichetta](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="9fe6b-299">Nella pagina **Modelli di spiegazione** selezionare la spiegazione da usare, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-299">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![Selezionare un modello](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="9fe6b-301">Le informazioni relative al modello selezionato sono visualizzate nella pagina **Crea spiegazione**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-301">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="9fe6b-302">Se necessario, modificare il nome della spiegazione e aggiungere o rimuovere le voci dall'elenco frasi.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-302">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![Modifica modello](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="9fe6b-304">Al termine, selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9fe6b-304">When finished, select **Save**.</span></span>