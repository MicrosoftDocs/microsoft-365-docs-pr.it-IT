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
description: Informazioni sugli elementi non indicizzati in Exchange e SharePoint che è possibile includere in una ricerca eDiscovery eseguita nel Centro conformità Microsoft 365.
ms.openlocfilehash: 308e0755f1966b8e4559cf6f08b3133a00ea1b5a
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711906"
---
# <a name="partially-indexed-items-in-ediscovery"></a>Elementi parzialmente indicizzati in eDiscovery

Una ricerca eDiscovery eseguita dal Centro conformità Microsoft 365 include automaticamente gli elementi parzialmente indicizzati nei risultati di ricerca stimati quando si esegue una ricerca. Gli elementi parzialmente indicizzati sono elementi e documenti delle cassette postali di Exchange nei siti di SharePoint e OneDrive for Business che per qualche motivo non sono stati completamente indicizzati per la ricerca. In Exchange, un elemento parzialmente indicizzato contiene in genere un file (di un tipo di file che non può essere indicizzato) allegato a un messaggio di posta elettronica. Ecco alcuni altri motivi per cui gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi parzialmente indicizzati quando si esegue una ricerca eDiscovery:
  
- Il tipo di file non è riconosciuto o supportato per l'indicizzazione.

- I messaggi hanno un file allegato senza un gestore valido, ad esempio i file di immagine; questa è la causa più comune di elementi di posta elettronica parzialmente indicizzati.

- Il tipo di file è supportato per l'indicizzazione ma si è verificato un errore di indicizzazione per un file specifico.

- Troppi file allegati a un messaggio di posta elettronica.

- Un file allegato a un messaggio di posta elettronica è troppo grande.

- Un file è crittografato con tecnologie non Microsoft.

- Un file è protetto da password.

> [!NOTE]
> La maggior parte delle organizzazioni ha meno dell'1% del contenuto in base al volume e meno del 12% per dimensioni parzialmente indicizzate. Il motivo della differenza tra volume e dimensioni è che i file di dimensioni maggiori hanno una probabilità maggiore di contenere contenuto che non può essere completamente indicizzato.
  
Per le indagini legali, è possibile che all'organizzazione venga richiesto di esaminare gli elementi parzialmente indicizzati. È inoltre possibile specificare se includere elementi parzialmente indicizzati quando si esportano i risultati della ricerca in un computer locale o quando si preparano i risultati per l'analisi con Advanced eDiscovery. Per ulteriori informazioni, vedere [Analisi degli elementi parzialmente indicizzati in eDiscovery.](investigating-partially-indexed-items-in-ediscovery.md)
  
## <a name="file-types-not-indexed-for-search"></a>Tipi di file non indicizzati per la ricerca

Alcuni tipi di file, ad esempio i file Bitmap o MP3, non presentano contenuti che possono essere indicizzati. Di conseguenza, i server di indicizzazione della ricerca in Exchange e SharePoint non eseguono l'indicizzazione full-text su questi tipi di file. Questi tipi di file sono considerati tipi di file non supportati. Esistono anche tipi di file pe i quali l'indicizzazione di testo completo è stata disattivata, o per impostazione predefinita o da un amministratore. I tipi di file non supportati e disabilitati vengono etichettati come elementi non indicizzati nelle ricerche di contenuto. Come indicato in precedenza, gli elementi parzialmente indicizzati possono essere inclusi nel set di risultati di ricerca quando si esegue una ricerca, si esportano i risultati della ricerca in un computer locale o si preparano i risultati della ricerca per Advanced eDiscovery.
  
Per un elenco dei formati di file supportati e disabilitati, vedere i seguenti argomenti:
  
