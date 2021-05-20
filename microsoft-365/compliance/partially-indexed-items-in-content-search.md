---
title: Elementi parzialmente indicizzati in Ricerca contenuto e altri strumenti di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnindexedItemsLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: Informazioni sugli elementi non indicizzati in Exchange e SharePoint che è possibile includere in una ricerca eDiscovery eseguita nel Centro Microsoft 365 conformità.
ms.openlocfilehash: e1730959cd3177fe1f7bce1f0315c871b5a57598
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537656"
---
# <a name="partially-indexed-items-in-ediscovery"></a>Elementi parzialmente indicizzati in eDiscovery

Una ricerca eDiscovery eseguita dal Centro conformità Microsoft 365 include automaticamente elementi parzialmente indicizzati nei risultati di ricerca stimati quando si esegue una ricerca. Gli elementi parzialmente indicizzati sono Exchange di cassette postali e documenti nei siti SharePoint e OneDrive for Business che per qualche motivo non sono stati completamente indicizzati per la ricerca. In Exchange, un elemento parzialmente indicizzato in genere contiene un file (di un tipo di file che non può essere indicizzato) allegato a un messaggio di posta elettronica. Ecco alcuni altri motivi per cui gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi parzialmente indicizzati quando si esegue una ricerca eDiscovery:
  
- Il tipo di file non è riconosciuto o supportato per l'indicizzazione.

- I messaggi dispongono di un file allegato senza un gestore valido, ad esempio file di immagine. questa è la causa più comune degli elementi di posta elettronica parzialmente indicizzati.

- Il tipo di file è supportato per l'indicizzazione ma si è verificato un errore di indicizzazione per un file specifico.

- Troppi file allegati a un messaggio di posta elettronica.

- Un file allegato a un messaggio di posta elettronica è troppo grande.

- Un file è crittografato con tecnologie non Microsoft.

- Un file è protetto da password.

> [!NOTE]
> La maggior parte delle organizzazioni ha meno dell'1% del contenuto in base al volume e meno del 12% per dimensioni parzialmente indicizzate. La differenza tra volume e dimensioni è che i file di dimensioni maggiori hanno una probabilità maggiore di contenere contenuto che non può essere indicizzato completamente.
  
Per indagini legali, l'organizzazione potrebbe essere necessaria per esaminare gli elementi parzialmente indicizzati. È inoltre possibile specificare se includere elementi parzialmente indicizzati quando si esportano i risultati della ricerca in un computer locale o quando si preparano i risultati per l'analisi con Advanced eDiscovery. Per ulteriori informazioni, vedere [Investigating partially indexed items in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md).
  
## <a name="file-types-not-indexed-for-search"></a>Tipi di file non indicizzati per la ricerca

Alcuni tipi di file, ad esempio i file Bitmap o MP3, non presentano contenuti che possono essere indicizzati. Di conseguenza, i server di indicizzazione della ricerca Exchange e SharePoint non eseguono l'indicizzazione full-text su questi tipi di file. Questi tipi di file sono considerati tipi di file non supportati. Esistono anche tipi di file pe i quali l'indicizzazione di testo completo è stata disattivata, o per impostazione predefinita o da un amministratore. I tipi di file non supportati e disabilitati sono etichettati come elementi non indicizzati nelle ricerche di contenuto. Come indicato in precedenza, gli elementi parzialmente indicizzati possono essere inclusi nel set di risultati di ricerca quando si esegue una ricerca, si esportano i risultati della ricerca in un computer locale o si preparano i risultati della ricerca per Advanced eDiscovery.
  
Per un elenco dei formati di file supportati e disabilitati, vedere i seguenti argomenti:
  
