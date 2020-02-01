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
description: Gli smart tag consentono di applicare le funzionalità di apprendimento automatico quando si esaminano i contenuti in un caso avanzato di eDiscovery. Utilizzare i gruppi di smart tag per visualizzare i risultati dei modelli di rilevamento di apprendimento automatico, ad esempio il modello di privilegio avvocato-client.
ms.openlocfilehash: 9b3e1310baa06f53a3ee1dab5c371fb67d6ab95c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597403"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>Configurare gli smart tag in Advanced eDiscovery

Le funzionalità di apprendimento automatico (ML) in Advanced eDiscovery consentono di rendere il processo decisionale più efficiente quando si esaminano i documenti dei casi in un set di revisione. Gli smart tag rappresentano un modo per portare le funzionalità ML in cui vengono registrate le decisioni: quando si contrassegnano i documenti durante la revisione. Quando si crea un gruppo di smart tag, le decisioni che sono il risultato del modello ML associato al gruppo smart tag vengono visualizzate in linea con i tag del gruppo di tag. Questo consente di visualizzare le informazioni sui risultati in linea quando si stanno esaminando documenti specifici.

## <a name="how-to-set-up-a-smart-tag-group"></a>Come configurare un gruppo di smart tag

1. In un set di Revisione fare clic su **Gestisci Revisione set** e quindi su **Gestisci Tag**.

2. Fare clic su **Aggiungi gruppo Tag** e quindi selezionare **Aggiungi gruppo smart tag**.

3. Selezionare il modello ML che si desidera associare al gruppo di tag.
    
   In questo modo viene creato un gruppo di tag e *n* tag figlio, dove *n* è il numero di output possibili del modello. Ad esempio, il [modello di rilevamento dei privilegi avvocato-client](attorney-privilege-detection.md) ha due possibili output: 

   - **Positivo** : consente di contrassegnare i documenti che contengono contenuto privilegiato avvocato-client.
   
   - **Negativo** : consente di contrassegnare i documenti che non contengono contenuto privilegiato avvocato-client.
    
    Se si seleziona questo modello, viene creato un gruppo di tag con due tag figlio (un tag figlio con nome **positivo** e l'altro **negativo**) per il set di revisione. In questo esempio, ogni tag figlio corrisponde a uno dei possibili output del modello di rilevamento dei privilegi avvocato-client.

4. Facoltativamente, è possibile rinominare il gruppo di tag e i tag figlio. Ad esempio, è possibile rinominare il tag **positivo** su **Privileged** e il tag **negative** su **not Privileged**.

## <a name="how-to-use-smart-tags"></a>Come usare gli smart tag

Quando si esamina un documento, i risultati del modello vengono visualizzati accanto al tag figlio appropriato. Ad esempio, se si dispone di un gruppo di smart tag per il rilevamento dei privilegi avvocato-client e si esamina un documento potenzialmente privilegiato, la causa di tale conclusione viene visualizzata accanto al tag appropriato. È importante tenere presente che il tag non viene applicato automaticamente al documento. Il revisore prende la decisione su come contrassegnare il documento.