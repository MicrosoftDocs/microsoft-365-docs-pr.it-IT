---
title: Domande frequenti sullo spostamento dati
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: Trovare le risposte alle domande frequenti su come spostare i dati di base in un nuovo datacenter geo di Office 365.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77d30778ae11865e5d773be4fa64db9b64480e76
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691325"
---
# <a name="data-move-general-faq"></a>Domande frequenti sullo spostamento dati

Di seguito sono riportate le risposte alle domande generali su come spostare i dati di base in un nuovo datacenter Geo.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Quali clienti sono idonei a richiedere una mossa?
  
I clienti commerciali Microsoft 365 esistenti che hanno selezionato un paese idoneo per il nuovo datacenter Geo potranno richiedere uno spostamento.  Il programma esiste solo per i tenant che dispongono di un codice paese idoneo assegnato al tenant di Microsoft 365 per eseguire la migrazione dei dati del cliente di base a REST per i carichi di lavoro idonei per il datacenter geografico Microsoft 365 corrispondente.  Fare riferimento alla pagina [come richiedere lo spostamento dei dati](request-your-data-move.md) per confermare l'idoneità del paese.   

## <a name="how-do-we-define-core-customer-data"></a>Come definire i dati di base dei clienti
 
I dati dei clienti di base sono un termine che fa riferimento a un sottoinsieme di dati dei clienti definiti nelle [condizioni dei servizi online Microsoft](https://aka.ms/ost): 
- Contenuto delle cassette postali di Exchange Online (corpo del messaggio di posta elettronica, voci del calendario e contenuto degli allegati di posta elettronica)
- Contenuto del sito di SharePoint Online e file archiviati all'interno del sito
- File caricati in OneDrive for business 

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>A che punto viene completata la migrazione in modo che i dati del cliente principale del tenant vengano archiviati a riposo nel nuovo geografico?

A causa delle dipendenze condivise tra Exchange Online e SharePoint Online/OneDrive for business, qualsiasi migrazione non può essere considerata completata finché non vengono migrati entrambi i servizi.  Exchange Online e SharePoint Online/OneDrive for business spesso migrano in momenti separati e indipendentemente gli uni dagli altri.  Gli amministratori dei tenant ricevono la conferma nel centro messaggi quando ogni migrazione del servizio è completata e può visualizzare la scheda percorso dati nell'interfaccia di amministrazione in qualsiasi momento per confermare i dati del cliente di base in posizione Rest per ogni servizio.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>In che modo è possibile verificare che i dati dei clienti siano al sicuro durante lo spostamento e che non si verifichino tempi di inattività?
  
Gli spostamenti di dati rappresentano un'operazione del servizio back-end con un impatto minimo sugli utenti finali. Le caratteristiche che possono essere influenzate sono elencate [durante e dopo lo spostamento dei dati](during-and-after-your-data-move.md). Il contratto di servizio di [Microsoft Online Services (SLA, Service Level Agreement)](https://go.microsoft.com/fwlink/p/?LinkId=523897) per la disponibilità è pertanto insufficiente per consentire ai clienti di prepararsi o monitorarli durante lo spostamento. 
  
Tutti i servizi di Microsoft 365 eseguono le stesse versioni nei data center, pertanto è possibile garantire una funzionalità coerente. Il servizio è supportato completamente nel corso del processo.

## <a name="what-is-in-scope-for-teams-migration"></a>Che cos'è l'ambito per la migrazione dei team?

Oltre a Exchange Online, SharePoint Online e OneDrive for business; Microsoft eseguirà la migrazione dei dati del team nel datacenter locale.  
- Messaggi di chat dei team, inclusi i messaggi privati e i messaggi di canale. 
- Immagini di Team utilizzate nelle chat. 

I file dei team sono archiviati in SharePoint Online e i file chat di team sono archiviati in OneDrive for business.  La segreteria telefonica, il calendario, la cronologia chat e i contatti sono archiviati in Exchange Online.  In molti casi, Exchange Online, SharePoint Online e OneDrive for business sono già utilizzati dal cliente nel centro dati geografico locale e fanno parte del programma di migrazione Microsoft 365 per i paesi idonei ai clienti.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Quali sono le conseguenze dell'utilizzo di servizi diversi in GEOS?

Alcuni dei servizi di Microsoft 365 possono trovarsi in GEOS diversi per alcuni clienti esistenti e per i clienti che si trovano al centro del processo di spostamento. I nostri servizi vengono eseguiti indipendentemente l'uno dall'altro e non vi è alcun impatto sull'esperienza utente, se questo è il caso.Tuttavia, a fini di residenza dei dati, una migrazione tenant non può essere considerata completa finché sia Exchange Online che SharePoint Online/OneDrive for business non verranno migrati nello stesso datacenter Geo.
  
## <a name="will-new-microsoft-365-customers-be-automatically-provisioned-in-the-new-datacenter-geos"></a>I nuovi clienti di Microsoft 365 verranno automaticamente provisionati nel nuovo datacenter GEOS?
  
Sì. Una volta che un nuovo datacenter geografico è disponibile, nuovi clienti Microsoft 365 che selezionano un paese idoneo per il nuovo Geo come paese durante l'iscrizione avranno i dati di base dei clienti archiviati a riposo nel nuovo datacenter Geo.
  
 ## <a name="where-is-my-core-customer-data-located"></a>Dove si trovano i dati dei clienti di base?

Gli amministratori tenant possono visualizzare la scheda percorso dati nell'interfaccia di amministrazione in qualsiasi momento per confermare i dati del cliente di base nel percorso REST per ogni servizio, in particolare per il tenant.Inoltre, viene pubblicata la posizione del centro dati GEOS, dei datacenter e la posizione di Office 365 clienti sui [mapping del datacenter interattivi di office 365 ](https://office.com/datamaps) come riferimento per i dati dei clienti di base predefiniti correnti nelle posizioni REST per i nuovi tenant.  È possibile verificare il percorso dei dati del cliente a riposo tramite la sezione percorso dati sotto il profilo dell'organizzazione nell'interfaccia di amministrazione di Microsoft 365.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>Quando sarà possibile richiedere una mossa?
  
Per ulteriori informazioni, vedere la sezione come richiedere la pagina di [spostamento dei dati](request-your-data-move.md) per i calendari supportati per il datacenter Geo.
  
## <a name="how-can-i-request-to-be-moved"></a>Come si può richiedere di essere spostati?
  
I clienti idonei vedranno una pagina nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/). Per istruzioni su come richiedere uno spostamento, vedere [come richiedere lo spostamento dei dati](request-your-data-move.md) . 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>È possibile modificare la selezione dopo aver richiesto uno spostamento?
  
