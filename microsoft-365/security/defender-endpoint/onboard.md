---
title: Configurare e gestire le funzionalità di Microsoft Defender ATP
ms.reviewer: ''
description: Configurare e gestire le funzionalità di Microsoft Defender ATP, ad esempio la riduzione della superficie di attacco e la protezione di nuova generazione
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e2082929cf1fb7f4b55331cf62adcd9b936168d0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061078"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="a0e4b-104">Configurare e gestire le funzionalità di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a0e4b-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a0e4b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a0e4b-105">**Applies to:**</span></span>
- [<span data-ttu-id="a0e4b-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a0e4b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="a0e4b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0e4b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a0e4b-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a0e4b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a0e4b-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a0e4b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="a0e4b-110">Configura e gestisci tutte le funzionalità di Defender for Endpoint per ottenere la protezione di sicurezza migliore per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0e4b-110">Configure and manage all the Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="a0e4b-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a0e4b-111">In this section</span></span> 
<span data-ttu-id="a0e4b-112">Argomento</span><span class="sxs-lookup"><span data-stu-id="a0e4b-112">Topic</span></span> | <span data-ttu-id="a0e4b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0e4b-113">Description</span></span> 
:---|:---
[<span data-ttu-id="a0e4b-114">Configurare le funzionalità di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="a0e4b-114">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) |  <span data-ttu-id="a0e4b-115">Assicurandosi che le impostazioni di configurazione siano impostate correttamente e che le tecniche di mitigazione degli exploit siano applicate, questo set di funzionalità resiste agli attacchi e allo sfruttamento.</span><span class="sxs-lookup"><span data-stu-id="a0e4b-115">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="a0e4b-116">Configurare la protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="a0e4b-116">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="a0e4b-117">Configurare la protezione di nuova generazione per rilevare tutti i tipi di minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="a0e4b-117">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="a0e4b-118">Configurare le funzionalità di Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="a0e4b-118">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="a0e4b-119">Configurare e gestire il modo in cui si desidera ottenere l'intelligence sulle minacce per la sicurezza informatica da Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="a0e4b-119">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="a0e4b-120">Configurare l'integrazione di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a0e4b-120">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration)| <span data-ttu-id="a0e4b-121">Configurare altre soluzioni che si integrano con Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a0e4b-121">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="a0e4b-122">Gestione e supporto api</span><span class="sxs-lookup"><span data-stu-id="a0e4b-122">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis)| <span data-ttu-id="a0e4b-123">Eseguire il pull degli avvisi nel SIEM o usare le API per creare avvisi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a0e4b-123">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="a0e4b-124">Creare e creare report di Power BI.</span><span class="sxs-lookup"><span data-stu-id="a0e4b-124">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="a0e4b-125">Configurare le impostazioni di Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="a0e4b-125">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) |  <span data-ttu-id="a0e4b-126">Configurare le impostazioni relative al portale, ad esempio le impostazioni generali, le funzionalità avanzate, abilitare l'esperienza di anteprima e altre.</span><span class="sxs-lookup"><span data-stu-id="a0e4b-126">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



