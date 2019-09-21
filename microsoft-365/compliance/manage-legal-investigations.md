---
title: Gestire le indagini legali in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: Utilizzare i casi di eDiscovery nel centro sicurezza & compliance in Office 365 per gestire le indagini legali dell'organizzazione. Se si dispone di un abbonamento E5, è possibile analizzare ulteriormente i dati del caso utilizzando l'analisi del testo, l'apprendimento automatico e le funzionalità di codifica predittiva di Advanced eDiscovery.
ms.openlocfilehash: c6b5b3048039a8c92d120d2b9f46d6d22d9ccee0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083795"
---
# <a name="manage-legal-investigations-in-office-365"></a>Gestire le indagini legali in Office 365

Le organizzazioni hanno molti motivi per rispondere a un caso legale che coinvolge alcuni dirigenti o altri dipendenti dell'organizzazione. Ciò può comportare la ricerca e la conservazione rapida di ulteriori informazioni specifiche relative alla posta elettronica, ai documenti, alle conversazioni di messaggistica istantanea e ad altri percorsi di contenuto utilizzati dalle persone nelle attività quotidiane. È possibile eseguire queste e molte altre attività simili utilizzando gli strumenti case di eDiscovery nel centro sicurezza & conformità.
  
[Gestire le indagini legali con i casi di eDiscovery](#manage-legal-investigations-with-ediscovery-cases)
  
[Analizzare i dati dei casi tramite Office 365 Advanced eDiscovery](#analyze-case-data-using-office-365-advanced-ediscovery)
  
**Volete sapere in che modo Microsoft gestisce le indagini di eDiscovery?** Ecco un [white paper tecnico](https://go.microsoft.com/fwlink/?linkid=852161) che è possibile scaricare che spiega come utilizzare gli stessi strumenti di ricerca e analisi di Office 365 per gestire il flusso di lavoro interno di eDiscovery.
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Gestire le indagini legali con i casi di eDiscovery

i casi di eDiscovery consentono di controllare gli utenti autorizzati a creare, accedere e gestire i casi di eDiscovery nell'organizzazione. Utilizzare i casi per aggiungere membri e controllare i tipi di azioni che possono eseguire, inserire un'esenzione nei percorsi di contenuto rilevanti per un caso legale e utilizzare lo strumento di ricerca contenuto per cercare i contenuti che potrebbero rispondere al caso. È inoltre possibile esportare e scaricare i risultati per ulteriori indagini da parte di revisori esterni. Se l'organizzazione di Office 365 ha un abbonamento E5, è anche possibile preparare i risultati della ricerca per l'analisi in Advanced eDiscovery.
  
- [Gestire il flusso di lavoro di eDiscovery](ediscovery-cases.md) mediante la creazione e l'utilizzo di casi di eDiscovery per ogni indagine legale che l'organizzazione deve intraprendere 
    
- [Assegnare le autorizzazioni di eDiscovery](assign-ediscovery-permissions.md) per controllare chi può creare e gestire i casi di eDiscovery nell'organizzazione 
    
- [Impostare i limiti di conformità](tagging-and-assessment-in-advanced-ediscovery.md) per controllare i percorsi di contenuto utente che i responsabili di eDiscovery possono eseguire ricerche 
    
- [Ricerca di contenuti](search-for-content.md) nell'organizzazione 
    
- [Preparare il contenuto del caso per Advanced eDiscovery in](prepare-search-results-for-advanced-ediscovery.md) modo da poter eseguire l'analisi utilizzando potenti strumenti analitici avanzati di eDiscovery, ad esempio il riconoscimento ottico dei caratteri, il threading della posta elettronica e la codifica predittiva 
    
### <a name="use-scripts-for-advanced-scenarios"></a>Utilizzare gli script per gli scenari avanzati

Analogamente alla sezione precedente in cui sono elencati gli script per gli scenari di ricerca del contenuto, sono stati creati anche script di PowerShell per la sicurezza & Compliance Center per la gestione dei casi di eDiscovery.
  
- [Creare un rapporto di blocco di eDiscovery](create-a-report-on-holds-in-ediscovery-cases.md) contenente informazioni su tutte le esenzioni associate ai casi di eDiscovery nell'organizzazione 
    
- [Aggiungere cassette postali e posizioni OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) per un elenco di utenti a un blocco eDiscovery 
  
## <a name="analyze-case-data-using-office-365-advanced-ediscovery"></a>Analizzare i dati dei casi tramite Office 365 Advanced eDiscovery

Office 365 Advanced eDiscovery si basa sulle funzionalità di ricerca contenuto e eDiscovery descritte nelle sezioni precedenti. Dopo la creazione di un caso di eDiscovery, l'archiviazione delle posizioni del custode e la raccolta dei dati che potrebbero essere sensibili al caso, è possibile analizzare ulteriormente i dati utilizzando l'analisi del testo, l'apprendimento automatico e le funzionalità di codifica predittiva di Advanced eDiscovery. In questo modo, l'organizzazione elaborerà rapidamente migliaia di messaggi di posta elettronica, documenti e altri tipi di dati per individuare gli elementi più probabili rilevanti per un caso specifico. E, abbiamo Unified Case Management e Advanced eDiscovery in modo da poter gestire senza problemi lo stesso caso all'interno del Centro sicurezza & Compliance.
  
> [!NOTE]
> Per analizzare i dati di un utente tramite Advanced eDiscovery, all'utente (custode dei dati) deve essere assegnata una licenza di Office 365 E5. In alternativa, agli utenti con una licenza di Office 365 E1 o E3 può essere assegnata una licenza di eDiscovery autonoma avanzata. Gli amministratori e i responsabili della conformità assegnati ai casi e utilizzano Advanced eDiscovery per analizzare i dati non hanno bisogno di una licenza E5. 
  
### <a name="get-started"></a>Attività iniziali

Il modo più rapido per iniziare a utilizzare Advanced eDiscovery consiste nel creare un caso e preparare i risultati della ricerca nel centro sicurezza & conformità, caricare i risultati in Advanced eDiscovery, quindi eseguire l'analisi Express per analizzare i dati dei casi e quindi esportare i risultati per Revisione esterna.
  
- [Ottenere una breve panoramica](quick-setup-for-advanced-ediscovery.md) del flusso di lavoro avanzato di eDiscovery 
    
- [Configurare gli utenti e i casi](set-up-users-and-cases-in-advanced-ediscovery.md) per Advanced eDiscovery mediante la creazione di un caso, l'assegnazione di autorizzazioni di eDiscovery e l'aggiunta di membri del caso, il tutto tramite il centro sicurezza & Compliance 
    
- [Preparare e caricare i dati di ricerca](prepare-data-for-advanced-ediscovery.md) per il caso in Advanced eDiscovery 
    
- [Caricare i dati non di Office 365](import-non-office-365-data-into-advanced-ediscovery.md) in un caso per analizzarli in Advanced eDiscovery 
    
- [Utilizzare l'analisi Express](use-express-analysis-in-advanced-ediscovery.md) per analizzare rapidamente i dati in un caso e quindi esportare facilmente i risultati. 
    
### <a name="analyze-data"></a>Analizzare i dati

Dopo aver caricato i dati di ricerca nel caso in Advanced eDiscovery, si utilizzerà il modulo Analyze per iniziare a analizzarlo. La prima parte del processo di analisi consiste nell'organizzazione di file in gruppi di file univoci, duplicati e quasi duplicati (noti anche come somiglianza di documento). I dati verranno quindi organizzati di nuovo in gruppi gerarchicamente strutturati di thread e temi di posta elettronica e, facoltativamente, i filtri di testo vengono impostati in modo da escludere un determinato testo dall'analisi. Verrà quindi eseguita l'analisi e verranno visualizzati i risultati.
  
- Informazioni [sulla somiglianza del documento](understand-document-similarity-in-advanced-ediscovery.md) per preparare l'analisi dei dati in Advanced eDiscovery 
    
- [Configurare le opzioni](set-analyze-options-in-advanced-ediscovery.md) per i quasi duplicati, i temi e il threading della posta elettronica, quindi eseguire il modulo Analyze 
    
- [Set up ignora filtri testo](set-ignore-text-in-advanced-ediscovery.md) per escludere il testo e le stringhe di testo da analizzare. Questi filtri ignoreranno anche il testo quando si esegue l'analisi della pertinenza 
    
- [Visualizzare i risultati](view-analyze-results-in-advanced-ediscovery.md) del processo di analisi 
    
- [Configurare le impostazioni avanzate](set-analyze-advanced-settings-in-advanced-ediscovery.md) per il processo di analisi 
    
### <a name="set-up-relevance-training"></a>Configurare il training per la rilevanza

La codifica predittiva (denominata pertinenza) in Advanced eDiscovery consente di formare il sistema su ciò che si sta cercando, permettendo di prendere decisioni (se qualcosa è pertinente o meno) su un piccolo insieme di documenti.
  
- Informazioni [su come configurare la formazione di pertinenza](manage-relevance-setup-in-advanced-ediscovery.md) , contrassegnare i file rilevanti per un caso e definire i problemi di caso 
    
- [Definire eventuali problemi](define-issues-and-assign-users.md) e assegnare ogni problema a un utente che addestrerà i file 
    
- [Aggiungere i file importati al carico corrente o nuovo](set-up-loads-to-add-imported-files.md) che verrà aggiunto alla formazione relativa alla pertinenza. un carico è un nuovo batch di file che vengono aggiunti a un caso e quindi utilizzati per la formazione di pertinenza 
    
- [Definire le parole chiave evidenziate](define-highlighted-keywords-and-advanced-options.md) che è possibile aggiungere all'allenamento di pertinenza; in questo modo è possibile identificare meglio i file rilevanti per un caso 
    
### <a name="run-the-relevance-module"></a>Eseguire il modulo pertinenza

Dopo aver configurato la formazione, si è pronti per eseguire il modulo pertinenza e valutare l'efficacia delle impostazioni di formazione questo comporta una classificazione di pertinenza che consente di decidere se è necessario eseguire una formazione aggiuntiva o se si è pronti per iniziare a contrassegnare i file come rilevanti per il caso.
  
- Informazioni sul [processo di rilevanza](use-relevance-in-advanced-ediscovery.md) e sul processo iterativo di valutazione, tagging, monitoraggio e riqualificazione in base al set di file di esempio 
    
- Informazioni [sulla valutazione](assessment-in-relevance-in-advanced-ediscovery.md) , in cui un esperto che ha familiarità con il caso esamina una serie di file di casi e determina l'efficacia della formazione di pertinenza 
    
- [Valutare i file dei casi](tagging-and-assessment-in-advanced-ediscovery.md) per calcolare l'efficacia (denominata *ricchezza* ) delle impostazioni di formazione e quindi contrassegnare i file come rilevanti o non rilevanti per il caso in questione. in questo modo è possibile determinare se l'allenamento corrente è sufficiente o se è necessario modificare le impostazioni di training. 
    
- [Eseguire la formazione di pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md) dopo aver completato la valutazione e quindi ancora una volta i file Tag rilevanti o non rilevanti per i problemi definiti per il caso 
    
- [Monitorare il processo di analisi della pertinenza](track-relevance-analysis-in-advanced-ediscovery.md) per determinare se la formazione di pertinenza ha raggiunto l'obiettivo di valutazione (noto come *stato di formazione stabile* ) o se sono necessari ulteriori corsi di formazione; è inoltre possibile visualizzare i risultati relativi alla pertinenza per ogni problema di caso 
    
- [Prendere decisioni in base all'analisi della pertinenza](decision-based-on-the-results-in-advanced-ediscovery.md) per determinare le dimensioni dell'insieme risultante di file case che possono essere esportati per la revisione 
    
- [Testare la qualità dell'analisi della pertinenza](test-relevance-analysis-in-advanced-ediscovery.md) per convalidare le decisioni relative all'eliminazione dei prodotti durante il processo di pertinenza 
    
### <a name="export-results"></a>Esportare i risultati

L'ultimo passaggio per analizzare i dati dei casi in Advanced eDiscovery consiste nell'esportare i risultati dell'analisi per la revisione esterna.
  
- [Informazioni su come esportare i dati del caso](export-case-data-in-advanced-ediscovery.md)
    
- [Esportare i dati del caso](export-results-in-advanced-ediscovery.md)
    
- [Visualizzare la cronologia dei batch ed esportare i risultati precedenti](view-batch-history-and-export-past-results.md)
    
- [Esportare i campi del report](export-report-fields-in-advanced-ediscovery.md)
    
### <a name="other-advanced-ediscovery-tools"></a>Altri strumenti avanzati di eDiscovery

Advanced eDiscovery fornisce ulteriori strumenti e funzionalità oltre a analizzare i dati dei casi, l'analisi della pertinenza e l'esportazione dei dati.
  
- [Esecuzione di report avanzati di eDiscovery](run-reports-in-advanced-ediscovery.md)
    
- [Definire le impostazioni del case e del tenant](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [Utilità avanzate di eDiscovery](use-advanced-ediscovery-utilities.md)
