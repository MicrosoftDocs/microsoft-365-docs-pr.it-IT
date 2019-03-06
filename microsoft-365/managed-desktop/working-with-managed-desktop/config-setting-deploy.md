---
title: Distribuire le impostazioni configurabili in Microsoft Managed Desktop
description: Distribuire e monitorare le modifiche alle impostazioni configurabili in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, deploy, Deployment a fasi, impostazioni configurabili
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 62a17c95f5dc6b11f446a27684c507d7aaa95b7b
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414170"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="9f0ea-104">Distribuire e monitorare le impostazioni configurabili-Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="9f0ea-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="9f0ea-105">Dopo aver apportato le modifiche alle categorie di impostazioni e aver eseguito una distribuzione, è possibile distribuire e registrare lo stato di avanzamento per la distribuzione in stato di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-105">After you make changes to your setting categories and stage a deployment, you can deploy and track progress for the deployment on Deployment status.</span></span> <span data-ttu-id="9f0ea-106">In questa pagina viene visualizzato un riepilogo di ogni impostazione configurabile.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="9f0ea-107">Aprire una categoria di impostazioni per visualizzare tutte le distribuzioni e i relativi dettagli, per distribuire le modifiche.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-107">Open a setting category to see each deployment and their details, to deploy the changes.</span></span> 

## <a name="deployment-statuses"></a><span data-ttu-id="9f0ea-108">Stati di distribuzione</span><span class="sxs-lookup"><span data-stu-id="9f0ea-108">Deployment statuses</span></span> 

<span data-ttu-id="9f0ea-109">Queste sono le statue che verranno visualizzate per ogni distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-109">These are the statues you’ll see for each deployment.</span></span>

<span data-ttu-id="9f0ea-110">Stato</span><span class="sxs-lookup"><span data-stu-id="9f0ea-110">Status</span></span>  | <span data-ttu-id="9f0ea-111">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="9f0ea-111">Explanation</span></span> 
--- | --- 
<span data-ttu-id="9f0ea-112">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="9f0ea-112">Deploy</span></span> | <span data-ttu-id="9f0ea-113">La modifica è in attesa di essere distribuita su questo anello.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-113">Your change is waiting to be deployed to this ring.</span></span>
<span data-ttu-id="9f0ea-114">In corso</span><span class="sxs-lookup"><span data-stu-id="9f0ea-114">In progress</span></span> | <span data-ttu-id="9f0ea-115">La modifica viene applicata ai dispositivi attivi in questo anello.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-115">The change is being applied to active devices in this ring.</span></span> 
<span data-ttu-id="9f0ea-116">Completa</span><span class="sxs-lookup"><span data-stu-id="9f0ea-116">Complete</span></span> | <span data-ttu-id="9f0ea-117">La modifica completata su tutti i dispositivi attivi in questo anello.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-117">The change completed on all active devices in this ring.</span></span> 
<span data-ttu-id="9f0ea-118">Failed</span><span class="sxs-lookup"><span data-stu-id="9f0ea-118">Failed</span></span> | <span data-ttu-id="9f0ea-119">La modifica ha avuto esito negativo su un 10% dei dispositivi attivi sul ring, quindi la distribuzione è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-119">The change failed on a 10 percent of active devices in the ring, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="9f0ea-120">Una richiesta di supporto verrà aperta automaticamente con le operazioni di Microsoft Managed Desktop per la risoluzione dei problemi relativi alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span> 
<span data-ttu-id="9f0ea-121">Ripristinati</span><span class="sxs-lookup"><span data-stu-id="9f0ea-121">Reverted</span></span> | <span data-ttu-id="9f0ea-122">La modifica è stata ripristinata all'Ultima modifica che è stata distribuita correttamente in tutti gli anelli di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-122">The change was reverted to the last change that was successfully deployed to all deployment rings.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="9f0ea-123">Distribuire le modifiche</span><span class="sxs-lookup"><span data-stu-id="9f0ea-123">Deploy changes</span></span>

