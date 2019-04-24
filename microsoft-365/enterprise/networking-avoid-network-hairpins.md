---
title: 'Passaggio 3: evitare fenomeni di "hairpinning" di rete'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e rimuovere fenomeni di "hairpinning" di rete per prestazioni migliori.
ms.openlocfilehash: eef8770dff6c54da51650b0fb70077fdd125f981
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291520"
---
# <a name="step-3-avoid-network-hairpins"></a>Passaggio 3: evitare fenomeni di "hairpinning" di rete

*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Un [hairpin di rete](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) si verifica quando il traffico associato a una destinazione viene prima indirizzato a un'altra posizione intermedia, come uno stack di sicurezza in locale, un broker di accesso cloud o un gateway Web basato sul cloud. Un hairpin di rete potrebbe anche essere dovuto a uno scarso routing su Internet a causa dei provider di servizi di rete. Un hairpin aggiunge latenza e può potenzialmente reindirizzare il traffico a una posizione geograficamente lontana.

Per ottimizzare le prestazioni per il traffico verso i servizi basati sul cloud di Microsoft 365, verificare se l'ISP che fornisce la connessione Internet locale dispone di una relazione di peering diretto con Microsoft Global Network nelle immediate vicinanze della posizione in questione. Tali connessioni non hanno hairpin.

Se si utilizza una rete basata sul cloud o servizi di sicurezza per il traffico di Microsoft 365, verificare che venga valutato l'effetto di hairpinning e che venga interpretato il suo impatto sulle prestazioni. Esaminare quanto riportato di seguito:

- Il numero e le posizioni dei provider di servizi con cui viene inoltrato il traffico in relazione alle succursali e ai punti di peering di Microsoft Global Network 
- La qualità della relazione di peering della rete del provider di servizi con l'ISP e Microsoft 
- L'impatto del backhauling sulle prestazioni nell'infrastruttura del provider di servizi

Ove possibile, configurare i router periferici in modo da inviare direttamente il traffico di Microsoft 365 attendibile, anziché inoltrarlo tramite proxy o tunneling attraverso un fornitore di sicurezza di rete basato sul cloud o un cloud di terze parti che elabora il traffico di Internet. 

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step3) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[Configurare il bypass di traffico](networking-configure-proxies-firewalls.md)|
