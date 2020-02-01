---
title: Modifica in blocco delle ricerche di contenuto
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
search.appverid: MOE150
ms.assetid: 39e4654a-9588-41f6-892b-c33ab57bfbe2
description: Utilizzare l'editor ricerche in blocco nel centro sicurezza e conformità di Office 365 o Microsoft 365 per modificare rapidamente i percorsi di query e di contenuto per una o più ricerche di contenuto.
ms.openlocfilehash: 40d3a6c04a57f368a4f53ae0bbc543b049b26d52
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596273"
---
# <a name="bulk-edit-content-searches"></a>Modifica in blocco delle ricerche di contenuto

È possibile utilizzare l'editor ricerca in blocco nello strumento ricerca contenuto per modificare più ricerche contemporaneamente. L'utilizzo di questo strumento consente di modificare rapidamente la query e i percorsi di contenuto per una o più ricerche. È quindi possibile eseguire di nuovo le ricerche e ottenere nuovi risultati della ricerca stimati per le ricerche rivedute. L'editor consente inoltre di copiare e incollare query e percorsi di contenuto da un file di testo o da un file di Microsoft Excel. Questo significa che è possibile utilizzare lo strumento Statistiche di ricerca per visualizzare le statistiche di una o più ricerche, esportare le statistiche in un file CSV, in cui è possibile modificare le query e i percorsi di contenuto in Excel. Successivamente, utilizzare l'editor ricerche in blocco per aggiungere le query e i percorsi di contenuto rivisti alle ricerche. Dopo aver rivisto una o più ricerche, è possibile riavviarle e ottenere nuovi risultati della ricerca stimati.
  
Per ulteriori informazioni sull'utilizzo dello strumento Statistiche di ricerca, vedere [View keyword Statistics for content search results](view-keyword-statistics-for-content-search.md).
  
## <a name="use-the-bulk-search-editor-to-change-queries"></a>Utilizzare l'editor ricerche in blocco per modificare le query

