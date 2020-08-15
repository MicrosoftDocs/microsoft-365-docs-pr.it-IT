---
title: Microsoft 365 registrazione interna per Microsoft 365 Engineering
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
description: In questo articolo, trovare una spiegazione di come funziona la registrazione interna per i team di ingegneri di Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b4c4b1db876a6b68ec852adbbd51afe7386a1855
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696113"
---
# <a name="internal-logging-for-microsoft-365-engineering"></a>Registrazione interna per Microsoft 365 Engineering

Oltre agli eventi e ai dati dei registri disponibili per i clienti, è presente anche un sistema di raccolta dati interno disponibile per gli ingegneri Microsoft 365 di Microsoft. Molti tipi diversi di dati di log vengono caricati da server Microsoft 365 a un servizio di elaborazione dati di grandi dimensioni interno denominato Cosmos. Ogni team di servizio carica i registri di controllo dai rispettivi server nel database Cosmos per l'aggregazione e l'analisi. Questo trasferimento dei dati si verifica su una connessione TLS convalidata FIPS 140-2 su porte e protocolli approvati utilizzando uno strumento di automazione proprietaria denominato Office Data Loader (FAD). Gli strumenti utilizzati in Microsoft 365 per la raccolta e l'elaborazione dei record di controllo non consentono modifiche permanenti o irreversibili al contenuto del record di controllo originale o all'ordine di tempo.

I team di servizio utilizzano Cosmos come repository centralizzato per eseguire un'analisi dell'utilizzo delle applicazioni, per misurare le prestazioni operative e del sistema e per cercare anomalie e modelli che potrebbero indicare problemi o problemi di sicurezza. Ogni team di servizio carica una linea di base dei log in Cosmos, a seconda di ciò che stanno cercando di analizzare, che spesso includono:

- Registri eventi
- Registri di AppLocker
- Dati sulle prestazioni
- Dati di System Center
- Record dettagli chiamata
- Dati sulla qualità delle esperienze
- Registri del server Web IIS
- Registri di SQL Server
- Dati syslog
- Registri di controllo della sicurezza

Prima di caricare i dati in Cosmos, l'applicazione per l'utilizzo dell'assistenza viene utilizzata per nascondere i campi che contengono i dati dei clienti, ad esempio le informazioni sui tenant e le informazioni di identificazione degli utenti finali, e sostituire tali campi con un valore hash. I registri con hash e anonimi vengono riscritti e quindi caricati nel cosmo. I team di servizio eseguono query con ambito sui dati in Cosmos per la correlazione, l'avviso e la creazione di report. Il periodo di conservazione dei dati del log di controllo in Cosmos è determinato dai team di servizio. la maggior parte dei dati del registro di controllo viene conservata per 90 giorni o più per supportare le indagini sugli incidenti di sicurezza e soddisfare i requisiti di conservazione normativi.

L'accesso ai dati di Microsoft 365 archiviati in Cosmos è limitato al personale autorizzato. Microsoft limita la gestione della funzionalità di controllo al sottoinsieme limitato di membri del team di servizio responsabili della funzionalità di controllo. Questi membri del team non hanno la possibilità di modificare o eliminare i dati dal cosmo e tutte le modifiche apportate ai meccanismi di registrazione per Cosmos vengono registrate e controllate.

Ogni team di servizio accede ai dati di log per l'analisi autorizzando determinate applicazioni a eseguire analisi specifiche. Ad esempio, il team di sicurezza Microsoft 365 utilizza i dati provenienti da Cosmos tramite un parser di registri eventi proprietari per correlare, allertare e generare report azionabili su possibili attività sospette nell'ambiente di produzione di Microsoft 365. I report di questi dati vengono utilizzati per correggere le vulnerabilità e per migliorare le prestazioni complessive del servizio. Se un determinato avviso o rapporto richiede ulteriori indagini, il personale di servizio può richiedere l'importazione dei dati nel servizio Microsoft 365. Poiché il log specifico importato da Cosmos è crittografato e il personale di servizio non ha accesso alle chiavi di decrittografia, il log di destinazione viene passato a livello di programmazione tramite un servizio di decrittografia che restituisce i risultati con ambito al personale di servizio autorizzato. Tutte le vulnerabilità rilevate da questo esercizio sono segnalate ed Escalate utilizzando i canali di gestione degli incidenti di sicurezza standard di Microsoft.
