---
title: Configurare Gli argomenti di Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informazioni su come configurare Microsoft Viva Topics
ms.openlocfilehash: 19395cf3a9ecc991f08f375425803cb81a2a1d35
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930222"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="4ac45-103">Configurare Gli argomenti di Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="4ac45-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="4ac45-104">È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per configurare [Gli argomenti](topic-experiences-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4ac45-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="4ac45-105">È importante pianificare il modo migliore per configurare e configurare gli argomenti nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4ac45-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="4ac45-106">Leggere Plan [for Microsoft Viva Topics](plan-topic-experiences.md) prima di iniziare le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4ac45-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="4ac45-107">È necessario essere [abbonati a Viva Topics](https://www.microsoft.com/microsoft-viva/topics) ed essere un amministratore globale o un amministratore di SharePoint per accedere all'interfaccia di amministrazione di Microsoft 365 e configurare Gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="4ac45-108">Se SharePoint è stato configurato per [richiedere dispositivi gestiti,](/sharepoint/control-access-from-unmanaged-devices)assicurarsi di configurare Gli argomenti da un dispositivo gestito.</span><span class="sxs-lookup"><span data-stu-id="4ac45-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="4ac45-109">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="4ac45-109">Video demonstration</span></span>

<span data-ttu-id="4ac45-110">Questo video mostra il processo di configurazione degli argomenti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ac45-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a><span data-ttu-id="4ac45-111">Assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="4ac45-111">Assign licenses</span></span>

<span data-ttu-id="4ac45-112">È necessario assegnare licenze per gli utenti che utilizzano Argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-112">You must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="4ac45-113">Solo gli utenti con una licenza possono visualizzare informazioni su argomenti quali evidenziazioni, schede argomento, pagine di argomenti e il Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-113">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="4ac45-114">Per assegnare le licenze:</span><span class="sxs-lookup"><span data-stu-id="4ac45-114">To assign licenses:</span></span>

1. <span data-ttu-id="4ac45-115">Nell'interfaccia di amministrazione di Microsoft 365, in **Utenti** fare clic su **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="4ac45-115">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="4ac45-116">Seleziona gli utenti di cui vuoi ottenere la licenza e fai clic **su Licenze e app.**</span><span class="sxs-lookup"><span data-stu-id="4ac45-116">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="4ac45-117">In **Licenze** selezionare **Viva Topics.**</span><span class="sxs-lookup"><span data-stu-id="4ac45-117">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="4ac45-118">In **App** assicurati che sia selezionata l'opzione Cerca connettori grafico con indice **(Argomenti Viva)** **e Viva Argomenti.**</span><span class="sxs-lookup"><span data-stu-id="4ac45-118">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4ac45-119">![Licenze di Microsoft Viva Topics nell'interfaccia di amministrazione di Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="4ac45-119">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="4ac45-120">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="4ac45-120">Click **Save changes**.</span></span>

<span data-ttu-id="4ac45-121">L'accesso agli argomenti dopo l'assegnazione delle licenze potrebbe richiedere fino a un'ora.</span><span class="sxs-lookup"><span data-stu-id="4ac45-121">It may take up to an hour for users to get access to Topics after the licenses are assigned.</span></span>

## <a name="set-up-topics"></a><span data-ttu-id="4ac45-122">Configurare Argomenti</span><span class="sxs-lookup"><span data-stu-id="4ac45-122">Set up Topics</span></span>

<span data-ttu-id="4ac45-123">Per configurare gli argomenti</span><span class="sxs-lookup"><span data-stu-id="4ac45-123">To set up Topics</span></span>

1. <span data-ttu-id="4ac45-124">Nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com)selezionare **Installazione** e quindi visualizzare la **sezione File e** contenuto.</span><span class="sxs-lookup"><span data-stu-id="4ac45-124">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="4ac45-125">Nella sezione **File e contenuto** fare clic su Connetti persone alla **conoscenza.**</span><span class="sxs-lookup"><span data-stu-id="4ac45-125">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Connettere le persone alla conoscenza](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="4ac45-127">Nella pagina **Connetti persone alla knowledge** base fare clic su **Introduzione** per iniziare a eseguire il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="4ac45-127">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Per iniziare](../media/k-get-started.png) 

