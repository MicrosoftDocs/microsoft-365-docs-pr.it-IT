---
title: Avvisi per la gestione dei rischi Insider
description: Informazioni sugli avvisi per la gestione dei rischi Insider in Microsoft 365
keywords: Microsoft 365, rischio Insider, gestione dei rischi, conformità
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
ms.openlocfilehash: 602571e5cbd3132209382ca2e2a3d8941ea8ab2e
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208827"
---
# <a name="insider-risk-management-alerts"></a>Avvisi per la gestione dei rischi Insider

Gli avvisi per la gestione dei rischi Insider vengono generati automaticamente dagli indicatori di rischio definiti nei criteri di gestione dei rischi Insider. Questi avvisi forniscono agli analisti e agli investigatori della conformità una visione a tutto tondo dello stato di rischio corrente e consentono all'organizzazione di valutarlo ed eseguire azioni per i rischi individuati. Per impostazione predefinita, i criteri generano una determinata quantità di avvisi di gravità bassa, media e alta, ma è possibile aumentare o ridurre il [volume](insider-risk-management-settings.md#alert-volume) degli avvisi in base alle proprie esigenze. Inoltre, è possibile configurare la soglia di [avviso per gli indicatori](insider-risk-management-settings.md#indicator-level-settings-preview) dei criteri quando si crea un nuovo criterio con la procedura guidata dei criteri.

## <a name="alert-dashboard"></a>Dashboard degli avvisi

Il dashboard di avviso **per i rischi** Insider consente di visualizzare e agire sugli avvisi generati dai criteri di rischio Insider. Ogni widget report visualizza le informazioni degli ultimi 30 giorni.

- **Avvisi da esaminare:** viene elencato il numero totale di avvisi che devono essere esaminati e valutati, inclusa una suddivisione in base alla gravità dell'avviso.
- **Avvisi aperti negli ultimi 30** giorni: numero totale di avvisi creati dai criteri corrispondenti negli ultimi 30 giorni, ordinati in base ai livelli di gravità degli avvisi alti, medi e bassi.
- **Tempo medio per la risoluzione degli avvisi**: un riepilogo delle statistiche degli avvisi utili:
    - Tempo medio per la risoluzione degli avvisi di gravità elevata, elencati in ore, giorni o mesi.
    - Tempo medio per risolvere gli avvisi di gravità media, elencati in ore, giorni o mesi.
    - Tempo medio per risolvere gli avvisi di gravità bassa, elencati in ore, giorni o mesi.

![Dashboard di avviso per la gestione dei rischi Insider](../media/insider-risk-alerts-dashboard.png)

>[!NOTE]
>La gestione dei rischi Insider usa la limitazione degli avvisi integrata per proteggere e ottimizzare l'analisi e l'esperienza di revisione dei rischi. Questa limitazione protegge da problemi che potrebbero causare un sovraccarico di avvisi per i criteri, ad esempio connettori di dati non configurati correttamente o criteri DLP. Di conseguenza, potrebbe verificarsi un ritardo nella visualizzazione di nuovi avvisi per un utente.

## <a name="alert-status-and-severity"></a>Stato e gravità dell'avviso

È possibile valutarne lo stato in uno dei seguenti stati:

- **Confermato:** avviso confermato e assegnato a un caso nuovo o esistente.
- **Ignorato:** un avviso è stato ignorato come innocuo nel processo di triage.
- **Revisione delle esigenze:** un nuovo avviso in cui non sono ancora state intraprese azioni di valutazione.
- **Risolto:** avviso che fa parte di un caso chiuso e risolto.

I punteggi di rischio degli avvisi vengono calcolati automaticamente da diversi indicatori di attività di rischio. Questi indicatori includono il tipo di attività di rischio, il numero e la frequenza dell'occorrenza dell'attività, la cronologia dell'attività di rischio utente e l'aggiunta di rischi di attività che possono aumentare la gravità dell'attività. Il punteggio di rischio dell'avviso determina l'assegnazione programmatica di un livello di gravità del rischio per ogni avviso e non può essere personalizzato. Se gli avvisi non vengono ancora e le attività di rischio continuano ad accumularsi nell'avviso, il livello di gravità del rischio può aumentare. Gli analisti e gli investigatori dei rischi possono utilizzare la gravità del rischio degli avvisi per facilitare la valutazione degli avvisi in conformità ai criteri e agli standard di rischio dell'organizzazione.

