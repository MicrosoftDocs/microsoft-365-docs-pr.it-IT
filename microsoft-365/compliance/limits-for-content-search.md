---
title: Limiti per la ricerca di contenuto e eDiscovery di base nel centro conformità
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: Informazioni sui limiti effettivi per la funzionalità di ricerca contenuto nel centro conformità di Microsoft 365, ad esempio il numero massimo di ricerche simultanee. Questi limiti di ricerca si applicano anche alle ricerche associate ai casi di eDiscovery di base.
ms.openlocfilehash: 23751fd62b2d96400d8184faa0d8d74b06b68906
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840493"
---
# <a name="limits-for-content-search"></a>Limiti per la ricerca di contenuto 
Vari limiti vengono applicati allo strumento di ricerca del contenuto nel centro conformità di Microsoft 365. Sono incluse le ricerche eseguite nella pagina **Ricerca contenuto** e le ricerche associate a un caso di eDiscovery nella pagina **Core eDiscovery** . Questi limiti consentono di mantenere l'integrità e la qualità dei servizi forniti alle organizzazioni. Sono inoltre presenti limiti relativi all'indicizzazione dei messaggi di posta elettronica in Exchange Online per la ricerca. Non è possibile modificare i limiti relativi alla ricerca di contenuto o all'indicizzazione della posta elettronica, ma è necessario conoscerli in modo da poter prendere in considerazione questi limiti durante la pianificazione, l'esecuzione e la risoluzione dei problemi relativi alle ricerche di contenuto.
  
## <a name="search-limits"></a>Limiti relativi alla ricerca

Nella tabella seguente sono elencati i limiti di ricerca quando si utilizza lo strumento di ricerca del contenuto nel centro conformità di Microsoft 365 e per le ricerche associate a un caso di eDiscovery di base.
  
