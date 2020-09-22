---
title: Backscatter in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni su backscatter e Microsoft Exchange Online Protection (EOP)
ms.openlocfilehash: 2a752c89e2430f24441d14178942b89362736322
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203588"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="70165-103">Backscatter in EOP</span><span class="sxs-lookup"><span data-stu-id="70165-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="70165-104">*Backscatter* è rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo) ricevuti per i messaggi che non sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="70165-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="70165-105">Gli spammer falsificano l'indirizzo da: dei messaggi e spesso usano indirizzi di posta elettronica reali per dare credibilità ai propri messaggi.</span><span class="sxs-lookup"><span data-stu-id="70165-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="70165-106">Pertanto, quando gli spammer inviano inevitabilmente messaggi a destinatari inesistenti (la posta indesiderata è un'operazione di alto volume), il server di posta elettronica di destinazione viene sostanzialmente indotto a restituire il messaggio non recapitabile in un rapporto di mancato recapito al mittente falsificato nell'indirizzo from:.</span><span class="sxs-lookup"><span data-stu-id="70165-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="70165-107">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, EOP compie ogni sforzo per identificare e eliminare automaticamente i messaggi da fonti dubbie senza generare un rapporto di mancato recapito.</span><span class="sxs-lookup"><span data-stu-id="70165-107">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="70165-108">Tuttavia, in base al volume di messaggi di posta elettronica che scorre attraverso il servizio, c'è sempre la possibilità che EOP invierà involontariamente backscatter.</span><span class="sxs-lookup"><span data-stu-id="70165-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="70165-109">Backscatterer.org gestisce un elenco di indirizzi bloccati (noto anche come elenco di indirizzi DNS o DNSBL) dei server di posta elettronica responsabili dell'invio di backscatter e i server di EOP potrebbero essere presenti in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="70165-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="70165-110">Tuttavia, non si tenta di rimuovere noi stessi dall'elenco dei blocchi di Backscatterer.org perché non si tratta di un elenco di spammer (per loro stessa ammissione).</span><span class="sxs-lookup"><span data-stu-id="70165-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="70165-111">Il sito Web Backscatter.org ( <http://www.backscatterer.org/?target=usage> ) consiglia di utilizzare il servizio per controllare la posta elettronica in arrivo in modalità provvisoria invece della modalità rifiuto (i servizi di posta elettronica di grandi dimensioni quasi sempre inviano un backscatter).</span><span class="sxs-lookup"><span data-stu-id="70165-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
