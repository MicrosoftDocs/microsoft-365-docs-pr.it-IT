---
title: Eseguire una versione di valutazione di Microsoft Viva Topics
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: Informazioni su come pianificare ed eseguire un programma pilota di valutazione per Microsoft Viva Topics nell'organizzazione.
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327114"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a><span data-ttu-id="343d4-103">Eseguire una versione di valutazione di Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="343d4-103">Run a trial of Microsoft Viva Topics</span></span>

<span data-ttu-id="343d4-104">In questo articolo viene descritto come configurare ed eseguire un programma pilota di prova per distribuire Viva Topics nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="343d4-104">This article describes how to set up and run a trial pilot program to deploy Viva Topics to your organization.</span></span> <span data-ttu-id="343d4-105">In questo articolo vengono inoltre consigliate le procedure consigliate per la versione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="343d4-105">This article also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="343d4-106">Iscriversi per una versione di valutazione</span><span class="sxs-lookup"><span data-stu-id="343d4-106">Sign up for a trial</span></span>

<span data-ttu-id="343d4-107">Le versioni di valutazione sono disponibili pubblicamente da una delle origini seguenti.</span><span class="sxs-lookup"><span data-stu-id="343d4-107">Trials are publicly available from one of the following sources.</span></span> <span data-ttu-id="343d4-108">Queste versioni di valutazione offrono a 25 utenti l'accesso a Viva Topics per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="343d4-108">These trials offer 25 users access to Viva Topics for 30 days.</span></span>