- **Exchange**  -  [Formati di file indicizzati da Exchange ricerca](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- **Exchange**  -  [Get-SearchDocumentFormat](/powershell/module/exchange/get-searchdocumentformat)

- **SharePoint**  -  [Estensioni di file sottoposte a ricerca per indicizzazione e tipi di file](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) analizzati predefiniti in SharePoint
  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>I messaggi e i documenti con tipi di file parzialmente indicizzati possono essere restituiti nei risultati della ricerca

Non tutti i messaggi di posta elettronica con un allegato di file parzialmente indicizzato o tutti i documenti SharePoint parzialmente indicizzati vengono restituiti automaticamente come elemento parzialmente indicizzato. Ciò è dovuto al fatto che altre proprietà del messaggio o del documento, ad esempio la proprietà **Subject** nei messaggi di posta elettronica e le proprietà **Title** o **Author** per i documenti vengono indicizzate e disponibili per la ricerca. Ad esempio, una ricerca tramite parola chiave per "finanziaria" restituirà gli elementi con un allegato di file parzialmente indicizzato se tale parola chiave viene visualizzata nell'oggetto di un messaggio di posta elettronica o nel nome di file o nel titolo di un documento. Tuttavia, se la parola chiave viene visualizzata solo nel corpo del file, il messaggio o il documento verrà restituito come elemento parzialmente indicizzato.
  
Analogamente, i messaggi con file allegati parzialmente indicizzati e documenti di un tipo di file parzialmente indicizzato vengono inclusi nei risultati della ricerca quando altri messaggi o proprietà del documento, indicizzati e disponibili per la ricerca, corrispondono ai criteri di ricerca. Le proprietà del messaggio che vengono indicizzate per la ricerca includono le date di invio e ricezione, il mittente e il destinatario, il nome del file di un allegato e il testo nel corpo del messaggio. Le proprietà del documento indicizzate per la ricerca includono le date create e modificate. Pertanto, anche se un allegato del messaggio può essere un elemento parzialmente indicizzato, il messaggio verrà incluso nei risultati di ricerca regolari se il valore di altre proprietà del messaggio o del documento corrisponde ai criteri di ricerca.
  
Per un elenco delle proprietà della posta elettronica e dei documenti che è possibile cercare utilizzando la funzionalità di ricerca nel Centro sicurezza & conformità, vedere Query con parole chiave e condizioni di ricerca [per eDiscovery.](keyword-queries-and-search-conditions.md)
  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Elementi parzialmente indicizzati inclusi nei risultati della ricerca

L'organizzazione potrebbe essere necessaria per identificare ed eseguire analisi aggiuntive su elementi parzialmente indicizzati per determinare cosa sono, cosa contengono e se sono rilevanti per un'indagine specifica. Come spiegato in precedenza, gli elementi parzialmente indicizzati nei percorsi di contenuto in cui viene eseguita la ricerca vengono inclusi automaticamente con i risultati di ricerca stimati. È possibile includere questi elementi parzialmente indicizzati quando si esportano i risultati della ricerca o si preparano i risultati della ricerca per Advanced eDiscovery.
  
Tenere presente quanto segue sugli elementi parzialmente indicizzati:
  
- Quando si esegue una ricerca eDiscovery, il numero totale e le dimensioni degli elementi Exchange parzialmente indicizzati (restituiti dalla query di ricerca) vengono visualizzati nelle statistiche di ricerca nella pagina a comparsa ed etichettati come elementi non indicizzati. Le statistiche sugli elementi parzialmente indicizzati visualizzati nella pagina a comparsa non includono elementi parzialmente indicizzati in SharePoint siti o OneDrive account.

- Se la ricerca da cui si esportano i risultati è una ricerca di percorsi di contenuto specifici o di tutti i percorsi di contenuto nell'organizzazione, verranno esportati solo gli elementi non indicizzati delle posizioni di contenuto che contengono elementi che soddisfano i criteri di ricerca. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Il motivo è che l'esportazione di elementi parzialmente indicizzati da numerose posizioni nell'organizzazione potrebbe aumentare la probabilità di errori di esportazione e aumentare il tempo necessario per esportare e scaricare i risultati della ricerca.

    Per esportare elementi parzialmente indicizzati da tutti i percorsi di contenuto per una ricerca, configurare la ricerca per restituire tutti gli elementi (rimuovendo eventuali parole chiave dalla query di ricerca) e quindi esportare solo gli elementi parzialmente indicizzati quando si esportano i risultati della ricerca (facendo clic su Solo gli elementi con un formato non **riconosciuto,** crittografati o non indicizzati per altri motivi in **Opzioni di output**).

- Se si sceglie di includere tutti gli elementi della cassetta postale nei risultati della ricerca o se una query di ricerca non specifica parole chiave o specifica solo un intervallo di date, gli elementi parzialmente indicizzati potrebbero non essere copiati nel file PST contenente gli elementi parzialmente indicizzati. Questo perché tutti gli elementi, inclusi gli elementi parzialmente indicizzati, verranno inclusi automaticamente nei risultati di ricerca regolari.

- Gli elementi parzialmente indicizzati non sono disponibili per l'anteprima. È necessario esportare i risultati della ricerca per visualizzare gli elementi parzialmente indicizzati restituiti dalla ricerca.

   Inoltre, quando si esportano i risultati della ricerca e si includono elementi parzialmente indicizzati nell'esportazione, gli elementi parzialmente indicizzati da elementi SharePoint vengono esportati in una cartella denominata **Uncrawlable.** Quando si esportano elementi Exchange parzialmente indicizzati, questi vengono esportati in modo diverso a seconda che gli elementi parzialmente indicizzati corrispondano o meno alla query di ricerca e alla configurazione delle impostazioni di esportazione. 

- Nella tabella seguente viene illustrato il comportamento di esportazione degli elementi indicizzati e parzialmente indicizzati e se ognuno di essi è incluso per le diverse impostazioni di configurazione dell'esportazione.

  |**Esportazione della configurazione**|**Elementi indicizzati che corrispondono alla query di ricerca**|**Elementi parzialmente indicizzati che corrispondono alla query di ricerca**|**Elementi parzialmente indicizzati che non corrispondono alla query di ricerca**|
  |:-----|:-----|:-----|:-----|
  |Esportare solo gli elementi indicizzati  <br/> |Esportato<br/> |Esportato (incluso con gli elementi indicizzati esportati)<br/>  |Non esportato <br/>|
  |Esportare solo elementi parzialmente indicizzati  <br/> |Non esportato  <br/> |Esportato (come elementi parzialmente indicizzati)<br/> |Esportato (come elementi parzialmente indicizzati)|
  |Esportare elementi indicizzati e parzialmente indicizzati  <br/> |Esportato<br/> |Esportato (incluso con gli elementi indicizzati esportati)<br/>  |Esportato (come elementi parzialmente indicizzati)<br/>|
  ||||
  
## <a name="indexing-limits-for-messages"></a>Limiti di indicizzazione per i messaggi

Nella tabella seguente vengono descritti i limiti di indicizzazione che potrebbero comportare la restituita di un messaggio di posta elettronica come elemento parzialmente indicizzato in una ricerca eDiscovery in Microsoft 365.
  
Per un elenco dei limiti di indicizzazione per SharePoint documenti, vedere Limiti di [ricerca per SharePoint Online.](/sharepoint/search-limits)
  
|**Limite di indicizzazione**|**Note**|**Descrizione**|
|:-----|:-----|:-----|
|Dimensioni massime degli allegati (ad Excel file)  <br/> |150 MB  <br/> |Dimensione massima di un allegato di posta elettronica che verrà analizzato per l'indicizzazione. Qualsiasi allegato superiore a questo limite non verrà analizzato per l'indicizzazione e il messaggio con l'allegato verrà contrassegnato come parzialmente indicizzato.  <br/><br/> **Nota:** L'analisi è il processo in cui il servizio di indicizzazione estrae il testo dall'allegato, rimuove i caratteri non necessari come punteggiatura e spazi e quindi divide il testo in parole (in un processo denominato tokenization), che vengono quindi archiviate nell'indice.           |
|Dimensioni massime dei Excel file  <br/> |4 MB  <br/> |La dimensione massima di un file Excel contenuto in un sito o allegato a un messaggio di posta elettronica che verrà analizzato per l'indicizzazione. Qualsiasi Excel file con dimensioni superiori a questo limite non verrà analizzato e il file o il messaggio di posta elettronica con il file allegato verrà contrassegnato come non indicizzato.  <br/> |
|Numero massimo di allegati  <br/> |250  <br/> |Numero massimo di file allegati a un messaggio di posta elettronica che verranno analizzati per l'indicizzazione. Se un messaggio contiene più di 250 allegati, i primi 250 allegati vengono analizzati e indicizzati e il messaggio viene contrassegnato come parzialmente indicizzato perché contiene allegati aggiuntivi che non sono stati analizzati.  <br/> |
|Profondità massima degli allegati  <br/> |30  <br/> |Numero massimo di allegati annidati analizzati. Ad esempio, se a un messaggio di posta elettronica è allegato un altro messaggio e al messaggio allegato è allegato un documento di Word, il documento di Word e il messaggio allegato verranno indicizzati. Questo comportamento continuerà fino a 30 allegati annidati.  <br/> |
|Numero massimo di immagini allegate  <br/> |0  <br/> |Un'immagine allegata a un messaggio di posta elettronica viene ignorata dal parser e non viene indicizzata.  <br/> |
|Tempo massimo dedicato all'analisi di un elemento  <br/> |30 secondi  <br/> |Vengono trascorsi al massimo 30 secondi per l'analisi di un elemento per l'indicizzazione. Se il tempo di analisi supera i 30 secondi, l'elemento viene contrassegnato come parzialmente indicizzato.  <br/> |
|Output massimo parser  <br/> |2 milioni di caratteri  <br/> |Quantità massima di output di testo dal parser indicizzato. Ad esempio, se il parser ha estratto 8 milioni di caratteri da un documento, vengono indicizzati solo i primi 2 milioni di caratteri.  <br/> |
|Numero massimo di token di annotazione  <br/> |2 milioni  <br/> |Quando un messaggio di posta elettronica viene indicizzato, ogni parola viene annotata con istruzioni di elaborazione diverse che specificano la modalità di indicizzazione di tale parola. Ogni set di istruzioni di elaborazione è denominato token di annotazione. Per mantenere la qualità del servizio in Office 365, è previsto un limite di 2 milioni di token di annotazione per un messaggio di posta elettronica.  <br/> |
|Dimensioni massime del corpo nell'indice  <br/> |67 milioni di caratteri  <br/> |Numero totale di caratteri nel corpo di un messaggio di posta elettronica e di tutti i relativi allegati. Quando un messaggio di posta elettronica viene indicizzato, tutto il testo nel corpo del messaggio e in tutti gli allegati viene concatenato in una singola stringa. La dimensione massima di questa stringa indicizzata è di 67 milioni di caratteri.  <br/> |
|Numero massimo di token univoci nel corpo  <br/> |1 milione  <br/> |Come spiegato in precedenza, i token sono il risultato dell'estrazione del testo dal contenuto, della rimozione della punteggiatura e degli spazi e quindi della suddivisione in parole (detti token) archiviate nell'indice. Ad esempio, la frase  `"cat, mouse, bird, dog, dog"` contiene 5 token. Ma solo 4 di questi sono token univoci. Esiste un limite di 1 milione di token univoci per ogni messaggio di posta elettronica, che consente di evitare che l'indice sia troppo grande con token casuali.  <br/> |
||||

## <a name="more-information-about-partially-indexed-items"></a>Ulteriori informazioni sugli elementi parzialmente indicizzati

- Come indicato in precedenza, poiché le proprietà del messaggio e del documento e i relativi metadati sono indicizzati, una ricerca con parole chiave potrebbe restituire risultati se tale parola chiave viene visualizzata nei metadati indicizzati. Tuttavia, la stessa ricerca di parole chiave potrebbe non restituire lo stesso elemento se la parola chiave viene visualizzata solo nel contenuto di un elemento con un tipo di file non supportato. In questo caso, l'elemento verrà restituito come elemento parzialmente indicizzato.

- Se un elemento parzialmente indicizzato viene incluso nei risultati della ricerca perché corrisponde ai criteri della query di ricerca, non verrà incluso come elemento parzialmente indicizzato nelle statistiche di ricerca stimate. Inoltre, non verrà incluso con elementi parzialmente indicizzati quando si esportano i risultati della ricerca.

- Anche se un tipo di file è supportato per l'indicizzazione e indicizzato, possono verificarsi errori di indicizzazione o di ricerca che causeranno la restituire un file come elemento parzialmente indicizzato. Ad esempio, la ricerca di un file Excel di grandi dimensioni potrebbe avere esito positivo parzialmente (perché i primi 4 MB sono indicizzati), ma quindi non riesce perché il limite di dimensioni del file viene superato. In questo caso, è possibile che lo stesso file sia restituito con i risultati della ricerca e come elemento parzialmente indicizzato.

- I file crittografati con le tecnologie di crittografia [Microsoft](encryption.md) e allegati a un messaggio di posta elettronica che corrisponde ai criteri di una ricerca possono essere visualizzati in anteprima e decrittografati quando vengono esportati. Al momento, i file crittografati con le tecnologie di crittografia Microsoft (e archiviati in SharePoint o OneDrive for Business) vengono parzialmente indicizzati.

- I messaggi di posta elettronica crittografati con S/MIME sono parzialmente indicizzati. Sono inclusi i messaggi crittografati con o senza allegati.

- I messaggi di posta elettronica protetti con Azure Rights Management vengono indicizzati e verranno inclusi nei risultati della ricerca se corrispondono alla query di ricerca. I messaggi di posta elettronica protetti da diritti vengono decrittografati e possono essere visualizzati in anteprima ed esportati. Questa funzionalità richiede l'assegnazione del ruolo decrittografia RMS, assegnato per impostazione predefinita al gruppo di ruoli eDiscover Manager.

- Se si crea un'esenzione basata su query associata a un caso di eDiscovery, tutti gli elementi parzialmente indicizzati vengono messi in attesa. Sono inclusi gli elementi parzialmente indicizzati che non corrispondono ai criteri della query di ricerca per l'esenzione. Per ulteriori informazioni sulla creazione di blocchi eDiscovery basati su query, vedere [Create an eDiscovery hold](create-ediscovery-holds.md).

## <a name="see-also"></a>Vedere anche

[Analisi degli elementi parzialmente indicizzati in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)