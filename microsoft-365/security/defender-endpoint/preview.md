---
title: Funzionalità di anteprima di Microsoft Defender ATP
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
ms.openlocfilehash: 9400d448b2b133f7478ef8ceb01f605c17f36bc9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064949"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="06134-104">Funzionalità di anteprima di Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="06134-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>[!IMPORTANT]
><span data-ttu-id="06134-105">Le versioni di anteprima vengono fornite senza un contratto di servizio e non sono consigliate per i carichi di lavoro di produzione.</span><span class="sxs-lookup"><span data-stu-id="06134-105">The preview versions are provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="06134-106">Alcune funzionalità potrebbero non essere supportate o avere funzionalità vincolate.</span><span class="sxs-lookup"><span data-stu-id="06134-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="06134-107">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="06134-107">**Applies to:**</span></span>
- [<span data-ttu-id="06134-108">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="06134-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="06134-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06134-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="06134-110">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="06134-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="06134-111">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="06134-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="06134-112">Il servizio Defender for Endpoint viene costantemente aggiornato per includere nuovi miglioramenti e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="06134-112">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

> [!TIP]
> <span data-ttu-id="06134-113">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="06134-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="06134-114">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="06134-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-abovefoldlink)

<span data-ttu-id="06134-115">Scopri le nuove funzionalità nella versione di anteprima di Defender for Endpoint ed essere tra i primi a provare le funzionalità future attivando l'esperienza di anteprima.</span><span class="sxs-lookup"><span data-stu-id="06134-115">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="06134-116">Ricevi una notifica quando questa pagina viene aggiornata copiando e incollando l'URL seguente nel lettore di feed: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span><span class="sxs-lookup"><span data-stu-id="06134-116">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22Microsoft+Defender+ATP+preview+features%22&locale=en-us`</span></span>

<span data-ttu-id="06134-117">Per altre informazioni sulle nuove funzionalità disponibili in genere, vedi Novità [di Defender per Endpoint.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="06134-117">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="06134-118">Attivare funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="06134-118">Turn on preview features</span></span>

<span data-ttu-id="06134-119">Avrai accesso alle funzionalità future su cui puoi fornire feedback per migliorare l'esperienza complessiva prima che le funzionalità siano generalmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="06134-119">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="06134-120">Attivare l'opzione esperienza di anteprima per essere tra i primi a provare le funzionalità che saranno introdotte.</span><span class="sxs-lookup"><span data-stu-id="06134-120">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="06134-121">Nel riquadro di spostamento selezionare **Impostazioni Caratteristiche** avanzate  >  **Funzionalità di**  >  **anteprima**.</span><span class="sxs-lookup"><span data-stu-id="06134-121">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="06134-122">Attiva o disattiva **l'impostazione** **e** seleziona Salva **preferenze.**</span><span class="sxs-lookup"><span data-stu-id="06134-122">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="06134-123">Funzionalità di anteprima</span><span class="sxs-lookup"><span data-stu-id="06134-123">Preview features</span></span>

<span data-ttu-id="06134-124">Nella versione di anteprima sono incluse le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="06134-124">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="06134-125">Filtro contenuto Web</span><span class="sxs-lookup"><span data-stu-id="06134-125">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="06134-126">Il filtro contenuto Web fa parte delle funzionalità di protezione Web in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="06134-126">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="06134-127">Consente all'organizzazione di tenere traccia e regolare l'accesso ai siti Web in base alle categorie di contenuto.</span><span class="sxs-lookup"><span data-stu-id="06134-127">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="06134-128">Molti di questi siti Web, sebbene non dannosi, potrebbero essere problematici a causa delle normative di conformità, dell'utilizzo della larghezza di banda o di altri problemi.</span><span class="sxs-lookup"><span data-stu-id="06134-128">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="06134-129">Report integrità e conformità dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="06134-129">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="06134-130">Il report sull'integrità e la conformità dei dispositivi fornisce informazioni di alto livello sui dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="06134-130">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

- [<span data-ttu-id="06134-131">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="06134-131">Information protection</span></span>](information-protection-in-windows-overview.md)<BR>
<span data-ttu-id="06134-132">La protezione delle informazioni è parte integrante della famiglia di prodotti Microsoft 365 Enterprise, offrendo una protezione intelligente per proteggere i dati sensibili, consentendo al contempo la produttività sul luogo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="06134-132">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span> <span data-ttu-id="06134-133">Microsoft Defender for Endpoint è perfettamente integrato in Microsoft Threat Protection per fornire una soluzione completa e completa per la prevenzione della perdita dei dati (DLP) per i dispositivi Windows.</span><span class="sxs-lookup"><span data-stu-id="06134-133">Microsoft Defender for Endpoint is seamlessly integrated in Microsoft Threat Protection to provide a complete and comprehensive data loss prevention (DLP) solution for Windows devices.</span></span>

    >[!NOTE]
    ><span data-ttu-id="06134-134">Parzialmente disponibile da Windows 10, versione 1809.</span><span class="sxs-lookup"><span data-stu-id="06134-134">Partially available from Windows 10, version 1809.</span></span>

- [<span data-ttu-id="06134-135">Onboard di Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="06134-135">Onboard Windows Server 2019</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-version-1803-and-windows-server-2019) <BR> <span data-ttu-id="06134-136">Microsoft Defender for Endpoint ora aggiunge il supporto per Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="06134-136">Microsoft Defender for Endpoint now adds support for Windows Server 2019.</span></span> <span data-ttu-id="06134-137">Potrai eseguire l'onboardboard di Windows Server 2019 nello stesso metodo disponibile per i dispositivi client Windows 10.</span><span class="sxs-lookup"><span data-stu-id="06134-137">You'll be able to onboard Windows Server 2019 in the same method available for Windows 10 client devices.</span></span>


> [!TIP] 
> <span data-ttu-id="06134-138">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="06134-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="06134-139">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="06134-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
