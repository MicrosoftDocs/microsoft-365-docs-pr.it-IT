---
title: Configurare le opzioni di analisi per Antivirus Microsoft Defender
description: Puoi configurare Microsoft Defender AV per analizzare i file di archiviazione della posta elettronica, i punti di backup o di analisi, i file di rete e i file archiviati (ad esempio, .zip file).
keywords: analisi avanzate, analisi, posta elettronica, archivio, zip, rar, archivio, analisi reparse
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1efa72d5b8d204b6aec1cef05fe3c8afe1ca82f7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275306"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Configurare le opzioni di analisi di Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Utilizzare Microsoft Intune per configurare le opzioni di analisi

Per [altri dettagli, vedi](/intune/device-restrictions-configure) Configurare le impostazioni di restrizione Microsoft Intune e Antivirus Microsoft Defender dispositivo per Windows 10 in [Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Utilizzare Microsoft Endpoint Manager per configurare le opzioni di analisi

Per informazioni dettagliate sulla configurazione di Microsoft Endpoint Manager (current branch), vedere How [to create and deploy antimalware policies: Scan settings.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)

## <a name="use-group-policy-to-configure-scanning-options"></a>Utilizzare Criteri di gruppo per configurare le opzioni di analisi

Per configurare le impostazioni di Criteri di gruppo descritte nella tabella seguente:

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**

3. Espandere l'albero **Windows componenti > Antivirus Microsoft Defender** e quindi il **percorso** specificato nella tabella seguente.

4. Fai doppio clic **sull'impostazione del** criterio come specificato nella tabella seguente e imposta l'opzione sulla configurazione desiderata. Fare **clic su OK** e ripetere l'operazione per tutte le altre impostazioni.

Descrizione | Posizione e impostazione | Impostazione predefinita (se non configurata) | Parametro di PowerShell `Set-MpPreference` o proprietà WMI per la `MSFT_MpPreference` classe
---|---|---|---
Analisi della posta elettronica Vedere [Limitazioni dell'analisi della posta elettronica](#ref1)| Analisi > Attivare l'analisi della posta elettronica | Disabilitato | `-DisableEmailScanning`
Analisi [dei reparse point](/windows/win32/fileio/reparse-points) | Analisi > Attiva analisi reparse point | Disabilitato | Non disponibile
Analisi delle unità di rete mappate | Analisi > eseguire l'analisi completa sulle unità di rete mappate | Disabilitato | `-DisableScanningMappedNetworkDrivesForFullScan`
 Analizzare i file di archivio (ad esempio .zip o .rar file). [L'elenco di esclusione delle](configure-extension-file-exclusions-microsoft-defender-antivirus.md) estensioni avrà la precedenza su questa impostazione. | Analisi > analizzare i file di archivio | Abilitato | `-DisableArchiveScanning`
Analizzare i file in rete | Analisi > file di rete | Disabilitato | `-DisableScanningNetworkFiles`
Eseguire l'analisi di file eseguibili imballati | Analisi > eseguire l'analisi di file eseguibili imballati | Abilitato | Non disponibile
Analizzare le unità rimovibili solo durante le analisi complete | Analisi > eseguire l'analisi delle unità rimovibili | Disabilitato | `-DisableRemovableDriveScanning`
Specificare il livello di sottocartelle all'interno di una cartella di archiviazione da analizzare | Analisi > Specificare la profondità massima per l'analisi dei file di archivio | 0 | Non disponibile
 Specifica il carico massimo della CPU (come percentuale) durante un'analisi. Nota: non si tratta di un limite rigido, ma di una guida che il motore di analisi non superi in media questo limite massimo. | Analisi > Specificare la percentuale massima di utilizzo della CPU durante un'analisi | 50 |  `-ScanAvgCPULoadFactor`
 Specificare le dimensioni massime, in kilobyte, dei file di archivio da analizzare. Il valore **predefinito, 0**, non applica alcun limite | Analisi > Specificare la dimensione massima dei file di archivio da analizzare | Nessun limite | Non disponibile
 Configurare la priorità della CPU bassa per le analisi pianificate | Analisi > La priorità della CPU bassa per le analisi pianificate | Disabilitato | Non disponibile
 
> [!NOTE]
> Se la protezione in tempo reale è attivata, i file vengono analizzati prima dell'accesso e dell'esecuzione. L'ambito di analisi include tutti i file, inclusi i file su supporti rimovibili montati, ad esempio unità USB. Se il dispositivo che esegue l'analisi ha la protezione in tempo reale o la protezione all'accesso attivata, l'analisi includerà anche condivisioni di rete.

## <a name="use-powershell-to-configure-scanning-options"></a>Utilizzare PowerShell per configurare le opzioni di analisi

Vedere [Manage Antivirus Microsoft Defender with PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Antivirus Microsoft Defender.

## <a name="use-wmi-to-configure-scanning-options"></a>Utilizzare WMI per configurare le opzioni di analisi

Per l'uso delle classi WMI, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>Limitazioni dell'analisi della posta elettronica

L'analisi della posta elettronica consente di analizzare i file di posta elettronica utilizzati da Outlook e da altri client di posta elettronica durante le analisi su richiesta e pianificate. Vengono analizzati anche gli oggetti incorporati all'interno di un file di posta elettronica, ad esempio allegati e file archiviati. È possibile analizzare e correggere i seguenti tipi di formato di file:

- DBX
- MBX
- MIME

Verranno analizzati anche i file PST utilizzati da Outlook 2003 o versioni precedenti (in cui il tipo di archivio è impostato su non Unicode), ma Windows Defender non può correggere le minacce rilevate all'interno dei file PST.

Se Antivirus Microsoft Defender rileva una minaccia all'interno di un messaggio di posta elettronica, verranno visualizzate le informazioni seguenti per facilitare l'identificazione della posta elettronica compromessa, in modo da poter correggere manualmente la minaccia:

- Oggetto e-mail
- Nome allegato

## <a name="related-topics"></a>Argomenti correlati

- [Personalizzare, avviare ed esaminare i risultati di Antivirus Microsoft Defender analisi e correzione](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Configurare ed eseguire analisi di Microsoft Defender Antivirus su richiesta](run-scan-microsoft-defender-antivirus.md)
- [Configurare le Antivirus Microsoft Defender pianificate](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)