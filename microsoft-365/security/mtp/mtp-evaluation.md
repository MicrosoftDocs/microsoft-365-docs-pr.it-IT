---
title: Valutare Microsoft Threat Protection
description: Configurare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota per provare come la soluzione coordinata di protezione dalle minacce, progettata per proteggere dispositivi, identità, dati e applicazioni, può aiutare l'organizzazione
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 62852dfe75794d5d0e33453f978967fff40813e1
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816938"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="0884e-104">Creare un laboratorio di valutazione di Microsoft Threat Protection o un ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="0884e-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

<span data-ttu-id="0884e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0884e-105">**Applies to:**</span></span>
- <span data-ttu-id="0884e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0884e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0884e-107">Lo scopo della creazione di questo laboratorio di valutazione o di un ambiente pilota è di illustrare le funzionalità complete, integrate e intelligenti di Microsoft Threat Protection in Detection, Prevention, Investigation e Response che è possibile utilizzare nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0884e-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="0884e-108">In questa guida vengono illustrati i passaggi necessari per avviare la valutazione di Microsoft Threat Protection in base ai percorsi di distribuzione consigliati.</span><span class="sxs-lookup"><span data-stu-id="0884e-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="0884e-109">L'obiettivo è facilitare la configurazione dei servizi Microsoft Threat Protection integrati in un ambiente lab quando si utilizza un account di valutazione o in un ambiente pilota in fase di produzione quando si utilizza una licenza completa.</span><span class="sxs-lookup"><span data-stu-id="0884e-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment when using a trial account, or in a pilot environment in production when using a full license.</span></span> <span data-ttu-id="0884e-110">I risultati saranno utili per la presentazione dei casi di utilizzo delle operazioni di sicurezza ai responsabili decisionali della soluzione di sicurezza nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0884e-110">The results of which will be useful in presenting security operation use cases to security solution decision makers in your organization.</span></span> <span data-ttu-id="0884e-111">Al termine dell'esecuzione delle simulazioni di attacco e soddisfatto dei risultati, è possibile distribuirlo e operazionalizzare completamente nell'organizzazione con l'ausilio di professionisti o esperti di Microsoft Technical Sales nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0884e-111">When you’re done running your attack simulations, and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="0884e-112">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="0884e-112">This guide will help you:</span></span>
- <span data-ttu-id="0884e-113">Configurare il server e i computer lab</span><span class="sxs-lookup"><span data-stu-id="0884e-113">Set up your lab server and computers</span></span>
- <span data-ttu-id="0884e-114">Configurare Active Directory con utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="0884e-114">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="0884e-115">Configurazione e configurazione di Azure ATP, Office ATP, Microsoft Defender ATP e Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="0884e-115">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="0884e-116">Impostare i criteri locali per il server e i computer</span><span class="sxs-lookup"><span data-stu-id="0884e-116">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="0884e-117">Simulare un attacco di minacce per generare un evento o un avviso di testing in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0884e-117">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="0884e-118">Per ottenere risultati ottimali, seguire le istruzioni per l'installazione del Lab il più fedelmente possibile.</span><span class="sxs-lookup"><span data-stu-id="0884e-118">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="0884e-119">Fasi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="0884e-119">Deployment phases</span></span>

