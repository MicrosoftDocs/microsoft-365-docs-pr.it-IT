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
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130891"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="bf3a2-104">Creare un laboratorio di valutazione di Microsoft 365 Defender o un ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="bf3a2-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bf3a2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="bf3a2-105">**Applies to:**</span></span>
- <span data-ttu-id="bf3a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf3a2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bf3a2-107">Lo scopo della creazione di questo laboratorio di valutazione o di un ambiente pilota è quello di illustrare le funzionalità complete e integrate di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bf3a2-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="bf3a2-108">Sperimentare come questa soluzione di sicurezza intelligente rileva, impedisce, indaga automaticamente e risponde alle minacce avanzate dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bf3a2-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="bf3a2-109">Questa guida illustra i passaggi necessari per avviare la valutazione di Microsoft 365 Defender in base ai percorsi di distribuzione consigliati.</span><span class="sxs-lookup"><span data-stu-id="bf3a2-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="bf3a2-110">L'obiettivo è facilitare la configurazione della soluzione di sicurezza in un ambiente lab con un account di prova oppure in un ambiente pilota in produzione con una licenza completa.</span><span class="sxs-lookup"><span data-stu-id="bf3a2-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="bf3a2-111">La preparazione del Lab di valutazione o dell'ambiente pilota può fornire informazioni sui casi di utilizzo delle operazioni di sicurezza ai responsabili decisionali nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bf3a2-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="bf3a2-112">Al termine dell'esecuzione delle simulazioni di attacco e soddisfatte dei risultati, è possibile distribuirlo e operazionalizzare completamente nell'organizzazione con l'ausilio di professionisti o esperti di Microsoft Technical Sales nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bf3a2-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="bf3a2-113">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="bf3a2-113">This guide will help you:</span></span>
- <span data-ttu-id="bf3a2-114">Configurare il server e i computer lab</span><span class="sxs-lookup"><span data-stu-id="bf3a2-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="bf3a2-115">Configurare Active Directory con utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="bf3a2-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="bf3a2-116">Impostare e configurare Microsoft Defender per Identity, Microsoft Defender per Office 365, Microsoft Defender per endpoint e Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="bf3a2-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="bf3a2-117">Impostare i criteri locali per il server e i computer</span><span class="sxs-lookup"><span data-stu-id="bf3a2-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="bf3a2-118">Simulare un attacco di minaccia per generare un avviso o un evento di prova in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf3a2-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="bf3a2-119">Per ottenere risultati ottimali, seguire le istruzioni per l'installazione del Lab il più fedelmente possibile.</span><span class="sxs-lookup"><span data-stu-id="bf3a2-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="bf3a2-120">Fasi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="bf3a2-120">Deployment phases</span></span>

<span data-ttu-id="bf3a2-121">Sono disponibili tre fasi per la creazione di un ambiente di laboratorio di valutazione di Microsoft 365 Defender e la relativa distribuzione:</span><span class="sxs-lookup"><span data-stu-id="bf3a2-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

![Fasi di distribuzione: preparazione, installazione, Onboard](../../media/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="bf3a2-123">Fase</span><span class="sxs-lookup"><span data-stu-id="bf3a2-123">Phase</span></span> | <span data-ttu-id="bf3a2-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf3a2-124">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="bf3a2-125">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="bf3a2-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="bf3a2-126">Informazioni su ciò che è necessario prendere in considerazione quando si distribuisce Microsoft 365 Defender in un laboratorio di valutazione o in un ambiente pilota:</span><span class="sxs-lookup"><span data-stu-id="bf3a2-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="bf3a2-127">-Parti interessate e disconnessione</span><span class="sxs-lookup"><span data-stu-id="bf3a2-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="bf3a2-128">-Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="bf3a2-128">- Environment considerations</span></span> <br><span data-ttu-id="bf3a2-129">-Access</span><span class="sxs-lookup"><span data-stu-id="bf3a2-129">- Access</span></span> <br><span data-ttu-id="bf3a2-130">-Configurazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bf3a2-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="bf3a2-131">-Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="bf3a2-131">- Configuration order</span></span>
|[<span data-ttu-id="bf3a2-132">Fase 2: installazione</span><span class="sxs-lookup"><span data-stu-id="bf3a2-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="bf3a2-133">Eseguire la procedura iniziale per accedere al centro sicurezza Microsoft 365 per configurare l'ambiente pilota o il laboratorio di valutazione di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bf3a2-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="bf3a2-134">Verrà visualizzata la guida per:</span><span class="sxs-lookup"><span data-stu-id="bf3a2-134">You'll be guided to:</span></span><br><br><span data-ttu-id="bf3a2-135">-Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bf3a2-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="bf3a2-136">-Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="bf3a2-136">- Configure domain</span></span><br><span data-ttu-id="bf3a2-137">-Assegnare licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bf3a2-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="bf3a2-138">-Completare l'installazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="bf3a2-138">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="bf3a2-139">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="bf3a2-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="bf3a2-140">Configurare ogni pilastro Microsoft 365 Defender e gli endpoint di bordo.</span><span class="sxs-lookup"><span data-stu-id="bf3a2-140">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="bf3a2-141">Verrà visualizzata la guida per:</span><span class="sxs-lookup"><span data-stu-id="bf3a2-141">You'll be guided to:</span></span><br><br><span data-ttu-id="bf3a2-142">-Configurare Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="bf3a2-142">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="bf3a2-143">-Configurare Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="bf3a2-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="bf3a2-144">-Configurare Microsoft Defender per Identity</span><span class="sxs-lookup"><span data-stu-id="bf3a2-144">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="bf3a2-145">-Configurare Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="bf3a2-145">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="bf3a2-146">Nell'ambito</span><span class="sxs-lookup"><span data-stu-id="bf3a2-146">In scope</span></span>

<span data-ttu-id="bf3a2-147">Le attività seguenti rientrano nell'ambito di questa guida:</span><span class="sxs-lookup"><span data-stu-id="bf3a2-147">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="bf3a2-148">Configurare Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bf3a2-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="bf3a2-149">Configurare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf3a2-149">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="bf3a2-150">Iscriversi a Microsoft 365 E5 trial o utilizzare la licenza completa se si sta eseguendo un progetto pilota</span><span class="sxs-lookup"><span data-stu-id="bf3a2-150">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="bf3a2-151">Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="bf3a2-151">Configure domain</span></span>
    -   <span data-ttu-id="bf3a2-152">Assegnare le licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bf3a2-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="bf3a2-153">Completamento dell'installazione guidata all'interno del portale</span><span class="sxs-lookup"><span data-stu-id="bf3a2-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="bf3a2-154">Configurare tutti i pilastri di Microsoft 365 Defender in base alle procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="bf3a2-154">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="bf3a2-155">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="bf3a2-155">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="bf3a2-156">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="bf3a2-156">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="bf3a2-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bf3a2-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="bf3a2-158">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="bf3a2-158">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="bf3a2-159">Esclusioni</span><span class="sxs-lookup"><span data-stu-id="bf3a2-159">Out of scope</span></span>

<span data-ttu-id="bf3a2-160">Di seguito sono riportate le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="bf3a2-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="bf3a2-161">Configurazione di soluzioni di terze parti che possono essere integrate con Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf3a2-161">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="bf3a2-162">Test di penetrazione nell'ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="bf3a2-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="bf3a2-163">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="bf3a2-163">Next step</span></span>
<span data-ttu-id="bf3a2-164">[Fase 1: preparazione](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="bf3a2-164">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="bf3a2-165">Preparare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="bf3a2-165">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
