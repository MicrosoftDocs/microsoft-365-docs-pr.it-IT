---
title: Configurazione di SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Configurazione della comprensione dei contenuti in Project Cortex
ms.openlocfilehash: a275b2ec14403e16651acb293f8598b453fd3739
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515017"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="7ab8f-103">Configurazione di SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="7ab8f-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="7ab8f-104">Gli amministratori possono usare l'interfaccia di amministrazione di Microsoft 365 per configurare [Microsoft SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="7ab8f-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="7ab8f-105">Prima di iniziare, prendere in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7ab8f-105">Consider the following before you start:</span></span>

- <span data-ttu-id="7ab8f-106">In quali siti di SharePoint verrà abilitata l'elaborazione dei moduli?</span><span class="sxs-lookup"><span data-stu-id="7ab8f-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="7ab8f-107">Tutti, alcuni o determinati siti?</span><span class="sxs-lookup"><span data-stu-id="7ab8f-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="7ab8f-108">Quale sarà il nome assegnato al centro contenuti predefinito?</span><span class="sxs-lookup"><span data-stu-id="7ab8f-108">What will you name your default content center?</span></span>

<span data-ttu-id="7ab8f-109">È possibile cambiare le impostazioni dopo la configurazione iniziale nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="7ab8f-110">Prima di procedere, assicurarsi di pianificare in modo ottimale la configurazione della comprensione dei contenuti nel proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="7ab8f-111">Ad esempio, è necessario prendere le decisioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ab8f-111">For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="7ab8f-112">I siti di SharePoint in cui si vuole abilitare l'elaborazione dei moduli: tutti, alcuni o determinati siti.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="7ab8f-113">Il nome e gli amministratori del centro contenuti</span><span class="sxs-lookup"><span data-stu-id="7ab8f-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="7ab8f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ab8f-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="7ab8f-115">È necessario disporre delle autorizzazioni di amministratore globale o amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="7ab8f-116">Gli amministratori possono anche modificare le impostazioni selezionate in qualsiasi momento dopo la configurazione, nonché le impostazioni di gestione della comprensione dei contenuti nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

### <a name="licensing"></a><span data-ttu-id="7ab8f-117">Licenze</span><span class="sxs-lookup"><span data-stu-id="7ab8f-117">Licensing</span></span>

