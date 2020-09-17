---
title: Dati analitici sull'affidabilità
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950343"
---
# <a name="reliability-insights"></a><span data-ttu-id="7618d-103">Dati analitici sull'affidabilità</span><span class="sxs-lookup"><span data-stu-id="7618d-103">Reliability insights</span></span>

<span data-ttu-id="7618d-104">Questa visualizzazione fornisce un riepilogo di integrità dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="7618d-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="7618d-105">Per visualizzare i dati di attendibilità, selezionare la scheda **affidabilità** .</span><span class="sxs-lookup"><span data-stu-id="7618d-105">To view reliability data, select the **Reliability** tab.</span></span>


![Riquadro di affidabilità: affidabilità tra i dispositivi in alto a sinistra e affidabilità nel grafico temporale in alto a destra, tabella problemi principali nella parte inferiore.](../../media/insights_reliability.png)

<span data-ttu-id="7618d-108">La sezione **affidabilità tra i dispositivi** offre un riepilogo rapido dell'integrità della distribuzione negli ultimi 14 giorni segnalando la percentuale di dispositivi considerati "integro" e il tempo medio osservato dopo l'ultimo errore segnalato.</span><span class="sxs-lookup"><span data-stu-id="7618d-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="7618d-109">Il grafico sull' **affidabilità nel tempo** sulla destra riporta il numero di dispositivi con errori critici e il numero totale di errori critici osservati nel tempo.</span><span class="sxs-lookup"><span data-stu-id="7618d-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="7618d-110">La sezione **problemi principali** specifica i problemi rilevati specifici che incidono almeno sul 5% dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="7618d-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="7618d-111">I dettagli riportati includono:</span><span class="sxs-lookup"><span data-stu-id="7618d-111">Reported details include:</span></span>

- <span data-ttu-id="7618d-112">Il tipo di problema</span><span class="sxs-lookup"><span data-stu-id="7618d-112">The type of issue</span></span>
    - <span data-ttu-id="7618d-113">Crash dell'applicazione, in cui un'app smette di funzionare o si arresta in modo imprevisto</span><span class="sxs-lookup"><span data-stu-id="7618d-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="7618d-114">L'applicazione si blocca, in cui un'applicazione smette di rispondere all'input</span><span class="sxs-lookup"><span data-stu-id="7618d-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="7618d-115">Errori critici, che si verificano quando Windows ha riscontrato un problema di cui non è possibile eseguire il ripristino</span><span class="sxs-lookup"><span data-stu-id="7618d-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="7618d-116">Il numero di dispositivi coinvolti nello stesso problema</span><span class="sxs-lookup"><span data-stu-id="7618d-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="7618d-117">La percentuale di dispositivi gestiti che il numero rappresenta</span><span class="sxs-lookup"><span data-stu-id="7618d-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="7618d-118">Il numero totale di occorrenze del problema specifico</span><span class="sxs-lookup"><span data-stu-id="7618d-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="7618d-119">Il componente software che sembra essere l'origine del problema</span><span class="sxs-lookup"><span data-stu-id="7618d-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="7618d-120">La categoria del problema rilevato:</span><span class="sxs-lookup"><span data-stu-id="7618d-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="7618d-121">Browser (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="7618d-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="7618d-122">Unknown (componenti non Microsoft)</span><span class="sxs-lookup"><span data-stu-id="7618d-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="7618d-123">Driver (audio, grafica o altri driver)</span><span class="sxs-lookup"><span data-stu-id="7618d-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="7618d-124">Produttività (Slack, G-Suites, Microsoft Office e relativi componenti aggiuntivi o estensioni, Teams)</span><span class="sxs-lookup"><span data-stu-id="7618d-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="7618d-125">Contenuto multimediale (app di immagini, musica o video</span><span class="sxs-lookup"><span data-stu-id="7618d-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="7618d-126">Sicurezza (componenti di sicurezza di Windows)</span><span class="sxs-lookup"><span data-stu-id="7618d-126">Security (Windows security components)</span></span>
- <span data-ttu-id="7618d-127">Lo stato corrente delle operazioni di Microsoft Managed Desktop indaga e rimedia il problema</span><span class="sxs-lookup"><span data-stu-id="7618d-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

