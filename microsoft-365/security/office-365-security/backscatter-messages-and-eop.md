---
title: Backscatter e EOP
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
description: Backscatter è un messaggio di rimbalzo automatico inviato agli indirizzi di posta elettronica contraffatti. Il DNSBL Backscatterer identifica i server che inviano messaggi di backscatter (che potrebbero includere molte fonti di posta elettronica legittime). Poiché non si tratta di un elenco di spammer, non si tenta di rimuovere noi stessi dal Backscatterer DNSBL.
ms.openlocfilehash: 22eeec29722cf1742e096234aad95b9f6ee407e2
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895406"
---
# <a name="backscatter-and-eop"></a>Backscatter e EOP

*Backscatter* è rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo) ricevuti per i messaggi che non sono stati inviati. Gli spammer falsificano l'indirizzo da: dei messaggi e spesso usano indirizzi di posta elettronica reali per dare credibilità ai propri messaggi. Pertanto, quando gli spammer inviano inevitabilmente messaggi a destinatari inesistenti (la posta indesiderata è un'operazione di alto volume), il server di posta elettronica di destinazione viene sostanzialmente indotto a restituire il messaggio non recapitabile in un rapporto di mancato recapito al mittente falsificato nell'indirizzo from:.

Exchange Online Protection (EOP) fa ogni sforzo per identificare e eliminare automaticamente i messaggi da fonti dubbie senza generare un rapporto di mancato recapito. Tuttavia, in base al volume di messaggi di posta elettronica che scorre attraverso il servizio, c'è sempre la possibilità che EOP invierà involontariamente backscatter.

Backscatterer.org gestisce un elenco di indirizzi bloccati (noto anche come elenco di indirizzi DNS o DNSBL) dei server di posta elettronica responsabili dell'invio di backscatter e i server di EOP potrebbero essere presenti in questo elenco. Tuttavia, non si tenta di rimuovere noi stessi dall'elenco dei blocchi di Backscatterer.org perché non si tratta di un elenco di spammer (per loro stessa ammissione).

> [!TIP]
> Il sito Web Backscatter.org<http://www.backscatterer.org/?target=usage>() consiglia di utilizzare il servizio per controllare la posta elettronica in arrivo in modalità provvisoria invece della modalità rifiuto (i servizi di posta elettronica di grandi dimensioni quasi sempre inviano un backscatter).
