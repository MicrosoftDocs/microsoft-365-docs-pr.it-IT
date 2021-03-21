---
title: De-duplicazione nei risultati della ricerca di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
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
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come eliminare i risultati della ricerca eDiscovery duplicati in modo da esportare solo una copia di un messaggio di posta elettronica.
ms.openlocfilehash: 859c1c41a9f6a530cdefce5220039fbc6ba1a14e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925672"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>De-duplicazione nei risultati della ricerca di eDiscovery

In questo articolo viene descritto il funzionamento della deduplicazione dei risultati della ricerca eDiscovery e vengono illustrate le limitazioni dell'algoritmo di deduplicazione.
  
Quando si utilizzano gli strumenti di eDiscovery per esportare i risultati di una ricerca eDiscovery, è possibile de-duplicare i risultati esportati. Cosa significa questo messaggio? Quando si abilita la deduplicazione (per impostazione predefinita, la deduplicazione non è abilitata), viene esportata solo una copia di un messaggio di posta elettronica anche se nelle cassette postali in cui è stata ricercata potrebbero essere state trovate più istanze dello stesso messaggio. La deduplicazione consente di risparmiare tempo riducendo il numero di elementi da esaminare e analizzare dopo l'esportazione dei risultati della ricerca. Tuttavia, è importante comprendere il funzionamento della deduplicazione e tenere presente che esistono limitazioni all'algoritmo che potrebbero causare il contrassegnato come duplicato di un elemento univoco durante il processo di esportazione.
  
## <a name="how-duplicate-messages-are-identified"></a>Come vengono identificati i messaggi duplicati

Gli strumenti di eDiscovery utilizzano una combinazione delle seguenti proprietà di posta elettronica per determinare se un messaggio è duplicato:
  
- **InternetMessageId-** Questa proprietà specifica l'identificatore del messaggio Internet di un messaggio di posta elettronica, ovvero un identificatore univoco globale che fa riferimento a una versione specifica di un messaggio specifico. Questo ID viene generato dal programma client di posta elettronica del mittente o dal sistema di posta elettronica host che invia il messaggio. Se una persona invia un messaggio a più destinatari, l'ID messaggio Internet sarà lo stesso per ogni istanza del messaggio. Le revisioni successive al messaggio originale riceveranno un identificatore di messaggio diverso. 

- **ConversationTopic:** questa proprietà specifica l'oggetto del thread di conversazione di un messaggio. Il valore della **proprietà ConversationTopic** è la stringa che descrive l'argomento generale della conversazione. Una conservazione è costituita da un messaggio iniziale e da tutti i messaggi inviati in risposta al messaggio iniziale. I messaggi all'interno della stessa conversazione hanno lo stesso valore per la **proprietà ConversationTopic.** Il valore di questa proprietà è in genere la riga Subject del messaggio iniziale che ha generato la conversazione. 

- **BodyTagInfo** - Proprietà dell'archivio di Exchange interna. Il valore di questa proprietà viene calcolato controllando vari attributi nel corpo del messaggio. Questa proprietà viene utilizzata per identificare le differenze nel corpo dei messaggi. 

Durante il processo di esportazione di eDiscovery, queste tre proprietà vengono confrontate per ogni messaggio che corrisponde ai criteri di ricerca. Se queste proprietà sono identiche per due o più messaggi, tali messaggi vengono determinati come duplicati e il risultato è che verrà esportata solo una copia del messaggio se è abilitata la deduplicazione. Il messaggio esportato è noto come "elemento di origine". Le informazioni sui messaggi  duplicati sono incluse nei reportResults.csve **Manifest.xml** inclusi nei risultati della ricerca esportati. Nel file **Results.csv,** un messaggio duplicato viene identificato con un valore nella **colonna Duplica in** elemento. Il valore in questa colonna corrisponde al valore nella colonna **Identità** elemento per il messaggio esportato. 
  
Nella grafica seguente viene illustrato il  modo in cui i messaggi duplicati vengono visualizzati neiResults.csve **Manifest.xml** che vengono esportati con i risultati della ricerca. Questi report non includono le proprietà di posta elettronica descritte in precedenza, che vengono utilizzate nell'algoritmo di deduplicazione. I report includono invece la **proprietà Item Identity** assegnata agli elementi dall'archivio di Exchange. 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Results.csv report (visualizzato in Excel)
  
