---
title: Onboard dei dispositivi al servizio Microsoft Defender for Endpoint
description: Onboard di dispositivi Windows 10, server, dispositivi non Windows e scopri come eseguire un test di rilevamento.
keywords: onboarding, Microsoft Defender for Endpoint onboarding, sccm, criteri di gruppo, mdm, script locale, test di rilevamento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 05cc5770df5bb05687bb8be69ad89a7abd6875ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933554"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="20d5d-104">Onboard dei dispositivi al servizio Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="20d5d-104">Onboard devices to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="20d5d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="20d5d-105">**Applies to:**</span></span>
- [<span data-ttu-id="20d5d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="20d5d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="20d5d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20d5d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="20d5d-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="20d5d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="20d5d-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="20d5d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="20d5d-110">Dovrai passare alla sezione onboarding del portale di Defender for Endpoint per eseguire l'onboarding di uno dei dispositivi supportati.</span><span class="sxs-lookup"><span data-stu-id="20d5d-110">You'll need to go the onboarding section of the Defender for Endpoint portal to onboard any of the supported devices.</span></span> <span data-ttu-id="20d5d-111">A seconda del dispositivo, sarai guidato con i passaggi appropriati e le opzioni degli strumenti di gestione e distribuzione disponibili per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="20d5d-111">Depending on the device, you'll be guided with appropriate steps and provided management and deployment tool options suitable for the device.</span></span> 

<span data-ttu-id="20d5d-112">In generale, per eseguire l'onboardboard dei dispositivi nel servizio:</span><span class="sxs-lookup"><span data-stu-id="20d5d-112">In general, to onboard devices to the service:</span></span>

- <span data-ttu-id="20d5d-113">Verificare che il dispositivo soddisfa i [requisiti minimi](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="20d5d-113">Verify that the device fulfills the [minimum requirements](minimum-requirements.md)</span></span>
- <span data-ttu-id="20d5d-114">A seconda del dispositivo, segui i passaggi di configurazione forniti nella sezione onboarding del portale defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="20d5d-114">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal</span></span>
- <span data-ttu-id="20d5d-115">Usare lo strumento di gestione e il metodo di distribuzione appropriati per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="20d5d-115">Use the appropriate management tool and deployment method for your devices</span></span>
- <span data-ttu-id="20d5d-116">Eseguire un test di rilevamento per verificare che i dispositivi siano correttamente onboarded e segnalare al servizio</span><span class="sxs-lookup"><span data-stu-id="20d5d-116">Run a detection test to verify that the devices are properly onboarded and reporting to the service</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a><span data-ttu-id="20d5d-117">Opzioni dello strumento di onboarding</span><span class="sxs-lookup"><span data-stu-id="20d5d-117">Onboarding tool options</span></span>
<span data-ttu-id="20d5d-118">Nella tabella seguente sono elencati gli strumenti disponibili in base all'endpoint da eseguire l'onboard.</span><span class="sxs-lookup"><span data-stu-id="20d5d-118">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="20d5d-119">Endpoint</span><span class="sxs-lookup"><span data-stu-id="20d5d-119">Endpoint</span></span>     | <span data-ttu-id="20d5d-120">Opzioni degli strumenti</span><span class="sxs-lookup"><span data-stu-id="20d5d-120">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="20d5d-121">**Windows**</span><span class="sxs-lookup"><span data-stu-id="20d5d-121">**Windows**</span></span>  |  [<span data-ttu-id="20d5d-122">Script locale (fino a 10 dispositivi)</span><span class="sxs-lookup"><span data-stu-id="20d5d-122">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="20d5d-123">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="20d5d-123">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="20d5d-124">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="20d5d-124">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="20d5d-125">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="20d5d-125">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="20d5d-126">Script VDI</span><span class="sxs-lookup"><span data-stu-id="20d5d-126">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="20d5d-127">**macOS**</span><span class="sxs-lookup"><span data-stu-id="20d5d-127">**macOS**</span></span>    | [<span data-ttu-id="20d5d-128">Script locali</span><span class="sxs-lookup"><span data-stu-id="20d5d-128">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="20d5d-129">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="20d5d-129">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="20d5d-130">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="20d5d-130">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="20d5d-131">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="20d5d-131">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="20d5d-132">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="20d5d-132">**Linux Server**</span></span> | [<span data-ttu-id="20d5d-133">Script locale</span><span class="sxs-lookup"><span data-stu-id="20d5d-133">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="20d5d-134">Pupazzo</span><span class="sxs-lookup"><span data-stu-id="20d5d-134">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="20d5d-135">Ansible</span><span class="sxs-lookup"><span data-stu-id="20d5d-135">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="20d5d-136">**iOS**</span><span class="sxs-lookup"><span data-stu-id="20d5d-136">**iOS**</span></span>      | [<span data-ttu-id="20d5d-137">Basato su app</span><span class="sxs-lookup"><span data-stu-id="20d5d-137">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="20d5d-138">**Android**</span><span class="sxs-lookup"><span data-stu-id="20d5d-138">**Android**</span></span>  | [<span data-ttu-id="20d5d-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="20d5d-139">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




## <a name="in-this-section"></a><span data-ttu-id="20d5d-140">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="20d5d-140">In this section</span></span>
<span data-ttu-id="20d5d-141">Argomento</span><span class="sxs-lookup"><span data-stu-id="20d5d-141">Topic</span></span> | <span data-ttu-id="20d5d-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20d5d-142">Description</span></span>
:---|:---
[<span data-ttu-id="20d5d-143">Aggiungere versioni precedenti di Windows</span><span class="sxs-lookup"><span data-stu-id="20d5d-143">Onboard previous versions of Windows</span></span>](onboard-downlevel.md)| <span data-ttu-id="20d5d-144">Onboard di dispositivi Windows 7 e Windows 8.1 a Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="20d5d-144">Onboard Windows 7 and Windows 8.1 devices to Defender for Endpoint.</span></span> 
[<span data-ttu-id="20d5d-145">Aggiungere di dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="20d5d-145">Onboard Windows 10 devices</span></span>](configure-endpoints.md) | <span data-ttu-id="20d5d-146">Dovrai eseguire l'onboardboard dei dispositivi per segnalare al servizio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="20d5d-146">You'll need to onboard devices for it to report to the Defender for Endpoint service.</span></span> <span data-ttu-id="20d5d-147">Scopri gli strumenti e i metodi che puoi usare per configurare i dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="20d5d-147">Learn about the tools and methods you can use to configure devices in your enterprise.</span></span>
[<span data-ttu-id="20d5d-148">Server di onboard</span><span class="sxs-lookup"><span data-stu-id="20d5d-148">Onboard servers</span></span>](configure-server-endpoints.md) |  <span data-ttu-id="20d5d-149">Onboarding di Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) versione 1803 e successive, Windows Server 2019 e versioni successive e Windows Server 2019 core edition per Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="20d5d-149">Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) version 1803 and later, Windows Server 2019 and later, and Windows Server 2019 core edition to Defender for Endpoint.</span></span>
[<span data-ttu-id="20d5d-150">Aggiungere dispositivi non Windows</span><span class="sxs-lookup"><span data-stu-id="20d5d-150">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md) | <span data-ttu-id="20d5d-151">Defender for Endpoint offre un'esperienza operativa di sicurezza centralizzata per Windows e per le piattaforme non Windows.</span><span class="sxs-lookup"><span data-stu-id="20d5d-151">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="20d5d-152">Potrai visualizzare gli avvisi di vari sistemi operativi supportati in Microsoft Defender Security Center e proteggere meglio la rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="20d5d-152">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> <span data-ttu-id="20d5d-153">Questa esperienza sfrutta i dati del sensore di prodotti di sicurezza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="20d5d-153">This experience leverages on a third-party security products' sensor data.</span></span> 
[<span data-ttu-id="20d5d-154">Eseguire un test di rilevamento in un dispositivo appena aggiunto</span><span class="sxs-lookup"><span data-stu-id="20d5d-154">Run a detection test on a newly onboarded device</span></span>](run-detection-test.md) | <span data-ttu-id="20d5d-155">Esegui uno script su un dispositivo appena onboarded per verificare che sia correttamente segnalato al servizio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="20d5d-155">Run a script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>
[<span data-ttu-id="20d5d-156">Configurare le impostazioni proxy e Internet</span><span class="sxs-lookup"><span data-stu-id="20d5d-156">Configure proxy and Internet settings</span></span>](configure-proxy-internet.md)| <span data-ttu-id="20d5d-157">Abilitare la comunicazione con il servizio cloud Defender for Endpoint configurando le impostazioni di connettività Internet e proxy.</span><span class="sxs-lookup"><span data-stu-id="20d5d-157">Enable communication with the Defender for Endpoint cloud service by configuring the proxy and Internet connectivity settings.</span></span>
[<span data-ttu-id="20d5d-158">Risolvere i problemi di onboarding</span><span class="sxs-lookup"><span data-stu-id="20d5d-158">Troubleshoot onboarding issues</span></span>](troubleshoot-onboarding.md) | <span data-ttu-id="20d5d-159">Informazioni sulla risoluzione dei problemi che potrebbero verificarsi durante l'onboarding.</span><span class="sxs-lookup"><span data-stu-id="20d5d-159">Learn about resolving issues that might arise during onboarding.</span></span>

><span data-ttu-id="20d5d-160">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="20d5d-160">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="20d5d-161">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="20d5d-161">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
