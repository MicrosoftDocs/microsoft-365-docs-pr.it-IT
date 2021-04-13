---
title: Configurare e convalidare le esclusioni in base all'estensione, al nome o alla posizione
description: Escludere i file dalle analisi di Microsoft Defender Antivirus in base all'estensione, al nome file o al percorso.
keywords: esclusioni, file, estensione, tipo di file, nome cartella, nome file, analisi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 74732c033ee1a8d45fe6f9a44bf641a3a9adbc13
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690294"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a>Configurare e convalidare le esclusioni in base all'estensione di file e al percorso della cartella

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> Le esclusioni di Microsoft Defender Antivirus non si applicano ad altre funzionalità di Microsoft Defender for Endpoint, tra cui il rilevamento e la risposta degli [endpoint (EDR),](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)le regole di riduzione della superficie di attacco [(ASR)](/microsoft-365/security/defender-endpoint/attack-surface-reduction)e l'accesso controllato [alle cartelle.](/microsoft-365/security/defender-endpoint/controlled-folders) I file esclusi utilizzando i metodi descritti in questo articolo possono comunque attivare avvisi EDR e altri rilevamenti. Per escludere i file in modo generale, aggiungerli agli indicatori personalizzati di Microsoft Defender for [Endpoint.](/microsoft-365/security/defender-endpoint/manage-indicators)

## <a name="exclusion-lists"></a>Elenchi di esclusione

Puoi escludere determinati file dalle analisi di Microsoft Defender Antivirus modificando gli elenchi di esclusione. **In genere, non è necessario applicare esclusioni**. Microsoft Defender Antivirus include molte esclusioni automatiche basate su comportamenti noti del sistema operativo e file di gestione tipici, ad esempio quelli utilizzati nella gestione aziendale, nella gestione dei database e in altri scenari e situazioni aziendali.

> [!NOTE]
> Le esclusioni si applicano anche ai rilevamenti di app potenzialmente indesiderate.

> [!NOTE]
> Le esclusioni automatiche si applicano solo a Windows Server 2016 e versione precedente. Queste esclusioni non sono visibili nell'app Sicurezza di Windows e in PowerShell.

In questo articolo viene descritto come configurare gli elenchi di esclusione per i file e le cartelle. Vedere [Suggerimenti per la definizione delle esclusioni](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) prima di definire gli elenchi di esclusione.

| Esclusione | Esempi | Elenco di esclusione |
|:---|:---|:---|
|Qualsiasi file con un'estensione specifica | Tutti i file con l'estensione specificata, in qualsiasi punto del computer. <p> Sintassi valida: `.test` e `test`  | Esclusioni di estensione |
|Qualsiasi file in una cartella specifica | Tutti i file nella `c:\test\sample` cartella | Esclusioni di file e cartelle |
| Un file specifico in una cartella specifica | Solo `c:\sample\sample.test` il file | Esclusioni di file e cartelle |
| Un processo specifico | Il file eseguibile `c:\test\process.exe` | Esclusioni di file e cartelle |

Gli elenchi di esclusione hanno le caratteristiche seguenti:

- Le esclusioni di cartelle si applicano a tutti i file e le cartelle in tale cartella, a meno che la sottocartella non sia un reparse point. Le sottocartelle dei reparse point devono essere escluse separatamente.
- Le estensioni di file si applicano a qualsiasi nome di file con l'estensione definita se non è definito un percorso o una cartella.

> [!IMPORTANT]
> - L'utilizzo di caratteri jolly come l'asterisco ( \* ) modificherà la modalità di interpretazione delle regole di esclusione. Per informazioni importanti sul funzionamento dei caratteri jolly, vedere la sezione Use [wildcards in the file name and folder path or extension exclusion lists.](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)
> - Non è possibile escludere le unità di rete mappate. È necessario specificare il percorso di rete effettivo.
> - Le cartelle che sono reparse point create dopo l'avvio del servizio Microsoft Defender Antivirus e che sono state aggiunte all'elenco di esclusione non verranno incluse. Devi riavviare il servizio (riavviando Windows) perché i nuovi reparse point siano riconosciuti come destinazione di esclusione valida.

Per escludere i file aperti da un processo specifico, vedere [Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).

