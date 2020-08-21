---
title: Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Trovare le risposte alle domande più frequenti sui messaggi che sono stati accodati, posticipati o rimbalzati durante il processo di filtro di Exchange Online Protection (EOP).
ms.openlocfilehash: 76fe08f3a83321b6c0549dae5f1382ead5f0b3ae
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827750"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="1d768-103">Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1d768-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="1d768-104">In questo argomento vengono fornite le risposte alle domande frequenti sui messaggi che sono stati accodati, posticipati o rimbalzati durante il processo di filtro di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="1d768-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="1d768-105">Perché i messaggi vengono accodati?</span><span class="sxs-lookup"><span data-stu-id="1d768-105">Why is mail queuing?</span></span>

<span data-ttu-id="1d768-106">I messaggi vengono accodati o differiti se il servizio non è in grado di creare una connessione al server del destinatario per il recapito dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="1d768-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="1d768-107">I messaggi non verranno differiti se viene restituito un errore 500 dalla rete dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="1d768-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="1d768-108">Come viene differito un messaggio?</span><span class="sxs-lookup"><span data-stu-id="1d768-108">How does a message become deferred?</span></span>

<span data-ttu-id="1d768-109">I messaggi vengono mantenuti quando non è possibile eseguire una connessione al server dei destinatari e il server del destinatario restituisce un "errore temporaneo", ad esempio un timeout di connessione, una connessione rifiutata o un errore 400.</span><span class="sxs-lookup"><span data-stu-id="1d768-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="1d768-110">Se si verifica un errore permanente, ad esempio un errore 500, il messaggio verrà restituito al mittente.</span><span class="sxs-lookup"><span data-stu-id="1d768-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="1d768-111">Per quanto tempo un messaggio rimane in coda e qual è l'intervallo tra tentativi?</span><span class="sxs-lookup"><span data-stu-id="1d768-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="1d768-112">I messaggi in differimento rimarranno nelle code per 1 giorno.</span><span class="sxs-lookup"><span data-stu-id="1d768-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="1d768-113">I tentativi di invio dei messaggi variano in base all'errore ricevuto dal sistema di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="1d768-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="1d768-114">I primi deferimenti sono di 15 minuti o meno, con i successivi tentativi (nelle prossime mezze dozzine) che aumentano l'intervallo su più tentativi fino a un massimo di 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="1d768-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="1d768-115">L'espansione della durata dell'intervallo è dinamica, tenendo in considerazione più variabili come le dimensioni delle code e la priorità dei messaggi interni.</span><span class="sxs-lookup"><span data-stu-id="1d768-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="1d768-116">In Basic, è 15 minuti (o meno) per iniziare, quindi espandersi da lì nelle prossime ore fino a 60 mins max.</span><span class="sxs-lookup"><span data-stu-id="1d768-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="1d768-117">Dopo il ripristino del server di posta elettronica, come vengono distribuiti i messaggi in coda?</span><span class="sxs-lookup"><span data-stu-id="1d768-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="1d768-118">Dopo il ripristino del server di posta elettronica, tutti i messaggi accodati sono automaticamente elaborati nell'ordine in cui sono stati ricevuti e vengono accodati quando il server non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="1d768-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
