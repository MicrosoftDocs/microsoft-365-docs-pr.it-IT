---
title: Configurare i gruppi di dispositivi in Jamf Pro
description: Scopri come configurare i gruppi di dispositivi in Jamf Pro per Microsoft Defender per Endpoint per macOS
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
ms.openlocfilehash: 80dcb4ff73edd5e95603b15e097232a43dc0e05e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861612"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Configurare Microsoft Defender per Endpoint nei gruppi di dispositivi macOS in Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Configurare i gruppi di dispositivi in modo simile alle unità organizzative (OU) di Criteri di gruppo, alla raccolta di dispositivi di Microsoft Endpoint Configuration Manager e ai gruppi di dispositivi di Intune.

1. Passare a **Gruppi di computer statici**.

2. Selezionare **Nuovo**. 

    ![Immagine di Jamf Pro1](images/jamf-pro-static-group.png)

3. Specificare un nome visualizzato e selezionare **Salva**.

    ![Immagine di Jamf Pro2](images/jamfpro-machine-group.png)

4. A questo punto verrà visualizzato il **gruppo di computer di Contoso** in Gruppi di computer **statici**.

    ![Immagine di Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a>Passaggio successivo
- [Configurare Microsoft Defender per Endpoint nei criteri macOS in Jamf Pro](mac-jamfpro-policies.md)