Non è possibile per noi rimuovere il processo dopo aver inviato la richiesta.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>Cosa succede se non si richiede una mossa prima della scadenza?
  
Potrebbe essere possibile accettare le richieste su base eccezione per concedere al tenant una scadenza impegnata per completare lo spostamento.  Contattare il [supporto tecnico Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkID=522459) per eseguire la richiesta.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>Che cosa fare se si desidera spostare i dati in modo da ottenere prestazioni di rete migliori?
  
La vicinanza fisica a un datacenter Microsoft 365 non garantisce una migliore prestazione di rete. Esistono numerosi fattori e componenti che influiscono sulle prestazioni di rete tra l'utente finale e il servizio Microsoft 365. Per ulteriori informazioni su questo e sull'ottimizzazione delle prestazioni, vedere [pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](network-planning-and-performance.md).
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>I dati vengono spostati nello stesso giorno da tutti i servizi?
 
Ogni servizio viene spostato in modo indipendente e probabilmente sposta i dati in momenti diversi.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>È possibile scegliere quando si desidera spostare i dati?
 
I clienti non sono in grado di selezionare una data specifica, non possono posticiparne lo spostamento e non è possibile condividere una data o un intervallo di tempo specifico per gli spostamenti.
  
 ## <a name="can-you-share-when-my-data-will-be-be-moved"></a>È possibile condividere quando i dati verranno spostati?
  
Gli spostamenti di dati sono un'operazione back-end con un impatto minimo sugli utenti finali. La complessità, la precisione e la scalabilità in cui è necessario eseguire lo spostamento dei dati in un ambiente automatizzato e gestito a livello globale impediscono la condivisione quando si prevede che lo spostamento dei dati venga completato per il tenant o per qualsiasi altro tenant. I clienti riceveranno una conferma nel centro messaggi per ogni servizio di partecipazione quando il relativo spostamento dei dati è stato completato. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>Cosa succede se gli utenti accedono ai servizi durante lo spostamento dei dati?

Vedere [durante e dopo lo spostamento dei dati](during-and-after-your-data-move.md) per un elenco completo delle caratteristiche che possono essere limitate durante le parti dello spostamento dei dati per ogni servizio. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Come si fa a sapere se lo spostamento è stato completato?
  
