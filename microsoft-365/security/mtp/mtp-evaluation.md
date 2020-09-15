---
title: Valutare Microsoft Threat Protection
description: Configurare l'ambiente di laboratorio di valutazione di Microsoft Threat Protection per provare come la soluzione coordinata di protezione dalle minacce progettata per proteggere dispositivi, identità, dati e applicazioni può aiutare l'organizzazione
keywords: Microsoft Threat Protection Trial, provare Microsoft Threat Protection, valutare Microsoft Threat Protection, Microsoft Threat Protection Lab, sicurezza cibernetica, Advanced Persistent Threat, Enterprise Security, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi automatizzata e correzione, ricerca avanzata
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
ms.openlocfilehash: a9d7b514aac8d1a769c0dabf6dcdb54f4bcb447b
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47649962"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="430ac-104">Creare un ambiente lab di valutazione di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="430ac-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="430ac-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="430ac-105">**Applies to:**</span></span>
- <span data-ttu-id="430ac-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="430ac-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="430ac-107">Lo scopo della creazione di questo ambiente di laboratorio di valutazione consiste nell'illustrare le funzionalità complete, integrate e intelligenti di Microsoft Threat Protection in Detection, Prevention, Investigation e Response che è possibile utilizzare nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="430ac-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="430ac-108">In questa guida vengono illustrati i passaggi necessari per avviare la valutazione di Microsoft Threat Protection in base ai percorsi di distribuzione consigliati.</span><span class="sxs-lookup"><span data-stu-id="430ac-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="430ac-109">L'obiettivo è facilitare la configurazione dei servizi di Microsoft Threat Protection integrati in un ambiente lab o come prova del concetto (POC) quando si presentano ai responsabili delle decisioni della soluzione di sicurezza nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="430ac-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="430ac-110">Dopo aver completato l'esecuzione delle simulazioni di attacco, l'analisi e la risposta automatizzate e sono soddisfatte con i risultati, è possibile distribuirla nell'ambiente di produzione con l'ausilio di professionisti o esperti di Microsoft Technical Sales all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="430ac-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="430ac-111">Questa guida ti aiuterà a:</span><span class="sxs-lookup"><span data-stu-id="430ac-111">This guide will help you:</span></span>
- <span data-ttu-id="430ac-112">Configurare il server e i computer lab</span><span class="sxs-lookup"><span data-stu-id="430ac-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="430ac-113">Configurare Active Directory con utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="430ac-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="430ac-114">Configurazione e configurazione di Azure ATP, Office ATP, Microsoft Defender ATP e Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="430ac-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="430ac-115">Impostare i criteri locali per il server e i computer</span><span class="sxs-lookup"><span data-stu-id="430ac-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="430ac-116">Simulare un attacco di minacce per generare un evento o un avviso di testing in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="430ac-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="430ac-117">Per ottenere risultati ottimali, seguire le istruzioni per l'installazione del Lab il più fedelmente possibile.</span><span class="sxs-lookup"><span data-stu-id="430ac-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="430ac-118">Fasi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="430ac-118">Deployment phases</span></span>

