---
title: Passare a Microsoft Defender for Endpoint - Installazione
description: Fase 2, il processo di configurazione, quando si passa a Microsoft Defender per Endpoint.
keywords: migrazione, Microsoft Defender for Endpoint, edr, Windows Defender
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
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: e8abf10bd036b5e6e76d08e86ab4963629d2f994
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537992"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Passare a Microsoft Defender per Endpoint - Fase 2: installazione

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fase 1: preparazione](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fase 1: preparazione](switch-to-microsoft-defender-prepare.md) |![Fase 2: configurazione](images/phase-diagrams/setup.png)<br/>Fase 2: configurazione |[![Fase 3: Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Fase 3: onboarding](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*Sei qui!* | |

**Benvenuti nella fase di installazione [del passaggio a Defender per Endpoint.](switch-to-microsoft-defender-migration.md#the-migration-process)** Questa fase include i passaggi seguenti:

1. [Reinstallare/abilitare Antivirus Microsoft Defender sugli endpoint](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).

2. [Configurare Defender per Endpoint](#configure-defender-for-endpoint).

3. [Aggiungi Defender per Endpoint all'elenco di esclusione per la soluzione esistente.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)

4. [Aggiungere la soluzione esistente all'elenco di esclusione per Antivirus Microsoft Defender](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus).

5. [Configurare i gruppi di dispositivi, le raccolte di dispositivi e le unità organizzative.](#set-up-your-device-groups-device-collections-and-organizational-units)

6. [Configurare i criteri antimalware e la protezione in tempo reale.](#configure-antimalware-policies-and-real-time-protection)


## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>Reinstallare/abilitare Antivirus Microsoft Defender nei tuoi endpoint

In alcune versioni di Windows, è probabile Antivirus Microsoft Defender disinstallato o disabilitato quando è stata installata la soluzione antivirus/antimalware non Microsoft. Per ulteriori informazioni, vedere [Antivirus Microsoft Defender compatibilità.](microsoft-defender-antivirus-compatibility.md)

Nei client Windows, quando viene installata una soluzione antivirus/antimalware non Microsoft, Antivirus Microsoft Defender viene disabilitato automaticamente fino a quando tali dispositivi non vengono onboarded in Defender for Endpoint. Quando gli endpoint client vengono onboarded in Defender for Endpoint, Antivirus Microsoft Defender passa in modalità passiva fino a quando la soluzione antivirus non Microsoft non viene disinstallata. Antivirus Microsoft Defender deve essere ancora installato, ma è probabile che sia disabilitato a questo punto del processo di migrazione. A Antivirus Microsoft Defender non è stata disinstallata, non è necessario eseguire alcuna azione per i Windows client.

Nei Windows, quando è installato un antivirus/antimalware non Microsoft, il Antivirus Microsoft Defender viene disabilitato manualmente (se non disinstallato). Le attività seguenti assicurano che Antivirus Microsoft Defender installato e impostato sulla modalità passiva in Windows Server.

- [Impostare DisableAntiSpyware su false Windows Server](#set-disableantispyware-to-false-on-windows-server) (solo se necessario)

- [Reinstallare Antivirus Microsoft Defender in Windows Server](#reinstall-microsoft-defender-antivirus-on-windows-server) 

- [Impostare Antivirus Microsoft Defender modalità passiva in Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Impostare DisableAntiSpyware su false Windows Server

La chiave del Registro di sistema [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) è stata utilizzata in passato per disabilitare Antivirus Microsoft Defender e distribuire un altro prodotto antivirus, ad esempio McAfee, Symantec o altri. In generale, non dovresti avere questa chiave del Registro di sistema nei dispositivi Windows e negli endpoint; Tuttavia, se è stata `DisableAntiSpyware` configurata, ecco come impostarne il valore su false:

1. Nel dispositivo Windows Server aprire l'editor del Registro di sistema.

2. Passare a `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.

3. In tale cartella cerca una voce DWORD denominata **DisableAntiSpyware.**
   - Se la voce non viene visualizzata, è tutto impostato.
   - Se viene visualizzato **DisableAntiSpyware,** andare al passaggio 4.

4. Fare clic con il pulsante destro del mouse sul valore DWORD DisableAntiSpyware e quindi scegliere **Modifica**.

5. Impostare il valore su `0` . Questa azione imposta il valore della chiave del Registro di sistema su *false.*

> [!TIP]
> Per ulteriori informazioni su questa chiave del Registro di sistema, [vedere DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Reinstallare Antivirus Microsoft Defender in Windows Server

> [!IMPORTANT]
> La procedura seguente si applica solo agli endpoint o ai dispositivi che eseguono le versioni seguenti di Windows:
> - Windows Server 2019
> - Windows Server, versione 1803 (modalità solo core)
> - Windows Server 2016 (vedere la sezione seguente, [Si sta usando Windows Server 2016?](#are-you-using-windows-server-2016))

1. In quanto amministratore locale nell'endpoint o nel dispositivo, apri Windows PowerShell.

2. Eseguire i cmdlet di PowerShell seguenti: <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <p>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
    > [!NOTE]
    > Quando si usa il comando Gestione e manutenzione immagini distribuzione all'interno di una sequenza di attività che esegue PS, è necessario cmd.exe percorso seguente.
    > Esempio:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<p>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Per verificare Antivirus Microsoft Defender è in esecuzione, utilizzare il cmdlet PowerShell seguente: <br/>
   `Get-Service -Name windefend`

   Cercare lo stato In *esecuzione*.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Impostare Antivirus Microsoft Defender modalità passiva in Windows Server

1. Aprire l'editor del Registro di sistema e quindi passare a <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Modificare (o creare) una voce DWORD denominata **ForcePassiveMode** e specificare le impostazioni seguenti:
   - Imposta il valore DWORD su **1.**
   - In **Base** selezionare **Esadecimale.**

> [!NOTE]
> Dopo l'onboarding in Defender per Endpoint, potrebbe essere necessario impostare Antivirus Microsoft Defender modalità passiva in Windows Server.

### <a name="are-you-using-windows-server-2016"></a>Si sta usando Windows Server 2016?

Se sono in esecuzione endpoint Windows Server 2016, non è possibile eseguire Antivirus Microsoft Defender insieme a una soluzione antivirus/antimalware non Microsoft. Antivirus Microsoft Defender non può essere eseguito in modalità passiva Windows Server 2016. In questo caso, dovrai disinstallare la soluzione antivirus/antimalware non Microsoft e installare/abilitare Antivirus Microsoft Defender. Per altre informazioni, vedi [Compatibilità delle soluzioni antivirus con Defender per Endpoint.](microsoft-defender-antivirus-compatibility.md)

Se si usa Windows Server 2016 e si verificano problemi nell'abilitazione Antivirus Microsoft Defender, utilizzare il cmdlet PowerShell seguente:

`mpcmdrun -wdenable`

Per ulteriori informazioni, vedere [Antivirus Microsoft Defender on Windows Server](microsoft-defender-antivirus-on-windows-server.md).

## <a name="configure-defender-for-endpoint"></a>Configurare Defender per Endpoint

Questo passaggio del processo di migrazione prevede la configurazione Antivirus Microsoft Defender per gli endpoint. È consigliabile usare Intune; tuttavia, è possibile utilizzare uno qualsiasi dei metodi elencati nella tabella seguente:

|Metodo  |Soluzione  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**NOTA:** Intune fa ora parte di Microsoft Endpoint Manager. | 1. Accedere [all'Microsoft Endpoint Manager di amministrazione](https://go.microsoft.com/fwlink/?linkid=2109431) ed eseguire l'accesso.<p> 2. Selezionare **Profili** di configurazione dei dispositivi e quindi selezionare il tipo  >  di profilo che si desidera configurare. Se non hai ancora  creato un tipo di profilo Restrizioni dispositivo o se vuoi crearne uno nuovo, vedi Configurare le impostazioni di restrizione dei dispositivi [in Microsoft Intune](/intune/device-restrictions-configure).<p> 3. Selezionare **Proprietà** e quindi Impostazioni **di configurazione: Modifica**.<p> 4. Espandere **Antivirus Microsoft Defender**. <p> 5. Abilitare **la protezione consegnata dal cloud.**<p> 6. Nell'elenco a discesa **Chiedi conferma agli utenti prima** dell'invio di esempio seleziona Invia **automaticamente tutti i campioni.**<p> 7. Nell'elenco a discesa **Rileva applicazioni potenzialmente indesiderate** selezionare **Abilita** o **Controlla.**<p> 8. Selezionare **Rivedi e salva** e quindi scegliere **Salva.**<p>**SUGGERIMENTO:** per ulteriori informazioni sui profili di dispositivo intune, inclusa la procedura per creare e configurare le impostazioni, vedere [What are Microsoft Intune device profiles?](/intune/device-profiles).|
|Pannello di controllo in Windows     |Seguire le indicazioni qui: [Attivare Antivirus Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows). <p>**NOTA:** potrebbe essere visualizzato *Windows Defender Antivirus* invece *di Antivirus Microsoft Defender* in alcune versioni di Windows.        |
|[Gestion avancée des stratégies de groupe](/microsoft-desktop-optimization-pack/agpm/) <br/>oppure<br/>[Console Gestione Criteri di gruppo](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  | 1. Passare a **Configurazione computer** Modelli amministrativi  >  **Windows** componenti  >    >  **Antivirus Microsoft Defender**. <p> 2. Cercare un criterio denominato **Disattiva Antivirus Microsoft Defender**.<p> 3. Scegliere **Modifica impostazione dei criteri** e assicurarsi che il criterio sia disabilitato. Questa azione consente di Antivirus Microsoft Defender. <p>**NOTA:** potrebbe essere visualizzato *Windows Defender Antivirus* invece *di Antivirus Microsoft Defender* in alcune versioni di Windows. |

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Aggiungere Microsoft Defender for Endpoint all'elenco di esclusione per la soluzione esistente

Questo passaggio del processo di configurazione prevede l'aggiunta di Defender for Endpoint all'elenco di esclusione per la soluzione di endpoint protection esistente e per qualsiasi altro prodotto di sicurezza utilizzato dall'organizzazione. 

> [!TIP]
> Per informazioni sulla configurazione delle esclusioni, fare riferimento alla documentazione del provider di soluzioni.

Le esclusioni specifiche da configurare dipendono dalla versione di Windows degli endpoint o dei dispositivi in esecuzione e sono elencate nella tabella seguente:

|Sistema operativo |Esclusioni |
|--|--|
|Windows 10 versione [1803](/windows/release-health/status-windows-10-1803) o successiva (vedere Windows 10 [sulla versione](/windows/release-health/release-information))<p>Windows 10 versione 1703 o 1709 con [KB4493441](https://support.microsoft.com/help/4493441) installato <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server, versione 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<p>  |
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**NOTA:** i file temporanei dell'host di monitoraggio 6\45 possono essere sottocartelle numerate diverse. <p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Aggiungere la soluzione esistente all'elenco di esclusione per Antivirus Microsoft Defender

Durante questo passaggio del processo di installazione, aggiungere la soluzione esistente all'Antivirus Microsoft Defender di esclusione. Puoi scegliere tra diversi metodi per aggiungere le esclusioni Antivirus Microsoft Defender, come elencato nella tabella seguente:

|Metodo | Soluzione|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**NOTA:** Intune fa ora parte di Microsoft Endpoint Manager. | 1. Accedere [all'Microsoft Endpoint Manager di amministrazione](https://go.microsoft.com/fwlink/?linkid=2109431) ed eseguire l'accesso.<p> 2. Selezionare **Profili** di configurazione dei dispositivi e quindi  >  selezionare il profilo che si desidera configurare.<p> 3. In **Gestisci** selezionare **Proprietà.**<p> 4. Selezionare **Impostazioni di configurazione: Modifica**.<p> 5. Espandere **Antivirus Microsoft Defender** e quindi espandere Antivirus Microsoft Defender **esclusioni**.<p> 6. Specificare i file e le cartelle, le estensioni e i processi da escludere Antivirus Microsoft Defender analisi. Per informazioni di riferimento, [vedere Antivirus Microsoft Defender esclusioni.](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<p> 7. Scegliere **Rivedi e salva** e quindi **Salva.**  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) | 1. Utilizzando la [console di Configuration Manager,](/mem/configmgr/core/servers/manage/admin-console)passare a **Assets and Compliance**  >  **Endpoint Protection**  >  **Antimalware Policies** e quindi selezionare il criterio che si desidera modificare. <p> 2. Specificare le impostazioni di esclusione per file e cartelle, estensioni e processi da escludere Antivirus Microsoft Defender analisi. |
|[Oggetto Criteri di gruppo](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Nel computer di gestione di Criteri di gruppo, aprire la [Console](https://technet.microsoft.com/library/cc731212.aspx)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.<p> 2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**<p> 3. Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > esclusioni**.<br/>**NOTA:** potrebbe essere visualizzato *Windows Defender Antivirus* invece *di Antivirus Microsoft Defender* in alcune versioni di Windows.<p> 4. Fare doppio clic **sull'impostazione Esclusioni percorso** e aggiungere le esclusioni.<br/>- Impostare l'opzione su **Abilitato**.<br/>- Nella sezione **Opzioni** selezionare **Mostra...**.<br/>- Specificare ogni cartella nella propria riga nella **colonna Nome** valore.<br/>- Se si specifica un file, assicurarsi di immettere un percorso completo del file, inclusi la lettera di unità, il percorso della cartella, il nome del file e l'estensione. Immettere **0** nella **colonna** Valore.<p> 5. Selezionare **OK**.<p> 6. Fare doppio clic **sull'impostazione Esclusioni estensioni** e aggiungere le esclusioni.<br/>- Impostare l'opzione su **Abilitato**.<br/>- Nella sezione **Opzioni** selezionare **Mostra...**.<br/>- Immettere ogni estensione di file nella propria riga nella **colonna Nome** valore.  Immettere **0** nella **colonna** Valore.<p> 7. Selezionare **OK**. |
|Oggetto Criteri di gruppo locali |1. Nell'endpoint o nel dispositivo aprire l'Editor Criteri di gruppo locali. <p>2. Passare a **Configurazione computer**  >  **Modelli**  >  **amministrativi Windows componenti**  >  **Antivirus Microsoft Defender**  >  **esclusioni**.<p>**NOTA:** potrebbe essere visualizzato *Windows Defender Antivirus* invece *di Antivirus Microsoft Defender* in alcune versioni di Windows.<p>3. Specificare il percorso e le esclusioni di processo. |
|Chiave del Registro di sistema |1. Esportare la seguente chiave del Registro di sistema: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<p>2. Importare la chiave del Registro di sistema. Ecco due esempi:<br/>- Percorso locale: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Condivisione di rete: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>Tenere presenti i punti seguenti relativi alle esclusioni

Quando si [aggiungono esclusioni alle Antivirus Microsoft Defender,](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)è consigliabile aggiungere le esclusioni di percorso ed elaborazione. Tenere presenti i punti seguenti:

- *Le esclusioni di percorso* escludono file specifici e qualsiasi file a cui accedono.

- *Le esclusioni di* processo escludono qualsiasi cosa tocca un processo, ma non escludono il processo stesso.

- Elencare le esclusioni di processo usando il percorso completo e non solo in base al nome. Il metodo solo nome è meno sicuro.

- Se si elenca ogni eseguibile (.exe) sia come esclusione di percorso che come esclusione di processo, il processo e tutto ciò che tocca vengono esclusi.


## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Configurare i gruppi di dispositivi, le raccolte di dispositivi e le unità organizzative

I gruppi di dispositivi, le raccolte di dispositivi e le unità organizzative consentono al team di sicurezza di gestire e assegnare criteri di sicurezza in modo efficiente ed efficiente. La tabella seguente descrive ognuno di questi gruppi e come configurarli. L'organizzazione potrebbe non utilizzare tutti e tre i tipi di raccolta.

| Tipo di raccolta | Soluzione |
|--|--|
|[I gruppi di](/microsoft-365/security/defender-endpoint/machine-groups) dispositivi (in *precedenza* denominati gruppi di computer) consentono al team delle operazioni di sicurezza di configurare funzionalità di sicurezza, ad esempio analisi e correzione automatizzate.<p>I gruppi di dispositivi sono utili anche per assegnare l'accesso a tali dispositivi in modo che il team delle operazioni di sicurezza possa eseguire azioni correttive se necessario. <p>I gruppi di dispositivi vengono creati nella [Microsoft Defender Security Center](microsoft-defender-security-center.md). |1. Passare al Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<p>2. Nel riquadro di spostamento a sinistra scegliere Impostazioni  >  **autorizzazioni**  >  **Gruppi di dispositivi**.  <p>3. Scegliere **+ Aggiungi gruppo di dispositivi.**<p>4. Specificare un nome e una descrizione per il gruppo di dispositivi.<p>5. **Nell'elenco Livello di automazione** selezionare un'opzione. È consigliabile **completare la correzione automatica delle minacce.** Per ulteriori informazioni sui vari livelli di automazione, vedere [Come vengono corretti i rischi.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<p>6. Specificare le condizioni per una regola di corrispondenza per determinare quali dispositivi appartengono al gruppo di dispositivi. Ad esempio, puoi scegliere un dominio, le versioni del sistema operativo o persino usare i [tag del dispositivo.](/microsoft-365/security/defender-endpoint/machine-tags)<p>7. Nella **scheda Accesso** utente specificare i ruoli che devono avere accesso ai dispositivi inclusi nel gruppo di dispositivi. <p>8. Scegliere **Fine.** |
|[Le raccolte di](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) dispositivi consentono al team delle operazioni di sicurezza di gestire le applicazioni, distribuire le impostazioni di conformità o installare aggiornamenti software nei dispositivi dell'organizzazione.<p>Le raccolte di dispositivi vengono create tramite [Configuration Manager.](/mem/configmgr/) |Seguire i passaggi descritti in [Creare una raccolta](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create). |
|[Le unità organizzative](/azure/active-directory-domain-services/create-ou) consentono di raggruppare logicamente oggetti quali account utente, account di servizio o account computer. È quindi possibile assegnare amministratori a unità organizzative specifiche e applicare criteri di gruppo per applicare impostazioni di configurazione mirate.<p> Le unità organizzative sono definite in [Azure Active Directory Domain Services](/azure/active-directory-domain-services). | Seguire i passaggi descritti in [Create an Organizational Unit in an Azure Active Directory Domain Services managed domain services](/azure/active-directory-domain-services/create-ou). |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Configurare criteri antimalware e protezione in tempo reale

Usando Configuration Manager e le raccolte di dispositivi, configura i criteri antimalware.

- Vedere [Creare e distribuire criteri antimalware per Endpoint Protection in Configuration Manager.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)

- Durante la creazione e la configurazione dei criteri [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) antimalware, verificare le impostazioni di protezione in tempo reale e abilitare [il blocco al primo sguardo.](configure-block-at-first-sight-microsoft-defender-antivirus.md)

> [!TIP]
> Puoi distribuire i criteri prima dell'onboarded dei dispositivi dell'organizzazione.

## <a name="next-step"></a>Passaggio successivo

**Congratulazioni**! Hai completato la fase di installazione [del passaggio a Defender for Endpoint!](switch-to-microsoft-defender-migration.md#the-migration-process)

- [Passare alla fase 3: eseguire l'onboard per Defender per Endpoint](switch-to-microsoft-defender-onboard.md)
