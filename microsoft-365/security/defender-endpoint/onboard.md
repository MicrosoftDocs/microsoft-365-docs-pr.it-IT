---
title: Configurare e gestire le funzionalità di Microsoft Defender for Endpoint
ms.reviewer: ''
description: Configurare e gestire le funzionalità di Microsoft Defender for Endpoint, ad esempio la riduzione della superficie di attacco e la protezione di nuova generazione
keywords: configurare, gestire, funzionalità, riduzione della superficie di attacco, protezione di nuova generazione, controlli di sicurezza, rilevamento e risposta degli endpoint, analisi e correzione automatica, controlli di sicurezza, controlli
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c58d7d4192afd0aa13a5ffb0c7f3204b4eaf0315
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844407"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="441f8-104">Configurare e gestire le funzionalità di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="441f8-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="441f8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="441f8-105">**Applies to:**</span></span>

- [<span data-ttu-id="441f8-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="441f8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="441f8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="441f8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="441f8-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="441f8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="441f8-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="441f8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="441f8-110">Scopri come configurare e gestire le funzionalità di Defender for Endpoint per ottenere la migliore protezione della sicurezza per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="441f8-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="441f8-111">Per consigli pratici sulla connessione di nuovi dispositivi nell'organizzazione, vedere [Onboard devices to the Microsoft Defender for Endpoint service.](./onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="441f8-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="441f8-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="441f8-112">In this section</span></span>

<span data-ttu-id="441f8-113">Argomento</span><span class="sxs-lookup"><span data-stu-id="441f8-113">Topic</span></span> | <span data-ttu-id="441f8-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="441f8-114">Description</span></span>
:---|:---
[<span data-ttu-id="441f8-115">Configurare Microsoft Defender Security Center impostazioni</span><span class="sxs-lookup"><span data-stu-id="441f8-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="441f8-116">Configurare le impostazioni correlate al portale, ad esempio impostazioni generali, funzionalità avanzate o abilitare l'esperienza di anteprima.</span><span class="sxs-lookup"><span data-stu-id="441f8-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="441f8-117">Configurare le funzionalità per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="441f8-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="441f8-118">Configurare le funzionalità di riduzione della superficie di attacco, per garantire che le impostazioni siano applicate correttamente e che le tecniche di mitigazione degli exploit siano impostate.</span><span class="sxs-lookup"><span data-stu-id="441f8-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="441f8-119">Configurare la protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="441f8-119">Configure next-generation protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="441f8-120">Configurare la protezione di nuova generazione per rilevare tutti i tipi di minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="441f8-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="441f8-121">Configurare Microsoft Threat Experts funzionalità</span><span class="sxs-lookup"><span data-stu-id="441f8-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="441f8-122">Configurare e gestire l'intelligence sulle minacce per la sicurezza informatica da Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="441f8-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="441f8-123">Configurare l'integrazione Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="441f8-123">Configure Microsoft 365 Defender integration</span></span>](/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="441f8-124">Configurare altre soluzioni che si integrano con Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="441f8-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="441f8-125">Gestione e supporto api</span><span class="sxs-lookup"><span data-stu-id="441f8-125">Management and API support</span></span>](/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="441f8-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span><span class="sxs-lookup"><span data-stu-id="441f8-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="441f8-127">Creare e compilare Power BI report.</span><span class="sxs-lookup"><span data-stu-id="441f8-127">Create and build Power BI reports.</span></span>
