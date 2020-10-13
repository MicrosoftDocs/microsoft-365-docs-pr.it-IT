---
title: Valutare Microsoft Threat Protection
description: Configurare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota per provare e sperimentare la soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni nell'organizzazione.
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
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447120"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="c9767-104">Creare un laboratorio di valutazione di Microsoft Threat Protection o un ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="c9767-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c9767-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c9767-105">**Applies to:**</span></span>
- <span data-ttu-id="c9767-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9767-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c9767-107">Lo scopo della creazione di questo laboratorio di valutazione o dell'ambiente pilota è di illustrare le funzionalità complete e integrate di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c9767-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="c9767-108">Sperimentare come questa soluzione di sicurezza intelligente rileva, impedisce, indaga automaticamente e risponde alle minacce avanzate dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9767-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="c9767-109">In questa guida vengono illustrati i passaggi necessari per avviare la valutazione di Microsoft Threat Protection in base ai percorsi di distribuzione consigliati.</span><span class="sxs-lookup"><span data-stu-id="c9767-109">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="c9767-110">L'obiettivo è facilitare la configurazione della soluzione di sicurezza in un ambiente lab con un account di prova oppure in un ambiente pilota in produzione con una licenza completa.</span><span class="sxs-lookup"><span data-stu-id="c9767-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="c9767-111">La preparazione del Lab di valutazione o dell'ambiente pilota può fornire informazioni sui casi di utilizzo delle operazioni di sicurezza ai responsabili decisionali nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9767-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="c9767-112">Al termine dell'esecuzione delle simulazioni di attacco e soddisfatte dei risultati, è possibile distribuirlo e operazionalizzare completamente nell'organizzazione con l'ausilio di professionisti o esperti di Microsoft Technical Sales nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9767-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="c9767-113">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="c9767-113">This guide will help you:</span></span>
- <span data-ttu-id="c9767-114">Configurare il server e i computer lab</span><span class="sxs-lookup"><span data-stu-id="c9767-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="c9767-115">Configurare Active Directory con utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="c9767-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="c9767-116">Configurazione e configurazione di Azure ATP, Office ATP, Microsoft Defender ATP e Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="c9767-116">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="c9767-117">Impostare i criteri locali per il server e i computer</span><span class="sxs-lookup"><span data-stu-id="c9767-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="c9767-118">Simulare un attacco di minacce per generare un evento o un avviso di testing in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9767-118">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="c9767-119">Per ottenere risultati ottimali, seguire le istruzioni per l'installazione del Lab il più fedelmente possibile.</span><span class="sxs-lookup"><span data-stu-id="c9767-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="c9767-120">Fasi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="c9767-120">Deployment phases</span></span>

<span data-ttu-id="c9767-121">Sono disponibili tre fasi per la creazione di un ambiente di laboratorio di valutazione di Microsoft Threat Protection e la relativa distribuzione:</span><span class="sxs-lookup"><span data-stu-id="c9767-121">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="c9767-122">Fase</span><span class="sxs-lookup"><span data-stu-id="c9767-122">Phase</span></span> | <span data-ttu-id="c9767-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9767-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="c9767-124">![Fase 1: preparazione](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="c9767-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="c9767-125">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="c9767-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="c9767-126">Informazioni su ciò che è necessario prendere in considerazione quando si distribuisce Microsoft Threat Protection in un laboratorio di valutazione o in un ambiente pilota:</span><span class="sxs-lookup"><span data-stu-id="c9767-126">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="c9767-127">-Parti interessate e disconnessione</span><span class="sxs-lookup"><span data-stu-id="c9767-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="c9767-128">-Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="c9767-128">- Environment considerations</span></span> <br><span data-ttu-id="c9767-129">-Access</span><span class="sxs-lookup"><span data-stu-id="c9767-129">- Access</span></span> <br><span data-ttu-id="c9767-130">-Configurazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c9767-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="c9767-131">-Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="c9767-131">- Configuration order</span></span>
|  <span data-ttu-id="c9767-132">![Fase 2: installazione](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="c9767-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="c9767-133">Fase 2: installazione</span><span class="sxs-lookup"><span data-stu-id="c9767-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="c9767-134">Eseguire la procedura iniziale per accedere al centro sicurezza Microsoft 365 per configurare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="c9767-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="c9767-135">Verrà visualizzata la guida per:</span><span class="sxs-lookup"><span data-stu-id="c9767-135">You'll be guided to:</span></span><br><br><span data-ttu-id="c9767-136">-Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c9767-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="c9767-137">-Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="c9767-137">- Configure domain</span></span><br><span data-ttu-id="c9767-138">-Assegnare licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c9767-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="c9767-139">-Completare l'installazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="c9767-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="c9767-140">![Fase 3: configurare & onboard](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="c9767-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="c9767-141">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="c9767-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="c9767-142">Configurare ogni pilastro di Microsoft Threat Protection e gli endpoint di bordo.</span><span class="sxs-lookup"><span data-stu-id="c9767-142">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="c9767-143">Verrà visualizzata la guida per:</span><span class="sxs-lookup"><span data-stu-id="c9767-143">You'll be guided to:</span></span><br><br><span data-ttu-id="c9767-144">-Configurare Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9767-144">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="c9767-145">-Configurare Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="c9767-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="c9767-146">-Configurare Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9767-146">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="c9767-147">-Configurare Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9767-147">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="c9767-148">Nell'ambito</span><span class="sxs-lookup"><span data-stu-id="c9767-148">In scope</span></span>

<span data-ttu-id="c9767-149">Le attività seguenti rientrano nell'ambito di questa guida:</span><span class="sxs-lookup"><span data-stu-id="c9767-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="c9767-150">Configurare Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c9767-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="c9767-151">Configurare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9767-151">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="c9767-152">Iscriversi a Microsoft 365 E5 trial o utilizzare la licenza completa se si sta eseguendo un progetto pilota</span><span class="sxs-lookup"><span data-stu-id="c9767-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="c9767-153">Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="c9767-153">Configure domain</span></span>
    -   <span data-ttu-id="c9767-154">Assegnare le licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c9767-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="c9767-155">Completamento dell'installazione guidata all'interno del portale</span><span class="sxs-lookup"><span data-stu-id="c9767-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="c9767-156">Configurare tutti i pilastri di protezione dalle minacce Microsoft in base alle procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="c9767-156">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="c9767-157">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9767-157">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="c9767-158">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9767-158">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="c9767-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c9767-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="c9767-160">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9767-160">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="c9767-161">Esclusioni</span><span class="sxs-lookup"><span data-stu-id="c9767-161">Out of scope</span></span>

<span data-ttu-id="c9767-162">Di seguito sono riportate le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="c9767-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="c9767-163">Configurazione di soluzioni di terze parti che possono essere integrate con Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9767-163">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="c9767-164">Test di penetrazione nell'ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="c9767-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="c9767-165">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c9767-165">Next step</span></span>
<span data-ttu-id="c9767-166">![Fase 1: preparazione](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="c9767-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="c9767-167">[Fase 1: preparazione](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="c9767-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="c9767-168">Preparare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="c9767-168">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
