---
title: Elementi parzialmente indicizzati in ricerca contenuto e altri strumenti di eDiscovery
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
description: Informazioni sugli elementi non indicizzati in Exchange e SharePoint che è possibile includere in una ricerca di eDiscovery eseguita nel centro conformità di Microsoft 365.
ms.openlocfilehash: 34758ae904678d194e889a4f1b65606d2420a3c7
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920300"
---
# <a name="partially-indexed-items-in-ediscovery"></a>Elementi parzialmente indicizzati in eDiscovery

Una ricerca di eDiscovery eseguita dal centro conformità di Microsoft 365 include automaticamente gli elementi parzialmente indicizzati nei risultati della ricerca stimati durante l'esecuzione di una ricerca. Gli elementi parzialmente indicizzati sono gli elementi della cassetta postale di Exchange e i documenti sui siti di SharePoint e OneDrive for business che per qualche motivo non sono stati completamente indicizzati per la ricerca. In Exchange, un elemento parzialmente indicizzato in genere contiene un file (di tipo file che non può essere indicizzato) associato a un messaggio di posta elettronica. Di seguito sono riportati alcuni motivi per i quali gli elementi non possono essere indicizzati per la ricerca e vengono restituiti come elementi parzialmente indicizzati quando si esegue una ricerca eDiscovery:
  
- Il tipo di file non è riconosciuto o supportato per l'indicizzazione.

- I messaggi dispongono di un file allegato privo di un gestore valido, ad esempio file di immagine. Questa è la causa più comune degli elementi di posta elettronica parzialmente indicizzati.

- Il tipo di file è supportato per l'indicizzazione ma si è verificato un errore di indicizzazione per un file specifico.

- Troppi file allegati a un messaggio di posta elettronica.

- Un file allegato a un messaggio di posta elettronica è troppo grande.

- Un file è crittografato con tecnologie non Microsoft.

- Un file è protetto da password.

> [!NOTE]
> La maggior parte delle organizzazioni ha meno dell'1% del contenuto in base al volume e meno del 12% in base alle dimensioni parzialmente indicizzate. Il motivo della differenza tra volume e dimensioni consiste nel fatto che i file più grandi hanno una probabilità maggiore di contenere contenuto che non può essere completamente indicizzato.
  
Per le indagini legali, è possibile che l'organizzazione debba esaminare gli elementi parzialmente indicizzati. È inoltre possibile specificare se includere gli elementi parzialmente indicizzati quando si esportano i risultati della ricerca in un computer locale o quando si preparano i risultati per l'analisi con Advanced eDiscovery. Per ulteriori informazioni, vedere [analisi degli elementi parzialmente indicizzati in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md).
  
## <a name="file-types-not-indexed-for-search"></a>Tipi di file non indicizzati per la ricerca

Alcuni tipi di file, ad esempio i file Bitmap o MP3, non presentano contenuti che possono essere indicizzati. Di conseguenza, i server di indicizzazione della ricerca in Exchange e SharePoint non eseguono indicizzazione full-text su questi tipi di file. Questi tipi di file sono considerati tipi di file non supportati. Esistono anche tipi di file pe i quali l'indicizzazione di testo completo è stata disattivata, o per impostazione predefinita o da un amministratore. I tipi di file non supportati e disabilitati sono etichettati come elementi non indicizzati nelle ricerche di contenuto. Come indicato in precedenza, gli elementi parzialmente indicizzati possono essere inclusi nel set di risultati della ricerca durante l'esecuzione di una ricerca, esportare i risultati della ricerca in un computer locale oppure preparare i risultati della ricerca per Advanced eDiscovery.
  
Per un elenco dei formati di file supportati e disattivati, vedere i seguenti argomenti:
  
