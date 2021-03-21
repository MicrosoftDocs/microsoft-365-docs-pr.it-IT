---
title: Modifica in blocco ricerche contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/29/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 39e4654a-9588-41f6-892b-c33ab57bfbe2
ms.custom:
- seo-marvel-apr2020
description: Utilizzare l'editor di ricerca in blocco nel Centro sicurezza e conformità per modificare rapidamente le posizioni di query e contenuto per una o più ricerche di contenuto.
ms.openlocfilehash: 9f4d84a2f9c99f544bbb402fc24ac2dcbf0864f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918232"
---
# <a name="bulk-edit-content-searches"></a>Modifica in blocco ricerche contenuto

È possibile utilizzare l'editor di ricerca in blocco nello strumento Ricerca contenuto per modificare più ricerche contemporaneamente. Questo strumento consente di modificare rapidamente le posizioni di query e contenuto per una o più ricerche. È quindi possibile eseguire di nuovo le ricerche e ottenere nuovi risultati di ricerca stimati per le ricerche riviste. L'editor consente inoltre di copiare e incollare query e percorsi di contenuto da un file di Microsoft Excel o da un file di testo. Ciò significa che è possibile utilizzare lo strumento Statistiche di ricerca per visualizzare le statistiche di una o più ricerche, esportare le statistiche in un file CSV, in cui è possibile modificare le query e i percorsi del contenuto in Excel. È quindi possibile utilizzare l'editor di ricerca in blocco per aggiungere le query e i percorsi di contenuto revisionati alle ricerche. Dopo aver rivisto una o più ricerche, è possibile riavviarle e ottenere nuovi risultati di ricerca stimati.
  
Per ulteriori informazioni sull'utilizzo dello strumento Statistiche di ricerca, vedere [View keyword statistics for Content Search results.](view-keyword-statistics-for-content-search.md)
  
## <a name="use-the-bulk-search-editor-to-change-queries"></a>Utilizzare l'editor di ricerca in blocco per modificare le query