![Visualizzazione di informazioni sugli elementi duplicati nel report Results.csv dati](../media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest.xml report (visualizzato in Excel)
  
![Visualizzazione di informazioni sugli elementi duplicati nel report Manifest.xml dati](../media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
Inoltre, altre proprietà dei messaggi duplicati sono incluse nei rapporti di esportazione. Ciò include la cassetta postale in cui si trova il messaggio duplicato, se il messaggio è stato inviato a un gruppo di distribuzione e se il messaggio era Cc o Ccn a un altro utente.
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>Limitazioni dell'algoritmo di deduplicazione

Esistono alcune limitazioni note dell'algoritmo di deduplicazione che potrebbero causare la presenza di elementi univoci contrassegnati come duplicati. È importante comprendere queste limitazioni in modo da poter decidere se utilizzare o meno la funzionalità di deduplicazione facoltativa.
  
Esiste una situazione in cui la funzionalità di deduplicazione potrebbe erroneamente identificare un messaggio come duplicato e non esportarlo (ma comunque citarlo come duplicato nei rapporti di esportazione). Si tratta di messaggi che un utente modifica ma non invia. Ad esempio, si supponga che un utente seleziona un messaggio in Outlook, copia il contenuto del messaggio e quindi lo incolla in un nuovo messaggio. L'utente modifica quindi una delle copie rimuovendo o aggiungendo un allegato o modificando la riga dell'oggetto o il corpo stesso. Se questi due messaggi corrispondono alla query di una ricerca eDiscovery, solo uno dei messaggi verrà esportato se la deduplicazione è abilitata quando i risultati della ricerca vengono esportati. Pertanto, anche se il messaggio originale o il messaggio copiato è stato modificato, nessuno dei messaggi modificati è stato inviato e pertanto i valori delle proprietà **InternetMessageId,** **ConversationTopic** e **BodyTagInfo** non sono stati aggiornati. Come spiegato in precedenza, tuttavia, entrambi i messaggi verranno elencati nei report di esportazione 
  
I messaggi univoci possono anche essere contrassegnati come duplicati quando è abilitata la funzionalità di protezione delle pagine copy-on-write, come nel caso di una cassetta postale in attesa per controversia legale o In-Place conservazione. La funzionalità Copia in scrittura copia il messaggio originale (e lo salva nella cartella Versioni della cartella Elementi ripristinabili dell'utente) prima che la revisione venga salvata nell'elemento originale. In questo caso, la copia rivista e il messaggio originale (nella cartella Elementi ripristinabili) potrebbero essere considerati come messaggi duplicati e pertanto solo uno di essi verrebbe esportato.
  
> [!IMPORTANT]
> Se le limitazioni dell'algoritmo di deduplicazione potrebbero influire sulla qualità dei risultati della ricerca, non è consigliabile abilitare la deduplicazione quando si esportano elementi. Se è improbabile che le situazioni descritte in questa sezione siano un fattore nei risultati della ricerca e si desidera ridurre il numero di elementi più probabili come duplicati, è consigliabile abilitare la deduplicazione. 
  
## <a name="more-information"></a>Ulteriori informazioni

- Le informazioni contenute in questo articolo sono applicabili quando si esportano i risultati della ricerca utilizzando uno dei seguenti strumenti di eDiscovery:

  - Ricerca contenuto nel Centro conformità in Office 365

  - eDiscovery sul posto in Exchange Online

  - Centro eDiscovery in SharePoint Online

- Per ulteriori informazioni sull'esportazione dei risultati della ricerca, vedere:

  - [Esportare ricerca contenuto](export-search-results.md)

  - [Esportare il rapporto della Ricerca contenuto](export-a-content-search-report.md)

  - [Esportare In-Place risultati della ricerca eDiscovery in un file PST](/exchange/security-and-compliance/in-place-ediscovery/export-search-results)

  - [Esportare il contenuto e creare report nel centro eDiscovery](/SharePoint/governance/export-content-and-create-reports-in-the-ediscovery-center)