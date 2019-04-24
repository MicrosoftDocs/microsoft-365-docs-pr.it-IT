---
title: Distribuire le impostazioni configurabili in Microsoft Managed Desktop
description: Distribuire e monitorare le modifiche alle impostazioni configurabili in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, deploy, Deployment a fasi, impostazioni configurabili
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4662373b926d07558ecedd05c9dfcf472ceb6357
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278426"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="06139-104">Distribuire e monitorare le impostazioni configurabili-Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="06139-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="06139-105">Dopo aver apportato le modifiche alle categorie di impostazioni e a organizzare una distribuzione, la pagina Stato distribuzione consente di iniziare a distribuire le impostazioni ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="06139-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="06139-106">In questa pagina viene visualizzato un riepilogo di ogni impostazione configurabile.</span><span class="sxs-lookup"><span data-stu-id="06139-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="06139-107">Aprendo una categoria di impostazione è possibile distribuire le impostazioni ai gruppi e monitorare lo stato di avanzamento di queste distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="06139-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="06139-108">Stati di distribuzione</span><span class="sxs-lookup"><span data-stu-id="06139-108">Deployment statuses</span></span> 

<span data-ttu-id="06139-109">Queste sono le statue che verranno visualizzate per ogni distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06139-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="06139-110">Stato</span><span class="sxs-lookup"><span data-stu-id="06139-110">Status</span></span>  | <span data-ttu-id="06139-111">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="06139-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="06139-112">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="06139-112">Deploy</span></span> | <span data-ttu-id="06139-113">La modifica è in attesa di essere distribuita in questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="06139-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="06139-114">In corso</span><span class="sxs-lookup"><span data-stu-id="06139-114">In progress</span></span> | <span data-ttu-id="06139-115">La modifica viene applicata ai dispositivi attivi di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="06139-115">The change is being applied to active devices in this group.</span></span> 
<span data-ttu-id="06139-116">Completa</span><span class="sxs-lookup"><span data-stu-id="06139-116">Complete</span></span> | <span data-ttu-id="06139-117">La modifica completata su tutti i dispositivi attivi di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="06139-117">The change completed on all active devices in this group.</span></span> 
<span data-ttu-id="06139-118">Failed</span><span class="sxs-lookup"><span data-stu-id="06139-118">Failed</span></span> | <span data-ttu-id="06139-119">La modifica ha avuto esito negativo su un 10% dei dispositivi attivi nel gruppo, quindi la distribuzione è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="06139-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="06139-120">Una richiesta di supporto verrà aperta automaticamente con le operazioni di Microsoft Managed Desktop per la risoluzione dei problemi relativi alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06139-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="06139-121">Ripristinati</span><span class="sxs-lookup"><span data-stu-id="06139-121">Reverted</span></span> | <span data-ttu-id="06139-122">La modifica è stata ripristinata all'Ultima modifica che è stata distribuita correttamente in tutti i gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06139-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="06139-123">Distribuire le modifiche</span><span class="sxs-lookup"><span data-stu-id="06139-123">Deploy changes</span></span>

<span data-ttu-id="06139-124">In queste istruzioni viene visualizzata l'immagine di sfondo del desktop.</span><span class="sxs-lookup"><span data-stu-id="06139-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="06139-125">Dopo aver organizzato una distribuzione, è necessario distribuire le modifiche dalla pagina Stato distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06139-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span> 

<span data-ttu-id="06139-126">**Per distribuire le modifiche**</span><span class="sxs-lookup"><span data-stu-id="06139-126">**To deploy changes**</span></span>

1. <span data-ttu-id="06139-127">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="06139-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="06139-128">In **Impostazioni**, selezionare \*\*\*\* configurabile.</span><span class="sxs-lookup"><span data-stu-id="06139-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="06139-129">In area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera distribuire e quindi selezionare la distribuzione a fasi da distribuire.</span><span class="sxs-lookup"><span data-stu-id="06139-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="06139-130">Fare \*\*\*\* clic su Distribuisci per distribuire la modifica a uno dei gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06139-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

![Panoramica dello stato di distribuzione delle impostazioni conFigurabili](images/deploy-cs-overview.png)

<span data-ttu-id="06139-132">Microsoft Managed Desktop consiglia la distribuzione ai gruppi di distribuzione nell'ordine seguente: test, First, Fast e then Broad.</span><span class="sxs-lookup"><span data-stu-id="06139-132">Microsoft Managed Desktop recommends deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="06139-133">Quando le modifiche vengono completate in ogni gruppo, lo stato diventa **completo**.</span><span class="sxs-lookup"><span data-stu-id="06139-133">When changes complete in each group, the status changes to **Complete**.</span></span>

![Completamento della distribuzione delle impostazioni conFigurabili](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="06139-135">Ripristinare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="06139-135">Revert deployment</span></span>

<span data-ttu-id="06139-136">Dopo aver distribuito una modifica, è possibile ripristinare **lo stato della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="06139-136">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="06139-137">Quando si ripristina una modifica **in corso** o **completata**, la distribuzione corrente viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="06139-137">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="06139-138">L'impostazione ritornerà all'ultima versione distribuita in tutti i gruppi.</span><span class="sxs-lookup"><span data-stu-id="06139-138">The setting will revert to the last version that was deployed to all groups.</span></span> 

<span data-ttu-id="06139-139">Vengono illustrati i passaggi da eseguire per ripristinare una modifica utilizzando l'immagine di sfondo del desktop come esempio.</span><span class="sxs-lookup"><span data-stu-id="06139-139">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="06139-140">**Per annullare una modifica**</span><span class="sxs-lookup"><span data-stu-id="06139-140">**To revert a change**</span></span>
1. <span data-ttu-id="06139-141">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="06139-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="06139-142">In **Impostazioni**, selezionare \*\*\*\* configurabile.</span><span class="sxs-lookup"><span data-stu-id="06139-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="06139-143">Nell'area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera ripristinare e quindi selezionare la distribuzione a fasi da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="06139-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="06139-144">In **necessità di ripristinare questa modifica**, selezionare **Ripristina distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="06139-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Ripristinare la distribuzione delle impostazioni conFigurabili](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="06139-146">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="06139-146">Additional resources</span></span>
- [<span data-ttu-id="06139-147">Panoramica delle impostazioni conFigurabili</span><span class="sxs-lookup"><span data-stu-id="06139-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="06139-148">Informazioni di riferimento sulle impostazioni conFigurabili</span><span class="sxs-lookup"><span data-stu-id="06139-148">Configurable settings reference</span></span>](config-setting-ref.md) 
