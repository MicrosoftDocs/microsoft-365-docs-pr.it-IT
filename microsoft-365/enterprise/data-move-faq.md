---
title: Domande frequenti sullo spostamento dati
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: Trovare le risposte alle domande frequenti sullo spostamento dei dati di base in una nuova area geografica del datacenter di Office 365.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7e59622e35604ebd9befbbe17a8a125ed15e101
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094656"
---
# <a name="data-move-general-faq"></a>Domande frequenti sullo spostamento dati

Ecco le risposte alle domande generali sullo spostamento dei dati di base dei clienti in un nuovo data center geografico.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Quali clienti sono idonei a richiedere un trasferimento?
  
I clienti commerciali di Microsoft 365 esistenti che hanno selezionato un paese idoneo per il nuovo data center geografico potranno richiedere uno spostamento. Il programma esiste solo per i tenant con un codice paese idoneo assegnato al tenant di Microsoft 365 per eseguire la migrazione dei dati principali dei clienti in pausa per i carichi di lavoro idonei alla posizione geografica del datacenter di Microsoft 365 corrispondente. Fare riferimento alla pagina [Come richiedere lo spostamento dei](request-your-data-move.md) dati per confermare l'idoneità del paese.   

## <a name="how-do-we-define-core-customer-data"></a>Come definire i dati di base dei clienti?
 
