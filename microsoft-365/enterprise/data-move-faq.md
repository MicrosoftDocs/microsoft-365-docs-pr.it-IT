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
description: Risposte alle domande frequenti sullo spostamento dei dati di base in un nuovo data center Office 365 geo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 46dfdddc50c62970b679a130b3cccf692648cd5c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52298053"
---
# <a name="data-move-general-faq"></a>Domande frequenti sullo spostamento dati

Ecco le risposte alle domande generali sullo spostamento dei dati principali dei clienti a riposo in un nuovo datacenter geografico.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>Quali clienti sono idonei a richiedere uno spostamento?
  
I Microsoft 365 commerciali che hanno selezionato un paese idoneo per il nuovo data center geo potranno richiedere uno spostamento. Il programma esiste solo per i tenant con un codice paese idoneo assegnato al tenant di Microsoft 365 per eseguire la migrazione dei dati principali dei clienti in pausa per i carichi di lavoro idonei alla posizione geografica del datacenter Microsoft 365 corrispondente. Fai riferimento alla [pagina Come richiedere lo spostamento dei dati](request-your-data-move.md) per confermare l'idoneità del paese.   

## <a name="how-do-we-define-core-customer-data"></a>Come definire i dati di base dei clienti?
 
Dati di base dei clienti è un termine che si riferisce a un sottoinsieme di dati dei clienti definiti nei [termini Microsoft Online Services:](https://aka.ms/ost) 
- Exchange Online della cassetta postale (corpo della posta elettronica, voci del calendario e contenuto degli allegati di posta elettronica)
- SharePoint Contenuto del sito online e file archiviati in tale sito
- File caricati in OneDrive for Business 

## <a name="what-is-in-scope-for-teams-migration"></a>Qual è l'ambito della Teams migrazione?

Oltre a Exchange Online, SharePoint Online e OneDrive for Business; Microsoft eseguirà la migrazione Teams dati nel datacenter locale. 
- Teams messaggi di chat, inclusi i messaggi privati e i messaggi di canale. 
- Teams immagini usate nelle chat. 

Teams file vengono archiviati in SharePoint Online e Teams file di chat vengono archiviati in OneDrive for Business. La segreteria telefonica, il calendario e i contatti vengono archiviati in Exchange Online. In molti casi, Exchange Online, SharePoint Online e OneDrive for Business sono già utilizzati dal cliente nel centro dati geografico locale e fanno parte del programma di migrazione di Microsoft 365 per i paesi dei clienti idonei.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>A che punto è stata completata la migrazione in modo che i dati dei clienti principali del tenant vengano archiviati a riposo nella nuova posizione geografica?

A causa delle dipendenze condivise tra Exchange Online e SharePoint Online/OneDrive for Business, qualsiasi migrazione non può essere considerata completata finché non viene eseguita la migrazione di entrambi i servizi. Exchange Online e SharePoint Online/OneDrive for Business spesso migrano in momenti separati e in modo indipendente l'uno dall'altro. Gli amministratori tenant dei clienti ricevono una conferma nel Centro messaggi al termine di ogni migrazione del servizio e possono visualizzare la scheda percorso dati nell'interfaccia di amministrazione in qualsiasi momento per confermare i dati di base del cliente in posizione di riposo per ogni servizio.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>Come verificare che i dati dei clienti siano al sicuro durante lo spostamento e che non si verifichino tempi di inattività?
  
Gli spostamenti di dati sono un'operazione di servizio back-end con un impatto minimo per gli utenti finali. Le funzionalità che possono essere influenzate sono elencate in [Durante e dopo lo spostamento dei dati.](during-and-after-your-data-move.md) Aderiamo al [contratto Microsoft Online Services service level agreement (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) per la disponibilità, quindi non è necessario che i clienti si preparino o monitorino durante lo spostamento. 
  
Tutti Microsoft 365 eseguono le stesse versioni nei datacenter, in modo da essere certi di funzionalità coerenti. Il servizio è completamente supportato durante tutto il processo.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>Qual è l'impatto di avere servizi diversi situati in aree geografiche diverse?

Alcuni dei servizi Microsoft 365 possono trovarsi in aree geografiche diverse per alcuni clienti esistenti e per i clienti che si trovano nel mezzo del processo di spostamento. I nostri servizi vengono eseguiti in modo indipendente l'uno dall'altro e non hanno alcun impatto sull'esperienza utente in questo caso. Tuttavia, ai fini della residenza dei dati, una migrazione tenant non può essere considerata completa finché non viene eseguita la migrazione di Exchange Online e SharePoint Online/OneDrive for Business nello stesso data center geografico.

 ## <a name="where-is-my-core-customer-data-located"></a>Dove si trovano i dati principali dei clienti?

Gli amministratori tenant dei clienti possono visualizzare la scheda percorso dati nell'interfaccia di amministrazione in qualsiasi momento per confermare i dati principali dei clienti in posizione di riposo per ogni servizio, in particolare per il tenant.  Microsoft pubblica anche la posizione dei dati geografici, dei data center e della posizione dei dati dei clienti di Office 365 nelle mappe dei datacenter interattivi di [Microsoft 365 come](https://office.com/datamaps) riferimento per i dati correnti dei clienti di base in posizioni di riposo per i nuovi tenant. Puoi verificare la posizione dei dati dei clienti in pausa tramite la sezione Posizione dati sotto il profilo dell'organizzazione nell'interfaccia di amministrazione Microsoft 365 aziendale.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>Quando sarà possibile richiedere uno spostamento?
  
Fai riferimento alla pagina [Come richiedere lo](request-your-data-move.md) spostamento dei dati per i tempi supportati per il tuo datacenter geo.
  
## <a name="how-can-i-request-to-be-moved"></a>Come posso richiedere di essere spostato?
  
I clienti idonei visualizzano una pagina [nell'Microsoft 365 di amministrazione.](https://admin.microsoft.com/) Per istruzioni [su come richiedere uno spostamento,](request-your-data-move.md) vedere Come richiedere lo spostamento dei dati. 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>È possibile modificare la selezione dopo aver richiesto uno spostamento?
  
Non è possibile rimuovere l'utente dal processo dopo l'invio della richiesta.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>Cosa succede se non si richiede uno spostamento prima della scadenza?
  
Non è possibile accettare richieste di migrazione dopo il periodo di registrazione aperto.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>Cosa succede se si desidera spostare i dati per ottenere prestazioni di rete migliori?
  
La prossimità fisica a un Microsoft 365 datacenter non è una garanzia per prestazioni di rete migliori. Esistono molti fattori e componenti che influiscono sulle prestazioni di rete tra l'utente finale e il Microsoft 365 servizio. Per ulteriori informazioni su questa e sull'ottimizzazione delle prestazioni, vedere Pianificazione della rete e [ottimizzazione delle](network-planning-and-performance.md)prestazioni per Microsoft 365 .
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>Tutti i servizi spostano i dati nello stesso giorno?
 
Ogni servizio si sposta in modo indipendente e probabilmente sposta i dati in momenti diversi.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>È possibile scegliere quando spostare i dati?
 
I clienti non sono in grado di selezionare una data specifica, non possono ritardare lo spostamento e non possiamo condividere una data o un intervallo di tempo specifico per gli spostamenti.
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>È possibile condividere quando i dati verranno spostati?
  
Gli spostamenti di dati sono un'operazione back-end con un impatto minimo per gli utenti finali. La complessità, la precisione e la scala con cui è necessario eseguire gli spostamenti di dati all'interno di un ambiente gestito a livello globale e automatizzato ci impediscono di condividere quando è previsto il completamento di uno spostamento di dati per il tenant o qualsiasi altro tenant singolo. I clienti riceveranno una conferma nel Centro messaggi per ogni servizio partecipante al termine del relativo spostamento dei dati. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>Cosa succede se gli utenti accedono ai servizi durante lo spostamento dei dati?

Vedere [Durante e dopo lo](during-and-after-your-data-move.md) spostamento dei dati per un elenco completo delle funzionalità che potrebbero essere limitate durante lo spostamento di parti dei dati per ogni servizio. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>Come è possibile sapere se lo spostamento è stato completato?
  
Controllare il Microsoft 365 messaggio per confermare che lo spostamento dei dati di ogni servizio è stato completato. Quando i dati di ogni servizio vengono spostati, verrà pubblicato un avviso di completamento in modo da ottenere tre avvisi di completamento: uno per Exchange Online, SharePoint Online e Skype for Business Online. Puoi anche verificare la posizione dei dati dei clienti in pausa tramite la sezione Posizione dati sotto il profilo dell'organizzazione nell'interfaccia di amministrazione Microsoft 365 aziendale.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Sono un cliente Microsoft 365 in una delle nuove aree geografiche del datacenter, ma quando ho effettuato l'accesso, ho selezionato un altro paese. Come posso essere spostato nel nuovo datacenter geo?

Non è possibile modificare il paese di iscrizione associato al tenant. È invece necessario creare un nuovo tenant Microsoft 365 con una nuova sottoscrizione e spostare manualmente gli utenti e i dati nel nuovo tenant.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Cosa succede se è in corso la migrazione dei dati di posta elettronica a Microsoft 365 durante lo Exchange Online spostamento?

Si tratta di uno scenario molto comune ed è completamente supportato.  La migrazione cloud tra i dati geografici del datacenter non interferisce con le migrazioni delle cassette postali locali a cloud.
  
 ## <a name="can-i-pilot-some-users"></a>Posso pilotare alcuni utenti?
  
È possibile creare un tenant di prova separato per testare la connettività, ma il tenant di valutazione non può essere combinato in alcun modo con il tenant esistente.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Non voglio aspettare che Microsoft sposti i miei dati. Posso creare un nuovo tenant e spostarmi?
  
Sì, tuttavia, il processo non sarà così semplice come se Microsoft eseguiva lo spostamento dei dati.
  
Se si crea un nuovo tenant dopo la disponibilità del nuovo datacenter geo, il nuovo tenant verrà ospitato nella nuova posizione geografica. Questo nuovo tenant è completamente separato dal tenant precedente ed è responsabile dello spostamento di tutte le cassette postali degli utenti, del contenuto del sito, dei nomi di dominio e di qualsiasi altro dato. Si noti che non è possibile spostare il nome del tenant da un tenant a un altro. Ti consigliamo di attendere il programma di spostamento fornito da Microsoft perché ci occuperemo dello spostamento di tutte le impostazioni, i dati e le sottoscrizioni per gli utenti.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>I dati dei clienti sono già stati spostati in un nuovo data center geo. Posso tornare indietro?
 
No, non è possibile. I clienti che sono stati spostati in nuovi datacenter geografici non possono essere spostati di nuovo. I clienti di qualsiasi area geografica sperimenteranno la stessa qualità del servizio, delle prestazioni e dei controlli di sicurezza che hai fatto in precedenza. [Microsoft 365 Multi Geo](https://aka.ms/multi-geo) è disponibile per alcuni clienti come componente aggiuntivo e consente a un singolo tenant di creare più geo satellite e spostare i dati utente in tali geo con impegni di residenza dei dati.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>I Microsoft 365 tenant ospitati nei nuovi data center saranno disponibili per gli utenti esterni al paese?
  
Sì. Microsoft gestisce una rete globale di grandi dimensioni con connessioni Internet pubbliche in più di 130 posizioni in 35 paesi in tutto il mondo con contratti di peering con più di 2.700 provider di servizi Internet (ISP). Gli utenti saranno in grado di accedere ai datacenter ovunque si trovano su Internet.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Il tenant ha configurato [il componente aggiuntivo Multi Geo.](https://aka.ms/multi-geo) Posso ancora iscrivermi al tenant nel programma Microsoft 365 Move per modificare la posizione geografica predefinita e spostare qualsiasi utente non in un'area satellite nella nuova area geografica predefinita?

Sì, il tenant è idoneo per la registrazione, ma esistono considerazioni significative perché lo spostamento a livello di tenant non è completamente supportato per i clienti che hanno configurato Multi-Geo.

SharePoint Online e OneDrive for Business non possono eseguire la migrazione al nuovo datacenter geo a livello di tenant tramite questo programma. L'amministratore del cliente può configurare le condivisioni di OneDrive for Business per lo spostamento in qualsiasi area geografica disponibile tramite Multi-Geo, ma la posizione predefinita per il tenant non può essere modificata dopo la configurazione di Multi-Geo per un tenant.

Per i clienti che acconsentino esplicitamente alla migrazione, verranno spostate tutte le cassette postali di Exchange Online dalla posizione geografica predefinita corrente alla nuova area geografica del datacenter locale e verrà aggiornato l'area geografica Exchange Online predefinita. Non verranno spostate cassette postali EXO configurate in aree satellite Multi Geo per continuare a rispettare la residenza dei dati dell'area satellite come previsto. 

## <a name="related-topics"></a>Argomenti correlati

[Spostamento di dati di base in Microsoft 365 geo del datacenter](moving-data-to-new-datacenter-geos.md)

[Come richiedere lo spostamento dati](request-your-data-move.md)

[Microsoft 365 Multi Geo](https://aka.ms/multi-geo)

[Microsoft 365 datacenter interattivo](https://office.com/datamaps)

[Microsoft 365 Supporto](../business-video/get-help-support.md)

[Nuovi geo datacenter per Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Servizi di Azure per area geografica](https://azure.microsoft.com/regions/)