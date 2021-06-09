---
title: Ritiro del modulo di pertinenza in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: Il modulo Pertinenza in Advanced eDiscovery verrà ritirato il 10 marzo 2021. Questo articolo spiega cosa fare prima che la rilevanza venga ritirata. In particolare, completare tutti i modelli non completati eseguendo il calcolo batch in modo da poter conservare i metadati del modello.
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821998"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a>Ritiro del modulo Pertinenza in Advanced eDiscovery

Il 10 marzo 2021 ritiriamo il modulo Pertinenza in Advanced eDiscovery. Questo ritiro significa che le organizzazioni non avranno più accesso al modulo Pertinenza (accedendo a Gestisci set di revisione Pertinenza in un caso di Advanced eDiscovery) o potranno accedere ai modelli di pertinenza  >   esistenti. Il modulo di rilevanza corrente in fase di ritiro verrà sostituito con una nuova soluzione di codifica predittiva nel Q2 CY 2021. Questa nuova funzionalità consente alle organizzazioni di creare modelli di codifica predittivi personalizzati in un flusso di lavoro più semplice e intuitivo.

Per prepararsi a questo ritiro imminente, è consigliabile che le organizzazioni che utilizzano il modulo Pertinenza esportino l'output del modello prima della data di ritiro eseguendo un calcolo batch per tutti i modelli esistenti. Tutti i punteggi di pertinenza del modello verranno archiviati in modo permanente nel set di revisione corrispondente e accessibili quando i documenti vengono esportati. I punteggi di pertinenza vengono mantenuti anche come metadati nel file di caricamento. Inoltre, sarà comunque possibile filtrare il contenuto nel set di recensioni in base al punteggio di pertinenza e avere accesso a tutti i metadati prodotti dai modelli di pertinenza.

## <a name="complete-unfinished-models"></a>Completare i modelli non completati

Per tutti i modelli di pertinenza non completati, completare la valutazione, la formazione e il calcolo batch in modo da poter applicare il modello ai documenti in un set di revisioni. Il completamento del calcolo batch conserverà le informazioni dopo la data di ritiro del modulo Pertinenza.

Ecco i passaggi per completare tutti i modelli non completati:

1. Eseguire il training del modello fino a quando non viene stabilizzato e pronto per il calcolo batch. Vedi [Formazione su tagging e pertinenza.](tagging-and-relevance-training-in-advanced-ediscovery.md)

   Lo screenshot seguente mostra un modulo pronto per un calcolo batch. Si noti che la valutazione e la formazione sono completate e il passaggio successivo consiste nell'eseguire il calcolo batch.

   ![Screenshot del modello pronto per il calcolo batch](../media/ReadyForBatchCalculation.png)

2. Eseguire il calcolo batch. Vedere [Esecuzione del calcolo batch](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).

3. Verificare che il calcolo batch sia stato eseguito correttamente. Vedere [Risultati del calcolo batch](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).

Per assistenza nel completamento dei modelli di pertinenza non completati, contattare il supporto tecnico Microsoft.
