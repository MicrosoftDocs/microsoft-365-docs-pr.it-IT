---
title: Onboard delle versioni precedenti di Windows in Microsoft Defender for Endpoint
description: Onboard ha supportato le versioni precedenti dei dispositivi Windows in modo che possano inviare i dati del sensore al sensore Microsoft Defender for Endpoint
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, livello inferiore
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 945645e0f20f316c094f746adb6ba193f6806f86
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861360"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="80c6f-104">Aggiungere versioni precedenti di Windows</span><span class="sxs-lookup"><span data-stu-id="80c6f-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="80c6f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="80c6f-105">**Applies to:**</span></span>
- [<span data-ttu-id="80c6f-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="80c6f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="80c6f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80c6f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="80c6f-108">**Piattaforme**</span><span class="sxs-lookup"><span data-stu-id="80c6f-108">**Platforms**</span></span>
- <span data-ttu-id="80c6f-109">Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="80c6f-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="80c6f-110">Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="80c6f-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="80c6f-111">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="80c6f-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="80c6f-112">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="80c6f-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="80c6f-113">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="80c6f-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="80c6f-114">[Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="80c6f-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="80c6f-115">Defender for Endpoint estende il supporto per includere sistemi operativi di livello inferiore, fornendo funzionalità avanzate di rilevamento e analisi degli attacchi nelle versioni di Windows supportate.</span><span class="sxs-lookup"><span data-stu-id="80c6f-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="80c6f-116">Per eseguire l'onboard degli endpoint client Windows di livello inferiore in Defender for Endpoint, dovrai:</span><span class="sxs-lookup"><span data-stu-id="80c6f-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="80c6f-117">Configurare e aggiornare i client di System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="80c6f-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="80c6f-118">Installare e configurare Microsoft Monitoring Agent (MMA) per segnalare i dati del sensore a Defender per Endpoint, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="80c6f-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="80c6f-119">Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che sia stato correttamente eseguito l'onboarding nel servizio.</span><span class="sxs-lookup"><span data-stu-id="80c6f-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="80c6f-120">Per altre informazioni, vedi Eseguire un test di rilevamento su un defender appena [onboarded per endpoint](run-detection-test.md)endpoint.</span><span class="sxs-lookup"><span data-stu-id="80c6f-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="80c6f-121">Configurare e aggiornare i client di System Center Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="80c6f-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="80c6f-122">Questo passaggio è obbligatorio solo se l'organizzazione usa System Center Endpoint Protection (SCEP).</span><span class="sxs-lookup"><span data-stu-id="80c6f-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="80c6f-123">Defender for Endpoint si integra con System Center Endpoint Protection per fornire visibilità ai rilevamenti di malware e per interrompere la propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto.</span><span class="sxs-lookup"><span data-stu-id="80c6f-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="80c6f-124">Per abilitare questa integrazione, sono necessari i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="80c6f-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="80c6f-125">Installare l'aggiornamento della piattaforma antimalware di gennaio [2017 per i client di Endpoint Protection](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="80c6f-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="80c6f-126">Configurare l'appartenenza del servizio di protezione cloud del client SCEP **all'impostazione** Avanzate</span><span class="sxs-lookup"><span data-stu-id="80c6f-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="80c6f-127">Configurare la rete per consentire le connessioni al cloud Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="80c6f-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="80c6f-128">Per ulteriori informazioni, vedere [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span><span class="sxs-lookup"><span data-stu-id="80c6f-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="80c6f-129">Installare e configurare Microsoft Monitoring Agent (MMA) per segnalare i dati del sensore a Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="80c6f-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="80c6f-130">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="80c6f-130">Before you begin</span></span>
<span data-ttu-id="80c6f-131">Esaminare i dettagli seguenti per verificare i requisiti minimi di sistema:</span><span class="sxs-lookup"><span data-stu-id="80c6f-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="80c6f-132">Installare [l'aggiornamento cumulativo mensile di febbraio 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="80c6f-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="80c6f-133">Applicabile solo per Windows 7 SP1 Enterprise e Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="80c6f-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="80c6f-134">Installare [l'aggiornamento per l'esperienza del cliente e la telemetria diagnostica](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span><span class="sxs-lookup"><span data-stu-id="80c6f-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="80c6f-135">Installare [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o versione successiva) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="80c6f-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="80c6f-136">Applicabile solo per Windows 7 SP1 Enterprise e Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="80c6f-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="80c6f-137">Non installare .NET Framework 4.0.x, poiché nega l'installazione precedente.</span><span class="sxs-lookup"><span data-stu-id="80c6f-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="80c6f-138">Soddisfare i requisiti minimi di sistema dell'agente Azure Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="80c6f-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="80c6f-139">Per altre informazioni, vedi [Raccogliere dati dai computer dell'ambiente con Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="80c6f-139">For more information, see [Collect data from computers in you environment with Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span></span>



1. <span data-ttu-id="80c6f-140">Scaricare il file di installazione dell'agente: [agente di Windows a 64 bit](https://go.microsoft.com/fwlink/?LinkId=828603) o agente windows a [32 bit.](https://go.microsoft.com/fwlink/?LinkId=828604)</span><span class="sxs-lookup"><span data-stu-id="80c6f-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="80c6f-141">Ottenere l'ID area di lavoro:</span><span class="sxs-lookup"><span data-stu-id="80c6f-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="80c6f-142">Nel riquadro di spostamento Defender for Endpoint seleziona **Impostazioni > Gestione > onboarding**</span><span class="sxs-lookup"><span data-stu-id="80c6f-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="80c6f-143">Selezionare **Windows 7 SP1 e 8.1** come sistema operativo</span><span class="sxs-lookup"><span data-stu-id="80c6f-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="80c6f-144">Copiare l'ID dell'area di lavoro e la chiave dell'area di lavoro</span><span class="sxs-lookup"><span data-stu-id="80c6f-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="80c6f-145">Utilizzando l'ID area di lavoro e la chiave Workspace scegliere uno dei metodi di installazione seguenti per installare l'agente:</span><span class="sxs-lookup"><span data-stu-id="80c6f-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="80c6f-146">[Installare manualmente l'agente utilizzando il programma di installazione](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="80c6f-146">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="80c6f-147">Nella pagina **Opzioni di installazione agente** selezionare Connetti **l'agente ad Azure Log Analytics (OMS)**</span><span class="sxs-lookup"><span data-stu-id="80c6f-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="80c6f-148">[Installare l'agente utilizzando la riga di comando](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="80c6f-148">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="80c6f-149">[Configurare l'agente utilizzando uno script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="80c6f-149">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="80c6f-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span><span class="sxs-lookup"><span data-stu-id="80c6f-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="80c6f-151">Se si usa un proxy per connettersi a Internet, vedere la sezione Configurare le impostazioni proxy.</span><span class="sxs-lookup"><span data-stu-id="80c6f-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="80c6f-152">Al termine, gli endpoint onboarded dovrebbero essere visualizzati nel portale entro un'ora.</span><span class="sxs-lookup"><span data-stu-id="80c6f-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="80c6f-153">Configurare le impostazioni di connettività Proxy e Internet</span><span class="sxs-lookup"><span data-stu-id="80c6f-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="80c6f-154">Ogni endpoint di Windows deve essere in grado di connettersi a Internet tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="80c6f-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="80c6f-155">Questa connessione può essere diretta, tramite un proxy o tramite il [gateway OMS.](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)</span><span class="sxs-lookup"><span data-stu-id="80c6f-155">This connection can be direct, using a proxy, or through the [OMS Gateway](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="80c6f-156">Se un proxy o un firewall blocca tutto il traffico per impostazione predefinita e consente solo domini specifici tramite o l'analisi HTTPS (ispezione SSL), assicurati di abilitare l'accesso a Defender per gli URL del servizio [endpoint.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="80c6f-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="80c6f-157">Endpoint client offboard</span><span class="sxs-lookup"><span data-stu-id="80c6f-157">Offboard client endpoints</span></span>
<span data-ttu-id="80c6f-158">Per eseguire l'offboard, puoi disinstallare l'agente MMA dall'endpoint o scollegarlo dalla segnalazione nell'area di lavoro defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="80c6f-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="80c6f-159">Dopo l'offboarding dell'agente, l'endpoint non invierà più i dati del sensore a Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="80c6f-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="80c6f-160">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="80c6f-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="80c6f-161">[Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)</span><span class="sxs-lookup"><span data-stu-id="80c6f-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>

