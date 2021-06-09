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
ms.openlocfilehash: 4843894638ccf119c0cadcf003e159e793c18368
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843735"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="5a252-104">Note sulla versione di Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="5a252-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="5a252-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5a252-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5a252-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5a252-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5a252-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5a252-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5a252-108">Le informazioni seguenti elencano gli aggiornamenti apportati alle API di Microsoft Defender per endpoint e le date in cui sono stati effettuati.</span><span class="sxs-lookup"><span data-stu-id="5a252-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="5a252-109">Feed RSS: ricevere una notifica quando questa pagina viene aggiornata copiando e incollando l'URL seguente nel lettore di feed:</span><span class="sxs-lookup"><span data-stu-id="5a252-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a><span data-ttu-id="5a252-110">Note sulla versione - dal più recente al meno recente (gg.mm.aaaa)</span><span class="sxs-lookup"><span data-stu-id="5a252-110">Release notes - newest to oldest (dd.mm.yyyy)</span></span>

### <a name="05252021"></a><span data-ttu-id="5a252-111">05.25.2021</span><span class="sxs-lookup"><span data-stu-id="5a252-111">05.25.2021</span></span>

- <span data-ttu-id="5a252-112">Sono stati aggiunti nuovi metodi [e proprietà di valutazione per l'esportazione delle](get-assessment-methods-properties.md)API per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5a252-112">Added new API [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="03052021"></a><span data-ttu-id="5a252-113">03.05.2021</span><span class="sxs-lookup"><span data-stu-id="5a252-113">03.05.2021</span></span>

- <span data-ttu-id="5a252-114">È stata aggiunta una nuova API: [proprietà e metodi di attività di correzione.](get-remediation-methods-properties.md)</span><span class="sxs-lookup"><span data-stu-id="5a252-114">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="5a252-115">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="5a252-115">10.02.2021</span></span>

- <span data-ttu-id="5a252-116">Aggiunta nuova API: [Avvisi di aggiornamento in batch](batch-update-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="5a252-116">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="5a252-117">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="5a252-117">25.01.2021</span></span>

- <span data-ttu-id="5a252-118">Limitazioni di frequenza aggiornate per [l'API Advanced Hunting](run-advanced-query-api.md) da 15 a 45 richieste al minuto.</span><span class="sxs-lookup"><span data-stu-id="5a252-118">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="5a252-119">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="5a252-119">21.01.2021</span></span>

- <span data-ttu-id="5a252-120">Aggiunta di una nuova API: [Trova i dispositivi in base al tag](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="5a252-120">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="5a252-121">Aggiunta nuova API: [Importa indicatori](import-ti-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="5a252-121">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="5a252-122">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="5a252-122">03.01.2021</span></span>

- <span data-ttu-id="5a252-123">Evidenza dell'avviso aggiornata: aggiunte ***proprietà detectionStatus** _, _*_parentProcessFilePath_*_ e _ *_parentProcessFileName_** .</span><span class="sxs-lookup"><span data-stu-id="5a252-123">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="5a252-124">Entità [alert aggiornata](alerts.md): aggiunta della proprietà ***detectorId.***</span><span class="sxs-lookup"><span data-stu-id="5a252-124">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="5a252-125">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="5a252-125">15.12.2020</span></span>

- <span data-ttu-id="5a252-126">Entità [Device](machine.md) aggiornata: aggiunto ***l'elenco IpInterfaces.***</span><span class="sxs-lookup"><span data-stu-id="5a252-126">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="5a252-127">Vedi [Elencare i dispositivi](get-machines.md).</span><span class="sxs-lookup"><span data-stu-id="5a252-127">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="5a252-128">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="5a252-128">04.11.2020</span></span>

- <span data-ttu-id="5a252-129">Aggiunta nuova API: [Imposta valore dispositivo](set-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="5a252-129">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="5a252-130">Entità [Device](machine.md) aggiornata: aggiunta ***della proprietà deviceValue.***</span><span class="sxs-lookup"><span data-stu-id="5a252-130">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="5a252-131">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="5a252-131">01.09.2020</span></span>

- <span data-ttu-id="5a252-132">È stata aggiunta un'opzione per espandere l'entità Avviso con l'evidenza correlata.</span><span class="sxs-lookup"><span data-stu-id="5a252-132">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="5a252-133">Vedere [Avvisi elenco](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="5a252-133">See [List Alerts](get-alerts.md).</span></span>
