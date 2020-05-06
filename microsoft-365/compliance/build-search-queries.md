---
title: Creare query di ricerca-indagini sui dati
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom: seo-marvel-mar2020
description: Utilizzare parole chiave e condizioni per limitare l'ambito di ricerca durante la ricerca di dati utilizzando l'analisi dei dati in Microsoft 365.
ms.openlocfilehash: 95466d0e7c7109001fef001cc0d5bca5b6d658ed
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034114"
---
# <a name="build-search-queries"></a><span data-ttu-id="6d3b7-103">Creare query di ricerca</span><span class="sxs-lookup"><span data-stu-id="6d3b7-103">Build search queries</span></span>

<span data-ttu-id="6d3b7-104">Durante la creazione di query di ricerca, è possibile utilizzare parole chiave per trovare contenuti e condizioni specifici per limitare l'ambito della ricerca per restituire gli elementi più rilevanti per l'indagine.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-104">When building search queries, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your investigation.</span></span>

![Utilizzare parole chiave e condizioni per limitare i risultati di una ricerca](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="6d3b7-106">Ricerche di parole chiave</span><span class="sxs-lookup"><span data-stu-id="6d3b7-106">Keyword searches</span></span>

<span data-ttu-id="6d3b7-107">Digitare una query di parole chiave nella casella **Keywords** della query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="6d3b7-108">È possibile specificare le parole chiave, le proprietà del messaggio di posta elettronica, ad esempio le date inviate e ricevute, o le proprietà del documento, ad esempio i nomi di file o la data dell'Ultima modifica di un documento.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-108">You can specify keywords, email message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="6d3b7-109">È anche possibile usare query più complesse che usano un operatore booleano, ad esempio **AND**, **OR**, **NOT** o **NEAR**.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="6d3b7-110">È inoltre possibile cercare informazioni riservate, ad esempio i numeri di previdenza sociale, nei documenti di SharePoint e OneDrive (non nei messaggi di posta elettronica) oppure cercare documenti che sono stati condivisi esternamente.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-110">You can also search for sensitive information, such as social security numbers, in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="6d3b7-111">Se si lascia vuota la casella **parole chiave** , tutto il contenuto che si trova nei percorsi di contenuto specificato è incluso nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-111">If you leave the **Keywords** box empty, all content located in the specified content locations is included in the search results.</span></span>
    
<span data-ttu-id="6d3b7-112">In alternativa, è possibile selezionare la casella di controllo **Mostra elenco parole chiave** e quindi digitare una parola chiave o una frase di parole chiave in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-112">Alternatively, you can select the **Show keyword list** check box and then type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="6d3b7-113">Se si esegue questa operazione, le parole chiave in ogni riga sono connesse da un operatore logico (rappresentato come *c:s*) che è simile alla funzionalità all'operatore **or** nella query di ricerca creata.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-113">If you do this, the keywords in each row are connected by a logical operator (represented as *c:s*) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="6d3b7-114">Questo significa che gli elementi che contengono qualsiasi parola chiave in qualsiasi riga vengono inclusi nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-114">This means that items that contain any keyword in any row are included in the search results.</span></span>

![Utilizzare l'elenco di parole chiave per ottenere statistiche su ogni parola chiave nella query](../media/KeywordListSearch.png)

<span data-ttu-id="6d3b7-116">Perché usare l'elenco di parole chiave?</span><span class="sxs-lookup"><span data-stu-id="6d3b7-116">Why use the keyword list?</span></span> <span data-ttu-id="6d3b7-117">È possibile ottenere statistiche che mostrano quanti elementi corrispondono a ciascuna parola chiave nell'elenco delle parole chiave.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="6d3b7-118">In questo modo è possibile identificare rapidamente le parole chiave più (e meno) effettive.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="6d3b7-119">È inoltre possibile utilizzare una frase parola chiave (racchiusa tra parentesi) in una riga dell'elenco parole chiave.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="6d3b7-120">Per ulteriori informazioni sulle statistiche di ricerca, vedere [Search Statistics](search-statistics.md).</span><span class="sxs-lookup"><span data-stu-id="6d3b7-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6d3b7-121">Per contribuire a ridurre i problemi causati da elenchi di parole chiave di grandi dimensioni, è possibile limitare il numero massimo di 20 righe nell'elenco delle parole chiave.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="6d3b7-122">Condizioni</span><span class="sxs-lookup"><span data-stu-id="6d3b7-122">Conditions</span></span>
    
<span data-ttu-id="6d3b7-123">È possibile aggiungere condizioni di ricerca per limitare l'ambito di una ricerca e restituire un insieme di risultati più raffinato.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="6d3b7-124">Ogni condizione aggiunge una clausola alla query di ricerca creata ed eseguita all'avvio della ricerca.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="6d3b7-125">Una condizione è connessa logicamente alla query con parole chiave, specificata nella casella parola chiave, da un operatore logico (rappresentato come *c:c*) simile alla funzionalità all'operatore **and** .</span><span class="sxs-lookup"><span data-stu-id="6d3b7-125">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (which is represented as *c:c*) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="6d3b7-126">Questo significa che gli elementi devono soddisfare sia la query con parole chiave sia una o più condizioni da includere nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-126">This means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="6d3b7-127">Ecco in che modo le condizioni aiutano a limitare i risultati.</span><span class="sxs-lookup"><span data-stu-id="6d3b7-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="6d3b7-128">Per un elenco e una descrizione delle condizioni che è possibile utilizzare in una query di ricerca, vedere la sezione "condizioni di ricerca" in [query di parole chiave e condizioni di ricerca](keyword-queries-and-search-conditions.md#search-conditions).</span><span class="sxs-lookup"><span data-stu-id="6d3b7-128">For a list and description of conditions you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
