---
title: Panoramica dell'integrazione di Microsoft Cloud App Security
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
ms.openlocfilehash: 6ea885c17cf506ef6f9a4a7138630aed671f0ce8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066290"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="337c2-104">Panoramica di Microsoft Cloud App Security in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="337c2-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="337c2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="337c2-105">**Applies to:**</span></span>
- [<span data-ttu-id="337c2-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="337c2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="337c2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="337c2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="337c2-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="337c2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="337c2-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="337c2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="337c2-110">Microsoft Cloud App Security (Cloud App Security) è una soluzione completa che offre visibilità sulle app e sui servizi cloud consentendoti di controllare e limitare l'accesso alle app cloud, nell'applicazione dei requisiti di conformità ai dati archiviati nel cloud.</span><span class="sxs-lookup"><span data-stu-id="337c2-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="337c2-111">Per altre informazioni, vedi [Cloud App Security.](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="337c2-111">For more information, see [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="337c2-112">Questa funzionalità è disponibile con una licenza E5 per [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) nei dispositivi che eseguono Windows 10 versione 1809 o successiva.</span><span class="sxs-lookup"><span data-stu-id="337c2-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="337c2-113">Integrazione di Microsoft Defender per Endpoint e Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="337c2-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="337c2-114">L'individuazione di Cloud App Security si basa sul fatto che i registri del traffico cloud vengono inoltrati da server proxy e firewall aziendali.</span><span class="sxs-lookup"><span data-stu-id="337c2-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="337c2-115">Microsoft Defender for Endpoint si integra con Cloud App Security raccogliendo e inoltrando tutte le attività di rete delle app cloud, offrendo una visibilità impareggiabile all'utilizzo delle app cloud.</span><span class="sxs-lookup"><span data-stu-id="337c2-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="337c2-116">La funzionalità di monitoraggio è incorporata nel dispositivo, fornendo una copertura completa dell'attività di rete.</span><span class="sxs-lookup"><span data-stu-id="337c2-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="337c2-117">L'integrazione offre i seguenti miglioramenti principali all'individuazione di Cloud App Security esistente:</span><span class="sxs-lookup"><span data-stu-id="337c2-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="337c2-118">Disponibile ovunque: poiché l'attività di rete viene raccolta direttamente dall'endpoint, è disponibile ovunque il dispositivo si trovi, all'interno o all'esterno della rete aziendale, in quanto non dipende più dal traffico instradato attraverso il firewall aziendale o i server proxy.</span><span class="sxs-lookup"><span data-stu-id="337c2-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="337c2-119">Non è necessaria alcuna configurazione: l'inoltro dei log del traffico cloud a Cloud App Security richiede la configurazione del firewall e del server proxy.</span><span class="sxs-lookup"><span data-stu-id="337c2-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="337c2-120">Con l'integrazione di Defender per Endpoint e Cloud App Security, non è necessaria alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="337c2-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="337c2-121">Basta attivarlo nelle impostazioni di Microsoft Defender Security Center e sei a posto.</span><span class="sxs-lookup"><span data-stu-id="337c2-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="337c2-122">Contesto di dispositivo: i log del traffico cloud non dispongono del contesto di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="337c2-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="337c2-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span><span class="sxs-lookup"><span data-stu-id="337c2-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="337c2-124">Per altre informazioni sull'individuazione cloud, vedi [Uso delle app individuate.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="337c2-124">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="337c2-125">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="337c2-125">Related topic</span></span>

- [<span data-ttu-id="337c2-126">Configurare l'integrazione di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="337c2-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
