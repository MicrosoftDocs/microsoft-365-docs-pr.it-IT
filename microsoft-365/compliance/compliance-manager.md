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
description: Microsoft Compliance Manager consente alle organizzazioni di semplificare e automatizzare le valutazioni dei rischi e suggerisce le azioni consigliate per risolvere i rischi.
ms.openlocfilehash: 7bff6a2a7a150a08b98fe7a92cd71d266df9fda7
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376547"
---
# <a name="microsoft-compliance-manager"></a>Microsoft Compliance Manager

**In questo articolo:** Informazioni su Compliance Manager, su come consente di semplificare la conformità e ridurre i rischi e i relativi componenti chiave.

## <a name="whats-new-the-ga-release-of-compliance-manager"></a>Novità: la versione GA di Compliance Manager

Compliance Manager è ora disponibile a livello generale come soluzione di gestione della conformità end-to-end all'interno del Centro conformità [Microsoft 365.](microsoft-365-compliance-center.md) Con questa versione, Compliance Manager completa la transizione dalla posizione precedente in Microsoft Service Trust Portal. Compliance Manager è ora disponibile anche per i clienti di US Government Community (GCC) Moderate e GCC High.

Ciò che è iniziato con l'anteprima pubblica del punteggio di conformità si è evoluto in uno strumento centralizzato con funzionalità di gestione della conformità avanzate e maggiore facilità d'uso.  La versione GA offre una raccolta più ampia di valutazioni predefinite per aiutarti a ridimensionare le attività di conformità.

