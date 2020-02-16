---
title: Distribuire le impostazioni configurabili in Microsoft Managed Desktop
description: Distribuire e monitorare le modifiche alle impostazioni configurabili in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, deploy, Deployment a fasi, impostazioni configurabili
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e6946c138cb6fde15e35374b447038d5c302187e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085761"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="93dc6-104">Distribuire e monitorare le impostazioni configurabili-Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="93dc6-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="93dc6-105">Dopo aver apportato le modifiche alle categorie di impostazioni e a organizzare una distribuzione, la pagina Stato distribuzione consente di iniziare a distribuire le impostazioni ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="93dc6-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="93dc6-106">In questa pagina viene visualizzato un riepilogo di ogni impostazione configurabile.</span><span class="sxs-lookup"><span data-stu-id="93dc6-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="93dc6-107">Aprendo una categoria di impostazione è possibile distribuire le impostazioni ai gruppi e monitorare lo stato di avanzamento di queste distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="93dc6-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="93dc6-108">Stati di distribuzione</span><span class="sxs-lookup"><span data-stu-id="93dc6-108">Deployment statuses</span></span> 

<span data-ttu-id="93dc6-109">Si tratta degli Stati che verranno visualizzati per ogni distribuzione.</span><span class="sxs-lookup"><span data-stu-id="93dc6-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="93dc6-110">Stato</span><span class="sxs-lookup"><span data-stu-id="93dc6-110">Status</span></span>  | <span data-ttu-id="93dc6-111">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="93dc6-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="93dc6-112">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="93dc6-112">Deploy</span></span> | <span data-ttu-id="93dc6-113">La modifica è in attesa di essere distribuita in questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="93dc6-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="93dc6-114">In corso</span><span class="sxs-lookup"><span data-stu-id="93dc6-114">In progress</span></span> | <span data-ttu-id="93dc6-115">La modifica viene applicata ai dispositivi attivi di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="93dc6-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="93dc6-116">Completa</span><span class="sxs-lookup"><span data-stu-id="93dc6-116">Complete</span></span> | <span data-ttu-id="93dc6-117">La modifica completata su tutti i dispositivi attivi di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="93dc6-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="93dc6-118">Failed</span><span class="sxs-lookup"><span data-stu-id="93dc6-118">Failed</span></span> | <span data-ttu-id="93dc6-119">La modifica ha avuto esito negativo su un 10% dei dispositivi attivi nel gruppo, quindi la distribuzione è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="93dc6-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="93dc6-120">Una richiesta di supporto verrà aperta automaticamente con le operazioni di Microsoft Managed Desktop per la risoluzione dei problemi relativi alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="93dc6-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="93dc6-121">Ripristinati</span><span class="sxs-lookup"><span data-stu-id="93dc6-121">Reverted</span></span> | <span data-ttu-id="93dc6-122">La modifica è stata ripristinata all'Ultima modifica che è stata distribuita correttamente in tutti i gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="93dc6-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="93dc6-123">Distribuire le modifiche</span><span class="sxs-lookup"><span data-stu-id="93dc6-123">Deploy changes</span></span>

<span data-ttu-id="93dc6-124">In queste istruzioni viene visualizzata l'immagine di sfondo del desktop.</span><span class="sxs-lookup"><span data-stu-id="93dc6-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="93dc6-125">Dopo aver organizzato una distribuzione, è necessario distribuire le modifiche dalla pagina Stato distribuzione.</span><span class="sxs-lookup"><span data-stu-id="93dc6-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="93dc6-126">**Per distribuire le modifiche**</span><span class="sxs-lookup"><span data-stu-id="93dc6-126">**To deploy changes**</span></span>

