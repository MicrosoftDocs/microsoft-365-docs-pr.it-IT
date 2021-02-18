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
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Trovare le risposte alle domande più comuni sui messaggi accodati, rinviati o restituiti al mittente durante il processo di filtro di Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e54a260a70a9c68a94412243308bffe60d989e99
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289700"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="43a1d-103">Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="43a1d-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="43a1d-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="43a1d-104">**Applies to**</span></span>
- [<span data-ttu-id="43a1d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="43a1d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="43a1d-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="43a1d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="43a1d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43a1d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="43a1d-108">In questo argomento vengono fornite le risposte alle domande frequenti sui messaggi accodati, rinviati o restituiti al mittente durante il processo di filtro di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="43a1d-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="43a1d-109">Perché i messaggi vengono accodati?</span><span class="sxs-lookup"><span data-stu-id="43a1d-109">Why is mail queuing?</span></span>

<span data-ttu-id="43a1d-110">I messaggi vengono accodati o differiti se il servizio non è in grado di creare una connessione al server del destinatario per il recapito dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="43a1d-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="43a1d-111">I messaggi non verranno differiti se viene restituito un errore 500 dalla rete dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="43a1d-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="43a1d-112">Come viene differito un messaggio?</span><span class="sxs-lookup"><span data-stu-id="43a1d-112">How does a message become deferred?</span></span>

<span data-ttu-id="43a1d-113">I messaggi vengono mantenuti quando non è possibile eseguire una connessione al server dei destinatari e il server del destinatario restituisce un "errore temporaneo", ad esempio un timeout di connessione, una connessione rifiutata o un errore 400.</span><span class="sxs-lookup"><span data-stu-id="43a1d-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="43a1d-114">Se si verifica un errore permanente, ad esempio un errore 500, il messaggio verrà restituito al mittente.</span><span class="sxs-lookup"><span data-stu-id="43a1d-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="43a1d-115">Per quanto tempo un messaggio rimane in coda e qual è l'intervallo tra tentativi?</span><span class="sxs-lookup"><span data-stu-id="43a1d-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="43a1d-116">I messaggi in differimento rimarranno nelle code per 1 giorno.</span><span class="sxs-lookup"><span data-stu-id="43a1d-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="43a1d-117">I tentativi di invio dei messaggi variano in base all'errore ricevuto dal sistema di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="43a1d-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="43a1d-118">I primi rinvii sono di 15 minuti o meno, con tentativi successivi (oltre la successiva mezza decina) che aumentano l'intervallo su più tentativi fino a un massimo di 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="43a1d-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="43a1d-119">L'espansione della durata dell'intervallo è dinamica, prendendo in considerazione più variabili come le dimensioni delle code e la priorità dei messaggi interni.</span><span class="sxs-lookup"><span data-stu-id="43a1d-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="43a1d-120">In base, è 15 minuti (o meno) per iniziare, quindi espandersi da lì nelle prossime ore a 60 min max.</span><span class="sxs-lookup"><span data-stu-id="43a1d-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="43a1d-121">Dopo il ripristino del server di posta elettronica, come vengono distribuiti i messaggi in coda?</span><span class="sxs-lookup"><span data-stu-id="43a1d-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="43a1d-122">Dopo il ripristino del server di posta elettronica, tutti i messaggi accodati sono automaticamente elaborati nell'ordine in cui sono stati ricevuti e vengono accodati quando il server non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="43a1d-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