**Ulteriori informazioni sulla versione GA:**
- Le [domande frequenti illustrano](compliance-manager-faq.md) in modo più dettagliato l'evoluzione.
- Per informazioni sui miglioramenti apportati alle funzionalità ga, [vedere questo post di blog.](https://aka.ms/compliancemanager/GAblog)

Guardare il video seguente per informazioni su come Compliance Manager può semplificare il modo in cui l'organizzazione gestisce la conformità:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a>Che cos'è Compliance Manager

[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) è una funzionalità del Centro conformità [Microsoft 365](microsoft-365-compliance-center.md) che consente di gestire i requisiti di conformità dell'organizzazione con maggiore facilità e comodità. Compliance Manager può essere utile per tutto il percorso di conformità, dall'inventario dei rischi per la protezione dei dati alla gestione delle complessità dell'implementazione dei controlli, al rispetto di normative e certificazioni e alla creazione di report ai revisori.

Compliance Manager consente di semplificare la conformità e ridurre i rischi fornendo:

- Valutazioni predefinite per standard e normative comuni del settore e regionali o valutazioni personalizzate per soddisfare le specifiche esigenze di conformità (le valutazioni disponibili dipendono dal contratto di licenza; [per ulteriori informazioni,](https://go.microsoft.com/fwlink/?linkid=2132371)vedere .

- Funzionalità del flusso di lavoro che consentono di completare in modo efficiente le valutazioni dei rischi tramite un singolo strumento.

- Istruzioni dettagliate sulle azioni di miglioramento suggerite per garantire la conformità agli standard e alle normative più rilevanti per l'organizzazione. Per le azioni gestite da Microsoft, vedrai i dettagli dell'implementazione e i risultati del controllo.

- Un punteggio di conformità basato sul rischio che consente di comprendere la propria posizione di conformità misurando i progressi nel completamento delle azioni di miglioramento.

Il dashboard di Compliance Manager mostra il punteggio di conformità corrente, consente di vedere cosa richiede attenzione e guida l'utente verso le azioni di miglioramento chiave. Di seguito è riportato un esempio dell'aspetto del dashboard di Compliance Manager:

![Compliance Manager - dashboard](../media/compliance-manager-dashboard.png "Dashboard di Compliance Manager")

## <a name="understanding-your-compliance-score"></a>Informazioni sul punteggio di conformità

Compliance Manager premia l'utente per il completamento delle azioni di miglioramento intraprese per conformarsi a una normativa, uno standard o un criterio e combina tali punti in un punteggio di conformità complessivo. Ogni azione ha un impatto diverso sul punteggio a seconda dei potenziali rischi coinvolti. Il punteggio di conformità può contribuire a definire le priorità su quale azione concentrarsi per migliorare la propria posizione di conformità complessiva.

Compliance Manager fornisce un punteggio iniziale basato sulla linea di base di protezione dei dati di Microsoft 365. Questa linea di base è un insieme di controlli che include normative e standard chiave per la protezione dei dati e la governance generale dei dati.

##### <a name="learn-more"></a>Ulteriori informazioni

[Comprendere come viene calcolato il punteggio di conformità.](compliance-score-calculation.md)

[Informazioni su come utilizzare le azioni di miglioramento.](compliance-manager-improvement-actions.md)

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>Elementi chiave: controlli, valutazioni, modelli, azioni di miglioramento

Compliance Manager usa diversi elementi di dati per gestire le attività di conformità. Quando si utilizza Compliance Manager per assegnare, testare e monitorare le attività di conformità, è utile avere una conoscenza di base degli elementi chiave: controlli, valutazioni, modelli e azioni di miglioramento.

### <a name="controls"></a>Controlli

Un controllo è un requisito di una normativa, di uno standard o di un criterio. Definisce il modo in cui valutare e gestire la configurazione del sistema, il processo organizzativo e le persone responsabili di soddisfare un requisito specifico di una normativa, uno standard o un criterio.

Compliance Manager tiene traccia dei seguenti tipi di controlli:

1. **Controlli gestiti da Microsoft:** controlli per i servizi cloud Microsoft, che Microsoft è responsabile dell'implementazione
2. **Controlli:** a volte definiti controlli gestiti dal cliente, si tratta di controlli implementati e gestiti dall'organizzazione
3. **Controlli condivisi:** si tratta di controlli che l'organizzazione e Microsoft condividono per l'implementazione

##### <a name="learn-more"></a>Ulteriori informazioni

[Monitorare lo stato dei controlli.](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)

[Informazioni su come Compliance Manager valuta continuamente i controlli.](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)

### <a name="assessments"></a>Valutazioni

Una valutazione è un raggruppamento di controlli da una normativa, uno standard o un criterio specifico. Il completamento delle azioni all'interno di una valutazione consente di soddisfare i requisiti di uno standard, di una normativa o di una legge. Ad esempio, si potrebbe avere una valutazione che, quando si completano tutte le azioni al suo interno, consente di allineare le impostazioni di Microsoft 365 ai requisiti ISO 27001.

Le valutazioni hanno diversi componenti:

- **Servizi nell'ambito:** l'insieme specifico di servizi Microsoft applicabili alla valutazione
- **Controlli gestiti da Microsoft:** controlli per i servizi cloud Microsoft, che Microsoft implementa per conto dell'utente
- **Controlli:** a volte definiti controlli gestiti dal cliente, si tratta di controlli implementati e gestiti dall'organizzazione
- **Controlli condivisi:** si tratta di controlli che l'organizzazione e Microsoft condividono per l'implementazione
- **Punteggio di valutazione:** mostra i progressi nel raggiungimento dei punti totali possibili dalle azioni all'interno della valutazione gestite dall'organizzazione e da Microsoft

Quando si creano valutazioni, le si assegna a un gruppo. È possibile configurare i gruppi nel modo più logico per l'organizzazione. Ad esempio, è possibile raggruppare le valutazioni in base all'anno di controllo, all'area geografica, alla soluzione, ai team all'interno dell'organizzazione o in altro modo. Dopo aver creato i gruppi, è possibile [filtrare il dashboard di Compliance Manager](compliance-manager-setup.md#filtering-your-dashboard-view) per visualizzare il punteggio in base a uno o più gruppi.

##### <a name="learn-more"></a>Ulteriori informazioni

[Creare e gestire le valutazioni in Compliance Manager.](compliance-manager-assessments.md)

### <a name="templates"></a>Modelli

Compliance Manager fornisce modelli che consentono di creare rapidamente valutazioni. È possibile modificare questi modelli per creare una valutazione ottimizzata per le proprie esigenze. Puoi anche creare una valutazione personalizzata creando un modello con controlli e azioni personalizzati. Ad esempio, è possibile che un modello riguardi un controllo interno del processo aziendale o uno standard di protezione dei dati regionale non coperto da uno dei nostri oltre 150 modelli di valutazione predefiniti.

##### <a name="learn-more"></a>Ulteriori informazioni

[Visualizzare l'elenco dei modelli di valutazione forniti da Compliance Manager.](compliance-manager-templates-list.md)

[Istruzioni dettagliate per la creazione e la modifica di modelli per le valutazioni.](compliance-manager-templates.md)

### <a name="improvement-actions"></a>Azioni di miglioramento

Le azioni di miglioramento consentono di centralizzare le attività di conformità. Ogni azione di miglioramento fornisce indicazioni consigliate che consentono di allinearsi alle normative e agli standard di protezione dei dati. Le azioni di miglioramento possono essere assegnate agli utenti dell'organizzazione per eseguire attività di implementazione e test. È inoltre possibile archiviare documentazione, note e registrare gli aggiornamenti dello stato all'interno dell'azione di miglioramento.

##### <a name="learn-more"></a>Ulteriori informazioni

[Utilizzare le azioni di miglioramento per gestire il flusso di lavoro di conformità.](compliance-manager-improvement-actions.md)

[Informazioni su come le azioni influiscono sul punteggio di conformità.](compliance-score-calculation.md#action-types-and-points)

## <a name="supported-languages"></a>Lingue supportate

Compliance Manager è disponibile nelle lingue seguenti:

- Inglese
- Bahasa Indonesiano
- Bahasa Malese
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

## <a name="next-steps-set-up-and-customize"></a>Passaggi successivi: configurazione e personalizzazione

Informazioni su come accedere, assegnare autorizzazioni e ruoli, configurare le impostazioni e personalizzare la visualizzazione del dashboard in [Introduzione a Compliance Manager.](compliance-manager-setup.md)

Iniziare quindi a personalizzare Compliance Manager per garantire la conformità agli standard di settore più importanti per l'organizzazione [configurando le valutazioni.](compliance-manager-assessments.md)