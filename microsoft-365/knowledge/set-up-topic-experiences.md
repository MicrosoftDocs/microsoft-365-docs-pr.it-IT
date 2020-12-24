---
title: Configurare le esperienze degli argomenti in Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come configurare le esperienze degli argomenti in Microsoft 365
ms.openlocfilehash: df4dccead4b627a215ec7ebd11932aa0f2b6ac08
ms.sourcegitcommit: 18f95c4b7f74881b4a6ce71ad2ffa78a6ead5584
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731368"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="ced9b-103">Configurare le esperienze degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ced9b-103">Set up topic experiences in Microsoft 365</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LBp7]  

</br>

<span data-ttu-id="ced9b-104">È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per impostare e configurare le [esperienze degli argomenti](topic-experiences-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ced9b-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="ced9b-105">È importante pianificare il modo migliore per impostare e configurare gli argomenti nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="ced9b-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="ced9b-106">Prima di iniziare le procedure descritte in questo articolo, leggere l' [argomento piano Experience](plan-topic-experiences.md) .</span><span class="sxs-lookup"><span data-stu-id="ced9b-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="ced9b-107">È necessario essere un amministratore globale o un amministratore di SharePoint per accedere all'interfaccia di amministrazione di Microsoft 365 e impostare le esperienze degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ced9b-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="ced9b-108">Configurare le esperienze dell'argomento</span><span class="sxs-lookup"><span data-stu-id="ced9b-108">Set up topic experiences</span></span>

<span data-ttu-id="ced9b-109">Per impostare le esperienze degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ced9b-109">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="ced9b-110">Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com)selezionare **Setup** e quindi visualizzare la sezione **file e contenuto** .</span><span class="sxs-lookup"><span data-stu-id="ced9b-110">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="ced9b-111">Nella sezione **file e contenuto** fare clic su **Connetti persone alla conoscenza**.</span><span class="sxs-lookup"><span data-stu-id="ced9b-111">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Connettere le persone alla conoscenza](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="ced9b-113">Nella pagina **Connect people to Knowledge** fare clic su Guida **introduttiva** per eseguire il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="ced9b-113">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Per iniziare](../media/k-get-started.png) 

4. <span data-ttu-id="ced9b-115">Nella pagina **scegliere il modo in cui la rete di informazioni può trovare gli argomenti** , verrà configurata l'individuazione dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="ced9b-115">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="ced9b-116">Nella sezione **selezione origini argomenti di SharePoint** selezionare i siti di SharePoint che verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="ced9b-116">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="ced9b-117">Scegliere da:</span><span class="sxs-lookup"><span data-stu-id="ced9b-117">Choose from:</span></span>
    - <span data-ttu-id="ced9b-118">**Tutti i siti**: tutti i siti di SharePoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ced9b-118">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="ced9b-119">Sono inclusi i siti correnti e futuri.</span><span class="sxs-lookup"><span data-stu-id="ced9b-119">This includes current and future sites.</span></span>
    - <span data-ttu-id="ced9b-120">**All, eccetto siti selezionati**: digitare i nomi dei siti che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="ced9b-120">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="ced9b-121">È inoltre possibile caricare un elenco di siti che si desidera escludere dall'individuazione.</span><span class="sxs-lookup"><span data-stu-id="ced9b-121">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="ced9b-122">I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ced9b-122">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="ced9b-123">**Solo siti selezionati**: digitare i nomi dei siti che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="ced9b-123">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="ced9b-124">È inoltre possibile caricare un elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="ced9b-124">You can also upload a list of sites.</span></span> <span data-ttu-id="ced9b-125">I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ced9b-125">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="ced9b-126">**Nessun sito**: non includere alcun sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ced9b-126">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Scegliere come trovare gli argomenti](../media/ksetup1.png) 
   
5. <span data-ttu-id="ced9b-128">Nella sezione **Escludi argomenti per nome** è possibile aggiungere i nomi degli argomenti che si desidera escludere dall'individuazione dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="ced9b-128">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="ced9b-129">Utilizzare questa impostazione per impedire l'inclusione di informazioni riservate come argomenti.</span><span class="sxs-lookup"><span data-stu-id="ced9b-129">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="ced9b-130">Le opzioni sono:</span><span class="sxs-lookup"><span data-stu-id="ced9b-130">The options are:</span></span>
    - <span data-ttu-id="ced9b-131">**Non escludere argomenti**</span><span class="sxs-lookup"><span data-stu-id="ced9b-131">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="ced9b-132">**Escludi argomenti per nome**</span><span class="sxs-lookup"><span data-stu-id="ced9b-132">**Exclude topics by name**</span></span>

    ![Escludi argomenti](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="ced9b-134">I Knowledge Manager possono anche escludere gli argomenti nell'argomento centro dopo l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="ced9b-134">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="ced9b-135">Come escludere gli argomenti per nome</span><span class="sxs-lookup"><span data-stu-id="ced9b-135">How to exclude topics by name</span></span>    

    <span data-ttu-id="ced9b-136">Se è necessario escludere gli argomenti, dopo aver selezionato **Escludi argomenti per nome**, selezionare Scarica il modello CSV e aggiornarlo con l'elenco di argomenti che si desidera escludere dai risultati dell'individuazione.</span><span class="sxs-lookup"><span data-stu-id="ced9b-136">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Escludi argomenti nel modello CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="ced9b-138">Nel modello CSV, immettere le informazioni seguenti sugli argomenti che si desidera escludere:</span><span class="sxs-lookup"><span data-stu-id="ced9b-138">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="ced9b-139">**Nome**: digitare il nome dell'argomento che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="ced9b-139">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="ced9b-140">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="ced9b-140">There are two ways to do this:</span></span>
        - <span data-ttu-id="ced9b-141">Corrispondenza esatta: è possibile includere il nome o l'acronimo esatto (ad esempio, *Contoso* o *ATL*).</span><span class="sxs-lookup"><span data-stu-id="ced9b-141">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="ced9b-142">Corrispondenza parziale: è possibile escludere tutti gli argomenti in cui è presente una parola specifica.</span><span class="sxs-lookup"><span data-stu-id="ced9b-142">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="ced9b-143">Ad esempio, *Arc* escluderà tutti gli argomenti con l' *arco* di parola in esso, ad esempio *cerchio arco*, *saldatura ad arco al plasma* o *arco di training*. Tenere presente che non verranno esclusi gli argomenti in cui il testo viene incluso come parte di una parola, ad esempio l' *architettura*.</span><span class="sxs-lookup"><span data-stu-id="ced9b-143">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="ced9b-144">Acronimo **di (facoltativo)**: se si desidera escludere un acronimo, digitare le parole in cui si trova l'acronimo.</span><span class="sxs-lookup"><span data-stu-id="ced9b-144">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="ced9b-145">**MatchType-exact/partial**: digitare se il nome immesso è un tipo di corrispondenza *esatta* o *parziale* .</span><span class="sxs-lookup"><span data-stu-id="ced9b-145">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="ced9b-146">Dopo aver completato e salvato il file. csv, selezionare **Sfoglia** per individuarlo e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="ced9b-146">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="ced9b-147">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ced9b-147">Select **Next**.</span></span>

6. <span data-ttu-id="ced9b-148">Negli **utenti che possono visualizzare gli argomenti e dove possono visualizzarli** , verrà configurata la visibilità dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="ced9b-148">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="ced9b-149">Negli **utenti che possono visualizzare gli argomenti nell'impostazione della rete di conoscenze** , scegliere chi avrà accesso ai dettagli sull'argomento, ad esempio argomenti evidenziati, schede argomento, risposte agli argomenti nelle pagine di ricerca e argomento.</span><span class="sxs-lookup"><span data-stu-id="ced9b-149">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="ced9b-150">È possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="ced9b-150">You can select:</span></span>
    - <span data-ttu-id="ced9b-151">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="ced9b-151">**Everyone in my organization**</span></span>
    - <span data-ttu-id="ced9b-152">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="ced9b-152">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="ced9b-153">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="ced9b-153">**No one**</span></span>

    ![Utenti autorizzati a visualizzare gli argomenti](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="ced9b-155">Anche se questa impostazione consente di selezionare qualsiasi utente dell'organizzazione, solo gli utenti che dispongono di licenze per l'argomento sono in grado di visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ced9b-155">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="ced9b-156">Nella pagina **autorizzazioni per gestione** argomenti scegliere gli utenti che potranno creare, modificare o gestire gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ced9b-156">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="ced9b-157">Nella sezione **utenti autorizzati a creare e modificare gli argomenti** , è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="ced9b-157">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="ced9b-158">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="ced9b-158">**Everyone in my organization**</span></span>
    - <span data-ttu-id="ced9b-159">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="ced9b-159">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="ced9b-160">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="ced9b-160">**No one**</span></span>

    ![Autorizzazioni per la gestione degli argomenti, gli utenti che possono creare e modificare i temi](../media/ksetup3.png) 

8. <span data-ttu-id="ced9b-162">Nella sezione **chi può gestire gli argomenti** è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="ced9b-162">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="ced9b-163">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="ced9b-163">**Everyone in my organization**</span></span>
    - <span data-ttu-id="ced9b-164">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="ced9b-164">**Only selected people or security groups**</span></span>

    ![Autorizzazioni per la gestione degli argomenti](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="ced9b-166">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ced9b-166">Select **Next**.</span></span>

9. <span data-ttu-id="ced9b-167">Nella pagina **Crea centro** argomenti è possibile creare il sito Centro argomenti in cui è possibile visualizzare le pagine degli argomenti e gestire i temi.</span><span class="sxs-lookup"><span data-stu-id="ced9b-167">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="ced9b-168">Nella casella **nome sito** Digitare un nome per il centro degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ced9b-168">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="ced9b-169">Facoltativamente, è possibile digitare una breve descrizione nella casella **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="ced9b-169">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="ced9b-170">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ced9b-170">Select **Next**.</span></span>

   ![Creare centro informazioni](../media/ksetup4.png)  

10. <span data-ttu-id="ced9b-172">Nella pagina **Verificare e completare**, è possibile esaminare l'impostazione selezionata e scegliere se apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="ced9b-172">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="ced9b-173">Al termine, selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="ced9b-173">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="ced9b-174">Verrà visualizzata la pagina **rete informazioni attivata** che conferma che il sistema inizierà a analizzare i siti selezionati per gli argomenti e a creare il sito del centro informazioni.</span><span class="sxs-lookup"><span data-stu-id="ced9b-174">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="ced9b-175">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="ced9b-175">Select **Done**.</span></span>

12. <span data-ttu-id="ced9b-176">Verrà restituito alla pagina **Connect people to Knowledge** .</span><span class="sxs-lookup"><span data-stu-id="ced9b-176">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="ced9b-177">In questa pagina è possibile selezionare **Gestisci** per modificare le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ced9b-177">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Impostazioni applicate](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="ced9b-179">Assegnare le licenze</span><span class="sxs-lookup"><span data-stu-id="ced9b-179">Assign licenses</span></span>

<span data-ttu-id="ced9b-180">Dopo aver configurato l'argomento esperienze, è necessario assegnare le licenze per gli utenti che utilizzeranno le esperienze degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="ced9b-180">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="ced9b-181">Solo gli utenti con una licenza possono visualizzare informazioni su argomenti quali evidenziazione, schede argomento, pagine argomento e centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="ced9b-181">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="ced9b-182">Per assegnare le licenze:</span><span class="sxs-lookup"><span data-stu-id="ced9b-182">To assign licenses:</span></span>

1. <span data-ttu-id="ced9b-183">Nell'interfaccia di amministrazione di Microsoft 365, in **Utenti** fare clic su **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="ced9b-183">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="ced9b-184">Selezionare gli utenti a cui si vuole assegnare una licenza, poi fare clic su **Gestisci le licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="ced9b-184">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="ced9b-185">Selezionare **Assegna altre**.</span><span class="sxs-lookup"><span data-stu-id="ced9b-185">Select **Assign more**.</span></span>

4. <span data-ttu-id="ced9b-186">In **licenze** selezionare l' **argomento esperienze**.</span><span class="sxs-lookup"><span data-stu-id="ced9b-186">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="ced9b-187">In **app**, verificare che i **connettori di Graph Search con l'indice** e gli **argomenti** siano entrambi selezionati.</span><span class="sxs-lookup"><span data-stu-id="ced9b-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ced9b-188">![Licenze di SharePoint Syntex nell'interfaccia di amministrazione di Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="ced9b-188">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="ced9b-189">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="ced9b-189">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="ced9b-190">Gestire le esperienze degli argomenti</span><span class="sxs-lookup"><span data-stu-id="ced9b-190">Manage topic experiences</span></span>

<span data-ttu-id="ced9b-191">Dopo aver impostato le esperienze sugli argomenti, è possibile modificare le impostazioni scelte durante l'installazione nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span><span class="sxs-lookup"><span data-stu-id="ced9b-191">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="ced9b-192">Vedere i riferimenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ced9b-192">See the following references:</span></span>

- [<span data-ttu-id="ced9b-193">Gestire l'individuazione degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ced9b-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="ced9b-194">Gestire la visibilità degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ced9b-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="ced9b-195">Gestire le autorizzazioni per l'argomento in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ced9b-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="ced9b-196">Modificare il nome del centro argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ced9b-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="ced9b-197">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ced9b-197">See also</span></span>

[<span data-ttu-id="ced9b-198">Panoramica delle esperienze degli argomenti</span><span class="sxs-lookup"><span data-stu-id="ced9b-198">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
