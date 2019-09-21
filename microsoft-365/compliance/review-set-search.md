---
title: Eseguire query sui dati in un insieme da rivedere
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
ms.openlocfilehash: 446f3f2588a79cb328476db490f1f555448b5ce7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084775"
---
# <a name="query-the-data-in-a-review-set"></a>Eseguire query sui dati in un insieme da rivedere

Nella maggior parte dei casi, sarà utile essere in grado di approfondire gli elementi presenti in un set di revisione e organizzarli per la revisione in modo più efficiente. Le query all'interno di un set di revisione consentono di eseguire questa operazione consentendo di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri definiti dall'utente in una sola volta.

## <a name="creating-and-running-a-query-within-a-review-set"></a>Creazione e esecuzione di una query all'interno di un set di Revisione

Per creare ed eseguire una query all'interno del set di recensioni, fare clic su "nuova query" nel set di recensioni. Dopo aver denominati la query e aver definito le condizioni, fare clic su "Salva" per eseguire la query. Per eseguire una query salvata in precedenza, è sufficiente fare clic sulla query salvata. Fare riferimento ai [campi dei metadati del documento](document-metadata-fields.md) per un elenco di metadati di cui è possibile eseguire la ricerca.

## <a name="building-your-query"></a>Creazione di una query

È possibile creare la query utilizzando una combinazione di schede di condizione e lingua di query nella scheda condizione parole chiave. È possibile raggruppare le schede delle condizioni insieme come blocco per creare una query più complessa.

### <a name="condition-card"></a>Scheda condizione

Tutti i campi ricercabili in un set di revisione dispongono di una scheda di condizione corrispondente che è possibile utilizzare per creare la query.

Sono disponibili più tipi di schede di condizione:
- FREETEXT: la scheda di stato FREETEXT viene utilizzata per i campi di testo, ad esempio subject. È possibile elencare più termini di ricerca separandoli con una virgola.
- Data: la scheda condizione data viene utilizzata per i campi data, ad esempio la data dell'Ultima modifica.
- Opzioni di ricerca: la scheda delle opzioni di ricerca fornirà un elenco di valori possibili per il campo specifico del set di revisione. Viene utilizzato per i campi, ad esempio sender, in cui è presente un numero finito di valori possibili nel set di revisione.
- Keyword: la scheda condizione parola chiave è una specifica istanza della scheda di condizione di FREETEXT che è possibile utilizzare per cercare i termini oppure utilizzare la lingua di query simile a KQL. Per ulteriori informazioni, vedere di seguito.

### <a name="query-language"></a>Lingua query

Oltre alle schede delle condizioni, è possibile utilizzare una lingua di query simile a KQL nella scheda Parole chiave per creare la query. Il linguaggio di query supporta la sintassi di KQL standard, come e, o, non e vicino (n). Supporta anche caratteri jolly con caratteri singoli (?) e caratteri jolly (*).

## <a name="filter"></a>Filtro

Oltre alle query che è possibile salvare, è possibile sovrapporre ulteriori condizioni al volo ai risultati delle query utilizzando filtri. I filtri differiscono dalle query in pochi modi significativi:
- I filtri sono transitori (ovvero non sono permanenti su sessioni diverse), mentre le query vengono salvate nel set di revisione.
- I filtri sono sempre additivi. i filtri verranno applicati in base alla query in vigore al momento, mentre l'applicazione di una query sostituirà la query in effetti.