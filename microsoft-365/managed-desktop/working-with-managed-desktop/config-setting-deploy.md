---
title: Distribuire le impostazioni configurabili in Microsoft Managed Desktop
description: Distribuire e tenere traccia delle modifiche alle impostazioni configurabili in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, distribuzione, distribuzione a fasi, impostazioni configurabili
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: aad4995f9c329b0fd8fcbcc8b1d13379453c2a76
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287800"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a><span data-ttu-id="54cb4-104">Distribuire e tenere traccia delle impostazioni configurabili - Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="54cb4-104">Deploy and track configurable settings - Microsoft Managed Desktop</span></span>

<span data-ttu-id="54cb4-105">Dopo aver apportato modifiche alle categorie di impostazioni e aver in fasi una distribuzione, la pagina Stato distribuzione consente di iniziare a distribuire le impostazioni ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="54cb4-105">After you make changes to your setting categories and stage a deployment, the Deployment status page allows you to begin deploying your settings to groups.</span></span> <span data-ttu-id="54cb4-106">Questa pagina mostra un riepilogo di ogni impostazione configurabile.</span><span class="sxs-lookup"><span data-stu-id="54cb4-106">This page shows a summary of each configurable setting.</span></span> <span data-ttu-id="54cb4-107">Aprendo una categoria di impostazioni è possibile distribuire le impostazioni ai gruppi e tenere traccia dello stato di avanzamento di queste distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="54cb4-107">By opening a setting category you can deploy settings to groups and track the progress of these deployments.</span></span>

## <a name="deployment-statuses"></a><span data-ttu-id="54cb4-108">Stati della distribuzione</span><span class="sxs-lookup"><span data-stu-id="54cb4-108">Deployment statuses</span></span>

<span data-ttu-id="54cb4-109">Questi sono gli stati che verranno visualizzati per ogni distribuzione.</span><span class="sxs-lookup"><span data-stu-id="54cb4-109">These are the statuses you’ll see for each deployment.</span></span>

<span data-ttu-id="54cb4-110">Stato</span><span class="sxs-lookup"><span data-stu-id="54cb4-110">Status</span></span> | <span data-ttu-id="54cb4-111">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="54cb4-111">Explanation</span></span>
--- | ---
<span data-ttu-id="54cb4-112">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="54cb4-112">Deploy</span></span> | <span data-ttu-id="54cb4-113">La modifica è in attesa di essere distribuita in questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="54cb4-113">Your change is waiting to be deployed to this group.</span></span>
<span data-ttu-id="54cb4-114">In corso</span><span class="sxs-lookup"><span data-stu-id="54cb4-114">In progress</span></span> | <span data-ttu-id="54cb4-115">La modifica viene applicata ai dispositivi attivi in questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="54cb4-115">The change is being applied to active devices in this group.</span></span>
<span data-ttu-id="54cb4-116">Completa</span><span class="sxs-lookup"><span data-stu-id="54cb4-116">Complete</span></span> | <span data-ttu-id="54cb4-117">Modifica completata in tutti i dispositivi attivi in questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="54cb4-117">The change completed on all active devices in this group.</span></span>
<span data-ttu-id="54cb4-118">Non riuscito</span><span class="sxs-lookup"><span data-stu-id="54cb4-118">Failed</span></span> | <span data-ttu-id="54cb4-119">La modifica non è riuscita su un 10% dei dispositivi attivi nel gruppo, quindi la distribuzione è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="54cb4-119">The change failed on a 10 percent of active devices in the group, so the deployment was stopped.</span></span><br><br> <span data-ttu-id="54cb4-120">Una richiesta di supporto verrà aperta automaticamente con le Microsoft Managed Desktop per risolvere i problemi della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="54cb4-120">A support request will be automatically opened with Microsoft Managed Desktop operations to troubleshoot the deployment.</span></span>
<span data-ttu-id="54cb4-121">Ripristinato</span><span class="sxs-lookup"><span data-stu-id="54cb4-121">Reverted</span></span> | <span data-ttu-id="54cb4-122">La modifica è stata ripristinata all'ultima modifica distribuita correttamente in tutti i gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="54cb4-122">The change was reverted to the last change that was successfully deployed to all deployment groups.</span></span>

## <a name="deploy-changes"></a><span data-ttu-id="54cb4-123">Distribuire le modifiche</span><span class="sxs-lookup"><span data-stu-id="54cb4-123">Deploy changes</span></span>

<span data-ttu-id="54cb4-124">In queste istruzioni verrà mostrata l'immagine di sfondo del desktop.</span><span class="sxs-lookup"><span data-stu-id="54cb4-124">We’ll show Desktop background picture in these instructions.</span></span> <span data-ttu-id="54cb4-125">Dopo aver a fasi una distribuzione, è possibile distribuire le modifiche dalla pagina Stato distribuzione.</span><span class="sxs-lookup"><span data-stu-id="54cb4-125">After you’ve staged a deployment, you deploy changes from the Deployment status page.</span></span>