Le esclusioni si applicano [alle analisi pianificate,](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [alle analisi su richiesta](run-scan-microsoft-defender-antivirus.md)e alla protezione in tempo [reale.](configure-real-time-protection-microsoft-defender-antivirus.md)

> [!IMPORTANT]
> Le modifiche apportate all'elenco di esclusione con Criteri di **gruppo** verranno mostrate negli elenchi nell'app [Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)
> Le modifiche apportate nell'app Sicurezza di Windows **non verranno mostrate** negli elenchi di Criteri di gruppo.

By default, local changes made to the lists (by users with administrator privileges, including changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune. Gli elenchi di Criteri di gruppo hanno la precedenza in caso di conflitti.

È possibile [configurare la modalità di unione degli](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) elenchi di esclusioni definite localmente e globalmente per consentire alle modifiche locali di ignorare le impostazioni di distribuzione gestite.

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a>Configurare l'elenco di esclusioni in base al nome della cartella o all'estensione di file

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a>Usare Intune per configurare le esclusioni di nome file, cartella o estensione di file

Fare inoltre riferimento ai seguenti articoli:
- [Configurare le impostazioni di restrizione dei dispositivi in Microsoft Intune](/intune/device-restrictions-configure)
- [Impostazioni di restrizione del dispositivo Microsoft Defender Antivirus per Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a>Usare Configuration Manager per configurare le esclusioni di file, cartelle o estensioni di file

Vedi [Come creare e distribuire criteri antimalware: impostazioni](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) di esclusione per informazioni dettagliate sulla configurazione di Microsoft Endpoint Manager (current branch).

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a>Utilizzare Criteri di gruppo per configurare le esclusioni di cartelle o estensioni di file

>[!NOTE]
>Se si specifica un percorso completo di un file, viene escluso solo tale file. Se nell'esclusione è definita una cartella, vengono esclusi tutti i file e le sottodirectory in tale cartella.

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**

3. Espandere l'albero fino **ai componenti di Windows**  >  **Esclusioni di Microsoft Defender Antivirus**  >  .

4. Apri **l'impostazione Esclusioni percorso** per la modifica e aggiungi le esclusioni.

    1. Impostare l'opzione su **Abilitato**.
    1. Nella sezione **Opzioni** fare clic su **Mostra**.
    1. Specificare ogni cartella sulla propria riga nella **colonna Nome** valore.
    1. Se si specifica un file, assicurarsi di immettere un percorso completo del file, inclusi la lettera di unità, il percorso della cartella, il nome del file e l'estensione. Immettere **0** nella **colonna** Valore.

5. Scegliere **OK**.

6. Apri **l'impostazione Esclusioni estensioni** per la modifica e aggiungi le esclusioni.

    1. Impostare l'opzione su **Abilitato**.
    1. Nella sezione **Opzioni** selezionare **Mostra**.
    1. Immettere ogni estensione di file nella propria riga nella **colonna Nome** valore.  Immettere **0** nella **colonna** Valore.

7. Scegliere **OK**.

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a>Utilizzare i cmdlet di PowerShell per configurare le esclusioni di file, cartelle o estensioni di file

L'utilizzo di PowerShell per aggiungere o rimuovere esclusioni per i file in base all'estensione, al percorso o al nome di file richiede l'utilizzo di una combinazione di tre cmdlet e del parametro dell'elenco di esclusione appropriato. I cmdlet sono tutti nel [modulo Defender](/powershell/module/defender/).

Il formato dei cmdlet è il seguente:

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

Gli elementi seguenti sono consentiti come `<cmdlet>` :

| Azione di configurazione | Cmdlet di PowerShell |
|:---|:---|
|Creare o sovrascrivere l'elenco | `Set-MpPreference` |
|Aggiungi all'elenco | `Add-MpPreference` |
|Rimuovere un elemento dall'elenco | `Remove-MpPreference` |

Gli elementi seguenti sono consentiti come `<exclusion list>` :

| Tipo di esclusione | Parametro di PowerShell |
|:---|:---|
| Tutti i file con un'estensione di file specificata | `-ExclusionExtension` |
| Tutti i file in una cartella (inclusi i file nelle sottodirectory) o in un file specifico | `-ExclusionPath` |

> [!IMPORTANT]
> Se è stato creato un elenco con o , utilizzando di nuovo `Set-MpPreference` `Add-MpPreference` il cmdlet verrà `Set-MpPreference` sovrascritto l'elenco esistente.

Ad esempio, il frammento di codice seguente fa in modo che le analisi di Microsoft Defender Antivirus escludono qualsiasi file con estensione `.test` file:

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

Per ulteriori informazioni, vedere [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a>Utilizzare Windows Management Instruction (WMI) per configurare le esclusioni di file, cartelle o estensioni di file

Utilizzare i [ **metodi Set**, **Add** e **Remove** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
ExclusionExtension
ExclusionPath
```

**L'utilizzo di Set,** **Add** e **Remove** è analogo alle rispettive controparti in PowerShell: , `Set-MpPreference` e `Add-MpPreference` `Remove-MpPreference` .

Per altre informazioni, [vedi Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a>Usare l'app Sicurezza di Windows per configurare le esclusioni di file, cartelle o estensioni di file

Per istruzioni, vedi Aggiungere [esclusioni nell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Utilizzare caratteri jolly negli elenchi di esclusione di estensione e nome file e percorso cartella

È possibile utilizzare l'asterisco, il punto interrogativo o le variabili di ambiente (ad esempio ) come caratteri jolly per definire gli elementi nell'elenco di esclusione del nome file o `*` `?` del percorso della `%ALLUSERSPROFILE%` cartella. Il modo in cui questi caratteri jolly vengono interpretati è diverso dall'utilizzo normale in altre app e lingue. Leggere questa sezione per comprendere le limitazioni specifiche.

> [!IMPORTANT]
> Esistono limitazioni chiave e scenari di utilizzo per questi caratteri jolly:
> - L'utilizzo delle variabili di ambiente è limitato alle variabili del computer e a quelle applicabili ai processi in esecuzione come account NT AUTHORITY\SYSTEM.
> - Non è possibile utilizzare un carattere jolly al posto di una lettera di unità.
> - Un `*` asterisco in un'esclusione di cartella è in posizione per una singola cartella. Utilizzare più istanze di `\*\` per indicare più cartelle annidate con nomi non specificati.

Nella tabella seguente viene descritto come utilizzare i caratteri jolly e vengono forniti alcuni esempi.


|Carattere jolly  |Esempi  |
|:---------|:---------|
|`*` (asterisco) <p> Nelle **inclusioni di nomi di file ed** estensioni di file, l'asterisco sostituisce qualsiasi numero di caratteri e si applica solo ai file nell'ultima cartella definita nell'argomento. <p> Nelle **esclusioni di cartelle,** l'asterisco sostituisce una singola cartella. Usa più `*` barre con cartelle per indicare più cartelle `\` annidate. Dopo aver trovato la corrispondenza con il numero di cartelle con caratteri jolly e con nome, vengono incluse anche tutte le sottocartelle.   | `C:\MyData\*.txt` include `C:\MyData\notes.txt` <p> `C:\somepath\*\Data` include tutti i file `C:\somepath\Archives\Data` e le relative sottocartelle e le relative `C:\somepath\Authorized\Data` sottocartelle <p> `C:\Serv\*\*\Backup` include qualsiasi file nelle `C:\Serv\Primary\Denied\Backup` sottocartelle e nelle `C:\Serv\Secondary\Allowed\Backup` relative sottocartelle e nelle relative sottocartelle     |
|`?` (punto interrogativo)  <p> Nelle **inclusioni di nomi di file ed** estensioni di file , il punto interrogativo sostituisce un singolo carattere e si applica solo ai file nell'ultima cartella definita nell'argomento. <p> Nelle **esclusioni cartella,** il punto interrogativo sostituisce un singolo carattere in un nome di cartella. Dopo aver trovato la corrispondenza con il numero di cartelle con caratteri jolly e con nome, vengono incluse anche tutte le sottocartelle.   |`C:\MyData\my?.zip` include `C:\MyData\my1.zip` <p> `C:\somepath\?\Data` include qualsiasi file in `C:\somepath\P\Data` e nelle relative sottocartelle  <p> `C:\somepath\test0?\Data` includerebbe qualsiasi file in `C:\somepath\test01\Data` e nelle relative sottocartelle          |
|Variabili di ambiente <p> La variabile definita viene popolata come percorso quando viene valutata l'esclusione.          |`%ALLUSERSPROFILE%\CustomLogFiles` includerebbe `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`         |
        

> [!IMPORTANT]
> Se si combina un argomento di esclusione file con un argomento di esclusione cartella, le regole verranno bloccate in corrispondenza della corrispondenza dell'argomento file nella cartella corrispondente e non verranno cercate corrispondenze di file in alcuna sottocartella.
> È ad esempio possibile escludere tutti i file che iniziano con "data" nelle cartelle e `c:\data\final\marked` `c:\data\review\marked` utilizzando l'argomento regola `c:\data\*\marked\date*` .
> Questo argomento, tuttavia, non corrisponde ad alcun file nelle sottocartelle in `c:\data\final\marked` o `c:\data\review\marked` .

<a id="review"></a>

### <a name="system-environment-variables"></a>Variabili di ambiente di sistema

Nella tabella seguente sono elencate e descritte le variabili di ambiente degli account di sistema. 

| Questa variabile di ambiente di sistema... | Reindirizza a questo |
|:--|:--|
| `%APPDATA%`| `C:\Users\UserName.DomainName\AppData\Roaming` |
| `%APPDATA%\Microsoft\Internet Explorer\Quick Launch` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch` |
| `%APPDATA%\Microsoft\Windows\Start Menu` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu` |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` |
| `%LOCALAPPDATA%` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%ProgramData%` | `C:\ProgramData` |
| `%ProgramFiles%` | `C:\Program Files` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles%\Windows Sidebar\Gadgets` | `C:\Program Files\Windows Sidebar\Gadgets` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles(x86)%` | `C:\Program Files (x86)` |
| `%ProgramFiles(x86)%\Common Files` | `C:\Program Files (x86)\Common Files` |
| `%SystemDrive%` | `C:` |
| `%SystemDrive%\Program Files` | `C:\Program Files` |
| `%SystemDrive%\Program Files (x86)` | `C:\Program Files (x86)` |
| `%SystemDrive%\Users` | `C:\Users` |
| `%SystemDrive%\Users\Public` | `C:\Users\Public` |
| `%SystemRoot%` | `C:\Windows` |
| `%windir%` | `C:\Windows` |
| `%windir%\Fonts` | `C:\Windows\Fonts` |
| `%windir%\Resources` | `C:\Windows\Resources` |
| `%windir%\resources\0409` | `C:\Windows\resources\0409` |
| `%windir%\system32` | `C:\Windows\System32` |
| `%ALLUSERSPROFILE%` | `C:\ProgramData` |
| `%ALLUSERSPROFILE%\Application Data` | `C:\ProgramData\Application Data` |
| `%ALLUSERSPROFILE%\Documents` | `C:\ProgramData\Documents` |
| `%ALLUSERSPROFILE%\Documents\My Music\Sample Music` | `C:\ProgramData\Documents\My Music\Sample Music` |
| `%ALLUSERSPROFILE%\Documents\My Music` | `C:\ProgramData\Documents\My Music` |
| `%ALLUSERSPROFILE%\Documents\My Pictures` | `C:\ProgramData\Documents\My Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures` | `C:\ProgramData\Documents\My Pictures\Sample Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Videos` | `C:\ProgramData\Documents\My Videos` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore` | `C:\ProgramData\Microsoft\Windows\DeviceMetadataStore` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer` | `C:\ProgramData\Microsoft\Windows\GameExplorer` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones` | `C:\ProgramData\Microsoft\Windows\Ringtones` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu` | `C:\ProgramData\Microsoft\Windows\Start Menu` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Templates` | `C:\ProgramData\Microsoft\Windows\Templates` |
| `%ALLUSERSPROFILE%\Start Menu` | `C:\ProgramData\Start Menu` |
| `%ALLUSERSPROFILE%\Start Menu\Programs` | C:\ProgramData\Start Menu\Programs |
| `%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Start Menu\Programs\Administrative Tools` | 
| `%ALLUSERSPROFILE%\Templates` | `C:\ProgramData\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\History` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History` |
| `%PUBLIC%` | `C:\Users\Public` |
| `%PUBLIC%\AccountPictures` | `C:\Users\Public\AccountPictures` |
| `%PUBLIC%\Desktop` | `C:\Users\Public\Desktop` |
| `%PUBLIC%\Documents` | `C:\Users\Public\Documents` |
| `%PUBLIC%\Downloads` | `C:\Users\Public\Downloads` |
| `%PUBLIC%\Music\Sample Music` | `C:\Users\Public\Music\Sample Music` |
| `%PUBLIC%\Music\Sample Playlists` | `C:\Users\Public\Music\Sample Playlists` |
| `%PUBLIC%\Pictures\Sample Pictures` | `C:\Users\Public\Pictures\Sample Pictures` |
| `%PUBLIC%\RecordedTV.library-ms` | `C:\Users\Public\RecordedTV.library-ms` |
| `%PUBLIC%\Videos` | `C:\Users\Public\Videos` |
| `%PUBLIC%\Videos\Sample Videos` | `C:\Users\Public\Videos\Sample Videos` | 
| `%USERPROFILE%` | `C:\Windows\System32\config\systemprofile` |
| `%USERPROFILE%\AppData\Local` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%USERPROFILE%\AppData\LocalLow` | `C:\Windows\System32\config\systemprofile\AppData\LocalLow` |
| `%USERPROFILE%\AppData\Roaming` | `C:\Windows\System32\config\systemprofile\AppData\Roaming` |


## <a name="review-the-list-of-exclusions"></a>Esaminare l'elenco delle esclusioni

È possibile recuperare gli elementi nell'elenco di esclusione utilizzando uno dei metodi seguenti:
- [Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- MpCmdRun
- PowerShell
- [App Sicurezza di Windows](microsoft-defender-security-center-antivirus.md)

>[!IMPORTANT]
>Le modifiche apportate all'elenco di esclusione con Criteri di **gruppo** verranno mostrate negli elenchi nell'app [Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)
>
>Le modifiche apportate nell'app Sicurezza di Windows **non verranno mostrate** negli elenchi di Criteri di gruppo.

Se si utilizza PowerShell, è possibile recuperare l'elenco in due modi:

- Recuperare lo stato di tutte le preferenze di Microsoft Defender Antivirus. Ogni elenco viene visualizzato su righe separate, ma gli elementi all'interno di ogni elenco vengono combinati nella stessa riga.
- Scrivi lo stato di tutte le preferenze in una variabile e usa tale variabile solo per chiamare l'elenco specifico che ti interessa. Ogni utilizzo di `Add-MpPreference` viene scritto in una nuova riga.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Convalidare l'elenco di esclusione utilizzando MpCmdRun

Per controllare le esclusioni con lo strumento da riga di comando dedicato [mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), utilizzare il comando seguente:

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

>[!NOTE]
>Il controllo delle esclusioni con MpCmdRun richiede Microsoft Defender Antivirus CAMP versione 4.18.1812.3 (rilasciata a dicembre 2018) o successiva.

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Esaminare l'elenco delle esclusioni insieme a tutte le altre preferenze di Microsoft Defender Antivirus tramite PowerShell

Utilizzare il cmdlet seguente:

```PowerShell
Get-MpPreference
```

Nell'esempio seguente vengono evidenziati gli elementi contenuti `ExclusionExtension` nell'elenco:

![Output di PowerShell per Get-MpPreference l'elenco di esclusione insieme ad altre preferenze](images/defender/wdav-powershell-get-exclusions-all.png)

Per ulteriori informazioni, vedere [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Recuperare un elenco di esclusioni specifico tramite PowerShell

Usa il frammento di codice seguente (immetti ogni riga come comando separato); sostituire **WDAVprefs** con qualsiasi etichetta che si desidera assegnare alla variabile:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

Nell'esempio seguente l'elenco viene suddiviso in nuove righe per ogni utilizzo del `Add-MpPreference` cmdlet:

![Output di PowerShell che mostra solo le voci nell'elenco di esclusione](images/defender/wdav-powershell-get-exclusions-variable.png)

Per ulteriori informazioni, vedere [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Convalidare gli elenchi di esclusioni con il file di test EICAR

È possibile verificare che gli elenchi di esclusione funzionino utilizzando PowerShell con il cmdlet o la classe `Invoke-WebRequest` .NET WebClient per scaricare un file di test.

Nel frammento di codice di PowerShell seguente sostituire *test.txt* con un file conforme alle regole di esclusione. Ad esempio, se l'estensione è `.testing` stata esclusa, sostituire `test.txt` con `test.testing` . Se si sta testando un percorso, assicurarsi di eseguire il cmdlet all'interno di tale percorso.

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

Se Microsoft Defender Antivirus segnala malware, la regola non funziona. Se non è presente alcun rapporto di malware e il file scaricato esiste, l'esclusione funziona. È possibile aprire il file per verificare che il contenuto sia identico a quello descritto nel sito Web [del file di test EICAR.](http://www.eicar.org/86-0-Intended-use.html)

È inoltre possibile utilizzare il codice di PowerShell seguente, che chiama la classe .NET WebClient per scaricare il file di test, come nel cmdlet, e sostituirec:\test.txtcon un file conforme alla regola che si sta `Invoke-WebRequest` convalidando: 

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

Se non si dispone dell'accesso a Internet, è possibile creare il proprio file di test EICAR scrivendo la stringa EICAR in un nuovo file di testo con il comando powershell seguente:

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

È inoltre possibile copiare la stringa in un file di testo vuoto e tentare di salvarla con il nome del file o nella cartella che si sta tentando di escludere.

## <a name="related-topics"></a>Argomenti correlati

- [Configurare e convalidare le esclusioni nelle analisi di Microsoft Defender Antivirus](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurare e convalidare le esclusioni per i file aperti dai processi](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Configurare le esclusioni di Microsoft Defender Antivirus in Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Errori comuni da evitare durante la definizione delle esclusioni](common-exclusion-mistakes-microsoft-defender-antivirus.md)
