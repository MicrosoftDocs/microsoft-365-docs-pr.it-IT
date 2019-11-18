---
title: Riprovare una ricerca contenuto per risolvere un errore del percorso del contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Utilizzare il pulsante Riprova per risolvere le ricerche di contenuto che presentano errori di posizione del contenuto.
ms.openlocfilehash: b35c2985efeafa3192a2404047fe62e28e04157e
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686612"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="e791e-103">Riprovare una ricerca contenuto per risolvere un errore del percorso del contenuto</span><span class="sxs-lookup"><span data-stu-id="e791e-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="e791e-104">Quando si utilizza la ricerca contenuto nel centro sicurezza e conformità per eseguire ricerche in un numero elevato di cassette postali, è possibile che si verifichino errori di ricerca analoghi a quelli riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="e791e-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the following:</span></span>

```text
Error

The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="e791e-105">Tali errori (con i codici di errore di CS001-002, CS003-002, CS008-009, CS012-002 e altri errori del modulo CS0XX-0XX) indicano che la ricerca contenuto non è riuscita a individuare percorsi di contenuto specifici. in questo esempio non sono state cercate due cassette postali.</span><span class="sxs-lookup"><span data-stu-id="e791e-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="e791e-106">Questi errori vengono visualizzati nella pagina del riquadro a comparsa dei dettagli sullo stato della ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="e791e-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="e791e-107">Causa degli errori del percorso del contenuto</span><span class="sxs-lookup"><span data-stu-id="e791e-107">Cause of content location errors</span></span>

<span data-ttu-id="e791e-108">Quando si esegue la ricerca di un numero elevato di cassette postali, la ricerca viene distribuita in migliaia di server in un datacenter Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e791e-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="e791e-109">In una sola volta, i server specifici potrebbero essere nello stato di riavvio o nel processo di failover di copie ridondanti.</span><span class="sxs-lookup"><span data-stu-id="e791e-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="e791e-110">In entrambi i casi, la richiesta di ricerca del contenuto per il recupero dei dati verrà impostata su timeout.</span><span class="sxs-lookup"><span data-stu-id="e791e-110">In either of these cases, the Content Search's request to retrieve data will timeout.</span></span> <span data-ttu-id="e791e-111">Nell'esempio precedente gli errori relativi alle cassette postali non riuscite sono stati causati dal timeout della ricerca.</span><span class="sxs-lookup"><span data-stu-id="e791e-111">In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="e791e-112">Risoluzione degli errori relativi alla posizione del contenuto</span><span class="sxs-lookup"><span data-stu-id="e791e-112">Resolving content location errors</span></span>

<span data-ttu-id="e791e-113">Il riavvio della ricerca spesso comporterà errori simili su server diversi.</span><span class="sxs-lookup"><span data-stu-id="e791e-113">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="e791e-114">Invece di riavviare la ricerca, fare clic sul pulsante **Riprova** visualizzato nella parte superiore della pagina dei risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e791e-114">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![Fare clic sul pulsante Riprova per risolvere gli errori relativi alla posizione del contenuto](media/retrycontentsearch3.png)

<span data-ttu-id="e791e-116">In questo modo, la ricerca verrà ritentata solo per le cassette postali che hanno avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e791e-116">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="e791e-117">Quando si ritenta la ricerca, vengono mantenuti gli altri risultati restituiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="e791e-117">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="e791e-118">Suggerimenti per evitare errori di posizione del contenuto</span><span class="sxs-lookup"><span data-stu-id="e791e-118">Tips to avoid content location errors</span></span>

<span data-ttu-id="e791e-119">Di seguito sono riportate alcune cause di aggiunta degli errori relativi alla posizione del contenuto e alcuni suggerimenti utili per evitarli quando si cerca un numero elevato di cassette postali.</span><span class="sxs-lookup"><span data-stu-id="e791e-119">Here are some addition causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="e791e-120">La cassetta postale che si sta cercando potrebbe essere occupata a causa dell'attività dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e791e-120">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="e791e-121">In questo caso, il servizio di ricerca potrebbe limitarsi a impedire che la cassetta postale diventi non disponibile.</span><span class="sxs-lookup"><span data-stu-id="e791e-121">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="e791e-122">Per evitare questo, provare a eseguire le ricerche durante gli orari non di ufficio.</span><span class="sxs-lookup"><span data-stu-id="e791e-122">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="e791e-123">La query di ricerca potrebbe recuperare troppo contenuto dalla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e791e-123">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="e791e-124">Se possibile, provare a restringere l'ambito della ricerca utilizzando parole chiave, intervalli di date e condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e791e-124">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="e791e-125">Se si crea una query di ricerca utilizzando l' [elenco delle parole](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)chiave, vengono create troppe parole chiavi o frasi.</span><span class="sxs-lookup"><span data-stu-id="e791e-125">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches).</span></span> <span data-ttu-id="e791e-126">Quando si esegue una query di ricerca che utilizza l'elenco di parole chiave, il servizio esegue essenzialmente una ricerca distinta per ogni riga dell'elenco di parole chiave in modo che le statistiche possano essere generate.</span><span class="sxs-lookup"><span data-stu-id="e791e-126">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="e791e-127">Se si utilizza l'elenco delle parole chiave nelle query di ricerca, ridurre al minimo il numero di righe nell'elenco parole chiave o dividere il numero in elenchi di dimensioni ridotte e creare una ricerca diversa per ogni elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="e791e-127">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e791e-128">Per contribuire a ridurre i problemi causati da elenchi di parole chiave di grandi dimensioni, si è limitato a un massimo di 20 righe nell'elenco delle parole chiave di una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e791e-128">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="e791e-129">Sono state eseguite troppe ricerche contemporaneamente sulla stessa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e791e-129">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="e791e-130">Se possibile, provare a eseguire una ricerca alla volta su una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e791e-130">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="e791e-131">Ricerca di un numero eccessivo di cassette postali in una singola ricerca.</span><span class="sxs-lookup"><span data-stu-id="e791e-131">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="e791e-132">Quando si esegue la ricerca di un numero elevato di cassette postali, aumenta la probabilità che si verifichino errori.</span><span class="sxs-lookup"><span data-stu-id="e791e-132">The probability of content location errors increases when searching a very large number of mailboxes.</span></span> <span data-ttu-id="e791e-133">Se possibile, provare a eseguire più ricerche in modo che ogni ricerca includa un sottoinsieme di cassette postali nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e791e-133">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="e791e-134">La manutenzione necessaria viene eseguita sulla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e791e-134">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="e791e-135">Anche se questa causa si verifica raramente, attendere un po' di tempo dopo aver ricevuto l'errore relativo alla posizione del contenuto e quindi riprovare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e791e-135">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
