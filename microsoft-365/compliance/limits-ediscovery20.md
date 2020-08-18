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
description: Informazioni sui limiti del caso, sui limiti di indicizzazione e sui limiti di ricerca in vigore per la soluzione avanzata di eDiscovery in Microsoft 365.
ms.openlocfilehash: 5666bae5315586ed421ad8d6c748505cda8ae3e6
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778462"
---
# <a name="limits-in-advanced-ediscovery"></a>Limiti di Advanced eDiscovery

In questo articolo vengono descritti i limiti della soluzione avanzata di eDiscovery in Microsoft 365.

## <a name="case-and-review-set-limits"></a>Limiti del caso e del set di Revisione

Nella tabella seguente sono elencati i limiti relativi ai casi e ai set di revisione in Advanced eDiscovery.

|**Descrizione del limite**|**Tipo di limite**|
|:-----|:-----|
|Numero totale di documenti che è possibile aggiungere a un caso (per tutti i set di revisione in un caso).  <br/> |3 milioni <br/> |
|Dimensione totale dei file per set di carico. Questo include il caricamento di non Office 365 in un set di revisione.  <br/> |300 GB <br/> |
|Quantità totale di dati caricati in tutti i set di revisione nell'organizzazione al giorno.<br/> |2 TB <br/> |
|Numero massimo di set di carichi per caso.  <br/> |200 <br/> |
|Numero massimo di insiemi di revisione per ogni caso.  <br/> |20 <br/> |
|||

## <a name="indexing-limits"></a>Limiti di indicizzazione

Nella tabella seguente sono elencati i limiti di indicizzazione in Advanced eDiscovery.

|**Descrizione del limite**|**Tipo di limite**|
  |:-----|:-----|
  |Numero massimo di caratteri estratti da un singolo file.  <br/> |10 milioni<sup>1</sup> <br/> |
  |Dimensione massima di un singolo file.   <br/> |100 MB<sup>1</sup> <br/> |
  |Profondità massima degli elementi incorporati in un documento.  <br/> |25<sup>1</sup> <br/> |
  |Dimensioni massime dei file elaborati dal riconoscimento ottico dei caratteri (OCR).  <br/> |24 MB<sup>1</sup> <br/> |  
|||

## <a name="search-limits"></a>Limiti relativi alla ricerca

I limiti descritti in questa sezione sono correlati all'utilizzo dello strumento di ricerca nella scheda **ricerche** per raccogliere i dati per un caso. Per ulteriori informazioni, vedere [raccolta di dati per un caso in Advanced eDiscovery](collecting-data-for-ediscovery.md).

