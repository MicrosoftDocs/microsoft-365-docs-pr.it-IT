---
title: Configurare le esclusioni per i file aperti da processi specifici
description: È possibile escludere i file dalle analisi se sono stati aperti da un processo specifico.
keywords: Microsoft Defender Antivirus, processo, esclusione, file, analisi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2fdc646cf616ff6a6fa36a83be3d2b1dd0432fbe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274617"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>Configurare le esclusioni per i file aperti dai processi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Puoi escludere i file aperti da processi specifici dalle analisi di Microsoft Defender Antivirus. Vedere [Suggerimenti per la definizione delle esclusioni](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) prima di definire gli elenchi di esclusione.

In questo articolo viene descritto come configurare gli elenchi di esclusione. 

## <a name="examples-of-exclusions"></a>Esempi di esclusioni

|Esclusione | Esempio |
|---|---|
|Qualsiasi file nel computer aperto da qualsiasi processo con un nome di file specifico | Specificando si `test.exe` escluderebbero i file aperti da: <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|Qualsiasi file nel computer aperto da qualsiasi processo in una cartella specifica | Specificando si `c:\test\sample\*` escluderebbero i file aperti da:<br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|Qualsiasi file nel computer aperto da un processo specifico in una cartella specifica | Se si specifica `c:\test\process.exe` l'esclusione dei file aperti solo da `c:\test\process.exe` |


Quando aggiungi un processo all'elenco di esclusione dei processi, Microsoft Defender Antivirus non analizza i file aperti da tale processo, indipendentemente dalla posizione in cui si trovano i file. Il processo stesso, tuttavia, verrà analizzato a meno che non sia stato aggiunto anche [all'elenco di esclusione file.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

Le esclusioni si applicano solo alla protezione e al monitoraggio sempre in tempo [reale.](configure-real-time-protection-microsoft-defender-antivirus.md) Non si applicano alle analisi pianificate o su richiesta.

Le modifiche apportate con Criteri di gruppo agli elenchi di **esclusione verranno** mostrate negli elenchi nell'app Sicurezza [di Windows.](microsoft-defender-security-center-antivirus.md) Tuttavia, le modifiche apportate nell'app Sicurezza di Windows **non verranno mostrate** negli elenchi di Criteri di gruppo.

Puoi aggiungere, rimuovere ed esaminare gli elenchi per le esclusioni in Criteri di gruppo, Microsoft Endpoint Configuration Manager, Microsoft Intune e con l'app Sicurezza di Windows e puoi usare i caratteri jolly per personalizzare ulteriormente gli elenchi.

È inoltre possibile utilizzare i cmdlet di PowerShell e WMI per configurare gli elenchi di esclusione, inclusa la revisione degli elenchi.

Per impostazione predefinita, le modifiche locali apportate agli elenchi (dagli utenti con privilegi di amministratore, le modifiche apportate con PowerShell e WMI) verranno unite agli elenchi definiti (e distribuiti) da Criteri di gruppo, Configuration Manager o Intune. Gli elenchi di Criteri di gruppo avranno la precedenza in caso di conflitti.

È possibile [configurare la modalità di unione degli](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) elenchi di esclusioni definite localmente e globalmente per consentire alle modifiche locali di ignorare le impostazioni di distribuzione gestite.

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>Configurare l'elenco di esclusioni per i file aperti da processi specificati

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Usare Microsoft Intune per escludere i file aperti da processi specificati dalle analisi

Per [altri dettagli, vedi](/intune/device-restrictions-configure) Configurare le impostazioni di restrizione dei dispositivi in Microsoft Intune e Microsoft Defender Antivirus per [Windows 10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Utilizzare Microsoft Endpoint Manager per escludere i file aperti da processi specificati dalle analisi

Vedi [Come creare e distribuire criteri antimalware: impostazioni](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) di esclusione per informazioni dettagliate sulla configurazione di Microsoft Endpoint Manager (current branch).

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Utilizzare Criteri di gruppo per escludere i file aperti da processi specificati dalle analisi

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**

3. Espandi l'albero **fino ai componenti di Windows > Microsoft Defender Antivirus > Esclusioni**.

4. Fare doppio clic **su Elabora esclusioni** e aggiungere le esclusioni:

    1. Impostare l'opzione su **Abilitato**.
    2. Nella sezione **Opzioni** fare clic su **Mostra...**.
    3. Immettere ogni processo nella propria riga nella **colonna Nome** valore. Vedere la tabella di esempio per i diversi tipi di esclusioni di processo.  Immettere **0** nella **colonna Valore** per tutti i processi.

5. Fare clic su **OK**.

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Utilizzare i cmdlet di PowerShell per escludere i file aperti da processi specificati dalle analisi

L'utilizzo di PowerShell per aggiungere o rimuovere esclusioni per i file aperti dai processi richiede l'utilizzo di una combinazione di tre cmdlet con il `-ExclusionProcess` parametro . I cmdlet sono tutti nel [modulo Defender](/powershell/module/defender/).

Il formato per i cmdlet è:

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

Gli elementi seguenti sono consentiti come \<cmdlet> :

|Azione di configurazione | Cmdlet di PowerShell |
|---|---|
|Creare o sovrascrivere l'elenco | `Set-MpPreference` |
|Aggiungi all'elenco | `Add-MpPreference` |
|Rimuovere elementi dall'elenco | `Remove-MpPreference` |

>[!IMPORTANT]
>Se è stato creato un elenco con o , utilizzando di nuovo `Set-MpPreference` `Add-MpPreference` il cmdlet verrà `Set-MpPreference` sovrascritto l'elenco esistente.

Ad esempio, il frammento di codice seguente fa in modo che le analisi di Microsoft Defender AV escludono qualsiasi file aperto dal processo specificato:

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

Per ulteriori informazioni su come usare PowerShell con Microsoft Defender Antivirus, vedere Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets.](/powershell/module/defender)

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Utilizzare Windows Management Instruction (WMI) per escludere i file aperti da processi specificati dalle analisi

