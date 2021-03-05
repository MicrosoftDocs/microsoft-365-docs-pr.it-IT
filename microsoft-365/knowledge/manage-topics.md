---
title: Gestire gli argomenti nel Centro argomenti in Microsoft Viva Topics
description: Come gestire gli argomenti nel Centro argomenti.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 3d083537f3a9337d88d63861e0bf66867f558aba
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454006"
---
# <a name="manage-topics-in-the-topic-center"></a><span data-ttu-id="678f0-103">Gestire gli argomenti nel Centro argomenti</span><span class="sxs-lookup"><span data-stu-id="678f0-103">Manage topics in the Topic center</span></span> 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="678f0-104">Nel Centro argomenti viva, un responsabile  della knowledge base può visualizzare la pagina Gestisci argomenti per esaminare gli argomenti identificati nei percorsi di origine di SharePoint come specificato dall'amministratore della knowledge base.</span><span class="sxs-lookup"><span data-stu-id="678f0-104">In the Viva Topics Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Centro argomenti](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="678f0-106">I responsabili della conoscenza consentono di guidare gli argomenti individuati nel ciclo di vita degli argomenti in cui sono:</span><span class="sxs-lookup"><span data-stu-id="678f0-106">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="678f0-107">Consigliato: un argomento è stato identificato dall'intelligenza artificiale e dispone di risorse, connessioni e proprietà di supporto sufficienti.</span><span class="sxs-lookup"><span data-stu-id="678f0-107">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="678f0-108">Confermato: viene convalidato un argomento suggerito dall'intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="678f0-108">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="678f0-109">La convalida viene eseguita tramite la conferma di un responsabile della conoscenza.</span><span class="sxs-lookup"><span data-stu-id="678f0-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="678f0-110">Inoltre, un argomento può essere confermato se almeno due utenti forniscono feedback positivo tramite la domanda di feedback nella scheda dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="678f0-110">Additionally, a topic can be confirmed if at least two users give positive feedback through the feedback question on the topic card.</span></span>
- <span data-ttu-id="678f0-111">Published: Argomento confermato che è stato curato: sono state apportate modifiche manuali per migliorarne la qualità.</span><span class="sxs-lookup"><span data-stu-id="678f0-111">Published: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="678f0-112">Rimosso: un argomento viene rifiutato da un responsabile della conoscenza e non sarà più visibile ai visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="678f0-112">Removed: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="678f0-113">L'argomento può essere in qualsiasi stato quando viene rimosso (suggerito, confermato o pubblicato).</span><span class="sxs-lookup"><span data-stu-id="678f0-113">The topic can be in any state when it is removed (suggested, confirmed or published).</span></span> <span data-ttu-id="678f0-114">Quando un argomento pubblicato viene rimosso, la pagina con i dettagli selezionati dovrà essere eliminata manualmente tramite la Raccolta pagine del Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="678f0-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![Grafico ciclo di vita degli argomenti](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="678f0-116">Nella pagina Gestisci argomenti, ogni knowledge manager sarà in grado di visualizzare solo gli argomenti in cui hanno accesso ai file e alle pagine dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="678f0-116">In the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the files and pages of the topic.</span></span> <span data-ttu-id="678f0-117">Ciò si rifletterà negli argomenti elencati nelle schede Suggerite, Confermate, Rimosse e Pubblicate.</span><span class="sxs-lookup"><span data-stu-id="678f0-117">This will be reflected in the topics that are listed under the Suggested, Confirmed, Removed, and Published tabs.</span></span> <span data-ttu-id="678f0-118">Nell'argomento vengono tuttavia visualizzati i conteggi totali nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="678f0-118">The topic counts, however, show the total counts in the organization.</span></span>

## <a name="requirements"></a><span data-ttu-id="678f0-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="678f0-119">Requirements</span></span>

<span data-ttu-id="678f0-120">Per gestire gli argomenti nel Centro argomenti, è necessario:</span><span class="sxs-lookup"><span data-stu-id="678f0-120">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="678f0-121">Avere una licenza Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="678f0-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="678f0-122">Disporre [**dell'autorizzazione Chi può gestire gli**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) argomenti.</span><span class="sxs-lookup"><span data-stu-id="678f0-122">Have the [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) permission.</span></span> <span data-ttu-id="678f0-123">Gli amministratori della knowledge base possono concedere agli utenti questa autorizzazione nelle impostazioni delle autorizzazioni dell'argomento Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="678f0-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="678f0-124">Non sarà possibile visualizzare la pagina Gestisci argomenti nel Centro argomenti, a meno che non si abbia l'autorizzazione Chi **può gestire gli** argomenti.</span><span class="sxs-lookup"><span data-stu-id="678f0-124">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="678f0-125">Nel Centro argomenti un responsabile della knowledge base può esaminare gli argomenti identificati nei percorsi di origine di SharePoint specificati e può confermarli o rifiutarli.</span><span class="sxs-lookup"><span data-stu-id="678f0-125">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="678f0-126">Un responsabile della conoscenza può anche creare e pubblicare nuove pagine di argomento se non ne è stata trovata una nell'individuazione di argomenti oppure modificare quelle esistenti se è necessario aggiornarne una.</span><span class="sxs-lookup"><span data-stu-id="678f0-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="678f0-127">Esaminare gli argomenti suggeriti</span><span class="sxs-lookup"><span data-stu-id="678f0-127">Review suggested topics</span></span>

