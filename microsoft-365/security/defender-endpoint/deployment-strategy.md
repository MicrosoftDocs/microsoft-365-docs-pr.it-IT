---
title: Pianificare la distribuzione di Microsoft Defender for Endpoint
description: Selezionare la migliore strategia di distribuzione di Microsoft Defender for Endpoint per il proprio ambiente
keywords: distribuire, pianificare, strategia di distribuzione, cloud nativo, gestione, in locale, valutazione, onboarding, locale, Criteri di gruppo, criteri di gruppo, gestore endpoint, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163576"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="5bb11-104">Pianificare la distribuzione di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5bb11-104">Plan your Microsoft Defender for Endpoint deployment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5bb11-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5bb11-105">**Applies to:**</span></span>
- [<span data-ttu-id="5bb11-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5bb11-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5bb11-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5bb11-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5bb11-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5bb11-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5bb11-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5bb11-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


<span data-ttu-id="5bb11-110">Pianificare la distribuzione di Microsoft Defender for Endpoint in modo da ottimizzare le funzionalità di sicurezza all'interno della famiglia di prodotti e proteggere meglio l'azienda dalle minacce informatiche.</span><span class="sxs-lookup"><span data-stu-id="5bb11-110">Plan your Microsoft Defender for Endpoint deployment so that you can maximize the security capabilities within the suite and better protect your enterprise from cyber threats.</span></span>


<span data-ttu-id="5bb11-111">Questa soluzione fornisce indicazioni su come identificare l'architettura dell'ambiente, selezionare il tipo di strumento di distribuzione più adatto alle proprie esigenze e indicazioni su come configurare le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5bb11-111">This solution provides guidance on how to identify your environment architecture, select the type of deployment tool that best fits your needs, and guidance on how to configure capabilities.</span></span>


![Immagine del flusso di distribuzione](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a><span data-ttu-id="5bb11-113">Passaggio 1: identificare l'architettura</span><span class="sxs-lookup"><span data-stu-id="5bb11-113">Step 1: Identify architecture</span></span>
<span data-ttu-id="5bb11-114">Tutti gli ambienti aziendali sono univoci, quindi sono disponibili diverse opzioni per offrire la flessibilità necessaria per scegliere come distribuire il servizio.</span><span class="sxs-lookup"><span data-stu-id="5bb11-114">We understand that every enterprise environment is unique, so we've provided several options to give you the flexibility in choosing how to deploy the service.</span></span>

<span data-ttu-id="5bb11-115">Alcuni strumenti sono più adatti per determinate architetture, a seconda dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="5bb11-115">Depending on your environment, some tools are better suited for certain architectures.</span></span> 

<span data-ttu-id="5bb11-116">Usa il materiale seguente per selezionare l'architettura di Defender for Endpoint appropriata per la famiglia di prodotti più adatta alla tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5bb11-116">Use the following material to select the appropriate Defender for Endpoint architecture that best suites your organization.</span></span>

| <span data-ttu-id="5bb11-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5bb11-117">Item</span></span> | <span data-ttu-id="5bb11-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5bb11-118">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="5bb11-119">[![Immagine di scorrimento per la strategia di distribuzione di Defender for Endpoint](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="5bb11-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="5bb11-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="5bb11-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="5bb11-121">Il materiale sull'architettura consente di pianificare la distribuzione per le architetture seguenti:</span><span class="sxs-lookup"><span data-stu-id="5bb11-121">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="5bb11-122">Nativa del cloud</span><span class="sxs-lookup"><span data-stu-id="5bb11-122">Cloud-native</span></span> </li><li> <span data-ttu-id="5bb11-123">Co-gestione</span><span class="sxs-lookup"><span data-stu-id="5bb11-123">Co-management</span></span> </li><li> <span data-ttu-id="5bb11-124">Locale</span><span class="sxs-lookup"><span data-stu-id="5bb11-124">On-premise</span></span></li><li><span data-ttu-id="5bb11-125">Valutazione e onboarding locale</span><span class="sxs-lookup"><span data-stu-id="5bb11-125">Evaluation and local onboarding</span></span></li>



## <a name="step-2-select-deployment-method"></a><span data-ttu-id="5bb11-126">Passaggio 2: Selezionare il metodo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="5bb11-126">Step 2: Select deployment method</span></span>
<span data-ttu-id="5bb11-127">Defender for Endpoint supporta un'ampia gamma di endpoint che è possibile eseguire l'onboard nel servizio.</span><span class="sxs-lookup"><span data-stu-id="5bb11-127">Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> 

<span data-ttu-id="5bb11-128">Nella tabella seguente sono elencati gli endpoint supportati e lo strumento di distribuzione corrispondente che è possibile utilizzare per pianificare la distribuzione in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="5bb11-128">The following table lists the supported endpoints and the corresponding deployment tool that you can use so that you can plan the deployment appropriately.</span></span>

| <span data-ttu-id="5bb11-129">Endpoint</span><span class="sxs-lookup"><span data-stu-id="5bb11-129">Endpoint</span></span>     | <span data-ttu-id="5bb11-130">Strumento di distribuzione</span><span class="sxs-lookup"><span data-stu-id="5bb11-130">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="5bb11-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="5bb11-131">**Windows**</span></span>  |  [<span data-ttu-id="5bb11-132">Script locale (fino a 10 dispositivi)</span><span class="sxs-lookup"><span data-stu-id="5bb11-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="5bb11-133">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="5bb11-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="5bb11-134">Microsoft Endpoint Manager/ Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="5bb11-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="5bb11-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5bb11-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="5bb11-136">Script VDI</span><span class="sxs-lookup"><span data-stu-id="5bb11-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="5bb11-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="5bb11-137">**macOS**</span></span>    | [<span data-ttu-id="5bb11-138">Script locale</span><span class="sxs-lookup"><span data-stu-id="5bb11-138">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="5bb11-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5bb11-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="5bb11-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="5bb11-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="5bb11-141">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="5bb11-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="5bb11-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="5bb11-142">**Linux Server**</span></span> | [<span data-ttu-id="5bb11-143">Script locale</span><span class="sxs-lookup"><span data-stu-id="5bb11-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="5bb11-144">Pupazzo</span><span class="sxs-lookup"><span data-stu-id="5bb11-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="5bb11-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="5bb11-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="5bb11-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="5bb11-146">**iOS**</span></span>      | [<span data-ttu-id="5bb11-147">Basato su app</span><span class="sxs-lookup"><span data-stu-id="5bb11-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="5bb11-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="5bb11-148">**Android**</span></span>  | [<span data-ttu-id="5bb11-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="5bb11-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a><span data-ttu-id="5bb11-150">Passaggio 3: Configurare le funzionalità</span><span class="sxs-lookup"><span data-stu-id="5bb11-150">Step 3: Configure capabilities</span></span>
<span data-ttu-id="5bb11-151">Dopo gli endpoint di onboarding, configura le funzionalità di sicurezza in Defender per Endpoint in modo da poter ottimizzare la protezione di sicurezza affidabile disponibile nella famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="5bb11-151">After onboarding endpoints, configure the security capabilities in Defender for Endpoint so that you can maximize the robust security protection available in the suite.</span></span> <span data-ttu-id="5bb11-152">Le funzionalità includono:</span><span class="sxs-lookup"><span data-stu-id="5bb11-152">Capabilities include:</span></span>

- <span data-ttu-id="5bb11-153">Rilevamento endpoint e risposta</span><span class="sxs-lookup"><span data-stu-id="5bb11-153">Endpoint detection and response</span></span>
- <span data-ttu-id="5bb11-154">Protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="5bb11-154">Next-generation protection</span></span>
- <span data-ttu-id="5bb11-155">La riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="5bb11-155">Attack surface reduction</span></span>


  
## <a name="related-topics"></a><span data-ttu-id="5bb11-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5bb11-156">Related topics</span></span>
- [<span data-ttu-id="5bb11-157">Fasi della distribuzione</span><span class="sxs-lookup"><span data-stu-id="5bb11-157">Deployment phases</span></span>](deployment-phases.md)
