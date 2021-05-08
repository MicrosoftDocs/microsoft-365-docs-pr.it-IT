---
title: Report dispositivi vulnerabili - gestione di minacce e vulnerabilità
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
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245481"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="d3561-105">Report dispositivi vulnerabili - gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="d3561-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d3561-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d3561-106">**Applies to:**</span></span>

- [<span data-ttu-id="d3561-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d3561-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d3561-108">Gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="d3561-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="d3561-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3561-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d3561-110">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d3561-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d3561-111">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d3561-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="d3561-112">Il report mostra grafici e grafici a barre con tendenze dei dispositivi vulnerabili e statistiche correnti.</span><span class="sxs-lookup"><span data-stu-id="d3561-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="d3561-113">L'obiettivo è comprendere il respiro e l'ambito dell'esposizione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d3561-113">The goal is for you to understand the breath and scope of your device exposure.</span></span>

<span data-ttu-id="d3561-114">Accedere al report nel Microsoft Defender Security Center accedendo a **Report > dispositivi vulnerabili**</span><span class="sxs-lookup"><span data-stu-id="d3561-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="d3561-115">Sono disponibili due colonne:</span><span class="sxs-lookup"><span data-stu-id="d3561-115">There are two columns:</span></span>

- <span data-ttu-id="d3561-116">Tendenze (nel tempo).</span><span class="sxs-lookup"><span data-stu-id="d3561-116">Trends (over time).</span></span> <span data-ttu-id="d3561-117">Può mostrare gli ultimi 30 giorni, 3 mesi, 6 mesi o un intervallo di date personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d3561-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="d3561-118">Oggi (informazioni correnti)</span><span class="sxs-lookup"><span data-stu-id="d3561-118">Today (current information)</span></span>

<span data-ttu-id="d3561-119">**Filtro:** è possibile filtrare i dati in base ai livelli di gravità della vulnerabilità, alla disponibilità degli exploit, al periodo di validità della vulnerabilità, alla piattaforma del sistema operativo, Windows 10 versione o al gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d3561-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="d3561-120">**Drill-down:** se sono disponibili informazioni approfondite che si desidera esplorare ulteriormente, selezionare il grafico a barre pertinente per visualizzare un elenco filtrato di dispositivi nella pagina Inventario dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d3561-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="d3561-121">Da qui è possibile esportare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="d3561-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="d3561-122">Grafici del livello di gravità</span><span class="sxs-lookup"><span data-stu-id="d3561-122">Severity level graphs</span></span>

<span data-ttu-id="d3561-123">Ogni dispositivo viene conteggiato una sola volta in base alla vulnerabilità più grave riscontrata in tale dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d3561-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![Un grafico dei livelli di gravità della vulnerabilità del dispositivo corrente e un grafico che mostra i livelli nel tempo.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="d3561-125">Grafici sulla disponibilità degli exploit</span><span class="sxs-lookup"><span data-stu-id="d3561-125">Exploit availability graphs</span></span>

<span data-ttu-id="d3561-126">Ogni dispositivo viene conteggiato una sola volta in base al livello più alto di exploit noto.</span><span class="sxs-lookup"><span data-stu-id="d3561-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![Un grafico della disponibilità degli exploit del dispositivo corrente e un grafico che mostra la disponibilità nel tempo.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="d3561-128">Grafici dell'età delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="d3561-128">Vulnerability age graphs</span></span>

<span data-ttu-id="d3561-129">Ogni dispositivo viene conteggiato una sola volta alla data di pubblicazione della vulnerabilità meno recente.</span><span class="sxs-lookup"><span data-stu-id="d3561-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="d3561-130">Le vulnerabilità precedenti hanno maggiori probabilità di essere sfruttate.</span><span class="sxs-lookup"><span data-stu-id="d3561-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![Un grafico dell'età della vulnerabilità del dispositivo corrente e un grafico che mostra l'età nel tempo.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="d3561-132">Dispositivi vulnerabili in base ai grafici della piattaforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d3561-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="d3561-133">Numero di dispositivi in ogni sistema operativo esposti a causa di vulnerabilità software.</span><span class="sxs-lookup"><span data-stu-id="d3561-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![Un grafico dei dispositivi vulnerabili correnti per piattaforma del sistema operativo e un grafico che mostra i dispositivi vulnerabili da parte delle piattaforme del sistema operativo nel tempo.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="d3561-135">Dispositivi vulnerabili per grafici Windows 10 versione</span><span class="sxs-lookup"><span data-stu-id="d3561-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="d3561-136">Numero di dispositivi in ogni versione Windows 10 esposta a causa di applicazioni vulnerabili o del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d3561-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![Un grafico dei dispositivi vulnerabili correnti per Windows 10 versione e un grafico che mostra i dispositivi vulnerabili Windows 10 versione nel tempo.](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="d3561-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d3561-138">Related topics</span></span>

- [<span data-ttu-id="d3561-139">Panoramica delle minacce gestione delle vulnerabilità sicurezza</span><span class="sxs-lookup"><span data-stu-id="d3561-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="d3561-140">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="d3561-140">Security recommendations</span></span>](tvm-security-recommendation.md)
