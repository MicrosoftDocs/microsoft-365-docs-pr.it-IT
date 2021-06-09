---
title: Onboard delle versioni precedenti di Windows in Microsoft Defender per Endpoint
description: Onboard le versioni precedenti dei dispositivi Windows in modo che possano inviare i dati del sensore al sensore Microsoft Defender for Endpoint
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
ms.openlocfilehash: d0cb4a3d01c1380f4fd06999c8f81a4054e2fd00
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844431"
---
# <a name="onboard-previous-versions-of-windows"></a>Aggiungere versioni precedenti di Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Piattaforme**
- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 Pro
- Windows 8.1 Enterprise


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)

Defender for Endpoint estende il supporto per includere sistemi operativi di livello inferiore, fornendo funzionalità avanzate di rilevamento e analisi degli attacchi nelle versioni Windows supportate.

Per eseguire l'onboard Windows endpoint client di livello inferiore in Defender for Endpoint, dovrai:
- Configurare e aggiornare i System Center Endpoint Protection client.
- Installa e configura Microsoft Monitoring Agent (MMA) per segnalare i dati del sensore a Defender per Endpoint come indicato di seguito.

> [!TIP]
> Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che sia stato correttamente eseguito l'onboarding nel servizio. Per altre informazioni, vedi Eseguire un test di rilevamento su un defender appena [onboarded per endpoint](run-detection-test.md)endpoint.

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Configurare e aggiornare i System Center Endpoint Protection client
> [!IMPORTANT]
> Questo passaggio è obbligatorio solo se l'organizzazione utilizza System Center Endpoint Protection (SCEP).

Defender for Endpoint si integra con System Center Endpoint Protection per fornire visibilità ai rilevamenti di malware e per interrompere la propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto. 

Per abilitare questa integrazione, sono necessari i passaggi seguenti: 
- Installare l'aggiornamento della piattaforma antimalware di gennaio [2017 per Endpoint Protection client](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- Configurare l'appartenenza del servizio di protezione cloud del client SCEP **all'impostazione** Avanzate
- Configurare la rete per consentire le connessioni al cloud Antivirus Microsoft Defender locale. Per ulteriori informazioni, vedere [Allow connections to the Antivirus Microsoft Defender cloud](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Installare e configurare Microsoft Monitoring Agent (MMA) per segnalare i dati del sensore a Microsoft Defender per Endpoint

### <a name="before-you-begin"></a>Prima di iniziare
Esaminare i dettagli seguenti per verificare i requisiti minimi di sistema:
- Installare [l'aggiornamento cumulativo mensile di febbraio 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > Applicabile solo per Windows 7 SP1 Enterprise e Windows 7 SP1 Pro. 

- Installare [l'aggiornamento per l'esperienza del cliente e la telemetria diagnostica](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- Installare [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o versione successiva) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Applicabile solo per Windows 7 SP1 Enterprise e Windows 7 SP1 Pro.
    > Non installare .NET Framework 4.0.x, poiché nega l'installazione precedente.

- Soddisfare i requisiti minimi di sistema dell'agente Azure Log Analytics. Per ulteriori informazioni, vedere [Raccogliere dati dai computer dell'ambiente con Log Analytics.](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)



1. Scaricare il file di installazione [dell'agente: Windows](https://go.microsoft.com/fwlink/?LinkId=828603) agente a 64 bit [o Windows agente a 32 bit](https://go.microsoft.com/fwlink/?LinkId=828604).

2. Ottenere l'ID area di lavoro:
   - Nel riquadro di spostamento Defender for Endpoint seleziona Impostazioni > **gestione dei dispositivi > onboarding**
   - Selezionare **Windows 7 SP1 e 8.1** come sistema operativo
   - Copiare l'ID dell'area di lavoro e la chiave dell'area di lavoro

3. Utilizzando l'ID area di lavoro e la chiave Workspace scegliere uno dei metodi di installazione seguenti per installare l'agente:
    - [Installare manualmente l'agente utilizzando il programma di installazione](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). <br>
      Nella pagina **Opzioni di installazione agente** selezionare **Connessione'agente in Azure Log Analytics (OMS)**
    - [Installare l'agente utilizzando la riga di comando](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configurare l'agente utilizzando uno script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

   > [!NOTE]
   > If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.

4. Se si usa un proxy per connettersi a Internet, vedere la sezione Configurare le impostazioni proxy.

Al termine, gli endpoint onboarded dovrebbero essere visualizzati nel portale entro un'ora.

### <a name="configure-proxy-and-internet-connectivity-settings"></a>Configurare le impostazioni di connettività Proxy e Internet
 
- Ogni Windows endpoint deve essere in grado di connettersi a Internet tramite HTTPS. Questa connessione può essere diretta, tramite un proxy o tramite il [gateway OMS.](/azure/log-analytics/log-analytics-oms-gateway)
- Se un proxy o un firewall blocca tutto il traffico per impostazione predefinita e consente solo domini specifici tramite o l'analisi HTTPS (ispezione SSL), assicurati di abilitare l'accesso a Defender per gli URL del servizio [endpoint.](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)

## <a name="offboard-client-endpoints"></a>Endpoint client offboard
Per eseguire l'offboard, puoi disinstallare l'agente MMA dall'endpoint o scollegarlo dalla segnalazione nell'area di lavoro defender per endpoint. Dopo l'offboarding dell'agente, l'endpoint non invierà più i dati del sensore a Defender per Endpoint. 

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)
