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
description: Informazioni sulla funzionalità di ricostruzione delle conversazioni in Advanced eDiscovery (denominato threading delle conversazioni) per ricostruire, esaminare ed esportare conversazioni di chat nei gruppi di Microsoft Teams e Yammer.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 12887ba8dd74c3dab445dcc76e155e274a371539
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838305"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a>Threading delle conversazioni in Advanced eDiscovery

La messaggistica istantanea è un modo pratico per porre domande, condividere idee o comunicare rapidamente tra gruppi di destinatari di grandi dimensioni. Poiché le piattaforme di messaggistica istantanea, come i gruppi di Microsoft Teams e Yammer, diventano fondamentali per la collaborazione aziendale, le organizzazioni devono valutare il modo in cui il flusso di lavoro di eDiscovery affronta queste nuove forme di comunicazione e collaborazione.

La funzionalità di ricostruzione delle conversazioni in Advanced eDiscovery è progettata per consentire l'identificazione del contenuto contestuale e la produzione di visualizzazioni di conversazione distinte. Questa funzionalità consente di esaminare in modo efficiente e rapido conversazioni complete di messaggistica istantanea (denominate anche conversazioni a *thread)* generate in piattaforme come Microsoft Teams.

Con la ricostruzione delle conversazioni, puoi usare le funzionalità integrate per ricostruire, rivedere ed esportare conversazioni a thread. Utilizzare la ricostruzione avanzata delle conversazioni di eDiscovery per:

- Conservare metadati univoci a livello di messaggio in tutti i messaggi all'interno di una conversazione.

- Raccogliere i messaggi contestuali relativi ai risultati della ricerca.

- Rivedere, annotare e redigere conversazioni in thread.

- Esportare singoli messaggi o conversazioni in thread

## <a name="terminology"></a>Terminologia

Ecco alcune definizioni utili per iniziare a usare la ricostruzione delle conversazioni.

- **Messaggi:** Rappresenta l'unità più piccola di una conversazione. I messaggi possono variare in base alle dimensioni, alla struttura e ai metadati. 

- **Conversazione:** Rappresenta un raggruppamento di uno o più messaggi. In diverse applicazioni, le conversazioni possono essere rappresentate in modi diversi. In alcune applicazioni esiste un'azione esplicita che deriva dalla risposta a un messaggio esistente. Le conversazioni vengono formate in modo esplicito a seguito di questa azione dell'utente. Ad esempio, ecco uno screenshot di una conversazione di canale in Microsoft Teams.

   ![Conversazione sul canale di Microsoft Teams](../media/threadedchat.png)

   In altre app (ad esempio i messaggi di chat 1xN in Teams), non esiste una catena di risposta formale e i messaggi vengono invece visualizzati come un "flat river di messaggi" all'interno di un singolo thread. In questi tipi di app, le conversazioni vengono dedotto da un gruppo di messaggi che si verificano entro un determinato periodo di tempo. Questo "raggruppamento soft" dei messaggi (anziché una catena di risposte) rappresenta la conversazione "avanti e indietro" su un argomento specifico di interesse.

## <a name="step-1-create-a-draft-collection"></a>Passaggio 1: Creare una raccolta di bozze

Dopo aver identificato i custodi e le posizioni dei contenuti rilevanti, è possibile creare una ricerca per trovare contenuto potenzialmente pertinente. Nella scheda **Raccolte** del caso Advanced eDiscovery è possibile creare una raccolta facendo clic su **Nuova raccolta** e seguendo la procedura guidata. Per informazioni su come creare una raccolta, creare una query di ricerca e visualizzare in anteprima i risultati della ricerca, vedere [Create a draft collection.](create-draft-collection.md)

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a>Passaggio 2: Eseguire il commit di una bozza di raccolta in un set di revisione

Dopo aver esaminato e finalizzato la query di ricerca in una raccolta, è possibile aggiungere i risultati della ricerca a un set di revisione. Quando si aggiungono i risultati della ricerca in un set di revisione, i dati originali vengono copiati in un'area di Archiviazione di Azure per facilitare il processo di revisione e analisi. Per ulteriori informazioni sull'aggiunta dei risultati di ricerca a un set di revisione, vedere [Commit di una raccolta di bozze in un set di revisione.](commit-draft-collection.md)

Quando aggiungi elementi dalle conversazioni a un set di recensioni, puoi usare l'opzione conversazioni a thread per raccogliere messaggi contestuali dalle conversazioni che contengono elementi che corrispondono ai criteri di ricerca della raccolta. Dopo aver selezionato l'opzione conversazioni di thread, possono verificarsi le operazioni seguenti:

  ![Recupero conversazioni](../media/messagesandconversations.png)
  
1. Utilizzando una parola chiave e una query di intervallo di date, la ricerca ha restituito un risultato *nel messaggio 3.* Questo messaggio fa parte di una conversazione più ampia, illustrata da *CRC1.*
  
2. Quando si aggiungono i dati in un set di revisione e si abilitano le opzioni di recupero delle conversazioni, Advanced eDiscovery torna indietro e raccoglie altri elementi in *CRC1.*
  
3. Dopo aver aggiunto gli elementi al set di revisione, è possibile esaminare tutti i singoli messaggi di *CRC1.*