<span data-ttu-id="9f0ea-124">In queste istruzioni viene visualizzata l'immagine di sfondo del desktop.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="9f0ea-125">Dopo aver organizzato una distribuzione, è necessario distribuire le modifiche dallo stato di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-125">After you’ve staged a deployment, you deploy changes from Deployment status.</span></span> 

<span data-ttu-id="9f0ea-126">**Per distribuire le modifiche**</span><span class="sxs-lookup"><span data-stu-id="9f0ea-126">**To deploy changes**</span></span>

1. <span data-ttu-id="9f0ea-127">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="9f0ea-127">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="9f0ea-128">In **Impostazioni**, selezionare \*\*\*\* configurabile.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-128">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="9f0ea-129">In area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera distribuire e quindi selezionare la distribuzione a fasi da distribuire.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="9f0ea-130">Fare \*\*\*\* clic su Distribuisci per distribuire la modifica a uno degli anelli di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-130">Select **Deploy** to deploy the change to one of the deployment rings.</span></span>

![Panoramica dello stato di distribuzione delle impostazioni conFigurabili](images/deploy-cs-overview.png)

<span data-ttu-id="9f0ea-132">Microsoft Managed Desktop consiglia la distribuzione agli anelli di distribuzione nell'ordine seguente: test, First, Fast e then Broad.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-132">Microsoft Managed Desktop recommends deploying to deployment rings in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="9f0ea-133">Quando le modifiche vengono completate in ogni anello, lo stato diventa **completo**.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-133">When changes complete in each ring, the status changes to **Complete**.</span></span>

![Completamento della distribuzione delle impostazioni conFigurabili](images/config-setting-complete.png)

## <a name="revert-deployment"></a><span data-ttu-id="9f0ea-135">Ripristinare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="9f0ea-135">Revert deployment</span></span>

<span data-ttu-id="9f0ea-136">In queste istruzioni viene visualizzata l'immagine di sfondo del desktop.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-136">We’ll show Desktop background picture in these instructions.</span></span> 

<span data-ttu-id="9f0ea-137">Dopo aver distribuito una modifica, è possibile ripristinare **lo stato della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-137">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="9f0ea-138">Quando si ripristina una modifica **in corso** o **completata**, la distribuzione corrente viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-138">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="9f0ea-139">L'impostazione ritornerà all'ultima versione distribuita in tutti gli anelli.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-139">The setting will revert to the last version that was deployed to all rings.</span></span> 

<span data-ttu-id="9f0ea-140">**Per annullare una modifica**</span><span class="sxs-lookup"><span data-stu-id="9f0ea-140">**To revert a change**</span></span>
1. <span data-ttu-id="9f0ea-141">Accedere al [portale di amministrazione di Microsoft managEd desktop](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="9f0ea-141">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="9f0ea-142">In **Impostazioni**, selezionare \*\*\*\* configurabile.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-142">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="9f0ea-143">Nell'area di lavoro **stato distribuzione** selezionare l'impostazione che si desidera ripristinare e quindi selezionare la distribuzione a fasi da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-143">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="9f0ea-144">In **necessità di ripristinare questa modifica**, selezionare **Ripristina distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="9f0ea-144">Under **Need to revert this change**, select **Revert deployment**.</span></span>

![Ripristinare la distribuzione delle impostazioni conFigurabili](images/config-setting-revert.png) 

## <a name="additional-resources"></a><span data-ttu-id="9f0ea-146">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9f0ea-146">Additional resources</span></span>
- [<span data-ttu-id="9f0ea-147">Panoramica delle impostazioni conFigurabili</span><span class="sxs-lookup"><span data-stu-id="9f0ea-147">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="9f0ea-148">Informazioni di riferimento sulle impostazioni conFigurabili</span><span class="sxs-lookup"><span data-stu-id="9f0ea-148">Configurable settings reference</span></span>](config-setting-ref.md) 