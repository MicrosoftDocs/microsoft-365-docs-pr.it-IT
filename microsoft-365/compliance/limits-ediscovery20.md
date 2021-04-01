---
title: Limiti di Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni sui limiti dei casi, i limiti di indicizzazione e i limiti di ricerca in vigore per la soluzione Advanced eDiscovery in Microsoft 365.
ms.openlocfilehash: 145d5de5027a9d6171215c0602a733ced5265657
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445322"
---
# <a name="limits-in-advanced-ediscovery"></a>Limiti di Advanced eDiscovery

In questo articolo vengono descritti i limiti della soluzione Advanced eDiscovery in Microsoft 365.

## <a name="case-and-review-set-limits"></a>Limiti dei set di casi e revisioni

Nella tabella seguente sono elencati i limiti per i casi e i set di revisione in Advanced eDiscovery.

| Descrizione del limite | Limite |
|:-----|:-----|
|Numero totale di documenti che è possibile aggiungere a un caso (per tutti i set di revisioni in un caso).  <br/> |3 milioni <br/> |
|Dimensioni totali del file per set di caricamento. Ciò include il caricamento non di Office 365 in un set di revisione.  <br/> |300 GB <br/> |
|Quantità totale di dati caricati in tutti i set di revisione nell'organizzazione al giorno.<br/> |2 TB <br/> |
|Numero massimo di set di carico per caso.  <br/> |200 <br/> |
|Numero massimo di set di revisione per caso.  <br/> |20 <br/> |
|Numero massimo di gruppi di tag per caso.  <br/> |1000 <br/> |
|Numero massimo di tag per caso.  <br/> |1000 <br/> |
|Numero massimo di processi simultanei nell'organizzazione per aggiungere contenuto a un set di revisioni. Questi processi sono denominati **Aggiunta di dati a un set di** revisione e vengono visualizzati nella **scheda** Processi in un caso.| 10 <sup>4</sup> |
|Numero massimo di processi simultanei per aggiungere contenuto a un set di recensioni per utente. Questi processi sono denominati **Aggiunta di dati a un set di** revisione e vengono visualizzati nella **scheda** Processi in un caso. | 3  |
|||

## <a name="hold-limits"></a>Limiti di blocco

Nella tabella seguente sono elencati i limiti per i blocchi associati a un caso advanced eDiscovery.

| Descrizione del limite | Limite |
|:-----|:-----|
|Numero massimo di cassette postali in un singolo caso di blocco. Questo limite include il totale combinato delle cassette postali degli utenti e le cassette postali associate ai gruppi di Microsoft 365, Microsoft Teams e Gruppi di Yammer. <br/> |1,000  <br/> |
|Numero massimo di siti in un singolo caso di blocco. Questo limite include il totale combinato dei siti di OneDrive for Business, dei siti di SharePoint e dei siti associati ai gruppi di Microsoft 365, Microsoft Teams e Yammer.  <br/> |100  <br/> |

## <a name="indexing-limits"></a>Limiti di indicizzazione

Nella tabella seguente sono elencati i limiti di indicizzazione in Advanced eDiscovery.

| Descrizione del limite | Limite |
|:-----|:-----|
|Numero massimo di caratteri estratti da un singolo file.  <br/> |10 milioni<sup>1</sup> <br/> |
|Dimensione massima di un singolo file.   <br/> |100 MB<sup>1</sup> <br/> |
|Profondità massima degli elementi incorporati in un documento.  <br/> |25<sup>1</sup> <br/> |
|Dimensioni massime dei file elaborati dal riconoscimento ottico dei caratteri (OCR).  <br/> |24 MB<sup>1</sup> <br/> 
|Numero massimo di processi di indicizzazione per organizzazione al giorno. <br/> |10<sup>6</sup> <br/>|  
|||

## <a name="search-limits"></a>Limiti relativi alla ricerca

I limiti descritti in questa sezione sono correlati all'utilizzo dello strumento di ricerca **nella** scheda Ricerche per raccogliere dati per un caso. Per ulteriori informazioni, vedere [Collect data for a case in Advanced eDiscovery.](collecting-data-for-ediscovery.md)

| Descrizione del limite | Limite |
|:-----|:-----|
|Numero massimo di cassette postali o siti in cui è possibile eseguire ricerche in una singola ricerca. |Nessun limite|
|Numero massimo di ricerche che possono essere eseguite contemporaneamente. |Nessun limite |
|Numero massimo di ricerche che un singolo utente può avviare contemporaneamente. |10   | 
|Numero massimo di caratteri per una query di ricerca (inclusi gli operatori e le condizioni). |10.000 &nbsp; <sup>2</sup>|
|Numero minimo di caratteri alfa per i caratteri jolly del prefisso. ad esempio, **uno \* *_ o _* set \***.|3  |  
|Numero massimo di varianti restituite quando si utilizza il carattere jolly prefisso per cercare una frase esatta o quando si utilizza un carattere jolly prefisso e l'operatore **booleano NEAR.** |10.000 &nbsp; <sup>3</sup>|
|Numero massimo di elementi per cassetta postale utente visualizzati nella pagina di anteprima per le ricerche. Vengono visualizzati gli elementi più recenti. |100|
|Numero massimo di elementi di tutte le cassette postali visualizzate nella pagina di anteprima per le ricerche.|1,000|
|Numero massimo di cassette postali che possono essere visualizzate in anteprima per i risultati della ricerca.  Se sono presenti più di 1000 cassette postali che contengono elementi che corrispondono alla query di ricerca, solo le prime 1.000 cassette postali con il maggior numero di risultati sono disponibili per l'anteprima.|1,000|
|Numero massimo di elementi dai siti di SharePoint e OneDrive for Business visualizzati nella pagina di anteprima per le ricerche. Vengono visualizzati gli elementi più recenti. |200|
|Numero massimo di siti di SharePoint e OneDrive for Business che possono essere visualizzati in anteprima per i risultati della ricerca. Se sono presenti più di 200 siti che contengono elementi che corrispondono alla query di ricerca, solo i 200 siti principali con il maggior numero di risultati sono disponibili per l'anteprima.|200|
|Numero massimo di elementi per cassetta postale delle cartelle pubbliche visualizzato nella pagina di anteprima per le ricerche. |100|
|Numero massimo di elementi trovati in tutti gli elementi delle cassette postali delle cartelle pubbliche visualizzati nella pagina di anteprima per le ricerche. |200|
|Numero massimo di cassette postali delle cartelle pubbliche che possono essere visualizzate in anteprima per i risultati della ricerca. Se sono presenti più di 500 cassette postali di cartelle pubbliche che contengono elementi che corrispondono alla query di ricerca, solo le prime 500 cassette postali con il maggior numero di risultati sono disponibili per l'anteprima.|500|
|||

