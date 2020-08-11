---
title: 'Configurare la comprensione del contenuto (anteprima) '
description: Come configurare la corteccia del progetto.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5fcc7f78bfc12faae19ce2a3fbc77c4348da01de
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612703"
---
# <a name="set-up-content-understanding-preview"></a><span data-ttu-id="12a8f-103">Configurare la comprensione del contenuto (anteprima)</span><span class="sxs-lookup"><span data-stu-id="12a8f-103">Set up content understanding (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="12a8f-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="12a8f-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="12a8f-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="12a8f-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="12a8f-106">Gli amministratori possono utilizzare l'interfaccia di amministrazione di Microsoft 365 per impostare e configurare la comprensione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="12a8f-106">Admins can use the Microsoft 365 admin center to set up and configure content understanding.</span></span> 

<span data-ttu-id="12a8f-107">Prima di eseguire l'installazione, assicurarsi di pianificare il modo migliore per impostare e configurare la comprensione del contenuto nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="12a8f-107">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="12a8f-108">Ad esempio, è necessario prendere in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="12a8f-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="12a8f-109">Quali siti di SharePoint consentiranno di abilitare l'elaborazione dei moduli?</span><span class="sxs-lookup"><span data-stu-id="12a8f-109">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="12a8f-110">Tutti, alcuni o Seleziona siti?</span><span class="sxs-lookup"><span data-stu-id="12a8f-110">All of them, some, or select sites?</span></span>
- <span data-ttu-id="12a8f-111">Nome del centro di contenuto e chi è l'amministratore principale del sito?</span><span class="sxs-lookup"><span data-stu-id="12a8f-111">Name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="12a8f-112">Un amministratore può anche apportare modifiche alle impostazioni selezionate in qualsiasi momento dopo l'installazione tramite le impostazioni di gestione del contenuto nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12a8f-112">An admin can also make changes to your selected settings anytime after setup through the content understanding management settings in the Microsoft 365 admin center.</span></span>


## <a name="requirements"></a><span data-ttu-id="12a8f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12a8f-113">Requirements</span></span> 
<span data-ttu-id="12a8f-114">È necessario disporre delle autorizzazioni di amministratore globale o di amministratore di SharePoint per poter accedere all'interfaccia di amministrazione di Microsoft 365 e configurare la comprensione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="12a8f-114">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>


## <a name="to-set-up-content-understanding"></a><span data-ttu-id="12a8f-115">Per configurare la comprensione del contenuto</span><span class="sxs-lookup"><span data-stu-id="12a8f-115">To set up content understanding</span></span>

