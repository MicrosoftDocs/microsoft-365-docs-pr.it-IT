---
title: Eseguire query sui dati in un insieme da rivedere
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 4005b1e379b138f4eb22bb5c11e1f278185dc65e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597613"
---
# <a name="query-the-data-in-a-review-set"></a>Eseguire query sui dati in un insieme da rivedere

Nella maggior parte dei casi, sarà utile essere in grado di approfondire i dati in un set di revisione e organizzare tali dati per facilitare una revisione più efficiente. L'utilizzo di query in un set di revisione consente di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri della revisione.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Creazione e esecuzione di una query in un set di Revisione

Per creare ed eseguire una query sui documenti in un set di revisione, fare clic su **nuova query** nel set di revisione. Dopo aver denominato la query e aver definito le condizioni, fare clic su **Salva** per salvare ed eseguire la query. Per eseguire una query salvata in precedenza, fare clic su una query salvata.

![Esaminare le query di set](media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Creazione di una query del set di Revisione

È possibile creare una query utilizzando una combinazione di schede di condizione e lingua di query nella scheda condizione parole chiave. È inoltre possibile raggruppare le schede delle condizioni insieme come blocco (denominato *gruppo di condizioni*) per creare una query più complessa. Per un elenco e una descrizione delle proprietà dei metadati di cui è possibile eseguire la ricerca, vedere [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="condition-cards"></a>Schede delle condizioni

Tutti i campi ricercabili in un set di revisione dispongono di una scheda di condizione corrispondente che è possibile utilizzare per creare la query.

Sono disponibili più tipi di schede di condizione:

- FREETEXT: viene utilizzata una scheda di condizione FREETEXT per i campi di testo, ad esempio subject. È possibile elencare più termini di ricerca separandoli con una virgola.

- Data: viene utilizzata una scheda condizione data per i campi data, ad esempio la data dell'Ultima modifica.

- Opzioni di ricerca: una scheda condizione opzioni di ricerca fornirà un elenco di valori possibili per il campo specifico del set di revisione. Viene utilizzato per i campi, ad esempio sender, in cui è presente un numero finito di valori possibili nel set di revisione.

- Keyword: una scheda di condizione di parola chiave è un'istanza specifica di FREETEXT Condition card che è possibile utilizzare per cercare i termini oppure utilizzare la lingua di query KQL-like. Per ulteriori informazioni, vedere di seguito.

### <a name="query-language"></a>Lingua query

Oltre alle schede delle condizioni, è possibile utilizzare un linguaggio di query simile a KQL nella scheda Parole chiave per creare la query. Il linguaggio di query per le query dei set di revisione supporta gli operatori booleani standard, ad esempio **e**, **o**, **non**e **vicino**. Supporta anche un carattere jolly con caratteri singoli (?) e un carattere jolly a più caratteri (*).

## <a name="using-filters"></a>Utilizzo di filtri

Oltre alle query che è possibile salvare, è possibile utilizzare i filtri set di revisione per applicare rapidamente condizioni aggiuntive a una query del set di revisione. In questo modo è possibile affinare ulteriormente i risultati visualizzati da una query del set di revisione.

![Esaminare i filtri impostati](media/AeDReviewSetFilters.png)

I filtri differiscono dalle query in due modi significativi:

- I filtri sono transitori. Non vengono mantenuti oltre la sessione esistente. In altre parole, non è possibile salvare un filtro. Le query vengono salvate nel set di revisione e vengono accessibili ogni volta che si apre il set di revisione.

- I filtri sono sempre additivi. I filtri vengono applicati oltre alla query del set di revisione corrente. L'applicazione di una query diversa sostituirà i risultati restituiti dalla query corrente.
