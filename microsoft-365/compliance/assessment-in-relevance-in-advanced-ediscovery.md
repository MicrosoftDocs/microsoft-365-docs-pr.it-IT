---
title: Comprendere la valutazione in rilevanza in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Ottenere una panoramica della fase di valutazione e del relativo ruolo per determinare la ricchezza dei problemi durante la formazione di pertinenza in Advanced eDiscovery.
ms.openlocfilehash: e1e090a9b3aceecad8451657d7a8e5d26e92ed6f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636154"
---
# <a name="understand-assessment-in-relevance-in-advanced-ediscovery-classic"></a>Comprendere la valutazione in rilevanza in Advanced eDiscovery (Classic)

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Advanced eDiscovery consente di valutare precocemente, ad esempio, i problemi definiti e i dati importati per un caso. Advanced eDiscovery consente all'esperto di prendere decisioni su un approccio adottato e di applicare queste decisioni al progetto di revisione del documento.
  
## <a name="understanding-assessment"></a>Informazioni sulla valutazione

In valutazione, l'esperto esamina un insieme casuale di almeno 500 file, che vengono utilizzati per determinare la ricchezza dei problemi e produrre statistiche che riflettono i risultati della formazione. La valutazione ha esito positivo quando sono stati trovati file rilevanti sufficienti per raggiungere un livello statistico che consentirà di rendere più efficace la pertinenza di eDiscovery per fornire statistiche accurate e determinare efficacemente il punto di stabilizzazione nel processo di formazione. 
  
Maggiore è il numero di file rilevanti nel set di valutazione, maggiore è la precisione delle statistiche e l'efficacia dell'algoritmo di stabilità. Il numero di file rilevanti all'interno dei file di valutazione dipende dalla ricchezza del problema. La ricchezza è la percentuale stimata di file rilevanti nel set pertinente a un problema. I problemi con una ricchezza maggiore raggiungeranno un numero maggiore di file rilevanti più rapidamente rispetto ai problemi con una ricchezza più bassa. I problemi con una ricchezza estremamente bassa (ad esempio, il 2% o meno) richiedono un set di valutazioni molto esteso per raggiungere un numero significativo di file rilevanti.
  
Le statistiche, presentate nelle schede traccia e decidi durante l'allenamento e dopo il calcolo del batch, includono stime di richiamo per diversi insiemi di revisione. In statistica, le stime basate su un set di esempio (in questo caso, i file di valutazione) includono il margine di errore e il livello di confidenza del margine di errore. Ad esempio, il richiamo stimato del 80% potrebbe avere un margine di errore pari o meno al 5% con un livello di confidenza pari al 95%. Questo significa che il richiamo stimato è effettivamente 75%-85% e questa stima ha 95% di confidenza. Maggiore è il set di valutazione, il margine di errore diventa più piccolo e le statistiche sono più accurate. 
  
Dopo che l'esperto ha esaminato un gruppo di valutazione iniziale di 500 file, la pertinenza può determinare il margine di errore corrente dei valori di richiamo. Pertinenza consiglierà anche un margine di errore predefinito da raggiungere per ottimizzare il set di valutazione. Ecco alcuni esempi:
  
- Se il set di valutazione ha già restituito un margine di errore pari o meno al 10%, la pertinenza consiglierà di passare alla formazione (non è necessaria alcuna revisione di valutazione supplementare). 
    
- Se il set di valutazione ha restituito un margine di errore più o meno 13%, la pertinenza potrebbe consigliare la revisione di un altro gruppo di file di valutazione per raggiungere un margine inferiore. 
    
- Se la ricchezza è estremamente bassa, la pertinenza potrebbe consigliare l'interruzione della valutazione anche se il margine di errore è di grandi dimensioni (per rendere impraticabile la statistica), in quanto il set di valutazione necessario per raggiungere un margine di errore utile è troppo elevato.
    
Ogni problema ha la propria ricchezza, il margine di errore corrente e, di conseguenza, il numero stimato di file di valutazione aggiuntivi. Il set di valutazione successivo viene creato in base al numero massimo di file (fino a 1.000 in un solo set).
  
È possibile accettare le indicazioni relative alla pertinenza o regolare il margine di errore corrente in base alle proprie esigenze. Il margine di errore corrente predefinito è determinato per il richiamo pari o superiori a 75%.
  
> [!NOTE]
> La fase di valutazione può essere ignorata, nella scheda ** \> Tracking pertinenza** della visualizzazione espansa per un problema, deselezionando la casella di controllo **valutazione** per problema e quindi per "tutti i problemi". Tuttavia, di conseguenza, non saranno disponibili statistiche per questo problema. > deselezionando la casella di controllo **valutazione** può essere eseguita solo prima di eseguire la valutazione. Se in un caso esistono più problemi, la valutazione viene ignorata solo se la casella di controllo è deselezionata per ogni problema. 
  
## <a name="see-also"></a>Vedere anche

[Advanced eDiscovery (classico)](office-365-advanced-ediscovery.md)
  
[Tagging e valutazione](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Formazione di tagging e pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Verifica dell'analisi della pertinenza](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidere in base ai risultati](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Verifica dell'analisi della pertinenza](test-relevance-analysis-in-advanced-ediscovery.md)

