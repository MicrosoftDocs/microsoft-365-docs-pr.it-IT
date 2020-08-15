---
title: Guida sulla fine del supporto di SharePoint Server 2007
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/28/2019
audience: ITPro
ms.topic: conceptual
f1.keywords:
- CSH
ms.custom:
- vsemail
- MS_WSS_DirectoryManagement
- MS_WSS_ConfigEmail
- globalemailconfig
- configssc
- AppDefToBDC
- seo-marvel-apr2020
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- OFU120
- SPS150
- OSU140
- WSU120
- OSR120
- SPO160
- PJW120
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: ba124775-d5c0-4d68-b88d-8458ad4c3717
description: Il 10 ottobre 2017 è stato terminato il supporto per SharePoint Server 2007. In questo articolo vengono fornite informazioni relative all'aggiornamento, alla migrazione e alle opzioni di supporto.
ms.openlocfilehash: c89f150618150e352de476e0a0982fd2d98348e2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691508"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Guida sulla fine del supporto di SharePoint Server 2007

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Il **10 ottobre 2017**, Microsoft Office SharePoint Server 2007 ha raggiunto la fine del supporto. Se non è stata avviata la migrazione da SharePoint Server 2007 a Microsoft 365 o una versione più recente di SharePoint Server locale, ora è il momento di iniziare a pianificare. In questo articolo vengono illustrate le risorse che consentono agli utenti di eseguire la migrazione dei dati in SharePoint Online o di aggiornare il server SharePoint locale. 
  
## <a name="what-does-end-of-support-mean"></a>Cosa significa fine del supporto?

SharePoint Server, come quasi tutti i prodotti Microsoft, ha un ciclo di vita di supporto durante il quale Microsoft fornisce nuove funzionalità, correzioni di bug, correzioni di sicurezza e così via. Questo ciclo di vita di solito dura 10 anni a partire dalla data di rilascio iniziale del prodotto e la fine di questo ciclo di vita è nota come fine del prodotto di supporto. Alla fine del supporto, Microsoft non fornisce più:
  
- Supporto tecnico per i problemi che possono verificarsi;
    
- Correzioni dei bug per i problemi individuati e che possono influire sulla stabilità e sull'usabilità del server;
    
- Correzioni per la sicurezza per le vulnerabilità individuate e che possono rendere il server vulnerabile alle violazioni della sicurezza; e 
    
- Aggiornamenti del fuso orario.
    
Anche se la farm di SharePoint Server 2007 continuerà a essere operativa dopo il 10 ottobre 2017, non verranno spediti ulteriori aggiornamenti, patch o correzioni per il prodotto (incluse le patch di sicurezza/correzioni) e il supporto tecnico Microsoft avrà spostato completamente le proprie attività di supporto per le versioni più recenti del prodotto. Poiché l'installazione non è più supportata o patchata, al termine degli approcci di supporto è necessario aggiornare il prodotto o eseguire la migrazione di dati importanti.
  
> [!TIP]
> Se non è stato già pianificato l'aggiornamento o la migrazione, vedere: [Opzioni di migrazione di SharePoint 2007 da prendere in considerazione](sharepoint-2007-migration-options.md), per alcuni esempi di inizio. È inoltre possibile cercare i [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) che possono essere utili per l'aggiornamento o Microsoft 365 Migration (o entrambi). 
  
