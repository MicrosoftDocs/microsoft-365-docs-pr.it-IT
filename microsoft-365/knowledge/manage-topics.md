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
ms.openlocfilehash: 59581dce3701e622a1e2d7ed264370c9d92b3211
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327274"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="5bd3f-103">Gestire gli argomenti nel Centro argomenti in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="5bd3f-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="5bd3f-104">Nel Centro argomenti Viva, un responsabile  della knowledge base può visualizzare la pagina Gestisci argomenti per esaminare gli argomenti identificati nelle posizioni di origine come specificato dall'amministratore della knowledge base.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Centro argomenti](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="5bd3f-106">Fasi dell'argomento</span><span class="sxs-lookup"><span data-stu-id="5bd3f-106">Topic stages</span></span>

<span data-ttu-id="5bd3f-107">I knowledge manager aiutano a guidare gli argomenti individuati nelle varie fasi del ciclo di vita degli argomenti: **Suggerite,** **Confermate,** **Pubblicate** e **Rimosse.**</span><span class="sxs-lookup"><span data-stu-id="5bd3f-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![Grafico ciclo di vita degli argomenti](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="5bd3f-109">**Consigliato:** un argomento è stato identificato dall'IA e dispone di risorse, connessioni e proprietà di supporto sufficienti.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="5bd3f-110">Questi argomenti sono contrassegnati come **argomento consigliato** nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="5bd3f-111">**Confermata:** viene convalidato un argomento suggerito dall'IA.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-111">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="5bd3f-112">La convalida dell'argomento deve essere confermata da un responsabile della conoscenza.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-112">Topic validation must be confirmed by a knowledge manager.</span></span> <span data-ttu-id="5bd3f-113">Per confermare un argomento, è necessario che vi sia una rete di due voti positivi ricevuti dagli utenti che hanno votato usando il meccanismo di feedback nella scheda dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-113">For a topic to be confirmed, there must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="5bd3f-114">Ad esempio, se un utente ha votato positivo e un utente ha votato negativo per un determinato argomento, sarebbero comunque necessari altri due voti positivi per confermare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-114">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="5bd3f-115">**Published**: argomento confermato che è stato curato: sono state apportate modifiche manuali per migliorarne la qualità.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-115">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>

- <span data-ttu-id="5bd3f-116">**Rimosso**: un argomento viene rifiutato da un responsabile della conoscenza e non sarà più visibile ai visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-116">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="5bd3f-117">Un argomento può essere rimosso in qualsiasi stato (suggerito, confermato o pubblicato).</span><span class="sxs-lookup"><span data-stu-id="5bd3f-117">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="5bd3f-118">Per rimuovere un argomento, deve essere presente una rete di due voti negativi ricevuti dagli utenti che hanno votato usando i meccanismi di feedback nella scheda dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-118">For a topic to be removed, there must be a net of two negative votes received from users who voted using the feedback mechanisms on the topic card.</span></span> <span data-ttu-id="5bd3f-119">Ad esempio, se un utente ha votato negativo e un utente ha votato positivo per un determinato argomento, sarebbero comunque necessari altri due voti negativi per rimuovere l'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-119">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span> <span data-ttu-id="5bd3f-120">Quando un argomento pubblicato viene rimosso, la pagina con i dettagli curati dovrà essere eliminata manualmente tramite la raccolta pagine del Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-120">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

<span data-ttu-id="5bd3f-121">Nella pagina **Gestisci argomenti,** un responsabile delle conoscenze può vedere se un argomento è stato confermato o rimosso dai voti degli utenti o da una persona specifica.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-121">On the **Manage topics** page, a knowledge manager can see whether a topic was confirmed or removed by user votes or by a specific person.</span></span> <span data-ttu-id="5bd3f-122">Ad esempio, per gli argomenti rimossi dai voti  degli utenti, il motivo viene visualizzato nella colonna Rimosso da come **voti** dell'utente anziché come nome di una persona.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-122">For example, for topics removed by user votes, the reason is shown in the **Removed by** column as **User votes** rather than a person's name.</span></span> 

   ![Screenshot of Manage topics page showing removed topics list with User votes highlighted.](../media/knowledge-management/removed-topics-user-votes.png) 

