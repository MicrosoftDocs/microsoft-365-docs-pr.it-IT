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
ms.openlocfilehash: ba8cb8ceb3c98019099bfe5438d274c9d2b32280
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612549"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="b7236-103">Configurare la gestione delle informazioni (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b7236-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="b7236-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="b7236-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="b7236-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="b7236-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="b7236-106">È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per impostare e configurare la [gestione delle informazioni](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b7236-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="b7236-107">È importante pianificare il modo migliore per impostare e configurare la gestione della conoscenza nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="b7236-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="b7236-108">Ad esempio, è necessario prendere in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b7236-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="b7236-109">I siti di SharePoint che si desidera analizzare per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7236-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="b7236-110">Gli utenti a cui si desidera rendere visibili gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7236-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="b7236-111">Gli utenti che si desidera concedere le autorizzazioni per la gestione degli argomenti nell'argomento centro.</span><span class="sxs-lookup"><span data-stu-id="b7236-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="b7236-112">Gli utenti che si desidera concedere le autorizzazioni per la creazione o la modifica di argomenti nel centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7236-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="b7236-113">Il nome che si desidera assegnare al centro dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="b7236-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="b7236-114">Potrebbe essere utile creare gruppi di sicurezza per assegnare agli utenti le autorizzazioni necessarie per visualizzare gli argomenti, gestire l'argomento e creare e modificare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7236-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="b7236-115">Un amministratore può anche [apportare modifiche alle impostazioni selezionate in qualsiasi momento dopo l'installazione](manage-knowledge-network.md) tramite le impostazioni di gestione delle informazioni nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7236-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7236-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7236-116">Requirements</span></span> 
<span data-ttu-id="b7236-117">È necessario disporre delle autorizzazioni di amministratore globale o di amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare le attività relative alla conoscenza organizzativa.</span><span class="sxs-lookup"><span data-stu-id="b7236-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="b7236-118">Configurare la rete di conoscenze</span><span class="sxs-lookup"><span data-stu-id="b7236-118">Set up your knowledge network</span></span>

<span data-ttu-id="b7236-119">Se si configura la rete della Knowledge base, è possibile effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="b7236-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="b7236-120">Individuazione dell'argomento: selezione di origini e argomenti di argomento da escludere dall'individuazione.</span><span class="sxs-lookup"><span data-stu-id="b7236-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="b7236-121">Visibilità sull'argomento: selezione degli utenti che possono visualizzare gli argomenti come elementi salienti, nelle pagine di ricerca e nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="b7236-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="b7236-122">Autorizzazioni per l'argomento: selezione degli utenti autorizzati a creare, modificare e gestire gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7236-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="b7236-123">Centro argomenti: creare il centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7236-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="b7236-124">Revisione: controllare e applicare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b7236-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="b7236-125">Per configurare la rete delle informazioni:</span><span class="sxs-lookup"><span data-stu-id="b7236-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="b7236-126">Nell'interfaccia di amministrazione di Microsoft 365 (admin.microsoft.com), selezionare **Setup**e quindi visualizzare la sezione relativa alle **informazioni sull'organizzazione** .</span><span class="sxs-lookup"><span data-stu-id="b7236-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="b7236-127">Nella sezione **informazioni organizzative** fare clic su **Connetti persone alla conoscenza**.</span><span class="sxs-lookup"><span data-stu-id="b7236-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Connettere le persone alla conoscenza](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="b7236-129">Nella pagina **Connect people to Knowledge** fare clic su Guida **introduttiva** per eseguire il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="b7236-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Per iniziare](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="b7236-131">Nella pagina **scegliere il modo in cui la rete di informazioni può trovare gli argomenti** , verrà configurata l'individuazione dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="b7236-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="b7236-132">Nella sezione **selezione origini argomenti di SharePoint** selezionare i siti di SharePoint che verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="b7236-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="b7236-133">Questo include:</span><span class="sxs-lookup"><span data-stu-id="b7236-133">This includes:</span></span></br>
    <span data-ttu-id="b7236-134">a.</span><span class="sxs-lookup"><span data-stu-id="b7236-134">a.</span></span> <span data-ttu-id="b7236-135">**Tutti i siti**: tutti i siti di SharePoint nel tenant.</span><span class="sxs-lookup"><span data-stu-id="b7236-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="b7236-136">Questo acquisisce i siti correnti e futuri.</span><span class="sxs-lookup"><span data-stu-id="b7236-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="b7236-137">b.</span><span class="sxs-lookup"><span data-stu-id="b7236-137">b.</span></span> <span data-ttu-id="b7236-138">**All, eccetto siti selezionati**: digitare i nomi dei siti che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="b7236-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="b7236-139">È inoltre possibile caricare un elenco di siti che si desidera escludere dall'individuazione.</span><span class="sxs-lookup"><span data-stu-id="b7236-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="b7236-140">I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7236-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="b7236-141">c.</span><span class="sxs-lookup"><span data-stu-id="b7236-141">c.</span></span> <span data-ttu-id="b7236-142">**Solo siti selezionati**: digitare i nomi dei siti che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="b7236-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="b7236-143">È inoltre possibile caricare un elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="b7236-143">You can also upload a list of sites.</span></span> <span data-ttu-id="b7236-144">I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7236-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Scegliere come trovare gli argomenti](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="b7236-146">Nella sezione **Escludi argomenti per nome** è possibile scegliere di includere i nomi degli argomenti che non si desidera siano inclusi nei risultati individuati.</span><span class="sxs-lookup"><span data-stu-id="b7236-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="b7236-147">Utilizzare questa impostazione per impedire l'inclusione di argomenti sensibili nell'ambito della rete della Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="b7236-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="b7236-148">Le opzioni includono:</span><span class="sxs-lookup"><span data-stu-id="b7236-148">Your options include:</span></span></br>
    <span data-ttu-id="b7236-149">a.</span><span class="sxs-lookup"><span data-stu-id="b7236-149">a.</span></span> <span data-ttu-id="b7236-150">**Non escludere argomenti**</span><span class="sxs-lookup"><span data-stu-id="b7236-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="b7236-151">b.</span><span class="sxs-lookup"><span data-stu-id="b7236-151">b.</span></span> <span data-ttu-id="b7236-152">**Escludere l'argomento contenente i termini seguenti**: se sono presenti argomenti che non si desidera visualizzare agli utenti nell'ambito della rete della Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="b7236-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="b7236-153">-Scaricare il modello specificato.</span><span class="sxs-lookup"><span data-stu-id="b7236-153">- Download the provided template.</span></span>
   <span data-ttu-id="b7236-154">-Immettere i nomi degli argomenti che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="b7236-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="b7236-155">È necessario indicare il tipo di corrispondenza come esatto o parziale.</span><span class="sxs-lookup"><span data-stu-id="b7236-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="b7236-156">Corrispondenza esatta significa che gli argomenti che corrispondono al termine esatto verranno esclusi.</span><span class="sxs-lookup"><span data-stu-id="b7236-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="b7236-157">La corrispondenza parziale è più rigorosa e significa che verranno esclusi gli argomenti che contengono il termine.</span><span class="sxs-lookup"><span data-stu-id="b7236-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="b7236-158">Ad esempio, se si immette *doc* come nome dell'argomento, l' *assembly doc* verrà escluso mentre il *Docker* non lo farà.</span><span class="sxs-lookup"><span data-stu-id="b7236-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="b7236-159">I nomi degli argomenti sono case insensitive.</span><span class="sxs-lookup"><span data-stu-id="b7236-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="b7236-160">-Selezionare questa impostazione  **+**   per importare il file CSV completato.</span><span class="sxs-lookup"><span data-stu-id="b7236-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="b7236-161">Selezionare **carica**.</span><span class="sxs-lookup"><span data-stu-id="b7236-161">Then select **Upload**.</span></span> <span data-ttu-id="b7236-162">Se il file è stato elaborato correttamente, verrà visualizzato un segno di spunta verde.</span><span class="sxs-lookup"><span data-stu-id="b7236-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="b7236-163">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b7236-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="b7236-164">Negli **utenti che possono visualizzare gli argomenti e dove possono visualizzarli** , verrà configurata la visibilità dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="b7236-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="b7236-165">Negli **utenti che possono visualizzare gli argomenti nell'impostazione della rete di conoscenze** , scegliere chi avrà accesso ai dettagli sull'argomento, ad esempio argomenti evidenziati, schede argomento, risposte agli argomenti nelle pagine di ricerca e argomento.</span><span class="sxs-lookup"><span data-stu-id="b7236-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="b7236-166">È possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="b7236-166">You can select:</span></span></br>
    <span data-ttu-id="b7236-167">a.</span><span class="sxs-lookup"><span data-stu-id="b7236-167">a.</span></span> <span data-ttu-id="b7236-168">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="b7236-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="b7236-169">b.</span><span class="sxs-lookup"><span data-stu-id="b7236-169">b.</span></span> <span data-ttu-id="b7236-170">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="b7236-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="b7236-171">c.</span><span class="sxs-lookup"><span data-stu-id="b7236-171">c.</span></span> <span data-ttu-id="b7236-172">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="b7236-172">**No one**</span></span></br>

    ![Utenti autorizzati a visualizzare gli argomenti](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="b7236-174">Anche se questa impostazione consente di selezionare qualsiasi utente dell'organizzazione, solo gli utenti che dispongono di licenze di gestione delle informazioni assegnate potranno visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7236-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="b7236-175">Nella pagina **autorizzazioni per gestione** argomenti scegliere gli utenti che potranno creare, modificare o gestire gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7236-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="b7236-176">Nella sezione **utenti autorizzati a creare e modificare gli argomenti** , è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="b7236-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="b7236-177">a.</span><span class="sxs-lookup"><span data-stu-id="b7236-177">a.</span></span> <span data-ttu-id="b7236-178">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="b7236-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="b7236-179">b.</span><span class="sxs-lookup"><span data-stu-id="b7236-179">b.</span></span> <span data-ttu-id="b7236-180">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="b7236-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="b7236-181">Nella sezione **chi può gestire gli argomenti** è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="b7236-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="b7236-182">a.</span><span class="sxs-lookup"><span data-stu-id="b7236-182">a.</span></span> <span data-ttu-id="b7236-183">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="b7236-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="b7236-184">b.</span><span class="sxs-lookup"><span data-stu-id="b7236-184">b.</span></span> <span data-ttu-id="b7236-185">**Utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="b7236-185">**Selected people or security groups**</span></span></br>

    ![Autorizzazioni per la gestione degli argomenti](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="b7236-187">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b7236-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="b7236-188">Nella pagina **Crea centro** argomenti è possibile creare il sito Centro argomenti in cui è possibile visualizzare le pagine degli argomenti e gestire i temi.</span><span class="sxs-lookup"><span data-stu-id="b7236-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="b7236-189">Nella casella **nome centro argomenti** Digitare un nome per il centro degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="b7236-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="b7236-190">Facoltativamente, è possibile digitare una breve descrizione nella casella **Descrizione sito** .</span><span class="sxs-lookup"><span data-stu-id="b7236-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="b7236-191">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b7236-191">Select **Next**.</span></span></br>

   ![Creare centro informazioni](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="b7236-193">Nella pagina **revisione e fine** è possibile esaminare l'impostazione selezionata e scegliere di apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="b7236-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="b7236-194">Se si è soddisfatti delle selezioni, selezionare **attiva**.</span><span class="sxs-lookup"><span data-stu-id="b7236-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Fine e Revisione](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="b7236-196">Verrà visualizzata la pagina **rete informazioni attivata** che conferma che il sistema inizierà a analizzare i siti selezionati per gli argomenti e a creare il sito del centro informazioni.</span><span class="sxs-lookup"><span data-stu-id="b7236-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="b7236-197">Scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b7236-197">Select **Done**.</span></span></br>

    ![Attivato](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="b7236-199">Verrà restituito alla pagina **Connect people to Knowledge** .</span><span class="sxs-lookup"><span data-stu-id="b7236-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="b7236-200">Da questa pagina, è possibile selezionare **Gestisci** per apportare modifiche alle impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b7236-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Impostazioni applicate](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="b7236-202">Dopo l'installazione, un amministratore può [apportare modifiche alle impostazioni di gestione delle informazioni selezionate](manage-knowledge-network.md) in qualsiasi momento tornando alla pagina.</span><span class="sxs-lookup"><span data-stu-id="b7236-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="b7236-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7236-203">See also</span></span>



  






