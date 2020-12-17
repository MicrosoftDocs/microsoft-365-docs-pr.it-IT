---
title: "Gestire gli argomenti nell'argomento centro in esperienze di argomento (anteprima) "
description: Come gestire gli argomenti nell'argomento centro.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 832067d157ed9ffcba1ed9ad514c375cbbdd752b
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698911"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="614fa-103">Gestire gli argomenti nell'argomento centro (anteprima)</span><span class="sxs-lookup"><span data-stu-id="614fa-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="614fa-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="614fa-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="614fa-105">[Altre informazioni su Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="614fa-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="614fa-106">Nel centro argomenti, un responsabile della Knowledge base può visualizzare la pagina **Gestisci argomenti** per esaminare gli argomenti che sono stati identificati nei percorsi di origine di SharePoint come specificato dall'amministratore delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="614fa-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Centro argomenti](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="614fa-108">I Knowledge Manager aiutano a guidare gli argomenti individuati tramite il ciclo di vita dell'argomento in cui gli argomenti sono:</span><span class="sxs-lookup"><span data-stu-id="614fa-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="614fa-109">Suggerito: un argomento è stato identificato da AI e dispone di sufficienti risorse di supporto, connessioni e proprietà per raggiungere la soglia dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="614fa-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="614fa-110">Confermato: è stato convalidato un argomento suggerito dall'IA.</span><span class="sxs-lookup"><span data-stu-id="614fa-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="614fa-111">La convalida viene fatta tramite conferma da un amministratore della Knowledge base. Inoltre, è possibile confermare un argomento se almeno due utenti forniscono commenti e suggerimenti positivi tramite commenti e suggerimenti sull'argomento valido.</span><span class="sxs-lookup"><span data-stu-id="614fa-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="614fa-112">Rimossi: un argomento viene rifiutato da un amministratore della Knowledge base e non sarà più visibile ai visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="614fa-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="614fa-113">L'argomento può trovarsi in uno stato qualsiasi quando viene rimosso (suggerito o confermato).</span><span class="sxs-lookup"><span data-stu-id="614fa-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="614fa-114">Published: un argomento confermato che è stato aggiornato manualmente.</span><span class="sxs-lookup"><span data-stu-id="614fa-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![Grafico del ciclo di vita degli argomenti](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="614fa-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="614fa-116">Requirements</span></span>

<span data-ttu-id="614fa-117">Per gestire gli argomenti nel centro tematico, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="614fa-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="614fa-118">Avere una licenza per l'argomento experiences.</span><span class="sxs-lookup"><span data-stu-id="614fa-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="614fa-119">Dispongono delle autorizzazioni per gli [**utenti che possono gestire gli argomenti**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span><span class="sxs-lookup"><span data-stu-id="614fa-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="614fa-120">Gli amministratori delle informazioni possono fornire agli utenti questa autorizzazione nelle impostazioni delle autorizzazioni per l'argomento Knowledge Network.</span><span class="sxs-lookup"><span data-stu-id="614fa-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="614fa-121">Non sarà possibile visualizzare la pagina Gestisci argomenti nel centro argomenti, a meno che non sia **possibile gestire gli argomenti** autorizzati.</span><span class="sxs-lookup"><span data-stu-id="614fa-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="614fa-122">Nel centro argomenti, un responsabile della Knowledge base può esaminare gli argomenti che sono stati identificati nei percorsi di origine di SharePoint specificati e può confermarli o rifiutarli.</span><span class="sxs-lookup"><span data-stu-id="614fa-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="614fa-123">Un responsabile della Knowledge base può inoltre creare e pubblicare nuove pagine degli argomenti se non si è trovato nell'argomento Discovery o modificare quelli esistenti se è necessario aggiornarli.</span><span class="sxs-lookup"><span data-stu-id="614fa-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="614fa-124">Esaminare gli argomenti consigliati</span><span class="sxs-lookup"><span data-stu-id="614fa-124">Review suggested topics</span></span>

<span data-ttu-id="614fa-125">Nella scheda **suggerimenti** dell'argomento relativo alla gestione degli argomenti del centro temi sono stati rilevati gli argomenti individuati nei percorsi di origine di SharePoint specificati. Un responsabile della Knowledge base può esaminare gli argomenti non confermati e scegliere di confermarli o rifiutarli.</span><span class="sxs-lookup"><span data-stu-id="614fa-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="614fa-126">Per esaminare un argomento consigliato:</span><span class="sxs-lookup"><span data-stu-id="614fa-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="614fa-127">Nella pagina **Gestisci argomenti** selezionare la scheda **suggerimenti** , quindi selezionare l'argomento per aprire la pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="614fa-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="614fa-128">Nella pagina dell'argomento esaminare la pagina dell'argomento e selezionare **modifica** se è necessario apportare modifiche alla pagina.</span><span class="sxs-lookup"><span data-stu-id="614fa-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="614fa-129">Dopo aver esaminato l'argomento, tornare alla pagina Gestisci argomenti.</span><span class="sxs-lookup"><span data-stu-id="614fa-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="614fa-130">Per l'argomento selezionato, è possibile:</span><span class="sxs-lookup"><span data-stu-id="614fa-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="614fa-131">Selezionare il segno di spunta per confermare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="614fa-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="614fa-132">Selezionare la **x** se si desidera rifiutare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="614fa-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="614fa-133">Gli argomenti confermati verranno rimossi dall'elenco **suggerito** e verranno visualizzati nell'elenco **confermato** .</span><span class="sxs-lookup"><span data-stu-id="614fa-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="614fa-134">Gli argomenti rifiutati verranno rimossi dall'elenco **suggerito** e verranno visualizzati nella scheda **rimossa** .</span><span class="sxs-lookup"><span data-stu-id="614fa-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="614fa-135">Argomenti convalidati</span><span class="sxs-lookup"><span data-stu-id="614fa-135">Confirmed topics</span></span>

<span data-ttu-id="614fa-136">Nella pagina Gestisci argomenti, gli argomenti che sono stati individuati nei percorsi di origine di SharePoint specificati e sono stati confermati da un responsabile della Knowledge base o da "crowd-sourced" confermati da due o più persone tramite il meccanismo di feedback della scheda saranno elencati nella scheda **confermata** . Se necessario, un utente con autorizzazioni per la gestione degli argomenti può esaminare gli argomenti confermati e scegliere di rifiutarli.</span><span class="sxs-lookup"><span data-stu-id="614fa-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="614fa-137">Per esaminare un argomento confermato:</span><span class="sxs-lookup"><span data-stu-id="614fa-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="614fa-138">Nella scheda **confermata** selezionare l'argomento per aprire la pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="614fa-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="614fa-139">Nella pagina dell'argomento esaminare la pagina dell'argomento e selezionare **modifica** se è necessario apportare modifiche alla pagina.</span><span class="sxs-lookup"><span data-stu-id="614fa-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="614fa-140">Si noti che è comunque possibile scegliere di rifiutare un argomento confermato.</span><span class="sxs-lookup"><span data-stu-id="614fa-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="614fa-141">A tale scopo, passare all'argomento selezionato nell'elenco confermati e selezionare la **x** se si desidera rifiutare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="614fa-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="614fa-142">Argomenti pubblicati</span><span class="sxs-lookup"><span data-stu-id="614fa-142">Published topics</span></span>
<span data-ttu-id="614fa-143">Gli argomenti pubblicati sono stati modificati in modo che informazioni specifiche vengano sempre visualizzate a chiunque incontri la pagina.</span><span class="sxs-lookup"><span data-stu-id="614fa-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="614fa-144">Gli argomenti creati manualmente sono elencati qui.</span><span class="sxs-lookup"><span data-stu-id="614fa-144">Manually created topics are listed here.</span></span>




