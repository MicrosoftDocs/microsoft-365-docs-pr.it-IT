---
title: Creare una ricerca
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
description: Informazioni su come creare, definire e scegliere i custodi e le posizioni di custodia per una ricerca in Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035768"
---
# <a name="create-a-search"></a><span data-ttu-id="2bf4f-103">Creare una ricerca</span><span class="sxs-lookup"><span data-stu-id="2bf4f-103">Create a search</span></span>

<span data-ttu-id="2bf4f-104">Nella scheda **Ricerche** del caso, è possibile creare una nuova ricerca facendo clic su **Nuova ricerca** e seguendo la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2bf4f-104">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![Ricerca guidata in un Advanced eDiscovery caso](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="2bf4f-106">Assegnare un nome alla ricerca e assegnargli una descrizione</span><span class="sxs-lookup"><span data-stu-id="2bf4f-106">Name the search and give it a description</span></span>

<span data-ttu-id="2bf4f-107">Ogni ricerca con un caso deve avere un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="2bf4f-107">Each search with a case should have a unique name.</span></span> <span data-ttu-id="2bf4f-108">Facoltativamente, è possibile fornire una descrizione per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2bf4f-108">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="2bf4f-109">Scegliere i custodi e i percorsi di custodia in cui eseguire la ricerca</span><span class="sxs-lookup"><span data-stu-id="2bf4f-109">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="2bf4f-110">Scegliere i percorsi del contenuto di archiviazione in cui eseguire la ricerca specificando che i custodi sono stati aggiunti al caso.</span><span class="sxs-lookup"><span data-stu-id="2bf4f-110">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="2bf4f-111">Selezionando un responsabile, la ricerca verrà eseguita su tutte le origini dati mappate al responsabile.</span><span class="sxs-lookup"><span data-stu-id="2bf4f-111">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="2bf4f-112">È inoltre possibile limitare la ricerca alle origini dati selezionate per ogni responsabile.</span><span class="sxs-lookup"><span data-stu-id="2bf4f-112">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="2bf4f-113">Per ulteriori informazioni su come aggiungere i custodi e gestire le rispettive origini dati, vedere [Utilizzare i custodi.](managing-custodians.md)</span><span class="sxs-lookup"><span data-stu-id="2bf4f-113">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="2bf4f-114">Scegliere posizioni non di custodia</span><span class="sxs-lookup"><span data-stu-id="2bf4f-114">Choose non-custodial locations</span></span>

<span data-ttu-id="2bf4f-115">In alcuni casi, potrebbe essere necessario cercare origini dati non associate a un responsabile.</span><span class="sxs-lookup"><span data-stu-id="2bf4f-115">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="2bf4f-116">In questo caso, è possibile specificare i percorsi in cui si desidera eseguire la ricerca oppure scegliere di cercare in tutti i percorsi di contenuto uno specifico servizio Microsoft , ad esempio tutte le cassette postali di Exchange o tutti i siti di SharePoint e gli account OneDrive).</span><span class="sxs-lookup"><span data-stu-id="2bf4f-116">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Microsoft service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="2bf4f-117">Definire la query e le condizioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="2bf4f-117">Define the search query and conditions</span></span>

<span data-ttu-id="2bf4f-118">È possibile definire la query delle parole chiave e qualsiasi condizione per la ricerca utilizzando le schede delle condizioni predefinite o il linguaggio KQL (Keyword Query Language).</span><span class="sxs-lookup"><span data-stu-id="2bf4f-118">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="2bf4f-119">Per ulteriori informazioni, vedere [Creare query di ricerca.](building-search-queries.md)</span><span class="sxs-lookup"><span data-stu-id="2bf4f-119">For more information, see [Build search queries](building-search-queries.md).</span></span>