Dati di base del cliente è un termine che si riferisce a un sottoinsieme di dati del cliente definiti nelle [condizioni Microsoft Online Services:](https://aka.ms/ost) 
- Contenuto della cassetta postale di Exchange Online (corpo della posta elettronica, voci del calendario e contenuto degli allegati di posta elettronica)
- Contenuto del sito di SharePoint Online e file archiviati in tale sito
- File caricati in OneDrive for Business 

## <a name="what-is-in-scope-for-teams-migration"></a>Qual è l'ambito della migrazione di Teams?

Oltre a Exchange Online, SharePoint Online e OneDrive for Business; Microsoft eseguirà la migrazione dei dati di Teams nel datacenter locale. 
- Messaggi di chat di Teams, inclusi messaggi privati e messaggi di canale. 
- Immagini di Teams usate nelle chat. 

I file di Teams sono archiviati in SharePoint Online e i file di chat di Teams sono archiviati in OneDrive for Business. La segreteria telefonica, il calendario e i contatti sono archiviati in Exchange Online. In molti casi, Exchange Online, SharePoint Online e OneDrive for Business sono già usati dal cliente nella posizione geografica del datacenter locale e fanno parte del programma di migrazione di Microsoft 365 per i paesi dei clienti idonei.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>A che punto è stata completata la migrazione in modo che i dati principali dei clienti del tenant vengano archiviati in una nuova posizione geografica?

A causa delle dipendenze condivise tra Exchange Online e SharePoint Online/OneDrive for Business, qualsiasi migrazione non può essere considerata completata finché non viene eseguita la migrazione di entrambi i servizi. Exchange Online e SharePoint Online/OneDrive for Business spesso migrano in momenti separati e in modo indipendente l'uno dall'altro. Gli amministratori tenant dei clienti ricevono una conferma nel Centro messaggi al termine di ogni migrazione del servizio e possono visualizzare la scheda della posizione dati nell'interfaccia di amministrazione in qualsiasi momento per confermare i dati di base del cliente nella posizione di riposo per ogni servizio.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Come verificare che i dati dei clienti siano sicuri durante lo spostamento e che non si verifichino tempi di inattività?
  
Gli spostamenti di dati sono un'operazione di servizio back-end con un impatto minimo sugli utenti finali. Le funzionalità che possono essere influenzate sono elencate in [Durante e dopo lo spostamento dei dati.](during-and-after-your-data-move.md) Aderiamo al [contratto Microsoft Online Services service level agreement (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) per la disponibilità, quindi non c'è nulla che i clienti devono preparare o monitorare durante il trasferimento. 
  
Tutti i servizi di Microsoft 365 eseguono le stesse versioni nei datacenter, in modo da essere certi di funzionalità coerenti. Il servizio è completamente supportato durante tutto il processo.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Qual è l'impatto della presenza di servizi diversi in aree geografiche diverse?

Alcuni dei servizi di Microsoft 365 possono trovarsi in aree geografiche diverse per alcuni clienti esistenti e per i clienti che si trovano nel corso del processo di spostamento. I servizi vengono eseguiti in modo indipendente l'uno dall'altro e, in questo caso, non influiscono sull'esperienza utente. Tuttavia, ai fini della residenza dei dati, una migrazione del tenant non può essere considerata completa finché non viene eseguita la migrazione di Exchange Online e SharePoint Online/OneDrive for Business nello stesso data center geografico.

 ## <a name="where-is-my-core-customer-data-located"></a>Dove si trovano i dati principali dei clienti?

Gli amministratori tenant dei clienti possono visualizzare la scheda della posizione dati nell'interfaccia di amministrazione in qualsiasi momento per confermare i dati principali dei clienti nella posizione di riposo per ogni servizio, in particolare per il tenant.  Microsoft pubblica anche la posizione di aree geografiche, datacenter e posizione dei dati dei clienti di Office 365 nelle mappe dei datacenter interattivi di [Microsoft 365 ](https://office.com/datamaps) come riferimento per i dati correnti dei clienti di base nelle posizioni di riposo per i nuovi tenant. È possibile verificare la posizione dei dati dei clienti in stato di inquieto tramite la sezione Posizione dati nel profilo dell'organizzazione nell'interfaccia di amministrazione di Microsoft 365.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>Quando sarà possibile richiedere uno spostamento?
  
Fare riferimento alla pagina [Come richiedere lo spostamento dei dati](request-your-data-move.md) per gli intervallo di tempo supportati per la posizione geografica del datacenter.
  
## <a name="how-can-i-request-to-be-moved"></a>Come posso richiedere di essere spostato?
  
I clienti idonei visualizzano una pagina nell'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com/) Per istruzioni [su come richiedere uno spostamento,](request-your-data-move.md) vedere Come richiedere lo spostamento dei dati. 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>È possibile modificare la selezione dopo aver richiesto uno spostamento?
  
Non è possibile rimuovere l'utente dal processo dopo l'invio della richiesta.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>Cosa succede se non si richiede uno spostamento prima della scadenza?
  
Non è possibile accettare richieste di migrazione dopo il periodo di registrazione aperto.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>Cosa succede se si desidera spostare i dati per ottenere prestazioni di rete migliori?
  
La prossimità fisica a un datacenter di Microsoft 365 non è una garanzia per prestazioni di rete migliori. Esistono molti fattori e componenti che influiscono sulle prestazioni di rete tra l'utente finale e il servizio Microsoft 365. Per ulteriori informazioni su questa e sull'ottimizzazione delle prestazioni, vedere Pianificazione della rete e [ottimizzazione delle prestazioni per Microsoft 365.](network-planning-and-performance.md)
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Tutti i servizi spostano i dati nello stesso giorno?
 
Ogni servizio si sposta in modo indipendente e probabilmente sposta i dati in momenti diversi.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>È possibile scegliere quando spostare i dati?
 
I clienti non possono selezionare una data specifica, non possono ritardare lo spostamento e non possiamo condividere una data o un intervallo di tempo specifico per gli spostamenti.
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>È possibile condividere quando i dati verranno spostati?
  
Gli spostamenti di dati sono un'operazione back-end con un impatto minimo sugli utenti finali. La complessità, la precisione e la scala con cui è necessario eseguire spostamenti di dati all'interno di un ambiente gestito a livello globale e automatizzato ci impediscono di condividere quando è previsto il completamento di uno spostamento di dati per il tenant o qualsiasi altro tenant singolo. Al termine del trasferimento dei dati, i clienti riceveranno una conferma nel Centro messaggi per ogni servizio partecipante. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>Cosa succede se gli utenti accedono ai servizi durante lo spostamento dei dati?

Per [un elenco](during-and-after-your-data-move.md) completo delle funzionalità che possono essere limitate durante e dopo lo spostamento dei dati per ogni servizio, vedere Durante e dopo lo spostamento dei dati. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Come è possibile sapere se lo spostamento è stato completato?
  
Controllare il Centro messaggi di Microsoft 365 per confermare che lo spostamento dei dati di ogni servizio è stato completato. Quando i dati di ogni servizio vengono spostati, verrà pubblicato un avviso di completamento per ricevere tre avvisi di completamento: uno per Exchange Online, SharePoint Online e Skype for Business online. È anche possibile verificare la posizione dei dati dei clienti in stato di inquieto tramite la sezione Posizione dati nel profilo dell'organizzazione nell'interfaccia di amministrazione di Microsoft 365.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>I am a Microsoft 365 customer in one of the new datacenter geos, but when I signed up, I selected a different country. Come posso essere spostato nel nuovo datacenter geografico?

Non è possibile modificare il paese di iscrizione associato al tenant. È invece necessario creare un nuovo tenant di Microsoft 365 con un nuovo abbonamento e spostare manualmente gli utenti e i dati nel nuovo tenant.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Cosa succede se è in corso la migrazione dei dati di posta elettronica a Microsoft 365 durante lo spostamento di Exchange Online?

Si tratta di uno scenario molto comune ed è completamente supportato.  La migrazione cloud tra le posizioni geografiche del datacenter non interferisce con le migrazioni delle cassette postali da locale a cloud.
  
 ## <a name="can-i-pilot-some-users"></a>Posso pilotare alcuni utenti?
  
È possibile creare un tenant di prova separato per testare la connettività, ma il tenant di prova non può essere combinato in alcun modo con il tenant esistente.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Non voglio aspettare che Microsoft sposti i miei dati. Posso creare un nuovo tenant e spostarmi?
  
Sì, tuttavia il processo non sarà facile come se Microsoft eseguiva lo spostamento dei dati.
  
Se si crea un nuovo tenant dopo la disponibilità della nuova posizione geografica del datacenter, il nuovo tenant verrà ospitato nella nuova posizione geografica. Questo nuovo tenant è completamente separato dal tenant precedente ed è responsabile dello spostamento di tutte le cassette postali degli utenti, del contenuto del sito, dei nomi di dominio e di tutti gli altri dati. Si noti che non è possibile spostare il nome del tenant da un tenant a un altro. È consigliabile attendere il programma di spostamento fornito da Microsoft, poiché microsoft si occuperà dello spostamento di tutte le impostazioni, i dati e le sottoscrizioni per gli utenti.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>I dati del cliente sono già stati spostati in una nuova posizione geografica del datacenter. Posso tornare indietro?
 
No, non è possibile. I clienti che sono stati spostati in nuovi datacenter geografici non possono essere spostati di nuovo. In qualità di cliente in qualsiasi area geografica, potrai sperimentare la stessa qualità del servizio, le prestazioni e i controlli di sicurezza che hai fatto in precedenza. [Microsoft 365 Multi Geo](https://aka.ms/multi-geo) è disponibile per alcuni clienti come componente aggiuntivo e consente a un singolo tenant di creare più geo satellite e spostare i dati degli utenti in tali geo con impegni di residenza dei dati.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>I tenant di Microsoft 365 ospitati nei nuovi datacenter saranno disponibili per gli utenti esterni al paese?
  
Sì. Microsoft gestisce una rete globale di grandi dimensioni con connessioni Internet pubbliche in più di 130 posizioni in 35 paesi in tutto il mondo con contratti di peering con più di 2.700 provider di servizi Internet (ISP). Gli utenti saranno in grado di accedere ai datacenter ovunque si trovano su Internet.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Il tenant ha configurato [il componente aggiuntivo Multi Geo.](https://aka.ms/multi-geo) Posso comunque iscrivermi al mio tenant nel programma di spostamento di Microsoft 365 per modificare la mia posizione geografica predefinita e spostare qualsiasi utente non in un'area geografica satellite nella nuova area geografica predefinita?

Sì, il tenant è idoneo per la registrazione, ma esistono considerazioni significative perché lo spostamento a livello di tenant non è completamente supportato per i clienti che hanno configurato Multi-Geo.

SharePoint Online e OneDrive for Business non possono eseguire la migrazione alla nuova posizione geografica del datacenter a livello di tenant tramite questo programma. L'amministratore del cliente può configurare le condivisioni di OneDrive for Business in modo che si spostino in qualsiasi area geografica disponibile tramite Multi-Geo, ma la posizione predefinita per il tenant non può essere modificata dopo la configurazione di Multi-Geo per un tenant.

Per i clienti che acconsentino esplicitamente alla migrazione, tutte le cassette postali di Exchange Online verranno spostate dalla posizione geografica predefinita corrente alla nuova area geografica del datacenter locale e verrà aggiornato l'area predefinita di Exchange Online. Non verranno spostate cassette postali EXO configurate in aree satellite Multi Geo per continuare a rispettare la residenza dei dati dell'area satellite come previsto. 

## <a name="related-topics"></a>Argomenti correlati

[Spostamento dei dati di base in nuove posizioni geografiche del datacenter di Microsoft 365](moving-data-to-new-datacenter-geos.md)

[Come richiedere lo spostamento dati](request-your-data-move.md)

[Microsoft 365 Multi Geo](https://aka.ms/multi-geo)

[Mappa del datacenter interattivo di Microsoft 365](https://office.com/datamaps)

[Supporto di Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkID=522459)

[Nuovi centri dati geografici per Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Servizi di Azure per area geografica](https://azure.microsoft.com/regions/)
