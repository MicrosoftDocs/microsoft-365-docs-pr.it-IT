---
title: Pianificare analisi regolari rapide e complete con Antivirus Microsoft Defender
description: Configurare analisi ricorrenti (pianificate), inclusa la data e l'ora in cui devono essere eseguite e se vengono eseguite come analisi complete o rapide
keywords: analisi rapida, analisi completa, rapida e completa, pianificazione dell'analisi, giornaliera, settimanale, ora, pianificata, ricorrente, regolare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 038818b711400eb16fea89573dc70664a442fc1d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245901"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Configurare analisi pianificate rapide o complete di Microsoft Defender Antivirus

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Per impostazione predefinita, Antivirus Microsoft Defender un aggiornamento 15 minuti prima dell'ora di qualsiasi analisi pianificata. È possibile gestire la pianificazione per il momento in cui gli aggiornamenti di protezione [devono essere scaricati e applicati per](manage-protection-update-schedule-microsoft-defender-antivirus.md) ignorare questa impostazione predefinita. 

Oltre alla protezione sempre in tempo [](run-scan-microsoft-defender-antivirus.md) reale e alle analisi su richiesta, è possibile configurare analisi regolari e pianificate. 

È possibile configurare il tipo di analisi, quando deve essere eseguita [](manage-protection-updates-microsoft-defender-antivirus.md) e se l'analisi deve essere eseguita dopo un aggiornamento della protezione o se l'endpoint è in uso. È inoltre possibile specificare quando eseguire analisi speciali per completare la correzione.

In questo articolo viene descritto come configurare le analisi pianificate con Criteri di gruppo, cmdlet di PowerShell e WMI. È inoltre possibile configurare le analisi delle pianificazioni [con Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) o [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>Per configurare le impostazioni di Criteri di gruppo descritte in questo articolo

1. Nel computer di gestione di Criteri di gruppo, nell'Editor Criteri di gruppo, passare **a** Configurazione computer Modelli amministrativi  >    >  **Windows Componenti**  >  **Antivirus Microsoft Defender**  >  **Analisi**.

2. Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.

3. Specificare le impostazioni per l'oggetto Criteri di gruppo e quindi selezionare **OK.** 

4. Ripetere i passaggi da 1 a 4 per ogni impostazione che si desidera configurare.

5. Distribuire l'oggetto Criteri di gruppo come si fa normalmente. Per assistenza con gli oggetti Criteri di gruppo, vedere [Create a Group Policy Object.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

Vedere anche gli [argomenti Gestire quando scaricare e](manage-protection-update-schedule-microsoft-defender-antivirus.md) applicare gli aggiornamenti della protezione e Impedire o consentire agli utenti di modificare [localmente le impostazioni dei](configure-local-policy-overrides-microsoft-defender-antivirus.md) criteri.

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Analisi rapida e analisi completa e analisi personalizzata

Quando si configurano analisi pianificate, è possibile specificare se l'analisi deve essere completa o rapida.


|Analisi rapida  |Analisi completa  | Analisi personalizzata |
|---------|---------|---------|
|Un'analisi rapida esamina tutti i percorsi in cui potrebbe essere registrato malware per iniziare con il sistema, ad esempio le chiavi del Registro di sistema e le cartelle di avvio Windows note. <p>Nella maggior parte dei casi, un'analisi rapida è sufficiente ed è consigliata per le analisi pianificate. |Un'analisi completa inizia eseguendo un'analisi rapida e quindi continua con un'analisi sequenziale dei file di tutti i dischi fissi montati e delle unità rimovibili/di rete (se l'analisi completa è configurata per farlo). <p>Il completamento di un'analisi completa può richiedere alcune ore o giorni, a seconda della quantità e del tipo di dati da analizzare.<p>Al termine dell'analisi completa, è disponibile una nuova intelligence per la sicurezza ed è necessaria una nuova analisi per assicurarsi che non siano rilevate altre minacce con la nuova intelligence per la sicurezza.   | Un'analisi personalizzata è un'analisi rapida eseguita sui file e sulle cartelle specificati. Ad esempio, puoi scegliere di analizzare un'unità USB o una cartella specifica nell'unità locale del dispositivo. <p> | 

>[!NOTE]
>Per impostazione predefinita, le analisi rapide vengono eseguite su dispositivi rimovibili montati, ad esempio unità USB.

### <a name="how-do-i-know-which-scan-type-to-choose"></a>Come è possibile sapere quale tipo di analisi scegliere?

