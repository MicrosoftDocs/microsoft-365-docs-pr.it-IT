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
description: ''
ms.openlocfilehash: 4b740b07b59b7500b8f57584767796b7f31ae87d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635976"
---
# <a name="create-a-search"></a><span data-ttu-id="270d4-102">Creare una ricerca</span><span class="sxs-lookup"><span data-stu-id="270d4-102">Create a search</span></span>

<span data-ttu-id="270d4-103">Nella scheda **ricerche** del caso, è possibile creare una nuova ricerca facendo clic su **nuova ricerca** e seguendo la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="270d4-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![La procedura guidata di ricerca in un caso avanzato di eDiscovery](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="270d4-105">Denominare la ricerca e assegnarle una descrizione</span><span class="sxs-lookup"><span data-stu-id="270d4-105">Name the search and give it a description</span></span>

<span data-ttu-id="270d4-106">Ogni ricerca con un caso deve avere un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="270d4-106">Each search with a case should have a unique name.</span></span> <span data-ttu-id="270d4-107">Facoltativamente, è possibile fornire una descrizione per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="270d4-107">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="270d4-108">Scegliere i depositari e le posizioni di custodia per la ricerca</span><span class="sxs-lookup"><span data-stu-id="270d4-108">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="270d4-109">Scegliere posizioni di contenuto custode per la ricerca specificando i depositari che sono stati aggiunti al caso.</span><span class="sxs-lookup"><span data-stu-id="270d4-109">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="270d4-110">Selezionando un custode, verrà eseguita la ricerca in tutte le origini dati mappate al custode.</span><span class="sxs-lookup"><span data-stu-id="270d4-110">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="270d4-111">È inoltre possibile limitare la ricerca a origini dati selezionate per ogni custode.</span><span class="sxs-lookup"><span data-stu-id="270d4-111">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="270d4-112">Per ulteriori informazioni su come aggiungere depositari e gestire le origini dati, vedere [lavorare con i depositari](managing-custodians.md).</span><span class="sxs-lookup"><span data-stu-id="270d4-112">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="270d4-113">Scegliere le posizioni non detentive</span><span class="sxs-lookup"><span data-stu-id="270d4-113">Choose non-custodial locations</span></span>

<span data-ttu-id="270d4-114">In alcuni casi, è possibile che si desideri cercare origini dati che non sono associate a un custode.</span><span class="sxs-lookup"><span data-stu-id="270d4-114">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="270d4-115">In questo caso, è possibile specificare i percorsi che si desidera ricercare oppure scegliere di cercare tutti i percorsi di contenuto per uno specifico servizio Microsoft, ad esempio la ricerca in tutte le cassette postali di Exchange o di tutti i siti di SharePoint e gli account di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="270d4-115">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Microsoft service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="270d4-116">Definire la query di ricerca e le condizioni</span><span class="sxs-lookup"><span data-stu-id="270d4-116">Define the search query and conditions</span></span>

<span data-ttu-id="270d4-117">È possibile definire la query di parole chiave e tutte le condizioni per la ricerca utilizzando le schede delle condizioni predefinite o utilizzando KQL (Keyword Query Language).</span><span class="sxs-lookup"><span data-stu-id="270d4-117">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="270d4-118">Per ulteriori informazioni, vedere [creazione di query di ricerca](building-search-queries.md).</span><span class="sxs-lookup"><span data-stu-id="270d4-118">For more information, see [Build search queries](building-search-queries.md).</span></span>
