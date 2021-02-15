---
title: 'Modalità di accessibilità Syntex di SharePoint '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Informazioni su come usare la modalità di accessibilità durante la formazione di un modello in SharePoint Syntex.
ms.openlocfilehash: 32e5bd132a7a0145f03e4620545d65d1d92ff223
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "50081008"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="27e4e-103">Modalità di accessibilità Syntex di SharePoint</span><span class="sxs-lookup"><span data-stu-id="27e4e-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="27e4e-104">In [SharePoint Syntex,](index.md)gli utenti possono attivare la modalità accessibilità in tutte le fasi del training del modello (etichetta, formazione, test) quando si lavora con documenti di esempio.</span><span class="sxs-lookup"><span data-stu-id="27e4e-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="27e4e-105">L'uso della modalità di accessibilità può aiutare gli utenti con problemi di vista a semplificare l'accessibilità tramite tastiera mentre si spostano e etichettano gli elementi nel visualizzatore di documenti.</span><span class="sxs-lookup"><span data-stu-id="27e4e-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="27e4e-106">Ciò consente agli utenti di usare le tastiere per spostarsi all'interno del testo nel visualizzatore di documenti e ascoltare un commento audio non solo sui valori selezionati, ma anche sulle azioni (ad esempio l'etichettatura o la rimozione di etichette dal testo selezionato) o sui valori previsti per le etichette mentre si forma il modello con altri documenti di esempio.</span><span class="sxs-lookup"><span data-stu-id="27e4e-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![Modalità accessibilità](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="27e4e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="27e4e-108">Requirements</span></span>

<span data-ttu-id="27e4e-109">Per ascoltare l'audio del commento audio, assicurati di attivare [l'app](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) Assistente vocale nelle impostazioni dell'Assistente vocale nel sistema Windows 10.</span><span class="sxs-lookup"><span data-stu-id="27e4e-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![Attivare l'Assistente vocale](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="27e4e-111">Etichettatura per gli utenti della tastiera</span><span class="sxs-lookup"><span data-stu-id="27e4e-111">Labeling for keyboard users</span></span>

<span data-ttu-id="27e4e-112">Per gli utenti che usano la modalità accessibilità, se stai etichettando il testo in un documento di esempio nel visualizzatore, puoi usare i tasti seguenti:</span><span class="sxs-lookup"><span data-stu-id="27e4e-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="27e4e-113">Tab: sposta l'utente in avanti e seleziona la parola successiva.</span><span class="sxs-lookup"><span data-stu-id="27e4e-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="27e4e-114">TAB + MAIUSC: consente di spostarsi all'indietro e selezionare la parola precedente.</span><span class="sxs-lookup"><span data-stu-id="27e4e-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="27e4e-115">Invio: etichetta o rimuove un'etichetta dalla parola selezionata.</span><span class="sxs-lookup"><span data-stu-id="27e4e-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="27e4e-116">Freccia avanti: consente di spostarsi in avanti tra i singoli caratteri di una parola selezionata.</span><span class="sxs-lookup"><span data-stu-id="27e4e-116">Forward arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="27e4e-117">Freccia indietro: consente di spostarsi all'indietro tra i singoli caratteri di una parola selezionata.</span><span class="sxs-lookup"><span data-stu-id="27e4e-117">Backward arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="27e4e-118">Se si etichettano più parole per una singola etichetta, è necessario etichettare ogni parola.</span><span class="sxs-lookup"><span data-stu-id="27e4e-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="27e4e-119">Commenti audio</span><span class="sxs-lookup"><span data-stu-id="27e4e-119">Narration</span></span>

<span data-ttu-id="27e4e-120">Per gli utenti dell'Assistente vocale che usano la modalità di accessibilità, usa lo stesso spostamento tramite tastiera descritto per consentire agli utenti della tastiera di passare attraverso il documento di esempio nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="27e4e-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="27e4e-121">Durante lo spostamento tra i documenti di esempio e i valori delle stringhe delle etichette, l'Assistente vocale offrirà all'utente le istruzioni audio seguenti:</span><span class="sxs-lookup"><span data-stu-id="27e4e-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="27e4e-122">Quando usi la tastiera per spostarsi all'interno del visualizzatore di documenti, l'audio dell'Assistente vocale segnalerà la stringa selezionata.</span><span class="sxs-lookup"><span data-stu-id="27e4e-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="27e4e-123">All'interno di una stringa selezionata, l'audio dell'Assistente vocale segnalerà ogni carattere nella stringa mentre li selezionerai usando la freccia avanti o indietro.</span><span class="sxs-lookup"><span data-stu-id="27e4e-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the forward or backward arrow.</span></span>
- <span data-ttu-id="27e4e-124">Se si seleziona una stringa etichettata, l'Assistente vocale indica il valore e quindi "etichetta".</span><span class="sxs-lookup"><span data-stu-id="27e4e-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="27e4e-125">Ad esempio, se il valore dell'etichetta è "Contoso", verrà visualizzato lo stato "Costoso etichettato".</span><span class="sxs-lookup"><span data-stu-id="27e4e-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="27e4e-126">Nella scheda training, se si seleziona una stringa nel visualizzatore di documenti che è stata solo stimata, l'audio dell'Assistente vocale indica il valore e quindi "previsto".</span><span class="sxs-lookup"><span data-stu-id="27e4e-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="27e4e-127">Ciò si verifica quando il training prevede un valore nel file che non corrisponde a quello etichettato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="27e4e-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="27e4e-128">Nella scheda training, se si seleziona una stringa nel visualizzatore di documenti che è stata etichettata e stimata, l'audio dell'Assistente vocale indica il valore e quindi "etichettato e previsto".</span><span class="sxs-lookup"><span data-stu-id="27e4e-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="27e4e-129">Ciò si verifica quando il training ha esito positivo ed esiste una corrispondenza tra un valore previsto e l'etichetta utente.</span><span class="sxs-lookup"><span data-stu-id="27e4e-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="27e4e-130">Dopo l'etichetta di una stringa o la rimozione di un'etichetta nel visualizzatore, l'audio dell'Assistente vocale ti avvisa di salvare le modifiche prima di uscire.</span><span class="sxs-lookup"><span data-stu-id="27e4e-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="27e4e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27e4e-131">See Also</span></span>

[<span data-ttu-id="27e4e-132">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="27e4e-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="27e4e-133">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="27e4e-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



