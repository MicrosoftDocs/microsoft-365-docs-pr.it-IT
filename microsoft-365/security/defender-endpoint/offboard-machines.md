---
title: Dispositivi offboard dal servizio Microsoft Defender ATP
description: Onboard di dispositivi Windows 10, server, dispositivi non Windows dal servizio Microsoft Defender ATP
keywords: offboarding, microsoft defender per l'offboarding degli endpoint, offboarding windows atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a95ff5214ea9f696622ea184ece1c5aa9fb3db2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186966"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="67659-104">Dispositivi offboard dal servizio Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="67659-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="67659-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="67659-105">**Applies to:**</span></span>
- [<span data-ttu-id="67659-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="67659-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="67659-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67659-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="67659-108">**Piattaforme**</span><span class="sxs-lookup"><span data-stu-id="67659-108">**Platforms**</span></span>
- <span data-ttu-id="67659-109">macOS</span><span class="sxs-lookup"><span data-stu-id="67659-109">macOS</span></span>
- <span data-ttu-id="67659-110">Linux</span><span class="sxs-lookup"><span data-stu-id="67659-110">Linux</span></span>
- <span data-ttu-id="67659-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="67659-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="67659-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="67659-112">Windows Server 2016</span></span>

><span data-ttu-id="67659-113">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="67659-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="67659-114">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="67659-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="67659-115">Seguire le istruzioni corrispondenti a seconda del metodo di distribuzione preferito.</span><span class="sxs-lookup"><span data-stu-id="67659-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="67659-116">Lo stato di un dispositivo verrà commutato [su Inattivo](fix-unhealthy-sensors.md#inactive-devices) 7 giorni dopo l'offboarding.</span><span class="sxs-lookup"><span data-stu-id="67659-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="67659-117">I dati dei dispositivi offboarded (ad esempio sequenza temporale, avvisi, vulnerabilità [](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) e così via) rimarranno nel portale fino alla scadenza del periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="67659-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="67659-118">Il profilo del dispositivo (senza dati) [](machines-view-overview.md) rimarrà nell'elenco dei dispositivi per non più di 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="67659-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="67659-119">Inoltre, i dispositivi che non sono attivi negli ultimi 30 giorni non vengono utilizzati nei dati [](tvm-exposure-score.md) che riflettono il punteggio di esposizione della gestione delle minacce e delle vulnerabilità dell'organizzazione e il punteggio microsoft secure per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="67659-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="67659-120">Per visualizzare solo i dispositivi attivi, è possibile filtrare in base allo [stato di](machines-view-overview.md#health-state)integrità, ai tag [dei dispositivi](machine-tags.md) o ai gruppi [di computer.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="67659-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="67659-121">Offboard dei dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="67659-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="67659-122">Dispositivi offboard con uno script locale</span><span class="sxs-lookup"><span data-stu-id="67659-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="67659-123">Dispositivi offboard con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="67659-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="67659-124">Dispositivi offboard con strumenti di gestione dei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="67659-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="67659-125">Server offboard</span><span class="sxs-lookup"><span data-stu-id="67659-125">Offboard Servers</span></span>
- [<span data-ttu-id="67659-126">Server offboard</span><span class="sxs-lookup"><span data-stu-id="67659-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="67659-127">Offboard di dispositivi non Windows</span><span class="sxs-lookup"><span data-stu-id="67659-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="67659-128">Offboard di dispositivi non Windows</span><span class="sxs-lookup"><span data-stu-id="67659-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

