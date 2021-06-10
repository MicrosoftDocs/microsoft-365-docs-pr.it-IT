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
ms.openlocfilehash: fb87f36c5289d622df2615046c5bb2fd8fad9543
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842243"
---
# <a name="create-indicators"></a><span data-ttu-id="1d337-104">Creare indicatori</span><span class="sxs-lookup"><span data-stu-id="1d337-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d337-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1d337-105">**Applies to:**</span></span>
- [<span data-ttu-id="1d337-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="1d337-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d337-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d337-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="1d337-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1d337-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d337-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="1d337-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="1d337-110">La corrispondenza degli indicatori di compromissione (IoC) è una funzionalità essenziale in ogni soluzione di protezione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="1d337-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="1d337-111">Questa funzionalità offre a SecOps la possibilità di impostare un elenco di indicatori per il rilevamento e il blocco (prevenzione e risposta).</span><span class="sxs-lookup"><span data-stu-id="1d337-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="1d337-112">Creare indicatori che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.</span><span class="sxs-lookup"><span data-stu-id="1d337-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="1d337-113">Puoi definire l'azione da eseguire, nonché la durata per l'applicazione dell'azione e l'ambito del gruppo di dispositivi a cui applicarla.</span><span class="sxs-lookup"><span data-stu-id="1d337-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="1d337-114">Le origini attualmente supportate sono il motore di rilevamento cloud di Defender for Endpoint, il motore di analisi e correzione automatizzato e il motore di prevenzione degli endpoint (Antivirus Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="1d337-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="1d337-115">**Motore di rilevamento cloud**</span><span class="sxs-lookup"><span data-stu-id="1d337-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="1d337-116">Il motore di rilevamento cloud di Defender for Endpoint analizza regolarmente i dati raccolti e cerca di corrispondere agli indicatori impostati.</span><span class="sxs-lookup"><span data-stu-id="1d337-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="1d337-117">In caso di corrispondenza, verrà eseguita un'azione in base alle impostazioni specificate per l'IoC.</span><span class="sxs-lookup"><span data-stu-id="1d337-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="1d337-118">**Motore di prevenzione degli endpoint**</span><span class="sxs-lookup"><span data-stu-id="1d337-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="1d337-119">Lo stesso elenco di indicatori viene rispettato dall'agente di prevenzione.</span><span class="sxs-lookup"><span data-stu-id="1d337-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="1d337-120">Ciò significa che se Microsoft Defender AV è l'av principale configurato, gli indicatori corrispondenti verranno trattati in base alle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="1d337-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="1d337-121">Ad esempio, se l'azione è "Avviso e blocco", Microsoft Defender AV impedirà le esecuzioni di file (blocco e correzione) e verrà generato un avviso corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1d337-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="1d337-122">D'altra parte, se l'azione è impostata su "Consenti", Microsoft Defender AV non rileva né blocca l'esecuzione del file.</span><span class="sxs-lookup"><span data-stu-id="1d337-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="1d337-123">**Motore di analisi e correzione automatizzato**</span><span class="sxs-lookup"><span data-stu-id="1d337-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="1d337-124">L'analisi e la correzione automatizzate si comportano allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="1d337-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="1d337-125">Se un indicatore è impostato su "Consenti", l'analisi e la correzione automatizzate ignoreranno un verdetto "negativo".</span><span class="sxs-lookup"><span data-stu-id="1d337-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="1d337-126">Se impostato su "Blocca", l'analisi e la correzione automatizzate lo tratteranno come "non corretti".</span><span class="sxs-lookup"><span data-stu-id="1d337-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>

> [!NOTE]
> <span data-ttu-id="1d337-127">L'impostazione EnableFileHashComputation calcola l'hash del file per il certificato e il file IoC durante le analisi dei file.</span><span class="sxs-lookup"><span data-stu-id="1d337-127">The EnableFileHashComputation setting computes the file hash for the cert and file IoC during file scans.</span></span> <span data-ttu-id="1d337-128">Supporta l'imposizione IoC di hash e certificati appartenenti ad applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="1d337-128">It supports IoC enforcement of hashes and certs belong to trusted applications.</span></span> <span data-ttu-id="1d337-129">Verrà abilitato e disabilitato contemporaneamente con l'impostazione Consenti o blocca file.</span><span class="sxs-lookup"><span data-stu-id="1d337-129">It will be concurrently enabled and disabled with the allow or block file setting.</span></span> <span data-ttu-id="1d337-130">EnableFileHashComputation viene abilitato manualmente tramite Criteri di gruppo ed è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1d337-130">EnableFileHashComputation is enabled manually through Group Policy, and is disabled by default.</span></span>


<span data-ttu-id="1d337-131">Le azioni attualmente supportate sono:</span><span class="sxs-lookup"><span data-stu-id="1d337-131">The current supported actions are:</span></span>
- <span data-ttu-id="1d337-132">Consenti</span><span class="sxs-lookup"><span data-stu-id="1d337-132">Allow</span></span>
- <span data-ttu-id="1d337-133">Solo avviso</span><span class="sxs-lookup"><span data-stu-id="1d337-133">Alert only</span></span>
- <span data-ttu-id="1d337-134">Avviso e blocco</span><span class="sxs-lookup"><span data-stu-id="1d337-134">Alert and block</span></span>


<span data-ttu-id="1d337-135">È possibile creare un indicatore per:</span><span class="sxs-lookup"><span data-stu-id="1d337-135">You can create an indicator for:</span></span>
- [<span data-ttu-id="1d337-136">File</span><span class="sxs-lookup"><span data-stu-id="1d337-136">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="1d337-137">Indirizzi IP, URL/domini</span><span class="sxs-lookup"><span data-stu-id="1d337-137">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="1d337-138">Certificati</span><span class="sxs-lookup"><span data-stu-id="1d337-138">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="1d337-139">Esiste un limite di 15.000 indicatori per tenant.</span><span class="sxs-lookup"><span data-stu-id="1d337-139">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="1d337-140">Gli indicatori di file e certificati non [bloccano le esclusioni definite per Antivirus Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="1d337-140">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="1d337-141">Gli indicatori non sono supportati in Antivirus Microsoft Defender quando è in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="1d337-141">Indicators are not supported in Microsoft Defender Antivirus when it is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="1d337-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1d337-142">Related topics</span></span>

- [<span data-ttu-id="1d337-143">Creare ioC contestuali</span><span class="sxs-lookup"><span data-stu-id="1d337-143">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="1d337-144">Usare l'API Microsoft Defender for Endpoint indicators</span><span class="sxs-lookup"><span data-stu-id="1d337-144">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="1d337-145">Usare soluzioni integrate per i partner</span><span class="sxs-lookup"><span data-stu-id="1d337-145">Use partner integrated solutions</span></span>](partner-applications.md)
