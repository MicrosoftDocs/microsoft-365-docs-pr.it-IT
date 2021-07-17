---
title: Abilitare l'ambiente di valutazione per Microsoft Cloud App Security
description: Informazioni sull'architettura di MCAS in Microsoft Defender per Office 365 e comprendere le interazioni tra i Microsoft 365 Defender prodotti.
keywords: Microsoft 365 Defender prova, provare Microsoft 365 Defender, valutare Microsoft 365 Defender, laboratorio di valutazione Microsoft 365 Defender, pilota di Microsoft 365 Defender, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458050"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a><span data-ttu-id="0ef06-104">Abilitare l'ambiente di valutazione per Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0ef06-104">Enable the evaluation environment for Microsoft Cloud App Security</span></span>


<span data-ttu-id="0ef06-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0ef06-105">**Applies to:**</span></span>

- <span data-ttu-id="0ef06-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ef06-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0ef06-107">Questo articolo è [il passaggio 2 di 2](eval-defender-mcas-overview.md) nel processo di configurazione dell'ambiente di valutazione per Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="0ef06-107">This article is [Step 2 of 2](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="0ef06-108">Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-mcas-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0ef06-108">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="0ef06-109">Questo articolo illustra il processo di accesso al portale Cloud App Security e la configurazione dell'integrazione necessaria per raccogliere i dati sul traffico delle app cloud.</span><span class="sxs-lookup"><span data-stu-id="0ef06-109">This article walks you through the process of accessing the Cloud App Security portal and configuring the necessary integration to collect cloud app traffic data.</span></span>

<span data-ttu-id="0ef06-110">Per individuare le app cloud usate nell'ambiente, è possibile eseguire una o entrambe le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ef06-110">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="0ef06-111">Iniziare rapidamente a utilizzare Cloud Discovery integrandosi con Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0ef06-111">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="0ef06-112">Questa integrazione nativa consente di avviare immediatamente la raccolta di dati sul traffico cloud nei dispositivi Windows 10, all'interno e all'uscita dalla rete.</span><span class="sxs-lookup"><span data-stu-id="0ef06-112">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="0ef06-113">Per individuare tutte le app cloud accessibili da tutti i dispositivi connessi alla rete, distribuire l'Cloud App Security di log nei firewall e in altri proxy.</span><span class="sxs-lookup"><span data-stu-id="0ef06-113">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="0ef06-114">In questo modo vengono raccolti i dati dagli endpoint e inviati a Cloud App Security per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="0ef06-114">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="0ef06-115">Cloud App Security si integra in modo nativo con alcuni proxy di terze parti per altre funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0ef06-115">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="0ef06-116">Questo articolo include indicazioni per entrambi i metodi.</span><span class="sxs-lookup"><span data-stu-id="0ef06-116">This article includes guidance for both methods.</span></span>

<span data-ttu-id="0ef06-117">Eseguire la procedura seguente per configurare Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="0ef06-117">Use the following steps to set up Microsoft Cloud App Security.</span></span>

