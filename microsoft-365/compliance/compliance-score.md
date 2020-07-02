---
title: Punteggio di conformità Microsoft (anteprima)
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Score (Preview) consente alle organizzazioni di semplificare e automatizzare le valutazioni dei rischi e suggerisce azioni consigliate per aiutare a gestire i rischi.
ms.openlocfilehash: 0cb8bd0b5aa39be2a9a6e706afa21bb7dc53eadb
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016139"
---
# <a name="microsoft-compliance-score-preview"></a>Punteggio di conformità Microsoft (anteprima)

**In questo articolo:** Informazioni sul punteggio di conformità, sul modo in cui è possibile semplificare la gestione della conformità e su come configurarlo per l'organizzazione.

**Novità:** La versione di giugno 2020 include nuove funzionalità per la creazione e la gestione di valutazioni e per visualizzare i controlli all'interno del Punteggio di conformità. Visitare le [Note sulla versione del Punteggio di conformità](compliance-score-release-notes.md) per vedere cosa c'è di nuovo nell'anteprima pubblica del Punteggio di conformità.

## <a name="what-is-compliance-score"></a>Che cos'è il Punteggio di conformità

[Microsoft Compliance Score](https://compliance.microsoft.com/compliancescore) è una funzionalità di anteprima del [centro conformità di Microsoft 365](microsoft-365-compliance-center.md) che consente di comprendere la posizione di conformità dell'organizzazione. Calcola un punteggio basato sui rischi misurando lo stato di avanzamento del processo di completamento delle azioni che consentono di ridurre i rischi per la protezione dei dati e gli standard normativi.

È possibile utilizzare il Punteggio di conformità come strumento per monitorare tutte le valutazioni dei rischi. Offre funzionalità di flusso di lavoro che consentono di completare efficacemente le valutazioni dei rischi tramite uno strumento comune.

Gli utenti di [Compliance Manager](compliance-manager-overview.md) noterà che il Punteggio di conformità è ora una funzionalità autonoma con una progettazione più semplice e più facile da usare per consentire alle organizzazioni di gestire più facilmente la conformità.

La pagina principale del Punteggio di conformità è il dashboard personalizzato. Mostra il tuo punteggio corrente, ti aiuta a vedere cosa ha bisogno di attenzioni e ti guida alle azioni per migliorare il tuo punteggio. Il dashboard del Punteggio di conformità avrà l'aspetto seguente:

![Punteggio di conformità-dashboard](../media/compliance-score-dashboard.png "Dashboard del Punteggio di conformità")

### <a name="simplified-compliance-management"></a>Gestione della conformità semplificata

Il Punteggio di conformità consente di semplificare la gestione della conformità fornendo:

- **Valutazioni continue**: consente di analizzare automaticamente gli ambienti Microsoft 365 per rilevare e monitorare l'efficacia dei controlli di protezione dei dati nel sistema
- **Azioni consigliate**: fornisce consigli e istruzioni dettagliate su come implementare i controlli per massimizzare il Punteggio
-  **Mapping di controllo incorporato**: consente di rimanere aggiornati con il paesaggio di conformità in evoluzione fornendo un Framework di controllo comune incorporato.

> [!IMPORTANT]
> I consigli di Compliance Manager e Punteggio di conformità non devono essere interpretati come una garanzia di conformità. Spetta a te valutare e convalidare l'efficacia dei controlli del cliente per il tuo ambiente normativo. Questi servizi sono attualmente in anteprima e sono soggetti ai termini e alle condizioni nelle condizioni dei [servizi online](https://go.microsoft.com/fwlink/?linkid=2108910). Vedere anche [linee guida per la gestione delle licenze di Microsoft 365 per sicurezza e conformità](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="relationship-to-compliance-manager"></a>Relazione con Compliance Manager

Considerare la conformità score come un'esperienza semplificata di Compliance Manager. Mentre i due esistono come strumenti distinti ma integrati, il Punteggio di conformità rende più facile monitorare la postura di conformità globale e adottare misure per migliorarla.

Il Punteggio di conformità condivide lo stesso backend con Compliance Manager. Tutto ciò che si esegue in uno strumento verrà riposto nell'altro strumento.

Alcune funzionalità per la valutazione e la gestione dei modelli restano in Compliance Manager durante l'anteprima pubblica. Si consiglia di iniziare tutte le attività di gestione della conformità in Score Compliance. Quando si arriva a funzioni gestite da Compliance Manager, vi guideremo là.

#### <a name="learn-more"></a>Altre informazioni

[Comprendere la relazione tra Score compliance e Compliance Manager](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).

## <a name="understanding-your-score"></a>Informazioni sul Punteggio

Premi Punteggio di conformità punti per il completamento delle azioni intraprese per conformarsi a un regolamento, uno standard o un criterio. Ogni azione ha un impatto diverso sulla partitura a seconda dei possibili rischi coinvolti. Il Punteggio può contribuire a definire la priorità su quale azione concentrarsi per migliorare la posizione di conformità generale.

Punteggio di conformità fornisce un punteggio iniziale basato sulla linea di base per la protezione dei dati di Microsoft 365.  Questa linea di base è un insieme di controlli che include le normative fondamentali e gli standard per la protezione dei dati e la governance dei dati generale. Questa linea di base estrae gli elementi principalmente dal NIST CSF (Istituto nazionale per gli standard e la tecnologia Cybersecurity Framework) e ISO (International Organization for Standardizzation), oltre che da FedRAMP (Federal Risk and Authorization Management Program) e GDPR (General Data Protection Regulation dell'Unione europea).

La valutazione della linea di base per la protezione dei dati viene utilizzata per calcolare il punteggio iniziale prima di configurare eventuali altre valutazioni. Dopo la prima visita, il Punteggio di conformità è già in grado di raccogliere segnali dalle soluzioni Microsoft 365. Verrà visualizzato a colpo d'occhio il modo in cui l'organizzazione è in esecuzione rispetto agli standard e alle normative sulla protezione dei dati e le azioni consigliate da intraprendere.

Poiché ogni organizzazione ha esigenze specifiche, il Punteggio di conformità si basa su di esso per configurare e gestire le proprie valutazioni per attenuare meglio i rischi. Ad esempio, se l'organizzazione appartiene al settore dei servizi finanziari, potrebbe essere necessario aggiungere la valutazione di FFIEC. Se l'organizzazione appartiene all'industria del settore sanitario, è possibile aggiungere la valutazione HIPAA/HITECH.

#### <a name="learn-more"></a>Altre informazioni

[Comprendere in che modo il Punteggio di conformità viene calcolato e monitorato continuamente](compliance-score-methodology.md).

[Creare e gestire valutazioni nel punteggio di conformità](compliance-score-assessments.md).

## <a name="key-components-controls-assessments-templates-improvement-actions"></a>Componenti principali: controlli, valutazioni, modelli, azioni di miglioramento

Il Punteggio di conformità utilizza diversi componenti per facilitare la gestione delle attività di conformità. Quando si utilizza il Punteggio di conformità per assegnare, testare e monitorare le attività di conformità, è utile avere una conoscenza di base dei componenti principali: controlli, valutazioni, modelli e azioni di miglioramento.

### <a name="controls"></a>Controlli

Un controllo è un requisito di una norma, di uno standard o di un criterio. Definisce come valutare e gestire la configurazione del sistema, il processo organizzativo e gli utenti responsabili della riunione di un requisito specifico di una norma, di uno standard o di un criterio.

Il Punteggio di conformità tiene traccia di due tipi di controlli:

1. **Controlli gestiti Microsoft**: controlli per i servizi cloud Microsoft, che Microsoft è responsabile dell'implementazione
2. **I controlli**: a volte indicati come controlli del cliente, questi sono i controlli implementati e gestiti dall'organizzazione

#### <a name="learn-more"></a>Altre informazioni

[Monitorare lo stato dei controlli](compliance-score-assessments.md#monitor-assessment-progress-and-controls).

### <a name="assessments"></a>Valutazioni

Una valutazione è il raggruppamento di controlli da una regolamentazione, standard o criteri specifici. Il completamento delle azioni all'interno di una valutazione consente di soddisfare i requisiti di una norma, di una normativa o di una legge. Ad esempio, si può avere una valutazione che, quando si completano tutte le azioni al suo interno, apporta le impostazioni di Microsoft 365 in linea con i requisiti ISO 27001.

Le valutazioni hanno diversi componenti:

- **Servizi nell'ambito**: l'insieme specifico di servizi Microsoft applicabile alla valutazione
- **Controlli gestiti Microsoft**: controlli implementati da Microsoft e test
- **Controlli seguenti: controlli**gestiti
- **Punteggio di valutazione**: la percentuale dei punti ottenuti completando le azioni di miglioramento all'interno di tale valutazione

Quando si creano valutazioni, è necessario assegnarle a un **gruppo**. È possibile configurare i gruppi in qualunque modo la più logica per l'organizzazione. Ad esempio, è possibile raggruppare le valutazioni per anno, standard di conformità, servizio, team all'interno dell'organizzazione o in altro modo. Dopo aver creato i gruppi, è possibile [filtrare il dashboard del Punteggio di conformità](compliance-score-setup.md#filtering-your-dashboard-view) per visualizzare il Punteggio di uno o più gruppi.

#### <a name="learn-more"></a>Altre informazioni

[Creare e gestire valutazioni nel punteggio di conformità](compliance-score-assessments.md).

### <a name="templates"></a>Modelli

Punteggio di conformità fornisce modelli che sono pronti per creare rapidamente valutazioni. È possibile modificare questi modelli per creare una valutazione ottimizzata per le proprie esigenze. È inoltre possibile creare una valutazione personalizzata sviluppando il proprio modello con i propri controlli e le proprie azioni. Ad esempio, potrebbe essere necessario un modello per coprire un controllo del processo aziendale interno o uno standard di protezione dei dati regionale non incluso in uno dei modelli.

La creazione di modelli personalizzati consente di monitorare non solo le valutazioni cloud di Microsoft, ma anche eventuali altre valutazioni dei rischi nell'ambito della propria organizzazione.

#### <a name="learn-more"></a>Altre informazioni

[Visualizzare i modelli disponibili nel punteggio di conformità per le valutazioni dell'edificio](compliance-score-templates.md).

[Ottenere istruzioni dettagliate per la creazione e la modifica dei modelli Compliance Manager](working-with-compliance-manager.md#templates).

### <a name="improvement-actions"></a>Azioni di miglioramento

Le azioni di miglioramento centralizzano le attività di conformità. Ogni azione di miglioramento fornisce indicazioni dettagliate sull'implementazione che consentono di allineare le normative e i criteri di protezione dei dati. Le azioni possono essere assegnate agli utenti dell'organizzazione per eseguire il lavoro di implementazione e testing. È inoltre possibile archiviare la documentazione, le note e gli aggiornamenti dello stato del record all'interno dell'azione di miglioramento.

#### <a name="learn-more"></a>Altre informazioni

[Utilizzare azioni di miglioramento per gestire il flusso di lavoro di conformità](compliance-score-improvement-actions.md).

## <a name="next-steps-set-up-and-customize"></a>Passaggi successivi: configurare e personalizzare

Informazioni su come effettuare l'accesso, impostare le autorizzazioni e i ruoli, configurare gli aggiornamenti dei punti di sicurezza e personalizzare la visualizzazione Dashboard all' [installazione del Punteggio di conformità](compliance-score-setup.md).

Avviare quindi la personalizzazione del Punteggio di conformità per l'organizzazione mediante la [configurazione di valutazioni](compliance-score-assessments.md).