---
title: Assegnare il valore del dispositivo - gestione delle minacce e delle vulnerabilità
description: Scopri come assegnare un valore basso, normale o elevato a un dispositivo per distinguere le priorità degli asset.
keywords: valore del dispositivo microsoft defender atp, valore del dispositivo di gestione delle minacce e delle vulnerabilità, dispositivi ad alto valore, punteggio di esposizione al valore del dispositivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: be578158e18d55bb25d450749c3fb4373854456b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065997"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="43dd4-104">Assegnare il valore del dispositivo - gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="43dd4-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="43dd4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="43dd4-105">**Applies to:**</span></span>

- [<span data-ttu-id="43dd4-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="43dd4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="43dd4-107">Gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="43dd4-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="43dd4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43dd4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="43dd4-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="43dd4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="43dd4-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="43dd4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="43dd4-111">La definizione del valore di un dispositivo consente di distinguere le priorità degli asset.</span><span class="sxs-lookup"><span data-stu-id="43dd4-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="43dd4-112">Il valore del dispositivo viene utilizzato per incorporare la propensione al rischio di un singolo asset nel calcolo del punteggio di esposizione alla gestione delle minacce e delle vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="43dd4-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="43dd4-113">I dispositivi assegnati come "valore elevato" riceveranno più peso.</span><span class="sxs-lookup"><span data-stu-id="43dd4-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="43dd4-114">Puoi anche usare [l'API set device value](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="43dd4-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="43dd4-115">Opzioni valore dispositivo:</span><span class="sxs-lookup"><span data-stu-id="43dd4-115">Device value options:</span></span>

- <span data-ttu-id="43dd4-116">Basso</span><span class="sxs-lookup"><span data-stu-id="43dd4-116">Low</span></span>
- <span data-ttu-id="43dd4-117">Normale (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="43dd4-117">Normal (Default)</span></span>
- <span data-ttu-id="43dd4-118">Alto</span><span class="sxs-lookup"><span data-stu-id="43dd4-118">High</span></span>

<span data-ttu-id="43dd4-119">Esempi di dispositivi a cui assegnare un valore elevato:</span><span class="sxs-lookup"><span data-stu-id="43dd4-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="43dd4-120">Controller di dominio, Active Directory</span><span class="sxs-lookup"><span data-stu-id="43dd4-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="43dd4-121">Dispositivi con connessione Internet</span><span class="sxs-lookup"><span data-stu-id="43dd4-121">Internet facing devices</span></span>
- <span data-ttu-id="43dd4-122">Dispositivi VIP</span><span class="sxs-lookup"><span data-stu-id="43dd4-122">VIP devices</span></span>
- <span data-ttu-id="43dd4-123">Dispositivi che ospitano servizi di produzione interni/esterni</span><span class="sxs-lookup"><span data-stu-id="43dd4-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="43dd4-124">Scegliere il valore del dispositivo</span><span class="sxs-lookup"><span data-stu-id="43dd4-124">Choose device value</span></span>

1. <span data-ttu-id="43dd4-125">Passare a qualsiasi pagina del dispositivo, il posto più semplice è dall'inventario dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="43dd4-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="43dd4-126">Seleziona **Valore dispositivo** da tre punti accanto alla barra delle azioni nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="43dd4-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![Esempio dell'elenco a discesa del valore del dispositivo.](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="43dd4-128">Verrà visualizzato un riquadro a comparsa con il valore corrente del dispositivo e il relativo significato.</span><span class="sxs-lookup"><span data-stu-id="43dd4-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="43dd4-129">Esamina il valore del dispositivo e scegli quello più adatto al tuo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43dd4-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="43dd4-130">![Esempio del riquadro a comparsa del valore del dispositivo.](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="43dd4-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="43dd4-131">Impatto del valore del dispositivo sul punteggio di esposizione</span><span class="sxs-lookup"><span data-stu-id="43dd4-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="43dd4-132">Il punteggio di esposizione è una media ponderata in tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="43dd4-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="43dd4-133">Se hai gruppi di dispositivi, puoi anche filtrare il punteggio in base al gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="43dd4-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="43dd4-134">I dispositivi normali hanno un peso di 1</span><span class="sxs-lookup"><span data-stu-id="43dd4-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="43dd4-135">I dispositivi a basso valore hanno un peso di 0,75</span><span class="sxs-lookup"><span data-stu-id="43dd4-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="43dd4-136">I dispositivi ad alto valore hanno un peso di NumberOfAssets / 10.</span><span class="sxs-lookup"><span data-stu-id="43dd4-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="43dd4-137">Se hai 100 dispositivi, ogni dispositivo ad alto valore avrà un peso di 10 (100/10)</span><span class="sxs-lookup"><span data-stu-id="43dd4-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="43dd4-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="43dd4-138">Related topics</span></span>

- [<span data-ttu-id="43dd4-139">Panoramica della gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="43dd4-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="43dd4-140">Punteggio di esposizione</span><span class="sxs-lookup"><span data-stu-id="43dd4-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="43dd4-141">API</span><span class="sxs-lookup"><span data-stu-id="43dd4-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)