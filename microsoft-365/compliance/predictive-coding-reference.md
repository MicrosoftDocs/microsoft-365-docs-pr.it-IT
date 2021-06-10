---
title: Riferimento della codifica predittiva
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: ''
ms.openlocfilehash: 90c76fade54c109fc02e145a49bbe93d11ad8b79
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822525"
---
# <a name="predictive-coding-reference-preview"></a>Riferimento alla codifica predittiva (anteprima)

Questo articolo descrive i concetti chiave e le metriche dello strumento di codifica predittiva in Advanced eDiscovery. Le sezioni dell'articolo sono elencate in ordine alfabetico.

## <a name="confidence-level"></a>Livello di probabilità

Il livello di probabilità è un'impostazione avanzata quando si crea un modello di codifica predittivo. Definisce che le metriche delle prestazioni del modello (ad esempio, richness, precisione e richiamo) rientrano in un intervallo specificato (che è determinato il margine di errore definito per il modello) che è rappresentativo dei valori effettivi dei punteggi di previsione assegnati dal modello agli elementi nel set di revisione. I valori relativi al livello di probabilità e al margine di errore consentono inoltre di determinare il numero di elementi inclusi nel set di controlli. Il valore predefinito per il livello di probabilità è 0,95 o 95%.

## <a name="control-set"></a>Set di controlli

Un set di controlli viene utilizzato durante il processo di training di un modello di codifica predittivo. Il set di controlli consente di valutare i punteggi di stima assegnati dal modello agli elementi con l'etichettatura eseguita durante i round di training. Le dimensioni del set di controlli si basano sul numero di elementi nel set di revisione e sul livello di probabilità e sul margine di errore impostati durante la creazione del modello. Gli elementi nel set di controlli non cambiano mai e non sono identificabili per gli utenti. Il numero totale di elementi nel set di controlli viene visualizzato nella pagina del riquadro a comparsa per un round di training.

## <a name="control-set-confusion-matrix"></a>Matrice confusione set di controlli

Dopo aver completato un round di training, il modello assegna un punteggio di previsione ai 10 elementi nel set di controlli etichettati durante la fase di training. Il modello confronta il punteggio di stima di questi 10 elementi con l'etichetta effettiva assegnata all'elemento durante la fase di training. In base a questo confronto, il modello identifica le classificazioni seguenti per valutare le prestazioni di previsione del modello:
  
  |          |Il modello prevede che l'elemento sia rilevante |Il modello prevede che l'elemento non sia rilevante |
  |:---------|:---------|:---------|
  |**Elemento etichette revisore pertinente**| True positive| Falso positivo |
  |**Elemento etichette revisore non pertinente**| Falso negativo |True negative |
  ||||

  In base a questi confronti, il modello deriva i valori per le metriche del punteggio F, della precisione e del richiamo e del margine di errore per ognuno di essi. Il numero di ognuno dei tipi di confusione della matrice viene visualizzato nella pagina del riquadro a comparsa per un round di training.

## <a name="f-score"></a>Punteggio F

Il punteggio F è una media ponderata dei punteggi per le metriche di precisione e richiamo.  L'intervallo di punteggi per questa metrica è **compreso tra 0** e **1.** Un punteggio più vicino **a 1** indica che il modello rileverà in modo più accurato gli elementi rilevanti. La metrica punteggio F viene visualizzata nel dashboard del modello e nella pagina del riquadro a comparsa per ogni round di training.

## <a name="margin-of-error"></a>Margine di errore

Il margine di errore è un'impostazione avanzata quando crei una modalità di codifica predittiva. Specifica il grado di errore nelle metriche delle prestazioni (ad esempio, richness, precisione e richiamo) derivato dal campionamento casuale di elementi nel set di controlli. Un margine di errore inferiore richiede un set di controlli più grande per garantire che le metriche delle prestazioni del modello rientrano in un intervallo inferiore. I valori relativi al margine di errore e al livello di probabilità consentono inoltre di determinare il numero di elementi inclusi nel set di controlli. Il valore predefinito per il margine di errore è 0,05 o 5%.

## <a name="model-stability"></a>Stabilità del modello

La stabilità del modello indica la capacità del modello di prevedere con precisione se un documento in un set di revisioni è rilevante o meno. Quando un modello è instabile, potrebbe essere necessario eseguire più round di training per includere la stabilità del modello. Quando il modello è stabile, potrebbe non essere necessario eseguire altri round di training. Il dashboard del modello indica lo stato corrente della stabilità del modello. Quando un modello è stabile, le metriche delle prestazioni hanno raggiunto un livello corrispondente alle impostazioni per il livello di probabilità e il margine di errore.

