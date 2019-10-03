---
title: 'Passaggio 5: ottimizzare client e prestazioni del servizio di Office 365'
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
description: Configurare le impostazioni TCP e i servizi di Office 365 per ottenere prestazioni migliori.
ms.openlocfilehash: f89ae816780101c31971c8e3e60df803f82f1e55
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370073"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Passaggio 5: ottimizzare client e prestazioni del servizio di Office 365

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![Fase 1 - Rete](./media/deploy-foundation-infrastructure/networking_icon-small.png)

È possibile migliorare le prestazioni ottimizzando il funzionamento del TCP (Transmission Control Protocol) tra dispositivi client e i servizi di Office 365.

È possibile modificare le seguenti impostazioni TCP sui dispositivi client per ottimizzare le performance TCP:

- [Ridimensionamento della finestra TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), in modo che il dispositivo client possa inviare altri dati prima di richiedere una conferma
- [Tempo di inattività TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), in questo modo il dispositivo client può gestire connessioni aperte in maniera più efficiente
- [Dimensione massima del segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), in questo modo il dispositivo client potrà inviare i blocchi di dati più grandi in un pacchetto
- [Riconoscimenti selettivi TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), in questo modo il dispositivo client potrà riconoscere i dati ricevuti in maniera più efficiente

Per i servizi di Office 365, vedere queste risorse aggiuntive per ottimizzare le prestazioni:

- [Exchange Online](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [Skype for Business Online](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [SharePoint Online](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [Project Web App in Project Online](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step5) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

[Criteri uscita dell'infrastruttura di rete](networking-exit-criteria.md)