<span data-ttu-id="54cb4-126">**Per distribuire le modifiche**</span><span class="sxs-lookup"><span data-stu-id="54cb4-126">**To deploy changes**</span></span>

1. <span data-ttu-id="54cb4-127">Accedi a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passa al menu **Dispositivi**</span><span class="sxs-lookup"><span data-stu-id="54cb4-127">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="54cb4-128">Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="54cb4-128">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="54cb4-129">**Nell'area di** lavoro Stato distribuzione selezionare l'impostazione che si desidera distribuire e quindi selezionare la distribuzione a fasi da distribuire.</span><span class="sxs-lookup"><span data-stu-id="54cb4-129">In **Deployment status** workspace, select the setting you want to deploy, and then select the staged deployment to deploy.</span></span>
4. <span data-ttu-id="54cb4-130">Selezionare **Distribuisci** per distribuire la modifica a uno dei gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="54cb4-130">Select **Deploy** to deploy the change to one of the deployment groups.</span></span>

> [!NOTE]
> <span data-ttu-id="54cb4-131">L'icona di attenzione arancione indica che è disponibile un gruppo precedente per la distribuzione, in quanto è consigliabile implementarlo nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="54cb4-131">The orange caution icon indicates there is a previous group available for deployment as it’s recommended to roll out in order.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

<span data-ttu-id="54cb4-132">È consigliabile eseguire la distribuzione nei gruppi di distribuzione nell'ordine seguente: Test, First, Fast e quindi Broad.</span><span class="sxs-lookup"><span data-stu-id="54cb4-132">We recommend deploying to deployment groups in this order: Test, First, Fast, and then Broad.</span></span> 

<span data-ttu-id="54cb4-133">Quando le modifiche vengono completate in ogni gruppo, lo stato viene modificato in **Completa**.</span><span class="sxs-lookup"><span data-stu-id="54cb4-133">When changes complete in each group, the status changes to **Complete**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a><span data-ttu-id="54cb4-134">Ripristinare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="54cb4-134">Revert deployment</span></span>

<span data-ttu-id="54cb4-135">Dopo aver distribuito una modifica, è possibile ripristinare lo **stato della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="54cb4-135">After you’ve deployed a change, you can revert from **Deployment status**.</span></span> <span data-ttu-id="54cb4-136">Quando si ripristina una modifica **in corso** **o** Completata, la distribuzione corrente viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="54cb4-136">When you revert a change that is **In progress** or **Complete**, the current deployment stops.</span></span> <span data-ttu-id="54cb4-137">Verrà ripristinata l'ultima versione distribuita in tutti i gruppi.</span><span class="sxs-lookup"><span data-stu-id="54cb4-137">The setting will revert to the last version that was deployed to all groups.</span></span>

<span data-ttu-id="54cb4-138">Verrà illustrata la procedura per ripristinare una modifica utilizzando l'immagine di sfondo del desktop come esempio.</span><span class="sxs-lookup"><span data-stu-id="54cb4-138">We’ll show the steps to revert a change using the Desktop background picture as an example.</span></span> 

<span data-ttu-id="54cb4-139">**Per ripristinare una modifica**</span><span class="sxs-lookup"><span data-stu-id="54cb4-139">**To revert a change**</span></span>

1. <span data-ttu-id="54cb4-140">Accedi a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e passa al menu **Dispositivi**</span><span class="sxs-lookup"><span data-stu-id="54cb4-140">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu</span></span>
2. <span data-ttu-id="54cb4-141">Cercare la sezione Microsoft Managed Desktop, selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="54cb4-141">Look for the Microsoft Managed Desktop section, select **Settings**.</span></span>
3. <span data-ttu-id="54cb4-142">**Nell'area di lavoro** Stato distribuzione selezionare l'impostazione che si desidera ripristinare e quindi selezionare la distribuzione a fasi da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="54cb4-142">In **Deployment status** workspace, select the setting you want to revert, and then select the staged deployment to revert.</span></span>
4. <span data-ttu-id="54cb4-143">In **È necessario annullare questa modifica?** selezionare Ripristina **distribuzione.**</span><span class="sxs-lookup"><span data-stu-id="54cb4-143">Under **Need to revert this change?**, select **Revert deployment**.</span></span>

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a><span data-ttu-id="54cb4-144">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="54cb4-144">Additional resources</span></span>

- [<span data-ttu-id="54cb4-145">Panoramica delle impostazioni configurabili</span><span class="sxs-lookup"><span data-stu-id="54cb4-145">Configurable settings overview</span></span>](config-setting-overview.md)
- [<span data-ttu-id="54cb4-146">Riferimento alle impostazioni configurabili</span><span class="sxs-lookup"><span data-stu-id="54cb4-146">Configurable settings reference</span></span>](config-setting-ref.md) 
