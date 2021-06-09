---
title: Esportare un report di Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Anziché esportare i risultati effettivi di una ricerca di contenuto nel Centro sicurezza & conformità in Office 365, è possibile esportare un report dei risultati della ricerca. Il report contiene un riepilogo dei risultati della ricerca e un documento con informazioni dettagliate su ogni elemento da esportare.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311574"
---
# <a name="export-a-content-search-report"></a>Esportare il rapporto della Ricerca contenuto

Anziché esportare il set completo di risultati della ricerca da una ricerca contenuto nel Centro conformità Microsoft 365 (o da una ricerca associata a un caso di eDiscovery di base), è possibile esportare gli stessi report generati quando si esportano i risultati della ricerca effettivi.
  
Quando si esporta un report, i file di report vengono scaricati in una cartella del computer locale con lo stesso nome di Ricerca contenuto, ma accodati con *_ReportsOnly*. Ad esempio, se la ricerca contenuto è denominata  *ContosoCase0815,* il report viene scaricato in una cartella denominata *ContosoCase0815_ReportsOnly*. Per un elenco dei documenti inclusi nel report, vedere [What's included in the report](#whats-included-in-the-report).

## <a name="before-you-export-a-search-report"></a>Prima di esportare un report di ricerca

- Per esportare un report di ricerca, è necessario disporre del ruolo di gestione ricerca di conformità nel Centro sicurezza & conformità. Questo ruolo viene assegnato per impostazione predefinita ai gruppi di ruoli Gestione eDiscovery e Gestione organizzazione incorporati. Per altre informazioni, vedere [Assegnare autorizzazioni di eDiscovery](assign-ediscovery-permissions.md).

- Quando si esporta un report, i dati vengono temporaneamente archiviati in un percorso Archiviazione di Azure nel cloud Microsoft prima di essere scaricati nel computer locale. Assicurati che l'organizzazione possa connettersi all'endpoint in Azure, che è **\* .blob.core.windows.net** (il carattere jolly rappresenta un identificatore univoco per l'esportazione). I dati dei risultati della ricerca vengono eliminati dalla posizione Archiviazione di Azure due settimane dopo la creazione.

- Il computer utilizzato per esportare i risultati della ricerca deve soddisfare i seguenti requisiti di sistema:

  - Versione più recente Windows (32 bit o 64 bit)

  - Microsoft .NET Framework 4.7

- Per eseguire lo strumento di esportazione di eDiscovery<sup>1,</sup>è necessario utilizzare uno dei browser supportati seguenti:

  - Microsoft Edge <sup>2</sup>

    OPPURE

  - Microsoft Internet Explorer 10 e versioni successive

  > [!NOTE]
  > <sup>1</sup> Microsoft non produce estensioni o componenti aggiuntivi di terze parti per ClickOnce applicazioni. L'esportazione dei risultati della ricerca con un browser non supportato con estensioni o componenti aggiuntivi di terze parti non è supportata.<br/>
  > <sup>2</sup> In seguito alle recenti modifiche apportate al Microsoft Edge, il ClickOnce non è più abilitato per impostazione predefinita. Per istruzioni sull'abilitazione del ClickOnce in Edge, vedere [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).

- Se le dimensioni totali stimate dei risultati restituiti dalla ricerca superano i 2 TB, l'esportazione dei report ha esito negativo. Per esportare correttamente i report, provare a restringere l'ambito ed eseguire di nuovo la ricerca in modo che la dimensione stimata dei risultati sia inferiore a 2 TB.

- Se i risultati di una ricerca sono precedenti a 7 giorni e si invia un processo di report di esportazione, viene visualizzato un messaggio di errore in cui viene richiesto di eseguire di nuovo la ricerca per aggiornare i risultati della ricerca. In questo caso, annullare l'esportazione, eseguire di nuovo la ricerca e quindi avviare di nuovo l'esportazione.

- L'esportazione dei report di ricerca viene eseguita in base al numero massimo di esportazioni in esecuzione contemporaneamente e al numero massimo di esportazioni che un singolo utente può eseguire. Per ulteriori informazioni sui limiti di esportazione, vedere [Export Content search results](export-search-results.md#export-limits).
  
## <a name="step-1-generate-the-report-for-export"></a>Passaggio 1: Generare il report per l'esportazione

Il primo passaggio consiste nel preparare il report per il download nel computer in uso. Quando si esporta il report, i documenti del report vengono caricati in un'area Archiviazione di Azure nel cloud Microsoft.
  
1. Nel Centro Microsoft 365 conformità selezionare la ricerca contenuto da cui si desidera esportare il report.
  
2. Scegliere **Esporta** report dal menu Azioni nella parte inferiore della pagina del riquadro a comparsa **di ricerca.**

   ![Opzione Esporta report nel menu Azioni](../media/ActionMenuExportReport.png)

   Viene **visualizzata la** pagina a comparsa Esporta report. Le opzioni del report di esportazione disponibili per esportare le informazioni sulla ricerca dipendono dal fatto che i risultati della ricerca si trovino nelle cassette postali o nei siti o in una combinazione di entrambi.
  
3. In **Opzioni di output** scegliere una delle opzioni seguenti:
  
   ![Opzioni di esportazione dell'output](../media/ExportOutputOptions.png)

    - Tutti gli elementi, esclusi quelli con formato non riconosciuto, vengono crittografati o non sono stati **indicizzati per altri motivi.** Questa opzione esporta solo informazioni sugli elementi indicizzati.
  
    - Tutti gli elementi, inclusi quelli con formato non riconosciuto, vengono crittografati o non sono stati **indicizzati per altri motivi.** Questa opzione esporta informazioni sugli elementi indicizzati e non indicizzati.
  
    - **Solo gli elementi con un** formato non riconosciuto, crittografati o non indicizzati per altri motivi. Questa opzione esporta solo informazioni sugli elementi non indicizzati.

4. Configurare **l'opzione Abilita deduplicazione per Exchange contenuto.**
  
   - Se si seleziona questa opzione, il conteggio dei messaggi duplicati (prima della deduplicazione e dopo la deduplicazione) viene incluso nel rapporto riepilogativo dell'esportazione. Inoltre, solo una copia di un messaggio verrà inclusa nel file manifest.xml. Tuttavia, il report dei risultati dell'esportazione conterrà una riga per ogni copia di un messaggio duplicato in modo da poter identificare le cassette postali che contengono una copia del messaggio duplicato. Per ulteriori informazioni sui report esportati, vedere [What's included in the report](#whats-included-in-the-report).

   - Se non si seleziona questa opzione, i rapporti di esportazione conterranno informazioni su tutti i messaggi restituiti dalla ricerca, inclusi i duplicati.

     Per ulteriori informazioni sulla deduplicazione e su come vengono identificati gli elementi duplicati, vedere [De-duplicazione nei risultati della ricerca eDiscovery.](de-duplication-in-ediscovery-search-results.md)

5. Fare **clic su Genera report**.

   I report di ricerca sono preparati per il download, il che significa che i documenti del report vengono caricati in un percorso Archiviazione di Azure nel cloud Microsoft. Questa operazione può richiedere diversi minuti.

Per istruzioni su come scaricare i report di ricerca esportati, vedere la sezione successiva.
  
## <a name="step-2-download-the-report"></a>Passaggio 2: scaricare il report

Il passaggio successivo consiste nel scaricare il report dall'area Archiviazione di Azure nel computer locale.

1. Nella pagina **Ricerca contenuto** nel Centro Microsoft 365 conformità selezionare la **scheda** Esportazioni
  
   Potrebbe essere necessario fare clic **su Aggiorna** per aggiornare l'elenco dei processi di esportazione in modo che venga visualizzato il processo di esportazione creato. I processi di report di esportazione hanno lo stesso nome della ricerca corrispondente **_ReportsOnly** aggiunto al nome di ricerca.
  
2. Selezionare il processo di esportazione creato nel passaggio 1.

3. Nella pagina **a comparsa Esporta report** in Chiave di **esportazione** fare clic su Copia **negli Appunti.** Questa chiave viene utilizzata nel passaggio 6 per scaricare i risultati della ricerca.
  
   > [!IMPORTANT]
   > Poiché chiunque può installare e avviare lo strumento di esportazione di eDiscovery e quindi utilizzare questa chiave per scaricare il report di ricerca, assicurarsi di adottare precauzioni per proteggere questa chiave proprio come si proteggono le password o altre informazioni correlate alla sicurezza.

4. Nella parte superiore della pagina a comparsa fare clic su **Scarica risultati.**

5. Se viene richiesto di installare lo strumento di **esportazione di eDiscovery,** fare clic su **Installa**.

6. Nello strumento **di esportazione eDiscovery** eseguire le operazioni seguenti:

   ![Strumento di esportazione eDiscovery](../media/eDiscoveryExportTool.png)

   1. Incollare la chiave di esportazione copiata nel passaggio 3 nella casella appropriata.
  
   2. Fare **clic su** Sfoglia per specificare il percorso in cui si desidera scaricare i file di report di ricerca.

7. Fare clic su **Avvia** per scaricare i risultati della ricerca nel computer.
  
    Lo **Strumento di esportazione eDiscovery** consente di visualizzare informazioni sullo stato delle informazioni relative al processo di esportazione, incluso il numero stimato (e le dimensioni) degli elementi rimanenti da scaricare. Una volta completato il processo di esportazione, è possibile accedere ai file nel percorso in cui sono stati scaricati.
  
## <a name="whats-included-in-the-report"></a>Elementi inclusi nel report

Quando si genera ed esporta un report sui risultati di una ricerca contenuto, vengono scaricati i documenti seguenti:
  
- **Riepilogo esportazione:** Un Excel contenente un riepilogo dell'esportazione. Sono incluse informazioni quali il numero di origini contenuto in cui è stata ricercata, il numero di risultati della ricerca da ogni percorso di contenuto, il numero stimato di elementi, il numero effettivo di elementi da esportare e le dimensioni stimate ed effettive degli elementi che verranno esportati.

   Se si includono elementi non indicizzati durante l'esportazione del report, il numero di elementi non indicizzati viene incluso nel numero totale di risultati di ricerca stimati e nel numero totale di risultati di ricerca scaricati (se si desidera esportare i risultati della ricerca) elencati nel rapporto riepilogativo dell'esportazione. In altre parole, il numero totale di elementi che verrebbero scaricati è uguale al numero totale di risultati stimati e al numero totale di elementi non indicizzati.
  
- **Manifesto:** File manifesto (in formato XML) contenente informazioni su ogni elemento incluso nei risultati della ricerca. Se è stata abilitata l'opzione di deduplicazione, i messaggi duplicati non vengono inclusi nel file manifesto.

- **Risultati:** Un Excel contenente una riga con informazioni su ogni elemento indicizzato che verrà esportato con i risultati della ricerca. Per la posta elettronica, il log dei risultati contiene informazioni su ogni messaggio, tra cui: 

  - Il percorso del messaggio nella cassetta postale di origine (e se il messaggio è nella cassetta postale principale o di archiviazione).

  - La data in cui è stato inviato o ricevuto il messaggio.

  - La riga dell'oggetto del messaggio.

  - Il mittente e i destinatari del messaggio.

  Per i documenti SharePoint e OneDrive for Business, il registro dei risultati contiene informazioni su ogni documento, tra cui:

  - L'URL per il documento.

  - L’URL per la raccolta di siti in cui si trova il documento.

  - La data dell'ultima modifica al documento.

  - Il nome del documento (che si trova nella colonna Oggetto nel log dei risultati).

  > [!NOTE]
  > Il numero di righe nel report **Risultati** deve essere uguale al numero totale di risultati della ricerca meno il numero totale di elementi elencati nel report **Elementi non indicizzati.**
  
- **Trace.log**: Registro di traccia contenente informazioni dettagliate sulla registrazione del processo di esportazione e che consente di individuare i problemi durante l'esportazione. Se si apre un ticket con il supporto tecnico Microsoft per un problema relativo all'esportazione dei report di ricerca, potrebbe essere richiesto di fornire questo registro di traccia.

- **Elementi non indicizzati:** Un Excel contenente informazioni su eventuali elementi non indicizzati inclusi nei risultati della ricerca. Se non si includono elementi non indicizzati quando si genera il report dei risultati della ricerca, il report verrà comunque scaricato, ma sarà vuoto.
