---
title: Da Symantec a Microsoft Defender per endpoint - Fase 2, configurazione
description: Questa è la fase 2 del programma di installazione della migrazione da Symantec a Microsoft Defender per Endpoint
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
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 32ed277c87f5cca1a286cc24549dc331774cf03b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245733"
---
# <a name="migrate-from-symantec---phase-2-set-up-microsoft-defender-for-endpoint"></a>Eseguire la migrazione da Symantec - Fase 2: configurare Microsoft Defender per Endpoint

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: preparazione](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Fase 1: preparazione](symantec-to-microsoft-defender-atp-prepare.md) |![Fase 2: configurazione](images/phase-diagrams/setup.png)<br/>Fase 2: configurazione |[![Fase 3: onboarding](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fase 3: onboarding](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
||*Sei qui!* | |


**Benvenuti nella fase di installazione della [migrazione da Symantec a Microsoft Defender per Endpoint.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** Questa fase include i passaggi seguenti:
1. [Abilitare o reinstallare Antivirus Microsoft Defender (per determinate versioni di Windows)](#enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows).
2. [Abilita Antivirus Microsoft Defender](#enable-microsoft-defender-antivirus).
3. [Ottenere gli aggiornamenti per Antivirus Microsoft Defender](#get-updates-for-microsoft-defender-antivirus).
4. [Aggiungi Microsoft Defender per Endpoint all'elenco di esclusione per Symantec.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec)
5. [Aggiungere Symantec all'elenco di esclusione per Antivirus Microsoft Defender](#add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus).
6. [Aggiungi Symantec all'elenco di esclusione per Microsoft Defender for Endpoint.](#add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint)
7. [Configurare i gruppi di dispositivi, le raccolte di dispositivi e le unità organizzative.](#set-up-your-device-groups-device-collections-and-organizational-units)
8. [Configurare i criteri antimalware e la protezione in tempo reale.](#configure-antimalware-policies-and-real-time-protection)

## <a name="enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows"></a>Abilitare o reinstallare Antivirus Microsoft Defender (per determinate versioni di Windows)

> [!TIP]
> Se si esegue Windows 10, non è necessario eseguire questa attività. Passare a **[Abilita Antivirus Microsoft Defender](#enable-microsoft-defender-antivirus)**.

In alcune versioni di Windows, Antivirus Microsoft Defender potrebbe essere stato disinstallato o disabilitato. Questo perché Antivirus Microsoft Defender non entra in modalità passiva o disabilitata quando si installa un prodotto antivirus di terze parti, ad esempio Symantec. Per ulteriori informazioni, vedere [Antivirus Microsoft Defender compatibilità.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility) 

Ora che stai passando da Symantec a Microsoft Defender for Endpoint, dovrai abilitare o reinstallare Antivirus Microsoft Defender e impostarlo sulla modalità passiva. 

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Reinstallare Antivirus Microsoft Defender in Windows Server

> [!NOTE]
> La procedura seguente si applica solo agli endpoint o ai dispositivi che eseguono le versioni seguenti di Windows:
> - Windows Server 2019
> - Windows Server, versione 1803 (modalità solo core)
> - Windows Server 2016
> 
> Antivirus Microsoft Defender è incorporato in Windows 10, ma potrebbe essere disabilitato. In questo caso, passare [a Abilita Antivirus Microsoft Defender](#enable-microsoft-defender-antivirus).

1. In quanto amministratore locale nell'endpoint o nel dispositivo, apri Windows PowerShell.

1. Eseguire i cmdlet di PowerShell seguenti:<br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`

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
> Ulteriore assistenza Vedere [Antivirus Microsoft Defender su Windows Server 2016 e 2019](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Impostare Antivirus Microsoft Defender modalità passiva in Windows Server

Poiché l'organizzazione usa ancora Symantec, è necessario impostare Antivirus Microsoft Defender modalità passiva. In questo modo, Symantec e Antivirus Microsoft Defender possono essere eseguiti affiancati fino al termine dell'onboarding in Microsoft Defender for Endpoint.

1. Aprire l'editor del Registro di sistema e quindi passare a <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Modificare (o creare) una voce DWORD denominata **ForceDefenderPassiveMode** e specificare le impostazioni seguenti:
   - Imposta il valore DWORD su **1.**
   - In **Base** selezionare **Esadecimale.**

> [!NOTE]
> È possibile utilizzare altri metodi per impostare la chiave del Registro di sistema, ad esempio:
>- [Preferenza di Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Strumento Oggetto Criteri di gruppo locale](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Un pacchetto in Configuration Manager](/mem/configmgr/apps/deploy-use/packages-and-programs)

## <a name="enable-microsoft-defender-antivirus"></a>Abilita Antivirus Microsoft Defender

Poiché l'organizzazione ha utilizzato Symantec come soluzione antivirus principale, Antivirus Microsoft Defender è probabilmente disabilitata nei dispositivi Windows'organizzazione. Questo passaggio del processo di migrazione prevede l'abilitazione Antivirus Microsoft Defender. 

Per abilitare Antivirus Microsoft Defender, è consigliabile usare Intune. Tuttavia, è possibile utilizzare uno qualsiasi dei metodi elencati nella tabella seguente:

|Metodo  |Soluzione  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**NOTA:** Intune è ora Microsoft Endpoint Manager. |1. Accedere [all'Microsoft Endpoint Manager di amministrazione](https://go.microsoft.com/fwlink/?linkid=2109431) ed eseguire l'accesso.<br/><br/>2. Selezionare **Profili** di configurazione dei dispositivi e quindi selezionare il tipo  >  di profilo che si desidera configurare. Se non hai ancora  creato un tipo di profilo Restrizioni dispositivo o se vuoi crearne uno nuovo, vedi Configurare le impostazioni di restrizione dei dispositivi [in Microsoft Intune](/intune/device-restrictions-configure).<br/><br/>3. Selezionare **Proprietà** e quindi Impostazioni **di configurazione: Modifica**.<br/><br/>4. Espandere **Antivirus Microsoft Defender**. <br/><br/>5. Abilitare **la protezione consegnata dal cloud.**<br/><br/>6. Nell'elenco a discesa **Chiedi conferma agli utenti prima** dell'invio di esempio seleziona Invia **automaticamente tutti i campioni.**<br/><br/>7. Nell'elenco a discesa **Rileva applicazioni potenzialmente indesiderate** selezionare **Abilita** o **Controlla.**<br/><br/>8. Selezionare **Rivedi e salva** e quindi scegliere **Salva.**<br/>Per ulteriori informazioni sui profili dei dispositivi Intune, inclusa la procedura per creare e configurare le impostazioni, vedere [What are Microsoft Intune device profiles?](/intune/device-profiles).|
|Pannello di controllo in Windows     |Seguire le indicazioni qui: [Attivare Antivirus Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows). <br/>**NOTA:** potrebbe essere visualizzato *Windows Defender Antivirus* invece *di Antivirus Microsoft Defender* in alcune versioni di Windows.        |
|[Gestion avancée des stratégies de groupe](/microsoft-desktop-optimization-pack/agpm/) <br/>oppure<br/>[Console Gestione Criteri di gruppo](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. Passare a `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <br/><br/>2. Cercare un criterio denominato **Disattiva Antivirus Microsoft Defender**.<br/><br/>3. Scegliere **Modifica impostazione dei criteri** e assicurarsi che il criterio sia disabilitato. In questo modo Antivirus Microsoft Defender. <br/><br/>**NOTA:** potrebbe essere visualizzato *Windows Defender Antivirus* invece *di Antivirus Microsoft Defender* in alcune versioni di Windows. |

### <a name="verify-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Verificare che Antivirus Microsoft Defender sia in modalità passiva

Antivirus Microsoft Defender possibile eseguire insieme a Symantec se si imposta Antivirus Microsoft Defender modalità passiva. È possibile utilizzare il prompt dei comandi o PowerShell per eseguire questa attività, come descritto nella tabella seguente:

|Metodo  |Soluzione  |
|---------|---------|
|Prompt dei comandi     |1. In un dispositivo Windows, aprire prompt dei comandi come amministratore. <br/><br/>2. Digitare `sc query windefend` e quindi premere INVIO.<br/><br/>3. Esaminare i risultati per verificare che Antivirus Microsoft Defender in esecuzione in modalità passiva.         |
|PowerShell     |1. In un dispositivo Windows, aprire Windows PowerShell come amministratore.<br/><br/>2. Eseguire il cmdlet [Get-MpComputerStatus.](/powershell/module/defender/Get-MpComputerStatus)<br/> <br/>3. Nell'elenco dei risultati, cercare **AMRunningMode: Modalità** passiva o **AMRunningMode: modalità passiva SxS.**|

> [!NOTE]
> Potrebbe essere visualizzato *Windows Defender Antivirus* invece *di Antivirus Microsoft Defender* in alcune versioni di Windows.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Ottenere gli aggiornamenti per Antivirus Microsoft Defender

Mantenere Antivirus Microsoft Defender aggiornato è fondamentale per garantire ai dispositivi la tecnologia e le funzionalità più recenti necessarie per la protezione da nuove tecniche di malware e attacchi, anche se Antivirus Microsoft Defender è in esecuzione in modalità [passiva.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Esistono due tipi di aggiornamenti correlati alla Antivirus Microsoft Defender aggiornati:
- Aggiornamenti delle funzionalità di intelligence per la sicurezza
- Aggiornamenti dei prodotti

Per ottenere gli aggiornamenti, seguire le indicazioni in Gestire Antivirus Microsoft Defender [aggiornamenti e applicare le linee di base.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec"></a>Aggiungere Microsoft Defender for Endpoint all'elenco di esclusione per Symantec

Questo passaggio del processo di configurazione prevede l'aggiunta di Microsoft Defender per Endpoint all'elenco di esclusione per Symantec e qualsiasi altro prodotto di sicurezza utilizzato dall'organizzazione. Le esclusioni specifiche da configurare dipendono dalla versione di Windows degli endpoint o dei dispositivi in esecuzione e sono elencate nella tabella seguente:

|Sistema operativo |Esclusioni |
|--|--|
|- Windows 10 versione [1803](/windows/release-health/status-windows-10-1803) o successiva (vedere Windows 10 [sulla versione](/windows/release-health/release-information))<br/>- Windows 10 versione 1703 o 1709 con [KB4493441](https://support.microsoft.com/help/4493441) installato <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, versione 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/><br/>  |
|- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/><br/>- [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**NOTA:** dove i file temporanei dell'host di monitoraggio 6\45 possono essere sottocartelle numerate diverse.<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Aggiungere Symantec all'elenco di esclusione per Antivirus Microsoft Defender

Durante questo passaggio del processo di installazione, si aggiungono Symantec e le altre soluzioni di sicurezza all'Antivirus Microsoft Defender di esclusione. 

> [!NOTE]
> Per avere un'idea dei processi e dei servizi da escludere, vedi Processi e servizi di Broadcom usati da [Endpoint Protection 14](https://knowledge.broadcom.com/external/article/170706/processes-and-services-used-by-endpoint.html).

Quando si [aggiungono esclusioni alle Antivirus Microsoft Defender,](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)è consigliabile aggiungere le esclusioni di percorso ed elaborazione. Tenere presenti i punti seguenti:
- Le esclusioni di percorso escludono file specifici e qualsiasi file a cui accedono.
- Le esclusioni di processo escludono qualsiasi cosa tocca un processo, ma non escludono il processo stesso.
- Se si elenca ogni eseguibile (.exe) sia come esclusione di percorso che come esclusione di processo, il processo e tutto ciò che tocca vengono esclusi.
- Elencare le esclusioni di processo usando il percorso completo e non solo in base al nome. Il metodo solo nome è meno sicuro.

Puoi scegliere tra diversi metodi per aggiungere le esclusioni Antivirus Microsoft Defender, come elencato nella tabella seguente:

|Metodo | Soluzione|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**NOTA:** Intune è ora Microsoft Endpoint Manager. |1. Accedere [all'Microsoft Endpoint Manager di amministrazione](https://go.microsoft.com/fwlink/?linkid=2109431) ed eseguire l'accesso.<br/><br/>2. Selezionare **Profili** di configurazione dei dispositivi e quindi  >  selezionare il profilo che si desidera configurare.<br/><br/>3. In **Gestisci** selezionare **Proprietà.** <br/><br/>4. Selezionare **Impostazioni di configurazione: Modifica**.<br/><br/>5. Espandere **Antivirus Microsoft Defender** e quindi espandere Antivirus Microsoft Defender **esclusioni**.<br/><br/>6. Specificare i file e le cartelle, le estensioni e i processi da escludere Antivirus Microsoft Defender analisi. Per informazioni di riferimento, [vedere Antivirus Microsoft Defender esclusioni.](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<br/><br/>7. Scegliere **Rivedi e salva** e quindi **Salva.**  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) |1. Utilizzando la [console di Configuration Manager,](/mem/configmgr/core/servers/manage/admin-console)passare a **Assets and Compliance**  >  **Endpoint Protection**  >  **Antimalware Policies** e quindi selezionare il criterio che si desidera modificare. <br/><br/>2. Specificare le impostazioni di esclusione per file e cartelle, estensioni e processi da escludere Antivirus Microsoft Defender analisi. |
|[Oggetto Criteri di gruppo](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Nel computer di gestione di Criteri di gruppo, aprire la [Console](https://technet.microsoft.com/library/cc731212.aspx)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.<br/><br/>2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e fare clic su **Modelli amministrativi.**<br/><br/>3. Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > esclusioni**.<br/>**NOTA:** potrebbe essere visualizzato *Windows Defender Antivirus* invece *di Antivirus Microsoft Defender* in alcune versioni di Windows.<br/><br/>4. Fare doppio clic **sull'impostazione Esclusioni percorso** e aggiungere le esclusioni.<br/><br/>- Impostare l'opzione su **Abilitato**.<br/><br/>- Nella sezione **Opzioni** fare clic su **Mostra...**.<br/><br/>- Specificare ogni cartella nella propria riga nella **colonna Nome** valore.<br/><br/>- Se si specifica un file, assicurarsi di immettere un percorso completo del file, inclusi la lettera di unità, il percorso della cartella, il nome del file e l'estensione. Immettere **0** nella **colonna** Valore.<br/><br/>5. Fare clic **su OK.**<br/><br/>6. Fare doppio clic **sull'impostazione Esclusioni estensioni** e aggiungere le esclusioni.<br/><br/>- Impostare l'opzione su **Abilitato**.<br/><br/>- Nella sezione **Opzioni** fare clic su **Mostra...**.<br/><br/>- Immettere ogni estensione di file nella propria riga nella **colonna Nome** valore.  Immettere **0** nella **colonna** Valore.<br/>7. Fare clic **su OK.** |
|Oggetto Criteri di gruppo locali |1. Nell'endpoint o nel dispositivo aprire l'Editor Criteri di gruppo locali. <br/><br/>2. Passare a **Configurazione computer**  >  **Modelli**  >  **amministrativi Windows componenti**  >  **Antivirus Microsoft Defender**  >  **esclusioni**. <br/>**NOTA:** potrebbe essere visualizzato *Windows Defender Antivirus* invece *di Antivirus Microsoft Defender* in alcune versioni di Windows.<br/><br/>3. Specificare il percorso e le esclusioni di processo. |
|Chiave del Registro di sistema |1. Esportare la seguente chiave del Registro di sistema: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<br/><br/>2. Importare la chiave del Registro di sistema. Ecco due esempi:<br/>- Percorso locale: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Condivisione di rete: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>Aggiungere Symantec all'elenco di esclusione per Microsoft Defender for Endpoint

Per aggiungere esclusioni a Microsoft Defender for Endpoint, devi creare [indicatori](/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files).

1. Vai al Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) e accedi.

1. Nel riquadro di spostamento scegliere **Impostazioni**  >  **regole**  >  .

1.  Nella scheda **Hash file** scegliere **Aggiungi indicatore.**

1. Nella scheda **Indicatore** specificare le impostazioni seguenti:
   - Hash del file (serve aiuto? Vedere [Trovare un hash di file tramite CMPivot](#find-a-file-hash-using-cmpivot) in questo articolo.
   - In **Scadenza il (UTC)** scegliere **Mai.**
   
1. Nella scheda **Azione** specificare le impostazioni seguenti:
   - **Azione di risposta**: **Consenti**
   - Titolo e descrizione

1. Nella scheda **Ambito,** in **Gruppi di dispositivi,** selezionare Tutti i **dispositivi nell'ambito** o **Seleziona dall'elenco**.

1. Nella scheda **Riepilogo** esaminare le impostazioni e quindi fare clic su **Salva.**

### <a name="find-a-file-hash-using-cmpivot"></a>Trovare un hash di file tramite CMPivot

CMPivot è un'utilità nella console per Configuration Manager. CMPivot consente di accedere allo stato in tempo reale dei dispositivi nell'ambiente. Esegue immediatamente una query su tutti i dispositivi attualmente connessi nella raccolta di destinazione e restituisce i risultati. Per ulteriori informazioni, vedere [Panoramica di CMPivot.](/mem/configmgr/core/servers/manage/cmpivot-overview)

Per usare CMPivot per ottenere l'hash del file, attenersi alla seguente procedura:

1. Esaminare i [prerequisiti](/mem/configmgr/core/servers/manage/cmpivot#prerequisites).<br/>

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
|[I gruppi di](/microsoft-365/security/defender-endpoint/machine-groups) dispositivi (in precedenza denominati gruppi di computer) consentono al team delle operazioni di sicurezza di configurare funzionalità di sicurezza, ad esempio analisi e correzione automatizzate.<br/> I gruppi di dispositivi sono utili anche per assegnare l'accesso a tali dispositivi in modo che il team delle operazioni di sicurezza possa eseguire azioni correttive se necessario. <br/>I gruppi di dispositivi vengono creati nella Microsoft Defender Security Center. |1. Passare al Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<br/><br/>2. Nel riquadro di spostamento a sinistra scegliere Impostazioni  >  **autorizzazioni**  >  **Gruppi di dispositivi**.  <br/><br/>3. Scegliere **+ Aggiungi gruppo di dispositivi.**<br/><br/>4. Specificare un nome e una descrizione per il gruppo di dispositivi.<br/><br/>5. **Nell'elenco Livello di automazione** selezionare un'opzione. È consigliabile **completare la correzione automatica delle minacce.** Per ulteriori informazioni sui vari livelli di automazione, vedere [Come vengono corretti i rischi.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<br/><br/>6. Specificare le condizioni per una regola di corrispondenza per determinare quali dispositivi appartengono al gruppo di dispositivi. Ad esempio, puoi scegliere un dominio, le versioni del sistema operativo o persino usare i [tag del dispositivo.](/microsoft-365/security/defender-endpoint/machine-tags)<br/> <br/>7. Nella **scheda Accesso** utente specificare i ruoli che devono avere accesso ai dispositivi inclusi nel gruppo di dispositivi. <br/><br/>8. Scegliere **Fine.** |
|[Le raccolte di](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) dispositivi consentono al team delle operazioni di sicurezza di gestire le applicazioni, distribuire le impostazioni di conformità o installare aggiornamenti software nei dispositivi dell'organizzazione. <br/>Le raccolte di dispositivi vengono create tramite [Configuration Manager.](/mem/configmgr/) |Seguire i passaggi descritti in [Creare una raccolta](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
|[Le unità organizzative](/azure/active-directory-domain-services/create-ou) consentono di raggruppare logicamente oggetti quali account utente, account di servizio o account computer. È quindi possibile assegnare amministratori a unità organizzative specifiche e applicare criteri di gruppo per applicare impostazioni di configurazione mirate.<br/> Le unità organizzative sono definite in [Azure Active Directory Domain Services](/azure/active-directory-domain-services). | Seguire i passaggi descritti in [Create an Organizational Unit in an Azure Active Directory Domain Services managed domain services](/azure/active-directory-domain-services/create-ou). |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Configurare criteri antimalware e protezione in tempo reale

Usando Configuration Manager e le raccolte di dispositivi, configura i criteri antimalware.

- Vedere [Creare e distribuire criteri antimalware per Endpoint Protection in Configuration Manager.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)

- Durante la creazione e la configurazione dei criteri [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) antimalware, verificare le impostazioni di protezione in tempo reale e abilitare [il blocco al primo sguardo.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> Puoi distribuire i criteri prima dell'onboarded dei dispositivi dell'organizzazione.

## <a name="next-step"></a>Passaggio successivo

**Congratulazioni**! Hai completato la fase di installazione della [migrazione da Symantec a Microsoft Defender per Endpoint!](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)
- [Passare alla fase 3: eseguire l'onboard in Microsoft Defender per Endpoint](symantec-to-microsoft-defender-atp-onboard.md)
