---
title: Temi
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
ms.openlocfilehash: b26b031b767f23504294880f4424be5042350c71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084750"
---
# <a name="themes"></a><span data-ttu-id="36a50-102">Temi</span><span class="sxs-lookup"><span data-stu-id="36a50-102">Themes</span></span>
<span data-ttu-id="36a50-103">In che modo una persona scrive un documento?</span><span class="sxs-lookup"><span data-stu-id="36a50-103">How does a person write a document?</span></span> <span data-ttu-id="36a50-104">In genere iniziano con una o più idee che vogliono trasmettere nel documento e compongono l'utilizzo di parole che si allineano con le idee.</span><span class="sxs-lookup"><span data-stu-id="36a50-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="36a50-105">Più è prevalente un'idea, più le parole che sono correlate a quell'idea tendono ad essere.</span><span class="sxs-lookup"><span data-stu-id="36a50-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="36a50-106">In questo modo viene spiegato come gli utenti utilizzano i documenti. la cosa importante da leggere è la lettura di un documento e le idee che il documento sta cercando di trasmettere e quali idee vengono visualizzate e quali sono le relazioni tra le idee.</span><span class="sxs-lookup"><span data-stu-id="36a50-106">This informs how people consume documents as well; the important thing to get from reading a document is the ideas that the document is trying to convey, and which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="36a50-107">Questo può essere esteso a come una persona desidera utilizzare un insieme di documenti.</span><span class="sxs-lookup"><span data-stu-id="36a50-107">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="36a50-108">Desiderano vedere quali idee sono presenti nei set e quali documenti si riferiscono a queste idee.</span><span class="sxs-lookup"><span data-stu-id="36a50-108">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="36a50-109">Inoltre, se trovano un particolare documento di interesse, vogliono essere in grado di visualizzare i documenti che discutono di idee simili.</span><span class="sxs-lookup"><span data-stu-id="36a50-109">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="36a50-110">Il modulo themes cerca di simulare il modo in cui gli umani ragionano sui documenti, analizzando i "temi" descritti in un set di revisione e assegnando loro i documenti.</span><span class="sxs-lookup"><span data-stu-id="36a50-110">Themes module tries to mimic how humans reason about documents, by analyzing the "themes" that are discussed in a review set and assigning them to documents.</span></span> <span data-ttu-id="36a50-111">I temi fanno un ulteriore passo e identifica per documento il "tema dominante"; vale a dire il tema più visualizzato.</span><span class="sxs-lookup"><span data-stu-id="36a50-111">Themes goes one step further and identifies per document the "dominant theme"; i.e. the theme that appears the most.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="36a50-112">Modalità di funzionamento dei temi</span><span class="sxs-lookup"><span data-stu-id="36a50-112">How does Themes work?</span></span>
<span data-ttu-id="36a50-113">Themes analizza i documenti con testo in un set di revisione per analizzare i temi comuni che vengono visualizzati tra i documenti.</span><span class="sxs-lookup"><span data-stu-id="36a50-113">Themes analyzes documents with text in a review set to parse out common themes that appear accross the documents.</span></span> <span data-ttu-id="36a50-114">Assegna quindi tali temi ai documenti in cui vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="36a50-114">Then, it assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="36a50-115">Le etichette vengono inoltre contrassegnate con le parole utilizzate nei documenti rappresentativi del tema.</span><span class="sxs-lookup"><span data-stu-id="36a50-115">It also labels each with words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="36a50-116">Poiché un documento può avere più di un argomento, in molti casi a un documento sono assegnati più temi.</span><span class="sxs-lookup"><span data-stu-id="36a50-116">Since a document can be about more than one subject matter, in many cases a document has more than one themes assigned to it.</span></span> <span data-ttu-id="36a50-117">Il tema più prominente in un documento è designato come tema dominante.</span><span class="sxs-lookup"><span data-stu-id="36a50-117">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>