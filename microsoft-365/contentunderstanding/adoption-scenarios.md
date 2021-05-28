---
title: Scenari e casi d'uso per Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: laurieellis
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Trova gli scenari su come usare SharePoint Syntex nell'organizzazione.
ms.openlocfilehash: b28239a304c8fab209436c12e6cdbffe160b7981
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697062"
---
# <a name="scenarios-and-use-cases-for-microsoft-sharepoint-syntex"></a>Scenari e casi d'uso per Microsoft SharePoint Syntex

Usa gli scenari di esempio seguenti per richiedere idee su come usare SharePoint Syntex nell'organizzazione.

- [Scenario: tenere traccia dei dati delle fatture con l'elaborazione dei moduli](adoption-scenarios.md#scenario-track-data-from-invoices-with-form-processing)
- [Scenario: tenere traccia delle informazioni dai contratti con informazioni sui documenti](adoption-scenarios.md#scenario-track-information-from-contracts-with-document-understanding)
- [Scenario: evitare rischi con i processi di gestione dei record, governance dei documenti e conformità basati SharePoint Syntex](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex)
- [Scenario: acquisire informazioni da documenti inaccessibili in precedenza](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [Scenario: migliorare l'elaborazione dei dati per fornire dati analitici e analitici](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [Scenario: automatizzare l'elaborazione degli ordini](adoption-scenarios.md#scenario-automate-order-processing)
- [Scenario: semplificare il processo di rinnovo del visto](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-data-from-invoices-with-form-processing"></a>Scenario: tenere traccia dei dati delle fatture con l'elaborazione dei moduli

Ad esempio, è possibile configurare un processo utilizzando SharePoint syntex e Power Automate per tenere traccia e monitorare le fatture.

1. Configurare una raccolta per archiviare i documenti delle fatture.
1. Eseguire il training del modello per riconoscere i campi nei documenti.
1. Estrarre i campi di cui si desidera tenere traccia in un elenco.
1. Configurare un flusso per inviare notifiche per eventi specifici, ad esempio:
    - Viene aggiunta una nuova fattura.
    - Una fattura è scaduta.
    - Una fattura è per un importo superiore all'importo di approvazione automatica.

![Tenere traccia e monitorare le fatture con SharePoint Syntex e Power Automate](../media/content-understanding/process-invoices-flow.png)

Quando si automatizza questo scenario, è possibile:

- Risparmia tempo e denaro estraendo automaticamente i dati dalle fatture invece di farlo manualmente.
- Ridurre potenziali errori e garantire una conformità migliore utilizzando i flussi di lavoro per controllare le fatture e segnalare eventuali problemi.

## <a name="scenario-track-information-from-contracts-with-document-understanding"></a>Scenario: tenere traccia delle informazioni dai contratti con informazioni sui documenti

Come altro esempio, è possibile configurare un processo per identificare i contratti stipulati dalla società con altre società o singoli utenti. Configurare un modello per estrarre le informazioni chiave da tali contratti, ad esempio il nome del cliente, le tariffe, le date o altre informazioni importanti, e aggiungere le informazioni alla raccolta come campi che è possibile visualizzare rapidamente. Applicare un'etichetta di conservazione nella raccolta documenti per garantire che i contratti non possano essere eliminati prima di un periodo di tempo specifico per garantire la conformità alle normative aziendali.

1. Iniziare dal centro contenuti e creare un nuovo modello di comprensione dei documenti per i contratti.
1. Upload documenti di esempio per esempi positivi e negativi, quindi eseguire la formazione per identificare i documenti del contratto ed esaminare i risultati.
1. Formare l'estrattore per identificare i campi nei contratti, ad esempio il nome del cliente, la commissione e la data, quindi testare l'estrattore.
1. Al termine del modello, applica il modello a una raccolta in cui puoi caricare contratti.
1. Applicare un'etichetta di conservazione al campo data, in modo che i contratti siano conservati nella raccolta per il periodo di tempo richiesto.

![Tenere traccia e monitorare i contratti con SharePoint Syntex e le etichette di conservazione](../media/content-understanding/process-contracts-flow.png)

Quando si automatizza questo scenario, è possibile:

- Risparmia tempo e denaro estraendo automaticamente i dati dai contratti invece di farlo manualmente.
- Garantire una conformità migliore utilizzando le etichette di conservazione per garantire che i contratti siano conservati in modo appropriato.

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>Scenario: evitare rischi con i processi di gestione dei record, governance dei documenti e conformità basati SharePoint Syntex

La riduzione dei rischi è un obiettivo comune per la maggior parte delle aziende. Potrebbe essere necessario:

- Un modo migliore per fornire/applicare la governance delle informazioni nel tenant.
- Migliorare il sistema di classificazione di documenti, messaggi di posta elettronica e altre forme di comunicazione considerati "record" per i progetti.
- Per controllare le ricevute, i contratti e così via, per garantire la conformità ai criteri aziendali.
- Per garantire che i progetti dispongono di tutta la documentazione necessaria per la conformità.

Configurare alcuni processi per la conformità con SharePoint Syntex per acquisire e classificare, controllare e contrassegnare in modo appropriato documenti e moduli che necessitano di una governance migliore. È possibile fare affidamento SharePoint Syntex per classificare automaticamente il contenuto anziché affidarsi agli utenti finali per contrassegnare manualmente o al team di conformità per applicare manualmente le regole di governance e l'archiviazione. È inoltre possibile abilitare un'esperienza di ricerca semplificata, gestire i volumi di dati, applicare criteri di gestione e conservazione dei record, garantire la conformità e procedure consigliate di archiviazione ed eliminazione.

Quando si automatizza questo scenario, è possibile sentirsi sicuri che:

- La conformità viene confermata e i rischi vengono ridotti.
- La gestione della tassonomia e dei record viene applicata in modo coerente e accurato.
- I volumi di contenuto sono controllati.
- I dipendenti possono individuare facilmente le informazioni giuste nel contesto giusto.

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Scenario: acquisire informazioni da documenti inaccessibili in precedenza

La maggior parte delle organizzazioni dispone di archivi di grandi dimensioni di documenti legali, criteri, contratti, documenti HR e linee guida per la governance. Estrarre questi archivi dati per estrarre informazioni importanti, ad esempio: progetti, settori, temi, persone, aree geografiche e così via.

Ad esempio, un responsabile delle risorse umane deve accedere rapidamente a tutti i documenti hr, inclusi curriculum, criteri hr e altri moduli. Inoltre, desiderano identificare rapidamente le informazioni necessarie dai curriculum e da altri documenti relativi alle risorse umane senza passare manualmente al setaggiamento dei documenti. Cercano una soluzione che consenta loro di trovare rapidamente le informazioni necessarie senza dover esaminare manualmente migliaia di curriculum, criteri delle risorse umane e altra documentazione che può essere diffusa in diversi siti.

Quando si automatizza questo scenario, è possibile:

- Sbloccare le conoscenze dal contenuto digitale.
- Classificare criteri hr, curriculum, documenti di vendita, progetti tecnici, piani di account ed estrarre informazioni.
- Trovare rapidamente le informazioni corrette o il documento che si sta cercando.
- Ottenere l'accesso immediato alle informazioni più recenti.
- Ridurre i tempi di ricerca.

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a>Scenario: migliorare l'elaborazione dei dati per fornire dati analitici e analitici

Ad esempio, una società farmaceutica potrebbe usare SharePoint Syntex per estrarre informazioni dai documenti DELLA FDA per rispondere alle domande dei loro dirigenti. Avere le risposte più facilmente accessibili può ridurre il tempo necessario per produrre queste risposte e aumentare la disponibilità dei dati per generare risposte più accurate alle domande sulla leadership.

Ad esempio, un project manager deve fornire rapidamente risposte alle domande relative al prodotto del team di leadership. Devono trovare informazioni e metriche relative alle query in un dashboard consolidato. Stanno cercando una soluzione che estrae le informazioni necessarie dalle etichette di prodotto, dagli opuscoli di prodotto e da altri materiali e genera un report consolidato che può essere utilizzato per la segnalazione al team di leadership.

Quando si automatizza questo scenario, è possibile:

- Ridurre il tempo necessario per produrre risposte.
- Aumentare la disponibilità dei dati.
- Fornire risposte più accurate.

## <a name="scenario-automate-order-processing"></a>Scenario: automatizzare l'elaborazione degli ordini

Con SharePoint Syntex, è possibile ridurre il tempo di elaborazione manuale degli ordini dei clienti. Ad esempio, è possibile caricare gli ordini da fax, posta elettronica o carta in SharePoint utilizzando l'elaborazione OCR e quindi estrarre i metadati da tali ordini in modo da poterli soddisfare utilizzando processi automatizzati.

Ad esempio, un responsabile della catena di approvvigionamento desidera ridurre gli errori causati dall'immissione manuale dei dati. Desiderano evitare la revisione manuale e l'immissione di dati degli ordini dei clienti in ingresso (carta, fax o posta elettronica) per ridurre gli errori che si verificano nei sistemi aziendali. Desiderano una soluzione che applica le tecniche di intelligenza artificiale e machine learning per convalidare le informazioni sugli ordini in arrivo, estrarre i dati di base e inserire automaticamente i dati nel sistema ERP, per l'evasione e la riconciliazione degli ordini.

Quando si automatizza questo scenario, è possibile verificare che:

- L'accuratezza dell'ordine e della spedizione aumenta.
- Le tariffe o le sanzioni associate agli errori di ordine o spedizione vengono ridotte.
- I ritardi nella fatturazione o nei pagamenti diminuiscono.
- I costi del personale sono ridotti.

## <a name="scenario-simplify-visa-renewal-process"></a>Scenario: semplificare il processo di rinnovo del visto

SharePoint Syntex può aiutarti ad automatizzare promemoria e rinnovi per le informazioni chiave sui contratti. Ad esempio, un responsabile delle risorse umane deve assicurarsi che i visti dei dipendenti siano aggiornati e/o rinnovati in tempo. Vogliono offrire alle persone un processo semplice e intuitivo per l'aggiornamento dei visti. Hanno bisogno di una soluzione che estrae le date di rinnovo dai contratti e invia automaticamente promemoria ai dipendenti quando si avvicinano le date di rinnovo.

Quando si automatizza questo scenario, è possibile verificare che:

- I livelli di non conformità sono ridotti.
- Il numero di promemoria manuali è ridotto.
- Il numero di sanzioni per la non conformità è ridotto.

## <a name="see-also"></a>Vedere anche

[Microsoft SharePoint Syntex adoption: Introduzione](adoption-getstarted.md)