1. Passare a [https://protection.office.com](https://protection.office.com) e quindi selezionare **Ricerca** \> **contenuto**.
    
2. Nell'elenco delle ricerche, selezionare una o più ricerche e quindi selezionare il pulsante **Bulk Search Editor** Bulk Search Editor ![ ](../media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png) .
    
    ![Selezionare una o più ricerche e quindi selezionare Editor ricerca in blocco](../media/600c9716-89a2-4451-b111-fa7cfaad2006.png)
  
    Le informazioni seguenti vengono visualizzate nella pagina **Query** dell'editor di ricerca in blocco. 
    
    ![Nella pagina Editor ricerca in blocco vengono visualizzate le query per le ricerche selezionate](../media/189659af-cc78-4479-b0bc-a93decad2f6c.png)
  
    a. Nella **colonna Ricerca** viene visualizzato il nome della ricerca contenuto. Come indicato in precedenza, è possibile modificare la query per più ricerche. 
    
    b. Nella **colonna Query** viene visualizzata la query per la ricerca contenuto elencata nella colonna **Ricerca.** Se la query è stata creata utilizzando la funzionalità elenco parole chiave, le parole chiave sono separate dal testo ** `(c:s)` **. Ciò indica che le parole chiave sono connesse dall'operatore **OR.** Inoltre, se la query `(c:c)` include condizioni,** le parole chiave e le condizioni sono separate dal testo ** . Ciò indica che le parole chiave (o le fasi delle parole chiave) sono connesse alle condizioni dall'operatore **AND.** Ad esempio, nella schermata precedente la query per la ricerca ContosoSearch1, la query KQL equivalente  `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)` a sarebbe  `(customer OR pricing) AND (date=2002-01-01..2016-09-30)` .
    
3. Per modificare una query, selezionare nella cella della query che si desidera modificare ed eseguire una delle operazioni seguenti. Quando si seleziona la cella, alla cella viene visualizzata una casella blu.
    
   - Digitare la nuova query nella cella. Non è possibile modificare una parte della query. È necessario digitare l'intera query.
    
      Oppure
    
    - Incollare una nuova query nella cella. Si presuppone che il testo della query sia stato copiato da un file, ad esempio un file di testo o un file di Excel.
    
4. Dopo aver modificato una o più query nella pagina **Query,** selezionare **Salva.**
    
    La query rivista viene visualizzata nella **colonna Query** per la ricerca selezionata. 
    
5. Selezionare **Chiudi per** chiudere l'editor di ricerca in blocco. 
    
6. Nella pagina **Ricerca contenuto** selezionare la ricerca modificata  e selezionare Avvia ricerca per riavviare la ricerca utilizzando la query modificata. 
    
Ecco alcuni suggerimenti per la modifica delle query tramite l'editor di ricerca in blocco:
  
- Copiare la query esistente (utilizzando **CTRL C)** in un file di testo. Modificare la query nel file di testo, quindi copiare la query rivista e incollarla (utilizzando **CTRL V)** di nuovo nella cella della **pagina** Query. 
    
- È inoltre possibile copiare query da altre applicazioni, ad esempio Microsoft Word o Microsoft Excel. Tuttavia, è possibile aggiungere inavvertitamente caratteri non supportati a una query utilizzando l'editor di ricerca in blocco. Il modo migliore per evitare caratteri non supportati è semplicemente digitare la query in una cella della **pagina** Query. Oppure è possibile copiare una query da Word o Excel e incollarla in un file in un editor di testo normale, ad esempio Blocco note Microsoft. Salvare quindi il file di testo e selezionare **ANSI** **nell'elenco** a discesa Codifica. In questo modo viene rimossa la formattazione e i caratteri non supportati. È quindi possibile copiare e incollare la query dal file di testo alla **pagina** Query. 
    
  
## <a name="use-the-bulk-search-editor-to-change-content-locations"></a>Utilizzare l'editor di ricerca in blocco per modificare i percorsi del contenuto

1. Nell'Editor ricerca in blocco per una o più ricerche selezionate,  selezionare **Abilita editor** di posizioni in blocco e quindi selezionare il collegamento Posizioni visualizzato nella pagina. 
    
    Le informazioni seguenti vengono visualizzate nella pagina **Percorsi** dell'editor di ricerca in blocco. 
    
    ![Selezionare Abilita editor di percorsi in blocco, quindi selezionare Percorsi per aggiungere o rimuovere percorsi di contenuto](../media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)
  
    a. **Cassette postali in cui eseguire la ricerca** In questa sezione viene visualizzata una colonna per ogni ricerca contenuto selezionata e una riga per ogni cassetta postale inclusa nella ricerca. Un segno di spunta indica che la cassetta postale è inclusa nella ricerca. È possibile aggiungere cassette postali a una ricerca digitando l'indirizzo di posta elettronica della cassetta postale in una riga vuota e quindi selezionando la casella di controllo per la ricerca di contenuto a cui si desidera aggiungerla. Oppure è possibile rimuovere una cassetta postale da una ricerca deselezionando la casella di controllo.
    
    b. **Siti di SharePoint in cui eseguire la ricerca** In questa sezione viene visualizzata una riga per ogni sito di SharePoint e OneDrive incluso in ogni ricerca contenuto selezionata. Un segno di spunta indica che il sito è incluso nella ricerca. È possibile aggiungere siti a una ricerca digitando l'URL del sito in una riga vuota e quindi selezionando la casella di controllo corrispondente alla ricerca contenuto a cui si desidera aggiungerlo. Oppure è possibile rimuovere un sito da una ricerca deselezionando la casella di controllo.
    
    c. **Altre opzioni di ricerca** Questa sezione indica se gli elementi non indicizzati e le cartelle pubbliche sono inclusi nella ricerca. Per includerli, verificare che la casella di controllo sia selezionata. Per rimuoverli, deselezionare la casella di controllo.
    
2. Dopo aver modificato una o più sezioni  nella pagina Percorsi, selezionare **Salva**.
    
    I percorsi del contenuto revisionati vengono visualizzati nella sezione appropriata per le ricerche selezionate.
    
3. Selezionare **Chiudi per** chiudere l'editor di ricerca in blocco. 
    
4. Nella pagina **Ricerca contenuto** selezionare la ricerca modificata  e selezionare Avvia ricerca per riavviare la ricerca utilizzando i percorsi di contenuto modificati. 
    
Ecco alcuni suggerimenti per la modifica dei percorsi di contenuto tramite l'editor di ricerca in blocco:
  
- È possibile modificare le ricerche di contenuto per eseguire ricerche in tutte  le cassette postali o in tutti i siti dell'organizzazione digitando **Tutto** in una riga vuota nella sezione Cassette postali in cui cercare o Siti di **SharePoint** in cui eseguire la ricerca e quindi selezionando la casella di controllo. 
    
- È possibile aggiungere più percorsi di contenuto a una o più ricerche copiando più righe da un file di testo o da un file di Excel e quindi incollandole in una sezione della **pagina** Percorsi. Dopo aver aggiunto nuove posizioni, assicurarsi di selezionare la casella di controllo per ogni ricerca a cui si desidera aggiungere la posizione. 
    
    > [!TIP]
    > Per generare un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione, eseguire il comando PowerShell nel passaggio 2 [del passaggio 2: generare un elenco di utenti.](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step-2-generate-a-list-of-users) Oppure seguire i passaggi descritti in Ottenere un elenco di tutti gli URL di [OneDrive](/onedrive/list-onedrive-urls) dell'utente nell'organizzazione per generare un elenco di tutti i siti di OneDrive for Business nell'organizzazione. Si noti che sarà necessario aggiungere l'URL per il dominio MySite dell'organizzazione( ad esempio, ai siti di OneDrive for Business creati https://contoso-my.sharepoint.com) dallo script. Dopo aver visualizzato l'elenco degli indirizzi di posta elettronica o dei siti di OneDrive for Business, è possibile copiarli e incollarli nella **pagina Percorsi** nell'editor di ricerca in blocco. 
  
- Dopo aver selezionato **Salva per** salvare le modifiche nell'editor di ricerca in blocco, verrà convalidato l'indirizzo di posta elettronica per le cassette postali aggiunte a una ricerca. Se l'indirizzo di posta elettronica non esiste, viene visualizzato un messaggio di errore che indica che non è possibile trovare la cassetta postale. Gli URL dei siti non vengono convalidati. 
