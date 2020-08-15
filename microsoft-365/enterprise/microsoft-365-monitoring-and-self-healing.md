---
title: Microsoft 365 Monitoring and Self-Healing
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni sulle funzionalità di monitoraggio e autoguarigione di Microsoft 365.
ms.openlocfilehash: 459fdb50577c255d3cf27a31dbbbdd5768392c44
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691521"
---
# <a name="microsoft-365-monitoring-and-self-healing"></a>Microsoft 365 Monitoring and Self-Healing

Data la scala di Microsoft 365, sarebbe impossibile mantenere i dati dei clienti resilienti e sicuri da malware senza il monitoraggio integrato che è completo, avvisando che è intelligente e auto-guarigione che è veloce e affidabile. Il monitoraggio di un set di servizi alla scala di Microsoft 365 è molto impegnativo. Sono state introdotte nuove mentalità e metodologie che sono state necessarie per creare e gestire il servizio in un ambiente globale connesso. L'approccio di monitoraggio tradizionale della raccolta e del filtro dei dati è stato rimosso per creare avvisi per un approccio basato sull'analisi dei dati. prendere segnali e creare fiducia nei dati e quindi utilizzare l'automazione per recuperare o risolvere il problema. Questo approccio consente di eliminare gli umani dall'equazione di ripristino, che rende le operazioni meno onerose, veloci e meno soggette a errori. 

Fondamentale per il monitoraggio di Microsoft 365 è una raccolta di tecnologie che include il motore Data Insights, basato su Azure, SQL Azure e la tecnologia dei [database di flusso open source](https://cassandra.apache.org/). È stato creato per raccogliere e aggregare i dati e raggiungere conclusioni. Attualmente, elabora più di 500 milioni eventi all'ora da oltre 100.000 server (~ 15 TB al giorno) sparsi in decine di datacenter in molte aree geografiche e questi numeri sono in crescita. 

Microsoft 365 utilizza il *monitoraggio esterno*, che prevede la creazione di transazioni sintetiche per testare tutto ciò che è importante. Ad esempio, in Exchange Online ogni scenario verifica tutti i database di tutto il mondo ogni cinque minuti in modo sparso, fornendo una copertura continua di tutto ciò che vive nel sistema. Da più posizioni vengono eseguite 250 milioni transazioni di test giornalieri per creare una linea di base o un battito cardiaco robusto per il servizio. 

Microsoft 365 utilizza anche il concetto di *Red Alert*, che riduce tutti i segnali di monitoraggio provenienti da tutte le macchine nei nostri centri dati a un elemento gestibile da un essere umano. Il concetto è piuttosto semplice: se succede qualcosa su più segnali, deve esserci qualcosa da fare. Non si tratta di creare la sicurezza in un unico segnale, bensì di avere una fedeltà ragionevole per ogni segnale, in modo da ottenere una maggiore accuratezza. Questo sistema di monitoraggio è talmente potente che non è presente il personale 24x7 che guarda i nostri monitor; tutto quello che abbiamo è la macchina che si risveglia se rileva un problema, nel qual caso verrà pagina il personale di chiamata appropriato, o più spesso come è il caso, sarà solo andare avanti e risolvere il problema. Dopo aver avviato la raccolta dei segnali e la creazione di avvisi rossi, è possibile avviare la triangolazione in tutte le partizioni di servizio. 

In base alla combinazione tra l'avviso di errore e gli avvisi rossi, questo avviso indica esattamente quali componenti potrebbero avere un problema e che il sistema tenterà di risolvere il problema da solo riavviando un server cassette postali. 

Oltre alle funzionalità di autoguarigione, ad esempio il ripristino di una singola pagina, Exchange Online include diverse funzionalità che interessano il monitoraggio e la guarigione automatica, che si concentra sulla conservazione dell'esperienza degli utenti finali. Queste funzionalità includono la *disponibilità gestita*, che fornisce azioni di monitoraggio e ripristino incorporate, e il reseeding automatico, che ripristina automaticamente la ridondanza dei database dopo un errore del disco. 

## <a name="managed-availability"></a>Disponibilità gestita 

La disponibilità gestita fornisce una soluzione per il ripristino e il controllo dell'integrità nativo che monitora e protegge l'esperienza dell'utente finale mediante azioni orientate al ripristino. La disponibilità gestita è l'integrazione delle azioni di monitoraggio e ripristino incorporate con la piattaforma a disponibilità elevata di Exchange. Tale piattaforma è stata progettata per rilevare e risolvere i problemi non appena si verificano e vengono rilevati dal sistema. Diversamente dalle precedenti soluzioni e tecniche di monitoraggio esterno di Exchange, la disponibilità gestita non cerca di identificare o comunicare la causa principale di un problema. Si concentra invece sugli aspetti di ripristino che si riferiscono a tre aree principali dell'esperienza dell'utente finale:

- **Disponibilità** : gli utenti possono accedere al servizio? 
- **Latenza** -come è l'esperienza per gli utenti? 
- **Errori** : gli utenti sono in grado di realizzare ciò che desiderano? 

La disponibilità gestita è una funzionalità interna che viene eseguita su tutti i server Microsoft 365 che eseguono Exchange Online. Effettua il polling e analizza centinaia di metriche di integrità ogni secondo. Se si verifica un errore, la maggior parte delle volte viene risolta automaticamente. Tuttavia, saranno sempre presenti problemi che la disponibilità gestita non sarà in grado di risolvere autonomamente. In questi casi, la disponibilità gestita escrescerà il problema in un team di supporto di Microsoft 365 tramite la registrazione di eventi.

## <a name="autoreseed"></a>Reseeding automatico

I server Exchange Online vengono distribuiti in una configurazione in cui vengono archiviati più database e i relativi flussi di log sullo stesso disco non RAID. Questa configurazione viene spesso definita solo come *un gruppo di dischi* (JBOD) perché non vengono utilizzati meccanismi di ridondanza dello spazio di archiviazione, ad esempio RAID, per duplicare i dati nel disco. Quando un disco ha esito negativo in un ambiente JBOD, i dati del disco sono persi. 

Date le dimensioni di Exchange Online e il fatto che è distribuito all'interno di esso sono milioni di unità disco, gli errori dell'unità disco sono un'occorrenza normale in Exchange Online. Infatti, più di 100 hanno esito negativo ogni giorno. Quando un disco ha esito negativo in una distribuzione aziendale locale, è necessario che un amministratore sostituisca manualmente il disco non riuscito e ripristini i dati interessati. In una distribuzione cloud le dimensioni di Microsoft 365, con operatori (amministratori cloud) che sostituiscono manualmente i dischi non è né pratico né economicamente fattibile. 

Il reseeding automatico, o *il reseeding automatico*, è una funzionalità che è la sostituzione di quella che è in genere azione basata sull'operatore in risposta a un errore del disco, un evento di danneggiamento del database o un altro problema che richiede il reseeding di una copia del database. L'AutoReseed è stato ideato per ripristinare automaticamente la ridondanza del database a seguito di un errore del disco utilizzando dischi di riserva forniti con il sistema. Se un disco ha esito negativo, le copie del database archiviate su tale disco vengono reseedate automaticamente su un disco di riserva preconfigurato sul server, ripristinando in tal modo la ridondanza. 