Utilizzare la tabella seguente per scegliere un tipo di analisi.


|Scenario  |Tipo di analisi consigliato  |
|---------|---------|
|Si desidera configurare analisi regolari e pianificate     | Analisi rapida <p>Un'analisi rapida controlla i processi, la memoria, i profili e alcune posizioni nel dispositivo. In combinazione con la protezione [in tempo](configure-real-time-protection-microsoft-defender-antivirus.md)reale sempre on, un'analisi rapida consente di fornire una copertura avanzata sia per il malware che inizia con il sistema che con il malware a livello di kernel. La protezione in tempo reale esamina i file quando vengono aperti e chiusi e ogni volta che un utente passa a una cartella.         |
|Le minacce, ad esempio malware, vengono rilevate in un dispositivo     | Analisi completa <p>Un'analisi completa consente di identificare se sono presenti componenti inattivi che richiedono una pulizia più approfondita.         |
|Si desidera eseguire [un'analisi su richiesta](run-scan-microsoft-defender-antivirus.md)     | Analisi completa  <p>Un'analisi completa esamina tutti i file sul disco del dispositivo, inclusi i file non obsoleti, archiviati e non accessibili ogni giorno.      |
| Si desidera verificare che un dispositivo portatile, ad esempio un'unità USB, non contenga malware | Analisi personalizzata <p>Un'analisi personalizzata consente di selezionare percorsi, cartelle o file specifici ed esegue un'analisi rapida. |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>Altre informazioni sulle analisi rapide e complete

- I file dannosi possono essere archiviati in posizioni non incluse in un'analisi rapida. Tuttavia, la protezione sempre in tempo reale esamina tutti i file aperti e chiusi e tutti i file presenti in cartelle a cui un utente accede. La combinazione di protezione in tempo reale e analisi rapida consente di garantire una protezione avanzata dal malware.

- La protezione all'accesso con protezione garantita dal [cloud](cloud-protection-microsoft-defender-antivirus.md) garantisce che tutti i file a cui si accede nel sistema vengano analizzati con i modelli più recenti di security intelligence e machine learning cloud.

- Quando la protezione in tempo reale rileva malware e l'estensione dei file interessati non viene determinata inizialmente, Antivirus Microsoft Defender avvia un'analisi completa come parte del processo di correzione.

- Un'analisi completa può rilevare file dannosi non rilevati da altre analisi, ad esempio un'analisi rapida. Tuttavia, un'analisi completa può richiedere un po' di tempo e utilizzare risorse di sistema preziose per il completamento.

- Se un dispositivo è offline per un lungo periodo di tempo, il completamento di un'analisi completa può richiedere più tempo. 

## <a name="set-up-scheduled-scans"></a>Configurare le analisi pianificate

Le analisi pianificate vengono eseguite il giorno e l'ora specificati. È possibile utilizzare Criteri di gruppo, PowerShell e WMI per configurare le analisi pianificate.

> [!NOTE]
> Se un dispositivo viene scollegato e in esecuzione a batteria durante un'analisi completa pianificata, l'analisi pianificata verrà interrotta con l'evento 1002, che indica che l'analisi è stata interrotta prima del completamento. Antivirus Microsoft Defender verrà eseguita un'analisi completa alla successiva ora pianificata.

### <a name="use-group-policy-to-schedule-scans"></a>Utilizzare Criteri di gruppo per pianificare le analisi

|Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata) |
|:---|:---|:---|:---|
|Analisi | Specificare il tipo di analisi da utilizzare per un'analisi pianificata | Analisi rapida |
|Analisi | Specificare il giorno della settimana per l'esecuzione di un'analisi pianificata | Specificare il giorno (o mai) in cui eseguire un'analisi. | Mai |
|Analisi | Specificare l'ora del giorno per l'esecuzione di un'analisi pianificata | Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per l'1 di notte). | 02.00 |
|Radice | Tempo attività programmato casuale |In Antivirus Microsoft Defender, randomizzare l'ora di inizio dell'analisi a qualsiasi intervallo da 0 a 4 ore. <p>In [SCEP,](/mem/intune/protect/certificates-scep-configure)esegui analisi casuali a qualsiasi intervallo più o meno 30 minuti. Ciò può essere utile nelle macchine virtuali o nelle distribuzioni VDI. | Abilitato |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Utilizzare i cmdlet di PowerShell per pianificare le analisi

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Per ulteriori informazioni, vedere [Use PowerShell cmdlets to configure and run Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Antivirus Microsoft Defender.

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Utilizzare Windows Management Instruction (WMI) per pianificare le analisi

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>Avviare analisi pianificate solo quando l'endpoint non è in uso

È possibile impostare l'analisi pianificata in modo che si verifichi solo quando l'endpoint è attivato ma non in uso con Criteri di gruppo, PowerShell o WMI.

> [!NOTE]
> Queste analisi non rispettano la configurazione della limitazione della CPU e sfruttano appieno le risorse disponibili per completare l'analisi il più velocemente possibile.

### <a name="use-group-policy-to-schedule-scans"></a>Utilizzare Criteri di gruppo per pianificare le analisi

|Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata) |
|:---|:---|:---|:---|
|Analisi | Avviare l'analisi pianificata solo quando il computer è in uso ma non è in uso | Le analisi pianificate non verranno eseguite, a meno che il computer non sia in uso | Abilitato |

