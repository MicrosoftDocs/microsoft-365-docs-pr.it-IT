---
title: Codifica predittiva in Advanced eDiscovery - Guida introduttiva
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
description: Informazioni su come iniziare a usare il modulo di codifica predittiva in Advanced eDiscovery. In questo articolo viene descritto il processo end-to-end relativo all'utilizzo della codifica predittiva per identificare il contenuto in un set di recensioni più rilevante per l'indagine.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822560"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a>Guida introduttiva: codifica predittiva in Advanced eDiscovery (anteprima)

In questo articolo viene presentata una guida introduttiva all'uso della codifica predittiva in Advanced eDiscovery. Il modulo di codifica predittivo in Advanced eDiscovery utilizza le funzionalità intelligenti di machine learning in Advanced eDiscovery per ridurre la quantità di contenuto da esaminare. La codifica predittiva consente di ridurre e ridurre grandi volumi di contenuto del caso a un set pertinente di elementi di cui è possibile definire la priorità per la revisione. Questa operazione viene eseguita creando e formando i propri modelli di codifica predittivi che consentono di definire la priorità della revisione degli elementi più rilevanti in un set di recensioni.

Ecco una breve panoramica del processo di codifica predittiva:

![Processo di avvio rapido per la codifica di previsione](..\media\PredictiveCodingQuickStartProcess.png)

Per iniziare, crea un modello e etichetta fino a 50 elementi come pertinenti o non rilevanti. Il sistema usa quindi questo training per applicare i punteggi di previsione a ogni elemento del set di recensioni. In questo modo puoi filtrare gli elementi in base al punteggio di previsione, che ti consente di esaminare prima gli elementi più pertinenti (o non rilevanti). Se si desidera eseguire il training di modelli con livelli di attribuzione e frequenza di richiamo più elevati, è possibile continuare a etichettare gli elementi nei round di training successivi fino a quando il modello non si stabilizza. Una volta stabilizzato il modello, è possibile applicare il filtro di stima finale per definire la priorità degli elementi da esaminare.

Per una panoramica dettagliata della codifica predittiva, vedere Informazioni sulla codifica [predittiva in Advanced eDiscovery](predictive-coding-overview.md).

## <a name="step-1-create-a-new-predictive-coding-model"></a>Passaggio 1: Creare un nuovo modello di codifica predittiva

Il primo passaggio consiste nel creare un nuovo modello di codifica predittiva nel set di revisioni

1. Nel Centro Microsoft 365 conformità aprire un caso Advanced eDiscovery e quindi selezionare la **scheda Revisione set.**

2. Apri un set di recensioni e quindi fai clic su **Analisi**  >  **Gestisci codifica predittiva (anteprima)**.

   ![Fai clic sul menu a discesa Analizza nel set di recensioni per passare alla pagina Codifica predittiva](..\media\ManagePredictiveCoding.png)

3. Nella pagina **Modelli di codifica predittiva (anteprima)** fare clic su **Nuovo modello.**

4. Nella pagina a comparsa digitare un nome per il modello e una descrizione facoltativa.

5. Fare **clic su** Salva per creare il modello.

   Il sistema predisporrà il modello in un paio di minuti. Una volta pronto, è possibile eseguire il primo ciclo di formazione.

Per istruzioni più dettagliate, vedere [Create a predictive coding model](predictive-coding-create-model.md).

## <a name="step-2-perform-the-first-training-round"></a>Passaggio 2: Eseguire il primo round di formazione

Dopo aver creato il modello, il passaggio successivo consiste nel completare il primo ciclo di training etichettando gli elementi come rilevanti o non rilevanti.

1. Apri il set di revisione e quindi fai **clic** su Analisi  >  **Gestisci codifica predittiva (anteprima).**

2. Nella pagina **Modelli di codifica predittiva (anteprima)** selezionare il modello di cui si desidera eseguire il training.