I livelli di gravità del rischio di avviso sono:

- **Gravità elevata:** le attività e gli indicatori per l'avviso rappresentano un rischio significativo. Le attività di rischio associate sono gravi, ripetitive e sono fortemente correlate ad altri fattori di rischio significativi.
- **Gravità media:** le attività e gli indicatori per l'avviso rappresentano un rischio moderato. Le attività di rischio associate sono moderate, frequenti e hanno una correlazione con altri fattori di rischio.
- **Gravità bassa:** le attività e gli indicatori per l'avviso rappresentano un rischio minore. Le attività di rischio associate sono minori, più raramente e non si diffondono ad altri fattori di rischio significativi.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Filtrare gli avvisi nel dashboard degli avvisi

A seconda del numero e del tipo di criteri di gestione dei rischi Insider attivi nell'organizzazione, esaminare una coda di avvisi di grandi dimensioni può essere difficile. L'uso dei filtri di avviso può aiutare gli analisti e gli investigatori a ordinare gli avvisi in base a diversi attributi. Per filtrare gli avvisi nel **dashboard degli** avvisi, selezionare il **controllo** Filtro. È possibile filtrare gli avvisi in base a uno o più attributi:

- **Stato:** selezionare uno o più valori di stato per filtrare l'elenco di avvisi. Le opzioni sono *Confirmed,* *Dismissed,* *Needs review* e *Resolved.*
- **Gravità: selezionare** uno o più livelli di gravità del rischio di avviso per filtrare l'elenco degli avvisi. Le opzioni disponibili *sono Alta,* *Media* e *Bassa.*
- **Ora rilevata:** selezionare le date di inizio e di fine per la creazione dell'avviso.
- **Criterio:** selezionare uno o più criteri per filtrare gli avvisi generati dai criteri selezionati.

## <a name="search-alerts-on-the-alert-dashboard"></a>Cercare gli avvisi nel dashboard degli avvisi

Per cercare una parola specifica nel nome dell'avviso, selezionare il **controllo** Ricerca e digitare la parola da cercare. Nei risultati della ricerca viene visualizzato qualsiasi avviso per i criteri contenente la parola definita nella ricerca.

## <a name="triage-alerts"></a>Avvisi di triage

Per la valutazione di un avviso per i rischi Insider, completare i passaggi seguenti:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la scheda **Avvisi.**
2. Nel **dashboard Degli avvisi** selezionare l'avviso che si desidera utilizzare.
3. Nel riquadro **dei dettagli degli avvisi** è possibile esaminare le schede seguenti e esaminare l'avviso:
    - **Riepilogo:** questa scheda contiene informazioni generali sull'avviso e consente di confermare l'avviso e creare un nuovo caso o di ignorare l'avviso. Include lo stato corrente dell'avviso e il livello di gravità del rischio dell'avviso, elencato come *Alto,* *Medio* o *Basso.* Il livello di gravità può aumentare o diminuire nel tempo se l'avviso non viene valutato.
        - **Cosa è successo:** visualizza le prime tre attività di rischio e le corrispondenze dei criteri durante il periodo di valutazione dell'attività, incluso il tipo di violazione associata all'attività.
        - **Dettagli utente**: visualizza informazioni generali sull'utente assegnato all'avviso. Se l'anonimizzazione è abilitata, i campi nome utente, indirizzo di posta elettronica, alias e organizzazione vengono anonimi.
        - **Dettagli avviso:** include il periodo di tempo dalla generazione dell'avviso, i criteri che hanno generato l'avviso e il caso generato dall'avviso. Per i nuovi avvisi, **nel campo** Caso viene visualizzato Nessuno.
        - **Contenuto rilevato:** include il contenuto associato alle attività di rischio per l'avviso e riepiloga gli eventi di attività per aree chiave. Selezionando un collegamento attività si apre Esplora attività e vengono visualizzati ulteriori dettagli sull'attività.
    - **Attività utente:** in questa scheda viene visualizzata la cronologia delle attività per l'utente associato all'avviso. Questa cronologia include altri avvisi e attività correlati agli indicatori di rischio definiti nel modello assegnato al criterio per questo avviso. Questa cronologia consente agli analisti e agli investigatori del rischio di fattori di qualsiasi comportamento rischioso passato per il dipendente nell'ambito del processo di valutazione.
    - **Azioni**: per ogni avviso sono disponibili le azioni seguenti:
        - **Apri visualizzazione espansa:** apre il dashboard **esplora** attività.
        - **Conferma e crea caso:** utilizzare questa azione per confermare e creare un nuovo caso per tutti gli avvisi associati a un utente. Questa azione modifica automaticamente lo stato dell'avviso *in Confermata.*
        - **Ignora avviso:** utilizzare questa azione per ignorare l'avviso. Questa azione modifica lo stato dell'avviso in *Risolto.*

