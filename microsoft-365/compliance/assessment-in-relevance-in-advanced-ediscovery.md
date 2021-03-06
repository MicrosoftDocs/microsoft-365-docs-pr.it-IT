---
title: Comprendere la valutazione della pertinenza in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Ottieni una panoramica della fase di valutazione e del suo ruolo nel determinare la ricchezza dei problemi durante la formazione sulla pertinenza in Microsoft 365 Advanced eDiscovery.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769277"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Valutazione nel modulo Pertinenza in Advanced eDiscovery
  
Advanced eDiscovery consente la valutazione anticipata, ad esempio per i problemi definiti e i dati importati per un caso. Advanced eDiscovery consente all'esperto di prendere decisioni su un approccio adottato e di applicarlo al progetto di revisione dei documenti.
  
## <a name="understanding-assessment"></a>Informazioni sulla valutazione

In Valutazione, l'esperto esamina un insieme casuale di almeno 500 file, che vengono utilizzati per determinare la ricchezza dei problemi e per produrre statistiche che riflettono i risultati della formazione. La valutazione ha esito positivo quando vengono trovati file pertinenti sufficienti per raggiungere un livello statistico che consente di Advanced eDiscovery Pertinenza per fornire statistiche accurate e determinare in modo efficace il punto di stabilizzazione nel processo di formazione. 
  
Maggiore è il numero di file rilevanti nel set di valutazioni, più accurate sono le statistiche e l'efficacia dell'algoritmo di stabilità. Il numero di file pertinenti all'interno dei file di valutazione dipende dalla ricchezza del problema. Richness è la percentuale stimata di file rilevanti nel set rilevante per un problema. I problemi con una maggiore ricchezza raggiungeranno un numero più elevato di file rilevanti più rapidamente rispetto ai problemi con una minore ricchezza. I problemi con una ricchezza estremamente bassa (ad esempio, il 2% o meno) richiederanno un set di valutazione molto grande per raggiungere un numero significativo di file rilevanti.
  
Le statistiche, presentate nelle schede Traccia e Decidi durante l'addestramento e dopo il calcolo batch, includono stime del richiamo per diversi set di revisione. Nelle statistiche, le stime basate su un set di campioni (in questo caso i file di valutazione) includono il margine di errore e il livello di probabilità di tale margine di errore. Ad esempio, il richiamo stimato dell'80% potrebbe avere un margine di errore maggiore o inferiore al 5% con un livello di probabilità del 95%. Ciò significa che il richiamo stimato è in realtà del 75%-85% e questa stima ha una probabilità del 95%. Più grande è il set di valutazioni, il margine di errore diventa più piccolo e le statistiche sono più accurate. 
  
Dopo che l'esperto ha verificato un set di valutazione iniziale di 500 file, la rilevanza può determinare il margine di errore corrente dei valori di richiamo. La pertinenza consiglia inoltre un margine di errore predefinito da raggiungere per ottimizzare il set di valutazione. Di seguito vengono descritti alcuni esempi:
  
- Se il set di valutazioni ha già restituito un margine di errore maggiore o inferiore al 10%, Pertinenza consiglia di passare alla formazione (non è necessaria alcuna revisione di valutazione aggiuntiva). 

- Se il set di valutazioni ha restituito un margine di errore maggiore o minore del 13%, la pertinenza potrebbe consigliare la revisione di un altro set di file di valutazione per raggiungere un margine inferiore. 

- Se la ricchezza è estremamente bassa, la pertinenza potrebbe consigliare di interrompere la valutazione anche se il margine di errore è elevato (rendendo le statistiche poco pratiche), perché il set di valutazione necessario per raggiungere un margine di errore utile è troppo grande.

Ogni problema ha la propria ricchezza, il margine di errore corrente e, di conseguenza, il numero stimato di file di valutazione aggiuntivi. Il set di valutazione successivo viene creato in base al numero massimo di file (fino a 1.000 in un singolo set).
  
Puoi accettare i suggerimenti per la pertinenza o modificare il margine di errore corrente in base alle tue esigenze. Il margine di errore corrente predefinito viene determinato per il richiamo su un valore uguale o superiore al 75%.
  
> [!NOTE]
> La fase di valutazione può essere ignorata, nella scheda Traccia di pertinenza nella visualizzazione espansa per un problema, deselezionando la casella di controllo Valutazione per problema e quindi per "tutti i problemi". **\>**  Di conseguenza, non ci saranno statistiche per questo problema. La cancellazione **della casella di** controllo Valutazione può essere eseguita solo prima dell'esecuzione della valutazione. Se in un caso sono presenti più problemi, la valutazione viene ignorata solo se la casella di controllo è deselezionata per ogni problema.
