---
title: Utilizzare le comunicazioni in Advanced eDiscovery
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
description: Advanced eDiscovery facilita la gestione del flusso di lavoro di notifica per la conservazione legale in merito alla notifica ai depositari nelle indagini legali.
ms.openlocfilehash: 4ca3e5a8e500f6a8e5a5483ccc3efd070c05c5cd
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071583"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a>Utilizzare le comunicazioni in Advanced eDiscovery

Advanced eDiscovery consente ai reparti legali di semplificare i propri processi per il monitoraggio e la distribuzione delle notifiche di blocco legale. Lo strumento di comunicazione del custode consente ai servizi legali di gestire e automatizzare l'intero processo di conservazione, dalle notifiche iniziali ai promemoria e alle escalation, tutto in un'unica posizione.

## <a name="what-is-a-legal-hold-notification"></a>Che cos'è una notifica di conservazione legale?

Avviso di conservazione (noto anche come *blocco per controversia*legale) è una notifica inviata dal reparto legale di un'organizzazione ai dipendenti, al personale contingente o ai depositari di dati che potrebbero essere rilevanti per un'indagine legale. Tali notifiche indicano ai depositari di conservare le informazioni archiviate elettronicamente, nonché qualsiasi contenuto che potrebbe essere pertinente a una questione legale attiva o imminente. I team legali devono sapere che ogni custode ha ricevuto, letto, compreso e ha accettato di conformarsi alle istruzioni fornite.

## <a name="the-legal-hold-notification-process"></a>Processo di notifica per il blocco legale

Un'organizzazione ha il dovere di conservare le informazioni rilevanti quando viene a conoscenza di una controversia legale imminente o di un'indagine di regolamentazione. Per soddisfare i requisiti di conservazione di un'indagine, l'organizzazione deve informare immediatamente i potenziali depositari del proprio dovere di preservare le informazioni rilevanti.

Con Advanced eDiscovery, i team legali possono creare e personalizzare il flusso di lavoro di notifica per la conservazione legale. Lo strumento di comunicazione del custode consente ai team legali di configurare le notifiche e i flussi di lavoro seguenti:

1. **Avviso di rilascio**: un avviso di conservazione legale viene emesso (o avviato) da una notifica del reparto legale ai depositari che potrebbero avere informazioni rilevanti sulla questione del caso. Questo avviso indica ai depositari di conservare tutte le informazioni che potrebbero essere necessarie per l'individuazione.
   
2.  **Avviso di riemissione**: durante un caso, è possibile che ai depositari venga richiesto di conservare contenuto aggiuntivo (o meno contenuto) rispetto a quanto richiesto in precedenza. Per questo scenario, è possibile aggiornare l'avviso di conservazione esistente e ristamparlo in depositari.

3.  **Avviso di rilascio**: una volta risolto il problema e il custode non è più soggetto a un requisito di conservazione, il custode può essere rilasciato dal caso. Inoltre, è possibile notificare al custode che non sono più necessari per mantenere il contenuto e fornire istruzioni su come riprendere la normale attività lavorativa in relazione ai dati.

4. **Promemoria e escalation**: in alcuni casi, solo l'emissione di un avviso non è sufficiente per soddisfare i requisiti di individuazione legale. Con ogni notifica, i team legali possono programmare una serie di flussi di lavoro di promemoria e di escalation per il follow-up automatico con custodi insensibili.

    - **Promemoria**: dopo aver emesso o riemesso un avviso per la conservazione legale, un'organizzazione può impostare i promemoria per avvisare gli amministratori che non rispondono.

    - **Escalation**: in alcuni casi, se un custode rimane inattivo anche dopo una serie di promemoria per un determinato periodo di tempo, il team legale può impostare un flusso di lavoro di escalation per notificare ai depositari non rispondenti e al loro manager.

## <a name="role-groups-and-permissions"></a>Gruppi di ruoli e autorizzazioni 

I team legali possono controllare e separare l'attività del caso utilizzando gruppi di ruoli e autorizzazioni di eDiscovery nel centro sicurezza & Compliance. 

Per creare e gestire notifiche di blocco legale, un utente deve far parte dei gruppi di ruoli seguenti:

- **eDiscovery Manager** : i membri di questo gruppo di ruoli possono creare e gestire i casi di eDiscovery. Sono in grado di aggiungere e rimuovere membri, inserire depositari e posizioni di contenuto in attesa, gestire le notifiche di archiviazione legale, creare e modificare le ricerche di contenuto associate a un caso, esportare i risultati di una ricerca di contenuto e preparare i risultati della ricerca per l'analisi in Advanced eDiscovery. In questo gruppo di ruoli sono disponibili due sottogruppi. La differenza tra questi sottogruppi dipende dall'ambito.

  - **eDiscovery Manager** -è in grado di visualizzare e gestire i casi di eDiscovery che creano o sono membri di. Se un altro Manager di eDiscovery crea un caso ma non aggiunge un secondo Manager di eDiscovery come membro del caso, il secondo responsabile di eDiscovery non sarà in grado di visualizzare o aprire il caso nella pagina eDiscovery del Centro sicurezza & Compliance. i responsabili di eDiscovery possono inoltre accedere ai propri casi in Advanced eDiscovery per eseguire attività di analisi.

  - **amministratore di eDiscovery** : consente di eseguire tutte le attività di gestione dei casi che un Manager di eDiscovery può eseguire. Inoltre, un amministratore di eDiscovery è in grado di:
    
    - Visualizzare tutti i casi elencati nella pagina eDiscovery.
    - Gestire qualsiasi caso nell'organizzazione dopo che si è aggiunto come membro del caso.
    - Accedere ai dati del caso in Advanced eDiscovery per tutti i casi nell'organizzazione.

Per ulteriori informazioni, vedere [assegnare le autorizzazioni di eDiscovery nel centro sicurezza & Compliance](assign-ediscovery-permissions.md).
