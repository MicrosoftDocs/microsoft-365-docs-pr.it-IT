---
title: Distribuzione di Microsoft Defender per Endpoint in macOS con Jamf Pro
description: Distribuzione di Microsoft Defender per Endpoint in macOS con Jamf Pro
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installazione, distribuzione, disinstallazione, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: d102635a284ec5c802e352f097d1632e2f20e166
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929062"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="24aa5-104">Distribuzione di Microsoft Defender per Endpoint in macOS con Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="24aa5-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="24aa5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="24aa5-105">**Applies to:**</span></span>
- [<span data-ttu-id="24aa5-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="24aa5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24aa5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24aa5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="24aa5-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="24aa5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="24aa5-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="24aa5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="24aa5-110">Scopri come distribuire Microsoft Defender for Endpoint in macOS con Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="24aa5-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="24aa5-111">Se si usa macOS Catalina (10.15.4) o versioni più recenti di macOS, vedere Nuovi profili di configurazione per [macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)e versioni più recenti di macOS.</span><span class="sxs-lookup"><span data-stu-id="24aa5-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="24aa5-112">Si tratta di un processo a più passaggi.</span><span class="sxs-lookup"><span data-stu-id="24aa5-112">This is a multi step process.</span></span> <span data-ttu-id="24aa5-113">Dovrai completare tutti i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="24aa5-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="24aa5-114">Accedere al portale Jamf</span><span class="sxs-lookup"><span data-stu-id="24aa5-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="24aa5-115">Configurare Microsoft Defender per Endpoint nei gruppi di dispositivi macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="24aa5-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="24aa5-116">Configurare i criteri di Microsoft Defender for Endpoint su macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="24aa5-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="24aa5-117">Registrare Microsoft Defender for Endpoint nei dispositivi macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="24aa5-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