- **Exchange**  -  [Formati di file indicizzati da ricerca di Exchange](https://go.microsoft.com/fwlink/p/?LinkID=386618)

- **Exchange**  -  [Get-SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)

- **SharePoint**  -  [Estensioni di file sottoposte a ricerca per indicizzazione predefinite e tipi di file analizzati in SharePoint](https://go.microsoft.com/fwlink/p/?LinkID=404033)
  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>I messaggi e i documenti con tipi di file parzialmente indicizzati possono essere restituiti nei risultati della ricerca

Non tutti i messaggi di posta elettronica con un allegato di file parzialmente indicizzato o tutti i documenti di SharePoint parzialmente indicizzati vengono automaticamente restituiti come elementi parzialmente indicizzati. Ciò è dovuto al fatto che altre proprietà del messaggio o del documento, ad esempio la proprietà **Subject** nei messaggi di posta elettronica e le proprietà **title** o **Author** per i documenti, sono indicizzate e sono disponibili per la ricerca. Ad esempio, una parola chiave Search for "Financial" restituirà gli elementi con un allegato di file parzialmente indicizzato se la parola chiave viene visualizzata nell'oggetto di un messaggio di posta elettronica o nel nome o nel titolo di un documento. Tuttavia, se la parola chiave è presente solo nel corpo del file, il messaggio o il documento verrebbe restituito come elemento parzialmente indicizzato.
  
Analogamente, i messaggi con allegati di file parzialmente indicizzati e i documenti di un tipo di file parzialmente indicizzato vengono inclusi nei risultati della ricerca quando altre proprietà del messaggio o del documento, indicizzate e ricercabili, soddisfano i criteri di ricerca. Le proprietà del messaggio che vengono indicizzate per la ricerca includono le date di invio e ricezione, il mittente e il destinatario, il nome del file di un allegato e il testo nel corpo del messaggio. Le proprietà del documento indicizzate per la ricerca includono date create e modificate. Pertanto, anche se un allegato del messaggio può essere un elemento parzialmente indicizzato, il messaggio verrà incluso nei risultati della ricerca normali se il valore di altre proprietà del messaggio o del documento corrisponde ai criteri di ricerca.
  
Per un elenco delle proprietà di posta elettronica e di documento che è possibile cercare utilizzando la funzionalità di ricerca nel centro sicurezza & conformità, vedere [keyword queries and Search Conditions for eDiscovery](keyword-queries-and-search-conditions.md).
  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Elementi parzialmente indicizzati inclusi nei risultati della ricerca

L'organizzazione potrebbe essere necessaria per identificare ed eseguire un'analisi aggiuntiva sugli elementi parzialmente indicizzati per determinare quali sono, cosa contengono e se sono rilevanti per un'indagine specifica. Come spiegato in precedenza, gli elementi parzialmente indicizzati nei percorsi di contenuto in cui viene eseguita la ricerca vengono inclusi automaticamente nei risultati della ricerca stimati. È possibile includere questi elementi parzialmente indicizzati quando si esportano i risultati della ricerca o si preparano i risultati della ricerca per Advanced eDiscovery.
  
Tenere presente quanto segue sugli elementi parzialmente indicizzati:
  
- Quando si esegue una ricerca eDiscovery, il numero totale e la dimensione degli elementi di Exchange parzialmente indicizzati (restituiti dalla query di ricerca) vengono visualizzati nelle statistiche di ricerca nel riquadro dei dettagli ed etichettati come **elementi indicizzati**. Le statistiche sugli elementi parzialmente indicizzati visualizzati nel riquadro dei dettagli non includono elementi parzialmente indicizzati in SharePoint o OneDrive.

- Se la ricerca da cui si stanno esportando i risultati è stata una ricerca di percorsi di contenuto specifici o di tutti i percorsi di contenuto dell'organizzazione, verranno esportati solo gli elementi non indicizzati provenienti da percorsi di contenuto che contengono elementi che corrispondono ai criteri di ricerca. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Il motivo è che l'esportazione di elementi parzialmente indicizzati da un numero elevato di posizioni nell'organizzazione potrebbe aumentare la probabilità di errori di esportazione e aumentare il tempo necessario per esportare e scaricare i risultati della ricerca.

    Per esportare gli elementi parzialmente indicizzati da tutti i percorsi di contenuto per una ricerca, configurare la ricerca in modo che restituisca tutti gli elementi (rimuovendo le parole chiave dalla query di ricerca) e quindi esportare solo gli elementi parzialmente indicizzati quando si esportano i risultati della ricerca (facendo clic su **solo gli elementi con un formato non riconosciuto, sono crittografati o non sono stati indicizzati per** **Output options**

- Se si sceglie di includere tutti gli elementi delle cassette postali nei risultati della ricerca o se una query di ricerca non specifica parole chiave o specifica un intervallo di date, è possibile che gli elementi parzialmente indicizzati non vengano copiati nel file PST che contiene gli elementi parzialmente indicizzati. Ciò è dovuto al fatto che tutti gli elementi, compresi gli elementi parzialmente indicizzati, verranno inclusi automaticamente nei risultati di ricerca normali.

- Gli elementi parzialmente indicizzati non sono disponibili per la visualizzazione in anteprima. È necessario esportare i risultati della ricerca per visualizzare gli elementi parzialmente indicizzati restituiti dalla ricerca.

Inoltre, quando si esportano i risultati della ricerca e si includono gli elementi parzialmente indicizzati nell'esportazione, gli elementi parzialmente indicizzati provenienti da elementi di SharePoint vengono esportati in una cartella denominata non **indicizzabile**. Quando si esportano parzialmente gli elementi di Exchange indicizzati, vengono esportati in modo diverso a seconda che gli elementi parzialmente indicizzati corrispondano alla query di ricerca e alla configurazione delle impostazioni di esportazione. 

Nella tabella seguente viene illustrato il comportamento di esportazione degli elementi indicizzati e parzialmente indicizzati e se sono inclusi o meno per le diverse impostazioni di configurazione di esportazione.

|**Configurazione di esportazione**|**Elementi indicizzati che corrispondono alla query di ricerca**|**Elementi parzialmente indicizzati che corrispondono alla query di ricerca**|**Elementi parzialmente indicizzati che non corrispondono alla query di ricerca**|
|:-----|:-----|:-----|:-----|
|Esportare solo gli elementi indicizzati  <br/> |Esportato<br/> |Esportati (inclusi negli elementi indicizzati che vengono esportati)<br/>  |Non esportato <br/>|
|Esporta solo gli elementi parzialmente indicizzati  <br/> |Non esportato  <br/> |Esportati (come elementi parzialmente indicizzati)<br/> |Esportati (come elementi parzialmente indicizzati)|
|Esportare elementi indicizzati e parzialmente indicizzati  <br/> |Esportato<br/> |Esportati (inclusi negli elementi indicizzati che vengono esportati)<br/>  |Esportati (come elementi parzialmente indicizzati)<br/>|
||||

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Elementi parzialmente indicizzati esclusi dai risultati della ricerca

Se un elemento è parzialmente indicizzato ma non soddisfa i criteri di query di ricerca, non verrà incluso come elemento parzialmente indicizzato nei risultati della ricerca. In altre parole, l'elemento è escluso dai risultati della ricerca. Ad esempio, si supponga di eseguire una ricerca e non includere parole chiave o proprietà perché si desidera includere tutto il contenuto. Tuttavia, è inclusa una condizione dell'intervallo di date per la query. Se un elemento parzialmente indicizzato rientra all'esterno dell'intervallo di date, non verrà incluso come elemento parzialmente indicizzato. Gli intervalli di date rappresentano un modo efficace per escludere gli elementi parzialmente indicizzati dai risultati della ricerca.
  
Analogamente, se si sceglie di includere gli elementi parzialmente indicizzati quando si esportano i risultati di una ricerca, gli elementi parzialmente indicizzati esclusi dai risultati della ricerca non verranno esportati.
  
Una delle eccezioni a questa regola è quando si crea un blocco basato su query associato a un caso di eDiscovery. Se si crea un blocco di eDiscovery basato su query, tutti gli elementi parzialmente indicizzati vengono inseriti in attesa. Sono inclusi gli elementi parzialmente indicizzati che non corrispondono ai criteri di query di ricerca e gli elementi parzialmente indicizzati che potrebbero non essere compresi in una condizione dell'intervallo di date. Per ulteriori informazioni sulla creazione di esenzioni di eDiscovery basate su query, vedere [Create an eDiscovery Hold](create-ediscovery-holds.md).
  
## <a name="indexing-limits-for-messages"></a>Limiti di indicizzazione per i messaggi

Nella tabella seguente vengono descritti i limiti di indicizzazione che possono comportare la restituzione di un messaggio di posta elettronica come elemento parzialmente indicizzato in una ricerca di eDiscovery in Microsoft 365.
  
Per un elenco dei limiti di indicizzazione per i documenti di SharePoint, vedere [limiti della ricerca per SharePoint Online](https://docs.microsoft.com/sharepoint/search-limits).
  
|**Limite di indicizzazione**|**Note**|**Descrizione**|
|:-----|:-----|:-----|
|Dimensione massima degli allegati (esclusi i file di Excel)  <br/> |150 MB  <br/> |Le dimensioni massime di un allegato di posta elettronica che analizzerà l'indicizzazione. Qualsiasi allegato che è più grande di questo limite non verrà analizzato per l'indicizzazione e il messaggio con l'allegato verrà contrassegnato come parzialmente indicizzato.  <br/><br/> **Nota:** L'analisi è il processo in cui il servizio di indicizzazione estrae il testo dall'allegato, rimuove i caratteri non necessari come la punteggiatura e gli spazi e quindi divide il testo in parole (in un processo denominato tokenation), che vengono quindi memorizzate nell'indice.           |
|Dimensioni massime dei file di Excel  <br/> |4 MB  <br/> |La dimensione massima di un file di Excel che si trova in un sito o collegato a un messaggio di posta elettronica che verrà analizzato per l'indicizzazione. Qualsiasi file di Excel di dimensioni superiori a questo limite non verrà analizzato e il file o l'indirizzo di posta elettronica il messaggio con l'allegato file verrà contrassegnato come non indicizzato.  <br/> |
|Numero massimo di allegati  <br/> |250  <br/> |Numero massimo di file allegati a un messaggio di posta elettronica che verranno analizzati per l'indicizzazione. Se un messaggio contiene più di 250 allegati, i primi 250 allegati vengono analizzati e indicizzati e il messaggio viene contrassegnato come indicizzato parzialmente perché aveva allegati aggiuntivi che non sono stati analizzati.  <br/> |
|Profondità massima degli allegati  <br/> |30  <br/> |Numero massimo di allegati nidificati analizzati. Ad esempio, se a un messaggio di posta elettronica è associato un altro messaggio e al messaggio allegato è associato un documento di Word, il documento di Word e il messaggio allegato verranno indicizzati. Questo comportamento continuerà fino a 30 allegati nidificati.  <br/> |
|Numero massimo di immagini collegate  <br/> |0  <br/> |Un'immagine associata a un messaggio di posta elettronica viene ignorata dal parser e non è indicizzata.  <br/> |
|Tempo massimo per l'analisi di un elemento  <br/> |30 secondi  <br/> |Viene speso un massimo di 30 secondi per l'analisi di un elemento per l'indicizzazione. Se il tempo di analisi supera 30 secondi, l'elemento viene contrassegnato come parzialmente indicizzato.  <br/> |
|Output del parser massimo  <br/> |2 milioni di caratteri  <br/> |La quantità massima di output di testo del parser indicizzato. Ad esempio, se il parser ha Estratto 8 milioni caratteri da un documento, solo i primi 2 milioni caratteri vengono indicizzati.  <br/> |
|Token di annotazione massimi  <br/> |2 milioni  <br/> |Quando un messaggio di posta elettronica viene indicizzato, ogni parola viene annotata con istruzioni di elaborazione diverse che specificano la modalità di indicizzazione di tale parola. Ogni set di istruzioni di elaborazione è denominato token di annotazione. Per mantenere la qualità del servizio in Office 365, è presente un limite di 2 milioni token di annotazione per un messaggio di posta elettronica.  <br/> |
|Dimensione massima del corpo nell'indice  <br/> |67 milioni caratteri  <br/> |Il numero totale di caratteri presenti nel corpo di un messaggio di posta elettronica e di tutti gli allegati. Quando un messaggio di posta elettronica viene indicizzato, tutto il testo nel corpo del messaggio e in tutti gli allegati viene concatenato in una singola stringa. Le dimensioni massime della stringa indicizzata sono 67 milioni caratteri.  <br/> |
|Numero massimo di token univoci nel corpo  <br/> |1 milione  <br/> |Come spiegato in precedenza, i token sono il risultato dell'estrazione del testo dal contenuto, la rimozione della punteggiatura e degli spazi e quindi la suddivisione in parole (denominate token) memorizzate nell'indice. Ad esempio, la frase  `"cat, mouse, bird, dog, dog"` contiene 5 token. Ma solo 4 di questi sono token univoci. Vi è un limite di 1 milione token univoci per ogni messaggio di posta elettronica, che consente di evitare che l'indice venga troppo esteso con token casuali.  <br/> |

## <a name="more-information-about-partially-indexed-items"></a>Ulteriori informazioni sugli elementi parzialmente indicizzati

- Come indicato in precedenza, poiché le proprietà del messaggio e del documento e i relativi metadati sono indicizzate, una ricerca per parola chiave potrebbe restituire risultati se la parola chiave viene visualizzata nei metadati indicizzati. Tuttavia, la stessa ricerca con parole chiave potrebbe non restituire lo stesso elemento se la parola chiave viene visualizzata solo nel contenuto di un elemento con un tipo di file non supportato. In questo caso, l'elemento verrebbe restituito come elemento parzialmente indicizzato.

- Se un elemento parzialmente indicizzato è incluso nei risultati della ricerca, poiché ha soddisfatto i criteri di query di ricerca e non è stato escluso, non verrà incluso come elemento parzialmente indicizzato nelle statistiche di ricerca stimate. Inoltre, non verrà incluso con gli elementi parzialmente indicizzati quando si esportano i risultati della ricerca.

- Anche se un tipo di file è supportato per l'indicizzazione ed è indicizzato, è possibile che si verifichino errori di indicizzazione o di ricerca che provochino la restituzione di un file come elemento parzialmente indicizzato. Ad esempio, la ricerca di un file di Excel di dimensioni molto grandi potrebbe avere esito positivo, in quanto i primi 4 MB sono indicizzati, ma quindi ha esito negativo a causa del superamento del limite di dimensione del file. In questo caso, è possibile che lo stesso file venga restituito con i risultati della ricerca e come elemento parzialmente indicizzato.

- I file crittografati con le [tecnologie di crittografia Microsoft](encryption.md) e sono allegati a un messaggio di posta elettronica che corrisponde ai criteri di una ricerca possono essere visualizzati in anteprima e verranno decrittografati quando vengono esportati. In questo momento, i file crittografati con le tecnologie di crittografia Microsoft (e archiviati in SharePoint o OneDrive for business) sono parzialmente indicizzati.

- I messaggi di posta elettronica crittografati con S/MIME sono parzialmente indicizzati. Sono inclusi i messaggi crittografati con o senza allegati.

- I messaggi di posta elettronica protetti tramite Azure Rights Management vengono indicizzati e verranno inclusi nei risultati della ricerca se corrispondono alla query di ricerca. I messaggi di posta elettronica protetti da diritti vengono decrittografati e possono essere visualizzati in anteprima ed esportati. Per questa funzionalità è necessario che venga assegnato il ruolo di decrittografia RMS, assegnato per impostazione predefinita al gruppo di ruoli eDiscover Manager.

## <a name="see-also"></a>Vedere anche

[Analisi degli elementi parzialmente indicizzati in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)