### <a name="use-powershell-cmdlets"></a>Utilizzare i cmdlet di PowerShell

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

Per ulteriori informazioni, vedere [Use PowerShell cmdlets to configure and run Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi"></a>Utilizzare Windows Management Instruction (WMI)

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
ScanOnlyIfIdleEnabled
```

Per altre informazioni sulle API e sui parametri consentiti, vedi Windows Defender [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Configurare quando eseguire le analisi complete per completare la correzione

Alcune minacce potrebbero richiedere un'analisi completa per completare la rimozione e la correzione. È possibile specificare quando eseguire queste analisi con Criteri di gruppo, PowerShell o WMI.

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>Utilizzare Criteri di gruppo per pianificare le analisi necessarie per la correzione

| Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata) |
|---|---|---|---|
|Correzione | Specificare il giorno della settimana in cui eseguire un'analisi completa pianificata per completare la correzione | Specificare il giorno (o mai) in cui eseguire un'analisi. | Mai |
|Correzione | Specificare l'ora del giorno in cui eseguire un'analisi completa pianificata per completare la correzione | Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per le 13.00) | 02.00 |

### <a name="use-powershell-cmdlets"></a>Utilizzare i cmdlet di PowerShell

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Use [PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Antivirus Microsoft Defender run Antivirus Microsoft Defender and [Defender cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi"></a>Utilizzare Windows Management Instruction (WMI)

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).


## <a name="set-up-daily-quick-scans"></a>Configurare analisi rapide giornaliere

È possibile abilitare un'analisi rapida giornaliera che può essere eseguita in aggiunta alle altre analisi pianificate con Criteri di gruppo, PowerShell o WMI.

### <a name="use-group-policy-to-schedule-daily-scans"></a>Utilizzare Criteri di gruppo per pianificare le analisi giornaliere

|Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata) |
|:---|:---|:---|:---|
|Analisi | Specificare l'intervallo per l'esecuzione di analisi rapide al giorno | Specificare il numero di ore che devono trascorrere prima della successiva analisi rapida. Ad esempio, per eseguire ogni due ore, immettere **2**, per una volta al giorno, **immettere 24**. Immettere **0 per** non eseguire mai un'analisi rapida giornaliera. | Mai |
|Analisi | Specificare l'ora per un'analisi rapida giornaliera | Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per le 13.00) | 02.00 |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>Utilizzare i cmdlet di PowerShell per pianificare le analisi giornaliere

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Per ulteriori informazioni su come utilizzare PowerShell con Antivirus Microsoft Defender, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire Antivirus Microsoft Defender [e i cmdlet defender.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Utilizzare Windows Management Instruction (WMI) per pianificare le analisi giornaliere

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
ScanScheduleQuickScanTime
```

Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).


## <a name="enable-scans-after-protection-updates"></a>Abilitare le analisi dopo gli aggiornamenti della protezione

È possibile forzare l'esecuzione di un'analisi dopo ogni [aggiornamento della protezione](manage-protection-updates-microsoft-defender-antivirus.md) con Criteri di gruppo.

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>Utilizzare Criteri di gruppo per pianificare le analisi dopo gli aggiornamenti della protezione

|Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata)|
|:---|:---|:---|:---|
|Aggiornamenti delle firme | Attivare l'analisi dopo l'aggiornamento di Security Intelligence | Un'analisi verrà eseguita immediatamente dopo il download di un nuovo aggiornamento della protezione | Abilitato |

## <a name="see-also"></a>Vedere anche

- [Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Configurare ed eseguire analisi di Microsoft Defender Antivirus su richiesta](run-scan-microsoft-defender-antivirus.md)
- [Configurare le opzioni di analisi di Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)