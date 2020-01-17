---
title: Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive
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
ms.openlocfilehash: 0e164afca97818d2082ddf4053df791317e29ac5
ms.sourcegitcommit: 7705fdbcee4f8714ce044c9e120a431023f7a367
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "41218586"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive (anteprima pubblica)

In precedenza, quando sono state applicate etichette di riservatezza che includono la crittografia per i file di Office archiviati in SharePoint e OneDrive, il servizio non è in grado di elaborare il contenuto di tali file. La CoAuthoring, la eDiscovery, la prevenzione della perdita di dati, la ricerca, l'approfondimento e altre funzionalità di collaborazione non hanno funzionato in queste circostanze. Questa anteprima consente di abilitare queste caratteristiche:

- SharePoint riconosce le etichette di riservatezza applicate ai file di Word, Excel e PowerPoint in SharePoint e OneDrive. SharePoint applica anche le impostazioni che corrispondono a ciascuna etichetta.

- Quando si scarica un file da SharePoint o OneDrive, l'etichetta di riservatezza viaggia con il file e le impostazioni restano applicate.

- Applicare le etichette di riservatezza ai file di Office e aprire e modificare i file con etichette di riservatezza applicate (se le autorizzazioni dell'etichetta lo consentono) utilizzando le versioni Web di Word, Excel e PowerPoint. Con Word sul Web, è possibile utilizzare l'etichettatura automatica anche quando si modificano i documenti.

- Office 365 eDiscovery supporta la ricerca full-text nei file con etichette di riservatezza applicate. I criteri di prevenzione della perdita di dati (DLP) riguardano i contenuti di questi file.

- Sono disponibili tre nuovi eventi di controllo per il monitoraggio delle etichette di riservatezza:
  - FileSensitivityApplied
  - FileSensitivityLabelChanged
  - FileSensitivityLabelRemoved

È inoltre possibile applicare etichette di riservatezza a Microsoft teams, gruppi di Office 365 e siti di SharePoint. Per ulteriori informazioni su questa anteprima separata, vedere [use Sensitivity labels with Microsoft teams, Office 365 groups, and SharePoint sites (Public Preview)](sensitivity-labels-teams-groups-sites.md).

È sempre possibile scegliere di escludere l'anteprima in qualsiasi momento.

## <a name="requirements"></a>Requisiti

Queste funzionalità funzionano solo con le [etichette di riservatezza](sensitivity-labels.md) . Se al momento sono presenti etichette di Azure Information Protection, prima eseguirne la migrazione in etichette di riservatezza, in modo da poter abilitare queste funzionalità per i nuovi file caricati. Per istruzioni, vedere [How to migrate Azure Information Protection labels to Unified Sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Per questa anteprima, utilizzare la versione di OneDrive Sync App 19.002.0121.0008 o versioni successive su Windows e la versione 19.002.0107.0008 o versioni successive su Mac. Entrambe le versioni sono state rilasciate il 28 gennaio 2019 e sono attualmente rilasciate a tutti gli anelli. Per ulteriori informazioni, vedere le [Note sulla versione di OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Dopo aver abilitato l'anteprima, gli utenti che eseguono una versione precedente dell'app di sincronizzazione vengono invitati a aggiornarlo.

## <a name="limitations"></a>Limitazioni

- Quando si abilita questa anteprima, gli utenti che modificano un'etichetta in un file in una cartella di sincronizzazione di OneDrive potrebbero non essere in grado di salvare le modifiche apportate al file.  Gli utenti visualizzano un [cerchio rosso con un errore di icona trasversale bianco](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)e sono invitati a salvare nuove modifiche come copia distinta.  Oltre alle modifiche alle etichette avviate dagli utenti, lo stesso comportamento può verificarsi se un amministratore modifica le impostazioni per un'etichetta pubblicata già applicata ai file scaricati nel client di sincronizzazione degli utenti.
    
    Per evitare di perdere il lavoro per questi scenari, eseguire una delle operazioni seguenti:
    - Per applicare le etichette, utilizzare le versioni Web delle app di Office.
    - Chiudere un file dopo l'applicazione di un'etichetta e quindi riaprire il file per apportare altre modifiche.

- SharePoint non applica automaticamente le nuove etichette ai file esistenti già crittografati utilizzando le etichette di Azure Information Protection. Al contrario, per far funzionare le caratteristiche dopo aver abilitato l'anteprima, completare le seguenti attività:
    
    1. Assicurarsi di aver eseguito la migrazione delle etichette di Azure Information Protection in etichette di riservatezza e di pubblicarle dal centro conformità di Microsoft 365 o dall'interfaccia di amministrazione dell'etichettatura equivalente.
    
    2. Scaricare i file e caricarli in SharePoint.

- SharePoint non è in grado di elaborare i file crittografati quando l'etichetta che applica la crittografia ha una delle seguenti configurazioni per la crittografia:
    - **Consenti agli utenti di assegnare autorizzazioni quando applicano l'etichetta** e **in Word, PowerPoint ed Excel, richiedere agli utenti di specificare le autorizzazioni**
    - **L'accesso degli utenti al contenuto scade** è impostato su un valore diverso da **Never**.

- Per un documento crittografato che consenta di modificare le autorizzazioni per un utente, la copia non può essere bloccata nelle versioni Web delle app di Office.

- Il sito di verifica dei documenti di Azure Information Protection non è supportato.

- Le app desktop di Office e le app per dispositivi mobili non supportano la CoAuthoring. Queste app continuano invece a aprire file in modalità di modifica esclusiva.

- Se un'etichetta include la crittografia, Microsoft cloud app Security non è in grado di leggere le informazioni sull'etichetta per i file in SharePoint.

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>Preparare la shell di gestione di SharePoint Online per l'anteprima

Prima di abilitare l'anteprima, verificare che sia in esecuzione SharePoint Online Management Shell versione 16.0.19418.12000 o versioni successive. Se si ha già la versione più recente, è possibile procedere e abilitare l'anteprima.

1. Se è stata installata una versione precedente di SharePoint Online Management Shell dalla raccolta di PowerShell, è possibile aggiornare il modulo eseguendo il cmdlet seguente.

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
