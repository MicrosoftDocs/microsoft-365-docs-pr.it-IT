---
title: Configurare l'integrazione di Microsoft Cloud App Security
ms.reviewer: ''
description: Scopri come attivare le impostazioni per abilitare l'integrazione di Microsoft Defender for Endpoint con Microsoft Cloud App Security.
keywords: cloud, app, sicurezza, impostazioni, integrazione, individuazione, report
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ddf32b26191826ab6ecbad6b9d047ac7bbb6276a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068533"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Configurare Microsoft Cloud App Security in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Per trarre vantaggio dai segnali di individuazione delle app cloud di Microsoft Defender for Endpoint, attiva l'integrazione di Microsoft Cloud App Security.

>[!NOTE]
>Questa funzionalità sarà disponibile con una licenza E5 per [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) nei dispositivi che eseguono Windows 10 versione 1709 (OS Build 16299.1085 con [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, versione 1803 (OS Build 17134.704 con [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10 versione 1809 (OS Build 17763.379 con [KB4489899](https://support.microsoft.com/help/4489899)) o versioni successive di Windows 10.

> Vedi [Microsoft Defender per l'integrazione degli endpoint con Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) per un'integrazione dettagliata di Microsoft Defender for Endpoint con Microsoft Cloud App Security. 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Abilitare Microsoft Cloud App Security in Microsoft Defender for Endpoint

1. Nel riquadro di spostamento seleziona **Impostazioni preferenze**  >  **Funzionalità avanzate.**
2. Seleziona **Microsoft Cloud App Security** e imposta l'interruttore su **Attivato.**
3. Fare **clic su Salva preferenze.**

Una volta attivato, Microsoft Defender for Endpoint inizierà immediatamente l'inoltro dei segnali di individuazione a Cloud App Security.

## <a name="view-the-data-collected"></a>Visualizzare i dati raccolti

Per visualizzare e accedere ai dati di Microsoft Defender for Endpoint in Microsoft Cloud Apps Security, vedi [Analizzare i dispositivi in Cloud App Security.](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)


Per altre informazioni sull'individuazione cloud, vedi [Uso delle app individuate.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

Se si è interessati a provare Microsoft Cloud App Security, vedere [Versione di valutazione di Microsoft Cloud App Security.](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)

## <a name="related-topic"></a>Argomento correlato
- [Integrazione di Microsoft Cloud App Security](microsoft-cloud-app-security-integration.md)
