---
title: Differenze tra i risultati della ricerca eDiscovery stimati ed effettivi
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 8f20ca4f-a908-46ec-99e6-9890d269ecf2
description: Comprendere perché i risultati della ricerca stimati ed effettivi possono variare nelle ricerche eseguite con gli strumenti di eDiscovery in Office 365.
ms.openlocfilehash: d530b083b2353b66ee5d4fd4bb72b175aef28be8
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532117"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>Differenze tra i risultati della ricerca eDiscovery stimati ed effettivi

Questo argomento si applica alle ricerche che è possibile eseguire utilizzando uno dei seguenti strumenti Microsoft 365 eDiscovery: 

- Ricerca contenuto
- Core eDiscovery

Quando si esegue una ricerca eDiscovery, lo strumento in uso restituirà una stima del numero di elementi (e delle relative dimensioni totali) che corrispondono ai criteri di ricerca. Ad esempio, quando si esegue una ricerca nel Centro conformità Microsoft 365, i risultati della ricerca stimati vengono visualizzati nella pagina a comparsa per la ricerca selezionata.
  
![Stima dei risultati visualizzati nella pagina del riquadro a comparsa di ricerca](../media/EstimatedSearchResults1.png)
  
Si tratta della stessa stima delle dimensioni totali e del numero di elementi visualizzati nello strumento di esportazione di eDiscovery quando si esportano i risultati in un computer locale e nel report Riepilogo esportazione scaricato con i risultati della ricerca.
  
**Risultati stimati nello strumento di esportazione di eDiscovery**

