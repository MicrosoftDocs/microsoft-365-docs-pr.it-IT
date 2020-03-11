---
title: Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Gli amministratori possono abilitare il supporto delle etichette di riservatezza per i file Word, Excel e PowerPoint in SharePoint e OneDrive.
ms.openlocfilehash: ba65624d0c7a67eb4a5be55a7f3e08c217039e83
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583143"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive (anteprima pubblica)

Prima di questa anteprima, quando sono state applicate etichette di riservatezza che includono la crittografia per i file di Office archiviati in SharePoint e OneDrive, il servizio non è in grado di elaborare il contenuto di tali file. La CoAuthoring, la eDiscovery, la prevenzione della perdita di dati, la ricerca, l'approfondimento e altre funzionalità di collaborazione non hanno funzionato in queste circostanze. Questa anteprima consente di abilitare queste funzionalità per i file nuovi e modificati che dispongono di un'etichetta di riservatezza applicata che include la crittografia con una chiave basata su cloud:

- SharePoint riconosce le etichette di riservatezza applicate ai file di Word, Excel e PowerPoint in SharePoint e OneDrive: mentre il file è archiviato in SharePoint, la crittografia da Azure Information Protection viene rimossa in modo che il contenuto del file possa essere elaborato. Per informazioni su come proteggere i documenti mentre sono archiviati in SharePoint, vedere [crittografia dei dati in OneDrive for business e SharePoint Online](data-encryption-in-odb-and-spo.md).

- Quando si scarica o si accede a questo file da SharePoint o OneDrive, l'etichetta di riservatezza e tutte le impostazioni di crittografia dell'etichetta vengono riapplicate con il file e tali impostazioni vengono applicate ovunque venga salvato il file. A causa di questo comportamento, accertarsi di fornire istruzioni all'utente per l'utilizzo esclusivo delle etichette per la protezione dei documenti. Per ulteriori informazioni, vedere [Opzioni di Information Rights Management (RIM) e etichette di riservatezza](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).

- Affinché SharePoint elimini la crittografia dal file al momento del caricamento, l'utente che carica il file contrassegnato e crittografato deve disporre dei diritti di utilizzo per visualizzare almeno il file. SharePoint non rimuove la crittografia dai file se l'utente non è in grado di aprirli all'esterno di SharePoint.

- Utilizzare Office sul Web (Word, Excel, PowerPoint) per aprire e modificare i file di Office che dispongono di etichette di riservatezza che applicano la crittografia. Le autorizzazioni assegnate alla crittografia vengono applicate. Con Word sul Web, è possibile utilizzare l'etichettatura automatica anche quando si modificano questi documenti.

- Office 365 eDiscovery supporta la ricerca full-text per questi file. I criteri di prevenzione della perdita di dati (DLP) riguardano i contenuti di questi file.

- Sono disponibili tre nuovi [eventi di controllo](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) per il monitoraggio delle etichette di riservatezza applicate con Office sul Web:
  - **Etichetta di riservatezza applicata al file**
  - **Etichetta di riservatezza applicata a un file modificata**
  - **Etichetta di riservatezza rimossa dal file**

> [!NOTE]
> Se la crittografia non è stata applicata con una chiave basata su cloud ma con una chiave locale, una topologia di gestione delle chiavi spesso definita "tenere la propria chiave" (HYOK), il comportamento di SharePoint non cambia con questa anteprima.
>
> Il comportamento di SharePoint non cambia anche per i file etichettati e crittografati esistenti in SharePoint prima di abilitare l'anteprima. Affinché questi file traggano vantaggio dalle nuove funzionalità, devono essere scaricati e caricati o modificati dopo aver abilitato l'anteprima. Ad esempio, verranno restituiti nei risultati di ricerca e eDiscovery.

È inoltre possibile applicare etichette di riservatezza a Microsoft teams, gruppi di Office 365 e siti di SharePoint. Per ulteriori informazioni su questa anteprima separata, vedere [use Sensitivity labels with Microsoft teams, Office 365 groups, and SharePoint sites (Public Preview)](sensitivity-labels-teams-groups-sites.md).

È sempre possibile scegliere di escludere l'anteprima in qualsiasi momento.

Guardare il video seguente (senza audio) per visualizzare le nuove funzionalità in azione:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a>Requisiti

