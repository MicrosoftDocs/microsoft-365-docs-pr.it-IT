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
ms.date: 03/19/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 85fb60d8d4504ba3a4aa8744c1183d094da01a9b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274749"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Configurare e gestire Antivirus Microsoft Defender con lo mpcmdrun.exe da riga di comando

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile eseguire varie Antivirus Microsoft Defender con lo strumento da riga di comando dedicato **mpcmdrun.exe**. Questa utilità è utile quando si desidera automatizzare l Antivirus Microsoft Defender utilizzarsi. È possibile trovare l'utilità in `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . È necessario eseguirlo da un prompt dei comandi.

> [!NOTE]
> Potrebbe essere necessario aprire una versione a livello di amministratore del prompt dei comandi. Quando si cerca prompt **dei comandi** dal menu Start, scegliere Esegui **come amministratore.**
> Se si esegue una versione aggiornata di Microsoft Defender Platform, eseguire `**MpCmdRun**` dal percorso seguente: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .

L'utilità dispone dei comandi seguenti:

```console
MpCmdRun.exe [command] [-options]
```
Di seguito viene riportato un esempio:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| Comando  | Descrizione   |
|:----|:----|
| `-?` **oppure** `-h`   | Visualizza tutte le opzioni disponibili per questo strumento |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Esegue la ricerca di software dannoso. I valori **per ScanType** sono: **0** Default, in base alla configurazione, **-1** Analisi rapida, **-2** Analisi completa, **-3** Analisi personalizzata di file e directory.  CpuThrottling rispetta la limitazione della CPU configurata dal criterio |
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

|Messaggio di errore | Motivo possibile
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | Il Antivirus Microsoft Defender è disabilitato. Abilitare il servizio e riprovare. <br>   **Nota:**  In Windows 10 1909 o versioni precedenti e Windows Server 2019 o versioni precedenti, il servizio era denominato servizio "Windows Defender Antivirus".|
| `0x80070667` | Il comando viene eseguito da un computer Windows 10 versione 1607 o precedente o da Windows Server 2016 `-ValidateMapsConnection` o meno recente. Eseguire il comando da un computer Windows 10 versione 1703 o successiva o Windows Server 2019 o versione successiva.|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | Lo strumento deve essere eseguito da: o (dove gli aggiornamenti della piattaforma sono mensili ad `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` eccezione di `2012.4-0` marzo)|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | Privilegi insufficienti. Utilizzare il prompt dei comandi (cmd.exe) come amministratore.|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | Il firewall blocca la connessione o esegue l'ispezione SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | Possibili problemi correlati alla rete, come i problemi di risoluzione dei nomi|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | Il firewall blocca la connessione o esegue l'ispezione SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | Il firewall blocca la connessione o esegue l'ispezione SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | Il firewall blocca la connessione o esegue l'ispezione SSL. |

## <a name="see-also"></a>Vedere anche

- [Configurare la funzionalità di Microsoft Defender Antivirus](configure-microsoft-defender-antivirus-features.md)
- [Gestire Antivirus Microsoft Defender nell'azienda](configuration-management-reference-microsoft-defender-antivirus.md)
- [Argomenti di riferimento per gli strumenti di gestione e configurazione](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)