3. Nella scheda **Panoramica,** in **Round 1,** fare clic **su Avvia il round di formazione successivo.**

   Viene **visualizzata** la scheda Formazione che contiene 50 elementi da etichettare.

4. Esaminare ogni documento e quindi selezionare il **pulsante Rilevante** o **Non** rilevante nella parte inferiore del riquadro di lettura per etichettarlo.

   ![Etichettare ogni documento come rilevante o non pertinente](..\media\TrainModel1.png)

5. Dopo aver etichettato tutti i 50 elementi, fare clic su **Fine.**

    Il sistema avrà un paio di minuti per "imparare" dall'etichettatura e aggiornare il modello. Al termine di questo processo, viene visualizzato lo stato **Pronto** per il modello nella pagina Modelli di codifica predittiva **(anteprima).**

Per istruzioni più dettagliate, vedere [Training a predictive coding model](predictive-coding-train-model.md).

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a>Passaggio 3: Applicare il filtro del punteggio di previsione agli elementi nel set di revisione

Dopo aver eseguito al momento del lease un round di training, è possibile applicare il filtro del punteggio di previsione agli elementi nel set di revisione. In questo modo è possibile esaminare gli elementi previsti dal modello come rilevanti o non pertinenti.   

1. Apri il set di recensioni.

   ![Fare clic su Filtri per visualizzare la pagina a comparsa Filtri](..\media\PredictionScoreFilter0.png)

   I filtri predefiniti precaricati vengono visualizzati nella parte superiore della pagina del set di recensioni. È possibile lasciare questa impostazione su **Any**.

2. Fare **clic su** Filtri per visualizzare la pagina **a** comparsa Filtri.

3. Espandi la **sezione Analisi & codifica predittiva** per visualizzare un set di filtri.

      ![Filtro punteggio di previsione nella sezione Analisi & codifica predittiva](..\media\PredictionScoreFilter1.png)

   La convenzione di denominazione per i filtri del punteggio di previsione è **Punteggio di previsione (nome modello).** Ad esempio, il nome del filtro del punteggio di previsione per un modello denominato **Modello A** è Punteggio di **previsione (modello A).**

4. Selezionare il filtro del punteggio di previsione che si desidera utilizzare e quindi fare clic su **Fine.**

5. Nella pagina del set di recensioni, fare clic sull'elenco a discesa per il filtro del punteggio di previsione e digitare i valori minimo e massimo per l'intervallo di punteggio di previsione. Ad esempio, lo screenshot seguente mostra un intervallo di punteggio di previsione compreso tra **0,5** e **1,0.**

   ![Valori minimi e massimi per il filtro del punteggio di previsione](..\media\PredictionScoreFilter2.png)

6. Fare clic all'esterno del filtro per applicare automaticamente il filtro al set di revisioni.

  Nella pagina del set di revisioni viene visualizzato un elenco di documenti con un punteggio di previsione compreso nell'intervallo specificato.

Per istruzioni più dettagliate, vedere [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).

## <a name="step-4-perform-more-training-rounds"></a>Passaggio 4: Eseguire più round di formazione

Più che probabile, dovrai eseguire più round di formazione per formare il modulo per prevedere meglio gli elementi pertinenti e non rilevanti nel set di recensioni. In generale, il modello verrà addestrato abbastanza volte fino a quando non si stabilizzerà abbastanza per soddisfare i requisiti.

Per ulteriori informazioni, vedere [Eseguire round di formazione aggiuntivi](predictive-coding-train-model.md#perform-additional-training-rounds)

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a>Passaggio 5: Applicare il filtro del punteggio di previsione finale per definire le priorità della revisione

Ripetere le istruzioni nel passaggio 3 per applicare il punteggio di previsione finale al set di revisione per definire la priorità della revisione degli elementi rilevanti e non rilevanti dopo aver completato tutti i round di training e aver stabilizzato il modello.
