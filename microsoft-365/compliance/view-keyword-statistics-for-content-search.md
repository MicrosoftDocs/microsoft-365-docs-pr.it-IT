---
title: Visualizzare le statistiche delle parole chiave per i risultati di Ricerca contenuto
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: Utilizzare la funzionalità di statistiche di ricerca per visualizzare e confrontare le statistiche per più ricerche di contenuto nel centro sicurezza & conformità. È inoltre possibile configurare l'elenco di parole chiave quando si crea o si modifica una query di ricerca per ottenere statistiche avanzate che mostrano il numero di elementi corrispondenti a ciascuna parola chiave o frase di parola chiave.
ms.openlocfilehash: 558d8bd269d1c1d8bfcf3f15452a83de74f3e38d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084295"
---
# <a name="view-keyword-statistics-for-content-search-results"></a>Visualizzare le statistiche delle parole chiave per i risultati di Ricerca contenuto

Dopo aver creato ed eseguito una ricerca di contenuto, è possibile visualizzare le statistiche sui risultati della ricerca stimati. Questo include un riepilogo dei risultati della ricerca (simile al riepilogo dei risultati di ricerca stimati visualizzati nel riquadro dettagli), le statistiche di query, ad esempio il numero di posizioni di contenuto con gli elementi che corrispondono alla query di ricerca e il nome dei percorsi di contenuto. che presentano la maggior parte degli elementi corrispondenti. È possibile visualizzare le statistiche per una o più ricerche di contenuto. In questo modo è possibile confrontare rapidamente i risultati per più ricerche e prendere decisioni sull'efficacia delle query di ricerca.
  
È inoltre possibile configurare ricerche nuove ed esistenti per restituire statistiche per ogni parola chiave in una query di ricerca. In questo modo è possibile confrontare il numero di risultati per ogni parola chiave di una query e confrontare le statistiche delle parole chiave provenienti da più ricerche.
  
È inoltre possibile scaricare le statistiche di ricerca e le statistiche delle parole chiave in un file CSV. In questo modo è possibile utilizzare le funzionalità di filtro e ordinamento in Excel per confrontare i risultati e preparare i report per i risultati della ricerca.
  
## <a name="get-statistics-for-content-searches"></a>Ottenere statistiche per le ricerche di contenuto

Per visualizzare le statistiche per le ricerche di contenuto:
  
1. Nel centro sicurezza & conformità, andare a ricerca **** \> **contenuto**ricerca.
    
