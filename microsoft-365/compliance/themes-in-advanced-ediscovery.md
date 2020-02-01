---
title: Temi
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
ms.openlocfilehash: 4387c5e8fc199f0f8642041473d5f28f2f9b401b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601383"
---
# <a name="themes"></a><span data-ttu-id="9f638-102">Temi</span><span class="sxs-lookup"><span data-stu-id="9f638-102">Themes</span></span>

<span data-ttu-id="9f638-103">In che modo una persona scrive un documento?</span><span class="sxs-lookup"><span data-stu-id="9f638-103">How does a person write a document?</span></span> <span data-ttu-id="9f638-104">In genere iniziano con una o più idee che vogliono trasmettere nel documento e compongono l'utilizzo di parole che si allineano con le idee.</span><span class="sxs-lookup"><span data-stu-id="9f638-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="9f638-105">Più è prevalente un'idea, più le parole che sono correlate a quell'idea tendono ad essere.</span><span class="sxs-lookup"><span data-stu-id="9f638-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="9f638-106">In questo modo si informa come gli utenti utilizzano i documenti.</span><span class="sxs-lookup"><span data-stu-id="9f638-106">This informs how people consume documents as well.</span></span> <span data-ttu-id="9f638-107">La cosa importante da capire dalla lettura di un documento è l'idea che il documento sta cercando di trasmettere, quali sono le idee in cui vengono visualizzate e quali sono le relazioni tra le idee.</span><span class="sxs-lookup"><span data-stu-id="9f638-107">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="9f638-108">Questo può essere esteso a come una persona desidera utilizzare un insieme di documenti.</span><span class="sxs-lookup"><span data-stu-id="9f638-108">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="9f638-109">Desiderano vedere quali idee sono presenti nei set e quali documenti si riferiscono a queste idee.</span><span class="sxs-lookup"><span data-stu-id="9f638-109">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="9f638-110">Inoltre, se trovano un particolare documento di interesse, vogliono essere in grado di visualizzare i documenti che discutono di idee simili.</span><span class="sxs-lookup"><span data-stu-id="9f638-110">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="9f638-111">La funzionalità temi in Advanced eDiscovery tenta di simulare il modo in cui gli umani ragionano sui documenti, analizzando i *temi* discussi in un set di revisione e assegnando un tema ai documenti nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="9f638-111">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="9f638-112">In Advanced eDiscovery, i temi fanno un ulteriore passo avanti e identificano il *tema dominante* in ciascun documento.</span><span class="sxs-lookup"><span data-stu-id="9f638-112">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="9f638-113">Il tema dominante è quello che viene visualizzato più spesso in un documento.</span><span class="sxs-lookup"><span data-stu-id="9f638-113">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="9f638-114">Modalità di funzionamento dei temi</span><span class="sxs-lookup"><span data-stu-id="9f638-114">How does Themes work?</span></span>

<span data-ttu-id="9f638-115">La funzionalità temi analizza i documenti con testo in un set di revisione per analizzare i temi comuni visualizzati in tutti i documenti del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="9f638-115">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="9f638-116">Advanced eDiscovery assegna tali temi ai documenti in cui vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="9f638-116">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="9f638-117">Contrassegna inoltre ogni tema con le parole utilizzate nei documenti rappresentativi del tema.</span><span class="sxs-lookup"><span data-stu-id="9f638-117">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="9f638-118">Poiché un documento può contenere diversi tipi di argomenti, Advanced eDiscovery spesso assegna più temi ai documenti.</span><span class="sxs-lookup"><span data-stu-id="9f638-118">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="9f638-119">Il tema più prominente in un documento è designato come tema dominante.</span><span class="sxs-lookup"><span data-stu-id="9f638-119">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>