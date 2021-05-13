---
title: Eseguire query sui dati in un insieme da rivedere
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come creare ed eseguire una query in un set di revisione per organizzare i dati per una revisione più efficiente in un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345801"
---
# <a name="query-the-data-in-a-review-set"></a>Eseguire query sui dati in un insieme da rivedere

Nella maggior parte dei casi, sarà utile essere in grado di approfondire i dati in un set di recensioni e organizzare tali dati per facilitare una revisione più efficiente. L'utilizzo di query in un set di revisione consente di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri della revisione.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Creazione ed esecuzione di una query in un set di revisione

Per creare ed eseguire una query sui documenti di un set di revisioni, selezionare **Nuova query** nel set di revisioni. Dopo aver definito la query e aver definito le condizioni, selezionare **Salva** per salvare ed eseguire la query. Per eseguire una query salvata in precedenza, selezionare una query salvata.

![Esaminare le query impostate](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Creazione di una query del set di revisione

È possibile creare una query utilizzando una combinazione di parole chiave, proprietà e condizioni nella condizione Parole chiave. È inoltre possibile raggruppare le condizioni come blocco ( denominato gruppo *di condizioni*) per creare una query più complessa. Per un elenco e una descrizione delle proprietà dei metadati che è possibile cercare, vedere [Campi dei metadati del documento in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="conditions"></a>Condizioni

Ogni campo ricercabile in un set di revisione ha una condizione corrispondente che è possibile utilizzare per creare la query.

Esistono più tipi di condizioni:

- Testo libero: per i campi di testo, ad esempio l'oggetto, viene utilizzata una condizione di testo libero. È possibile elencare più termini di ricerca separandoli con una virgola.

- Data: per i campi data, ad esempio la data dell'ultima modifica, viene utilizzata una condizione di data.

- Opzioni di ricerca: una condizione delle opzioni di ricerca fornirà un elenco dei valori possibili per il campo specifico nel set di recensioni. Viene utilizzato per i campi, ad esempio il mittente, in cui è presente un numero limitato di valori possibili nel set di revisioni.

- Parola chiave: una condizione di parola chiave è un'istanza specifica della condizione di testo libero che puoi usare per cercare termini o usare un linguaggio di query simile a KQL. Vedi di seguito per altri dettagli.

### <a name="query-language"></a>Linguaggio di query

Oltre alle condizioni, è possibile utilizzare un linguaggio di query simile a KQL nella condizione Keywords per creare la query. Il linguaggio di query per le query di set di revisione supporta gli operatori Boolean standard, ad **esempio AND**, **OR**, **NOT** e **NEAR.** Supporta inoltre un carattere jolly a carattere singolo (?) e un carattere jolly a più caratteri (*).

## <a name="filters"></a>Filtri

Oltre alle query che è possibile salvare, è possibile utilizzare i filtri dei set di revisione per applicare rapidamente condizioni aggiuntive a una query del set di revisione. L'utilizzo dei filtri consente di perfezionare ulteriormente i risultati visualizzati da una query del set di revisione.

![Esaminare i filtri impostati](../media/AeDReviewSetFilters.png)

I filtri differiscono dalle query in due modi significativi:

- I filtri sono temporanei. Non vengono mantenuti oltre la sessione esistente. In altre parole, non è possibile salvare un filtro. Le query vengono salvate nel set di revisione e vi accedono ogni volta che si apre il set di revisioni.

- I filtri sono sempre additivi. I filtri vengono applicati in aggiunta alla query corrente dell'insieme da rivedere. L'applicazione di una query diversa sostituirà i risultati restituiti dalla query corrente.
