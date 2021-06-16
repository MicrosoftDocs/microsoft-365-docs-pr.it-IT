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
ms.date: 05/26/2021
ms.topic: how-to
ms.openlocfilehash: 96e4dab96f8ceb149916c908991079bb2dfa866f
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964898"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Configurare le opzioni di analisi di Microsoft Defender Antivirus

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Utilizzare Microsoft Intune per configurare le opzioni di analisi

Per ulteriori informazioni, vedere [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and Antivirus Microsoft Defender device restriction settings for Windows 10 in [Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus). 

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Utilizzare Microsoft Endpoint Manager per configurare le opzioni di analisi

Per informazioni dettagliate sulla configurazione Microsoft Endpoint Manager (ramo corrente), vedere [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).

## <a name="use-group-policy-to-configure-scanning-options"></a>Utilizzare Criteri di gruppo per configurare le opzioni di analisi

1. Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.

3. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**

4. Espandere l'albero **Windows componenti** Antivirus Microsoft Defender e quindi selezionare un percorso (vedere Impostazioni  >   [e posizioni](#settings-and-locations) in questo articolo).


5. Modificare l'oggetto criterio. 

6. Fare **clic su OK** e ripetere l'operazione per tutte le altre impostazioni.

### <a name="settings-and-locations"></a>Impostazioni e posizioni

| Elemento e percorso dei criteri | Impostazione predefinita (se non configurata) | Parametro di PowerShell `Set-MpPreference` o proprietà WMI per la `MSFT_MpPreference` classe |
|---|---|---|
| Analisi della posta elettronica <p> **Analisi**  >  **Attivare l'analisi della posta elettronica**<p>Vedere [Limitazioni dell'analisi della posta](#email-scanning-limitations) elettronica (in questo articolo) | Disattivato | `-DisableEmailScanning` |
|Analisi [dei reparse point](/windows/win32/fileio/reparse-points) <p> **Analisi**  >  **Attivare l'analisi dei reparse point** | Disattivato | Non disponibile <p>Vedere [Reparse points](/windows/win32/fileio/reparse-points)  |
| Analisi delle unità di rete mappate <p> **Analisi**  >  **Eseguire l'analisi completa sulle unità di rete mappate** | Disattivato | `-DisableScanningMappedNetworkDrivesForFullScan`|
| Analizzare i file di archivio (ad esempio .zip o .rar file).  <p> **Analisi**  >  **Analizzare i file di archivio** | Abilitato | `-DisableArchiveScanning` <p>[L'elenco di esclusione delle](configure-extension-file-exclusions-microsoft-defender-antivirus.md) estensioni avrà la precedenza su questa impostazione.|
| Analizzare i file in rete <p> **Analisi**  >  **Analizzare i file di rete** | Disattivato | `-DisableScanningNetworkFiles` |
| Eseguire l'analisi di file eseguibili imballati <p> **Analisi**  >  **Eseguire l'analisi di file eseguibili imballati** | Abilitato | Non disponibile |
| Analizzare le unità rimovibili solo durante le analisi complete <p> **Analisi**  >  **Analisi delle unità rimovibili** | Disattivato | `-DisableRemovableDriveScanning` |
| Specificare il livello di sottocartelle all'interno di una cartella di archiviazione da analizzare <p>**Analisi**  >  **Specificare la profondità massima per l'analisi dei file di archivio** | 0 | Non disponibile |
| Specifica il carico massimo della CPU (come percentuale) durante un'analisi. <p> **Analisi**  >  **Specificare la percentuale massima di utilizzo della CPU durante un'analisi** | 50 |  `-ScanAvgCPULoadFactor` <p>**NOTA:** il carico massimo della CPU non è un limite rigido, ma è una guida per il motore di analisi per non superare il massimo in media. Le analisi eseguite manualmente ignoreranno questa impostazione e verranno eseguite senza limiti di CPU. |
| Specificare le dimensioni massime, in kilobyte, dei file di archivio da analizzare. <p> **Analisi**  >  **Specificare la dimensione massima dei file di archivio da analizzare** | Nessun limite | Non disponibile <p>Il valore predefinito 0 non applica alcun limite |
| Configurare la priorità della CPU bassa per le analisi pianificate <p> **Analisi**  >  **Configurare la priorità della CPU bassa per le analisi pianificate** | Disattivato | Non disponibile |

 
> [!NOTE]
> Se la protezione in tempo reale è attivata, i file vengono analizzati prima dell'accesso e dell'esecuzione. L'ambito di analisi include tutti i file, inclusi i file su supporti rimovibili montati, ad esempio unità USB. Se il dispositivo che esegue l'analisi ha la protezione in tempo reale o la protezione all'accesso attivata, l'analisi includerà anche condivisioni di rete.

## <a name="use-powershell-to-configure-scanning-options"></a>Utilizzare PowerShell per configurare le opzioni di analisi


Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere

- [Gestire Antivirus Microsoft Defender con i cmdlet di PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Cmdlet defender](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>Utilizzare WMI per configurare le opzioni di analisi

Vedi [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="email-scanning-limitations"></a>Limitazioni dell'analisi della posta elettronica

L'analisi della posta elettronica consente di analizzare i file di posta elettronica utilizzati da Outlook e da altri client di posta elettronica durante le analisi su richiesta e pianificate. Vengono analizzati anche gli oggetti incorporati all'interno della posta elettronica, ad esempio allegati e file archiviati. È possibile analizzare e correggere i seguenti tipi di formato di file:

- DBX
- MBX
- MIME

Vengono analizzati anche i file PST utilizzati da Outlook 2003 o versioni precedenti (in cui il tipo di archivio è impostato su non Unicode), ma Antivirus Microsoft Defender non è in grado di correggere le minacce rilevate all'interno dei file PST.

Se Antivirus Microsoft Defender rileva una minaccia all'interno di un messaggio di posta elettronica, verranno visualizzate le informazioni seguenti per facilitare l'identificazione della posta elettronica compromessa, in modo da poter correggere manualmente la minaccia:

- Oggetto e-mail
- Nome allegato


## <a name="scanning-mapped-network-drives"></a>Analisi delle unità di rete mappate

In qualsiasi sistema operativo, vengono analizzate solo le unità di rete mappate a livello di sistema. Le unità di rete mappate a livello utente non vengono analizzate. Le unità di rete mappate a livello di utente sono quelle mappate manualmente da un utente nella sessione e utilizzando le proprie credenziali.

## <a name="see-also"></a>Vedere anche


- [Personalizzare, avviare ed esaminare i risultati di Antivirus Microsoft Defender analisi e correzione](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Configurare ed eseguire analisi di Microsoft Defender Antivirus su richiesta](run-scan-microsoft-defender-antivirus.md)
- [Configurare le Antivirus Microsoft Defender pianificate](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
