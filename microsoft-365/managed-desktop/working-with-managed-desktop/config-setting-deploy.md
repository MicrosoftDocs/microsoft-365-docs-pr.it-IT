---
title: Distribuire le impostazioni configurabili in Microsoft Managed Desktop
description: Distribuire e monitorare le modifiche alle impostazioni configurabili in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, deploy, Deployment a fasi, impostazioni configurabili
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 244070c7fd2d5c98f87990bcb4ef6de96ca5a90c
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962243"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="dfd81-104">Distribuire e monitorare le impostazioni configurabili-Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="dfd81-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="dfd81-105">Dopo aver apportato le modifiche alle categorie di impostazioni e a organizzare una distribuzione, la pagina Stato distribuzione consente di iniziare a distribuire le impostazioni ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="dfd81-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="dfd81-106">In questa pagina viene visualizzato un riepilogo di ogni impostazione configurabile.</span><span class="sxs-lookup"><span data-stu-id="dfd81-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="dfd81-107">Aprendo una categoria di impostazione è possibile distribuire le impostazioni ai gruppi e monitorare lo stato di avanzamento di queste distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="dfd81-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="dfd81-108">Stati di distribuzione</span><span class="sxs-lookup"><span data-stu-id="dfd81-108">Deployment statuses</span></span> 

<span data-ttu-id="dfd81-109">Si tratta degli Stati che verranno visualizzati per ogni distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dfd81-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="dfd81-110">Stato</span><span class="sxs-lookup"><span data-stu-id="dfd81-110">Status</span></span>  | <span data-ttu-id="dfd81-111">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="dfd81-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="dfd81-112">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="dfd81-112">Deploy</span></span> | <span data-ttu-id="dfd81-113">La modifica è in attesa di essere distribuita in questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="dfd81-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="dfd81-114">In corso</span><span class="sxs-lookup"><span data-stu-id="dfd81-114">In progress</span></span> | <span data-ttu-id="dfd81-115">La modifica viene applicata ai dispositivi attivi di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="dfd81-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="dfd81-116">Completa</span><span class="sxs-lookup"><span data-stu-id="dfd81-116">Complete</span></span> | <span data-ttu-id="dfd81-117">La modifica completata su tutti i dispositivi attivi di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="dfd81-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="dfd81-118">Failed</span><span class="sxs-lookup"><span data-stu-id="dfd81-118">Failed</span></span> | <span data-ttu-id="dfd81-119">La modifica ha avuto esito negativo su un 10% dei dispositivi attivi nel gruppo, quindi la distribuzione è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="dfd81-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="dfd81-120">Una richiesta di supporto verrà aperta automaticamente con le operazioni di Microsoft Managed Desktop per la risoluzione dei problemi relativi alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dfd81-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="dfd81-121">Ripristinati</span><span class="sxs-lookup"><span data-stu-id="dfd81-121">Reverted</span></span> | <span data-ttu-id="dfd81-122">La modifica è stata ripristinata all'Ultima modifica che è stata distribuita correttamente in tutti i gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dfd81-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="dfd81-123">Distribuire le modifiche</span><span class="sxs-lookup"><span data-stu-id="dfd81-123">Deploy changes</span></span>

<span data-ttu-id="dfd81-124">In queste istruzioni viene visualizzata l'immagine di sfondo del desktop.</span><span class="sxs-lookup"><span data-stu-id="dfd81-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="dfd81-125">Dopo aver organizzato una distribuzione, è necessario distribuire le modifiche dalla pagina Stato distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dfd81-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="dfd81-126">**Per distribuire le modifiche**</span><span class="sxs-lookup"><span data-stu-id="dfd81-126">**To deploy changes**</span></span>

1. <span data-ttu-id="dfd81-127">Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="dfd81-127">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="dfd81-128">In **Impostazioni**, selezionare **configurabile**.</span><span class="sxs-lookup"><span data-stu-id="dfd81-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="dfd81-129">In area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera distribuire e quindi selezionare la distribuzione a fasi da distribuire.</span><span class="sxs-lookup"><span data-stu-id="dfd81-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="dfd81-130">Fare clic su **Distribuisci** per distribuire la modifica a uno dei gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dfd81-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

<span data-ttu-id="dfd81-131">![Area di lavoro stato distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dfd81-131">![Deployment status workspace.</span></span> <span data-ttu-id="dfd81-132">Riquadro siti attendibili sulla destra.</span><span class="sxs-lookup"><span data-stu-id="dfd81-132">Trusted sites pane on the right.</span></span> <span data-ttu-id="dfd81-133">Nella sezione gruppi di distribuzione sono disponibili tre colonne: gruppi di distribuzione, dispositivi e stato.</span><span class="sxs-lookup"><span data-stu-id="dfd81-133">In the Deployment groups section are three columns: deployment groups, devices, and status.</span></span> <span data-ttu-id="dfd81-134">Nella colonna stato "deploy" è evidenziato.](images/1deployedit.png)</span><span class="sxs-lookup"><span data-stu-id="dfd81-134">In the status column, "deploy" is highlighted.](images/1deployedit.png)</span></span>
<span data-ttu-id="dfd81-135">È consigliabile eseguire la distribuzione ai gruppi di distribuzione nell'ordine seguente: test, First, Fast e then Broad.</span><span class="sxs-lookup"><span data-stu-id="dfd81-135">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="dfd81-136">Quando le modifiche vengono completate in ogni gruppo, lo stato diventa **completo**.</span><span class="sxs-lookup"><span data-stu-id="dfd81-136">When changes complete in each group, the status changes to **Complete**.</span></span>

![Area di lavoro dello stato di distribuzione con colonne per Data aggiornata, versione, test, First, Fast e Broad.](images/2completeedit.png)

## <a name="revert-deployment"></a><span data-ttu-id="dfd81-139">Ripristinare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="dfd81-139">Revert deployment</span></span>

<span data-ttu-id="dfd81-140">Dopo aver distribuito una modifica, è possibile ripristinare **lo stato della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="dfd81-140">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="dfd81-141">Quando si ripristina una modifica **in corso** o **completata**, la distribuzione corrente viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="dfd81-141">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="dfd81-142">L'impostazione ritornerà all'ultima versione distribuita in tutti i gruppi.</span><span class="sxs-lookup"><span data-stu-id="dfd81-142">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="dfd81-143">Vengono illustrati i passaggi da eseguire per ripristinare una modifica utilizzando l'immagine di sfondo del desktop come esempio.</span><span class="sxs-lookup"><span data-stu-id="dfd81-143">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="dfd81-144">**Per annullare una modifica**</span><span class="sxs-lookup"><span data-stu-id="dfd81-144">**To revert a change**</span></span>
1. <span data-ttu-id="dfd81-145">Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="dfd81-145">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="dfd81-146">In **Impostazioni**, selezionare **configurabile**.</span><span class="sxs-lookup"><span data-stu-id="dfd81-146">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="dfd81-147">Nell'area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera ripristinare e quindi selezionare la distribuzione a fasi da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="dfd81-147">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="dfd81-148">In **necessità di ripristinare questa modifica**, selezionare **Ripristina distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="dfd81-148">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

![Area di lavoro stato distribuzione.](images/3revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="dfd81-152">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="dfd81-152">Additional resources</span></span>
- [<span data-ttu-id="dfd81-153">Panoramica delle impostazioni configurabili</span><span class="sxs-lookup"><span data-stu-id="dfd81-153">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="dfd81-154">Riferimento alle impostazioni configurabili</span><span class="sxs-lookup"><span data-stu-id="dfd81-154">Configurable settings reference</span></span>](config-setting-ref.md) 
