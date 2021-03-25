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
ms.technology: m365d
ms.openlocfilehash: 95c462829b43ae41c1fe664b2313a716078baea7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064597"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="deef8-104">Configurare e gestire le funzionalità di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="deef8-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="deef8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="deef8-105">**Applies to:**</span></span>

- [<span data-ttu-id="deef8-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="deef8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="deef8-107">Configura e gestisci tutte le funzionalità di Microsoft Defender for Endpoint per ottenere la migliore protezione della sicurezza per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="deef8-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="deef8-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="deef8-108">In this section</span></span> 
<span data-ttu-id="deef8-109">Argomento</span><span class="sxs-lookup"><span data-stu-id="deef8-109">Topic</span></span> | <span data-ttu-id="deef8-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="deef8-110">Description</span></span> 
:---|:---
[<span data-ttu-id="deef8-111">Configurare le funzionalità di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="deef8-111">Configure attack surface reduction capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="deef8-112">Assicurandosi che le impostazioni di configurazione siano impostate correttamente e che le tecniche di mitigazione degli exploit siano applicate, questo set di funzionalità resiste agli attacchi e allo sfruttamento.</span><span class="sxs-lookup"><span data-stu-id="deef8-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="deef8-113">Configurare la protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="deef8-113">Configure next generation protection</span></span>](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="deef8-114">Configurare la protezione di nuova generazione per rilevare tutti i tipi di minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="deef8-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="deef8-115">Configurare le funzionalità di Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="deef8-115">Configure Microsoft Threat Experts capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="deef8-116">Configurare e gestire il modo in cui si desidera ottenere l'intelligence sulle minacce per la sicurezza informatica da Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="deef8-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="deef8-117">Configurare l'integrazione di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="deef8-117">Configure Microsoft 365 Defender integration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="deef8-118">Configurare altre soluzioni che si integrano con Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="deef8-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="deef8-119">Gestione e supporto api</span><span class="sxs-lookup"><span data-stu-id="deef8-119">Management and API support</span></span>](/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="deef8-120">Eseguire il pull degli avvisi nel SIEM o usare le API per creare avvisi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="deef8-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="deef8-121">Creare e creare report di Power BI.</span><span class="sxs-lookup"><span data-stu-id="deef8-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="deef8-122">Configurare le impostazioni di Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="deef8-122">Configure Microsoft Defender Security Center settings</span></span>](/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="deef8-123">Configurare le impostazioni relative al portale, ad esempio le impostazioni generali, le funzionalità avanzate, abilitare l'esperienza di anteprima e altre.</span><span class="sxs-lookup"><span data-stu-id="deef8-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>