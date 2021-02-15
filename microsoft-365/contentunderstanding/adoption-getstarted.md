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
ms.openlocfilehash: 7a0bd04121d7400cced22e43a539bd21c45a7fc3
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976574"
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

Nella tabella seguente vengono illustrate la disponibilità e le licenze per SharePoint Syntex:

| Elaborazione dei moduli | Informazioni sui documenti |
|:-------|:-------|
| L'elaborazione dei moduli si basa su Power Platform. <br>Per informazioni sulla disponibilità globale per Power Platform e Generatore di intelligenza artificiale, vedi [Disponibilità della piattaforma Power.](https://dynamics.microsoft.com/geographic-availability/) | Disponibile in tutte le aree geografiche. |
| Utilizza i crediti di Generatore di intelligenza artificiale.<br>I crediti possono essere acquistati in batch di 1M.<br>1M credits are included when 300+ SharePoint Syntex licenses are purchased.<br>1M credits will allow processing of 2000 file pages. | I modelli funzionano su tutte le lingue con alfabeto latino. Oltre all'inglese: tedesco, svedese, francese, spagnolo, italiano e portoghese. |
| Provisioning eseguito nell'ambiente del servizio dati comune predefinito. | Non ha restrizioni di capacità. |

Per altre informazioni sui crediti e sulle unità di credito per i generatori di intelligenza artificiale, vedi Gestione delle licenze di Generatore di intelligenza [artificiale.](https://docs.microsoft.com/ai-builder/administer-licensing)

SharePoint Syntex si integra con le funzionalità di conformità di Microsoft 365 come:

- Etichette di conservazione che definiscono i criteri di record in base all'età del documento o agli eventi esterni.
- Etichette di riservatezza che impostano criteri di prevenzione della perdita dei dati, crittografia, condivisione e accesso condizionale.

Gli utenti possono applicare etichette oppure possono essere applicate automaticamente dai modelli di intelligenza artificiale Syntex di SharePoint. I piani di analisi e file offrono una gestione in scala dell'utilizzo e dei criteri delle etichette.

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identificare gli scenari aziendali pilota da ottimizzare

Per prepararsi all'utilizzo di Syntex di SharePoint nell'organizzazione, è innanzitutto necessario comprendere gli scenari in cui sarà utile. Il motivo per cui è possibile determinare quale modello sarà necessario e come strutturare l'organizzazione in base alla posizione in cui verrà applicato il modello. Ecco alcuni scenari in cui la comprensione dei documenti può aiutare l'organizzazione:

- Content processing: Process contracts, statements of work, and other form-like documents. Utilizzare i moduli, formare il modello per comprendere ed eseguire il mapping dei campi e quindi eseguire i moduli per raccogliere automaticamente i dati. Per ulteriori informazioni, vedere [Panoramica dell'elaborazione dei moduli.](form-processing-overview.md)
- Analisi delle fatture: estrarre i dettagli pertinenti dalle fatture e assicurarsi che siano conformi ai criteri o siano elaborati in modo appropriato.

Riflettere sui modi in cui Syntex di SharePoint può aiutare l'organizzazione:

- Automatizzare i processi aziendali
- Migliorare l'accuratezza della ricerca
- Gestire i rischi di conformità

### <a name="form-processing-scenario-example"></a>Esempio di scenario di elaborazione dei moduli

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
- Ridurre potenziali errori e garantire una migliore conformità utilizzando i flussi di lavoro per agire sulle fatture e segnalare eventuali problemi.

### <a name="document-understanding-scenario-example"></a>Esempio di scenario di informazioni sui documenti

Come altro esempio, è possibile impostare un processo per identificare i contratti che l'azienda ha con altre società o singoli utenti. Puoi configurare un modello per estrarre informazioni chiave da tali contratti, ad esempio nome del cliente, tariffe, date o altre informazioni importanti, e aggiungerle alla raccolta come campi che puoi visualizzare rapidamente. È inoltre possibile applicare un'etichetta di conservazione alla raccolta documenti per garantire che i contratti non possano essere eliminati prima di un periodo di tempo specifico per una conformità appropriata alle normative aziendali.

1. Iniziare dal centro contenuti e creare un nuovo modello di comprensione dei documenti per i contratti.
1. Caricare documenti di esempio per esempi positivi e negativi, quindi eseguire la formazione per identificare i documenti contrattuali ed esaminare i risultati.
1. Formare l'estrattore per identificare i campi nei contratti, ad esempio il nome del cliente, la commissione e la data, quindi testare l'estrattore.
1. Al termine del modello, applica il modello a una raccolta in cui puoi caricare i contratti.
1. Applicare un'etichetta di conservazione al campo data, in modo che i contratti siano conservati nella raccolta per l'intervallo di tempo richiesto dall'organizzazione per i contratti.

![Tenere traccia e monitorare i contratti con Syntex di SharePoint e le etichette di conservazione](../media/content-understanding/process-contracts-flow.png)

Quando si automatizza questo scenario, è possibile:

- Risparmiare tempo e denaro estraendo automaticamente i dati dai contratti invece di farlo manualmente.
- Garantire una migliore conformità utilizzando le etichette di conservazione per garantire che i contratti siano conservati in modo appropriato.

### <a name="tips-for-identifying-scenarios"></a>Suggerimenti per l'identificazione degli scenari

Quando si pensa agli scenari aziendali da considerare, porsi le domande seguenti:

- Risolve un problema reale?
- Sarà ampiamente usato o avrà un impatto su vasta gamma?
- È possibile ottenerlo?
- È possibile misurare il successo?

Definire la priorità degli scenari in base all'impatto e alla facilità di implementazione. Rendere l'area di interesse iniziale scenari di maggiore impatto che possono essere implementati facilmente. De-prioritize lower impact scenarios that are hard to implement.

## <a name="identify-roles--responsibilities"></a>Identificare i ruoli & responsabilità

Determinare chi nell'organizzazione dovrà creare e gestire i modelli? Potrebbero essere coinvolti i ruoli seguenti:

| SharePoint/Knowledge Admin | Amministratore della piattaforma Power | Knowledge Manager | Proprietario del modello |
|:-------|:-------|:-------|:-------|
| Ruolo AAD| Ruolo ADD | Ruolo AAD | Promotori |
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
| Sponsor esecutivo   | Comunicare all'azienda visione e valori di alto livello   |  Leadership esecutiva   |
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
      - Ricerca
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