1. <span data-ttu-id="12a8f-116">Nell'interfaccia di amministrazione di Microsoft 365, selezionare **Setup**e quindi visualizzare la sezione relativa alle **informazioni sull'organizzazione** .</span><span class="sxs-lookup"><span data-stu-id="12a8f-116">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>
2. <span data-ttu-id="12a8f-117">Nella sezione **informazioni organizzative** selezionare **automatizza la comprensione del contenuto**.</span><span class="sxs-lookup"><span data-stu-id="12a8f-117">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Pagina di configurazione della conoscenza organizzativa](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="12a8f-119">Nella pagina **informazioni sull'automatizzazione del contenuto** , fare clic su Guida **introduttiva** per eseguire il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="12a8f-119">On the **Automate content understanding** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Avviare l'installazione](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. <span data-ttu-id="12a8f-121">Nella pagina **Configura elaborazione moduli** è possibile scegliere se si desidera consentire agli utenti di utilizzare il generatore ai per creare modelli di elaborazione dei moduli in specifiche raccolte documenti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="12a8f-121">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="12a8f-122">Nella barra multifunzione della raccolta documenti sarà disponibile un'opzione di menu per **creare un modello di elaborazione dei moduli** nelle raccolte documenti di SharePoint in cui è abilitata.</span><span class="sxs-lookup"><span data-stu-id="12a8f-122">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="12a8f-123">Per **il quale le raccolte di SharePoint dovrebbero mostrare l'opzione per creare un modello di elaborazione dei moduli**, è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="12a8f-123">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
    - <span data-ttu-id="12a8f-124">**Tutte le raccolte di SharePoint** per renderle disponibili per tutte le raccolte di SharePoint nel tenant.</span><span class="sxs-lookup"><span data-stu-id="12a8f-124">**All SharePoint libraries** to make it available to all SharePoint libraries in your tenant.</span></span></br>
    - <span data-ttu-id="12a8f-125">**Solo le raccolte nei siti selezionati**, quindi selezionare i siti in cui si desidera renderli disponibili.</span><span class="sxs-lookup"><span data-stu-id="12a8f-125">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>
    - <span data-ttu-id="12a8f-126">**Nessuna libreria di SharePoint** se attualmente non si desidera renderla disponibile per i siti (è possibile modificare questa impostazione dopo l'installazione).</span><span class="sxs-lookup"><span data-stu-id="12a8f-126">**No SharePoint libraries** if you currently don't want to make it available to any sites (you can change this after setup).</span></span>
</br>

   <span data-ttu-id="12a8f-127">![Configurare l'elaborazione dei moduli](../media/content-understanding/admin-configforms.png)
</span><span class="sxs-lookup"><span data-stu-id="12a8f-127">![Configure form processing](../media/content-understanding/admin-configforms.png)
</span></span></br>

   > [!Note]
   > <span data-ttu-id="12a8f-128">L'abilitazione di questa impostazione in una raccolta documenti di SharePoint non influisce sui modelli esistenti applicati alla raccolta o sulla possibilità di applicare i modelli di comprensione dei documenti a una raccolta.</span><span class="sxs-lookup"><span data-stu-id="12a8f-128">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 

    
5. <span data-ttu-id="12a8f-129">Nella pagina **Crea centro contenuto** è possibile creare un sito Centro contenuto di SharePoint in cui gli utenti possono creare e gestire i modelli di comprensione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="12a8f-129">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="12a8f-130">a.</span><span class="sxs-lookup"><span data-stu-id="12a8f-130">a.</span></span> <span data-ttu-id="12a8f-131">Per **nome sito**, digitare il nome che si desidera assegnare al sito Centro contenuto.</span><span class="sxs-lookup"><span data-stu-id="12a8f-131">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="12a8f-132">b.</span><span class="sxs-lookup"><span data-stu-id="12a8f-132">b.</span></span> <span data-ttu-id="12a8f-133">L' **indirizzo del sito** mostrerà l'URL del sito, in base alle operazioni selezionate per il nome del sito.</span><span class="sxs-lookup"><span data-stu-id="12a8f-133">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span></br>

    > [!Note] 
    > <span data-ttu-id="12a8f-134">Sebbene sia possibile selezionare una lingua supportata, tenere presente che i modelli di comprensione del contenuto possono essere creati solo per l'inglese.</span><span class="sxs-lookup"><span data-stu-id="12a8f-134">While you can select any supported language, note that content understanding models can only be created for English.</span></span></br>

      ![Creare centro contenuto](../media/content-understanding/admin-cu-create-cc.png)</br>


    <span data-ttu-id="12a8f-136">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="12a8f-136">Select **Next**.</span></span>
6. <span data-ttu-id="12a8f-137">Nella pagina **fine e revisione** è possibile esaminare l'impostazione selezionata e scegliere di apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="12a8f-137">On the **Finish and review** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="12a8f-138">Se si è soddisfatti delle selezioni, selezionare **attiva**.</span><span class="sxs-lookup"><span data-stu-id="12a8f-138">If you are satisfied with your selections, select **Activate**.</span></span>



7. <span data-ttu-id="12a8f-139">Verrà visualizzata la pagina **informazioni sull'attivazione del contenuto** , confermando che il sistema ha aggiunto le preferenze di elaborazione dei moduli e ha creato il sito Centro contenuto.</span><span class="sxs-lookup"><span data-stu-id="12a8f-139">The **Content understanding activated** page will display, confirming that the system has added your form processing preferences and creating the Content Center site.</span></span> <span data-ttu-id="12a8f-140">Scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="12a8f-140">Select **Done**.</span></span>

8. <span data-ttu-id="12a8f-141">Verrà restituita la pagina di **informazioni sul contenuto automatico** .</span><span class="sxs-lookup"><span data-stu-id="12a8f-141">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="12a8f-142">Da questa pagina, è possibile selezionare **Gestisci** per apportare modifiche alle impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="12a8f-142">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="12a8f-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12a8f-143">See also</span></span>



  






