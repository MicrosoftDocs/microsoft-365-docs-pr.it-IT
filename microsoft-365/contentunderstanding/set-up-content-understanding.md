---
title: Configurare SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Configurare la comprensione del contenuto in Project Cortex
ms.openlocfilehash: 31c6b6dd31b3f1bc47deb8424dd847cc0af6d429
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304781"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="21675-103">Configurare SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="21675-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="21675-104">Gli amministratori possono utilizzare l'interfaccia di amministrazione di Microsoft 365 per configurare e Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="21675-104">Admins can use the Microsoft 365 admin center to set up and Microsoft SharePoint Syntex.</span></span> 

<span data-ttu-id="21675-105">Prima di iniziare, prendere in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="21675-105">Consider the following before you start:</span></span>

- <span data-ttu-id="21675-106">Quali siti di SharePoint consentiranno di abilitare l'elaborazione dei moduli?</span><span class="sxs-lookup"><span data-stu-id="21675-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="21675-107">Tutti, alcuni o Seleziona siti?</span><span class="sxs-lookup"><span data-stu-id="21675-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="21675-108">Che cosa è il nome del centro di contenuti e chi è l'amministratore principale del sito?</span><span class="sxs-lookup"><span data-stu-id="21675-108">What will you name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="21675-109">È possibile modificare le impostazioni dopo l'installazione iniziale nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21675-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="21675-110">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="21675-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="21675-111">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="21675-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="21675-112">Prima di eseguire l'installazione, assicurarsi di pianificare il modo migliore per impostare e configurare la comprensione del contenuto nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="21675-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="21675-113">Ad esempio, è necessario prendere in considerazione i seguenti nomi:</span><span class="sxs-lookup"><span data-stu-id="21675-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="21675-114">I siti di SharePoint che si desidera abilitare l'elaborazione del modulo: tutti, alcuni o siti selezionati</span><span class="sxs-lookup"><span data-stu-id="21675-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="21675-115">Il centro contenuto e il nome dell'amministratore del sito principale</span><span class="sxs-lookup"><span data-stu-id="21675-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="21675-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21675-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="21675-117">È necessario disporre delle autorizzazioni di amministratore globale o di amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare la comprensione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="21675-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="21675-118">Come amministratore, è anche possibile apportare modifiche alle impostazioni selezionate in qualsiasi momento dopo l'installazione e in tutte le impostazioni di gestione del contenuto nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21675-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="21675-119">Per configurare SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="21675-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="21675-120">Nell'interfaccia di amministrazione di Microsoft 365, selezionare **Setup**e quindi visualizzare la sezione relativa alle **informazioni sull'organizzazione** .</span><span class="sxs-lookup"><span data-stu-id="21675-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="21675-121">Nella sezione **informazioni organizzative** selezionare **automatizza la comprensione del contenuto**.</span><span class="sxs-lookup"><span data-stu-id="21675-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Pagina di configurazione della conoscenza organizzativa](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="21675-123">Nella pagina **automatizzare SharePoint Syntex** , fare clic su Guida **introduttiva** per eseguire il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="21675-123">On the **Automate SharePoint Syntex** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Avviare l'installazione](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="21675-125">Nella pagina attiva tagging immagine scegliere se si desidera consentire il [tagging dell'immagine](image-tagging.md).</span><span class="sxs-lookup"><span data-stu-id="21675-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![Schermata delle opzioni di tagging dell'immagine](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="21675-127">Nella pagina **Configura elaborazione moduli** è possibile scegliere se si desidera consentire agli utenti di utilizzare il generatore ai per creare modelli di elaborazione dei moduli in specifiche raccolte documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="21675-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="21675-128">Nella barra multifunzione della raccolta documenti sarà disponibile un'opzione di menu per **creare un modello di elaborazione dei moduli** nelle raccolte documenti di SharePoint in cui è abilitata.</span><span class="sxs-lookup"><span data-stu-id="21675-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="21675-129">Per **il quale le raccolte di SharePoint dovrebbero mostrare l'opzione per creare un modello di elaborazione dei moduli**, è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="21675-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="21675-130">**Tutte le raccolte di SharePoint** per renderle disponibili per tutte le raccolte di SharePoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21675-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="21675-131">**Solo le raccolte nei siti selezionati**, quindi selezionare i siti in cui si desidera renderli disponibili.</span><span class="sxs-lookup"><span data-stu-id="21675-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>

   ![Configurare l'elaborazione dei moduli](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="21675-133">L'abilitazione di questa impostazione in una raccolta documenti di SharePoint non influisce sui modelli esistenti applicati alla raccolta o sulla possibilità di applicare i modelli di comprensione dei documenti a una raccolta.</span><span class="sxs-lookup"><span data-stu-id="21675-133">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="21675-134">Nella pagina **Crea centro contenuto** è possibile creare un sito Centro contenuto di SharePoint in cui gli utenti possono creare e gestire i modelli di comprensione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="21675-134">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="21675-135">a.</span><span class="sxs-lookup"><span data-stu-id="21675-135">a.</span></span> <span data-ttu-id="21675-136">Per **nome sito**, digitare il nome che si desidera assegnare al sito Centro contenuto.</span><span class="sxs-lookup"><span data-stu-id="21675-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="21675-137">b.</span><span class="sxs-lookup"><span data-stu-id="21675-137">b.</span></span> <span data-ttu-id="21675-138">L' **indirizzo del sito** mostrerà l'URL del sito, in base alle operazioni selezionate per il nome del sito.</span><span class="sxs-lookup"><span data-stu-id="21675-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="21675-139">Se si desidera modificarlo, fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="21675-139">If you want to change it, click **Edit**.</span></span></br>

      ![Creare centro contenuto](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="21675-141">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="21675-141">Select **Next**.</span></span>

7. <span data-ttu-id="21675-142">Nella pagina **revisione e fine** è possibile esaminare l'impostazione selezionata e scegliere di apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="21675-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="21675-143">Se si è soddisfatti delle selezioni, selezionare **attiva**.</span><span class="sxs-lookup"><span data-stu-id="21675-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="21675-144">Nella pagina Conferma fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="21675-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="21675-145">Verrà restituita la pagina di **informazioni sul contenuto automatico** .</span><span class="sxs-lookup"><span data-stu-id="21675-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="21675-146">Da questa pagina, è possibile selezionare **Gestisci** per apportare modifiche alle impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="21675-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="21675-147">Assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="21675-147">Assign licenses</span></span>

<span data-ttu-id="21675-148">Dopo aver configurato SharePoint Syntex, è necessario assegnare le licenze per gli utenti che utilizzeranno le funzionalità di elaborazione dei moduli e la comprensione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="21675-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using form processing and document understanding features.</span></span>

<span data-ttu-id="21675-149">Per assegnare le licenze:</span><span class="sxs-lookup"><span data-stu-id="21675-149">To assign licenses:</span></span>

1. <span data-ttu-id="21675-150">Nell'interfaccia di amministrazione di Microsoft 365, in **utenti**, fare clic su **utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="21675-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="21675-151">Selezionare gli utenti che si desidera concedere una licenza e fare clic su **Gestisci licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="21675-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="21675-152">Selezionare **assegna altro**.</span><span class="sxs-lookup"><span data-stu-id="21675-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="21675-153">Selezionare **Intelligent Content Services**.</span><span class="sxs-lookup"><span data-stu-id="21675-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="21675-154">In **app**, verificare che sia selezionata l'opzione **Common Data Service per Intelligent Content Services** e **Intelligent Content Services** .</span><span class="sxs-lookup"><span data-stu-id="21675-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Licenze di Syntex di SharePoint nell'interfaccia di amministrazione di Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="21675-156">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="21675-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="21675-157">Crediti AI Builder</span><span class="sxs-lookup"><span data-stu-id="21675-157">AI Builder credits</span></span>

<span data-ttu-id="21675-158">Se si dispone di 300 o più licenze di Syntex di SharePoint per SharePoint Syntex nell'organizzazione, verranno assegnati 1 milione AI Credits Builder.</span><span class="sxs-lookup"><span data-stu-id="21675-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="21675-159">Se si dispone di meno di 300 licenze, è necessario acquistare i crediti Builder AI per poter utilizzare l'elaborazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="21675-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="21675-160">È possibile valutare la capacità del generatore AI che è adatta a te con la [calcolatrice di ai Builder](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="21675-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="21675-161">Accedere all'interfaccia di [amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) per controllare i crediti e l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="21675-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="21675-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21675-162">See also</span></span>

[<span data-ttu-id="21675-163">Panoramica del modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="21675-163">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="21675-164">Step-by-Step: come creare un modello di comprensione dei documenti (video)</span><span class="sxs-lookup"><span data-stu-id="21675-164">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

