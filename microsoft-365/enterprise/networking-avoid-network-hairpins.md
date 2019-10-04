---
title: 'Passaggio 3: evitare fenomeni di "hairpinning" di rete'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e rimuovere fenomeni di "hairpinning" di rete per prestazioni migliori.
ms.openlocfilehash: 8d3c971c1295f8f1112c594635bfd791b251bd68
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370333"
---
# <a name="step-3-avoid-network-hairpins"></a>Passaggio 3: evitare fenomeni di "hairpinning" di rete

*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![Fase 1: collegamento in rete](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Si verifica un ["hairpinning" di rete](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) quando il traffico associato per una destinazione viene prima indirizzato a un'altra posizione intermedia, ad esempio uno stack di sicurezza locale, un broker di accesso cloud o un gateway Web basato sul cloud. Ecco un esempio.

![Esempio di "hairpinning" di rete](./media/networking-avoid-network-hairpins/network-hairpin-example.png)

Un "hairpinning" di rete può dipendere anche da un routing insufficiente in Internet causato dai provider di servizi di rete. 

Un "hairpinning" aggiunge latenza e può potenzialmente reindirizzare il traffico a una posizione geograficamente distante.

Per ottimizzare le prestazioni per il traffico verso i servizi basati sul cloud di Microsoft 365, verificare se l'ISP che fornisce la connessione Internet locale dispone di una relazione di peering diretto con Microsoft Global Network nelle immediate vicinanze della posizione in questione. Tali connessioni non hanno hairpin.

Se si utilizza una rete basata sul cloud o servizi di sicurezza per il traffico di Microsoft 365, verificare che venga valutato l'effetto di hairpinning e che venga interpretato il suo impatto sulle prestazioni. Esaminare quanto riportato di seguito:

- Il numero e le posizioni dei provider di servizi con cui viene inoltrato il traffico in relazione alle succursali e ai punti di peering di Microsoft Global Network 
- La qualità della relazione di peering della rete del provider di servizi con l'ISP e Microsoft 
- L'impatto del backhauling sulle prestazioni nell'infrastruttura del provider di servizi

Ove possibile, configurare i router periferici in modo da inviare direttamente il traffico di Microsoft 365 attendibile, anziché inoltrarlo tramite proxy o tunneling attraverso un fornitore di sicurezza di rete basato sul cloud o un cloud di terze parti che elabora il traffico di Internet. 

![Esempio di bypass dell'"hairpinning" di rete](./media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step3) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![Passaggio 4](./media/stepnumbers/Step4.png)|[Configurare il bypass di traffico](networking-configure-proxies-firewalls.md)|
