---
title: Note sulla versione di Microsoft Defender for Endpoint API
description: Note sulla versione per gli aggiornamenti apportati al set di API di Microsoft Defender for Endpoint.
keywords: Note sulla versione di Microsoft Defender for Endpoint API, mde, API, Microsoft Defender for Endpoint API, aggiornamenti, note, rilascio
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 5c8e9d8e1c8ec020b4d742f61d276c93f6730bec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245553"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="31c5d-104">Note sulla versione di Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="31c5d-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="31c5d-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="31c5d-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="31c5d-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="31c5d-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="31c5d-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="31c5d-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="31c5d-108">Le informazioni seguenti elencano gli aggiornamenti apportati alle API di Microsoft Defender per endpoint e le date in cui sono stati effettuati.</span><span class="sxs-lookup"><span data-stu-id="31c5d-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="31c5d-109">Feed RSS: ricevere una notifica quando questa pagina viene aggiornata copiando e incollando l'URL seguente nel lettore di feed:</span><span class="sxs-lookup"><span data-stu-id="31c5d-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a><span data-ttu-id="31c5d-110">Note sulla versione - dal più recente al meno recente (gg.mm.aaaa)</span><span class="sxs-lookup"><span data-stu-id="31c5d-110">Release notes - newest to oldest (dd.mm.yyyy)</span></span>

### <a name="03052021"></a><span data-ttu-id="31c5d-111">03.05.2021</span><span class="sxs-lookup"><span data-stu-id="31c5d-111">03.05.2021</span></span>

- <span data-ttu-id="31c5d-112">È stata aggiunta una nuova API: [proprietà e metodi di attività di correzione.](get-remediation-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="31c5d-112">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="31c5d-113">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="31c5d-113">10.02.2021</span></span>

- <span data-ttu-id="31c5d-114">Aggiunta nuova API: [Avvisi di aggiornamento in batch](batch-update-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="31c5d-114">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="31c5d-115">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="31c5d-115">25.01.2021</span></span>

- <span data-ttu-id="31c5d-116">Limitazioni di frequenza aggiornate per [l'API Advanced Hunting](run-advanced-query-api.md) da 15 a 45 richieste al minuto.</span><span class="sxs-lookup"><span data-stu-id="31c5d-116">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="31c5d-117">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="31c5d-117">21.01.2021</span></span>

- <span data-ttu-id="31c5d-118">Aggiunta di una nuova API: [Trova i dispositivi in base al tag](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="31c5d-118">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="31c5d-119">Aggiunta nuova API: [Importa indicatori](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="31c5d-119">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="31c5d-120">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="31c5d-120">03.01.2021</span></span>

- <span data-ttu-id="31c5d-121">Evidenza dell'avviso aggiornata: aggiunte ***proprietà detectionStatus** _, _*_parentProcessFilePath_*_ e _ *_parentProcessFileName_** .</span><span class="sxs-lookup"><span data-stu-id="31c5d-121">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="31c5d-122">Entità [alert aggiornata](alerts.md): aggiunta della proprietà ***detectorId.***</span><span class="sxs-lookup"><span data-stu-id="31c5d-122">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="31c5d-123">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="31c5d-123">15.12.2020</span></span>

- <span data-ttu-id="31c5d-124">Entità [Device](machine.md) aggiornata: aggiunto ***l'elenco IpInterfaces.***</span><span class="sxs-lookup"><span data-stu-id="31c5d-124">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="31c5d-125">Vedi [Elencare i dispositivi](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="31c5d-125">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="31c5d-126">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="31c5d-126">04.11.2020</span></span>

- <span data-ttu-id="31c5d-127">Aggiunta nuova API: [Imposta valore dispositivo](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="31c5d-127">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="31c5d-128">Entità [Device](machine.md) aggiornata: aggiunta ***della proprietà deviceValue.***</span><span class="sxs-lookup"><span data-stu-id="31c5d-128">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="31c5d-129">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="31c5d-129">01.09.2020</span></span>

- <span data-ttu-id="31c5d-130">È stata aggiunta un'opzione per espandere l'entità Avviso con l'evidenza correlata.</span><span class="sxs-lookup"><span data-stu-id="31c5d-130">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="31c5d-131">Vedere [Avvisi elenco](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="31c5d-131">See [List Alerts](get-alerts.md).</span></span>
