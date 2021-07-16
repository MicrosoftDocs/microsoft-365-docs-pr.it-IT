---
title: Limiti per Ricerca contenuto ed eDiscovery di base nel Centro conformità
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
description: Informazioni sui limiti in vigore per le funzionalità ricerca contenuto e eDiscovery di base nell'Centro conformità Microsoft 365.
ms.openlocfilehash: db0f24d66fd7dc23a82a5ededfcfbc4d9edabad7
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53463986"
---
# <a name="limits-for-ediscovery-search"></a>Limiti per la ricerca eDiscovery

Diversi limiti vengono applicati agli strumenti di ricerca di eDiscovery nella Centro conformità Microsoft 365. Sono incluse le ricerche eseguite nella **pagina Ricerca** contenuto e le ricerche associate a un caso di eDiscovery nella pagina **Core eDiscovery.** Questi limiti consentono di mantenere l'integrità e la qualità dei servizi forniti alle organizzazioni. Esistono anche limiti relativi all'indicizzazione dei messaggi di posta elettronica in Exchange Online ricerca. Non è possibile modificare i limiti per le ricerche di eDiscovery o l'indicizzazione della posta elettronica, ma è necessario conoscerli in modo da poter prendere in considerazione questi limiti durante la pianificazione, l'esecuzione e la risoluzione dei problemi delle ricerche di eDiscovery.

Per i limiti correlati allo strumento Advanced eDiscovery, vedere [Limiti in Advanced eDiscovery](limits-ediscovery20.md)

## <a name="search-limits"></a>Limiti relativi alla ricerca

Nella tabella seguente sono elencati i limiti di ricerca quando si utilizza lo strumento di ricerca contenuto nel Centro conformità Microsoft 365 e per le ricerche associate a un caso di eDiscovery di base.

<br>

****

|Descrizione del limite|Limite|
|---|---|
|Numero massimo di cassette postali o siti in cui è possibile eseguire ricerche in una singola ricerca|Nessun limite <sup>1</sup>|
|Numero massimo di ricerche che possono essere eseguite contemporaneamente nell'organizzazione.|30|
|Numero massimo di ricerche a livello di organizzazione che possono essere eseguite contemporaneamente.|3 |
|Numero massimo di ricerche che un singolo utente può avviare contemporaneamente. Questo limite è molto probabilmente raggiunto quando l'utente tenta di avviare più ricerche utilizzando il comando **Get-ComplianceSearch \| Start-ComplianceSearch** in PowerShell del Centro sicurezza & conformità.|10 |
|Numero massimo di elementi per cassetta postale utente visualizzati nella pagina di anteprima durante l'anteprima dei risultati di Ricerca contenuto.|100|
|Il numero massimo di elementi trovati in tutte le cassette postali degli utenti che possono essere visualizzati nella pagina di anteprima durante l'anteprima dei risultati della ricerca. Vengono visualizzati gli elementi più recenti.|1.000 <sup>2</sup>|
|Numero massimo di cassette postali utente che è possibile visualizzare in anteprima per i risultati della ricerca. Se sono presenti più di 1000 cassette postali che contengono contenuto corrispondente alla query di ricerca, al massimo, solo le prime 1000 cassette postali con il maggior numero di risultati di ricerca saranno disponibili per l'anteprima.|1,000|
|Numero massimo di elementi trovati nei siti SharePoint e OneDrive for Business visualizzati nella pagina di anteprima durante l'anteprima dei risultati della ricerca. Vengono visualizzati gli elementi più recenti.|200|
|Numero massimo di siti (in SharePoint e OneDrive for Business) che possono essere visualizzati in anteprima per i risultati della ricerca. Se sono presenti più di 200 siti totali contenenti contenuto corrispondente alla query di ricerca, solo i 200 siti principali con il maggior numero di risultati di ricerca saranno disponibili per l'anteprima.|200|
|Il numero massimo di elementi per cassetta postale delle cartelle pubbliche che vengono visualizzati nella pagina di anteprima durante l'anteprima dei risultati della ricerca contenuto.|100|
|Numero massimo di elementi trovati in tutte le cassette postali delle cartelle pubbliche visualizzate nella pagina di anteprima durante l'anteprima dei risultati della ricerca contenuto.|200|
|Numero massimo di cassette postali delle cartelle pubbliche che possono essere visualizzate in anteprima per i risultati della ricerca. Se sono presenti più di 500 cassette postali di cartelle pubbliche che contengono contenuto corrispondente alla query di ricerca, solo le prime 500 cassette postali delle cartelle pubbliche con il maggior numero di risultati di ricerca saranno disponibili per l'anteprima.|500|
|Numero massimo di caratteri per la query di ricerca ,inclusi gli operatori e le condizioni, per una ricerca. <p> **Nota:** Questo limite ha effetto dopo l'espansione della query e include i caratteri della query con parole chiave, eventuali filtri delle autorizzazioni di ricerca applicati all'utente e gli URL di tutte le posizioni del sito. Ciò significa che la query verrà espansa in base a ognuna delle parole chiave. Se ad esempio una query di ricerca include 15 parole chiave e parametri e condizioni aggiuntivi, la query viene espansa 15 volte, ognuna con gli altri parametri e condizioni della query. Pertanto, anche se il numero di caratteri nella query di ricerca potrebbe essere inferiore al limite, è la query espansa che può contribuire a superare questo limite.|**Cassette postali:** 10.000. <p> **Siti:** 4.000 durante la ricerca in tutti i siti o 2.000 durante la ricerca fino a 20 siti. <sup>3</sup>|
|Numero massimo di varianti restituite quando si utilizza un carattere jolly prefisso per cercare una frase esatta in una query di ricerca o quando si utilizza un carattere jolly prefisso e l'operatore **booleano NEAR.**|10.000 <sup>4</sup>|
|Numero minimo di caratteri alfa per i caratteri jolly del prefisso. ad `time*` esempio, , `one*` o `set*` .|3 |
|Numero massimo di cassette postali in una ricerca in cui è possibile eliminare elementi eseguendo un'azione di "ricerca ed eliminazione" (utilizzando il comando **New-ComplianceSearchAction -Purge).** Se la ricerca per cui si sta eseguendo un'azione di eliminazione ha più cassette postali di origine rispetto a questo limite, l'azione di eliminazione avrà esito negativo. Per ulteriori informazioni sulla ricerca e sull'eliminazione, vedere [Search for and delete email messages in your organization](search-for-and-delete-messages-in-your-organization.md).|50.000|
|Numero massimo di posizioni in una ricerca da cui è possibile esportare gli elementi. Se la ricerca che si sta esportando ha più posizioni oltre questo limite, l'esportazione avrà esito negativo. Per ulteriori informazioni, vedere [Export content search results](export-search-results.md).|100,000|
|||

