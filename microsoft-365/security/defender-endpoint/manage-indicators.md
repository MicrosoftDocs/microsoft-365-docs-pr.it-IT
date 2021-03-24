---
title: Creare indicatori
ms.reviewer: ''
description: Creare indicatori per un hash di file, un indirizzo IP, url o domini che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.
keywords: gestire, consentito, bloccato, bloccare, pulito, dannoso, hash file, indirizzo IP, URL, dominio
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fc3bce7130dbdcec76a67df70eb1a6c72474013e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064050"
---
# <a name="create-indicators"></a><span data-ttu-id="b1ee1-104">Creare indicatori</span><span class="sxs-lookup"><span data-stu-id="b1ee1-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1ee1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b1ee1-105">**Applies to:**</span></span>
- [<span data-ttu-id="b1ee1-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b1ee1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b1ee1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1ee1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="b1ee1-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b1ee1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b1ee1-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="b1ee1-110">La corrispondenza degli indicatori di compromissione (IoC) è una funzionalità essenziale in ogni soluzione di protezione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="b1ee1-111">Questa funzionalità offre a SecOps la possibilità di impostare un elenco di indicatori per il rilevamento e il blocco (prevenzione e risposta).</span><span class="sxs-lookup"><span data-stu-id="b1ee1-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="b1ee1-112">Creare indicatori che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="b1ee1-113">Puoi definire l'azione da eseguire, nonché la durata per l'applicazione dell'azione e l'ambito del gruppo di dispositivi a cui applicarla.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="b1ee1-114">Le origini attualmente supportate sono il motore di rilevamento cloud di Defender for Endpoint, il motore di analisi e correzione automatizzato e il motore di prevenzione degli endpoint (Microsoft Defender AV).</span><span class="sxs-lookup"><span data-stu-id="b1ee1-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender AV).</span></span>

<span data-ttu-id="b1ee1-115">**Motore di rilevamento cloud**</span><span class="sxs-lookup"><span data-stu-id="b1ee1-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="b1ee1-116">Il motore di rilevamento cloud di Defender for Endpoint analizza regolarmente i dati raccolti e cerca di corrispondere agli indicatori impostati.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="b1ee1-117">In caso di corrispondenza, verrà eseguita un'azione in base alle impostazioni specificate per l'IoC.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="b1ee1-118">**Motore di prevenzione degli endpoint**</span><span class="sxs-lookup"><span data-stu-id="b1ee1-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="b1ee1-119">Lo stesso elenco di indicatori viene rispettato dall'agente di prevenzione.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="b1ee1-120">Ciò significa che se Microsoft Defender AV è l'av principale configurato, gli indicatori corrispondenti verranno trattati in base alle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="b1ee1-121">Ad esempio, se l'azione è "Avviso e blocco", Microsoft Defender AV impedirà le esecuzioni di file (blocco e correzione) e verrà generato un avviso corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="b1ee1-122">D'altra parte, se l'azione è impostata su "Consenti", Microsoft Defender AV non rileva né blocca l'esecuzione del file.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="b1ee1-123">**Motore di analisi e correzione automatizzato**</span><span class="sxs-lookup"><span data-stu-id="b1ee1-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="b1ee1-124">L'analisi e la correzione automatizzate si comportano allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="b1ee1-125">Se un indicatore è impostato su "Consenti", l'analisi e la correzione automatizzate ignoreranno un verdetto "negativo".</span><span class="sxs-lookup"><span data-stu-id="b1ee1-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="b1ee1-126">Se impostato su "Blocca", l'analisi e la correzione automatizzate lo tratteranno come "non corretti".</span><span class="sxs-lookup"><span data-stu-id="b1ee1-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>


<span data-ttu-id="b1ee1-127">Le azioni attualmente supportate sono:</span><span class="sxs-lookup"><span data-stu-id="b1ee1-127">The current supported actions are:</span></span>
- <span data-ttu-id="b1ee1-128">Consenti</span><span class="sxs-lookup"><span data-stu-id="b1ee1-128">Allow</span></span>
- <span data-ttu-id="b1ee1-129">Solo avviso</span><span class="sxs-lookup"><span data-stu-id="b1ee1-129">Alert only</span></span>
- <span data-ttu-id="b1ee1-130">Avviso e blocco</span><span class="sxs-lookup"><span data-stu-id="b1ee1-130">Alert and block</span></span>


<span data-ttu-id="b1ee1-131">È possibile creare un indicatore per:</span><span class="sxs-lookup"><span data-stu-id="b1ee1-131">You can create an indicator for:</span></span>
- [<span data-ttu-id="b1ee1-132">File</span><span class="sxs-lookup"><span data-stu-id="b1ee1-132">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="b1ee1-133">Indirizzi IP, URL/domini</span><span class="sxs-lookup"><span data-stu-id="b1ee1-133">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="b1ee1-134">Certificati</span><span class="sxs-lookup"><span data-stu-id="b1ee1-134">Certificates</span></span>](indicator-certificates.md)


>[!NOTE]
><span data-ttu-id="b1ee1-135">Esiste un limite di 15.000 indicatori per tenant.</span><span class="sxs-lookup"><span data-stu-id="b1ee1-135">There is a limit of 15,000 indicators per tenant.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b1ee1-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b1ee1-136">Related topics</span></span>

- [<span data-ttu-id="b1ee1-137">Creare ioC contestuali</span><span class="sxs-lookup"><span data-stu-id="b1ee1-137">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="b1ee1-138">Usare l'API Microsoft Defender for Endpoint indicators</span><span class="sxs-lookup"><span data-stu-id="b1ee1-138">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="b1ee1-139">Usare soluzioni integrate per i partner</span><span class="sxs-lookup"><span data-stu-id="b1ee1-139">Use partner integrated solutions</span></span>](partner-applications.md)
