---
title: Panoramica su Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/31/2019
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Exchange Online Protection (EOP) è un servizio di filtro della posta elettronica che aiuta l'organizzazione a proteggersi da spam e malware e include funzionalità in grado di tutelare l'organizzazione dalle violazioni dei criteri di messaggistica.
ms.openlocfilehash: fc744d09711b65e3951408741ea1952d2d73614c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083492"
---
# <a name="exchange-online-protection-overview"></a>Panoramica su Exchange Online Protection

Microsoft Exchange Online Protection (EOP) è un servizio di filtro della posta elettronica che aiuta l'organizzazione a proteggersi da spam e malware e include funzionalità in grado di tutelare l'organizzazione dalle violazioni dei criteri di messaggistica. EOP è in grado di semplificare la gestione dell'ambiente di messaggistica e ridurre molte delle responsabilità associate alla gestione di componenti hardware e software locali.
  
Di seguito sono riportati i modi principali in cui è possibile utilizzare EOP per la protezione dei messaggi:
  
- **In uno scenario autonomo** EOP fornisce la protezione della posta elettronica basata sul cloud per l'ambiente di Microsoft Exchange Server 2013 locale, le versioni legacy di Exchange Server o per qualsiasi altra soluzione di posta elettronica SMTP locale. 
    
- **Come parte di Microsoft Exchange Online** Per impostazioni predefinita, EOP protegge le cassette postali di Microsoft Exchange Online ospitate nel cloud. Vedere [Protect Against Threats](protect-against-threats.md) for help configuring these Exchange Online capabilities. 
    
- **In una distribuzione ibrida** EOP può essere configurato in modo da proteggere l'ambiente di messaggistica e controllare il routing della posta quando si utilizza una combinazione di cassette postali locali e basate sul cloud. 

Gli articoli di Exchange Online Protection sono validi per gli ambienti ibridi e locali. 
    
## <a name="how-eop-works"></a>Come funziona EOP

Per capire come funziona EOP, aiuta osservare il modo in cui elabora la posta in arrivo:

![Diagramma del processo di posta elettronica.](../media/GitHubBugs/emailprocessingineop1.png)
  
Un messaggio in arrivo passa inizialmente tramite il filtro connessioni, che controlla la reputazione del mittente e controlla il messaggio per il malware. La maggior parte della posta indesiderata viene interrotta a questo punto e viene eliminata da EOP. I messaggi continuano tramite il filtro dei criteri, in cui i messaggi vengono valutati in base alle regole del flusso di posta personalizzate (note anche come regole di trasporto) create o applicate da un modello. Ad esempio, è possibile disporre di una regola che invia una notifica a un responsabile quando la posta arriva da un mittente specifico. (I controlli di prevenzione della perdita di dati si verificano anche a questo punto, se si dispone di tale caratteristica, vedere la [Descrizione del servizio Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=320619)). Successivamente, i messaggi passano attraverso il filtro contenuto, in cui il contenuto viene controllato per la terminologia o le proprietà comuni alla posta indesiderata. Un messaggio determinato come posta indesiderata dal filtro contenuto può essere inviato alla cartella posta indesiderata di un utente o alla quarantena, tra le altre opzioni (inclusa la posta in arrivo o la cartella personalizzata), in base alle impostazioni. Dopo che un messaggio ha superato tutti questi livelli di protezione, viene recapitato al destinatario.
  
### <a name="eop-datacenters"></a>Datacenter EOP

EOP viene eseguito in una rete globale di centri dati progettati per offrire la massima disponibilità. Ad esempio, se un datacenter non è disponibile, i messaggi di posta elettronica vengono automaticamente instradati a un altro datacenter senza interruzione del servizio. I server in ogni centro dati accettano messaggi per conto dell'utente, offrendo un livello di separazione tra l'organizzazione e Internet, riducendo in questo modo il carico sui server. Attraverso questa rete altamente disponibile, Microsoft può garantire che la posta elettronica raggiunga l'organizzazione in modo tempestivo. 
  
EOP esegue il bilanciamento del carico tra i datacenter ma solo all'intero di un'area geografica. In caso di provisioning in un'unica area geografica, tutti i messaggi saranno elaborati utilizzando il routing della posta per tale area geografica. L'elenco seguente mostra il modo in cui funziona il routing della posta regionale per i datacenter EOP:
  
    
- In Europa, Medio Oriente e Africa (EMEA), tutte le cassette postali di Exchange Online si trovano in datacenter situati in EMEA e tutti i messaggi vengono instradati tramite datacenter in EMEA per il filtraggio EOP.
    
- In Asia-Pacifico (APAC), tutte le cassette postali di Exchange Online si trovano in datacenter APAC e i messaggi sono attualmente instradati attraverso i datacenter di APAC per il filtro EOP.

- Nelle Americhe, tutte le cassette postali di Exchange Online si trovano nei data center degli Stati Uniti, ad eccezione del Sud America, in cui vengono utilizzati i datacenter in Brasile e Cile e in Canada, in cui vengono utilizzati i datacenter in Canada. Tutti i messaggi di posta elettronica, inclusi i messaggi per i clienti del Sud America e del Canada, vengono instradati tramite datacenter locali per il filtro EOP; la posta elettronica di Quaratined viene archiviata nel centro dati in cui si trova il tenant.
    
- Per GCC (Government Community Cloud) tutte le cassette postali di Exchange Online si trovano in datacenter degli Stati Uniti e tutti i messaggi vengono instradati tramite datacenter statunitensi per il filtraggio EOP.
    
## <a name="eop-plans-and-features"></a>Piani e funzionalità di EOP

I piani di sottoscrizione EOP disponibili sono:
  
- **EOP autonomo** EOP protegge le cassette di posta locali. 
    
- **Funzionalità di EOP in Exchange Online** EOP protegge le cassette postali di Exchange Online ospitate nel cloud. 
    
- **CAL di Exchange Enterprise con Services** Protegge le cassette postali locali, come EOP autonomo, e include le funzionalità di prevenzione della perdita di dati (DLP) e di segnalazione tramite servizi Web. 
    
Per ulteriori informazioni sui requisiti, i limiti importanti e le funzionalità disponibili in tutti i piani di sottoscrizione EOP; vedere [Descrizione del servizio Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=320619).
  
## <a name="setting-up-eop"></a>Configurare EOP

La configurazione di EOP può essere semplice, specialmente nel caso di una piccola organizzazione con poche regole di conformità. Tuttavia, se si ha una grande organizzazione con più domini, regole di conformità personalizzate o flusso di posta ibrido, la configurazione può richiedere più pianificazione e tempo.
  
Se EOP è già stato acquistato, vedere [Installazione del servizio EOP](set-up-your-eop-service.md) per assicurarsi di completare tutti i passaggi necessari per configurare EOP per proteggere l'ambiente di messaggistica. 
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Funzionalità di EOP](eop-features.md)
  
[Domande frequenti generali su EOP](eop-general-faq.md)
  
[Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP](eop-queued-deferred-and-bounced-messages-faq.md)
  
[Domande frequenti sull'amministrazione con delega](delegated-administration-faq.md)
  
[Spostare i domini e le impostazioni da un'organizzazione di EOP a un'altra organizzazione di EOP](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  

