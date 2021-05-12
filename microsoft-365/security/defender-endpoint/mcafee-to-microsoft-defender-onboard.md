---
title: Da McAfee a Microsoft Defender for Endpoint - Onboard
description: Questa è la fase 3, Onboard, per la migrazione da McAfee a Microsoft Defender per Endpoint.
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
- m365solution-McAfeemigrate
- m365solution-scenario
ms.custom: migrationguides
ms.topic: article
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 00f96234fd92a70b4d2a2c1dba2862a6ee3404f4
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327379"
---
# <a name="migrate-from-mcafee---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Eseguire la migrazione da McAfee - Fase 3: onboard a Microsoft Defender per Endpoint

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


|[![Fase 1: preparazione](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[Fase 1: preparazione](mcafee-to-microsoft-defender-prepare.md) |[![Fase 2: configurazione](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Fase 2: configurazione](mcafee-to-microsoft-defender-setup.md) |![Phase 3: onboarding](images/phase-diagrams/onboard.png)<br/>Fase 3: onboarding |
|--|--|--|
|| |*Sei qui!* |

**Benvenuti nella fase 3 della [migrazione da McAfee Endpoint Security (McAfee) a Microsoft Defender for Endpoint.](mcafee-to-microsoft-defender-migration.md#the-migration-process)** Questa fase di migrazione include i passaggi seguenti:

1. [Onboard dei dispositivi a Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Eseguire un test di rilevamento](#run-a-detection-test).
3. [Disinstallare McAfee](#uninstall-mcafee).
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
|Windows 10     |- [Criteri di gruppo](configure-endpoints-gp.md)<br/>- [Configuration Manager](configure-endpoints-sccm.md)<br/>- [Gestione dei dispositivi mobili (Intune)](configure-endpoints-mdm.md)<br/>- [Script locale](configure-endpoints-script.md) <p>**NOTA:** uno script locale è adatto per un modello di prova, ma non deve essere utilizzato per la distribuzione di produzione. Per una distribuzione di produzione, è consigliabile usare Criteri di gruppo, Microsoft Endpoint Configuration Manager o Intune.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<p>**NOTA:** Microsoft Monitoring Agent è ora l'agente di Azure Log Analytics. Per ulteriori informazioni, vedere [Panoramica dell'agente di log analytics.](/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 e versioni successive <br/>- Windows Server 2019 Core Edition <br/>- Windows Server versione 1803 e successive |- [Script locale](configure-endpoints-script.md) <br/>- [Criteri di gruppo](configure-endpoints-gp.md) <br/>- [Configuration Manager](configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md) <br/>- [Script di onboarding VDI per dispositivi non persistenti](configure-endpoints-vdi.md) <p>**NOTA:** uno script locale è adatto per un modello di prova, ma non deve essere utilizzato per la distribuzione di produzione. Per una distribuzione di produzione, è consigliabile usare Criteri di gruppo, Microsoft Endpoint Configuration Manager o Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender Security Center](configure-server-endpoints.md)<br/>- [Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS<br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<p>iOS<p>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o superiore<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Aggiungere dispositivi non Windows](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Eseguire un test di rilevamento

Per verificare che i dispositivi onboarded siano connessi correttamente a Microsoft Defender for Endpoint, puoi eseguire un test di rilevamento.


|Sistema operativo  |Linee guida  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, versione 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Vedere [Eseguire un test di rilevamento](run-detection-test.md). <p>Visita il sito degli scenari demo di Microsoft Defender for Endpoint ( ) e [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) prova uno o più degli scenari. Ad esempio, provare lo **scenario demo di protezione fornito dal** cloud.         |
|macOS<br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)     |Scarica e usa l'app FAI-da-to-app all'indirizzo [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <p>Per altre informazioni, vedi [Microsoft Defender per Endpoint su Mac.](microsoft-defender-endpoint-mac.md)        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o superiore<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Eseguire il comando seguente e cercare il risultato **1**: <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Aprire una finestra del terminale ed eseguire il comando seguente: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Eseguire il comando seguente per elencare eventuali minacce rilevate: <br/>`mdatp threat list`. <p>Per altre informazioni, vedi [Microsoft Defender per Endpoint su Linux.](microsoft-defender-endpoint-linux.md) |

## <a name="uninstall-mcafee"></a>Disinstallare McAfee

Dopo aver installato i dispositivi dell'organizzazione in Microsoft Defender for Endpoint, il passaggio successivo consiste nel disinstallare McAfee.

Per ottenere assistenza con questo passaggio, passare al serviceportal McAfee ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) ).

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Verificare che Microsoft Defender for Endpoint sia in modalità attiva

Dopo aver disinstallato McAfee, il passaggio successivo consiste nel verificare che Microsoft Defender Antivirus e il rilevamento e la risposta degli endpoint siano abilitati e in modalità attiva.

A tale scopo, visitare il sito degli scenari dimostrativi di Microsoft Defender for Endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Prova uno o più degli scenari dimostrativi in tale pagina, inclusi almeno gli scenari seguenti:
- Protezione fornita dal cloud
- Applicazioni potenzialmente indesiderate
- Protezione di rete

> [!IMPORTANT]
> Se si usa Windows Server 2016, potrebbe essere necessario avviare Microsoft Defender Antivirus manualmente. A tale scopo, è possibile utilizzare il cmdlet PowerShell `mpcmdrun.exe -wdenable` nel dispositivo.

## <a name="next-steps"></a>Passaggi successivi

**Congratulazioni**! La migrazione da [McAfee](mcafee-to-microsoft-defender-migration.md#the-migration-process)a Microsoft Defender for Endpoint è stata completata. 

- [Visita il dashboard delle operazioni](security-operations-dashboard.md) di sicurezza in Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Gestire Microsoft Defender per Endpoint, dopo la migrazione.](manage-atp-post-migration.md)
