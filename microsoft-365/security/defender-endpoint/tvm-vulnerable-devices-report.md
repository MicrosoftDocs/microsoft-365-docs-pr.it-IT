---
title: Report sui dispositivi vulnerabili - Gestione delle minacce e delle vulnerabilità
description: Report che mostra le tendenze dei dispositivi vulnerabili e le statistiche correnti. L'obiettivo è comprendere il respiro e l'ambito dell'esposizione del dispositivo.
keywords: Microsoft Defender for Endpoint-tvm vulnerable devices, Microsoft Defender for Endpoint, tvm, reduce threat & vulnerability exposure, reduce threat and vulnerability, monitor security configuration
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4b2b581d570bd0924970a845c66a599495ff9829
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933710"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="4dc62-105">Report sui dispositivi vulnerabili - Gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="4dc62-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4dc62-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4dc62-106">**Applies to:**</span></span>

- [<span data-ttu-id="4dc62-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="4dc62-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4dc62-108">Gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="4dc62-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4dc62-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4dc62-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4dc62-110">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4dc62-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4dc62-111">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="4dc62-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="4dc62-112">Il report mostra grafici e grafici a barre con tendenze dei dispositivi vulnerabili e statistiche correnti.</span><span class="sxs-lookup"><span data-stu-id="4dc62-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="4dc62-113">L'obiettivo è comprendere il respiro e l'ambito dell'esposizione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4dc62-113">The goal is for you to understand the breath and scope of your device exposure.</span></span> 

<span data-ttu-id="4dc62-114">Accedere al report in Microsoft Defender Security Center accedendo a **Report > dispositivi vulnerabili**</span><span class="sxs-lookup"><span data-stu-id="4dc62-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="4dc62-115">Sono disponibili due colonne:</span><span class="sxs-lookup"><span data-stu-id="4dc62-115">There are two columns:</span></span>

- <span data-ttu-id="4dc62-116">Tendenze (nel tempo).</span><span class="sxs-lookup"><span data-stu-id="4dc62-116">Trends (over time).</span></span> <span data-ttu-id="4dc62-117">Può mostrare gli ultimi 30 giorni, 3 mesi, 6 mesi o un intervallo di date personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4dc62-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="4dc62-118">Oggi (informazioni correnti)</span><span class="sxs-lookup"><span data-stu-id="4dc62-118">Today (current information)</span></span>

<span data-ttu-id="4dc62-119">**Filtro:** è possibile filtrare i dati in base ai livelli di gravità della vulnerabilità, alla disponibilità degli exploit, al periodo di validità della vulnerabilità, alla piattaforma del sistema operativo, alla versione di Windows 10 o al gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4dc62-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="4dc62-120">**Drill-down:** se sono disponibili informazioni approfondite che si desidera esplorare ulteriormente, selezionare il grafico a barre pertinente per visualizzare un elenco filtrato di dispositivi nella pagina Inventario dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4dc62-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="4dc62-121">Da qui è possibile esportare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="4dc62-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="4dc62-122">Grafici del livello di gravità</span><span class="sxs-lookup"><span data-stu-id="4dc62-122">Severity level graphs</span></span>

<span data-ttu-id="4dc62-123">Ogni dispositivo viene conteggiato una sola volta in base alla vulnerabilità più grave riscontrata in tale dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4dc62-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![Un grafico dei livelli di gravità della vulnerabilità del dispositivo corrente e un grafico che mostra i livelli nel tempo.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="4dc62-125">Grafici sulla disponibilità degli exploit</span><span class="sxs-lookup"><span data-stu-id="4dc62-125">Exploit availability graphs</span></span>

<span data-ttu-id="4dc62-126">Ogni dispositivo viene conteggiato una sola volta in base al livello più alto di exploit noto.</span><span class="sxs-lookup"><span data-stu-id="4dc62-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![Un grafico della disponibilità degli exploit del dispositivo corrente e un grafico che mostra la disponibilità nel tempo.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="4dc62-128">Grafici dell'età delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="4dc62-128">Vulnerability age graphs</span></span>

<span data-ttu-id="4dc62-129">Ogni dispositivo viene conteggiato una sola volta alla data di pubblicazione della vulnerabilità meno recente.</span><span class="sxs-lookup"><span data-stu-id="4dc62-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="4dc62-130">Le vulnerabilità precedenti hanno maggiori probabilità di essere sfruttate.</span><span class="sxs-lookup"><span data-stu-id="4dc62-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![Un grafico dell'età della vulnerabilità del dispositivo corrente e un grafico che mostra l'età nel tempo.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="4dc62-132">Dispositivi vulnerabili in base ai grafici della piattaforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="4dc62-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="4dc62-133">Numero di dispositivi in ogni sistema operativo esposti a causa di vulnerabilità software.</span><span class="sxs-lookup"><span data-stu-id="4dc62-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![Un grafico dei dispositivi vulnerabili correnti per piattaforma del sistema operativo e un grafico che mostra i dispositivi vulnerabili da parte delle piattaforme del sistema operativo nel tempo.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="4dc62-135">Dispositivi vulnerabili tramite grafici della versione di Windows 10</span><span class="sxs-lookup"><span data-stu-id="4dc62-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="4dc62-136">Numero di dispositivi in ogni versione di Windows 10 esposti a causa di applicazioni vulnerabili o del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4dc62-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![Un grafico dei dispositivi vulnerabili correnti per la versione di Windows 10 e un grafico che mostra i dispositivi vulnerabili dalla versione di Windows 10 nel tempo.](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="4dc62-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4dc62-138">Related topics</span></span>

- [<span data-ttu-id="4dc62-139">Panoramica della gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="4dc62-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="4dc62-140">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="4dc62-140">Security recommendations</span></span>](tvm-security-recommendation.md)