<span data-ttu-id="678f0-128">Nella pagina Gestione argomenti del Centro argomenti gli argomenti individuati nei percorsi di origine di SharePoint specificati verranno elencati nella **scheda Suggeriti.** Se necessario, un responsabile della knowledge base può esaminare gli argomenti non confermati e scegliere di confermarli o rifiutarli.</span><span class="sxs-lookup"><span data-stu-id="678f0-128">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![Argomenti suggeriti](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="678f0-130">Per esaminare un argomento consigliato:</span><span class="sxs-lookup"><span data-stu-id="678f0-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="678f0-131">Nella pagina **Gestisci argomenti** selezionare la **scheda Suggeriti** e selezionare l'argomento per aprire la pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="678f0-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="678f0-132">Nella pagina dell'argomento esaminare la pagina dell'argomento e selezionare **Modifica** se è necessario apportare modifiche alla pagina.</span><span class="sxs-lookup"><span data-stu-id="678f0-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="678f0-133">La pubblicazione di eventuali modifiche sposterà questo argomento nella **scheda** Published.</span><span class="sxs-lookup"><span data-stu-id="678f0-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="678f0-134">Dopo aver esaminato l'argomento, tornare alla pagina Gestisci argomenti.</span><span class="sxs-lookup"><span data-stu-id="678f0-134">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="678f0-135">Per l'argomento selezionato, è possibile:</span><span class="sxs-lookup"><span data-stu-id="678f0-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="678f0-136">Selezionare il segno di spunta per confermare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="678f0-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="678f0-137">Selezionare la **x** se si desidera rifiutare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="678f0-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="678f0-138">Gli argomenti confermati verranno rimossi **dall'elenco** Suggeriti e ora verranno visualizzati **nell'elenco** Confermati.</span><span class="sxs-lookup"><span data-stu-id="678f0-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="678f0-139">Gli argomenti rifiutati verranno rimossi **dall'elenco** Suggeriti e ora verranno visualizzati nella **scheda** Rimosso.</span><span class="sxs-lookup"><span data-stu-id="678f0-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="678f0-140">Punteggio qualità</span><span class="sxs-lookup"><span data-stu-id="678f0-140">Quality score</span></span>

<span data-ttu-id="678f0-141">A ogni argomento visualizzato nella pagina Argomenti suggeriti <b>è</b> assegnato un punteggio di qualità.</span><span class="sxs-lookup"><span data-stu-id="678f0-141">Each topic that appears in your Suggested Topics page has a <b>Quality</b> score assigned to it.</span></span> <span data-ttu-id="678f0-142">Il punteggio Di qualità riflette la quantità di informazioni che l'utente medio potrà visualizzare per le informazioni sull'argomento, tenendo presente che ogni utente può visualizzare più o meno informazioni a causa delle autorizzazioni che possono o meno avere sulle informazioni in un argomento.</span><span class="sxs-lookup"><span data-stu-id="678f0-142">The Quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user may see more or less information because of the permissions they may or may not have on the information in a topic.</span></span> 

<span data-ttu-id="678f0-143">Il punteggio Di qualità può essere utile per fornire informazioni dettagliate sugli argomenti con il maggior numero di informazioni e può essere utile per trovare argomenti che potrebbero dover essere modificati manualmente.</span><span class="sxs-lookup"><span data-stu-id="678f0-143">The Quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span>  <span data-ttu-id="678f0-144">Ad esempio, un argomento con un punteggio di qualità inferiore può essere il risultato di alcuni utenti che non hanno autorizzazioni di SharePoint per i file o i siti pertinenti inclusi nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="678f0-144">For example, a topic with a lower quality score may be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="678f0-145">Un collaboratore può quindi modificare l'argomento in modo da includere le informazioni (se appropriato), che saranno quindi visualizzabili per tutti gli utenti che possono visualizzare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="678f0-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

<span data-ttu-id="678f0-146">Il punteggio Qualità può variare da 1 a 100.</span><span class="sxs-lookup"><span data-stu-id="678f0-146">The Quality score could range from 1 to 100.</span></span> <span data-ttu-id="678f0-147">Un argomento appena individuato avrà un punteggio di qualità pari a 0 fino a quando due o più utenti non lo avranno visualizzato.</span><span class="sxs-lookup"><span data-stu-id="678f0-147">A newly discovered topic will have a quality score of 0 until two or more users have viewed it.</span></span> <span data-ttu-id="678f0-148">Ogni punteggio di qualità degli utenti è determinato da una serie di fattori, ad esempio la quantità di contenuto visualizzato per l'utente specifico, che viene controllata dalle autorizzazioni dell'utente in quanto ogni pagina dell'argomento dispone di limitazione per motivi di sicurezza per il contenuto generato dall'intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="678f0-148">Each users quality score is determined by a number of factors, such as the amount of content displayed for the specific user, which is controlled the user's permissions as each topic page has security trimming in place for AI-generated content.</span></span> <span data-ttu-id="678f0-149">Il punteggio qualità visualizzato nella scheda Argomenti suggeriti è una media di ogni singolo punteggio degli utenti.</span><span class="sxs-lookup"><span data-stu-id="678f0-149">The Quality score shown on the Suggested topics tab is an average of each users individual score.</span></span>

### <a name="impressions"></a><span data-ttu-id="678f0-150">Impression</span><span class="sxs-lookup"><span data-stu-id="678f0-150">Impressions</span></span>

<span data-ttu-id="678f0-151">Nella <b>colonna Impression viene</b> visualizzato il numero di volte in cui un argomento è stato visualizzato agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="678f0-151">The <b>Impressions</b> column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="678f0-152">Sono incluse le visualizzazioni tramite le schede degli argomenti nella ricerca, le evidenziazioni degli argomenti e le visualizzazioni del Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="678f0-152">This includes views through topic cards in search, through topic highlights, and through Topic center views.</span></span> <span data-ttu-id="678f0-153">Non riflette il click-through su questi argomenti, ma che l'argomento è stato visualizzato.</span><span class="sxs-lookup"><span data-stu-id="678f0-153">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="678f0-154">La colonna Impression verrà visualizzata per gli argomenti nelle schede Suggerite, Confermate, Pubblicate e Rimosse nella pagina Gestisci argomenti.</span><span class="sxs-lookup"><span data-stu-id="678f0-154">The Impressions column will show for topics in the Suggested, Confirmed, Published, and Removed tabs in the Manage Topics page.</span></span>


## <a name="confirmed-topics"></a><span data-ttu-id="678f0-155">Argomenti confermati</span><span class="sxs-lookup"><span data-stu-id="678f0-155">Confirmed topics</span></span>

<span data-ttu-id="678f0-156">Nella pagina Gestisci argomenti, gli argomenti individuati nelle posizioni di origine di SharePoint specificate e confermati da un responsabile della conoscenza o "di  origine di massa" confermati da due o più persone tramite il meccanismo di feedback della scheda verranno elencati nella scheda Confermata. Se necessario, un utente con autorizzazioni per gestire gli argomenti può esaminare gli argomenti confermati e scegliere di rifiutarli.</span><span class="sxs-lookup"><span data-stu-id="678f0-156">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="678f0-157">Per esaminare un argomento confermato:</span><span class="sxs-lookup"><span data-stu-id="678f0-157">To review a confirmed topic:</span></span>

1. <span data-ttu-id="678f0-158">Nella scheda **Confirmed** selezionare l'argomento per aprire la pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="678f0-158">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="678f0-159">Nella pagina dell'argomento esaminare la pagina dell'argomento e selezionare **Modifica** se è necessario apportare modifiche alla pagina.</span><span class="sxs-lookup"><span data-stu-id="678f0-159">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="678f0-160">Tieni presente che puoi comunque scegliere di rifiutare un argomento confermato.</span><span class="sxs-lookup"><span data-stu-id="678f0-160">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="678f0-161">A tale scopo, passare all'argomento selezionato nell'elenco Confermata e selezionare **la x** se si desidera rifiutare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="678f0-161">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="678f0-162">Argomenti pubblicati</span><span class="sxs-lookup"><span data-stu-id="678f0-162">Published topics</span></span>
<span data-ttu-id="678f0-163">Gli argomenti pubblicati sono stati modificati in modo che informazioni specifiche vengano sempre visualizzate a chiunque incontri la pagina.</span><span class="sxs-lookup"><span data-stu-id="678f0-163">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="678f0-164">Anche gli argomenti creati manualmente sono elencati qui.</span><span class="sxs-lookup"><span data-stu-id="678f0-164">Manually created topics are listed here as well.</span></span>

   ![Gestire gli argomenti](../media/knowledge-management/manage-topics-new.png) </br> 




