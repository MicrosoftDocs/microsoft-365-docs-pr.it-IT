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
ms.openlocfilehash: 264ebbe0ceb6d6b83c006dbd1dd071a78ae219c3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841353"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Configurare Defender per le funzionalità di Endpoint in Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Accesso condizionale con Defender per Endpoint su Android  
Microsoft Defender per Endpoint su Android insieme a Microsoft Intune e Azure Active Directory consente di far rispettare la conformità dei dispositivi e i criteri di accesso condizionale in base ai livelli di rischio del dispositivo. Defender for Endpoint è una soluzione Mobile Threat Defense (MTD) che puoi distribuire per sfruttare questa funzionalità tramite Intune.

Per altre informazioni su come configurare Defender per Endpoint in Android e l'accesso condizionale, vedi [Defender per Endpoint e Intune.](/mem/intune/protect/advanced-threat-protection)

## <a name="configure-custom-indicators"></a>Configurare indicatori personalizzati  

> [!NOTE]
> Defender per Endpoint su Android supporta solo la creazione di indicatori personalizzati per indirizzi IP e URL/domini.

Defender per Endpoint su Android consente agli amministratori di configurare indicatori personalizzati per supportare anche i dispositivi Android. Per ulteriori informazioni su come configurare gli indicatori personalizzati, vedere [Manage indicators](manage-indicators.md).

## <a name="configure-web-protection"></a>Configurare la protezione Web
Defender per Endpoint su Android consente agli amministratori IT di configurare la funzionalità di protezione Web. Questa funzionalità è disponibile all'interno dell'Microsoft Endpoint Manager di amministrazione.

> [!NOTE]
> Defender per Endpoint su Android userebbe una VPN per fornire la funzionalità di protezione Web. Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo. Per altre informazioni, vedi [Configurare la protezione Web nei dispositivi che eseguono Android.](/mem/intune/protect/advanced-threat-protection-manage-android)

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica di Microsoft Defender per Endpoint su Android](microsoft-defender-endpoint-android.md)
- [Distribuzione di Microsoft Defender per Endpoint per Android con Microsoft Intune](android-intune.md)
