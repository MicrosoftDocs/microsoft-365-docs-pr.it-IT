---
title: 'Passaggio 5: ottimizzare client e prestazioni del servizio di Office 365'
f1.keywords:
- NOCSH
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
ms.openlocfilehash: e3aefb417330ab791a3dd217e2e34591eba3e1d1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066542"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Passaggio 5: ottimizzare client e prestazioni del servizio di Office 365

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![Fase 1 - Rete](../media/deploy-foundation-infrastructure/networking_icon-small.png)

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