|**Descrizione del limite**|**Tipo di limite**|
|:-----|:-----|
|Numero massimo di cassette postali o siti che possono essere ricercati in una singola ricerca.  <br/> |Nessun limite  <br/> |
|Numero massimo di ricerche che possono essere eseguite contemporaneamente.  <br/> |Nessun limite  <br/> | 
|Numero massimo di ricerche che un singolo utente può avviare contemporaneamente.  <br/> |10   <br/> | 
|Numero massimo di caratteri per una query di ricerca (inclusi operatori e condizioni).  <br/> |**Cassette postali**: 10.000<br/>**Siti**: 4.000 quando si effettua la ricerca in tutti i siti o 2.000 quando si effettua la ricerca fino a 20 siti <sup>2</sup> <br/> |
|Numero minimo di caratteri alfanumerici per i caratteri jolly del prefisso; ad esempio **1 \* ** o **set \* **. <br/> |3  <br/> |  
|Numero massimo di varianti restituite quando si utilizza il carattere jolly del prefisso per cercare una frase esatta o quando si utilizza un carattere jolly di prefisso e l'operatore booleano **vicino** .  <br/> |10.000 <sup>3</sup> <br/> |
|Numero massimo di elementi per ogni cassetta postale utente che vengono visualizzati nella pagina di anteprima per le ricerche. Vengono visualizzati gli elementi più recenti.   <br/> |100  <br/> |
|Numero massimo di elementi di tutte le cassette postali visualizzate nella pagina di anteprima per le ricerche.  <br/> |1.000  <br/> |
|Numero massimo di cassette postali che è possibile visualizzare in anteprima per i risultati della ricerca.  Se sono presenti più di 1000 cassette postali che contengono elementi che corrispondono alla query di ricerca, sono disponibili per l'anteprima solo le cassette postali di 1.000 con la maggior parte dei risultati.<br/> |1.000  <br/> |
|Numero massimo di elementi di siti di SharePoint e OneDrive for business visualizzati nella pagina di anteprima per le ricerche. Vengono visualizzati gli elementi più recenti.  <br/> |200  <br/> |
|Numero massimo di siti di SharePoint e OneDrive for business che è possibile visualizzare in anteprima per i risultati della ricerca. Se sono presenti più di 200 siti che contengono elementi che corrispondono alla query di ricerca, solo i primi 200 siti con la maggior parte dei risultati sono disponibili per l'anteprima.  <br/> |200  <br/> |
|Numero massimo di elementi per ogni cassetta postale di cartelle pubbliche visualizzata nella pagina di anteprima per le ricerche.  <br/> |100  <br/> |
|Numero massimo di elementi presenti in tutti gli elementi della cassetta postale delle cartelle pubbliche visualizzati nella pagina di anteprima per le ricerche.  <br/> |200  <br/> |
|Numero massimo di cassette postali delle cartelle pubbliche che è possibile visualizzare in anteprima per i risultati della ricerca. Se sono presenti più di 500 cassette postali delle cartelle pubbliche che contengono elementi che corrispondono alla query di ricerca, solo le cassette postali di 500 con la maggior parte dei risultati sono disponibili per l'anteprima.  <br/> |500  <br/> |
|||

## <a name="viewer-limits"></a>Limiti del Visualizzatore

|**Descrizione del limite**|**Tipo di limite**|
  |:-----|:-----|
  |Dimensione massima del file di Excel che è possibile visualizzare nel Visualizzatore nativo.  <br/> |4 MB  <br/> |
|||

## <a name="review-set-download-limits"></a>Revisione dei limiti di download dei set

|**Descrizione del limite**|**Tipo di limite**|
|:-----|:-----|
|Totale dimensioni dei file o numero massimo di documenti scaricati da un set di revisione.  <br/> |3 MB o 50 documenti <sup>4</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> qualsiasi elemento che supera il limite di un singolo file verrà visualizzato come un errore di elaborazione.<br/>
> <sup>2</sup> quando si eseguono ricerche nei percorsi di SharePoint e OneDrive for business, i caratteri negli URL dei siti di cui è stata eseguita la ricerca vengono conteggiati rispetto a questo limite.<br/>
> <sup>3</sup> per le query non basate su frasi (un valore di parola chiave che non utilizza virgolette doppie) viene utilizzato un indice di prefisso speciale. Questo indica che si verifica una parola in un documento, ma non in cui si trova nel documento. Per eseguire una query di frase (un valore di parola chiave con virgolette doppie), è necessario confrontare la posizione all'interno del documento per le parole della frase. Questo significa che non è possibile utilizzare l'indice di prefisso per le query di frase. In questo caso, la query viene espansa internamente con tutte le parole possibili che il prefisso espande; ad esempio, **il \* tempo** può espandersi su **"ora o timer o orari o Timex o timeboxed o..."**. Il limite di 10.000 è il numero massimo di varianti a cui la parola può espandersi, non il numero di documenti che corrispondono alla query. Non esiste un limite superiore per i termini non frase.<br/>
> <sup>4</sup> questo limite si applica al download di documenti selezionati da un set di revisione. Non si applica ai documenti di esportazione da un set di revisione. Per ulteriori informazioni sul download e l'esportazione di documenti, vedere [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md). <br/>

