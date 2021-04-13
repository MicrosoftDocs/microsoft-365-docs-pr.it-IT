---
title: Configurare i gruppi di dispositivi in Jamf Pro
description: Scopri come configurare i gruppi di dispositivi in Jamf Pro per Microsoft Defender ATP per macOS
keywords: dispositivo, gruppo, microsoft, defender, atp, mac, installazione, distribuire, disinstallazione, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 6c1d6ae5d4635186bf0a1cbb55c7f906e8584f01
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689690"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="d1c5a-104">Configurare Microsoft Defender per Endpoint nei gruppi di dispositivi macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="d1c5a-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d1c5a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d1c5a-105">**Applies to:**</span></span>
- [<span data-ttu-id="d1c5a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d1c5a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d1c5a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1c5a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d1c5a-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d1c5a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d1c5a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d1c5a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="d1c5a-110">Configurare i gruppi di dispositivi in modo simile alle unità organizzative (OU) di Criteri di gruppo, alla raccolta di dispositivi di Microsoft Endpoint Configuration Manager e ai gruppi di dispositivi di Intune.</span><span class="sxs-lookup"><span data-stu-id="d1c5a-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="d1c5a-111">Passare a **Gruppi di computer statici**.</span><span class="sxs-lookup"><span data-stu-id="d1c5a-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="d1c5a-112">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d1c5a-112">Select **New**.</span></span> 

    ![Immagine di Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="d1c5a-114">Specificare un nome visualizzato e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d1c5a-114">Provide a display name and select **Save**.</span></span>

    ![Immagine di Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="d1c5a-116">A questo punto verrà visualizzato il **gruppo di computer di Contoso** in Gruppi di computer **statici**.</span><span class="sxs-lookup"><span data-stu-id="d1c5a-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Immagine di Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="d1c5a-118">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d1c5a-118">Next step</span></span>
- [<span data-ttu-id="d1c5a-119">Configurare Microsoft Defender per Endpoint nei criteri macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="d1c5a-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
