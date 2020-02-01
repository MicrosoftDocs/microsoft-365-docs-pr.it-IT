---
title: Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: fd53438a-a760-45f6-9df4-861b50161ae4
description: Informazioni su come Office 365 Advanced eDiscovery può essere utile per analizzare i dati di Office 365, semplificare le revisioni dei documenti e prendere decisioni per eDiscovery efficienti.
ms.openlocfilehash: a3a6291459005d60defe61a8bca40ce382b6d052
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597893"
---
# <a name="office-365-advanced-ediscovery"></a>Office 365 Advanced eDiscovery

> [!IMPORTANT]
> Continuando ad investire nelle versioni più recenti di Advanced eDiscovery, si annuncia la pensione di Office 365 Advanced eDiscovery (noto anche come *Advanced eDiscovery v 1.0*). Se si sta ancora usando Advanced eDiscovery v 1.0, passare a [Advanced eDiscovery v 2.0](overview-ediscovery-20.md) (nota anche come *soluzione avanzata di eDiscovery in Microsoft 365*) appena possibile. Advanced eDiscovery 2,0 contiene funzionalità simili rilevate in Advanced eDiscovery v 1.0, ma offre anche molte nuove funzionalità come la gestione dei depositari, la gestione delle comunicazioni e i set di revisione. Per ulteriori informazioni sul pensionamento di Advanced eDiscovery v 1.0, vedere [pensionamento degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). 
  
Con Advanced eDiscovery, è possibile comprendere meglio i dati di Office 365 e ridurre i costi di eDiscovery. Advanced eDiscovery consente di analizzare i dati non strutturati all'interno di Office 365, di eseguire una revisione dei documenti più efficiente e di prendere decisioni per la riduzione dei dati per eDiscovery. È possibile utilizzare i dati archiviati in Exchange Online, SharePoint Online, OneDrive for business, Skype for business, gruppi di Office 365 e Microsoft teams. È possibile eseguire una ricerca di eDiscovery nel centro sicurezza e conformità per cercare contenuto in gruppi, cassette postali e siti singoli e quindi analizzare i risultati della ricerca con eDiscovery avanzato. Quando si preparano i risultati della ricerca per l'analisi in Advanced eDiscovery, il riconoscimento ottico dei caratteri consente l'estrazione del testo dalle immagini. Questa funzionalità consente di applicare ai file di immagine le potenti funzionalità analitiche del testo di Advanced eDiscovery.
  
Advanced eDiscovery semplifica e velocizza il processo di revisione del documento identificando informazioni ridondanti con caratteristiche come il rilevamento e l'analisi dei thread di posta elettronica quasi duplicati. La funzionalità pertinenza applica la tecnologia di codifica predittiva per identificare i documenti rilevanti. Advanced eDiscovery apprende dalle decisioni di tagging sui documenti di esempio e applica tecniche statistiche e di apprendimento automatico per calcolare la pertinenza di ogni documento nel set di dati. In questo modo è possibile concentrarsi sui documenti principali, prendere decisioni rapide ma informate sulla strategia del caso, i dati di eliminazione e la revisione delle priorità.
  
 **Perché Advanced eDiscovery?** Office 365 Advanced eDiscovery si basa sull'insieme esistente di funzionalità di eDiscovery in Office 365. Ad esempio, è possibile utilizzare la funzionalità di ricerca nel centro sicurezza &amp; e conformità di Office 365 per eseguire una ricerca iniziale di tutte le origini di contenuto dell'organizzazione per identificare e raccogliere i dati che possono essere rilevanti per uno specifico caso legale. Successivamente, è possibile eseguire un'analisi su tali dati applicando il testo analitico, l'apprendimento automatico e la funzionalità di codifica predittiva e di rilevanza di Advanced eDiscovery. In questo modo, l'organizzazione elaborerà rapidamente migliaia di messaggi di posta elettronica, documenti e altri tipi di dati per individuare gli elementi più probabili rilevanti per una specifica 
 
