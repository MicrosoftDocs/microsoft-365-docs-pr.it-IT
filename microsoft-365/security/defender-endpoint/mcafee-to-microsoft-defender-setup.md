---
title: Da McAfee a Microsoft Defender for Endpoint - Installazione
description: Questa è la fase 2 del programma di installazione per la migrazione da McAfee a Microsoft Defender per Endpoint.
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 0145f48a5bcf53cd06c70b18e9c48aa6e5e5c06c
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327587"
---
# <a name="migrate-from-mcafee---phase-2-set-up-microsoft-defender-for-endpoint"></a>Eseguire la migrazione da McAfee - Fase 2: configurare Microsoft Defender per Endpoint

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: preparazione](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[Fase 1: preparazione](mcafee-to-microsoft-defender-prepare.md) |![Fase 2: configurazione](images/phase-diagrams/setup.png)<br/>Fase 2: configurazione |[![Fase 3: onboarding](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[Fase 3: onboarding](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
||*Sei qui!* | |

**Benvenuti nella fase di installazione della [migrazione da McAfee Endpoint Security (McAfee) a Microsoft Defender for Endpoint.](mcafee-to-microsoft-defender-migration.md#the-migration-process)** Questa fase include i passaggi seguenti:
1. [Abilita Antivirus Microsoft Defender e verifica che sia in modalità passiva.](#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)
2. [Ottenere gli aggiornamenti per Antivirus Microsoft Defender](#get-updates-for-microsoft-defender-antivirus).
3. [Aggiungi Microsoft Defender per Endpoint all'elenco di esclusione per McAfee.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee)
4. [Aggiungere McAfee all'elenco di esclusione per Antivirus Microsoft Defender](#add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus).
5. [Aggiungi McAfee all'elenco di esclusione per Microsoft Defender for Endpoint.](#add-mcafee-to-the-exclusion-list-for-microsoft-defender-for-endpoint)
6. [Configurare i gruppi di dispositivi, le raccolte di dispositivi e le unità organizzative.](#set-up-your-device-groups-device-collections-and-organizational-units)
7. [Configurare i criteri antimalware e la protezione in tempo reale.](#configure-antimalware-policies-and-real-time-protection)

## <a name="enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode"></a>Abilita Antivirus Microsoft Defender e verifica che sia in modalità passiva

In alcune versioni di Windows, ad esempio Windows Server, è possibile che Antivirus Microsoft Defender sia stato disinstallato o disabilitato al momento dell'installazione della soluzione McAfee. Ciò è dovuto Antivirus Microsoft Defender non entra in modalità passiva o disabilitata quando si installa un prodotto antivirus di terze parti, ad esempio McAfee. Per ulteriori informazioni, vedere Antivirus Microsoft Defender [compatibilità.](microsoft-defender-antivirus-compatibility.md)

Questo passaggio del processo di migrazione include le attività seguenti:
- [Impostazione di DisableAntiSpyware su false in Windows Server](#set-disableantispyware-to-false-on-windows-server)
- [Reinstallazione Antivirus Microsoft Defender in Windows Server](#reinstall-microsoft-defender-antivirus-on-windows-server);
- [Impostazione Antivirus Microsoft Defender modalità passiva in Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)
- [Abilitazione Antivirus Microsoft Defender nei dispositivi client Windows;](#enable-microsoft-defender-antivirus-on-your-windows-client-devices) e
- [Verifica che la Antivirus Microsoft Defender sia impostata sulla modalità passiva](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode).  

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Impostare DisableAntiSpyware su false Windows Server

La chiave del Registro di sistema [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) è stata utilizzata in passato per disabilitare Antivirus Microsoft Defender e distribuire un altro prodotto antivirus, ad esempio McAfee. In generale, non dovresti avere questa chiave del Registro di sistema nei dispositivi Windows e negli endpoint; Tuttavia, se è stata `DisableAntiSpyware` configurata, ecco come impostarne il valore su false:

1. Nel dispositivo Windows Server aprire l'editor del Registro di sistema.

2. Passare a `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.

3. In tale cartella cerca una voce DWORD denominata **DisableAntiSpyware.**

   - Se la voce non viene visualizzata, è tutto impostato.

   - Se viene visualizzato **DisableAntiSpyware,** andare al passaggio 4.

4. Fare clic con il pulsante destro del mouse sul valore DWORD DisableAntiSpyware e quindi scegliere **Modifica**.

5. Impostare il valore su `0` . In questo modo il valore della chiave del Registro di sistema viene impostato su *false.*

> [!TIP]
> Per ulteriori informazioni su questa chiave del Registro di sistema, [vedere DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Reinstallare Antivirus Microsoft Defender in Windows Server

> [!NOTE]
> La procedura seguente si applica solo agli endpoint o ai dispositivi che eseguono le versioni seguenti di Windows:
> - Windows Server 2019
> - Windows Server, versione 1803 (modalità solo core)
> - Windows Server 2016

1. In quanto amministratore locale nell'endpoint o nel dispositivo, apri Windows PowerShell.

2. Eseguire i cmdlet di PowerShell seguenti: <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>

> [!NOTE]
> Quando si usa il comando Gestione e manutenzione immagini distribuzione all'interno di una sequenza di attività che esegue PS, è necessario cmd.exe percorso seguente.
> Esempio:<br/>
> `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
> `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Per verificare Antivirus Microsoft Defender è in esecuzione, utilizzare il cmdlet PowerShell seguente: <br/>
   
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Si sta usando Windows Server 2016?

Se si usa Windows Server 2016 e si verificano problemi nell'abilitazione Antivirus Microsoft Defender, utilizzare il cmdlet PowerShell seguente:

`mpcmdrun -wdenable`

> [!TIP]
> Serve ulteriore assistenza? Vedere [Antivirus Microsoft Defender su Windows Server 2016 e 2019](microsoft-defender-antivirus-on-windows-server.md).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Impostare Antivirus Microsoft Defender modalità passiva in Windows Server

Poiché l'organizzazione usa ancora McAfee, è necessario impostare Antivirus Microsoft Defender modalità passiva. In questo modo, McAfee e Antivirus Microsoft Defender possono essere eseguiti affiancati fino al termine dell'onboarding in Microsoft Defender per Endpoint.

1. Aprire l'editor del Registro di sistema e quindi passare a <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Modificare (o creare) una voce DWORD denominata **ForcePassiveMode** e specificare le impostazioni seguenti:
   
   - Imposta il valore DWORD su **1.**
   
   - In **Base** selezionare **Esadecimale.**

> [!NOTE]
> È possibile utilizzare altri metodi per impostare la chiave del Registro di sistema, ad esempio:
>- [Preferenza di Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Un pacchetto in Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="enable-microsoft-defender-antivirus-on-your-windows-client-devices"></a>Abilitare Antivirus Microsoft Defender nei dispositivi Windows client

Poiché l'organizzazione usa McAfee come soluzione antivirus principale, è molto probabile che Antivirus Microsoft Defender sia disabilitata nei dispositivi Windows'organizzazione. Questo passaggio del processo di migrazione prevede l'abilitazione Antivirus Microsoft Defender. 

Per abilitare Antivirus Microsoft Defender, è consigliabile usare Intune. Tuttavia, è possibile utilizzare uno qualsiasi dei metodi elencati nella tabella seguente:

|Metodo  |Soluzione  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <p>**NOTA:** Intune è ora Microsoft Endpoint Manager. |1. Accedere [all'Microsoft Endpoint Manager di amministrazione](https://go.microsoft.com/fwlink/?linkid=2109431) ed eseguire l'accesso.<p>2. Selezionare **Profili** di configurazione dei dispositivi e quindi selezionare il tipo  >  di profilo che si desidera configurare. <br/>Se non hai ancora  creato un tipo di profilo Restrizioni dispositivo o se vuoi crearne uno nuovo, vedi Configurare le impostazioni di restrizione dei dispositivi [in Microsoft Intune](/intune/device-restrictions-configure).<p>3. Selezionare **Proprietà** e quindi Impostazioni **di configurazione: Modifica**.<p>4. Espandere **Antivirus Microsoft Defender**. <p>5. Abilitare **la protezione consegnata dal cloud.**<p>6. Nell'elenco a discesa **Chiedi conferma agli utenti prima** dell'invio di esempio seleziona Invia **automaticamente tutti i campioni.**<p>7. Nell'elenco a discesa **Rileva applicazioni potenzialmente indesiderate** selezionare **Abilita** o **Controlla.**<p>8. Selezionare **Rivedi e salva** e quindi scegliere **Salva.**<p>Per ulteriori informazioni sui profili dei dispositivi Intune, inclusa la procedura per creare e configurare le impostazioni, vedere [What are Microsoft Intune device profiles?](/intune/device-profiles).|
|Pannello di controllo in Windows     |Seguire le indicazioni qui: [Attivare Antivirus Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows). <p>**NOTA:** potrebbe essere visualizzato *Windows Defender Antivirus* invece *di Antivirus Microsoft Defender* in alcune versioni di Windows.        |
|[Gestion avancée des stratégies de groupe](/microsoft-desktop-optimization-pack/agpm/) <br/>oppure<br/>[Console Gestione Criteri di gruppo](use-group-policy-microsoft-defender-antivirus.md)  |1. Passare a `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <p>2. Cercare un criterio denominato **Disattiva Antivirus Microsoft Defender**.<br/> <br/>3. Scegliere **Modifica impostazione dei criteri** e assicurarsi che il criterio sia disabilitato. In questo modo Antivirus Microsoft Defender. <p>**NOTA:** potrebbe essere visualizzato *Windows Defender Antivirus* invece *di Antivirus Microsoft Defender* in alcune versioni di Windows. |

### <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Verificare che Antivirus Microsoft Defender sia in modalità passiva

Microsoft Defender Antivirus può essere eseguito insieme a McAfee se si imposta Microsoft Defender Antivirus sulla modalità passiva. È possibile utilizzare il prompt dei comandi o PowerShell per eseguire questa attività, come descritto nella tabella seguente:

|Metodo  |Soluzione  |
|---------|---------|
|Prompt dei comandi     |1. In un dispositivo Windows, apri prompt dei comandi come amministratore. <p>2. Digitare `sc query windefend` e quindi premere INVIO.<p>3. Esaminare i risultati per verificare che Microsoft Defender Antivirus sia in esecuzione in modalità passiva.         |
|PowerShell     |1. In un dispositivo Windows, apri Windows PowerShell amministratore.<p>2. Eseguire il cmdlet [Get-MpComputerStatus.](/powershell/module/defender/Get-MpComputerStatus) <p>3. Nell'elenco dei risultati, cercare **AMRunningMode: Modalità** passiva o **AMRunningMode: modalità passiva SxS.**|

> [!NOTE]
> Potrebbe essere visualizzato *Windows Defender Antivirus* anziché Microsoft *Defender Antivirus* in alcune versioni di Windows.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Ottenere gli aggiornamenti per Microsoft Defender Antivirus

Mantenere Microsoft Defender Antivirus aggiornato è fondamentale per garantire ai dispositivi la tecnologia e le funzionalità più recenti necessarie per la protezione da nuove tecniche di malware e attacchi, anche se Microsoft Defender Antivirus è in esecuzione in [modalità passiva.](microsoft-defender-antivirus-compatibility.md)

Esistono due tipi di aggiornamenti correlati al mantenimento di Microsoft Defender Antivirus aggiornato:
- Aggiornamenti delle funzionalità di intelligence per la sicurezza
- Aggiornamenti dei prodotti

Per ottenere gli aggiornamenti, seguire le indicazioni in Gestire gli aggiornamenti di [Microsoft Defender Antivirus e applicare le linee di base.](manage-updates-baselines-microsoft-defender-antivirus.md)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee"></a>Aggiungere Microsoft Defender for Endpoint all'elenco di esclusione per McAfee

Questo passaggio del processo di configurazione prevede l'aggiunta di Microsoft Defender for Endpoint all'elenco di esclusione per McAfee e per qualsiasi altro prodotto di sicurezza utilizzato dall'organizzazione. 

> [!TIP]
> Per informazioni sulla configurazione delle esclusioni, fare riferimento alla documentazione di McAfee, ad esempio il seguente articolo: [McAfee Endpoint Security 10.5.0 - Threat Prevention Module Product Guide (McAfee ePolicy Orchestrator) - Windows: Configuring exclusions](https://docs.mcafee.com/bundle/endpoint-security-10.5.0-threat-prevention-product-guide-epolicy-orchestrator-windows/page/GUID-71C5FB4B-A143-43E6-8BF0-8B2C16ABE6DA.html).

Le esclusioni specifiche da configurare dipendono dalla versione di Windows in esecuzione degli endpoint o dei dispositivi e sono elencate nella tabella seguente:

|Sistema operativo |Esclusioni |
|--|--|
|- Windows 10 versione [1803](/windows/release-health/status-windows-10-1803) o successiva (Vedi informazioni sulla versione [di Windows 10](/windows/release-health/release-information))<br/>- Windows 10 versione 1703 o [1709](/windows/release-health/status-windows-10-1709) con [KB4493441](https://support.microsoft.com/help/4493441) installato <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, versione 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
|- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**NOTA:** dove i file temporanei dell'host di monitoraggio 6\45 possono essere sottocartelle numerate diverse.<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Aggiungere McAfee all'elenco di esclusione per Microsoft Defender Antivirus

Durante questo passaggio del processo di installazione aggiungi McAfee e le altre soluzioni di sicurezza all'elenco di esclusione di Microsoft Defender Antivirus. 

Quando aggiungi [esclusioni alle analisi di Microsoft Defender Antivirus,](configure-exclusions-microsoft-defender-antivirus.md)devi aggiungere le esclusioni di percorso ed elaborazione. Tenere presenti i punti seguenti:
- Le esclusioni di percorso escludono file specifici e qualsiasi file a cui accedono.
- Le esclusioni di processo escludono qualsiasi cosa tocca un processo, ma non escludono il processo stesso.
- Se si elenca ogni eseguibile (.exe) sia come esclusione di percorso che come esclusione di processo, il processo e tutto ciò che tocca vengono esclusi.
- Elencare le esclusioni di processo usando il percorso completo e non solo in base al nome. Il metodo solo nome è meno sicuro.

Puoi scegliere tra diversi metodi per aggiungere le esclusioni a Microsoft Defender Antivirus, come elencato nella tabella seguente:

|Metodo | Soluzione|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <p>**NOTA:** Intune è ora Microsoft Endpoint Manager. |1. Accedere all'interfaccia di amministrazione di [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) ed eseguire l'accesso.<p>2. Selezionare **Profili** di configurazione dei dispositivi e quindi  >  selezionare il profilo che si desidera configurare.<p>3. In **Gestisci** selezionare **Proprietà.** <p>4. Selezionare **Impostazioni di configurazione: Modifica**.<p>5. Espandere **Microsoft Defender Antivirus** e quindi Microsoft Defender Antivirus **Exclusions**.<p>6. Specificare i file e le cartelle, le estensioni e i processi da escludere dalle analisi di Microsoft Defender Antivirus. Per informazioni di riferimento, vedere [Esclusioni di Microsoft Defender Antivirus.](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<p>7. Scegliere **Rivedi e salva** e quindi **Salva.**  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) |1. Utilizzando la [console di Configuration Manager,](/mem/configmgr/core/servers/manage/admin-console)passare a **Assets and Compliance** Endpoint  >  **Protection**  >  **Antimalware Policies** e quindi selezionare il criterio che si desidera modificare. <p>2. Specificare le impostazioni di esclusione per file e cartelle, estensioni e processi da escludere dalle analisi di Microsoft Defender Antivirus. |
|[Oggetto Criteri di gruppo](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Nel computer di gestione di Criteri di gruppo, aprire la [Console](https://technet.microsoft.com/library/cc731212.aspx)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.<p>2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e fare clic su **Modelli amministrativi.**<p>3. Espandere l'albero fino ai componenti **di Windows > Microsoft Defender Antivirus > Esclusioni**.<br/>**NOTA:** in alcune versioni *di Windows potrebbe Windows Defender antivirus* anziché Microsoft Defender *Antivirus.*<p>4. Fare doppio clic **sull'impostazione Esclusioni percorso** e aggiungere le esclusioni.<br/>- Impostare l'opzione su **Abilitato**.<br/>- Nella sezione **Opzioni** fare clic su **Mostra...**.<br/>- Specificare ogni cartella nella propria riga nella **colonna Nome** valore.<br/>- Se si specifica un file, assicurarsi di immettere un percorso completo del file, inclusi la lettera di unità, il percorso della cartella, il nome del file e l'estensione. Immettere **0** nella **colonna** Valore.<p>5. Fare clic **su OK.**<p>6. Fare doppio clic **sull'impostazione Esclusioni estensioni** e aggiungere le esclusioni.<br/>- Impostare l'opzione su **Abilitato**.<br/>- Nella sezione **Opzioni** fare clic su **Mostra...**.<br/>- Immettere ogni estensione di file nella propria riga nella **colonna Nome** valore.  Immettere **0** nella **colonna** Valore.<p>7. Fare clic **su OK.** |
|Oggetto Criteri di gruppo locali |1. Nell'endpoint o nel dispositivo aprire l'Editor Criteri di gruppo locali. <p>2. Passare a **Configurazione computer** Modelli amministrativi  >  **Componenti** di  >  **Windows** Componenti di Microsoft  >  **Defender Antivirus**  >  **Esclusioni**. <br/>**NOTA:** in alcune versioni *di Windows potrebbe Windows Defender antivirus* anziché Microsoft Defender *Antivirus.*<p>3. Specificare il percorso e le esclusioni di processo. |
|Chiave del Registro di sistema |1. Esportare la seguente chiave del Registro di sistema: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<p>2. Importare la chiave del Registro di sistema. Ecco due esempi:<br/>- Percorso locale: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Condivisione di rete: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-mcafee-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>Aggiungere McAfee all'elenco di esclusione per Microsoft Defender for Endpoint

> [!IMPORTANT]
> In generale, non dovresti aggiungere esclusioni per Defender per Endpoint, soprattutto se hai già definito le esclusioni per Microsoft Defender Antivirus. Tuttavia, se si verificano problemi in cui Microsoft Defender Antivirus non rimarrà in modalità passiva, eseguire l'attività seguente. In caso contrario, ignora questa sezione e passa a Configurare i gruppi di dispositivi, le [raccolte di dispositivi e le unità organizzative.](#set-up-your-device-groups-device-collections-and-organizational-units)

Per aggiungere esclusioni a Microsoft Defender for Endpoint, devi creare [indicatori](indicator-file.md).

1. Vai a Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e accedi.

2. Nel riquadro di spostamento scegliere **Impostazioni**  >  **Regole**  >  **Indicatori**.

3.  Nella scheda **Hash file** scegliere **Aggiungi indicatore.**

3. Nella scheda **Indicatore** specificare le impostazioni seguenti:
   - Hash del file (serve aiuto? Vedere [Trovare un hash di file tramite CMPivot](#find-a-file-hash-using-cmpivot) in questo articolo.
   - In **Scadenza il (UTC)** scegliere **Mai.**

4. Nella scheda **Azione** specificare le impostazioni seguenti:
   - **Azione di risposta**: **Consenti**
   - Titolo e descrizione

5. Nella scheda **Ambito,** in **Gruppi di dispositivi,** selezionare Tutti i **dispositivi nell'ambito** o **Seleziona dall'elenco**.

6. Nella scheda **Riepilogo** esaminare le impostazioni e quindi fare clic su **Salva.**

### <a name="find-a-file-hash-using-cmpivot"></a>Trovare un hash di file tramite CMPivot

CMPivot è un'utilità nella console per Configuration Manager. CMPivot consente di accedere allo stato in tempo reale dei dispositivi nell'ambiente. Esegue immediatamente una query su tutti i dispositivi attualmente connessi nella raccolta di destinazione e restituisce i risultati. Per ulteriori informazioni, vedere [Panoramica di CMPivot.](/mem/configmgr/core/servers/manage/cmpivot-overview)

Per usare CMPivot per ottenere l'hash del file, attenersi alla seguente procedura:

1. Esaminare i [prerequisiti](/mem/configmgr/core/servers/manage/cmpivot#prerequisites).

2. [Avviare CMPivot.](/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot) 

3. Connessione a Configuration Manager ( `SCCM_ServerName.DomainName.com` ).

4. Selezionare la **scheda Query.**
 
5. **Nell'elenco Raccolta dispositivi** scegliere Tutti i sistemi **(impostazione predefinita).**

6. Nella casella della query digitare la query seguente:<br/>

```kusto
File(c:\\windows\\notepad.exe)
| project Hash
```
> [!NOTE]
> Nella query precedente, sostituire *notepad.exe* con il nome del processo del prodotto di sicurezza di terze parti. 

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Configurare i gruppi di dispositivi, le raccolte di dispositivi e le unità organizzative

| Tipo di raccolta | Soluzione |
|--|--|
|[I gruppi di](machine-groups.md) dispositivi (in precedenza denominati gruppi di computer) consentono al team delle operazioni di sicurezza di configurare funzionalità di sicurezza, ad esempio analisi e correzione automatizzate.<p> I gruppi di dispositivi sono utili anche per assegnare l'accesso a tali dispositivi in modo che il team delle operazioni di sicurezza possa eseguire azioni correttive se necessario. <p>I gruppi di dispositivi vengono creati nella Microsoft Defender Security Center. |1. Passare al Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<p>2. Nel riquadro di spostamento a sinistra scegliere Impostazioni  >  **autorizzazioni**  >  **Gruppi di dispositivi**.  <p>3. Scegliere **+ Aggiungi gruppo di dispositivi.**<p>4. Specificare un nome e una descrizione per il gruppo di dispositivi.<p>5. **Nell'elenco Livello di automazione** selezionare un'opzione. È consigliabile **completare la correzione automatica delle minacce.** Per ulteriori informazioni sui vari livelli di automazione, vedere [Come vengono corretti i rischi.](automated-investigations.md#how-threats-are-remediated)<p>6. Specificare le condizioni per una regola di corrispondenza per determinare quali dispositivi appartengono al gruppo di dispositivi. Ad esempio, puoi scegliere un dominio, le versioni del sistema operativo o persino usare i [tag del dispositivo.](machine-tags.md) <p>7. Nella **scheda Accesso** utente specificare i ruoli che devono avere accesso ai dispositivi inclusi nel gruppo di dispositivi. <p>8. Scegliere **Fine.** |
|[Le raccolte di](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) dispositivi consentono al team delle operazioni di sicurezza di gestire le applicazioni, distribuire le impostazioni di conformità o installare aggiornamenti software nei dispositivi dell'organizzazione. <p>Le raccolte di dispositivi vengono create tramite [Configuration Manager.](/mem/configmgr/) |Seguire i passaggi descritti in [Creare una raccolta](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
|[Le unità organizzative](/azure/active-directory-domain-services/create-ou) consentono di raggruppare logicamente oggetti quali account utente, account di servizio o account computer. È quindi possibile assegnare amministratori a unità organizzative specifiche e applicare criteri di gruppo per applicare impostazioni di configurazione mirate.<p> Le unità organizzative sono definite in [Azure Active Directory Domain Services](/azure/active-directory-domain-services). | Seguire i passaggi descritti in [Create an Organizational Unit in an Azure Active Directory Domain Services managed domain services](/azure/active-directory-domain-services/create-ou). |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Configurare criteri antimalware e protezione in tempo reale

Usando Configuration Manager e le raccolte di dispositivi, configura i criteri antimalware.

- Vedere [Creare e distribuire criteri antimalware per Endpoint Protection in Configuration Manager.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)

- Durante la creazione e la configurazione dei criteri [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) antimalware, verificare le impostazioni di protezione in tempo reale e abilitare [il blocco al primo sguardo.](configure-block-at-first-sight-microsoft-defender-antivirus.md)

> [!TIP]
> Puoi distribuire i criteri prima dell'onboarded dei dispositivi dell'organizzazione.

## <a name="next-step"></a>Passaggio successivo

**Congratulazioni**! Hai completato la fase di installazione della [migrazione da McAfee a Microsoft Defender for Endpoint!](mcafee-to-microsoft-defender-migration.md#the-migration-process)

- [Passare alla fase 3: eseguire l'onboard in Microsoft Defender per Endpoint](mcafee-to-microsoft-defender-onboard.md)