Utilizzare i [ **metodi Set**, **Add** e **Remove** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
ExclusionProcess
```

**L'utilizzo di Set,** **Add** e **Remove** è analogo alle rispettive controparti in PowerShell: , `Set-MpPreference` e `Add-MpPreference` `Remove-MpPreference` .

Per altre informazioni e parametri consentiti, [vedi Windows Defender API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Usare l'app Sicurezza di Windows per escludere i file aperti da processi specificati dalle analisi

Per istruzioni, vedi Aggiungere [esclusioni nell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)

## <a name="use-wildcards-in-the-process-exclusion-list"></a>Utilizzare caratteri jolly nell'elenco di esclusione dei processi

L'utilizzo dei caratteri jolly nell'elenco di esclusione dei processi è diverso dall'utilizzo in altri elenchi di esclusione.

In particolare, non è possibile utilizzare il carattere jolly punto interrogativo ( ) e il carattere jolly asterisco ( ) può essere utilizzato solo alla fine `?` `*` di un percorso completo. È comunque possibile utilizzare variabili di ambiente (ad esempio ) come caratteri jolly per `%ALLUSERSPROFILE%` definire gli elementi nell'elenco di esclusione dei processi.

Nella tabella seguente viene descritto come utilizzare i caratteri jolly nell'elenco di esclusione dei processi:

|Carattere jolly | Esempio di utilizzo | Corrispondenze di esempio |
|:---|:---|:---|
|`*` (asterisco) <br/><br/> Sostituisce qualsiasi numero di caratteri | `C:\MyData\*` | Qualsiasi file aperto da `C:\MyData\file.exe` |
|Variabili di ambiente <br/><br/> La variabile definita viene popolata come percorso quando viene valutata l'esclusione | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | Qualsiasi file aperto da `C:\ProgramData\CustomLogFiles\file.exe` |

## <a name="review-the-list-of-exclusions"></a>Esaminare l'elenco delle esclusioni

Puoi recuperare gli elementi nell'elenco di esclusione con MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)o l'app Di sicurezza [di Windows.](microsoft-defender-security-center-antivirus.md)

Se si utilizza PowerShell, è possibile recuperare l'elenco in due modi:

- Recuperare lo stato di tutte le preferenze di Microsoft Defender Antivirus. Ogni elenco verrà visualizzato su righe separate, ma gli elementi all'interno di ogni elenco verranno combinati nella stessa riga.
- Scrivi lo stato di tutte le preferenze in una variabile e usa tale variabile solo per chiamare l'elenco specifico che ti interessa. Ogni utilizzo di `Add-MpPreference` viene scritto in una nuova riga.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Convalidare l'elenco di esclusione utilizzando MpCmdRun

Per controllare le esclusioni con lo strumento da riga di comando dedicato [mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), utilizzare il comando seguente:

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> Il controllo delle esclusioni con MpCmdRun richiede Microsoft Defender Antivirus CAMP versione 4.18.1812.3 (rilasciata a dicembre 2018) o successiva.


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Esaminare l'elenco delle esclusioni insieme a tutte le altre preferenze di Microsoft Defender Antivirus tramite PowerShell

Utilizzare il cmdlet seguente:

```PowerShell
Get-MpPreference
```

Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender)

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Recuperare un elenco di esclusioni specifico tramite PowerShell

Usa il frammento di codice seguente (immetti ogni riga come comando separato); sostituire **WDAVprefs** con qualsiasi etichetta che si desidera assegnare alla variabile:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender)

## <a name="related-articles"></a>Articoli correlati

- [Configurare e convalidare le esclusioni nelle analisi di Microsoft Defender Antivirus](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurare e convalidare le esclusioni in base al nome file, all'estensione e al percorso della cartella](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurare le esclusioni di Microsoft Defender Antivirus in Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Errori comuni da evitare quando si definiscono le esclusioni](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Personalizzare, avviare ed esaminare i risultati delle analisi e delle correzioni di Microsoft Defender Antivirus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)