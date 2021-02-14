---
title: Esaminare le conversazioni in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come usare la funzionalità di ricostruzione delle conversazioni in Advanced eDiscovery per ricostruire, rivedere ed esportare conversazioni in thread.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf5c39f567240b58546dbeb353e3e461e9b69e48
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358344"
---
# <a name="review-conversations-in-advanced-ediscovery"></a>Esaminare le conversazioni in Advanced eDiscovery 

La messaggistica istantanea è un modo pratico per porre domande, condividere idee o comunicare rapidamente tra grandi gruppi di destinatari. Poiché le piattaforme di messaggistica istantanea, come Microsoft Teams, diventano fondamentali per la collaborazione aziendale, le organizzazioni devono valutare il modo in cui il flusso di lavoro di eDiscovery affronta queste nuove forme di comunicazione e collaborazione. 

La funzionalità di ricostruzione delle conversazioni in Advanced eDiscovery è progettata per facilitare l'identificazione del contenuto contestuale e la produzione di visualizzazioni di conversazione distinte. Questa funzionalità consente di esaminare in modo efficiente e rapido conversazioni complete di messaggistica istantanea (denominate anche conversazioni in *thread)* generate in piattaforme come Microsoft Teams.

Con la ricostruzione delle conversazioni, puoi usare le funzionalità integrate per ricostruire, rivedere ed esportare conversazioni in thread. Utilizzare advanced eDiscovery Conversation Reconstruction per:

- Conservare metadati univoci a livello di messaggio in tutti i messaggi all'interno di una conversazione.

- Raccogliere i messaggi contestuali relativi ai risultati della ricerca.

- Rivedere, annotare e redigere conversazioni in thread.

- Esportare singoli messaggi o conversazioni in thread

## <a name="terminology"></a>Terminologia

Ecco alcune definizioni utili per iniziare a usare la ricostruzione delle conversazioni.

- **Messaggi:** Rappresenta l'unità più piccola di una conversazione. I messaggi possono variare in base alle dimensioni, alla struttura e ai metadati. 

- **Conversazione:** Rappresenta un raggruppamento di uno o più messaggi. Nelle diverse applicazioni, le conversazioni possono essere rappresentate in modi diversi. In alcune applicazioni esiste un'azione esplicita che deriva dalla risposta a un messaggio esistente. Le conversazioni vengono formate in modo esplicito come risultato di questa azione dell'utente. Ad esempio, ecco uno screenshot di una conversazione di canale in Microsoft Teams.

   ![Conversazione del canale di Microsoft Teams](../media/threadedchat.png)

   In altre app (ad esempio i messaggi di chat 1xN in Teams), non esiste una catena di risposte formale e i messaggi vengono invece visualizzati come un "flat river di messaggi" all'interno di un singolo thread. In questi tipi di app, le conversazioni vengono dedote da un gruppo di messaggi che si verificano entro un determinato periodo di tempo. Questo "raggruppamento soft" di messaggi (anziché una catena di risposte) rappresenta la conversazione "avanti e indietro" su un argomento specifico di interesse. 

## <a name="step-1-run-a-search"></a>Passaggio 1: Eseguire una ricerca

Dopo aver identificato i responsabile e i percorsi dei contenuti pertinenti, è possibile creare una ricerca per trovare contenuto potenzialmente pertinente. Nella scheda **Ricerche** nel caso di Advanced eDiscovery, è possibile creare una ricerca facendo clic su Nuova ricerca **e** seguendo la procedura guidata. Per informazioni su come creare una ricerca, creare una query di ricerca e visualizzare i risultati della ricerca, vedere [Raccogliere dati per un caso.](create-search-to-collect-data.md)

## <a name="step-2-create-a-conversation-review-set"></a>Passaggio 2: Creare un insieme di recensioni di conversazione

