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
description: Il supporto per SharePoint Server 2007 è terminato nell'ottobre 2017. In questo articolo vengono fornite informazioni relative all'aggiornamento, alla migrazione e alle opzioni di supporto.
ms.openlocfilehash: aa09669d1c7b90f70e6c136a85d06ef2a516e4b5
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519635"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Guida sulla fine del supporto di SharePoint Server 2007

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Il **10 ottobre 2017**, Microsoft Office SharePoint Server 2007 ha raggiunto la fine del supporto. Se non è stata eseguita la migrazione da SharePoint Server 2007 a Microsoft 365 o a una versione più recente di SharePoint Server locale, è giunto il momento di iniziare a pianificare. In questo articolo vengono fornite risorse che consentono di eseguire la migrazione dei dati in SharePoint Online o di aggiornare il server di SharePoint locale.
  
## <a name="what-does-end-of-support-mean"></a>Cosa significa *fine del supporto* ?

SharePoint Server, come la maggior parte dei prodotti Microsoft, ha un ciclo di vita di supporto, durante il quale Microsoft fornisce nuove funzionalità, correzioni di bug, correzioni di sicurezza e così via. Questo ciclo di vita in genere ha una durata di 10 anni rispetto alla versione iniziale del prodotto. La fine del ciclo di vita è nota come fine del supporto del prodotto. Dopo la fine del supporto, Microsoft non fornisce più:
  
- Supporto tecnico per i problemi che possono verificarsi.
    
- Correzioni degli errori relativi a problemi che possono influire sulla stabilità e sull'usabilità del server.
    
- Correzioni per la sicurezza per vulnerabilità che potrebbero rendere il server vulnerabile alle violazioni della sicurezza.
    
- Aggiornamenti del fuso orario.
    
La farm di SharePoint Server 2007 continuerà a essere operativa dopo il 10 ottobre 2017, ma non verranno rilasciati ulteriori aggiornamenti, patch o correzioni per il prodotto, incluse le patch o le correzioni per la sicurezza. Il supporto tecnico Microsoft ha completamente spostato gli sforzi di supporto per le versioni più recenti del prodotto. Poiché l'installazione non è più supportata o patchata, è consigliabile aggiornare il prodotto o eseguire la migrazione dei dati importanti.
  
> [!TIP]
> Se non è stato già pianificato l'aggiornamento o la migrazione, vedere: [Opzioni di migrazione di SharePoint 2007 da prendere in considerazione](sharepoint-2007-migration-options.md) per alcuni esempi di inizio. È inoltre possibile cercare i [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) che possono essere utili per l'aggiornamento o Microsoft 365 Migration (o entrambi).
  
