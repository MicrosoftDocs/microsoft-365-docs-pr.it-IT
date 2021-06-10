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
description: Panoramica dell'utilizzo della sicurezza per visualizzare gli argomenti.
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939624"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="1aac4-103">Limitazione per motivi di sicurezza di Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="1aac4-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="1aac4-104">Gli utenti di Viva Topics non possono visualizzare informazioni negli argomenti che le autorizzazioni Office 365 esistenti ne impediscono la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="1aac4-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="1aac4-105">Tutto ciò che un utente visualizza in una pagina di argomenti, ad esempio i siti di SharePoint, documenti e file, saranno informazioni che è già autorizzato a visualizzare.</span><span class="sxs-lookup"><span data-stu-id="1aac4-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="1aac4-106">Viva Topics non modifica le autorizzazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="1aac4-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="1aac4-107">Perché due utenti possono avere visualizzazioni diverse dello stesso argomento</span><span class="sxs-lookup"><span data-stu-id="1aac4-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="1aac4-108">Quando viene creato un argomento tramite l'intelligenza artificiale o la gestione manuale, questo può contenere una descrizione, nomi alternativi, persone associate all'argomento, oltre a siti, pagine e file correlati all'argomento.</span><span class="sxs-lookup"><span data-stu-id="1aac4-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="1aac4-109">Quando queste informazioni vengono visualizzate in una pagina dell'argomento, è possibile che due utenti che visualizzano lo stesso argomento non visualizzino le stesse informazioni.</span><span class="sxs-lookup"><span data-stu-id="1aac4-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="1aac4-110">Ad esempio, quando l'utente 1 visualizza la pagina dell'argomento di Nettuno, potrebbe vedere questa visualizzazione della pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="1aac4-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Argomento Nettuno per l'utente 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="1aac4-112">Tuttavia, quando l'utente 2 esamina la stessa pagina dell'argomento di Nettuno, la relativa visualizzazione è diversa dall'utente 1.</span><span class="sxs-lookup"><span data-stu-id="1aac4-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="1aac4-113">L'utente 2 è in grado di visualizzare il file *DG-2000 Product Overview* nella sezione **File** e pagine aggiunti della pagina dell'argomento, che non viene visualizzata per l'utente 1.</span><span class="sxs-lookup"><span data-stu-id="1aac4-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Argomento Nettuno per l'utente 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="1aac4-115">La differenza tra ciò che gli utenti possono visualizzare nello stesso argomento è che gli utenti potrebbero non disporre delle autorizzazioni Office 365 per visualizzare un sito o un file correlato.</span><span class="sxs-lookup"><span data-stu-id="1aac4-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="1aac4-116">Viva Topics rispetta le autorizzazioni impostate per gli elementi di un argomento e non può modificarne l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1aac4-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="1aac4-117">In questo esempio, l'utente 1 non è in grado di visualizzare il file *DG-2000 Product Overview* nella pagina dell'argomento relativa a Nettuno perché l'utente 1 non dispone delle autorizzazioni Office 365 per visualizzare il file.</span><span class="sxs-lookup"><span data-stu-id="1aac4-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="1aac4-118">Se un utente non è in grado di visualizzare informazioni sufficienti in un argomento per essere utile, l'argomento non sarà disponibile per l'utente.</span><span class="sxs-lookup"><span data-stu-id="1aac4-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="1aac4-119">In questo caso, l'utente non visualizza l'argomento evidenziato.</span><span class="sxs-lookup"><span data-stu-id="1aac4-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="1aac4-120">Mentre, un utente che dispone delle autorizzazioni necessarie per accedere ad altre informazioni dell'argomento potrà consultare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="1aac4-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="1aac4-121">Autorizzazioni per gli argomenti per i knowledge manager e i collaboratori degli argomenti</span><span class="sxs-lookup"><span data-stu-id="1aac4-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="1aac4-122">Gli utenti a cui sono assegnate le autorizzazioni per gestire gli argomenti, i responsabili delle conoscenze, potranno visualizzare solo le informazioni che dispongono delle autorizzazioni necessarie per la visualizzazione all'interno degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="1aac4-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="1aac4-123">Analogamente, gli utenti che dispongono di autorizzazioni per la creazione e la modifica di argomenti, i collaboratori di argomenti, potranno visualizzare solo le informazioni di cui dispongono delle autorizzazioni per visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="1aac4-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="1aac4-124">Intelligenza artificiale vs informazioni sull'argomento curate manualmente</span><span class="sxs-lookup"><span data-stu-id="1aac4-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="1aac4-125">Gli argomenti possono contenere informazioni generate dall'IA e informazioni aggiunte o modificate da collaboratori o knowledge manager.</span><span class="sxs-lookup"><span data-stu-id="1aac4-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="1aac4-126">Le informazioni in un argomento aggiunte dall'intelligenza artificiale sono visibili solo alle persone che hanno accesso al contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="1aac4-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="1aac4-127">La descrizione dell'argomento e le informazioni sulle persone aggiunte o modificate manualmente da un collaboratore o da un responsabile della conoscenza sono visibili a tutti gli utenti che possono visualizzare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="1aac4-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="1aac4-128">I file, le pagine e i siti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine, sia aggiunte manualmente o aggiunte dall'IA.</span><span class="sxs-lookup"><span data-stu-id="1aac4-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="1aac4-129">Nella tabella seguente vengono descritti gli elementi che gli utenti, i visualizzatori di argomenti, i collaboratori e i responsabili della conoscenza, possono visualizzare in un determinato argomento in base alle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="1aac4-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="1aac4-130">Oggetto dell'argomento</span><span class="sxs-lookup"><span data-stu-id="1aac4-130">Topic item</span></span>|<span data-ttu-id="1aac4-131">Argomenti che gli utenti possono visualizzare</span><span class="sxs-lookup"><span data-stu-id="1aac4-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="1aac4-132">Nome dell'argomento</span><span class="sxs-lookup"><span data-stu-id="1aac4-132">Topic name</span></span>|<span data-ttu-id="1aac4-133">Gli utenti possono visualizzare il nome degli argomenti nel Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="1aac4-133">Users can see the topic name of topics in the topic center.</span></span> <span data-ttu-id="1aac4-134">Alcuni argomenti potrebbero non essere visibili se gli utenti non dispongono delle autorizzazioni per il contenuto di origine o hanno una pertinenza bassa per l'utente.</span><span class="sxs-lookup"><span data-stu-id="1aac4-134">Some topics may not be visible if users don't have permissions to the source content or have a low relevancy to the user.</span></span>|
|<span data-ttu-id="1aac4-135">Descrizione dell'argomento</span><span class="sxs-lookup"><span data-stu-id="1aac4-135">Topic description</span></span>|<span data-ttu-id="1aac4-136">Le descrizioni generate dall'IA sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="1aac4-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="1aac4-137">Le descrizioni immesse o modificate manualmente sono visibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1aac4-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="1aac4-138">Persone</span><span class="sxs-lookup"><span data-stu-id="1aac4-138">People</span></span>|<span data-ttu-id="1aac4-139">Le persone bloccate sono visibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1aac4-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="1aac4-140">Le persone suggerite sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="1aac4-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="1aac4-141">File</span><span class="sxs-lookup"><span data-stu-id="1aac4-141">Files</span></span>|<span data-ttu-id="1aac4-142">I file sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="1aac4-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="1aac4-143">Pagine</span><span class="sxs-lookup"><span data-stu-id="1aac4-143">Pages</span></span>|<span data-ttu-id="1aac4-144">Le pagine sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="1aac4-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="1aac4-145">Siti</span><span class="sxs-lookup"><span data-stu-id="1aac4-145">Sites</span></span>|<span data-ttu-id="1aac4-146">I siti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="1aac4-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="1aac4-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aac4-147">See also</span></span>