## <a name="activity-explorer-preview"></a>Esplora attività (anteprima)

>[!NOTE]
>Esplora attività è disponibile nell'area di gestione degli avvisi per gli utenti che attivano eventi dopo che questa funzionalità è disponibile nell'organizzazione.

Esplora attività offre agli investigatori e agli analisti dei rischi uno strumento analitico completo che fornisce informazioni dettagliate sugli avvisi. Con Esplora attività, i revisori possono esaminare rapidamente una sequenza temporale delle attività rischiose rilevate e identificare e filtrare tutte le attività di rischio associate agli avvisi. Per filtrare gli avvisi in Esplora attività, selezionare il controllo Filtro. È possibile filtrare gli avvisi in base a uno o più attributi elencati nel riquadro dei dettagli per l'avviso. Esplora attività supporta anche colonne personalizzabili per aiutare gli investigatori e gli analisti a concentrare il dashboard sulle informazioni più importanti per loro.

![Panoramica di Insider Risk Management Activity Explorer](../media/insider-risk-management-activity-explorer.png)

Per usare Esplora **attività,** completa i passaggi seguenti:

1. Nel Centro conformità Microsoft 365 passare a **Gestione dei rischi Insider** e selezionare la scheda **Avvisi.**
2. Nel **dashboard Degli avvisi** selezionare l'avviso che si desidera utilizzare.
3. Nel riquadro **dei dettagli degli avvisi** selezionare Apri visualizzazione **espansa.**
4. Nella pagina dell'avviso selezionato selezionare la **scheda Esplora** attività.

Quando esaminano le attività in Esplora attività, gli investigatori e gli analisti possono selezionare un'attività specifica e aprire il riquadro dei dettagli dell'attività. Nel riquadro vengono visualizzate informazioni dettagliate sull'attività che gli investigatori e gli analisti possono utilizzare durante il processo di analisi degli avvisi. Le informazioni dettagliate possono fornire contesto per l'avviso e facilitare l'identificazione dell'ambito completo dell'attività di rischio che ha attivato l'avviso.

![Dettagli di Insider Risk Management Activity Explorer](../media/insider-risk-management-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Creare un caso per un avviso

Quando l'avviso viene esaminato e esaminato, è possibile creare un nuovo caso per analizzare ulteriormente l'attività di rischio. Per creare un caso per un avviso, attenersi alla seguente procedura:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la scheda **Avvisi.**
2. Nel **dashboard Degli avvisi** selezionare l'avviso per cui si desidera confermare e creare un nuovo caso.
3. Nel riquadro **dei dettagli degli avvisi** selezionare Azioni   >  **Confermare gli avvisi & creare il caso.**
4. Nella finestra **di dialogo** Conferma avviso e crea caso di rischio Insider immetti un nome per il caso, seleziona gli utenti da aggiungere come collaboratori e aggiungi i commenti in base alle condizioni applicabili. I commenti vengono aggiunti automaticamente al caso come nota del caso.
5. Selezionare **Crea caso** per creare un nuovo caso o Annulla per chiudere la finestra di dialogo senza creare un caso. 

Dopo la creazione del caso, gli investigatori e gli analisti possono gestire e agire sul caso. Per altri [dettagli, vedi l'articolo](insider-risk-management-cases.md) sul caso di gestione dei rischi Insider.
