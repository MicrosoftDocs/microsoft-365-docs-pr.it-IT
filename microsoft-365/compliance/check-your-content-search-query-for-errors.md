---
title: Verificare la presenza di errori nella query di ricerca
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: Informazioni su come rilevare errori e errori di digitazione nella query con parole chiave per le ricerche di eDiscovery prima di eseguire la ricerca.
ms.openlocfilehash: 9c041ca690df3306347cbca77df3ba9639801245
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311689"
---
# <a name="check-your-search-query-for-errors"></a><span data-ttu-id="459d4-103">Verificare la presenza di errori nella query di ricerca</span><span class="sxs-lookup"><span data-stu-id="459d4-103">Check your search query for errors</span></span>
  
<span data-ttu-id="459d4-104">Ecco un elenco dei caratteri non supportati che controlliamo nelle query di ricerca per Ricerca contenuto ed eDiscovery di base.</span><span class="sxs-lookup"><span data-stu-id="459d4-104">Here's a list of the unsupported characters that we check for in search queries for Content search and Core eDiscovery.</span></span> <span data-ttu-id="459d4-105">I caratteri non supportati sono spesso nascosti e in genere causano un errore di ricerca o restituiscono risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="459d4-105">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="459d4-106">**Virgolette intelligenti** : le virgolette singole e doppie intelligenti (denominate anche virgolette graffe) non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="459d4-106">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="459d4-107">In una query di ricerca è possibile utilizzare solo virgolette semplici.</span><span class="sxs-lookup"><span data-stu-id="459d4-107">Only straight quotation marks can be used in a search query.</span></span> 

- <span data-ttu-id="459d4-108">**Caratteri non stampabili e** di controllo - I caratteri non stampabili e di controllo non rappresentano un simbolo scritto, ad esempio un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="459d4-108">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="459d4-109">Esempi di caratteri non stampabili e di controllo includono caratteri che formattano testo o righe di testo separate.</span><span class="sxs-lookup"><span data-stu-id="459d4-109">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 

- <span data-ttu-id="459d4-110">**Segni da** sinistra a destra e da destra a sinistra- Questi segni sono caratteri di controllo utilizzati per indicare la direzione del testo per le lingue da sinistra a destra (ad esempio inglese e spagnolo) e le lingue da destra a sinistra (ad esempio arabo ed ebraico).</span><span class="sxs-lookup"><span data-stu-id="459d4-110">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>

- <span data-ttu-id="459d4-111">**Operatori booleani** minuscoli- Se si utilizza un operatore booleano, ad esempio **AND**, **OR** e **NOT** in una query di ricerca, è necessario che sia maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="459d4-111">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="459d4-112">Quando si verifica la presenza di errori di digitazione in una query, la sintassi della query spesso indica che viene utilizzato un operatore Boolean anche se è possibile utilizzare operatori minuscoli. ad  `(WordA or WordB) and (WordC or WordD)` esempio.</span><span class="sxs-lookup"><span data-stu-id="459d4-112">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="459d4-113">Cosa succede se una query ha un carattere non supportato?</span><span class="sxs-lookup"><span data-stu-id="459d4-113">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="459d4-114">Se nella query vengono trovati caratteri non supportati, viene visualizzato un messaggio di avviso che indica che sono stati trovati caratteri non supportati e suggerisce un'alternativa.</span><span class="sxs-lookup"><span data-stu-id="459d4-114">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="459d4-115">È quindi possibile mantenere la query originale o sostituirla con la query rivista suggerita.</span><span class="sxs-lookup"><span data-stu-id="459d4-115">You then have the option keep the original query or replace it with the suggested revised query.</span></span>

<span data-ttu-id="459d4-116">Ecco un esempio del messaggio di avviso visualizzato dopo aver fatto clic su Controlla **query** per errori di digitazione per la query di ricerca nello screenshot precedente.</span><span class="sxs-lookup"><span data-stu-id="459d4-116">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="459d4-117">Si noti che la query originale ha utilizzato le virgolette intelligenti e gli operatori booleani minuscoli.</span><span class="sxs-lookup"><span data-stu-id="459d4-117">Note the original query used smart quotes and lowercase Boolean operators.</span></span>
  
![Viene visualizzato un messaggio di avviso con una revisione suggerita per la query](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="459d4-119">Come impedire i caratteri non supportati nelle query di ricerca</span><span class="sxs-lookup"><span data-stu-id="459d4-119">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="459d4-120">I caratteri non supportati vengono in genere aggiunti a una query quando si copiano la query o parti della query da altre applicazioni (ad esempio Microsoft Word o Microsoft Excel) e li incollano nella casella parola chiave nella pagina di query di una ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="459d4-120">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="459d4-121">Il modo migliore per impedire i caratteri non supportati è semplicemente digitare la query nella casella parola chiave.</span><span class="sxs-lookup"><span data-stu-id="459d4-121">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="459d4-122">Oppure è possibile copiare una query da Word o Excel e quindi incollarla in un editor di testo normale, ad esempio Microsoft Blocco note.</span><span class="sxs-lookup"><span data-stu-id="459d4-122">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="459d4-123">Salvare il file di testo e selezionare **ANSI** **nell'elenco a** discesa Codifica.</span><span class="sxs-lookup"><span data-stu-id="459d4-123">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="459d4-124">Questa operazione rimuoverà la formattazione e i caratteri non supportati.</span><span class="sxs-lookup"><span data-stu-id="459d4-124">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="459d4-125">È quindi possibile copiare e incollare la query dal file di testo alla casella di query con parole chiave.</span><span class="sxs-lookup"><span data-stu-id="459d4-125">Then you can copy and paste the query from the text file to the keyword query box.</span></span>
