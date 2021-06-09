---
title: Panoramica integrazione di Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender for Endpoint si integra con Cloud App Security inoltrando tutte le attività di rete delle app cloud.
keywords: cloud, app, rete, visibilità, utilizzo
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
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844743"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Microsoft Cloud App Security in Panoramica di Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) è una soluzione completa che offre visibilità sulle app e sui servizi cloud consentendo di controllare e limitare l'accesso alle app cloud, nell'applicazione dei requisiti di conformità ai dati archiviati nel cloud. Per ulteriori informazioni, vedere [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).

>[!NOTE]
>Questa funzionalità è disponibile con una licenza E5 per Enterprise Mobility + Security [nei](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) dispositivi Windows 10 versione 1809 o successiva.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Integrazione tra Endpoint e Cloud App Security Microsoft Defender 

Cloud App Security'individuazione si basa su log del traffico cloud inoltrati da server proxy e firewall aziendali. Microsoft Defender for Endpoint si integra con Cloud App Security raccogliendo e inoltrando tutte le attività di rete delle app cloud, offrendo una visibilità impareggiabile all'utilizzo delle app cloud. La funzionalità di monitoraggio è incorporata nel dispositivo, fornendo una copertura completa dell'attività di rete.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


L'integrazione offre i seguenti miglioramenti principali all'individuazione Cloud App Security esistente: 

- Disponibile ovunque: poiché l'attività di rete viene raccolta direttamente dall'endpoint, è disponibile ovunque il dispositivo si trovi, all'interno o all'esterno della rete aziendale, in quanto non dipende più dal traffico instradato attraverso il firewall aziendale o i server proxy. 

- Non è necessaria alcuna configurazione: l'inoltro dei registri del traffico cloud Cloud App Security la configurazione del server proxy e del firewall. Con l'integrazione di Defender for Endpoint e Cloud App Security, non è necessaria alcuna configurazione. Basta attivarlo nelle Microsoft Defender Security Center e sei a posto. 

- Contesto di dispositivo: i log del traffico cloud non dispongono del contesto di dispositivo. Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it. 

Per altre informazioni sull'individuazione cloud, vedi [Uso delle app individuate.](/cloud-app-security/discovered-apps)

## <a name="related-topic"></a>Argomento correlato

- [Configurare l'integrazione di Microsoft Cloud App Security.](microsoft-cloud-app-security-config.md)
