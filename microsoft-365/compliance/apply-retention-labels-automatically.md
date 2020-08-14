---
title: Applicare automaticamente un'etichetta di conservazione per conservare o eliminare il contenuto
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Creare e pubblicare automaticamente etichette di conservazione in modo da poter applicare automaticamente etichette per conservare ciò che serve ed eliminare ciò che non serve
ms.openlocfilehash: 80a5ef502450a24d9c8aeeb08d571bfcbd51a4e3
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648805"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a>Applicare automaticamente un'etichetta di conservazione per conservare o eliminare il contenuto

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Una delle funzionalità più efficaci delle [etichette di conservazione](retention.md) è la possibilità di applicarle automaticamente al contenuto che soddisfa condizioni specificate. In questo caso, gli utenti dell'organizzazione non dovranno applicare le etichette di conservazione. Microsoft 365 lo farà automaticamente.
  
Le etichette di conservazione applicate automaticamente sono potenti perché:
  
- Non è necessario formare gli utenti su tutte le classificazioni.
    
- Non è necessario affidarsi solo agli utenti per la classificazione corretta di tutto il contenuto.
    
- Gli utenti non hanno più bisogno di conoscere i criteri di governance dai dati e possono concentrarsi sul loro lavoro.
    
È possibile applicare automaticamente etichette di conservazione al contenuto quando questo include informazioni sensibili, parole chiave o una corrispondenza per [classificatori sottoponibili a training](classifier-getting-started-with.md).
    
I processi per l'applicazione automatica di un'etichetta di conservazione si basano sulle condizioni seguenti:

![Diagramma di ruoli e attività per le etichette applicate automaticamente](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

Usare le istruzioni seguenti per i due passaggi per l'amministratore.

> [!NOTE]
> I criteri di applicazione automatica usano l'etichettatura sul lato servizio con condizioni per applicare automaticamente etichette di conservazione. È anche possibile applicare automaticamente un'etichetta di conservazione con un criterio di etichetta eseguendo le operazioni seguenti: 
>
> - Applicare un'etichetta di conservazione predefinita a un set di documenti, una cartella o una raccolta di SharePoint in modo che il contenuto non etichettato presente nel contenitore venga etichettato automaticamente
>- Applicazione automatica di un'etichetta di conservazione alla posta elettronica mediante regole
>
> Per questi scenari, vedere [Creare e applicare etichette di conservazione nelle app](create-apply-retention-labels.md).

## <a name="before-you-begin"></a>Prima di iniziare

L'amministratore globale dell'organizzazione dispone delle autorizzazioni complete per creare e modificare le etichette conservazione e i relativi criteri. Se non si esegue l'accesso come amministratore globale, vedere le [autorizzazioni necessarie per creare e gestire criteri di conservazione ed etichette di conservazione](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="how-to-auto-apply-a-retention-label"></a>Come applicare automaticamente un'etichetta di conservazione

Creare prima di tutto l'etichetta di conservazione. Quindi, creare un criterio automatico per applicare l'etichetta. Se è già stata creata l'etichetta di conservazione, passare a [Creare un criterio di applicazione automatica](#step-2-create-an-auto-apply-policy).

Le istruzioni di spostamento variano a seconda che si usi o meno la [gestione dei record](records-management.md). Sono disponibili istruzioni per entrambi gli scenari.

### <a name="step-1-create-a-retention-label"></a>Passaggio 1: Creare un'etichetta di conservazione

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) passare a una delle posizioni seguenti:
    
    - Se si usa la gestione dei record:
        - **Soluzioni** > **Records management** > scheda **Piano di archiviazione** > **+ Crea un'etichetta** > **Etichetta di conservazione**
        
    - Se non si usa la gestione dei record:
       - **Soluzioni** > **Governance delle informazioni** > scheda **Etichette** > + **Crea un'etichetta**
    
    L'opzione non è immediatamente visibile? Selezionare per prima cosa **Mostra tutto**. 

2. Seguire le istruzioni della procedura guidata. Se si usa la gestione dei record:
    
    - Per informazioni sui descrittori del piano di archiviazione, vedere [Usare il piano di archiviazione per gestire le etichette di conservazione](file-plan-manager.md).
    
    - Per usare l'etichetta di conservazione per dichiarare il contenuto come record, attivare la casella di controllo **Usa l'etichetta per classificare il contenuto come "Record"**.

