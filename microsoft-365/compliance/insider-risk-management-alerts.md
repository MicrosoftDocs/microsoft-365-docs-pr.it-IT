---
title: Avvisi relativi alla gestione dei rischi Insider
description: Informazioni sugli avvisi relativi alla gestione dei rischi insider in Microsoft 365
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
ms.openlocfilehash: 0c0c529569ae1c4ca0ed54863b8b2ddcfcfcba2d
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416860"
---
# <a name="insider-risk-management-alerts"></a>Avvisi relativi alla gestione dei rischi Insider

Gli avvisi di gestione dei rischi Insider vengono generati automaticamente dagli indicatori di rischio definiti nei criteri di gestione dei rischi. Gli avvisi forniscono agli analisti e ai ricercatori una panoramica generale dello stato del rischio corrente e consentono all'organizzazione di valutare e intraprendere azioni per i rischi individuati. Per impostazione predefinita, i criteri generano una determinata quantità di avvisi di gravità bassa, media e alta, ma è possibile [aumentare o diminuire il volume degli avvisi](insider-risk-management-settings.md#alert-volume) per soddisfare le proprie esigenze. È inoltre possibile configurare la [soglia di avviso per gli indicatori dei criteri](insider-risk-management-settings.md#indicator-level-settings-preview) quando si crea un nuovo criterio con la creazione guidata criteri.

## <a name="alert-dashboard"></a>Dashboard avvisi

Il dashboard di **avviso** dei rischi insider consente di visualizzare e agire su avvisi generati da criteri di rischio Insider. Ogni widget del report Visualizza informazioni per gli ultimi 30 giorni.

- **Avvisi per la revisione**: sono elencati il numero totale di avvisi che richiedono la revisione e la valutazione, inclusa una scomposizione in base alla gravità degli avvisi.
- **Aprire avvisi negli ultimi 30 giorni**: il numero totale di avvisi creati da criteri corrisponde negli ultimi 30 giorni, ordinati in base ai livelli di gravità degli avvisi alti, medi e bassi.
- **Tempo medio per la risoluzione degli avvisi**: un riepilogo delle statistiche utili sugli avvisi:
    - Tempo medio per risolvere gli avvisi di gravità elevata, elencati in ore, giorni o mesi.
    - Tempo medio per la risoluzione degli avvisi di gravità media, elencati in ore, giorni o mesi.
    - Tempo medio per risolvere gli avvisi di gravità bassa, elencati in ore, giorni o mesi.

![Dashboard di avviso gestione dei rischi Insider](../media/insider-risk-alerts-dashboard.png)

>[!NOTE]
>Insider Risk Management utilizza la limitazione degli avvisi incorporata per proteggere e ottimizzare l'analisi dei rischi e l'esperienza di revisione. Questa limitazione protegge i problemi che possono comportare un sovraccarico di avvisi sui criteri, ad esempio i connettori dati non configurati correttamente o i criteri DLP. Di conseguenza, potrebbe verificarsi un ritardo nella visualizzazione di nuovi avvisi per un utente.

## <a name="alert-status-and-severity"></a>Stato avviso e gravità

È possibile valutare gli avvisi in uno degli Stati seguenti:

- **Confermato**: avviso confermato e assegnato a un caso nuovo o esistente.
- **Respinto**: un avviso è stato respinto come benigno nel processo di valutazione.
- **Revisione delle esigenze**: un nuovo avviso in cui le azioni di valutazione non sono state ancora eseguite.
- **Risolto**: avviso che fa parte di un caso chiuso e risolto.

I punteggi dei rischi di avviso vengono calcolati automaticamente da diversi indicatori di attività di rischio. Tali indicatori includono il tipo di attività di rischio, il numero e la frequenza dell'evento attività, la cronologia delle attività di rischio per gli utenti e l'aggiunta dei rischi di attività che possono aumentare la gravità dell'attività. Il Punteggio di rischio avviso determina l'assegnazione a livello di programmazione di un livello di gravità dei rischi per ogni avviso e non può essere personalizzato. Se gli avvisi rimangono non valutati e le attività di rischio continuano a essere attribuite all'avviso, il livello di gravità del rischio può aumentare. Gli analisti di rischio e gli investigatori possono utilizzare la severità dei rischi di avviso per aiutare gli avvisi di valutazione in conformità con le norme e i criteri di rischio dell'organizzazione.

I livelli di gravità dei rischi di avviso sono:

- **Gravità elevata**: le attività e gli indicatori per l'avviso presentano un rischio significativo. Le attività associate ai rischi sono gravi, ripetitive e corelascono fortemente ad altri fattori di rischio significativi.
- **Gravità media**: le attività e gli indicatori dell'avviso rappresentano un rischio moderato. Le attività associate ai rischi sono moderate, frequenti e hanno una certa correlazione con altri fattori di rischio.
- **Gravità bassa**: le attività e gli indicatori dell'avviso rappresentano un rischio minore. Le attività associate ai rischi sono minime, più rare e non coriguardano altri fattori di rischio significativi.

