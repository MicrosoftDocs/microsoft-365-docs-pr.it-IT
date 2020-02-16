---
title: Panoramica delle indagini sui dati (anteprima) in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo viene descritto il nuovo strumento di analisi dei dati (Preview) in Microsoft 365.
ms.openlocfilehash: 1dc0a98208d553a4ea94703b98f982dd8e19167f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071079"
---
# <a name="overview-of-data-investigations-preview-in-microsoft-365"></a>Panoramica delle indagini sui dati (anteprima) in Microsoft 365

La fuoriuscita di dati si verifica quando un documento contenente contenuti riservati, sensibili o dannosi viene rilasciato in un ambiente non attendibile. Quando viene rilevata una fuoriuscita di dati, è importante contenere rapidamente l'ambiente, valutare la dimensione e le posizioni del versamento, esaminare le attività degli utenti e quindi eliminare i dati versati dal servizio. Utilizzando lo strumento nuovo data Investigation (Preview), è possibile eseguire la ricerca di dati sensibili, dannosi o fuori luogo tra Office 365, esaminare cosa è successo e intraprendere le azioni appropriate per correggere la fuoriuscita.  

In questo articolo viene descritto come utilizzare le funzionalità del nuovo strumento di analisi dei dati (Preview) per risolvere uno scenario di fuoriuscita dei dati.

## <a name="permissions"></a>Autorizzazioni

Per accedere e condurre un'indagine sui dati, è necessario essere membri del gruppo di ruolo ricercatore di dati. Per ulteriori informazioni, vedere [assegnare le autorizzazioni per le indagini sui dati](permissions.md).

## <a name="data-investigations-preview-workflow"></a>Analisi dei dati (anteprima) flusso di lavoro 

Nelle sezioni seguenti viene descritto ogni passaggio del flusso di lavoro incorporato in indagini sui dati (Preview). Nella schermata seguente viene illustrata la scheda **Home** di un'indagine denominata *High Risk: Finance Documents dispersione*. 

![Flusso di lavoro nello strumento indagini dati](../media/DataInvestigationsWorkflow.png)

## <a name="search-for-sensitive-malicious-or-misplaced-data"></a>Ricerca di dati sensibili, dannosi o fuori luogo

Utilizzare la scheda **ricerche** per creare ricerche per trovare la pagina di Office 365 per i dati che si desidera correggere. È possibile creare ed eseguire ricerche basate su query per identificare un set di messaggi di posta elettronica e documenti che potrebbero contenere dati rovesciati e quindi raccoglierli come prova per esaminare e analizzare. Inoltre, è possibile utilizzare lo strumento di ricerca per visualizzare in anteprima i documenti di esempio e visualizzare le statistiche di ricerca che consentono di affinare e migliorare i risultati della ricerca. Dopo aver verificato che i risultati della ricerca contengono tutti i dati rilevanti per l'indagine, è necessario aggiungere i risultati della ricerca al set di evidenze per ulteriori riesami, valutazioni dell'impatto ed eseguire azioni correttive in base alle esigenze. Per ulteriori informazioni, vedere [Search for data in an Investigation](search-for-data.md).

## <a name="review-and-investigate-evidence"></a>Esaminare ed esaminare gli elementi probatori

Utilizzare la scheda **Evidence** per esaminare i dati raccolti dal servizio Live, che in questo caso è Office 365. I dati del set di evidenze sono uno snapshot dei risultati della ricerca raccolti. Quando si aggiungono i risultati della ricerca come prova, viene attivato un processo per estrarre file, metadati e testo. Al termine del processo, lo strumento di analisi dei dati crea un nuovo indice di tutti i dati e lo aggiunge a un set di prove. Per qualsiasi indagine sensibile al tempo, questo consente di contenere rapidamente l'ambiente eliminando i dati presenti nei percorsi di contenuto originale (nel servizio Live) durante l'analisi delle evidenze raccolte in un ambiente in quarantena. Dopo la raccolta di prove, è possibile eseguire altre query per limitare i dati in base a intervalli temporali, tipi di file, proprietari di dati e altri tipi di condizioni. Ad esempio, utilizzando le condizioni per l'autore, il mittente e il destinatario, è possibile identificare rapidamente coloro che sono stati coinvolti nella perdita di dati e se uno qualsiasi dei dati versati è stato condiviso con persone esterne all'organizzazione.