In un insieme da rivedere, è possibile cercare, contrassegnare, annotare e redigere documenti, messaggi di posta elettronica e conversazioni in chat. In Advanced eDiscovery, è possibile personalizzare la revisione delle conversazioni, in base a singoli messaggi o conversazioni in thread. Questo è determinato dal tipo di insieme di revisione a cui si aggiungono i risultati della ricerca creata nel passaggio 1. Esistono due diversi tipi di insiemi di recensioni: 
  
  - **Set di revisioni standard:** I messaggi nelle conversazioni vengono elaborati e visualizzati come singoli elementi. 
  
  -  **Insiemi di revisioni di conversazione:** I messaggi nelle conversazioni vengono elaborati singolarmente, ma visualizzati in una visualizzazione per conversazione. In un insieme di revisioni di conversazione, è possibile annotare, contrassegnare e redigere i messaggi in una visualizzazione conversazione in thread. 

Per ulteriori informazioni su come esaminare e gestire il contenuto in un insieme da rivedere, vedere [Gestire i set di recensioni.](managing-review-sets.md) 

## <a name="step-3-enable-conversation-retrieval-options"></a>Passaggio 3: abilitare le opzioni di recupero delle conversazioni

Dopo aver esaminato e finalizzato la query di ricerca, è possibile aggiungere i risultati della ricerca a un insieme da rivedere. Quando si aggiungono i risultati della ricerca in un insieme da rivedere, i dati originali vengono copiati in un'area di archiviazione di Azure per facilitare il processo di revisione e analisi. Per ulteriori informazioni sull'aggiunta di risultati di ricerca a un insieme da rivedere, vedere [Aggiungere risultati di ricerca a un insieme da rivedere.](add-data-to-review-set.md) 

Quando si aggiungono dati dalle conversazioni a un insieme da rivedere, è possibile utilizzare le opzioni di recupero delle conversazioni per espandere la ricerca e includere messaggi contestuali. Dopo aver impostato le opzioni di recupero delle conversazioni, possono verificarsi le operazioni seguenti:

  ![Recupero conversazioni](../media/messagesandconversations.png)
  
1. Utilizzando una query con parole chiave e intervalli di date, la ricerca ha restituito un risultato *nel messaggio 3.* Questo messaggio fa parte di una conversazione più ampia, illustrata da *CRC1.* 
  
2. Quando si aggiungono i dati in un insieme da rivedere e si abilitano le opzioni di recupero della conversazione, Advanced eDiscovery tornerà indietro e raccoglierà altri elementi in *CRC1.* 
  
3. Dopo aver aggiunto gli elementi all'insieme da rivedere, è possibile esaminare tutti i singoli messaggi provenienti da *CRC1.* 

Per abilitare il recupero delle conversazioni:
  
1. Nella scheda **Ricerche** nel caso di Advanced eDiscovery, selezionare una ricerca e quindi fare clic su Aggiungi per rivedere **il set** nella pagina a comparsa.
  
2. Selezionare un insieme di recensioni esistente o crearne uno. È possibile configurare le opzioni di recupero quando si aggiungono risultati di ricerca a un insieme standard o a una revisione di conversazione.
  
3. In **Opzioni raccolta** configurare le opzioni di recupero delle conversazioni per le origini  di contenuto che si desidera espandere nella ricerca e quindi fare clic su Aggiungi per avviare il processo.  
  
4. Al termine **del processo di impostazione Aggiungi** a revisione nella **scheda** Processi, è possibile iniziare a esaminare le conversazioni.

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a>Passaggio 4: Rivedere ed esportare conversazioni in un insieme da rivedere

Dopo che il contenuto è stato elaborato e aggiunto al set di recensioni, puoi iniziare a esaminare i dati nel set di recensioni. Le funzionalità di revisione sono diverse a seconda che il contenuto sia stato aggiunto a un insieme di recensioni standard o a un insieme di recensioni di conversazione. 

### <a name="reviewing-conversations-in-a-standard-review-set"></a>Revisione delle conversazioni in un insieme di recensioni standard