| Descrizione del limite | Limite |
|:-----|:-----|
|Il numero massimo di cassette postali o di siti che possono essere ricercati in una singola ricerca  <br/> |Nessun limite <sup>1</sup> <br/> |
|Il numero massimo di ricerche che possono essere eseguite contemporaneamente nell'organizzazione.  <br/> |30  <br/> |
|Il numero massimo di ricerche che un singolo utente può avviare contemporaneamente. È probabile che questo limite venga colpito quando l'utente tenta di avviare più ricerche utilizzando il comando **Get-ComplianceSearch \| Start-ComplianceSearch** nel centro sicurezza & Compliance Center PowerShell.  <br/> |10   <br/> |
|Il numero massimo di elementi per ogni cassetta postale utente visualizzati nella pagina di anteprima quando si visualizzano i risultati della ricerca contenuto.  <br/> |100  <br/> |
|Il numero massimo di elementi presenti in tutte le cassette postali degli utenti visualizzati nella pagina di anteprima quando si visualizzano i risultati della ricerca. Vengono visualizzati gli elementi più recenti.  <br/> |1,000  <br/> |
|Il numero massimo di cassette postali utente che è possibile visualizzare in anteprima per i risultati della ricerca. Se sono presenti più di 1000 cassette postali che contengono contenuto che corrisponde alla query di ricerca, solo le cassette postali di 1000 con la maggior parte dei risultati della ricerca saranno disponibili per l'anteprima.  <br/> |1,000  <br/> |
|Il numero massimo di elementi trovati nei siti di SharePoint e OneDrive for business visualizzati nella pagina di anteprima quando si visualizzano i risultati della ricerca. Vengono visualizzati gli elementi più recenti.  <br/> |200  <br/> |
|Il numero massimo di siti (in SharePoint e OneDrive for business) che è possibile visualizzare in anteprima per i risultati della ricerca. Se sono presenti più di 200 siti totali che contengono contenuto che corrisponde alla query di ricerca, solo i primi 200 siti con i risultati di ricerca più saranno disponibili per l'anteprima.  <br/> |200  <br/> |
|Il numero massimo di elementi per ogni cassetta postale di cartelle pubbliche visualizzati nella pagina di anteprima quando si visualizzano i risultati della ricerca contenuto.  <br/> |100  <br/> |
|Il numero massimo di elementi trovati in tutte le cassette postali delle cartelle pubbliche che vengono visualizzate nella pagina di anteprima quando si visualizzano i risultati della ricerca del contenuto.  <br/> |200  <br/> |
|Il numero massimo di cassette postali pubbliche che è possibile visualizzare in anteprima per i risultati della ricerca. Se sono presenti più di 500 cassette postali delle cartelle pubbliche che contengono contenuto che corrisponde alla query di ricerca, solo le cassette postali delle cartelle pubbliche Top 500 con la maggior parte dei risultati della ricerca saranno disponibili per l'anteprima.  <br/> |500  <br/> |
|Numero massimo di caratteri per la query di ricerca (compresi gli operatori e le condizioni) per una ricerca.  <br/><br/> **Nota:** Questo limite ha effetto dopo che la query è stata espansa, il che significa che la query verrà espansa rispetto a ciascuna delle parole chiave. Ad esempio, se una query di ricerca contiene 15 parole chiave e parametri e condizioni aggiuntivi, la query viene espansa di 15 volte, ognuno con gli altri parametri e le condizioni della query. Pertanto, anche se il numero di caratteri nella query di ricerca potrebbe essere inferiore al limite, è la query espansa che può contribuire a superare questo limite.  <br/> |**Cassette postali:** 10.000  <br/> **Siti:** 4.000 quando si effettua la ricerca in tutti i siti o 2.000 quando si effettua la ricerca fino a 20 siti <sup>2</sup> <br/> |
|Numero massimo di varianti restituite quando si utilizza un carattere jolly prefisso per cercare una frase esatta in una query di ricerca o quando si utilizza un carattere jolly prefisso e l'operatore **near** Boolean.  <br/> |10.000 <sup>3</sup> <br/> |
|Numero minimo di caratteri alfanumerici per i caratteri jolly del prefisso. ad esempio,,,  `time*`  `one*` o  `set*` .  <br/> |3   <br/> |
|Il numero massimo di cassette postali in una ricerca in cui è possibile eliminare gli elementi eseguendo un'azione di "ricerca ed eliminazione" (tramite il comando **New-ComplianceSearchAction-Purge** ). Se la ricerca per la quale si sta eseguendo un'azione di eliminazione ha più cassette postali di origine rispetto a questo limite, l'azione Purge avrà esito negativo. Per ulteriori informazioni sulla ricerca e sul Purge, vedere [cercare ed eliminare i messaggi di posta elettronica nell'organizzazione](search-for-and-delete-messages-in-your-organization.md).  <br/> |50.000  <br/> |
|Numero massimo di posizioni in una ricerca di cui è possibile esportare gli elementi. Se la ricerca che si sta esportando ha più posizioni rispetto a questo limite, l'esportazione avrà esito negativo. Per ulteriori informazioni, vedere [Export content search results](export-search-results.md).  <br/> |100.000  <br/> |
|||