È inoltre possibile eseguire l'analisi avanzata sulle prove raccolte. In questo modo è possibile fornire i temi generali e organizzare le prove tramite thread di posta elettronica, duplicati esatti e quasi duplicati per facilitare l'indagine. È possibile esaminare i documenti in visualizzazione testo estratto o nel formato di file nativo e contrassegnarli con i risultati dell'analisi. Per altre informazioni, vedere:

  - [Esaminare i dati nelle prove](review-data-in-evidence.md)

  - [Eseguire analisi per velocizzare le indagini](run-analytics-to-investigate-faster.md)


## <a name="managing-people-of-interest"></a>Gestione degli utenti di interesse

Utilizzare la scheda **utenti di interesse** per aggiungere e gestire gli utenti identificati come persone di interesse durante l'indagine sull'evidenza. Quando si aggiungono persone di interesse, le origini dati, ad esempio la cassetta postale e l'account OneDrive, vengono identificate e mappate. È quindi possibile cercare nell'ambito ricerche solo i percorsi di contenuto di tali utenti. Quando gli utenti hanno un ambito di interesse, le ricerche sono più efficienti e accurate perché lo strumento rielabora tutti i dati non indicizzati, ad esempio immagini o tipi di file non supportati. Nella scheda **utenti di interesse** è inoltre possibile visualizzare e cercare l'attività dei log di controllo di tali utenti per facilitare l'indagine. È possibile aggiungere altre persone di interesse durante l'indagine. Per ulteriori informazioni, vedere [Manage people of interest an Investigation](manage-people-of-interest.md).

## <a name="indexing-the-data-of-people-of-interest"></a>Indicizzazione dei dati degli utenti interessati

L'aggiunta di una persona interessata a un'indagine riindicizza tutti gli elementi parzialmente indicizzati dalle origini dati della persona. Questo processo è denominato *Advanced indicizzazione*. Advanced indicizzazione rielabora i dati quali immagini e tipi di file non supportati in modo che questi dati siano completamente individuabili quando si eseguono ricerche per raccogliere i dati per un'indagine. Utilizzare la scheda **elaborazione** per monitorare lo stato dell'indicizzazione avanzata e correggere eventuali errori di elaborazione che possono verificarsi utilizzando un processo denominato correzione degli *errori*. Per ulteriori informazioni, vedere [correzione degli errori durante l'elaborazione dei dati per un'indagine](error-remediation.md).

## <a name="exporting-data"></a>Esportazione di dati

Se si desidera esportare i dati, utilizzare la scheda **Esporta** per gestire un processo di esportazione e scaricare i dati dal set di evidenze. Quando si esportano le evidenze, i dati vengono caricati in un percorso di archiviazione di Azure e quindi sono disponibili per il download in un computer locale. Nella scheda **esportazioni** è possibile ottenere l'URL della posizione di archiviazione di Azure e la chiave di valutazione dello spazio di archiviazione, che sono entrambi necessari per scaricare i dati esportati. Per ulteriori informazioni, vedere [esportare i dati da un'indagine](export-data.md).

## <a name="managing-jobs"></a>Gestione dei processi

Utilizzare la scheda **processi** per monitorare i processi a esecuzione prolungata per le attività correlate all'indagine. Sono inclusi i processi per l'esecuzione delle ricerche, l'aggiunta di dati a un set di prove, la reindicizzazione dei dati e l'esportazione di elementi probatori Ad esempio, è possibile creare una ricerca nella scheda **ricerche** che include molte origini dati. Lo stato di questo processo di ricerca viene visualizzato nella scheda **processi** . Per ulteriori informazioni, vedere [gestire i processi in un'analisi dei dati](manage-jobs.md).

## <a name="configuring-investigation-settings"></a>Configurazione delle impostazioni di analisi

Utilizzare la scheda **Impostazioni** per configurare le impostazioni a livello di analisi. Ciò include l'aggiunta di membri a un'indagine, la chiusura o l'eliminazione di un'analisi e la configurazione del comportamento di ricerca e analisi.
