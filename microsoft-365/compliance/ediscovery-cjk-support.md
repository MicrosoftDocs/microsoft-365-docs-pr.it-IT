---
title: Supporto CJK/Double Byte per Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come Advanced eDiscovery in Microsoft 365 supporta le lingue cinese, giapponese e coreano (CJK), che utilizzano un set di caratteri a byte doppio.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626936"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="bf7af-103">Supporto del linguaggio CJK per Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bf7af-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="bf7af-104">Advanced eDiscovery supporta le lingue dei set di caratteri a byte doppio (tra cui cinese semplificato, cinese tradizionale, giapponese e coreano, note collettivamente come lingue *CJK)* per i seguenti scenari avanzati in un insieme da rivedere:</span><span class="sxs-lookup"><span data-stu-id="bf7af-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="bf7af-105">Quando si [esegue una query sui dati in un insieme da rivedere.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="bf7af-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="bf7af-106">Quando si [contrassegnano i documenti in un insieme da rivedere.](tagging-documents.md)</span><span class="sxs-lookup"><span data-stu-id="bf7af-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="bf7af-107">Quando si [analizzano i dati del caso in un insieme da rivedere](analyzing-data-in-review-set.md) usando il rilevamento quasi duplicato, il threading della posta elettronica e l'analisi dei temi.</span><span class="sxs-lookup"><span data-stu-id="bf7af-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="bf7af-108">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="bf7af-108">Frequently asked questions</span></span>

<span data-ttu-id="bf7af-109">**Come si crea una ricerca per raccogliere elementi che contengono caratteri CJK?**</span><span class="sxs-lookup"><span data-stu-id="bf7af-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="bf7af-110">È possibile utilizzare i caratteri CJK per [le](building-search-queries.md#keyword-searches)ricerche tramite parole chiave, le query con [parole chiave](keyword-queries-and-search-conditions.md) e le condizioni di ricerca durante la ricerca di contenuto in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="bf7af-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="bf7af-111">La ricerca di caratteri CJK è supportata anche quando si cerca contenuto in Core eDiscovery e Ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="bf7af-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="bf7af-112">Viene fornito il supporto [](keyword-queries-and-search-conditions.md#search-operators) CJK per tutti gli operatori di ricerca e le condizioni di [ricerca,](keyword-queries-and-search-conditions.md#search-conditions)inclusi gli operatori **booleani AND**, **OR**, **NOT** e **NEAR.**</span><span class="sxs-lookup"><span data-stu-id="bf7af-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="bf7af-113">Se si è certi che i percorsi di contenuto o gli elementi contengano caratteri CJK, ma le ricerche non restituiscono risultati, fare clic sull'icona lingua-paese/area geografica della query</span><span class="sxs-lookup"><span data-stu-id="bf7af-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Icona lingua-paese/area geografica della query in Ricerca contenuto](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="bf7af-115">e selezionare il valore del codice lingua-paese corrispondente per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bf7af-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="bf7af-116">La lingua/area geografica predefinita è neutrale.</span><span class="sxs-lookup"><span data-stu-id="bf7af-116">The default language/region is neutral.</span></span>

<span data-ttu-id="bf7af-117">**È possibile cercare più lingue contemporaneamente?**</span><span class="sxs-lookup"><span data-stu-id="bf7af-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="bf7af-118">Dipende dallo scenario di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bf7af-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="bf7af-119">Quando si [e interrogano i dati in un insieme](review-set-search.md) di recensioni in Advanced eDiscovery, è possibile cercare più lingue.</span><span class="sxs-lookup"><span data-stu-id="bf7af-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="bf7af-120">Quando [crei una ricerca per raccogliere dati,](create-search-to-collect-data.md)crea una ricerca separata per ogni lingua di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bf7af-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="bf7af-121">Se ad esempio si sta cercando un documento contenente sia il cinese che il coreano, selezionare il cinese per la prima query e il coreano per la seconda query.</span><span class="sxs-lookup"><span data-stu-id="bf7af-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="bf7af-122">**Non viene visualizzata l'icona lingua-paese/area geografica della query per selezionare una lingua per le query in un insieme da rivedere. Come è possibile specificare una lingua di query in una ricerca di set di recensioni?**</span><span class="sxs-lookup"><span data-stu-id="bf7af-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="bf7af-123">Per le query di revisione impostate, non è necessario specificare una lingua del documento.</span><span class="sxs-lookup"><span data-stu-id="bf7af-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="bf7af-124">Advanced eDiscovery rileva automaticamente le lingue dei documenti quando si aggiunge contenuto a un insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="bf7af-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="bf7af-125">Ciò consente di ottimizzare i risultati delle query in un insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="bf7af-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="bf7af-126">**È possibile visualizzare le lingue rilevate nei [metadati dei file?](view-documents-in-review-set.md#file-metadata)**</span><span class="sxs-lookup"><span data-stu-id="bf7af-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="bf7af-127">No, non è possibile visualizzare le lingue rilevate nei metadati dei file.</span><span class="sxs-lookup"><span data-stu-id="bf7af-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="bf7af-128">**È possibile filtrare in base alle lingue dei documenti in un insieme da rivedere?**</span><span class="sxs-lookup"><span data-stu-id="bf7af-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="bf7af-129">No, non è possibile filtrare, ordinare o cercare in base alle lingue dei documenti in un insieme di revisioni.</span><span class="sxs-lookup"><span data-stu-id="bf7af-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="bf7af-130">**Questa versione di CJK per gli scenari impostati per la revisione influirà su una delle ricerche e dei set di revisioni esistenti?**</span><span class="sxs-lookup"><span data-stu-id="bf7af-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="bf7af-131">No, nessuna delle ricerche e dei set di revisioni esistenti cambierà.</span><span class="sxs-lookup"><span data-stu-id="bf7af-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="bf7af-132">Non è necessario reindicizzare i dati esistenti e i risultati della ricerca per il testo in inglese saranno gli stessi.</span><span class="sxs-lookup"><span data-stu-id="bf7af-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="bf7af-133">**Come modificare la lingua di visualizzazione in cinese, giapponese o coreano**</span><span class="sxs-lookup"><span data-stu-id="bf7af-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="bf7af-134">Per informazioni su come modificare la lingua di visualizzazione e il fuso orario, vedere Come impostare le impostazioni di lingua [e area geografica per Office 365.](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)</span><span class="sxs-lookup"><span data-stu-id="bf7af-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="bf7af-135">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="bf7af-135">Known issues</span></span>

- <span data-ttu-id="bf7af-136">L'OCR non supporta i caratteri CJK dai file di immagine</span><span class="sxs-lookup"><span data-stu-id="bf7af-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="bf7af-137">I file di posta elettronica (ad esempio \*.eml e \*.msg) nella visualizzazione [Annotate](view-documents-in-review-set.md#annotate-view) non sono supportati per i linguaggi CJK.</span><span class="sxs-lookup"><span data-stu-id="bf7af-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="bf7af-138">L'evidenziazione dei risultati della ricerca [nella](view-documents-in-review-set.md#text-view) visualizzazione Testo non è supportata per i linguaggi CJK.</span><span class="sxs-lookup"><span data-stu-id="bf7af-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="bf7af-139">Il [modulo Pertinenza](using-relevance.md) utilizzato per analizzare i dati non supporta i linguaggi CJK.</span><span class="sxs-lookup"><span data-stu-id="bf7af-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="bf7af-140">[Le esenzioni basate su](managing-holds.md#manage-non-custodial-holds) query non sono supportate per i linguaggi CJK.</span><span class="sxs-lookup"><span data-stu-id="bf7af-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
