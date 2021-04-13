---
title: Configurare Le funzionalità di Microsoft Defender per Endpoint su Android
description: Descrive come configurare Microsoft Defender per Endpoint su Android
keywords: microsoft, defender, atp, mde, android, configurazione
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
ms.openlocfilehash: 8ec4a19bdd641c721bfcd7be2ceb59de1de92963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688034"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a><span data-ttu-id="71dec-104">Configurare Defender per le funzionalità di Endpoint per Android</span><span class="sxs-lookup"><span data-stu-id="71dec-104">Configure Defender for Endpoint for Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="71dec-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="71dec-105">**Applies to:**</span></span>
- [<span data-ttu-id="71dec-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="71dec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="71dec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71dec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a><span data-ttu-id="71dec-108">Accesso condizionale con Defender per Endpoint per Android</span><span class="sxs-lookup"><span data-stu-id="71dec-108">Conditional Access with Defender for Endpoint for Android</span></span>  
<span data-ttu-id="71dec-109">Microsoft Defender per Endpoint su Android insieme a Microsoft Intune e Azure Active Directory consente di attivare la conformità dei dispositivi e i criteri di accesso condizionale in base ai livelli di rischio del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="71dec-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="71dec-110">Defender for Endpoint è una soluzione Mobile Threat Defense (MTD) che puoi distribuire per sfruttare questa funzionalità tramite Intune.</span><span class="sxs-lookup"><span data-stu-id="71dec-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="71dec-111">Per altre informazioni su come configurare Defender per Endpoint per Android e l'accesso condizionale, vedi [Defender per Endpoint e Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="71dec-111">For more information about how to set up Defender for Endpoint for Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="71dec-112">Configurare indicatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="71dec-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="71dec-113">Defender per Endpoint per Android supporta solo la creazione di indicatori personalizzati per indirizzi IP e URL/domini.</span><span class="sxs-lookup"><span data-stu-id="71dec-113">Defender for Endpoint for Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="71dec-114">Defender for Endpoint per Android consente agli amministratori di configurare indicatori personalizzati per supportare anche i dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="71dec-114">Defender for Endpoint for Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="71dec-115">Per ulteriori informazioni su come configurare gli indicatori personalizzati, vedere [Manage indicators](manage-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="71dec-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="71dec-116">Configurare la protezione Web</span><span class="sxs-lookup"><span data-stu-id="71dec-116">Configure web protection</span></span>
<span data-ttu-id="71dec-117">Defender for Endpoint per Android consente agli amministratori IT di configurare la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="71dec-117">Defender for Endpoint for Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="71dec-118">Questa funzionalità è disponibile nell'interfaccia di amministrazione di Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="71dec-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="71dec-119">Defender per Endpoint per Android userebbe una VPN per fornire la funzionalità di protezione Web.</span><span class="sxs-lookup"><span data-stu-id="71dec-119">Defender for Endpoint for Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="71dec-120">Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="71dec-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="71dec-121">Per altre informazioni, vedi [Configurare la protezione Web nei dispositivi che eseguono Android.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)</span><span class="sxs-lookup"><span data-stu-id="71dec-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="71dec-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="71dec-122">Related topics</span></span>
- [<span data-ttu-id="71dec-123">Panoramica di Microsoft Defender per Endpoint su Android</span><span class="sxs-lookup"><span data-stu-id="71dec-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="71dec-124">Distribuire Microsoft Defender per Endpoint su Android con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="71dec-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
