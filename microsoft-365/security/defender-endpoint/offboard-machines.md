---
title: Dispositivi offboard dal servizio Microsoft Defender for Endpoint
description: Onboard Windows 10 dispositivi, server, dispositivi non Windows dal servizio Microsoft Defender for Endpoint
keywords: offboarding, offboarding di Microsoft Defender per endpoint, offboarding
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
ms.openlocfilehash: 425e5b9e0be12b89c8fd3b7201010b0f776cc6a5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934154"
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
> Inoltre, i dispositivi che non sono attivi negli ultimi 30 giorni non vengono factorati nei [](tvm-exposure-score.md) dati che riflettono il punteggio di esposizione gestione di minacce e vulnerabilità dell'organizzazione e microsoft Secure Score per i dispositivi. <br>
> Per visualizzare solo i dispositivi attivi, è possibile filtrare in base allo [stato di](machines-view-overview.md#health-state)integrità, ai tag [dei dispositivi](machine-tags.md) o ai gruppi [di computer.](machine-groups.md) 

## <a name="offboard-windows-10-devices"></a>Offboard Windows 10 dispositivi
- [Dispositivi offboard con uno script locale](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [Dispositivi offboard con Criteri di gruppo](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [Dispositivi offboard con strumenti di gestione dei dispositivi mobili](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>Server offboard
- [Server offboard](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>Offboard non Windows dispositivi
- [Offboard non Windows dispositivi](configure-endpoints-non-windows.md#offboard-non-windows-devices)

