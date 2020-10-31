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
description: Informazioni su come creare ed eseguire una query in un set di revisione per organizzare i dati per una revisione più efficiente in un caso avanzato di eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816569"
---
# <a name="query-the-data-in-a-review-set"></a>Eseguire query sui dati in un insieme da rivedere

Nella maggior parte dei casi, sarà utile essere in grado di approfondire i dati in un set di revisione e organizzare tali dati per facilitare una revisione più efficiente. L'utilizzo di query in un set di revisione consente di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri della revisione.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Creazione e esecuzione di una query in un set di Revisione

Per creare ed eseguire una query sui documenti in un set di revisione, selezionare **nuova query** nel set di revisione. Dopo aver denominato la query e aver definito le condizioni, selezionare **Salva** per salvare ed eseguire la query. Per eseguire una query salvata in precedenza, selezionare una query salvata.

![Esaminare le query di set](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Creazione di una query del set di Revisione

È possibile creare una query utilizzando una combinazione di parole chiave, proprietà e condizioni nella condizione keywords. È inoltre possibile raggruppare le condizioni come blocco (denominato *gruppo di condizioni* ) per creare una query più complessa. Per un elenco e una descrizione delle proprietà dei metadati di cui è possibile eseguire la ricerca, vedere [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="conditions"></a>Condizioni

Tutti i campi ricercabili in un set di revisione dispongono di una condizione corrispondente che è possibile utilizzare per creare la query.

Sono disponibili più tipi di condizioni:

- FREETEXT: viene utilizzata una condizione FREETEXT per i campi di testo, ad esempio subject. È possibile elencare più termini di ricerca separandoli con una virgola.

- Data: viene utilizzata una condizione data per i campi data, ad esempio la data dell'Ultima modifica.

- Opzioni di ricerca: una condizione per le opzioni di ricerca fornirà un elenco di valori possibili per il campo specifico del set di revisione. Viene utilizzato per i campi, ad esempio sender, in cui è presente un numero finito di valori possibili nel set di revisione.

- Keyword: una condizione di parola chiave è un'istanza specifica della condizione di FREETEXT che è possibile utilizzare per cercare i termini oppure utilizzare la lingua di query simile a KQL. Per ulteriori informazioni, vedere di seguito.

### <a name="query-language"></a>Lingua query

Oltre alle condizioni, è possibile utilizzare un linguaggio di query simile a KQL nella condizione keywords per creare la query. Il linguaggio di query per le query dei set di revisione supporta gli operatori booleani standard, ad esempio **e** , **o** , **non** e **vicino** . Supporta anche un carattere jolly con caratteri singoli (?) e un carattere jolly a più caratteri (*).

## <a name="filters"></a>Filtri

Oltre alle query che è possibile salvare, è possibile utilizzare i filtri set di revisione per applicare rapidamente condizioni aggiuntive a una query del set di revisione. L'utilizzo dei filtri consente di affinare ulteriormente i risultati visualizzati da una query del set di revisione.

![Esaminare i filtri impostati](../media/AeDReviewSetFilters.png)

I filtri differiscono dalle query in due modi significativi:

- I filtri sono transitori. Non vengono mantenuti oltre la sessione esistente. In altre parole, non è possibile salvare un filtro. Le query vengono salvate nel set di revisione e vengono accessibili ogni volta che si apre il set di revisione.

- I filtri sono sempre additivi. I filtri vengono applicati oltre alla query del set di revisione corrente. L'applicazione di una query diversa sostituirà i risultati restituiti dalla query corrente.
