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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a0191a52c64b32b314d4b2f2f36c85b060226ad6
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984653"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="49cf9-104">Note sulla versione di Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="49cf9-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="49cf9-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="49cf9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="49cf9-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="49cf9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="49cf9-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="49cf9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="49cf9-108">Le informazioni seguenti elencano gli aggiornamenti apportati alle API di Microsoft Defender per endpoint e le date in cui sono stati effettuati.</span><span class="sxs-lookup"><span data-stu-id="49cf9-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="49cf9-109">Feed RSS: ricevere una notifica quando questa pagina viene aggiornata copiando e incollando l'URL seguente nel lettore di feed:</span><span class="sxs-lookup"><span data-stu-id="49cf9-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a><span data-ttu-id="49cf9-110">Note sulla versione - dal più recente al meno recente (gg.mm.aaaa)</span><span class="sxs-lookup"><span data-stu-id="49cf9-110">Release notes - newest to oldest (dd.mm.yyyy)</span></span>

### <a name="06102021"></a><span data-ttu-id="49cf9-111">06.10.2021</span><span class="sxs-lookup"><span data-stu-id="49cf9-111">06.10.2021</span></span>

- <span data-ttu-id="49cf9-112">È stato aggiunto il nuovo metodo API di valutazione dell'esportazione - _Delta Export software vulnerabilities assessment (OData)_ [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span><span class="sxs-lookup"><span data-stu-id="49cf9-112">Added new Export assessment API method  - _Delta Export software vulnerabilities assessment (OData)_ [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="05252021"></a><span data-ttu-id="49cf9-113">05.25.2021</span><span class="sxs-lookup"><span data-stu-id="49cf9-113">05.25.2021</span></span>

- <span data-ttu-id="49cf9-114">Sono stati aggiunti nuovi metodi [e proprietà di valutazione per l'esportazione delle](get-assessment-methods-properties.md)API per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49cf9-114">Added new API [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="03052021"></a><span data-ttu-id="49cf9-115">03.05.2021</span><span class="sxs-lookup"><span data-stu-id="49cf9-115">03.05.2021</span></span>

- <span data-ttu-id="49cf9-116">È stata aggiunta una nuova API: [proprietà e metodi di attività di correzione.](get-remediation-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="49cf9-116">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="49cf9-117">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="49cf9-117">10.02.2021</span></span>

- <span data-ttu-id="49cf9-118">Aggiunta nuova API: [Avvisi di aggiornamento in batch](batch-update-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="49cf9-118">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="49cf9-119">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="49cf9-119">25.01.2021</span></span>

- <span data-ttu-id="49cf9-120">Limitazioni di frequenza aggiornate per [l'API Advanced Hunting](run-advanced-query-api.md) da 15 a 45 richieste al minuto.</span><span class="sxs-lookup"><span data-stu-id="49cf9-120">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="49cf9-121">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="49cf9-121">21.01.2021</span></span>

- <span data-ttu-id="49cf9-122">Aggiunta di una nuova API: [Trova i dispositivi in base al tag](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="49cf9-122">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="49cf9-123">Aggiunta nuova API: [Importa indicatori](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="49cf9-123">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="49cf9-124">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="49cf9-124">03.01.2021</span></span>

- <span data-ttu-id="49cf9-125">Evidenza dell'avviso aggiornata: aggiunte ***proprietà detectionStatus** _, _*_parentProcessFilePath_*_ e _ *_parentProcessFileName_** .</span><span class="sxs-lookup"><span data-stu-id="49cf9-125">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="49cf9-126">Entità [alert aggiornata](alerts.md): aggiunta della proprietà ***detectorId.***</span><span class="sxs-lookup"><span data-stu-id="49cf9-126">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="49cf9-127">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="49cf9-127">15.12.2020</span></span>

- <span data-ttu-id="49cf9-128">Entità [Device](machine.md) aggiornata: aggiunto ***l'elenco IpInterfaces.***</span><span class="sxs-lookup"><span data-stu-id="49cf9-128">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="49cf9-129">Vedi [Elencare i dispositivi](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="49cf9-129">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="49cf9-130">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="49cf9-130">04.11.2020</span></span>

- <span data-ttu-id="49cf9-131">Aggiunta nuova API: [Imposta valore dispositivo](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="49cf9-131">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="49cf9-132">Entità [Device](machine.md) aggiornata: aggiunta ***della proprietà deviceValue.***</span><span class="sxs-lookup"><span data-stu-id="49cf9-132">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="49cf9-133">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="49cf9-133">01.09.2020</span></span>

- <span data-ttu-id="49cf9-134">È stata aggiunta un'opzione per espandere l'entità Avviso con l'evidenza correlata.</span><span class="sxs-lookup"><span data-stu-id="49cf9-134">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="49cf9-135">Vedere [Avvisi elenco](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="49cf9-135">See [List Alerts](get-alerts.md).</span></span>
