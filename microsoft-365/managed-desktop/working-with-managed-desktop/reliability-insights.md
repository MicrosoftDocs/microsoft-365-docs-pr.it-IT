---
title: Dati analitici sull'affidabilità
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b7f56a64f1846676f458f7b3ddb210e84b9ca8f7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085671"
---
# <a name="reliability-insights"></a><span data-ttu-id="4e452-103">Dati analitici sull'affidabilità</span><span class="sxs-lookup"><span data-stu-id="4e452-103">Reliability insights</span></span>

<span data-ttu-id="4e452-104">Questa visualizzazione fornisce un riepilogo di integrità dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="4e452-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="4e452-105">Per visualizzare i dati di attendibilità, selezionare la scheda **affidabilità** .</span><span class="sxs-lookup"><span data-stu-id="4e452-105">To view reliability data, select the **Reliability** tab.</span></span>


![Riquadro di affidabilità: affidabilità tra i dispositivi in alto a sinistra e affidabilità nel grafico temporale in alto a destra, tabella problemi principali nella parte inferiore.](../../media/insights_reliability.png)

<span data-ttu-id="4e452-108">La sezione **affidabilità tra i dispositivi** offre un riepilogo rapido dell'integrità della distribuzione negli ultimi 14 giorni segnalando la percentuale di dispositivi considerati "integro" e il tempo medio osservato dopo l'ultimo errore segnalato.</span><span class="sxs-lookup"><span data-stu-id="4e452-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="4e452-109">Il grafico sull' **affidabilità nel tempo** sulla destra riporta il numero di dispositivi con errori critici e il numero totale di errori critici osservati nel tempo.</span><span class="sxs-lookup"><span data-stu-id="4e452-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="4e452-110">La sezione **problemi principali** specifica i problemi rilevati specifici che incidono almeno sul 5% dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="4e452-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="4e452-111">I dettagli riportati includono:</span><span class="sxs-lookup"><span data-stu-id="4e452-111">Reported details include:</span></span>

- <span data-ttu-id="4e452-112">Il tipo di problema</span><span class="sxs-lookup"><span data-stu-id="4e452-112">The type of issue</span></span>
    - <span data-ttu-id="4e452-113">Crash dell'applicazione, in cui un'app smette di funzionare o si arresta in modo imprevisto</span><span class="sxs-lookup"><span data-stu-id="4e452-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="4e452-114">L'applicazione si blocca, in cui un'applicazione smette di rispondere all'input</span><span class="sxs-lookup"><span data-stu-id="4e452-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="4e452-115">Errori critici, che si verificano quando Windows ha riscontrato un problema di cui non è possibile eseguire il ripristino</span><span class="sxs-lookup"><span data-stu-id="4e452-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="4e452-116">Il numero di dispositivi coinvolti nello stesso problema</span><span class="sxs-lookup"><span data-stu-id="4e452-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="4e452-117">La percentuale di dispositivi gestiti che il numero rappresenta</span><span class="sxs-lookup"><span data-stu-id="4e452-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="4e452-118">Il numero totale di occorrenze del problema specifico</span><span class="sxs-lookup"><span data-stu-id="4e452-118">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="4e452-119">Il componente software che sembra essere l'origine del problema</span><span class="sxs-lookup"><span data-stu-id="4e452-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="4e452-120">La categoria del problema rilevato:</span><span class="sxs-lookup"><span data-stu-id="4e452-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="4e452-121">Browser (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="4e452-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="4e452-122">Unknown (componenti non Microsoft)</span><span class="sxs-lookup"><span data-stu-id="4e452-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="4e452-123">Driver (audio, grafica o altri driver)</span><span class="sxs-lookup"><span data-stu-id="4e452-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="4e452-124">Produttività (Slack, G-Suites, Microsoft Office e relativi componenti aggiuntivi o estensioni, Teams)</span><span class="sxs-lookup"><span data-stu-id="4e452-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="4e452-125">Contenuto multimediale (app di immagini, musica o video</span><span class="sxs-lookup"><span data-stu-id="4e452-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="4e452-126">Sicurezza (componenti di sicurezza di Windows)</span><span class="sxs-lookup"><span data-stu-id="4e452-126">Security (Windows security components)</span></span>
- <span data-ttu-id="4e452-127">Lo stato corrente delle operazioni di Microsoft Managed Desktop indaga e rimedia il problema</span><span class="sxs-lookup"><span data-stu-id="4e452-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