> [!NOTE]
> <sup>1</sup> Sebbene sia possibile eseguire ricerche in un numero illimitato di cassette postali in una singola ricerca, è possibile scaricare solo i risultati della ricerca esportati da un massimo di 100.000 cassette postali utilizzando lo strumento di esportazione di eDiscovery nel Centro conformità Microsoft 365.
>
> <sup>2</sup> Lo scopo della pagina di anteprima è mostrare un campione limitato dei risultati. Anche per ricerche di grandi dimensioni con migliaia di risultati, il numero di elementi visualizzati nella pagina di anteprima può e spesso essere molto inferiore al valore massimo possibile di 1000. Per visualizzare i risultati di ricerca completi, è necessario esportare i risultati.
>
> <sup>3</sup> Quando si SharePoint e OneDrive for Business percorsi, i caratteri negli URL dei siti in cui viene eseguita la ricerca vengono conteggiati rispetto a questo limite.
>
> <sup>4</sup> Per le query non di frase (un valore di parola chiave che non utilizza virgolette doppie) viene utilizzato un indice di prefisso speciale. Ciò indica che una parola si trova in un documento, ma non dove si verifica nel documento. Per eseguire una query di frase (un valore di parola chiave con virgolette doppie), è necessario confrontare la posizione all'interno del documento per le parole nella frase. Ciò significa che non è possibile utilizzare l'indice del prefisso per le query di frase. In questo caso, la query viene espansa internamente con tutte le parole possibili a cui si espande il prefisso. ad esempio, `"time*"` può espandere fino a `"time OR timer OR times OR timex OR timeboxed OR ..."` . 10.000 è il numero massimo di varianti che la parola può espandere, non il numero di documenti corrispondenti alla query. Non esiste un limite massimo per i termini non frasi.

## <a name="search-times"></a>Tempi di ricerca

