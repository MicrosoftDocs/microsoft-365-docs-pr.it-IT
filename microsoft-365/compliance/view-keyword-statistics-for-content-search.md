---
title: Visualizzare le statistiche delle parole chiave per i risultati di Ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: Informazioni su come usare la funzionalità Statistiche di ricerca per visualizzare e confrontare le statistiche per più ricerche di contenuto nel Centro sicurezza & conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7faf956aaec5619655818036b969086e0af0c6a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49987834"
---
# <a name="view-keyword-statistics-for-content-search-results"></a>Visualizzare le statistiche delle parole chiave per i risultati di Ricerca contenuto

Dopo aver creato ed eseguito una ricerca di contenuto, è possibile visualizzare le statistiche relative ai risultati della ricerca stimati. Include un riepilogo dei risultati della ricerca (simile al riepilogo dei risultati della ricerca stimati visualizzati nel riquadro dei dettagli), le statistiche delle query, ad esempio il numero di percorsi di contenuto con elementi che corrispondono alla query di ricerca e il nome dei percorsi di contenuto con gli elementi più corrispondenti. È possibile visualizzare statistiche per una o più ricerche di contenuto. In questo modo è possibile confrontare rapidamente i risultati di più ricerche e prendere decisioni sull'efficacia delle query di ricerca.
  
È inoltre possibile configurare ricerche nuove ed esistenti per restituire statistiche per ogni parola chiave in una query di ricerca. In questo modo è possibile confrontare il numero di risultati per ogni parola chiave in una query e confrontare le statistiche delle parole chiave di più ricerche.
  
È anche possibile scaricare le statistiche di ricerca e delle parole chiave in un file CSV. Questo consente di usare le funzionalità di filtro e ordinamento di Excel per confrontare i risultati e preparare report per i risultati della ricerca.
  
## <a name="get-statistics-for-content-searches"></a>Ottenere statistiche per le ricerche di contenuto

Per visualizzare le statistiche per le ricerche di contenuto:
  
1. Nel Centro conformità Microsoft 365 passare a **Mostra tutta la ricerca** di  >  **contenuto.**

