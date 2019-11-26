---
title: Intuizioni di affidabilità
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f830e01d54aef9065727971533633f8e63bc1214
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257034"
---
# <a name="reliability-insights"></a><span data-ttu-id="96343-103">Intuizioni di affidabilità</span><span class="sxs-lookup"><span data-stu-id="96343-103">Reliability insights</span></span>

<span data-ttu-id="96343-104">Questa visualizzazione fornisce un riepilogo di integrità dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="96343-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="96343-105">Per visualizzare i dati di attendibilità, selezionare la scheda **affidabilità** .</span><span class="sxs-lookup"><span data-stu-id="96343-105">To view reliability data, select the **Reliability** tab.</span></span>


![Riquadro affidabilità](images/insights_reliability.png)

<span data-ttu-id="96343-107">La sezione **affidabilità tra i dispositivi** offre un riepilogo rapido dell'integrità della distribuzione negli ultimi 14 giorni segnalando la percentuale di dispositivi considerati "integro" e il tempo medio osservato dopo l'ultimo errore segnalato.</span><span class="sxs-lookup"><span data-stu-id="96343-107">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="96343-108">Il grafico sull' **affidabilità nel tempo** sulla destra riporta il numero di dispositivi con errori critici e il numero totale di errori critici osservati nel tempo.</span><span class="sxs-lookup"><span data-stu-id="96343-108">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="96343-109">La sezione **problemi principali** specifica i problemi rilevati specifici che incidono almeno sul 5% dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="96343-109">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="96343-110">I dettagli riportati includono:</span><span class="sxs-lookup"><span data-stu-id="96343-110">Reported details include:</span></span>

- <span data-ttu-id="96343-111">Il tipo di problema</span><span class="sxs-lookup"><span data-stu-id="96343-111">The type of issue</span></span>
    - <span data-ttu-id="96343-112">Crash dell'applicazione, in cui un'app smette di funzionare o si arresta in modo imprevisto</span><span class="sxs-lookup"><span data-stu-id="96343-112">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="96343-113">L'applicazione si blocca, in cui un'applicazione smette di rispondere all'input</span><span class="sxs-lookup"><span data-stu-id="96343-113">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="96343-114">Errori critici, che si verificano quando Windows ha riscontrato un problema di cui non è possibile eseguire il ripristino</span><span class="sxs-lookup"><span data-stu-id="96343-114">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="96343-115">Il numero di dispositivi coinvolti nello stesso problema</span><span class="sxs-lookup"><span data-stu-id="96343-115">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="96343-116">La percentuale di dispositivi gestiti che il numero rappresenta</span><span class="sxs-lookup"><span data-stu-id="96343-116">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="96343-117">Il numero totale di occorrenze del problema specifico</span><span class="sxs-lookup"><span data-stu-id="96343-117">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="96343-118">Il componente software che sembra essere l'origine del problema</span><span class="sxs-lookup"><span data-stu-id="96343-118">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="96343-119">Lo stato corrente delle operazioni di Microsoft Managed Desktop indaga e rimedia il problema</span><span class="sxs-lookup"><span data-stu-id="96343-119">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