1. Andare a [https://protection.office.com](https://protection.office.com), quindi selezionare ricerca **** \> **contenuto**ricerca.
    
2. Nell'elenco delle ricerche, selezionare una o più ricerche, quindi selezionare il pulsante **** ![](media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png)editor ricerca bulk editor ricerche in blocco.
    
    ![Selezionare una o più ricerche, quindi selezionare Editor ricerche in blocco](media/600c9716-89a2-4451-b111-fa7cfaad2006.png)
  
    Nella pagina **query** dell'editor ricerche in blocco vengono visualizzate le informazioni seguenti. 
    
    ![Nella pagina Editor ricerche in blocco vengono visualizzate le query per le ricerche selezionate](media/189659af-cc78-4479-b0bc-a93decad2f6c.png)
  
    a. Nella colonna **ricerca** viene visualizzato il nome della ricerca di contenuto. Come indicato in precedenza, è possibile modificare la query per più ricerche. 
    
    b. La colonna **query** Visualizza la query per la ricerca di contenuto elencata nella colonna **ricerca** . Se la query è stata creata utilizzando la caratteristica elenco di parole chiave, la parola chiave viene separata dal `(c:s)`testo * * **. Ciò indica che le parole chiave sono connesse tramite l'operatore **or** . Inoltre, se la query include condizioni, le parole chiave e le condizioni sono separate dal testo * * `(c:c)` **. Ciò indica che le parole chiave (o fasi parola chiave) sono connesse alle condizioni dall'operatore **and** . Ad esempio, nella schermata precedente per la ricerca ContosoSearch1, la query KQL equivalente a `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)` sarebbe. `(customer OR pricing) AND (date=2002-01-01..2016-09-30)`
    
3. Per modificare una query, selezionare nella cella della query che si desidera modificare e quindi eseguire una delle operazioni seguenti. La cella è delimitata da una casella blu quando la si seleziona.
    
   - Digitare la nuova query nella cella. Non è possibile modificare una parte della query. È necessario digitare l'intera query.
    
      Oppure
    
    - Incollare una nuova query nella cella. In questo modo si presuppone che il testo della query sia stato copiato da un file, ad esempio un file di testo o un file di Excel.
    
4. Dopo aver modificato una o più query nella pagina **query** , fare clic su **Salva**.
    
    La query riveduta viene visualizzata nella colonna **query** per la ricerca selezionata. 
    
5. Selezionare **Chiudi** per chiudere l'editor ricerche in blocco. 
    
6. Nella pagina **Ricerca contenuto** , selezionare la ricerca modificata e quindi fare clic su **Avvia** ricerca per riavviare la ricerca utilizzando la query riveduta. 
    
Di seguito sono riportate alcune indicazioni per la modifica delle query tramite l'editor ricerca in blocco:
  
- Copiare la query esistente (tramite **CTRL C** ) in un file di testo. Modificare la query nel file di testo e quindi copiare la query riveduta e incollarla (utilizzando **CTRL V** ) nuovamente nella cella della pagina **query** . 
    
- È anche possibile copiare le query da altre applicazioni, ad esempio Microsoft Word o Microsoft Excel. Tuttavia, è possibile aggiungere inavvertitamente caratteri non supportati a una query utilizzando l'editor ricerche in blocco. Il modo migliore per evitare che i caratteri non supportati consiste nel digitare semplicemente la query in una cella della pagina **query** . In alternativa, è possibile copiare una query da Word o Excel e incollarla nel file in un editor di testo normale, ad esempio il blocco note Microsoft. Salvare quindi il file di testo e selezionare **ANSI** nell'elenco a discesa **Encoding** . In questo caso vengono rimossi tutti i caratteri di formattazione e non supportati. È quindi possibile copiare e incollare la query dal file di testo alla pagina **query** . 
    
  
## <a name="use-the-bulk-search-editor-to-change-content-locations"></a>Utilizzare l'editor ricerche in blocco per modificare le posizioni di contenuto

1. Nell'editor ricerche di massa per una o più ricerche selezionate selezionare **Abilita editor percorso di massa**e quindi selezionare il collegamento **percorsi** visualizzato nella pagina. 
    
    Nella pagina **percorsi** dell'editor ricerche in blocco vengono visualizzate le informazioni seguenti. 
    
    ![Selezionare Abilita editor percorso di massa e quindi selezionare percorsi per aggiungere o rimuovere percorsi di contenuto](media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)
  
    a. **Cassette postali da cercare** In questa sezione viene visualizzata una colonna per ogni ricerca di contenuto selezionata e una riga per ogni cassetta postale inclusa nella ricerca. Un segno di spunta indica che la cassetta postale è inclusa nella ricerca. È possibile aggiungere cassette postali a una ricerca digitando l'indirizzo di posta elettronica della cassetta postale in una riga vuota e quindi selezionando la casella di controllo per la ricerca di contenuto a cui si desidera aggiungerla. In alternativa, è possibile rimuovere una cassetta postale da una ricerca deselezionando la casella di controllo.
    
    b. **Siti di SharePoint da cercare** In questa sezione viene visualizzata una riga per ogni sito di SharePoint e OneDrive incluso in ogni ricerca contenuto selezionata. Un segno di spunta indica che il sito è incluso nella ricerca. È possibile aggiungere siti a una ricerca digitando l'URL del sito in una riga vuota e quindi selezionando la casella di controllo per la ricerca di contenuto a cui si desidera aggiungerla. In alternativa, è possibile rimuovere un sito da una ricerca deselezionando la casella di controllo.
    
    c. **Altre opzioni di ricerca** In questa sezione viene indicato se nella ricerca vengono inclusi gli elementi non indicizzati e le cartelle pubbliche. Per includerle, verificare che sia selezionata la casella di controllo. Per rimuoverle, deselezionare la casella di controllo.
    
2. Dopo aver modificato una o più sezioni della pagina **posizioni** , selezionare **Salva**.
    
    I percorsi di contenuto rivisti sono visualizzati nella sezione appropriata per le ricerche selezionate.
    
3. Selezionare **Chiudi** per chiudere l'editor ricerche in blocco. 
    
4. Nella pagina **Ricerca contenuto** , selezionare la ricerca modificata e quindi fare clic su **Avvia** ricerca per riavviare la ricerca utilizzando i percorsi di contenuto riveduti. 
    
Di seguito sono riportate alcune indicazioni per la modifica delle posizioni di contenuto tramite l'editor ricerca in blocco:
  
- È possibile modificare le ricerche di contenuto per eseguire la ricerca in tutte le cassette postali o i siti dell'organizzazione digitando **tutto** in una riga vuota nelle **cassette postali per cercare** i **siti di SharePoint** e la sezione ricerca e quindi selezionando la casella di controllo. 
    
- È possibile aggiungere più percorsi di contenuto a una o più ricerche copiando più righe da un file di testo o da un file di Excel e quindi incollando tali posizioni in una sezione della pagina **percorsi** . Dopo aver aggiunto nuove posizioni, assicurarsi di selezionare la casella di controllo per ogni ricerca per la quale si desidera aggiungere il percorso. 
    
    > [!TIP]
    > Per generare un elenco di indirizzi di posta elettronica per tutti gli utenti dell'organizzazione, eseguire il comando PowerShell nel passaggio 2 del [passaggio 2: generazione di un elenco di utenti](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step-2-generate-a-list-of-users). In alternativa, seguire la procedura illustrata in [ottenere un elenco di tutti gli URL di OneDrive utente nell'organizzazione](https://docs.microsoft.com/onedrive/list-onedrive-urls) per generare un elenco di tutti i siti di OneDrive for business nell'organizzazione. Tenere presente che è necessario aggiungere l'URL per il dominio del sito Web dell'organizzazione (ad esempio, https://contoso-my.sharepoint.com) per i siti di OneDrive for business creati dallo script. Dopo aver ricevuto un elenco di indirizzi di posta elettronica o siti di OneDrive for business, è possibile copiarli e incollarli nella pagina **percorsi** nell'editor ricerche in blocco. 
  
- Dopo aver selezionato **Salva** per salvare le modifiche apportate all'editor ricerche in blocco, l'indirizzo di posta elettronica per le cassette postali aggiunte a una ricerca verrà convalidato. Se l'indirizzo di posta elettronica non esiste, viene visualizzato un messaggio di errore che indica che la cassetta postale non può essere individuata. Gli URL dei siti non vengono convalidati. 
  

