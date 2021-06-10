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
# <a name="backscatter-in-eop"></a>Backscatter in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* sono rapporti di mancato recapito (noti anche come rapporti di mancato recapito o messaggi di mancato recapito) ricevuti per i messaggi che non sono stati inviati. Gli spammer falsificano l'indirizzo Da: dei messaggi, e spesso usano indirizzi di posta elettronica reali per rendere credibili i propri messaggi. Pertanto, quando gli spammer inviano inevitabilmente messaggi a destinatari inesistenti (la posta indesiderata è un'operazione con un volume elevato), il server di posta elettronica di destinazione viene essenzialmente ingiusto a restituire il messaggio non recapitabile in un rapporto di mancato recapito al mittente contraffatto nell'indirizzo Da:.

Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, EOP fa tutto il possibile per identificare e rilasciare automaticamente i messaggi da origini dubbie senza generare un rapporto di mancato recapito. Tuttavia, in base all'elevato volume di posta elettronica che attraversa il servizio, esiste sempre la possibilità che EOP invii involontariamente backscatter.

Backscatterer.org gestisce un elenco di indirizzi di blocco (noto anche come elenco di blocco DNS o DNSBL) dei server di posta elettronica responsabili dell'invio di backscatter e i server EOP potrebbero comparire in questo elenco. Tuttavia, non tentiamo di rimuoverci dall'Backscatterer.org di blocco perché non si tratta di un elenco di spammer (per propria ammissione).

> [!TIP]
> Il Backscatter.org web ( ) consiglia di usare il servizio per controllare la posta elettronica in arrivo in modalità provvisoria anziché in modalità rifiutata (i servizi di posta elettronica di grandi dimensioni inviano quasi sempre <http://www.backscatterer.org/?target=usage> backscatter).