Queste funzionalità funzionano solo con le [etichette di riservatezza](sensitivity-labels.md) . Se al momento sono presenti etichette di Azure Information Protection, prima eseguirne la migrazione in etichette di riservatezza, in modo da poter abilitare queste funzionalità per i nuovi file caricati. Per istruzioni, vedere [How to migrate Azure Information Protection labels to Unified Sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Per questa anteprima, utilizzare la versione di OneDrive Sync App 19.002.0121.0008 o versioni successive su Windows e la versione 19.002.0107.0008 o versioni successive su Mac. Entrambe le versioni sono state rilasciate il 28 gennaio 2019 e sono attualmente rilasciate a tutti gli anelli. Per ulteriori informazioni, vedere le [Note sulla versione di OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Dopo aver abilitato l'anteprima, gli utenti che eseguono una versione precedente dell'app di sincronizzazione vengono invitati a aggiornarlo.

## <a name="limitations"></a>Limitazioni

- Quando si abilita questa anteprima, gli utenti che modificano un'etichetta su un file in una cartella di sincronizzazione di OneDrive potrebbero non essere in grado di salvare le modifiche apportate al file.  Gli utenti visualizzano un [cerchio rosso con un errore di icona trasversale bianco](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)e sono invitati a salvare nuove modifiche come copia distinta.  Oltre alle modifiche alle etichette avviate dagli utenti, lo stesso comportamento può verificarsi se un amministratore modifica le impostazioni per un'etichetta pubblicata già applicata ai file scaricati nel client di sincronizzazione degli utenti.
    
    Per evitare di perdere il lavoro per questi scenari, eseguire una delle operazioni seguenti:
    - Per applicare le etichette, utilizzare le versioni Web delle app di Office.
    - Chiudere un file dopo l'applicazione di un'etichetta e quindi riaprire il file per apportare altre modifiche.

- SharePoint non applica automaticamente le etichette di riservatezza ai file esistenti già crittografati utilizzando le etichette di Azure Information Protection. Al contrario, per far funzionare le caratteristiche dopo aver abilitato l'anteprima, completare le seguenti attività:
    
    1. Assicurarsi di aver eseguito la migrazione delle etichette di Azure Information Protection in etichette di riservatezza e di pubblicarle dal centro conformità di Microsoft 365 o dall'interfaccia di amministrazione dell'etichettatura equivalente.
    
    2. Scaricare i file e quindi caricarli in SharePoint.

- SharePoint non è in grado di elaborare i file crittografati quando l'etichetta che applica la crittografia ha una delle seguenti configurazioni per la crittografia:
    - **Consenti agli utenti di assegnare le autorizzazioni quando applicano l'etichetta** e la casella di controllo per **in Word, PowerPoint ed Excel,** è selezionata l'opzione utenti per specificare le autorizzazioni. Questa impostazione viene a volte definita "autorizzazioni definite dall'utente".
    - **L'accesso degli utenti al contenuto scade** è impostato su un valore diverso da **Never**.
    
    Per le etichette con una di queste configurazioni di crittografia, le etichette non vengono visualizzate per gli utenti di Office sul Web. Inoltre, non è possibile utilizzare le nuove funzionalità di questa anteprima con i documenti contrassegnati che dispongono già di queste impostazioni di crittografia. Ad esempio, questi documenti non verranno restituiti nei risultati della ricerca, anche se sono stati aggiornati.

- Per un documento crittografato che consenta di modificare le autorizzazioni per un utente, la copia non può essere bloccata nelle versioni Web delle app di Office.

- Il sito di verifica dei documenti di Azure Information Protection non è supportato.

- Le app desktop di Office e le app per dispositivi mobili non supportano la CoAuthoring. Queste app continuano invece a aprire file in modalità di modifica esclusiva.

- Se un documento etichettato viene caricato in SharePoint e l'etichetta ha applicato la crittografia utilizzando un account di un nome dell'entità servizio, il documento non può essere aperto in Office sul Web. Gli scenari di esempio includono la sicurezza delle app cloud di Microsoft e un file inviato ai team tramite posta elettronica.

- Gli utenti possono sperimentare il salvataggio dei problemi dopo l'esecuzione offline o in modalità Sleep quando invece di usare Office per il Web, utilizzano le app desktop e per dispositivi mobili per Word, Excel o PowerPoint. Per questi utenti, quando riprendono la sessione dell'app di Office e tentano di salvare le modifiche, visualizzano un messaggio di errore di caricamento con un'opzione per salvare una copia anziché salvare il file originale. 

- I documenti che sono stati crittografati nei modi seguenti non possono essere aperti in Office sul Web:
    - Crittografia che utilizza una chiave locale ("mantenere la propria chiave" o HYOK)
    - Crittografia applicata indipendentemente da un'etichetta, ad esempio applicando direttamente un modello di protezione di Rights Management.

- Se si elimina un'etichetta applicata a un documento in SharePoint, anziché rimuovere l'etichetta dal criterio di etichetta applicabile, il documento al momento del download non verrà etichettato o crittografato. Se il documento etichettato è archiviato all'esterno di SharePoint, il documento resta crittografato se l'etichetta è stata eliminata. Si noti che, sebbene sia possibile eliminare le etichette durante la fase di testing, è molto raro eliminare un'etichetta in un ambiente di produzione.

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>Preparare la shell di gestione di SharePoint Online per l'anteprima

Prima di abilitare l'anteprima, verificare che sia in esecuzione SharePoint Online Management Shell versione 16.0.19418.12000 o versioni successive. Se si ha già la versione più recente, è possibile procedere e abilitare l'anteprima.

1. Se è stata installata una versione precedente di SharePoint Online Management Shell da PowerShell Gallery, è possibile aggiornare il modulo eseguendo il cmdlet seguente.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. In alternativa, se è stata installata una versione precedente di SharePoint Online Management Shell dall'area download Microsoft, è anche possibile **aggiungere o rimuovere programmi** e disinstallare SharePoint Online Management Shell.

3. In un Web browser passare alla pagina Area download e [scaricare l'ultima versione di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Selezionare la lingua e fare clic su **Scarica**.

5. Scegliere tra il file MSI x64 o x86. Scaricare il file x64 se si esegue la versione di Windows a 64 bit o il file x86 se si esegue la versione a 32 bit. Se non si conosce, vedere [la versione del sistema operativo Windows in esecuzione?](https://support.microsoft.com/help/13443/windows-which-operating-system)


6. Dopo aver scaricato il file, eseguire il file e seguire i passaggi illustrati nell'installazione guidata.

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a>Abilitare l'anteprima tramite Microsoft PowerShell (opt-in)

Per abilitare l'anteprima, utilizzare il cmdlet Set-SPOTenant:

1. Utilizzo di un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale o di amministrazione di SharePoint in Office 365, connettersi a SharePoint. Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

2. Eseguire il comando riportato di seguito:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>Pianificare l'implementazione dopo la creazione o la modifica di un'etichetta di riservatezza

Dopo aver creato o modificato un'etichetta di riservatezza nel centro conformità di Microsoft 365, pubblicarla in fasi. Se si pubblicano etichette che non sono state completamente sincronizzate, quando gli utenti applicano le etichette ai file e le caricano in SharePoint, i file non possono essere aperti nelle versioni Web delle app di Office. Anche le funzioni di ricerca e eDiscovery non funzionano per i file.

È consigliabile attenersi alla seguente procedura:

1. Pubblicare l'etichetta di riservatezza nuova o modificata solo su una o due persone.

2. Attendere almeno 24 ore dopo la pubblicazione iniziale. Verificare che l'etichetta sia stata completamente sincronizzata.

3. Pubblicare l'etichetta in senso più generale.

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a>Disabilitare l'anteprima tramite Microsoft PowerShell (opt-out)

Se si disattiva questa anteprima, i file caricati durante l'anteprima continueranno a essere protetti dall'etichetta. Le impostazioni corrispondenti continuano a essere applicate. Quando si applicano etichette ai nuovi file dopo aver disabilitato l'anteprima, la ricerca full-text, eDiscovery e la CoAuthoring non funzioneranno più.

Per disabilitare l'anteprima, utilizzare il cmdlet Set-SPOTenant:

1. Utilizzo di un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale o di amministrazione di SharePoint in Office 365, connettersi a SharePoint. Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

2. Eseguire il comando riportato di seguito:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
