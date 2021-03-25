---
title: Strumenti e metodi di onboarding per i dispositivi Windows 10
description: Onboard dei dispositivi Windows 10 in modo che possano inviare i dati del sensore al sensore Microsoft Defender ATP
keywords: Onboard dei dispositivi Windows 10, criteri di gruppo, gestione della configurazione degli endpoint, gestione dei dispositivi mobili, script locale, criteri di gruppo, sccm, mdm, intune
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
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165538"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a><span data-ttu-id="5255a-104">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="5255a-104">Onboarding tools and methods for Windows 10 devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5255a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5255a-105">**Applies to:**</span></span>
- [<span data-ttu-id="5255a-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5255a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5255a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5255a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="5255a-108">Prevenzione della perdita dei dati di Microsoft 365 Endpoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="5255a-108">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

><span data-ttu-id="5255a-109">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5255a-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5255a-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5255a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="5255a-111">I dispositivi nell'organizzazione devono essere configurati in modo che il servizio Defender for Endpoint possa ottenere i dati del sensore da essi.</span><span class="sxs-lookup"><span data-stu-id="5255a-111">Devices in your organization must be configured so that the Defender for Endpoint service can get sensor data from them.</span></span> <span data-ttu-id="5255a-112">Esistono diversi metodi e strumenti di distribuzione che è possibile utilizzare per configurare i dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5255a-112">There are various methods and deployment tools that you can use to configure the devices in your organization.</span></span>

<span data-ttu-id="5255a-113">Sono supportati gli strumenti e i metodi di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="5255a-113">The following deployment tools and methods are supported:</span></span>

- <span data-ttu-id="5255a-114">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="5255a-114">Group Policy</span></span>
- <span data-ttu-id="5255a-115">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5255a-115">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="5255a-116">Gestione dei dispositivi mobili (incluso Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="5255a-116">Mobile Device Management (including Microsoft Intune)</span></span>
- <span data-ttu-id="5255a-117">Script locale</span><span class="sxs-lookup"><span data-stu-id="5255a-117">Local script</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5255a-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5255a-118">In this section</span></span>
<span data-ttu-id="5255a-119">Argomento</span><span class="sxs-lookup"><span data-stu-id="5255a-119">Topic</span></span> | <span data-ttu-id="5255a-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5255a-120">Description</span></span>
:---|:---
[<span data-ttu-id="5255a-121">Onboardare dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="5255a-121">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md) | <span data-ttu-id="5255a-122">Usa Criteri di gruppo per distribuire il pacchetto di configurazione nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5255a-122">Use Group Policy to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="5255a-123">Onboard dei dispositivi Windows con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5255a-123">Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) | <span data-ttu-id="5255a-124">Puoi usare Microsoft Endpoint Manager (current branch) versione 1606 o Microsoft Endpoint Manager (current branch) versione 1602 o precedente per distribuire il pacchetto di configurazione nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5255a-124">You can use either use Microsoft Endpoint Manager (current branch) version 1606 or Microsoft Endpoint Manager (current branch) version 1602 or earlier to deploy the configuration package on devices.</span></span>
[<span data-ttu-id="5255a-125">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="5255a-125">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md) | <span data-ttu-id="5255a-126">Usa gli strumenti di gestione dei dispositivi mobili o Microsoft Intune per distribuire il pacchetto di configurazione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5255a-126">Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on device.</span></span>
[<span data-ttu-id="5255a-127">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="5255a-127">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md) | <span data-ttu-id="5255a-128">Scopri come usare lo script locale per distribuire il pacchetto di configurazione sugli endpoint.</span><span class="sxs-lookup"><span data-stu-id="5255a-128">Learn how to use the local script to deploy the configuration package on endpoints.</span></span>
[<span data-ttu-id="5255a-129">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti</span><span class="sxs-lookup"><span data-stu-id="5255a-129">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md) | <span data-ttu-id="5255a-130">Scopri come usare il pacchetto di configurazione per configurare i dispositivi VDI.</span><span class="sxs-lookup"><span data-stu-id="5255a-130">Learn how to use the configuration package to configure VDI devices.</span></span>


><span data-ttu-id="5255a-131">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5255a-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5255a-132">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5255a-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
