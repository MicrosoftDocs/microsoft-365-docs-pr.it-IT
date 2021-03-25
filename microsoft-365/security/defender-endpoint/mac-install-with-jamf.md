---
title: Distribuzione di Microsoft Defender ATP per macOS con Jamf Pro
description: Distribuzione di Microsoft Defender ATP per macOS con Jamf Pro
keywords: microsoft, defender, atp, mac, installazione, distribuire, disinstallazione, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 56f5e860bd2a9dd47ce16379b5e1ca1a263d62d0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187410"
---
# <a name="deploying-microsoft-defender-for-endpoint-for-macos-with-jamf-pro"></a><span data-ttu-id="9c50a-104">Distribuzione di Microsoft Defender per Endpoint per macOS con Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="9c50a-104">Deploying Microsoft Defender for Endpoint for macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9c50a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9c50a-105">**Applies to:**</span></span>
- [<span data-ttu-id="9c50a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="9c50a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9c50a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c50a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9c50a-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="9c50a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9c50a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="9c50a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="9c50a-110">Scopri come distribuire Microsoft Defender for Endpoint per macOS con Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="9c50a-110">Learn how to deploy Microsoft Defender for Endpoint for macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="9c50a-111">Se si usa macOS Catalina (10.15.4) o versioni più recenti di macOS, vedere Nuovi profili di configurazione per [macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)e versioni più recenti di macOS.</span><span class="sxs-lookup"><span data-stu-id="9c50a-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="9c50a-112">Si tratta di un processo a più passaggi.</span><span class="sxs-lookup"><span data-stu-id="9c50a-112">This is a multi step process.</span></span> <span data-ttu-id="9c50a-113">Dovrai completare tutti i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c50a-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="9c50a-114">Accedere al portale Jamf</span><span class="sxs-lookup"><span data-stu-id="9c50a-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="9c50a-115">Configurare Microsoft Defender for Endpoint per i gruppi di dispositivi macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="9c50a-115">Setup the Microsoft Defender for Endpoint for macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="9c50a-116">Configurare i criteri di Microsoft Defender for Endpoint per macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="9c50a-116">Setup the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="9c50a-117">Registrare Microsoft Defender for Endpoint per i dispositivi macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="9c50a-117">Enroll the Microsoft Defender for Endpoint for macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




