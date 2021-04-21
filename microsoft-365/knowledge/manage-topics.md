---
title: Gestire gli argomenti nel Centro argomenti in Microsoft Viva Topics
description: Come gestire gli argomenti nel Centro argomenti.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 4532f5685fdde7c89ca59e5c22e1ad8afdf2b112
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904035"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="13685-103">Gestire gli argomenti nel Centro argomenti in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="13685-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="13685-104">Nel Centro argomenti Viva, un responsabile  della knowledge base può visualizzare la pagina Gestisci argomenti per esaminare gli argomenti identificati nelle posizioni di origine come specificato dall'amministratore della knowledge base.</span><span class="sxs-lookup"><span data-stu-id="13685-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Centro argomenti](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="13685-106">I knowledge manager aiutano a guidare gli argomenti individuati nelle varie fasi del ciclo di vita degli argomenti:</span><span class="sxs-lookup"><span data-stu-id="13685-106">Knowledge managers help to guide discovered topics through the various topic lifecycle stages:</span></span>

- <span data-ttu-id="13685-107">**Consigliato:** un argomento è stato identificato dall'IA e dispone di risorse, connessioni e proprietà di supporto sufficienti.</span><span class="sxs-lookup"><span data-stu-id="13685-107">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="13685-108">**Confermata:** viene convalidato un argomento suggerito dall'IA.</span><span class="sxs-lookup"><span data-stu-id="13685-108">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="13685-109">La convalida viene eseguita tramite conferma da un responsabile della conoscenza.</span><span class="sxs-lookup"><span data-stu-id="13685-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="13685-110">Inoltre, un argomento può essere confermato se sono presenti 2 voti positivi netti ricevuti dagli utenti finali tramite i meccanismi di feedback nella scheda dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="13685-110">Additionally, a topic can be confirmed if there is a net positive 2 votes from end users received via the feedback mechanisms on the topic card.</span></span>
- <span data-ttu-id="13685-111">**Published**: argomento confermato che è stato curato: sono state apportate modifiche manuali per migliorarne la qualità.</span><span class="sxs-lookup"><span data-stu-id="13685-111">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="13685-112">**Rimosso**: un argomento viene rifiutato da un responsabile della conoscenza e non sarà più visibile ai visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="13685-112">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="13685-113">L'argomento può essere in qualsiasi stato quando viene rimosso (suggerito, confermato o pubblicato).</span><span class="sxs-lookup"><span data-stu-id="13685-113">The topic can be in any state when it is removed (suggested, confirmed, or published).</span></span> <span data-ttu-id="13685-114">Quando un argomento pubblicato viene rimosso, la pagina con i dettagli curati dovrà essere eliminata manualmente tramite la raccolta pagine del Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="13685-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![Grafico ciclo di vita degli argomenti](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="13685-116">Nella pagina Gestisci argomenti, ogni knowledge manager potrà visualizzare solo gli argomenti in cui hanno accesso ai file e alle pagine sottostanti connessi all'argomento.</span><span class="sxs-lookup"><span data-stu-id="13685-116">On the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="13685-117">Questa limitazione delle autorizzazioni verrà riflessa nell'elenco degli argomenti visualizzati nelle schede Suggerite, **Confermate,** Rimosse e **Pubblicate.**</span><span class="sxs-lookup"><span data-stu-id="13685-117">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Removed**, and **Published** tabs.</span></span> <span data-ttu-id="13685-118">Il conteggio degli argomenti, tuttavia, mostra i conteggi totali nell'organizzazione indipendentemente dalle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="13685-118">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="13685-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13685-119">Requirements</span></span>