![Passaggi per abilitare Microsoft Microsoft Cloud App Security nell'ambiente di valutazione di Microsoft Defender](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [<span data-ttu-id="0ef06-119">Passaggio 1. Connessione al portale Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0ef06-119">Step 1. Connect to the Cloud App Security portal</span></span>](#step-1-connect-to-the-cloud-app-security-portal)
- [<span data-ttu-id="0ef06-120">Passaggio 2. Integrazione con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0ef06-120">Step 2. Integrate with Microsoft Defender for Endpoint</span></span>](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [<span data-ttu-id="0ef06-121">Passaggio 3. Distribuire l'Cloud App Security di log nei firewall e in altri proxy</span><span class="sxs-lookup"><span data-stu-id="0ef06-121">Step 3. Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [<span data-ttu-id="0ef06-122">Passaggio 4. Visualizzare il dashboard di Cloud Discovery per sapere quali app vengono usate nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="0ef06-122">Step 4. View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a><span data-ttu-id="0ef06-123">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="0ef06-123">Step 1.</span></span> <span data-ttu-id="0ef06-124">Connessione al portale Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0ef06-124">Connect to the Cloud App Security portal</span></span>

<span data-ttu-id="0ef06-125">Per verificare le licenze e connettersi al portale Cloud App Security, vedere [Guida introduttiva:](/cloud-app-security/getting-started-with-cloud-app-security)Introduzione a Microsoft Cloud App Security .</span><span class="sxs-lookup"><span data-stu-id="0ef06-125">To verify licensing and to connect to the Cloud App Security portal, see [Quickstart: Get started with Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span></span> 

<span data-ttu-id="0ef06-126">Se non si è immediatamente in grado di connettersi al portale, potrebbe essere necessario aggiungere l'indirizzo IP all'elenco consenti del firewall.</span><span class="sxs-lookup"><span data-stu-id="0ef06-126">If you're not immediately able to connect to the portal, you might need to add the IP address to the allow list of your firewall.</span></span> <span data-ttu-id="0ef06-127">Vedere [Configurazione di base per Cloud App Security](/cloud-app-security/general-setup).</span><span class="sxs-lookup"><span data-stu-id="0ef06-127">See [Basic setup for Cloud App Security](/cloud-app-security/general-setup).</span></span>

<span data-ttu-id="0ef06-128">Se il problema persiste, vedere Requisiti [di rete.](/cloud-app-security/network-requirements)</span><span class="sxs-lookup"><span data-stu-id="0ef06-128">If you're still having trouble, review [Network requirements](/cloud-app-security/network-requirements).</span></span>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="0ef06-129">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="0ef06-129">Step 2.</span></span> <span data-ttu-id="0ef06-130">Integrazione con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0ef06-130">Integrate with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="0ef06-131">Microsoft Cloud App Security si integra in modo nativo con Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0ef06-131">Microsoft Cloud App Security integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="0ef06-132">L'integrazione semplifica l'implementazione di Cloud Discovery, estende le funzionalità di Cloud Discovery oltre la rete aziendale e consente l'analisi basata su dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0ef06-132">The integration simplifies roll out of Cloud Discovery, extends Cloud Discovery capabilities beyond your corporate network, and enables device-based investigation.</span></span> <span data-ttu-id="0ef06-133">Questa integrazione rivela le app cloud e i servizi a cui si accede da dispositivi Windows 10 IT.</span><span class="sxs-lookup"><span data-stu-id="0ef06-133">This integration reveals cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 

<span data-ttu-id="0ef06-134">Se hai già configurato Microsoft Defender per Endpoint, la configurazione dell'integrazione con Cloud App Security è un interruttore in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="0ef06-134">If you've already set up Microsoft Defender for Endpoint, configuring integration with Cloud App Security is a toggle in Microsoft 365 Defender.</span></span> <span data-ttu-id="0ef06-135">Dopo aver attivato l'integrazione, è possibile tornare al portale Cloud App Security e visualizzare dati rtf nel dashboard di individuazione cloud.</span><span class="sxs-lookup"><span data-stu-id="0ef06-135">After integration is turned on, you can return to the Cloud App Security portal and view rich data in the Cloud Discovery Dashboard.</span></span>

<span data-ttu-id="0ef06-136">Per eseguire queste attività, vedi [Integrazione di Microsoft Defender per Endpoint con Microsoft Cloud App Security](/cloud-app-security/mde-integration).</span><span class="sxs-lookup"><span data-stu-id="0ef06-136">To accomplish these tasks, see [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration).</span></span> 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a><span data-ttu-id="0ef06-137">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="0ef06-137">Step 3.</span></span> <span data-ttu-id="0ef06-138">Distribuire l'Cloud App Security di log nei firewall e in altri proxy</span><span class="sxs-lookup"><span data-stu-id="0ef06-138">Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>

<span data-ttu-id="0ef06-139">Per la copertura su tutti i dispositivi connessi alla rete, distribuire l'agente di raccolta log di Cloud App Security nei firewall e in altri proxy per raccogliere i dati dagli endpoint e inviarli a Cloud App Security per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="0ef06-139">For coverage on all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.</span></span> 

<span data-ttu-id="0ef06-140">Se si utilizza uno dei seguenti gateway Web protetti (SWG), Cloud App Security la distribuzione e l'integrazione senza problemi:</span><span class="sxs-lookup"><span data-stu-id="0ef06-140">If you're using one of the following Secure Web Gateways (SWG), Cloud App Security provides seamless deployment and integration:</span></span>
- <span data-ttu-id="0ef06-141">Zscaler</span><span class="sxs-lookup"><span data-stu-id="0ef06-141">Zscaler</span></span>
- <span data-ttu-id="0ef06-142">iboss</span><span class="sxs-lookup"><span data-stu-id="0ef06-142">iboss</span></span>
- <span data-ttu-id="0ef06-143">Corrata</span><span class="sxs-lookup"><span data-stu-id="0ef06-143">Corrata</span></span>
- <span data-ttu-id="0ef06-144">Menlo Security</span><span class="sxs-lookup"><span data-stu-id="0ef06-144">Menlo Security</span></span>

<span data-ttu-id="0ef06-145">Per ulteriori informazioni sull'integrazione con questi dispositivi di rete, vedere [Set up Cloud Discovery.](/cloud-app-security/set-up-cloud-discovery)</span><span class="sxs-lookup"><span data-stu-id="0ef06-145">For more information on integrating with these network devices, see [Set up Cloud Discovery](/cloud-app-security/set-up-cloud-discovery).</span></span> 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a><span data-ttu-id="0ef06-146">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="0ef06-146">Step 4.</span></span> <span data-ttu-id="0ef06-147">Visualizzare il dashboard di Cloud Discovery per sapere quali app vengono usate nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="0ef06-147">View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>

<span data-ttu-id="0ef06-148">Il dashboard di Cloud Discovery è progettato per fornire informazioni più approfondite sull'uso delle app cloud nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0ef06-148">The Cloud Discovery dashboard is designed to give you more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="0ef06-149">Fornisce una panoramica generale dei tipi di app in uso, degli avvisi aperti e dei livelli di rischio delle app nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0ef06-149">It provides an at-a-glance overview of what kinds of apps are being used, your open alerts, and the risk levels of apps in your organization.</span></span> 

<span data-ttu-id="0ef06-150">Per iniziare a usare il dashboard di Cloud Discovery, vedi [Uso delle app individuate.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="0ef06-150">To get started using the Cloud Discovery dashboard, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0ef06-151">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0ef06-151">Next steps</span></span>

<span data-ttu-id="0ef06-152">Passaggio 3 di 3: [test pilota Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="0ef06-152">Step 3 of 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span></span>

<span data-ttu-id="0ef06-153">Tornare alla panoramica di [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0ef06-153">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="0ef06-154">Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0ef06-154">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>