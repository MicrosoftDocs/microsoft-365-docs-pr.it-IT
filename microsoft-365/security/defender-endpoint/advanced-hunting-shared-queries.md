---
title: Usare le query condivise nella ricerca avanzata
description: Avviare subito la ricerca delle minacce con query predefinite e condivise. Condividere le query con il pubblico o la propria organizzazione.
keywords: ricerca avanzata, ricerca di minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, rilevamenti personalizzati, schema, kusto, repository github, query, query condivise
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 78a532167e4256e3453803f1a0b4a9e4875771cf
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499429"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="b4958-105">Usare le query condivise nella ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="b4958-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b4958-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b4958-106">**Applies to:**</span></span>
- [<span data-ttu-id="b4958-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b4958-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="b4958-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b4958-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b4958-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b4958-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="b4958-110">[Le query Ricerca avanzata](advanced-hunting-overview.md) possono essere condivise tra con gli utenti della stessa organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b4958-110">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="b4958-111">È anche possibile trovare query condivise pubblicamente su GitHub.</span><span class="sxs-lookup"><span data-stu-id="b4958-111">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="b4958-112">Queste query consentono di intraprendere rapidamente specifici scenari di ricerca delle minacce senza dover scrivere le query da zero.</span><span class="sxs-lookup"><span data-stu-id="b4958-112">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Immagine di query condivise](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="b4958-114">Salvare, modificare e condividere una query</span><span class="sxs-lookup"><span data-stu-id="b4958-114">Save, modify, and share a query</span></span>
<span data-ttu-id="b4958-115">È possibile salvare una query nuova o esistente in modo che sia solo accessibile all'utente o condivisa con altri utenti della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b4958-115">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span>

1. <span data-ttu-id="b4958-116">Digitare una nuova query o caricarne una esistente in **Query condivise** o **Query personalizzate**.</span><span class="sxs-lookup"><span data-stu-id="b4958-116">Type a new query or load an existing one from under **Shared queries** or **My queries**.</span></span>

2. <span data-ttu-id="b4958-117">Selezionare **Salva** o **Salva con nome** dalle opzioni di salvataggio.</span><span class="sxs-lookup"><span data-stu-id="b4958-117">Select **Save** or **Save as** from the save options.</span></span> <span data-ttu-id="b4958-118">Per evitare di sovrascrivere una query esistente, scegliere **Salva con nome.**</span><span class="sxs-lookup"><span data-stu-id="b4958-118">To avoid overwriting an existing query, choose **Save as**.</span></span>

3. <span data-ttu-id="b4958-119">Immettere un nome per la query.</span><span class="sxs-lookup"><span data-stu-id="b4958-119">Enter a name for the query.</span></span>

   ![Immagine del salvataggio di una query](images/advanced-hunting-save-query.png)

4. <span data-ttu-id="b4958-121">Selezionare la cartella in cui si vuole salvare la query.</span><span class="sxs-lookup"><span data-stu-id="b4958-121">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="b4958-122">**Query condivise,** condivise con tutti gli utenti dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="b4958-122">**Shared queries** — shared to all users in your organization</span></span>
    - <span data-ttu-id="b4958-123">**Query personali**: query accessibili solo all'utente</span><span class="sxs-lookup"><span data-stu-id="b4958-123">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="b4958-124">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b4958-124">Select **Save**.</span></span>

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="b4958-125">Eliminare o rinominare una query</span><span class="sxs-lookup"><span data-stu-id="b4958-125">Delete or rename a query</span></span>
1. <span data-ttu-id="b4958-126">Fare clic con il pulsante destro del mouse su una query che si vuole rinominare o eliminare.</span><span class="sxs-lookup"><span data-stu-id="b4958-126">Right-click on a query you want to rename or delete.</span></span>

    ![Immagine dell'eliminazione di una query](images/atp_advanced_hunting_delete_rename.png)

2. <span data-ttu-id="b4958-128">Selezionare **Elimina** per confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="b4958-128">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="b4958-129">In alternativa, selezionare **Rinomina** e immettere un nuovo nome per la query.</span><span class="sxs-lookup"><span data-stu-id="b4958-129">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="b4958-130">Creare un collegamento diretto a una query</span><span class="sxs-lookup"><span data-stu-id="b4958-130">Create a direct link to a query</span></span>
<span data-ttu-id="b4958-131">Per generare un collegamento che apre la query direttamente nell'editor di query di ricerca avanzata, finalizzare la query e selezionare **Condividi collegamento.**</span><span class="sxs-lookup"><span data-stu-id="b4958-131">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="b4958-132">Accedere alle query nel repository GitHub</span><span class="sxs-lookup"><span data-stu-id="b4958-132">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="b4958-133">I ricercatori della sicurezza Microsoft condividono regolarmente query di ricerca avanzata in un [repository pubblico designato in GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span><span class="sxs-lookup"><span data-stu-id="b4958-133">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span> <span data-ttu-id="b4958-134">È possibile collaborare a questo repository.</span><span class="sxs-lookup"><span data-stu-id="b4958-134">This repository is open to contributions.</span></span> <span data-ttu-id="b4958-135">Per collaborare, [iscriversi a GitHub gratuitamente](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="b4958-135">To contribute, [join GitHub for free](https://github.com/).</span></span> 

>[!TIP]
><span data-ttu-id="b4958-136">I ricercatori della sicurezza Microsoft forniscono anche query di ricerca avanzata che è possibile usare per trovare le attività e gli indicatori associati alle minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="b4958-136">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="b4958-137">Queste query sono incluse nei report di [analisi delle minacce](threat-analytics.md) nel Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="b4958-137">These queries are provided as part of the [threat analytics](threat-analytics.md) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b4958-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b4958-138">Related topics</span></span>
- [<span data-ttu-id="b4958-139">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="b4958-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b4958-140">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="b4958-140">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b4958-141">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="b4958-141">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="b4958-142">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="b4958-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="b4958-143">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="b4958-143">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b4958-144">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="b4958-144">Custom detections overview</span></span>](overview-custom-detections.md)
