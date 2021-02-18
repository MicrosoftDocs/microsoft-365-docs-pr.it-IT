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
# <a name="backscatter-in-eop"></a>Backscatter in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*I rapporti di mancato* recapito (noti anche come rapporti di mancato recapito o notifiche di mancato recapito) ricevuti per i messaggi che non sono stati inviati. Gli spammer falsificano (spoofing) l'indirizzo da: dei loro messaggi e spesso utilizzano indirizzi di posta elettronica reali per dare credibilità ai loro messaggi. Pertanto, quando gli spammer inviano inevitabilmente messaggi a destinatari inesistenti (la posta indesiderata è un'operazione di volume elevato), il server di posta elettronica di destinazione viene essenzialmente in ingannato a restituire il messaggio non recapitabile in un rapporto di mancato recapito al mittente contraffatto nell'indirizzo Da:.

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, EOP fa tutto il possibile per identificare e rilasciare automaticamente i messaggi da origini dubbie senza generare un rapporto di mancato recapito. Tuttavia, in base all'elevato volume di posta elettronica che attraversa il servizio, esiste sempre la possibilità che EOP invii inavvio posta indesiderata.

Backscatterer.org gestisce un elenco di indirizzi bloccati (noto anche come elenco di indirizzi dns bloccati o DNSBL) di server di posta elettronica responsabili dell'invio di posta indesiderata in uscita e i server EOP potrebbero essere visualizzati in questo elenco. Tuttavia, non si tenta di rimuoversi dall'Backscatterer.org di blocco perché non è un elenco di spammer (per ammissione).

> [!TIP]
> Il Backscatter.org web ( ) consiglia di utilizzare il servizio per controllare la posta elettronica in arrivo in modalità provvisoria anziché in modalità rifiutata (i servizi di posta elettronica di grandi dimensioni inviano quasi sempre posta indesiderata <http://www.backscatterer.org/?target=usage> in uscita).