Per modificare un'etichetta esistente, selezionarla e quindi selezionare **Modifica etichetta** per avviare la stessa procedura guidata che consente di modificare le descrizioni dell'etichetta e le [impostazioni idonee](#updating-retention-labels-and-their-policies) dal passaggio 2. In alternativa, selezionare una delle opzioni **Modifica** disponibili per passare direttamente alla pagina pertinente per eseguire l'aggiornamento.


### <a name="step-2-create-an-auto-apply-policy"></a>Passaggio 2: Creare un criterio di applicazione automatica

Quando si crea un criterio di applicazione automatica, si seleziona un'etichetta di conservazione da applicare automaticamente al contenuto in base alle condizioni specificate.

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) passare a una delle posizioni seguenti:
    
    - Se si usa la gestione dei record: **Governance delle informazioni**:
        - **Soluzioni** > **Gestione dei record** > scheda **Criteri delle etichette** > **Applica automaticamente le etichette**
    
    - Se non si usa la gestione dei record:
        - **Soluzioni** > **Governance delle informazioni** > scheda **Criteri delle etichette** > **Applica automaticamente le etichette**
    
    L'opzione non è immediatamente visibile? Selezionare per prima cosa **Mostra tutto**. 

2. Seguire le istruzioni della procedura guidata.
    
    Per informazioni su come configurare le condizioni per l'applicazione automatica dell'etichetta di conservazione, vedere la sezione [Configurare le condizioni per l'applicazione automatica delle etichette di conservazione](#configuring-conditions-for-auto-apply-retention-labels) in questa pagina.
    
    Per informazioni sulle posizioni supportate dalle etichette di conservazione, vedere la sezione [Etichette di conservazione e posizioni](retention.md#retention-label-policies-and-locations).

Per modificare un criterio di etichetta applicata automaticamente, selezionarlo e quindi selezionare **Modifica criteri** per avviare la stessa procedura guidata che consente di modificare la descrizione del criterio e le [impostazioni idonee](#updating-retention-labels-and-their-policies) dal passaggio 2. In alternativa, selezionare una delle opzioni **Modifica** disponibili per passare direttamente alla pagina pertinente per eseguire l'aggiornamento.

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a>Configurare le condizioni per l'applicazione automatica delle etichette di conservazione

È possibile applicare automaticamente etichette di conservazione al contenuto quando questo contiene:

- [Tipi specifici di informazioni riservate.](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [Parole chiave specifiche che corrispondono a una query creata.](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [Una corrispondenza per classificatori sottoponibili a training](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>Applicare automaticamente etichette al contenuto con tipi specifici di informazioni sensibili

Quando si creano etichette di conservazione ad applicazione automatica per le informazioni riservate, viene visualizzato lo stesso elenco di modelli di criteri mostrato quando si creano criteri di prevenzione della perdita dei dati (DLP). Ogni modello di criteri è preconfigurato in modo da cercare specifici tipi di informazioni riservate. Ad esempio, il modello illustrato di seguito cerca codici identificativi del singolo contribuente (ITIN), codici di previdenza sociale (SSN) e numeri di passaporto statunitensi. Per altre informazioni sui criteri DLP, vedere [Panoramica dei criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md).
  
![Modelli di criteri con le tipologie di informazioni sensibili](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
Dopo aver selezionato un modello di criteri, è possibile aggiungere o rimuovere qualunque tipo di informazioni riservate e modificare il numero di istanze e l'accuratezza della corrispondenza. Nell'esempio mostrato di seguito, verrà applicata automaticamente un'etichetta di conservazione solo quando:
  
- Il contenuto include tra 1 e 9 istanze di qualsiasi di tipo di informazioni riservate. È possibile eliminare il valore **max** in modo che diventi **qualsiasi**.
    
- Il tipo di informazioni sensibili rilevate ha un'accuratezza della corrispondenza (o livello di attendibilità) di almeno 75. Molti tipi di informazioni sensibili sono definiti con più criteri. I criteri con un livello di accuratezza della corrispondenza superiore richiedono l'individuazione di ulteriori elementi di prova (ad esempio parole chiave, date o indirizzi), mentre i criteri con un livello di accuratezza della corrispondenza inferiore richiedono meno elementi di prova. Più basso è il valore di accuratezza della corrispondenza **min**, più facile sarà che il contenuto soddisfi la condizione. 
    
Per altre informazioni su queste opzioni, vedere [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match) (Ottimizzazione delle regole per rendere più facile o difficile la corrispondenza).
    
![Opzioni per l'identificazione dei tipi di informazioni riservate](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>Applicare automaticamente etichette al contenuto con parole chiave o con proprietà disponibili per le ricerche

È possibile applicare automaticamente etichette al contenuto che soddisfa determinate condizioni. Le condizioni disponibili ora supportano l'applicazione di un'etichetta al contenuto che include parole, frasi, valori o proprietà disponibili per le ricerche specifiche. È possibile perfezionare la query usando operatori di ricerca come AND, OR e NOT.

Durante l'applicazione automatica delle etichette per le proprietà ricercabili, nella query non è possibile usare un alias per una proprietà gestita. Deve essere il nome effettivo della proprietà gestita, ad esempio RefinableString01.

Per altre informazioni sulla sintassi della query, vedere:

- [Riferimenti per la sintassi di Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

Le etichette basate su query usano l’indice di ricerca per identificare il contenuto. Per altre informazioni sulle proprietà disponibili per la ricerca valide, vedere:

- [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
- [Panoramica delle proprietà gestite e sottoposte a ricerca per indicizzazione in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

Esempi di query:

- Exchange
    - subject:"Quarterly Financials"
    - recipients:garthf<!--nolink-->@contoso.com
- SharePoint e OneDrive
    - contenttype:contract
    - site:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract

![Editor di query](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>Etichette applicate automaticamente al contenuto con classificatori sottoponibili a training

Se si sceglie l'opzione del classificatore sottoponibile a training, è possibile selezionare un classificatore predefinito oppure personalizzato. I classificatori predefiniti includono i **curriculum**, il **codice sorgente**, le **molestie mirate**, i **contenuti volgari** e le **minacce**:

![Scegliere un classificatore sottoponibile a training](../media/retention-label-classifers.png)

> [!CAUTION]
> Il classificatore predefinito **Linguaggio offensivo** è stato deprecato perché generava un numero elevato di falsi positivi. Non usare questo classificatore predefinito e, se è in uso, è consigliabile spostare i processi aziendali da esso. Usare invece i classificatori predefiniti per **molestie**, **volgarità** e **minacce**.

Per applicare automaticamente un'etichetta utilizzando questa opzione, i siti e le cassette postali di SharePoint Online devono avere almeno 10 MB di dati.

Per altre informazioni sui classificatori sottoponibili a training, vedere [Introduzione ai classificatori sottoponibili a training (anteprima)](classifier-getting-started-with.md).

Per avere un esempio di configurazione, vedere [Come preparare e usare un classificatore integrato](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>Tempo necessario per l'applicazione delle etichette di conservazione

In caso di applicazione automatica di etichette di conservazione, possono essere necessari fino a sette giorni prima che le etichette vengano applicate a tutto il contenuto esistente che soddisfa le condizioni.
  
![Diagramma di disponibilità delle etichette applicate automaticamente](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a>Aggiornare le etichette di conservazione e i criteri

Quando si modifica un'etichetta di conservazione o un criterio di applicazione automatica e l'etichetta di conservazione è già applicata al contenuto, le impostazioni aggiornate verranno applicate automaticamente a tale contenuto oltre che a quello identificato per la prima volta.

Alcune impostazioni non possono essere modificate dopo aver creato e salvato l'etichetta o i criteri, tra cui:
- Le impostazioni di conservazione tranne il periodo di conservazione, a meno che l'etichetta non sia stata configurata per conservare o eliminare il contenuto in base alla data di creazione.
- L'opzione per classificare come record.

## <a name="next-steps"></a>Passaggi successivi

Vedere [Usare etichette di riservatezza per gestire il ciclo di vita dei documenti archiviati in SharePoint](auto-apply-retention-labels-scenario.md) per uno scenario di esempio in cui vengono usati un criterio di applicazione automatica con proprietà gestite in SharePoint conservazione e la conservazione basata su eventi per avviare il periodo di conservazione.
