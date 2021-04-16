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
ms.openlocfilehash: fb5a9a4d35af2d400cdff1e417727e662738514e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861348"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Onboard dei dispositivi senza accesso a Internet a Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Per eseguire l'onboardboard dei dispositivi senza accesso a Internet, è necessario eseguire la procedura generale seguente:

> [!IMPORTANT] 
> I passaggi seguenti sono applicabili solo ai dispositivi che eseguono versioni precedenti di Windows, ad esempio: Windows Server 2016 e versioni precedenti o Windows 8.1 e versioni precedenti.

> [!NOTE]
> - Un server gateway OMS non può essere utilizzato come proxy per i dispositivi Windows 10 o Windows Server 2019 disconnessi quando configurato tramite il Registro di sistema o l'oggetto Criteri di gruppo "TelemetryProxyServer".
> - Per Windows 10 o Windows Server 2019- anche se puoi usare TelemetryProxyServer, deve puntare a un dispositivo proxy standard o a un dispositivo.
> - Inoltre, Windows 10 o Windows Server 2019 in ambienti disconnessi devono essere in grado di aggiornare gli elenchi di certificati attendibili offline tramite un file interno o un server Web.
> - Per ulteriori informazioni sull'aggiornamento dei CTL offline, vedere [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).

Per ulteriori informazioni sui metodi di onboarding, vedere gli articoli seguenti:
- [Aggiungere versioni precedenti di Windows](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Onboard dei server al servizio Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [Configurare le impostazioni del proxy del dispositivo e della connettività Internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a>Dispositivi locali

- Configurare Azure Log Analytics (in precedenza noto come gateway OMS) per agire come proxy o hub:
  - [Agente di analisi dei log di Azure](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Installare e configurare Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) punta a Defender per endpoint workspace & ID

- Dispositivi offline nella stessa rete di Azure Log Analytics
  -  Configurare MMA in modo che punti a:
     - IP di Azure Log Analytics come proxy
     - ID & dell'area di lavoro di Defender for Endpoint

## <a name="azure-virtual-machines"></a>Macchine virtuali di Azure
- Configurare e abilitare [l'area di lavoro di Azure Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)

    - Configurare Azure Log Analytics Gateway (in precedenza noto come gateway OMS) per agire come proxy o hub:
      - [Azure Log Analytics Gateway](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - [Installare e configurare Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) punta a Defender per endpoint workspace & ID
    - Macchine virtuali di Azure offline nella stessa rete del gateway OMS
      - Configurare l'IP di Azure Log Analytics come proxy
      - ID chiave dell'area di lavoro & di Azure Log Analytics

    - Centro sicurezza di Azure (ASC)
      - [Area di lavoro \> analisi log criteri di sicurezza](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [Rilevamento delle minacce \> Consenti a Defender per Endpoint di accedere ai miei dati](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        Per ulteriori informazioni, vedere [Utilizzo dei criteri di sicurezza.](https://docs.microsoft.com/azure/security-center/tutorial-security-policy)
