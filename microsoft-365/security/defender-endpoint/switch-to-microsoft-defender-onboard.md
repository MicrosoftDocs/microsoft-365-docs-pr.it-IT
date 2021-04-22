---
title: Passare a Microsoft Defender per Endpoint - Onboard
description: Questa è la fase 3, Onboard, per la migrazione da una soluzione non Microsoft a Microsoft Defender for Endpoint.
keywords: migrazione, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
ms.custom: migrationguides
ms.topic: article
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 459a113bb28c4ae0fa7c4d4a0b004ad2badc0da8
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935918"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Passare a Microsoft Defender per Endpoint - Fase 3: onboard

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Fase 1: Preparare 3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fase 1: preparazione](switch-to-microsoft-defender-prepare.md) | [![Fase 2: configurazione](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fase 2: configurazione](switch-to-microsoft-defender-setup.md) | ![Phase 3: onboarding](images/phase-diagrams/onboard.png)<br/>Fase 3: onboarding |
|--|--|--|
|| |*Sei qui!* |


**Benvenuti nella fase 3 del [passaggio a Microsoft Defender per Endpoint.](switch-to-microsoft-defender-migration.md#the-migration-process)** Questa fase di migrazione include i passaggi seguenti:

1. [Onboard dei dispositivi a Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Eseguire un test di rilevamento](#run-a-detection-test).
3. [Disinstallare la soluzione non Microsoft.](#uninstall-your-non-microsoft-solution)
4. [Assicurati che Microsoft Defender for Endpoint sia in modalità attiva.](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Aggiungere dispositivi a Microsoft Defender for Endpoint

1. Vai a Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e accedi.
2. Scegliere **Impostazioni**  >    >  **Onboarding gestione dispositivi**. 
3. **Nell'elenco Selezionare il sistema operativo per avviare il processo di onboarding** selezionare un sistema operativo. 
4. In **Metodo di distribuzione** selezionare un'opzione. Segui i collegamenti e le istruzioni per eseguire l'onboardboard dei dispositivi dell'organizzazione. Hai bisogno di assistenza? Vedere [Metodi di onboarding](#onboarding-methods) (in questo articolo).

### <a name="onboarding-methods"></a>Metodi di onboarding
 
I metodi di distribuzione variano a seconda del sistema operativo selezionato. Per informazioni sull'onboarding, fare riferimento alle risorse elencate nella tabella seguente.

|Sistema operativo  |Metodo  |
|---------|---------|
|Windows 10     |- [Criteri di gruppo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)<br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)<br/>- [Gestione dei dispositivi mobili (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)<br/>- [Script locale](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/><br/>**NOTA:** uno script locale è adatto per un modello di prova, ma non deve essere utilizzato per la distribuzione di produzione. Per una distribuzione di produzione, è consigliabile usare Criteri di gruppo, Microsoft Endpoint Configuration Manager o Intune.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/>**NOTA:** Microsoft Monitoring Agent è ora l'agente di Azure Log Analytics. Per ulteriori informazioni, vedere [Panoramica dell'agente di log analytics.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 e versioni successive <br/>- Windows Server 2019 Core Edition <br/>- Windows Server versione 1803 e successive |- [Script locale](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/>- [Criteri di gruppo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp) <br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) <br/>- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager) <br/>- [Script di onboarding VDI per dispositivi non persistenti](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi) <br/><br/>**NOTA:** uno script locale è adatto per un modello di prova, ma non deve essere utilizzato per la distribuzione di produzione. Per una distribuzione di produzione, è consigliabile usare Criteri di gruppo, Microsoft Endpoint Configuration Manager o Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)<br/>- [Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o superiore<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Aggiungere dispositivi non Windows](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a>Eseguire un test di rilevamento

Per verificare che i dispositivi onboarded siano connessi correttamente a Microsoft Defender for Endpoint, puoi eseguire un test di rilevamento.

|Sistema operativo  |Linee guida  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, versione 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Vedere [Eseguire un test di rilevamento](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test). <br/><br/>Visita il sito degli scenari demo di Microsoft Defender for Endpoint ( ) e [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) prova uno o più degli scenari. Ad esempio, provare lo **scenario demo di protezione fornito dal** cloud.         |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)     |Scarica e usa l'app FAI-da-to-app all'indirizzo [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <br/><br/>Per altre informazioni, vedi [Microsoft Defender per Endpoint su macOS.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o superiore<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Eseguire il comando seguente e cercare il risultato **1**: <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Aprire una finestra del terminale ed eseguire il comando seguente: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Eseguire il comando seguente per elencare eventuali minacce rilevate: <br/>`mdatp threat list`. <br/><br/>Per altre informazioni, vedi [Microsoft Defender per Endpoint su Linux.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-linux) |

## <a name="uninstall-your-non-microsoft-solution"></a>Disinstallare la soluzione non Microsoft

Dopo aver installato i dispositivi dell'organizzazione in Microsoft Defender for Endpoint, il passaggio successivo consiste nel disinstallare la soluzione di protezione degli endpoint non Microsoft.

Per ottenere assistenza con questo passaggio, contattare il team di supporto tecnico del provider di soluzioni.

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Verificare che Microsoft Defender for Endpoint sia in modalità attiva

Dopo aver disinstallato la soluzione di protezione degli endpoint non Microsoft, il passaggio successivo consiste nel verificare che Microsoft Defender Antivirus e Microsoft Defender for Endpoint siano abilitati e in modalità attiva.

A tale scopo, visitare il sito degli scenari dimostrativi di Microsoft Defender for Endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Prova uno o più degli scenari dimostrativi in tale pagina, inclusi almeno gli scenari seguenti:
- Protezione fornita dal cloud
- Applicazioni potenzialmente indesiderate
- Protezione di rete

> [!IMPORTANT]
> Se si usa Windows Server 2016, potrebbe essere necessario avviare Microsoft Defender Antivirus manualmente. A tale scopo, è possibile utilizzare il cmdlet PowerShell `mpcmdrun.exe -wdenable` nel dispositivo.

## <a name="next-steps"></a>Passaggi successivi

**Congratulazioni**! La migrazione a Microsoft Defender for Endpoint è stata [completata.](switch-to-microsoft-defender-migration.md#the-migration-process) 

- [Visita il dashboard delle operazioni](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) di sicurezza in Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Gestire Microsoft Defender per Endpoint, dopo la migrazione.](manage-atp-post-migration.md)
