---
title: Onboard Windows server al servizio Microsoft Defender for Endpoint
description: Onboard Windows server in modo che possano inviare i dati del sensore al sensore Microsoft Defender for Endpoint.
keywords: onboarding di server, server, 2012r2, 2016, 2019, onboarding del server, gestione dei dispositivi, configurare Microsoft Defender per i server endpoint, eseguire l'onboarding di Microsoft Defender per i server endpoint, eseguire l'onboarding di Microsoft Defender per i server endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ff4c44199e4b6f8f1b3ca4806908813d7e710e4b
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415612"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="afffc-104">Onboard Windows server al servizio Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="afffc-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="afffc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="afffc-105">**Applies to:**</span></span>

- <span data-ttu-id="afffc-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="afffc-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="afffc-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="afffc-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="afffc-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="afffc-108">Windows Server 2016</span></span>
- <span data-ttu-id="afffc-109">Windows Server (SAC) versione 1803 e successive</span><span class="sxs-lookup"><span data-stu-id="afffc-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="afffc-110">Windows Server 2019 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="afffc-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="afffc-111">Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="afffc-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="afffc-112">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="afffc-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="afffc-113">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="afffc-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="afffc-114">Defender for Endpoint estende il supporto per includere anche il sistema operativo Windows Server.</span><span class="sxs-lookup"><span data-stu-id="afffc-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="afffc-115">Questo supporto offre funzionalità avanzate di rilevamento e analisi degli attacchi tramite la console Microsoft 365 Defender avanzata.</span><span class="sxs-lookup"><span data-stu-id="afffc-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft 365 Defender console.</span></span>

