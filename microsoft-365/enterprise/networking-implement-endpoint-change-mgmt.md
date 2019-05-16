---
title: 'Passaggio 4: pianificare modifiche apportate agli indirizzi IP e URL'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: dacd2ad83bdeb106ae398e8223f457c66a12b598
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073226"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a>Passaggio 4: pianificare modifiche apportate agli indirizzi IP e URL

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
>Questo passaggio richiede di aver completato il [passaggio 3](networking-configure-proxies-firewalls.md). Se non è stato completato il passaggio 3, andare al [passaggio 5](networking-optimize-tcp-performance.md).
>

Gli URL e gli indirizzi IP usati dalla rete globale di Microsoft 365 cambiano nel tempo, è quindi importante pianificare gli aggiornamenti a questi endpoint. Ad esempio, potrebbe essere necessario configurare di nuovo i dispositivi di sicurezza nella rete perimetrale con:

- Nuovi URL per nuovi servizi che richiedono l'elaborazione senza intoppi
- Rimozione di URL per servizi non più disponibili
- Nuovi intervalli di indirizzi IP per nuovi percorsi di rete e server Microsoft su Internet 
- Modifiche agli intervalli di indirizzi IP per i diversi servizi

Per ulteriori informazioni sulla creazione di un piano di implementazione delle modifiche agli endpoint, comprensivo di notifiche di tali modifiche, vedere [Gestione degli endpoint di Office 365 - Integrazione](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) e [Gestione degli endpoint di Office 365 - Proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step4) di questa fase.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Ottimizzare prestazioni di client e del servizio di Office 365](networking-optimize-tcp-performance.md)|