<span data-ttu-id="13685-120">Per gestire gli argomenti nel Centro argomenti, è necessario:</span><span class="sxs-lookup"><span data-stu-id="13685-120">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="13685-121">Avere una licenza Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="13685-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="13685-122">Disporre [**dell'autorizzazione Chi può gestire gli**](./topic-experiences-user-permissions.md) argomenti.</span><span class="sxs-lookup"><span data-stu-id="13685-122">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="13685-123">Gli amministratori della knowledge base possono concedere agli utenti questa autorizzazione nelle impostazioni delle autorizzazioni dell'argomento Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="13685-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="13685-124">Non sarà possibile visualizzare la pagina Gestisci argomenti nel Centro argomenti a meno che non si dispone dell'autorizzazione Chi **può gestire gli** argomenti.</span><span class="sxs-lookup"><span data-stu-id="13685-124">You will not be able to view the Manage Topics page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="13685-125">Nel Centro argomenti, un responsabile della conoscenza può esaminare gli argomenti identificati nelle posizioni di origine specificate e può confermarli o rifiutarli.</span><span class="sxs-lookup"><span data-stu-id="13685-125">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="13685-126">Un responsabile della conoscenza può anche creare e pubblicare nuove pagine di argomento se non ne è stata trovata una nell'individuazione degli argomenti o modificare quelle esistenti se è necessario aggiornarne una.</span><span class="sxs-lookup"><span data-stu-id="13685-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="13685-127">Esaminare gli argomenti suggeriti</span><span class="sxs-lookup"><span data-stu-id="13685-127">Review suggested topics</span></span>