Per ulteriori informazioni sui server di Office 2007 che raggiungono la fine del supporto, vedere [risorse che consentono di eseguire l'aggiornamento da server e client di office 2007](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

Il primo arresto dovrebbe essere il [sito del ciclo](https://go.microsoft.com/fwlink/?linkid=843148)di vita del prodotto. Se si dispone di un prodotto Microsoft locale invecchiato, è necessario verificare la data di fine del supporto in modo che, un anno o così fuori-o fino a quando le migrazioni richiedono generalmente-è possibile pianificare l'aggiornamento o le migrazioni. Quando si sceglie il passaggio successivo, potrebbe essere utile pensare in termini di prestazioni sufficienti, migliori e migliori quando si tratta di caratteristiche del prodotto. Di seguito viene riportato un esempio:
  
|**Buone**|**Meglio**|**Elevate**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||Ambiente ibrido di SharePoint  <br/> |SharePoint Server 2016  <br/> |
| | |Ambiente ibrido di SharePoint  <br/> |
   
Se si scelgono le opzioni sulla parte bassa della scala (sufficiente), tenere presente che è necessario iniziare a pianificare l'aggiornamento molto presto dopo la migrazione da SharePoint Server 2007. (la fine del supporto per SharePoint Server 2007 è il 10 ottobre 2017. Tenere presente che queste date sono soggette a modifiche e controllano il [sito del ciclo](https://support.microsoft.com/lifecycle)di vita del prodotto.
  
## <a name="where-can-i-go-next"></a>Come si prosegue?

SharePoint Server può essere installato in locale nei server personali oppure è possibile utilizzare SharePoint Online, che è un servizio online che fa parte di Microsoft 365. È possibile scegliere di:
  
- Eseguire la migrazione a SharePoint Online
    
- Aggiornare SharePoint Server locale
    
- Eseguire entrambe le operazione sopra riportate
    
- Implementazione di una soluzione [ibrida di SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) 
    
Tenere presente che i costi nascosti associati alla gestione di una server farm vengono inoltrati, la gestione o la migrazione delle personalizzazioni e l'aggiornamento dell'hardware da cui dipende SharePoint Server. La disponibilità di una farm di SharePoint Server locale è gratificante se si tratta di una necessità. in caso contrario, se si esegue la farm nei server di SharePoint Legacy, senza una personalizzazione pesante, è possibile trarre vantaggio da una migrazione pianificata a SharePoint Online.
  
> [!IMPORTANT]
> È disponibile un'altra opzione se il contenuto in SharePoint 2007 viene utilizzato raramente. Alcuni amministratori di SharePoint possono scegliere di creare un abbonamento a Microsoft 365, configurare un nuovo sito di SharePoint Online e quindi eliminare SharePoint 2007, tenendo in considerazione solo i documenti più essenziali per i siti di SharePoint Online freschi. Da qui, i dati possono essere drenati dal sito di SharePoint 2007 in archivi. Illustrare in che modo gli utenti possono utilizzare i dati per l'installazione di SharePoint 2007. Potrebbero esserci modi creativi per risolvere il problema. 
  
|**SharePoint Online (SPO)**|**SharePoint Server locale**|
|:-----|:-----|
|Costo elevato nel tempo (piano/esecuzione/verifica)  <br/> |Costo elevato nel tempo (piano/esecuzione/verifica)  <br/> |
|Costi inferiori per i fondi (nessun acquisto hardware)  <br/> |Costo maggiore nei fondi (hardware + sviluppatori/amministratori)  <br/> |
|Costo di una tantum nella migrazione  <br/> |Costo di una tantum ripetuto per la migrazione futura  <br/> |
|Costo totale di proprietà/manutenzione basso  <br/> |Costo totale elevato di proprietà/manutenzione  <br/> |
   
Quando si esegue la migrazione a Microsoft 365, lo spostamento di una tantum avrà un costo più pesante in anticipo, mentre si stanno organizzando i dati e decidendo cosa prendere per il cloud e cosa lasciarsi alle spalle. Tuttavia, gli aggiornamenti saranno automatici da quel momento in poi, non è più necessario gestire gli aggiornamenti hardware e software e il tempo di attesa della farm verrà eseguito da un contratto di servizio ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)) di Microsoft.
  
### <a name="migrate-to-sharepoint-online"></a>Eseguire la migrazione a SharePoint Online

Verificare che in SharePoint Online siano disponibili tutte le funzionalità necessarie rivedendo la descrizione del servizio associato. Vedere [le descrizioni del servizio Microsoft 365 e Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library).
  
Non esiste un modo diretto per eseguire la migrazione da SharePoint 2007 a SharePoint Online; lo spostamento a SharePoint Online verrebbe effettuato manualmente. Se si esegue l'aggiornamento a SharePoint Server 2013 o SharePoint Server 2016, è possibile che lo spostamento implichi anche l'utilizzo dell'API di migrazione di SharePoint (per eseguire la migrazione delle informazioni in OneDrive for business, ad esempio).
  
