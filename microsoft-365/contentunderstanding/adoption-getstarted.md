---
title: 'Microsoft SharePoint Syntex adoption: Introduzione'
description: Informazioni su come utilizzare e implementare SharePoint Syntex nell'organizzazione per risolvere i problemi aziendali.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: e88a7de1c81995b878dbf8a9308fbc774583289e
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597059"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Microsoft SharePoint Syntex adoption: Introduzione

Si pensi ai servizi di contenuto intelligenti disponibili in SharePoint Syntex come a tre parti:

- **Comprensione del contenuto:** creare modelli di intelligenza artificiale senza codice per classificare ed estrarre informazioni dal contenuto per applicare automaticamente i metadati per l'individuazione e il riutilizzo delle informazioni. Ulteriori informazioni sulla [comprensione del contenuto.](document-understanding-overview.md)
- **Elaborazione del contenuto:** Automatizzare l'acquisizione, l'inserimento e la categorizzazione del contenuto e semplificare i processi incentrati sul contenuto con Power Automate. Ulteriori informazioni [sull'elaborazione del contenuto.](form-processing-overview.md)
- **Conformità del contenuto:** Controllare e gestire il contenuto per migliorare la sicurezza e la governance con l'integrazione con Microsoft Information Protection.

Grazie ai nuovi servizi EA e alle nuove funzionalità, è possibile creare app di comprensione e classificazione dei contenuti direttamente nel flusso di gestione dei contenuti tramite SharePoint Syntex. Esistono due modi diversi per comprendere il contenuto. Il tipo di modello utilizzato si basa sul formato di file e sul caso d'uso:

| Elaborazione dei moduli | Informazioni sui documenti |
|:-------|:-------|
| Creato da una raccolta documenti. | Creato nel Centro contenuti, parte di SharePoint Syntex. |
| Modello creato in Generatore di intelligenza artificiale. | Modello creato nell'interfaccia nativa. |
| Utilizzato per i formati di file semistrutturati. | Utilizzato per i formati di file non strutturati. |
| Classificatore impostabile. | Classificatore trainabile con estrattori facoltativi. |
| Limitato a una singola raccolta. | Può essere applicato a più raccolte. |
| Formazione su formato PDF, JPG, PNG, totale 50 MB/500 pp. | Formazione su file PDF, Office o e-mail di 5-10, inclusi esempi negativi. |

Per un confronto più completo delle funzionalità, vedere Differenze tra la comprensione dei documenti e i modelli [di elaborazione dei moduli.](difference-between-document-understanding-and-form-processing-model.md)

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identificare gli scenari aziendali pilota da ottimizzare

Per prepararsi all'utilizzo di Syntex di SharePoint nell'organizzazione, è innanzitutto necessario comprendere gli scenari in cui sarà utile. Il "perché" consente di determinare quale modello sarà necessario e come strutturare l'organizzazione in base alla posizione in cui verrà applicato il modello. Ecco alcuni scenari in cui la comprensione dei documenti può aiutare l'organizzazione:

- **Elaborazione del contenuto:** Elaborare contratti, dichiarazioni di lavoro e altri documenti di tipo modulo. Utilizzare i moduli, formare il modello per comprendere ed eseguire il mapping dei campi, quindi eseguire i moduli per raccogliere automaticamente i dati. Per ulteriori informazioni, vedere [Panoramica dell'elaborazione dei moduli.](form-processing-overview.md)
- **Analisi delle fatture:** Estrarre i dettagli pertinenti dalle fatture e assicurarsi che siano conformi ai criteri o che vengano elaborati in modo appropriato.

Riflettere sui modi in cui Syntex di SharePoint può aiutare l'organizzazione:

- Automatizzare i processi aziendali
- Migliorare l'accuratezza della ricerca
- Gestire i rischi di conformità

Quando si pensa agli scenari aziendali da considerare, porsi le domande seguenti:

- Risolve un problema reale?
- Verrà ampiamente usato o avrà un impatto generale?
- È possibile ottenerlo?
- È possibile misurare il successo?

Definire la priorità degli scenari in base all'impatto e alla facilità di implementazione. Rendere l'area di interesse iniziale scenari di maggiore impatto che possono essere implementati facilmente. De-prioritize lower impact scenarios that are hard to implement.

Utilizzare gli scenari di esempio seguenti per richiedere idee su come utilizzare Syntex di SharePoint nell'organizzazione.

### <a name="scenario-track-data-from-invoices-with-form-processing"></a>Scenario: tenere traccia dei dati dalle fatture con l'elaborazione dei moduli

Ad esempio, è possibile configurare un processo utilizzando le funzionalità Syntex e Power Automate di SharePoint per tenere traccia e monitorare le fatture.

1. Configurare una raccolta per archiviare i documenti della fattura.
1. Formare il modello per riconoscere i campi nei documenti.
1. Estrarre i campi di cui si desidera tenere traccia in un elenco.
1. Configurare un flusso per inviare notifiche per eventi specifici, ad esempio:
    - Viene aggiunta una nuova fattura.
    - La data di scadenza di una fattura è scaduta.
    - Una fattura è per un importo superiore all'importo di approvazione automatica.

![Tenere traccia e monitorare le fatture con SharePoint Syntex e Power Automate](../media/content-understanding/process-invoices-flow.png)

Quando si automatizza questo scenario, è possibile:

- Risparmiare tempo e denaro estraendo automaticamente i dati dalle fatture invece di farlo manualmente.
- Ridurre potenziali errori e garantire una migliore conformità utilizzando i flussi di lavoro per controllare le fatture e segnalare eventuali problemi.

### <a name="scenario-track-information-from-contracts-with-document-understanding"></a>Scenario: tenere traccia delle informazioni dai contratti con la comprensione dei documenti

Come altro esempio, è possibile impostare un processo per identificare i contratti stipulati dall'azienda con altre società o singoli utenti. Configurare un modello per estrarre informazioni chiave da tali contratti, ad esempio il nome del cliente, le tariffe, le date o altre informazioni importanti, e aggiungere le informazioni alla raccolta come campi che è possibile visualizzare rapidamente. Applicare un'etichetta di conservazione alla raccolta documenti per garantire che i contratti non possano essere eliminati prima di un periodo di tempo specifico per una conformità appropriata alle normative aziendali.

1. Iniziare dal centro contenuti e creare un nuovo modello di comprensione dei documenti per i contratti.
1. Caricare documenti di esempio per esempi positivi e negativi, quindi eseguire la formazione per identificare i documenti contrattuali ed esaminare i risultati.
1. Formare l'estrattore per identificare i campi nei contratti, ad esempio il nome del cliente, la commissione e la data, quindi testare l'estrattore.
1. Al termine del modello, applica il modello a una raccolta in cui puoi caricare i contratti.
1. Applicare un'etichetta di conservazione al campo data, in modo che i contratti siano conservati nella raccolta per l'intervallo di tempo richiesto.

![Tenere traccia e monitorare i contratti con Le etichette di conservazione e Syntex di SharePoint](../media/content-understanding/process-contracts-flow.png)

Quando si automatizza questo scenario, è possibile:

- Risparmiare tempo e denaro estraendo automaticamente i dati dai contratti invece di farlo manualmente.
- Garantire una migliore conformità utilizzando le etichette di conservazione per garantire che i contratti siano conservati in modo appropriato.

### <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>Scenario: evitare rischi con la gestione dei record, la governance dei documenti e i processi di conformità basati su SharePoint Syntex

La riduzione dei rischi è un obiettivo comune per la maggior parte delle aziende. Potrebbe essere necessario:

- Un modo migliore per fornire/applicare la governance delle informazioni all'interno del tenant.
- Migliorare il sistema per la classificazione di documenti, messaggi di posta elettronica e altre forme di comunicazione considerate "record" per i progetti.
- Per controllare ricevute, contratti e così via, per garantire la conformità ai criteri aziendali.
- Per garantire che i progetti dispongono di tutta la documentazione necessaria per la conformità.

Configurare alcuni processi per la conformità con SharePoint Syntex per acquisire e classificare, controllare e contrassegnare in modo appropriato documenti e moduli che necessitano di una governance migliore. È possibile fare affidamento su Syntex di SharePoint per classificare automaticamente il contenuto anziché affidarsi agli utenti finali per contrassegnare manualmente o il team di conformità per applicare manualmente le regole di governance e l'archiviazione. È inoltre possibile abilitare un'esperienza di ricerca semplificata, gestire volumi di dati, applicare criteri di conservazione e gestione dei record, garantire la conformità e procedure consigliate per l'archiviazione e l'eliminazione.

Quando si automatizza questo scenario, è possibile sentirsi sicuri che:

- La conformità viene confermata e i rischi vengono ridotti.
- La gestione della tassonomia e dei record viene applicata in modo coerente e accurato.
- I volumi di contenuto sono controllati.
- I dipendenti possono trovare facilmente le informazioni giuste nel contesto giusto.

### <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Scenario: acquisire informazioni da documenti inaccessibili in precedenza

La maggior parte delle organizzazioni dispone di archivi di documenti legali, criteri, contratti, documenti hr e linee guida per la governance. Estrarre questi archivi dati per estrarre informazioni preziose, ad esempio: progetti, settori, temi, persone, aree geografiche e così via.

Ad esempio, un responsabile delle risorse umane deve accedere rapidamente a tutti i documenti delle risorse umane, inclusi curriculum, criteri per le risorse umane e altri moduli. Inoltre, desiderano identificare rapidamente le informazioni necessarie dai curriculum e da altri documenti relativi alle risorse umane senza passare manualmente al setaggiamento dei documenti. Cercano una soluzione che consenta loro di trovare rapidamente le informazioni necessarie senza dover esaminare manualmente migliaia di curriculum, criteri per le risorse umane e altra documentazione che potrebbe essere diffusa in diversi siti.

Quando si automatizza questo scenario, è possibile:

- Sbloccare le informazioni dai contenuti digitali.
- Classificare i criteri delle risorse umane, i curriculum, i documenti di vendita, i progetti tecnici, i piani account ed estrarre informazioni.
- Trovare rapidamente le informazioni o i documenti corretti che si stanno cercando.
- Ottenere l'accesso immediato alle informazioni più recenti.
- Ridurre i tempi di ricerca.

### <a name="scenario-improve-data-processing-to-provide-insights--analytics"></a>Scenario: migliorare l'elaborazione dei dati per fornire & analitica

Ad esempio, una società di produzione di prodotti a base di prodotto può utilizzare SharePoint Syntex per estrarre informazioni dai documenti DELLA FDA per rispondere alle domande dei loro responsabili. Avere le risposte più facilmente accessibili può ridurre il tempo necessario per produrre queste risposte e aumentare la disponibilità dei dati per generare risposte più accurate alle domande della dirigenza.

Ad esempio, un project manager deve fornire rapidamente risposte alle domande relative al prodotto del team di leadership. Devono trovare informazioni e metriche relative alle query in un dashboard consolidato. Stanno cercando una soluzione che estrae le informazioni necessarie dalle etichette di prodotto, dai pamphlet di prodotto e da altri materiali e genera un report consolidato che possono usare per segnalare di nuovo al team di leadership.

Quando si automatizza questo scenario, è possibile:

- Ridurre il tempo necessario per produrre risposte.
- Aumentare la disponibilità dei dati.
- Fornire risposte più accurate.

### <a name="scenario-automate-order-processing"></a>Scenario: automatizzare l'elaborazione degli ordini

Con SharePoint Syntex, è possibile ridurre il tempo di elaborazione manuale degli ordini dei clienti. Ad esempio, è possibile caricare ordini da fax, posta elettronica o carta in SharePoint utilizzando l'elaborazione OCR e quindi estrarre i metadati da tali ordini in modo da poterli soddisfare utilizzando processi automatizzati.

Ad esempio, un responsabile della catena di approvvigionamento desidera ridurre gli errori causati dall'immissione manuale dei dati. Desiderano evitare la revisione manuale e l'immissione dei dati degli ordini dei clienti in ingresso (carta, fax o posta elettronica) per ridurre gli errori che si verificano nei sistemi aziendali. Vogliono una soluzione che applica le tecniche di intelligenza artificiale e machine learning per convalidare le informazioni sugli ordini in arrivo, estrarre i dati di base e inviare automaticamente i dati nel sistema ERP, per l'evasione e la riconciliazione degli ordini.

Quando si automatizza questo scenario, è possibile verificare che:

- L'accuratezza dell'ordine e della spedizione aumenta.
- Le tariffe o le sanzioni associate agli errori di ordine o spedizione vengono ridotte.
- I ritardi nella fatturazione o nei pagamenti diminuiscono.
- I costi del personale sono ridotti.

### <a name="scenario-simplify-visa-renewal-process"></a>Scenario: semplificare il processo di rinnovo del visto

Syntex di SharePoint consente di automatizzare promemoria e rinnovi per informazioni chiave sui contratti. Ad esempio, un amministratore delle risorse umane deve assicurarsi che i visti dei dipendenti siano aggiornati e/o rinnovati in tempo. Vogliono offrire alle persone un processo semplice e intuitivo per aggiornare i loro visti. Hanno bisogno di una soluzione che estraa le date di rinnovo dai contratti e invii automaticamente promemoria ai dipendenti quando si avvicinano le date di rinnovo.

Quando si automatizza questo scenario, è possibile verificare che:

- I livelli di non conformità vengono ridotti.
- Il numero di promemoria manuali viene ridotto.
- Il numero di sanzioni per la mancata conformità è ridotto.

## <a name="identify-roles--responsibilities"></a>Identificare i ruoli & responsabilità

Determinare chi nell'organizzazione dovrà creare e gestire i modelli? Potrebbero essere coinvolti i ruoli seguenti:

| SharePoint/Knowledge Admin | Amministratore della piattaforma Power | Knowledge Manager | Proprietario del modello |
|:-------|:-------|:-------|:-------|
| Ruolo AAD| Ruolo AAD | Ruolo AAD | Promotori |
| Configurare l'elaborazione moduli | Configurare l'ambiente del servizio dati comune per l'elaborazione dei moduli | Raccogliere casi d'uso | Raccogliere casi d'uso aziendali |
| Gestire i centri contenuti e le autorizzazioni| Acquistare e allocare crediti AIB | Stabilire le procedure consigliate e rivedere l'analisi del modello | Creare e applicare modelli |

Il responsabile della conoscenza, il proprietario del processo aziendale e il proprietario del modello di contenuto creano modelli di esempio e l'adozione dei campioni nell'organizzazione.
Altri che potrebbero essere coinvolti: amministratore della conformità, responsabili della tassonomia.

Dove verranno compilati e applicati i modelli? Esistono processi o archivi esistenti che potrebbero essere migliorati?

- Elaborazione dei moduli: decidere quali siti riceveranno l'azione di elaborazione dei moduli.
- Informazioni sui documenti: è possibile creare più centri contenuti per aree aziendali diverse.

## <a name="strategic-positioning"></a>Posizionamento strategico

Collaborare con gli stakeholder per assicurarsi che siano allineati alla strategia per l'utilizzo di Syntex di SharePoint. Ricercare e fornire le risorse seguenti per facilitare questo posizionamento:

- Risultati aziendali:
  - Potenziali risultati fiscali
  - Potenziali risultati di agilità
  - Modello dei risultati aziendali
- Stakeholders/Exec sponsor buy-in/alignment
  - Business case decks
  - Modelli finanziari
  - Conformità aziendale - cultura

## <a name="identify-stakeholders"></a>Identificare le parti interessate

Identificare le parti interessate per il progetto.

|Ruolo |Responsabilità |Reparto |
|:-------|:-------|:--------|
| Sponsor esecutivo   | Comunicare all'azienda la visione e i valori di alto livello   |  Leadership esecutiva   |
| Project lead(s) | Supervisionare l'intero processo di esecuzione e implementazione dell'avvio | Gestione dei progetti |
| Amministratori della knowledge base| Creare e gestire i centri contenuti | IT o altro reparto|
| Responsabili del contenuto e proprietari dei modelli| Raccogliere casi d'uso e creare e applicare modelli | Qualsiasi reparto|
| Promotori | Aiutare a migliorare e gestire la gestione delle richieste di assistenza | Qualsiasi reparto (personale) |
| Amministratore tenant | Configurare le impostazioni a livello di tenant | Reparto IT|
| Amministratore power platform| Configurare l'ambiente dei servizi dati comuni | Reparto IT|

> [!Note]
> Anche se è consigliabile che ognuno di questi ruoli venga evaso durante l'implementazione, è possibile che non sia necessario che tutti questi ruoli inizino a usare la soluzione identificata.

## <a name="readiness-checklist"></a>Elenco di controllo per la preparazione

Per prepararsi per l'implementazione di Syntex di SharePoint, è necessario:

![Preparazione per la comprensione del contenuto](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Pianificare lo stato finale
    - I modelli di comprensione dei documenti sono il mezzo, non la fine.
    - Pianificare l'utilizzo del valore dei metadati estratti con:
      - Cerca
      - Applicazione di filtri e formattazione della visualizzazione
      - Conformità
      - Automazione
2. Identificazione
    - Comprendere l'architettura delle informazioni e l'utilizzo delle funzionalità di gestione del contenuto esistenti.
    - I tipi di contenuto esistenti sono candidati validi per i modelli?
    - Quali processi esistenti verrebbero migliorati dai metadati?
3. Struttura
    - Progettare l'approccio all'architettura delle informazioni, ai metadati gestiti e ai tipi di contenuto
    - Progettare il processo per la definizione, la creazione, la gestione.

## <a name="engage-your-organization"></a>Coinvolgere l'organizzazione

1. Identificare i titolari della posta in gioco, confermare gli scenari e sviluppare un piano di progetto.
1. Configurare le impostazioni e applicare le licenze.
1. Iniziare la consapevolezza e la formazione: selezionare i campioni.
1. Implementazione in fasi.  
1. Raccogliere feedback e iterazione.
1. Man mano che l'utilizzo aumenta, pianifica i crediti di qualsiasi generatore di intelligenza artificiale in base alle esigenze.