<span data-ttu-id="13685-128">Nella pagina Gestisci argomenti del Centro argomenti gli argomenti individuati nei percorsi di origine di SharePoint specificati verranno elencati nella **scheda Suggeriti.** Se necessario, un responsabile della knowledge base può esaminare gli argomenti non confermati e scegliere di confermarli o rifiutarli.</span><span class="sxs-lookup"><span data-stu-id="13685-128">On the topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![Argomenti suggeriti](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="13685-130">Per esaminare un argomento consigliato:</span><span class="sxs-lookup"><span data-stu-id="13685-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="13685-131">Nella pagina **Gestisci argomenti** selezionare la **scheda Suggeriti** e selezionare l'argomento per aprire la pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="13685-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="13685-132">Nella pagina dell'argomento esaminare la pagina dell'argomento e selezionare **Modifica** se è necessario apportare modifiche alla pagina.</span><span class="sxs-lookup"><span data-stu-id="13685-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="13685-133">La pubblicazione di eventuali modifiche sposterà questo argomento nella **scheda Published.**</span><span class="sxs-lookup"><span data-stu-id="13685-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="13685-134">Dopo aver esaminato l'argomento, tornare alla pagina Gestisci argomenti.</span><span class="sxs-lookup"><span data-stu-id="13685-134">After reviewing the topic, go back to the Manage Topics page.</span></span> <span data-ttu-id="13685-135">Per l'argomento selezionato, è possibile:</span><span class="sxs-lookup"><span data-stu-id="13685-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="13685-136">Selezionare il segno di spunta per confermare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="13685-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="13685-137">Selezionare la **x** se si desidera rifiutare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="13685-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="13685-138">Gli argomenti confermati verranno rimossi **dall'elenco Suggeriti** e ora verranno visualizzati **nell'elenco** Confermati.</span><span class="sxs-lookup"><span data-stu-id="13685-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="13685-139">Gli argomenti rifiutati verranno rimossi **dall'elenco Suggeriti** e ora verranno visualizzati nella **scheda** Rimosso.</span><span class="sxs-lookup"><span data-stu-id="13685-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="13685-140">Punteggio qualità</span><span class="sxs-lookup"><span data-stu-id="13685-140">Quality score</span></span>

<span data-ttu-id="13685-141">A ogni argomento visualizzato nella pagina Argomenti suggeriti è assegnato un punteggio di qualità.</span><span class="sxs-lookup"><span data-stu-id="13685-141">Each topic that appears on your Suggested Topics page has a quality score assigned to it.</span></span> <span data-ttu-id="13685-142">Il punteggio di qualità è un riflesso della quantità di informazioni che l'utente medio visualizza per le informazioni sull'argomento, tenendo presente che ogni utente potrebbe visualizzare più o meno informazioni a causa delle autorizzazioni che potrebbero o meno avere sulle informazioni in un argomento.</span><span class="sxs-lookup"><span data-stu-id="13685-142">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="13685-143">Il punteggio di qualità può contribuire a fornire informazioni approfondite sugli argomenti con la maggior parte delle informazioni e può essere utile per trovare argomenti che potrebbero essere modificati manualmente.</span><span class="sxs-lookup"><span data-stu-id="13685-143">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="13685-144">Ad esempio, un argomento con un punteggio di qualità inferiore potrebbe essere il risultato di alcuni utenti che non hanno autorizzazioni di SharePoint per i file o i siti pertinenti inclusi nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="13685-144">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="13685-145">Un collaboratore può quindi modificare l'argomento in modo da includere le informazioni (se appropriato), che saranno quindi visualizzabili per tutti gli utenti che possono visualizzare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="13685-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="13685-146">Impression</span><span class="sxs-lookup"><span data-stu-id="13685-146">Impressions</span></span>

<span data-ttu-id="13685-147">Nella **colonna Impressions** viene visualizzato il numero di volte in cui un argomento è stato visualizzato agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="13685-147">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="13685-148">Sono incluse le visualizzazioni tramite le schede di risposta degli argomenti nella ricerca e le evidenziazioni degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="13685-148">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="13685-149">Non riflette il click-through su questi argomenti, ma che l'argomento è stato visualizzato.</span><span class="sxs-lookup"><span data-stu-id="13685-149">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="13685-150">La **colonna Impressions** verrà visualizzata per gli argomenti nelle  schede **Suggerite,** Confermate, **Pubblicate** e Rimosse della pagina Gestisci argomenti. </span><span class="sxs-lookup"><span data-stu-id="13685-150">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the Manage Topics page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="13685-151">Argomenti confermati</span><span class="sxs-lookup"><span data-stu-id="13685-151">Confirmed topics</span></span>

<span data-ttu-id="13685-152">Nella pagina Gestisci argomenti, gli argomenti individuati nelle posizioni di origine di SharePoint specificate e confermati da un knowledge manager o "crowdsourced" confermati da due o più persone nette (bilanciamento dei voti negativi degli utenti rispetto ai voti degli utenti positivi) tramite il meccanismo di feedback della scheda saranno elencati nella **scheda Confermata.** Se necessario, un utente con autorizzazioni per gestire gli argomenti può esaminare gli argomenti confermati e scegliere di rifiutarli.</span><span class="sxs-lookup"><span data-stu-id="13685-152">On the Manage Topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="13685-153">Per esaminare un argomento confermato:</span><span class="sxs-lookup"><span data-stu-id="13685-153">To review a confirmed topic:</span></span>

1. <span data-ttu-id="13685-154">Nella scheda **Confermata** selezionare l'argomento per aprire la pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="13685-154">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="13685-155">Nella pagina dell'argomento esaminare la pagina dell'argomento e selezionare **Modifica** se è necessario apportare modifiche alla pagina.</span><span class="sxs-lookup"><span data-stu-id="13685-155">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="13685-156">Tieni presente che puoi comunque scegliere di rifiutare un argomento confermato.</span><span class="sxs-lookup"><span data-stu-id="13685-156">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="13685-157">A tale scopo, passare all'argomento selezionato **nella** scheda Confermata e selezionare **la x** se si desidera rifiutare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="13685-157">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="13685-158">Argomenti pubblicati</span><span class="sxs-lookup"><span data-stu-id="13685-158">Published topics</span></span>
<span data-ttu-id="13685-159">Gli argomenti pubblicati sono stati modificati in modo che informazioni specifiche vengano sempre visualizzate a chiunque incontri la pagina.</span><span class="sxs-lookup"><span data-stu-id="13685-159">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="13685-160">Anche gli argomenti creati manualmente sono elencati qui.</span><span class="sxs-lookup"><span data-stu-id="13685-160">Manually created topics are listed here as well.</span></span>

   ![Gestire gli argomenti](../media/knowledge-management/manage-topics-new.png) </br>
