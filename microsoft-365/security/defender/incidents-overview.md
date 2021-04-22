---
title: Eventi imprevisti in Microsoft 365 Defender
description: Analizzare gli incidenti osservati su dispositivi, utenti e cassette postali nel Centro sicurezza Microsoft 365.
keywords: incidenti, avvisi, analizzare, analizzare, risposta, correlazione, attacco, computer, dispositivi, utenti, identità, identità, identità, cassetta postale, posta elettronica, 365, microsoft, m365
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
ms.openlocfilehash: 890e64367c49c24c8c70e2cbda9869a5d0797219
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939589"
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

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Flusso di lavoro di risposta agli eventi imprevisti di esempio per Microsoft 365 Defender

Ecco un flusso di lavoro di esempio per rispondere a eventi imprevisti in Microsoft 365 con il Centro sicurezza Microsoft 365.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Esempio di flusso di lavoro per la risposta a eventi imprevisti per Microsoft 365":::

Su base continuativa, identificare gli eventi imprevisti con priorità più alta per l'analisi e la risoluzione nella coda degli eventi imprevisti e prepararli per la risposta. Questa è una combinazione di:

- [Per determinare](incident-queue.md) gli eventi imprevisti con priorità più alta, è necessario filtrare e ordinare la coda degli eventi imprevisti.
- [Gestire](manage-incidents.md) gli eventi imprevisti modificandone il titolo, assegnandoli a un analista e aggiungendo tag e commenti.

1. Per ogni evento imprevisto, avviare [un'analisi degli attacchi e degli avvisi:](investigate-incidents.md)

   a. Visualizzare il riepilogo dell'evento imprevisto per comprendere l'ambito e la gravità e le entità interessate **(scheda** Riepilogo).

   b. Iniziare ad analizzare gli avvisi per comprenderne l'origine, l'ambito e la gravità **(scheda** Avvisi).

   c. In base alle esigenze, raccogliere informazioni sui dispositivi, gli utenti e le cassette postali influenzati (le schede **Dispositivi,** **Utenti** e **Cassette** postali).

   d. Scopri come Microsoft 365 Defender ha risolto automaticamente alcuni avvisi **(scheda** Indagini).
   
   e. Se necessario, usare le informazioni nel set di dati per l'evento imprevisto per ulteriori informazioni (scheda **Prova e** risposta).

2. Dopo o durante l'analisi, affrontare il contenimento per ridurre qualsiasi ulteriore impatto dell'attacco e dell'eliminazione della minaccia alla sicurezza.

3. Per quanto possibile, eseguire il ripristino dall'attacco ripristinando le risorse del tenant allo stato in cui si trovavano prima dell'incidente.

4. [Risolvere](manage-incidents.md#resolve-incident) l'evento imprevisto e richiedere tempo per l'apprendimento post-incidente per:

   - Comprendere il tipo di attacco e il relativo impatto.
   - Ricercare l'attacco in [Threat Analytics](threat-analytics.md) e nella community di sicurezza per una tendenza di attacco alla sicurezza.
   - Richiamare il flusso di lavoro utilizzato per risolvere l'evento imprevisto e aggiornare i flussi di lavoro, i processi, i criteri e i playbook standard in base alle esigenze.
   - Determinare se sono necessarie modifiche alla configurazione della sicurezza e implementarle.

## <a name="example-security-operations-for-microsoft-365-defender"></a>Operazioni di sicurezza di esempio per Microsoft 365 Defender

Ecco un esempio di operazioni di sicurezza per Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Esempio di operazioni di sicurezza per Micosoft 365 Defender":::

Le attività giornaliere possono includere:

- [Gestione](manage-incidents.md) degli eventi imprevisti
- Revisione delle [azioni di indagine e risposta automatizzate (AIR)](m365d-action-center.md)
- Analisi delle minacce più [recenti](threat-analytics.md)
- [Risposta](investigate-incidents.md) agli eventi imprevisti

Le attività mensili possono includere:

- Revisione delle [impostazioni AIR](m365d-configure-auto-investigation-response.md)
- Esame del [punteggio sicuro e](microsoft-secure-score-improvement-actions.md) della gestione delle & delle [minacce](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Creazione di report alla catena di gestione della sicurezza IT

Le attività trimestrali possono includere una relazione e un briefing dei risultati della sicurezza al Chief Information Security Officer (CISO).

Le attività annuali possono includere l'esecuzione di un grave evento imprevisto o di violazione per testare il personale, i sistemi e i processi. 

Le attività giornaliere, mensili, trimestrali e annuali possono essere utilizzate per aggiornare o perfezionare processi, criteri e configurazioni di sicurezza.

## <a name="next-steps"></a>Passaggi successivi

Nella coda degli eventi imprevisti della **pagina Eventi imprevisti** sono elencati gli eventi imprevisti più recenti. Da qui è possibile:

- Vedere quali eventi imprevisti devono essere [classificati in](incident-queue.md) base alla gravità e ad altri fattori. 
- [Gestire gli eventi imprevisti,](manage-incidents.md)che includono la ridenominazione, l'assegnazione, la classificazione e l'aggiunta di tag e commenti per il flusso di lavoro di gestione degli eventi imprevisti.
- Eseguire [un'analisi](investigate-incidents.md) di un evento imprevisto.