In un insieme di revisione standard, i messaggi vengono elaborati e visualizzati come singoli elementi, in modo analogo al modo in cui vengono archiviati in una cartella delle cassette postali. In questo flusso di lavoro, ogni messaggio viene elaborato come elemento separato. Di conseguenza, le opzioni di riepilogo ed esportazione in thread non sono disponibili in un insieme di revisione standard. 

  ![Insieme da rivedere standard](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>Revisione delle conversazioni in un insieme di revisioni di conversazione

In un insieme di revisioni di conversazione, i singoli messaggi vengono uniti e presentati come conversazioni. In questo modo è possibile esaminare ed esportare conversazioni contestuali. 

  ![Insieme per la revisione delle conversazioni](../media/ConversationRSOptions.PNG)

Le sezioni seguenti descrivono la revisione e l'esportazione delle conversazioni in un insieme di revisioni di conversazione.

#### <a name="reviewing-conversations"></a>Revisione delle conversazioni

In un insieme di revisioni di conversazione, è possibile utilizzare le opzioni seguenti per facilitare il processo di revisione.

- **Raggruppamento per conversazione:** Raggruppa i messaggi all'interno della stessa conversazione per aiutare gli utenti a semplificare e accelerare il processo di revisione. 

- **Visualizzazione riepilogo:** Visualizza la conversazione in thread. In questa visualizzazione è possibile visualizzare l'intera conversazione e accedere ai metadati per ogni singolo messaggio.  
  
   - Visualizzare i metadati per i singoli messaggi
   
   - Scaricare singoli messaggi

- **Visualizzazione testo:** Fornisce il testo estratto per l'intera conversazione. 

- **Annotate view:** Consente di aggiungere commenti a una visualizzazione in thread della conversazione. Tutti i messaggi della conversazione condividono lo stesso documento annotato.

- **Tagging:** Quando si visualizzano le conversazioni in un insieme da rivedere, è possibile visualizzare e applicare i tag facendo clic sul **pannello Tagging** nel pannello Codifica.

- **Eseguire di nuovo la conversione della conversazione:** Quando i messaggi vengono aggiunti a un insieme di revisione delle conversazioni, viene eseguito automaticamente un processo di conversione per creare il riepilogo in thread e annotare le visualizzazioni. Se il processo di ricostruzione della conversazione ha esito negativo, è possibile rieseguire il processo facendo clic su **Azione > Crea PDF** conversazione nel set da rivedere.

#### <a name="exporting-conversations"></a>Esportazione di conversazioni

In un insieme di revisione delle conversazioni, è possibile impostare le opzioni seguenti per esportare le conversazioni:

![Opzioni di esportazione per le conversazioni](../media/export.png)

a. Opzioni dei metadati

   - **Carica file:** I metadati sono inclusi per ogni singolo messaggio, messaggio di posta elettronica e documento. In una conversazione è presente una riga per ogni messaggio. 

   - **Tag:** I tag del processo di revisione sono inclusi nel file di metadati. I messaggi di una conversazione condividono gli stessi tag. 

b. Opzioni di conversazione
  
   - **File di conversazione:** Quando si esportano i file di conversazione, la visualizzazione con annotazioni viene convertita in un file PDF e scaricata nella cartella di esportazione. I messaggi in un file di conversazione puntano alla versione PDF dello stesso file di conversazione.  
  
   - **Singoli messaggi di chat:** Quando si esportano singoli messaggi, ogni messaggio univoco nella conversazione viene esportato come elemento autonomo. Il file viene esportato nello stesso formato in cui è stato salvato nella cassetta postale. Per una conversazione specifica, si ricevono più file con estensione msg. 

     >[!NOTE]
     > Se sono state applicate annotazioni al file di conversazione, queste annotazioni non verranno trasferite ai singoli messaggi. 

c. Altre opzioni

   - **Generare file di testo per tutto il contenuto esportato:** Genera un file di testo per ogni conversazione esportata dal set di recensioni. 

   - **Sostituisci il contenuto esportato con PDF redatti:** Se i file di conversazione redatti vengono generati durante il processo di revisione, questi file sono disponibili durante l'esportazione. È possibile decidere se esportare solo i file nativi (non selezionando questa opzione) o sostituire i file nativi con le versioni dei file nativi (selezionando questa opzione), che vengono esportati come file PDF.

## <a name="more-information"></a>Altre informazioni

Per ulteriori informazioni su come esaminare i dati dei casi in Advanced eDiscovery, vedere i seguenti articoli:

- [Visualizzare i dati del caso](view-documents-in-review-set.md)

- [Analizzare i dati del caso](analyzing-data-in-review-set.md)

- [Esportare i dati del caso](exporting-data-ediscover20.md)
