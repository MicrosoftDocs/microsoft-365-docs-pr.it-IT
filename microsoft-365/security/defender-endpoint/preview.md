---
title: Funzionalità di anteprima di Microsoft Defender per Endpoint
description: Scopri come accedere alle funzionalità di anteprima di Microsoft Defender for Endpoint.
keywords: anteprima, esperienza di anteprima, Microsoft Defender for Endpoint, funzionalità, aggiornamenti
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
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0ed494cc29eb990430be590e62db5f0365ace494
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322426"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="f6719-104">Funzionalità di anteprima di Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="f6719-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f6719-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f6719-105">**Applies to:**</span></span>
- [<span data-ttu-id="f6719-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f6719-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f6719-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6719-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f6719-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f6719-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6719-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f6719-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="f6719-110">Il servizio Defender for Endpoint viene costantemente aggiornato per includere nuovi miglioramenti e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f6719-110">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="f6719-111">Scopri le nuove funzionalità nella versione di anteprima di Defender for Endpoint ed essere tra i primi a provare le funzionalità future attivando l'esperienza di anteprima.</span><span class="sxs-lookup"><span data-stu-id="f6719-111">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="f6719-112">Ricevi una notifica quando questa pagina viene aggiornata copiando e incollando l'URL seguente nel lettore di feed: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="f6719-112">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="f6719-113">Per altre informazioni sulle nuove funzionalità disponibili in genere, vedi Novità [di Defender per Endpoint.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="f6719-113">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="f6719-114">Cosa è necessario sapere</span><span class="sxs-lookup"><span data-stu-id="f6719-114">What you need to know</span></span>

<span data-ttu-id="f6719-115">Quando si lavora con le funzionalità in anteprima pubblica, queste funzionalità:</span><span class="sxs-lookup"><span data-stu-id="f6719-115">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="f6719-116">Può avere funzionalità limitate o limitate.</span><span class="sxs-lookup"><span data-stu-id="f6719-116">May have restricted or limited functionality.</span></span> <span data-ttu-id="f6719-117">Ad esempio, la funzionalità può essere applicata solo a una piattaforma.</span><span class="sxs-lookup"><span data-stu-id="f6719-117">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="f6719-118">In genere, le modifiche delle funzionalità vengono apportate prima che siano disponibili in genere.</span><span class="sxs-lookup"><span data-stu-id="f6719-118">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="f6719-119">Sono completamente supportati da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f6719-119">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="f6719-120">Può essere disponibile solo in aree geografiche o ambienti cloud selezionati.</span><span class="sxs-lookup"><span data-stu-id="f6719-120">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="f6719-121">Ad esempio, la funzionalità potrebbe non esistere nel cloud per enti pubblici.</span><span class="sxs-lookup"><span data-stu-id="f6719-121">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="f6719-122">Le singole funzionalità in anteprima possono avere più restrizioni di utilizzo e supporto.</span><span class="sxs-lookup"><span data-stu-id="f6719-122">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="f6719-123">In tal caso, queste informazioni vengono in genere riportate nella documentazione relativa alle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f6719-123">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="f6719-124">Le versioni di anteprima sono fornite con un livello di supporto standard ed è consigliabile per i carichi di lavoro di produzione.</span><span class="sxs-lookup"><span data-stu-id="f6719-124">The preview versions are provided with a standard support level, and it is recommended for production workloads.</span></span> 



## <a name="turn-on-preview-features"></a><span data-ttu-id="f6719-125">Attivare funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="f6719-125">Turn on preview features</span></span>

<span data-ttu-id="f6719-126">Avrai accesso alle funzionalità future su cui puoi fornire feedback per migliorare l'esperienza complessiva prima che le funzionalità siano generalmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="f6719-126">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="f6719-127">Attivare l'opzione esperienza di anteprima per essere tra i primi a provare le funzionalità che saranno introdotte.</span><span class="sxs-lookup"><span data-stu-id="f6719-127">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="f6719-128">Nel riquadro di spostamento selezionare **Impostazioni**  >  **funzionalità avanzate**  >  **Funzionalità di anteprima.**</span><span class="sxs-lookup"><span data-stu-id="f6719-128">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="f6719-129">Attiva o disattiva **l'impostazione** **e** seleziona Salva **preferenze.**</span><span class="sxs-lookup"><span data-stu-id="f6719-129">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="f6719-130">Funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="f6719-130">Preview features</span></span>

<span data-ttu-id="f6719-131">Nella versione di anteprima sono incluse le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6719-131">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="f6719-132">Filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="f6719-132">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="f6719-133">Il filtro contenuto Web fa parte delle funzionalità di protezione Web in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f6719-133">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f6719-134">Consente all'organizzazione di tenere traccia e regolare l'accesso ai siti Web in base alle categorie di contenuto.</span><span class="sxs-lookup"><span data-stu-id="f6719-134">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="f6719-135">Molti di questi siti Web, sebbene non dannosi, potrebbero essere problematici a causa delle normative di conformità, dell'utilizzo della larghezza di banda o di altri problemi.</span><span class="sxs-lookup"><span data-stu-id="f6719-135">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="f6719-136">Report dell'integrità e la conformità dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f6719-136">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="f6719-137">Il report sull'integrità e la conformità dei dispositivi fornisce informazioni di alto livello sui dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f6719-137">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="f6719-138">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f6719-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6719-139">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f6719-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
