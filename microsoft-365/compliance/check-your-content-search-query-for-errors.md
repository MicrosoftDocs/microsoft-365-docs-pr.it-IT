---
title: Verificare la presenza di errori nella query di Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: Informazioni su come rilevare errori e errori di digitazione nella query con parole chiave per la ricerca di contenuto, prima di eseguire la ricerca.
ms.openlocfilehash: 250db272014d5801bfb3927d14072eea94bd635f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818095"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="14e44-103">Verificare la presenza di errori nella query di Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="14e44-103">Check your Content Search query for errors</span></span>

<span data-ttu-id="14e44-104">Quando si crea o si modifica una ricerca di contenuto, è possibile fare in modo che Microsoft 365 controlli la query per verificare la presenza di caratteri non supportati e operatori booleani minuscoli.</span><span class="sxs-lookup"><span data-stu-id="14e44-104">When you create or edit a Content Search, you can have Microsoft 365 check your query for unsupported characters and lowercase Boolean operators.</span></span> <span data-ttu-id="14e44-105">Come?</span><span class="sxs-lookup"><span data-stu-id="14e44-105">How?</span></span> <span data-ttu-id="14e44-106">È sufficiente **fare clic su Controlla errori di digitazione** nella pagina di query di una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="14e44-106">Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![Fare clic su "Controlla errori di digitazione nella query" per verificare la presenza di caratteri non supportati nella query di ricerca](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="14e44-108">Ecco un elenco dei caratteri non supportati che controlliamo.</span><span class="sxs-lookup"><span data-stu-id="14e44-108">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="14e44-109">I caratteri non supportati sono spesso nascosti e in genere causano un errore di ricerca o restituiscono risultati indesiderati.</span><span class="sxs-lookup"><span data-stu-id="14e44-109">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="14e44-110">**Virgolette inglesi** - Le virgolette singole e doppie intelligenti (denominate anche virgolette inglesi) non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="14e44-110">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="14e44-111">In una query di ricerca è possibile utilizzare solo le virgolette semplici.</span><span class="sxs-lookup"><span data-stu-id="14e44-111">Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="14e44-112">**Caratteri non stampabili** e di controllo: i caratteri non stampabili e di controllo non rappresentano un simbolo scritto, ad esempio un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="14e44-112">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="14e44-113">Tra gli esempi di caratteri non stampabili e di controllo sono inclusi i caratteri che formattano il testo o righe di testo separate.</span><span class="sxs-lookup"><span data-stu-id="14e44-113">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="14e44-114">Segni da sinistra a destra e da destra a **sinistra-** Questi segni sono caratteri di controllo utilizzati per indicare la direzione del testo per le lingue da sinistra a destra (ad esempio inglese e spagnolo) e lingue da destra a sinistra (ad esempio arabo ed ebraico).</span><span class="sxs-lookup"><span data-stu-id="14e44-114">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="14e44-115">**Operatori booleani minuscoli:** se si utilizza un operatore booleano, ad esempio **AND**, **OR** e **NOT** in una query di ricerca, è necessario che sia maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="14e44-115">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="14e44-116">Quando viene verificata la presenza di errori di digitazione in una query, la sintassi della query spesso indica che viene utilizzato un operatore booleano anche se è possibile utilizzare operatori minuscoli. ad esempio  `(WordA or WordB) and (WordC or WordD)` .</span><span class="sxs-lookup"><span data-stu-id="14e44-116">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="14e44-117">Cosa succede se una query contiene un carattere non supportato?</span><span class="sxs-lookup"><span data-stu-id="14e44-117">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="14e44-118">Se nella query vengono trovati caratteri non supportati, viene visualizzato un messaggio di avviso che indica che sono stati trovati caratteri non supportati e suggerisce un'alternativa.</span><span class="sxs-lookup"><span data-stu-id="14e44-118">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="14e44-119">È quindi possibile mantenere la query originale o sostituirla con la query modificata suggerita.</span><span class="sxs-lookup"><span data-stu-id="14e44-119">You then have the option keep the original query or replace it with the suggested revised query.</span></span> <span data-ttu-id="14e44-120">Ecco un esempio del messaggio di avviso visualizzato dopo aver fatto clic su Controlla **query** per errori di digitazione per la query di ricerca nello screenshot precedente.</span><span class="sxs-lookup"><span data-stu-id="14e44-120">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="14e44-121">Si noti che la query originale contiene virgolette intelligenti e operatori booleani minuscoli.</span><span class="sxs-lookup"><span data-stu-id="14e44-121">Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![Viene visualizzato un messaggio di avviso con una revisione suggerita per la query](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="14e44-123">Come impedire i caratteri non supportati nelle query di ricerca</span><span class="sxs-lookup"><span data-stu-id="14e44-123">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="14e44-124">I caratteri non supportati vengono in genere aggiunti a una query quando si copia la query o parti di tale query da altre applicazioni, ad esempio Microsoft Word o Microsoft Excel, e li si incolla nella casella delle parole chiave nella pagina della query di una ricerca di contenuto.</span><span class="sxs-lookup"><span data-stu-id="14e44-124">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="14e44-125">Il modo migliore per impedire i caratteri non supportati è semplicemente digitare la query nella casella della parola chiave.</span><span class="sxs-lookup"><span data-stu-id="14e44-125">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="14e44-126">Oppure è possibile copiare una query da Word o Excel e quindi incollarla in un editor di testo normale, ad esempio Blocco note Microsoft.</span><span class="sxs-lookup"><span data-stu-id="14e44-126">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="14e44-127">Salvare il file di testo e selezionare **ANSI** **nell'elenco a** discesa Codifica.</span><span class="sxs-lookup"><span data-stu-id="14e44-127">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="14e44-128">In questo modo verranno rimosso tutti i caratteri di formattazione e non supportati.</span><span class="sxs-lookup"><span data-stu-id="14e44-128">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="14e44-129">È quindi possibile copiare e incollare la query dal file di testo alla casella di query con parole chiave.</span><span class="sxs-lookup"><span data-stu-id="14e44-129">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
