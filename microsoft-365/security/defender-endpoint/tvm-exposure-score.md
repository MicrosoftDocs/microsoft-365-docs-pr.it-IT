---
title: Punteggio di esposizione nella gestione delle minacce e delle vulnerabilità
description: Il punteggio di esposizione alla gestione delle minacce e delle vulnerabilità riflette la vulnerabilità dell'organizzazione alle minacce di cybersecurity.
keywords: punteggio di esposizione, punteggio di esposizione mdatp, punteggio di esposizione mdatp tvm, punteggio di esposizione dell'organizzazione, punteggio di esposizione dell'organizzazione tvm, gestione delle minacce e delle vulnerabilità, Microsoft Defender for Endpoint
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34c3122b017b14605fdbb3358f31f73e26361a4d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500122"
---
# <a name="exposure-score---threat-and-vulnerability-management"></a><span data-ttu-id="a2afe-104">Punteggio di esposizione - Gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="a2afe-104">Exposure score - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a2afe-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a2afe-105">**Applies to:**</span></span>

- [<span data-ttu-id="a2afe-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a2afe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a2afe-107">Gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="a2afe-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a2afe-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2afe-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a2afe-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a2afe-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a2afe-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a2afe-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="a2afe-111">Il punteggio di esposizione è visibile nel [dashboard di gestione](tvm-dashboard-insights.md) delle minacce e delle vulnerabilità di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="a2afe-111">Your exposure score is visible in the [Threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="a2afe-112">Riflette la vulnerabilità dell'organizzazione alle minacce alla cybersecurity.</span><span class="sxs-lookup"><span data-stu-id="a2afe-112">It reflects how vulnerable your organization is to cybersecurity threats.</span></span> <span data-ttu-id="a2afe-113">Il punteggio di esposizione basso indica che i dispositivi sono meno vulnerabili dallo sfruttamento.</span><span class="sxs-lookup"><span data-stu-id="a2afe-113">Low exposure score means your devices are less vulnerable from exploitation.</span></span>

- <span data-ttu-id="a2afe-114">Comprendere e identificare rapidamente le informazioni di alto livello sullo stato di sicurezza nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2afe-114">Quickly understand and identify high-level takeaways about the state of security in your organization.</span></span>
- <span data-ttu-id="a2afe-115">Rilevare e rispondere alle aree che richiedono indagini o azioni per migliorare lo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="a2afe-115">Detect and respond to areas that require investigation or action to improve the current state.</span></span>
- <span data-ttu-id="a2afe-116">Comunicare con i peer e la gestione sull'impatto degli sforzi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a2afe-116">Communicate with peers and management about the impact of security efforts.</span></span>

<span data-ttu-id="a2afe-117">La scheda offre una visualizzazione di alto livello della tendenza del punteggio di esposizione nel tempo.</span><span class="sxs-lookup"><span data-stu-id="a2afe-117">The card gives you a high-level view of your exposure score trend over time.</span></span> <span data-ttu-id="a2afe-118">Eventuali picchi nel grafico offrono un'indicazione visiva di un'elevata esposizione alle minacce di cybersecurity che è possibile analizzare ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="a2afe-118">Any spikes in the chart give you a visual indication of a high cybersecurity threat exposure that you can investigate further.</span></span>

![Scheda punteggio esposizione](images/tvm_exp_score.png)

## <a name="how-it-works"></a><span data-ttu-id="a2afe-120">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="a2afe-120">How it works</span></span>

<span data-ttu-id="a2afe-121">Il punteggio di esposizione è suddiviso nei livelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2afe-121">The exposure score is broken down into the following levels:</span></span>

- <span data-ttu-id="a2afe-122">0-29: punteggio di esposizione basso</span><span class="sxs-lookup"><span data-stu-id="a2afe-122">0–29: low exposure score</span></span>
- <span data-ttu-id="a2afe-123">30-69: punteggio di esposizione medio</span><span class="sxs-lookup"><span data-stu-id="a2afe-123">30–69: medium exposure score</span></span>
- <span data-ttu-id="a2afe-124">70-100: punteggio di esposizione elevata</span><span class="sxs-lookup"><span data-stu-id="a2afe-124">70–100: high exposure score</span></span>

<span data-ttu-id="a2afe-125">È possibile correggere i problemi in base ai consigli di sicurezza con priorità [per](tvm-security-recommendation.md) ridurre il punteggio di esposizione.</span><span class="sxs-lookup"><span data-stu-id="a2afe-125">You can remediate the issues based on prioritized [security recommendations](tvm-security-recommendation.md) to reduce the exposure score.</span></span> <span data-ttu-id="a2afe-126">Ogni software presenta punti deboli che vengono trasformati in consigli e classificati in ordine di priorità in base ai rischi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2afe-126">Each software has weaknesses that are transformed into recommendations and prioritized based on risk to the organization.</span></span>

## <a name="reduce-your-threat-and-vulnerability-exposure"></a><span data-ttu-id="a2afe-127">Ridurre la minaccia e l'esposizione alle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="a2afe-127">Reduce your threat and vulnerability exposure</span></span>

<span data-ttu-id="a2afe-128">Ridurre l'esposizione alle minacce e alle vulnerabilità corredando i [suggerimenti per la sicurezza.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="a2afe-128">Lower your threat and vulnerability exposure by remediating [security recommendations](tvm-security-recommendation.md).</span></span> <span data-ttu-id="a2afe-129">Per ottenere il massimo impatto sul punteggio di esposizione, correggere i principali suggerimenti per la sicurezza, che possono essere visualizzati nel dashboard di gestione delle minacce [e delle vulnerabilità.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="a2afe-129">Make the most impact to your exposure score by remediating the top security recommendations, which can be viewed in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2afe-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a2afe-130">Related topics</span></span>

- [<span data-ttu-id="a2afe-131">Panoramica della gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="a2afe-131">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a2afe-132">Punteggio di sicurezza Microsoft per dispositivi</span><span class="sxs-lookup"><span data-stu-id="a2afe-132">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="a2afe-133">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="a2afe-133">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="a2afe-134">Sequenza temporale eventi</span><span class="sxs-lookup"><span data-stu-id="a2afe-134">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
