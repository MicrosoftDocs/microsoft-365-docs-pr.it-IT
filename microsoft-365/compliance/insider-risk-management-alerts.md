---
title: Avvisi per la gestione dei rischi Insider
description: Informazioni sugli avvisi di gestione dei rischi insider in Microsoft 365
keywords: Microsoft 365, rischio insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 2a21dfead9b1f1ba2f05fc7629ce4fcda9991017
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819978"
---
# <a name="insider-risk-management-alerts"></a>Avvisi per la gestione dei rischi Insider

Gli avvisi di gestione dei rischi Insider vengono generati automaticamente dagli indicatori di rischio definiti nei criteri di gestione dei rischi insider. Questi avvisi offrono agli analisti e agli investigatori della conformità una visione a tutto tondo dello stato di rischio corrente e consentono all'organizzazione di eseguire analisi ed azioni per i rischi individuati. Per impostazione predefinita, i criteri generano una determinata quantità di avvisi di gravità bassa, media e alta, ma è possibile aumentare o ridurre il [volume](insider-risk-management-settings.md#alert-volume) degli avvisi in base alle proprie esigenze. Inoltre, è possibile configurare la soglia di [avviso per gli indicatori dei](insider-risk-management-settings.md#indicator-level-settings-preview) criteri quando si crea un nuovo criterio con la procedura guidata dei criteri.

## <a name="alert-dashboard"></a>Dashboard degli avvisi

Il dashboard di avviso **per il rischio** insider consente di visualizzare e agire sugli avvisi generati dai criteri di rischio insider. Ogni widget di report visualizza informazioni per gli ultimi 30 giorni.

- **Totale avvisi che devono essere esaminati**: viene elencato il numero totale di avvisi che necessitano di revisione e valutazione, inclusa una suddivisione in base alla gravità dell'avviso.
- **Avvisi aperti negli ultimi 30** giorni: numero totale di avvisi creati dai criteri corrispondenti negli ultimi 30 giorni, ordinati in base ai livelli di gravità degli avvisi alti, medi e bassi.
- **Tempo medio per la risoluzione degli avvisi**: riepilogo delle statistiche di avviso utili:
    - Tempo medio per la risoluzione degli avvisi di gravità elevata, elencati in ore, giorni o mesi.
    - Tempo medio per la risoluzione degli avvisi di gravità media, elencati in ore, giorni o mesi.
    - Tempo medio per la risoluzione degli avvisi di gravità bassa, elencati in ore, giorni o mesi.

![Dashboard di avviso per la gestione dei rischi Insider](../media/insider-risk-alerts-dashboard.png)

>[!NOTE]
>La gestione dei rischi Insider usa la limitazione degli avvisi integrata per proteggere e ottimizzare l'analisi e l'esperienza di revisione dei rischi. Questa limitazione protegge da problemi che potrebbero causare un sovraccarico di avvisi dei criteri, ad esempio connettori di dati non configurati correttamente o criteri DLP. Di conseguenza, potrebbe verificarsi un ritardo nella visualizzazione di nuovi avvisi per un utente.

## <a name="alert-status-and-severity"></a>Stato e gravità dell'avviso

È possibile eseguire il triage degli avvisi in uno dei seguenti stati:

- **Confirmed**: avviso confermato e assegnato a un caso nuovo o esistente.
- **Dismissed**: avviso ignorato come benigno nel processo di triage.
- **Revisione delle esigenze**: nuovo avviso in cui non sono ancora state eseguite azioni di valutazione.
- **Risolto**: avviso che fa parte di un caso chiuso e risolto.

I punteggi dei rischi di avviso vengono calcolati automaticamente da diversi indicatori di attività di rischio. Questi indicatori includono il tipo di attività di rischio, il numero e la frequenza dell'occorrenza dell'attività, la cronologia dell'attività di rischio utente e l'aggiunta di rischi di attività che possono aumentare la gravità dell'attività. Il punteggio di rischio dell'avviso determina l'assegnazione programmatica di un livello di gravità del rischio per ogni avviso e non può essere personalizzato. Se gli avvisi non vengono ancora inviati e le attività di rischio continuano a accumularsi nell'avviso, il livello di gravità del rischio può aumentare. Gli analisti e gli investigatori del rischio possono utilizzare la gravità del rischio degli avvisi per facilitare la valutazione degli avvisi in base ai criteri e agli standard di rischio dell'organizzazione.