![Risultati stimati nello strumento di esportazione di eDiscovery](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Risultati stimati nel report Riepilogo esportazione**

![I risultati della ricerca stimati sono inclusi nel report Riepilogo esportazione](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Tuttavia, come si noterà nella schermata precedente del report Riepilogo esportazione, le dimensioni e il numero dei risultati di ricerca effettivi scaricati sono diversi da quelli dei risultati di ricerca stimati.
  
![Differenza tra i risultati della ricerca stimati e scaricati](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Ecco alcuni motivi per queste differenze:
  
- **Modalità di stima dei risultati**. Una stima dei risultati della ricerca è solo una stima (e non un conteggio effettivo) degli elementi che soddisfano i criteri di query di ricerca. Per compilare la stima degli elementi Exchange, un elenco degli ID messaggio che soddisfano i criteri di ricerca viene richiesto dal database di Exchange dallo strumento eDiscovery in uso. Tuttavia, quando si esportano i risultati della ricerca, la ricerca viene rieseguita e i messaggi effettivi vengono recuperati dal database Exchange ricerca. Queste differenze potrebbero pertanto derivare dal modo in cui vengono determinati il numero stimato di elementi e il numero effettivo di elementi.

- **Modifiche che si verificano tra il momento in cui si stimano ed esportano i risultati della ricerca.** Quando si esportano i risultati della ricerca, la ricerca viene riavviata per raccogliere gli elementi più recenti nell'indice di ricerca che soddisfano i criteri di ricerca. È possibile che siano stati creati, inviati o ricevuti elementi aggiuntivi che soddisfano i criteri di ricerca nel periodo tra la raccolta dei risultati della ricerca stimati e l'esportazione dei risultati della ricerca. È inoltre possibile che gli elementi che si trovavano nell'indice di ricerca al momento della stima dei risultati della ricerca non siano più presenti perché sono stati eliminati dal percorso del contenuto prima dell'esportazione dei risultati della ricerca. Un modo per ovviare a questo problema è specificare un intervallo di date per una ricerca eDiscovery. Un altro modo è quello di conservare i percorsi del contenuto in modo che gli elementi siano conservati e non possano essere eliminati. 

   Anche se rara, anche nel caso in cui viene applicata un'esenzione, la manutenzione degli elementi di calendario incorporati (che non sono modificabili dall'utente, ma sono inclusi in molti risultati di ricerca) può essere rimossa di tanto in tanto. Questa rimozione periodica degli elementi del calendario comporta un numero minore di elementi esportati.

- **Elementi non indicizzati**. Gli elementi non indicizzati per la ricerca possono causare differenze tra i risultati di ricerca stimati ed effettivi. È possibile includere elementi non indicizzati quando si esportano i risultati della ricerca. Se si includono elementi non indicizzati durante l'esportazione dei risultati della ricerca, potrebbero essere presenti più elementi esportati. Ciò causerà una differenza tra i risultati di ricerca stimati ed esportati.

    Quando si utilizza lo strumento ricerca contenuto, è possibile includere elementi non indicizzati quando si esportano i risultati della ricerca. Il numero di elementi non indicizzati restituiti dalla ricerca è elencato nella pagina a comparsa insieme agli altri risultati di ricerca stimati. Tutti gli elementi non indicizzati verranno inclusi anche nella dimensione totale dei risultati di ricerca stimati. Quando si esportano i risultati della ricerca, è possibile includere o non includere elementi non indicizzati. La configurazione di queste opzioni potrebbe comportare differenze tra i risultati di ricerca stimati e i risultati di ricerca effettivi scaricati.

- **Esportazione dei risultati di una ricerca contenuto che include tutti i percorsi di contenuto.** Se la ricerca da cui si esportano i risultati è una ricerca di tutti i percorsi di contenuto nell'organizzazione, verranno esportati solo gli elementi non indicizzati dai percorsi di contenuto che contengono elementi che soddisfano i criteri di ricerca. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Tuttavia, gli elementi non indicizzati di tutti i percorsi di contenuto (anche quelli che non contengono elementi che corrispondono alla query di ricerca) verranno inclusi nei risultati di ricerca stimati.

    In alternativa, se la ricerca che si sta esportando risultati da percorsi di contenuto specifici inclusi, gli elementi non indicizzati (che non sono esclusi dai criteri di ricerca) da tutti i percorsi di contenuto specificati nella ricerca verranno esportati. In questo caso, il numero stimato di elementi non indicizzati e il numero di elementi non indicizzati esportati devono essere uguali.

    Il motivo per cui non si esportano elementi non indicizzati da ogni posizione dell'organizzazione è perché potrebbe aumentare la probabilità di errori di esportazione e aumentare il tempo necessario per esportare e scaricare i risultati della ricerca.

- **Gli elementi non indicizzati in SharePoint e OneDrive non sono inclusi nelle stime di ricerca.** Gli elementi non indicizzati SharePoint siti e OneDrive for Business non sono inclusi nei risultati di ricerca stimati. Questo perché l'SharePoint non contiene dati per gli elementi non indicizzati. Solo gli elementi non indicizzati dalle cassette postali sono inclusi nelle stime di ricerca. Tuttavia, se si includono elementi non indicizzati durante l'esportazione dei risultati della ricerca, vengono inclusi gli elementi non indicizzati in SharePoint e OneDrive, con un aumento del numero di elementi effettivamente esportati. Ciò determina differenze tra i risultati stimati (che non includono gli elementi non indicizzati nei siti SharePoint e OneDrive) e gli elementi effettivi scaricati. La regola sull'esportazione di elementi non indicizzati solo da percorsi di contenuto che contengono elementi che soddisfano i criteri di ricerca si applica ancora in questa situazione.

- **Versioni dei documenti in SharePoint e OneDrive**. Quando si SharePoint siti e OneDrive, più versioni di un documento non vengono incluse nel conteggio dei risultati di ricerca stimati. Tuttavia, è possibile includere tutte le versioni dei documenti quando si esportano i risultati della ricerca. Se si includono versioni dei documenti durante l'esportazione dei risultati della ricerca, il numero effettivo (e le dimensioni totali) degli elementi esportati verrà aumentato.

- **SharePoint cartelle .** Se il nome delle cartelle in SharePoint corrisponde a una query di ricerca, la stima della ricerca includerà un conteggio di tali cartelle (ma non gli elementi in tali cartelle). Quando si esportano i risultati della ricerca, gli elementi nella cartella vengono esportati, ma la cartella effettiva in non viene esportata. Ne risulta che il numero di elementi esportati esportati sarà superiore al numero di risultati di ricerca stimati. Se una cartella è vuota, il numero di risultati di ricerca effettivi esportati verrà ridotto di un elemento, perché la cartella effettiva non viene esportata.

- **SharePoint elenchi .** Se il nome di un SharePoint corrisponde a una query di ricerca, la stima della ricerca includerà un conteggio di tutti gli elementi dell'elenco. Quando si esportano i risultati della ricerca, l'elenco e gli elementi dell'elenco vengono esportati come singolo file CSV. In questo modo si ridurrà il numero effettivo di elementi effettivamente esportati. Se l'elenco contiene allegati, gli allegati verranno esportati come documenti separati, con un aumento del numero di elementi esportati.

- **Formati di file non elaborati e formati di file esportati**. Per Exchange, le dimensioni stimate dei risultati della ricerca vengono calcolate utilizzando le dimensioni Exchange messaggi non elaborati. Tuttavia, i messaggi di posta elettronica vengono esportati in un file PST o come singoli messaggi (formattati come file EML). Entrambe queste opzioni di esportazione utilizzano un formato di file diverso rispetto ai messaggi Exchange non elaborati, il che comporta che le dimensioni totali dei file esportati siano diverse rispetto alle dimensioni stimate del file.

- **Deduplicazione degli elementi Exchange durante l'esportazione.** Per Exchange elementi, la deduplicazione riduce il numero di elementi esportati. È possibile de-duplicare i risultati della ricerca durante l'esportazione. Per Exchange messaggi, ciò significa che viene esportata una sola istanza di un messaggio, anche se tale messaggio potrebbe essere presente in più cassette postali. I risultati della ricerca stimati includono ogni istanza di un messaggio. Pertanto, se si sceglie l'opzione di deduplicazione durante l'esportazione dei risultati della ricerca, il numero effettivo di elementi esportati potrebbe essere notevolmente inferiore al numero stimato di elementi.

    Un altro aspetto da tenere presente se si sceglie l'opzione di deduplicazione è che tutti gli elementi Exchange vengono esportati in un singolo file PST e la struttura delle cartelle dalle cassette postali di origine non viene mantenuta. Il file PST esportato contiene solo gli elementi di posta elettronica. Tuttavia, un report dei risultati della ricerca contiene una voce per ogni messaggio esportato che identifica la cassetta postale di origine in cui si trova il messaggio. In questo modo è possibile identificare tutte le cassette postali che contengono un messaggio duplicato. Se invece non si attiva la deduplicazione, viene esportato un file PST separato per ciascuna cassetta postale inclusa nella ricerca.

> [!NOTE]
> Se non si seleziona  l'opzione Includi elementi crittografati o con un formato non riconosciuto quando si esportano i risultati della ricerca o si scaricano semplicemente i report, le segnalazioni degli errori dell'indice vengono scaricate ma non dispongono di alcuna voce. Questo non significa che non siano presenti errori di indicizzazione. Significa solo che gli elementi non indicizzati non sono stati inclusi nell'esportazione.