> [!Note] 
> <span data-ttu-id="5bd3f-124">Nella pagina **Gestisci argomenti,** ogni knowledge manager potrà visualizzare solo gli argomenti in cui hanno accesso ai file e alle pagine sottostanti connessi all'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-124">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="5bd3f-125">Questa limitazione delle autorizzazioni verrà riflessa nell'elenco degli argomenti visualizzati nelle schede Suggerite, **Confermate,** **Pubblicate** **e Rimosse.**</span><span class="sxs-lookup"><span data-stu-id="5bd3f-125">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="5bd3f-126">Il conteggio degli argomenti, tuttavia, mostra i conteggi totali nell'organizzazione indipendentemente dalle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-126">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="5bd3f-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5bd3f-127">Requirements</span></span>

<span data-ttu-id="5bd3f-128">Per gestire gli argomenti nel Centro argomenti, è necessario:</span><span class="sxs-lookup"><span data-stu-id="5bd3f-128">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="5bd3f-129">Avere una licenza Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-129">Have a Viva Topics license.</span></span>

- <span data-ttu-id="5bd3f-130">Disporre [**dell'autorizzazione Who gestire gli argomenti.**](./topic-experiences-user-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="5bd3f-130">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="5bd3f-131">Gli amministratori della knowledge base possono concedere agli utenti questa autorizzazione nelle impostazioni delle autorizzazioni dell'argomento Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-131">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="5bd3f-132">Non sarà possibile visualizzare  la pagina Gestisci argomenti nel Centro argomenti a meno che non si dispone dell'autorizzazione Who **gestire gli** argomenti.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-132">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="5bd3f-133">Nel Centro argomenti, un responsabile della conoscenza può esaminare gli argomenti identificati nelle posizioni di origine specificate e può confermarli o rimuoverli.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-133">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="5bd3f-134">Un responsabile della conoscenza può anche creare e pubblicare nuove pagine di argomento se non ne è stata trovata una nell'individuazione degli argomenti o modificare quelle esistenti se è necessario aggiornarne una.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-134">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="5bd3f-135">Esaminare gli argomenti suggeriti</span><span class="sxs-lookup"><span data-stu-id="5bd3f-135">Review suggested topics</span></span>

<span data-ttu-id="5bd3f-136">Nella pagina **Gestisci argomenti** gli argomenti individuati nei percorsi di origine SharePoint specificati verranno elencati nella **scheda Suggeriti.** Se necessario, un responsabile della knowledge base può esaminare gli argomenti non confermati e scegliere di confermarli o rimuoverli.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-136">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![Argomenti suggeriti](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="5bd3f-138">Per esaminare un argomento consigliato:</span><span class="sxs-lookup"><span data-stu-id="5bd3f-138">To review a suggested topic:</span></span>

1. <span data-ttu-id="5bd3f-139">Nella pagina **Gestisci argomenti** selezionare la **scheda** Suggeriti e quindi selezionare l'argomento per aprire la pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-139">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="5bd3f-140">Nella pagina dell'argomento esaminare la pagina dell'argomento e selezionare **Modifica** se è necessario apportare modifiche alla pagina.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-140">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="5bd3f-141">La pubblicazione di eventuali modifiche sposterà questo argomento nella **scheda Published.**</span><span class="sxs-lookup"><span data-stu-id="5bd3f-141">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="5bd3f-142">Dopo aver esaminato l'argomento, tornare alla **pagina Gestisci** argomenti.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-142">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="5bd3f-143">Per l'argomento selezionato, è possibile:</span><span class="sxs-lookup"><span data-stu-id="5bd3f-143">For the selected topic, you can:</span></span>

   - <span data-ttu-id="5bd3f-144">Selezionare il segno di spunta per confermare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-144">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="5bd3f-145">Selezionare la **x** se si desidera rimuovere l'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-145">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="5bd3f-146">Gli argomenti confermati verranno rimossi **dall'elenco Suggeriti** e ora verranno visualizzati **nell'elenco** Confermati.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-146">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="5bd3f-147">Gli argomenti rimossi verranno rimossi **dall'elenco Suggeriti** e ora verranno visualizzati nella **scheda** Rimosso.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-147">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="5bd3f-148">Punteggio qualità</span><span class="sxs-lookup"><span data-stu-id="5bd3f-148">Quality score</span></span>

<span data-ttu-id="5bd3f-149">A ogni argomento visualizzato nella **pagina Argomenti** suggeriti è assegnato un punteggio di qualità.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-149">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="5bd3f-150">Il punteggio di qualità è un riflesso della quantità di informazioni che l'utente medio visualizza per le informazioni sull'argomento, tenendo presente che ogni utente potrebbe visualizzare più o meno informazioni a causa delle autorizzazioni che potrebbero o meno avere sulle informazioni in un argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-150">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="5bd3f-151">Il punteggio di qualità può contribuire a fornire informazioni approfondite sugli argomenti con la maggior parte delle informazioni e può essere utile per trovare argomenti che potrebbero essere modificati manualmente.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-151">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="5bd3f-152">Ad esempio, un argomento con un punteggio di qualità inferiore potrebbe essere il risultato di alcuni utenti che non hanno autorizzazioni SharePoint per i file o i siti pertinenti inclusi nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-152">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="5bd3f-153">Un collaboratore può quindi modificare l'argomento in modo da includere le informazioni (se appropriato), che saranno quindi visualizzabili per tutti gli utenti che possono visualizzare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-153">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="5bd3f-154">Impression</span><span class="sxs-lookup"><span data-stu-id="5bd3f-154">Impressions</span></span>

<span data-ttu-id="5bd3f-155">Nella **colonna Impressions** viene visualizzato il numero di volte in cui un argomento è stato visualizzato agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-155">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="5bd3f-156">Sono incluse le visualizzazioni tramite le schede di risposta degli argomenti nella ricerca e le evidenziazioni degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-156">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="5bd3f-157">Non riflette il click-through su questi argomenti, ma che l'argomento è stato visualizzato.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-157">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="5bd3f-158">La **colonna Impressions** verrà visualizzata per gli argomenti nelle  schede **Suggerite,** Confermate, **Pubblicate** e Rimosse della **pagina Gestisci** argomenti. </span><span class="sxs-lookup"><span data-stu-id="5bd3f-158">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="5bd3f-159">Argomenti confermati</span><span class="sxs-lookup"><span data-stu-id="5bd3f-159">Confirmed topics</span></span>

<span data-ttu-id="5bd3f-160">Nella  pagina Gestisci argomenti, gli argomenti individuati nelle posizioni di origine SharePoint specificate e confermati da un responsabile della conoscenza o "crowdsourced" confermati da due o più persone nette (bilanciamento dei voti negativi degli utenti rispetto ai voti degli utenti positivi) tramite il meccanismo di feedback della scheda saranno elencati nella **scheda Confermata.** Se necessario, un utente con autorizzazioni per gestire gli argomenti può esaminare gli argomenti confermati e scegliere di rifiutarli.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-160">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="5bd3f-161">Per esaminare un argomento confermato:</span><span class="sxs-lookup"><span data-stu-id="5bd3f-161">To review a confirmed topic:</span></span>

1. <span data-ttu-id="5bd3f-162">Nella scheda **Confermata** selezionare l'argomento per aprire la pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-162">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="5bd3f-163">Nella pagina dell'argomento esaminare la pagina dell'argomento e selezionare **Modifica** se è necessario apportare modifiche alla pagina.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-163">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="5bd3f-164">Tieni presente che puoi comunque scegliere di rifiutare un argomento confermato.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-164">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="5bd3f-165">A tale scopo, passare all'argomento selezionato **nella** scheda Confermata e selezionare **la x** se si desidera rifiutare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-165">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="5bd3f-166">Argomenti pubblicati</span><span class="sxs-lookup"><span data-stu-id="5bd3f-166">Published topics</span></span>

<span data-ttu-id="5bd3f-167">Gli argomenti pubblicati sono stati modificati in modo che informazioni specifiche vengano sempre visualizzate a chiunque incontri la pagina.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-167">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="5bd3f-168">Anche gli argomenti creati manualmente sono elencati qui.</span><span class="sxs-lookup"><span data-stu-id="5bd3f-168">Manually created topics are listed here as well.</span></span>

   ![Gestire gli argomenti](../media/knowledge-management/manage-topics-new.png)
