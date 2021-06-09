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
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="99841-104">Microsoft Cloud App Security in Panoramica di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="99841-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="99841-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="99841-105">**Applies to:**</span></span>
- [<span data-ttu-id="99841-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="99841-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="99841-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99841-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="99841-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="99841-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="99841-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="99841-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="99841-110">Microsoft Cloud App Security (Cloud App Security) è una soluzione completa che offre visibilità sulle app e sui servizi cloud consentendo di controllare e limitare l'accesso alle app cloud, nell'applicazione dei requisiti di conformità ai dati archiviati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="99841-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="99841-111">Per ulteriori informazioni, vedere [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="99841-111">For more information, see [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="99841-112">Questa funzionalità è disponibile con una licenza E5 per Enterprise Mobility + Security [nei](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) dispositivi Windows 10 versione 1809 o successiva.</span><span class="sxs-lookup"><span data-stu-id="99841-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="99841-113">Integrazione tra Endpoint e Cloud App Security Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="99841-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="99841-114">Cloud App Security'individuazione si basa su log del traffico cloud inoltrati da server proxy e firewall aziendali.</span><span class="sxs-lookup"><span data-stu-id="99841-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="99841-115">Microsoft Defender for Endpoint si integra con Cloud App Security raccogliendo e inoltrando tutte le attività di rete delle app cloud, offrendo una visibilità impareggiabile all'utilizzo delle app cloud.</span><span class="sxs-lookup"><span data-stu-id="99841-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="99841-116">La funzionalità di monitoraggio è incorporata nel dispositivo, fornendo una copertura completa dell'attività di rete.</span><span class="sxs-lookup"><span data-stu-id="99841-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="99841-117">L'integrazione offre i seguenti miglioramenti principali all'individuazione Cloud App Security esistente:</span><span class="sxs-lookup"><span data-stu-id="99841-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="99841-118">Disponibile ovunque: poiché l'attività di rete viene raccolta direttamente dall'endpoint, è disponibile ovunque il dispositivo si trovi, all'interno o all'esterno della rete aziendale, in quanto non dipende più dal traffico instradato attraverso il firewall aziendale o i server proxy.</span><span class="sxs-lookup"><span data-stu-id="99841-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="99841-119">Non è necessaria alcuna configurazione: l'inoltro dei registri del traffico cloud Cloud App Security la configurazione del server proxy e del firewall.</span><span class="sxs-lookup"><span data-stu-id="99841-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="99841-120">Con l'integrazione di Defender for Endpoint e Cloud App Security, non è necessaria alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="99841-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="99841-121">Basta attivarlo nelle Microsoft Defender Security Center e sei a posto.</span><span class="sxs-lookup"><span data-stu-id="99841-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="99841-122">Contesto di dispositivo: i log del traffico cloud non dispongono del contesto di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="99841-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="99841-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span><span class="sxs-lookup"><span data-stu-id="99841-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="99841-124">Per altre informazioni sull'individuazione cloud, vedi [Uso delle app individuate.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="99841-124">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="99841-125">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="99841-125">Related topic</span></span>

- [<span data-ttu-id="99841-126">Configurare l'integrazione di Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="99841-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
