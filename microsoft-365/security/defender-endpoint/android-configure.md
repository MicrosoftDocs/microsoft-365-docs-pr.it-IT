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
# <a name="configure-defender-for-endpoint-for-android-features"></a>Configurare Defender per le funzionalità di Endpoint per Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a>Accesso condizionale con Defender per Endpoint per Android  
Microsoft Defender per Endpoint su Android insieme a Microsoft Intune e Azure Active Directory consente di attivare la conformità dei dispositivi e i criteri di accesso condizionale in base ai livelli di rischio del dispositivo. Defender for Endpoint è una soluzione Mobile Threat Defense (MTD) che puoi distribuire per sfruttare questa funzionalità tramite Intune.

Per altre informazioni su come configurare Defender per Endpoint per Android e l'accesso condizionale, vedi [Defender per Endpoint e Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)

## <a name="configure-custom-indicators"></a>Configurare indicatori personalizzati  

> [!NOTE]
> Defender per Endpoint per Android supporta solo la creazione di indicatori personalizzati per indirizzi IP e URL/domini.

Defender for Endpoint per Android consente agli amministratori di configurare indicatori personalizzati per supportare anche i dispositivi Android. Per ulteriori informazioni su come configurare gli indicatori personalizzati, vedere [Manage indicators](manage-indicators.md).

## <a name="configure-web-protection"></a>Configurare la protezione Web
Defender for Endpoint per Android consente agli amministratori IT di configurare la funzionalità di protezione Web. Questa funzionalità è disponibile nell'interfaccia di amministrazione di Microsoft Endpoint Manager.

> [!NOTE]
> Defender per Endpoint per Android userebbe una VPN per fornire la funzionalità di protezione Web. Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo. Per altre informazioni, vedi [Configurare la protezione Web nei dispositivi che eseguono Android.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica di Microsoft Defender per Endpoint su Android](microsoft-defender-endpoint-android.md)
- [Distribuire Microsoft Defender per Endpoint su Android con Microsoft Intune](android-intune.md)
