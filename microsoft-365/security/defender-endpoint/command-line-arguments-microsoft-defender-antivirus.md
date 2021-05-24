---
title: Utilizzare la riga di comando per gestire Antivirus Microsoft Defender
description: Eseguire Antivirus Microsoft Defender analisi e configurare la protezione di nuova generazione con un'utilità della riga di comando dedicata.
keywords: eseguire windows defender scan, eseguire l'analisi antivirus dalla riga di comando, eseguire windows defender scan dalla riga di comando, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 25f038846f9dd9855823382d4e1babcf0547fed6
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636171"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Configurare e gestire Antivirus Microsoft Defender con lo mpcmdrun.exe da riga di comando

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile eseguire varie funzioni in Antivirus Microsoft Defender utilizzando lo strumento da riga di comando dedicato **mpcmdrun.exe**. Questa utilità è utile quando si desidera automatizzare Antivirus Microsoft Defender attività. È possibile trovare l'utilità in `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Eseguirlo da un prompt dei comandi.

> [!TIP]
> Potrebbe essere necessario aprire una versione a livello di amministratore del prompt dei comandi. Quando si cerca prompt **dei comandi** dal menu Start, scegliere Esegui **come amministratore.** Se si esegue una versione aggiornata di Microsoft Defender Platform, eseguire `MpCmdRun` dal percorso seguente: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` . Per ulteriori informazioni sulla piattaforma antimalware, vedere Antivirus Microsoft Defender [aggiornamenti e baseline.](manage-updates-baselines-microsoft-defender-antivirus.md)

L'utilità MpCmdRun utilizza la sintassi seguente:

```console
MpCmdRun.exe [command] [-options]
```

Di seguito viene riportato un esempio:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

In questo esempio, l'utilità MpCmdRun avvia un'analisi antivirus completa nel dispositivo.

## <a name="commands"></a>Comandi

| Comando  | Descrizione   |
|:----|:----|
| `-?`**o**`-h`   | Visualizza tutte le opzioni disponibili per lo strumento MpCmdRun |
| `-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Esegue la ricerca di software dannoso. I valori **per ScanType** sono:<p>**0** Impostazione predefinita, in base alla configurazione<p>**1 Analisi** rapida<p>**2** Analisi completa<p>**3** Analisi personalizzata di file e directory.<p>CpuThrottling viene eseguito in base alle configurazioni dei criteri |
| `-Trace [-Grouping #] [-Level #]` | Avvia l'analisi diagnostica |
| `-GetFiles [-SupportLogLocation <path>]` | Raccoglie informazioni di supporto. Vedere '[Raccolta di dati di diagnostica](collect-diagnostic-data.md)'  |
| `-GetFilesDiagTrack`  | Uguale a `-GetFiles` , ma viene restituito nella cartella Temporanea DiagTrack |
| `-RemoveDefinitions [-All]` | Ripristina l'intelligence per la sicurezza installata su una copia di backup precedente o sul set predefinito originale |
| `-RemoveDefinitions [-DynamicSignatures]` | Rimuove solo l'intelligence per la sicurezza scaricata dinamicamente |
| `-RemoveDefinitions [-Engine]` | Ripristina il motore installato precedente |
| `-SignatureUpdate [-UNC \| -MMPC]` | Controlla la disponibilità di nuovi aggiornamenti di Security intelligence |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | Ripristina o elenca gli elementi in quarantena |
| `-AddDynamicSignature [-Path]` | Carica l'intelligence dinamica per la sicurezza |
| `-ListAllDynamicSignatures` | Elenca l'intelligence dinamica per la sicurezza caricata |
| `-RemoveDynamicSignature [-SignatureSetID]` | Rimuove l'intelligence per la sicurezza dinamica |
| `-CheckExclusion -path <path>` | Controlla se un percorso è escluso |
| `-ValidateMapsConnection` | Verifica che la rete sia in grado di comunicare con il Antivirus Microsoft Defender cloud. Questo comando funziona solo su Windows 10 versione 1703 o successiva.|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Errori comuni nell'esecuzione di comandi tramite mpcmdrun.exe 

Nella tabella seguente sono elencati gli errori comuni che possono verificarsi durante l'utilizzo dello strumento MpCmdRun.

|Messaggio di errore | Motivo possibile |
|:----|:----|
| **ValidateMapsConnection non riuscito (800106BA)** **o 0x800106BA** | Il Antivirus Microsoft Defender è disabilitato. Abilitare il servizio e riprovare. Se serve aiuto per ri-abilitare Antivirus Microsoft Defender, vedi [Reinstallare/abilitare](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)Antivirus Microsoft Defender sugli endpoint.<p>   **SUGGERIMENTO**  In Windows 10 1909 o versioni precedenti e Windows Server 2019 o versioni precedenti, il servizio era in precedenza denominato *Windows Defender Antivirus*. |
| **0x80070667** | Il comando viene eseguito da un computer Windows 10 versione 1607 o precedente o da Windows Server 2016 `-ValidateMapsConnection` o meno recente. Eseguire il comando da un computer Windows 10 versione 1703 o successiva o Windows Server 2019 o versione successiva.|
| **MpCmdRun non viene riconosciuto come comando interno o esterno, programma operabile o file batch.** | Lo strumento deve essere eseguito da uno o (dove potrebbe essere diverso dal momento che gli aggiornamenti della piattaforma `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` sono `2012.4-0` mensili ad eccezione di marzo)|
| **ValidateMapsConnection non è riuscito a stabilire una connessione a MAPS (hr=80070005 httpcode=450)** | Il comando è stato tentato utilizzando privilegi insufficienti. Utilizzare il prompt dei comandi (cmd.exe) come amministratore.|
| **ValidateMapsConnection non è riuscito a stabilire una connessione a MAPS (hr=80070006 httpcode=451)** | Il firewall blocca la connessione o esegue l'ispezione SSL. |
| **ValidateMapsConnection non è riuscito a stabilire una connessione a MAPS (hr=80004005 httpcode=450)** | Possibili problemi correlati alla rete, come i problemi di risoluzione dei nomi|
| **ValidateMapsConnection non è riuscito a stabilire una connessione a MAPS (hr=0x80508015** | Il firewall blocca la connessione o esegue l'ispezione SSL. |
| **ValidateMapsConnection non è riuscito a stabilire una connessione a MAPS (hr=800722F0D** | Il firewall blocca la connessione o esegue l'ispezione SSL. |
| **ValidateMapsConnection non è riuscito a stabilire una connessione a MAPS (hr=80072EE7 httpcode=451)** | Il firewall blocca la connessione o esegue l'ispezione SSL. |

## <a name="see-also"></a>Vedere anche

- [Configurare la funzionalità di Microsoft Defender Antivirus](configure-microsoft-defender-antivirus-features.md)
- [Configurare e convalidare le connessioni di rete di Windows Defender Antivirus](configure-network-connections-microsoft-defender-antivirus.md)
- [Argomenti di riferimento per gli strumenti di gestione e configurazione](configuration-management-reference-microsoft-defender-antivirus.md)
