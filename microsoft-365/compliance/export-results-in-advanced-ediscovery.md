---
title: Esportare i risultati in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: "Informazioni su come definire le opzioni per l'esportazione dei risultati da Office 365 Advanced eDiscovery, inclusa la procedura per specificare i parametri per un batch di esportazione. "
ms.openlocfilehash: 9194bc9dc44587fb03798c2107c408d2afb2ae70
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074311"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a>Esportare i risultati in Office 365 Advanced eDiscovery

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In questo argomento vengono descritte le opzioni avanzate di installazione di eDiscovery Export.
  
 **In questo argomento:**
  
- [Definizione di batch e sessioni di esportazione](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [Esportazioni incrementali e aggiuntive](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [Impostare i parametri di esportazione batch](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [Esportare i file di output dei report](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a>Definizione di batch e sessioni di esportazione
<a name="BK_Define"> </a>

Un batch di esportazione consente l'esportazione dell'elaborazione utilizzando un set di parametri definiti. Advanced eDiscovery consente di definire i batch per personalizzare ogni esportazione.
  
I parametri vengono definiti per ogni batch di esportazione. Per impostazione predefinita, viene creato un batch denominato "Export batch 01" per il primo batch di un caso. È inoltre possibile modificare il nome e la descrizione del batch.
  
Una sessione di esportazione è un'esecuzione dell'esportazione avanzata di eDiscovery all'interno di un batch di esportazione.
  
## <a name="incremental-and-additional-exports"></a>Esportazioni incrementali e aggiuntive
<a name="BK_IncrementalReports"> </a>

È possibile eseguire più sessioni di esportazione all'interno di un batch di esportazione per garantire risultati coerenti in base allo stesso modello di esportazione e ai parametri. Per ogni sessione all'interno di un batch, è possibile esportare analisi per i dati del caso appena elaborati ed elaborarli in modo incrementale.
  
Per esportare utilizzando un set di parametri diverso, è necessario innanzitutto creare un nuovo batch. La prima sessione del nuovo batch produrrà risultati per i file elaborati nel caso fino a quel momento, indipendentemente dal fatto che questi file siano stati importati ed elaborati in una o più importazioni. Ogni batch Ricalcola pivot, similitudini, inclusioni e così via. Le sessioni utilizzano i parametri definiti per il batch e non ricalcolano pivot, similitudini, inclusioni e così via per ogni esecuzione di sessione.
  
Ad esempio, si supponga che sia stato importato un caso e che i dati siano stati analizzati. Per recuperare i risultati dei messaggi di posta elettronica quasi duplicati e di threading per i dati incrementali, fare clic su **Crea sessione di esportazione** nello stesso batch precedentemente utilizzato per esportare i dati. 
  
## <a name="set-up-batch-export-parameters"></a>Impostare i parametri di esportazione batch
<a name="BK_SetUpExport"> </a>

Lo strumento di esportazione di eDiscovery viene utilizzato per esportare i risultati della ricerca da Advanced eDiscovery al computer locale. Per aumentare la velocità effettiva di trasferimento dei dati e velocizzare il processo di esportazione, è possibile configurare un'impostazione del registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Se si desidera aumentare la velocità di download, configurare l'impostazione del registro di sistema prima di impostare i parametri di esportazione. Per ulteriori informazioni, vedere [aumentare la velocità di download quando si esportano i risultati di ricerca di eDiscovery da Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).
  
1. In Advanced eDiscovery, selezionare un caso e fare clic su **Esporta** \> **installazione**.
    
    - Nell'elenco **Esporta batch** selezionare il nome del batch o esportare i risultati in batch di esportazione 01 (il batch predefinito). 
    
    - Per esportare i risultati per i nuovi file aggiunti a un caso esistente, continuare con il batch corrente. Per creare una sessione nel batch, selezionare lo stesso numero di batch e fare clic su **Crea sessione di esportazione** è possibile utilizzare questa opzione per esportare gli stessi parametri del batch precedente, in modo incrementale. 
    
    - Per esportare in un nuovo batch, fare **** ![clic su Aggiungi](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)icona e immettere un nuovo nome in **batch Name** (o accettare il valore predefinito) e una descrizione in **batch Description**. Fare clic su **OK**.
    
    - Per modificare un nome o una descrizione in batch, selezionare il nome in **batch di esportazione**, fare](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)clic su **modifica** ![icona modifica e quindi modificare i campi.
    
      > [!NOTE]
      > Dopo aver eseguito le sessioni per un batch di esportazione, non è possibile eliminarle. Inoltre, solo alcuni parametri possono essere modificati dopo l'esecuzione della prima sessione. 
  
    - Per creare un batch di esportazione duplicato, scegliere **Duplica esportazione batch** ![creare un'icona](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) del batch di esportazione duplicata e immettere un nome e una descrizione per il batch duplicato nel pannello. 
    
    - Per eliminare un batch di esportazione, scegliere **Delete** ![Delete an export batch](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)Icon.
    
    - Per visualizzare la cronologia di un batch, fare clic su cronologia **batch** ![Visualizza](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)cronologia.
    
2. In **popolamento**selezionare **Includi solo i file sopra il Punteggio di rilevanza** e/o il **batch di esportazione** se si desidera ottimizzare le impostazioni per il batch di esportazione. 
    
3. Se si seleziona **Includi solo i file sopra il Punteggio di rilevanza**, il **problema** è abilitato. Se il Punteggio di pertinenza del file è superiore al Punteggio di troncamento per il problema selezionato, il file verrà esportato a meno che non sia escluso dal filtro ' per la revisione '. 
  
    Se si seleziona **affina esportazione batch**, i pulsanti di opzione **deduplicazione** e filtro in base a' per la revisione ' sono abilitati. Se si sceglie **deduplicazione**, i file duplicati verranno filtrati in base al criterio definito [case Level (impostazione predefinita): da ogni set di file duplicati nell'intero caso, tutti tranne un file verranno deselezionati. Livello di custode: da ogni serie di file duplicati dello stesso custode, tutti tranne un file verranno deduplicati. L'output di esportazione contiene un record di tutti i file duplicati. Se si sceglie **Filtra per campo ' per la revisione '** , selezionare **modifica in metadati** per immettere le impostazioni del campo **' per la revisione '** . Selezionare **Includi file di input** per includere i file di origine nel contenuto del pacchetto. È possibile cancellare questa impostazione per velocizzare il processo di esportazione. Si noti che i file nativi verranno esportati in tutti i casi. 
    
4. In **metadati**selezionare una delle opzioni seguenti nell'elenco **modello di esportazione** (una volta per sessione). 
    
    - **Standard**: set di elementi di dati, metadati e proprietà di base. Utilizzare questa opzione quando i dati di importazione sono già stati elaborati in Advanced eDiscovery e i dati di esportazione vengono caricati in un sistema che già contiene i file. Per impostazione predefinita, le colonne dei modelli di esportazione vengono create e riempite.
    
    - **All**: set completo di metadati standard, inclusi tutti i dati di elaborazione, nonché analisi e punteggi di pertinenza. Questo modello è necessario quando Advanced eDiscovery esegue l'elaborazione e i dati dei file vengono caricati su un sistema esterno per la prima volta.
    
    - **Problemi**: selezionare **tutti i problemi** o selezionare un particolare problema creato. 
    
5. In **destinazione**:
    
    - **Scaricare nel computer locale**
    
    - **Esporta in Azure BLOB definito dall'utente**: se questa opzione è selezionata, è possibile specificare un URL del contenitore e un token SAS.
    
      > [!NOTE]
      > Dopo l'archiviazione di un pacchetto di esportazione nell'oggetto BLOB di Azure definito dall'utente, i dati non vengono più gestiti da Advanced eDiscovery; è gestito dal BLOB di Azure. Questo significa che, se si elimina il caso, i file esportati rimarranno sempre sul BLOB di Azure. 
  
    - **Save SAS token for future Export Session**: se selezionata, il token SAS verrà crittografato nel database interno di Advanced eDiscovery per un utilizzo futuro.
    
      > [!NOTE]
      > Attualmente il token SAS scade dopo un mese. Se si tenta di eseguire il download dopo più di un mese, è necessario annullare l'ultima sessione e quindi riesportarla. 
  
6. Fare clic su **modifica** per impostare le impostazioni del campo ' per la revisione '. 
    
    ![Configurare le impostazioni dei campi di revisione per un batch di esportazione](../media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
   - In **Impostazioni campo per la revisione**, in selezionare l'elenco a discesa dello **scenario** , selezionare lo scenario e l'ambito della revisione. Le impostazioni vengono visualizzate in base alla selezione.
    
      - **Verifica tutto** (impostazione predefinita): tutti i messaggi di posta elettronica, gli allegati e i documenti sono selezionati per impostazione predefinita. 
    
      - **Esaminare tutti i contenuti univoci in un set**: inclusioni e copie univoche inclusive, allegati univoci nel livello di posta elettronica, rappresentativi da ogni serie di duplicati esatti.
    
      - **Esaminare tutto il contenuto univoco in una copia di set-no inclusive**: Inclusive, allegati univoci nel livello di posta elettronica, rappresentante da ogni serie di duplicati esatti.
    
      - **Esaminare tutti i contenuti univoci e i relativi file di famiglia**: inclusivi, allegati univoci nel livello di posta elettronica, rappresentativi da ogni serie di duplicati esatti, Espandi fino a includere file di famiglia.
    
      - **Personalizzato** (consente di definire le opzioni nella finestra di dialogo): l'impostazione predefinita consiste nel mantenere le selezioni correnti e attivare tutte le opzioni di dialogo, per consentire la selezione. Se si seleziona questa opzione, è possibile personalizzare le impostazioni per i messaggi di posta elettronica, i documenti, gli allegati e varie.
    
    - In **messaggi di posta elettronica**selezionare i messaggi di posta elettronica che si desidera esportare.
    
      - **Tutti i messaggi di posta elettronica**: (impostazione predefinita) tutti i messaggi sono selezionati.
    
      - **Inclusive**: un messaggio di posta elettronica incluso è l'ultimo messaggio di posta elettronica di un thread e contiene tutti gli altri messaggi di posta elettronica provenienti dal thread.
    
      - **Inclusioni e copie esclusive inclusive**: copie inclusive e inclusive con gli stessi soggetti, corpo e allegati; le copie uniche Inclusive sono copie univoche di questi messaggi di posta elettronica.
    
    - In **documenti**selezionare i documenti che si desidera esportare. 
    
      - **Tutti i documenti**: (impostazione predefinita) sono selezionati tutti i documenti.
    
      - **Pivot**: un file scelto come rappresentativo del set di quasi duplicati, che in genere viene utilizzato come linea di base per la revisione del set.
    
      - **Rappresentante da ogni set di duplicati esatti**: file quasi duplicati univoci (incluso il pivot).
    
    - In **allegati**selezionare gli allegati che si desidera esportare. 
    
      - **Tutti gli allegati**: (impostazione predefinita) tutti gli allegati sono selezionati.
    
      - **Allegato univoco nel caso di livello**: file di allegati univoci all'interno del caso specificato.
    
      - **Allegato univoco nel set di messaggi di posta elettronica**: file di allegati univoci all'interno del caso di posta elettronica specificato.
    
   - In**Micellaneous**, è possibile scegliere di **trattare gli allegati come documenti**, **considerare i messaggi di posta elettronica come documenti**o **espanderli in modo da includere i file della famiglia**. Quando si sceglie **Espandi per includere i file della famiglia**, per ogni file contrassegnato per la revisione, verranno contrassegnati anche tutti i file della stessa famiglia.
    
7. Scegliere **Salva** per salvare le impostazioni. 
    
8. Dopo aver specificato i parametri di esportazione, per avviare l'esportazione batch, fare clic su **Crea sessione di esportazione**.
    
    Durante l'esportazione, lo stato viene visualizzato in **stato attività**. I risultati vengono visualizzati nel **Riepilogo di esportazione**.
    
9. Nella finestra **Download file** fare clic su **copia negli Appunti** per copiare la chiave di esportazione. 
    
    ![Scaricare file](../media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
10. Fare clic su **Chiudi**. 
    
    Lo strumento di esportazione di eDiscovery è stato avviato.
    
    ![Strumento di esportazione di eDiscovery](../media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
11. Nello **strumento di esportazione di eDiscovery**:
    
    -  In **Incolla la firma di accesso condiviso che verrà utilizzata per la connessione all'origine**, incollare la chiave di esportazione che youcopied negli Appunti nel passaggio 7.
    
    - Fare clic su **Sfoglia** per selezionare il percorso di destinazione per l'archiviazione dei file di esportazione scaricati nel computer locale. 
    
    - Fare clic su **Avvia**. I file di esportazione vengono scaricati nel computer locale. Se nel passaggio 4 è stata selezionata l'opzione **Esporta in Azure BLOB definiti dall'utente** , la sessione viene esportata in una destinazione URL di archiviazione BLOB scelta.
    
Per una descrizione completa dei campi del rapporto di esportazione, vedere [Export report Fields](export-report-fields-in-advanced-ediscovery.md).
  
## <a name="export-report-output-files"></a>Esportare i file di output dei report
<a name="BK_ExportOutputFIles"> </a>

Nella tabella seguente sono elencati i file di output generati quando si esegue un batch di esportazione.
  
|**Nome file**|**Tipo file**|**Descrizione**|
|:-----|:-----|:-----|
|Riepilogo esportazione  <br/> |CSV  <br/> |File di registro generato dallo strumento di esportazione di eDiscovery.  <br/> |
|Traccia  <br/> |txt  <br/> |File di registro generato dallo strumento di esportazione di eDiscovery.  <br/> |
|File di testo estratti  <br/> |Cartella file  <br/> |Cartella che contiene i file di testo estratti dei file esportati.  <br/> |
|Input o file nativi  <br/> |Cartella file  <br/> |Cartella che contiene i file nativi e di input dei file esportati.  <br/> |
|Esporta elenco  <br/> |XLSX  <br/> |Metadati dei file esportati in formato xlsx. I campi nei file sono conformi all'utente modello selezionato per l'esportazione. Se necessario, vengono creati diversi file, ognuno contenente le righe di 100 150K. Se un determinato valore contiene più caratteri di una cella di Excel che può contenere (attualmente il limite è 32.767 caratteri), il valore verrà tagliato fino alla lunghezza massima consentita. Se viene tagliato un valore, il colore di sfondo della cella è rosso per indicare l'utente. " Partecipanti al messaggio di posta elettronica "è un esempio di un campo che può superare il limite di lunghezza, se il messaggio di posta elettronica è stato inviato a una distribuzione di grandi dimensioni. Per informazioni dettagliate sui campi di output, vedere [Export report Fields](export-report-fields-in-advanced-ediscovery.md) .  <br/> |
|Carica file  <br/> |CSV  <br/> |Metadati dei file esportati in formato CSV per il caricamento in un'altra applicazione. I campi nei file sono conformi all'utente modello selezionato per l'esportazione.  <br/> |
|Indicatore di esito positivo  <br/> |txt  <br/> |Creato solo quando viene esportato in un BLOB di Azure di terze parti. Se l'esportazione ha esito positivo, il file verrà creato. In caso di errore o di esito positivo parziale, il file non verrà creato. Il file verrà creato nella cartella radice, consentendo la verifica automatica su diversi Stati di batch/sessioni di esportazione. Si tratta di un file vuoto. Il nome è: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime. txt.  <br/> |
   
## <a name="see-also"></a>Vedere anche

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Visualizzazione della cronologia batch ed esportazione dei risultati precedenti](view-batch-history-and-export-past-results.md)
  
[Configurazione rapida di Office 365 Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md)

[Esportare i campi del report](export-report-fields-in-advanced-ediscovery.md)
  
[Aumentare la velocità di download quando si esportano i risultati di ricerca di eDiscovery da Office 365](increase-download-speeds-when-exporting-ediscovery-results.md)