> [!NOTE]
> Advanced eDiscovery richiede un Office 365 E3 con il componente aggiuntivo per la conformità avanzato o un abbonamento E5 per l'organizzazione. Se non si dispone di tale piano e si desidera provare Advanced eDiscovery, è possibile [iscriversi per una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). caso. Il set di dati ridotto può quindi essere esportato fuori da Office 365 per ulteriori riesami. 
  
## <a name="get-started"></a>Introduzione

Il modo più rapido per iniziare a utilizzare Advanced eDiscovery consiste nel creare un caso e preparare i risultati della ricerca nel centro sicurezza & conformità, caricare i risultati in Advanced eDiscovery, quindi eseguire l'analisi Express per analizzare i dati dei casi e quindi esportare i risultati per la revisione esterna.
  
- [Ottenere una breve panoramica](quick-setup-for-advanced-ediscovery.md) del flusso di lavoro avanzato di eDiscovery 
    
- [Configurare gli utenti e i casi](set-up-users-and-cases-in-advanced-ediscovery.md) per Advanced eDiscovery mediante la creazione di un caso, l'assegnazione di autorizzazioni di eDiscovery e l'aggiunta di membri del caso, il tutto tramite il centro sicurezza & Compliance 
    
- [Preparare e caricare i dati di ricerca](prepare-data-for-advanced-ediscovery.md) per il caso in Advanced eDiscovery 
    
- [Caricare i dati non di Office 365](import-non-office-365-data-into-advanced-ediscovery.md) in un caso per analizzarli in Advanced eDiscovery 
    
