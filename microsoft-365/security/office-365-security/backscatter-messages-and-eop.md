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
description: In questo articolo vengono apprese informazioni su Backscatter and Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286970"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="47883-103">Backscatter in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="47883-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="47883-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="47883-104">**Applies to**</span></span>
- [<span data-ttu-id="47883-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="47883-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="47883-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="47883-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="47883-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47883-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="47883-108">*I rapporti di mancato* recapito (noti anche come rapporti di mancato recapito o notifiche di mancato recapito) ricevuti per i messaggi che non sono stati inviati.</span><span class="sxs-lookup"><span data-stu-id="47883-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="47883-109">Gli spammer falsificano (spoofing) l'indirizzo da: dei loro messaggi e spesso utilizzano indirizzi di posta elettronica reali per dare credibilità ai loro messaggi.</span><span class="sxs-lookup"><span data-stu-id="47883-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="47883-110">Pertanto, quando gli spammer inviano inevitabilmente messaggi a destinatari inesistenti (la posta indesiderata è un'operazione di volume elevato), il server di posta elettronica di destinazione viene essenzialmente in ingannato a restituire il messaggio non recapitabile in un rapporto di mancato recapito al mittente contraffatto nell'indirizzo Da:.</span><span class="sxs-lookup"><span data-stu-id="47883-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="47883-111">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, EOP fa tutto il possibile per identificare e rilasciare automaticamente i messaggi da origini dubbie senza generare un rapporto di mancato recapito.</span><span class="sxs-lookup"><span data-stu-id="47883-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="47883-112">Tuttavia, in base all'elevato volume di posta elettronica che attraversa il servizio, esiste sempre la possibilità che EOP invii inavvio posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="47883-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="47883-113">Backscatterer.org gestisce un elenco di indirizzi bloccati (noto anche come elenco di indirizzi dns bloccati o DNSBL) di server di posta elettronica responsabili dell'invio di posta indesiderata in uscita e i server EOP potrebbero essere visualizzati in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="47883-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="47883-114">Tuttavia, non si tenta di rimuoversi dall'Backscatterer.org di blocco perché non è un elenco di spammer (per ammissione).</span><span class="sxs-lookup"><span data-stu-id="47883-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="47883-115">Il Backscatter.org web ( ) consiglia di utilizzare il servizio per controllare la posta elettronica in arrivo in modalità provvisoria anziché in modalità rifiutata (i servizi di posta elettronica di grandi dimensioni inviano quasi sempre posta indesiderata <http://www.backscatterer.org/?target=usage> in uscita).</span><span class="sxs-lookup"><span data-stu-id="47883-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
