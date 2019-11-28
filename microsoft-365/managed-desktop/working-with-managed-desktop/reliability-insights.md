---
title: Dati analitici sull'affidabilità
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8ecc117b2bc6e7cec3dcf0470a6d3c61ad34adf0
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634033"
---
# <a name="reliability-insights"></a><span data-ttu-id="279a4-103">Dati analitici sull'affidabilità</span><span class="sxs-lookup"><span data-stu-id="279a4-103">Reliability insights</span></span>

<span data-ttu-id="279a4-104">Questa visualizzazione fornisce un riepilogo di integrità dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="279a4-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="279a4-105">Per visualizzare i dati di attendibilità, selezionare la scheda **affidabilità** .</span><span class="sxs-lookup"><span data-stu-id="279a4-105">To view reliability data, select the **Reliability** tab.</span></span>


![Riquadro affidabilità](images/insights_reliability.png)

<span data-ttu-id="279a4-107">La sezione **affidabilità tra i dispositivi** offre un riepilogo rapido dell'integrità della distribuzione negli ultimi 14 giorni segnalando la percentuale di dispositivi considerati "integro" e il tempo medio osservato dopo l'ultimo errore segnalato.</span><span class="sxs-lookup"><span data-stu-id="279a4-107">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="279a4-108">Il grafico sull' **affidabilità nel tempo** sulla destra riporta il numero di dispositivi con errori critici e il numero totale di errori critici osservati nel tempo.</span><span class="sxs-lookup"><span data-stu-id="279a4-108">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="279a4-109">La sezione **problemi principali** specifica i problemi rilevati specifici che incidono almeno sul 5% dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="279a4-109">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="279a4-110">I dettagli riportati includono:</span><span class="sxs-lookup"><span data-stu-id="279a4-110">Reported details include:</span></span>

- <span data-ttu-id="279a4-111">Il tipo di problema</span><span class="sxs-lookup"><span data-stu-id="279a4-111">The type of issue</span></span>
    - <span data-ttu-id="279a4-112">Crash dell'applicazione, in cui un'app smette di funzionare o si arresta in modo imprevisto</span><span class="sxs-lookup"><span data-stu-id="279a4-112">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="279a4-113">L'applicazione si blocca, in cui un'applicazione smette di rispondere all'input</span><span class="sxs-lookup"><span data-stu-id="279a4-113">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="279a4-114">Errori critici, che si verificano quando Windows ha riscontrato un problema di cui non è possibile eseguire il ripristino</span><span class="sxs-lookup"><span data-stu-id="279a4-114">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="279a4-115">Il numero di dispositivi coinvolti nello stesso problema</span><span class="sxs-lookup"><span data-stu-id="279a4-115">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="279a4-116">La percentuale di dispositivi gestiti che il numero rappresenta</span><span class="sxs-lookup"><span data-stu-id="279a4-116">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="279a4-117">Il numero totale di occorrenze del problema specifico</span><span class="sxs-lookup"><span data-stu-id="279a4-117">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="279a4-118">Il componente software che sembra essere l'origine del problema</span><span class="sxs-lookup"><span data-stu-id="279a4-118">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="279a4-119">La categoria del problema rilevato:</span><span class="sxs-lookup"><span data-stu-id="279a4-119">The category of the detected problem:</span></span>
    - <span data-ttu-id="279a4-120">Browser (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="279a4-120">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="279a4-121">Unknown (componenti non Microsoft)</span><span class="sxs-lookup"><span data-stu-id="279a4-121">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="279a4-122">Driver (audio, grafica o altri driver)</span><span class="sxs-lookup"><span data-stu-id="279a4-122">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="279a4-123">Produttività (Slack, G-Suites, Microsoft Office e relativi componenti aggiuntivi o estensioni, Teams)</span><span class="sxs-lookup"><span data-stu-id="279a4-123">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="279a4-124">Contenuto multimediale (app di immagini, musica o video</span><span class="sxs-lookup"><span data-stu-id="279a4-124">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="279a4-125">Sicurezza (componenti di sicurezza di Windows)</span><span class="sxs-lookup"><span data-stu-id="279a4-125">Security (Windows security components)</span></span>
- <span data-ttu-id="279a4-126">Lo stato corrente delle operazioni di Microsoft Managed Desktop indaga e rimedia il problema</span><span class="sxs-lookup"><span data-stu-id="279a4-126">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

