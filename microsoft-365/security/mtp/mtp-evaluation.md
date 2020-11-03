---
title: Valutare Microsoft 365 Defender
description: Configurare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota per provare e sperimentare la soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni nell'organizzazione.
keywords: Valutazione di Microsoft Threat Protection, provare Microsoft Threat Protection, valutare Microsoft Threat Protection, Microsoft Threat Protection Lab, Microsoft Threat Protection Pilot, Cyber Security, Advanced Persistent Threat, Enterprise Security, Devices, Device, Identity, Users, data, Applications, Incidents, Automatic Investigation and remediation, Advanced Hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: d6c96f7720344721bb2786dc130c490a5a8ea657
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846485"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="ab50d-104">Creare un laboratorio di valutazione di Microsoft 365 Defender o un ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="ab50d-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ab50d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ab50d-105">**Applies to:**</span></span>
- <span data-ttu-id="ab50d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab50d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ab50d-107">Lo scopo della creazione di questo laboratorio di valutazione o di un ambiente pilota è quello di illustrare le funzionalità complete e integrate di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ab50d-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="ab50d-108">Sperimentare come questa soluzione di sicurezza intelligente rileva, impedisce, indaga automaticamente e risponde alle minacce avanzate dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ab50d-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="ab50d-109">Questa guida illustra i passaggi necessari per avviare la valutazione di Microsoft 365 Defender in base ai percorsi di distribuzione consigliati.</span><span class="sxs-lookup"><span data-stu-id="ab50d-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="ab50d-110">L'obiettivo è facilitare la configurazione della soluzione di sicurezza in un ambiente lab con un account di prova oppure in un ambiente pilota in produzione con una licenza completa.</span><span class="sxs-lookup"><span data-stu-id="ab50d-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="ab50d-111">La preparazione del Lab di valutazione o dell'ambiente pilota può fornire informazioni sui casi di utilizzo delle operazioni di sicurezza ai responsabili decisionali nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ab50d-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="ab50d-112">Al termine dell'esecuzione delle simulazioni di attacco e soddisfatte dei risultati, è possibile distribuirlo e operazionalizzare completamente nell'organizzazione con l'ausilio di professionisti o esperti di Microsoft Technical Sales nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ab50d-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="ab50d-113">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="ab50d-113">This guide will help you:</span></span>
- <span data-ttu-id="ab50d-114">Configurare il server e i computer lab</span><span class="sxs-lookup"><span data-stu-id="ab50d-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="ab50d-115">Configurare Active Directory con utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="ab50d-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="ab50d-116">Impostare e configurare Microsoft Defender per Identity, Microsoft Defender per Office 365, Microsoft Defender per endpoint e Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="ab50d-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="ab50d-117">Impostare i criteri locali per il server e i computer</span><span class="sxs-lookup"><span data-stu-id="ab50d-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="ab50d-118">Simulare un attacco di minaccia per generare un avviso o un evento di prova in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab50d-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="ab50d-119">Per ottenere risultati ottimali, seguire le istruzioni per l'installazione del Lab il più fedelmente possibile.</span><span class="sxs-lookup"><span data-stu-id="ab50d-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="ab50d-120">Fasi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="ab50d-120">Deployment phases</span></span>

<span data-ttu-id="ab50d-121">Sono disponibili tre fasi per la creazione di un ambiente di laboratorio di valutazione di Microsoft 365 Defender e la relativa distribuzione:</span><span class="sxs-lookup"><span data-stu-id="ab50d-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

