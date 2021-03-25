---
title: Configurare le funzionalità di Microsoft Defender ATP per Android
description: Descrive come configurare Microsoft Defender ATP per Android
keywords: microsoft, defender, atp, android, configurazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4325020e653f14898ece4192e03cbf8b90131136
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163448"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a><span data-ttu-id="482f9-104">Configurare Defender per le funzionalità di Endpoint per Android</span><span class="sxs-lookup"><span data-stu-id="482f9-104">Configure Defender for Endpoint for Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="482f9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="482f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="482f9-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="482f9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="482f9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="482f9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a><span data-ttu-id="482f9-108">Accesso condizionale con Defender per Endpoint per Android</span><span class="sxs-lookup"><span data-stu-id="482f9-108">Conditional Access with Defender for Endpoint for Android</span></span>  
<span data-ttu-id="482f9-109">Microsoft Defender per Endpoint per Android insieme a Microsoft Intune e Azure Active Directory consente di attivare la conformità dei dispositivi e i criteri di accesso condizionale in base ai livelli di rischio del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="482f9-109">Microsoft Defender for Endpoint for Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="482f9-110">Defender for Endpoint è una soluzione Mobile Threat Defense (MTD) che puoi distribuire per sfruttare questa funzionalità tramite Intune.</span><span class="sxs-lookup"><span data-stu-id="482f9-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="482f9-111">Per altre informazioni su come configurare Defender per Endpoint per Android e l'accesso condizionale, vedi [Defender per Endpoint e Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="482f9-111">For more information about how to set up Defender for Endpoint for Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="482f9-112">Configurare indicatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="482f9-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="482f9-113">Defender per Endpoint per Android supporta solo la creazione di indicatori personalizzati per indirizzi IP e URL/domini.</span><span class="sxs-lookup"><span data-stu-id="482f9-113">Defender for Endpoint for Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="482f9-114">Defender for Endpoint per Android consente agli amministratori di configurare indicatori personalizzati per supportare anche i dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="482f9-114">Defender for Endpoint for Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="482f9-115">Per ulteriori informazioni su come configurare gli indicatori personalizzati, vedere [Manage indicators](manage-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="482f9-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="482f9-116">Configurare la protezione Web</span><span class="sxs-lookup"><span data-stu-id="482f9-116">Configure web protection</span></span>
<span data-ttu-id="482f9-117">Defender for Endpoint per Android consente agli amministratori IT di configurare la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="482f9-117">Defender for Endpoint for Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="482f9-118">Questa funzionalità è disponibile nell'interfaccia di amministrazione di Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="482f9-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="482f9-119">Defender per Endpoint per Android userebbe una VPN per fornire la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="482f9-119">Defender for Endpoint for Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="482f9-120">Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="482f9-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="482f9-121">Per altre informazioni, vedi [Configurare la protezione Web nei dispositivi che eseguono Android.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="482f9-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="482f9-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="482f9-122">Related topics</span></span>
- [<span data-ttu-id="482f9-123">Panoramica di Microsoft Defender per Endpoint per Android</span><span class="sxs-lookup"><span data-stu-id="482f9-123">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="482f9-124">Distribuire Microsoft Defender per Endpoint per Android con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="482f9-124">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span>](android-intune.md)
