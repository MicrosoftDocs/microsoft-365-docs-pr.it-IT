---
title: Eventi imprevisti in Microsoft 365 Defender
description: Analizzare gli eventi imprevisti visualizzati su dispositivi, utenti e cassette postali.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5b2baa2041a8cffcea212eb449d40b9a9cbfc22a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759514"
---
# <a name="incidents-in-microsoft-365-defender"></a>Eventi imprevisti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

> Vuoi provare Microsoft 365 Defender? Puoi [valutarlo in un ambiente lab](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [eseguire il progetto pilota in produzione](m365d-pilot.md?ocid=cx-evalpilot).
>

Un evento imprevisto in Microsoft 365 Defender è una raccolta di avvisi correlati e dati associati che costituiscono la storia di un attacco. 

I servizi e le app di Microsoft 365 creano avvisi quando rilevano un evento o un'attività sospetta o dannosa. I singoli avvisi forniscono indicazioni preziose su un attacco completato o in corso. Tuttavia, gli attacchi in genere utilizzano diverse tecniche per diversi tipi di entità, ad esempio dispositivi, utenti e cassette postali. Il risultato è più avvisi per più entità nel tenant. 

Poiché l'aggregazione dei singoli avvisi per ottenere informazioni approfondite su un attacco può essere impegnativa e dispendiosa in termini di tempo, Microsoft 365 Defender aggrega automaticamente gli avvisi e le informazioni associate in un evento imprevisto.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Come Microsoft 365 Defender correla gli eventi dalle entità a un evento imprevisto":::

Guarda questa breve panoramica degli incidenti in Microsoft 365 Defender (4 minuti).

<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Il raggruppamento degli avvisi correlati in un evento imprevisto offre una visualizzazione completa di un attacco. Ad esempio, è possibile visualizzare:

- Da dove è iniziato l'attacco.
- Quali tattiche sono state usate.
- La distanza dell'attacco nel tenant.
- Ambito dell'attacco, ad esempio il numero di dispositivi, utenti e cassette postali che sono stati influenzati. 
- Tutti i dati associati all'attacco.

Se [abilitato,](m365d-enable.md)Microsoft 365 Defender può analizzare e risolvere automaticamente gli avvisi tramite l'automazione e l'intelligenza artificiale. È inoltre possibile eseguire ulteriori passaggi di correzione per risolvere l'attacco. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Eventi imprevisti e avvisi nel Centro sicurezza Microsoft 365

È possibile gestire gli eventi imprevisti da Eventi imprevisti & avvisi **> eventi** imprevisti sulla barra di avvio veloce del Centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)). Di seguito viene riportato un esempio.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Pagina Eventi imprevisti nel Centro sicurezza Microsoft 365":::

Se si seleziona un nome di evento imprevisto, viene visualizzato un riepilogo dell'evento imprevisto e viene fornito l'accesso alle schede con informazioni aggiuntive.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Esempio della pagina Riepilogo per un evento imprevisto nel Centro sicurezza Microsoft 365":::

Le schede aggiuntive per un evento imprevisto sono:

- Avvisi 

  Tutti gli avvisi relativi all'evento imprevisto e le relative informazioni.

- Dispositivi

  Tutti i dispositivi identificati come parte o correlati all'evento imprevisto.

- Utenti

  Tutti gli utenti identificati come parte o correlati all'evento imprevisto.

- Cassette postali

  Tutte le cassette postali identificate come parte o correlate all'evento imprevisto.

- Indagini

  Tutte le indagini automatizzate attivate dagli avvisi nell'evento imprevisto.

- Prova e risposta

  Tutti gli eventi supportati e le entità sospette negli avvisi nell'evento imprevisto.

Ecco la relazione tra un evento imprevisto e i relativi dati e le schede di un evento imprevisto nel Centro sicurezza Microsoft 365.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Relazione di un evento imprevisto e dei relativi dati con le schede di un evento imprevisto nel Centro sicurezza Microsoft 365":::

## <a name="next-step"></a>Passaggio successivo

Nella coda degli eventi imprevisti della **pagina Eventi imprevisti** sono elencati gli eventi imprevisti più recenti. Da qui è possibile:

- Vedere quali eventi imprevisti devono essere [classificati in](incident-queue.md) base alla gravità e ad altri fattori. 
- Eseguire [un'analisi](investigate-incidents.md) di un evento imprevisto.
- [Gestire gli eventi imprevisti,](manage-incidents.md)che includono la ridenominazione, l'assegnazione, la classificazione e l'aggiunta di tag per il flusso di lavoro di gestione degli eventi imprevisti.
