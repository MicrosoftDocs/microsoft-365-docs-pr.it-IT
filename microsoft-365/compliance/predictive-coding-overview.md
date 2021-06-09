---
title: Modulo di codifica predittiva per Advanced eDiscovery (anteprima)
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
description: Il nuovo modulo di codifica predittiva in Advanced eDiscovery usa l'apprendimento automatico per analizzare gli elementi in un set di revisione per prevedere quali elementi sono rilevanti per il caso o l'indagine.
ms.openlocfilehash: 3c8fbd75bd585dd6ae722bf17deea906611d8df6
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822040"
---
# <a name="learn-about-predictive-coding-in-advanced-ediscovery-preview"></a>Informazioni sulla codifica predittiva in Advanced eDiscovery (anteprima)

Il modulo di codifica predittivo in Advanced eDiscovery utilizza le funzionalità intelligenti di machine learning per ridurre la quantità di contenuto da esaminare. La codifica predittiva consente di ridurre e ridurre grandi volumi di contenuto del caso a un set pertinente di elementi di cui è possibile definire la priorità per la revisione. Questa operazione viene eseguita creando e formando i propri modelli di codifica predittivi che consentono di definire la priorità della revisione degli elementi più rilevanti in un set di recensioni.

Il modulo di codifica predittiva è progettato per semplificare la complessità della gestione di un modello all'interno di un set di revisioni e fornire un approccio iterativo per la formazione del modello in modo da poter iniziare più velocemente con le funzionalità di machine learning in Advanced eDiscovery. Per iniziare, puoi creare un modello, etichettare fino a 50 elementi come rilevanti o non rilevanti. Il sistema usa questo training per applicare i punteggi di previsione a ogni elemento del set di recensioni. In questo modo puoi filtrare gli elementi in base al punteggio di previsione, che ti consente di esaminare prima gli elementi più pertinenti (o non rilevanti). Se si desidera eseguire il training di modelli con livelli di attribuzione e frequenza di richiamo più elevati, è possibile continuare a etichettare gli elementi nei round di training successivi fino a quando il modello non si stabilizza.  

## <a name="the-predictive-coding-workflow"></a>Flusso di lavoro di codifica predittiva

Ecco una panoramica e una descrizione di ogni flusso di lavoro di codifica predittiva per ogni passaggio. Per una descrizione più dettagliata dei concetti e della terminologia del processo di codifica predittiva, vedere [Predictive coding reference](predictive-coding-reference.md).

![Flusso di lavoro di codifica predittiva](..\media\PredictiveCodingWorkflow.png)

1. **Creare un nuovo modello di codifica predittiva nel set di revisioni**. Il primo passaggio consiste nel creare un nuovo modello di codifica predittiva nel set di revisioni. Per creare un modello, è necessario disporre di almeno 2.000 elementi nel set di revisione. Dopo aver creato un modello, il sistema determinerà il numero di elementi da utilizzare come *set di controlli*. Il set di controlli viene utilizzato durante il processo di training per valutare i punteggi di previsione assegnati dal modello agli elementi con l'etichettatura eseguita durante i round di training. Le dimensioni del set di controlli si basano sul numero di elementi nel set di revisione e sul livello di probabilità e sul margine di errore impostati durante la creazione del modello. Gli elementi nel set di controlli non cambiano mai e non sono identificabili per gli utenti.

   Per ulteriori informazioni, vedere [Create a predictive coding model](predictive-coding-create-model.md).

2. **Completare il primo ciclo di formazione etichettando gli elementi come rilevanti o non pertinenti.** Il passaggio successivo consiste nel eseguire il training del modello avviando il primo ciclo di training. Quando si avvia un round di training, il modello seleziona in modo casuale altri elementi dal set di revisione, denominato *set di training.* Questi elementi (sia dal set di controlli che dal set di formazione) vengono presentati in modo da poter etichettare ognuno di essi come "pertinente" o "non pertinente". La pertinenza si basa sul contenuto dell'elemento e non sui metadati del documento. Dopo aver completato il processo di etichettatura nel round di training, il modello "apprenderà" in base al modo in cui hai etichettato gli elementi nel set di training. In base a questo training, il modello eelaborare gli elementi nel set di revisione e applicare un punteggio di previsione a ognuno di essi.

   Per ulteriori informazioni, vedere [Training a predictive coding model](predictive-coding-train-model.md).

3. **Applicare il filtro del punteggio di previsione agli elementi nel set di revisione**. Al termine del passaggio di training precedente, il passaggio successivo consiste nell'applicare il filtro del punteggio di previsione agli elementi della revisione per visualizzare gli elementi che il modello ha determinato sono "più rilevanti" (in alternativa, è possibile utilizzare un filtro di previsione per visualizzare gli elementi "non rilevanti"). Quando si applica il filtro di stima, si specifica un intervallo di punteggi di stima da filtrare. L'intervallo di punteggi di previsione è compreso tra **0** e **1,** con **0** che è "non rilevante" e **1** è rilevante. In generale, gli elementi con punteggi di previsione compresi tra **0** e **0,5** sono considerati "non rilevanti" e gli elementi con punteggi di previsione compresi tra **0,5** e **1** sono considerati rilevanti.

   Per ulteriori informazioni, vedere [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).

4. **Eseguire più round di training fino a quando il modello non si stabilizza.** È possibile eseguire ulteriori round di training se si desidera creare un modello con una maggiore accuratezza della previsione e una maggiore frequenza di richiamo. *La frequenza* di richiamo misura la percentuale di elementi stimati dal modello pertinenti tra gli elementi effettivamente rilevanti (quelli contrassegnati come rilevanti durante il training). Il punteggio della frequenza di richiamo varia **da 0** a **1.** Un punteggio più vicino **a 1** indica che il modello identificherà gli elementi più rilevanti. In un nuovo ciclo di formazione vengono etichettati altri elementi in un nuovo set di formazione. Dopo aver completato il round di training, il modello viene aggiornato in base al nuovo apprendimento degli elementi di etichettatura più recenti nel set di training. Il modello elaturerà di nuovo gli elementi nel set di revisione e applierà nuovi punteggi di previsione. Puoi continuare a eseguire round di training finché il modello non si stabilizza. Un modello viene considerato stabilizzato quando il tasso di varianza dopo l'ultimo round di training è inferiore al 5%. *La percentuale di* varianza è definita come percentuale di elementi in un set di revisione in cui il punteggio di previsione è cambiato tra i turni di training. Il dashboard di codifica predittiva visualizza informazioni e statistiche che consentono di valutare la stabilità di un modello.

5. **Applica il filtro del punteggio di previsione "finale" per esaminare gli elementi impostati per definire la priorità della revisione.** Dopo aver completato tutti i round di training e aver stabilizzato il modello, l'ultimo passaggio consiste nell'applicare il punteggio di previsione finale al set di revisione per definire la priorità della revisione degli elementi rilevanti e non rilevanti. Si tratta della stessa attività eseguita nel passaggio 3, ma a questo punto il modello è stabile e non si prevede di eseguire altri round di training.
