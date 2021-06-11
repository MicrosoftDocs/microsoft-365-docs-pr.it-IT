---
title: Configurare le impostazioni del proxy del dispositivo e della connessione Internet
description: Configurare le impostazioni di Microsoft Defender per proxy endpoint e Internet per abilitare la comunicazione con il servizio cloud.
keywords: configurare, proxy, Internet, connettività Internet, impostazioni, impostazioni proxy, netsh, winhttp, server proxy
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
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0de55eefe2f7dd8c9f891fbe126a68a49699ecd3
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594098"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurare le impostazioni di connettività Proxy e Internet del dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Il sensore Defender for Endpoint richiede Microsoft Windows HTTP (WinHTTP) per segnalare i dati del sensore e comunicare con il servizio Defender for Endpoint.

Il sensore Defender for Endpoint incorporato viene eseguito nel contesto di sistema usando l'account LocalSystem. Il sensore usa Microsoft Windows HTTP Services (WinHTTP) per abilitare la comunicazione con il servizio cloud Defender for Endpoint.

>[!TIP]
>Per le organizzazioni che usano i proxy come porta di accesso a Internet, è possibile usare la protezione della rete per esaminare gli eventi che si verificano dietro un proxy. Per altre informazioni, vedere [Esaminare gli eventi di connessione che si verificano dietro i proxy di inoltro](investigate-behind-proxy.md).

L'impostazione di configurazione WinHTTP è indipendente dalle impostazioni del proxy di esplorazione Internet di Windows Internet (WinINet) e può individuare un server proxy solo utilizzando i metodi di individuazione seguenti:

- Metodi di individuazione automatica:

  - Proxy trasparente

  - Protocollo Web Proxy Auto-discovery (WPAD)

    > [!NOTE]
    > Se si usa il proxy trasparente o WPAD nella topologia di rete, non sono necessarie impostazioni di configurazione speciali. Per altre informazioni sulle esclusioni degli URL di Defender for Endpoint nel proxy, vedi Abilitare l'accesso a Defender per gli URL del servizio [endpoint nel server proxy.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

- Configurazione manuale del proxy statico:

  - Configurazione basata sul registro

  - WinHTTP configurato utilizzando il comando netsh. Questo è adatto solo per desktop in una topologia stabile (ad esempio: un desktop in una rete aziendale dietro lo stesso proxy)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Configurare manualmente il server proxy con un proxy statico basato sul registro

Configura un proxy statico basato sul Registro di sistema per consentire solo al sensore Defender for Endpoint di segnalare i dati di diagnostica e comunicare con Defender per i servizi endpoint se a un computer non è consentito connettersi a Internet.

> [!NOTE]
> Quando si utilizza questa opzione in Windows 10 o Windows Server 2019, è consigliabile avere la build (o versione successiva) seguente e l'aggiornamento cumulativo cumulativo:
>
> - Windows 10, versione 1809 o Windows Server 2019 -https://support.microsoft.com/kb/5001384
> - Windows 10, versione 1909 -https://support.microsoft.com/kb/4601380
> - Windows 10, versione 2004 -https://support.microsoft.com/kb/4601382
> - Windows 10, versione 20H2 -https://support.microsoft.com/kb/4601382
>
> Questi aggiornamenti migliorano la connettività e l'affidabilità del canale CnC (Comando e controllo).

Il proxy statico è configurabile tramite Criteri di gruppo. I criteri di gruppo sono disponibili in:

