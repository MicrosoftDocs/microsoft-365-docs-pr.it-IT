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
ms.openlocfilehash: d221f2932dc2ca9f562800b7b274e35e7f3d1db3
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749612"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="3da07-103">Configurare le esperienze degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3da07-103">Set up topic experiences in Microsoft 365</span></span>

<span data-ttu-id="3da07-104">È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per impostare e configurare le [esperienze degli argomenti](topic-experiences-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3da07-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="3da07-105">È importante pianificare il modo migliore per impostare e configurare gli argomenti nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="3da07-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="3da07-106">Prima di iniziare le procedure descritte in questo articolo, leggere l' [argomento piano Experience](plan-topic-experiences.md) .</span><span class="sxs-lookup"><span data-stu-id="3da07-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="3da07-107">È necessario essere un amministratore globale o un amministratore di SharePoint per accedere all'interfaccia di amministrazione di Microsoft 365 e impostare le esperienze degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="3da07-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="3da07-108">Dimostrazione video</span><span class="sxs-lookup"><span data-stu-id="3da07-108">Video demonstration</span></span>

<span data-ttu-id="3da07-109">In questo video viene illustrato il processo di impostazione delle esperienze degli argomenti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3da07-109">This video shows the process for setting up topic experiences in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="3da07-110">Configurare le esperienze dell'argomento</span><span class="sxs-lookup"><span data-stu-id="3da07-110">Set up topic experiences</span></span>

<span data-ttu-id="3da07-111">Per impostare le esperienze degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3da07-111">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="3da07-112">Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com)selezionare **Setup** e quindi visualizzare la sezione **file e contenuto** .</span><span class="sxs-lookup"><span data-stu-id="3da07-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="3da07-113">Nella sezione **file e contenuto** fare clic su **Connetti persone alla conoscenza**.</span><span class="sxs-lookup"><span data-stu-id="3da07-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Connettere le persone alla conoscenza](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="3da07-115">Nella pagina **Connect people to Knowledge** fare clic su Guida **introduttiva** per eseguire il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="3da07-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Per iniziare](../media/k-get-started.png) 

4. <span data-ttu-id="3da07-117">Nella pagina **scegliere il modo in cui la rete di informazioni può trovare gli argomenti** , verrà configurata l'individuazione dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="3da07-117">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="3da07-118">Nella sezione **selezione origini argomenti di SharePoint** selezionare i siti di SharePoint che verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="3da07-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="3da07-119">Scegliere da:</span><span class="sxs-lookup"><span data-stu-id="3da07-119">Choose from:</span></span>
    - <span data-ttu-id="3da07-120">**Tutti i siti**: tutti i siti di SharePoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3da07-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="3da07-121">Sono inclusi i siti correnti e futuri.</span><span class="sxs-lookup"><span data-stu-id="3da07-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="3da07-122">**All, eccetto siti selezionati**: digitare i nomi dei siti che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="3da07-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="3da07-123">È inoltre possibile caricare un elenco di siti che si desidera escludere dall'individuazione.</span><span class="sxs-lookup"><span data-stu-id="3da07-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="3da07-124">I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="3da07-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="3da07-125">**Solo siti selezionati**: digitare i nomi dei siti che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="3da07-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="3da07-126">È inoltre possibile caricare un elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="3da07-126">You can also upload a list of sites.</span></span> <span data-ttu-id="3da07-127">I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="3da07-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="3da07-128">**Nessun sito**: non includere alcun sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3da07-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Scegliere come trovare gli argomenti](../media/ksetup1.png) 
   