## <a name="search-times"></a>Tempi di ricerca

Microsoft raccoglie informazioni sulle prestazioni per le ricerche eseguite da tutte le organizzazioni. Sebbene la complessità della query di ricerca possa influire sui tempi di ricerca, il fattore principale che influisce sul tempo necessario per una ricerca è il numero di cassette postali in cui la ricerca viene eseguita. Anche se Microsoft non fornisce un contratto di servizio per i tempi di ricerca, nella tabella seguente sono elencati i tempi medi di ricerca per le ricerche di raccolta in base al numero di cassette postali incluse nella ricerca.
  
  |**Numero di cassette postali**|**Tempo medio di ricerca**|
  |:-----|:-----|
  |100  <br/> |30 secondi  <br/> |
  |1.000  <br/> |45 secondi  <br/> |
  |10.000  <br/> |4 minuti  <br/> |
  |25.000  <br/> |10 minuti  <br/> |
  |50.000  <br/> |20 minuti  <br/> |
  |100.000  <br/> |25 minuti  <br/> |
  |||

## <a name="viewer-limits"></a>Limiti del visualizzatore

| Descrizione del limite | Limite |
|:-----|:-----|
|Dimensione massima del file di Excel visualizzabile nel visualizzatore nativo.  <br/> |4 MB  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a>Limiti di esportazione - Esportazione finale al di fuori del set di revisione

I limiti descritti in questa sezione sono correlati all'esportazione di documenti da un set di revisioni.

| Descrizione del limite | Limite |
|:-----|:-----|
|Dimensione massima di una singola esportazione.|3 milioni di documenti o 100 GB, a seconda di quale sia più piccolo|
|Numero massimo di esportazioni simultanee per set di revisioni. | 1 |
|||

## <a name="review-set-download-limits"></a>Rivedere i limiti di download del set

| Descrizione del limite | Limite |
|:-----|:-----|
|Dimensioni totali del file o numero massimo di documenti scaricati da un set di revisioni.  <br/> |3 MB o 50 documenti <sup>5</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> Qualsiasi elemento che supera un singolo limite di file verrà visualizzato come errore di elaborazione.
>
> <sup>2</sup> Quando si esegue una ricerca in posizioni di SharePoint e OneDrive for Business, i caratteri negli URL dei siti in cui viene eseguita la ricerca vengono conteggiati rispetto a questo limite.
>
> <sup>3</sup> Per le query non di frase (un valore di parola chiave che non utilizza virgolette doppie) viene utilizzato un indice di prefisso speciale. Ciò indica che una parola si trova in un documento, ma non dove si verifica nel documento. Per eseguire una query di frase (un valore di parola chiave con virgolette doppie), è necessario confrontare la posizione all'interno del documento per le parole nella frase. Ciò significa che non è possibile utilizzare l'indice del prefisso per le query di frase. In questo caso, la query viene espansa internamente con tutte le parole possibili a cui si espande il prefisso. ad esempio, **time \* *_ può espandersi a _*"time OR timer OR times OR timex OR timex OR timeboxed OR ..."**. Il limite di 10.000 è il numero massimo di varianti che la parola può espandere, non il numero di documenti corrispondenti alla query. Non esiste un limite massimo per i termini non frasi.
>
> <sup>4</sup> Questo limite viene condiviso con l'esportazione di contenuto in altri strumenti di eDiscovery. Ciò significa che le esportazioni simultanee in Ricerca contenuto e Core eDiscovery (e l'aggiunta di contenuto ai set di revisione in Advanced eDiscovery) vengono applicate a questo limite.
>
> <sup>5</sup> Questo limite si applica al download di documenti selezionati da un set di revisioni. Non si applica all'esportazione di documenti da un set di revisioni. Per ulteriori informazioni sul download e l'esportazione di documenti, vedere [Export case data in Advanced eDiscovery.](exporting-data-ediscover20.md)
>
> <sup>6</sup> Limiti di indicizzazione per organizzazione al giorno. Per ovviare al problema, è  possibile selezionare più custodi  nella scheda Origini dati in un caso e quindi fare clic su Aggiorna indice per evitare di creare un processo di indicizzazione separato per ogni responsabile. 
