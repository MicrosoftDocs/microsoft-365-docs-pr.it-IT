---
title: 'Configurare la gestione delle informazioni (anteprima) '
description: Come configurare la gestione delle informazioni.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: d6495f297f09ddc167d7c36835ac82a15abc91ac
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405654"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="b537e-103">Configurare la gestione delle informazioni (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b537e-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="b537e-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="b537e-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="b537e-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="b537e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="b537e-106">È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per impostare e configurare la [gestione delle informazioni](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b537e-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="b537e-107">È importante pianificare il modo migliore per impostare e configurare la gestione della conoscenza nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="b537e-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="b537e-108">Ad esempio, è necessario prendere in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b537e-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="b537e-109">I siti di SharePoint che si desidera analizzare per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b537e-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="b537e-110">Gli utenti a cui si desidera rendere visibili gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b537e-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="b537e-111">Gli utenti che si desidera concedere le autorizzazioni per la gestione degli argomenti nell'argomento centro.</span><span class="sxs-lookup"><span data-stu-id="b537e-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="b537e-112">Gli utenti che si desidera concedere le autorizzazioni per la creazione o la modifica di argomenti nel centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="b537e-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="b537e-113">Il nome che si desidera assegnare al centro dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="b537e-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="b537e-114">Potrebbe essere utile creare gruppi di sicurezza per assegnare agli utenti le autorizzazioni necessarie per visualizzare gli argomenti, gestire l'argomento e creare e modificare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b537e-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="b537e-115">Un amministratore può anche [apportare modifiche alle impostazioni selezionate in qualsiasi momento dopo l'installazione](manage-knowledge-network.md) tramite le impostazioni di gestione delle informazioni nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b537e-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="b537e-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b537e-116">Requirements</span></span> 
<span data-ttu-id="b537e-117">È necessario disporre delle autorizzazioni di amministratore globale o di amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare le attività relative alla conoscenza organizzativa.</span><span class="sxs-lookup"><span data-stu-id="b537e-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="b537e-118">Configurare la rete di conoscenze</span><span class="sxs-lookup"><span data-stu-id="b537e-118">Set up your knowledge network</span></span>

<span data-ttu-id="b537e-119">Se si configura la rete della Knowledge base, è possibile effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="b537e-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="b537e-120">Individuazione dell'argomento: selezione di origini e argomenti di argomento da escludere dall'individuazione.</span><span class="sxs-lookup"><span data-stu-id="b537e-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="b537e-121">Visibilità sull'argomento: selezione degli utenti che possono visualizzare gli argomenti come elementi salienti, nelle pagine di ricerca e nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="b537e-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="b537e-122">Autorizzazioni per l'argomento: selezione degli utenti autorizzati a creare, modificare e gestire gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b537e-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="b537e-123">Centro argomenti: creare il centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="b537e-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="b537e-124">Revisione: controllare e applicare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b537e-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="b537e-125">Per configurare la rete delle informazioni:</span><span class="sxs-lookup"><span data-stu-id="b537e-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="b537e-126">Nell'interfaccia di amministrazione di Microsoft 365 (admin.microsoft.com), selezionare **Setup**e quindi visualizzare la sezione relativa alle **informazioni sull'organizzazione** .</span><span class="sxs-lookup"><span data-stu-id="b537e-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="b537e-127">Nella sezione **informazioni organizzative** fare clic su **Connetti persone alla conoscenza**.</span><span class="sxs-lookup"><span data-stu-id="b537e-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Connettere le persone alla conoscenza](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="b537e-129">Nella pagina **Connect people to Knowledge** fare clic su Guida **introduttiva** per eseguire il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="b537e-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Per iniziare](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="b537e-131">Nella pagina **scegliere il modo in cui la rete di informazioni può trovare gli argomenti** , verrà configurata l'individuazione dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="b537e-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="b537e-132">Nella sezione **selezione origini argomenti di SharePoint** selezionare i siti di SharePoint che verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="b537e-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="b537e-133">Ciò include:</span><span class="sxs-lookup"><span data-stu-id="b537e-133">This includes:</span></span></br>
    <span data-ttu-id="b537e-134">a.</span><span class="sxs-lookup"><span data-stu-id="b537e-134">a.</span></span> <span data-ttu-id="b537e-135">**Tutti i siti**: tutti i siti di SharePoint nel tenant.</span><span class="sxs-lookup"><span data-stu-id="b537e-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="b537e-136">Questo acquisisce i siti correnti e futuri.</span><span class="sxs-lookup"><span data-stu-id="b537e-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="b537e-137">b.</span><span class="sxs-lookup"><span data-stu-id="b537e-137">b.</span></span> <span data-ttu-id="b537e-138">**All, eccetto siti selezionati**: digitare i nomi dei siti che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="b537e-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="b537e-139">È inoltre possibile caricare un elenco di siti che si desidera escludere dall'individuazione.</span><span class="sxs-lookup"><span data-stu-id="b537e-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="b537e-140">I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b537e-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="b537e-141">c.</span><span class="sxs-lookup"><span data-stu-id="b537e-141">c.</span></span> <span data-ttu-id="b537e-142">**Solo siti selezionati**: digitare i nomi dei siti che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="b537e-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="b537e-143">È inoltre possibile caricare un elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="b537e-143">You can also upload a list of sites.</span></span> <span data-ttu-id="b537e-144">I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b537e-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Scegliere come trovare gli argomenti](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="b537e-146">Nella sezione **Escludi argomenti per nome** è possibile scegliere di includere i nomi degli argomenti che non si desidera siano inclusi nei risultati individuati.</span><span class="sxs-lookup"><span data-stu-id="b537e-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="b537e-147">Utilizzare questa impostazione per impedire l'inclusione di argomenti sensibili nell'ambito della rete della Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="b537e-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="b537e-148">Le opzioni includono:</span><span class="sxs-lookup"><span data-stu-id="b537e-148">Your options include:</span></span></br>
    <span data-ttu-id="b537e-149">a.</span><span class="sxs-lookup"><span data-stu-id="b537e-149">a.</span></span> <span data-ttu-id="b537e-150">**Non escludere argomenti**</span><span class="sxs-lookup"><span data-stu-id="b537e-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="b537e-151">b.</span><span class="sxs-lookup"><span data-stu-id="b537e-151">b.</span></span> <span data-ttu-id="b537e-152">**Escludi argomenti per nome**: se sono presenti argomenti che non si desidera vengano visualizzati dagli utenti nell'ambito della rete della Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="b537e-152">**Exclude topics by name**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span></br>

    ![Escludi argomenti](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="b537e-154">Come escludere gli argomenti per nome</span><span class="sxs-lookup"><span data-stu-id="b537e-154">How to exclude topics by name</span></span>    

    <span data-ttu-id="b537e-155">Se è necessario escludere gli argomenti, fare clic su **Scarica il modello. csv**dopo aver selezionato **Escludi argomenti per nome**.</span><span class="sxs-lookup"><span data-stu-id="b537e-155">If you need to exclude topics, after selecting **Exclude topics by name**, select **Download the .csv template**.</span></span> <span data-ttu-id="b537e-156">Utilizzare Excel. Modello CSV che include un elenco di argomenti che si desidera escludere dai risultati dell'individuazione.</span><span class="sxs-lookup"><span data-stu-id="b537e-156">Use the Excel .CSV template to include a list of topics that you want to exclude from your discovery results.</span></span>

    ![Escludi argomenti nel modello CSV](../media/content-understanding/csv1.png) </br>

    <span data-ttu-id="b537e-158">Nel modello CSV, immettere le informazioni seguenti sugli argomenti che si desidera escludere:</span><span class="sxs-lookup"><span data-stu-id="b537e-158">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="b537e-159">**Nome**: digitare il nome dell'argomento che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="b537e-159">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="b537e-160">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="b537e-160">There are two ways to do this:</span></span></br>
        - <span data-ttu-id="b537e-161">Corrispondenza esatta: è possibile includere il nome o l'acronimo esatto (ad esempio, *Contoso* o *ATL*).</span><span class="sxs-lookup"><span data-stu-id="b537e-161">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span></br>
        - <span data-ttu-id="b537e-162">Corrispondenza parziale: è possibile escludere tutti gli argomenti in cui è presente una parola specifica.</span><span class="sxs-lookup"><span data-stu-id="b537e-162">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="b537e-163">Ad esempio, *Arc* escluderà tutti gli argomenti con l' *arco* di parola in esso, ad esempio *cerchio arco*, *saldatura ad arco al plasma*o *arco di training*. Tenere presente che non verranno esclusi gli argomenti in cui il testo viene incluso come parte di una parola, ad esempio l' *architettura*.</span><span class="sxs-lookup"><span data-stu-id="b537e-163">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span></br>
    - <span data-ttu-id="b537e-164">**Espansione (facoltativo)**: se si desidera escludere un acronimo, digitare le parole in cui si trova l'acronimo.</span><span class="sxs-lookup"><span data-stu-id="b537e-164">**Expansion (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span></br>
    - <span data-ttu-id="b537e-165">**MatchType-exact/partial**: digitare se il nome immesso è un tipo di corrispondenza *esatta* o *parziale* .</span><span class="sxs-lookup"><span data-stu-id="b537e-165">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span></br>

    <span data-ttu-id="b537e-166">Dopo aver completato e salvato il file del modello CSV, selezionare **Sfoglia** per individuarlo e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="b537e-166">After you've completed and saved your CSV template file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="b537e-167">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b537e-167">Select **Next**.</span></span></br>

6. <span data-ttu-id="b537e-168">Negli **utenti che possono visualizzare gli argomenti e dove possono visualizzarli** , verrà configurata la visibilità dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="b537e-168">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="b537e-169">Negli **utenti che possono visualizzare gli argomenti nell'impostazione della rete di conoscenze** , scegliere chi avrà accesso ai dettagli sull'argomento, ad esempio argomenti evidenziati, schede argomento, risposte agli argomenti nelle pagine di ricerca e argomento.</span><span class="sxs-lookup"><span data-stu-id="b537e-169">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="b537e-170">È possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="b537e-170">You can select:</span></span></br>
    <span data-ttu-id="b537e-171">a.</span><span class="sxs-lookup"><span data-stu-id="b537e-171">a.</span></span> <span data-ttu-id="b537e-172">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="b537e-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="b537e-173">b.</span><span class="sxs-lookup"><span data-stu-id="b537e-173">b.</span></span> <span data-ttu-id="b537e-174">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="b537e-174">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="b537e-175">c.</span><span class="sxs-lookup"><span data-stu-id="b537e-175">c.</span></span> <span data-ttu-id="b537e-176">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="b537e-176">**No one**</span></span></br>

    ![Utenti autorizzati a visualizzare gli argomenti](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="b537e-178">Anche se questa impostazione consente di selezionare qualsiasi utente dell'organizzazione, solo gli utenti che dispongono di licenze di gestione delle informazioni assegnate potranno visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b537e-178">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="b537e-179">Nella pagina **autorizzazioni per gestione** argomenti scegliere gli utenti che potranno creare, modificare o gestire gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b537e-179">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="b537e-180">Nella sezione **utenti autorizzati a creare e modificare gli argomenti** , è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="b537e-180">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="b537e-181">a.</span><span class="sxs-lookup"><span data-stu-id="b537e-181">a.</span></span> <span data-ttu-id="b537e-182">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="b537e-182">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="b537e-183">b.</span><span class="sxs-lookup"><span data-stu-id="b537e-183">b.</span></span> <span data-ttu-id="b537e-184">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="b537e-184">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="b537e-185">Nella sezione **chi può gestire gli argomenti** è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="b537e-185">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="b537e-186">a.</span><span class="sxs-lookup"><span data-stu-id="b537e-186">a.</span></span> <span data-ttu-id="b537e-187">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="b537e-187">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="b537e-188">b.</span><span class="sxs-lookup"><span data-stu-id="b537e-188">b.</span></span> <span data-ttu-id="b537e-189">**Utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="b537e-189">**Selected people or security groups**</span></span></br>

    ![Autorizzazioni per la gestione degli argomenti](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="b537e-191">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b537e-191">Select **Next**.</span></span></br>
9. <span data-ttu-id="b537e-192">Nella pagina **Crea centro** argomenti è possibile creare il sito Centro argomenti in cui è possibile visualizzare le pagine degli argomenti e gestire i temi.</span><span class="sxs-lookup"><span data-stu-id="b537e-192">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="b537e-193">Nella casella **nome centro argomenti** Digitare un nome per il centro degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b537e-193">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="b537e-194">Facoltativamente, è possibile digitare una breve descrizione nella casella **Descrizione sito** .</span><span class="sxs-lookup"><span data-stu-id="b537e-194">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="b537e-195">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b537e-195">Select **Next**.</span></span></br>

   ![Creare centro informazioni](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="b537e-197">Nella pagina **revisione e fine** è possibile esaminare l'impostazione selezionata e scegliere di apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="b537e-197">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="b537e-198">Se si è soddisfatti delle selezioni, selezionare **attiva**.</span><span class="sxs-lookup"><span data-stu-id="b537e-198">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Fine e Revisione](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="b537e-200">Verrà visualizzata la pagina **rete informazioni attivata** che conferma che il sistema inizierà a analizzare i siti selezionati per gli argomenti e a creare il sito del centro informazioni.</span><span class="sxs-lookup"><span data-stu-id="b537e-200">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="b537e-201">Scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b537e-201">Select **Done**.</span></span></br>

    ![Attivato](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="b537e-203">Verrà restituito alla pagina **Connect people to Knowledge** .</span><span class="sxs-lookup"><span data-stu-id="b537e-203">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="b537e-204">Da questa pagina, è possibile selezionare **Gestisci** per apportare modifiche alle impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b537e-204">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Impostazioni applicate](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="b537e-206">Dopo l'installazione, un amministratore può [apportare modifiche alle impostazioni di gestione delle informazioni selezionate](manage-knowledge-network.md) in qualsiasi momento tornando alla pagina.</span><span class="sxs-lookup"><span data-stu-id="b537e-206">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="b537e-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b537e-207">See also</span></span>



  






