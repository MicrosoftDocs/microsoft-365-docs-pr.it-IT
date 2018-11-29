---
title: 'Passaggio 5: ottimizzare client e prestazioni del servizio di Office 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Configurare le impostazioni TCP e i servizi di Office 365 per ottenere prestazioni migliori.
ms.openlocfilehash: 40f99f1b50a324af0650382de165dcfd3df97b0c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868485"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Passaggio 5: ottimizzare client e prestazioni del servizio di Office 365

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

È possibile migliorare le prestazioni ottimizzando il funzionamento del TCP (Transmission Control Protocol) tra dispositivi client e i servizi di Office 365.

È possibile modificare le seguenti impostazioni TCP sui dispositivi client per ottimizzare le performance TCP:

- [Ridimensionamento della finestra TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), in modo che il dispositivo client possa inviare altri dati prima di richiedere una conferma
- [Tempo di inattività TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), in questo modo il dispositivo client può gestire connessioni aperte in maniera più efficiente
- [Dimensione massima del segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), in questo modo il dispositivo client potrà inviare i blocchi di dati più grandi in un pacchetto
- [Riconoscimenti selettivi TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), in questo modo il dispositivo client potrà riconoscere i dati ricevuti in maniera più efficiente

Per i servizi di Office 365, vedere queste risorse aggiuntive per ottimizzare le prestazioni:

- [Exchange Online](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [Skype for Business Online](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [SharePoint Online](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [Project Online](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step5) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

[Criteri uscita dell'infrastruttura di rete](networking-exit-criteria.md)
