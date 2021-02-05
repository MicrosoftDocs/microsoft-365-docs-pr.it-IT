---
title: Limitazione per motivi di sicurezza di Microsoft Viva Topics
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Panoramica del modo in cui viene utilizzata la sicurezza per visualizzare gli argomenti.
ms.openlocfilehash: fc8e2a08fcf9af266aee49eee878738f7f17aa59
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107519"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="4ec66-103">Limitazione per motivi di sicurezza di Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="4ec66-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="4ec66-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span><span class="sxs-lookup"><span data-stu-id="4ec66-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="4ec66-105">Tutte le informazioni visualizzate da un utente in una pagina dell'argomento(ad esempio, siti di SharePoint, documenti, file) saranno informazioni che sono già autorizzate a visualizzare.</span><span class="sxs-lookup"><span data-stu-id="4ec66-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="4ec66-106">Viva Topics non apporta modifiche alle autorizzazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="4ec66-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="4ec66-107">Perché due utenti possono avere visualizzazioni diverse dello stesso argomento</span><span class="sxs-lookup"><span data-stu-id="4ec66-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="4ec66-108">Quando un argomento viene creato tramite IA o la gestione manuale, può contenere una descrizione dell'argomento, nomi alternativi, persone associate all'argomento, nonché siti, pagine e file correlati all'argomento.</span><span class="sxs-lookup"><span data-stu-id="4ec66-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="4ec66-109">Quando queste informazioni vengono visualizzate in una pagina dell'argomento, è possibile che due utenti che visualizzano lo stesso argomento non visualizzino le stesse informazioni.</span><span class="sxs-lookup"><span data-stu-id="4ec66-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="4ec66-110">Ad esempio, quando l'utente 1 visualizza la pagina dell'argomento Neptune, potrebbe vedere questa visualizzazione della pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="4ec66-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Argomento Nettuno per l'utente 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="4ec66-112">Tuttavia, quando l'utente 2 esamina la stessa pagina dell'argomento neptune, la visualizzazione è diversa dall'utente 1.</span><span class="sxs-lookup"><span data-stu-id="4ec66-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="4ec66-113">L'utente 2 è in grado di visualizzare il file *DG-2000 Product Overview* nella sezione **Pinned files and pages** della pagina dell'argomento, che non viene visualizzata per l'utente 1.</span><span class="sxs-lookup"><span data-stu-id="4ec66-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Argomento Neptune per l'utente 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="4ec66-115">La differenza tra ciò che gli utenti possono vedere nello stesso argomento è che gli utenti potrebbero non disporre delle autorizzazioni di Office 365 per visualizzare un sito o un file correlato.</span><span class="sxs-lookup"><span data-stu-id="4ec66-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="4ec66-116">Viva Topics rispetta le autorizzazioni impostate per gli elementi di un argomento e non può modificarli.</span><span class="sxs-lookup"><span data-stu-id="4ec66-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="4ec66-117">In questo esempio, l'utente 1 non è in grado di visualizzare il file *DG-2000 Product Overview* nella pagina dell'argomento per Nettuno perché l'utente 1 non dispone delle autorizzazioni di Office 365 per visualizzare il file.</span><span class="sxs-lookup"><span data-stu-id="4ec66-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="4ec66-118">Se un utente non è in grado di visualizzare informazioni sufficienti in un argomento per essere utile, l'argomento non sarà disponibile per l'utente.</span><span class="sxs-lookup"><span data-stu-id="4ec66-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="4ec66-119">In questo caso, l'utente non visualizza l'argomento evidenziato.</span><span class="sxs-lookup"><span data-stu-id="4ec66-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="4ec66-120">Un utente diverso che dispone delle autorizzazioni per ulteriori informazioni nell'argomento per essere utile, sarà in grado di visualizzare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="4ec66-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="4ec66-121">Autorizzazioni per gli argomenti per knowledge manager e collaboratori di argomenti</span><span class="sxs-lookup"><span data-stu-id="4ec66-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="4ec66-122">Gli utenti a cui sono assegnate le autorizzazioni per gestire gli argomenti, i responsabili delle conoscenze, potranno visualizzare solo le informazioni che dispongono delle autorizzazioni necessarie per la visualizzazione all'interno degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ec66-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="4ec66-123">Analogamente, gli utenti che dispongono di autorizzazioni per gli argomenti di creazione e modifica, collaboratori di argomenti, potranno visualizzare solo le informazioni che dispongono delle autorizzazioni per la visualizzazione all'interno degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ec66-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="4ec66-124">Confronto tra IA e informazioni sull'argomento curate manualmente</span><span class="sxs-lookup"><span data-stu-id="4ec66-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="4ec66-125">Gli argomenti possono contenere informazioni generate dall'intelligenza artificiale e informazioni aggiunte o modificate da collaboratori di argomenti o responsabili delle conoscenze.</span><span class="sxs-lookup"><span data-stu-id="4ec66-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="4ec66-126">Le informazioni in un argomento aggiunto dall'intelligenza artificiale sono visibili solo agli utenti che hanno accesso al contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="4ec66-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="4ec66-127">Le informazioni aggiunte o modificate manualmente da un collaboratore o un responsabile della conoscenza sono visibili a tutti gli utenti che possono visualizzare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="4ec66-127">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="4ec66-128">Nella tabella seguente vengono descritti gli utenti, i visualizzatori di argomenti, i collaboratori e i responsabili delle conoscenze, che possono visualizzare in un determinato argomento in base alle relative autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4ec66-128">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="4ec66-129">Elemento dell'argomento</span><span class="sxs-lookup"><span data-stu-id="4ec66-129">Topic item</span></span>|<span data-ttu-id="4ec66-130">Cosa possono vedere gli utenti</span><span class="sxs-lookup"><span data-stu-id="4ec66-130">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="4ec66-131">Nome argomento</span><span class="sxs-lookup"><span data-stu-id="4ec66-131">Topic name</span></span>|<span data-ttu-id="4ec66-132">Gli utenti possono visualizzare il nome dell'argomento di tutti gli argomenti nel Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ec66-132">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="4ec66-133">Alcuni argomenti potrebbero non essere visibili se hanno una pertinenza bassa per l'utente.</span><span class="sxs-lookup"><span data-stu-id="4ec66-133">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="4ec66-134">Descrizione dell'argomento</span><span class="sxs-lookup"><span data-stu-id="4ec66-134">Topic description</span></span>|<span data-ttu-id="4ec66-135">Le descrizioni generate dall'intelligenza artificiale sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="4ec66-135">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="4ec66-136">Le descrizioni immesse o modificate manualmente sono visibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4ec66-136">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="4ec66-137">Persone</span><span class="sxs-lookup"><span data-stu-id="4ec66-137">People</span></span>|<span data-ttu-id="4ec66-138">Gli utenti aggiunti sono visibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4ec66-138">Pinned people are visible to all users.</span></span> <span data-ttu-id="4ec66-139">Gli utenti suggeriti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="4ec66-139">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4ec66-140">File</span><span class="sxs-lookup"><span data-stu-id="4ec66-140">Files</span></span>|<span data-ttu-id="4ec66-141">I file sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="4ec66-141">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4ec66-142">Pagine</span><span class="sxs-lookup"><span data-stu-id="4ec66-142">Pages</span></span>|<span data-ttu-id="4ec66-143">Le pagine sono visibili solo per gli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="4ec66-143">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="4ec66-144">Siti</span><span class="sxs-lookup"><span data-stu-id="4ec66-144">Sites</span></span>|<span data-ttu-id="4ec66-145">I siti sono visibili solo per gli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="4ec66-145">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="4ec66-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ec66-146">See also</span></span>

