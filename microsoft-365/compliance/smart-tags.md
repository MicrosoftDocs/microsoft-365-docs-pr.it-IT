---
title: Configurare gli smart tag in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Gli smart tag consentono di applicare le funzionalità di machine learning durante la revisione del contenuto in Advanced eDiscovery caso. Utilizzare i gruppi di smart tag per visualizzare i risultati dei modelli di rilevamento dell'apprendimento automatico, ad esempio il modello dei privilegi avvocato-client.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081083"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>Configurare gli smart tag in Advanced eDiscovery

Le funzionalità di machine learning (ML) in Advanced eDiscovery consentono di rendere il processo decisionale più efficiente quando si esaminano i documenti dei casi in un set di recensioni. Gli smart tag consentono di portare le funzionalità ML in cui vengono registrate le decisioni: quando si contrassegnano i documenti durante la revisione. Quando si crea un gruppo di smart tag, le decisioni che sono il risultato del modello di ML associato al gruppo di smart tag vengono visualizzate in linea con i tag nel gruppo di tag. Ciò consente di visualizzare le ML dei risultati in linea durante la revisione di documenti specifici.

## <a name="how-to-set-up-a-smart-tag-group"></a>Come configurare un gruppo di smart tag

1. In un set di recensioni, fare clic **su Gestisci set di revisioni** e quindi su Gestisci **tag.**

2. Fare **clic su Aggiungi gruppo di tag** e quindi selezionare Aggiungi gruppo di smart **tag.**

3. Selezionare il ML che si desidera associare al gruppo di tag.
    
   In questo modo vengono creati un gruppo di tag *e N* tag figlio, dove *N* è il numero di possibili output del modello. Ad esempio, il [modello di rilevamento dei privilegi avvocato-client](attorney-privilege-detection.md) ha due possibili output: 

   - **Positivo:** consente di contrassegnare i documenti che contengono contenuto con privilegi avvocato-client.
   
   - **Negativo:** consente di contrassegnare i documenti che non contengono contenuto con privilegi avvocato-client.
    
    Se si seleziona questo modello, viene creato un gruppo di tag con due tag figlio (un tag figlio denominato **Positive** e l'altro denominato **Negative)** per il set di revisioni. In questo esempio, ogni tag figlio corrisponde a uno dei possibili output del modello di rilevamento dei privilegi avvocato-client.

4. Facoltativamente, è possibile rinominare il gruppo di tag e i tag figlio. Ad esempio, puoi rinominare il tag **Positive** in **Privileged** e il tag **Negative** in **Not privileged**.

## <a name="how-to-use-smart-tags"></a>Come usare gli smart tag

Durante la revisione di un documento, i risultati del modello vengono visualizzati accanto al tag figlio appropriato. Ad esempio, se si dispone di un gruppo di smart tag per il rilevamento dei privilegi avvocato-client e si esamina un documento potenzialmente privilegiato, il motivo di tale conclusione viene visualizzato accanto al tag appropriato. È importante notare che il tag non viene applicato automaticamente al documento. Il revisore prende la decisione su come contrassegnare il documento.