|**Pro online**|**Con online**|
|:-----|:-----|
|Microsoft fornisce l'hardware di SPO e tutte le amministrazioni hardware.  <br/> |Le funzionalità disponibili possono essere diverse tra SharePoint Server locale e SPO.  <br/> |
|L'utente è l'amministratore globale dell'abbonamento e può assegnare gli amministratori ai siti SPO.  <br/> |Alcune azioni disponibili per un amministratore di farm in SharePoint Server locale non sono presenti (o non sono necessarie) incluse nel ruolo di amministratore di SharePoint in Microsoft 365.  <br/> |
|Microsoft applica patch, correzioni e aggiornamenti per l'hardware e il software sottostanti.  <br/> |Poiché non è disponibile alcun accesso al file system sottostante nel servizio, alcune personalizzazioni sono limitate.  <br/> |
|Microsoft pubblica [contratti a livello di servizio](https://go.microsoft.com/fwlink/?linkid=843153) e si sposta rapidamente per risolvere gli incidenti a livello di servizio.  <br/> |Il backup e il ripristino e altre opzioni di ripristino vengono automatizzati dal servizio in SharePoint Online-i backup vengono sovrascritti se non utilizzati.  <br/> |
|I test di sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguite su base continuativa del servizio da Microsoft.  <br/> |Le modifiche apportate all'interfaccia utente e ad altre funzionalità di SharePoint vengono installate dal servizio e possono essere attivate o disattivate.  <br/> |
|Microsoft 365 soddisfa molti standard del settore: [offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |L'assistenza di [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) per la migrazione è limitata.  <br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di SPO descritta nella Guida di [orientamento al contenuto di SharePoint Online e OneDrive Migration](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Né gli ingegneri del supporto Microsoft né i dipendenti del datacenter dispongono dell'accesso amministratore illimitato all'abbonamento.  <br/> |Se è necessario aggiornare l'infrastruttura hardware per supportare la versione più recente di SharePoint o se è necessaria una farm secondaria per l'aggiornamento, è possibile che siano presenti costi aggiuntivi.  <br/> |
|I partner possono assistere con il processo monouso di migrazione dei dati a SharePoint Online.  <br/> ||
|I prodotti online vengono aggiornati automaticamente nel servizio, il che significa che se le funzionalità possono essere deprecate, non esiste una vera fine del supporto.  <br/> ||
   
Se si è deciso di creare un nuovo sito Microsoft 365 e la migrazione dei dati viene eseguita manualmente come necessario, è possibile esaminare le opzioni di [microsoft 365](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Aggiornare SharePoint Server locale

Non esiste un modo storica di ignorare le versioni degli aggiornamenti di SharePoint, almeno non dalla versione di SharePoint Server 2016. Questo significa che gli aggiornamenti vanno in sequenza:
  
- SharePoint 2007 \> SharePoint server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016
   
Per utilizzare l'intero percorso da SharePoint 2007 a SharePoint Server 2016, si verificherà un notevole investimento di tempo e comporterà un costo in termini di hardware aggiornato (tenere presente che è necessario aggiornare anche SQL Server), il software e l'amministrazione. Le personalizzazioni dovranno essere aggiornate o abbandonate, in base alla criticità della caratteristica.
  
> [!NOTE]
> È possibile mantenere la farm di SharePoint 2007 di fine vita, installare una farm di SharePoint Server 2016 su un nuovo hardware (in modo che le farm separate vengano eseguite affiancate) e quindi pianificare ed eseguire una migrazione manuale del contenuto, ad esempio per il download e il caricamento del contenuto. Tenere conto di alcuni aspetti negativi degli spostamenti manuali, ad esempio gli spostamenti di documenti che sostituiscono l'ultimo account modificato con l'alias dell'account che esegue lo spostamento manuale, e il lavoro che deve essere eseguito in anticipo, ad esempio la ricreazione di siti, siti secondari, autorizzazioni e strutture di elenchi. Di nuovo, è il momento di prendere in considerazione i dati che è possibile spostare nello spazio di archiviazione, o non è più necessario, un'azione che può ridurre l'impatto della migrazione.
  
In entrambi i casi, pulire l'ambiente prima dell'aggiornamento. Accertarsi che la farm esistente sia funzionale prima di eseguire l'aggiornamento e (di sicuro) prima di rimuovere le autorizzazioni. 
  
Tenere presente i **percorsi di aggiornamento supportati e non consolidati**: 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Se si dispone di **personalizzazioni**, è importante disporre di un piano di aggiornamento per ogni passaggio del percorso di migrazione: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Pro locale**|**Con in locale**|
|:-----|:-----|
|Controllo completo di tutti gli aspetti della farm di SharePoint, dall'hardware del server verso l'alto.  <br/> |Tutte le interruzioni e le correzioni sono responsabili della società (è possibile coinvolgere il supporto tecnico Microsoft se il prodotto non è alla fine del supporto tecnico):  <br/> |
|Set di funzionalità completo di SharePoint Server locale con l'opzione di connettere la farm locale a un abbonamento a SharePoint Online tramite ibrido.  <br/> |Aggiornamento, patch, correzioni per la sicurezza e tutte le operazioni di manutenzione di SharePoint Server gestite in locale.  <br/> |
|Accesso completo per una maggiore personalizzazione.  <br/> |Le [offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devono essere configurate manualmente in locale.  <br/> |
|Test di sicurezza e ottimizzazione delle prestazioni del server, eseguite nei locali (è sotto il controllo).  <br/> |Microsoft 365 può rendere disponibili le funzionalità di SharePoint Online che non interagiscono con SharePoint Server locale  <br/> |
|I partner possono assistere alla migrazione dei dati alla prossima versione di SharePoint Server (e oltre).  <br/> |I siti di SharePoint Server non utilizzeranno automaticamente i certificati [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) come mostrato in SharePoint Online.  <br/> |
|Controllo completo delle convenzioni di denominazione, del backup e del ripristino e di altre opzioni di ripristino in SharePoint Server locale.  <br/> |SharePoint Server locale è sensibile ai ciclo di vita del prodotto.  <br/> |
   
### <a name="upgrade-resources"></a>Risorse per l'aggiornamento

Per iniziare, è necessario conoscere i requisiti hardware e software e quindi seguire i metodi di aggiornamento supportati.
  
- **Requisiti hardware e software per**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Limiti software e limitazioni per**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Panoramica del processo di aggiornamento per**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creare una soluzione ibrida di SharePoint tra SharePoint Online e in locale

Se la risposta alle esigenze di migrazione è da qualche parte tra il self-control offerto da locale e il minor costo di proprietà offerto da SharePoint Online, è possibile connettere le farm di SharePoint Server 2013 o 2016 a SharePoint Online, tramite ibridi. [Informazioni sulle soluzioni ibride di SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Se si decide che una farm di SharePoint Server ibrida trarrà vantaggio dalla propria azienda, acquisire familiarità con i tipi di ibrido esistenti e come configurare la connessione tra la farm di SharePoint locale e la sottoscrizione Microsoft 365.
  
| Opzione | Descrizione |
|:-----|:-----|
[Offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |L'assistenza di [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) per la migrazione è limitata.  <br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di SPO descritta nella Guida di [orientamento al contenuto di SharePoint Online e OneDrive Migration](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Né gli ingegneri del supporto Microsoft né i dipendenti del datacenter dispongono dell'accesso amministratore illimitato all'abbonamento.  <br/> |Se è necessario aggiornare l'infrastruttura hardware per supportare la versione più recente di SharePoint o se è necessaria una farm secondaria per l'aggiornamento, è possibile che siano presenti costi aggiuntivi.  <br/> |
|I partner possono assistere con il processo monouso di migrazione dei dati a SharePoint Online.  <br/> ||
|I prodotti online vengono aggiornati automaticamente nel servizio, il che significa che se le funzionalità possono essere deprecate, non esiste una vera fine del supporto.  <br/> ||
   
Se si è deciso di creare un nuovo sito Microsoft 365 e la migrazione dei dati viene eseguita manualmente come necessario, è possibile esaminare le opzioni di [microsoft 365](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Aggiornare SharePoint Server locale

Non esiste un modo storica di ignorare le versioni degli aggiornamenti di SharePoint, almeno non dalla versione di SharePoint Server 2016. Questo significa che gli aggiornamenti vanno in sequenza:
  
- SharePoint 2007 \> SharePoint server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016
   
Per utilizzare l'intero percorso da SharePoint 2007 a SharePoint Server 2016, si verificherà un notevole investimento di tempo e comporterà un costo in termini di hardware aggiornato (tenere presente che è necessario aggiornare anche SQL Server), il software e l'amministrazione. Le personalizzazioni dovranno essere aggiornate o abbandonate, in base alla criticità della caratteristica.
  
> [!NOTE]
> È possibile mantenere la farm di SharePoint 2007 di fine vita, installare una farm di SharePoint Server 2016 su un nuovo hardware (in modo che le farm separate vengano eseguite affiancate) e quindi pianificare ed eseguire una migrazione manuale del contenuto, ad esempio per il download e il caricamento del contenuto. Tenere conto di alcuni aspetti negativi degli spostamenti manuali, ad esempio gli spostamenti di documenti che sostituiscono l'ultimo account modificato con l'alias dell'account che esegue lo spostamento manuale, e il lavoro che deve essere eseguito in anticipo, ad esempio la ricreazione di siti, siti secondari, autorizzazioni e strutture di elenchi. Di nuovo, è il momento di prendere in considerazione i dati che è possibile spostare nello spazio di archiviazione, o non è più necessario, un'azione che può ridurre l'impatto della migrazione.
  
In entrambi i casi, pulire l'ambiente prima dell'aggiornamento. Accertarsi che la farm esistente sia funzionale prima di eseguire l'aggiornamento e (di sicuro) prima di rimuovere le autorizzazioni. 
  
Tenere presente i **percorsi di aggiornamento supportati e non consolidati**: 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Se si dispone di **personalizzazioni**, è importante disporre di un piano di aggiornamento per ogni passaggio del percorso di migrazione: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Pro locale**|**Con in locale**|
|:-----|:-----|
|Controllo completo di tutti gli aspetti della farm di SharePoint, dall'hardware del server verso l'alto.  <br/> |Tutte le interruzioni e le correzioni sono responsabili della società (è possibile coinvolgere il supporto tecnico Microsoft se il prodotto non è alla fine del supporto tecnico):  <br/> |
|Set di funzionalità completo di SharePoint Server locale con l'opzione di connettere la farm locale a un abbonamento a SharePoint Online tramite ibrido.  <br/> |Aggiornamento, patch, correzioni per la sicurezza e tutte le operazioni di manutenzione di SharePoint Server gestite in locale.  <br/> |
|Accesso completo per una maggiore personalizzazione.  <br/> |Le [offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devono essere configurate manualmente in locale.  <br/> |
|Test di sicurezza e ottimizzazione delle prestazioni del server, eseguite nei locali (è sotto il controllo).  <br/> |Microsoft 365 può rendere disponibili le funzionalità di SharePoint Online che non interagiscono con SharePoint Server locale  <br/> |
|I partner possono assistere alla migrazione dei dati alla prossima versione di SharePoint Server (e oltre).  <br/> |I siti di SharePoint Server non utilizzeranno automaticamente i certificati [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) come mostrato in SharePoint Online.  <br/> |
|Controllo completo delle convenzioni di denominazione, del backup e del ripristino e di altre opzioni di ripristino in SharePoint Server locale.  <br/> |SharePoint Server locale è sensibile ai ciclo di vita del prodotto.  <br/> |
   
### <a name="upgrade-resources"></a>Risorse per l'aggiornamento

Per iniziare, è necessario conoscere i requisiti hardware e software e quindi seguire i metodi di aggiornamento supportati.
  
- **Requisiti hardware e software per**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Limiti software e limitazioni per**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Panoramica del processo di aggiornamento per**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creare una soluzione ibrida di SharePoint tra SharePoint Online e in locale

Se la risposta alle esigenze di migrazione è da qualche parte tra il self-control offerto da locale e il minor costo di proprietà offerto da SharePoint Online, è possibile connettere le farm di SharePoint Server 2013 o 2016 a SharePoint Online, tramite ibridi. [Informazioni sulle soluzioni ibride di SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Se si decide che una farm di SharePoint Server ibrida trarrà vantaggio dalla propria azienda, acquisire familiarità con i tipi di ibrido esistenti e come configurare la connessione tra la farm di SharePoint locale e la sottoscrizione Microsoft 365.
  
Un ottimo modo per vedere come funziona è la creazione di un ambiente di sviluppo/test di Microsoft 365, che è possibile configurare con le [guide dei laboratori di testing](m365-enterprise-test-lab-guides.md). Una volta che si dispone di una versione di valutazione o di una sottoscrizione di Microsoft 365 acquistata, è possibile creare le raccolte siti, i siti Web e le raccolte documenti in SharePoint Online a cui eseguire la migrazione dei dati (manualmente, tramite l'API di migrazione o-se si desidera eseguire la migrazione del contenuto del sito personale in OneDrive for business-tramite la procedura guidata ibrida).
  
> [!NOTE]
> Tenere presente che la farm di SharePoint 2007 dovrà essere aggiornata, in locale, a SharePoint Server 2013 o SharePoint Server 2016 per utilizzare l'opzione ibrida 
  
## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi e ripristino dell'aggiornamento (Office SharePoint Server 2007)](https://go.microsoft.com/fwlink/?linkid=843192)
  
[Risoluzione dei problemi relativi all'aggiornamento (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=843194)
  
[Risolvere i problemi relativi all'aggiornamento dei database in SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Cercare i partner Microsoft per agevolare l'aggiornamento](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Risorse utili per l'aggiornamento da server e client di Office 2007](upgrade-from-office-2007-servers-and-products.md)
  

