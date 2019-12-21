---
title: Posta indesiderata costituita da falsi rapporti di mancato recapito ed EOP
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
ms.openlocfilehash: f6e8398565837f7a380c8a6a5c4cd8de422cc215
ms.sourcegitcommit: ca4ce9e8c7e4b433608cd059857740ffd5a472c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2019
ms.locfileid: "40840165"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="79589-105">Posta indesiderata costituita da falsi rapporti di mancato recapito ed Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="79589-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="79589-106">*I messaggi backscatter* sono rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo) ricevuti per i messaggi che non sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="79589-106">*Backscatter messages* are non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="79589-107">Gli spammer falsificano l'indirizzo da: dei messaggi e spesso usano indirizzi di posta elettronica reali per dare credibilità ai propri messaggi.</span><span class="sxs-lookup"><span data-stu-id="79589-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="79589-108">Pertanto, quando si inviano inevitabilmente messaggi a destinatari inesistenti (la posta indesiderata è un'operazione di alto volume), il server di posta elettronica di destinazione potrebbe rispondere in modo doveroso con un rapporto di mancato recapito, che viene inviato al mittente contraffatto nell'indirizzo from:.</span><span class="sxs-lookup"><span data-stu-id="79589-108">So, when they inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server might dutifully respond with an NDR, which is sent to the forged sender in the From: address.</span></span>

<span data-ttu-id="79589-109">Exchange Online Protection (EOP) fa ogni sforzo per identificare e eliminare automaticamente i messaggi da fonti dubbie senza generare un rapporto di mancato recapito.</span><span class="sxs-lookup"><span data-stu-id="79589-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="79589-110">Tuttavia, in base al volume di posta elettronica che scorre attraverso il servizio, c'è sempre la possibilità che EOP invierà accidentalmente messaggi backscatter.</span><span class="sxs-lookup"><span data-stu-id="79589-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter messages.</span></span>

<span data-ttu-id="79589-111">Backscatterer.org gestisce un elenco di indirizzi bloccati (noto anche come elenco di indirizzi DNS o DNSBL) dei server di posta elettronica responsabili dell'invio dei messaggi backscatter e i server di EOP potrebbero essere presenti in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="79589-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter messages, and EOP servers might appear on this list.</span></span> <span data-ttu-id="79589-112">Tuttavia, non si tenta di rimuovere noi stessi dall'elenco dei blocchi di Backscatterer.org perché non si tratta di un elenco di spammer (per loro stessa ammissione).</span><span class="sxs-lookup"><span data-stu-id="79589-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="79589-113">Secondo il backscatter. o il sito Web`http://www.backscatterer.org/?target=usage`(), si consiglia di utilizzare il servizio per controllare la posta elettronica in arrivo in modalità provvisoria invece che in modalità rifiuto (i servizi di posta elettronica di grandi dimensioni quasi sempre inviano messaggi backscatter).</span><span class="sxs-lookup"><span data-stu-id="79589-113">According to the Backscatter.or website (`http://www.backscatterer.org/?target=usage`), they recommend using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter messages).</span></span>
