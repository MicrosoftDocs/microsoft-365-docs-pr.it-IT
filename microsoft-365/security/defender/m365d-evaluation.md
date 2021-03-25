---
title: Valutare Microsoft 365 Defender
description: Configurare il laboratorio di valutazione o l'ambiente pilota di Microsoft 365 Defender per provare e sperimentare la soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni nell'organizzazione.
keywords: Versione di valutazione di Microsoft Threat Protection, provare Microsoft Threat Protection, valutare Microsoft Threat Protection, Microsoft Threat Protection evaluation lab, microsoft threat protection pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2ea829e0e2697facd2522dbf16ced7d620662eee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068618"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="4ba7e-104">Creare un ambiente pilota o un laboratorio di valutazione di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ba7e-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4ba7e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4ba7e-105">**Applies to:**</span></span>
- <span data-ttu-id="4ba7e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ba7e-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="4ba7e-107">Questa guida consente di configurare un ambiente lab con utenti e gruppi, quindi di illustrare la configurazione delle funzionalità in Microsoft 365 Defender in modo da poter simulare un attacco di minacce e ottenere un risultato di prova significativo.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="4ba7e-108">Lo scopo della creazione di questo laboratorio di valutazione o ambiente pilota è illustrare le funzionalità complete e integrate di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="4ba7e-109">Scopri come questa soluzione di sicurezza intelligente rileva, impedisce, analizza automaticamente e risponde alle minacce avanzate dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="4ba7e-110">Verrà illustrata la procedura per avviare la valutazione di Microsoft 365 Defender in base ai percorsi di distribuzione consigliati.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="4ba7e-111">L'obiettivo è quello di configurare la soluzione di sicurezza in un ambiente lab con un account di prova o in un ambiente pilota in produzione con una licenza completa.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="4ba7e-112">La preparazione del laboratorio di valutazione o dell'ambiente pilota può essere utile per presentare i casi di utilizzo delle operazioni di sicurezza ai decision maker dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="4ba7e-113">Al termine dell'esecuzione delle simulazioni di attacco e si è soddisfatti dei risultati, è possibile distribuirlo e operarlo completamente nell'organizzazione con l'aiuto di tecnici o esperti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="4ba7e-114">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="4ba7e-114">This guide will help you:</span></span>
- <span data-ttu-id="4ba7e-115">Configurare il server lab e i computer</span><span class="sxs-lookup"><span data-stu-id="4ba7e-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="4ba7e-116">Configurare Active Directory con utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="4ba7e-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="4ba7e-117">Configurare Microsoft Defender per l'identità, Microsoft Defender per Office 365, Microsoft Defender for Endpoint e Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4ba7e-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="4ba7e-118">Configurare criteri locali per il server e i computer</span><span class="sxs-lookup"><span data-stu-id="4ba7e-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="4ba7e-119">Simulare un attacco di minaccia per generare un evento imprevisto o un avviso di test in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ba7e-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="4ba7e-120">Per ottenere risultati ottimali, seguire le istruzioni per la configurazione del lab il più possibile.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="4ba7e-121">Fasi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="4ba7e-121">Deployment phases</span></span>

