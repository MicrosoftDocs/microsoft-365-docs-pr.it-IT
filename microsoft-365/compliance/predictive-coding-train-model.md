---
title: Training di un modello di codifica predittivo in Advanced eDiscovery
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
ms.openlocfilehash: ef6d1cf23d6cca58f4226696bc63c1dea5816cc1
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822552"
---
# <a name="train-a-predictive-coding-model-preview"></a>Eseguire il training di un modello di codifica predittivo (anteprima)

Dopo aver creato un modello di codifica predittivo in Advanced eDiscovery, il passaggio successivo consiste nell'eseguire il primo round di training per formare il modello su ciò che è rilevante e non pertinente nel set di recensioni. Dopo aver completato il primo ciclo di training, è possibile eseguire round di training successivi per migliorare la capacità del modello di prevedere contenuti pertinenti e non rilevanti.

Per esaminare il flusso di lavoro di codifica predittiva, vedere Informazioni sulla codifica [predittiva in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)

## <a name="before-you-train-a-model"></a>Prima di eseguire il training di un modello

- Durante un ciclo di formazione, etichettare gli elementi come **Rilevanti** o **Non** rilevanti in base alla pertinenza del contenuto del documento. Non basare la decisione sui valori nei campi dei metadati. Ad esempio, per i messaggi di posta elettronica Teams conversazioni, non basare la decisione di etichettatura sui partecipanti del messaggio. 

## <a name="train-a-model-for-the-first-time"></a>Training di un modello per la prima volta

1. Nel Centro Microsoft 365 conformità aprire un caso Advanced eDiscovery e quindi selezionare la **scheda Revisione set.**

2. Apri un set di recensioni e quindi fai clic su **Analisi**  >  **Gestisci codifica predittiva (anteprima)**.

3. Nella pagina **Modelli di codifica predittiva (anteprima)** selezionare il modello di cui si desidera eseguire il training.

4. Nella scheda **Panoramica,** in **Round 1,** fare clic **su Avvia il round di formazione successivo.**

   Viene **visualizzata** la scheda Formazione che contiene 50 elementi da etichettare.

5. Esaminare ogni documento e quindi selezionare il **pulsante Rilevante** o **Non** rilevante nella parte inferiore del riquadro di lettura per etichettarlo.

   ![Etichettare ogni documento come rilevante o non pertinente](..\media\TrainModel1.png)

6. Dopo aver etichettato tutti i 50 elementi, fare clic su **Fine.**

    Il sistema avrà un paio di minuti per "imparare" dall'etichettatura e aggiornare il modello. Al termine di questo processo, viene visualizzato lo stato **Pronto** per il modello nella pagina Modelli di codifica predittiva **(anteprima).**

## <a name="perform-additional-training-rounds"></a>Eseguire ulteriori round di formazione

Dopo aver eseguito il primo ciclo di formazione, è possibile eseguire round di formazione successivi seguendo i passaggi della sezione precedente. L'unica differenza è che il numero del round di training verrà aggiornato nella scheda **Panoramica del** modello. Ad esempio, dopo aver eseguito il primo round di formazione, è possibile fare clic su Avvia il round di **formazione** successivo per iniziare il secondo ciclo di formazione. E così via.

Ogni round di training (sia quelli in corso che quelli completati) viene visualizzato nella **scheda Training** per il modello. Quando si seleziona un round di formazione, viene visualizzata una pagina a comparsa con informazioni e metriche per il round.

## <a name="what-happens-after-you-perform-a-training-round"></a>Cosa succede dopo aver eseguito un round di formazione

Dopo aver eseguito il primo ciclo di formazione, viene avviato un processo che esegue le operazioni seguenti:

- In base al modo in cui hai etichettato i 40 elementi nel set di training, il modello apprende dall'etichettatura e si aggiorna per diventare più accurato.

- Il modello elabora quindi ogni elemento nell'intero set di revisione e assegna un punteggio di previsione compreso tra **0** (non rilevante) e **1** (pertinente).  

- Il modello assegna un punteggio di previsione ai 10 elementi del set di controlli etichettati durante il round di training. Il modello confronta il punteggio di stima di questi 10 elementi con l'etichetta effettiva assegnata all'elemento durante la fase di training. In base a questo confronto, il modello identifica la classificazione seguente (denominata matrice confusione *set* di controlli ) per valutare le prestazioni di previsione del modello:
  
  |          |Il modello prevede che l'elemento sia rilevante |Il modello prevede che l'elemento non sia rilevante |
  |:---------|:---------|:---------|
  |**Elemento etichette revisore pertinente**| True positive| Falso positivo |
  |**Elemento etichette revisore non pertinente**| Falso negativo |True negative |
  ||||

  In base a questi confronti, il modello deriva i valori per le metriche del punteggio F, della precisione e del richiamo e del margine di errore per ognuno di essi. I punteggi per queste metriche delle prestazioni del modello vengono visualizzati in una pagina a comparsa per il round di training. Per una descrizione di queste metriche, vedere [Informazioni di riferimento sulla codifica predittiva.](predictive-coding-reference.md)

- Infine, il modello determina i 50 elementi successivi che verranno utilizzati per il turno di training successivo. Questa volta, il modello potrebbe selezionare 20 elementi dal set di controlli e 30 nuovi elementi dal set di revisione e designarli come set di training per il turno successivo. Il campionamento per il turno di training successivo non viene campionato in modo uniforme. Il modello ottimizza la selezione di campionamento degli elementi dal set di recensioni per selezionare gli elementi in cui la previsione è ambigua, il che significa che il punteggio di stima è compreso nell'intervallo 0,5. Questo processo è noto come *selezione parziale.*

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a>Cosa succede dopo aver eseguito round di formazione successivi

Dopo aver eseguito round di training successivi (dopo il primo round di training), il modello esegue le operazioni seguenti:

- Il modello viene aggiornato in base alle etichette applicate al set di training in tale round di training.

- Il sistema valuta il punteggio di previsione del modello per gli elementi nel set di controlli e controlla se il punteggio è allineato al modo in cui hai etichettato gli elementi nel set di controlli. La valutazione viene eseguita su tutti gli elementi etichettati del set di controlli per tutti i round di training. I risultati di questa valutazione sono incorporati nel dashboard nella **scheda Panoramica** del modello.

- Il modello aggiornato rielabora ogni elemento nel set di revisione e assegna a ogni elemento un punteggio di previsione aggiornato.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver eseguito il primo round di training, è possibile eseguire più round di training o applicare il filtro del punteggio di previsione del modello al set di revisione per visualizzare gli elementi previsti dal modello come rilevanti o non pertinenti. Per ulteriori informazioni, vedere [Apply a prediction score filter to a review set](predictive-coding-apply-prediction-filter.md).
