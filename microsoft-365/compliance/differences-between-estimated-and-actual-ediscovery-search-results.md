---
title: Differenze tra i risultati di ricerca di eDiscovery stimati ed effettivi
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/13/2017
audience: Admin
ms.topic: overview
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
description: 'Comprendere il motivo per cui i risultati di ricerca stimati ed effettivi possono variare nelle ricerche eseguite con gli strumenti di eDiscovery in Office 365. '
ms.openlocfilehash: 3363b773e162d25a893319bcf2e38c7dd23f05cd
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943019"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>Differenze tra i risultati di ricerca di eDiscovery stimati ed effettivi

Questo argomento si applica alle ricerche che è possibile eseguire utilizzando uno dei seguenti strumenti di Microsoft eDiscovery: 

- Ricerca contenuto nel centro sicurezza & conformità  <br/>  
- EDiscovery sul posto nell'interfaccia di amministrazione di Exchange (EAC)  <br/>  
- Centro eDiscovery in SharePoint Online  <br/> 
   
Quando si esegue una ricerca eDiscovery, lo strumento che si sta utilizzando restituirà una stima del numero di elementi (e delle relative dimensioni totali) che soddisfano i criteri di ricerca. Ad esempio, quando si esegue una ricerca nel centro sicurezza & conformità, i risultati della ricerca stimati vengono visualizzati nel riquadro dei dettagli per la ricerca selezionata.
  
![Stima dei risultati visualizzati nel riquadro dei dettagli della ricerca selezionata](../media/74e4ce83-40be-41a9-b60f-5ad447e79fe4.png)
  
Si tratta della stessa stima delle dimensioni totali e del numero di elementi visualizzati nello strumento di esportazione di eDiscovery quando si esportano i risultati in un computer locale e nel rapporto di riepilogo di esportazione scaricato con i risultati della ricerca.
  
**Risultati stimati nello strumento di esportazione di eDiscovery**

