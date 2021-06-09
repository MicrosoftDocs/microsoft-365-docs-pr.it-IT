---
title: Ritentare una ricerca di contenuto per risolvere un errore di percorso del contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Durante un'indagine, è possibile utilizzare il pulsante Riprova per risolvere le ricerche di contenuto con errori relativi alla posizione del contenuto.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311821"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="df711-103">Ritentare una ricerca di contenuto per risolvere un errore di percorso del contenuto</span><span class="sxs-lookup"><span data-stu-id="df711-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="df711-104">Quando si utilizza Ricerca contenuto nel Centro sicurezza e conformità per cercare un numero elevato di cassette postali, è possibile che si otterrà errori di ricerca simili all'errore:</span><span class="sxs-lookup"><span data-stu-id="df711-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the  error:</span></span>

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="df711-105">Questi errori (con codici di errore CS001-002, CS003-002, CS008-009, CS012-002 e altri errori nel formato CS0XX-0XX) indicano che ricerca contenuto non è riuscita a cercare percorsi di contenuto specifici. in questo esempio, non è stata ricercata due cassette postali.</span><span class="sxs-lookup"><span data-stu-id="df711-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="df711-106">Questi errori vengono visualizzati nella pagina a comparsa dei dettagli sullo stato della ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="df711-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="df711-107">Causa degli errori relativi al percorso del contenuto</span><span class="sxs-lookup"><span data-stu-id="df711-107">Cause of content location errors</span></span>

<span data-ttu-id="df711-108">Quando si esegue una ricerca in un numero elevato di cassette postali, la ricerca viene distribuita su migliaia di server in un datacenter Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df711-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="df711-109">In qualsiasi momento, server specifici potrebbero essere in stato di riavvio o in fase di failover in copie ridondanti.</span><span class="sxs-lookup"><span data-stu-id="df711-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="df711-110">In uno di questi casi, il timeout della richiesta di recupero dei dati da parte della ricerca di contenuto. Nell'esempio precedente, gli errori per le cassette postali non riuscite erano il risultato del timeout della ricerca.</span><span class="sxs-lookup"><span data-stu-id="df711-110">In either of these cases, the Content Search's request to retrieve data will time out. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="df711-111">Risoluzione degli errori relativi alla posizione del contenuto</span><span class="sxs-lookup"><span data-stu-id="df711-111">Resolving content location errors</span></span>

<span data-ttu-id="df711-112">Il riavvio della ricerca spesso genererà errori simili in server diversi.</span><span class="sxs-lookup"><span data-stu-id="df711-112">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="df711-113">Anziché riavviare la ricerca, fare clic sul pulsante **Riprova** visualizzato nella parte superiore della pagina dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="df711-113">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![Fare clic sul pulsante Riprova per risolvere gli errori relativi alla posizione del contenuto](../media/retrycontentsearch3.png)

<span data-ttu-id="df711-115">In questo modo verrà eseguito un nuovo tentativo di ricerca solo per le cassette postali non riuscite.</span><span class="sxs-lookup"><span data-stu-id="df711-115">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="df711-116">Quando si ritenta la ricerca, gli altri risultati restituiti correttamente vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="df711-116">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="df711-117">Suggerimenti evitare errori relativi al percorso del contenuto</span><span class="sxs-lookup"><span data-stu-id="df711-117">Tips to avoid content location errors</span></span>

<span data-ttu-id="df711-118">Ecco alcune cause aggiuntive degli errori relativi alla posizione del contenuto e alcuni suggerimenti per evitarli durante la ricerca di un numero elevato di cassette postali.</span><span class="sxs-lookup"><span data-stu-id="df711-118">Here are some additional causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="df711-119">La cassetta postale da cercare potrebbe essere occupata a causa dell'attività dell'utente.</span><span class="sxs-lookup"><span data-stu-id="df711-119">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="df711-120">In questo caso, il servizio di ricerca potrebbe essere limitato per evitare che la cassetta postale diventi non disponibile.</span><span class="sxs-lookup"><span data-stu-id="df711-120">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="df711-121">Per evitare questo problema, provare a eseguire ricerche durante l'orario non di ufficio.</span><span class="sxs-lookup"><span data-stu-id="df711-121">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="df711-122">La query di ricerca potrebbe recuperare troppo contenuto dalla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="df711-122">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="df711-123">Se possibile, provare a restringere l'ambito della ricerca utilizzando parole chiave, intervalli di date e condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="df711-123">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="df711-124">Troppe parole chiave o frasi di parole chiave quando si crea una query di ricerca utilizzando [l'elenco di parole chiave](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span><span class="sxs-lookup"><span data-stu-id="df711-124">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span></span> <span data-ttu-id="df711-125">Quando si esegue una query di ricerca che utilizza l'elenco di parole chiave, il servizio esegue essenzialmente una ricerca separata per ogni riga dell'elenco di parole chiave in modo da poter generare statistiche.</span><span class="sxs-lookup"><span data-stu-id="df711-125">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="df711-126">Se si utilizza l'elenco di parole chiave nelle query di ricerca, ridurre al minimo il numero di righe nell'elenco di parole chiave o dividere le parole chiave del numero in elenchi più piccoli e creare una ricerca diversa per ogni elenco di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="df711-126">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="df711-127">Per ridurre i problemi causati da elenchi di parole chiave di grandi dimensioni, ora si è limitati a un massimo di 20 righe nell'elenco di parole chiave di una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="df711-127">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="df711-128">Troppe ricerche vengono eseguite contemporaneamente sulla stessa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="df711-128">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="df711-129">Se possibile, provare a eseguire una ricerca alla volta in una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="df711-129">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="df711-130">Ricerca di troppe cassette postali in una singola ricerca.</span><span class="sxs-lookup"><span data-stu-id="df711-130">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="df711-131">La probabilità di errori del percorso del contenuto aumenta durante la ricerca in un numero elevato di cassette postali.</span><span class="sxs-lookup"><span data-stu-id="df711-131">The probability of content location errors increases when searching a large number of mailboxes.</span></span> <span data-ttu-id="df711-132">Se possibile, provare a eseguire più ricerche in modo che ogni ricerca includa un sottoinsieme di cassette postali nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df711-132">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="df711-133">È in corso la manutenzione necessaria per la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="df711-133">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="df711-134">Anche se questa causa probabilmente si verifica raramente, attendere un po' dopo aver ricevuto l'errore del percorso del contenuto e quindi ritentare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="df711-134">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