<span data-ttu-id="afffc-116">Per una guida pratica su ciò che deve essere in atto per le licenze e l'infrastruttura, vedere [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span><span class="sxs-lookup"><span data-stu-id="afffc-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="afffc-117">Per indicazioni su come scaricare e usare le Sicurezza di Windows di base per Windows server, vedere Sicurezza di Windows [Baselines](/windows/device-security/windows-security-baselines).</span><span class="sxs-lookup"><span data-stu-id="afffc-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="afffc-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 e Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="afffc-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="afffc-119">È possibile eseguire l'onboarding di Windows Server 2008 R2 SP1, Windows Server 2012 R2 e Windows Server 2016 a Defender per Endpoint utilizzando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="afffc-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="afffc-120">**Opzione 1:** [eseguire l'onboarding installando e configurando Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="afffc-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="afffc-121">**Opzione 2:** [onboard tramite il Centro sicurezza Di Azure](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="afffc-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="afffc-122">**Opzione 3:** [onboard fino Microsoft Endpoint Manager 2002 e versioni successive](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="afffc-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="afffc-123">Dopo aver completato la procedura di onboarding usando una delle opzioni fornite, è necessario configurare e aggiornare System Center Endpoint Protection [client](#configure-and-update-system-center-endpoint-protection-clients).</span><span class="sxs-lookup"><span data-stu-id="afffc-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="afffc-124">Defender for Endpoint standalone server license is required, per node, per eseguire l'onboard di un server Windows tramite Microsoft Monitoring Agent (opzione 1) o tramite Microsoft Endpoint Manager (opzione 3).</span><span class="sxs-lookup"><span data-stu-id="afffc-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="afffc-125">In alternativa, è necessaria una licenza di Azure Defender for Servers, per nodo, per eseguire l'onboardboard di un server Windows tramite il Centro sicurezza Di Azure (opzione 2), vedere Funzionalità supportate disponibili [in Azure Defender.](/azure/security-center/security-center-services)</span><span class="sxs-lookup"><span data-stu-id="afffc-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Defender](/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="afffc-126">Opzione 1: eseguire l'onboarding installando e configurando Microsoft Monitoring Agent (MMA)</span><span class="sxs-lookup"><span data-stu-id="afffc-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="afffc-127">Dovrai installare e configurare MMA per i server Windows per segnalare i dati del sensore a Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="afffc-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="afffc-128">Per ulteriori informazioni, vedere [Raccogliere i dati di log con l'agente Di log di Azure.](/azure/azure-monitor/platform/log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="afffc-128">For more information, see [Collect log data with Azure Log Analytics agent](/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="afffc-129">Se si usa già System Center Operations Manager (SCOM) o Azure Monitor (in precedenza noto come Operations Management Suite (OMS),collegare il Microsoft Monitoring Agent (MMA) per creare report nell'area di lavoro di Defender for Endpoint tramite il supporto multihoming.</span><span class="sxs-lookup"><span data-stu-id="afffc-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="afffc-130">In generale, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="afffc-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="afffc-131">Soddisfare i requisiti di onboarding descritti nella **sezione Prima di** iniziare.</span><span class="sxs-lookup"><span data-stu-id="afffc-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="afffc-132">Attivare il monitoraggio dei server Microsoft 365 Defender portale.</span><span class="sxs-lookup"><span data-stu-id="afffc-132">Turn on server monitoring from Microsoft 365 Defender portal.</span></span>
3. <span data-ttu-id="afffc-133">Installare e configurare MMA per il server per segnalare i dati del sensore a Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="afffc-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="afffc-134">Configurare e aggiornare i System Center Endpoint Protection client.</span><span class="sxs-lookup"><span data-stu-id="afffc-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="afffc-135">Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che sia stato correttamente eseguito l'onboarding nel servizio.</span><span class="sxs-lookup"><span data-stu-id="afffc-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="afffc-136">Per altre informazioni, vedi Eseguire un test di rilevamento su un defender appena [onboarded per endpoint](run-detection-test.md)endpoint.</span><span class="sxs-lookup"><span data-stu-id="afffc-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="afffc-137">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="afffc-137">Before you begin</span></span>

<span data-ttu-id="afffc-138">Eseguire la procedura seguente per soddisfare i requisiti di onboarding:</span><span class="sxs-lookup"><span data-stu-id="afffc-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="afffc-139">Per Windows Server 2008 R2 SP1 o Windows Server 2012 R2, assicurarsi di installare l'hotfix seguente:</span><span class="sxs-lookup"><span data-stu-id="afffc-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="afffc-140">Aggiornamento per l'esperienza del cliente e telemetria diagnostica</span><span class="sxs-lookup"><span data-stu-id="afffc-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="afffc-141">Per Windows Server 2008 R2 SP1, assicurarsi di soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="afffc-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="afffc-142">Installare [l'aggiornamento cumulativo mensile di febbraio](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="afffc-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="afffc-143">Installare [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o versione successiva) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="afffc-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="afffc-144">Se si sta gestendo Windows Server 2008 R2 SP1 con SCCM, l'agente client SCCM installa .Net Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="afffc-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="afffc-145">Non è quindi necessario installare .NET Framework 4.5 (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="afffc-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="afffc-146">Per Windows Server 2008 R2 SP1 e Windows Server 2012 R2: Configurare e [aggiornare System Center Endpoint Protection client](#configure-and-update-system-center-endpoint-protection-clients).</span><span class="sxs-lookup"><span data-stu-id="afffc-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="afffc-147">Questo passaggio è necessario solo se l'organizzazione utilizza System Center Endpoint Protection (SCEP) e si sta onboarding Windows Server 2008 R2 SP1 e Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="afffc-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="afffc-148">Installare e configurare Microsoft Monitoring Agent (MMA) per segnalare i dati del sensore a Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="afffc-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="afffc-149">Scaricare il file di installazione [dell'agente: Windows agente a 64 bit.](https://go.microsoft.com/fwlink/?LinkId=828603)</span><span class="sxs-lookup"><span data-stu-id="afffc-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="afffc-150">Utilizzando l'ID area di lavoro e la chiave Workspace ottenuta nella procedura precedente, scegliere uno dei metodi di installazione seguenti per installare l'agente nel server Windows:</span><span class="sxs-lookup"><span data-stu-id="afffc-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="afffc-151">[Installare manualmente l'agente utilizzando il programma di installazione](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="afffc-151">[Manually install the agent using setup](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="afffc-152">Nella pagina **Opzioni di installazione agente** scegliere **Connessione'agente in Azure Log Analytics (OMS).**</span><span class="sxs-lookup"><span data-stu-id="afffc-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="afffc-153">[Installare l'agente utilizzando la riga di comando](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="afffc-153">[Install the agent using the command line](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="afffc-154">[Configurare l'agente utilizzando uno script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="afffc-154">[Configure the agent using a script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="afffc-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span><span class="sxs-lookup"><span data-stu-id="afffc-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="afffc-156">Configurare Windows proxy server e le impostazioni di connettività Internet, se necessario</span><span class="sxs-lookup"><span data-stu-id="afffc-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="afffc-157">Se i server devono usare un proxy per comunicare con Defender per Endpoint, usa uno dei metodi seguenti per configurare la MMA per l'utilizzo del server proxy:</span><span class="sxs-lookup"><span data-stu-id="afffc-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="afffc-158">Configurare la MMA per l'utilizzo di un server proxy</span><span class="sxs-lookup"><span data-stu-id="afffc-158">Configure the MMA to use a proxy server</span></span>](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="afffc-159">Configurare Windows per l'utilizzo di un server proxy per tutte le connessioni</span><span class="sxs-lookup"><span data-stu-id="afffc-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="afffc-160">Se è in uso un proxy o un firewall, assicurarsi che i server possano accedere a tutti gli URL del servizio Microsoft Defender for Endpoint direttamente e senza l'intercettazione SSL.</span><span class="sxs-lookup"><span data-stu-id="afffc-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="afffc-161">Per altre informazioni, vedi [abilitare l'accesso a Defender per gli URL del servizio endpoint.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="afffc-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="afffc-162">L'uso dell'intercettazione SSL impedirà al sistema di comunicare con il servizio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="afffc-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="afffc-163">Una volta completato, dovrebbe essere possibile visualizzare i server Windows nel portale entro un'ora.</span><span class="sxs-lookup"><span data-stu-id="afffc-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="afffc-164">Opzione 2: onboard Windows server tramite il Centro sicurezza di Azure</span><span class="sxs-lookup"><span data-stu-id="afffc-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="afffc-165">Nel riquadro Microsoft 365 Defender di spostamento selezionare **Impostazioni**  >    >    >  **Onboarding** gestione dispositivi endpoint.</span><span class="sxs-lookup"><span data-stu-id="afffc-165">In the Microsoft 365 Defender navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="afffc-166">Selezionare **Windows Server 2008 R2 SP1, 2012 R2 e 2016** come sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="afffc-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="afffc-167">Fare **clic su Onboard Servers nel Centro sicurezza di Azure.**</span><span class="sxs-lookup"><span data-stu-id="afffc-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="afffc-168">Seguire le istruzioni di onboarding in [Microsoft Defender for Endpoint con Azure Defender](/azure/security-center/security-center-wdatp) e Se si usa Azure ARC, seguire le istruzioni di onboarding in Enabling the Microsoft Defender for Endpoint [integration](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span><span class="sxs-lookup"><span data-stu-id="afffc-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Defender](/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="afffc-169">Dopo aver completato i passaggi di onboarding, è necessario configurare e [aggiornare i System Center Endpoint Protection client.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="afffc-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="afffc-170">Perché l'onboarding tramite Azure Defender for Servers funzioni come previsto, il server deve avere un'area di lavoro e una chiave appropriate configurate nelle impostazioni di Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="afffc-170">For onboarding via Azure Defender for Servers to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="afffc-171">Una volta configurato, il Management Pack cloud appropriato viene distribuito nel computer e il processo del sensore (MsSenseS.exe) verrà distribuito e avviato.</span><span class="sxs-lookup"><span data-stu-id="afffc-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="afffc-172">Questa operazione è necessaria anche se il server è configurato per l'utilizzo di un server gateway OMS come proxy.</span><span class="sxs-lookup"><span data-stu-id="afffc-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="afffc-173">Opzione 3: onboard Windows server tramite Microsoft Endpoint Manager 2002 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="afffc-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="afffc-174">Puoi eseguire l'onboard Windows Server 2012 R2 e Windows Server 2016 usando Microsoft Endpoint Manager versione 2002 e successive.</span><span class="sxs-lookup"><span data-stu-id="afffc-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="afffc-175">Per altre informazioni, vedi [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch.](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="afffc-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="afffc-176">Dopo aver completato i passaggi di onboarding, è necessario configurare e [aggiornare i System Center Endpoint Protection client.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="afffc-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="afffc-177">Windows Server (SAC) versione 1803, Windows Server 2019 e Windows Server 2019 Core Edition</span><span class="sxs-lookup"><span data-stu-id="afffc-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="afffc-178">È possibile eseguire l'onboard di Windows Server (SAC) versione 1803, Windows Server 2019 o Windows Server 2019 Core edition utilizzando i metodi di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="afffc-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="afffc-179">Script locale</span><span class="sxs-lookup"><span data-stu-id="afffc-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="afffc-180">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="afffc-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="afffc-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="afffc-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="afffc-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="afffc-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="afffc-183">Script di onboarding VDI per dispositivi non persistenti</span><span class="sxs-lookup"><span data-stu-id="afffc-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="afffc-184">Il pacchetto di onboarding per Windows Server 2019 Microsoft Endpoint Manager attualmente spedisce uno script.</span><span class="sxs-lookup"><span data-stu-id="afffc-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="afffc-185">Per altre informazioni su come distribuire gli script in Configuration Manager, vedi [Pacchetti e programmi in Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="afffc-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="afffc-186">Uno script locale è adatto per un modello di prova, ma non deve essere utilizzato per la distribuzione di produzione.</span><span class="sxs-lookup"><span data-stu-id="afffc-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="afffc-187">Per una distribuzione di produzione, è consigliabile usare Criteri di gruppo o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="afffc-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="afffc-188">Il supporto per Windows Server fornisce informazioni più approfondite sulle attività del server, sulla copertura per il rilevamento di attacchi di kernel e memoria e consente azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="afffc-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="afffc-189">Configura le impostazioni di onboarding di Defender per Endpoint nel server Windows usando gli stessi strumenti e metodi per Windows 10 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="afffc-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="afffc-190">Per altre informazioni, vedi [Onboard Windows 10 dispositivi](configure-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="afffc-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="afffc-191">Se si esegue una soluzione antimalware di terze parti, è necessario applicare le impostazioni della modalità passiva di Microsoft Defender AV seguenti.</span><span class="sxs-lookup"><span data-stu-id="afffc-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="afffc-192">Verificare che sia stato configurato correttamente:</span><span class="sxs-lookup"><span data-stu-id="afffc-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="afffc-193">Impostare la voce del Registro di sistema seguente:</span><span class="sxs-lookup"><span data-stu-id="afffc-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="afffc-194">Percorso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="afffc-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="afffc-195">Nome: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="afffc-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="afffc-196">Tipo: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="afffc-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="afffc-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="afffc-197">Value: 1</span></span>

    1. <span data-ttu-id="afffc-198">Eseguire il comando di PowerShell seguente per verificare che la modalità passiva sia stata configurata:</span><span class="sxs-lookup"><span data-stu-id="afffc-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="afffc-199">Verificare che sia stato trovato un evento recente contenente l'evento in modalità passiva:</span><span class="sxs-lookup"><span data-stu-id="afffc-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Immagine del risultato della verifica in modalità passiva](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="afffc-201">Eseguire il comando seguente per verificare se Microsoft Defender AV è installato:</span><span class="sxs-lookup"><span data-stu-id="afffc-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="afffc-202">Se il risultato è "Il servizio specificato non esiste come servizio installato", dovrai installare Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="afffc-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="afffc-203">Per ulteriori informazioni, vedere [Antivirus Microsoft Defender in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span><span class="sxs-lookup"><span data-stu-id="afffc-203">For more information, see [Microsoft Defender Antivirus in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="afffc-204">Per informazioni su come utilizzare Criteri di gruppo per configurare e gestire Antivirus Microsoft Defender nei server Windows, vedere [Use Group Policy settings to configure and manage Antivirus Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="afffc-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-defender"></a><span data-ttu-id="afffc-205">Integrazione con Azure Defender</span><span class="sxs-lookup"><span data-stu-id="afffc-205">Integration with Azure Defender</span></span>

<span data-ttu-id="afffc-206">Defender for Endpoint può integrarsi con Azure Defender per fornire una soluzione completa Windows protezione dei server.</span><span class="sxs-lookup"><span data-stu-id="afffc-206">Defender for Endpoint can integrate with Azure Defender to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="afffc-207">Con questa integrazione, Azure Defender può usare la potenza di Defender for Endpoint per fornire un rilevamento delle minacce migliorato per Windows server.</span><span class="sxs-lookup"><span data-stu-id="afffc-207">With this integration, Azure Defender can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="afffc-208">In questa integrazione sono incluse le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="afffc-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="afffc-209">Onboarding automatizzato: il sensore Defender for Endpoint viene abilitato automaticamente nei Windows server di cui è stata eseguita l'onboarding in Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="afffc-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Defender.</span></span> <span data-ttu-id="afffc-210">Per altre informazioni sull'onboarding di Azure Defender, vedi [Usare la licenza integrata di Microsoft Defender for Endpoint.](/azure/security-center/security-center-wdatp)</span><span class="sxs-lookup"><span data-stu-id="afffc-210">For more information on Azure Defender onboarding, see [Use the integrated Microsoft Defender for Endpoint license](/azure/security-center/security-center-wdatp).</span></span>

    > [!NOTE]
    > <span data-ttu-id="afffc-211">L'integrazione tra Azure Defender for Servers e Microsoft Defender for Endpoint è stata estesa per supportare [Windows Server 2019 e Windows Virtual Desktop (WVD).](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)</span><span class="sxs-lookup"><span data-stu-id="afffc-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="afffc-212">Windows i server monitorati da Azure Defender saranno disponibili anche in Defender for Endpoint: Azure Defender si connette senza problemi al tenant Defender for Endpoint, fornendo una singola visualizzazione tra client e server.</span><span class="sxs-lookup"><span data-stu-id="afffc-212">Windows servers monitored by Azure Defender will also be available in Defender for Endpoint - Azure Defender seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="afffc-213">Inoltre, gli avvisi defender per endpoint saranno disponibili nella console di Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="afffc-213">In addition, Defender for Endpoint alerts will be available in the Azure Defender console.</span></span>
- <span data-ttu-id="afffc-214">Indagine server: i clienti di Azure Defender possono accedere Microsoft 365 Defender portale per eseguire un'indagine dettagliata per scoprire l'ambito di una potenziale violazione.</span><span class="sxs-lookup"><span data-stu-id="afffc-214">Server investigation -  Azure Defender customers can access Microsoft 365 Defender portal to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="afffc-215">Quando usi Azure Defender per monitorare i server, viene creato automaticamente un tenant defender per endpoint (negli Stati Uniti per gli utenti statunitensi, nell'UE per gli utenti europei e del Regno Unito).</span><span class="sxs-lookup"><span data-stu-id="afffc-215">When you use Azure Defender to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="afffc-216">I dati raccolti da Defender per Endpoint vengono archiviati nella posizione geografica del tenant come identificato durante il provisioning.</span><span class="sxs-lookup"><span data-stu-id="afffc-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="afffc-217">Se usi Defender per Endpoint prima di usare Azure Defender, i dati verranno archiviati nella posizione specificata al momento della creazione del tenant anche se ti integri con Azure Defender in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="afffc-217">If you use Defender for Endpoint before using Azure Defender, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Defender at a later time.</span></span>
> - <span data-ttu-id="afffc-218">Dopo la configurazione, non è possibile modificare la posizione in cui sono archiviati i dati.</span><span class="sxs-lookup"><span data-stu-id="afffc-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="afffc-219">Se è necessario spostare i dati in un'altra posizione, è necessario contattare il supporto tecnico Microsoft per reimpostare il tenant.</span><span class="sxs-lookup"><span data-stu-id="afffc-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="afffc-220">Il monitoraggio degli endpoint del server che utilizza questa integrazione è stato disabilitato per Office 365 GCC clienti.</span><span class="sxs-lookup"><span data-stu-id="afffc-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="afffc-221">Configurare e aggiornare i System Center Endpoint Protection client</span><span class="sxs-lookup"><span data-stu-id="afffc-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="afffc-222">Defender for Endpoint si integra con System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="afffc-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="afffc-223">L'integrazione fornisce visibilità ai rilevamenti di malware e per interrompere la propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto.</span><span class="sxs-lookup"><span data-stu-id="afffc-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="afffc-224">Per abilitare questa integrazione, sono necessari i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="afffc-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="afffc-225">Installare l'aggiornamento della piattaforma antimalware di gennaio [2017 per Endpoint Protection client](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span><span class="sxs-lookup"><span data-stu-id="afffc-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="afffc-226">[Configurare l'appartenenza del servizio di protezione cloud](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) del client SCEP all'impostazione Avanzate. </span><span class="sxs-lookup"><span data-stu-id="afffc-226">[Configure the SCEP client Cloud Protection Service membership](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="afffc-227">Offboard Windows server</span><span class="sxs-lookup"><span data-stu-id="afffc-227">Offboard Windows servers</span></span>

<span data-ttu-id="afffc-228">È possibile eseguire l'offboard dell'edizione Windows Server (SAC), Windows Server 2019 e Windows Server 2019 Core nello stesso metodo disponibile per i dispositivi client Windows 10.</span><span class="sxs-lookup"><span data-stu-id="afffc-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

- [<span data-ttu-id="afffc-229">Offboarding tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="afffc-229">Offboarding using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="afffc-230">Dispositivi offboard con Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="afffc-230">Offboard devices using Configuration Manager</span></span>](configure-endpoints-sccm.md#offboard-devices-using-configuration-manager)
- [<span data-ttu-id="afffc-231">Offboard e monitora i dispositivi con gli strumenti di gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="afffc-231">Offboard and monitor devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)
- [<span data-ttu-id="afffc-232">Dispositivi offboard con uno script locale</span><span class="sxs-lookup"><span data-stu-id="afffc-232">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)


<span data-ttu-id="afffc-233">Per altre Windows server, sono disponibili due opzioni per eseguire l'offboard Windows server dal servizio:</span><span class="sxs-lookup"><span data-stu-id="afffc-233">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="afffc-234">Disinstallare l'agente MMA</span><span class="sxs-lookup"><span data-stu-id="afffc-234">Uninstall the MMA agent</span></span>
- <span data-ttu-id="afffc-235">Rimuovere la configurazione dell'area di lavoro defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="afffc-235">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="afffc-236">L'offboarding fa sì che il server Windows interrompi l'invio dei dati del sensore al portale, ma i dati del server Windows, incluso il riferimento agli avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.</span><span class="sxs-lookup"><span data-stu-id="afffc-236">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="afffc-237">Disinstallare Windows server disinstallando l'agente MMA</span><span class="sxs-lookup"><span data-stu-id="afffc-237">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="afffc-238">Per eseguire l'offboard Windows server, puoi disinstallare l'agente MMA dal server Windows o scollegarlo dalla segnalazione nell'area di lavoro defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="afffc-238">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="afffc-239">Dopo l'offboarding dell'agente, il server Windows non invierà più i dati del sensore a Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="afffc-239">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="afffc-240">Per ulteriori informazioni, vedere [Per disabilitare un agente.](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)</span><span class="sxs-lookup"><span data-stu-id="afffc-240">For more information, see [To disable an agent](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="afffc-241">Rimuovere la configurazione dell'area di lavoro defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="afffc-241">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="afffc-242">Per eseguire l'offboard Windows server, è possibile utilizzare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="afffc-242">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="afffc-243">Rimuovere la configurazione dell'area di lavoro defender per endpoint dall'agente MMA</span><span class="sxs-lookup"><span data-stu-id="afffc-243">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="afffc-244">Eseguire un comando di PowerShell per rimuovere la configurazione</span><span class="sxs-lookup"><span data-stu-id="afffc-244">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="afffc-245">Rimuovere la configurazione dell'area di lavoro defender per endpoint dall'agente MMA</span><span class="sxs-lookup"><span data-stu-id="afffc-245">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="afffc-246">Nella finestra **Microsoft Monitoring Agent ,** selezionare la scheda Azure Log **Analytics (OMS).**</span><span class="sxs-lookup"><span data-stu-id="afffc-246">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="afffc-247">Seleziona l'area di lavoro Defender per Endpoint e fai clic su **Rimuovi.**</span><span class="sxs-lookup"><span data-stu-id="afffc-247">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Immagine di Microsoft Monitoring Agent proprietà](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="afffc-249">Eseguire un comando di PowerShell per rimuovere la configurazione</span><span class="sxs-lookup"><span data-stu-id="afffc-249">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="afffc-250">Ottenere l'ID area di lavoro:</span><span class="sxs-lookup"><span data-stu-id="afffc-250">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="afffc-251">Nel riquadro Microsoft 365 Defender di spostamento selezionare **Impostazioni**  >    >    >  **Onboarding** gestione dispositivi endpoint.</span><span class="sxs-lookup"><span data-stu-id="afffc-251">In the Microsoft 365 Defender navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>

   1. <span data-ttu-id="afffc-252">Selezionare **Windows Server 2008 R2 SP1, 2012 R2 e 2016** come sistema operativo e ottenere l'ID area di lavoro:</span><span class="sxs-lookup"><span data-stu-id="afffc-252">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Immagine dell'onboarding Windows server](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="afffc-254&quot;>Aprire un PowerShell con privilegi elevati ed eseguire il comando seguente.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;afffc-254&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;afffc-255&quot;>Utilizzare l'ID area di lavoro ottenuto e sostituendo `WorkspaceID` :</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;afffc-255&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="afffc-256">Server di onboarding senza soluzione di gestione</span><span class="sxs-lookup"><span data-stu-id="afffc-256">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="afffc-257">Utilizzo di Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="afffc-257">Using Group Policy</span></span>

<span data-ttu-id="afffc-258">**Passaggio 1: creare i file necessari da copiare nei server.**</span><span class="sxs-lookup"><span data-stu-id="afffc-258">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="afffc-259">Passare a c:\windows\sysvol\domain\scripts (il controllo delle modifiche potrebbe essere necessario in uno dei controller di dominio).</span><span class="sxs-lookup"><span data-stu-id="afffc-259">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="afffc-260">Crea una cartella denominata MMA.</span><span class="sxs-lookup"><span data-stu-id="afffc-260">Create a folder named MMA.</span></span>
1. <span data-ttu-id="afffc-261">Scarica quanto segue e inserisci nella cartella MMA:</span><span class="sxs-lookup"><span data-stu-id="afffc-261">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="afffc-262">**Aggiornamento per l'esperienza del cliente e telemetria diagnostica (Windows Server 2008 R2 e Windows Server 2012 R2)**</span><span class="sxs-lookup"><span data-stu-id="afffc-262">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="afffc-263">Per Windows 2008 R2 x64</span><span class="sxs-lookup"><span data-stu-id="afffc-263">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="afffc-264">Per Windows 2012 R2 x64</span><span class="sxs-lookup"><span data-stu-id="afffc-264">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="afffc-265">In questo articolo si presuppone che si utilizzino server basati su x64 (agente MMA .exe x64 [Nuova versione conforme a SHA-2](https://go.microsoft.com/fwlink/?LinkId=828603))</span><span class="sxs-lookup"><span data-stu-id="afffc-265">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="afffc-266">**Passaggio 2: Creare un nome di file DeployMMA.cmd (tramite blocco note)** Aggiungere le righe seguenti al file cmd.</span><span class="sxs-lookup"><span data-stu-id="afffc-266">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="afffc-267">Tieni presente che avrai bisogno dell'ID workspace e della chiave.</span><span class="sxs-lookup"><span data-stu-id="afffc-267">Note that you'll need your WORKSPACE ID and KEY.</span></span>

```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a><span data-ttu-id="afffc-268">Configurazione di Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="afffc-268">Group Policy Configuration</span></span>

<span data-ttu-id="afffc-269">Crea un nuovo criterio di gruppo specifico per i dispositivi di onboarding, ad esempio "Microsoft Defender for Endpoint Onboarding".</span><span class="sxs-lookup"><span data-stu-id="afffc-269">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="afffc-270">Creare una cartella di Criteri di gruppo denominata "c:\windows\MMA"</span><span class="sxs-lookup"><span data-stu-id="afffc-270">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="cartelle":::

    <span data-ttu-id="afffc-272">**Verrà aggiunta una nuova cartella in ogni server a cui viene applicato l'oggetto Criteri di gruppo, denominato MMA, e che verrà archiviata in c:\windows. Conterrà i file di installazione per l'MMA, i prerequisiti e lo script di installazione.**</span><span class="sxs-lookup"><span data-stu-id="afffc-272">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="afffc-273">Creare una preferenza File di Criteri di gruppo per ognuno dei file archiviati in Accesso rete.</span><span class="sxs-lookup"><span data-stu-id="afffc-273">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="immagine criteri di gruppo1":::

<span data-ttu-id="afffc-275">Copia i file da DOMAIN\NETLOGON\MMA\filename in C:\windows\MMA\filename, in modo che i file di installazione siano locali **nel server**:</span><span class="sxs-lookup"><span data-stu-id="afffc-275">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="distribuire mma cmd":::

<span data-ttu-id="afffc-277">Per i due KB (uno per Windows Server 2008R2/Windows 7 e l'altro per Windows Server 2012 R2) ripetere il processo ma creare la destinazione a livello di elemento nella scheda COMMON, in modo che il file venga copiato solo nella piattaforma o nella versione del sistema operativo appropriata nell'ambito:</span><span class="sxs-lookup"><span data-stu-id="afffc-277">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="editor di destinazione":::

- <span data-ttu-id="afffc-279">Per Windows Server 2008 R2 è necessario (e verrà copiato solo) Windows6.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="afffc-279">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="afffc-280">Per Windows Server 2012 R2 è necessario (e verrà copiato solo) Windows8.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="afffc-280">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="afffc-281">Al termine di questa operazione, è necessario creare un criterio script di avvio:</span><span class="sxs-lookup"><span data-stu-id="afffc-281">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="start up properties":::

<span data-ttu-id="afffc-283">Il nome del file da eseguire qui è c:\windows\MMA\DeployMMA.cmd.</span><span class="sxs-lookup"><span data-stu-id="afffc-283">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd.</span></span>
<span data-ttu-id="afffc-284">Una volta riavviato il server come parte del processo di avvio, installerà l'aggiornamento per l'esperienza del cliente e la telemetria diagnostica KB, quindi installerà l'agente MMA, impostando l'ID e la chiave dell'area di lavoro, e il server verrà onboarded.</span><span class="sxs-lookup"><span data-stu-id="afffc-284">Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMA Agent, while setting the Workspace ID and Key, and the server will be onboarded.</span></span>

<span data-ttu-id="afffc-285">È inoltre possibile utilizzare **un'attività immediata** per eseguire deployMMA.cmd se non si desidera riavviare tutti i server.</span><span class="sxs-lookup"><span data-stu-id="afffc-285">You could also use an **immediate task** to run the deployMMA.cmd if you don't want to reboot all the servers.</span></span>
<span data-ttu-id="afffc-286">Questa operazione può essere eseguita in due fasi.</span><span class="sxs-lookup"><span data-stu-id="afffc-286">This could be done in two phases.</span></span> <span data-ttu-id="afffc-287">Creare innanzitutto **i file e la** cartella nell'oggetto Criteri di gruppo: concedere al sistema il tempo necessario per verificare che l'oggetto Criteri di gruppo sia stato applicato e che tutti i server dispongono dei file di installazione.</span><span class="sxs-lookup"><span data-stu-id="afffc-287">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="afffc-288">Aggiungi quindi l'attività immediata.</span><span class="sxs-lookup"><span data-stu-id="afffc-288">Then, add the immediate task.</span></span> <span data-ttu-id="afffc-289">In questo modo si ottiene lo stesso risultato senza richiedere un riavvio.</span><span class="sxs-lookup"><span data-stu-id="afffc-289">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="afffc-290">Poiché lo script dispone di un metodo exit e non viene rieseguiti se la MMA è installata, è anche possibile utilizzare un'attività pianificata giornaliera per ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="afffc-290">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="afffc-291">Analogamente a un criterio di conformità di Configuration Manager, verrà verificata ogni giorno per verificare che la MMA sia presente.</span><span class="sxs-lookup"><span data-stu-id="afffc-291">Similar to a Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="attività di pianificazione":::

:::image type="content" source="images/newtaskprops.png" alt-text="nuove proprietà delle attività":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="distribuire le proprietà di download mma":::

:::image type="content" source="images/tasksch.png" alt-text="utilità di pianificazione":::

<span data-ttu-id="afffc-296">Come accennato nella documentazione relativa all'onboarding per Server in particolare per Server 2008 R2, vedere di seguito:</span><span class="sxs-lookup"><span data-stu-id="afffc-296">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="afffc-297">Per Windows Server 2008 R2 PS1, assicurarsi di soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="afffc-297">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="afffc-298">Installare [l'aggiornamento cumulativo mensile di febbraio 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="afffc-298">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="afffc-299">Installare [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o versione successiva) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="afffc-299">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="afffc-300">Si prega di verificare che i KB siano presenti prima dell'onboarding Windows Server 2008 R2 Questo processo consente di eseguire l'onboarding di tutti i server se non si dispone di Configuration Manager che gestisce i server.</span><span class="sxs-lookup"><span data-stu-id="afffc-300">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="afffc-301">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="afffc-301">Related topics</span></span>

- [<span data-ttu-id="afffc-302">Aggiungere di dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="afffc-302">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="afffc-303">Aggiungere dispositivi non Windows</span><span class="sxs-lookup"><span data-stu-id="afffc-303">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="afffc-304">Configurare le impostazioni di connettività Proxy e Internet</span><span class="sxs-lookup"><span data-stu-id="afffc-304">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="afffc-305">Eseguire un test di rilevamento in un dispositivo Defender for Endpoint appena onboarded</span><span class="sxs-lookup"><span data-stu-id="afffc-305">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="afffc-306">Risoluzione dei problemi di onboarding di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="afffc-306">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
