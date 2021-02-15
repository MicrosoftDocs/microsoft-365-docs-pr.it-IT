---
title: Decisione basata sui risultati di Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Informazioni su come la scheda Decide in Advanced eDiscovery fornisce dati che consentono di determinare le dimensioni corrette del set di file del caso da rivedere.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769151"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>Decisioni basate sui risultati di pertinenza in Advanced eDiscovery
  
Nel modulo Rilevanza in Advanced eDiscovery, la scheda Decide fornisce informazioni aggiuntive per la visualizzazione e l'utilizzo delle statistiche di supporto decisionale per determinare le dimensioni del set di file del caso da rivedere.
  
## <a name="using-the-decide-tab"></a>Uso della scheda Decide

![Decisione di pertinenza](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
Questa scheda include i componenti seguenti:
  
- **Problema:** da qui è possibile selezionare l'emissione di interesse dall'elenco.

- **Rapporto revisione-richiamo**: confronti della revisione di Advanced eDiscovery in base ai punteggi di pertinenza. Il punto di taglio nel grafico rappresenta la percentuale di file da esaminare, mappata a un punteggio di pertinenza. Viene usato nella fase di test di pertinenza e come soglia di esportazione per il culling. Il punto di taglio predefinito, per il numero di file da esaminare, è il punto in cui il bilanciamento tra richiamo e precisione è ottimale. Il punto di taglio effettivo deve essere determinato dall'utente in base agli obiettivi e al compromesso dei costi (%review) e del rischio (%recall). Usando il dispositivo di scorrimento, puoi regolare il punto di taglio e vedere l'effetto sul grafico e sui parametri, quando regola la percentuale di file rilevanti da recuperare e prima di convalidare una decisione.

- **Parametri**: i parametri Review, Recall, Next relevant e Total cost sono statistiche calcolate cumulative relative alla revisione impostata in relazione alla raccolta per l'intero caso. Le definizioni per questi parametri sono le seguenti:

  - **Review:** percentuale di file da esaminare in base a questa riduzione.

  - **Richiamo:** percentuale di file rilevanti nel set da rivedere.

  - **Successivo pertinente:** Costo per la revisione e l'identificazione di un altro file rilevante che non è attualmente presente nel set di recensioni.

  - **Costo totale:** costo per la revisione di questa percentuale dei file dei casi. Le impostazioni dei parametri dei costi possono essere impostate dal responsabile del caso.

  - **Distribuzione in base al punteggio di** pertinenza: i file nella visualizzazione grigio scuro a sinistra sono al di sotto del punteggio di pertinenza. Una descrizione comando visualizza il punteggio di pertinenza e la percentuale correlata di file nel set di file da rivedere in relazione al totale dei file.

Nel riquadro **dettagli** espanso vengono visualizzati altri dettagli. I file nelle figure della raccolta non includono file vuoti o nebulosi. Le figure dei file di famiglia rappresentano i file non caricati in Rilevanza, ma ancora conteggiati come parte della famiglia.
