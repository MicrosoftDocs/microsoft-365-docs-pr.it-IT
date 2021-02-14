---
title: Dati analitici sull'affidabilità
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
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
# <a name="reliability-insights"></a><span data-ttu-id="eccf0-103">Dati analitici sull'affidabilità</span><span class="sxs-lookup"><span data-stu-id="eccf0-103">Reliability insights</span></span>

<span data-ttu-id="eccf0-104">Questa visualizzazione fornisce un riepilogo dell'integrità dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="eccf0-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="eccf0-105">Per visualizzare i dati di affidabilità, selezionare **la scheda Affidabilità.**</span><span class="sxs-lookup"><span data-stu-id="eccf0-105">To view reliability data, select the **Reliability** tab.</span></span>


![Riquadro Affidabilità: affidabilità tra i dispositivi in alto a sinistra, affidabilità nel grafico del tempo in alto a destra, tabella dei problemi principali nella parte inferiore.](../../media/insights_reliability.png)

<span data-ttu-id="eccf0-108">La  sezione Affidabilità tra dispositivi offre un breve riepilogo dell'integrità della distribuzione negli ultimi 14 giorni segnalando la percentuale di dispositivi considerati "integri" e il tempo medio osservato dopo l'ultimo errore segnalato.</span><span class="sxs-lookup"><span data-stu-id="eccf0-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="eccf0-109">Il **grafico Affidabilità nel** tempo sulla destra segnala il numero di dispositivi con errori critici e il numero totale di errori critici osservati nel tempo.</span><span class="sxs-lookup"><span data-stu-id="eccf0-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="eccf0-110">Nella **sezione Principali problemi** vengono fornite informazioni dettagliate sui problemi rilevati specifici che interessano almeno il 5% dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="eccf0-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="eccf0-111">I dettagli segnalati includono:</span><span class="sxs-lookup"><span data-stu-id="eccf0-111">Reported details include:</span></span>

- <span data-ttu-id="eccf0-112">Tipo di problema</span><span class="sxs-lookup"><span data-stu-id="eccf0-112">The type of issue</span></span>
    - <span data-ttu-id="eccf0-113">Arresti anomali dell'applicazione, in cui un'app smette di funzionare o si arresta in modo imprevisto</span><span class="sxs-lookup"><span data-stu-id="eccf0-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="eccf0-114">L'applicazione si blocca, in cui un'applicazione smette di rispondere all'input</span><span class="sxs-lookup"><span data-stu-id="eccf0-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="eccf0-115">Errori critici che si verificano quando Si verifica un problema in Windows da cui non è possibile eseguire il ripristino</span><span class="sxs-lookup"><span data-stu-id="eccf0-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="eccf0-116">Il numero di dispositivi interessati dallo stesso problema</span><span class="sxs-lookup"><span data-stu-id="eccf0-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="eccf0-117">Percentuale di dispositivi gestiti che il numero rappresenta</span><span class="sxs-lookup"><span data-stu-id="eccf0-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="eccf0-118">Numero totale di occorrenze del problema specifico</span><span class="sxs-lookup"><span data-stu-id="eccf0-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="eccf0-119">Il componente software che sembra essere l'origine del problema</span><span class="sxs-lookup"><span data-stu-id="eccf0-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="eccf0-120">Categoria del problema rilevato:</span><span class="sxs-lookup"><span data-stu-id="eccf0-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="eccf0-121">Browser (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="eccf0-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="eccf0-122">Sconosciuto (componenti non Microsoft)</span><span class="sxs-lookup"><span data-stu-id="eccf0-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="eccf0-123">Driver (audio, grafica o altri driver)</span><span class="sxs-lookup"><span data-stu-id="eccf0-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="eccf0-124">Produttività (Slack, G-Suite, Microsoft Office componenti aggiuntivi o estensioni, Teams)</span><span class="sxs-lookup"><span data-stu-id="eccf0-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="eccf0-125">App multimediali (app per immagini, musica o video</span><span class="sxs-lookup"><span data-stu-id="eccf0-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="eccf0-126">Sicurezza (componenti di sicurezza di Windows)</span><span class="sxs-lookup"><span data-stu-id="eccf0-126">Security (Windows security components)</span></span>
- <span data-ttu-id="eccf0-127">Lo stato corrente di Microsoft Managed Desktop Operations analizza e corree il problema</span><span class="sxs-lookup"><span data-stu-id="eccf0-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