2. Nell'elenco delle ricerche, selezionare due o più ricerche e quindi fare clic **su** Statistiche di ricerca nella pagina a comparsa **Azioni in** blocco.
    
    ![Selezionare più ricerche e quindi fare clic su Statistiche ricerca](../media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. Nella pagina **Statistiche ricerca** fare clic su uno dei collegamenti seguenti per visualizzare le statistiche sulle ricerche selezionate. 
    
    **Riepilogo**
    
    In questa pagina vengono visualizzate statistiche simili a quelle visualizzate nel riquadro dei dettagli della **pagina Ricerca** contenuto. Vengono visualizzate le statistiche per tutte le ricerche selezionate. Tieni presente che puoi anche eseguire di nuovo le ricerche selezionate da questa pagina per aggiornare le statistiche. 
    
    ![Riepilogo delle statistiche per le ricerche selezionate](../media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    a.  Nome della ricerca di contenuto. Come indicato in precedenza, è possibile visualizzare e confrontare le statistiche per più ricerche.
    
    b. Tipo di percorso del contenuto in cui è stata ricercata. In ogni riga vengono visualizzate le statistiche relative alle cassette postali, ai siti e alle cartelle pubbliche della ricerca specificata.
    
    c. Numero di percorsi di contenuto contenenti elementi che corrispondono alla query di ricerca. Per le cassette postali, questa statistica include anche il numero di cassette postali di archiviazione che contengono elementi che corrispondono alla query di ricerca.
    
    d. Numero totale di elementi di tutti i percorsi di contenuto specificati che corrispondono alla query di ricerca. Alcuni esempi di tipi di elementi sono i messaggi di posta elettronica, gli elementi del calendario e i documenti. Se un elemento contiene più istanze di una parola chiave in fase di ricerca, viene conteggiato una sola volta nel numero totale di elementi. Ad esempio, se si cercano parole "stock" o "fraud" e un messaggio di posta elettronica contiene tre istanze della parola "stock", viene conteggiato una sola volta nella colonna **Items.** 
    
    e. Dimensioni totali di tutti gli elementi trovati nel percorso di contenuto specificato che corrispondono alla query di ricerca. 
    
    **Query**
    
    In questa pagina vengono visualizzate le statistiche relative alla query di ricerca.
    
    ![Statistiche delle query di ricerca per le ricerche selezionate](../media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    a. Nome della ricerca di contenuto per cui la riga contiene le statistiche di query.
    
    b. Tipo di percorso del contenuto a cui sono applicabili le statistiche delle query.
    
    c. Questa colonna indica a quale parte della query di ricerca sono applicabili le statistiche. **Primary** indica l'intera query di ricerca. Se si utilizza un elenco di parole chiave quando si crea o si modifica una query di ricerca, nella tabella sono incluse le statistiche per ogni componente della query. Per ulteriori [informazioni, vedere](#get-keyword-statistics-for-content-searches) la sezione Ottenere le statistiche delle parole chiave per le ricerche di contenuto in questo articolo. 
    
    d. Questa colonna contiene la query di ricerca effettiva eseguita dallo strumento Ricerca contenuto. Si noti che lo strumento aggiunge automaticamente alcuni componenti aggiuntivi alla query creata. 

    - Quando si cerca tutto il contenuto nelle cassette postali (senza specificare alcuna parola chiave), la query di parola chiave effettiva è in modo che tutti gli  `size>=0` elementi vengono restituiti. 
    
     - Quando si esegue una ricerca nei siti di SharePoint Online e OneDrive for Business, vengono aggiunti i due componenti seguenti:
    
          **NOT IsExternalContent:1** - Esclude qualsiasi contenuto da un'organizzazione di SharePoint locale. 
    
          **NOT IsOneNotePage:1** - Esclude tutti i file di OneNote perché si tratta di duplicati di qualsiasi documento che corrisponde alla query di ricerca. 

    
    e. Numero di percorsi di contenuto (specificati dalla colonna ** Tipo di posizione **) che contengono gli elementi che corrispondono alla query di ricerca elencata nella **colonna Query.** 
    
    f. Numero di elementi (dal percorso di contenuto specificato) che corrispondono alla query di ricerca elencata nella **colonna Query.** Come spiegato in precedenza, se un elemento contiene più istanze di una parola chiave in fase di ricerca, viene conteggiato una sola volta nella colonna. 
    
    g. Dimensione totale di tutti gli elementi trovati (nel percorso di contenuto specificato) che corrispondono alla query di ricerca nella **colonna Query.** 
    
    **Posizioni principali**
    
    In questa pagina vengono visualizzate le statistiche relative al numero di elementi che corrispondono alla query di ricerca in ogni percorso di contenuto in cui è stata eseguita la ricerca. Vengono visualizzati i primi 1.000 percorsi. Se si visualizzano le statistiche per più ricerche, vengono visualizzate le prime 1.000 posizioni per ogni ricerca. Si noti che un percorso di contenuto non è incluso in questa pagina se non contiene elementi che corrispondono alla query di ricerca.
    
    ![Statistiche sul numero di elementi trovati nei percorsi di contenuto in cui è stata ricercata](../media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    a. Nome del percorso del contenuto.
    
    b. Tipo di percorso del contenuto a cui sono applicabili le statistiche sulla posizione.
    
    c. Esistono colonne per ogni ricerca per cui si visualizzano le statistiche. Questa colonna mostra il numero (e le dimensioni totali) degli elementi che corrispondono alla query di ricerca in ogni percorso del contenuto. Si noti che quando si visualizzano le statistiche per più ricerche, la "NA" in questa colonna indica che il percorso del contenuto non è stato incluso nella ricerca. 

## <a name="get-keyword-statistics-for-content-searches"></a>Ottenere statistiche sulle parole chiave per le ricerche di contenuto

Come illustrato in precedenza, **la** pagina Query mostra la query di ricerca e il numero (e le dimensioni) degli elementi che corrispondono alla query. Se si utilizza un elenco di parole chiave quando si crea o si modifica una query di ricerca, è possibile ottenere statistiche avanzate che mostrano quanti elementi corrispondono a ogni parola chiave o frase parola chiave. In questo modo è possibile identificare rapidamente quali parti della query sono più (e meno) efficaci. Se ad esempio una parola chiave restituisce un numero elevato di elementi, è possibile scegliere di perfezionare la query con parole chiave per restringere i risultati della ricerca. È possibile configurare un elenco di parole chiave quando si crea o si modifica una ricerca di contenuto. 

Per creare un elenco di parole chiave e visualizzare le statistiche delle parole chiave per una ricerca di contenuto:
  
1. Nel Centro conformità Microsoft 365 passare a **Mostra tutta la ricerca** di  >  **contenuto.**
    
2. Nell'elenco delle ricerche di contenuto fare clic su una ricerca e quindi fare clic **sull'icona** ![ Modifica ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) modifica.
    
3. Fare **clic su Query** e quindi eseguire le operazioni seguenti: 
    
    ![Fare clic sulla casella di controllo Mostra elenco parole chiave e digitare una parola chiave in ogni riga](../media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    a. Fare clic **sulla casella di controllo Mostra elenco parole** chiave. 
    
    b. Digitare una fase di parola chiave o parola chiave in una riga della tabella delle parole chiave. Ad esempio, digitare **budget** nella prima riga e quindi digitare **sicurezza** nella seconda riga. 
    
4. Dopo aver aggiunto le parole chiave per cui si desidera eseguire la ricerca e ottenere le statistiche, fare clic **su Cerca** per eseguire la ricerca rivista. 
    
5. Al termine della ricerca, selezionarla nell'elenco delle ricerche e quindi fare clic **sul** pulsante Statistiche ricerca ![ statistiche ](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) ricerca. È inoltre possibile visualizzare e confrontare le statistiche delle parole chiave per più ricerche.
    
6. Nella pagina **Statistiche ricerca fare** clic su **Query** per visualizzare le statistiche delle parole chiave per le ricerche selezionate. 
    
    ![Vengono visualizzate le statistiche per ogni parola chiave per le ricerche selezionate](../media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    Come illustrato nella schermata precedente, vengono visualizzate le statistiche per ogni parola chiave. ciò include: 
    
    - Statistiche delle parole chiave per ogni tipo di percorso del contenuto incluso nella ricerca.
    
    - Query di ricerca effettiva per ogni parola chiave, che include tutte le condizioni della query di ricerca. 
    
    - La query di ricerca completa (identificata **come Principale** nella **colonna Parte)** e le statistiche per la query completa. Si noti che si tratta delle stesse statistiche visualizzate nella **pagina Riepilogo.** 

> [!NOTE]
> Per ridurre i problemi causati da elenchi di parole chiave di grandi dimensioni, ora si è limitati a un massimo di 20 righe nell'elenco di parole chiave di una query di ricerca.