I livelli di gravità del rischio di avviso sono:

- **Gravità elevata:** le attività e gli indicatori per l'avviso rappresentano un rischio significativo. Le attività di rischio associate sono gravi, ripetitive e sono fortemente correlate ad altri fattori di rischio significativi.
- **Gravità media:** le attività e gli indicatori per l'avviso rappresentano un rischio moderato. Le attività di rischio associate sono moderate, frequenti e hanno una correlazione con altri fattori di rischio.
- **Gravità bassa:** le attività e gli indicatori per l'avviso rappresentano un rischio minore. Le attività di rischio associate sono secondarie, più poco frequenti e non sono correlate ad altri fattori di rischio significativi.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Filtrare gli avvisi nel dashboard degli avvisi

A seconda del numero e del tipo di criteri di gestione dei rischi insider attivi nell'organizzazione, la revisione di una coda di avvisi di grandi dimensioni può essere difficile. L'uso di filtri di avviso può aiutare analisti e investigatori a ordinare gli avvisi in base a diversi attributi. Per filtrare gli avvisi nel **dashboard Avvisi,** selezionare il **controllo** Filtro. È possibile filtrare gli avvisi in base a uno o più attributi:

- **Stato:** selezionare uno o più valori di stato per filtrare l'elenco degli avvisi. Le opzioni sono *Confirmed,* *Dismissed,* *Needs review* e *Resolved.*
- **Gravità:** selezionare uno o più livelli di gravità del rischio di avviso per filtrare l'elenco degli avvisi. Le opzioni sono *High,* *Medium* e *Low.*
- **Ora rilevata:** selezionare le date di inizio e di fine per la creazione dell'avviso.
- **Criterio:** selezionare uno o più criteri per filtrare gli avvisi generati dai criteri selezionati.

## <a name="search-alerts-on-the-alert-dashboard"></a>Ricerca degli avvisi nel dashboard degli avvisi

Per cercare una parola specifica nel nome dell'avviso, selezionare il **controllo Cerca** e digitare la parola da cercare. Nei risultati della ricerca viene visualizzato qualsiasi avviso per i criteri contenente la parola definita nella ricerca.

## <a name="triage-alerts"></a>Avvisi di triage

Per eseguire la valutazione di un avviso di rischio insider, completare i passaggi seguenti:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei** rischi Insider e selezionare la **scheda** Avvisi.
2. Nel **dashboard Avvisi** selezionare l'avviso che si desidera utilizzare.
3. Nel riquadro **dei dettagli degli avvisi** è possibile esaminare le schede seguenti e analizzare l'avviso:
    - **Riepilogo:** questa scheda contiene informazioni generali sull'avviso e consente di confermare l'avviso e creare un nuovo caso o di ignorare l'avviso. Include lo stato corrente per l'avviso e il livello di gravità del rischio di avviso, elencato come *Alto,* *Medio* o *Basso.* Il livello di gravità può aumentare o diminuire nel tempo se l'avviso non viene triaged.
        - **What happened (preview)**: Visualizza le prime tre attività di rischio e le corrispondenze dei criteri durante il periodo di valutazione dell'attività, incluso il tipo di violazione associata all'attività e il numero di occorrenze.
        - **Dettagli utente**: visualizza informazioni generali sull'utente assegnato all'avviso. Se l'anonimizzazione è abilitata, i campi nome utente, indirizzo di posta elettronica, alias e organizzazione vengono anonimi.
        - **Dettagli avviso**: include il periodo di tempo dopo la generazione dell'avviso, i criteri che hanno generato l'avviso e il caso generato dall'avviso. Per i nuovi avvisi, nel **campo Caso** viene visualizzato Nessuno.
        - **Contenuto rilevato (anteprima):** include il contenuto associato alle attività di rischio per l'avviso e riepiloga gli eventi di attività in base alle aree chiave. Se si seleziona un collegamento a un'attività, viene aperto Esplora attività e vengono visualizzati ulteriori dettagli sull'attività.
    - **Attività utente**: in questa scheda viene visualizzata la cronologia delle attività per l'utente associato all'avviso. Questa cronologia include altri avvisi e attività correlati agli indicatori di rischio definiti nel modello assegnato al criterio per questo avviso. Questa cronologia consente agli analisti e agli investigatori del rischio di fattori di qualsiasi comportamento rischioso passato per il dipendente nell'ambito del processo di valutazione.
    - **Azioni**: sono disponibili le azioni seguenti per ogni avviso:
        - **Apri visualizzazione espansa**: apre il dashboard **esplora** attività.
        - **Conferma e crea caso**: utilizzare questa azione per confermare e creare un nuovo caso per tutti gli avvisi associati a un utente. Questa azione modifica automaticamente lo stato dell'avviso *in Confermato*.
        - **Ignora avviso:** utilizzare questa azione per ignorare l'avviso. Questa azione modifica lo stato dell'avviso in *Risolto*.