Microsoft raccoglie informazioni sulle prestazioni per le ricerche eseguite da tutte le organizzazioni. Sebbene la complessità della query di ricerca possa influire sui tempi di ricerca, il fattore principale che influisce sul tempo necessario per una ricerca è il numero di cassette postali in cui la ricerca viene eseguita. Anche se Microsoft non fornisce un contratto di servizio per i tempi di ricerca, nella tabella seguente sono elencati i tempi medi di ricerca per le ricerche di raccolta in base al numero di cassette postali incluse nella ricerca.

<br>

****

|Numero di cassette postali|Tempo medio di ricerca|
|---|---|
|100|30 secondi|
|1.000|45 secondi|
|10.000|4 minuti|
|25.000|10 minuti|
|50.000|20 minuti|
|100.000|25 minuti|
|||

## <a name="export-limits"></a>Limiti di esportazione

Nella tabella seguente sono elencati i limiti per l'esportazione dei risultati di una ricerca di contenuto. Questi limiti si applicano anche quando si esporta il contenuto da un caso di eDiscovery di base.

<br>

****

|Descrizione del limite|Limite|
|---|---|
|Quantità massima di dati esportabili da una singola ricerca  <p> **Nota:** Se i risultati della ricerca sono superiori a 2 TB, è consigliabile utilizzare intervalli di date o altri tipi di filtri per ridurre le dimensioni totali dei risultati della ricerca.|2 TB|
|Numero massimo di organizzazioni che è possibile esportare in un solo giorno <p> **Nota:** Questo limite viene reimpostato ogni giorno alle 12:00 UTC|2 TB|
|Numero massimo di esportazioni simultanee che possono essere eseguite contemporaneamente all'interno dell'organizzazione <p> **Nota:** **L'esecuzione di un report Solo** l'esportazione viene eseguita in base alle esportazioni simultanee totali per l'organizzazione. Se tre utenti eseguono 3 esportazioni ciascuna, è possibile eseguire solo un'altra esportazione. Indipendentemente dal fatto che esporti un report o i risultati della ricerca, non è possibile eseguire altre esportazioni finché non ne viene completata una.|10 |
|Numero massimo di esportazioni che un singolo utente può eseguire contemporaneamente|3 |
|Numero massimo di cassette postali per i risultati della ricerca che possono essere scaricate tramite lo strumento di esportazione di eDiscovery|100,000|
|Dimensione massima del file PST che può essere esportato <p> **Nota:** Se i risultati della ricerca dalla cassetta postale di un utente sono superiori a 10 GB, i risultati della ricerca per la cassetta postale verranno esportati in due (o più) file PST separati. Se si sceglie di esportare tutti i risultati della ricerca in un singolo file PST, il file PST verrà inserito in file PST aggiuntivi se la dimensione totale dei risultati della ricerca è superiore a 10 GB. Se si desidera modificare questa dimensione predefinita, è possibile modificare il Registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Vedere [Change the size of PST files when exporting eDiscovery search results](change-the-size-of-pst-files-when-exporting-results.md). I risultati della ricerca provenienti da una cassetta postale specifica non verranno suddivisi tra più file PST, a meno che il contenuto di una singola cassetta postale non sia superiore a 10 GB. Se si è scelto di esportare i risultati della ricerca in un file PST contenente tutti i messaggi in una singola cartella e i risultati della ricerca sono superiori a 10 GB, gli elementi sono ancora organizzati in ordine cronologico, quindi verranno suddivisi in altri file PST in base alla data di invio.|10 GB|
|Frequenza con cui i risultati della ricerca delle cassette postali e dei siti vengono caricati in un percorso Archiviazione di Azure fornito da Microsoft.|Massimo 2 GB all'ora|
|||

## <a name="indexing-limits-for-email-messages"></a>Limiti di indicizzazione per i messaggi di posta elettronica

Nella tabella seguente vengono descritti i limiti di indicizzazione che potrebbero comportare la visualizzazione di un messaggio di posta elettronica come elemento non indicizzato o parzialmente indicizzato nei risultati di una ricerca di contenuto.

<br>

****

