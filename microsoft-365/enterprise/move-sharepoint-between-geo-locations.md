---
title: Trasferire un sito di SharePoint in una posizione geografica diversa
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Scopri come spostare un sito SharePoint in una posizione geografica diversa all'interno dell'ambiente multi-geografico e comunicare le aspettative delle modifiche agli utenti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5a49098045dbce94ef1c474497b8da1b397ac0b0
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362355"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a>Trasferire un sito di SharePoint in una posizione geografica diversa

Con il trasferimento geografico dei siti di SharePoint, è possibile spostare siti di SharePoint in posizioni geografiche diverse all'interno del proprio ambiente multi-geografico.

È possibile trasferire da una posizione geografica a un'altra i tipi di siti seguenti:

- Microsoft 365 Siti connessi a gruppi, inclusi quelli associati a Microsoft Teams
- Siti moderni non associati a gruppi di Microsoft 365
- Siti di SharePoint classici
- Siti di comunicazioni

Per spostare un sito da una posizione geografica all'altra è necessario essere un amministratore globale o un amministratore di SharePoint.

Durante il trasferimento geografico del sito di SharePoint esiste una finestra di sola lettura di circa 4-6 ore, in base al contenuto del sito.

## <a name="best-practices"></a>Procedure consigliate

- Provare a eseguire il trasferimento di un sito di SharePoint in un sito di test per acquisire familiarità con la procedura.
- Verificare se il sito possa essere spostato prima di pianificare o eseguire lo spostamento.
- Quando è possibile, pianificare i trasferimenti di siti tra posizioni geografiche al di fuori dell'orario di ufficio, per ridurre l'impatto sugli utenti.
- Informare gli utenti interessati prima dello spostamento di siti.

## <a name="communicating-to-your-users"></a>Comunicazioni agli utenti

Quando si trasferiscono siti di SharePoint in posizioni geografiche diverse, è importante comunicare cosa avverrà agli utenti del sito, o in generale a chiunque abbia la possibilità di modificare il sito. Questo può aiutare a ridurre la confusione degli utenti e le conseguenti chiamate all'help desk. Inviare un'e-mail agli utenti prima del trasferimento per fornire loro le informazioni seguenti:

- Quando si prevede di eseguire lo spostamento e la durata del processo
- In quale posizione geografica si sta spostando il sito e l'URL per accedere alla nuova posizione
- L'indicazione di chiudere i file e non apportare modifiche durante il trasferimento.
- Le autorizzazioni di condivisione e sui file non cambieranno in seguito al trasferimento.
- Cosa aspettarsi dall'esperienza utente in ambiente multi-geografico

Assicurarsi di inviare agli utenti del sito un'e-mail nel momento in cui lo spostamento è stato completato correttamente informandoli della possibilità di riprendere a lavorare nei siti.

## <a name="scheduling-sharepoint-site-moves"></a>Pianificazione dello spostamento di siti di SharePoint

È possibile pianificare lo spostamenti di siti di SharePoint in anticipo (come descritto più avanti in questo articolo). Si possono pianificare gli spostamenti come segue:

- È possibile pianificare fino a 4.000 spostamenti alla volta.
- Una volta iniziati gli spostamenti, è possibile pianificarne di nuovi, con un massimo di 4.000 spostamenti in sospeso in coda in qualsiasi momento.

Per pianificare lo spostamento geografico di un sito di SharePoint per un momento successivo, includere uno dei parametri seguenti quando si inizia lo spostamento:

- `PreferredMoveBeginDate` - Il trasferimento inizierà probabilmente in questo orario specificato.
- `PreferredMoveEndDate` - Il trasferimento verrà probabilmente completato entro questo orario specificato, secondo il principio del best effort.

L'orario di entrambi i parametri deve essere specificato in formato UTC (Coordinated Universal Time).

## <a name="moving-the-site"></a>Trasferimento del sito

Per il trasferimento geografico di siti di SharePoint è necessario connettersi ed eseguire l'operazione dall'URL di amministrazione di SharePoint nella posizione geografica in cui è ubicato il sito.