4. <span data-ttu-id="4ac45-129">Nella pagina **Scegliere in che modo Viva Topics può trovare gli** argomenti, si configurerà l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-129">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="4ac45-130">Nella sezione **Selezione origini argomenti di SharePoint** selezionare quali siti di SharePoint verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="4ac45-130">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="4ac45-131">Scegli tra:</span><span class="sxs-lookup"><span data-stu-id="4ac45-131">Choose from:</span></span>
    - <span data-ttu-id="4ac45-132">**Tutti i siti**: tutti i siti di SharePoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ac45-132">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="4ac45-133">Sono inclusi i siti correnti e futuri.</span><span class="sxs-lookup"><span data-stu-id="4ac45-133">This includes current and future sites.</span></span>
    - <span data-ttu-id="4ac45-134">**Tutti, ad eccezione dei siti** selezionati: digitare i nomi dei siti che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="4ac45-134">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="4ac45-135">È inoltre possibile caricare un elenco di siti che si desidera rifiutare esplicitamente dall'individuazione.</span><span class="sxs-lookup"><span data-stu-id="4ac45-135">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="4ac45-136">I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-136">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="4ac45-137">**Solo siti selezionati:** digitare i nomi dei siti che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="4ac45-137">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="4ac45-138">È inoltre possibile caricare un elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-138">You can also upload a list of sites.</span></span> <span data-ttu-id="4ac45-139">I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-139">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="4ac45-140">**Nessun sito:** non includere alcun sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4ac45-140">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Scegliere come trovare gli argomenti](../media/ksetup1.png) 
   
