---
title: Supporto di CJK/Double byte per Advanced eDiscovery
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
description: Informazioni su come Advanced eDiscovery in Microsoft 365 supporta lingue cinesi, giapponesi e coreane (CJK), che utilizzano un set di caratteri a doppio byte.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626936"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a><span data-ttu-id="e23bb-103">Supporto per la lingua CJK per Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e23bb-103">CJK language support for Advanced eDiscovery</span></span>

<span data-ttu-id="e23bb-104">Advanced eDiscovery supporta le lingue con set di caratteri a doppio byte, tra cui il cinese semplificato, il cinese tradizionale, il giapponese e il coreano, noti collettivamente come lingue *CJK* , per i seguenti scenari avanzati in un set di riesame:</span><span class="sxs-lookup"><span data-stu-id="e23bb-104">Advanced eDiscovery supports double-byte character set languages (these include Simplified Chinese, Traditional Chinese, Japanese, and Korean, which are collectively known as *CJK* languages) for the following advanced scenarios in a review set:</span></span>

- <span data-ttu-id="e23bb-105">Quando si [esegue la query dei dati in un set di revisione](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="e23bb-105">When you [query the data in a review set](review-set-search.md).</span></span>

- <span data-ttu-id="e23bb-106">Quando si [contrassegnano i documenti in un set di revisione](tagging-documents.md).</span><span class="sxs-lookup"><span data-stu-id="e23bb-106">When you [tag documents in a review set](tagging-documents.md).</span></span>

- <span data-ttu-id="e23bb-107">Quando si [analizzano i dati del caso in un set di revisione](analyzing-data-in-review-set.md) , è possibile utilizzare la funzionalità di rilevamento duplicati, Threading di posta elettronica e analisi dei temi</span><span class="sxs-lookup"><span data-stu-id="e23bb-107">When you [analyze case data in a review set](analyzing-data-in-review-set.md) by using near duplicate detection, email threading, and themes analytics.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="e23bb-108">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="e23bb-108">Frequently asked questions</span></span>

<span data-ttu-id="e23bb-109">**Come creare una ricerca per raccogliere gli elementi che contengono caratteri CJK.**</span><span class="sxs-lookup"><span data-stu-id="e23bb-109">**How do I create a search to collect items that contains CJK characters?**</span></span>

<span data-ttu-id="e23bb-110">È possibile utilizzare i caratteri CJK per le [ricerche di parole chiave](building-search-queries.md#keyword-searches), [le query con parole chiave e le condizioni di ricerca](keyword-queries-and-search-conditions.md) durante la ricerca di contenuto in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="e23bb-110">You can use CJK characters for [keyword searches](building-search-queries.md#keyword-searches), [keyword queries and search conditions](keyword-queries-and-search-conditions.md) when searching for content in Advanced eDiscovery.</span></span> <span data-ttu-id="e23bb-111">La ricerca di caratteri CJK è supportata anche durante la ricerca di contenuto in eDiscovery di base e ricerca contenuto.</span><span class="sxs-lookup"><span data-stu-id="e23bb-111">Searching for CJK characters is also supported when searching for content in Core eDiscovery and Content Search.</span></span>

<span data-ttu-id="e23bb-112">Viene fornito il supporto CJK per tutti [gli operatori di ricerca](keyword-queries-and-search-conditions.md#search-operators) e le [condizioni di ricerca](keyword-queries-and-search-conditions.md#search-conditions), compresi gli operatori booleani **e**, **o**, **non**e **vicino**.</span><span class="sxs-lookup"><span data-stu-id="e23bb-112">We provide CJK support for all [search operators](keyword-queries-and-search-conditions.md#search-operators) and [search conditions](keyword-queries-and-search-conditions.md#search-conditions), including the boolean operators **AND**, **OR**, **NOT**, and **NEAR**.</span></span>

<span data-ttu-id="e23bb-113">Se si è certi che i percorsi o gli elementi di contenuto contengano caratteri CJK, ma le ricerche non restituiscono alcun risultato, fare clic sull'icona lingua query-paese/area geografica</span><span class="sxs-lookup"><span data-stu-id="e23bb-113">If you're certain that content locations or items contain CJK characters, but searches aren't returning any results, click the query language-country/region icon</span></span> ![Lingua query-icona paese/area geografica nella ricerca contenuto](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) <span data-ttu-id="e23bb-115">e seleziona il valore del codice corrispondente alla lingua per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e23bb-115">and select the corresponding language-country culture code value for the search.</span></span> <span data-ttu-id="e23bb-116">La lingua/area geografica predefinita è neutrale.</span><span class="sxs-lookup"><span data-stu-id="e23bb-116">The default language/region is neutral.</span></span>

<span data-ttu-id="e23bb-117">**È possibile eseguire la ricerca di più lingue contemporaneamente?**</span><span class="sxs-lookup"><span data-stu-id="e23bb-117">**Can I search for multiple languages at once?**</span></span>

<span data-ttu-id="e23bb-118">Dipende dallo scenario di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e23bb-118">It depends on your search scenario.</span></span>

- <span data-ttu-id="e23bb-119">Quando si [esegue una query di dati in un set di revisione](review-set-search.md) in Advanced eDiscovery, è possibile eseguire la ricerca di più lingue.</span><span class="sxs-lookup"><span data-stu-id="e23bb-119">When you [query data in a review set](review-set-search.md) in Advanced eDiscovery, you can search for multiple languages.</span></span>

- <span data-ttu-id="e23bb-120">Quando si [Crea una ricerca per raccogliere dati](create-search-to-collect-data.md), creare una ricerca distinta per ogni lingua che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e23bb-120">When you [create a search to collect data](create-search-to-collect-data.md), create a separate search for each language you're targeting.</span></span> <span data-ttu-id="e23bb-121">Ad esempio, se si esegue la ricerca di un documento contenente sia cinese che coreano, selezionare cinese per la prima query e selezionare coreano per la seconda query.</span><span class="sxs-lookup"><span data-stu-id="e23bb-121">For example, if you are searching for a document that contains both Chinese and Korean, select Chinese for your first query and select Korean for your second query.</span></span>

<span data-ttu-id="e23bb-122">**Non viene visualizzata l'icona lingua query-paese/area geografica per selezionare una lingua per le query in un set di revisione. In che modo è possibile specificare una lingua di query in una ricerca set di Revisione?**</span><span class="sxs-lookup"><span data-stu-id="e23bb-122">**I don't see the query language-country/region icon to select a language for queries in a review set. How can I specify a query language in a review set search?**</span></span>

<span data-ttu-id="e23bb-123">Per le query dei set di revisione, non è necessario specificare una lingua del documento.</span><span class="sxs-lookup"><span data-stu-id="e23bb-123">For review set queries, you don't need to specify a document language.</span></span> <span data-ttu-id="e23bb-124">Advanced eDiscovery rileva automaticamente le lingue del documento quando si aggiunge contenuto a un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="e23bb-124">Advanced eDiscovery automatically detects document languages when you add content to a review set.</span></span> <span data-ttu-id="e23bb-125">In questo modo è possibile ottimizzare i risultati delle query in un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="e23bb-125">This helps you optimize your query results in a review set.</span></span>

<span data-ttu-id="e23bb-126">**È possibile visualizzare le lingue rilevate nei [metadati dei file](view-documents-in-review-set.md#file-metadata)?**</span><span class="sxs-lookup"><span data-stu-id="e23bb-126">**Can I see detected languages in [file metadata](view-documents-in-review-set.md#file-metadata)?**</span></span>

<span data-ttu-id="e23bb-127">No, non è possibile visualizzare le lingue rilevate nei metadati dei file.</span><span class="sxs-lookup"><span data-stu-id="e23bb-127">No, you can't see detected languages in file metadata.</span></span>

<span data-ttu-id="e23bb-128">È **possibile filtrare in base alle lingue dei documenti in un set di revisione**?</span><span class="sxs-lookup"><span data-stu-id="e23bb-128">**Can I filter by document languages in a review set**?</span></span>

<span data-ttu-id="e23bb-129">No, non è possibile filtrare, ordinare o cercare in base alle lingue dei documenti in un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="e23bb-129">No, you can't filter, sort, or search by document languages in a review set.</span></span>

<span data-ttu-id="e23bb-130">**La versione CJK per gli scenari del set di revisione influirà sulle ricerche e sui set di revisione esistenti?**</span><span class="sxs-lookup"><span data-stu-id="e23bb-130">**Will this CJK release for review set scenarios affect any of my existing searches and review sets?**</span></span>

<span data-ttu-id="e23bb-131">No, non verranno modificate le ricerche esistenti e i set di revisione.</span><span class="sxs-lookup"><span data-stu-id="e23bb-131">No, none of your existing searches and review sets will change.</span></span> <span data-ttu-id="e23bb-132">Non è necessario reindicizzare i dati esistenti e i risultati della ricerca per il testo in inglese saranno gli stessi.</span><span class="sxs-lookup"><span data-stu-id="e23bb-132">You don't need to reindex existing data, and search results for English text will be the same.</span></span>

<span data-ttu-id="e23bb-133">**Come si modifica la lingua di visualizzazione in cinese, giapponese o coreano?**</span><span class="sxs-lookup"><span data-stu-id="e23bb-133">**How do I change my display language to Chinese, Japanese, or Korean?**</span></span>

<span data-ttu-id="e23bb-134">Per informazioni su come modificare la lingua e il fuso orario di visualizzazione, vedere [How to set Language and Region Settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span><span class="sxs-lookup"><span data-stu-id="e23bb-134">For information about how to change display language and time zone, see [How to set language and region settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).</span></span>

## <a name="known-issues"></a><span data-ttu-id="e23bb-135">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="e23bb-135">Known issues</span></span>

- <span data-ttu-id="e23bb-136">OCR non supporta i caratteri CJK dai file di immagine</span><span class="sxs-lookup"><span data-stu-id="e23bb-136">OCR doesn't support CJK characters from image files</span></span>

- <span data-ttu-id="e23bb-137">I file di posta elettronica (ad esempio, \*. eml e \*. msg) in [Visualizzazione annotazioni](view-documents-in-review-set.md#annotate-view) non sono supportati per le lingue CJK.</span><span class="sxs-lookup"><span data-stu-id="e23bb-137">Email files (such as \*.eml and \*.msg) in [Annotate view](view-documents-in-review-set.md#annotate-view) aren't supported for CJK languages.</span></span>

- <span data-ttu-id="e23bb-138">La ricerca hit highlighting nella [visualizzazione testo](view-documents-in-review-set.md#text-view) non è supportata per le lingue CJK.</span><span class="sxs-lookup"><span data-stu-id="e23bb-138">Search hit highlighting in [Text view](view-documents-in-review-set.md#text-view) isn't supported for CJK languages.</span></span>

- <span data-ttu-id="e23bb-139">Il [modulo di pertinenza](using-relevance.md) utilizzato per l'analisi dei dati non supporta le lingue CJK.</span><span class="sxs-lookup"><span data-stu-id="e23bb-139">The [Relevance module](using-relevance.md) used to analyze data doesn't support CJK languages.</span></span>

- <span data-ttu-id="e23bb-140">Le [esenzioni basate su query](managing-holds.md#manage-non-custodial-holds) non sono supportate per le lingue CJK.</span><span class="sxs-lookup"><span data-stu-id="e23bb-140">[Query-based holds](managing-holds.md#manage-non-custodial-holds) aren't supported for CJK languages.</span></span> 
