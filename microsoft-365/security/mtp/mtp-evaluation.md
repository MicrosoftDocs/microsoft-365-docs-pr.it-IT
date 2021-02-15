---
title: Valutare Microsoft 365 Defender
description: Configurare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender per provare e sperimentare la soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni nell'organizzazione.
keywords: Versione di valutazione di Microsoft Threat Protection, provare Microsoft Threat Protection, valutare Microsoft Threat Protection, laboratorio di valutazione di Microsoft Threat Protection, pilota di Microsoft Threat Protection, cyber security, minacce persistenti avanzate, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, eventi imprevisti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930211"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="f2fe3-104">Creare un ambiente pilota o un lab di valutazione di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2fe3-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f2fe3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f2fe3-105">**Applies to:**</span></span>
- <span data-ttu-id="f2fe3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2fe3-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="f2fe3-107">Questa guida consente di lavorare nella configurazione di un ambiente lab con utenti e gruppi, quindi guida l'utente attraverso la configurazione delle funzionalità in Microsoft 365 Defender in modo da poter simulare un attacco di minaccia e ottenere un risultato di prova significativo.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="f2fe3-108">Lo scopo della creazione di questo laboratorio di valutazione o ambiente pilota è illustrare le funzionalità complete e integrate di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="f2fe3-109">Scopri come questa soluzione di sicurezza intelligente rileva, impedisce, analizza automaticamente e risponde alle minacce avanzate dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="f2fe3-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="f2fe3-111">L'obiettivo è quello di aiutare a configurare la soluzione di sicurezza in un ambiente lab con un account di prova o in un ambiente pilota in produzione con una licenza completa.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="f2fe3-112">La preparazione del laboratorio di valutazione o dell'ambiente pilota può essere utile per presentare i casi d'uso delle operazioni di sicurezza ai decisori dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="f2fe3-113">Al termine dell'esecuzione delle simulazioni di attacco e si è soddisfatti dei risultati, è possibile distribuirlo e operarlo completamente nell'organizzazione con l'aiuto di tecnici o esperti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="f2fe3-114">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="f2fe3-114">This guide will help you:</span></span>
- <span data-ttu-id="f2fe3-115">Configurare il server lab e i computer</span><span class="sxs-lookup"><span data-stu-id="f2fe3-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="f2fe3-116">Configurare Active Directory con utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="f2fe3-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="f2fe3-117">Configurare Microsoft Defender per l'identità, Microsoft Defender per Office 365, Microsoft Defender per Endpoint e Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f2fe3-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f2fe3-118">Configurare i criteri locali per il server e i computer</span><span class="sxs-lookup"><span data-stu-id="f2fe3-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="f2fe3-119">Simulare un attacco di minaccia per generare un evento imprevisto o un avviso di test in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2fe3-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="f2fe3-120">Per ottenere risultati ottimali, seguire le istruzioni di configurazione del lab il più possibile.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="f2fe3-121">Fasi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="f2fe3-121">Deployment phases</span></span>

