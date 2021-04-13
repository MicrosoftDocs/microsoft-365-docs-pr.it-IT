---
title: Pianificare analisi regolari rapide e complete con Microsoft Defender Antivirus
description: Configurare analisi ricorrenti (pianificate), inclusa la data e l'ora in cui devono essere eseguite e se vengono eseguite come analisi complete o rapide
keywords: analisi rapida, analisi completa, rapida e completa, pianificazione dell'analisi, giornaliera, settimanale, ora, pianificata, ricorrente, regolare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691305"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Configurare analisi pianificate rapide o complete di Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> Per impostazione predefinita, Microsoft Defender Antivirus verifica la presenza di un aggiornamento 15 minuti prima dell'ora di qualsiasi analisi pianificata. È possibile gestire la pianificazione per il momento in cui gli aggiornamenti di protezione [devono essere scaricati e applicati per](manage-protection-update-schedule-microsoft-defender-antivirus.md) ignorare questa impostazione predefinita. 

Oltre alla protezione sempre in tempo [](run-scan-microsoft-defender-antivirus.md) reale e alle analisi su richiesta, è possibile configurare analisi regolari e pianificate. 

È possibile configurare il tipo di analisi, quando deve essere eseguita [](manage-protection-updates-microsoft-defender-antivirus.md) e se l'analisi deve essere eseguita dopo un aggiornamento della protezione o se l'endpoint è in uso. È inoltre possibile specificare quando eseguire analisi speciali per completare la correzione.

In questo articolo viene descritto come configurare le analisi pianificate con Criteri di gruppo, cmdlet di PowerShell e WMI. È inoltre possibile configurare le analisi delle pianificazioni con [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) o Microsoft [Intune.](/mem/intune/configuration/device-restrictions-windows-10)

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>Per configurare le impostazioni di Criteri di gruppo descritte in questo articolo

1.  Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

3.  **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

4.  Fare clic **su Modelli amministrativi**.

5.  Espandi l'albero **fino ai componenti di Windows > Microsoft Defender Antivirus** e quindi alla **posizione** specificata nella tabella seguente.

6. Fai doppio clic **sull'impostazione del** criterio come specificato nella tabella seguente e imposta l'opzione sulla configurazione desiderata. 

7. Fare **clic su OK** e ripetere l'operazione per tutte le altre impostazioni.

Vedere anche gli [argomenti Gestire quando scaricare e](manage-protection-update-schedule-microsoft-defender-antivirus.md) applicare gli aggiornamenti della protezione e Impedire o consentire agli utenti di modificare [localmente le impostazioni dei](configure-local-policy-overrides-microsoft-defender-antivirus.md) criteri.

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>Analisi rapida e analisi completa e analisi personalizzata

Quando si configurano analisi pianificate, è possibile specificare se l'analisi deve essere completa o rapida.

Le analisi rapide esaminano tutti i percorsi in cui potrebbe essere registrato malware per iniziare con il sistema, ad esempio le chiavi del Registro di sistema e le cartelle di avvio note di Windows. 

In combinazione con la funzionalità di protezione sempre in tempo [reale,](configure-real-time-protection-microsoft-defender-antivirus.md) che rivede i file quando vengono aperti e chiusi e ogni volta che un utente passa a una cartella, un'analisi rapida consente di fornire una copertura avanzata sia per il malware che inizia con il sistema che con il malware a livello di kernel.  

Nella maggior parte dei casi, ciò significa che un'analisi rapida è adeguata per trovare malware non raccolto dalla protezione in tempo reale.

Un'analisi completa può essere utile negli endpoint che hanno riscontrato una minaccia malware per identificare se sono presenti componenti inattivi che richiedono una pulizia più approfondita. In questo caso, è possibile utilizzare un'analisi completa quando si esegue [un'analisi](run-scan-microsoft-defender-antivirus.md)su richiesta .

Un'analisi personalizzata consente di specificare i file e le cartelle da analizzare, ad esempio un'unità USB. 

>[!NOTE]
>Per impostazione predefinita, le analisi rapide vengono eseguite su dispositivi rimovibili montati, ad esempio unità USB.

## <a name="set-up-scheduled-scans"></a>Configurare le analisi pianificate

Le analisi pianificate verranno eseguite nel giorno e nell'ora specificate. È possibile utilizzare Criteri di gruppo, PowerShell e WMI per configurare le analisi pianificate.

>[!NOTE]
>Se un computer viene scollegato e in esecuzione a batteria durante un'analisi completa pianificata, l'analisi pianificata verrà interrotta con l'evento 1002, che indica che l'analisi è stata interrotta prima del completamento. Microsoft Defender Antivirus eseguirà un'analisi completa alla successiva ora pianificata.

### <a name="use-group-policy-to-schedule-scans"></a>Utilizzare Criteri di gruppo per pianificare le analisi

|Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata) |
|:---|:---|:---|:---|
|Analisi | Specificare il tipo di analisi da utilizzare per un'analisi pianificata | Analisi rapida |
|Analisi | Specificare il giorno della settimana per l'esecuzione di un'analisi pianificata | Specificare il giorno (o mai) in cui eseguire un'analisi. | Mai |
|Analisi | Specificare l'ora del giorno per l'esecuzione di un'analisi pianificata | Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per l'1 di notte). | 02.00 |
|Radice | Tempo attività programmato casuale |In Microsoft Defender Antivirus: randomizzare l'ora di inizio dell'analisi a qualsiasi intervallo da 0 a 4 ore. <br>In FEP/SCEP: randomizzare a qualsiasi intervallo più o meno 30 minuti. Ciò può essere utile nelle distribuzioni di vm o VDI. | Abilitato |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>Utilizzare i cmdlet di PowerShell per pianificare le analisi

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Utilizzare Windows Management Instruction (WMI) per pianificare le analisi

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

Per ulteriori informazioni e parametri consentiti, vedere:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




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

Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi"></a>Usare Windows Management Instruction (WMI)

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
ScanOnlyIfIdleEnabled
```

Per ulteriori informazioni e parametri consentiti, vedere:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>Configurare quando eseguire le analisi complete per completare la correzione

Alcune minacce potrebbero richiedere un'analisi completa per completare la rimozione e la correzione. È possibile pianificare quando eseguire queste analisi con Criteri di gruppo, PowerShell o WMI.

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

Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi"></a>Usare Windows Management Instruction (WMI)

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

Per ulteriori informazioni e parametri consentiti, vedere:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




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

Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Utilizzare Windows Management Instruction (WMI) per pianificare le analisi giornaliere

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
ScanScheduleQuickScanTime
```

Per ulteriori informazioni e parametri consentiti, vedere:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


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
- [Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)