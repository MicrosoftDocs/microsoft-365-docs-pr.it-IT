---
title: Backscatter in Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In questo articolo verranno informazioni su Backscatter and Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205114"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="5abc5-103">Backscatter in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5abc5-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5abc5-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="5abc5-104">**Applies to**</span></span>
- [<span data-ttu-id="5abc5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5abc5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5abc5-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="5abc5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5abc5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5abc5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5abc5-108">*Backscatter* sono rapporti di mancato recapito (noti anche come rapporti di mancato recapito o messaggi di mancato recapito) ricevuti per i messaggi che non sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="5abc5-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="5abc5-109">Gli spammer falsificano l'indirizzo Da: dei messaggi, e spesso usano indirizzi di posta elettronica reali per rendere credibili i propri messaggi.</span><span class="sxs-lookup"><span data-stu-id="5abc5-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="5abc5-110">Pertanto, quando gli spammer inviano inevitabilmente messaggi a destinatari inesistenti (la posta indesiderata è un'operazione con un volume elevato), il server di posta elettronica di destinazione viene essenzialmente ingiusto a restituire il messaggio non recapitabile in un rapporto di mancato recapito al mittente contraffatto nell'indirizzo Da:.</span><span class="sxs-lookup"><span data-stu-id="5abc5-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="5abc5-111">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, EOP fa tutto il possibile per identificare e rilasciare automaticamente i messaggi da origini dubbie senza generare un rapporto di mancato recapito.</span><span class="sxs-lookup"><span data-stu-id="5abc5-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="5abc5-112">Tuttavia, in base all'elevato volume di posta elettronica che attraversa il servizio, esiste sempre la possibilità che EOP invii involontariamente backscatter.</span><span class="sxs-lookup"><span data-stu-id="5abc5-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="5abc5-113">Backscatterer.org gestisce un elenco di indirizzi di blocco (noto anche come elenco di blocco DNS o DNSBL) dei server di posta elettronica responsabili dell'invio di backscatter e i server EOP potrebbero comparire in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="5abc5-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="5abc5-114">Tuttavia, non tentiamo di rimuoverci dall'Backscatterer.org di blocco perché non si tratta di un elenco di spammer (per propria ammissione).</span><span class="sxs-lookup"><span data-stu-id="5abc5-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="5abc5-115">Il Backscatter.org web ( ) consiglia di usare il servizio per controllare la posta elettronica in arrivo in modalità provvisoria anziché in modalità rifiutata (i servizi di posta elettronica di grandi dimensioni inviano quasi sempre <http://www.backscatterer.org/?target=usage> backscatter).</span><span class="sxs-lookup"><span data-stu-id="5abc5-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
