---
title: Configurare funzionalità di Microsoft Defender per Endpoint su funzionalità Android
description: Descrive come configurare Microsoft Defender per Endpoint su Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, configurazione
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935318"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a><span data-ttu-id="536c9-104">Configurare Defender per le funzionalità di Endpoint in Android</span><span class="sxs-lookup"><span data-stu-id="536c9-104">Configure Defender for Endpoint on Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="536c9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="536c9-105">**Applies to:**</span></span>
- [<span data-ttu-id="536c9-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="536c9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="536c9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="536c9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a><span data-ttu-id="536c9-108">Accesso condizionale con Defender per Endpoint su Android</span><span class="sxs-lookup"><span data-stu-id="536c9-108">Conditional Access with Defender for Endpoint on Android</span></span>  
<span data-ttu-id="536c9-109">Microsoft Defender per Endpoint su Android insieme a Microsoft Intune e Azure Active Directory consente di attivare la conformità dei dispositivi e i criteri di accesso condizionale in base ai livelli di rischio del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="536c9-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="536c9-110">Defender for Endpoint è una soluzione Mobile Threat Defense (MTD) che puoi distribuire per sfruttare questa funzionalità tramite Intune.</span><span class="sxs-lookup"><span data-stu-id="536c9-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="536c9-111">Per altre informazioni su come configurare Defender per Endpoint in Android e l'accesso condizionale, vedi [Defender per Endpoint e Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="536c9-111">For more information about how to set up Defender for Endpoint on Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="536c9-112">Configurare indicatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="536c9-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="536c9-113">Defender per Endpoint su Android supporta solo la creazione di indicatori personalizzati per indirizzi IP e URL/domini.</span><span class="sxs-lookup"><span data-stu-id="536c9-113">Defender for Endpoint on Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="536c9-114">Defender per Endpoint su Android consente agli amministratori di configurare indicatori personalizzati per supportare anche i dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="536c9-114">Defender for Endpoint on Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="536c9-115">Per ulteriori informazioni su come configurare gli indicatori personalizzati, vedere [Manage indicators](manage-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="536c9-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="536c9-116">Configurare la protezione Web</span><span class="sxs-lookup"><span data-stu-id="536c9-116">Configure web protection</span></span>
<span data-ttu-id="536c9-117">Defender per Endpoint su Android consente agli amministratori IT di configurare la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="536c9-117">Defender for Endpoint on Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="536c9-118">Questa funzionalità è disponibile nell'interfaccia di amministrazione di Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="536c9-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="536c9-119">Defender per Endpoint su Android userebbe una VPN per fornire la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="536c9-119">Defender for Endpoint on Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="536c9-120">Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="536c9-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="536c9-121">Per altre informazioni, vedi [Configurare la protezione Web nei dispositivi che eseguono Android.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="536c9-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="536c9-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="536c9-122">Related topics</span></span>
- [<span data-ttu-id="536c9-123">Panoramica di Microsoft Defender per Endpoint su Android</span><span class="sxs-lookup"><span data-stu-id="536c9-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="536c9-124">Distribuzione di Microsoft Defender per Endpoint per Android con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="536c9-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
