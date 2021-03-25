---
title: Onboard al servizio Microsoft Defender ATP
description: Informazioni su come eseguire l'onboardboard degli endpoint nel servizio Microsoft Defender ATP
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56645553c43289995012d53d7caf879874e65c8a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186930"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="2ff22-103">Onboard al servizio Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ff22-103">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ff22-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2ff22-104">**Applies to:**</span></span>
- [<span data-ttu-id="2ff22-105">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="2ff22-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2ff22-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ff22-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="2ff22-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2ff22-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2ff22-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="2ff22-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2ff22-109">Informazioni sulle varie fasi della distribuzione di Microsoft Defender for Endpoint e su come configurare le funzionalità all'interno della soluzione.</span><span class="sxs-lookup"><span data-stu-id="2ff22-109">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="2ff22-110">La distribuzione di Defender per Endpoint è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="2ff22-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="2ff22-111">[![fase di distribuzione - preparazione](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="2ff22-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="2ff22-112">Fase 1: preparare</span><span class="sxs-lookup"><span data-stu-id="2ff22-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="2ff22-113">[![fase di distribuzione - installazione](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="2ff22-113">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="2ff22-114">Fase 2: installazione</span><span class="sxs-lookup"><span data-stu-id="2ff22-114">Phase 2: Setup</span></span>](production-deployment.md) | ![fase di distribuzione - onboard](images/phase-diagrams/onboard.png)<br><span data-ttu-id="2ff22-116">Fase 3: onboard</span><span class="sxs-lookup"><span data-stu-id="2ff22-116">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="2ff22-117">*Sei qui!*</span><span class="sxs-lookup"><span data-stu-id="2ff22-117">*You are here!*</span></span>|

<span data-ttu-id="2ff22-118">Si è attualmente in fase di onboarding.</span><span class="sxs-lookup"><span data-stu-id="2ff22-118">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="2ff22-119">Questi sono i passaggi da eseguire per distribuire Defender for Endpoint:</span><span class="sxs-lookup"><span data-stu-id="2ff22-119">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="2ff22-120">Passaggio 1: eseguire il onboard degli endpoint nel servizio</span><span class="sxs-lookup"><span data-stu-id="2ff22-120">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="2ff22-121">Passaggio 2: Configurare le funzionalità</span><span class="sxs-lookup"><span data-stu-id="2ff22-121">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="2ff22-122">Passaggio 1: onboardare gli endpoint usando uno degli strumenti di gestione supportati</span><span class="sxs-lookup"><span data-stu-id="2ff22-122">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="2ff22-123">[L'argomento Pianificare](deployment-strategy.md) la distribuzione descrive i passaggi generali da eseguire per distribuire Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2ff22-123">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="2ff22-124">Guarda questo video per una breve panoramica del processo di onboarding e scopri gli strumenti e i metodi disponibili.</span><span class="sxs-lookup"><span data-stu-id="2ff22-124">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="2ff22-125">Dopo aver identificato l'architettura, è necessario decidere quale metodo di distribuzione utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2ff22-125">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="2ff22-126">Lo strumento di distribuzione scelto influisce sulla modalità di onboard degli endpoint nel servizio.</span><span class="sxs-lookup"><span data-stu-id="2ff22-126">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="2ff22-127">Opzioni dello strumento di onboarding</span><span class="sxs-lookup"><span data-stu-id="2ff22-127">Onboarding tool options</span></span>

<span data-ttu-id="2ff22-128">Nella tabella seguente sono elencati gli strumenti disponibili in base all'endpoint da eseguire l'onboard.</span><span class="sxs-lookup"><span data-stu-id="2ff22-128">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="2ff22-129">Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ff22-129">Endpoint</span></span>     | <span data-ttu-id="2ff22-130">Opzioni degli strumenti</span><span class="sxs-lookup"><span data-stu-id="2ff22-130">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="2ff22-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="2ff22-131">**Windows**</span></span>  |  [<span data-ttu-id="2ff22-132">Script locale (fino a 10 dispositivi)</span><span class="sxs-lookup"><span data-stu-id="2ff22-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="2ff22-133">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="2ff22-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="2ff22-134">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="2ff22-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="2ff22-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2ff22-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="2ff22-136">Script VDI</span><span class="sxs-lookup"><span data-stu-id="2ff22-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="2ff22-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="2ff22-137">**macOS**</span></span>    | [<span data-ttu-id="2ff22-138">Script locali</span><span class="sxs-lookup"><span data-stu-id="2ff22-138">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="2ff22-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2ff22-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="2ff22-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="2ff22-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="2ff22-141">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="2ff22-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="2ff22-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="2ff22-142">**Linux Server**</span></span> | [<span data-ttu-id="2ff22-143">Script locale</span><span class="sxs-lookup"><span data-stu-id="2ff22-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="2ff22-144">Pupazzo</span><span class="sxs-lookup"><span data-stu-id="2ff22-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="2ff22-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="2ff22-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="2ff22-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="2ff22-146">**iOS**</span></span>      | [<span data-ttu-id="2ff22-147">Basato su app</span><span class="sxs-lookup"><span data-stu-id="2ff22-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="2ff22-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="2ff22-148">**Android**</span></span>  | [<span data-ttu-id="2ff22-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2ff22-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="2ff22-150">Passaggio 2: Configurare le funzionalità</span><span class="sxs-lookup"><span data-stu-id="2ff22-150">Step 2: Configure capabilities</span></span>
<span data-ttu-id="2ff22-151">Dopo l'onboarding degli endpoint, configurerai le varie funzionalità, ad esempio il rilevamento e la risposta degli endpoint, la protezione di nuova generazione e la riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="2ff22-151">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="2ff22-152">Distribuzioni di esempio</span><span class="sxs-lookup"><span data-stu-id="2ff22-152">Example deployments</span></span>
<span data-ttu-id="2ff22-153">In questa guida alla distribuzione verrà illustrato come usare due strumenti di distribuzione per eseguire l'onboarding degli endpoint e come configurare le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2ff22-153">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="2ff22-154">Gli strumenti nelle distribuzioni di esempio sono:</span><span class="sxs-lookup"><span data-stu-id="2ff22-154">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="2ff22-155">Onboarding con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2ff22-155">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="2ff22-156">Onboarding con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2ff22-156">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="2ff22-157">Usando gli strumenti di distribuzione menzionati in precedenza, sarai quindi guidato nella configurazione delle funzionalità di Defender for Endpoint seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ff22-157">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="2ff22-158">Rilevamento degli endpoint e configurazione della risposta</span><span class="sxs-lookup"><span data-stu-id="2ff22-158">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="2ff22-159">Configurazione di protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="2ff22-159">Next-generation protection configuration</span></span>
- <span data-ttu-id="2ff22-160">Configurazione della riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="2ff22-160">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ff22-161">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2ff22-161">Related topics</span></span>
- [<span data-ttu-id="2ff22-162">Onboarding con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2ff22-162">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="2ff22-163">Onboarding con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2ff22-163">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
