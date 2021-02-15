---
title: Limiti di Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni sui limiti dei casi, i limiti di indicizzazione e i limiti di ricerca in vigore per la soluzione Advanced eDiscovery in Microsoft 365.
ms.openlocfilehash: 6994a3511b97e9209491fa61a8c6f9bc147b6b87
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044631"
---
# <a name="limits-in-advanced-ediscovery"></a>Limiti di Advanced eDiscovery

In questo articolo vengono descritti i limiti della soluzione Advanced eDiscovery in Microsoft 365.

## <a name="case-and-review-set-limits"></a>Limiti impostati per caso e revisione

Nella tabella seguente sono elencati i limiti per i casi e i set di revisioni in Advanced eDiscovery.

| Descrizione del limite | Limite |
|:-----|:-----|
|Numero totale di documenti che è possibile aggiungere a un caso (per tutti i set di revisioni in un caso).  <br/> |3 milioni <br/> |
|Dimensioni totali dei file per set di caricamento. Ciò include il caricamento di non Office 365 in un insieme da rivedere.  <br/> |300 GB <br/> |
|Quantità totale di dati caricati in tutti i set di recensioni nell'organizzazione al giorno.<br/> |2 TB <br/> |
|Numero massimo di set di carichi per caso.  <br/> |200 <br/> |
|Numero massimo di insiemi di recensioni per caso.  <br/> |20 <br/> |
|Numero massimo di gruppi di tag per caso.  <br/> |1000 <br/> |
|Numero massimo di tag per caso.  <br/> |1000 <br/> |
|||

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

I limiti descritti in questa sezione sono correlati all'utilizzo dello strumento di ricerca nella scheda **Ricerche** per raccogliere dati per un caso. Per ulteriori informazioni, vedere [Raccogliere dati per un caso in Advanced eDiscovery.](collecting-data-for-ediscovery.md)

| Descrizione del limite | Limite |
|:-----|:-----|
|Numero massimo di cassette postali o siti in cui è possibile eseguire ricerche in una singola ricerca. |Nessun limite|
|Numero massimo di ricerche che è possibile eseguire contemporaneamente. |Nessun limite |
|Numero massimo di ricerche che un singolo utente può avviare contemporaneamente. |10   | 
|Numero massimo di caratteri per una query di ricerca (inclusi operatori e condizioni). |10.000 &nbsp; <sup>2</sup>|
|Numero minimo di caratteri alfa per i caratteri jolly del prefisso; ad esempio **one \** _ o _*set \**_.|3  |  
|Numero massimo di varianti restituite quando si utilizza il carattere jolly del prefisso per cercare una frase esatta o quando si utilizza un carattere jolly del prefisso e l'operatore booleano _ *NEAR**. |10.000 &nbsp; <sup>3</sup>|
|Numero massimo di elementi per cassetta postale utente visualizzati nella pagina di anteprima per le ricerche. Vengono visualizzati gli elementi più recenti. |100|
|Numero massimo di elementi da tutte le cassette postali visualizzate nella pagina di anteprima per le ricerche.|1.000|
|Numero massimo di cassette postali che è possibile visualizzare in anteprima per i risultati della ricerca.  Se sono presenti più di 1000 cassette postali che contengono elementi che corrispondono alla query di ricerca, solo le prime 1.000 cassette postali con il maggior numero di risultati sono disponibili per l'anteprima.|1.000|
|Numero massimo di elementi dai siti di SharePoint e OneDrive for Business visualizzati nella pagina di anteprima per le ricerche. Vengono visualizzati gli elementi più recenti. |200|
|Numero massimo di siti di SharePoint e OneDrive for Business visualizzabili in anteprima per i risultati della ricerca. Se sono presenti più di 200 siti che contengono elementi che corrispondono alla query di ricerca, solo i 200 siti principali con il maggior numero di risultati sono disponibili per l'anteprima.|200|
|Numero massimo di elementi per cassetta postale di cartelle pubbliche visualizzato nella pagina di anteprima per le ricerche. |100|
|Numero massimo di elementi trovati in tutti gli elementi della cassetta postale delle cartelle pubbliche visualizzati nella pagina di anteprima per le ricerche. |200|
|Numero massimo di cassette postali di cartelle pubbliche che possono essere visualizzate in anteprima per i risultati della ricerca. Se sono presenti più di 500 cassette postali di cartelle pubbliche che contengono elementi che corrispondono alla query di ricerca, solo le prime 500 cassette postali con il maggior numero di risultati sono disponibili per l'anteprima.|500|
|||

