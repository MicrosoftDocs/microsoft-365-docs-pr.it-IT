---
title: 'Gestire la rete di gestione delle informazioni (anteprima) '
description: Come configurare la gestione delle informazioni.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 265816a8d3d04b8d10b529f1ea1a0b658aa2931d
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "48989009"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="7e3c5-103">Gestire la rete di gestione delle informazioni (anteprima)</span><span class="sxs-lookup"><span data-stu-id="7e3c5-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="7e3c5-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="7e3c5-105">[Altre informazioni su Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="7e3c5-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="7e3c5-106">Dopo aver [configurato la gestione della conoscenza](set-up-topic-experiences.md), in qualsiasi momento, un amministratore può apportare le modifiche alle impostazioni di configurazione tramite l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-106">After you [set up knowledge management](set-up-topic-experiences.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="7e3c5-107">Ad esempio, potrebbe essere necessario modificare le impostazioni per una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="7e3c5-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="7e3c5-108">Aggiungere nuove origini di SharePoint ai miei argomenti.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="7e3c5-109">Modificare gli utenti che avranno accesso agli argomenti.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="7e3c5-110">Modificare gli utenti che dispongono delle autorizzazioni per eseguire attività nel centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="7e3c5-111">Modificare il nome del centro argomenti</span><span class="sxs-lookup"><span data-stu-id="7e3c5-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="7e3c5-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e3c5-112">Requirements</span></span> 
<span data-ttu-id="7e3c5-113">È necessario disporre delle autorizzazioni di amministratore globale o di amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e gestire le attività relative alla conoscenza organizzativa.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="7e3c5-114">Per accedere alle impostazioni di gestione delle informazioni:</span><span class="sxs-lookup"><span data-stu-id="7e3c5-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="7e3c5-115">Nell'interfaccia di amministrazione di Microsoft 365, selezionare **Setup** e quindi visualizzare la sezione relativa alle **informazioni sull'organizzazione** .</span><span class="sxs-lookup"><span data-stu-id="7e3c5-115">In the Microsoft 365 admin center, select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="7e3c5-116">Nella sezione **informazioni organizzative** fare clic su **Connetti persone alla conoscenza**.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Connettere le persone alla conoscenza](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="7e3c5-118">Nella pagina **Connect people to Knowledge** selezionare **Manage** to open the **Knowledge Network Settings** pane.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![Knowledge-Network-Settings](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="7e3c5-120">Modificare il modo in cui la rete di informazioni può trovare argomenti</span><span class="sxs-lookup"><span data-stu-id="7e3c5-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="7e3c5-121">Se si desidera aggiornare le opzioni per le origini degli argomenti di SharePoint, selezionare la scheda **individuazione argomenti** .</span><span class="sxs-lookup"><span data-stu-id="7e3c5-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="7e3c5-122">Questa impostazione consente di selezionare i siti di SharePoint nel tenant che verranno sottoposti a ricerca per indicizzazione e estratti per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="7e3c5-123">Nella scheda **individuazione argomento** , in **selezionare origini argomento di SharePoint** , selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-123">On the **Topic discovery** tab, under **Select SharePoint topic sources** , select **Edit**.</span></span>
2. <span data-ttu-id="7e3c5-124">Nella pagina **Seleziona origini argomenti di SharePoint** selezionare i siti di SharePoint che verranno sottoposti a ricerca per indicizzazione come origini per gli argomenti durante l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="7e3c5-125">Questo include:</span><span class="sxs-lookup"><span data-stu-id="7e3c5-125">This includes:</span></span></br>
    <span data-ttu-id="7e3c5-126">a.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-126">a.</span></span> <span data-ttu-id="7e3c5-127">**Tutti i siti** : tutti i siti di SharePoint nel tenant.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-127">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="7e3c5-128">Questo acquisisce i siti correnti e futuri.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="7e3c5-129">b.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-129">b.</span></span> <span data-ttu-id="7e3c5-130">**All, eccetto siti selezionati** : digitare i nomi dei siti che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-130">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="7e3c5-131">È inoltre possibile caricare un elenco di siti che si desidera escludere dall'individuazione.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="7e3c5-132">I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="7e3c5-133">c.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-133">c.</span></span> <span data-ttu-id="7e3c5-134">**Solo siti selezionati** : digitare i nomi dei siti che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-134">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="7e3c5-135">È inoltre possibile caricare un elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-135">You can also upload a list of sites.</span></span> <span data-ttu-id="7e3c5-136">I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Scegliere come trovare gli argomenti](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="7e3c5-138">Se si dispone di un numero di siti che si desidera escludere (se si seleziona **tutto, tranne i siti selezionati** ) o si include (se sono stati selezionati **solo i siti selezionati** ), è possibile scegliere di caricare un file CSV con i nomi e gli URL del sito.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites** ) or include (if you selected **Only selected sites** ), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="7e3c5-139">È possibile selezionare **Scarica modello di sito. csv** se si desidera utilizzare il file modello CSV.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="7e3c5-140">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="7e3c5-141">Modificare gli utenti che possono visualizzare gli argomenti nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7e3c5-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="7e3c5-142">Selezionare la scheda **individuazione argomento** se si desidera aggiornare gli argomenti individuati nei risultati della ricerca e quando gli argomenti vengono evidenziati nel contenuto come le pagine di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="7e3c5-143">Nella scheda **individuazione argomento** , in **utenti autorizzati a visualizzare gli argomenti della rete della Knowledge** base, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network** , select **Edit**.</span></span>
2. <span data-ttu-id="7e3c5-144">Gli **utenti che possono visualizzare gli argomenti della pagina della rete della Knowledge** base consentono di scegliere gli utenti che avranno accesso ai dettagli sull'argomento, ad esempio argomenti evidenziati, schede argomento, risposte agli argomenti nelle pagine di ricerca e nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="7e3c5-145">È possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="7e3c5-145">You can select:</span></span></br>
    <span data-ttu-id="7e3c5-146">a.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-146">a.</span></span> <span data-ttu-id="7e3c5-147">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="7e3c5-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="7e3c5-148">b.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-148">b.</span></span> <span data-ttu-id="7e3c5-149">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="7e3c5-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="7e3c5-150">c.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-150">c.</span></span> <span data-ttu-id="7e3c5-151">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="7e3c5-151">**No one**</span></span></br>

    ![Utenti autorizzati a visualizzare gli argomenti](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="7e3c5-153">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="7e3c5-154">Anche se questa impostazione consente di selezionare qualsiasi utente dell'organizzazione, solo gli utenti che dispongono di licenze di gestione delle informazioni assegnate potranno visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="7e3c5-155">Modificare gli utenti che dispongono delle autorizzazioni per eseguire attività nel centro argomenti</span><span class="sxs-lookup"><span data-stu-id="7e3c5-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="7e3c5-156">Selezionare la scheda autorizzazioni per l' **argomento** se si desidera aggiornare gli utenti che dispongono delle autorizzazioni per eseguire le operazioni seguenti nella pagina Centro argomenti:</span><span class="sxs-lookup"><span data-stu-id="7e3c5-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="7e3c5-157">Quali utenti possono creare e modificare gli argomenti: creare nuovi argomenti che non sono stati rilevati durante l'individuazione o modificare i dettagli della pagina di argomento esistente.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="7e3c5-158">Quali utenti possono gestire gli argomenti: confermare o rifiutare gli argomenti individuati.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="7e3c5-159">Per aggiornare gli utenti che dispongono delle autorizzazioni per la creazione e la modifica degli argomenti:</span><span class="sxs-lookup"><span data-stu-id="7e3c5-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="7e3c5-160">Nella scheda **autorizzazioni dell'argomento** , in **utenti autorizzati a creare e modificare gli argomenti** , selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-160">On the **Topic permissions** tab, under **Who can create and edit topics** , select **Edit**.</span></span></br>
2. <span data-ttu-id="7e3c5-161">Nella pagina **utenti autorizzati a creare e modificare gli argomenti** è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="7e3c5-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="7e3c5-162">a.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-162">a.</span></span> <span data-ttu-id="7e3c5-163">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="7e3c5-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="7e3c5-164">b.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-164">b.</span></span> <span data-ttu-id="7e3c5-165">**Solo persone o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="7e3c5-165">**Only selected people or security groups**</span></span></br>

    ![Creare e modificare gli argomenti](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="7e3c5-167">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-167">Select **Save**.</span></span></br>

<span data-ttu-id="7e3c5-168">Per aggiornare gli utenti che dispongono delle autorizzazioni per gestire gli argomenti:</span><span class="sxs-lookup"><span data-stu-id="7e3c5-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="7e3c5-169">Nella scheda **autorizzazioni dell'argomento** , in **utenti autorizzati a gestire gli argomenti** , selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-169">On the **Topic permissions** tab, under **Who can manage topics** , select **Edit**.</span></span></br>
2. <span data-ttu-id="7e3c5-170">Nella pagina **chi** è in grado di gestire gli argomenti, è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="7e3c5-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="7e3c5-171">a.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-171">a.</span></span> <span data-ttu-id="7e3c5-172">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="7e3c5-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="7e3c5-173">b.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-173">b.</span></span> <span data-ttu-id="7e3c5-174">**Utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="7e3c5-174">**Selected people or security groups**</span></span></br>

    ![Gestire gli argomenti](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="7e3c5-176">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="7e3c5-177">Aggiornare il nome del centro dell'argomento</span><span class="sxs-lookup"><span data-stu-id="7e3c5-177">Update your topic center name</span></span>

<span data-ttu-id="7e3c5-178">Selezionare la scheda **centro argomenti** se si desidera aggiornare il nome del centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="7e3c5-179">Nella scheda **centro argomenti** , in **nome centro argomenti** , selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-179">On the **Topic center** tab, under **Topic center name** , select **Edit**.</span></span>
2. <span data-ttu-id="7e3c5-180">Nella casella **nome centro** argomenti della pagina **modifica nome centro argomenti** Digitare il nuovo nome del centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="7e3c5-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="7e3c5-181">Selezionare **Salva**</span><span class="sxs-lookup"><span data-stu-id="7e3c5-181">Select **Save**</span></span>

    ![Modifica nome centro argomenti](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="7e3c5-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e3c5-183">See also</span></span>



  