<span data-ttu-id="430ac-119">Sono disponibili tre fasi per la creazione di un ambiente di laboratorio di valutazione di Microsoft Threat Protection e la relativa distribuzione:</span><span class="sxs-lookup"><span data-stu-id="430ac-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="430ac-120">Fase</span><span class="sxs-lookup"><span data-stu-id="430ac-120">Phase</span></span> | <span data-ttu-id="430ac-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="430ac-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="430ac-122">![Fase 1: preparazione](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="430ac-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="430ac-123">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="430ac-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="430ac-124">Informazioni su ciò che è necessario prendere in considerazione quando si distribuisce Microsoft Threat Protection in un ambiente di prova:</span><span class="sxs-lookup"><span data-stu-id="430ac-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="430ac-125">-Parti interessate e disconnessione</span><span class="sxs-lookup"><span data-stu-id="430ac-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="430ac-126">-Considerazioni sull'ambiente</span><span class="sxs-lookup"><span data-stu-id="430ac-126">- Environment considerations</span></span> <br><span data-ttu-id="430ac-127">-Access</span><span class="sxs-lookup"><span data-stu-id="430ac-127">- Access</span></span> <br><span data-ttu-id="430ac-128">-Configurazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="430ac-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="430ac-129">-Ordine di configurazione</span><span class="sxs-lookup"><span data-stu-id="430ac-129">- Configuration order</span></span>
|  <span data-ttu-id="430ac-130">![Fase 2: installazione](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="430ac-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="430ac-131">Fase 2: installazione</span><span class="sxs-lookup"><span data-stu-id="430ac-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="430ac-132">Eseguire la procedura iniziale per accedere a Microsoft 365 Security Center per configurare l'ambiente di valutazione di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="430ac-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="430ac-133">Verrà guidato per:</span><span class="sxs-lookup"><span data-stu-id="430ac-133">You will be guided to:</span></span><br><br><span data-ttu-id="430ac-134">-Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="430ac-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="430ac-135">-Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="430ac-135">- Configure domain</span></span><br><span data-ttu-id="430ac-136">-Assegnare licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="430ac-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="430ac-137">-Completare l'installazione guidata nel portale</span><span class="sxs-lookup"><span data-stu-id="430ac-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="430ac-138">![Fase 3: configurare & onboard](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="430ac-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="430ac-139">Fase 3: configurare & onboard</span><span class="sxs-lookup"><span data-stu-id="430ac-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="430ac-140">Configurare ogni pilastro di Microsoft Threat Protection e gli endpoint di bordo.</span><span class="sxs-lookup"><span data-stu-id="430ac-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="430ac-141">Verrà guidato per:</span><span class="sxs-lookup"><span data-stu-id="430ac-141">You will be guided to:</span></span><br><br><span data-ttu-id="430ac-142">-Configurare Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="430ac-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="430ac-143">-Configurare Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="430ac-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="430ac-144">-Configurare Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="430ac-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="430ac-145">-Configurare Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="430ac-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="430ac-146">Nell'ambito</span><span class="sxs-lookup"><span data-stu-id="430ac-146">In scope</span></span>

<span data-ttu-id="430ac-147">Di seguito sono riportate le opzioni per questa guida all'ambiente lab di valutazione:</span><span class="sxs-lookup"><span data-stu-id="430ac-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="430ac-148">Configurare Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="430ac-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="430ac-149">Configurare Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="430ac-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="430ac-150">Iscriversi alla versione di valutazione di Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="430ac-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="430ac-151">Configurare il dominio</span><span class="sxs-lookup"><span data-stu-id="430ac-151">Configure domain</span></span>
    -   <span data-ttu-id="430ac-152">Assegnare le licenze Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="430ac-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="430ac-153">Completamento dell'installazione guidata all'interno del portale</span><span class="sxs-lookup"><span data-stu-id="430ac-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="430ac-154">Configurare tutti i pilastri di protezione dalle minacce Microsoft in base alle procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="430ac-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="430ac-155">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="430ac-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="430ac-156">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="430ac-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="430ac-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="430ac-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="430ac-158">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="430ac-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="430ac-159">Esclusioni</span><span class="sxs-lookup"><span data-stu-id="430ac-159">Out of scope</span></span>

<span data-ttu-id="430ac-160">Di seguito sono riportate le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="430ac-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="430ac-161">Configurazione di soluzioni di terze parti che possono essere integrate con Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="430ac-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="430ac-162">Test di penetrazione nell'ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="430ac-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="430ac-163">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="430ac-163">Next step</span></span>
<span data-ttu-id="430ac-164">![Fase 1: preparazione](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="430ac-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="430ac-165">[Fase 1: preparazione](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="430ac-165">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="430ac-166">Preparare l'ambiente lab di valutazione di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="430ac-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
