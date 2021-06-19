---
title: Eventi imprevisti in Microsoft 365 Defender
description: Analizzare gli eventi imprevisti osservati su dispositivi, utenti e cassette postali nel Microsoft 365 Defender portale.
keywords: incidenti, avvisi, analizzare, analizzare, risposta, correlazione, attacco, computer, dispositivi, utenti, identità, identità, identità, cassetta postale, posta elettronica, 365, microsoft, m365, risposta agli incidenti, cyberattacco
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
ms.openlocfilehash: b6830c77a0c5cc93ea202844a8793c5f69f07650
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028524"
---
# <a name="incidents-in-microsoft-365-defender"></a>Eventi imprevisti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

> Vuoi provare Microsoft 365 Defender? Puoi [valutarlo in un ambiente lab](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [eseguire il progetto pilota in produzione](m365d-pilot.md?ocid=cx-evalpilot).
>

Un evento imprevisto Microsoft 365 Defender è una raccolta di avvisi correlati e dati associati che costituiscono la storia di un attacco. 

Microsoft 365 e le app creano avvisi quando rilevano un evento o un'attività sospetta o dannosa. I singoli avvisi forniscono indicazioni preziose su un attacco completato o in corso. Tuttavia, gli attacchi in genere utilizzano diverse tecniche per diversi tipi di entità, ad esempio dispositivi, utenti e cassette postali. Il risultato è più avvisi per più entità nel tenant. 

Poiché l'aggregazione dei singoli avvisi per ottenere informazioni approfondite su un attacco può essere impegnativa e dispendiosa in termini di tempo, Microsoft 365 Defender aggrega automaticamente gli avvisi e le informazioni associate in un evento imprevisto.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Come Microsoft 365 Defender gli eventi dalle entità a un evento imprevisto":::

Guarda questa breve panoramica degli incidenti in Microsoft 365 Defender (4 minuti).

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Il raggruppamento degli avvisi correlati in un evento imprevisto offre una visualizzazione completa di un attacco. Ad esempio, è possibile visualizzare:

- Da dove è iniziato l'attacco.
- Quali tattiche sono state usate.
- La distanza dell'attacco nel tenant.
- Ambito dell'attacco, ad esempio il numero di dispositivi, utenti e cassette postali che sono stati influenzati. 
- Tutti i dati associati all'attacco.

Se [abilitata,](m365d-enable.md)Microsoft 365 Defender può [analizzare e](m365d-autoir.md) risolvere automaticamente gli avvisi tramite l'automazione e l'intelligenza artificiale. È inoltre possibile eseguire ulteriori passaggi di correzione per risolvere l'attacco. 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>Eventi imprevisti e avvisi nel Microsoft 365 Defender portale

È possibile gestire gli eventi imprevisti & avvisi **> eventi** imprevisti sulla barra di avvio veloce del portale di Microsoft 365 Defender ([security.microsoft.com](https://security.microsoft.com)). Di seguito viene riportato un esempio.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Pagina Eventi imprevisti nel portale Microsoft 365 Defender utenti":::

Se si seleziona un nome di evento imprevisto, viene visualizzato un riepilogo dell'evento imprevisto e viene fornito l'accesso alle schede con informazioni aggiuntive.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Esempio della pagina Riepilogo per un evento imprevisto nel portale Microsoft 365 Defender":::

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

  Tutte le [indagini automatizzate attivate](m365d-autoir.md) dagli avvisi nell'evento imprevisto.

- Prova e risposta

  Tutti gli eventi supportati e le entità sospette negli avvisi nell'evento imprevisto.

- Graph (in anteprima)

  Figura che mostra la connessione degli avvisi agli asset che hanno effetto nell'organizzazione.

Ecco la relazione tra un evento imprevisto e i relativi dati e le schede di un evento imprevisto nel Microsoft 365 Defender portale.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Relazione di un evento imprevisto e dei relativi dati con le schede di un evento imprevisto nel Microsoft 365 Defender portale":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Flusso di lavoro di risposta agli eventi imprevisti di esempio per Microsoft 365 Defender

Ecco un flusso di lavoro di esempio per rispondere a eventi imprevisti in Microsoft 365 con il Microsoft 365 Defender portale.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Esempio di flusso di lavoro di risposta a eventi imprevisti per Microsoft 365":::

Su base continuativa, identificare gli eventi imprevisti con priorità più alta per l'analisi e la risoluzione nella coda degli eventi imprevisti e prepararli per la risposta. Questa è una combinazione di:

- [Per determinare](incident-queue.md) gli eventi imprevisti con priorità più alta, è necessario filtrare e ordinare la coda degli eventi imprevisti.
- [Gestire](manage-incidents.md) gli eventi imprevisti modificandone il titolo, assegnandoli a un analista e aggiungendo tag e commenti.

1. Per ogni evento imprevisto, avviare [un'analisi e un attacco:](investigate-incidents.md)
 
   1. Visualizzare il riepilogo dell'evento imprevisto per comprendere l'ambito e la gravità e le entità interessate **(scheda** Riepilogo).

   1. Iniziare ad analizzare gli avvisi per comprenderne l'origine, l'ambito e la gravità **(scheda** Avvisi).

   1. In base alle esigenze, raccogliere informazioni sui dispositivi, gli utenti e le cassette postali influenzati (le schede **Dispositivi,** **Utenti** e **Cassette** postali).

   1. Vedere come Microsoft 365 Defender [ha risolto automaticamente alcuni avvisi](m365d-autoir.md) (scheda Indagini). 
   
   1. Se necessario, usare le informazioni nel set di dati per l'evento imprevisto per ulteriori informazioni (scheda **Prova e** risposta).

2. Dopo o durante l'analisi, eseguire il contenimento per ridurre qualsiasi ulteriore impatto dell'attacco e dell'eliminazione della minaccia alla sicurezza.

3. Per quanto possibile, eseguire il ripristino dall'attacco ripristinando le risorse del tenant allo stato in cui si trovavano prima dell'incidente.

4. [Risolvere](manage-incidents.md#resolve-an-incident) l'evento imprevisto e richiedere tempo per l'apprendimento post-incidente per:

   - Comprendere il tipo di attacco e il relativo impatto.
   - Ricercare l'attacco in [Threat Analytics](threat-analytics.md) e nella community di sicurezza per una tendenza di attacco alla sicurezza.
   - Richiamare il flusso di lavoro utilizzato per risolvere l'evento imprevisto e aggiornare i flussi di lavoro, i processi, i criteri e i playbook standard in base alle esigenze.
   - Determinare se sono necessarie modifiche alla configurazione della sicurezza e implementarle.

Se non si ha di [](incidents-overview.md) che fare con l'analisi della sicurezza, vedere l'introduzione alla risposta al primo evento imprevisto per ulteriori informazioni e per analizzare un evento imprevisto di esempio.

Per ulteriori informazioni sulla risposta agli eventi imprevisti tra i prodotti Microsoft, vedere [questo articolo](/security/compass/incident-response-overview).

## <a name="example-security-operations-for-microsoft-365-defender"></a>Operazioni di sicurezza di esempio per Microsoft 365 Defender

Ecco un esempio di operazioni di sicurezza (SecOps) per Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Esempio di operazioni di sicurezza per Microsoft 365 Defender":::

Le attività giornaliere possono includere:

- [Gestione](manage-incidents.md) degli eventi imprevisti
- Revisione delle [azioni di indagine e risposta automatizzate (AIR)](m365d-action-center.md) nel centro notifiche
- Analisi delle minacce più [recenti](threat-analytics.md)
- [Risposta](investigate-incidents.md) agli eventi imprevisti

Le attività mensili possono includere:

- Revisione delle [impostazioni AIR](m365d-configure-auto-investigation-response.md)
- Esame del [punteggio sicuro e](microsoft-secure-score-improvement-actions.md) della gestione delle & delle [minacce](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Creazione di report alla catena di gestione della sicurezza IT

Le attività trimestrali possono includere una relazione e un briefing dei risultati della sicurezza al Chief Information Security Officer (CISO).

Le attività annuali possono includere l'esecuzione di un grave evento imprevisto o di violazione per testare il personale, i sistemi e i processi. 

Le attività giornaliere, mensili, trimestrali e annuali possono essere utilizzate per aggiornare o perfezionare processi, criteri e configurazioni di sicurezza.

### <a name="secops-resources-across-microsoft-products"></a>Risorse SecOps tra i prodotti Microsoft

Per ulteriori informazioni su SecOps nei prodotti Microsoft, vedere queste risorse:

- [Funzionalità](/security/compass/security-operations-capabilities)
- [Procedure consigliate](/security/compass/security-operations)
- [Video e diapositive](/security/compass/security-operations-videos-and-decks)

## <a name="next-steps"></a>Passaggi successivi

**Se non si ha la novità dell'analisi** della sicurezza e della risposta agli eventi imprevisti:

- Vedi la procedura [dettagliata](first-incident-overview.md) Rispondi al primo incidente per ottenere una presentazione guidata di un processo tipico di analisi, correzione e revisione post-incidente nel portale di Microsoft 365 Defender con un attacco di esempio.

**Se si ha esperienza con l'analisi** della sicurezza e la risposta agli incidenti:

- Introduzione alla coda degli eventi imprevisti dalla **pagina** Eventi imprevisti del Microsoft 365 Defender portale. Da qui è possibile:

  - Vedere quali eventi imprevisti devono essere [classificati in](incident-queue.md) base alla gravità e ad altri fattori. 

  - [Gestire gli eventi imprevisti,](manage-incidents.md)che includono la ridenominazione, l'assegnazione, la classificazione e l'aggiunta di tag e commenti in base al flusso di lavoro di gestione degli eventi imprevisti.

  - Eseguire [indagini](investigate-incidents.md) su eventi imprevisti.

- Vedi questi [playbook di risposta agli eventi imprevisti](/security/compass/incident-response-playbooks) per indicazioni dettagliate su phishing, spray per password e attacchi di concessione del consenso delle app.