Ad esempio, se l'URL del sito <https://contosohealthcare.sharepoint.com/sites/Turbines> è , connettersi all'URL SharePoint admin all'indirizzo <https://contosohealthcare-admin.sharepoint.com> :

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint Finestra di Online Management Shell che mostra il Connect-SPOService comando](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a>Convalida dell'ambiente

Prima di pianificare il trasferimento di un sito, è consigliabile eseguire una convalida per assicurarsi che il sito possa essere spostato.

Non è supportato il trasferimento di siti con:

- Servizi di integrazione applicativa
- Moduli di InfoPath
- Modelli applicati di Information Rights Management (IRM)

Per assicurarsi che tutte le posizioni geografiche siano compatibili, eseguire `Get-SPOGeoMoveCrossCompatibilityStatus`. Verranno mostrate tutte le posizioni geografiche e verrà indicato se l'ambiente è compatibile con la posizione geografica di destinazione.

Per eseguire un controllo di sola convalida nel sito, usare `Start-SPOSiteContentMove` con il parametro `-ValidationOnly` per verificare se il sito può essere trasferito. Ad esempio:

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

Verrà restituito *Success* se il sito è pronto per il trasferimento oppure *Fail* se sono presenti condizioni di blocco.

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a>Avviare lo spostamento geografico di un sito di SharePoint non associato a gruppi di Microsoft 365

Per impostazione predefinita, l'URL iniziale del sito diventerà l'URL della posizione geografica di destinazione. Ad esempio:

Da <https://Contoso.sharepoint.com/sites/projectx> a <https://ContosoEUR.sharepoint.com/sites/projectx>

Per i siti privi di associazioni a gruppi di Microsoft 365, è anche possibile rinominare il sito usando il parametro `-DestinationUrl`. Ad esempio:

Da <https://Contoso.sharepoint.com/sites/projectx> a <https://ContosoEUR.sharepoint.com/sites/projecty>

Per avviare il trasferimento del sito, eseguire:

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![Screenshot della finestra di PowerShell con il cmdlet Start-SPOSiteContentMove](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a>Avviare lo spostamento geografico di un sito di SharePoint a un sito connesso a un gruppo di Microsoft 365

Per trasferire un sito connesso a un gruppo di Office 365, l'amministratore globale o l’amministratore di SharePoint deve prima di tutto modificare l'attributo relativo alla posizione preferita dei dati per il gruppo di Office 365.

Per impostare la posizione preferita dei dati per un gruppo di Microsoft 365:

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

Dopo aver aggiornato il PDL, è possibile avviare il trasferimento del sito:

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a>Annullare il trasferimento geografico di un sito di SharePoint

È possibile interrompere il trasferimento geografico di un sito di SharePoint, purché non sia in corso o non sia stato completato usando il cmdlet `Stop-SPOSiteContentMove`.

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a>Determinazione dello stato del trasferimento geografico di un sito di SharePoint

È possibile determinare lo stato di un trasferimento di sito da o verso la posizione geografica a cui si è connessi con i cmdlet seguenti:

- [Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (siti non connessi a gruppi)
- [Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (siti connessi a gruppi)

Usare il parametro `-SourceSiteUrl` per specificare il sito di cui si vuole vedere lo stato di trasferimento.

Gli stati di trasferimento sono descritti nella tabella seguente.

****

|Stato|Descrizione|
|---|---|
|Ready to Trigger|Lo spostamento non è stato avviato.|
|Scheduled|Lo spostamento è in coda, ma non è ancora iniziato.|
|InProgress (n/4)|Lo spostamento è in corso in uno dei seguenti stati: Convalida (1/4), Backup (2/4), Ripristino 3/4, Pulizia (4/4).|
|Success|Lo spostamento è stato completato correttamente.|
|Failed|Lo spostamento non è riuscito.|
|

È anche possibile applicare l'opzione `-Verbose` per vedere informazioni aggiuntive sul trasferimento.

## <a name="user-experience"></a>Esperienza utente

Gli utenti del sito dovrebbero riscontrare un'interruzione minima del servizio durante il trasferimento in un'altra posizione geografica. A parte un breve periodo di disponibilità in sola lettura, i collegamenti e le autorizzazioni esistenti continueranno a funzionare come previsto al termine del trasferimento.

### <a name="site"></a>Sito

Durante il trasferimento, il sito viene impostato come di sola lettura. Al termine dello spostamento, l'utente viene indirizzato al nuovo sito nella nuova posizione geografica non fa clic su segnalibri o altri collegamenti al sito.

### <a name="permissions"></a>Autorizzazioni

Gli utenti con autorizzazioni per il sito continueranno ad avere accesso al contenuto durante il trasferimento e dopo il suo completamento.

### <a name="sync-app"></a>App di sincronizzazione

L'app di sincronizzazione rileva e trasferisce automaticamente la sincronizzazione nella nuova posizione del sito al termine dello spostamento del sito. L'utente non deve accedere di nuovo o eseguire altre operazioni. È necessaria la versione 17.3.6943.0625 o successiva dell'app di sincronizzazione.

Se un utente aggiorna un file mentre lo spostamento è in corso, l'app di sincronizzazione informerà l'utente che i caricamenti di file sono in sospeso mentre lo spostamento è in corso.

### <a name="sharing-links"></a>Condivisione dei collegamenti

Una volta completato il trasferimento geografico del sito di SharePoint, i collegamenti condivisi esistenti dei file spostati reindirizzeranno automaticamente alla nuova posizione geografica.

### <a name="most-recently-used-files-in-office-mru"></a>File usati di recente in Office (MRU)

Il servizio MRU viene aggiornato con l'URL del sito e gli URL del contenuto una volta completato il trasferimento. Questo si applica a Word, Excel e PowerPoint.

### <a name="onenote-experience"></a>Esperienza con OneNote

Il client win32 di OneNote e l'app UWP (Universal Windows Platform) rileveranno e sincronizzeranno automaticamente i blocchi appunti nella nuova posizione del sito al termine del trasferimento. L'utente non deve accedere di nuovo o eseguire altre operazioni. L'unico indicatore visibile all'utente viene mostrato in caso di sincronizzazione non riuscita del blocco appunti durante lo spostamento del sito. Questa esperienza è disponibile nelle versioni del client di OneNote seguenti:

- OneNote win32 – Versione 16.0.8326.2096 (e successive)
- OneNote UWP – Versione 16.0.8431.1006 (e successive)
- OneNote Mobile App – Versione 16.0.8431.1011 (e successive)

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>Teams (applicabile ai siti connessi a gruppi di Microsoft 365)

Al termine dello spostamento geografico del sito di SharePoint, gli utenti avranno accesso ai propri file nel sito del gruppo di Microsoft 365 nell'app Teams. Inoltre, i file condivisi tramite la chat di Teams dal proprio sito prima del trasferimento geografico continueranno a funzionare anche dopo il trasferimento.

### <a name="sharepoint-mobile-app-iosandroid"></a>App SharePoint per dispositivi mobili (iOS/Android)

L'app SharePoint per dispositivi mobili supporta l'uso di posizioni geografiche diverse ed è in grado di rilevare il trasferimento geografico del sito.

### <a name="sharepoint-workflows"></a>Flussi di lavoro di SharePoint

È necessario ripubblicare i flussi di lavoro di SharePoint 2013 dopo il trasferimento del sito. I flussi di lavoro di SharePoint 2010 continueranno a funzionare normalmente.

### <a name="apps"></a>App

Se si sposta un sito con le app, è necessario creare nuovamente un'istanza dell'app nella nuova posizione geografica, perché l'app e le relative connessioni potrebbero non essere disponibili nella posizione geografica di destinazione.

### <a name="flow"></a>Flow

Nella maggior parte dei casi, i flussi continueranno a funzionare dopo il trasferimento geografico di un sito di SharePoint. È consigliabile testarli una volta completato il trasferimento.

### <a name="powerapps"></a>PowerApps

Le PowerApp devono essere ricreate nella posizione di destinazione.

### <a name="data-movement-between-geo-locations"></a>Spostamento di dati tra posizioni geografiche

SharePoint usa l'archiviazione BLOB di Azure per il contenuto, mentre i metadati associati ai siti e i file sono archiviati in SharePoint. Dopo il trasferimento del sito dalla posizione geografica di origine a quella di destinazione, il servizio sposterà anche l'archivio BLOB associato. Gli spostamenti degli archivi BLOB vengono completati in circa 40 giorni.