## <a name="filter-alerts"></a>Filtrare gli avvisi

A seconda del numero e del tipo di criteri di gestione dei rischi Insider attivi nell'organizzazione, la revisione di una coda di avvisi di grandi dimensioni può essere impegnativa. L'utilizzo dei filtri avvisi può consentire agli analisti e agli investigatori di ordinare gli avvisi in base a diversi attributi. Per filtrare gli avvisi nel **Dashboard avvisi**, selezionare il controllo **filtro** . È possibile filtrare gli avvisi in base a uno o più attributi:

- **Stato**: selezionare uno o più valori di stato per filtrare l'elenco degli avvisi. Le opzioni vengono *confermate*, *ignorate*, *devono essere riesaminate*e *risolte*.
- **Severity**: selezionare uno o più livelli di gravità dei rischi di avviso per filtrare l'elenco degli avvisi. Le opzioni sono *High*, *medium*e *low*.
- **Tempo rilevato**: selezionare le date di inizio e di fine per il momento in cui è stato creato l'avviso.
- **Criterio**: selezionare uno o più criteri per filtrare gli avvisi generati dai criteri selezionati.

## <a name="search-alerts"></a>Avvisi di ricerca

Per cercare il nome dell'avviso per una parola specifica, selezionare il controllo di **ricerca** e digitare la parola da cercare. Nei risultati della ricerca viene visualizzato qualsiasi avviso di criteri contenente la parola definita nella ricerca.

## <a name="triage-alerts"></a>Avvisi di valutazione

Per valutare un avviso di rischio Insider, eseguire i passaggi seguenti:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **avvisi** .
2. Nel **Dashboard avvisi**selezionare l'avviso che si desidera sottoporre a triage.
3. Nel **riquadro dei dettagli avvisi**è possibile esaminare le schede seguenti e valutare l'avviso:
    - **Panoramica**: questa scheda contiene informazioni generali sull'avviso e consente di confermare l'avviso e creare un nuovo caso oppure di chiudere l'avviso.
        - **Stato**: stato dell'avviso
        - **Tempo rilevato**: il periodo di tempo da quando l'avviso è stato generato.
        - **Corrispondenze di criteri**: i criteri che hanno generato l'avviso sono elencati. Ogni criterio è elencato come un collegamento ai dettagli del criterio.
        - **Severity**: il livello di gravità del rischio di avviso corrente, elencato come *alto*, *medio*o *basso*. Il livello di gravità può aumentare o diminuire nel tempo se l'avviso non è valutato.
        - **Caso**: se confermata, il caso generato dall'avviso è elencato. Per i nuovi avvisi, il campo **case** non Visualizza *nessuno*.
    - **Attività utente**: questa scheda Visualizza la cronologia delle attività per l'utente associato all'avviso. Questa cronologia include altri avvisi e attività correlati agli indicatori di rischio definiti nel modello assegnato ai criteri per questo avviso. Questa cronologia consente agli analisti e ai ricercatori di rischi di fattorizzare qualsiasi comportamento di rischio passato per il dipendente nell'ambito del processo di valutazione.
    - **Profilo utente**: questa scheda Visualizza le informazioni generali sul dipendente assegnato all'avviso. Se Anonymization è abilitato, il nome utente, l'indirizzo di posta elettronica, l'alias e i campi dell'organizzazione sono anonimi.
    - **Confermare e creare il caso**: visibile tra tutte le schede, utilizzare questo pulsante per confermare e creare un nuovo caso. Questa azione consente di modificare automaticamente lo stato dell'avviso su *confermato*.
    - **Ignora avviso**: visibile in tutte le schede, utilizzare questo pulsante per chiudere l'avviso. Questa azione consente di modificare lo stato dell'avviso su *risolto*.

## <a name="create-a-case-for-an-alert"></a>Creare un caso per un avviso

Come avviso viene esaminato e valutato, è possibile creare un nuovo caso per analizzare ulteriormente l'attività di rischio. Per creare un caso per un avviso, eseguire la procedura seguente:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **avvisi** .
2. Nel **Dashboard avvisi**selezionare l'avviso per il quale si desidera confermare e creare un nuovo caso.
3. Nel **riquadro dei dettagli avvisi**selezionare **conferma e crea caso**.
4. Nella finestra di dialogo **conferma avviso e crea caso di rischio Insider** immettere un nome per il caso, selezionare gli utenti da aggiungere come collaboratori e aggiungere i commenti come applicabili. I commenti vengono aggiunti automaticamente al caso come nota del caso.
5. Selezionare **Crea caso** per creare un nuovo caso o seleziona **Annulla** per chiudere la finestra di dialogo senza creare un caso.
