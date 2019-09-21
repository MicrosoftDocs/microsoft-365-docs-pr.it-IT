---
title: Esaminare le conversazioni in Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d03df51df3c6314dcec072b5c3b8573a36c279d0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083161"
---
# <a name="review-conversations-in-advanced-ediscovery"></a>Esaminare le conversazioni in Advanced eDiscovery 

La messaggistica istantanea rappresenta un modo pratico per fare domande, condividere idee o comunicare rapidamente tra gruppi di destinatari di grandi dimensioni. Poiché le piattaforme di messaggistica istantanea, come Microsoft teams, diventano fondamentali per la collaborazione aziendale, le organizzazioni devono valutare in che modo il flusso di lavoro di eDiscovery affronta queste nuove forme di comunicazione e collaborazione. 

La funzionalità di ricostruzione della conversazione in Advanced eDiscovery è progettata per identificare il contenuto contestuale e produrre visualizzazioni di conversazione distinte. Questa funzionalità consente di esaminare in modo efficiente e rapido le conversazioni complete dei messaggi istantanei (denominate anche *conversazioni filettate*) generate in piattaforme come Microsoft teams.

Con la ricostruzione della conversazione, è possibile utilizzare le funzionalità predefinite per ricostruire, rivedere ed esportare conversazioni filettate. Utilizzare la ricostruzione avanzata della conversazione di eDiscovery per:

- Preservare i metadati a livello di messaggio univoci in tutti i messaggi all'interno di una conversazione.

- Raccogliere messaggi contestuali attorno ai risultati della ricerca.

- Esaminare, annotare e redigere conversazioni filettate.

- Esportare singoli messaggi o conversazioni filettate

## <a name="terminology"></a>Terminologia

Di seguito sono riportate alcune definizioni che consentono di iniziare a utilizzare la ricostruzione delle conversazioni.

- **Messaggi:** Rappresentano la più piccola unità di una conversazione. I messaggi possono variare in base alle dimensioni, alla struttura e ai metadati. 

- **Conversazione:** Rappresenta un raggruppamento di uno o più messaggi. Tra diverse applicazioni, le conversazioni possono essere rappresentate in modi diversi. In alcune applicazioni è presente un'azione esplicita che risulta dalla risposta a un messaggio esistente. Le conversazioni sono formate in modo esplicito a causa di questa azione dell'utente. Ad esempio, ecco uno screenshot di una conversazione di canale in Microsoft teams.

   ![Conversazione canale Microsoft Teams](media/threadedchat.png)

   In altre app (ad esempio i messaggi di chat di 1xN in teams), non esiste una catena di risposta formale e i messaggi vengono visualizzati come un "fiume di messaggi Flat" all'interno di un singolo thread. Nelle app di questo tipo, le conversazioni vengono desunte da un gruppo di messaggi che si verificano entro un determinato periodo di tempo. Questo "soft-grouping" dei messaggi (invece di una catena di risposta) rappresenta la conversazione "avanti e indietro" su un argomento specifico di interesse. 

## <a name="step-1-run-a-search"></a>Passaggio 1: eseguire una ricerca

Dopo aver identificato i depositari e i percorsi di contenuto rilevanti, è possibile creare una ricerca per trovare contenuti potenzialmente rilevanti. Nella scheda **ricerche** del caso Advanced eDiscovery, è possibile creare una ricerca facendo clic su **nuova ricerca** e seguendo la procedura guidata. Per informazioni sulla creazione di una ricerca, la creazione di una query di ricerca e la visualizzazione dei risultati della ricerca, vedere [Collect Data for a case](create-search-to-collect-data.md).

## <a name="step-2-create-a-conversation-review-set"></a>Passaggio 2: creare un set di revisione della conversazione

