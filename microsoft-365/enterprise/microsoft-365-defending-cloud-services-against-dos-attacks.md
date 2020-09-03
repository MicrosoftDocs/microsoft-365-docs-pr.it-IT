---
title: Difesa dei servizi cloud di Microsoft 365 per gli attacchi Denial of Service
ms.author: robmazz
author: robmazz
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
description: In questo articolo, vengono fornite informazioni su come Microsoft difende i propri servizi cloud in base agli attacchi DoS (Denial of Service).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 21b38950ec06874f8c1d959eeb6a8b60179636e3
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332497"
---
# <a name="defending-microsoft-365-cloud-services-against-denial-of-service-attacks"></a>Difesa dei servizi cloud di Microsoft 365 per gli attacchi Denial of Service

I datacenter Microsoft sono protetti da una sicurezza di difesa approfondita che include recinzioni perimetrali, telecamere, personale di sicurezza e accessi sicuri che utilizzano la biometria, la smartcard e l'autenticazione a più fattori. La sicurezza della difesa in profondità continua attraverso tutte le aree della struttura e di ogni unità server fisica. Il [gruppo Infrastructure and Operations di Microsoft Cloud](https://www.microsoft.com/cloud-platform/global-datacenters) fornisce l'infrastruttura di base e le tecnologie fondamentali per i servizi cloud. I datacenter sono conformi agli standard del settore per la sicurezza fisica e l'affidabilità e sono gestiti, monitorati e amministrati dal personale Microsoft Operations.

Per proteggere ulteriormente i servizi cloud, Microsoft fornisce un sistema di difesa DDoS che fa parte del monitoraggio continuo di Microsoft Azure e dei processi di test di penetrazione. Il sistema di difesa DDoS di Azure è stato creato non solo per resistere agli attacchi dall'esterno, ma anche da altri tenant di Azure. Azure utilizza tecniche di rilevamento e attenuazione standard, ad esempio i cookie SYN, la limitazione della velocità e i limiti di connessione per la protezione da attacchi DDoS.

I servizi cloud di Microsoft sono soggetti alla minaccia di attacchi provenienti da più origini. Per attenuare e proteggere le varie minacce DoS, sono stati sviluppati e implementati un sistema di prevenzione e rilevamento delle minacce basato su Azure estremamente scalabile e dinamico con l'obiettivo primario di proteggere l'infrastruttura sottostante dagli attacchi DoS e di evitare interruzioni del servizio per i clienti dei servizi cloud. Il sistema di attenuazione di Azure DoS protegge il traffico in ingresso, in uscita e tra aree geografiche.

