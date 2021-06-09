---
title: Onboard dei dispositivi senza accesso a Internet a Microsoft Defender for Endpoint
ms.reviewer: ''
description: Onboardare i dispositivi senza accesso a Internet in modo che possano inviare i dati del sensore al sensore Microsoft Defender for Endpoint
keywords: onboard, server, vm, locale, gateway oms, analisi dei log, analisi dei log di Azure, mma
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
ms.openlocfilehash: ed33f67695fddc78c0bac646f72ca0c48887bb04
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844419"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="62d5c-104">Onboard dei dispositivi senza accesso a Internet a Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="62d5c-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="62d5c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="62d5c-105">**Applies to:**</span></span>
- [<span data-ttu-id="62d5c-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="62d5c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="62d5c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62d5c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="62d5c-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="62d5c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="62d5c-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="62d5c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="62d5c-110">Per eseguire l'onboardboard dei dispositivi senza accesso a Internet, è necessario eseguire la procedura generale seguente:</span><span class="sxs-lookup"><span data-stu-id="62d5c-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="62d5c-111">I passaggi seguenti sono applicabili solo ai dispositivi che eseguono versioni precedenti di Windows, ad esempio: Windows Server 2016 precedenti o precedenti o Windows 8.1 e versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="62d5c-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="62d5c-112">Non è possibile utilizzare un server gateway OMS come proxy per i dispositivi Windows 10 o Windows Server 2019 disconnessi se configurati tramite il Registro di sistema o l'oggetto Criteri di gruppo "TelemetryProxyServer".</span><span class="sxs-lookup"><span data-stu-id="62d5c-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="62d5c-113">Per Windows 10 o Windows Server 2019- anche se è possibile usare TelemetryProxyServer, deve puntare a un dispositivo proxy standard o un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62d5c-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="62d5c-114">Inoltre, Windows 10 o Windows Server 2019 in ambienti disconnessi deve essere in grado di aggiornare gli elenchi di certificati attendibili offline tramite un file interno o un server Web.</span><span class="sxs-lookup"><span data-stu-id="62d5c-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="62d5c-115">Per ulteriori informazioni sull'aggiornamento dei CTL offline, vedere [Configure a file or web server to download the CTL files](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span><span class="sxs-lookup"><span data-stu-id="62d5c-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="62d5c-116">Per ulteriori informazioni sui metodi di onboarding, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="62d5c-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="62d5c-117">Aggiungere versioni precedenti di Windows</span><span class="sxs-lookup"><span data-stu-id="62d5c-117">Onboard previous versions of Windows</span></span>](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="62d5c-118">Onboard dei server al servizio Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="62d5c-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="62d5c-119">Configurare le impostazioni di connettività Proxy e Internet del dispositivo</span><span class="sxs-lookup"><span data-stu-id="62d5c-119">Configure device proxy and Internet connectivity settings</span></span>](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a><span data-ttu-id="62d5c-120">Dispositivi locali</span><span class="sxs-lookup"><span data-stu-id="62d5c-120">On-premise devices</span></span>

- <span data-ttu-id="62d5c-121">Configurare Azure Log Analytics (in precedenza noto come gateway OMS) per agire come proxy o hub:</span><span class="sxs-lookup"><span data-stu-id="62d5c-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="62d5c-122">Agente di analisi dei log di Azure</span><span class="sxs-lookup"><span data-stu-id="62d5c-122">Azure Log Analytics Agent</span></span>](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="62d5c-123">[Installare e configurare Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) puntano a Defender per l'ID & Endpoint Workspace</span><span class="sxs-lookup"><span data-stu-id="62d5c-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="62d5c-124">Dispositivi offline nella stessa rete di Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="62d5c-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="62d5c-125">Configurare MMA in modo che punti a:</span><span class="sxs-lookup"><span data-stu-id="62d5c-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="62d5c-126">IP di Azure Log Analytics come proxy</span><span class="sxs-lookup"><span data-stu-id="62d5c-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="62d5c-127">ID & dell'area di lavoro di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="62d5c-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="62d5c-128">Macchine virtuali di Azure</span><span class="sxs-lookup"><span data-stu-id="62d5c-128">Azure virtual machines</span></span>
- <span data-ttu-id="62d5c-129">Configurare e abilitare [l'area di lavoro di Azure Log Analytics](/azure/azure-monitor/platform/gateway)</span><span class="sxs-lookup"><span data-stu-id="62d5c-129">Configure and enable [Azure Log Analytics workspace](/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="62d5c-130">Configurare Azure Log Analytics Gateway (in precedenza noto come gateway OMS) per agire come proxy o hub:</span><span class="sxs-lookup"><span data-stu-id="62d5c-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="62d5c-131">Azure Log Analytics Gateway</span><span class="sxs-lookup"><span data-stu-id="62d5c-131">Azure Log Analytics Gateway</span></span>](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="62d5c-132">[Installare e configurare Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) puntano a Defender per l'ID & Endpoint Workspace</span><span class="sxs-lookup"><span data-stu-id="62d5c-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="62d5c-133">Macchine virtuali di Azure offline nella stessa rete del gateway OMS</span><span class="sxs-lookup"><span data-stu-id="62d5c-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="62d5c-134">Configurare l'IP di Azure Log Analytics come proxy</span><span class="sxs-lookup"><span data-stu-id="62d5c-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="62d5c-135">ID chiave dell'area di lavoro & di Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="62d5c-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="62d5c-136">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="62d5c-136">Azure Defender</span></span>
      - [<span data-ttu-id="62d5c-137">Area di lavoro \> analisi log criteri di sicurezza</span><span class="sxs-lookup"><span data-stu-id="62d5c-137">Security Policy \> Log Analytics Workspace</span></span>](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="62d5c-138">Rilevamento delle minacce \> Consenti a Defender per Endpoint di accedere ai miei dati</span><span class="sxs-lookup"><span data-stu-id="62d5c-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="62d5c-139">Per ulteriori informazioni, vedere [Utilizzo dei criteri di sicurezza.](/azure/security-center/tutorial-security-policy)</span><span class="sxs-lookup"><span data-stu-id="62d5c-139">For more information, see [Working with security policies](/azure/security-center/tutorial-security-policy).</span></span>
