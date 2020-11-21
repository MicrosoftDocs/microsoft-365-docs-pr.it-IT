---
title: Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager aiuta le organizzazioni a semplificare e automatizzare le valutazioni dei rischi e suggerisce azioni consigliate per aiutare a gestire i rischi.
ms.openlocfilehash: 7bff6a2a7a150a08b98fe7a92cd71d266df9fda7
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376547"
---
# <a name="microsoft-compliance-manager"></a>Microsoft Compliance Manager

**In questo articolo:** Informazioni su cos'è Compliance Manager, su come semplificare la conformità e ridurre i rischi e i componenti chiave.

## <a name="whats-new-the-ga-release-of-compliance-manager"></a>Novità: la versione GA di Compliance Manager

Compliance Manager è ora generalmente disponibile (GA) come soluzione di gestione della conformità end-to-end all'interno del [centro conformità Microsoft 365](microsoft-365-compliance-center.md). Con questa versione, Compliance Manager completa la transizione dal suo percorso precedente nel portale Microsoft Service Trust. Compliance Manager è ora disponibile anche per i clienti di US Government community (GCC) moderato e GCC High.

Che cosa è iniziato come l'anteprima pubblica del Punteggio di conformità si è evoluta in uno strumento centralizzato con funzionalità di gestione della conformità avanzate e una maggiore facilità di utilizzo.  La versione GA apporta una raccolta più ampia di valutazioni predefinite per semplificare la scalabilità delle attività di conformità.