La maggior parte degli attacchi DoS è stata avviata contro gli obiettivi dei layer Network (L3) e Transport (L4) del modello OSI ( [Open Systems Interconnection](https://docs.microsoft.com/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model) ). Gli attacchi diretti ai layer L3 e L4 sono stati studiati per inondare un'interfaccia o un servizio di rete con traffico di attacco per sopraffare le risorse e negare la possibilità di rispondere al traffico legittimo. In particolare, gli attacchi L3 e L4 tentano di saturare la capacità dei collegamenti di rete, i dispositivi o i servizi o sopraffare le CPU dei server o delle macchine virtuali che supportano un'applicazione.

Per evitare attacchi L3 e L4, Microsoft ha progettato, sviluppato e distribuito una soluzione mirata in modo specifico alla salvaguardia dell'infrastruttura e degli obiettivi del cliente che vengono attaccati proteggendo questi layer. La protezione dell'infrastruttura garantisce che il traffico di attacco previsto per un cliente non provochi danni collaterali o la qualità del servizio di rete ridotta per gli altri clienti. La soluzione utilizza i dati di campionamento del traffico dai router dei datacenter. Questi dati vengono analizzati da un servizio di monitoraggio della rete per rilevare gli attacchi. Quando viene rilevato un attacco, i meccanismi di difesa automatici interromperanno.

## <a name="application-level-defenses"></a>Difese a livello di applicazione
I team di Microsoft Engineering seguono gli standard rigorosi stabiliti da [Microsoft Operational Security Assurance](https://www.microsoft.com/SDL/OperationalSecurityAssurance) per garantire la protezione dei dati del cliente. I servizi cloud di Microsoft sono creati intenzionalmente per supportare un carico molto elevato, nonché per proteggere e mitigare gli attacchi DoS a livello di applicazione. È stata implementata un'architettura con scalabilità orizzontale, in cui i servizi vengono distribuiti in più centri dati globali con caratteristiche di isolamento e limitazione regionali in alcuni dei carichi di lavoro.

Ogni paese o area geografica del cliente, che l'amministratore del cliente identifica durante la configurazione iniziale dei servizi, determina la posizione di archiviazione principale per i dati del cliente. I dati dei clienti vengono replicati tra i datacenter ridondanti in base a una strategia di backup o primario. Un datacenter principale ospita il software dell'applicazione insieme a tutti i dati principali del cliente in esecuzione nel software. Un datacenter di backup fornisce il failover automatico. Se il data center principale cessa di funzionare per qualsiasi motivo, le richieste vengono reindirizzate alla copia dei dati del software e dei clienti nel datacenter di backup. In qualsiasi momento, i dati dei clienti possono essere elaborati sia nel datacenter primario che in quello di backup. La distribuzione di dati in più datacenter riduce la superficie in questione nel caso in cui un datacenter venga attaccato. Inoltre, i servizi nel datacenter coinvolto possono essere rapidamente reindirizzati al datacenter secondario come uno dei meccanismi di ripristino e viceversa (reindirizzati al datacenter principale dopo il ripristino del servizio).

I singoli carichi di lavoro includono funzionalità predefinite che gestiscono l'utilizzo delle risorse. Ad esempio, i meccanismi di limitazione di Exchange Online e SharePoint Online fanno parte di un approccio a più livelli per la difesa dagli attacchi DoS. La limitazione per gli utenti di Exchange Online si basa sul livello di risorse utilizzato dall'utente finale, se le risorse sono in Active Directory, nell'archivio informazioni di Exchange Online o altrove. Un budget viene assegnato a ogni client per limitare le risorse utilizzate da un utente. La limitazione di Exchange Online per l'attività degli utenti e i componenti di sistema si basa sulla [gestione del carico di lavoro](https://technet.microsoft.com/library/jj150503(v=exchg.150).aspx). Un carico di lavoro di Exchange Online è una funzionalità, un protocollo o un servizio di Exchange Online definito in modo esplicito ai fini della gestione delle risorse di sistema di Exchange Online. Ogni carico di lavoro di Exchange Online richiede risorse di sistema quali CPU, operazioni del database delle cassette postali o richieste di Active Directory per eseguire le richieste degli utenti o i lavori in background. Tra gli esempi di carichi di lavoro di Exchange Online sono inclusi Outlook sul Web, Exchange ActiveSync, la migrazione delle cassette postali e gli assistenti cassette postali. Gli amministratori tenant possono gestire le impostazioni di limitazione delle richieste di gestione dei carichi di lavoro di Exchange per gli utenti con Exchange Management Shell. Esistono varie forme di limitazione che sono state implementate all'interno di Exchange Online, tra cui PowerShell, servizi Web Exchange, POP e IMAP, Exchange ActiveSync, connessioni a dispositivi mobili, destinatari e altro ancora. Mentre gli amministratori delle distribuzioni di Exchange locali possono configurare i criteri di limitazione, gli amministratori non sono in grado di configurare i criteri di limitazione per Exchange Online.

Il trigger più comune per la limitazione in SharePoint Online è il codice CSOM (Client-Side Object Model) che esegue troppe operazioni a una frequenza troppo elevata. Con CSOM, è possibile eseguire molte azioni con una singola richiesta, che può superare i limiti di utilizzo e causare la limitazione per utente.

Indipendentemente dall'attività che potrebbe comportare la limitazione, quando un utente supera i limiti di utilizzo, in SharePoint Online la limitazione di eventuali ulteriori richieste da tale account utente, in genere per un breve periodo di tempo. Quando una limitazione dell'utente è attiva, tutte le azioni dell'utente vengono limitate fino alla scadenza del throttle, in base ai criteri seguenti:
- Per le richieste eseguite direttamente dall'utente in un browser, SharePoint Online reindirizza a una pagina di limitazione delle informazioni e le richieste hanno esito negativo.
- Per tutte le altre richieste, incluse le chiamate CSOM, SharePoint Online restituisce il codice di stato HTTP 429 ("troppe richieste") e le richieste hanno esito negativo.

Se il processo offensivo continua a superare i limiti di utilizzo, SharePoint Online può bloccare completamente il processo e restituire il codice di stato HTTP 503 ("servizio non disponibile").

## <a name="vulnerability-and-penetration-testing"></a>Verifica della vulnerabilità e della penetrazione
Microsoft utilizza molte [tecnologie e procedure di sicurezza](https://www.microsoft.com/trustcenter/security/threatmanagement) per [proteggere la propria infrastruttura cloud](https://blogs.technet.microsoft.com/hybridcloud/2015/05/05/protecting-your-datacenter-and-cloud-from-emerging-threats/) e le reti locali dalle minacce moderne e sofisticate, tra cui l'utilizzo di componenti e servizi antimalware per i servizi cloud, le macchine virtuali (VM) e altri sistemi. Advanced Threat Analytics, che monitora i normali modelli di utilizzo di reti, sistemi e utenti, e utilizza l'apprendimento automatico per contrassegnare qualsiasi comportamento fuori dal normale e regolare test di penetrazione.

Oltre a eseguire i propri test di penetrazione e ad offrire ai clienti un [programma di test di penetrazione Microsoft Cloud Unified](https://technet.microsoft.com/mt784683), è inoltre necessario collaborare con professionisti della sicurezza di terze parti che eseguono valutazioni periodiche della vulnerabilità e test di penetrazione nei servizi cloud. I report vengono apportati dalle valutazioni della vulnerabilità di terze parti disponibili per il download dal [servizio di attendibilità](https://aka.ms/STP) dei servizi e dalle porte di [garanzia del servizio](https://aka.ms/ServiceAssurance) .
