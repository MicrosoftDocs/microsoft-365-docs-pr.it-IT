---
title: Onboard dei server Windows nel servizio Microsoft Defender for Endpoint
description: Onboard dei server Windows in modo che possano inviare i dati del sensore al sensore Microsoft Defender for Endpoint.
keywords: onboarding di server, server, 2012r2, 2016, 2019, onboarding del server, gestione dei dispositivi, configurare i server Windows ATP, eseguire l'onboarding di Microsoft Defender per i server endpoint, eseguire l'onboarding di Microsoft Defender per i server endpoint
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
ms.openlocfilehash: bd92b44892b49a007316acb97296a44514db0578
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061701"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>Onboard dei server Windows nel servizio Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- Windows Server 2008 R2 SP1
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server (SAC) versione 1803 e successive
- Windows Server 2019 e versioni successive
- Windows Server 2019 Core Edition

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)


Defender for Endpoint estende il supporto per includere anche il sistema operativo Windows Server. Questo supporto offre funzionalità avanzate di rilevamento e analisi degli attacchi tramite la console di Microsoft Defender Security Center.

Per una guida pratica su cosa deve essere in atto per le licenze e l'infrastruttura, vedi [Protezione dei server Windows con Defender per endpoint.](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)

Per indicazioni su come scaricare e usare Le linee di base della sicurezza di Windows per i server Windows, vedi [Linee di base per la sicurezza di Windows.](https://docs.microsoft.com/windows/device-security/windows-security-baselines)

<br>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2008 R2 SP1, Windows Server 2012 R2 e Windows Server 2016

È possibile eseguire l'onboarding di Windows Server 2008 R2 SP1, Windows Server 2012 R2 e Windows Server 2016 in Defender for Endpoint utilizzando una delle opzioni seguenti:

- **Opzione 1:** [eseguire l'onboarding installando e configurando Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)
- **Opzione 2:** [onboard tramite il Centro sicurezza Di Azure](#option-2-onboard-windows-servers-through-azure-security-center)
- **Opzione 3**: [Onboard tramite Microsoft Endpoint Manager versione 2002 e successive](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)


Dopo aver completato i passaggi di onboarding usando una delle opzioni fornite, è necessario configurare e aggiornare i client [di System Center Endpoint Protection.](#configure-and-update-system-center-endpoint-protection-clients)


> [!NOTE]
> Defender for Endpoint è necessaria una licenza server autonoma per nodo per eseguire l'onboardboard di un server Windows tramite Microsoft Monitoring Agent (opzione 1) o Tramite Microsoft Endpoint Manager (opzione 3). In alternativa, è necessaria una licenza di Azure Defender for Servers, per nodo, per eseguire l'onboardboard di un server Windows tramite Il Centro sicurezza Di Azure (opzione 2), vedere Funzionalità supportate disponibili nel Centro sicurezza di [Azure.](https://docs.microsoft.com/azure/security-center/security-center-services)


### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a>Opzione 1: eseguire l'onboarding installando e configurando Microsoft Monitoring Agent (MMA)
Dovrai installare e configurare MMA per i server Windows per segnalare i dati del sensore a Defender per Endpoint. Per ulteriori informazioni, vedere [Raccogliere i dati di log con l'agente Di log di Azure.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)

Se si usa già System Center Operations Manager (SCOM) o Azure Monitor (in precedenza noto come Operations Management Suite (OMS),collegare Microsoft Monitoring Agent (MMA) per creare report nell'area di lavoro di Defender for Endpoint tramite il supporto di Multihoming.

In generale, è necessario eseguire la procedura seguente:
1. Soddisfare i requisiti di onboarding descritti nella **sezione Prima di** iniziare.
2. Attivare il monitoraggio dei server da Microsoft Defender Security Center.
3. Installare e configurare MMA per il server per segnalare i dati del sensore a Defender per Endpoint.
4. Configurare e aggiornare i client di System Center Endpoint Protection.


> [!TIP]
> Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che sia stato correttamente eseguito l'onboarding nel servizio. Per altre informazioni, vedi Eseguire un test di rilevamento su un defender appena [onboarded per endpoint](run-detection-test.md)endpoint.


#### <a name="before-you-begin"></a>Prima di iniziare 
Eseguire la procedura seguente per soddisfare i requisiti di onboarding:

 - Per Windows Server 2008 R2 SP1 o Windows Server 2012 R2, assicurarsi di installare l'hotfix seguente:
    - [Aggiornamento per l'esperienza del cliente e telemetria diagnostica](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

 - Inoltre, per Windows Server 2008 R2 SP1, assicurarsi di soddisfare i requisiti seguenti:
    - Installare [l'aggiornamento cumulativo mensile di febbraio](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
    - Installare [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o versione successiva) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

 - Per Windows Server 2008 R2 SP1 e Windows Server 2012 R2: Configurare e aggiornare i client [di System Center Endpoint Protection.](#configure-and-update-system-center-endpoint-protection-clients)

    > [!NOTE]
    > Questo passaggio è necessario solo se l'organizzazione usa System Center Endpoint Protection (SCEP) e stai onboarding di Windows Server 2008 R2 SP1 e Windows Server 2012 R2.


<span id="server-mma"/>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Installare e configurare Microsoft Monitoring Agent (MMA) per segnalare i dati del sensore a Microsoft Defender per Endpoint

1. Scaricare il file di installazione dell'agente: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).

2. Utilizzando l'ID area di lavoro e la chiave Workspace ottenuta nella procedura precedente, scegliere uno dei metodi di installazione seguenti per installare l'agente nel server Windows:
    - [Installare manualmente l'agente utilizzando il programma di installazione](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). <br>
    Nella pagina **Opzioni di installazione agente** scegliere Connetti **l'agente ad Azure Log Analytics (OMS).**
    - [Installare l'agente utilizzando la riga di comando](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configurare l'agente utilizzando uno script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

> [!NOTE]
> If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.


<span id="server-proxy"/>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a>Configurare le impostazioni di connettività Internet e proxy di Windows Server, se necessario
Se i server devono usare un proxy per comunicare con Defender per Endpoint, usa uno dei metodi seguenti per configurare la MMA per l'utilizzo del server proxy:


- [Configurare la MMA per l'utilizzo di un server proxy](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [Configurare Windows per l'utilizzo di un server proxy per tutte le connessioni](configure-proxy-internet.md)

Se è in uso un proxy o un firewall, assicurarsi che i server possano accedere a tutti gli URL del servizio Microsoft Defender for Endpoint direttamente e senza l'intercettazione SSL. Per altre informazioni, vedi [abilitare l'accesso a Defender per gli URL del servizio endpoint.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) L'uso dell'intercettazione SSL impedirà al sistema di comunicare con il servizio Defender for Endpoint. 

Al termine, nel portale dovrebbero essere visualizzati i server Windows onboarded entro un'ora.

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a>Opzione 2: onboard dei server Windows tramite il Centro sicurezza Di Azure
1. Nel riquadro di spostamento di Microsoft Defender Security Center seleziona **Impostazioni**  >    >  **Onboarding** gestione dispositivi.

2. Selezionare **Windows Server 2008 R2 SP1, 2012 R2 e 2016** come sistema operativo.

3. Fare **clic su Onboard Servers nel Centro sicurezza di Azure.**

4. Seguire le istruzioni per l'onboarding in [Microsoft Defender for Endpoint with Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).

Dopo aver completato i passaggi di onboarding, è necessario configurare e aggiornare i client [di System Center Endpoint Protection.](#configure-and-update-system-center-endpoint-protection-clients)

> [!NOTE]
> - Perché l'onboarding tramite Azure Defender for Servers (in precedenza Azure Security Center Standard Edition) funzioni come previsto, il server deve avere un'area di lavoro e una chiave appropriate configurate nelle impostazioni di Microsoft Monitoring Agent (MMA).
> - Una volta configurato, il Management Pack cloud appropriato viene distribuito nel computer e il processo del sensore (MsSenseS.exe) verrà distribuito e avviato. 
> - Questa operazione è necessaria anche se il server è configurato per l'utilizzo di un server gateway OMS come proxy.

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a>Opzione 3: onboard dei server Windows tramite Microsoft Endpoint Manager versione 2002 e successive
Puoi eseguire l'onboardazione di Windows Server 2012 R2 e Windows Server 2016 utilizzando Microsoft Endpoint Manager versione 2002 e successive. Per altre informazioni, vedi [Microsoft Defender for Endpoint nel ramo corrente di Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)

Dopo aver completato i passaggi di onboarding, è necessario configurare e aggiornare i client [di System Center Endpoint Protection.](#configure-and-update-system-center-endpoint-protection-clients)

<br>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a>Windows Server (SAC) versione 1803, Windows Server 2019 e Windows Server 2019 Core Edition
È possibile eseguire l'onboard di Windows Server (SAC) versione 1803, Windows Server 2019 o Windows Server 2019 Core edition utilizzando i metodi di distribuzione seguenti:

- [Script locale](configure-endpoints-script.md) 
- [Criteri di gruppo](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [System Center Configuration Manager 2012 / 2012 R2 1511 / 1602](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [Script di onboarding VDI per dispositivi non persistenti](configure-endpoints-vdi.md)

> [!NOTE]
> - Il pacchetto di onboarding per Windows Server 2019 tramite Microsoft Endpoint Manager attualmente contiene uno script. Per altre informazioni su come distribuire gli script in Configuration Manager, vedi [Pacchetti e programmi in Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)
> - Uno script locale è adatto per un modello di prova, ma non deve essere utilizzato per la distribuzione di produzione. Per una distribuzione di produzione, ti consigliamo di usare Criteri di gruppo o Microsoft Endpoint Configuration Manager.

Il supporto per Windows Server fornisce informazioni più approfondite sulle attività del server, sulla copertura per il rilevamento di attacchi di kernel e memoria e consente azioni di risposta.

1. Configura le impostazioni di onboarding di Defender per endpoint nel server Windows usando gli stessi strumenti e metodi per i dispositivi Windows 10. Per altre informazioni, vedi [Onboard di dispositivi Windows 10.](configure-endpoints.md)

2. Se si esegue una soluzione antimalware di terze parti, è necessario applicare le impostazioni della modalità passiva di Microsoft Defender AV seguenti. Verificare che sia stato configurato correttamente:

    1. Impostare la voce del Registro di sistema seguente:
       - Percorso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
       - Nome: ForceDefenderPassiveMode
       - Tipo: REG_DWORD
       - Value: 1

    1. Eseguire il comando di PowerShell seguente per verificare che la modalità passiva sia stata configurata:

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. Verificare che sia stato trovato un evento recente contenente l'evento in modalità passiva:

       ![Immagine del risultato della verifica in modalità passiva](images/atp-verify-passive-mode.png)

3. Eseguire il comando seguente per verificare se Microsoft Defender AV è installato:

   ```sc.exe query Windefend```

    Se il risultato è "Il servizio specificato non esiste come servizio installato", dovrai installare Microsoft Defender AV. Per altre informazioni, vedi [Microsoft Defender Antivirus in Windows 10.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)
    
    Per informazioni su come usare Criteri di gruppo per configurare e gestire Microsoft Defender Antivirus nei server Windows, vedere Usare le impostazioni di Criteri di gruppo per configurare e gestire [Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)

<br>

## <a name="integration-with-azure-security-center"></a>Integrazione con il Centro sicurezza di Azure
Defender for Endpoint può integrarsi con Il Centro sicurezza Di Azure per fornire una soluzione completa di protezione dei server Windows. Con questa integrazione, Il Centro sicurezza di Azure può usare la potenza di Defender for Endpoint per fornire un rilevamento delle minacce migliorato per i server Windows.

In questa integrazione sono incluse le funzionalità seguenti:
- Onboarding automatico: il sensore Defender for Endpoint viene abilitato automaticamente nei server Windows onboarding nel Centro sicurezza Di Azure. Per ulteriori informazioni sull'onboarding del Centro sicurezza di Azure, vedere [Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).

    > [!NOTE]
    > L'onboarding automatico è applicabile solo per Windows Server 2008 R2 SP1, Windows Server 2012 R2 e Windows Server 2016.

- I server Windows monitorati dal Centro sicurezza di Azure saranno disponibili anche in Defender for Endpoint: Azure Security Center si connette senza problemi al tenant Defender for Endpoint, offrendo una singola visualizzazione tra client e server.  Inoltre, gli avvisi di Defender for Endpoint saranno disponibili nella console del Centro sicurezza Di Azure.
- Indagine server: i clienti del Centro sicurezza Di Azure possono accedere a Microsoft Defender Security Center per eseguire indagini dettagliate per scoprire l'ambito di una potenziale violazione.

> [!IMPORTANT]
> - Quando si utilizza il Centro sicurezza di Azure per monitorare i server, viene creato automaticamente un tenant Defender for Endpoint (negli Stati Uniti per gli utenti statunitensi, nell'UE per gli utenti europei e del Regno Unito).<br>
I dati raccolti da Defender per Endpoint vengono archiviati nella posizione geografica del tenant come identificato durante il provisioning.
> - Se usi Defender per Endpoint prima di usare Il Centro sicurezza di Azure, i dati verranno archiviati nella posizione specificata al momento della creazione del tenant anche se ti integri con Il Centro sicurezza Di Azure in un secondo momento.
> - Dopo la configurazione, non è possibile modificare la posizione in cui sono archiviati i dati. Se è necessario spostare i dati in un'altra posizione, è necessario contattare il supporto tecnico Microsoft per reimpostare il tenant. <br>
Il monitoraggio degli endpoint del server che utilizza questa integrazione è stato disabilitato per i clienti di Office 365 GCC.

<br>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Configurare e aggiornare i client di System Center Endpoint Protection

Defender for Endpoint si integra con System Center Endpoint Protection. L'integrazione fornisce visibilità ai rilevamenti di malware e per interrompere la propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto.

Per abilitare questa integrazione, sono necessari i passaggi seguenti:
- Installare l'aggiornamento della piattaforma antimalware di gennaio [2017 per i client di Endpoint Protection.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)

- [Configurare l'appartenenza del servizio di protezione cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) del client SCEP all'impostazione Avanzate. 

<br>

## <a name="offboard-windows-servers"></a>Offboard di server Windows
Puoi eseguire l'offboard di Windows Server (SAC), Windows Server 2019 e Windows Server 2019 Core edition nello stesso metodo disponibile per i dispositivi client Windows 10.

Per altre versioni di Windows Server, sono disponibili due opzioni per eseguire l'offboard dei server Windows dal servizio:
- Disinstallare l'agente MMA
- Rimuovere la configurazione dell'area di lavoro defender per endpoint

> [!NOTE]
> L'offboarding fa sì che il server Windows interrompi l'invio dei dati del sensore al portale, ma i dati dal server Windows, incluso il riferimento a eventuali avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a>Disinstallare i server Windows disinstallando l'agente MMA
Per eseguire l'offboard del server Windows, puoi disinstallare l'agente MMA dal server Windows o scollegarlo dalla creazione di report nell'area di lavoro defender per endpoint. Dopo l'offboarding dell'agente, il server Windows non invierà più i dati del sensore a Defender per Endpoint.
Per ulteriori informazioni, vedere [Per disabilitare un agente.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>Rimuovere la configurazione dell'area di lavoro defender per endpoint
Per eseguire l'offboard del server Windows, è possibile utilizzare uno dei metodi seguenti:

- Rimuovere la configurazione dell'area di lavoro defender per endpoint dall'agente MMA
- Eseguire un comando di PowerShell per rimuovere la configurazione

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>Rimuovere la configurazione dell'area di lavoro defender per endpoint dall'agente MMA

1. Nelle proprietà **di Microsoft Monitoring Agent** selezionare la scheda Azure Log Analytics **(OMS).**

2. Seleziona l'area di lavoro Defender per Endpoint e fai clic su **Rimuovi.**

    ![Immagine delle proprietà di Microsoft Monitoring Agent](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>Eseguire un comando di PowerShell per rimuovere la configurazione

1. Ottenere l'ID area di lavoro:

   1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Onboarding.**

   1. Selezionare **Windows Server 2008 R2 SP1, 2012 R2 e 2016** come sistema operativo e ottenere l'ID area di lavoro:

      ![Immagine dell'onboarding di Windows Server](images/atp-server-offboarding-workspaceid.png)

2. Aprire un PowerShell con privilegi elevati ed eseguire il comando seguente. Utilizzare l'ID area di lavoro ottenuto e sostituendo `WorkspaceID` :

    ```powershell
    $ErrorActionPreference = "SilentlyContinue"
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

<br>

## <a name="related-topics"></a>Argomenti correlati
- [Onboard di dispositivi Windows 10](configure-endpoints.md)
- [Onboard di dispositivi non Windows](configure-endpoints-non-windows.md)
- [Configurare le impostazioni di connettività Proxy e Internet](configure-proxy-internet.md)
- [Eseguire un test di rilevamento in un dispositivo Defender for Endpoint appena onboarded](run-detection-test.md)
- [Risoluzione dei problemi di onboarding di Microsoft Defender per endpoint](troubleshoot-onboarding.md)
