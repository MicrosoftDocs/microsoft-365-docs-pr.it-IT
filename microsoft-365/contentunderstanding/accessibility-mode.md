---
title: 'Modalità di accessibilità di SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Scopri come usare la modalità di accessibilità durante il training di un modello in SharePoint Syntex.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515149"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="9135d-103">Modalità di accessibilità di SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="9135d-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="9135d-104">In [SharePoint Syntex,](index.md)gli utenti possono attivare la modalità di accessibilità in tutte le fasi del training del modello (etichetta, training, test) quando si lavora con documenti di esempio.</span><span class="sxs-lookup"><span data-stu-id="9135d-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="9135d-105">L'uso della modalità di accessibilità può aiutare gli utenti con problemi di vista a semplificare l'accessibilità tramite tastiera man mano che si spostano e etichettano gli elementi nel visualizzatore di documenti.</span><span class="sxs-lookup"><span data-stu-id="9135d-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="9135d-106">In questo modo, gli utenti possono usare le tastiere per spostarsi all'interno del testo nel visualizzatore di documenti e ascoltare un commento non solo sui valori selezionati, ma anche sulle azioni (ad esempio l'etichettatura o la rimozione di etichette dal testo selezionato) o sui valori previsti dell'etichetta durante il training del modello con altri documenti di esempio.</span><span class="sxs-lookup"><span data-stu-id="9135d-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![Modalità accessibilità](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="9135d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9135d-108">Requirements</span></span>

<span data-ttu-id="9135d-109">Per ascoltare l'audio del commento audio, assicurati di attivare [l'app Assistente vocale](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) nelle impostazioni Assistente vocale nel sistema Windows 10 audio.</span><span class="sxs-lookup"><span data-stu-id="9135d-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![Attivare Assistente vocale](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="9135d-111">Etichettatura per gli utenti della tastiera</span><span class="sxs-lookup"><span data-stu-id="9135d-111">Labeling for keyboard users</span></span>

<span data-ttu-id="9135d-112">Per gli utenti della tastiera che usano la modalità di accessibilità, se stai etichettando il testo in un documento di esempio nel visualizzatore, puoi usare i tasti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9135d-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="9135d-113">Tab: sposta l'utente in avanti e seleziona la parola successiva.</span><span class="sxs-lookup"><span data-stu-id="9135d-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="9135d-114">TAB + MAIUSC: consente di spostarsi all'indietro e selezionare la parola precedente.</span><span class="sxs-lookup"><span data-stu-id="9135d-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="9135d-115">Invio: etichetta o rimuove un'etichetta dalla parola selezionata.</span><span class="sxs-lookup"><span data-stu-id="9135d-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="9135d-116">Freccia destra: consente di spostarsi in avanti tra i singoli caratteri di una parola selezionata.</span><span class="sxs-lookup"><span data-stu-id="9135d-116">Right arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="9135d-117">Freccia sinistra: consente di spostarsi all'indietro tra i singoli caratteri di una parola selezionata.</span><span class="sxs-lookup"><span data-stu-id="9135d-117">Left arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="9135d-118">Se si stanno etichettando più parole per una singola etichetta, è necessario etichettare ogni parola.</span><span class="sxs-lookup"><span data-stu-id="9135d-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="9135d-119">Commento audio</span><span class="sxs-lookup"><span data-stu-id="9135d-119">Narration</span></span>

<span data-ttu-id="9135d-120">Per Assistente vocale utenti che usano la modalità di accessibilità, usa la stessa navigazione da tastiera descritta per gli utenti con tastiera per passare attraverso il documento di esempio nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="9135d-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="9135d-121">Durante lo spostamento tra i documenti di esempio e i valori delle stringhe di etichetta, Assistente vocale all'utente verranno visualizzate le istruzioni audio seguenti:</span><span class="sxs-lookup"><span data-stu-id="9135d-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="9135d-122">Quando usi la tastiera per spostarsi nel visualizzatore di documenti, Assistente vocale'audio segnalerà la stringa selezionata.</span><span class="sxs-lookup"><span data-stu-id="9135d-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="9135d-123">All'interno di una stringa selezionata, Assistente vocale audio segnalerà ogni carattere nella stringa mentre li si seleziona utilizzando i tasti freccia sinistra o destra.</span><span class="sxs-lookup"><span data-stu-id="9135d-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the left or right arrow keys.</span></span>
- <span data-ttu-id="9135d-124">Se si seleziona una stringa etichettata, Assistente vocale il valore e quindi "etichettato".</span><span class="sxs-lookup"><span data-stu-id="9135d-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="9135d-125">Ad esempio, se il valore dell'etichetta è "Contoso", verrà visualizzato "Costoso etichettato".</span><span class="sxs-lookup"><span data-stu-id="9135d-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="9135d-126">Nella scheda training, se si seleziona una stringa nel visualizzatore di documenti che è stata solo stimata, Assistente vocale audio indica il valore e quindi "previsto".</span><span class="sxs-lookup"><span data-stu-id="9135d-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="9135d-127">Ciò si verifica quando il training prevede un valore nel file che non corrisponde a quello etichettato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9135d-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="9135d-128">Nella scheda training, se si seleziona una stringa nel visualizzatore di documenti che è stata etichettata e stimata, Assistente vocale audio verrà specificato il valore e quindi "etichettato e previsto".</span><span class="sxs-lookup"><span data-stu-id="9135d-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="9135d-129">Ciò si verifica quando la formazione ha esito positivo e esiste una corrispondenza tra un valore previsto e l'etichetta utente.</span><span class="sxs-lookup"><span data-stu-id="9135d-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="9135d-130">Dopo l'etichetta di una stringa o la rimozione di un'etichetta nel visualizzatore, l Assistente vocale audio ti avvisa di salvare le modifiche prima di uscire.</span><span class="sxs-lookup"><span data-stu-id="9135d-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="9135d-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9135d-131">See Also</span></span>

[<span data-ttu-id="9135d-132">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="9135d-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="9135d-133">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="9135d-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