## <a name="viewer-limits"></a>Limiti relativi ai visualizzatore

| Descrizione del limite | Limite |
|:-----|:-----|
|Dimensione massima del file di Excel visualizzabile nel visualizzatore nativo.  <br/> |4 MB  <br/> |
|||

## <a name="export-limits"></a>Limiti di esportazione

| Descrizione del limite | Limite |
|:-----|:-----|
|Dimensione massima di una singola esportazione.|3 milioni di documenti o 100 GB, a seconda di quale sia più piccolo|
|Quantità massima di dati in un singolo giorno. | 2 TB |
|Numero massimo di esportazioni simultanee nell'organizzazione. | 10 <sup>4</sup> |
|Numero massimo di esportazioni simultanee per utente. | 3  |
|Dimensione massima di un singolo file PST. | 10 GB |
|Numero massimo di esportazioni simultanee per revisione impostata. | 1  |
|||

## <a name="review-set-download-limits"></a>Esaminare i limiti di download impostati

| Descrizione del limite | Limite |
|:-----|:-----|
|Dimensioni totali dei file o numero massimo di documenti scaricati da un insieme da rivedere.  <br/> |3 MB o 50 documenti <sup>5</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> Qualsiasi elemento che supera un singolo limite di file verrà visualizzato come errore di elaborazione.
>
> <sup>2</sup> Quando si esegue una ricerca nelle posizioni di SharePoint e OneDrive for Business, i caratteri negli URL dei siti in cui viene eseguita la ricerca vengono conteggiati rispetto a questo limite.
>
> <sup>3</sup> Per le query non di frase (un valore di parola chiave che non utilizza virgolette doppie) viene utilizzato un indice di prefisso speciale. Ciò indica che una parola si trova in un documento, ma non nella posizione in cui si trova nel documento. Per eseguire una query di frase (un valore di parola chiave con virgolette doppie), è necessario confrontare la posizione all'interno del documento per le parole nella frase. Ciò significa che non è possibile utilizzare l'indice del prefisso per le query di frasi. In questo caso, la query viene espansa internamente con tutte le parole possibili a cui il prefisso si espande; Ad esempio, **time \* *_ può espandersi a _*"time OR timer OR times OR timex OR timex OR timeboxed OR ..."**. Il limite di 10.000 è il numero massimo di varianti che la parola può espandere e non il numero di documenti corrispondenti alla query. Non esiste alcun limite massimo per i termini non frasi.
>
> <sup>4</sup> Questo limite viene condiviso tra tutti gli strumenti di eDiscovery. Ciò significa che le esportazioni simultanee in Ricerca contenuto, Core eDiscovery e Advanced eDiscovery vengono applicate a questo limite.
>
> <sup>5</sup> Questo limite si applica al download di documenti selezionati da un insieme da rivedere. Non si applica all'esportazione di documenti da un insieme da rivedere. Per ulteriori informazioni sul download e l'esportazione di documenti, vedere Esportare i [dati dei casi in Advanced eDiscovery.](exporting-data-ediscover20.md)
>
> <sup>6</sup> Limiti di indicizzazione per organizzazione al giorno. Come soluzione alternativa, è possibile selezionare  più responsabile nella scheda  Origini dati in un caso e quindi fare clic su Aggiorna indice per evitare di creare un processo di indicizzazione separato per ogni responsabile. 