![Risultati stimati nello strumento di esportazione di eDiscovery](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Risultati stimati nell'esportazione del rapporto riepilogativo**

![I risultati della ricerca stimati sono inclusi nel report Riepilogo esportazione](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Tuttavia, come si noterà nella schermata precedente del rapporto riepilogativo di esportazione, le dimensioni e il numero dei risultati di ricerca effettivamente scaricati sono diversi rispetto alla dimensione e al numero di risultati di ricerca stimati. 
  
![Differenza tra i risultati della ricerca stimati e scaricati](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Di seguito sono riportate alcune ragioni per queste differenze:
  
- **Il modo in cui vengono valutati i risultati** : una stima dei risultati della ricerca è solo quella, una stima (e non un numero effettivo) degli elementi che soddisfano i criteri di query di ricerca. Per compilare la stima degli elementi di Exchange, un elenco degli ID messaggio che soddisfano i criteri di ricerca è richiesto dal database di Exchange dallo strumento di eDiscovery che si sta utilizzando. Tuttavia, quando si esportano i risultati della ricerca, la ricerca viene rieseguita e i messaggi effettivi vengono recuperati dal database di Exchange. Pertanto, queste differenze potrebbero risultare a causa del modo in cui viene determinato il numero stimato di elementi e il numero effettivo di elementi. 
    
- **Modifiche che si verificano tra il momento in cui si valutano ed esportano i risultati** della ricerca: quando si esportano i risultati della ricerca, viene riavviata la ricerca per raccogliere gli elementi più recenti nell'indice di ricerca che soddisfano i criteri di ricerca. È possibile che siano stati creati, inviati o ricevuti elementi aggiuntivi che soddisfano i criteri di ricerca nel tempo tra la raccolta dei risultati della ricerca stimata e la data di esportazione dei risultati della ricerca. È inoltre possibile che gli elementi inclusi nell'indice di ricerca quando i risultati della ricerca sono stati stimati non siano più presenti perché sono stati eliminati dal percorso del contenuto prima dell'esportazione dei risultati della ricerca. Un modo per attenuare questo problema consiste nel specificare un intervallo di date per una ricerca eDiscovery. Un altro modo consiste nell'applicare un'esenzione ai percorsi di contenuto, in modo che gli elementi siano conservati e non possano essere eliminati. 
    
- **Elementi non indicizzati** : gli elementi non indicizzati per la ricerca possono causare differenze tra i risultati di ricerca stimati ed effettivi. Ad esempio, eDiscovery sul posto in Exchange e il centro eDiscovery in SharePoint non includono gli elementi non indicizzati (che non soddisfano i criteri di ricerca) quando si esegue una ricerca per stimare i risultati della ricerca. Tuttavia, è possibile includere gli elementi non indicizzati quando si esportano i risultati della ricerca. Se si includono gli elementi non indicizzati quando si esportano i risultati della ricerca, potrebbero essere presenti più elementi esportati. Ciò causerà una differenza tra i risultati di ricerca stimati ed esportati. 
    
    Quando si utilizza lo strumento di ricerca contenuto nel centro sicurezza & Compliance, è possibile includere gli elementi non indicizzati nella stima della ricerca. Il numero di elementi non indicizzati restituiti dalla ricerca è elencato nel riquadro dei dettagli insieme agli altri risultati della ricerca stimati. Tutti gli elementi non indicizzati verrebbero inclusi anche nella dimensione totale dei risultati della ricerca stimati. Quando si esportano i risultati della ricerca, si ha la possibilità di includere o meno gli elementi non indicizzati. Il modo in cui vengono configurate queste opzioni potrebbe causare differenze tra i risultati di ricerca stimati e quelli effettivamente scaricati. 
    
- **Esportazione dei risultati di una ricerca di contenuto che include tutti i percorsi di contenuto** : se la ricerca da cui si stanno esportando risultati è stata una ricerca di tutti i percorsi di contenuto dell'organizzazione, vengono esportati solo gli elementi non indicizzati provenienti da percorsi di contenuto che contengono elementi che corrispondono ai criteri di ricerca. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Tuttavia, gli elementi non indicizzati provenienti da tutti i percorsi di contenuto (anche quelli che non contengono elementi che corrispondono alla query di ricerca) saranno inclusi nei risultati della ricerca stimati. 
    
    In alternativa, se la ricerca che si sta esportando risulta da posizioni di contenuto specifiche incluse, gli elementi non indicizzati (che non sono esclusi dai criteri di ricerca) da tutti i percorsi di contenuto specificati nella ricerca verranno esportati. In questo caso, il numero stimato di elementi non indicizzati e il numero di elementi non indicizzati effettivamente esportati devono corrispondere.
    
    Non è possibile esportare gli elementi non indicizzati da ogni posizione dell'organizzazione perché potrebbe aumentare la probabilità di errori di esportazione e aumentare il tempo necessario per esportare e scaricare i risultati della ricerca.
    
- **Formati di file non elaborati rispetto ai formati di file esportati** -per gli elementi di Exchange, la dimensione stimata dei risultati della ricerca viene calcolata utilizzando le dimensioni dei messaggi RAW di Exchange. Tuttavia, i messaggi di posta elettronica vengono esportati in un file PST o come singoli messaggi (che sono formattati come file EML). Entrambe le opzioni di esportazione utilizzano un formato di file diverso da quello di scambio di messaggi non elaborati, che determina la dimensione complessiva dei file esportati in modo diverso rispetto alle dimensioni stimate del file. 
    
- **Versioni del documento** -per i documenti di SharePoint, più versioni di un documento non vengono incluse nei risultati della ricerca stimati. Tuttavia, è possibile includere tutte le versioni di documenti quando si esportano i risultati della ricerca, aumentando il numero effettivo (e le dimensioni totali) dei documenti esportati. 
    
- **De-duplication** -per gli elementi di Exchange, la deduplicazione riduce il numero di elementi che vengono esportati. Si ha la possibilità di deduplicare i risultati della ricerca quando vengono esportati. Per i messaggi di Exchange, ciò significa che viene esportata una sola istanza di un messaggio, anche se tale messaggio può essere trovato in più cassette postali. I risultati della ricerca stimati includono tutte le istanze di un messaggio. Pertanto, se si sceglie l'opzione di deduplicazione quando si esportano i risultati della ricerca, il numero effettivo di elementi che vengono esportati potrebbe essere notevolmente inferiore al numero stimato di elementi. 
    
    Un'altra cosa da tenere presente se si sceglie l'opzione di deduplicazione è che tutti gli elementi di Exchange vengono esportati in un singolo file PST e la struttura delle cartelle dalle cassette postali di origine non viene conservata. Il file PST esportato contiene solo gli elementi di posta elettronica. Tuttavia, un rapporto sui risultati di ricerca contiene una voce per ogni messaggio esportato che identifica la cassetta postale di origine in cui si trova il messaggio. In questo modo è possibile identificare tutte le cassette postali che contengono un messaggio duplicato. Se invece non si attiva la deduplicazione, viene esportato un file PST separato per ciascuna cassetta postale inclusa nella ricerca. 
    
## <a name="exporting-unindexed-items-from-the-ediscovery-center-in-sharepoint-online"></a>Esportazione di elementi non indicizzati dal centro eDiscovery in SharePoint Online

Nel centro eDiscovery in SharePoint Online, è possibile includere contenuto non indicizzato (da Exchange e SharePoint) quando si esportano i risultati di una ricerca di eDiscovery. A tale scopo, selezionare l'opzione **Includi elementi crittografati o che dispongono di un formato non riconosciuto** . Gli elementi non indicizzati (denominati anche non sottoposti a ricerca per indicizzazione in SharePoint) sono elementi in Exchange e SharePoint che per qualche motivo non sono stati indicizzati per la ricerca. Gli elementi di Exchange non indicizzati sono elencati nel rapporto **errori indice di Exchange** incluso quando si esportano i risultati della ricerca. Analogamente, gli elementi di SharePoint non indicizzati sono elencati nel rapporto **errori indice di SharePoint** . Quando si esportano gli elementi non indicizzati, vengono scaricati in una cartella denominata non sottoposta a **ricerca per indicizzazione**. Gli elementi di Exchange non indicizzati sono inclusi in un file PST. viene scaricato anche ogni documento non indicizzato da SharePoint. Il numero di elementi non indicizzati (se presenti) è elencato in ogni rapporto errori di indice. Il numero di elementi non indicizzati nei report deve corrispondere al numero di elementi non indicizzati scaricati. 
  
 **Quali sono i motivi per cui il numero di elementi non indicizzati esportati non corrisponde al numero di elementi nella relazione di errore di indice?** Come spiegato in precedenza, è possibile che gli elementi siano stati eliminati da Microsoft 365 tra il momento in cui è stata eseguita la stima di ricerca e l'ora in cui sono stati esportati i risultati della ricerca. Per gli elementi non indicizzati può verificarsi una discrepanza analoga. Ad esempio, l'indice di ricerca potrebbe essere obsoleto quando vengono esportati i risultati della ricerca. Ciò significa che un elemento non indicizzato esportato con i risultati della ricerca potrebbe non essere elencato nel rapporto errori di indice perché l'elemento non è stato indicizzato al momento in cui sono stati esportati i risultati della ricerca. Ciò comporterebbe l'esportazione di elementi più non indicizzati rispetto a quelli elencati nella relazione di errore di indice. Analogamente, un elemento non indicizzato elencato nel rapporto di errore dell'indice potrebbe essere stato eliminato da Microsoft 365 prima dell'aggiornamento dell'indice di ricerca. Ciò comporterebbe un minor numero di elementi non indicizzati da esportare rispetto a quelli elencati nella relazione di errore di indice. 
  
> [!NOTE]
> Se non si selezionano gli **elementi Includi crittografati o che dispongono di un formato non riconosciuto** quando si esportano i risultati della ricerca o si scaricano solo i report, vengono scaricati i report di errore di indice, ma non sono presenti voci. Questo non significa che non vi siano errori di indicizzazione. Significa solo che gli elementi non indicizzati non sono stati inclusi nell'esportazione. 
  