- **Exchange**  -  [Formati di file indicizzati da Ricerca di Exchange](https://go.microsoft.com/fwlink/p/?LinkID=386618)

- **Exchange**  -  [Get-SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)

- **SharePoint**  -  [Estensioni di file sottoposte a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint](https://go.microsoft.com/fwlink/p/?LinkID=404033)
  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>I messaggi e i documenti con tipi di file parzialmente indicizzati possono essere restituiti nei risultati della ricerca

Non tutti i messaggi di posta elettronica con un allegato di file parzialmente indicizzato o ogni documento di SharePoint parzialmente indicizzato vengono restituiti automaticamente come elemento parzialmente indicizzato. Ciò è dovuto al fatto che altre proprietà del messaggio o del documento, ad esempio la proprietà **Subject** nei messaggi di posta elettronica e le proprietà **Title** o **Author** per i documenti vengono indicizzate e possono essere cercate. Ad esempio, una ricerca tramite parola chiave per "financial" restituirà gli elementi con un file allegato parzialmente indicizzato se tale parola chiave viene visualizzata nell'oggetto di un messaggio di posta elettronica o nel nome di file o nel titolo di un documento. Tuttavia, se la parola chiave viene visualizzata solo nel corpo del file, il messaggio o il documento verrà restituito come elemento parzialmente indicizzato.
  
Analogamente, i messaggi con allegati di file parzialmente indicizzati e documenti di un tipo di file parzialmente indicizzato vengono inclusi nei risultati della ricerca quando altri messaggi o proprietà dei documenti, indicizzati e disponibili per la ricerca, soddisfano i criteri di ricerca. Le proprietà del messaggio che vengono indicizzate per la ricerca includono le date di invio e ricezione, il mittente e il destinatario, il nome del file di un allegato e il testo nel corpo del messaggio. Le proprietà del documento indicizzate per la ricerca includono le date create e modificate. Pertanto, anche se un allegato del messaggio può essere un elemento parzialmente indicizzato, il messaggio verrà incluso nei risultati di ricerca regolari se il valore di altre proprietà del messaggio o del documento corrisponde ai criteri di ricerca.
  
Per un elenco delle proprietà della posta elettronica e dei documenti che è possibile cercare utilizzando la funzionalità di ricerca nel Centro sicurezza & conformità, vedere Query con parole chiave e condizioni di ricerca per [eDiscovery.](keyword-queries-and-search-conditions.md)
  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Elementi parzialmente indicizzati inclusi nei risultati della ricerca

All'organizzazione potrebbe essere richiesto di identificare ed eseguire un'analisi aggiuntiva su elementi parzialmente indicizzati per determinare cosa sono, cosa contengono e se sono rilevanti per un'indagine specifica. Come descritto in precedenza, gli elementi parzialmente indicizzati nei percorsi di contenuto in cui viene eseguita la ricerca vengono inclusi automaticamente nei risultati di ricerca stimati. È possibile includere questi elementi parzialmente indicizzati quando si esportano i risultati della ricerca o si preparano i risultati della ricerca per Advanced eDiscovery.
  
Tenere presente quanto segue sugli elementi parzialmente indicizzati:
  
- Quando si esegue una ricerca eDiscovery, il numero totale e le dimensioni degli elementi di Exchange parzialmente indicizzati (restituiti dalla query di ricerca) vengono visualizzati nelle statistiche di ricerca nella pagina a comparsa ed etichettati come elementi non indicizzati. Le statistiche relative agli elementi parzialmente indicizzati visualizzati nella pagina a comparsa non includono gli elementi parzialmente indicizzati in SharePoint o OneDrive.

- Se la ricerca da cui si esportano i risultati è una ricerca di percorsi di contenuto specifici o di tutti i percorsi di contenuto dell'organizzazione, verranno esportati solo gli elementi non indicizzati dei percorsi di contenuto che contengono elementi che soddisfano i criteri di ricerca. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Il motivo è che l'esportazione di elementi parzialmente indicizzati da molte posizioni nell'organizzazione potrebbe aumentare la probabilità di errori di esportazione e il tempo necessario per esportare e scaricare i risultati della ricerca.

    Per esportare elementi parzialmente indicizzati da tutti i percorsi di contenuto per una ricerca, configurare la ricerca per restituire tutti gli elementi (rimuovendo le parole chiave dalla query di ricerca) e quindi esportare solo gli elementi parzialmente indicizzati quando si esportano i risultati della ricerca (facendo clic su Solo gli elementi con un formato non **riconosciuto,** crittografati o non indicizzati per altri motivi in Opzioni **di output).**

- Se si sceglie di includere tutti gli elementi della cassetta postale nei risultati della ricerca o se una query di ricerca non specifica parole chiave o specifica solo un intervallo di date, gli elementi parzialmente indicizzati potrebbero non essere copiati nel file PST contenente gli elementi parzialmente indicizzati. Questo perché tutti gli elementi, inclusi gli elementi parzialmente indicizzati, verranno inclusi automaticamente nei risultati di ricerca normali.

- Gli elementi parzialmente indicizzati non sono disponibili per la visualizzazione in anteprima. È necessario esportare i risultati della ricerca per visualizzare gli elementi parzialmente indicizzati restituiti dalla ricerca.

Inoltre, quando si esportano i risultati della ricerca e si includono elementi parzialmente indicizzati nell'esportazione, gli elementi parzialmente indicizzati dagli elementi di SharePoint vengono esportati in una cartella denominata **Uncrawlable.** Quando si esportano elementi di Exchange parzialmente indicizzati, questi vengono esportati in modo diverso a seconda che gli elementi parzialmente indicizzati corrispondano alla query di ricerca e alla configurazione delle impostazioni di esportazione. 

Nella tabella seguente viene illustrato il comportamento di esportazione di elementi indicizzati e parzialmente indicizzati e se ognuno di essi è incluso per le diverse impostazioni di configurazione dell'esportazione.

|**Configurazione esportazione**|**Elementi indicizzati che corrispondono alla query di ricerca**|**Elementi parzialmente indicizzati che corrispondono alla query di ricerca**|**Elementi parzialmente indicizzati che non corrispondono alla query di ricerca**|
|:-----|:-----|:-----|:-----|
|Esportare solo gli elementi indicizzati  <br/> |Esportato<br/> |Esportato (incluso con gli elementi indicizzati esportati)<br/>  |Non esportato <br/>|
|Esportare solo elementi parzialmente indicizzati  <br/> |Non esportato  <br/> |Esportato (come elementi parzialmente indicizzati)<br/> |Esportato (come elementi parzialmente indicizzati)|
|Esportare elementi indicizzati e parzialmente indicizzati  <br/> |Esportato<br/> |Esportato (incluso con gli elementi indicizzati esportati)<br/>  |Esportato (come elementi parzialmente indicizzati)<br/>|
||||

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Elementi parzialmente indicizzati esclusi dai risultati della ricerca

Se un elemento è parzialmente indicizzato ma non soddisfa i criteri della query di ricerca, non verrà incluso come elemento parzialmente indicizzato nei risultati della ricerca. In altre parole, l'elemento viene escluso dai risultati della ricerca. Si supponga, ad esempio, di eseguire una ricerca e di non includere parole chiave o proprietà perché si desidera includere tutto il contenuto. È tuttavia incluso un intervallo di date per la query. Se un elemento parzialmente indicizzato non rientra nell'intervallo di date specificato, non verrà incluso come elemento parzialmente indicizzato. Gli intervalli di date sono un modo efficace per escludere gli elementi parzialmente indicizzati dai risultati della ricerca.
  
Analogamente, se si sceglie di includere elementi parzialmente indicizzati quando si esportano i risultati di una ricerca, gli elementi parzialmente indicizzati esclusi dai risultati della ricerca non verranno esportati.
  
Un'eccezione a questa regola è quando si crea un blocco basato su query associato a un caso di eDiscovery. Se si crea un blocco eDiscovery basato su query, tutti gli elementi parzialmente indicizzati vengono messi in attesa. Sono inclusi gli elementi parzialmente indicizzati che non corrispondono ai criteri della query di ricerca e gli elementi parzialmente indicizzati che potrebbero non rientrare in una condizione di intervallo di date. Per ulteriori informazioni sulla creazione di blocchi di eDiscovery basati su query, vedere [Creare un blocco di eDiscovery.](create-ediscovery-holds.md)
  
## <a name="indexing-limits-for-messages"></a>Limiti di indicizzazione per i messaggi

Nella tabella seguente vengono descritti i limiti di indicizzazione che potrebbero comportare la restituita di un messaggio di posta elettronica come elemento parzialmente indicizzato in una ricerca eDiscovery in Microsoft 365.
  
Per un elenco dei limiti di indicizzazione per i documenti di SharePoint, vedere [Limiti di ricerca per SharePoint Online.](https://docs.microsoft.com/sharepoint/search-limits)
  
|**Limite di indicizzazione**|**Note**|**Descrizione**|
|:-----|:-----|:-----|
|Dimensione massima degli allegati (esclusi i file di Excel)  <br/> |150 MB  <br/> |La dimensione massima di un allegato di posta elettronica che verrà analizzato per l'indicizzazione. Qualsiasi allegato superiore a questo limite non verrà analizzato per l'indicizzazione e il messaggio con l'allegato verrà contrassegnato come parzialmente indicizzato.  <br/><br/> **Nota:** L'analisi è il processo in cui il servizio di indicizzazione estrae testo dall'allegato, rimuove i caratteri non necessari come punteggiatura e spazi e quindi divide il testo in parole (in un processo denominato tokenizzazione), che vengono quindi archiviate nell'indice.           |
|Dimensioni massime dei file di Excel  <br/> |4 MB  <br/> |Dimensione massima di un file di Excel che si trova in un sito o allegato a un messaggio di posta elettronica che verrà analizzato per l'indicizzazione. I file di Excel superiori a questo limite non verranno analizzati e il file o il messaggio di posta elettronica con il file allegato verrà contrassegnato come non indicizzato.  <br/> |
|Numero massimo di allegati  <br/> |250  <br/> |Numero massimo di file allegati a un messaggio di posta elettronica che verranno analizzati per l'indicizzazione. Se un messaggio contiene più di 250 allegati, i primi 250 allegati vengono analizzati e indicizzati e il messaggio viene contrassegnato come parzialmente indicizzato perché contiene allegati aggiuntivi che non sono stati analizzati.  <br/> |
|Profondità massima dell'allegato  <br/> |30  <br/> |Numero massimo di allegati annidati analizzati. Ad esempio, se a un messaggio di posta elettronica è allegato un altro messaggio e il messaggio allegato contiene un documento di Word allegato, il documento di Word e il messaggio allegato verranno indicizzati. Questo comportamento continuerà per un massimo di 30 allegati annidati.  <br/> |
|Numero massimo di immagini allegate  <br/> |0  <br/> |Un'immagine allegata a un messaggio di posta elettronica viene ignorata dal parser e non viene indicizzata.  <br/> |
|Tempo massimo dedicato all'analisi di un elemento  <br/> |30 secondi  <br/> |Viene impiegato un massimo di 30 secondi per l'analisi di un elemento per l'indicizzazione. Se il tempo di analisi supera i 30 secondi, l'elemento viene contrassegnato come parzialmente indicizzato.  <br/> |
|Output massimo parser  <br/> |2 milioni di caratteri  <br/> |La quantità massima di testo generato dal parser indicizzato. Se ad esempio il parser ha estratto 8 milioni di caratteri da un documento, vengono indicizzati solo i primi 2 milioni di caratteri.  <br/> |
|Numero massimo di token di annotazione  <br/> |2 milioni  <br/> |Quando un messaggio di posta elettronica viene indicizzato, ogni parola viene annotata con istruzioni di elaborazione diverse che specificano la modalità di indicizzazione di tale parola. Ogni set di istruzioni di elaborazione è denominato token di annotazione. Per mantenere la qualità del servizio in Office 365, esiste un limite di 2 milioni di token di annotazione per un messaggio di posta elettronica.  <br/> |
|Dimensioni massime del corpo nell'indice  <br/> |67 milioni di caratteri  <br/> |Numero totale di caratteri nel corpo di un messaggio di posta elettronica e di tutti i relativi allegati. Quando un messaggio di posta elettronica viene indicizzato, tutto il testo nel corpo del messaggio e in tutti gli allegati viene concatenato in un'unica stringa. La dimensione massima di questa stringa indicizzata è 67 milioni di caratteri.  <br/> |
|Numero massimo di token univoci nel corpo  <br/> |1 milione  <br/> |Come spiegato in precedenza, i token sono il risultato dell'estrazione di testo dal contenuto, della rimozione di punteggiatura e spazi e quindi della divisione in parole (denominate token) archiviate nell'indice. Ad esempio, la frase  `"cat, mouse, bird, dog, dog"` contiene 5 token. Ma solo 4 di questi sono token univoci. Esiste un limite di 1 milione di token univoci per ogni messaggio di posta elettronica, che consente di evitare che l'indice sia troppo grande con token casuali.  <br/> |

## <a name="more-information-about-partially-indexed-items"></a>Ulteriori informazioni sugli elementi parzialmente indicizzati

- Come indicato in precedenza, poiché le proprietà del messaggio e del documento e i relativi metadati sono indicizzati, una ricerca con parole chiave potrebbe restituire risultati se tale parola chiave viene visualizzata nei metadati indicizzati. Tuttavia, la stessa ricerca con parole chiave potrebbe non restituire lo stesso elemento se la parola chiave viene visualizzata solo nel contenuto di un elemento con un tipo di file non supportato. In questo caso, l'elemento verrà restituito come elemento parzialmente indicizzato.

- Se un elemento parzialmente indicizzato viene incluso nei risultati della ricerca perché soddisfa i criteri della query di ricerca (e non è stato escluso), non verrà incluso come elemento parzialmente indicizzato nelle statistiche di ricerca stimate. Inoltre, non verrà incluso con gli elementi parzialmente indicizzati quando si esportano i risultati della ricerca.

- Sebbene un tipo di file sia supportato per l'indicizzazione e sia indicizzato, possono verificarsi errori di indicizzazione o di ricerca che causeranno la restituire un file come elemento parzialmente indicizzato. Ad esempio, la ricerca in un file di Excel di dimensioni molto grandi potrebbe avere esito parzialmente positivo (perché i primi 4 MB sono indicizzati), ma quindi non riesce perché viene superato il limite di dimensione del file. In questo caso, è possibile che lo stesso file sia restituito con i risultati della ricerca e come elemento parzialmente indicizzato.

- I file crittografati con le tecnologie di crittografia [Microsoft](encryption.md) e allegati a un messaggio di posta elettronica che soddisfa i criteri di una ricerca possono essere visualizzati in anteprima e decrittografati quando vengono esportati. Al momento, i file crittografati con le tecnologie di crittografia Microsoft (e archiviati in SharePoint o OneDrive for Business) vengono parzialmente indicizzati.

- I messaggi di posta elettronica crittografati con S/MIME vengono parzialmente indicizzati. Sono inclusi i messaggi crittografati con o senza allegati.

- I messaggi di posta elettronica protetti con Azure Rights Management vengono indicizzati e verranno inclusi nei risultati della ricerca se corrispondono alla query di ricerca. I messaggi di posta elettronica protetti da diritti vengono decrittografati e possono essere visualizzati in anteprima ed esportati. Questa funzionalità richiede l'assegnazione del ruolo di decrittografia RMS, assegnato per impostazione predefinita al gruppo di ruoli eDiscover Manager.

## <a name="see-also"></a>Vedere anche

[Analisi degli elementi parzialmente indicizzati in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)
