---
title: Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP
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
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Trovare le risposte alle domande più frequenti sui messaggi che sono stati accodati, posticipati o rimbalzati durante il processo di filtro di Exchange Online Protection (EOP).
ms.openlocfilehash: 38e72a04e855862c621bd2b170c11407e0d22af3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206593"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in Exchange Online Protection

In questo argomento vengono fornite le risposte alle domande frequenti sui messaggi che sono stati accodati, posticipati o rimbalzati durante il processo di filtro di Exchange Online Protection (EOP).

## <a name="why-is-mail-queuing"></a>Perché i messaggi vengono accodati?

I messaggi vengono accodati o differiti se il servizio non è in grado di creare una connessione al server del destinatario per il recapito dei messaggi. I messaggi non verranno differiti se viene restituito un errore 500 dalla rete dei destinatari.

## <a name="how-does-a-message-become-deferred"></a>Come viene differito un messaggio?

I messaggi vengono mantenuti quando non è possibile eseguire una connessione al server dei destinatari e il server del destinatario restituisce un "errore temporaneo", ad esempio un timeout di connessione, una connessione rifiutata o un errore 400. Se si verifica un errore permanente, ad esempio un errore 500, il messaggio verrà restituito al mittente.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Per quanto tempo un messaggio rimane in coda e qual è l'intervallo tra tentativi?

I messaggi in differimento rimarranno nelle code per 1 giorno. I tentativi di invio dei messaggi variano in base all'errore ricevuto dal sistema di posta elettronica del destinatario. I primi deferimenti sono di 15 minuti o meno, con i successivi tentativi (nelle prossime mezze dozzine) che aumentano l'intervallo su più tentativi fino a un massimo di 60 minuti. L'espansione della durata dell'intervallo è dinamica, tenendo in considerazione più variabili come le dimensioni delle code e la priorità dei messaggi interni. In Basic, è 15 minuti (o meno) per iniziare, quindi espandersi da lì nelle prossime ore fino a 60 mins max.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Dopo il ripristino del server di posta elettronica, come vengono distribuiti i messaggi in coda?

Dopo il ripristino del server di posta elettronica, tutti i messaggi accodati sono automaticamente elaborati nell'ordine in cui sono stati ricevuti e vengono accodati quando il server non è più disponibile.