2. Nell'elenco delle ricerche, selezionare una o più ricerche, quindi fare clic su **Search Statistics**![Search Statistics Button](media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png).
    
    ![Selezionare più ricerche e quindi fare clic su statistiche di ricerca](media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. Nella pagina **statistiche di ricerca** fare clic su uno dei collegamenti seguenti per visualizzare le statistiche sulle ricerche selezionate. 
    
    **Riepilogo**
    
    In questa pagina vengono visualizzate statistiche simili a quelle visualizzate nel riquadro dei dettagli nella pagina **Ricerca contenuto** . Vengono visualizzate le statistiche per tutte le ricerche selezionate. Tenere presente che è anche possibile rieseguire le ricerche selezionate da questa pagina per aggiornare le statistiche. 
    
    ![Riepilogo delle statistiche per le ricerche selezionate](media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    un.  Nome della ricerca di contenuto. Come indicato in precedenza, è possibile visualizzare e confrontare le statistiche per più ricerche.
    
    b. Il tipo di percorso del contenuto in cui è stata eseguita la ricerca. In ogni riga vengono visualizzate le statistiche per le cassette postali, i siti e le cartelle pubbliche dalla ricerca specificata.
    
    c. Il numero di posizioni di contenuto che contengono gli elementi che corrispondono alla query di ricerca. Per le cassette postali, questa statistica include anche il numero di cassette postali di archiviazione che contengono elementi che corrispondono alla query di ricerca.
    
    d. Il numero totale di elementi di tutti i percorsi di contenuto specificati che corrispondono alla query di ricerca. Di seguito sono riportati alcuni esempi di tipi di elementi: messaggi di posta elettronica, elementi del calendario e documenti. Se un elemento contiene più istanze di una parola chiave che si sta cercando, viene conteggiata solo una volta nel numero totale di elementi. Ad esempio, se si cercano parole "magazzino" o "frode" e un messaggio di posta elettronica contiene tre istanze della parola "stock", viene conteggiata solo una volta nella colonna **elementi** . 
    
    e. Dimensione totale di tutti gli elementi individuati nel percorso del contenuto specificato che corrispondono alla query di ricerca. 
    
    **Query**
    
    In questa pagina vengono visualizzate le statistiche relative alla query di ricerca.
    
    ![Statistiche delle query di ricerca per le ricerche selezionate](media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    un. Nome della ricerca di contenuto per la quale la riga contiene le statistiche di query.
    
    b. Il tipo di percorso di contenuto a cui sono applicabili le statistiche di query.
    
    c. In questa colonna viene indicata la parte della query di ricerca a cui sono applicabili le statistiche. **Primary** indica l'intera query di ricerca. Se si utilizza un elenco di parole chiave quando si crea o si modifica una query di ricerca, le statistiche per ogni componente della query sono incluse in questa tabella. Per ulteriori informazioni, vedere la sezione [ottenere statistiche sulle parole chiave per la ricerca di contenuto](#get-keyword-statistics-for-content-searches) in questo articolo. 
    
    d. Questa colonna contiene la query di ricerca effettiva eseguita dallo strumento di ricerca del contenuto. Si noti che lo strumento aggiunge automaticamente alcuni componenti aggiuntivi alla query creata. 

    - Quando si esegue la ricerca di tutto il contenuto nelle cassette postali (non specificando parole chiave), la `size>=0` query parola chiave effettiva è in modo che tutti gli elementi vengano restituiti. 
    
     - Quando si eseguono ricerche in siti di SharePoint Online e OneDrive for business, vengono aggiunti i due componenti seguenti:
    
          **Not IsExternalContent: 1** -esclude qualsiasi contenuto proveniente da un'organizzazione di SharePoint locale. 
    
          **Not IsOneNotePage: 1** -esclude tutti i file di OneNote perché sono duplicati di qualsiasi documento corrispondente alla query di ricerca. 

    
    e. Il numero di posizioni di contenuto (specificate dal tipo * * location * * Column) che contengono elementi che corrispondono alla query di ricerca elencata nella colonna **query** . 
    
    f. Il numero di elementi (dalla posizione di contenuto specificata) che corrispondono alla query di ricerca elencata nella colonna **query** . Come spiegato in precedenza, se un elemento contiene più istanze di una parola chiave che si sta cercando, viene conteggiata solo una volta nella colonna this. 
    
    g. Dimensione totale di tutti gli elementi individuati (nel percorso del contenuto specificato) che corrispondono alla query di ricerca nella colonna **query** . 
    
    **Posizioni principali**
    
    In questa pagina vengono visualizzate le statistiche relative al numero di elementi che corrispondono alla query di ricerca in ogni percorso di contenuto in cui è stata eseguita la ricerca. Vengono visualizzate le posizioni principali di 1.000. Se si visualizzano le statistiche per più ricerche, vengono visualizzate le posizioni principali di 1.000 per ogni ricerca. Si noti che una posizione di contenuto non è inclusa in questa pagina se non contiene gli elementi che corrispondono alla query di ricerca.
    
    ![Statistiche relative al numero di elementi trovati nei percorsi di contenuto in cui è stata eseguita la ricerca](media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    un. Nome del percorso del contenuto.
    
    b. Tipo di percorso di contenuto a cui si applicano le statistiche relative alla posizione.
    
    c. Sono disponibili colonne per ogni ricerca in cui vengono visualizzate le statistiche. In questa colonna vengono visualizzati il numero e le dimensioni totali degli elementi che corrispondono alla query di ricerca in ogni percorso del contenuto. Si noti che quando si visualizzano statistiche per più ricerche, la "NA" in questa colonna indica che il percorso del contenuto non è stato incluso nella ricerca. 

## <a name="get-keyword-statistics-for-content-searches"></a>Ottenere statistiche sulle parole chiave per le ricerche di contenuto

Come spiegato in precedenza, la pagina **query** Visualizza la query di ricerca e il numero e le dimensioni degli elementi che corrispondono alla query. Se si utilizza un elenco di parole chiave quando si crea o si modifica una query di ricerca, è possibile ottenere statistiche avanzate che mostrano il numero di elementi che corrispondono a ogni parola chiave o frase di parola chiave. In questo modo è possibile identificare rapidamente quali parti della query sono le più (e meno) effettive. Ad esempio, se una parola chiave restituisce un numero elevato di elementi, è possibile scegliere di affinare la query con parole chiave per limitare i risultati della ricerca. È possibile configurare un elenco di parole chiave quando si crea o si modifica una ricerca di contenuto. 


Per creare un elenco di parole chiave e visualizzare le statistiche delle parole chiave per una ricerca contenuto:
  
1. Nel centro sicurezza & conformità, andare a ricerca **** \> **contenuto**ricerca.
    
2. Nell'elenco delle ricerche di contenuto, fare clic e una ricerca, quindi fare **** ![clic su modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)icona modifica.
    
3. Fare clic su **query** e quindi eseguire le operazioni seguenti: 
    
    ![Fare clic sulla casella di controllo Mostra elenco parole chiave e digitare una parola chiave in ogni riga](media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    un. Fare clic sulla casella di controllo **Mostra elenco parole chiave** . 
    
    b. Digitare una parola chiave o una fase di parola chiave in una riga della tabella keywords. Ad esempio, digitare **budget** nella prima riga e quindi digitare **sicurezza** nella seconda riga. 
    
4. Dopo aver aggiunto le parole chiave che si desidera cercare e ottenere le statistiche, fare clic su **Cerca** per eseguire la ricerca riveduta. 
    
5. Al termine della ricerca, selezionarlo nell'elenco delle ricerche, quindi fare clic su **Search Statistics** ![Search Statistics](media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png)Button. È inoltre possibile visualizzare e confrontare le statistiche delle parole chiave per più ricerche.
    
6. Nella pagina **statistiche di ricerca** fare clic su **query** per visualizzare le statistiche delle parole chiave per le ricerche selezionate. 
    
    ![Vengono visualizzate le statistiche per ogni parola chiave per le ricerche selezionate](media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    Come illustrato nella schermata precedente, vengono visualizzate le statistiche per ogni parola chiave. sono inclusi i seguenti: 
    
    - Statistiche sulle parole chiave per ogni tipo di percorso del contenuto incluso nella ricerca.
    
    - Query di ricerca effettiva per ogni parola chiave, che include tutte le condizioni della query di ricerca. 
    
    - La query di ricerca completa (identificata come **principale** nella colonna **parte** ) e le statistiche per la query completa. Note queste sono le stesse statistiche visualizzate nella pagina di **Riepilogo** . 

> [!NOTE]
> Per contribuire a ridurre i problemi causati da elenchi di parole chiave di grandi dimensioni, si è limitato a un massimo di 20 righe nell'elenco delle parole chiave di una query di ricerca.
