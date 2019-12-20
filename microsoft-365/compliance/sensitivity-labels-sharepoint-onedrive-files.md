---
title: Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Gli amministratori possono abilitare il supporto delle etichette di riservatezza per i file Word, Excel e PowerPoint in SharePoint e OneDrive.
ms.openlocfilehash: c62db0d77ed805c607e79bf25cb9816a554cb6d2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802829"
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

È inoltre possibile applicare etichette di riservatezza a Microsoft teams, gruppi di Office 365 e siti di SharePoint. [Altre informazioni](sensitivity-labels-teams-groups-sites.md).

Se necessario, è possibile escludere l'anteprima in qualsiasi momento.

## <a name="requirements"></a>Requisiti

Queste funzionalità funzionano solo con le [etichette di riservatezza](sensitivity-labels.md). Se sono state utilizzate le etichette di Azure Information Protection, è possibile convertirle in etichette di riservatezza per abilitare queste funzionalità per i nuovi file caricati. [Informazioni su come](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Per questa anteprima, utilizzare la versione di OneDrive Sync App 19.002.0121.0008 o versioni successive su Windows e la versione 19.002.0107.0008 o versioni successive su Mac. Entrambe le versioni sono state rilasciate il 28 gennaio 2019 e sono attualmente rilasciate a tutti gli anelli. [Vedere le note sulla versione di OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Dopo aver abilitato l'anteprima, gli utenti che eseguono una versione precedente dell'app di sincronizzazione verranno invitati a aggiornarlo.

## <a name="limitations"></a>Limitazioni

- Quando si abilita questa anteprima, gli utenti che applicano un'etichetta a un file utilizzando le app desktop o mobili di Office potrebbero non essere in grado di salvare le modifiche apportate al file. In alternativa, l'app richiede agli utenti di salvare o ignorare le modifiche locali. Per evitare di perdere il lavoro, eseguire una delle operazioni seguenti:

  - Per applicare le etichette, utilizzare le versioni Web delle app di Office.

  - Chiudere un file dopo l'applicazione di un'etichetta e quindi riaprire il file per apportare altre modifiche.

- SharePoint non applica automaticamente le nuove etichette ai file esistenti già crittografati utilizzando le etichette di Azure Information Protection. Al contrario, per far funzionare le caratteristiche dopo aver abilitato l'anteprima, completare le seguenti attività:

  - Convertire le etichette di Azure Information Protection in etichette di riservatezza.

  - Scaricare i file e caricarli in SharePoint.

- SharePoint non è in grado di elaborare etichette con autorizzazioni e etichette personalizzate con date di scadenza.

- Quando gli utenti dispongono di autorizzazioni di modifica, le versioni Web delle app di Office consentono la copia indipendentemente dall'impostazione del criterio di copia nell'etichetta.

- La revoca, la verifica e la segnalazione RMS non sono supportate.

- Le app desktop di Office e le app per dispositivi mobili non supportano la CoAuthoring. Queste app continuano invece a aprire file in modalità di modifica esclusiva.

- Se un'etichetta include la crittografia, Microsoft cloud app Security non è in grado di leggere le informazioni sull'etichetta per i file in SharePoint.

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>Preparare la shell di gestione di SharePoint Online per l'anteprima

Prima di abilitare l'anteprima, verificare che sia in esecuzione SharePoint Online Management Shell versione 16.0.19418.12000 o versioni successive. Se si ha già la versione più recente, è possibile procedere e abilitare l'anteprima.

1. Se è stata installata una versione precedente di SharePoint Online Management Shell dalla raccolta di PowerShell, è possibile aggiornare il modulo eseguendo il cmdlet seguente.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. In alternativa, se è stata installata una versione precedente di SharePoint Online Management Shell dall'area download Microsoft, è anche possibile **aggiungere o rimuovere programmi** e disinstallare SharePoint Online Management Shell.

3. In un Web browser passare alla pagina Centro download e [scaricare la versione più recente di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Selezionare la lingua e quindi fare clic su **download**.

5. Scegliere tra il file x64 e x86. msi. Scaricare il file x64 se si esegue la versione di Windows a 64 bit o il file x86 se si esegue la versione a 32 bit. Se non si conosce, vedere [la versione del sistema operativo Windows in esecuzione?](https://support.microsoft.com/help/13443/windows-which-operating-system)


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