## <a name="overturn-rate"></a>Tasso di capovolta

La percentuale di storno è la percentuale di elementi nel set di revisione in cui il punteggio di previsione è cambiato tra i turni di training. Un modello è considerato stabile quando il tasso di capovolta è inferiore al 5%. La metrica della frequenza di capovolta viene visualizzata nel dashboard del modello e nella pagina del riquadro a comparsa per ogni round di training. Il tasso di rovesciamento per il primo turno di training è zero perché non esiste un punteggio di previsione precedente da capovolre.

## <a name="precision"></a>Precisione

La metrica di precisione misura la proporzione di elementi effettivamente rilevanti tra gli elementi previsti dal modello. Ciò significa che gli elementi nel set di controlli dove l'etichetta è rilevante per il revisore e viene stimata come rilevante dal modello. L'intervallo di punteggi per questa metrica è **compreso tra 0** e **1.** Un punteggio più vicino **a 1** indica che il modello identificherà meno elementi non rilevanti. La metrica di precisione viene visualizzata nel dashboard del modello e nella pagina a comparsa per ogni round di training.

## <a name="prediction-score"></a>Punteggio di previsione

Questo è il punteggio assegnato da un modello a ogni documento in un set di revisioni. Il punteggio si basa sulla pertinenza del documento rispetto all'apprendimento del modello dai round di training. In generale, gli elementi con punteggi di previsione compresi tra **0** e **0,5** sono considerati non rilevanti e gli elementi con punteggi di previsione compresi tra **0,5** e **1** sono considerati rilevanti. Il punteggio di previsione è contenuto in un campo dei metadati del documento. È possibile utilizzare un filtro di stima per visualizzare gli elementi in un set di revisione che rientrano in un intervallo di stima specificato.

## <a name="recall"></a>Richiamo

La metrica di richiamo misura la percentuale di elementi previsti dal modello pertinenti tra gli elementi effettivamente rilevanti. Ciò significa che anche gli elementi nel set di controlli che il modello previsto erano rilevanti sono stati etichettati come rilevanti dal revisore. L'intervallo di punteggi per questa metrica è **compreso tra 0** e **1.** Un punteggio più vicino **a 1** indica che il modello identificherà una parte più grande degli elementi rilevanti. La metrica di richiamo viene visualizzata nel dashboard del modello e nella pagina a comparsa per ogni round di training.

## <a name="review-set"></a>Set di revisione

Un set di revisione fornisce l'ambito di un modello di codifica predittivo. Quando si crea un nuovo modello per il set di revisione, gli elementi per il set di controlli e i set di formazione vengono selezionati dal set di revisione. Quando il modello assegna i punteggi di previsione, assegna a tali punteggi gli elementi nella revisione. È necessario aggiungere tutti gli elementi al set di revisione prima di creare un modello di codifica predittivo. Se si aggiungono elementi dopo aver creato un modello, a tali elementi non verrà assegnato un punteggio di stima.

## <a name="richness"></a>Richness

La metrica richness misura la percentuale di elementi del set di revisione previsti dal modello come rilevanti. L'intervallo di punteggi per questa metrica è **compreso tra 0** e **1.** La metrica richness viene visualizzata nel dashboard del modello.

## <a name="sampled-items"></a>Elementi campionati

Il termine *elementi* campionati è un riferimento a un campione casuale di elementi in un set di revisione (che contengono testo) selezionati e associati al set di controlli quando si crea un modello di codifica predittivo. Per ogni turno di training viene selezionato anche un campione casuale di elementi. Gli elementi selezionati per il set di controlli di un modello non vengono mai inclusi in un set di training per lo stesso modello. È vero anche il contrario: gli elementi del set di training non vengono mai inclusi nel set di controlli.

## <a name="training-set"></a>Set di formazione

Il modello seleziona casualmente gli elementi dal set di revisione e li aggiunge a un set di training. Durante un ciclo di formazione, vengono presentati gli elementi del set di formazione (oltre agli elementi del set di controlli) in modo da poter etichettare ognuno di essi come "pertinente" o "non rilevante". Questo processo di etichettatura o "training" consente al modello di imparare a prevedere quali elementi della revisione sono pertinenti o non pertinenti. Ogni volta che si esegue un round di training, il modello seleziona più elementi dalla revisione e li aggiunge al set di training per tale round di training. Gli elementi del set di controlli non vengono mai selezionati per un set di training.