Per abilitato l'opzione conversazioni in thread, vedere [Commit di una bozza di raccolta in un set di revisione.](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)
  
## <a name="step-3-review-and-export-threaded-conversations"></a>Passaggio 3: esaminare ed esportare conversazioni in thread

Dopo che il contenuto è stato elaborato e aggiunto al set di recensioni, puoi iniziare a esaminare i dati nel set di recensioni. Le funzionalità di revisione sono diverse a seconda che il contenuto sia stato aggiunto a un set di revisione standard o a un set di recensioni di conversazione.

### <a name="reviewing-conversations-in-a-standard-review-set"></a>Revisione delle conversazioni in un set di recensioni standard

In un set di revisione standard, i messaggi vengono elaborati e visualizzati come singoli elementi, in modo analogo a come vengono archiviati in una cartella delle cassette postali. In questo flusso di lavoro, ogni messaggio viene elaborato come elemento separato. Di conseguenza, le opzioni di riepilogo ed esportazione a thread non sono disponibili in un set di revisione standard.

  ![Set di revisione standard](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>Revisione delle conversazioni in un set di revisione delle conversazioni

In un set di revisione delle conversazioni, i singoli messaggi vengono threadati e presentati come conversazioni. In questo modo è possibile esaminare ed esportare conversazioni contestuali. 

  ![Insieme di revisione delle conversazioni](../media/ConversationRSOptions.PNG)

Le sezioni seguenti descrivono la revisione e l'esportazione di conversazioni in un set di revisione delle conversazioni.

#### <a name="reviewing-conversations"></a>Revisione delle conversazioni

In un set di revisione delle conversazioni, puoi usare le opzioni seguenti per facilitare il processo di revisione.

- **Raggruppa per conversazione:** Raggruppa i messaggi all'interno della stessa conversazione per aiutare gli utenti a semplificare e accelerare il processo di revisione.

- **Visualizzazione riepilogo:** Visualizza la conversazione a thread. In questa visualizzazione è possibile visualizzare l'intera conversazione e accedere ai metadati per ogni singolo messaggio.  
  
   - Visualizzare i metadati per i singoli messaggi
   
   - Scaricare singoli messaggi

- **Visualizzazione testo:** Fornisce il testo estratto per l'intera conversazione.

- **Annotate view:** Consente di aggiungere un markup a una visualizzazione a thread della conversazione. Tutti i messaggi della conversazione condividono lo stesso documento annotato.

- **Tagging:** Quando visualizzi le conversazioni in un set di recensioni, puoi visualizzare e applicare i tag facendo clic sul **pannello Tagging** nel pannello Codifica.

- **Eseguire di nuovo la conversione della conversazione:** Quando i messaggi vengono aggiunti a un set di revisione delle conversazioni, viene eseguito automaticamente un processo di conversione per creare il riepilogo a thread e annotare le visualizzazioni. Se il processo di ricostruzione della conversazione ha esito negativo, è possibile rieseguire il processo facendo clic su Azione **> Creare PDF** di conversazione nel set di revisioni.

#### <a name="exporting-conversations"></a>Esportazione di conversazioni

In un set di revisione delle conversazioni, puoi impostare le opzioni seguenti per esportare le conversazioni:

![Opzioni di esportazione per le conversazioni](../media/export.png)

a. Opzioni metadati

   - **Carica file:** I metadati sono inclusi per ogni singolo messaggio, messaggio di posta elettronica e documento. In una conversazione è presente una riga per ogni messaggio. 

   - **Tag:** I tag del processo di revisione sono inclusi nel file di metadati. I messaggi di una conversazione condividono gli stessi tag. 

b. Opzioni di conversazione
  
   - **File di conversazione:** Quando si esportano file di conversazione, la visualizzazione con annotazioni viene convertita in un file PDF e scaricata nella cartella di esportazione. I messaggi in un file di conversazione puntano alla versione PDF dello stesso file di conversazione.  
  
   - **Singoli messaggi di chat:** Quando si esportano singoli messaggi, ogni messaggio univoco nella conversazione viene esportato come elemento autonomo. Il file viene esportato nello stesso formato in cui è stato salvato nella cassetta postale. Per una conversazione specifica, si ricevono più file msg.

     >[!NOTE]
     > Se sono state applicate annotazioni al file di conversazione, queste annotazioni non verranno trasferite ai singoli messaggi.

c. Altre opzioni

   - **Generare file di testo per tutto il contenuto esportato:** Genera un file di testo per ogni conversazione esportata dal set di recensioni.

   - **Sostituisci il contenuto esportato con PDF redatti:** Se i file di conversazione redatti vengono generati durante il processo di revisione, questi file sono disponibili durante l'esportazione. Puoi decidere se esportare solo i file nativi (non selezionando questa opzione) o sostituire i file nativi con le versioni rievocate dei file nativi (selezionando questa opzione), che vengono esportati come file PDF.

## <a name="more-information"></a>Altre informazioni

Per ulteriori informazioni su come esaminare i dati dei casi in Advanced eDiscovery, vedere gli articoli seguenti:

- [Visualizzare i dati del caso](view-documents-in-review-set.md)

- [Analizzare i dati del caso](analyzing-data-in-review-set.md)

- [Esportare i dati del caso](exporting-data-ediscover20.md)
