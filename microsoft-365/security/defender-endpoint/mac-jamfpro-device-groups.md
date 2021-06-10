---
title: Configurare i gruppi di dispositivi in Jamf Pro
description: Scopri come configurare i gruppi di dispositivi in Jamf Pro per Microsoft Defender per Endpoint in macOS
keywords: dispositivo, gruppo, microsoft, defender, Microsoft Defender for Endpoint, mac, installazione, distribuzione, disinstallazione, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 772b67ec84ae9614c9322763c140a60e7884644d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933806"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="b8375-104">Configurare Microsoft Defender per Endpoint nei gruppi di dispositivi macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="b8375-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b8375-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b8375-105">**Applies to:**</span></span>
- [<span data-ttu-id="b8375-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b8375-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b8375-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8375-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b8375-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b8375-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b8375-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b8375-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b8375-110">Configurare i gruppi di dispositivi in modo simile a Unità organizzative (OU) di Criteri di gruppo, alla raccolta di dispositivi di Microsoft Endpoint Configuration Manager e ai gruppi di dispositivi di Intune.</span><span class="sxs-lookup"><span data-stu-id="b8375-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="b8375-111">Passare a **Gruppi di computer statici**.</span><span class="sxs-lookup"><span data-stu-id="b8375-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="b8375-112">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b8375-112">Select **New**.</span></span> 

    ![Immagine di Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="b8375-114">Specificare un nome visualizzato e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b8375-114">Provide a display name and select **Save**.</span></span>

    ![Immagine di Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="b8375-116">A questo punto verrà visualizzato il **gruppo di computer di Contoso** in Gruppi di computer **statici**.</span><span class="sxs-lookup"><span data-stu-id="b8375-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Immagine di Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="b8375-118">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b8375-118">Next step</span></span>
- [<span data-ttu-id="b8375-119">Configurare Microsoft Defender per Endpoint nei criteri macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="b8375-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
