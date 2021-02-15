---
title: Configurare Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informazioni su come configurare Gli argomenti di Microsoft Viva
ms.openlocfilehash: 6bd0d3eca653ae44e46b410ef3ac55fe11629a6b
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150501"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="f7184-103">Configurare Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="f7184-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="f7184-104">È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per configurare gli [argomenti.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f7184-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="f7184-105">È importante pianificare il modo migliore per impostare e configurare gli argomenti nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="f7184-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="f7184-106">Prima di iniziare le procedure descritte in questo articolo, leggere Plan [for Microsoft Viva Topics.](plan-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="f7184-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="f7184-107">È necessario essere [iscritti ad Argomenti Viva](https://www.microsoft.com/microsoft-viva/topics) ed essere un amministratore globale o un amministratore di SharePoint per accedere all'interfaccia di amministrazione di Microsoft 365 e configurare Gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="f7184-108">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="f7184-108">Video demonstration</span></span>

<span data-ttu-id="f7184-109">Questo video mostra il processo di configurazione degli argomenti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f7184-109">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="f7184-110">Configurare Argomenti</span><span class="sxs-lookup"><span data-stu-id="f7184-110">Set up Topics</span></span>

<span data-ttu-id="f7184-111">Per configurare gli argomenti</span><span class="sxs-lookup"><span data-stu-id="f7184-111">To set up Topics</span></span>

1. <span data-ttu-id="f7184-112">[Nell'interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com)selezionare **Installazione** e quindi visualizzare la sezione **File e** contenuto.</span><span class="sxs-lookup"><span data-stu-id="f7184-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="f7184-113">Nella sezione **File e contenuto** fare clic su Connetti utenti alla **conoscenza.**</span><span class="sxs-lookup"><span data-stu-id="f7184-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Connettere le persone alle conoscenze](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="f7184-115">Nella pagina **Connetti utenti alla knowledge** base fare clic su Introduzione per illustrare il processo di configurazione. </span><span class="sxs-lookup"><span data-stu-id="f7184-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Per iniziare](../media/k-get-started.png) 

4. <span data-ttu-id="f7184-117">Nella pagina **Scegliere in che modo Viva Topics può trovare gli** argomenti, è necessario configurare l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-117">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="f7184-118">Nella sezione **Selezionare le origini degli argomenti di SharePoint** selezionare i siti di SharePoint che verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="f7184-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="f7184-119">Scegli tra:</span><span class="sxs-lookup"><span data-stu-id="f7184-119">Choose from:</span></span>
    - <span data-ttu-id="f7184-120">**Tutti i siti:** tutti i siti di SharePoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f7184-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="f7184-121">Sono inclusi i siti correnti e futuri.</span><span class="sxs-lookup"><span data-stu-id="f7184-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="f7184-122">**Tutti, ad eccezione dei siti** selezionati: digitare i nomi dei siti che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="f7184-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="f7184-123">Puoi anche caricare un elenco di siti che vuoi rifiutare esplicitamente dall'individuazione.</span><span class="sxs-lookup"><span data-stu-id="f7184-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="f7184-124">I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="f7184-125">**Solo siti selezionati:** digitare i nomi dei siti che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="f7184-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="f7184-126">È inoltre possibile caricare un elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="f7184-126">You can also upload a list of sites.</span></span> <span data-ttu-id="f7184-127">I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="f7184-128">**Nessun sito:** non includere alcun sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f7184-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Scegliere come trovare gli argomenti](../media/ksetup1.png) 
   
5. <span data-ttu-id="f7184-130">Nella sezione **Escludi argomenti per nome** è possibile aggiungere i nomi degli argomenti che si desidera escludere dall'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="f7184-131">Utilizzare questa impostazione per impedire che le informazioni riservate vengano incluse come argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="f7184-132">Le opzioni sono:</span><span class="sxs-lookup"><span data-stu-id="f7184-132">The options are:</span></span>
    - <span data-ttu-id="f7184-133">**Non escludere alcun argomento**</span><span class="sxs-lookup"><span data-stu-id="f7184-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="f7184-134">**Escludere gli argomenti in base al nome**</span><span class="sxs-lookup"><span data-stu-id="f7184-134">**Exclude topics by name**</span></span>

    ![Escludi argomenti](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="f7184-136">I knowledge manager possono anche escludere gli argomenti nel Centro argomenti dopo l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="f7184-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="f7184-137">Come escludere gli argomenti in base al nome</span><span class="sxs-lookup"><span data-stu-id="f7184-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="f7184-138">Se è necessario escludere gli argomenti, dopo aver selezionato Escludi argomenti per **nome,** scaricare il modello csv e aggiornarlo con l'elenco di argomenti che si desidera escludere dai risultati dell'individuazione.</span><span class="sxs-lookup"><span data-stu-id="f7184-138">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Escludere gli argomenti nel modello CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="f7184-140">Nel modello CSV immettere le informazioni seguenti sugli argomenti che si desidera escludere:</span><span class="sxs-lookup"><span data-stu-id="f7184-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="f7184-141">**Nome**: digitare il nome dell'argomento che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="f7184-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="f7184-142">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="f7184-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="f7184-143">Corrispondenza esatta: è possibile includere il nome esatto o l'acronimo (ad esempio, *Contoso* o *ATL).*</span><span class="sxs-lookup"><span data-stu-id="f7184-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="f7184-144">Corrispondenza parziale: è possibile escludere tutti gli argomenti che includono una parola specifica.</span><span class="sxs-lookup"><span data-stu-id="f7184-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="f7184-145">Ad esempio, *l'arco* escluderà tutti gli argomenti con la parola arco *al* suo interno, ad esempio arco *circolare,* saldatura arco *di plasma* o arco *di formazione.* Si noti che non verranno esclusi gli argomenti in cui il testo è incluso come parte di una parola, ad esempio *Architecture.*</span><span class="sxs-lookup"><span data-stu-id="f7184-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="f7184-146">**Acronimo (facoltativo):** se si desidera escludere un acronimo, digitare le parole che l'acronimo sta per.</span><span class="sxs-lookup"><span data-stu-id="f7184-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="f7184-147">**MatchType-Exact/Partial:** specificare se il nome immesso è un *tipo* di corrispondenza esatto *o* parziale.</span><span class="sxs-lookup"><span data-stu-id="f7184-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="f7184-148">Dopo aver completato e salvato il file CSV, selezionare **Sfoglia** per individuarlo e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="f7184-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="f7184-149">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7184-149">Select **Next**.</span></span>

6. <span data-ttu-id="f7184-150">Nella pagina Chi può visualizzare gli argomenti e dove possono **vederli,** è necessario configurare la visibilità degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="f7184-151">**Nell'impostazione Chi** può visualizzare gli argomenti è possibile scegliere chi avrà accesso ai dettagli dell'argomento, ad esempio argomenti evidenziati, schede argomento, risposte agli argomenti nella ricerca e pagine degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-151">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="f7184-152">È possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="f7184-152">You can select:</span></span>
    - <span data-ttu-id="f7184-153">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="f7184-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="f7184-154">**Solo utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="f7184-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="f7184-155">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="f7184-155">**No one**</span></span>

    ![Chi può visualizzare gli argomenti](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="f7184-157">Anche se questa impostazione consente di selezionare qualsiasi utente nell'organizzazione, solo gli utenti a cui sono assegnate licenze per esperienze argomento potranno visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="f7184-158">Nella pagina **Autorizzazioni per la gestione degli** argomenti è possibile scegliere chi sarà in grado di creare, modificare o gestire gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="f7184-159">Nella sezione **Chi può creare e modificare gli argomenti** è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="f7184-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="f7184-160">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="f7184-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="f7184-161">**Solo utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="f7184-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="f7184-162">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="f7184-162">**No one**</span></span>

    ![Autorizzazioni per la gestione degli argomenti, utenti che possono creare e modificare argomenti](../media/ksetup3.png) 

8. <span data-ttu-id="f7184-164">Nella sezione **Chi può gestire gli argomenti** è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="f7184-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="f7184-165">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="f7184-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="f7184-166">**Solo utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="f7184-166">**Only selected people or security groups**</span></span>

    ![Autorizzazioni per la gestione degli argomenti](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="f7184-168">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7184-168">Select **Next**.</span></span>

9. <span data-ttu-id="f7184-169">Nella pagina **Crea centro argomenti** è possibile creare il sito Centro argomenti in cui è possibile visualizzare le pagine degli argomenti e gestire gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="f7184-170">Nella casella **Nome sito** digitare un nome per il Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-170">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="f7184-171">Facoltativamente, è possibile digitare una breve descrizione nella **casella Descrizione.**</span><span class="sxs-lookup"><span data-stu-id="f7184-171">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="f7184-172">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7184-172">Select **Next**.</span></span>

   ![Creare centro informazioni](../media/ksetup4.png)  

10. <span data-ttu-id="f7184-174">Nella pagina **Verificare e completare**, è possibile esaminare l'impostazione selezionata e scegliere se apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="f7184-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="f7184-175">Al termine, selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="f7184-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="f7184-176">Verrà **visualizzata la pagina Viva Topics attivata,** che conferma che il sistema inizierà ora ad analizzare i siti selezionati per gli argomenti e a creare il sito Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-176">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="f7184-177">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="f7184-177">Select **Done**.</span></span>

12. <span data-ttu-id="f7184-178">You'll be returned to your **Connect people to knowledge** page.</span><span class="sxs-lookup"><span data-stu-id="f7184-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="f7184-179">In questa pagina è possibile selezionare **Gestisci** per modificare le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f7184-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Impostazioni applicate](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="f7184-181">Assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="f7184-181">Assign licenses</span></span>

<span data-ttu-id="f7184-182">Dopo aver configurato le esperienze per gli argomenti, è necessario assegnare licenze agli utenti che utilizzano gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-182">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="f7184-183">Solo gli utenti con una licenza possono visualizzare informazioni su argomenti quali evidenziazioni, schede argomento, pagine di argomenti e il Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="f7184-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="f7184-184">Per assegnare le licenze:</span><span class="sxs-lookup"><span data-stu-id="f7184-184">To assign licenses:</span></span>

1. <span data-ttu-id="f7184-185">Nell'interfaccia di amministrazione di Microsoft 365, in **Utenti** fare clic su **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="f7184-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="f7184-186">Seleziona gli utenti di cui vuoi ottenere la licenza e fai clic **su Licenze e app.**</span><span class="sxs-lookup"><span data-stu-id="f7184-186">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="f7184-187">In **App,** verificare che sia selezionata **l'opzione** Cerca nei connettori grafici con esperienze indice **ed** argomento.</span><span class="sxs-lookup"><span data-stu-id="f7184-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

4. <span data-ttu-id="f7184-188">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="f7184-188">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="f7184-189">Gestire le esperienze degli argomenti</span><span class="sxs-lookup"><span data-stu-id="f7184-189">Manage topic experiences</span></span>

<span data-ttu-id="f7184-190">Dopo aver configurato Gli argomenti, è possibile modificare le impostazioni scelte durante la configurazione nell'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="f7184-190">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="f7184-191">Vedere i riferimenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7184-191">See the following references:</span></span>

- [<span data-ttu-id="f7184-192">Gestire l'individuazione degli argomenti negli argomenti di Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="f7184-192">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="f7184-193">Gestire la visibilità degli argomenti negli argomenti di Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="f7184-193">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="f7184-194">Gestire le autorizzazioni per gli argomenti negli argomenti di Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="f7184-194">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="f7184-195">Modificare il nome del Centro argomenti in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="f7184-195">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="f7184-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7184-196">See also</span></span>

[<span data-ttu-id="f7184-197">Panoramica delle esperienze degli argomenti</span><span class="sxs-lookup"><span data-stu-id="f7184-197">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
