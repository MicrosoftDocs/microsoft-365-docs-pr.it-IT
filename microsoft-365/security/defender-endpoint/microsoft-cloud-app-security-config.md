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
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="863f8-104">Configurare Microsoft Cloud App Security in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="863f8-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="863f8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="863f8-105">**Applies to:**</span></span>
- [<span data-ttu-id="863f8-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="863f8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="863f8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="863f8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="863f8-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="863f8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="863f8-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="863f8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="863f8-110">Per trarre vantaggio dai segnali di individuazione delle app cloud di Microsoft Defender for Endpoint, attiva l'integrazione di Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="863f8-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="863f8-111">Questa funzionalità sarà disponibile con una licenza E5 per [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) nei dispositivi che eseguono Windows 10 versione 1709 (OS Build 16299.1085 con [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, versione 1803 (OS Build 17134.704 con [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10 versione 1809 (OS Build 17763.379 con [KB4489899](https://support.microsoft.com/help/4489899)) o versioni successive di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="863f8-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="863f8-112">Vedi [Microsoft Defender per l'integrazione degli endpoint con Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) per un'integrazione dettagliata di Microsoft Defender for Endpoint con Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="863f8-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="863f8-113">Abilitare Microsoft Cloud App Security in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="863f8-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="863f8-114">Nel riquadro di spostamento seleziona **Impostazioni preferenze**  >  **Funzionalità avanzate.**</span><span class="sxs-lookup"><span data-stu-id="863f8-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="863f8-115">Seleziona **Microsoft Cloud App Security** e imposta l'interruttore su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="863f8-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="863f8-116">Fare **clic su Salva preferenze.**</span><span class="sxs-lookup"><span data-stu-id="863f8-116">Click **Save preferences**.</span></span>

<span data-ttu-id="863f8-117">Una volta attivato, Microsoft Defender for Endpoint inizierà immediatamente l'inoltro dei segnali di individuazione a Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="863f8-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="863f8-118">Visualizzare i dati raccolti</span><span class="sxs-lookup"><span data-stu-id="863f8-118">View the data collected</span></span>

<span data-ttu-id="863f8-119">Per visualizzare e accedere ai dati di Microsoft Defender for Endpoint in Microsoft Cloud Apps Security, vedi [Analizzare i dispositivi in Cloud App Security.](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="863f8-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="863f8-120">Per altre informazioni sull'individuazione cloud, vedi [Uso delle app individuate.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="863f8-120">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="863f8-121">Se si è interessati a provare Microsoft Cloud App Security, vedere [Versione di valutazione di Microsoft Cloud App Security.](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)</span><span class="sxs-lookup"><span data-stu-id="863f8-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="863f8-122">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="863f8-122">Related topic</span></span>
- [<span data-ttu-id="863f8-123">Integrazione di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="863f8-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
