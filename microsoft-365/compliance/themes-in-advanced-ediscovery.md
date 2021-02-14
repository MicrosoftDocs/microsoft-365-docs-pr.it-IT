---
title: Temi - eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Utilizzare Temi in Advanced eDiscovery per organizzare i set di revisioni individuando il tema dominante in ogni documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285532"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="4f87f-103">Temi in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4f87f-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="4f87f-104">In che modo una persona scrive un documento?</span><span class="sxs-lookup"><span data-stu-id="4f87f-104">How does a person write a document?</span></span> <span data-ttu-id="4f87f-105">In genere iniziano con una o più idee che vogliono trasmettere nel documento e mettono parole in linea con le idee.</span><span class="sxs-lookup"><span data-stu-id="4f87f-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="4f87f-106">L'idea più diffusa è che più frequenti sono le parole correlate a tale idea.</span><span class="sxs-lookup"><span data-stu-id="4f87f-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="4f87f-107">In questo modo si informa anche il modo in cui gli utenti utilizzano i documenti.</span><span class="sxs-lookup"><span data-stu-id="4f87f-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="4f87f-108">La cosa importante da comprendere durante la lettura di un documento sono le idee che il documento sta cercando di trasmettere, quali idee appaiono dove e quali sono le relazioni tra le idee.</span><span class="sxs-lookup"><span data-stu-id="4f87f-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="4f87f-109">Questo può essere esteso al modo in cui un utente vuole usare un set di documenti.</span><span class="sxs-lookup"><span data-stu-id="4f87f-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="4f87f-110">Vogliono vedere quali idee sono presenti nei set e quali documenti parlano di tali idee.</span><span class="sxs-lookup"><span data-stu-id="4f87f-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="4f87f-111">Inoltre, se trovano un particolare documento di interesse, desiderano essere in grado di visualizzare documenti che discutono di idee simili.</span><span class="sxs-lookup"><span data-stu-id="4f87f-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="4f87f-112">La funzionalità Temi di Advanced eDiscovery tenta di simulare il  modo in cui l'utente fa ragione sui documenti, analizzando i temi descritti in un insieme da rivedere e assegnando un tema ai documenti nell'insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="4f87f-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="4f87f-113">In Advanced eDiscovery, i temi vanno oltre e identificano il *tema dominante* in ogni documento.</span><span class="sxs-lookup"><span data-stu-id="4f87f-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="4f87f-114">Il tema dominante è quello che viene visualizzato più spesso in un documento.</span><span class="sxs-lookup"><span data-stu-id="4f87f-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="4f87f-115">Come funzionano i temi?</span><span class="sxs-lookup"><span data-stu-id="4f87f-115">How does Themes work?</span></span>

<span data-ttu-id="4f87f-116">La funzionalità Temi analizza i documenti con il testo in un insieme da rivedere per analizzare i temi comuni che vengono visualizzati in tutti i documenti del set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="4f87f-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="4f87f-117">Advanced eDiscovery assegna tali temi ai documenti in cui vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="4f87f-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="4f87f-118">Inoltre, ogni tema viene etichettato con le parole utilizzate nei documenti che sono rappresentative del tema.</span><span class="sxs-lookup"><span data-stu-id="4f87f-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="4f87f-119">Poiché un documento può contenere vari tipi di materia, Advanced eDiscovery spesso assegna più temi ai documenti.</span><span class="sxs-lookup"><span data-stu-id="4f87f-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="4f87f-120">Il tema che viene visualizzato in modo più evidente in un documento viene designato come tema dominante.</span><span class="sxs-lookup"><span data-stu-id="4f87f-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
