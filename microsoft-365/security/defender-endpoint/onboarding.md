---
title: Onboard al servizio Microsoft Defender for Endpoint
description: Informazioni su come eseguire l'onboardboard degli endpoint a Microsoft Defender per il servizio endpoint
keywords: microsoft defender per endpoint, onboard, distribuire
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
ms.openlocfilehash: f63b4f81f454fec60a26c7cb063d66bed4a2bead
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933542"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="dbfec-104">Onboard al servizio Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dbfec-104">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dbfec-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="dbfec-105">**Applies to:**</span></span>
- [<span data-ttu-id="dbfec-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="dbfec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dbfec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbfec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="dbfec-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="dbfec-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dbfec-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="dbfec-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="dbfec-110">Informazioni sulle varie fasi della distribuzione di Microsoft Defender for Endpoint e su come configurare le funzionalità all'interno della soluzione.</span><span class="sxs-lookup"><span data-stu-id="dbfec-110">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="dbfec-111">La distribuzione di Defender per Endpoint è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="dbfec-111">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="dbfec-112">[![fase di distribuzione - preparazione](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="dbfec-112">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="dbfec-113">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="dbfec-113">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="dbfec-114">[![fase di distribuzione - installazione](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="dbfec-114">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="dbfec-115">Fase 2: configurazione</span><span class="sxs-lookup"><span data-stu-id="dbfec-115">Phase 2: Setup</span></span>](production-deployment.md) | ![fase di distribuzione - onboard](images/phase-diagrams/onboard.png)<br><span data-ttu-id="dbfec-117">Fase 3: onboarding</span><span class="sxs-lookup"><span data-stu-id="dbfec-117">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="dbfec-118">*Sei qui!*</span><span class="sxs-lookup"><span data-stu-id="dbfec-118">*You are here!*</span></span>|

<span data-ttu-id="dbfec-119">Si è attualmente in fase di onboarding.</span><span class="sxs-lookup"><span data-stu-id="dbfec-119">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="dbfec-120">Questi sono i passaggi da eseguire per distribuire Defender for Endpoint:</span><span class="sxs-lookup"><span data-stu-id="dbfec-120">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="dbfec-121">Passaggio 1: eseguire il onboard degli endpoint nel servizio</span><span class="sxs-lookup"><span data-stu-id="dbfec-121">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="dbfec-122">Passaggio 2: Configurare le funzionalità</span><span class="sxs-lookup"><span data-stu-id="dbfec-122">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="dbfec-123">Passaggio 1: onboardare gli endpoint usando uno degli strumenti di gestione supportati</span><span class="sxs-lookup"><span data-stu-id="dbfec-123">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="dbfec-124">[L'argomento Pianificare](deployment-strategy.md) la distribuzione descrive i passaggi generali da eseguire per distribuire Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="dbfec-124">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="dbfec-125">Guarda questo video per una breve panoramica del processo di onboarding e scopri gli strumenti e i metodi disponibili.</span><span class="sxs-lookup"><span data-stu-id="dbfec-125">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="dbfec-126">Dopo aver identificato l'architettura, è necessario decidere quale metodo di distribuzione utilizzare.</span><span class="sxs-lookup"><span data-stu-id="dbfec-126">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="dbfec-127">Lo strumento di distribuzione scelto influisce sulla modalità di onboard degli endpoint nel servizio.</span><span class="sxs-lookup"><span data-stu-id="dbfec-127">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="dbfec-128">Opzioni dello strumento di onboarding</span><span class="sxs-lookup"><span data-stu-id="dbfec-128">Onboarding tool options</span></span>

<span data-ttu-id="dbfec-129">Nella tabella seguente sono elencati gli strumenti disponibili in base all'endpoint da eseguire l'onboard.</span><span class="sxs-lookup"><span data-stu-id="dbfec-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="dbfec-130">Endpoint</span><span class="sxs-lookup"><span data-stu-id="dbfec-130">Endpoint</span></span>     | <span data-ttu-id="dbfec-131">Opzioni degli strumenti</span><span class="sxs-lookup"><span data-stu-id="dbfec-131">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="dbfec-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="dbfec-132">**Windows**</span></span>  |  [<span data-ttu-id="dbfec-133">Script locale (fino a 10 dispositivi)</span><span class="sxs-lookup"><span data-stu-id="dbfec-133">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="dbfec-134">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="dbfec-134">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="dbfec-135">Microsoft Endpoint Manager/ Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="dbfec-135">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="dbfec-136">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dbfec-136">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="dbfec-137">Script VDI</span><span class="sxs-lookup"><span data-stu-id="dbfec-137">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="dbfec-138">Integrazione con Azure Defender</span><span class="sxs-lookup"><span data-stu-id="dbfec-138">Integration with Azure Defender</span></span>](configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="dbfec-139">**macOS**</span><span class="sxs-lookup"><span data-stu-id="dbfec-139">**macOS**</span></span>    | [<span data-ttu-id="dbfec-140">Script locali</span><span class="sxs-lookup"><span data-stu-id="dbfec-140">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="dbfec-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="dbfec-141">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="dbfec-142">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="dbfec-142">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="dbfec-143">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="dbfec-143">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="dbfec-144">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="dbfec-144">**Linux Server**</span></span> | [<span data-ttu-id="dbfec-145">Script locale</span><span class="sxs-lookup"><span data-stu-id="dbfec-145">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="dbfec-146">Pupazzo</span><span class="sxs-lookup"><span data-stu-id="dbfec-146">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="dbfec-147">Ansible</span><span class="sxs-lookup"><span data-stu-id="dbfec-147">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="dbfec-148">**iOS**</span><span class="sxs-lookup"><span data-stu-id="dbfec-148">**iOS**</span></span>      | [<span data-ttu-id="dbfec-149">Basato su app</span><span class="sxs-lookup"><span data-stu-id="dbfec-149">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="dbfec-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="dbfec-150">**Android**</span></span>  | [<span data-ttu-id="dbfec-151">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="dbfec-151">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="dbfec-152">Passaggio 2: Configurare le funzionalità</span><span class="sxs-lookup"><span data-stu-id="dbfec-152">Step 2: Configure capabilities</span></span>
<span data-ttu-id="dbfec-153">Dopo l'onboarding degli endpoint, configurerai le varie funzionalità, ad esempio il rilevamento e la risposta degli endpoint, la protezione di nuova generazione e la riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="dbfec-153">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="dbfec-154">Distribuzioni di esempio</span><span class="sxs-lookup"><span data-stu-id="dbfec-154">Example deployments</span></span>
<span data-ttu-id="dbfec-155">In questa guida alla distribuzione verrà illustrato come usare due strumenti di distribuzione per eseguire l'onboarding degli endpoint e come configurare le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="dbfec-155">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="dbfec-156">Gli strumenti nelle distribuzioni di esempio sono:</span><span class="sxs-lookup"><span data-stu-id="dbfec-156">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="dbfec-157">Utilizzo di Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dbfec-157">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="dbfec-158">Onboarding con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="dbfec-158">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="dbfec-159">Usando gli strumenti di distribuzione menzionati in precedenza, sarai quindi guidato nella configurazione delle funzionalità di Defender for Endpoint seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbfec-159">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="dbfec-160">Rilevamento degli endpoint e configurazione della risposta</span><span class="sxs-lookup"><span data-stu-id="dbfec-160">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="dbfec-161">Configurazione di protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="dbfec-161">Next-generation protection configuration</span></span>
- <span data-ttu-id="dbfec-162">Configurazione della riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="dbfec-162">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="dbfec-163">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="dbfec-163">Related topics</span></span>
- [<span data-ttu-id="dbfec-164">Utilizzo di Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dbfec-164">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="dbfec-165">Onboarding con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="dbfec-165">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="dbfec-166">Sicurezza documenti in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dbfec-166">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