In un set di revisione è possibile eseguire ricerche, tag, annotazioni e documenti di redigere, messaggi di posta elettronica e conversazioni chat. In Advanced eDiscovery, è possibile personalizzare la revisione delle conversazioni, in base ai singoli messaggi o alle conversazioni filettate. Questo è determinato dal tipo di revisione impostato in cui si aggiungono i risultati della ricerca creata al passaggio 1. Sono disponibili due diversi tipi di set di Revisione: 
  
  - **Set di revisione standard:** I messaggi nelle conversazioni vengono elaborati e visualizzati come singoli elementi. 
  
  -  **Set di revisione della conversazione:** I messaggi nelle conversazioni vengono elaborati singolarmente ma visualizzati in una visualizzazione conversazione. In un set di revisione della conversazione, è possibile annotare, contrassegnare e redigere i messaggi in una visualizzazione di conversazione filettata. 

Per ulteriori informazioni su come esaminare e gestire il contenuto in un set di recensioni, vedere [Manage Review sets](managing-review-sets.md). 

## <a name="step-3-enable-conversation-retrieval-options"></a>Passaggio 3: abilitare le opzioni di recupero delle conversazioni

Dopo aver esaminato e completato la query di ricerca, è possibile aggiungere i risultati della ricerca a un set di revisione. Quando si aggiungono i risultati della ricerca in un set di revisione, i dati originali vengono copiati in un'area di archiviazione di Azure per semplificare il processo di revisione e analisi. Per ulteriori informazioni sull'aggiunta dei risultati di ricerca a un set di revisione, vedere [Add Search results to a Review set](add-data-to-review-set.md). 

Quando si aggiungono dati dalle conversazioni a un set di revisione, è possibile utilizzare le opzioni di recupero delle conversazioni per espandere la ricerca e includere i messaggi contestuali. Dopo aver impostato le opzioni di recupero delle conversazioni, è possibile che si verifichino le seguenti operazioni:

  ![Recupero delle conversazioni](media/messagesandconversations.png)
  
1. Utilizzando una query di parole chiave e intervallo di date, la ricerca ha restituito un hit sul *messaggio 3*. Questo messaggio è stato parte di una conversazione più grande, illustrata da *CRC1*. 
  
2. Quando si aggiungono i dati in un set di revisione e si abilitano le opzioni di recupero delle conversazioni, Advanced eDiscovery torna indietro e raccoglie altri elementi in *CRC1*. 
  
3. Dopo aver aggiunto gli elementi al set di revisione, è possibile esaminare tutti i singoli messaggi da *CRC1*. 



Per abilitare il recupero delle conversazioni:
  
1. Nella scheda **ricerche** del caso Advanced eDiscovery, selezionare una ricerca, quindi fare clic su **Aggiungi al set di revisione** nella pagina a comparsa.
  
2. Selezionare un set di revisione esistente o creare un set di revisione. È possibile configurare le opzioni di recupero quando si aggiungono i risultati di ricerca a un set di revisione standard o di conversazione.
  
3. In **Opzioni di raccolta**configurare le opzioni di recupero delle conversazioni per le origini di contenuto che si desidera espandere nella ricerca, quindi fare clic su **Aggiungi** per avviare il processo.  
  
4. Dopo aver completato il processo **di installazione del set di revisione** nella scheda **processi** , è possibile iniziare a rivedere le conversazioni.

## <a name="step-4-review-conversations-in-the-review-set"></a>Passaggio 4: esaminare le conversazioni nel set di Revisione

Dopo che il contenuto è stato elaborato e aggiunto al set di revisione, è possibile iniziare a visualizzare i dati nel set di revisione. Le funzionalità di revisione sono diverse a seconda che il contenuto sia stato aggiunto a un set di revisione standard o a un set di recensioni di conversazione. 

### <a name="reviewing-conversations-in-a-standard-review-set"></a>Revisione delle conversazioni in un set di riesame standard

