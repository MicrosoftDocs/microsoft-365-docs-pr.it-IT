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
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Configurare le impostazioni TCP e i servizi di Office 365 per ottenere prestazioni migliori.
ms.openlocfilehash: cf172bcaa87b7c69d33d349d18c449efff30a1d9
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290883"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="58ddf-103">Passaggio 5: ottimizzare client e prestazioni del servizio di Office 365</span><span class="sxs-lookup"><span data-stu-id="58ddf-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="58ddf-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="58ddf-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="58ddf-105">È possibile migliorare le prestazioni ottimizzando il funzionamento del TCP (Transmission Control Protocol) tra dispositivi client e i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="58ddf-105">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="58ddf-106">È possibile modificare le seguenti impostazioni TCP sui dispositivi client per ottimizzare le performance TCP:</span><span class="sxs-lookup"><span data-stu-id="58ddf-106">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="58ddf-107">[Ridimensionamento della finestra TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), in modo che il dispositivo client possa inviare altri dati prima di richiedere una conferma</span><span class="sxs-lookup"><span data-stu-id="58ddf-107">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="58ddf-108">[Tempo di inattività TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), in questo modo il dispositivo client può gestire connessioni aperte in maniera più efficiente</span><span class="sxs-lookup"><span data-stu-id="58ddf-108">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="58ddf-109">[Dimensione massima del segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), in questo modo il dispositivo client potrà inviare i blocchi di dati più grandi in un pacchetto</span><span class="sxs-lookup"><span data-stu-id="58ddf-109">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="58ddf-110">[Riconoscimenti selettivi TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), in questo modo il dispositivo client potrà riconoscere i dati ricevuti in maniera più efficiente</span><span class="sxs-lookup"><span data-stu-id="58ddf-110">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="58ddf-111">Per i servizi di Office 365, vedere queste risorse aggiuntive per ottimizzare le prestazioni:</span><span class="sxs-lookup"><span data-stu-id="58ddf-111">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="58ddf-112">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="58ddf-112">Exchange Online</span></span>](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [<span data-ttu-id="58ddf-113">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="58ddf-113">Skype for Business Online</span></span>](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [<span data-ttu-id="58ddf-114">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="58ddf-114">SharePoint Online</span></span>](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [<span data-ttu-id="58ddf-115">Project Online</span><span class="sxs-lookup"><span data-stu-id="58ddf-115">Project Online</span></span>](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

<span data-ttu-id="58ddf-116">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step5) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="58ddf-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="58ddf-117">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="58ddf-117">Next step</span></span>

[<span data-ttu-id="58ddf-118">Criteri uscita dell'infrastruttura di rete</span><span class="sxs-lookup"><span data-stu-id="58ddf-118">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