1. <span data-ttu-id="93dc6-127">Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="93dc6-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="93dc6-128">In **Impostazioni**, selezionare **configurabile**.</span><span class="sxs-lookup"><span data-stu-id="93dc6-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="93dc6-129">In area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera distribuire e quindi selezionare la distribuzione a fasi da distribuire.</span><span class="sxs-lookup"><span data-stu-id="93dc6-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="93dc6-130">Fare clic su **Distribuisci** per distribuire la modifica a uno dei gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="93dc6-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE] 
> <span data-ttu-id="93dc6-131">L'icona di avviso arancione indica che è disponibile un gruppo precedente per la distribuzione, come consigliato per l'implementazione in ordine.</span><span class="sxs-lookup"><span data-stu-id="93dc6-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span> 

<span data-ttu-id="93dc6-132">![Area di lavoro stato distribuzione.</span><span class="sxs-lookup"><span data-stu-id="93dc6-132">![Deployment status workspace.</span></span> <span data-ttu-id="93dc6-133">Riquadro siti attendibili sulla destra.</span><span class="sxs-lookup"><span data-stu-id="93dc6-133">Trusted sites pane on the right.</span></span> <span data-ttu-id="93dc6-134">Nella sezione gruppi di distribuzione sono disponibili tre colonne: gruppi di distribuzione, dispositivi e stato.</span><span class="sxs-lookup"><span data-stu-id="93dc6-134">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="93dc6-135">Nella colonna stato "deploy" è evidenziato.](../../media/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="93dc6-135">In the status column, "deploy" is highlighted.](../../media/1deployedit.png)</span></span>
<span data-ttu-id="93dc6-136">È consigliabile eseguire la distribuzione ai gruppi di distribuzione nell'ordine seguente: test, First, Fast e then Broad.</span><span class="sxs-lookup"><span data-stu-id="93dc6-136">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="93dc6-137">Quando le modifiche vengono completate in ogni gruppo, lo stato diventa **completo**.</span><span class="sxs-lookup"><span data-stu-id="93dc6-137">When changes complete in each group, the status changes to **Complete**.</span></span>

![Area di lavoro dello stato di distribuzione con colonne per Data aggiornata, versione, test, First, Fast e Broad.](../../media/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="93dc6-140">Ripristinare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="93dc6-140">Revert deployment</span></span>

<span data-ttu-id="93dc6-141">Dopo aver distribuito una modifica, è possibile ripristinare **lo stato della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="93dc6-141">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="93dc6-142">Quando si ripristina una modifica **in corso** o **completata**, la distribuzione corrente viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="93dc6-142">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="93dc6-143">L'impostazione ritornerà all'ultima versione distribuita in tutti i gruppi.</span><span class="sxs-lookup"><span data-stu-id="93dc6-143">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="93dc6-144">Vengono illustrati i passaggi da eseguire per ripristinare una modifica utilizzando l'immagine di sfondo del desktop come esempio.</span><span class="sxs-lookup"><span data-stu-id="93dc6-144">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="93dc6-145">**Per annullare una modifica**</span><span class="sxs-lookup"><span data-stu-id="93dc6-145">**To revert a change**</span></span>
1. <span data-ttu-id="93dc6-146">Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="93dc6-146">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="93dc6-147">In **Impostazioni**, selezionare **configurabile**.</span><span class="sxs-lookup"><span data-stu-id="93dc6-147">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="93dc6-148">Nell'area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera ripristinare e quindi selezionare la distribuzione a fasi da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="93dc6-148">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="93dc6-149">In **necessità di ripristinare questa modifica**, selezionare **Ripristina distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="93dc6-149">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![Area di lavoro stato distribuzione.](../../media/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="93dc6-153">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="93dc6-153">Additional resources</span></span>
- [<span data-ttu-id="93dc6-154">Panoramica delle impostazioni configurabili</span><span class="sxs-lookup"><span data-stu-id="93dc6-154">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="93dc6-155">Riferimento alle impostazioni configurabili</span><span class="sxs-lookup"><span data-stu-id="93dc6-155">Configurable settings reference</span></span>](config-setting-ref.md) 