<span data-ttu-id="f2fe3-122">La creazione di un ambiente lab di valutazione di Microsoft 365 Defender è in tre fasi.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Fasi di distribuzione: preparazione, configurazione, onboard](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="f2fe3-124">Fase</span><span class="sxs-lookup"><span data-stu-id="f2fe3-124">Phase</span></span> | <span data-ttu-id="f2fe3-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2fe3-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="f2fe3-126">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="f2fe3-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="f2fe3-127">Informazioni su cosa è necessario considerare quando si distribuisce Microsoft 365 Defender in un ambiente di prova o pilota:</span><span class="sxs-lookup"><span data-stu-id="f2fe3-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="f2fe3-128">- Parti interessate e disconnessione</span><span class="sxs-lookup"><span data-stu-id="f2fe3-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="f2fe3-129">- Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="f2fe3-129">- Environment considerations</span></span> <br><span data-ttu-id="f2fe3-130">- Access</span><span class="sxs-lookup"><span data-stu-id="f2fe3-130">- Access</span></span> <br><span data-ttu-id="f2fe3-131">- Configurazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f2fe3-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="f2fe3-132">- Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="f2fe3-132">- Configuration order</span></span>
|[<span data-ttu-id="f2fe3-133">Fase 2: installazione</span><span class="sxs-lookup"><span data-stu-id="f2fe3-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="f2fe3-134">Eseguire i passaggi iniziali per accedere al Centro sicurezza Microsoft 365 per configurare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="f2fe3-135">L'utente verrà guidato a:</span><span class="sxs-lookup"><span data-stu-id="f2fe3-135">You'll be guided to:</span></span><br><br><span data-ttu-id="f2fe3-136">- Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f2fe3-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="f2fe3-137">- Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="f2fe3-137">- Configure domain</span></span><br><span data-ttu-id="f2fe3-138">- Assegnare le licenze di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f2fe3-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="f2fe3-139">- Completare la configurazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="f2fe3-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="f2fe3-140">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="f2fe3-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="f2fe3-141">Configurare ogni pilastro di Microsoft 365 Defender e gli endpoint di onboard.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="f2fe3-142">L'utente verrà guidato a:</span><span class="sxs-lookup"><span data-stu-id="f2fe3-142">You'll be guided to:</span></span><br><br><span data-ttu-id="f2fe3-143">- Configurare Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="f2fe3-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="f2fe3-144">- Configurare Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f2fe3-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="f2fe3-145">- Configurare Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="f2fe3-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="f2fe3-146">- Configurare Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="f2fe3-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="f2fe3-147">Dopo aver completato questa guida, si avrebbero identificato i cointeressati coinvolti e le approvazioni necessarie, avere le autorizzazioni di accesso corrette, aver effettuato la registrazione per la versione di valutazione, configurato i domini e ognuno dei pilastri di Microsoft 365 Defender e gli endpoint verranno onboarded al servizio.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="f2fe3-148">Caratteristiche chiave</span><span class="sxs-lookup"><span data-stu-id="f2fe3-148">Key capabilities</span></span>

<span data-ttu-id="f2fe3-149">Anche se Microsoft 365 Defender offre molte funzionalità, lo scopo principale di questa guida alla distribuzione è quello di iniziare a usare i dispositivi di onboarding.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="f2fe3-150">Oltre all'onboarding, queste indicazioni ti consentono di iniziare con le funzionalità seguenti.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="f2fe3-151">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="f2fe3-151">Capability</span></span> | <span data-ttu-id="f2fe3-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2fe3-152">Description</span></span> 
:---|:---
<span data-ttu-id="f2fe3-153">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="f2fe3-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="f2fe3-154">Aiuta a proteggere l'intero ambiente di Office 365 dalle minacce odierne</span><span class="sxs-lookup"><span data-stu-id="f2fe3-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="f2fe3-155">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="f2fe3-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="f2fe3-156">Identifica e rileva le minacce alle identità compromesse e alle azioni Insider dannose.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="f2fe3-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f2fe3-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="f2fe3-158">Offre visibilità completa, controlla il viaggio dei dati e rileva le minacce informatiche nei servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="f2fe3-159">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f2fe3-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="f2fe3-160">Impedisce, rileva e fornisce funzionalità di risposta alle minacce avanzate con sicurezza completa degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="f2fe3-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="f2fe3-161">Nell'ambito</span><span class="sxs-lookup"><span data-stu-id="f2fe3-161">In scope</span></span>

<span data-ttu-id="f2fe3-162">L'ambito di questa guida è quello delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2fe3-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="f2fe3-163">Configurare Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f2fe3-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="f2fe3-164">Configurare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2fe3-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="f2fe3-165">Iscriversi alla versione di valutazione di Microsoft 365 E5 o usare la licenza completa se si esegue un progetto pilota</span><span class="sxs-lookup"><span data-stu-id="f2fe3-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="f2fe3-166">Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="f2fe3-166">Configure domain</span></span>
    -   <span data-ttu-id="f2fe3-167">Assegnare licenze di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f2fe3-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="f2fe3-168">Completamento dell'installazione guidata all'interno del portale</span><span class="sxs-lookup"><span data-stu-id="f2fe3-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="f2fe3-169">Configurare tutti i pilastri di Microsoft 365 Defender in base alle procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="f2fe3-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="f2fe3-170">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="f2fe3-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="f2fe3-171">Che cosa è Microsoft Defender per identità?</span><span class="sxs-lookup"><span data-stu-id="f2fe3-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="f2fe3-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f2fe3-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="f2fe3-173">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f2fe3-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="f2fe3-174">Esclusioni</span><span class="sxs-lookup"><span data-stu-id="f2fe3-174">Out of scope</span></span>

<span data-ttu-id="f2fe3-175">Gli elementi seguenti non sono nell'ambito di questa guida alla distribuzione:</span><span class="sxs-lookup"><span data-stu-id="f2fe3-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="f2fe3-176">Configurazione di soluzioni di terze parti che potrebbero integrarsi con Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2fe3-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="f2fe3-177">Test di penetrazione nell'ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="f2fe3-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="f2fe3-178">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="f2fe3-178">Next step</span></span>
<span data-ttu-id="f2fe3-179">[Fase 1: preparazione](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="f2fe3-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="f2fe3-180">Preparare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2fe3-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