- **Modelli amministrativi > Windows componenti > raccolte dati e build di anteprima > configurare l'utilizzo del proxy autenticato per il servizio Esperienza utente connessa e telemetria**

  Impostarlo su **Abilitato e** selezionare Disabilita utilizzo **proxy autenticato**.

  ![Immagine dell'impostazione di Criteri di gruppo1](images/atp-gpo-proxy1.png)

- Modelli amministrativi > Windows componenti > raccolte dati e build di anteprima > **Configurare esperienze utente connesse e telemetria**:

  Configurare il proxy inverso

  ![Immagine dell'impostazione di Criteri di gruppo2](images/atp-gpo-proxy2.png)

  Il criterio imposta due valori del Registro di sistema, `TelemetryProxyServer` come REG_SZ e come `DisableEnterpriseAuthProxy` REG_DWORD, nella chiave del Registro di sistema `HKLM\Software\Policies\Microsoft\Windows\DataCollection` .

  Il valore del Registro `TelemetryProxyServer` di sistema assume il formato stringa seguente:

  ```text
  <server name or ip>:<port>
  ```

  Ad esempio: 10.0.0.6:8080

  Il valore del registro `DisableEnterpriseAuthProxy` deve essere impostato su 1.

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Configurare manualmente il server proxy utilizzando il comando netsh

Usare netsh per configurare un proxy statico a livello di sistema.

> [!NOTE]
> - Questa operazione avrà effetto su tutte le applicazioni, inclusi i servizi di Windows che usano WinHTTP con proxy predefinito.</br>
> - I portatili che cambiano topologia (ad esempio, da ufficio a casa) non funzionano correttamente con netsh. È consigliabile usare la configurazione del proxy statico basata sul registro.

1. Aprire un prompt dei comandi con privilegi elevati:

   1. Passare a **Start** e digitare **cmd**.

   1. Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

2. Immettere il comando indicato di seguito e premere **INVIO**:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Ad esempio: `netsh winhttp set proxy 10.0.0.6:8080`

Per reimpostare il proxy winhttp, immettere il comando indicato di seguito e premere **INVIO**:

```PowerShell
netsh winhttp reset proxy
```

Per altre informazioni, vedere [Sintassi comando netsh, contesti e formattazione](/windows-server/networking/technologies/netsh/netsh-contexts).

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>Abilitare l'accesso agli URL del servizio Microsoft Defender for Endpoint nel server proxy

Se un proxy o un firewall blocca tutto il traffico per impostazione predefinita e consente solo domini specifici, aggiungere i domini elencati nel foglio di lavoro scaricabile all'elenco di domini consentiti.

Nel seguente foglio di calcolo scaricabile sono elencati i servizi e gli URL associati a cui la rete deve essere in grado di connettersi. È consigliabile verificare che non siano presenti regole di filtro di rete o firewall che negherebbero l'accesso *a* questi URL oppure potrebbe essere necessario creare una regola di autorizzazione specifica per tali URL.


| Foglio di calcolo dell'elenco dei domini | Descrizione |
|:-----|:-----|
|![Immagine di scorrimento per il foglio di calcolo degli URL di Microsoft Defender for Endpoint](images/mdatp-urls.png)<br/>  | Foglio di calcolo di record DNS specifici per le posizioni dei servizi, le posizioni geografiche e il sistema operativo. <br><br>[Scaricare il foglio di calcolo qui.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


Se un proxy o un firewall ha l’analisi HTTPS (ispezione SSL) abilitata, bisogna escludere i domini elencati nella tabella di analisi HTTPS di cui sopra.

> [!NOTE]
> settings-win.data.microsoft.com è necessario solo se si dispone di Windows 10 che eseguono la versione 1803 o precedente.<br>


> [!NOTE]
> Gli URL che includono v20 in essi sono necessari solo se hai Windows 10 dispositivi che eseguono la versione 1803 o successiva. Ad esempio, è necessario per un dispositivo Windows 10 che esegue la versione 1803 o successiva e sia stato onboarded nell'area `us-v20.events.data.microsoft.com` Archiviazione dati statunitensi.


> [!NOTE]
> Se si utilizza un Antivirus Microsoft Defender nell'ambiente, vedere [Configure network connections to the Antivirus Microsoft Defender cloud service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).

Se un proxy o un firewall blocca il traffico anonimo, poiché il sensore Defender for Endpoint si connette dal contesto di sistema, assicurati che il traffico anonimo sia consentito negli URL elencati in precedenza.

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA): requisiti proxy e firewall per le versioni precedenti di Windows client o Windows Server

Le informazioni seguenti elencano le informazioni di configurazione del proxy e del firewall necessarie per comunicare con l'agente di log analytics (spesso noto come Microsoft Monitoring Agent) per le versioni precedenti di Windows, ad esempio Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 e Windows Server 2016.

|Risorsa agente|Porte |Direction |Ignorare l'ispezione HTTPS|
|------|---------|--------|--------|   
|*.ods.opinsights.azure.com |Porta 443 |In uscita|Sì |  
|*.oms.opinsights.azure.com |Porta 443 |In uscita|Sì |  
|*.blob.core.windows.net |Porta 443 |In uscita|Sì |
|*.azure-automation.net |Porta 443 |In uscita|Sì |  


> [!NOTE]
> Come soluzione basata sul cloud, l'intervallo IP può cambiare. È consigliabile passare all'impostazione di risoluzione DNS.

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>Verificare Microsoft Monitoring Agent (MMA) Service URL Requirements 

Vedere le indicazioni seguenti per eliminare il requisito dei caratteri jolly (*) per l'ambiente specifico quando si utilizza il Microsoft Monitoring Agent (MMA) per le versioni precedenti di Windows.

1.  Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint and](https://go.microsoft.com/fwlink/p/?linkid=2010326) [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).

2.  Verificare che il computer eserciti correttamente la segnalazione nel Microsoft Defender Security Center portale.

3.  Eseguire lo strumento TestCloudConnection.exe da "C:\Programmi\Microsoft Monitoring Agent\Agente" per convalidare la connettività e visualizzare gli URL necessari per l'area di lavoro specifica.

4.  Controlla l'elenco degli URL degli endpoint di Microsoft Defender per l'elenco completo dei requisiti per la tua area geografica (fai riferimento al Foglio di calcolo DEGLI URL [del servizio).](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

    ![Immagine dell'amministratore in Windows PowerShell](images/admin-powershell.png)

I caratteri jolly (*) utilizzati negli endpoint URL *.ods.opinsights.azure.com, *.oms.opinsights.azure.com e *.agentsvc.azure-automation.net possono essere sostituiti con l'ID area di lavoro specifico. L'ID area di lavoro è specifico dell'ambiente e dell'area di lavoro ed è disponibile nella sezione Onboarding del tenant all'interno del Microsoft Defender Security Center portale.

L'endpoint URL *.blob.core.windows.net può essere sostituito con gli URL visualizzati nella sezione "Regola firewall: *.blob.core.windows.net" dei risultati del test. 

> [!NOTE]
> Nel caso dell'onboarding tramite Azure Defender, possono essere usate più aree di lavoro. Sarà necessario eseguire la procedura di TestCloudConnection.exe sopra descritta in un computer onboarded da ogni area di lavoro (per determinare se sono presenti modifiche agli URL *.blob.core.windows.net tra le aree di lavoro).

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>Verificare la connettività client a Microsoft Defender per gli URL del servizio endpoint

Verificare che la configurazione del proxy sia stata completata correttamente, che WinHTTP possa individuare e comunicare attraverso il server proxy nell’ambiente e che il server proxy consenta il traffico agli URL del servizio Defender per Endpoint.

1. Scarica lo [MDATP Analizzatore client nel](https://aka.ms/mdatpanalyzer) PC in cui è in esecuzione il sensore Defender for Endpoint.

2. Estrarre il contenuto di MDATPClientAnalyzer.zip nel dispositivo.

3. Aprire un prompt dei comandi con privilegi elevati:

   1. Passare a **Start** e digitare **cmd**.

   1.  Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

4. Immettere il comando indicato di seguito e premere **INVIO**:

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    Sostituire *HardDrivePath* con il percorso in cui è stato scaricato lo strumento MDATPClientAnalyzer, ad esempio:

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. Estrarre il *MDATPClientAnalyzerResult.zip* creato dallo strumento nella cartella utilizzata in *HardDrivePath.*

6. Aprire *MDATPClientAnalyzerResult.txt* e verificare di avere eseguito la procedura di configurazione del proxy per abilitare l'individuazione del server e l'accesso agli URL di servizio.

   Lo strumento controlla la connettività degli URL del servizio Defender per Endpoint con cui è configurato per interagire. Quindi immette i risultati per ogni URL che potrebbe essere potenzialmente utilizzato per comunicare con il servizio Defender per l'endpoint nel file *MDATPClientAnalyzerResult.txt*. Ad esempio:

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

Se almeno una delle opzioni di connettività restituisce uno stato (200), il client Defender per Endpoint può comunicare correttamente con l'URL testato usando questo metodo di connettività.

Tuttavia, se i risultati della verifica della connettività indicano un errore, viene visualizzato un errore HTTP (vedere codici di stato HTTP). Puoi quindi usare gli URL nella tabella illustrata in Abilitare l'accesso a Defender per gli URL del servizio [endpoint nel server proxy.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) Gli URL che userai dipendono dall'area selezionata durante la procedura di onboarding.

> [!NOTE]
>  Strumento di analisi della connettività non è compatibile con la regola ASR [Bloccare le creazioni di processi provenienti dai comandi PSExec e WMI](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules). È necessario disabilitare temporaneamente questa regola per eseguire lo strumento di connettività.


> [!NOTE]
> Quando telemetryProxyServer è impostato, nel Registro di sistema o tramite Criteri di gruppo, Defender for Endpoint esegue il fall back to direct se non è in grado di accedere al proxy definito.

## <a name="related-topics"></a>Argomenti correlati

- [Aggiungere di dispositivi Windows 10](configure-endpoints.md)
- [Risolvere i problemi di onboarding di Microsoft Defender per endpoint](troubleshoot-onboarding.md)