|Limite di indicizzazione|Valore massimo|Descrizione|
|---|---|---|
|Dimensione massima degli allegati|150 MB|Dimensione massima di un allegato di posta elettronica che verrà analizzato per l'indicizzazione. Qualsiasi allegato superiore a questo limite non verrà analizzato per l'indicizzazione e il messaggio con l'allegato verrà contrassegnato come parzialmente indicizzato. <p> **Nota:** L'analisi è il processo in cui il servizio di indicizzazione estrae il testo dall'allegato, rimuove i caratteri non necessari come punteggiatura e spazi e quindi divide il testo in parole (in un processo denominato tokenization), che vengono quindi archiviate nell'indice.|
|Numero massimo di allegati|250|Numero massimo di file allegati a un messaggio di posta elettronica che verranno analizzati per l'indicizzazione. Se un messaggio contiene più di 250 allegati, i primi 250 allegati vengono analizzati e indicizzati e il messaggio viene contrassegnato come parzialmente indicizzato perché contiene allegati aggiuntivi che non sono stati analizzati.|
|Profondità massima degli allegati|30|Numero massimo di allegati annidati analizzati. Ad esempio, se a un messaggio di posta elettronica è allegato un altro messaggio e al messaggio allegato è allegato un documento di Word, il documento di Word e il messaggio allegato verranno indicizzati. Questo comportamento continuerà fino a 30 allegati annidati.|
|Numero massimo di immagini allegate|0|Un'immagine allegata a un messaggio di posta elettronica viene ignorata dal parser e non viene indicizzata.|
|Tempo massimo dedicato all'analisi di un elemento|30 secondi|Vengono trascorsi al massimo 30 secondi per l'analisi di un elemento per l'indicizzazione. Se il tempo di analisi supera i 30 secondi, l'elemento viene contrassegnato come parzialmente indicizzato.|
|Output massimo parser|2 milioni di caratteri|Quantità massima di output di testo dal parser indicizzato. Ad esempio, se il parser ha estratto 8 milioni di caratteri da un documento, vengono indicizzati solo i primi 2 milioni di caratteri.|
|Numero massimo di token di annotazione|2 milioni|Quando un messaggio di posta elettronica viene indicizzato, ogni parola viene annotata con istruzioni di elaborazione diverse che specificano la modalità di indicizzazione di tale parola. Ogni set di istruzioni di elaborazione è denominato token di annotazione. Per mantenere la qualità del servizio in Office 365, è previsto un limite di 2 milioni di token di annotazione per un messaggio di posta elettronica.|
|Dimensioni massime del corpo nell'indice|67 milioni di caratteri|Numero totale di caratteri nel corpo di un messaggio di posta elettronica e di tutti i relativi allegati. Quando un messaggio di posta elettronica viene indicizzato, tutto il testo nel corpo del messaggio e in tutti gli allegati viene concatenato in una singola stringa. La dimensione massima di questa stringa indicizzata è di 67 milioni di caratteri.|
|Numero massimo di token univoci nel corpo|1 milione|Come spiegato in precedenza, i token sono il risultato dell'estrazione del testo dal contenuto, della rimozione della punteggiatura e degli spazi e quindi della suddivisione in parole (detti token) archiviate nell'indice. Ad esempio, la frase `"cat, mouse, bird, dog, dog"` contiene 5 token. Ma solo 4 di questi sono token univoci. Esiste un limite di 1 milione di token univoci per ogni messaggio di posta elettronica, che consente di evitare che l'indice sia troppo grande con token casuali.|
|||

## <a name="more-information"></a>Altre informazioni

Esistono ulteriori limiti correlati a diversi aspetti della ricerca di contenuto, ad esempio l'indicizzazione del contenuto. Per ulteriori informazioni su questi limiti, vedere i seguenti argomenti:

- [Elementi parzialmente indicizzati in Ricerca contenuto](partially-indexed-items-in-content-search.md)

- [Analisi degli elementi parzialmente indicizzati in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

- [Limiti di ricerca per SharePoint Online](/sharepoint/search-limits)

Per informazioni sulle ricerche di contenuto, vedere:

- [Ricerca contenuto in Microsoft 365](content-search.md)

- [Cercare contenuto in un caso di eDiscovery di base](search-for-content-in-core-ediscovery.md)

- [Query con parole chiave e condizioni di ricerca per la ricerca di contenuto](keyword-queries-and-search-conditions.md)

Per i limiti dei casi correlati a Core eDiscovery e Advanced eDiscovery, vedere:

- [Limiti in Core eDiscovery](limits-core-ediscovery.md)

- [Limiti di Advanced eDiscovery](limits-ediscovery20.md)