Per ulteriori informazioni sui server di Office 2007 e la fine del supporto, vedere [risorse che consentono di eseguire l'aggiornamento da server e client di office 2007](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

Il primo arresto dovrebbe essere il [sito del ciclo](https://go.microsoft.com/fwlink/?linkid=843148)di vita del prodotto. Se si dispone di un prodotto Microsoft locale che invecchia, controllare la data di fine del supporto in modo da avere un anno o più per pianificare un aggiornamento o una migrazione. Quando si sceglie il passaggio successivo, valutare quali funzionalità del prodotto sarebbero sufficienti, migliori e migliori. Di seguito viene riportato un esempio: 
  
|**Buone**|**Meglio**|**Elevate**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||Ambiente ibrido di SharePoint  <br/> |SharePoint Server 2016  <br/> |
| | |Ambiente ibrido di SharePoint  <br/> |
   
Se si sceglie un'opzione "sufficiente", è necessario iniziare a pianificare un altro aggiornamento dopo che è stata completata la migrazione da SharePoint Server 2007. 

>[!NOTE] 
>Le date di fine del supporto sono soggette a modifiche. Controllare il [sito del ciclo](https://support.microsoft.com/lifecycle)di vita del prodotto.
  
## <a name="where-can-i-go-next"></a>Come si prosegue?

SharePoint Server può essere installato in locale nei propri server. In alternativa, è possibile utilizzare SharePoint Online, che è un servizio online che fa parte di Microsoft 365. Le opzioni disponibili sono:
  
- Eseguire la migrazione a SharePoint Online.
    
- Aggiornare SharePoint Server locale.
    
- Eseguire entrambe le operazione sopra riportate.
    
- Implementare una soluzione [ibrida di SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) .
    
Tenere presente i costi nascosti associati alla gestione di una server farm, la gestione o la migrazione delle personalizzazioni e l'aggiornamento dell'hardware necessario per SharePoint Server. La disponibilità di una farm di SharePoint Server locale è gratificante, se necessario. Tuttavia, se si esegue la farm nei server di SharePoint Legacy senza una personalizzazione pesante, è possibile trarre vantaggio dalla migrazione a SharePoint Online.
  
> [!IMPORTANT]
> È disponibile un'altra opzione se il contenuto in SharePoint 2007 viene utilizzato raramente. Alcuni amministratori di SharePoint scelgono di creare un abbonamento a Microsoft 365, di configurare un nuovo sito di SharePoint Online e quindi di eliminare in modo pulito SharePoint 2007, tenendo solo i documenti essenziali per i siti di SharePoint Online freschi. I dati possono quindi essere svuotati dal sito di SharePoint 2007 in archivi. Valutare la modalità di utilizzo dei dati da parte degli utenti nell'installazione di SharePoint 2007. Possono essere disponibili modi creativi per gestire le proprie esigenze.
  
|**SharePoint Online (SPO)**|**SharePoint Server locale**|
|:-----|:-----|
|Costo elevato nel tempo (piano/esecuzione/verifica)  <br/> |Costo elevato nel tempo (piano/esecuzione/verifica)  <br/> |
|Costi inferiori per i fondi (nessun acquisto hardware)  <br/> |Costo maggiore nei fondi (hardware + sviluppatori/amministratori)  <br/> |
|Costo di una tantum nella migrazione  <br/> |Costo di una tantum ripetuto per la migrazione futura  <br/> |
|Costo totale di proprietà/manutenzione basso  <br/> |Costo totale elevato di proprietà/manutenzione  <br/> |
   
Quando si esegue la migrazione a Microsoft 365, lo spostamento di una tantum avrà un costo più alto, mentre si organizzano i dati e si decide cosa fare per il cloud e cosa lasciarsi alle spalle. Tuttavia, gli aggiornamenti futuri saranno automatici e non sarà più necessario gestire gli aggiornamenti hardware e software. Inoltre, il tempo di attesa della farm verrà eseguito da un contratto di servizio Microsoft ([SLA](https://go.microsoft.com/fwlink/?linkid=843153), Service Level Agreement).
  
### <a name="migrate-to-sharepoint-online"></a>Eseguire la migrazione a SharePoint Online

Assicurarsi che SharePoint Online disponga di tutte le funzionalità necessarie. Vedere [le descrizioni del servizio Microsoft 365 e Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library).
  
Non è possibile eseguire la migrazione direttamente da SharePoint 2007 a SharePoint Online. Lo spostamento a SharePoint Online verrebbe effettuato manualmente. Se si esegue l'aggiornamento a SharePoint Server 2013 o SharePoint Server 2016, è possibile utilizzare l'API di migrazione di SharePoint (per eseguire la migrazione delle informazioni in OneDrive for business, ad esempio).
  
|**Pro online**|**Con online**|
|:-----|:-----|
|Microsoft fornisce l'hardware di SPO e tutte le amministrazioni hardware.  <br/> |Le funzionalità disponibili possono variare tra SharePoint Server locale e SPO.  <br/> |
|L'utente è l'amministratore globale dell'abbonamento e può assegnare gli amministratori ai siti SPO.  <br/> |Alcune azioni disponibili per un amministratore di farm in SharePoint Server locale non esistono o non sono necessariamente incluse nel ruolo di amministratore di SharePoint in Microsoft 365.  <br/> |
|Microsoft applica patch, correzioni e aggiornamenti per l'hardware e il software sottostanti. <br/> |Poiché non è possibile accedere al file system sottostante nel servizio, la personalizzazione è limitata.  <br/> |
|Microsoft pubblica [contratti a livello di servizio](https://go.microsoft.com/fwlink/?linkid=843153) e si sposta rapidamente per risolvere gli incidenti a livello di servizio. <br/> |Backup e ripristino e altre opzioni di ripristino vengono automatizzate dal servizio in SharePoint Online. I backup vengono sovrascritti se non utilizzati. <br/> |
|I test di sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguite su base continuativa del servizio da Microsoft. <br/> |Le modifiche apportate all'interfaccia utente e ad altre funzionalità di SharePoint vengono installate dal servizio e possono essere attivate o disattivate. <br/> |
|Microsoft 365 soddisfa molti standard del settore: [offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |L'assistenza di [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) per la migrazione è limitata.  <br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di SPO descritta nella Guida di [orientamento al contenuto di SharePoint Online e OneDrive Migration](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Gli ingegneri del supporto tecnico Microsoft e i dipendenti del datacenter non avranno accesso di amministratore illimitato all'abbonamento. <br/> |Se è necessario aggiornare l'hardware per supportare la versione più recente di SharePoint o se è necessaria una farm secondaria per l'aggiornamento, è possibile che siano presenti costi aggiuntivi.  <br/> |
|I partner possono assistere con il processo monouso di migrazione dei dati a SharePoint Online.  <br/> ||
|I prodotti online vengono aggiornati automaticamente. Anche se le funzionalità possono essere deprecate, non esiste una vera fine del supporto. <br/> ||
   
Se si è deciso di creare un nuovo sito Microsoft 365 e di eseguirne manualmente la migrazione dei dati, vedere le [Opzioni di microsoft 365](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Aggiornare SharePoint Server locale

Non è possibile ignorare le versioni negli aggiornamenti di SharePoint. Gli aggiornamenti passano in sequenza:
  
- SharePoint 2007 \> SharePoint server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016
   
Per passare da SharePoint 2007 a SharePoint Server 2016, significa un investimento significativo del tempo e implica costi nell'hardware (è necessario aggiornare anche SQL Server), il software e l'amministrazione. Le personalizzazioni dovranno essere aggiornate o abbandonate.
  
> [!NOTE]
> È possibile mantenere la farm di SharePoint 2007 di fine vita, installare una farm di SharePoint Server 2016 su un nuovo hardware (in modo che le farm separate vengano eseguite affiancate) e quindi pianificare ed eseguire una migrazione manuale del contenuto, ad esempio per il download e il caricamento del contenuto. Tuttavia, è preoccuparsi di alcuni dei problemi di spostamento manuale, ad esempio gli spostamenti di documenti che sostituiscono l'account Last-modified con l'alias dell'account che esegue lo spostamento manuale. Si consideri anche il lavoro che deve essere svolto in anticipo, ad esempio ricreare siti, sottositi, autorizzazioni e strutture di elenchi. Valutare in anticipo quali dati è possibile spostare in archiviazione o eliminare per ridurre l'impatto della migrazione.
  
È importante pulire l'ambiente prima di eseguire l'aggiornamento. Accertarsi che la farm esistente sia funzionale prima di eseguire l'aggiornamento e, certamente, prima di rimuovere le autorizzazioni.
  
Tenere presente i *percorsi di aggiornamento supportati e non consolidati*: 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Se si dispone di personalizzazioni, è importante disporre di un piano per ogni passaggio del percorso di migrazione: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Pro locale**|**Con in locale**|
|:-----|:-----|
|Controllo completo di tutti gli aspetti della farm di SharePoint, dall'hardware del server verso l'alto.  <br/> |Tutte le interruzioni e le correzioni sono responsabili della società (è possibile coinvolgere il supporto tecnico Microsoft se il prodotto non è stato superato).  <br/> |
|Set di funzionalità completo di SharePoint Server locale con l'opzione di connettere la farm locale a un abbonamento a SharePoint Online tramite ibrido.  <br/> |Aggiornamento, patch, correzioni per la sicurezza e tutte le operazioni di manutenzione di SharePoint Server gestite in locale.  <br/> |
|Accesso completo per una maggiore personalizzazione.  <br/> |Le [offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devono essere configurate manualmente in locale.  <br/> |
|Test di sicurezza e ottimizzazione delle prestazioni del server vengono eseguite nei locali (sotto il controllo).  <br/> |Microsoft 365 può rendere disponibili le funzionalità di SharePoint Online che non interagiscono con SharePoint Server locale.  <br/> |
|I partner possono assistere alla migrazione dei dati alla prossima versione di SharePoint Server (e oltre).  <br/> |I siti di SharePoint Server non utilizzeranno automaticamente i certificati [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) come mostrato in SharePoint Online.  <br/> |
|Controllo completo delle convenzioni di denominazione, del backup e del ripristino e di altre opzioni di ripristino in SharePoint Server locale.  <br/> |SharePoint Server locale è sensibile ai ciclo di vita del prodotto.  <br/> |
   
### <a name="upgrade-resources"></a>Risorse per l'aggiornamento

Verificare che l'ambiente soddisfi i requisiti hardware e software e quindi seguire i metodi di aggiornamento supportati.
  
- **Requisiti hardware e software per**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Limiti software e limitazioni per**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Panoramica del processo di aggiornamento per**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creare una soluzione ibrida di SharePoint tra SharePoint Online e in locale

Se la risposta alle esigenze di migrazione è da qualche parte tra il self-control offerto da locale e il minor costo di proprietà offerto da SharePoint Online, è possibile connettere le farm di SharePoint Server 2013 o 2016 a SharePoint Online tramite ibridi. Informazioni [sulle soluzioni ibride di SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).
  
Se si decide che una farm di SharePoint Server ibrida trarrà vantaggio dalla propria azienda, acquisire familiarità con i tipi di ibridi esistenti e come configurare la connessione tra la farm di SharePoint locale e la sottoscrizione Microsoft 365.
  
| Opzione | Descrizione |
|:-----|:-----|
[Offerte per la conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165)  <br/> |L'assistenza di [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) per la migrazione è limitata.  <br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di SPO descritta nella Guida di [orientamento al contenuto di SharePoint Online e OneDrive Migration](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Gli ingegneri del supporto tecnico Microsoft e i dipendenti del Data Center non dispongono dell'accesso di amministratore illimitato all'abbonamento.<br/> |Se è necessario aggiornare l'infrastruttura hardware per supportare la versione più recente di SharePoint o se è necessaria una farm secondaria per l'aggiornamento, è possibile che siano presenti costi aggiuntivi.  <br/> |
|I partner possono assistere con il processo monouso di migrazione dei dati a SharePoint Online.  <br/> ||
|I prodotti online vengono aggiornati automaticamente all'interno del servizio. Anche se le funzionalità possono essere deprecate, non esiste una vera fine del supporto.<br/> ||
   
Se si è deciso di creare un nuovo sito Microsoft 365 e di eseguirne manualmente la migrazione dei dati, vedere le [Opzioni di microsoft 365](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Aggiornare SharePoint Server locale

Non è possibile ignorare le versioni negli aggiornamenti di SharePoint. Gli aggiornamenti passano in sequenza:
  
- SharePoint 2007 \> SharePoint server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016
   
Per passare da SharePoint 2007 a SharePoint Server 2016, si verificherà un notevole investimento di tempo e comporterà costi per l'hardware (devono essere aggiornati anche i server SQL), il software e l'amministrazione. Le personalizzazioni dovranno essere aggiornate o abbandonate.
  
> [!NOTE]
> È possibile mantenere la farm di SharePoint 2007 di fine vita, installare una farm di SharePoint Server 2016 su un nuovo hardware (in modo che le farm separate vengano eseguite affiancate) e quindi pianificare ed eseguire una migrazione manuale del contenuto, ad esempio per il download e il caricamento del contenuto. Tuttavia, prestare attenzione ai potenziali problemi di spostamento manuale, ad esempio gli spostamenti di documenti che sostituiscono l'account Last-modified con l'alias dell'account che esegue lo spostamento manuale e il lavoro che deve essere eseguito in anticipo, ad esempio la ricreazione di siti, sottositi, autorizzazioni e strutture di elenchi. Esaminare i dati che è possibile spostare in archiviazione o eliminare per ridurre l'impatto della migrazione.
  
Pulizia dell'ambiente prima dell'aggiornamento. Accertarsi che la farm esistente sia funzionale prima di eseguire l'aggiornamento e certamente prima di rimuovere le autorizzazioni. 
  
Tenere presente i *percorsi di aggiornamento supportati e non consolidati*: 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Se si dispone di *personalizzazioni*, è importante disporre di un piano di aggiornamento per ogni passaggio del percorso di migrazione: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Pro locale**|**Con in locale**|
|:-----|:-----|
|Controllo completo di tutti gli aspetti della farm di SharePoint, dall'hardware del server verso l'alto.  <br/> |Tutte le interruzioni e le correzioni sono responsabili della società. È possibile coinvolgere il supporto tecnico Microsoft se il prodotto non è stato superato.  <br/> |
|Set di funzionalità completo di SharePoint Server locale con l'opzione di connettere la farm locale a un abbonamento a SharePoint Online tramite ibrido.  <br/> |Aggiornamento, patch, correzioni per la sicurezza e tutte le operazioni di manutenzione di SharePoint Server gestite in locale.  <br/> |
|Accesso completo per una maggiore personalizzazione.  <br/> |Le [offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devono essere configurate manualmente in locale.  <br/> |
|I test di sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguite nella propria sede sotto il proprio controllo.  <br/> |Microsoft 365 può rendere disponibili le funzionalità di SharePoint Online che non interagiscono con SharePoint Server locale  <br/> |
|I partner possono contribuire alla migrazione dei dati alla prossima versione di SharePoint Server e oltre.  <br/> |I siti di SharePoint Server non utilizzeranno automaticamente i certificati [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) come mostrato in SharePoint Online.  <br/> |
|Controllo completo delle convenzioni di denominazione, del backup e del ripristino e di altre opzioni di ripristino in SharePoint Server locale.  <br/> |SharePoint Server locale è sensibile ai ciclo di vita del prodotto.  <br/> |
   
### <a name="upgrade-resources"></a>Risorse per l'aggiornamento

Verificare che l'ambiente soddisfi i requisiti hardware e software. Seguire quindi i metodi di aggiornamento supportati.
  
- **Requisiti hardware e software per:** 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Limiti software e limitazioni per:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Panoramica del processo di aggiornamento per:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creare una soluzione ibrida di SharePoint tra SharePoint Online e in locale

Se la risposta alle esigenze di migrazione è da qualche parte tra il self-control offerto da locale e il minor costo di proprietà offerto da SharePoint Online, è possibile connettere le farm di SharePoint Server 2013 o 2016 a SharePoint Online tramite ibridi. [Informazioni sulle soluzioni ibride di SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Se si decide che una farm di SharePoint Server ibrida trarrà vantaggio dalla propria azienda, acquisire familiarità con i tipi di ibridi esistenti e come configurare la connessione tra la farm di SharePoint locale e la sottoscrizione Microsoft 365.
  
Un buon modo per vedere come funziona è creare un ambiente di sviluppo e di testing di Microsoft 365, che è possibile configurare con le [guide dei laboratori di testing](m365-enterprise-test-lab-guides.md). Dopo aver ottenuto un abbonamento di valutazione o acquistato Microsoft 365, è possibile creare le raccolte siti, i siti Web e le raccolte documenti in SharePoint Online a cui è possibile eseguire la migrazione dei dati. È possibile eseguire la migrazione manuale, tramite l'API di migrazione, oppure, se si desidera eseguire la migrazione del contenuto del sito personale a OneDrive for business, tramite la procedura guidata ibrida.
  
> [!NOTE]
> Tenere presente che per utilizzare l'opzione ibrida, è necessario che la farm di SharePoint 2007 sia aggiornata, in locale, a SharePoint Server 2013 o SharePoint Server 2016.
  
## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi e ripristino dell'aggiornamento (Office SharePoint Server 2007)](https://go.microsoft.com/fwlink/?linkid=843192)
  
[Risoluzione dei problemi relativi all'aggiornamento (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=843194)
  
[Risolvere i problemi relativi all'aggiornamento dei database in SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Cercare i partner Microsoft per agevolare l'aggiornamento](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Risorse utili per l'aggiornamento da server e client di Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
