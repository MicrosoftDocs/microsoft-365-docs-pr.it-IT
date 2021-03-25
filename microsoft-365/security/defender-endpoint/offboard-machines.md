---
title: Dispositivi offboard dal servizio Microsoft Defender ATP
description: Onboard di dispositivi Windows 10, server, dispositivi non Windows dal servizio Microsoft Defender ATP
keywords: offboarding, microsoft defender per l'offboarding degli endpoint, offboarding windows atp
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a95ff5214ea9f696622ea184ece1c5aa9fb3db2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186966"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Dispositivi offboard dal servizio Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Piattaforme**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

Seguire le istruzioni corrispondenti a seconda del metodo di distribuzione preferito.

>[!NOTE]
> Lo stato di un dispositivo verrà commutato [su Inattivo](fix-unhealthy-sensors.md#inactive-devices) 7 giorni dopo l'offboarding. <br> I dati dei dispositivi offboarded (ad esempio sequenza temporale, avvisi, vulnerabilità [](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) e così via) rimarranno nel portale fino alla scadenza del periodo di conservazione configurato. <br>
> Il profilo del dispositivo (senza dati) [](machines-view-overview.md) rimarrà nell'elenco dei dispositivi per non più di 180 giorni.
> Inoltre, i dispositivi che non sono attivi negli ultimi 30 giorni non vengono utilizzati nei dati [](tvm-exposure-score.md) che riflettono il punteggio di esposizione della gestione delle minacce e delle vulnerabilità dell'organizzazione e il punteggio microsoft secure per i dispositivi. <br>
> Per visualizzare solo i dispositivi attivi, è possibile filtrare in base allo [stato di](machines-view-overview.md#health-state)integrità, ai tag [dei dispositivi](machine-tags.md) o ai gruppi [di computer.](machine-groups.md) 

## <a name="offboard-windows-10-devices"></a>Offboard dei dispositivi Windows 10
- [Dispositivi offboard con uno script locale](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [Dispositivi offboard con Criteri di gruppo](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Dispositivi offboard con strumenti di gestione dei dispositivi mobili](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Server offboard
- [Server offboard](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Offboard di dispositivi non Windows
- [Offboard di dispositivi non Windows](configure-endpoints-non-windows.md#offboard-non-windows-devices)