- <span data-ttu-id="343d4-109">Pagina [del prodotto Viva Topics](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="343d4-109">The [Viva Topics product page](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="343d4-110">Il [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="343d4-110">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="343d4-111">Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="343d4-111">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="343d4-112">Vai a **Fatturazione**  >  **Servizi di acquisto.**</span><span class="sxs-lookup"><span data-stu-id="343d4-112">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="343d4-113">Scorrere fino al pulsante **Componenti aggiuntivi**.</span><span class="sxs-lookup"><span data-stu-id="343d4-113">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="343d4-114">Nel riquadro **Esperienze argomento** seleziona **Dettagli.**</span><span class="sxs-lookup"><span data-stu-id="343d4-114">On the **Topic Experiences** tile, select **Details**.</span></span>
    5.  <span data-ttu-id="343d4-115">Selezionare **Ottieni una versione di valutazione gratuita**.</span><span class="sxs-lookup"><span data-stu-id="343d4-115">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="343d4-116">Segui i passaggi rimanenti della procedura guidata per confermare la versione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="343d4-116">Follow the remaining wizard steps to confirm the trial.</span></span>

<span data-ttu-id="343d4-117">È necessario essere un amministratore Microsoft 365 globale o un amministratore di fatturazione per attivare una versione di valutazione.</span><span class="sxs-lookup"><span data-stu-id="343d4-117">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

> [!NOTE]
> <span data-ttu-id="343d4-118">Le versioni di valutazione pubbliche possono essere aggiunte una sola volta per ogni tenant Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="343d4-118">Public trials can only be added once for each Microsoft 365 tenant.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="343d4-119">Who essere coinvolto in una versione di valutazione</span><span class="sxs-lookup"><span data-stu-id="343d4-119">Who should be involved in a trial</span></span>

|<span data-ttu-id="343d4-120">Ruolo</span><span class="sxs-lookup"><span data-stu-id="343d4-120">Role</span></span>  |<span data-ttu-id="343d4-121">Attività</span><span class="sxs-lookup"><span data-stu-id="343d4-121">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="343d4-122">Microsoft 365 amministratore globale o amministratore fatturazione</span><span class="sxs-lookup"><span data-stu-id="343d4-122">Microsoft 365 global admin or billing admin</span></span>  |   <span data-ttu-id="343d4-123">Attivare la versione di valutazione e assegnare le licenze</span><span class="sxs-lookup"><span data-stu-id="343d4-123">Activate the trial and assign licenses</span></span>      |
|<span data-ttu-id="343d4-124">Microsoft 365 amministratore globale o SharePoint amministratore globale</span><span class="sxs-lookup"><span data-stu-id="343d4-124">Microsoft 365 global admin or SharePoint admin</span></span>    |       <span data-ttu-id="343d4-125">Configurare Viva Topics e creare centri argomenti</span><span class="sxs-lookup"><span data-stu-id="343d4-125">Configure  Viva Topics and create topic centers</span></span>  |
|<span data-ttu-id="343d4-126">Utente aziendale</span><span class="sxs-lookup"><span data-stu-id="343d4-126">Business user</span></span>     |   <span data-ttu-id="343d4-127">Eseguire ruoli di knowledge manager, collaboratore di argomenti e consumer di argomenti</span><span class="sxs-lookup"><span data-stu-id="343d4-127">Perform knowledge manager, topic contributor, and topic consumer roles</span></span>      |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="343d4-128">Prima di attivare una versione di valutazione</span><span class="sxs-lookup"><span data-stu-id="343d4-128">Before you activate a trial</span></span>

<span data-ttu-id="343d4-129">La pianificazione è essenziale per una versione di valutazione efficace di Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="343d4-129">Planning is essential for an effective trial of Viva Topics.</span></span> <span data-ttu-id="343d4-130">Il periodo di valutazione è limitato e deve includere l'individuazione degli argomenti e l'esplorazione della qualità, della gestione e delle esperienze degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="343d4-130">The trial period is limited and must include topic discovery and exploring topic quality, management, and end-user experiences.</span></span>

#### <a name="discovery"></a><span data-ttu-id="343d4-131">Individuazione</span><span class="sxs-lookup"><span data-stu-id="343d4-131">Discovery</span></span>

<span data-ttu-id="343d4-132">Esistono due opzioni di strategia di alto livello per la configurazione dell'individuazione degli argomenti durante una versione di valutazione:</span><span class="sxs-lookup"><span data-stu-id="343d4-132">There are two high-level strategy options for configuration of topic discovery during a trial:</span></span>

- <span data-ttu-id="343d4-133">Indicizza tutto o la maggior parte del SharePoint online.</span><span class="sxs-lookup"><span data-stu-id="343d4-133">Index all or most of your SharePoint Online content.</span></span>
   - <span data-ttu-id="343d4-134">I tenant di grandi dimensioni possono richiedere fino a due settimane per l'indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="343d4-134">Large tenants can take up to two weeks to fully index.</span></span> <span data-ttu-id="343d4-135">Anche se gli argomenti verranno generati in modo incrementale durante questo periodo, l'indicizzazione completa potrebbe consumare fino alla metà del periodo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="343d4-135">While topics will be generated incrementally throughout this period, full indexing could consume up to half the trial period.</span></span>
   - <span data-ttu-id="343d4-136">Per i tenant con un volume significativo di dati, questa opzione può produrre un numero molto elevato di argomenti, ad esempio decine di migliaia.</span><span class="sxs-lookup"><span data-stu-id="343d4-136">For tenants with a significant volume of data, this option can produce a very large number of topics, perhaps tens of thousands.</span></span>

- <span data-ttu-id="343d4-137">Identificare un sottoinsieme dei siti SharePoint per l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="343d4-137">Identify a subset of your SharePoint sites for indexing.</span></span>

<span data-ttu-id="343d4-138">La scelta di queste strategie è un equilibrio tra i due fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="343d4-138">The choice of these strategies is a balance of the following two factors:</span></span>

- <span data-ttu-id="343d4-139">Dati sufficienti per generare argomenti significativi.</span><span class="sxs-lookup"><span data-stu-id="343d4-139">Having enough data to generate meaningful topics.</span></span> <span data-ttu-id="343d4-140">L'IA in Viva Topics è ottimizzata per lavorare su set di dati di grandi dimensioni, idealmente con più di 10.000 documenti.</span><span class="sxs-lookup"><span data-stu-id="343d4-140">The AI in Viva Topics is tuned to work on large datasets, ideally ones that have more than 10,000 documents.</span></span>
- <span data-ttu-id="343d4-141">Non generare così tanti argomenti durante il periodo di prova che valutarli durante il periodo di tempo disponibile è travolgente.</span><span class="sxs-lookup"><span data-stu-id="343d4-141">Not generating so many topics during the trial period that evaluating them during the available time period is overwhelming.</span></span>

<span data-ttu-id="343d4-142">Per la maggior parte delle organizzazioni, la seconda strategia produce il risultato migliore.</span><span class="sxs-lookup"><span data-stu-id="343d4-142">For most organizations, the second strategy produces the best outcome.</span></span>

> [!NOTE]
> <span data-ttu-id="343d4-143">A causa del numero di documenti richiesti dall'IA, è consigliabile eseguire le versioni di valutazione viva topics in un tenant di produzione.</span><span class="sxs-lookup"><span data-stu-id="343d4-143">Due to the number of documents required by the AI, we recommend that you run Viva Topics trials on a production tenant.</span></span> <span data-ttu-id="343d4-144">Non c'è alcun impatto sulle prestazioni del tenant durante questo periodo.</span><span class="sxs-lookup"><span data-stu-id="343d4-144">There’s no impact on the performance of the tenant during this period.</span></span> <span data-ttu-id="343d4-145">Solo gli utenti che dispongono di una licenza di valutazione possono accedere alle esperienze utente di Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="343d4-145">Only users who have a trial license can access Viva Topics user experiences.</span></span>

#### <a name="roles"></a><span data-ttu-id="343d4-146">Ruoli</span><span class="sxs-lookup"><span data-stu-id="343d4-146">Roles</span></span>

<span data-ttu-id="343d4-147">Durante la versione di valutazione, è necessario che siano attivi tre ruoli, descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="343d4-147">During the trial, there are three roles that must be active, which are described in the following table.</span></span>

|<span data-ttu-id="343d4-148">Ruolo</span><span class="sxs-lookup"><span data-stu-id="343d4-148">Role</span></span>  |<span data-ttu-id="343d4-149">Attività</span><span class="sxs-lookup"><span data-stu-id="343d4-149">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="343d4-150">Responsabile delle informazioni</span><span class="sxs-lookup"><span data-stu-id="343d4-150">Knowledge manager</span></span>     |   <span data-ttu-id="343d4-151">Controllare le fasi del ciclo di vita degli argomenti; confermare e rimuovere argomenti; agire come community manager per i collaboratori di argomenti</span><span class="sxs-lookup"><span data-stu-id="343d4-151">Control the lifecycle stages of topics; confirm and remove topics; act as a community manager for topic contributors</span></span>      |
|<span data-ttu-id="343d4-152">Collaboratore dell'argomento</span><span class="sxs-lookup"><span data-stu-id="343d4-152">Topic contributor</span></span>    |      <span data-ttu-id="343d4-153">Esperti in materia di contenuto, che possono:</span><span class="sxs-lookup"><span data-stu-id="343d4-153">Content subject matter experts, who can:</span></span><br> <span data-ttu-id="343d4-154">Esaminare gli argomenti per valutare la qualità del contenuto definito dall'IA</span><span class="sxs-lookup"><span data-stu-id="343d4-154">Review topics to evaluate the quality of AI-defined content</span></span><br><span data-ttu-id="343d4-155">Cura gli argomenti individuati con contenuto aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="343d4-155">Curate discovered topics with additional content</span></span><br><span data-ttu-id="343d4-156">Creare argomenti aggiuntivi che non sono stati individuati dall'IA</span><span class="sxs-lookup"><span data-stu-id="343d4-156">Create additional topics that weren’t discovered by AI</span></span>   |
|<span data-ttu-id="343d4-157">Consumer argomento</span><span class="sxs-lookup"><span data-stu-id="343d4-157">Topic consumer</span></span>    |     <span data-ttu-id="343d4-158">Usare gli argomenti tramite le evidenziazioni delle pagine e la ricerca</span><span class="sxs-lookup"><span data-stu-id="343d4-158">Consume topics through page highlights and search</span></span><br><span data-ttu-id="343d4-159">Fornire feedback sul valore degli argomenti presentati</span><span class="sxs-lookup"><span data-stu-id="343d4-159">Provide feedback on the value of the topics presented</span></span>    |

#### <a name="expected-topics"></a><span data-ttu-id="343d4-160">Argomenti previsti</span><span class="sxs-lookup"><span data-stu-id="343d4-160">Expected topics</span></span>

<span data-ttu-id="343d4-161">Può essere utile documentare gli argomenti che si prevede di generare dall'IA, anche se si basa solo su presupposti.</span><span class="sxs-lookup"><span data-stu-id="343d4-161">It can be useful to document the topics you expect to be generated by the AI, even if this is based only on assumptions.</span></span> <span data-ttu-id="343d4-162">Questa attività viene completata più facilmente quando si indicizza un sottoinsieme definito dei siti SharePoint per i quali le PMI possono essere facilmente identificate.</span><span class="sxs-lookup"><span data-stu-id="343d4-162">This task is most easily completed when you index a defined subset of your SharePoint sites for which SMEs can be easily identified.</span></span>

<span data-ttu-id="343d4-163">La presenza di un elenco documentato consente di:</span><span class="sxs-lookup"><span data-stu-id="343d4-163">Having a documented list will help you to:</span></span>

- <span data-ttu-id="343d4-164">Esamina l'elenco degli argomenti generati dall'IA, che potrebbero essere più grandi del previsto.</span><span class="sxs-lookup"><span data-stu-id="343d4-164">Review the list of AI-generated topics, which might be larger than you expect.</span></span>
- <span data-ttu-id="343d4-165">Conoscere gli argomenti che potrebbe essere necessario creare manualmente o che sono le priorità per la curazione.</span><span class="sxs-lookup"><span data-stu-id="343d4-165">Know the topics you might need to manually create or that are priorities for curation.</span></span>

<span data-ttu-id="343d4-166">Ci sarà sempre bisogno di una combinazione di argomenti definiti dall'IA e creati dall'utente in una corretta distribuzione o prova di Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="343d4-166">There will always be a need for a mixture of AI-defined and human-created topics in a successful deployment or trial of Viva Topics.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="343d4-167">Attivare una versione di valutazione</span><span class="sxs-lookup"><span data-stu-id="343d4-167">Activate a trial</span></span>

<span data-ttu-id="343d4-168">Quando avvii una versione di valutazione, devi:</span><span class="sxs-lookup"><span data-stu-id="343d4-168">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="343d4-169">Assegnare licenze agli utenti pertinenti.</span><span class="sxs-lookup"><span data-stu-id="343d4-169">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="343d4-170">Eseguire [la configurazione aggiuntiva](set-up-topic-experiences.md) di Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="343d4-170">Perform [additional setup](set-up-topic-experiences.md) of Viva Topics.</span></span>

<span data-ttu-id="343d4-171">Quando la versione di valutazione viene attivata, inizia il processo di individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="343d4-171">When the trial is activated, the topic discovery process begins.</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="343d4-172">Durante una versione di valutazione</span><span class="sxs-lookup"><span data-stu-id="343d4-172">During a trial</span></span>

<span data-ttu-id="343d4-173">Il periodo di prova deve essere utilizzato per valutare i seguenti componenti di Viva Topics:</span><span class="sxs-lookup"><span data-stu-id="343d4-173">The trial period should be used to evaluate the following components of Viva Topics:</span></span>

- <span data-ttu-id="343d4-174">Argomenti suggeriti dall'IA e contenuto degli argomenti</span><span class="sxs-lookup"><span data-stu-id="343d4-174">The AI-suggested topics and topic content</span></span>
- <span data-ttu-id="343d4-175">Le esperienze dell'utente finale, le schede degli argomenti in SharePoint e in Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="343d4-175">The end-user experiences, surfacing topic cards on modern SharePoint pages and in Microsoft Search</span></span>

<span data-ttu-id="343d4-176">Prendere in considerazione questi fattori:</span><span class="sxs-lookup"><span data-stu-id="343d4-176">Consider these factors:</span></span>

- <span data-ttu-id="343d4-177">Per offrire il massimo valore a Viva Topics, il contenuto degli argomenti deve essere una combinazione di contenuto definito dall'IA e contenuto curato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="343d4-177">For Viva Topics to deliver the maximum value, the content in topics needs to be a combination of AI-defined content and human-curated content.</span></span>
- <span data-ttu-id="343d4-178">Tutte le esperienze utente vengono "tagliate le autorizzazioni" (inclusa la visualizzazione del responsabile della conoscenza nella **pagina Gestisci** argomenti).</span><span class="sxs-lookup"><span data-stu-id="343d4-178">All user experiences are “permission trimmed” (including the knowledge manager’s view on the **Manage topics** page).</span></span> <span data-ttu-id="343d4-179">Gli utenti potranno visualizzare un argomento solo se dispongono delle autorizzazioni per visualizzare alcune delle risorse utilizzate per generare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="343d4-179">Users will only see a topic if they have permissions to view some of the resources that were used to generate the topic.</span></span> <span data-ttu-id="343d4-180">Ciò significa che utenti diversi potrebbero visualizzare contenuto diverso nella stessa pagina dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="343d4-180">This means that different users might see different content on the same topic page.</span></span>
- <span data-ttu-id="343d4-181">Gli utenti potrebbero visualizzare più argomenti con lo stesso nome nella **pagina Gestisci** argomenti.</span><span class="sxs-lookup"><span data-stu-id="343d4-181">Users might see multiple topics that have the same name in the **Manage topics** page.</span></span> <span data-ttu-id="343d4-182">Questi argomenti non sono necessariamente duplicati, ma possono essere a causa di un singolo termine utilizzato in più contesti nei dati, ad esempio un nome di codice di progetto utilizzato da due progetti distinti.</span><span class="sxs-lookup"><span data-stu-id="343d4-182">These topics aren't necessarily duplicates but might be because of a single term that’s used in multiple contexts in the data, such as a project code name that’s used by two distinct projects.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="343d4-183">Dopo una versione di valutazione</span><span class="sxs-lookup"><span data-stu-id="343d4-183">After a trial</span></span>

<span data-ttu-id="343d4-184">In base al risultato della versione di valutazione, è possibile decidere se procedere con l'uso in produzione di Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="343d4-184">Based on the outcome of the trial, you can decide whether to proceed to production use of Viva Topics.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="343d4-185">Passare all'uso in produzione</span><span class="sxs-lookup"><span data-stu-id="343d4-185">Proceed to production use</span></span>

<span data-ttu-id="343d4-186">Per garantire la continuità del servizio, è necessario acquistare il numero necessario di licenze e assegnarle agli utenti.</span><span class="sxs-lookup"><span data-stu-id="343d4-186">To ensure continuity of service, you must purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="343d4-187">Gli utenti di prova che non dispongono di una licenza completa alla fine del periodo di prova non potranno accedere ad alcuna esperienza Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="343d4-187">Trial users who don’t have a full license at the end of the trial period won’t be able to access any Viva Topics experiences.</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="343d4-188">Non procedere con l'uso in produzione</span><span class="sxs-lookup"><span data-stu-id="343d4-188">Don’t proceed to production use</span></span>

<span data-ttu-id="343d4-189">Se non acquisti licenze dopo la versione di valutazione:</span><span class="sxs-lookup"><span data-stu-id="343d4-189">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="343d4-190">L'individuazione degli argomenti verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="343d4-190">Topic discovery will stop.</span></span>
- <span data-ttu-id="343d4-191">Gli utenti non potranno più visualizzare le evidenziazioni o le schede degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="343d4-191">Users will no longer see topic highlights or cards.</span></span>
- <span data-ttu-id="343d4-192">Il Centro argomenti non verrà eliminato, ma gli argomenti suggeriti e le esperienze di gestione degli argomenti non saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="343d4-192">The topic center won’t be deleted, but the suggested topics and manage topics experiences won’t be available.</span></span>
- <span data-ttu-id="343d4-193">Tutti gli argomenti definiti dall'IA andranno persi.</span><span class="sxs-lookup"><span data-stu-id="343d4-193">Any AI-defined topics will be lost.</span></span>
- <span data-ttu-id="343d4-194">Gli argomenti modificati da un collaboratore di argomenti rimarranno nella raccolta pagine del Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="343d4-194">Topics that have been edited by a topic contributor will remain in the topic center pages library.</span></span> <span data-ttu-id="343d4-195">Solo il contenuto fornito manualmente rimarrà in queste pagine, non qualsiasi contenuto suggerito dall'IA.</span><span class="sxs-lookup"><span data-stu-id="343d4-195">Only the manually provided content will remain on these pages, not any AI-suggested content.</span></span>

## <a name="see-also"></a><span data-ttu-id="343d4-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="343d4-196">See also</span></span>

[<span data-ttu-id="343d4-197">Introduzione all'adozione di Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="343d4-197">Get started driving adoption of Microsoft Viva Topics</span></span>](topics-adoption-getstarted.md)