<span data-ttu-id="0884e-120">Sono disponibili tre fasi per la creazione di un ambiente di laboratorio di valutazione di Microsoft Threat Protection e la relativa distribuzione:</span><span class="sxs-lookup"><span data-stu-id="0884e-120">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="0884e-121">Fase</span><span class="sxs-lookup"><span data-stu-id="0884e-121">Phase</span></span> | <span data-ttu-id="0884e-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0884e-122">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="0884e-123">![Fase 1: preparazione](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="0884e-123">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="0884e-124">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="0884e-124">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="0884e-125">Informazioni su ciò che è necessario prendere in considerazione quando si distribuisce Microsoft Threat Protection in un laboratorio di valutazione o in un ambiente pilota:</span><span class="sxs-lookup"><span data-stu-id="0884e-125">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="0884e-126">-Parti interessate e disconnessione</span><span class="sxs-lookup"><span data-stu-id="0884e-126">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="0884e-127">-Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="0884e-127">- Environment considerations</span></span> <br><span data-ttu-id="0884e-128">-Access</span><span class="sxs-lookup"><span data-stu-id="0884e-128">- Access</span></span> <br><span data-ttu-id="0884e-129">-Configurazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0884e-129">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="0884e-130">-Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="0884e-130">- Configuration order</span></span>
|  <span data-ttu-id="0884e-131">![Fase 2: installazione](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="0884e-131">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="0884e-132">Fase 2: installazione</span><span class="sxs-lookup"><span data-stu-id="0884e-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="0884e-133">Eseguire la procedura iniziale per accedere al centro sicurezza Microsoft 365 per configurare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota.</span><span class="sxs-lookup"><span data-stu-id="0884e-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="0884e-134">Verrà visualizzata la guida per:</span><span class="sxs-lookup"><span data-stu-id="0884e-134">You'll be guided to:</span></span><br><br><span data-ttu-id="0884e-135">-Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="0884e-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="0884e-136">-Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="0884e-136">- Configure domain</span></span><br><span data-ttu-id="0884e-137">-Assegnare licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="0884e-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="0884e-138">-Completare l'installazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="0884e-138">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="0884e-139">![Fase 3: configurare & onboard](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="0884e-139">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="0884e-140">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="0884e-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="0884e-141">Configurare ogni pilastro di Microsoft Threat Protection e gli endpoint di bordo.</span><span class="sxs-lookup"><span data-stu-id="0884e-141">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="0884e-142">Verrà visualizzata la guida per:</span><span class="sxs-lookup"><span data-stu-id="0884e-142">You'll be guided to:</span></span><br><br><span data-ttu-id="0884e-143">-Configurare Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0884e-143">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="0884e-144">-Configurare Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="0884e-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="0884e-145">-Configurare Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0884e-145">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="0884e-146">-Configurare Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0884e-146">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="0884e-147">Nell'ambito</span><span class="sxs-lookup"><span data-stu-id="0884e-147">In scope</span></span>

<span data-ttu-id="0884e-148">Le attività seguenti rientrano nell'ambito di questa guida:</span><span class="sxs-lookup"><span data-stu-id="0884e-148">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="0884e-149">Configurare Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0884e-149">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="0884e-150">Configurare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0884e-150">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="0884e-151">Iscriversi a Microsoft 365 E5 trial o utilizzare la licenza completa se si sta eseguendo un progetto pilota</span><span class="sxs-lookup"><span data-stu-id="0884e-151">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="0884e-152">Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="0884e-152">Configure domain</span></span>
    -   <span data-ttu-id="0884e-153">Assegnare le licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="0884e-153">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="0884e-154">Completamento dell'installazione guidata all'interno del portale</span><span class="sxs-lookup"><span data-stu-id="0884e-154">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="0884e-155">Configurare tutti i pilastri di protezione dalle minacce Microsoft in base alle procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="0884e-155">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="0884e-156">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0884e-156">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="0884e-157">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0884e-157">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="0884e-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0884e-158">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="0884e-159">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0884e-159">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="0884e-160">Esclusioni</span><span class="sxs-lookup"><span data-stu-id="0884e-160">Out of scope</span></span>

<span data-ttu-id="0884e-161">Di seguito sono riportate le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="0884e-161">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="0884e-162">Configurazione di soluzioni di terze parti che possono essere integrate con Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0884e-162">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="0884e-163">Test di penetrazione nell'ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="0884e-163">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="0884e-164">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="0884e-164">Next step</span></span>
<span data-ttu-id="0884e-165">![Fase 1: preparazione](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="0884e-165">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="0884e-166">[Fase 1: preparazione](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="0884e-166">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="0884e-167">Preparare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="0884e-167">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
