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
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659634"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="38a26-104">Creare un laboratorio di valutazione di Microsoft 365 Defender o un ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="38a26-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="38a26-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="38a26-105">**Applies to:**</span></span>
- <span data-ttu-id="38a26-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38a26-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="38a26-107">In questa guida viene descritto come configurare un ambiente lab con utenti e gruppi, quindi è possibile eseguire la configurazione delle funzionalità di Microsoft 365 Defender per simulare un attacco di minacce e ottenere un risultato di prova significativo.</span><span class="sxs-lookup"><span data-stu-id="38a26-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="38a26-108">Lo scopo della creazione di questo laboratorio di valutazione o di un ambiente pilota è quello di illustrare le funzionalità complete e integrate di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="38a26-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="38a26-109">Sperimentare come questa soluzione di sicurezza intelligente rileva, impedisce, indaga automaticamente e risponde alle minacce avanzate dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38a26-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="38a26-110">L'utente verrà guidato tramite la procedura per avviare la valutazione di Microsoft 365 Defender in base ai percorsi di distribuzione consigliati.</span><span class="sxs-lookup"><span data-stu-id="38a26-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="38a26-111">L'obiettivo è facilitare la configurazione della soluzione di sicurezza in un ambiente lab con un account di prova oppure in un ambiente pilota in produzione con una licenza completa.</span><span class="sxs-lookup"><span data-stu-id="38a26-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="38a26-112">La preparazione del Lab di valutazione o dell'ambiente pilota può fornire informazioni sui casi di utilizzo delle operazioni di sicurezza ai responsabili decisionali nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38a26-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="38a26-113">Al termine dell'esecuzione delle simulazioni di attacco e soddisfatte dei risultati, è possibile distribuirlo e operazionalizzare completamente nell'organizzazione con l'ausilio di professionisti o esperti di Microsoft Technical Sales nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38a26-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="38a26-114">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="38a26-114">This guide will help you:</span></span>
- <span data-ttu-id="38a26-115">Configurare il server e i computer lab</span><span class="sxs-lookup"><span data-stu-id="38a26-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="38a26-116">Configurare Active Directory con utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="38a26-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="38a26-117">Impostare e configurare Microsoft Defender per Identity, Microsoft Defender per Office 365, Microsoft Defender per endpoint e Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="38a26-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="38a26-118">Impostare i criteri locali per il server e i computer</span><span class="sxs-lookup"><span data-stu-id="38a26-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="38a26-119">Simulare un attacco di minaccia per generare un avviso o un evento di prova in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38a26-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="38a26-120">Per ottenere risultati ottimali, seguire le istruzioni per l'installazione del Lab il più fedelmente possibile.</span><span class="sxs-lookup"><span data-stu-id="38a26-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="38a26-121">Fasi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="38a26-121">Deployment phases</span></span>