<span data-ttu-id="7ab8f-118">Per usare SharePoint Syntex, l'organizzazione deve avere un abbonamento a SharePoint Syntex e a ogni utente devono essere assegnate le licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ab8f-118">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="7ab8f-119">SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="7ab8f-119">SharePoint Syntex</span></span>
- <span data-ttu-id="7ab8f-120">SharePoint Syntex - tipo SPO</span><span class="sxs-lookup"><span data-stu-id="7ab8f-120">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="7ab8f-121">Servizio dati comuni per SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="7ab8f-121">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="7ab8f-122">Se si annulla l'abbonamento a SharePoint Syntex in futuro (o scade la versione di valutazione), gli utenti non saranno più in grado di creare o eseguire analisi dei documenti o modelli per l’elaborazione dei moduli e il modello del Centro contenuto non sarà più disponibile.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-122">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="7ab8f-123">Inoltre, i report dell'archivio termini, l'importazione della tassonomia SKOS e il push del tipo di contenuto non saranno più disponibili.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-123">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="7ab8f-124">Nessun contenuto verrà eliminato e le autorizzazioni per il sito non verranno modificate.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-124">No content will be deleted and site permissions will not be changed.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="7ab8f-125">Per configurare SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="7ab8f-125">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="7ab8f-126">Nell'interfaccia di amministrazione di Microsoft 365, selezionare **Configura** e poi visualizzare la sezione **File e contenuti**.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-126">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="7ab8f-127">Nella sezione **File e contenuti**, selezionare **Comprensione dei contenuti automatica**.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-127">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="7ab8f-128">Nella pagina **Comprensione dei contenuti automatica**, fare clic su **Inizia** e seguire le istruzioni per completare il processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-128">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ab8f-129">![Avviare la configurazione](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="7ab8f-129">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="7ab8f-130">Nella pagina **Configurare l’elaborazione moduli**, è possibile scegliere se si vuole consentire agli utenti di creare modelli di elaborazione moduli in raccolte documenti di SharePoint specifiche.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-130">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="7ab8f-131">Nella barra multifunzione della raccolta documenti sarà disponibile un'opzione del menu che consente di **Creare un modello di elaborazione moduli** nelle raccolte documenti di SharePoint in cui è abilitato.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-131">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="7ab8f-132">In **Quale raccolta di SharePoint deve mostrare l'opzione di creazione del modello di elaborazione moduli**, è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="7ab8f-132">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="7ab8f-133">**Librerie in tutti i siti di SharePoint** per renderla disponibile per tutte le raccolte di SharePoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-133">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="7ab8f-134">**Librerie in siti di SharePoint selezionati** e quindi selezionare i siti in cui si vuole rendere disponibile l'opzione oppure caricare un elenco di massimo 50 siti.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-134">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="7ab8f-135">**Nessuna raccolta di SharePoint** se non si vuole rendere l’opzione disponibile in alcun sito. È possibile modificare questa impostazione dopo la configurazione.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-135">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7ab8f-136">![Configurare l'elaborazione moduli](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="7ab8f-136">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="7ab8f-137">Rimuovere un sito dopo che l’opzione è stata inclusa, non influisce sui modelli esistenti applicati alle raccolte del sito o sulla possibilità di applicare modelli di analisi dei documenti a una raccolta.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-137">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="7ab8f-138">Nella pagina **Creare un centro contenuti**, è possibile creare un sito del centro contenuti di SharePoint in cui gli utenti possono creare e gestire i modelli di analisi dei documenti.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-138">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="7ab8f-139">Per **Nome del sito**, digitare il nome che si desidera assegnare al sito del centro contenuti.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-139">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="7ab8f-140">L’**Indirizzo del sito** mostrerà l'URL del sito in base a ciò che è stato selezionato per il nome del sito.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-140">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="7ab8f-141">Per modificarlo, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-141">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="7ab8f-142">![Creare un centro contenuti](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="7ab8f-142">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="7ab8f-143">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-143">Select **Next**.</span></span>

6. <span data-ttu-id="7ab8f-144">Nella pagina **Verificare e completare**, è possibile esaminare l'impostazione selezionata e scegliere se apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-144">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="7ab8f-145">Al termine, selezionare **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-145">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="7ab8f-146">Nella pagina di conferma, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-146">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="7ab8f-147">Si verrà indirizzati nuovamente alla pagina **Comprensione dei contenuti automatica**.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-147">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="7ab8f-148">In questa pagina è possibile selezionare **Gestisci** per modificare le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-148">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="7ab8f-149">Assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="7ab8f-149">Assign licenses</span></span>

<span data-ttu-id="7ab8f-150">Dopo aver configurato SharePoint Syntex, è necessario assegnare le licenze per gli utenti che useranno le funzionalità di SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-150">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="7ab8f-151">Per assegnare le licenze:</span><span class="sxs-lookup"><span data-stu-id="7ab8f-151">To assign licenses:</span></span>

1. <span data-ttu-id="7ab8f-152">Nell'interfaccia di amministrazione di Microsoft 365, in **Utenti** fare clic su **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-152">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="7ab8f-153">Selezionare gli utenti a cui si vuole assegnare una licenza e quindi scegliere **Gestisci licenze prodotto**.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-153">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="7ab8f-154">Scegliere **App** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-154">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="7ab8f-155">Selezionare **Mostra app per SharePoint Syntex**.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-155">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="7ab8f-156">In **App** verificare che l'opzione **Common Data Service per SharePoint Syntex**, **SharePoint Syntex** e **SharePoint Syntex - tipo SPO** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-156">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7ab8f-157">![Licenze di SharePoint Syntex nell'interfaccia di amministrazione di Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="7ab8f-157">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="7ab8f-158">Fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-158">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="7ab8f-159">Crediti di AI Builder</span><span class="sxs-lookup"><span data-stu-id="7ab8f-159">AI Builder credits</span></span>

<span data-ttu-id="7ab8f-160">Se nell'organizzazione sono presenti più di 300 licenze di SharePoint Syntex, si riceverà un milione di crediti di AI Builder.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-160">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="7ab8f-161">Se si hanno meno di 300 licenze, è necessario acquistare i crediti di AI Builder per poter usare l'elaborazione moduli.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-161">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="7ab8f-162">È possibile stimare la capacità di AI Builder che più adatta all’utente con [Calcolatore AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="7ab8f-162">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="7ab8f-163">Passare all'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) per controllare i crediti e il relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="7ab8f-163">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ab8f-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ab8f-164">See also</span></span>

[<span data-ttu-id="7ab8f-165">Panoramica del modello di elaborazione moduli</span><span class="sxs-lookup"><span data-stu-id="7ab8f-165">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="7ab8f-166">Istruzioni dettagliate per la creazione di un modello di analisi dei documenti (video)</span><span class="sxs-lookup"><span data-stu-id="7ab8f-166">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)