<span data-ttu-id="4ba7e-122">La creazione di un ambiente lab di valutazione di Microsoft 365 Defender è in tre fasi.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Fasi di distribuzione: preparazione, installazione, onboard](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="4ba7e-124">Fase</span><span class="sxs-lookup"><span data-stu-id="4ba7e-124">Phase</span></span> | <span data-ttu-id="4ba7e-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ba7e-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="4ba7e-126">Fase 1: preparare</span><span class="sxs-lookup"><span data-stu-id="4ba7e-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="4ba7e-127">Informazioni su cosa è necessario considerare quando si distribuisce Microsoft 365 Defender in un laboratorio di valutazione o in un ambiente pilota:</span><span class="sxs-lookup"><span data-stu-id="4ba7e-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="4ba7e-128">- Parti interessate e disconnessione</span><span class="sxs-lookup"><span data-stu-id="4ba7e-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="4ba7e-129">- Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="4ba7e-129">- Environment considerations</span></span> <br><span data-ttu-id="4ba7e-130">- Accesso</span><span class="sxs-lookup"><span data-stu-id="4ba7e-130">- Access</span></span> <br><span data-ttu-id="4ba7e-131">- Configurazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4ba7e-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="4ba7e-132">- Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="4ba7e-132">- Configuration order</span></span>
|[<span data-ttu-id="4ba7e-133">Fase 2: installazione</span><span class="sxs-lookup"><span data-stu-id="4ba7e-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="4ba7e-134">Eseguire i passaggi iniziali per accedere al Centro sicurezza Microsoft 365 per configurare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="4ba7e-135">Sarai guidato a:</span><span class="sxs-lookup"><span data-stu-id="4ba7e-135">You'll be guided to:</span></span><br><br><span data-ttu-id="4ba7e-136">- Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4ba7e-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="4ba7e-137">- Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="4ba7e-137">- Configure domain</span></span><br><span data-ttu-id="4ba7e-138">- Assegnare le licenze di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4ba7e-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="4ba7e-139">- Completare la configurazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="4ba7e-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="4ba7e-140">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="4ba7e-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="4ba7e-141">Configurare ogni pilastro di Microsoft 365 Defender e gli endpoint di onboard.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="4ba7e-142">Sarai guidato a:</span><span class="sxs-lookup"><span data-stu-id="4ba7e-142">You'll be guided to:</span></span><br><br><span data-ttu-id="4ba7e-143">- Configurare Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="4ba7e-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="4ba7e-144">- Configurare Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4ba7e-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="4ba7e-145">- Configurare Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="4ba7e-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="4ba7e-146">- Configurare Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="4ba7e-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="4ba7e-147">Dopo aver completato questa guida, si sarebbero identificate le parti interessate coinvolte e le approvazioni necessarie, avere le autorizzazioni di accesso corrette, aver effettuato la registrazione per la versione di valutazione, configurato i domini e ognuno dei pilastri di Microsoft 365 Defender e gli endpoint verranno onboarded al servizio.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="4ba7e-148">Caratteristiche chiave</span><span class="sxs-lookup"><span data-stu-id="4ba7e-148">Key capabilities</span></span>

<span data-ttu-id="4ba7e-149">Mentre Microsoft 365 Defender offre molte funzionalità, lo scopo principale di questa guida alla distribuzione è quello di iniziare a usare i dispositivi di onboarding.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="4ba7e-150">Oltre all'onboarding, questa guida ti consente di iniziare con le funzionalità seguenti.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="4ba7e-151">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="4ba7e-151">Capability</span></span> | <span data-ttu-id="4ba7e-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ba7e-152">Description</span></span> 
:---|:---
<span data-ttu-id="4ba7e-153">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="4ba7e-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="4ba7e-154">Aiuta a proteggere l'intero ambiente di Office 365 dalle minacce odierne</span><span class="sxs-lookup"><span data-stu-id="4ba7e-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="4ba7e-155">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="4ba7e-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="4ba7e-156">Identifica e rileva le minacce su identità compromesse e azioni insider dannose.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="4ba7e-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4ba7e-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="4ba7e-158">Offre visibilità completa, controlla il viaggio dei dati e rileva le minacce informatiche nei servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="4ba7e-159">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="4ba7e-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="4ba7e-160">Impedisce, rileva e fornisce funzionalità di risposta alle minacce avanzate con una sicurezza completa degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="4ba7e-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="4ba7e-161">Nell'ambito</span><span class="sxs-lookup"><span data-stu-id="4ba7e-161">In scope</span></span>

<span data-ttu-id="4ba7e-162">Per questa guida sono disponibili le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ba7e-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="4ba7e-163">Configurare Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4ba7e-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="4ba7e-164">Configurare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ba7e-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="4ba7e-165">Iscriversi alla versione di valutazione di Microsoft 365 E5 o usare la licenza completa se si esegue un progetto pilota</span><span class="sxs-lookup"><span data-stu-id="4ba7e-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="4ba7e-166">Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="4ba7e-166">Configure domain</span></span>
    -   <span data-ttu-id="4ba7e-167">Assegnare licenze di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4ba7e-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="4ba7e-168">Completamento dell'installazione guidata all'interno del portale</span><span class="sxs-lookup"><span data-stu-id="4ba7e-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="4ba7e-169">Configurare tutti i pilastri di Microsoft 365 Defender in base alle procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="4ba7e-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="4ba7e-170">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="4ba7e-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="4ba7e-171">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="4ba7e-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="4ba7e-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4ba7e-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="4ba7e-173">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="4ba7e-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="4ba7e-174">Esclusioni</span><span class="sxs-lookup"><span data-stu-id="4ba7e-174">Out of scope</span></span>

<span data-ttu-id="4ba7e-175">Gli elementi seguenti non sono nell'ambito di questa guida alla distribuzione:</span><span class="sxs-lookup"><span data-stu-id="4ba7e-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="4ba7e-176">Configurazione di soluzioni di terze parti che potrebbero integrarsi con Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ba7e-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="4ba7e-177">Test di penetrazione nell'ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="4ba7e-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="4ba7e-178">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="4ba7e-178">Next step</span></span>
<span data-ttu-id="4ba7e-179">[Fase 1: preparare](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="4ba7e-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="4ba7e-180">Preparare il laboratorio di valutazione o l'ambiente pilota di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ba7e-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