**Per ulteriori informazioni, vedere la versione GA:**
- Le [domande più frequenti](compliance-manager-faq.md) consentono di illustrare in modo approfondito l'evoluzione.
- Per ulteriori informazioni sui miglioramenti delle funzionalità di GA, vedere [questo post di Blog](https://aka.ms/compliancemanager/GAblog).

Guarda il video seguente per informazioni su come Compliance Manager può aiutare a semplificare la gestione della conformità dell'organizzazione:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a>Che cos'è Compliance Manager

[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) è una funzionalità del [centro conformità di Microsoft 365](microsoft-365-compliance-center.md) che consente di gestire i requisiti di conformità dell'organizzazione con maggiore facilità e convenienza. Compliance Manager può aiutare durante il viaggio di conformità, dall'inventario dei rischi per la protezione dei dati per la gestione delle complessità dell'implementazione dei controlli, della permanenza in corso con le normative e delle certificazioni e della creazione di rapporti con i revisori.

Compliance Manager consente di semplificare la conformità e di ridurre i rischi fornendo:

- Valutazioni precostruite per l'industria comune e standard regionali e regolamenti, o valutazioni personalizzate per soddisfare i requisiti di conformità univoci (le valutazioni disponibili dipendono dal contratto di licenza; Per ulteriori [informazioni](https://go.microsoft.com/fwlink/?linkid=2132371), vedere.

- Funzionalità del flusso di lavoro che consentono di completare efficacemente le valutazioni dei rischi tramite un unico strumento.

- Informazioni dettagliate sulle azioni di miglioramento consigliate per soddisfare gli standard e le normative più rilevanti per la propria organizzazione. Per le azioni gestite da Microsoft, vengono visualizzati i dettagli sull'implementazione e i risultati del controllo.

- Un punteggio di conformità basato sui rischi per facilitare la comprensione della postura di conformità misurando i progressi compiuti nel completamento delle azioni di miglioramento.

Il dashboard di Compliance Manager Mostra il Punteggio di conformità corrente, consente di visualizzare le esigenze di attenzione e di guidare le azioni di miglioramento principali. Di seguito è riportato un esempio di come sarà il dashboard di Compliance Manager:

![Compliance Manager-dashboard](../media/compliance-manager-dashboard.png "Dashboard di Compliance Manager")

## <a name="understanding-your-compliance-score"></a>Informazioni sul punteggio di conformità

Compliance Manager premia i punti per il completamento delle azioni di miglioramento adottate per conformarsi a un regolamento, uno standard o un criterio e combina tali punti in un punteggio di conformità globale. Ogni azione ha un impatto diverso sulla partitura a seconda dei possibili rischi coinvolti. Il Punteggio di conformità può contribuire a definire la priorità su quale azione concentrarsi per migliorare la posizione di conformità globale.

Compliance Manager fornisce un punteggio iniziale basato sulla linea di base per la protezione dei dati di Microsoft 365. Questa linea di base è un insieme di controlli che include le normative fondamentali e gli standard per la protezione dei dati e la governance dei dati generale.

##### <a name="learn-more"></a>Ulteriori informazioni

[Capire in che modo viene calcolato il Punteggio di conformità](compliance-score-calculation.md).

[Informazioni su come utilizzare le azioni di miglioramento](compliance-manager-improvement-actions.md).

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>Elementi chiave: controlli, valutazioni, modelli, azioni di miglioramento

Compliance Manager utilizza diversi elementi di dati per facilitare la gestione delle attività di conformità. Quando si utilizza Compliance Manager per assegnare, testare e monitorare le attività di conformità, è utile avere una conoscenza di base degli elementi chiave: controlli, valutazioni, modelli e azioni di miglioramento.

### <a name="controls"></a>Controlli

Un controllo è un requisito di una norma, di uno standard o di un criterio. Definisce come valutare e gestire la configurazione del sistema, il processo organizzativo e gli utenti responsabili della riunione di un requisito specifico di una norma, di uno standard o di un criterio.

Compliance Manager tiene traccia dei tipi di controlli seguenti:

1. **Controlli gestiti Microsoft**: controlli per i servizi cloud Microsoft, che Microsoft è responsabile dell'implementazione
2. **I controlli**: a volte definiti controlli gestiti dal cliente, questi sono i controlli implementati e gestiti dall'organizzazione
3. **Controlli condivisi**: questi sono i controlli che sia l'organizzazione che la responsabilità di Microsoft condividono per l'implementazione

##### <a name="learn-more"></a>Ulteriori informazioni

[Monitorare lo stato dei controlli](compliance-manager-assessments.md#monitor-assessment-progress-and-controls).

[Informazioni su come Compliance Manager valuta continuamente i controlli](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls).

### <a name="assessments"></a>Valutazioni

Una valutazione è il raggruppamento di controlli da una regolamentazione, standard o criteri specifici. Il completamento delle azioni all'interno di una valutazione consente di soddisfare i requisiti di una norma, di una normativa o di una legge. Ad esempio, si può avere una valutazione che, al termine di tutte le azioni al suo interno, contribuisca a portare le impostazioni di Microsoft 365 in linea con i requisiti ISO 27001.

Le valutazioni hanno diversi componenti:

- **Servizi nell'ambito**: l'insieme specifico di servizi Microsoft applicabile alla valutazione
- **Controlli gestiti Microsoft**: controlli per i servizi cloud Microsoft, che Microsoft implementa per conto dell'utente
- **I controlli**: a volte definiti controlli gestiti dal cliente, questi sono i controlli implementati e gestiti dall'organizzazione
- **Controlli condivisi**: questi sono i controlli che sia l'organizzazione che la responsabilità di Microsoft condividono per l'implementazione
- **Punteggio di valutazione**: consente di visualizzare i progressi compiuti per ottenere i possibili punti totali dalle azioni all'interno della valutazione gestita dall'organizzazione e da Microsoft

Quando si creano valutazioni, è necessario assegnarle a un gruppo. È possibile configurare i gruppi in qualunque modo la più logica per l'organizzazione. Ad esempio, è possibile raggruppare le valutazioni per anno di controllo, area geografica, soluzione, team all'interno dell'organizzazione o in altro modo. Dopo aver creato i gruppi, è possibile [filtrare il dashboard Compliance Manager](compliance-manager-setup.md#filtering-your-dashboard-view) per visualizzare il Punteggio di uno o più gruppi.

##### <a name="learn-more"></a>Ulteriori informazioni

[Creare e gestire valutazioni in Compliance Manager](compliance-manager-assessments.md).

### <a name="templates"></a>Modelli

Compliance Manager fornisce modelli che consentono di creare rapidamente valutazioni. È possibile modificare questi modelli per creare una valutazione ottimizzata per le proprie esigenze. È inoltre possibile creare una valutazione personalizzata creando un modello con i propri controlli e le proprie azioni. Ad esempio, potrebbe essere necessario un modello per coprire un controllo del processo aziendale interno o uno standard di protezione dei dati regionale non incluso in uno dei modelli di valutazione precompilati di 150 +.

##### <a name="learn-more"></a>Ulteriori informazioni

[Visualizzare l'elenco dei modelli di valutazione forniti da Compliance Manager](compliance-manager-templates-list.md).

[Ottenere istruzioni dettagliate per la creazione e la modifica dei modelli per le valutazioni](compliance-manager-templates.md).

### <a name="improvement-actions"></a>Azioni di miglioramento

Le azioni di miglioramento consentono di centralizzare le attività di conformità. Ogni azione di miglioramento fornisce indicazioni consigliate che consentono di allineare le normative e i criteri di protezione dei dati. Le azioni di miglioramento possono essere assegnate agli utenti dell'organizzazione per eseguire il lavoro di implementazione e testing. È inoltre possibile archiviare la documentazione, le note e gli aggiornamenti dello stato del record all'interno dell'azione di miglioramento.

##### <a name="learn-more"></a>Ulteriori informazioni

[Utilizzare azioni di miglioramento per gestire il flusso di lavoro di conformità](compliance-manager-improvement-actions.md).

[Informazioni sul modo in cui le azioni incidono sul punteggio di conformità](compliance-score-calculation.md#action-types-and-points).

## <a name="supported-languages"></a>Lingue supportate

Compliance Manager è disponibile nelle seguenti lingue:

- Inglese
- Bahasa indonesiano
- Bahasa Malay
- Cinese (semplificato)
- Cinese (tradizionale)
- Ceco
- Danese
- Olandese
- Finlandese
- Francese
- Tedesco
- Ebraico
- Ungherese
- Italiano
- Giapponese
- Coreano
- Norvegese
- Polacco
- Portoghese (Brasile)
- Russo
- Spagnolo
- Svedese
- Tailandese
- Turco

## <a name="next-steps-set-up-and-customize"></a>Passaggi successivi: configurare e personalizzare

Informazioni su come effettuare l'accesso, assegnare le autorizzazioni e i ruoli, configurare le impostazioni e personalizzare la visualizzazione Dashboard all'articolo [introduttivo di Compliance Manager](compliance-manager-setup.md).

Avviare quindi la personalizzazione di Compliance Manager per soddisfare gli standard del settore che interessano maggiormente la propria organizzazione tramite la [configurazione di valutazioni](compliance-manager-assessments.md).