> [!NOTE]
> <sup>1</sup> sebbene sia possibile cercare un numero illimitato di cassette postali in una singola ricerca, è possibile scaricare solo i risultati della ricerca esportati da un massimo di 100.000 cassette postali utilizzando lo strumento di esportazione di eDiscovery nel centro conformità di Microsoft 365. Per scaricare i risultati della ricerca da più di 100.000 cassette postali, è necessario utilizzare la sicurezza & Compliance Center PowerShell. Per ulteriori informazioni e uno script di esempio, vedere [esportazione dei risultati da più di 100.000 cassette postali](export-search-results.md#exporting-results-from-more-than-100000-mailboxes). <br/><br/> <sup>2</sup> quando si eseguono ricerche nei percorsi di SharePoint e OneDrive for business, i caratteri negli URL dei siti cercati vengono conteggiati rispetto a questo limite. <br/><br/> <sup>3</sup> per le query non basate su frasi (un valore di parola chiave che non utilizza virgolette doppie) viene utilizzato un indice di prefisso speciale. Questo indica che si verifica una parola in un documento, ma non in cui si trova nel documento. Per eseguire una query di frase (un valore di parola chiave con virgolette doppie), è necessario confrontare la posizione all'interno del documento per le parole della frase. Questo significa che non è possibile utilizzare l'indice di prefisso per le query di frase. In questo caso, la query viene espansa internamente con tutte le parole possibili che il prefisso espande; ad esempio, è  `"time*"` possibile espandersi su  `"time OR timer OR times OR timex OR timeboxed OR …"` . 10.000 è il numero massimo di varianti a cui la parola può espandersi, non il numero di documenti che corrispondono alla query. Non esiste un limite superiore per i termini non frase. 
  
## <a name="export-limits"></a>Limiti di esportazione
Nella tabella seguente sono elencati i limiti per l'esportazione dei risultati di una ricerca di contenuto. Questi limiti si applicano anche quando si esporta contenuto da un caso di eDiscovery di base.

|Descrizione del limite|Limite|
|:-----|:-----|
|Quantità massima di dati esportabili da una singola ricerca  <br/><br/> **Nota:** Se i risultati della ricerca sono superiori a 2 TB, prendere in considerazione l'utilizzo di intervalli di date o di altri tipi di filtri per ridurre le dimensioni totali dei risultati della ricerca. <br/>  |2 TB  <br/> | 
|Numero massimo di un'organizzazione che può esportare in un solo giorno <br/><br/> **Nota:** Questo limite viene reimpostato giornalmente alle 12.00 UTC <br/> |2 TB <br/> |
|Massime esportazioni simultanee che è possibile eseguire nello stesso momento all'interno dell'organizzazione <br/><br/> **Nota:** Esecuzione di un **report solo** l'esportazione conta rispetto alle esportazioni simultanee totali per l'organizzazione. Se tre utenti eseguono 3 esportazioni ciascuna, è possibile eseguire solo un'altra esportazione. Se si sta esportando un report o i risultati della ricerca, non è possibile eseguire altre esportazioni finché non si è completata.   <br/> |10  <br/> |
|Massime esportazioni un singolo utente può essere eseguito in una sola volta <br/> |3  <br/> |
|Numero massimo di cassette postali per i risultati di ricerca che è possibile scaricare tramite lo strumento di esportazione di eDiscovery <br/><br/> **Nota:** Per scaricare i risultati della ricerca da più di 100.000 cassette postali, è necessario utilizzare la sicurezza & Compliance Center PowerShell. Per istruzioni, vedere [esportazione dei risultati da più di 100.000 cassette postali](export-search-results.md#exporting-results-from-more-than-100000-mailboxes). <br/> | 100.000 <br/>|
|Dimensioni massime dei file PST che possono essere esportati <br/><br/> **Nota:** Se i risultati della ricerca della cassetta postale di un utente sono superiori a 10 GB, i risultati della ricerca della cassetta postale verranno esportati in due (o più) file PST separati. Se si sceglie di esportare tutti i risultati della ricerca in un singolo file PST, il file PST verrà suddiviso in file PST aggiuntivi se la dimensione complessiva dei risultati della ricerca è superiore a 10 GB. Se si desidera modificare queste dimensioni predefinite, è possibile modificare il registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Vedere [modificare le dimensioni dei file PST quando si esportano i risultati della ricerca di eDiscovery](change-the-size-of-pst-files-when-exporting-results.md). I risultati della ricerca di una cassetta postale specifica non verranno suddivisi tra più file PST, a meno che il contenuto di una singola cassetta postale sia superiore a 10 GB. Se si è scelto di esportare i risultati della ricerca in un file PST per che contiene tutti i messaggi in una singola cartella e i risultati della ricerca sono superiori a 10 GB, gli elementi sono ancora organizzati in ordine cronologico, in modo che vengano suddivisi in file PST aggiuntivi in base alla data di invio.<br/> | 10 GB <br/> |
|Frequenza con cui i risultati della ricerca provenienti da cassette postali e siti vengono caricati in una posizione di archiviazione di Azure fornita da Microsoft. |Massimo 2 GB all'ora|
|||

## <a name="indexing-limits-for-email-messages"></a>Limiti di indicizzazione per i messaggi di posta elettronica

Nella tabella seguente vengono descritti i limiti di indicizzazione che possono comportare la restituzione di un messaggio di posta elettronica come elemento non indicizzato o un elemento parzialmente indicizzato nei risultati di una ricerca di contenuto.
  
| Limite di indicizzazione | Valore massimo | Descrizione |
|:-----|:-----|:-----|
|Dimensione massima degli allegati|150 MB  <br/> |Le dimensioni massime di un allegato di posta elettronica che analizzerà l'indicizzazione. Qualsiasi allegato che è più grande di questo limite non verrà analizzato per l'indicizzazione e il messaggio con l'allegato verrà contrassegnato come parzialmente indicizzato.  <br/> <br/>**Nota:** L'analisi è il processo in cui il servizio di indicizzazione estrae il testo dall'allegato, rimuove i caratteri non necessari come la punteggiatura e gli spazi e quindi divide il testo in parole (in un processo denominato tokenation), che vengono quindi memorizzate nell'indice.           |
|Numero massimo di allegati  <br/> |250  <br/> |Numero massimo di file allegati a un messaggio di posta elettronica che verranno analizzati per l'indicizzazione. Se un messaggio contiene più di 250 allegati, i primi 250 allegati vengono analizzati e indicizzati e il messaggio viene contrassegnato come indicizzato parzialmente perché aveva allegati aggiuntivi che non sono stati analizzati.  <br/> |
|Profondità massima degli allegati  <br/> |30  <br/> |Numero massimo di allegati nidificati analizzati. Ad esempio, se a un messaggio di posta elettronica è associato un altro messaggio e al messaggio allegato è associato un documento di Word, il documento di Word e il messaggio allegato verranno indicizzati. Questo comportamento continuerà fino a 30 allegati nidificati.  <br/> |
|Numero massimo di immagini collegate  <br/> |0  <br/> |Un'immagine associata a un messaggio di posta elettronica viene ignorata dal parser e non è indicizzata.  <br/> |
|Tempo massimo per l'analisi di un elemento  <br/> |30 secondi  <br/> |Viene speso un massimo di 30 secondi per l'analisi di un elemento per l'indicizzazione. Se il tempo di analisi supera 30 secondi, l'elemento viene contrassegnato come parzialmente indicizzato.  <br/> |
|Output del parser massimo  <br/> |2 milioni di caratteri  <br/> |La quantità massima di output di testo del parser indicizzato. Ad esempio, se il parser ha Estratto 8 milioni caratteri da un documento, solo i primi 2 milioni caratteri vengono indicizzati.  <br/> |
|Token di annotazione massimi  <br/> |2 milioni  <br/> |Quando un messaggio di posta elettronica viene indicizzato, ogni parola viene annotata con istruzioni di elaborazione diverse che specificano la modalità di indicizzazione di tale parola. Ogni set di istruzioni di elaborazione è denominato token di annotazione. Per mantenere la qualità del servizio in Office 365, è presente un limite di 2 milioni token di annotazione per un messaggio di posta elettronica.  <br/> |
|Dimensione massima del corpo nell'indice  <br/> |67 milioni caratteri  <br/> |Il numero totale di caratteri presenti nel corpo di un messaggio di posta elettronica e di tutti gli allegati. Quando un messaggio di posta elettronica viene indicizzato, tutto il testo nel corpo del messaggio e in tutti gli allegati viene concatenato in una singola stringa. Le dimensioni massime della stringa indicizzata sono 67 milioni caratteri.  <br/> |
|Numero massimo di token univoci nel corpo  <br/> |1 milione  <br/> |Come spiegato in precedenza, i token sono il risultato dell'estrazione del testo dal contenuto, la rimozione della punteggiatura e degli spazi e quindi la suddivisione in parole (denominate token) memorizzate nell'indice. Ad esempio, la frase  `"cat, mouse, bird, dog, dog"` contiene 5 token. Ma solo 4 di questi sono token univoci. Vi è un limite di 1 milione token univoci per ogni messaggio di posta elettronica, che consente di evitare che l'indice venga troppo esteso con token casuali.  <br/> |
|||
  
## <a name="more-information"></a>Ulteriori informazioni

Sono disponibili ulteriori limiti relativi a diversi aspetti della ricerca di contenuto, ad esempio l'indicizzazione del contenuto. Per ulteriori informazioni su questi limiti, vedere i seguenti argomenti:

- [Elementi parzialmente indicizzati in Ricerca contenuto](partially-indexed-items-in-content-search.md)

- [Analisi degli elementi parzialmente indicizzati in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

- [Limiti della ricerca per SharePoint Online](https://docs.microsoft.com/sharepoint/search-limits)

Per informazioni sulle ricerche di contenuto, vedere:
  
- [Ricerca contenuto in Microsoft 365](content-search.md)

- [Ricerca di contenuto in un caso di eDiscovery di base](search-for-content-in-core-ediscovery.md)

- [Query di parole chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md)

Per i limiti relativi al caso di eDiscovery di base e eDiscovery avanzato, vedere:

- [Limiti in eDiscovery di base](limits-core-ediscovery.md)

- [Limiti di Advanced eDiscovery](limits-ediscovery20.md)