5. <span data-ttu-id="3da07-130">Nella sezione **Escludi argomenti per nome** è possibile aggiungere i nomi degli argomenti che si desidera escludere dall'individuazione dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="3da07-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="3da07-131">Utilizzare questa impostazione per impedire l'inclusione di informazioni riservate come argomenti.</span><span class="sxs-lookup"><span data-stu-id="3da07-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="3da07-132">Le opzioni sono:</span><span class="sxs-lookup"><span data-stu-id="3da07-132">The options are:</span></span>
    - <span data-ttu-id="3da07-133">**Non escludere argomenti**</span><span class="sxs-lookup"><span data-stu-id="3da07-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="3da07-134">**Escludi argomenti per nome**</span><span class="sxs-lookup"><span data-stu-id="3da07-134">**Exclude topics by name**</span></span>

    ![Escludi argomenti](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="3da07-136">I Knowledge Manager possono anche escludere gli argomenti nell'argomento centro dopo l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="3da07-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="3da07-137">Come escludere gli argomenti per nome</span><span class="sxs-lookup"><span data-stu-id="3da07-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="3da07-138">Se è necessario escludere gli argomenti, dopo aver selezionato **Escludi argomenti per nome**, selezionare Scarica il modello CSV e aggiornarlo con l'elenco di argomenti che si desidera escludere dai risultati dell'individuazione.</span><span class="sxs-lookup"><span data-stu-id="3da07-138">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Escludi argomenti nel modello CSV](../media/exclude-topics-csv.png) 

    <span data-ttu-id="3da07-140">Nel modello CSV, immettere le informazioni seguenti sugli argomenti che si desidera escludere:</span><span class="sxs-lookup"><span data-stu-id="3da07-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="3da07-141">**Nome**: digitare il nome dell'argomento che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="3da07-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="3da07-142">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="3da07-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="3da07-143">Corrispondenza esatta: è possibile includere il nome o l'acronimo esatto (ad esempio, *Contoso* o *ATL*).</span><span class="sxs-lookup"><span data-stu-id="3da07-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="3da07-144">Corrispondenza parziale: è possibile escludere tutti gli argomenti in cui è presente una parola specifica.</span><span class="sxs-lookup"><span data-stu-id="3da07-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="3da07-145">Ad esempio, *Arc* escluderà tutti gli argomenti con l' *arco* di parola in esso, ad esempio *cerchio arco*, *saldatura ad arco al plasma* o *arco di training*. Tenere presente che non verranno esclusi gli argomenti in cui il testo viene incluso come parte di una parola, ad esempio l' *architettura*.</span><span class="sxs-lookup"><span data-stu-id="3da07-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="3da07-146">Acronimo **di (facoltativo)**: se si desidera escludere un acronimo, digitare le parole in cui si trova l'acronimo.</span><span class="sxs-lookup"><span data-stu-id="3da07-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="3da07-147">**MatchType-exact/partial**: digitare se il nome immesso è un tipo di corrispondenza *esatta* o *parziale* .</span><span class="sxs-lookup"><span data-stu-id="3da07-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="3da07-148">Dopo aver completato e salvato il file. csv, selezionare **Sfoglia** per individuarlo e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="3da07-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="3da07-149">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3da07-149">Select **Next**.</span></span>

6. <span data-ttu-id="3da07-150">Negli **utenti che possono visualizzare gli argomenti e dove possono visualizzarli** , verrà configurata la visibilità dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="3da07-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="3da07-151">Negli **utenti che possono visualizzare gli argomenti nell'impostazione della rete di conoscenze** , scegliere chi avrà accesso ai dettagli sull'argomento, ad esempio argomenti evidenziati, schede argomento, risposte agli argomenti nelle pagine di ricerca e argomento.</span><span class="sxs-lookup"><span data-stu-id="3da07-151">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="3da07-152">È possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="3da07-152">You can select:</span></span>
    - <span data-ttu-id="3da07-153">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="3da07-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="3da07-154">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="3da07-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="3da07-155">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="3da07-155">**No one**</span></span>

    ![Utenti autorizzati a visualizzare gli argomenti](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="3da07-157">Anche se questa impostazione consente di selezionare qualsiasi utente dell'organizzazione, solo gli utenti che dispongono di licenze per l'argomento sono in grado di visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="3da07-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="3da07-158">Nella pagina **autorizzazioni per gestione** argomenti scegliere gli utenti che potranno creare, modificare o gestire gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="3da07-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="3da07-159">Nella sezione **utenti autorizzati a creare e modificare gli argomenti** , è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="3da07-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="3da07-160">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="3da07-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="3da07-161">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="3da07-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="3da07-162">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="3da07-162">**No one**</span></span>

    ![Autorizzazioni per la gestione degli argomenti, gli utenti che possono creare e modificare i temi](../media/ksetup3.png) 

8. <span data-ttu-id="3da07-164">Nella sezione **chi può gestire gli argomenti** è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="3da07-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="3da07-165">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="3da07-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="3da07-166">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="3da07-166">**Only selected people or security groups**</span></span>

    ![Autorizzazioni per la gestione degli argomenti](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="3da07-168">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3da07-168">Select **Next**.</span></span>

9. <span data-ttu-id="3da07-169">Nella pagina **Crea centro** argomenti è possibile creare il sito Centro argomenti in cui è possibile visualizzare le pagine degli argomenti e gestire i temi.</span><span class="sxs-lookup"><span data-stu-id="3da07-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="3da07-170">Nella casella **nome sito** Digitare un nome per il centro degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="3da07-170">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="3da07-171">Facoltativamente, è possibile digitare una breve descrizione nella casella **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="3da07-171">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="3da07-172">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3da07-172">Select **Next**.</span></span>

   ![Creare centro informazioni](../media/ksetup4.png)  

10. <span data-ttu-id="3da07-174">Nella pagina **Verificare e completare**, è possibile esaminare l'impostazione selezionata e scegliere se apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="3da07-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="3da07-175">Al termine, selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="3da07-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="3da07-176">Verrà visualizzata la pagina **rete informazioni attivata** che conferma che il sistema inizierà a analizzare i siti selezionati per gli argomenti e a creare il sito del centro informazioni.</span><span class="sxs-lookup"><span data-stu-id="3da07-176">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="3da07-177">Scegliere **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="3da07-177">Select **Done**.</span></span>

12. <span data-ttu-id="3da07-178">Verrà restituito alla pagina **Connect people to Knowledge** .</span><span class="sxs-lookup"><span data-stu-id="3da07-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="3da07-179">In questa pagina è possibile selezionare **Gestisci** per modificare le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3da07-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Impostazioni applicate](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="3da07-181">Assegnare le licenze</span><span class="sxs-lookup"><span data-stu-id="3da07-181">Assign licenses</span></span>

<span data-ttu-id="3da07-182">Dopo aver configurato l'argomento esperienze, è necessario assegnare le licenze per gli utenti che utilizzeranno le esperienze degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="3da07-182">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="3da07-183">Solo gli utenti con una licenza possono visualizzare informazioni su argomenti quali evidenziazione, schede argomento, pagine argomento e centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="3da07-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="3da07-184">Per assegnare le licenze:</span><span class="sxs-lookup"><span data-stu-id="3da07-184">To assign licenses:</span></span>

1. <span data-ttu-id="3da07-185">Nell'interfaccia di amministrazione di Microsoft 365, in **Utenti** fare clic su **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="3da07-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="3da07-186">Selezionare gli utenti a cui si vuole assegnare una licenza, poi fare clic su **Gestisci le licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="3da07-186">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="3da07-187">Selezionare **Assegna altre**.</span><span class="sxs-lookup"><span data-stu-id="3da07-187">Select **Assign more**.</span></span>

4. <span data-ttu-id="3da07-188">In **licenze** selezionare l' **argomento esperienze**.</span><span class="sxs-lookup"><span data-stu-id="3da07-188">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="3da07-189">In **app**, verificare che i **connettori di Graph Search con l'indice** e gli **argomenti** siano entrambi selezionati.</span><span class="sxs-lookup"><span data-stu-id="3da07-189">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3da07-190">![Licenze di SharePoint Syntex nell'interfaccia di amministrazione di Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="3da07-190">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="3da07-191">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="3da07-191">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="3da07-192">Gestire le esperienze degli argomenti</span><span class="sxs-lookup"><span data-stu-id="3da07-192">Manage topic experiences</span></span>

<span data-ttu-id="3da07-193">Dopo aver impostato le esperienze sugli argomenti, è possibile modificare le impostazioni scelte durante l'installazione nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span><span class="sxs-lookup"><span data-stu-id="3da07-193">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="3da07-194">Vedere i riferimenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3da07-194">See the following references:</span></span>

- [<span data-ttu-id="3da07-195">Gestire l'individuazione degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3da07-195">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="3da07-196">Gestire la visibilità degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3da07-196">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="3da07-197">Gestire le autorizzazioni per l'argomento in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3da07-197">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="3da07-198">Modificare il nome del centro argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3da07-198">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="3da07-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3da07-199">See also</span></span>

[<span data-ttu-id="3da07-200">Panoramica delle esperienze degli argomenti</span><span class="sxs-lookup"><span data-stu-id="3da07-200">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
