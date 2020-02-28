---
title: Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: I messaggi backscatter sono messaggi di rimbalzo automatici inviati agli indirizzi di posta elettronica contraffatti. Il DNSBL Backscatterer identifica i server che inviano messaggi di backscatter (che potrebbero includere molte fonti di posta elettronica legittime). Poiché non si tratta di un elenco di spammer, non si tenta di rimuovere noi stessi dal Backscatterer DNSBL.
ms.openlocfilehash: 20ed828680dd20e82819730e6dcd509b896d8616
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "42313811"
---
# <a name="backscatter-messages-and-eop"></a>Posta indesiderata costituita da falsi rapporti di mancato recapito ed Exchange Online Protection

*I messaggi backscatter* sono rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo) ricevuti per i messaggi che non sono stati inviati. Gli spammer falsificano l'indirizzo da: dei messaggi e spesso usano indirizzi di posta elettronica reali per dare credibilità ai propri messaggi. Pertanto, quando uno spammer Invia inevitabilmente messaggi a destinatari inesistenti (la posta indesiderata è un'operazione di alto volume), il server di posta elettronica di destinazione restituirà probabilmente il messaggio non recapitabile in un rapporto di mancato recapito, che verrà inviato al mittente falsificato nell'indirizzo from:.

Exchange Online Protection (EOP) fa ogni sforzo per identificare e eliminare automaticamente i messaggi da fonti dubbie senza generare un rapporto di mancato recapito. Tuttavia, in base al volume di posta elettronica che scorre attraverso il servizio, c'è sempre la possibilità che EOP invierà accidentalmente messaggi backscatter.

Backscatterer.org gestisce un elenco di indirizzi bloccati (noto anche come elenco di indirizzi DNS o DNSBL) dei server di posta elettronica responsabili dell'invio dei messaggi backscatter e i server di EOP potrebbero essere presenti in questo elenco. Tuttavia, non si tenta di rimuovere noi stessi dall'elenco dei blocchi di Backscatterer.org perché non si tratta di un elenco di spammer (per loro stessa ammissione).

> [!TIP]
> Il sito Web Backscatter.org<http://www.backscatterer.org/?target=usage>() consiglia di utilizzare il servizio per controllare la posta elettronica in arrivo in modalità provvisoria invece della modalità rifiuto (i servizi di posta elettronica di grandi dimensioni inviano quasi sempre alcuni messaggi backscatter).
