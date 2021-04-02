---
title: Proteggere l'organizzazione dalle minacce Web
description: Informazioni sulla protezione Web in Microsoft Defender ATP e su come può proteggere l'organizzazione.
keywords: protezione Web, protezione dalle minacce Web, esplorazione Web, sicurezza, phishing, malware, exploit, siti Web, protezione di rete, Edge, Internet Explorer, Chrome, Firefox, web browser
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: aeeea02ca1ef2d37623e9ab434b162237c2f4946
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499901"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="c6808-104">Proteggere l'organizzazione dalle minacce Web</span><span class="sxs-lookup"><span data-stu-id="c6808-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c6808-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c6808-105">**Applies to:**</span></span>
- [<span data-ttu-id="c6808-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c6808-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c6808-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6808-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c6808-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c6808-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c6808-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c6808-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="c6808-110">La protezione dalle minacce Web fa [parte della protezione Web](web-protection-overview.md) in Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c6808-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="c6808-111">Usa la [protezione di rete](network-protection.md) per proteggere i dispositivi dalle minacce Web.</span><span class="sxs-lookup"><span data-stu-id="c6808-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="c6808-112">Grazie all'integrazione con Microsoft Edge e i browser di terze parti più diffusi come Chrome e Firefox, La protezione dalle minacce Web interrompe le minacce Web senza un proxy Web e può proteggere i dispositivi mentre sono in locale o in locale.</span><span class="sxs-lookup"><span data-stu-id="c6808-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="c6808-113">La protezione dalle minacce Web interrompe l'accesso ai siti di phishing, ai vettori di malware, ai siti di exploit, a siti non attendibili o a bassa reputazione, nonché ai siti bloccati [nell'elenco degli indicatori personalizzati.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="c6808-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="c6808-114">I dispositivi possono richiedere fino a un'ora per ricevere nuovi indicatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c6808-114">It can take up to an hour for devices to receive new custom indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c6808-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c6808-115">Prerequisites</span></span>
<span data-ttu-id="c6808-116">La protezione Web usa la protezione di rete per garantire la sicurezza dell'esplorazione Web in Microsoft Edge e nei Web browser di terze parti.</span><span class="sxs-lookup"><span data-stu-id="c6808-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="c6808-117">Per attivare la protezione di rete nei dispositivi:</span><span class="sxs-lookup"><span data-stu-id="c6808-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="c6808-118">Modificare la linea di base per la sicurezza di Defender per endpoint in **Protezione di rete &** Web per abilitare la protezione di rete prima di distribuirla o ridistribuirla.</span><span class="sxs-lookup"><span data-stu-id="c6808-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="c6808-119">Informazioni su come esaminare e assegnare la baseline di sicurezza di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c6808-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="c6808-120">Attivare la protezione di rete usando la configurazione del dispositivo Intune, SCCM, Criteri di gruppo o la soluzione MDM.</span><span class="sxs-lookup"><span data-stu-id="c6808-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="c6808-121">Altre informazioni sull'abilitazione della protezione di rete</span><span class="sxs-lookup"><span data-stu-id="c6808-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="c6808-122">Se si imposta la protezione di rete **solo su Controlla**, il blocco non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="c6808-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="c6808-123">Inoltre, sarà possibile rilevare e registrare i tentativi di accesso a siti Web dannosi e indesiderati solo in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="c6808-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c6808-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c6808-124">Related topics</span></span>

- [<span data-ttu-id="c6808-125">Panoramica protezione Web</span><span class="sxs-lookup"><span data-stu-id="c6808-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="c6808-126">Protezione dalle minacce sul Web</span><span class="sxs-lookup"><span data-stu-id="c6808-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="c6808-127">Monitorare la sicurezza sul Web</span><span class="sxs-lookup"><span data-stu-id="c6808-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="c6808-128">Rispondere alle minacce sul Web</span><span class="sxs-lookup"><span data-stu-id="c6808-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="c6808-129">Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="c6808-129">Network protection</span></span>](network-protection.md)
