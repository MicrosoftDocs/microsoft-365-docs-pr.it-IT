---
title: Distribuire Microsoft Defender per Endpoint negli anelli
description: Informazioni su come distribuire Microsoft Defender per Endpoint negli anelli
keywords: distribuire, anelli, valutare, pilota, insider fast, insider slow, setup, onboard, phase, deployment, deploying, adoption, configuring
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
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5aeaa51e5ab8974c8ca26453534396dac14b5853
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297217"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="c4761-104">Distribuire Microsoft Defender per Endpoint negli anelli</span><span class="sxs-lookup"><span data-stu-id="c4761-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c4761-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c4761-105">**Applies to:**</span></span>
- [<span data-ttu-id="c4761-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c4761-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c4761-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4761-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c4761-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c4761-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c4761-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c4761-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="c4761-110">La distribuzione di Microsoft Defender per Endpoint può essere eseguita usando un approccio di distribuzione basato su anello.</span><span class="sxs-lookup"><span data-stu-id="c4761-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="c4761-111">I ring di distribuzione possono essere applicati negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4761-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="c4761-112">Nuove distribuzioni</span><span class="sxs-lookup"><span data-stu-id="c4761-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="c4761-113">Distribuzioni esistenti</span><span class="sxs-lookup"><span data-stu-id="c4761-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="c4761-114">Nuove distribuzioni</span><span class="sxs-lookup"><span data-stu-id="c4761-114">New deployments</span></span>

![Immagine dei ring di distribuzione](images/deployment-rings.png)


<span data-ttu-id="c4761-116">Un approccio basato su anello è un metodo per identificare un set di endpoint da eseguire l'onboarding e verificare che determinati criteri siano soddisfatti prima di procedere alla distribuzione del servizio in un set di dispositivi più ampio.</span><span class="sxs-lookup"><span data-stu-id="c4761-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="c4761-117">Puoi definire i criteri di uscita per ogni anello e assicurarti che siano soddisfatti prima di passare all'anello successivo.</span><span class="sxs-lookup"><span data-stu-id="c4761-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="c4761-118">L'adozione di una distribuzione basata su anello consente di ridurre i potenziali problemi che potrebbero verificarsi durante l'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="c4761-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="c4761-119">Pilotando prima un determinato numero di dispositivi, è possibile identificare potenziali problemi e ridurre i potenziali rischi che potrebbero verificarsi.</span><span class="sxs-lookup"><span data-stu-id="c4761-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="c4761-120">Nella tabella 1 viene fornito un esempio dei ring di distribuzione che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="c4761-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="c4761-121">**Tabella 1**</span><span class="sxs-lookup"><span data-stu-id="c4761-121">**Table 1**</span></span>

|<span data-ttu-id="c4761-122">**Anello di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="c4761-122">**Deployment ring**</span></span>|<span data-ttu-id="c4761-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c4761-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="c4761-124">Valuta</span><span class="sxs-lookup"><span data-stu-id="c4761-124">Evaluate</span></span> | <span data-ttu-id="c4761-125">Anello 1: identificare 50 sistemi per i test pilota</span><span class="sxs-lookup"><span data-stu-id="c4761-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="c4761-126">Distribuzione pilota</span><span class="sxs-lookup"><span data-stu-id="c4761-126">Pilot</span></span> | <span data-ttu-id="c4761-127">Anello 2: identificare i successivi 50-100 endpoint nell'ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="c4761-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="c4761-128">Distribuzione completa</span><span class="sxs-lookup"><span data-stu-id="c4761-128">Full deployment</span></span> | <span data-ttu-id="c4761-129">Anello 3: Implementare il servizio nel resto dell'ambiente con incrementi maggiori</span><span class="sxs-lookup"><span data-stu-id="c4761-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="c4761-130">Criteri di uscita</span><span class="sxs-lookup"><span data-stu-id="c4761-130">Exit criteria</span></span>
<span data-ttu-id="c4761-131">Un esempio di set di criteri di uscita per questi anelli può includere:</span><span class="sxs-lookup"><span data-stu-id="c4761-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="c4761-132">I dispositivi vengono visualizzati nell'elenco di inventario dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="c4761-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="c4761-133">Gli avvisi vengono visualizzati nel dashboard</span><span class="sxs-lookup"><span data-stu-id="c4761-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="c4761-134">Eseguire un test di rilevamento</span><span class="sxs-lookup"><span data-stu-id="c4761-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="c4761-135">Eseguire un attacco simulato su un dispositivo</span><span class="sxs-lookup"><span data-stu-id="c4761-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="c4761-136">Valuta</span><span class="sxs-lookup"><span data-stu-id="c4761-136">Evaluate</span></span>
<span data-ttu-id="c4761-137">Identificare un numero limitato di computer di test nell'ambiente da eseguire l'onboard nel servizio.</span><span class="sxs-lookup"><span data-stu-id="c4761-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="c4761-138">Idealmente, questi computer sarebbero meno di 50 endpoint.</span><span class="sxs-lookup"><span data-stu-id="c4761-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="c4761-139">Distribuzione pilota</span><span class="sxs-lookup"><span data-stu-id="c4761-139">Pilot</span></span>
<span data-ttu-id="c4761-140">Microsoft Defender for Endpoint supporta un'ampia gamma di endpoint che è possibile eseguire l'onboard nel servizio.</span><span class="sxs-lookup"><span data-stu-id="c4761-140">Microsoft Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="c4761-141">In questo anello, identificare diversi dispositivi da eseguire l'onboard e in base ai criteri di uscita definiti, decidere di passare al successivo anello di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c4761-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="c4761-142">La tabella seguente mostra gli endpoint supportati e lo strumento corrispondente che puoi usare per eseguire l'onboardboard dei dispositivi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="c4761-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="c4761-143">Endpoint</span><span class="sxs-lookup"><span data-stu-id="c4761-143">Endpoint</span></span>     | <span data-ttu-id="c4761-144">Strumento di distribuzione</span><span class="sxs-lookup"><span data-stu-id="c4761-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="c4761-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="c4761-145">**Windows**</span></span>  |  [<span data-ttu-id="c4761-146">Script locale (fino a 10 dispositivi)</span><span class="sxs-lookup"><span data-stu-id="c4761-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="c4761-147">NOTA: se vuoi distribuire più di 10 dispositivi in un ambiente di produzione, usa il metodo Criteri di gruppo o gli altri strumenti supportati elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="c4761-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="c4761-148">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="c4761-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="c4761-149">Microsoft Endpoint Manager/ Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c4761-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="c4761-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c4761-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="c4761-151">Script VDI</span><span class="sxs-lookup"><span data-stu-id="c4761-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="c4761-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="c4761-152">**macOS**</span></span>    | [<span data-ttu-id="c4761-153">Script locale</span><span class="sxs-lookup"><span data-stu-id="c4761-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="c4761-154">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="c4761-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="c4761-155">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="c4761-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="c4761-156">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="c4761-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="c4761-157">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="c4761-157">**Linux Server**</span></span> | [<span data-ttu-id="c4761-158">Script locale</span><span class="sxs-lookup"><span data-stu-id="c4761-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="c4761-159">Pupazzo</span><span class="sxs-lookup"><span data-stu-id="c4761-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="c4761-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="c4761-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="c4761-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="c4761-161">**iOS**</span></span>      | [<span data-ttu-id="c4761-162">Basato su app</span><span class="sxs-lookup"><span data-stu-id="c4761-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="c4761-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="c4761-163">**Android**</span></span>  | [<span data-ttu-id="c4761-164">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="c4761-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="c4761-165">Distribuzione completa</span><span class="sxs-lookup"><span data-stu-id="c4761-165">Full deployment</span></span>
<span data-ttu-id="c4761-166">In questa fase, è possibile utilizzare il [materiale di](deployment-strategy.md) pianificazione della distribuzione per pianificare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c4761-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="c4761-167">Usa il materiale seguente per selezionare l'architettura appropriata di Microsoft Defender for Endpoint che meglio si adatta alla tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4761-167">Use the following material to select the appropriate Microsoft Defender for Endpoint architecture that best suites your organization.</span></span>

|<span data-ttu-id="c4761-168">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="c4761-168">**Item**</span></span>|<span data-ttu-id="c4761-169">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c4761-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c4761-170">[![Immagine di scorrimento per la strategia di distribuzione di Microsoft Defender for Endpoint](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="c4761-170">[![Thumb image for Microsoft Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="c4761-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="c4761-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="c4761-172">Il materiale sull'architettura consente di pianificare la distribuzione per le architetture seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4761-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="c4761-173">Nativa del cloud</span><span class="sxs-lookup"><span data-stu-id="c4761-173">Cloud-native</span></span> </li><li> <span data-ttu-id="c4761-174">Co-gestione</span><span class="sxs-lookup"><span data-stu-id="c4761-174">Co-management</span></span> </li><li> <span data-ttu-id="c4761-175">Locale</span><span class="sxs-lookup"><span data-stu-id="c4761-175">On-premise</span></span></li><li><span data-ttu-id="c4761-176">Valutazione e onboarding locale</span><span class="sxs-lookup"><span data-stu-id="c4761-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="c4761-177">Distribuzioni esistenti</span><span class="sxs-lookup"><span data-stu-id="c4761-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="c4761-178">Windows endpoint</span><span class="sxs-lookup"><span data-stu-id="c4761-178">Windows endpoints</span></span>
<span data-ttu-id="c4761-179">Per Windows e/o Windows Server, è possibile selezionare più computer da testare in anticipo (prima della patch di martedì) utilizzando il programma Di convalida degli aggiornamenti della sicurezza **(SUVP).**</span><span class="sxs-lookup"><span data-stu-id="c4761-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="c4761-180">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="c4761-180">For more information, see:</span></span>
- [<span data-ttu-id="c4761-181">Che cos'è il programma di convalida degli aggiornamenti della sicurezza</span><span class="sxs-lookup"><span data-stu-id="c4761-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="c4761-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span><span class="sxs-lookup"><span data-stu-id="c4761-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="c4761-183">Endpoint non Windows</span><span class="sxs-lookup"><span data-stu-id="c4761-183">Non-Windows endpoints</span></span>
<span data-ttu-id="c4761-184">Con macOS e Linux, puoi prendere un paio di sistemi ed eseguirti nel canale Beta.</span><span class="sxs-lookup"><span data-stu-id="c4761-184">With macOS and Linux, you could take a couple of systems and run in the Beta channel.</span></span>

>[!NOTE]
><span data-ttu-id="c4761-185">Idealmente almeno un amministratore della sicurezza e uno sviluppatore in modo da poter trovare problemi di compatibilità, prestazioni e affidabilità prima che la build la relazioni nel canale Corrente.</span><span class="sxs-lookup"><span data-stu-id="c4761-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the Current channel.</span></span>

<span data-ttu-id="c4761-186">La scelta del canale determina il tipo e la frequenza degli aggiornamenti offerti al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4761-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="c4761-187">I dispositivi nella versione Beta sono i primi a ricevere aggiornamenti e nuove funzionalità, seguiti successivamente da Anteprima e infine da Current.</span><span class="sxs-lookup"><span data-stu-id="c4761-187">Devices in Beta are the first ones to receive updates and new features, followed later by Preview and lastly by Current.</span></span>

![Immagine degli anelli insider](images/insider-rings.png)

<span data-ttu-id="c4761-189">Per visualizzare in anteprima le nuove funzionalità e fornire feedback anticipato, è consigliabile configurare alcuni dispositivi dell'organizzazione per l'uso della versione Beta o dell'anteprima.</span><span class="sxs-lookup"><span data-stu-id="c4761-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either Beta or Preview.</span></span>

>[!WARNING]
><span data-ttu-id="c4761-190">Il cambio di canale dopo l'installazione iniziale richiede la reinstallazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="c4761-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="c4761-191">Per cambiare il canale del prodotto: disinstalla il pacchetto esistente, ri-configura il dispositivo per l'uso del nuovo canale e segui i passaggi in questo documento per installare il pacchetto dal nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="c4761-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>