5. <span data-ttu-id="4ac45-142">Nella sezione **Escludi argomenti per nome** è possibile aggiungere i nomi degli argomenti che si desidera escludere dall'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-142">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="4ac45-143">Utilizzare questa impostazione per impedire che le informazioni riservate vengano incluse come argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-143">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="4ac45-144">Le opzioni sono:</span><span class="sxs-lookup"><span data-stu-id="4ac45-144">The options are:</span></span>
    - <span data-ttu-id="4ac45-145">**Non escludere argomenti**</span><span class="sxs-lookup"><span data-stu-id="4ac45-145">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="4ac45-146">**Escludere gli argomenti in base al nome**</span><span class="sxs-lookup"><span data-stu-id="4ac45-146">**Exclude topics by name**</span></span>

    ![Escludi argomenti](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="4ac45-148">I responsabili della conoscenza possono anche escludere gli argomenti nel Centro argomenti dopo l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="4ac45-148">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="4ac45-149">Come escludere gli argomenti in base al nome</span><span class="sxs-lookup"><span data-stu-id="4ac45-149">How to exclude topics by name</span></span>    

    <span data-ttu-id="4ac45-150">Se è necessario escludere gli argomenti, dopo aver selezionato Escludi argomenti per **nome,** scaricare il modello CSV e aggiornarlo con l'elenco di argomenti che si desidera escludere dai risultati dell'individuazione.</span><span class="sxs-lookup"><span data-stu-id="4ac45-150">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Escludere gli argomenti nel modello CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="4ac45-152">Nel modello CSV immettere le informazioni seguenti sugli argomenti che si desidera escludere:</span><span class="sxs-lookup"><span data-stu-id="4ac45-152">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="4ac45-153">**Nome**: digitare il nome dell'argomento che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="4ac45-153">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="4ac45-154">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="4ac45-154">There are two ways to do this:</span></span>
        - <span data-ttu-id="4ac45-155">Corrispondenza esatta: è possibile includere il nome esatto o l'acronimo (ad esempio, *Contoso* o *ATL).*</span><span class="sxs-lookup"><span data-stu-id="4ac45-155">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="4ac45-156">Corrispondenza parziale: è possibile escludere tutti gli argomenti che includono una parola specifica.</span><span class="sxs-lookup"><span data-stu-id="4ac45-156">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="4ac45-157">Ad esempio, *arco* escluderà tutti gli argomenti con la parola arco *al* suo interno, ad esempio Cerchio *arco,* *Saldatura* arco di plasma o *Arco di formazione.* Si noti che non verranno esclusi gli argomenti in cui il testo è incluso come parte di una parola, ad esempio *Architettura*.</span><span class="sxs-lookup"><span data-stu-id="4ac45-157">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="4ac45-158">**Sta per (facoltativo):** se si desidera escludere un acronimo, digitare le parole che l'acronimo sta per.</span><span class="sxs-lookup"><span data-stu-id="4ac45-158">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="4ac45-159">**MatchType-Exact/Partial**: Digitare se il nome immesso è un *tipo* di corrispondenza esatto *o* parziale.</span><span class="sxs-lookup"><span data-stu-id="4ac45-159">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="4ac45-160">Dopo aver completato e salvato il file CSV, selezionare **Sfoglia** per individuarlo e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="4ac45-160">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="4ac45-161">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ac45-161">Select **Next**.</span></span>

6. <span data-ttu-id="4ac45-162">Nella pagina Chi può visualizzare gli argomenti e dove può **vederli,** configurerai la visibilità degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-162">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="4ac45-163">**Nell'impostazione Chi** può visualizzare gli argomenti scegliere chi avrà accesso ai dettagli dell'argomento, ad esempio argomenti evidenziati, schede argomento, risposte agli argomenti nella ricerca e pagine degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-163">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="4ac45-164">È possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="4ac45-164">You can select:</span></span>
    - <span data-ttu-id="4ac45-165">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="4ac45-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="4ac45-166">**Solo utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="4ac45-166">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="4ac45-167">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="4ac45-167">**No one**</span></span>

    ![Chi può visualizzare gli argomenti](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="4ac45-169">Anche se questa impostazione consente di selezionare qualsiasi utente nell'organizzazione, solo gli utenti a cui sono assegnate licenze esperienze argomento potranno visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-169">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="4ac45-170">Nella pagina **Autorizzazioni per la gestione degli** argomenti scegliere chi sarà in grado di creare, modificare o gestire gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-170">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="4ac45-171">Nella sezione **Utenti che possono creare e modificare argomenti** è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="4ac45-171">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="4ac45-172">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="4ac45-172">**Everyone in my organization**</span></span>
    - <span data-ttu-id="4ac45-173">**Solo utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="4ac45-173">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="4ac45-174">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="4ac45-174">**No one**</span></span>

    ![Autorizzazioni per la gestione degli argomenti, che possono creare e modificare argomenti](../media/ksetup3.png) 

8. <span data-ttu-id="4ac45-176">Nella sezione **Chi può gestire gli argomenti** è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="4ac45-176">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="4ac45-177">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="4ac45-177">**Everyone in my organization**</span></span>
    - <span data-ttu-id="4ac45-178">**Solo utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="4ac45-178">**Only selected people or security groups**</span></span>

    ![Autorizzazioni per la gestione degli argomenti](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="4ac45-180">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ac45-180">Select **Next**.</span></span>

9. <span data-ttu-id="4ac45-181">Nella pagina **Crea centro argomenti** è possibile creare il sito Centro argomenti in cui è possibile visualizzare le pagine degli argomenti e gestire gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-181">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="4ac45-182">Nella casella **Nome sito** digitare un nome per il Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-182">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="4ac45-183">Facoltativamente, è possibile digitare una breve descrizione nella **casella Descrizione.**</span><span class="sxs-lookup"><span data-stu-id="4ac45-183">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="4ac45-184">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ac45-184">Select **Next**.</span></span>

   ![Creare il Centro informazioni](../media/ksetup4.png)  

10. <span data-ttu-id="4ac45-186">Nella pagina **Verificare e completare**, è possibile esaminare l'impostazione selezionata e scegliere se apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="4ac45-186">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="4ac45-187">Al termine, selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="4ac45-187">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="4ac45-188">Verrà visualizzata la pagina **Viva Topics activated,** che conferma che il sistema inizierà ad analizzare i siti selezionati per gli argomenti e a creare il sito Centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-188">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="4ac45-189">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="4ac45-189">Select **Done**.</span></span>

12. <span data-ttu-id="4ac45-190">Verrà visualizzata la pagina Connetti **persone alla** conoscenza.</span><span class="sxs-lookup"><span data-stu-id="4ac45-190">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="4ac45-191">In questa pagina è possibile selezionare **Gestisci** per modificare le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4ac45-191">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Impostazioni applicate](../media/ksetup7.png)    

<span data-ttu-id="4ac45-193">Si noti che la prima volta che l'individuazione degli argomenti è abilitata, potrebbero essere necessario fino a due settimane prima che tutti gli argomenti suggeriti vengano visualizzati nella visualizzazione Gestisci argomenti.</span><span class="sxs-lookup"><span data-stu-id="4ac45-193">Note that the first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="4ac45-194">L'individuazione degli argomenti continua quando vengono apportati nuovi contenuti o aggiornamenti al contenuto.</span><span class="sxs-lookup"><span data-stu-id="4ac45-194">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="4ac45-195">È normale avere fluttuazioni nel numero di argomenti suggeriti nell'organizzazione poiché Viva Topics valuta nuove informazioni.</span><span class="sxs-lookup"><span data-stu-id="4ac45-195">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="4ac45-196">Gestire le esperienze degli argomenti</span><span class="sxs-lookup"><span data-stu-id="4ac45-196">Manage topic experiences</span></span>

<span data-ttu-id="4ac45-197">Dopo aver configurato Gli argomenti, è possibile modificare le impostazioni scelte durante l'installazione nell'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="4ac45-197">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="4ac45-198">Vedere i seguenti riferimenti:</span><span class="sxs-lookup"><span data-stu-id="4ac45-198">See the following references:</span></span>

- [<span data-ttu-id="4ac45-199">Gestire l'individuazione degli argomenti in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="4ac45-199">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="4ac45-200">Gestire la visibilità degli argomenti in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="4ac45-200">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="4ac45-201">Gestire le autorizzazioni per gli argomenti in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="4ac45-201">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="4ac45-202">Modificare il nome del Centro argomenti in Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="4ac45-202">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="4ac45-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ac45-203">See also</span></span>

[<span data-ttu-id="4ac45-204">Panoramica delle esperienze degli argomenti</span><span class="sxs-lookup"><span data-stu-id="4ac45-204">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
