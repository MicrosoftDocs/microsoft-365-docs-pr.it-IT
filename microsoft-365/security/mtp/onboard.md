---
title: Configurare e gestire Microsoft Defender per le funzionalità di endpoint
ms.reviewer: ''
description: Configurare e gestire Microsoft Defender per le funzionalità di endpoint quali la riduzione della superficie di attacco e la protezione di prossima generazione
keywords: configurazione, gestione, funzionalità, riduzione della superficie di attacco, protezione di prossima generazione, controlli di sicurezza, rilevamento e risposta di endpoint, ricerca e correzione automatici, controlli di sicurezza, controlli
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: b202b30e218448794eac7588078ff3ac9cfe9ee3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844813"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="f112f-104">Configurare e gestire Microsoft Defender per le funzionalità di endpoint</span><span class="sxs-lookup"><span data-stu-id="f112f-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f112f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f112f-105">**Applies to:**</span></span>

- [<span data-ttu-id="f112f-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f112f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="f112f-107">Configurare e gestire tutte le funzionalità di Microsoft Defender per endpoint per ottenere la migliore protezione per la sicurezza per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f112f-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="f112f-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f112f-108">In this section</span></span> 
<span data-ttu-id="f112f-109">Argomento</span><span class="sxs-lookup"><span data-stu-id="f112f-109">Topic</span></span> | <span data-ttu-id="f112f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f112f-110">Description</span></span> 
:---|:---
[<span data-ttu-id="f112f-111">Configurare le funzionalità di riduzione degli attacchi superficiali</span><span class="sxs-lookup"><span data-stu-id="f112f-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="f112f-112">Assicurando che le impostazioni di configurazione siano impostate correttamente e che vengano applicate le tecniche di attenuazione, questi insiemi di funzionalità resistono agli attacchi e allo sfruttamento.</span><span class="sxs-lookup"><span data-stu-id="f112f-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="f112f-113">Configurare la protezione di prossima generazione</span><span class="sxs-lookup"><span data-stu-id="f112f-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="f112f-114">Configurare la protezione di prossima generazione per individuare tutti i tipi di minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="f112f-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="f112f-115">Configurare le funzionalità di Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="f112f-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="f112f-116">Configurare e gestire in che modo si desidera ottenere Cybersecurity Threat Intelligence da Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="f112f-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="f112f-117">Configurare l'integrazione di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f112f-117">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="f112f-118">Configurare altre soluzioni che si integrano con Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="f112f-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="f112f-119">Supporto per la gestione e l'API</span><span class="sxs-lookup"><span data-stu-id="f112f-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="f112f-120">Tirare gli avvisi alla propria SIEM o utilizzare le API per creare avvisi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f112f-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="f112f-121">Creare e generare report di Power BI.</span><span class="sxs-lookup"><span data-stu-id="f112f-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="f112f-122">Configurare le impostazioni del Centro protezione Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f112f-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="f112f-123">Configurare le impostazioni relative al portale, ad esempio le impostazioni generali, le funzionalità avanzate, abilitare l'anteprima e altre.</span><span class="sxs-lookup"><span data-stu-id="f112f-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



