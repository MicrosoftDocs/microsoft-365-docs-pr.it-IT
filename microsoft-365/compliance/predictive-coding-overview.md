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
description: Il nuovo modulo di codifica predittiva in Advanced eDiscovery utilizza l'apprendimento automatico per analizzare i documenti in un set di revisione per prevedere quali documenti sono rilevanti per il caso o l'indagine.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382974"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a>Modulo di codifica predittiva per Advanced eDiscovery (anteprima)

Utilizzando il nuovo modulo di codifica predittiva in Advanced eDiscovery, è possibile creare e creare un modello per assegnare priorità alla revisione dei documenti a partire dai documenti più rilevanti. Per iniziare, è possibile creare un modello, etichettare fino a 50 documenti e quindi filtrare i documenti in base ai punteggi di previsione del modello per esaminare i documenti non rilevanti.

Ecco una breve panoramica del flusso di lavoro:

1. Aprire il modulo di codifica predittiva in un set di revisioni.

   ![Fare clic sull'elenco a discesa Analizza in una recensione per passare al modulo di codifica predittiva](..\media\PredictiveCoding1.png)

2. Nella pagina **Modelli di codifica predittiva** fare clic su **Nuovo modello** per creare un nuovo modello di codifica predittiva.

   ![Creare un nuovo modello](..\media\PredictiveCoding2.png)

3. Etichettare almeno 50 documenti come **rilevanti** o **non rilevanti.** Questa etichettatura viene utilizzata per eseguire il training del sistema.

   ![Etichettare i documenti come rilevanti o non rilevanti per la formazione del sistema](..\media\PredictiveCoding3.png)

4. Applica il **filtro Punteggio previsione** per il modello al set di recensioni. Per eseguire l'operazione:

   1. Nell'insieme di revisioni fare clic su **Filtri.**
   2. Nella pagina **a** comparsa Filtri espandi la **sezione Analytics/ML** e quindi seleziona la casella di controllo **Punteggio** di previsione per il modello che vuoi applicare.
   3. Nel filtro **Punteggio di previsione** specificare un punteggio di previsione. Il filtro visualizza i documenti nel set di revisione che corrispondono al punteggio di previsione.

      ![Specificare un punteggio di previsione per filtrare i documenti](..\media\PredictiveCoding4.png)

5. Monitorare le prestazioni, lo stato e la stabilità del modello.

   ![Monitorare le prestazioni, lo stato e la stabilità del modello](..\media\PredictiveCoding5.png)