- [Utilizzare l'analisi Express](use-express-analysis-in-advanced-ediscovery.md) per analizzare rapidamente i dati in un caso e quindi esportare facilmente i risultati. 
    
## <a name="analyze-data"></a>Analizzare i dati

Dopo aver caricato i dati di ricerca nel caso in Advanced eDiscovery, si utilizzerà il modulo Analyze per iniziare a analizzarlo. La prima parte del processo di analisi consiste nell'organizzazione di file in gruppi di file univoci, duplicati e quasi duplicati (noti anche come somiglianza di documento). Successivamente, i dati vengono organizzati di nuovo in gruppi gerarchicamente strutturati di thread e temi di posta elettronica e, facoltativamente, vengono impostati i filtri di testo per escludere un determinato testo dall'analisi. Successivamente, eseguire l'analisi e visualizzare i risultati.
  
- Informazioni [sulla somiglianza del documento](understand-document-similarity-in-advanced-ediscovery.md) per preparare l'analisi dei dati in Advanced eDiscovery 
    
- [Configurare le opzioni](set-analyze-options-in-advanced-ediscovery.md) per i quasi duplicati, i temi e il threading della posta elettronica, quindi eseguire il modulo Analyze 
    
- [Set up ignora filtri testo](set-ignore-text-in-advanced-ediscovery.md) per escludere il testo e le stringhe di testo da analizzare. Questi filtri ignoreranno anche il testo quando si esegue l'analisi della pertinenza 
    
- [Visualizzare i risultati](view-analyze-results-in-advanced-ediscovery.md) del processo di analisi 
    
- [Configurare le impostazioni avanzate](set-analyze-advanced-settings-in-advanced-ediscovery.md) per il processo di analisi 
    
## <a name="set-up-relevance-training"></a>Configurare il training per la rilevanza

La codifica predittiva (denominata pertinenza) in Advanced eDiscovery consente di formare il sistema su ciò che si sta cercando, permettendo di prendere decisioni (se qualcosa è pertinente o meno) su un piccolo insieme di documenti.
  
- Informazioni [su come configurare la formazione di pertinenza](manage-relevance-setup-in-advanced-ediscovery.md) , contrassegnare i file rilevanti per un caso e definire i problemi di caso 
    
- [Definire eventuali problemi](define-issues-and-assign-users.md) e assegnare ogni problema a un utente che addestrerà i file 
    
- [Aggiungere i file importati al carico corrente o nuovo](set-up-loads-to-add-imported-files.md) che verrà aggiunto alla formazione relativa alla pertinenza. Un carico è un nuovo batch di file che vengono aggiunti a un caso e quindi utilizzati per la formazione di pertinenza 
    
- [Definire le parole chiave evidenziate](define-highlighted-keywords-and-advanced-options.md) che è possibile aggiungere all'allenamento di pertinenza. In questo modo è possibile identificare meglio i file rilevanti per un caso 
    
## <a name="run-the-relevance-module"></a>Eseguire il modulo pertinenza

Dopo aver configurato l'allenamento, si è pronti per eseguire il modulo pertinenza e valutare l'efficacia delle impostazioni di formazione. Questo comporta una classificazione di pertinenza che aiuta a decidere se è necessario eseguire ulteriori corsi di formazione o se si è pronti per iniziare a contrassegnare i file come rilevanti per il caso.
  
- Informazioni sul [processo di rilevanza](use-relevance-in-advanced-ediscovery.md) e sul processo iterativo di valutazione, tagging, monitoraggio e riqualificazione in base al set di file di esempio 
    
- Informazioni [sulla valutazione](assessment-in-relevance-in-advanced-ediscovery.md) , in cui un esperto che ha familiarità con il caso esamina una serie di file di casi e determina l'efficacia della formazione di pertinenza 
    
- [Valutare i file dei casi](tagging-and-assessment-in-advanced-ediscovery.md) per calcolare l'efficacia (chiamata * richezza) delle impostazioni di formazione e quindi contrassegnare i file come rilevanti o non rilevanti per il caso. In questo modo è possibile determinare se l'allenamento corrente è sufficiente o se è necessario modificare le impostazioni di training. 
    
- [Eseguire la formazione di pertinenza](tagging-and-relevance-training-in-advanced-ediscovery.md) dopo aver completato la valutazione e quindi ancora una volta i file Tag rilevanti o non rilevanti per i problemi definiti per il caso 
    
- [Monitorare il processo di analisi della pertinenza](track-relevance-analysis-in-advanced-ediscovery.md) per determinare se la formazione di pertinenza ha raggiunto l'obiettivo di valutazione (noto come stato * di formazione stabile) o se sono necessari ulteriori corsi di formazione; è inoltre possibile visualizzare i risultati relativi alla pertinenza per ogni problema di caso 
    
- [Prendere decisioni in base all'analisi della pertinenza](decision-based-on-the-results-in-advanced-ediscovery.md) per determinare le dimensioni dell'insieme risultante di file case che possono essere esportati per la revisione 
    
- [Testare la qualità dell'analisi della pertinenza](test-relevance-analysis-in-advanced-ediscovery.md) per convalidare le decisioni relative all'eliminazione dei prodotti durante il processo di pertinenza 
    
## <a name="export-results"></a>Esportare i risultati

L'ultimo passaggio per analizzare i dati dei casi in Advanced eDiscovery consiste nell'esportare i risultati dell'analisi per la revisione esterna.
  
- [Informazioni su come esportare i dati del caso](export-case-data-in-advanced-ediscovery.md)
    
- [Esportare i dati del caso](export-results-in-advanced-ediscovery.md)
    
- [Visualizzare la cronologia dei batch ed esportare i risultati precedenti](view-batch-history-and-export-past-results.md)
    
- [Esportare i campi del report](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a>Altri strumenti avanzati di eDiscovery

Advanced eDiscovery fornisce ulteriori strumenti e funzionalità oltre a analizzare i dati dei casi, l'analisi della pertinenza e l'esportazione dei dati.
  
- [Esecuzione di report avanzati di eDiscovery](run-reports-in-advanced-ediscovery.md)
    
- [Definire le impostazioni del case e del tenant](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [Utilità avanzate di eDiscovery](use-advanced-ediscovery-utilities.md)