Controllare il centro messaggi di Microsoft 365 per confermare che lo spostamento dei dati di ogni servizio è stato completato. Quando i dati di ogni servizio vengono spostati, verrà visualizzato un avviso di completamento per ottenere tre notifiche di completamento: una per Exchange Online, SharePoint Online e Skype for business online.  È inoltre possibile verificare il percorso dei dati del cliente a riposo tramite la sezione percorso dati sotto il profilo dell'organizzazione nell'interfaccia di amministrazione di Microsoft 365.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Sono un cliente Microsoft 365 in uno dei nuovi datacenter GEOS, ma al momento dell'iscrizione, ho selezionato un paese diverso. Come si può essere spostati nel nuovo datacenter Geo?

Non è possibile modificare il paese di iscrizione associato al tenant. Al contrario, è necessario creare un nuovo tenant Microsoft 365 con un nuovo abbonamento e spostare manualmente gli utenti e i dati nel nuovo tenant.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Cosa succede se si è in fase di migrazione dei dati di posta elettronica a Microsoft 365 durante lo spostamento di Exchange Online?

Si tratta di uno scenario molto comune ed è completamente supportato.  La migrazione cloud tra i datacenter GEOS non interferisce con le migrazioni delle cassette postali di premisis su cloud.
  
 ## <a name="can-i-pilot-some-users"></a>È possibile pilotare alcuni utenti?
  
È possibile creare un tenant di prova separato per testare la connettività, ma il tenant di prova non può essere combinato in alcun modo con il tenant esistente.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Non si desidera attendere la trasferimento dei dati da Microsoft. È possibile creare un nuovo tenant e spostarmi?
  
Sì, tuttavia, il processo non sarà così semplice come se Microsoft stesse per eseguire lo spostamento dei dati.
  
Se si crea un nuovo tenant dopo che è disponibile il nuovo datacenter Geo, il nuovo tenant sarà ospitato nel nuovo Geo. Questo nuovo tenant è completamente separato dal tenant precedente e sarebbe responsabile dello spostamento di tutte le cassette postali degli utenti, il contenuto del sito, i nomi di dominio e qualsiasi altro dato. Si noti che non è possibile spostare il nome del tenant da un tenant a un altro. È consigliabile attendere il programma di spostamento fornito da Microsoft come si occuperà di spostare tutte le impostazioni, i dati e le sottoscrizioni per gli utenti.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>I dati dei clienti sono già stati spostati in un nuovo datacenter Geo. È possibile spostarsi di nuovo?
 
No, non è possibile. I clienti che sono stati spostati in nuovi datacenter geografici non possono essere spostati indietro. Come cliente in qualsiasi ambiente geografico, si verificherà lo stesso livello di qualità del servizio, delle prestazioni e dei controlli di sicurezza come in precedenza.  [Microsoft 365 multi Geo](https://aka.ms/multi-geo) è disponibile per alcuni clienti come componente aggiuntivo e consente a un singolo tenant di creare più satelliti GEOS e spostare i dati degli utenti in tali GEOS con gli impegni di residenza dei dati.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>Gli inquilini di Microsoft 365 ospitati nei nuovi datacenter saranno disponibili per gli utenti esterni al paese?
  
Sì. Microsoft mantiene una rete globale di grandi dimensioni con connessioni Internet pubbliche in più di 130 posizioni in 35 paesi di tutto il mondo con contratti di peering con più di 2.700 provider di servizi Internet (ISP). Gli utenti saranno in grado di accedere ai Data Center ovunque si trovino su Internet.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Il tenant ha configurato il [componente aggiuntivo multi Geo](https://aka.ms/multi-geo). È possibile continuare a iscriversi al tenant nel programma Microsoft 365 Move per modificare il mio account geografico predefinito e spostare tutti gli utenti non presenti in un'area satellite nel nuovo geografico predefinito?

Sì, il tenant è idoneo per la registrazione. Sposteremo tutte le cassette postali EXO dall'attuale Geo predefinito al nuovo Data Center geografico locale.  Non verranno spostate le cassette postali EXO configurate nelle diverse aree geografiche satelliti per continuare a rispettare la residenza dei dati delle aree satellite come previsto.  

SharePoint Online e OneDrive for business non possono eseguire la migrazione al nuovo datacenter Geo come parte del programma Move, anche se è possibile configurare le condivisioni di OneDrive for business per spostarsi in qualsiasi area desiderata tramite il programma multi Geo.

## <a name="related-topics"></a>Argomenti correlati

[Spostamento dei dati di base in un nuovo datacenter di Microsoft 365 GEOS](moving-data-to-new-datacenter-geos.md)

[Come richiedere lo spostamento dati](request-your-data-move.md)

[Microsoft 365 multi Geo](https://aka.ms/multi-geo)

[Mappa del centro dati interattivo Microsoft 365](https://office.com/datamaps)

[Supporto di Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkID=522459)

[Nuovo datacenter GEOS per Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Servizi di Azure in base all'area geografica](https://azure.microsoft.com/regions/)
