---
title: Topic Experience taglio di sicurezza (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Panoramica del modo in cui viene utilizzata la sicurezza per visualizzare gli argomenti.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698951"
---
# <a name="topic-experiences-security-trimming-preview"></a><span data-ttu-id="99480-103">Topic Experience taglio di sicurezza (anteprima)</span><span class="sxs-lookup"><span data-stu-id="99480-103">Topic Experiences security trimming (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="99480-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="99480-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="99480-105">[Altre informazioni su Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="99480-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="99480-106">Topic experiences gli utenti non saranno in grado di visualizzare le informazioni negli argomenti che le autorizzazioni esistenti di Office 365 impediscono loro di vedere.</span><span class="sxs-lookup"><span data-stu-id="99480-106">Topic experiences users will not be able to view information in topics that their existing Office 365 permissions prevents them from seeing.</span></span> <span data-ttu-id="99480-107">Tutto ciò che un utente vede in una pagina di un argomento (ad esempio, siti di SharePoint, documenti, file) sarà informazioni che sono già autorizzati a visualizzare.</span><span class="sxs-lookup"><span data-stu-id="99480-107">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="99480-108">L'argomento esperienze non consente di apportare modifiche alle autorizzazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="99480-108">Topic experiences does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="99480-109">Perché due utenti possono avere visualizzazioni diverse dello stesso argomento</span><span class="sxs-lookup"><span data-stu-id="99480-109">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="99480-110">Quando si crea un argomento tramite AI o con la cura manuale, può contenere una descrizione dell'argomento, nomi alternativi, persone associate all'argomento, nonché siti, pagine e file correlati all'argomento.</span><span class="sxs-lookup"><span data-stu-id="99480-110">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="99480-111">Quando queste informazioni vengono visualizzate in una pagina di argomento, è possibile che due utenti che stanno visualizzando lo stesso argomento My non vedano le stesse informazioni.</span><span class="sxs-lookup"><span data-stu-id="99480-111">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="99480-112">Ad esempio, quando l'utente 1 Visualizza la pagina dell'argomento Neptune, questo è ciò che potrebbe vedere.</span><span class="sxs-lookup"><span data-stu-id="99480-112">For example, when User 1 views the Neptune topic page, this is what they might see.</span></span>

![Argomento Neptune per l'utente 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="99480-114">Tuttavia, quando l'utente 2 Guarda la stessa pagina dell'argomento Neptune, la sua visualizzazione è diversa da quella dell'utente 1.</span><span class="sxs-lookup"><span data-stu-id="99480-114">However, when User 2 looks at the same Neptune topic page, her view differs from User 1.</span></span>  <span data-ttu-id="99480-115">L'utente 2 è in grado di visualizzare il file di *Panoramica del prodotto DG-2000* nella sezione **file bloccati e pagine** della pagina dell'argomento, che non viene visualizzata per l'utente 1.</span><span class="sxs-lookup"><span data-stu-id="99480-115">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Argomento Neptune per l'utente 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="99480-117">La differenza in quello che gli utenti possono vedere nello stesso argomento è che gli utenti potrebbero non disporre delle autorizzazioni di Office 365 per visualizzare un sito o un file correlato.</span><span class="sxs-lookup"><span data-stu-id="99480-117">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="99480-118">L'argomento experiences rispetta le autorizzazioni impostate per gli elementi di un argomento e non è in grado di modificarne l'accesso.</span><span class="sxs-lookup"><span data-stu-id="99480-118">Topic experiences respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="99480-119">In questo esempio, l'utente 1 non è in grado di visualizzare il file di *Panoramica del prodotto DG-2000* nella relativa pagina degli argomenti per Neptune perché l'utente 1 non dispone di autorizzazioni di Office 365 per visualizzare il file.</span><span class="sxs-lookup"><span data-stu-id="99480-119">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="99480-120">Se un utente non è in grado di visualizzare informazioni sufficienti in un argomento perché sia utile, l'argomento non sarà disponibile per l'utente.</span><span class="sxs-lookup"><span data-stu-id="99480-120">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="99480-121">In questo caso, l'argomento evidenziato non verrà visualizzato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="99480-121">In this instance, the user will not see the highlighted topic.</span></span> <span data-ttu-id="99480-122">Tuttavia, un utente diverso che dispone delle autorizzazioni per ulteriori informazioni nell'argomento per essere utile, sarà in grado di vedere l'argomento.</span><span class="sxs-lookup"><span data-stu-id="99480-122">However, a different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="99480-123">Autorizzazioni di argomento per i responsabili delle informazioni e i collaboratori degli argomenti</span><span class="sxs-lookup"><span data-stu-id="99480-123">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="99480-124">Gli utenti a cui vengono assegnate le autorizzazioni per la gestione degli argomenti-Knowledge Manager saranno in grado di visualizzare le informazioni che hanno le autorizzazioni per la visualizzazione all'interno degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="99480-124">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="99480-125">Analogamente, gli utenti che dispongono di autorizzazioni per l'argomento Create and Edit sono in grado di visualizzare le informazioni che dispongono di autorizzazioni per la visualizzazione all'interno degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="99480-125">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="99480-126">Informazioni sull'argomento AI rispetto a quelle curate manualmente</span><span class="sxs-lookup"><span data-stu-id="99480-126">AI versus manually curated topic information</span></span>

<span data-ttu-id="99480-127">Gli argomenti possono contenere informazioni generate da AI e informazioni aggiunte o modificate da parte di collaboratori o responsabili della conoscenza.</span><span class="sxs-lookup"><span data-stu-id="99480-127">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="99480-128">Le informazioni contenute in un argomento aggiunto da AI sono visibili solo agli utenti che hanno accesso al contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="99480-128">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="99480-129">Le informazioni aggiunte manualmente o modificate da un partecipante all'argomento o Knowledge Manager sono visibili a tutti gli utenti che possono visualizzare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="99480-129">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="99480-130">Nella tabella seguente vengono descritti gli utenti, ovvero i visualizzatori di argomenti, i collaboratori e i Knowledge Manager, che possono essere visualizzati in un argomento specifico in base alle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="99480-130">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="99480-131">Elemento dell'argomento</span><span class="sxs-lookup"><span data-stu-id="99480-131">Topic item</span></span>|<span data-ttu-id="99480-132">Cosa possono vedere gli utenti</span><span class="sxs-lookup"><span data-stu-id="99480-132">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="99480-133">Nome dell'argomento</span><span class="sxs-lookup"><span data-stu-id="99480-133">Topic name</span></span>|<span data-ttu-id="99480-134">Gli utenti possono visualizzare il nome dell'argomento di tutti gli argomenti nel centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="99480-134">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="99480-135">Alcuni argomenti potrebbero non essere visibili se l'utente ha una scarsa pertinenza.</span><span class="sxs-lookup"><span data-stu-id="99480-135">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="99480-136">Descrizione argomento</span><span class="sxs-lookup"><span data-stu-id="99480-136">Topic description</span></span>|<span data-ttu-id="99480-137">Le descrizioni generate AI sono visibili solo per gli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="99480-137">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="99480-138">Le descrizioni inserite o modificate manualmente sono visibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="99480-138">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="99480-139">Persone</span><span class="sxs-lookup"><span data-stu-id="99480-139">People</span></span>|<span data-ttu-id="99480-140">Le persone bloccate sono visibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="99480-140">Pinned people are visible to all users.</span></span> <span data-ttu-id="99480-141">Le persone suggerite sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="99480-141">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="99480-142">File</span><span class="sxs-lookup"><span data-stu-id="99480-142">Files</span></span>|<span data-ttu-id="99480-143">I file sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="99480-143">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="99480-144">Pagine</span><span class="sxs-lookup"><span data-stu-id="99480-144">Pages</span></span>|<span data-ttu-id="99480-145">Le pagine sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="99480-145">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="99480-146">Siti</span><span class="sxs-lookup"><span data-stu-id="99480-146">Sites</span></span>|<span data-ttu-id="99480-147">I siti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.</span><span class="sxs-lookup"><span data-stu-id="99480-147">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="99480-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99480-148">See also</span></span>

