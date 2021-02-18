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
ms.openlocfilehash: 12a2ad34c55cd63468266abca1fa053048053dd2
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279333"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="c1e35-103">Limitazione per motivi di sicurezza di Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="c1e35-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="c1e35-104">Gli utenti di Viva Topics non possono visualizzare informazioni negli argomenti che le autorizzazioni di Office 365 esistenti ne impediscono la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1e35-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="c1e35-105">Tutte le informazioni visualizzate da un utente in una pagina dell'argomento(ad esempio, siti di SharePoint, documenti, file) saranno informazioni che sono già autorizzate a visualizzare.</span><span class="sxs-lookup"><span data-stu-id="c1e35-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="c1e35-106">Viva Topics non apporta modifiche alle autorizzazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="c1e35-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="c1e35-107">Perché due utenti possono avere visualizzazioni diverse dello stesso argomento</span><span class="sxs-lookup"><span data-stu-id="c1e35-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="c1e35-108">Quando un argomento viene creato tramite IA o la gestione manuale, può contenere una descrizione dell'argomento, nomi alternativi, persone associate all'argomento, nonché siti, pagine e file correlati all'argomento.</span><span class="sxs-lookup"><span data-stu-id="c1e35-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="c1e35-109">Quando queste informazioni vengono visualizzate in una pagina dell'argomento, è possibile che due utenti che visualizzano lo stesso argomento non visualizzino le stesse informazioni.</span><span class="sxs-lookup"><span data-stu-id="c1e35-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="c1e35-110">Ad esempio, quando l'utente 1 visualizza la pagina dell'argomento Neptune, potrebbe vedere questa visualizzazione della pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="c1e35-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Argomento neptune per l'utente 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="c1e35-112">Tuttavia, quando l'utente 2 esamina la stessa pagina dell'argomento neptune, la visualizzazione è diversa dall'utente 1.</span><span class="sxs-lookup"><span data-stu-id="c1e35-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="c1e35-113">L'utente 2 è in grado di visualizzare il file *DG-2000 Product Overview* nella sezione **Pinned files and pages** della pagina dell'argomento, che non viene visualizzata per l'utente 1.</span><span class="sxs-lookup"><span data-stu-id="c1e35-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Argomento Neptune per l'utente 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="c1e35-115">La differenza tra ciò che gli utenti possono vedere nello stesso argomento è che gli utenti potrebbero non disporre delle autorizzazioni di Office 365 per visualizzare un sito o un file correlato.</span><span class="sxs-lookup"><span data-stu-id="c1e35-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="c1e35-116">Viva Topics rispetta le autorizzazioni impostate per gli elementi di un argomento e non può modificarne l'accesso.</span><span class="sxs-lookup"><span data-stu-id="c1e35-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="c1e35-117">In questo esempio, l'utente 1 non è in grado di visualizzare il file *DG-2000 Product Overview* nella pagina dell'argomento per Nettuno perché l'utente 1 non dispone delle autorizzazioni di Office 365 per visualizzare il file.</span><span class="sxs-lookup"><span data-stu-id="c1e35-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="c1e35-118">Se un utente non è in grado di visualizzare informazioni sufficienti in un argomento perché sia utile, l'argomento non sarà disponibile per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c1e35-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="c1e35-119">In questo caso, l'utente non visualizza l'argomento evidenziato.</span><span class="sxs-lookup"><span data-stu-id="c1e35-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="c1e35-120">Un utente diverso che dispone delle autorizzazioni per ulteriori informazioni nell'argomento per essere utile, sarà in grado di visualizzare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="c1e35-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="c1e35-121">Autorizzazioni per gli argomenti per knowledge manager e collaboratori di argomenti</span><span class="sxs-lookup"><span data-stu-id="c1e35-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="c1e35-122">Gli utenti a cui sono assegnate le autorizzazioni per gestire gli argomenti, i responsabili delle conoscenze, potranno visualizzare solo le informazioni che dispongono delle autorizzazioni necessarie per la visualizzazione all'interno degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="c1e35-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="c1e35-123">Analogamente, gli utenti che dispongono delle autorizzazioni per la creazione e la modifica degli argomenti, i collaboratori degli argomenti, potranno visualizzare solo le informazioni che dispongono delle autorizzazioni per la visualizzazione all'interno degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="c1e35-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="c1e35-124">Confronto tra IA e informazioni sull'argomento curate manualmente</span><span class="sxs-lookup"><span data-stu-id="c1e35-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="c1e35-125">Gli argomenti possono contenere informazioni generate dall'intelligenza artificiale e informazioni aggiunte o modificate da collaboratori di argomenti o responsabili delle conoscenze.</span><span class="sxs-lookup"><span data-stu-id="c1e35-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="c1e35-126">Le informazioni in un argomento aggiunto dall'intelligenza artificiale sono visibili solo agli utenti che hanno accesso al contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="c1e35-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="c1e35-127">La descrizione dell'argomento e le informazioni sulle persone aggiunte o modificate manualmente da un collaboratore o un responsabile della conoscenza sono visibili a tutti gli utenti che possono visualizzare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="c1e35-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="c1e35-128">I file, le pagine e i siti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine, sia aggiunte manualmente che dall'intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="c1e35-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="c1e35-129">Nella tabella seguente vengono descritti gli utenti, i visualizzatori di argomenti, i collaboratori e i responsabili delle conoscenze, che possono visualizzare in un determinato argomento in base alle relative autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c1e35-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="c1e35-130">Elemento dell'argomento</span><span class="sxs-lookup"><span data-stu-id="c1e35-130">Topic item</span></span>|<span data-ttu-id="c1e35-131">Cosa possono vedere gli utenti</span><span class="sxs-lookup"><span data-stu-id="c1e35-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="c1e35-132">Nome argomento</span><span class="sxs-lookup"><span data-stu-id="c1e35-132">Topic name</span></span>|<span data-ttu-id="c1e35-133">Gli utenti possono visualizzare il nome dell'argomento di tutti gli argomenti nel Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="c1e35-133">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="c1e35-134">Alcuni argomenti potrebbero non essere visibili se hanno una pertinenza bassa per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c1e35-134">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="c1e35-135">Descrizione dell'argomento</span><span class="sxs-lookup"><span data-stu-id="c1e35-135">Topic description</span></span>|<span data-ttu-id="c1e35-136">Le descrizioni generate dall'intelligenza artificiale sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="c1e35-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="c1e35-137">Le descrizioni immesse o modificate manualmente sono visibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c1e35-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="c1e35-138">Persone</span><span class="sxs-lookup"><span data-stu-id="c1e35-138">People</span></span>|<span data-ttu-id="c1e35-139">Gli utenti aggiunti sono visibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c1e35-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="c1e35-140">Gli utenti suggeriti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="c1e35-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="c1e35-141">File</span><span class="sxs-lookup"><span data-stu-id="c1e35-141">Files</span></span>|<span data-ttu-id="c1e35-142">I file sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="c1e35-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="c1e35-143">Pagine</span><span class="sxs-lookup"><span data-stu-id="c1e35-143">Pages</span></span>|<span data-ttu-id="c1e35-144">Le pagine sono visibili solo per gli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="c1e35-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="c1e35-145">Siti</span><span class="sxs-lookup"><span data-stu-id="c1e35-145">Sites</span></span>|<span data-ttu-id="c1e35-146">I siti sono visibili solo per gli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="c1e35-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="c1e35-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1e35-147">See also</span></span>

