---
title: Da Symantec a Microsoft Defender per Endpoint - Fase 3, Onboarding
description: Questa è la fase 3, onboarding, della migrazione da Symantec a Microsoft Defender per Endpoint
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: f2b2d5ca9f841e36df37f025a9b5856fc7e2dc6a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538364"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Eseguire la migrazione da Symantec - Fase 3: onboard a Microsoft Defender per Endpoint

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: preparazione](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Fase 1: preparazione](symantec-to-microsoft-defender-atp-prepare.md) |[![Fase 2: configurazione](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: configurazione](symantec-to-microsoft-defender-atp-setup.md) |![Phase 3: onboarding](images/phase-diagrams/onboard.png)<br/>Fase 3: onboarding |
|--|--|--|
|| |*Sei qui!* |


**Benvenuti nella fase 3 della [migrazione da Symantec a Microsoft Defender per Endpoint.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** Questa fase di migrazione include i passaggi seguenti:

1. [Onboard dei dispositivi a Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).

2. [Eseguire un test di rilevamento](#run-a-detection-test).

3. [Verificare che Antivirus Microsoft Defender sia in modalità passiva negli endpoint](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints).

4. [Ottenere gli aggiornamenti per Antivirus Microsoft Defender](#get-updates-for-microsoft-defender-antivirus).

5. [Disinstallare Symantec](#uninstall-symantec).

6. [Assicurati che Microsoft Defender for Endpoint funzioni correttamente.](#make-sure-microsoft-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Aggiungere dispositivi a Microsoft Defender for Endpoint

1. Vai al Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e accedi.

2. Scegliere **Impostazioni**  >    >  **Onboarding di Gestione dispositivi**. 

3. **Nell'elenco Selezionare il sistema operativo per avviare il processo di onboarding** selezionare un sistema operativo. 

4. In **Metodo di distribuzione** selezionare un'opzione. Segui i collegamenti e le istruzioni per eseguire l'onboardboard dei dispositivi dell'organizzazione. Hai bisogno di assistenza? Vedere [Metodi di onboarding](#onboarding-methods) (in questo articolo).

### <a name="onboarding-methods"></a>Metodi di onboarding
 
I metodi di distribuzione variano a seconda del sistema operativo selezionato. Per informazioni sull'onboarding, fare riferimento alle risorse elencate nella tabella seguente.

|Sistema operativo  |Metodo  |
|---------|---------|
|Windows 10     | [Criteri di gruppo](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[Gestione dei dispositivi mobili (Intune)](configure-endpoints-mdm.md)<p>[Script locale](configure-endpoints-script.md) <br/>**NOTA:** uno script locale è adatto per un modello di prova, ma non deve essere utilizzato per la distribuzione di produzione. Per una distribuzione di produzione, è consigliabile usare Criteri di gruppo, Microsoft Endpoint Configuration Manager o Intune.         |
| Windows 8.1 Enterprise <p>Windows 8.1 Pro <p>Windows 7 SP1 Enterprise<p>Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/>**NOTA:** Microsoft Monitoring Agent è ora l'agente di Azure Log Analytics. Per ulteriori informazioni, vedere [Panoramica dell'agente di log analytics.](/azure/azure-monitor/platform/log-analytics-agent)        |
| Windows Server 2019 e versioni successive <p>Windows Server 2019 Core Edition<p>Windows Server versione 1803 e successive | [Script locale](configure-endpoints-script.md)<p>[Criteri di gruppo](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)<p>[Script di onboarding VDI per dispositivi non persistenti](configure-endpoints-vdi.md) <br/>**NOTA:** uno script locale è adatto per un modello di prova, ma non deve essere utilizzato per la distribuzione di produzione. Per una distribuzione di produzione, è consigliabile usare Criteri di gruppo, Microsoft Endpoint Configuration Manager o Intune.    |
| Windows Server 2016<p>Windows Server 2012 R2<p>Windows Server 2008 R2 SP1  | [Microsoft Defender Security Center](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS<p>11.3.1 (Big Sur) <p>10.15 (Catalina)<p>10.14 (Mojave) |[Aggiungere dispositivi non Windows](configure-endpoints-non-windows.md)  |
|iOS |[Aggiungere dispositivi non Windows](configure-endpoints-non-windows.md)  |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS o superiore<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |[Aggiungere dispositivi non Windows](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Eseguire un test di rilevamento

Per verificare che i dispositivi onboarded siano connessi correttamente a Microsoft Defender for Endpoint, puoi eseguire un test di rilevamento.

|Sistema operativo  |Linee guida  |
|---------|---------|
| Windows 10<p>Windows Server 2019<p>Windows Server, versione 1803<p>Windows Server 2016<p>Windows Server 2012 R2     |Vedere [Eseguire un test di rilevamento](run-detection-test.md). <p>Visita il sito degli scenari demo di Microsoft Defender for Endpoint ( ) e [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) prova uno o più degli scenari. Ad esempio, provare lo **scenario demo di protezione fornito dal** cloud.         |
|macOS:<p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave)     |Scarica e usa l'app FAI-da-to-app all'indirizzo [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <p>Per altre informazioni, vedi [Microsoft Defender per Endpoint su macOS.](microsoft-defender-endpoint-mac.md)        |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS o superiore<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |1. Eseguire il comando seguente e cercare il risultato **1**: <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Aprire una finestra del terminale ed eseguire il comando seguente: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Eseguire il comando seguente per elencare eventuali minacce rilevate: <br/>`mdatp threat list`. <p>Per altre informazioni, vedi [Microsoft Defender per Endpoint su Linux.](microsoft-defender-endpoint-linux.md) |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Verificare che Antivirus Microsoft Defender sia in modalità passiva negli endpoint

Ora che gli endpoint sono stati onboarded in Defender for Endpoint, il passaggio successivo consiste nel verificare che Antivirus Microsoft Defender sia in esecuzione in modalità passiva. È possibile utilizzare il prompt dei comandi o PowerShell per eseguire questa attività, come descritto nella tabella seguente:

| Metodo    | Soluzione |
|:--|:--|
| Prompt dei comandi    | 1. In un dispositivo Windows, aprire prompt dei comandi come amministratore. <p>2. Digitare `sc query windefend` e quindi premere INVIO. <p>3. Esaminare i risultati per verificare che Antivirus Microsoft Defender in esecuzione in modalità passiva. |
|PowerShell | 1. In un dispositivo Windows, aprire Windows PowerShell come amministratore. <p>2. Eseguire il `Get-MpComputerStatus` cmdlet. <p>3. Nell'elenco dei risultati, cercare **AMRunningMode: Modalità** passiva o **AMRunningMode: modalità passiva SxS.** |

> [!NOTE]
> Potrebbe essere visualizzato Windows Defender Antivirus anziché Antivirus Microsoft Defender in alcune versioni di Windows.

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Impostare Antivirus Microsoft Defender su Windows Server per la modalità passiva manualmente

Per impostare Antivirus Microsoft Defender modalità passiva in Windows Server, versione 1803 o successiva o Windows Server 2019, attenersi alla seguente procedura:

1. Aprire l'editor del Registro di sistema e quindi passare a `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` .

2. Modificare (o creare) una voce DWORD denominata **ForcePassiveMode** e specificare le impostazioni seguenti:

   - Imposta il valore DWORD su 1.
   - In Base selezionare Esadecimale.

> [!NOTE]
> È possibile utilizzare altri metodi per impostare la chiave del Registro di sistema, ad esempio:
> - Preferenza di Criteri di gruppo
> - Strumento Oggetto Criteri di gruppo locale
> - Un pacchetto in Configuration Manager

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Avviare Antivirus Microsoft Defender su Windows Server 2016

Se si utilizza Windows Server 2016, potrebbe essere necessario avviare manualmente Antivirus Microsoft Defender computer. A tale scopo, è possibile utilizzare il cmdlet PowerShell `mpcmdrun.exe -wdenable` nel dispositivo.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Ottenere gli aggiornamenti per Antivirus Microsoft Defender

Mantenere Antivirus Microsoft Defender aggiornato è fondamentale per garantire ai dispositivi le tecnologie e le funzionalità più recenti necessarie per la protezione da nuove tecniche di malware e attacchi, anche se Antivirus Microsoft Defender è in esecuzione in modalità passiva.

Esistono due tipi di aggiornamenti correlati alla Antivirus Microsoft Defender aggiornati:

- Aggiornamenti delle funzionalità di intelligence per la sicurezza
- Aggiornamenti dei prodotti

Per ottenere gli aggiornamenti, seguire le indicazioni in Gestire Antivirus Microsoft Defender [aggiornamenti e applicare le linee di base.](manage-updates-baselines-microsoft-defender-antivirus.md)

## <a name="uninstall-symantec"></a>Disinstallare Symantec

Dopo aver installato i dispositivi dell'organizzazione in Microsoft Defender for Endpoint, il passaggio successivo consiste nel disinstallare Symantec.

1. [Disabilitare protezione manomissione](https://knowledge.broadcom.com/external/article?legacyId=tech192023) in Symantec.

2. Eliminare la password di disinstallazione per Symantec:<br/>

   1. Nei dispositivi Windows, aprire l'editor del Registro di sistema come amministratore.

   2. Passare a `HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC`.

   3. Cercare una voce denominata **SmcInstData**. 

   4. Fare clic con il pulsante destro del mouse sull'elemento e quindi scegliere **Elimina.** 

3. Rimuovi Symantec dai dispositivi. Per assistenza, vedere la documentazione di Broadcom. Ecco alcune risorse Broadcom: 

   - [Disinstallare Symantec Endpoint Protection](https://knowledge.broadcom.com/external/article/156148/uninstall-symantec-endpoint-protection.html)

   - Windows dispositivi: [disinstallare manualmente Endpoint Protection 14 client in Windows](https://knowledge.broadcom.com/external/article?articleId=170040)
   
   - computer macOS: [rimuovere il software Symantec per Mac usando RemoveSymantecMacFiles](https://knowledge.broadcom.com/external/article?articleId=151387)
   
   - Dispositivi Linux: [domande frequenti per Endpoint Protection su Linux](https://knowledge.broadcom.com/external/article?articleId=162054)

## <a name="make-sure-microsoft-defender-for-endpoint-is-working-correctly"></a>Verificare che Microsoft Defender for Endpoint funzioni correttamente

Dopo aver disinstallato Symantec, il passaggio successivo consiste nel verificare che Defender for Endpoint funzioni correttamente. Visitare il sito degli scenari demo di Microsoft Defender for Endpoint ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Prova uno o più degli scenari dimostrativi in tale pagina, inclusi almeno gli scenari seguenti:
- Protezione fornita dal cloud
- Applicazioni potenzialmente indesiderate
- Protezione di rete

## <a name="next-steps"></a>Passaggi successivi

**Congratulazioni**! La migrazione da [Symantec](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)a Microsoft Defender for Endpoint è stata completata. 
- [Visitare il dashboard delle operazioni](security-operations-dashboard.md) di sicurezza nella Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Gestire Microsoft Defender per Endpoint, dopo la migrazione.](manage-atp-post-migration.md)
