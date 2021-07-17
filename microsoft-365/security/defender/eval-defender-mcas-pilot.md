---
title: Progetti Microsoft Cloud App Security con Microsoft 365 Defender, creare gruppi pilota, configurare il controllo dell'accesso condizionale, provare le funzionalità, configurare come parte di Microsoft 365 Defender
description: Configurare il laboratorio di Microsoft 365 Defender o l'ambiente pilota per testare e sperimentare la soluzione di sicurezza progettata per proteggere dispositivi, identità, dati e applicazioni.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458047"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a><span data-ttu-id="c2eb9-103">Progetti pilota Microsoft Cloud App Security con Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2eb9-103">Pilot Microsoft Cloud App Security with Microsoft 365 Defender</span></span>


<span data-ttu-id="c2eb9-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c2eb9-104">**Applies to:**</span></span>
- <span data-ttu-id="c2eb9-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2eb9-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="c2eb9-106">Questo articolo è [il passaggio 3 di 3 nel](eval-defender-mcas-overview.md) processo di configurazione dell'ambiente di valutazione per Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-106">This article is [Step 3 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="c2eb9-107">Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-mcas-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c2eb9-107">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="c2eb9-108">Utilizzare la procedura seguente per configurare il progetto pilota per Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-108">Use the following steps to setup and configure the pilot for Microsoft Cloud App Security.</span></span>


![Passaggi per la distribuzione pilota Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- <span data-ttu-id="c2eb9-110">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-110">Step 1.</span></span> [<span data-ttu-id="c2eb9-111">Creare il gruppo pilota- Ambito della distribuzione pilota per determinati gruppi di utenti</span><span class="sxs-lookup"><span data-stu-id="c2eb9-111">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [<span data-ttu-id="c2eb9-112">Passaggio 2. Configurare la protezione - Controllo app con accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="c2eb9-112">Step 2. Configure protection — Conditional Access App Control</span></span>](#step-2-configure-protection--conditional-access-app-control)
- [<span data-ttu-id="c2eb9-113">Passaggio 3. Funzionalità di prova: esercitazioni per la protezione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="c2eb9-113">Step 3. Try out capabilities — Walk through tutorials for protecting your environment</span></span>](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a><span data-ttu-id="c2eb9-114">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-114">Step 1.</span></span> <span data-ttu-id="c2eb9-115">Creare il gruppo pilota- Ambito della distribuzione pilota per determinati gruppi di utenti</span><span class="sxs-lookup"><span data-stu-id="c2eb9-115">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>

<span data-ttu-id="c2eb9-116">Microsoft Cloud App Security consente di impostare l'ambito della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-116">Microsoft Cloud App Security enables you to scope your deployment.</span></span> <span data-ttu-id="c2eb9-117">L'ambito consente di selezionare determinati gruppi di utenti da monitorare per le app o esclusi dal monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-117">Scoping allows you to select certain user groups to be monitored for apps or excluded from monitoring.</span></span> <span data-ttu-id="c2eb9-118">È possibile includere o escludere gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-118">You can include or exclude user groups.</span></span> <span data-ttu-id="c2eb9-119">Per l'ambito della distribuzione pilota, vedere [Distribuzione con ambito](/cloud-app-security/scoped-deployment).</span><span class="sxs-lookup"><span data-stu-id="c2eb9-119">To scope your pilot deployment, see [Scoped Deployment](/cloud-app-security/scoped-deployment).</span></span>


## <a name="step-2-configure-protection--conditional-access-app-control"></a><span data-ttu-id="c2eb9-120">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-120">Step 2.</span></span> <span data-ttu-id="c2eb9-121">Configurare la protezione - Controllo app con accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="c2eb9-121">Configure protection — Conditional Access App Control</span></span>

<span data-ttu-id="c2eb9-122">Una delle protezioni più potenti che puoi configurare è il controllo dell'app con accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-122">One of the most powerful protections you can configure is Conditional Access App Control.</span></span> <span data-ttu-id="c2eb9-123">Ciò richiede l'integrazione con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c2eb9-123">This requires integration with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="c2eb9-124">Ti consente di applicare criteri di accesso condizionale, inclusi i criteri correlati (come la richiesta di dispositivi integri), alle app cloud che hai sanzionato.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-124">It allows you to apply Conditional Access policies, including related policies (like requiring healthy devices), to cloud apps you've sanctioned.</span></span> 

<span data-ttu-id="c2eb9-125">Il primo passaggio nell'Microsoft Cloud App Security per gestire le app SaaS consiste nell'individuarle e quindi aggiungerle al tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-125">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="c2eb9-126">Per assistenza con l'individuazione, vedi [Individuare e gestire le app SaaS nella rete.](/cloud-app-security/tutorial-shadow-it)</span><span class="sxs-lookup"><span data-stu-id="c2eb9-126">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="c2eb9-127">Dopo aver individuato le app, [aggiungerle al tenant di Azure AD.](/azure/active-directory/manage-apps/add-application-portal)</span><span class="sxs-lookup"><span data-stu-id="c2eb9-127">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="c2eb9-128">È possibile iniziare a gestire questi elementi eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2eb9-128">You can begin to manage these by doing the following:</span></span>

- <span data-ttu-id="c2eb9-129">Innanzitutto, in Azure AD crea un nuovo criterio di accesso condizionale e configuralo in "Usa controllo app di accesso condizionale".</span><span class="sxs-lookup"><span data-stu-id="c2eb9-129">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="c2eb9-130">In questo modo la richiesta viene reindirizzata Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-130">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="c2eb9-131">Puoi creare un criterio e aggiungere tutte le app SaaS a questo criterio.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-131">You can create one policy and add all SaaS apps to this policy.</span></span>
- <span data-ttu-id="c2eb9-132">Successivamente, in Cloud App Security creare i criteri di sessione.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-132">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="c2eb9-133">Creare un criterio per ogni controllo che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-133">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="c2eb9-134">Per altre informazioni, incluse le app e i client supportati, vedi Proteggere le [app Microsoft Cloud App Security controllo dell'app di accesso condizionale.](/cloud-app-security/proxy-intro-aad)</span><span class="sxs-lookup"><span data-stu-id="c2eb9-134">For more information, including supported apps and clients, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span> 

<span data-ttu-id="c2eb9-135">Ad esempio, vedere [Criteri di Microsoft Cloud App Security consigliati per le app SaaS.](../office-365-security/mcas-saas-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c2eb9-135">For example policies, see [Recommended Microsoft Cloud App Security policies for SaaS apps](../office-365-security/mcas-saas-access-policies.md).</span></span> <span data-ttu-id="c2eb9-136">Questi criteri si basano su un set di [criteri](../office-365-security/microsoft-365-policies-configurations.md) comuni di identità e accesso ai dispositivi consigliati come punto di partenza per tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-136">These policies build on a set of [common identity and device access policies](../office-365-security/microsoft-365-policies-configurations.md) that are recommended as a starting point for all customers.</span></span> 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a><span data-ttu-id="c2eb9-137">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-137">Step 3.</span></span> <span data-ttu-id="c2eb9-138">Funzionalità di prova: esercitazioni per la protezione dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="c2eb9-138">Try out capabilities — Walk through tutorials for protecting your environment</span></span> 

<span data-ttu-id="c2eb9-139">La Microsoft Cloud App Security include una serie di esercitazioni per individuare i rischi e proteggere l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c2eb9-139">The Microsoft Cloud App Security documentation includes a series of tutorials to help you discover risk and protect your environment.</span></span> 

<span data-ttu-id="c2eb9-140">Provare Cloud App Security esercitazioni:</span><span class="sxs-lookup"><span data-stu-id="c2eb9-140">Try out Cloud App Security tutorials:</span></span>

- [<span data-ttu-id="c2eb9-141">Rilevare attività utente sospette</span><span class="sxs-lookup"><span data-stu-id="c2eb9-141">Detect suspicious user activity</span></span>](/cloud-app-security/tutorial-suspicious-activity)
- [<span data-ttu-id="c2eb9-142">Analizzare gli utenti rischiosi</span><span class="sxs-lookup"><span data-stu-id="c2eb9-142">Investigate risky users</span></span>](/cloud-app-security/tutorial-ueba)
- [<span data-ttu-id="c2eb9-143">Analizzare le app OAuth rischiose</span><span class="sxs-lookup"><span data-stu-id="c2eb9-143">Investigate risky OAuth apps</span></span>](/cloud-app-security/investigate-risky-oauth)
- [<span data-ttu-id="c2eb9-144">Individuare e proteggere le informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="c2eb9-144">Discover and protect sensitive information</span></span>](/cloud-app-security/tutorial-dlp)
- [<span data-ttu-id="c2eb9-145">Proteggere qualsiasi app nell'organizzazione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="c2eb9-145">Protect any app in your organization in real time</span></span>](/cloud-app-security/tutorial-proxy)
- [<span data-ttu-id="c2eb9-146">Bloccare i download di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="c2eb9-146">Block downloads of sensitive information</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)
- [<span data-ttu-id="c2eb9-147">Proteggere i file con la quarantena dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="c2eb9-147">Protect your files with admin quarantine</span></span>](/cloud-app-security/use-case-admin-quarantine)
- [<span data-ttu-id="c2eb9-148">Richiedere l'autenticazione dettagliata in base a un'azione rischiosa</span><span class="sxs-lookup"><span data-stu-id="c2eb9-148">Require step-up authentication upon risky action</span></span>](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a><span data-ttu-id="c2eb9-149">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c2eb9-149">Next steps</span></span>

[<span data-ttu-id="c2eb9-150">Analizzare e rispondere usando Microsoft 365 Defender in un ambiente pilota</span><span class="sxs-lookup"><span data-stu-id="c2eb9-150">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>](eval-defender-investigate-respond.md)

<span data-ttu-id="c2eb9-151">Tornare alla panoramica di [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c2eb9-151">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="c2eb9-152">Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c2eb9-152">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>