|<span data-ttu-id="ab50d-122">Fase</span><span class="sxs-lookup"><span data-stu-id="ab50d-122">Phase</span></span> | <span data-ttu-id="ab50d-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab50d-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="ab50d-124">![Fase 1: preparazione](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="ab50d-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="ab50d-125">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="ab50d-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="ab50d-126">Informazioni su ciò che è necessario prendere in considerazione quando si distribuisce Microsoft 365 Defender in un laboratorio di valutazione o in un ambiente pilota:</span><span class="sxs-lookup"><span data-stu-id="ab50d-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="ab50d-127">-Parti interessate e disconnessione</span><span class="sxs-lookup"><span data-stu-id="ab50d-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="ab50d-128">-Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="ab50d-128">- Environment considerations</span></span> <br><span data-ttu-id="ab50d-129">-Access</span><span class="sxs-lookup"><span data-stu-id="ab50d-129">- Access</span></span> <br><span data-ttu-id="ab50d-130">-Configurazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ab50d-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="ab50d-131">-Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="ab50d-131">- Configuration order</span></span>
|  <span data-ttu-id="ab50d-132">![Fase 2: installazione](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="ab50d-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="ab50d-133">Fase 2: installazione</span><span class="sxs-lookup"><span data-stu-id="ab50d-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="ab50d-134">Eseguire la procedura iniziale per accedere al centro sicurezza Microsoft 365 per configurare l'ambiente pilota o il laboratorio di valutazione di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ab50d-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="ab50d-135">Verrà visualizzata la guida per:</span><span class="sxs-lookup"><span data-stu-id="ab50d-135">You'll be guided to:</span></span><br><br><span data-ttu-id="ab50d-136">-Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ab50d-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="ab50d-137">-Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="ab50d-137">- Configure domain</span></span><br><span data-ttu-id="ab50d-138">-Assegnare licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ab50d-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="ab50d-139">-Completare l'installazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="ab50d-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="ab50d-140">![Fase 3: configurare & onboard](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="ab50d-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="ab50d-141">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="ab50d-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="ab50d-142">Configurare ogni pilastro Microsoft 365 Defender e gli endpoint di bordo.</span><span class="sxs-lookup"><span data-stu-id="ab50d-142">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="ab50d-143">Verrà visualizzata la guida per:</span><span class="sxs-lookup"><span data-stu-id="ab50d-143">You'll be guided to:</span></span><br><br><span data-ttu-id="ab50d-144">-Configurare Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="ab50d-144">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="ab50d-145">-Configurare Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="ab50d-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="ab50d-146">-Configurare Microsoft Defender per Identity</span><span class="sxs-lookup"><span data-stu-id="ab50d-146">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="ab50d-147">-Configurare Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="ab50d-147">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="ab50d-148">Nell'ambito</span><span class="sxs-lookup"><span data-stu-id="ab50d-148">In scope</span></span>

<span data-ttu-id="ab50d-149">Le attività seguenti rientrano nell'ambito di questa guida:</span><span class="sxs-lookup"><span data-stu-id="ab50d-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="ab50d-150">Configurare Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ab50d-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="ab50d-151">Configurare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab50d-151">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="ab50d-152">Iscriversi a Microsoft 365 E5 trial o utilizzare la licenza completa se si sta eseguendo un progetto pilota</span><span class="sxs-lookup"><span data-stu-id="ab50d-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="ab50d-153">Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="ab50d-153">Configure domain</span></span>
    -   <span data-ttu-id="ab50d-154">Assegnare le licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ab50d-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="ab50d-155">Completamento dell'installazione guidata all'interno del portale</span><span class="sxs-lookup"><span data-stu-id="ab50d-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="ab50d-156">Configurare tutti i pilastri di Microsoft 365 Defender in base alle procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="ab50d-156">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="ab50d-157">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="ab50d-157">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="ab50d-158">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="ab50d-158">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="ab50d-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ab50d-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="ab50d-160">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ab50d-160">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="ab50d-161">Esclusioni</span><span class="sxs-lookup"><span data-stu-id="ab50d-161">Out of scope</span></span>

<span data-ttu-id="ab50d-162">Di seguito sono riportate le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="ab50d-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="ab50d-163">Configurazione di soluzioni di terze parti che possono essere integrate con Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab50d-163">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="ab50d-164">Test di penetrazione nell'ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="ab50d-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="ab50d-165">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ab50d-165">Next step</span></span>
<span data-ttu-id="ab50d-166">![Fase 1: preparazione](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="ab50d-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="ab50d-167">[Fase 1: preparazione](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="ab50d-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="ab50d-168">Preparare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="ab50d-168">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
