---
title: Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: In questo argomento vengono fornite le risposte alle domande frequenti sui messaggi restituiti al mittente, differiti e in coda durante la procedura di filtraggio in Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: e517fbf06da5bdea18f7c7af2733dbc8c359cc80
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441493"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in Exchange Online Protection

In questo argomento vengono fornite le risposte alle domande frequenti sui messaggi restituiti al mittente, differiti e in coda durante la procedura di filtraggio in Microsoft Exchange Online Protection (EOP).

**D. Perché i messaggi vengono accodati?**

R. I messaggi vengono accodati o differiti se il servizio non è in grado di creare una connessione al server del destinatario per il recapito dei messaggi. I messaggi non verranno differiti se viene restituito un errore 500 dalla rete dei destinatari.

**D. Come viene differito un messaggio?**

R. I messaggi vengono mantenuti quando non è possibile eseguire una connessione al server dei destinatari e il server del destinatario restituisce un "errore temporaneo", ad esempio un timeout di connessione, una connessione rifiutata o un errore 400. Se si verifica un errore permanente, ad esempio un errore 500, il messaggio verrà restituito al mittente.

**D. Per quanto tempo un messaggio rimane in coda e qual è l'intervallo tra tentativi?**

R. I messaggi in differimento rimarranno nelle code per 1 giorno. I tentativi di invio dei messaggi variano in base all'errore ricevuto dal sistema di posta elettronica del destinatario. I primi deferimenti sono di 15 minuti o meno, con i successivi tentativi (nelle prossime mezze dozzine) che aumentano l'intervallo su più tentativi fino a un massimo di 60 minuti. L'espansione della durata dell'intervallo è dinamica, tenendo in considerazione più variabili come le dimensioni delle code e la priorità dei messaggi interni. In Basic, è 15 minuti (o meno) per iniziare, quindi espandersi da lì nelle prossime ore fino a 60 mins max.

**D. Dopo il ripristino del server di posta elettronica, come vengono distribuiti i messaggi in coda?**

R. Dopo il ripristino del server di posta elettronica, tutti i messaggi accodati sono automaticamente elaborati nell'ordine in cui sono stati ricevuti e vengono accodati quando il server non è più disponibile.  