## <a name="activity-explorer-preview"></a>Esplora attività (anteprima)

>[!NOTE]
>Esplora attività è disponibile nell'area di gestione degli avvisi per gli utenti che attivano eventi dopo che questa funzionalità è disponibile nell'organizzazione.

Esplora attività offre agli investigatori e agli analisti dei rischi uno strumento analitico completo che fornisce informazioni dettagliate sugli avvisi. Con Esplora attività, i revisori possono esaminare rapidamente una sequenza temporale delle attività rischiose rilevate e identificare e filtrare tutte le attività di rischio associate agli avvisi. Per filtrare gli avvisi in Esplora attività, selezionare il controllo Filtro. È possibile filtrare gli avvisi in base a uno o più attributi elencati nel riquadro dei dettagli per l'avviso. Esplora attività supporta anche colonne personalizzabili per consentire a investigatori e analisti di concentrare il dashboard sulle informazioni più importanti per loro.

![Panoramica di Insider Risk Management Activity Explorer](../media/insider-risk-activity-explorer.png)

Per usare **Esplora attività,** completare la procedura seguente:

1. Nel Centro conformità Microsoft 365 passare a Gestione dei rischi **Insider** e selezionare la **scheda** Avvisi.
2. Nel **dashboard Avvisi** selezionare l'avviso che si desidera utilizzare.
3. Nel riquadro **dei dettagli degli avvisi** selezionare Apri visualizzazione **espansa.**
4. Nella pagina dell'avviso selezionato selezionare la **scheda Esplora** attività.

Quando si esaminano le attività in Esplora attività, gli investigatori e gli analisti possono selezionare un'attività specifica e aprire il riquadro dei dettagli dell'attività. Nel riquadro vengono visualizzate informazioni dettagliate sull'attività che gli investigatori e gli analisti possono utilizzare durante il processo di analisi degli avvisi. Le informazioni dettagliate possono fornire contesto per l'avviso e facilitare l'identificazione dell'ambito completo dell'attività di rischio che ha attivato l'avviso.

![Dettagli dell'esplorazione delle attività di gestione dei rischi insider](../media/insider-risk-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Creare un caso per un avviso

Quando l'avviso viene esaminato e esaminato, è possibile creare un nuovo caso per analizzare ulteriormente l'attività di rischio. Per creare un caso per un avviso, attenersi alla seguente procedura:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei** rischi Insider e selezionare la **scheda** Avvisi.
2. Nel **dashboard Avvisi** selezionare l'avviso per cui si desidera confermare e creare un nuovo caso.
3. Nel riquadro **Dei dettagli degli avvisi** selezionare Azioni   >  **Confermare gli avvisi & creare il caso.**
4. Nella finestra **di dialogo Conferma avviso e crea** caso di rischio insider immetti un nome per il caso, seleziona gli utenti da aggiungere come collaboratori e aggiungi commenti come applicabili. I commenti vengono aggiunti automaticamente al caso come nota del caso.
5. Selezionare **Crea caso** per creare un nuovo caso o Annulla per chiudere la finestra di dialogo senza creare un caso. 

Dopo la creazione del caso, gli investigatori e gli analisti possono gestire e agire sul caso. Per altri [dettagli, vedi l'articolo](insider-risk-management-cases.md) caso di gestione dei rischi Insider.
