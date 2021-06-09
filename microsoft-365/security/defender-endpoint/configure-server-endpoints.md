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
ms.openlocfilehash: 47d57e51eca4950f7a8f4284fbc916e9d030b2c7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844335"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>Onboard Windows server al servizio Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- Windows Server 2008 R2 SP1
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server (SAC) versione 1803 e successive
- Windows Server 2019 e versioni successive
- Windows Server 2019 Core Edition

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

Defender for Endpoint estende il supporto per includere anche il sistema operativo Windows Server. Questo supporto offre funzionalità avanzate di rilevamento e analisi degli attacchi tramite la console Microsoft Defender Security Center avanzata.

Per una guida pratica su ciò che deve essere in atto per le licenze e l'infrastruttura, vedere [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).

Per indicazioni su come scaricare e usare le Sicurezza di Windows di base per Windows server, vedere Sicurezza di Windows [Baselines](/windows/device-security/windows-security-baselines).

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2008 R2 SP1, Windows Server 2012 R2 e Windows Server 2016

È possibile eseguire l'onboarding di Windows Server 2008 R2 SP1, Windows Server 2012 R2 e Windows Server 2016 a Defender per Endpoint utilizzando una delle opzioni seguenti:

- **Opzione 1:** [eseguire l'onboarding installando e configurando Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)
- **Opzione 2:** [onboard tramite il Centro sicurezza Di Azure](#option-2-onboard-windows-servers-through-azure-security-center)
- **Opzione 3:** [onboard fino Microsoft Endpoint Manager 2002 e versioni successive](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)

Dopo aver completato la procedura di onboarding usando una delle opzioni fornite, è necessario configurare e aggiornare System Center Endpoint Protection [client](#configure-and-update-system-center-endpoint-protection-clients).

> [!NOTE]
> Defender for Endpoint standalone server license is required, per node, per eseguire l'onboard di un server Windows tramite Microsoft Monitoring Agent (opzione 1) o tramite Microsoft Endpoint Manager (opzione 3). In alternativa, è necessaria una licenza di Azure Defender for Servers, per nodo, per eseguire l'onboardboard di un server Windows tramite il Centro sicurezza Di Azure (opzione 2), vedere Funzionalità supportate disponibili [in Azure Defender.](/azure/security-center/security-center-services)

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a>Opzione 1: eseguire l'onboarding installando e configurando Microsoft Monitoring Agent (MMA)

Dovrai installare e configurare MMA per i server Windows per segnalare i dati del sensore a Defender per Endpoint. Per ulteriori informazioni, vedere [Raccogliere i dati di log con l'agente Di log di Azure.](/azure/azure-monitor/platform/log-analytics-agent)

Se si usa già System Center Operations Manager (SCOM) o Azure Monitor (in precedenza noto come Operations Management Suite (OMS),collegare il Microsoft Monitoring Agent (MMA) per creare report nell'area di lavoro di Defender for Endpoint tramite il supporto multihoming.

In generale, è necessario eseguire la procedura seguente:

1. Soddisfare i requisiti di onboarding descritti nella **sezione Prima di** iniziare.
2. Attivare il monitoraggio dei server da Microsoft Defender Security Center.
3. Installare e configurare MMA per il server per segnalare i dati del sensore a Defender per Endpoint.
4. Configurare e aggiornare i System Center Endpoint Protection client.

> [!TIP]
> Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che sia stato correttamente eseguito l'onboarding nel servizio. Per altre informazioni, vedi Eseguire un test di rilevamento su un defender appena [onboarded per endpoint](run-detection-test.md)endpoint.

#### <a name="before-you-begin"></a>Prima di iniziare

Eseguire la procedura seguente per soddisfare i requisiti di onboarding:

Per Windows Server 2008 R2 SP1 o Windows Server 2012 R2, assicurarsi di installare l'hotfix seguente:

- [Aggiornamento per l'esperienza del cliente e telemetria diagnostica](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

Per Windows Server 2008 R2 SP1, assicurarsi di soddisfare i requisiti seguenti:

- Installare [l'aggiornamento cumulativo mensile di febbraio](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
- Installare [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o versione successiva) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > Se si sta gestendo Windows Server 2008 R2 SP1 con SCCM, l'agente client SCCM installa .Net Framework 4.5.2. Non è quindi necessario installare .NET Framework 4.5 (o versione successiva).

Per Windows Server 2008 R2 SP1 e Windows Server 2012 R2: Configurare e [aggiornare System Center Endpoint Protection client](#configure-and-update-system-center-endpoint-protection-clients).

> [!NOTE]
> Questo passaggio è necessario solo se l'organizzazione utilizza System Center Endpoint Protection (SCEP) e si sta onboarding Windows Server 2008 R2 SP1 e Windows Server 2012 R2.

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>Installare e configurare Microsoft Monitoring Agent (MMA) per segnalare i dati del sensore a Microsoft Defender per Endpoint

1. Scaricare il file di installazione [dell'agente: Windows agente a 64 bit.](https://go.microsoft.com/fwlink/?LinkId=828603)

2. Utilizzando l'ID area di lavoro e la chiave Workspace ottenuta nella procedura precedente, scegliere uno dei metodi di installazione seguenti per installare l'agente nel server Windows:
    - [Installare manualmente l'agente utilizzando il programma di installazione](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard). 
    Nella pagina **Opzioni di installazione agente** scegliere **Connessione'agente in Azure Log Analytics (OMS).**
    - [Installare l'agente utilizzando la riga di comando](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).
    - [Configurare l'agente utilizzando uno script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).

> [!NOTE]
> If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a>Configurare Windows proxy server e le impostazioni di connettività Internet, se necessario

Se i server devono usare un proxy per comunicare con Defender per Endpoint, usa uno dei metodi seguenti per configurare la MMA per l'utilizzo del server proxy:

- [Configurare la MMA per l'utilizzo di un server proxy](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [Configurare Windows per l'utilizzo di un server proxy per tutte le connessioni](configure-proxy-internet.md)

Se è in uso un proxy o un firewall, assicurarsi che i server possano accedere a tutti gli URL del servizio Microsoft Defender for Endpoint direttamente e senza l'intercettazione SSL. Per altre informazioni, vedi [abilitare l'accesso a Defender per gli URL del servizio endpoint.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) L'uso dell'intercettazione SSL impedirà al sistema di comunicare con il servizio Defender for Endpoint.

Una volta completato, dovrebbe essere possibile visualizzare i server Windows nel portale entro un'ora.

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a>Opzione 2: onboard Windows server tramite il Centro sicurezza di Azure

1. Nel riquadro Microsoft Defender Security Center di spostamento selezionare **Impostazioni**  >    >  **Onboarding** gestione dispositivi .

2. Selezionare **Windows Server 2008 R2 SP1, 2012 R2 e 2016** come sistema operativo.

3. Fare **clic su Onboard Servers nel Centro sicurezza di Azure.**

4. Seguire le istruzioni di onboarding in [Microsoft Defender for Endpoint con Azure Defender](/azure/security-center/security-center-wdatp) e Se si usa Azure ARC, seguire le istruzioni di onboarding in Enabling the Microsoft Defender for Endpoint [integration](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).

Dopo aver completato i passaggi di onboarding, è necessario configurare e [aggiornare i System Center Endpoint Protection client.](#configure-and-update-system-center-endpoint-protection-clients)

> [!NOTE]
>
> - Perché l'onboarding tramite Azure Defender for Servers funzioni come previsto, il server deve avere un'area di lavoro e una chiave appropriate configurate nelle impostazioni di Microsoft Monitoring Agent (MMA).
> - Una volta configurato, il Management Pack cloud appropriato viene distribuito nel computer e il processo del sensore (MsSenseS.exe) verrà distribuito e avviato.
> - Questa operazione è necessaria anche se il server è configurato per l'utilizzo di un server gateway OMS come proxy.

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a>Opzione 3: onboard Windows server tramite Microsoft Endpoint Manager 2002 e versioni successive

Puoi eseguire l'onboard Windows Server 2012 R2 e Windows Server 2016 usando Microsoft Endpoint Manager versione 2002 e successive. Per altre informazioni, vedi [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch.](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)

Dopo aver completato i passaggi di onboarding, è necessario configurare e [aggiornare i System Center Endpoint Protection client.](#configure-and-update-system-center-endpoint-protection-clients)

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a>Windows Server (SAC) versione 1803, Windows Server 2019 e Windows Server 2019 Core Edition

È possibile eseguire l'onboard di Windows Server (SAC) versione 1803, Windows Server 2019 o Windows Server 2019 Core edition utilizzando i metodi di distribuzione seguenti:

- [Script locale](configure-endpoints-script.md)
- [Criteri di gruppo](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [System Center Configuration Manager 2012 / 2012 R2 1511 / 1602](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [Script di onboarding VDI per dispositivi non persistenti](configure-endpoints-vdi.md)

> [!NOTE]
>
> - Il pacchetto di onboarding per Windows Server 2019 Microsoft Endpoint Manager attualmente spedisce uno script. Per altre informazioni su come distribuire gli script in Configuration Manager, vedi [Pacchetti e programmi in Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)
> - Uno script locale è adatto per un modello di prova, ma non deve essere utilizzato per la distribuzione di produzione. Per una distribuzione di produzione, è consigliabile usare Criteri di gruppo o Microsoft Endpoint Configuration Manager.

Il supporto per Windows Server fornisce informazioni più approfondite sulle attività del server, sulla copertura per il rilevamento di attacchi di kernel e memoria e consente azioni di risposta.

1. Configura le impostazioni di onboarding di Defender per Endpoint nel server Windows usando gli stessi strumenti e metodi per Windows 10 dispositivi. Per altre informazioni, vedi [Onboard Windows 10 dispositivi](configure-endpoints.md).

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

    Se il risultato è "Il servizio specificato non esiste come servizio installato", dovrai installare Microsoft Defender AV. Per ulteriori informazioni, vedere [Antivirus Microsoft Defender in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).

    Per informazioni su come utilizzare Criteri di gruppo per configurare e gestire Antivirus Microsoft Defender nei server Windows, vedere [Use Group Policy settings to configure and manage Antivirus Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).

## <a name="integration-with-azure-defender"></a>Integrazione con Azure Defender

Defender for Endpoint può integrarsi con Azure Defender per fornire una soluzione completa Windows protezione dei server. Con questa integrazione, Azure Defender può usare la potenza di Defender for Endpoint per fornire un rilevamento delle minacce migliorato per Windows server.

In questa integrazione sono incluse le funzionalità seguenti:

- Onboarding automatizzato: il sensore Defender for Endpoint viene abilitato automaticamente nei Windows server di cui è stata eseguita l'onboarding in Azure Defender. Per altre informazioni sull'onboarding di Azure Defender, vedi [Usare la licenza integrata di Microsoft Defender for Endpoint.](/azure/security-center/security-center-wdatp)

    > [!NOTE]
    > L'integrazione tra Azure Defender for Servers e Microsoft Defender for Endpoint è stata estesa per supportare [Windows Server 2019 e Windows Virtual Desktop (WVD).](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)

- Windows i server monitorati da Azure Defender saranno disponibili anche in Defender for Endpoint: Azure Defender si connette senza problemi al tenant Defender for Endpoint, fornendo una singola visualizzazione tra client e server.  Inoltre, gli avvisi defender per endpoint saranno disponibili nella console di Azure Defender.
- Indagine server: i clienti di Azure Defender possono accedere Microsoft Defender Security Center per eseguire un'indagine dettagliata per scoprire l'ambito di una potenziale violazione.

> [!IMPORTANT]
> - Quando usi Azure Defender per monitorare i server, viene creato automaticamente un tenant defender per endpoint (negli Stati Uniti per gli utenti statunitensi, nell'UE per gli utenti europei e del Regno Unito).<br>
I dati raccolti da Defender per Endpoint vengono archiviati nella posizione geografica del tenant come identificato durante il provisioning.
> - Se usi Defender per Endpoint prima di usare Azure Defender, i dati verranno archiviati nella posizione specificata al momento della creazione del tenant anche se ti integri con Azure Defender in un secondo momento.
> - Dopo la configurazione, non è possibile modificare la posizione in cui sono archiviati i dati. Se è necessario spostare i dati in un'altra posizione, è necessario contattare il supporto tecnico Microsoft per reimpostare il tenant. <br>
Il monitoraggio degli endpoint del server che utilizza questa integrazione è stato disabilitato per Office 365 GCC clienti.

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>Configurare e aggiornare i System Center Endpoint Protection client

Defender for Endpoint si integra con System Center Endpoint Protection. L'integrazione fornisce visibilità ai rilevamenti di malware e per interrompere la propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto.

Per abilitare questa integrazione, sono necessari i passaggi seguenti:

- Installare l'aggiornamento della piattaforma antimalware di gennaio [2017 per Endpoint Protection client](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).

- [Configurare l'appartenenza del servizio di protezione cloud](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) del client SCEP all'impostazione Avanzate. 

## <a name="offboard-windows-servers"></a>Offboard Windows server

È possibile eseguire l'offboard dell'edizione Windows Server (SAC), Windows Server 2019 e Windows Server 2019 Core nello stesso metodo disponibile per i dispositivi client Windows 10.

Per altre Windows server, sono disponibili due opzioni per eseguire l'offboard Windows server dal servizio:

- Disinstallare l'agente MMA
- Rimuovere la configurazione dell'area di lavoro defender per endpoint

> [!NOTE]
> L'offboarding fa sì che il server Windows interrompi l'invio dei dati del sensore al portale, ma i dati del server Windows, incluso il riferimento agli avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a>Disinstallare Windows server disinstallando l'agente MMA

Per eseguire l'offboard Windows server, puoi disinstallare l'agente MMA dal server Windows o scollegarlo dalla segnalazione nell'area di lavoro defender per endpoint. Dopo l'offboarding dell'agente, il server Windows non invierà più i dati del sensore a Defender per Endpoint.
Per ulteriori informazioni, vedere [Per disabilitare un agente.](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>Rimuovere la configurazione dell'area di lavoro defender per endpoint

Per eseguire l'offboard Windows server, è possibile utilizzare uno dei metodi seguenti:

- Rimuovere la configurazione dell'area di lavoro defender per endpoint dall'agente MMA
- Eseguire un comando di PowerShell per rimuovere la configurazione

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>Rimuovere la configurazione dell'area di lavoro defender per endpoint dall'agente MMA

1. Nella finestra **Microsoft Monitoring Agent ,** selezionare la scheda Azure Log **Analytics (OMS).**

2. Seleziona l'area di lavoro Defender per Endpoint e fai clic su **Rimuovi.**

    ![Immagine di Microsoft Monitoring Agent proprietà](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>Eseguire un comando di PowerShell per rimuovere la configurazione

1. Ottenere l'ID area di lavoro:

   1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **onboarding**.

   1. Selezionare **Windows Server 2008 R2 SP1, 2012 R2 e 2016** come sistema operativo e ottenere l'ID area di lavoro:

      ![Immagine dell'onboarding Windows server](images/atp-server-offboarding-workspaceid.png)

2. Aprire un PowerShell con privilegi elevati ed eseguire il comando seguente. Utilizzare l'ID area di lavoro ottenuto e sostituendo `WorkspaceID` :

    ```powershell
    $ErrorActionPreference = "SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a>Server di onboarding senza soluzione di gestione

### <a name="using-group-policy"></a>Utilizzo di Criteri di gruppo

**Passaggio 1: creare i file necessari da copiare nei server.**

1. Passare a c:\windows\sysvol\domain\scripts (il controllo delle modifiche potrebbe essere necessario in uno dei controller di dominio).
1. Crea una cartella denominata MMA.
1. Scarica quanto segue e inserisci nella cartella MMA:

    **Aggiornamento per l'esperienza del cliente e telemetria diagnostica (Windows Server 2008 R2 e Windows Server 2012 R2)**

    [Per Windows 2008 R2 x64](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [Per Windows 2012 R2 x64](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > In questo articolo si presuppone che si utilizzino server basati su x64 (agente MMA .exe x64 [Nuova versione conforme a SHA-2](https://go.microsoft.com/fwlink/?LinkId=828603))

**Passaggio 2: Creare un nome di file DeployMMA.cmd (tramite blocco note)** Aggiungere le righe seguenti al file cmd. Tieni presente che avrai bisogno dell'ID workspace e della chiave.

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

## <a name="group-policy-configuration"></a>Configurazione di Criteri di gruppo

Crea un nuovo criterio di gruppo specifico per i dispositivi di onboarding, ad esempio "Microsoft Defender for Endpoint Onboarding".

- Creare una cartella di Criteri di gruppo denominata "c:\windows\MMA"

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="cartelle":::

    **Verrà aggiunta una nuova cartella in ogni server a cui viene applicato l'oggetto Criteri di gruppo, denominato MMA, e che verrà archiviata in c:\windows. Conterrà i file di installazione per l'MMA, i prerequisiti e lo script di installazione.**

- Creare una preferenza File di Criteri di gruppo per ognuno dei file archiviati in Accesso rete.

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="immagine criteri di gruppo1":::

Copia i file da DOMAIN\NETLOGON\MMA\filename in C:\windows\MMA\filename, in modo che i file di installazione siano locali **nel server**:

:::image type="content" source="images/deploymma.png" alt-text="distribuire mma cmd":::

Per i due KB (uno per Windows Server 2008R2/Windows 7 e l'altro per Windows Server 2012 R2) ripetere il processo ma creare la destinazione a livello di elemento nella scheda COMMON, in modo che il file venga copiato solo nella piattaforma o nella versione del sistema operativo appropriata nell'ambito:

:::image type="content" source="images/targeteditor.png" alt-text="editor di destinazione":::

- Per Windows Server 2008 R2 è necessario (e verrà copiato solo) Windows6.1-BJ3080149-x64.msu
- Per Windows Server 2012 R2 è necessario (e verrà copiato solo) Windows8.1-BJ3080149-x64.msu

Al termine di questa operazione, è necessario creare un criterio script di avvio:

:::image type="content" source="images/startupprops.png" alt-text="start up properties":::

Il nome del file da eseguire qui è c:\windows\MMA\DeployMMA.cmd.
Una volta riavviato il server come parte del processo di avvio, installerà l'aggiornamento per l'esperienza del cliente e la telemetria diagnostica KB, quindi installerà l'agente MMA, impostando l'ID e la chiave dell'area di lavoro, e il server verrà onboarded.

È inoltre possibile utilizzare **un'attività immediata** per eseguire deployMMA.cmd se non si desidera riavviare tutti i server.
Questa operazione può essere eseguita in due fasi. Creare innanzitutto **i file e la** cartella nell'oggetto Criteri di gruppo: concedere al sistema il tempo necessario per verificare che l'oggetto Criteri di gruppo sia stato applicato e che tutti i server dispongono dei file di installazione. Aggiungi quindi l'attività immediata. In questo modo si ottiene lo stesso risultato senza richiedere un riavvio.

Poiché lo script dispone di un metodo exit e non viene rieseguiti se la MMA è installata, è anche possibile utilizzare un'attività pianificata giornaliera per ottenere lo stesso risultato. Analogamente a un criterio di conformità di Configuration Manager, verrà verificata ogni giorno per verificare che la MMA sia presente.

:::image type="content" source="images/schtask.png" alt-text="attività di pianificazione":::

:::image type="content" source="images/newtaskprops.png" alt-text="nuove proprietà delle attività":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="distribuire le proprietà di download mma":::

:::image type="content" source="images/tasksch.png" alt-text="utilità di pianificazione":::

Come accennato nella documentazione relativa all'onboarding per Server in particolare per Server 2008 R2, vedere di seguito:

Per Windows Server 2008 R2 PS1, assicurarsi di soddisfare i requisiti seguenti:

- Installare [l'aggiornamento cumulativo mensile di febbraio 2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
- Installare [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (o versione successiva) o [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

Si prega di verificare che i KB siano presenti prima dell'onboarding Windows Server 2008 R2 Questo processo consente di eseguire l'onboarding di tutti i server se non si dispone di Configuration Manager che gestisce i server.

## <a name="related-topics"></a>Argomenti correlati

- [Aggiungere di dispositivi Windows 10](configure-endpoints.md)
- [Aggiungere dispositivi non Windows](configure-endpoints-non-windows.md)
- [Configurare le impostazioni di connettività Proxy e Internet](configure-proxy-internet.md)
- [Eseguire un test di rilevamento in un dispositivo Defender for Endpoint appena onboarded](run-detection-test.md)
- [Risoluzione dei problemi di onboarding di Microsoft Defender per endpoint](troubleshoot-onboarding.md)
