---
title: Da Symantec a Microsoft Defender per Endpoint - Fase 3, Onboarding
description: Questa è la fase 3, onboarding, della migrazione da Symantec a Microsoft Defender per Endpoint
keywords: migrazione, windows defender advanced threat protection, atp, edr
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: a59d277c117c41bfd796f9ff8adc3253360d8675
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068826"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Eseguire la migrazione da Symantec - Fase 3: onboard a Microsoft Defender per Endpoint

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: preparare](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Fase 1: preparare](symantec-to-microsoft-defender-atp-prepare.md) |[![Fase 2: configurazione](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: configurazione](symantec-to-microsoft-defender-atp-setup.md) |![Fase 3: onboard](images/phase-diagrams/onboard.png)<br/>Fase 3: onboard |
|--|--|--|
|| |*Sei qui!* |


**Benvenuti nella fase 3 della [migrazione da Symantec a Microsoft Defender per Endpoint.](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)** Questa fase di migrazione include i passaggi seguenti:

1. [Onboard dei dispositivi a Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Eseguire un test di rilevamento](#run-a-detection-test).
3. [Disinstallare Symantec](#uninstall-symantec).
4. [Assicurati che Microsoft Defender for Endpoint sia in modalità attiva.](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Onboard dei dispositivi a Microsoft Defender for Endpoint

1. Vai a Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e accedi.
2. Scegliere **Impostazioni**  >    >  **Onboarding gestione dispositivi**. 
3. **Nell'elenco Selezionare il sistema operativo per avviare il processo di onboarding** selezionare un sistema operativo. 
4. In **Metodo di distribuzione** selezionare un'opzione. Segui i collegamenti e le istruzioni per eseguire l'onboardboard dei dispositivi dell'organizzazione. Hai bisogno di assistenza? Vedere [Metodi di onboarding](#onboarding-methods) (in questo articolo).

### <a name="onboarding-methods"></a>Metodi di onboarding
 
I metodi di distribuzione variano a seconda del sistema operativo selezionato. Per informazioni sull'onboarding, fare riferimento alle risorse elencate nella tabella seguente.

|Sistema operativo  |Metodo  |
|---------|---------|
|Windows 10     |- [Criteri di gruppo](configure-endpoints-gp.md)<br/>- [Configuration Manager](configure-endpoints-sccm.md)<br/>- [Gestione dei dispositivi mobili (Intune)](configure-endpoints-mdm.md)<br/>- [Script locale](configure-endpoints-script.md) <br/><br/>**NOTA:** uno script locale è adatto per un modello di prova, ma non deve essere utilizzato per la distribuzione di produzione. Per una distribuzione di produzione, è consigliabile usare Criteri di gruppo, Microsoft Endpoint Configuration Manager o Intune.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/><br/>**NOTA:** Microsoft Monitoring Agent è ora l'agente di Azure Log Analytics. Per ulteriori informazioni, vedere [Panoramica dell'agente di log analytics.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 e versioni successive <br/>- Windows Server 2019 Core Edition <br/>- Windows Server versione 1803 e successive |- [Script locale](configure-endpoints-script.md) <br/>- [Criteri di gruppo](configure-endpoints-gp.md) <br/>- [Configuration Manager](/configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)<br/>- [Script di onboarding VDI per dispositivi non persistenti](configure-endpoints-vdi.md) <br/><br/>**NOTA:** uno script locale è adatto per un modello di prova, ma non deve essere utilizzato per la distribuzione di produzione. Per una distribuzione di produzione, è consigliabile usare Criteri di gruppo, Microsoft Endpoint Configuration Manager o Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender Security Center](configure-server-endpoints.md)<br/>- [Centro sicurezza di Azure](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o superiore<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Onboard di dispositivi non Windows](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Eseguire un test di rilevamento

Per verificare che i dispositivi onboarded siano connessi correttamente a Microsoft Defender for Endpoint, puoi eseguire un test di rilevamento.

|Sistema operativo  |Linee guida  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, versione 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Vedere [Eseguire un test di rilevamento](run-detection-test.md). <br/><br/>Visita il sito degli scenari demo di Microsoft Defender for Endpoint ( ) e [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) prova uno o più degli scenari. Ad esempio, provare lo **scenario demo di protezione fornito dal** cloud.         |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)     |Scarica e usa l'app FAI-da-to-app all'indirizzo [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <br/><br/>Per altre informazioni, vedi [Microsoft Defender per Endpoint per Mac.](microsoft-defender-endpoint-mac.md)        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o superiore<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Eseguire il comando seguente e cercare il risultato **1**: <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Aprire una finestra del terminale ed eseguire il comando seguente: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Eseguire il comando seguente per elencare eventuali minacce rilevate: <br/>`mdatp threat list`. <br/><br/>Per altre informazioni, vedi [Microsoft Defender per Endpoint per Linux.](microsoft-defender-endpoint-linux.md) |

## <a name="uninstall-symantec"></a>Disinstallare Symantec

Dopo aver installato i dispositivi dell'organizzazione in Microsoft Defender for Endpoint, il passaggio successivo consiste nel disinstallare Symantec.

1. [Disabilitare protezione manomissione](https://knowledge.broadcom.com/external/article?legacyId=tech192023) in Symantec.
2. Eliminare la password di disinstallazione per Symantec:<br/>
   1. Nei dispositivi Windows apri l'Editor del Registro di sistema come amministratore.
   2. Passare a `HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC`.
   3. Cercare una voce denominata **SmcInstData**. 
   4. Fare clic con il pulsante destro del mouse sull'elemento e quindi scegliere **Elimina.** 
3. Rimuovi Symantec dai dispositivi. Per assistenza, vedere la documentazione di Broadcom. Ecco alcune risorse Broadcom: 
   - [Disinstallare Symantec Endpoint Protection](https://knowledge.broadcom.com/external/article/156148/uninstall-symantec-endpoint-protection.html)
   - Dispositivi Windows: [disinstallare manualmente i client di Endpoint Protection 14 in Windows](https://knowledge.broadcom.com/external/article?articleId=170040)
   - computer macOS: [rimuovere il software Symantec per Mac usando RemoveSymantecMacFiles](https://knowledge.broadcom.com/external/article?articleId=151387)
   - Dispositivi Linux: [domande frequenti su Endpoint Protection per Linux](https://knowledge.broadcom.com/external/article?articleId=162054)

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Verificare che Microsoft Defender for Endpoint sia in modalità attiva

Dopo aver disinstallato Symantec, il passaggio successivo consiste nel verificare che Microsoft Defender Antivirus e Microsoft Defender for Endpoint siano abilitati e in modalità attiva.

A tale scopo, visitare il sito degli scenari dimostrativi di Microsoft Defender for Endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Prova uno o più degli scenari dimostrativi in tale pagina, inclusi almeno gli scenari seguenti:
- Protezione basata sul cloud
- Applicazioni potenzialmente indesiderate
- Protezione di rete

> [!IMPORTANT]
> Se si usa Windows Server 2016, potrebbe essere necessario avviare Microsoft Defender Antivirus manualmente. A tale scopo, è possibile utilizzare il cmdlet PowerShell `mpcmdrun.exe -wdenable` nel dispositivo.

## <a name="next-steps"></a>Passaggi successivi

**Congratulazioni**! La migrazione da [Symantec](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)a Microsoft Defender for Endpoint è stata completata. 
- [Visita il dashboard delle operazioni](security-operations-dashboard.md) di sicurezza in Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Gestire Microsoft Defender per Endpoint, dopo la migrazione.](manage-atp-post-migration.md)