In un set di revisione standard, i messaggi vengono elaborati e visualizzati come singoli elementi, analogamente a come vengono archiviati in una cartella delle cassette postali. In questo flusso di lavoro, ogni messaggio viene elaborato come elemento separato. Di conseguenza, le opzioni di riepilogo e esportazione filettate non sono disponibili in un set di analisi standard. 

  ![Set di revisione standard](media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>Revisione delle conversazioni in un set di recensioni di conversazione

In un set di revisione della conversazione, i singoli messaggi vengono configurati insieme e presentati come conversazioni. In questo modo è possibile esaminare ed esportare conversazioni contestuali. 

  ![Set di revisione della conversazione](media/ConversationRSOptions.PNG)

Nelle sezioni seguenti viene descritta la revisione e l'esportazione delle conversazioni in un set di recensioni di conversazione.

#### <a name="reviewing-conversations"></a>Revisione delle conversazioni

In un set di recensioni di conversazione è possibile utilizzare le opzioni seguenti per semplificare il processo di revisione.

- **Raggruppamento per conversazione:** Raggruppa i messaggi all'interno della stessa conversazione per consentire agli utenti di semplificare e velocizzare il processo di revisione. 

- **Visualizzazione Riepilogo:** Visualizza la conversazione filettata. In questa visualizzazione, è possibile visualizzare l'intera conversazione e accedere anche ai metadati per ogni singolo messaggio.  
  
   - Visualizzare i metadati per i singoli messaggi
   
   - Scaricare singoli messaggi

- **Visualizzazione testo:** Fornisce il testo estratto per l'intera conversazione. 

- **Visualizzazione annotazioni:** Consente di markup di una visualizzazione con thread della conversazione. Tutti i messaggi della conversazione condividono lo stesso documento con annotazioni.

- **Tagging:** Quando si visualizzano le conversazioni in un set di revisione, è possibile visualizzare e applicare i tag facendo clic su **tagging** nel pannello di codifica.

- **Rieseguire la conversione della conversazione:** Quando i messaggi vengono aggiunti a un set di revisione della conversazione, viene eseguito automaticamente un processo di conversione per creare il riepilogo filettato e le visualizzazioni annotazioni. Se il processo di ricostruzione della conversazione ha esito negativo, è possibile rieseguire questo processo facendo clic su **azione > creare file PDF di conversazione** nel set di revisione.


#### <a name="exporting-conversations"></a>Esportazione di conversazioni

In un set di recensioni di conversazione è possibile impostare le opzioni seguenti per esportare le conversazioni:

![Esportazione](media/export.png)

un. Opzioni dei metadati

   - **Carica file:** I metadati sono inclusi per ogni singolo messaggio, indirizzo di posta elettronica e documento. In una conversazione è presente una riga per ogni messaggio. 

   - **Tag:** I tag del processo di revisione sono inclusi nel file di metadati. I messaggi in una conversazione condividono gli stessi tag. 

b. Opzioni di conversazione
  
   - **File di conversazione:** Quando si esportano file di conversazione, la visualizzazione con annotazioni viene convertita in un file PDF e scaricata nella cartella Export. I messaggi in un file di conversazione puntano alla versione PDF dello stesso file di conversazione.  
  
   - **Messaggi di chat individuali:** Quando si esportano singoli messaggi, ciascun messaggio univoco nella conversazione viene esportato come elemento autonomo. Il file viene esportato nello stesso formato in cui è stato salvato come nella cassetta postale. Per una conversazione specifica, si ricevono più file. msg. 

     >[!NOTE]
     > Se le annotazioni sono state applicate al file di conversazione, queste annotazioni non verranno trasferite ai singoli messaggi. 

c. Altre opzioni

   - **Generare file di testo per tutto il contenuto esportato:** Genera un file di testo per ogni conversazione esportata dal set di revisione. 

   - **Sostituire il contenuto esportato con file PDF redatti:** Se durante il processo di revisione vengono generati file di conversazione redatti, questi file sono disponibili durante l'esportazione. È possibile decidere se esportare solo i file nativi (non selezionando questa opzione) o sostituire i file nativi con le versioni redatte dei file nativi (selezionando questa opzione), che vengono esportati come file PDF.

## <a name="more-information"></a>Ulteriori informazioni

Per ulteriori informazioni su come esaminare i dati dei casi in Advanced eDiscovery, vedere gli articoli seguenti:

- [Visualizzare i dati dei casi](view-documents-in-review-set.md) 

- [Analizzare i dati del caso](analyzing-data-in-review-set.md)

- [Esportare i dati del caso](exporting-data-ediscover20.md)