<span data-ttu-id="38a26-122">Sono disponibili tre fasi per la creazione di un ambiente di laboratorio di valutazione di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="38a26-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Fasi di distribuzione: preparazione, installazione, Onboard](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="38a26-124">Fase</span><span class="sxs-lookup"><span data-stu-id="38a26-124">Phase</span></span> | <span data-ttu-id="38a26-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38a26-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="38a26-126">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="38a26-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="38a26-127">Informazioni su ciò che è necessario prendere in considerazione quando si distribuisce Microsoft 365 Defender in un laboratorio di valutazione o in un ambiente pilota:</span><span class="sxs-lookup"><span data-stu-id="38a26-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="38a26-128">-Parti interessate e disconnessione</span><span class="sxs-lookup"><span data-stu-id="38a26-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="38a26-129">-Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="38a26-129">- Environment considerations</span></span> <br><span data-ttu-id="38a26-130">-Access</span><span class="sxs-lookup"><span data-stu-id="38a26-130">- Access</span></span> <br><span data-ttu-id="38a26-131">-Configurazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="38a26-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="38a26-132">-Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="38a26-132">- Configuration order</span></span>
|[<span data-ttu-id="38a26-133">Fase 2: installazione</span><span class="sxs-lookup"><span data-stu-id="38a26-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="38a26-134">Eseguire la procedura iniziale per accedere al centro sicurezza Microsoft 365 per configurare l'ambiente pilota o il laboratorio di valutazione di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="38a26-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="38a26-135">Verrà visualizzata la guida per:</span><span class="sxs-lookup"><span data-stu-id="38a26-135">You'll be guided to:</span></span><br><br><span data-ttu-id="38a26-136">-Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="38a26-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="38a26-137">-Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="38a26-137">- Configure domain</span></span><br><span data-ttu-id="38a26-138">-Assegnare licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="38a26-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="38a26-139">-Completare l'installazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="38a26-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="38a26-140">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="38a26-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="38a26-141">Configurare ogni pilastro Microsoft 365 Defender e gli endpoint di bordo.</span><span class="sxs-lookup"><span data-stu-id="38a26-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="38a26-142">Verrà visualizzata la guida per:</span><span class="sxs-lookup"><span data-stu-id="38a26-142">You'll be guided to:</span></span><br><br><span data-ttu-id="38a26-143">-Configurare Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="38a26-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="38a26-144">-Configurare Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="38a26-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="38a26-145">-Configurare Microsoft Defender per Identity</span><span class="sxs-lookup"><span data-stu-id="38a26-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="38a26-146">-Configurare Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="38a26-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="38a26-147">Dopo aver completato questa guida, sono state identificate le parti interessate e le approvazioni necessarie, sono state apportate le autorizzazioni di accesso appropriate, sono state sottoscritte per il processo, i domini configurati e tutti i pilastri di Microsoft 365 Defender e gli endpoint verranno onboarded al servizio.</span><span class="sxs-lookup"><span data-stu-id="38a26-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="38a26-148">Caratteristiche chiave</span><span class="sxs-lookup"><span data-stu-id="38a26-148">Key capabilities</span></span>

<span data-ttu-id="38a26-149">Anche se Microsoft 365 Defender fornisce molte funzionalità, lo scopo principale di questa guida alla distribuzione è iniziare con i dispositivi onboarding.</span><span class="sxs-lookup"><span data-stu-id="38a26-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="38a26-150">Oltre all'onboarding, queste linee guida consentono di iniziare con le seguenti funzionalità.</span><span class="sxs-lookup"><span data-stu-id="38a26-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="38a26-151">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="38a26-151">Capability</span></span> | <span data-ttu-id="38a26-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38a26-152">Description</span></span> 
:---|:---
<span data-ttu-id="38a26-153">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="38a26-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="38a26-154">Consente di proteggere l'intero Office 365 ambiente dalle minacce odierne</span><span class="sxs-lookup"><span data-stu-id="38a26-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="38a26-155">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="38a26-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="38a26-156">Identifica e rileva le minacce per le identità compromesse e le azioni Insider dannose.</span><span class="sxs-lookup"><span data-stu-id="38a26-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="38a26-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="38a26-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="38a26-158">Offre una visibilità completa, il controllo dei dati di viaggio e rileva Cyberthreats tra i servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="38a26-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="38a26-159">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="38a26-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="38a26-160">Impedisce, rileva e fornisce le funzionalità di risposta alle minacce avanzate con la sicurezza completa degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="38a26-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="38a26-161">Nell'ambito</span><span class="sxs-lookup"><span data-stu-id="38a26-161">In scope</span></span>

<span data-ttu-id="38a26-162">Le attività seguenti rientrano nell'ambito di questa guida:</span><span class="sxs-lookup"><span data-stu-id="38a26-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="38a26-163">Configurare Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="38a26-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="38a26-164">Configurare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38a26-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="38a26-165">Iscriversi a Microsoft 365 E5 trial o utilizzare la licenza completa se si sta eseguendo un progetto pilota</span><span class="sxs-lookup"><span data-stu-id="38a26-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="38a26-166">Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="38a26-166">Configure domain</span></span>
    -   <span data-ttu-id="38a26-167">Assegnare le licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="38a26-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="38a26-168">Completamento dell'installazione guidata all'interno del portale</span><span class="sxs-lookup"><span data-stu-id="38a26-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="38a26-169">Configurare tutti i pilastri di Microsoft 365 Defender in base alle procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="38a26-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="38a26-170">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="38a26-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="38a26-171">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="38a26-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="38a26-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="38a26-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="38a26-173">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="38a26-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="38a26-174">Esclusioni</span><span class="sxs-lookup"><span data-stu-id="38a26-174">Out of scope</span></span>

<span data-ttu-id="38a26-175">Di seguito sono riportate le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="38a26-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="38a26-176">Configurazione di soluzioni di terze parti che possono essere integrate con Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38a26-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="38a26-177">Test di penetrazione nell'ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="38a26-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="38a26-178">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="38a26-178">Next step</span></span>
<span data-ttu-id="38a26-179">[Fase 1: preparazione](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="38a26-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="38a26-180">Preparare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="38a26-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
