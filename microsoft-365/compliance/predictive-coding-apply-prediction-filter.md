---
title: Applicare il filtro punteggio di previsione agli elementi in un set di recensioni
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
description: Utilizzare un filtro del punteggio di previsione per visualizzare gli elementi che un modello di codifica predittivo prevede come pertinente o non pertinente.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822528"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a>Applicare un filtro punteggio di previsione a un set di recensioni (anteprima)

Dopo aver creato un modello di codifica predittivo in Advanced eDiscovery e averlo addestrato al punto in cui è stabile, è possibile applicare il filtro del punteggio di previsione per visualizzare gli elementi del set di revisione che il modello ha determinato siano pertinenti (o non pertinenti). Quando si crea un modello, viene creato anche un filtro del punteggio di previsione corrispondente. È possibile utilizzare questo filtro per visualizzare gli elementi assegnati a un punteggio di previsione all'interno di un intervallo specificato. In generale, i punteggi di stima compresi tra **0** e **0,5** vengono assegnati agli elementi previsti dal modello non sono rilevanti. Gli elementi assegnati ai punteggi di previsione **compresi tra 0,5** e **1,0** sono elementi pertinenti previsti dal modello.

Ecco due modi per usare il filtro del punteggio di previsione:

- Definire la priorità della revisione degli elementi in un set di revisione previsto dal modello sono rilevanti.

- Gli elementi del set di revisione previsti dal modello non sono rilevanti. In alternativa, è possibile utilizzare il filtro del punteggio di previsione per de-definire la priorità per la revisione degli elementi non rilevanti.

## <a name="before-you-apply-a-prediction-score-filter"></a>Prima di applicare un filtro punteggio di previsione

- Creare un modello di codifica predittiva in modo che sia creato un filtro punteggio di previsione corrispondente.

- È possibile applicare un filtro punteggio di previsione dopo uno qualsiasi dei round di training. Tuttavia, potresti voler attendere dopo aver eseguito diversi round o finché il modello non è stabile prima di usare il filtro del punteggio di previsione.

## <a name="apply-a-prediction-score-filter"></a>Applicare un filtro del punteggio di previsione

1. Nel Centro Microsoft 365 conformità aprire il caso Advanced eDiscovery, selezionare la scheda **Set di** revisioni e quindi aprire il set di recensioni.

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

  > [!TIP]
  > Per visualizzare il punteggio di previsione effettivo assegnato a un documento, è possibile fare clic sulla **scheda Metadati** nel riquadro di lettura. I punteggi di stima per tutti i modelli nel set di revisione vengono visualizzati nella proprietà dei metadati **RelevanceScores.**

## <a name="more-information"></a>Ulteriori informazioni

- Per ulteriori informazioni sull'utilizzo dei filtri, vedere [Query and filter content in a review set](review-set-search.md).
