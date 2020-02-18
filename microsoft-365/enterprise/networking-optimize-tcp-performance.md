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
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="a2403-103">Passaggio 5: ottimizzare client e prestazioni del servizio di Office 365</span><span class="sxs-lookup"><span data-stu-id="a2403-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="a2403-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="a2403-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1 - Rete](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="a2403-106">È possibile migliorare le prestazioni ottimizzando il funzionamento del TCP (Transmission Control Protocol) tra dispositivi client e i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a2403-106">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="a2403-107">È possibile modificare le seguenti impostazioni TCP sui dispositivi client per ottimizzare le performance TCP:</span><span class="sxs-lookup"><span data-stu-id="a2403-107">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="a2403-108">[Ridimensionamento della finestra TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), in modo che il dispositivo client possa inviare altri dati prima di richiedere una conferma</span><span class="sxs-lookup"><span data-stu-id="a2403-108">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="a2403-109">[Tempo di inattività TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), in questo modo il dispositivo client può gestire connessioni aperte in maniera più efficiente</span><span class="sxs-lookup"><span data-stu-id="a2403-109">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="a2403-110">[Dimensione massima del segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), in questo modo il dispositivo client potrà inviare i blocchi di dati più grandi in un pacchetto</span><span class="sxs-lookup"><span data-stu-id="a2403-110">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="a2403-111">[Riconoscimenti selettivi TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), in questo modo il dispositivo client potrà riconoscere i dati ricevuti in maniera più efficiente</span><span class="sxs-lookup"><span data-stu-id="a2403-111">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="a2403-112">Per i servizi di Office 365, vedere queste risorse aggiuntive per ottimizzare le prestazioni:</span><span class="sxs-lookup"><span data-stu-id="a2403-112">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="a2403-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a2403-113">Exchange Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [<span data-ttu-id="a2403-114">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a2403-114">Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [<span data-ttu-id="a2403-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a2403-115">SharePoint Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [<span data-ttu-id="a2403-116">Project Web App in Project Online</span><span class="sxs-lookup"><span data-stu-id="a2403-116">Project Web App in Project Online</span></span>](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

<span data-ttu-id="a2403-117">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step5) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="a2403-117">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a2403-118">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a2403-118">Next step</span></span>

[<span data-ttu-id="a2403-119">Criteri uscita dell'infrastruttura di rete</span><span class="sxs-lookup"><span data-stu-id="a2403-119">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
