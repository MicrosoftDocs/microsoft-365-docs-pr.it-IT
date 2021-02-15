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
description: Il supporto per SharePoint Server 2007 è terminato a ottobre 2017. In questo articolo sono disponibili informazioni sulle opzioni di aggiornamento, migrazione e supporto.
ms.openlocfilehash: aa09669d1c7b90f70e6c136a85d06ef2a516e4b5
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519635"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Guida sulla fine del supporto di SharePoint Server 2007

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Il **10 ottobre 2017,** Microsoft Office SharePoint Server 2007 ha raggiunto la fine del supporto. Se non è stata eseguita la migrazione da SharePoint Server 2007 a Microsoft 365 o a una versione più recente di SharePoint Server locale, è il momento di iniziare la pianificazione. In questo articolo vengono fornite risorse che consentono di eseguire la migrazione dei dati a SharePoint Online o di aggiornare SharePoint Server locale.
  
## <a name="what-does-end-of-support-mean"></a>Cosa significa *fine del supporto?*

SharePoint Server, come la maggior parte dei prodotti Microsoft, ha un ciclo di vita di supporto, durante il quale Microsoft fornisce nuove funzionalità, correzioni di bug, correzioni per la sicurezza e così via. Questo ciclo di vita in genere dura 10 anni dalla versione iniziale del prodotto. La fine di questo ciclo di vita è nota come fine del supporto del prodotto. Dopo la fine del supporto, Microsoft non fornisce più:
  
- Supporto tecnico per i problemi che possono verificarsi.
    
- Correzioni di bug per problemi che possono influire sulla stabilità e sull'usabilità del server.
    
- Correzioni per la sicurezza per vulnerabilità che possono rendere il server vulnerabile alle violazioni della sicurezza.
    
- Aggiornamenti del fuso orario.
    
La farm di SharePoint Server 2007 continuerà a essere operativa dopo il 10 ottobre 2017, ma non verranno rilasciati ulteriori aggiornamenti, patch o correzioni per il prodotto, incluse patch/correzioni per la sicurezza. Il supporto Tecnico Microsoft ha completamente spostato le proprie attività di supporto in versioni più recenti del prodotto. Poiché l'installazione non è più supportata o con patch, è consigliabile aggiornare il prodotto o eseguire la migrazione di dati importanti.
  
> [!TIP]
> Se non è stato ancora pianificato l'aggiornamento o la migrazione, vedere: Opzioni di migrazione di [SharePoint 2007](sharepoint-2007-migration-options.md) da prendere in considerazione per alcuni esempi di dove iniziare. È inoltre possibile cercare i [partner Microsoft che](https://go.microsoft.com/fwlink/?linkid=841249) possono aiutare con l'aggiornamento o la migrazione di Microsoft 365 (o entrambi).
  
Per ulteriori informazioni sui server Office 2007 e sulla fine del supporto, vedere Resources [to help you upgrade from Office 2007 servers and clients.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

Il primo arresto deve essere il [sito Ciclo di vita del prodotto.](https://go.microsoft.com/fwlink/?linkid=843148) If you have an on-premises Microsoft product that's aging, check its end of support date so that you have a year or so to schedule an upgrade or migration. Quando scegli il passaggio successivo, considera quali funzionalità del prodotto sarebbero sufficientemente buone, migliori e migliori. Di seguito viene riportato un esempio: 
  
|**Buone**|**Migliore**|**Elevate**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||Ambiente ibrido di SharePoint  <br/> |SharePoint Server 2016  <br/> |
| | |Ambiente ibrido di SharePoint  <br/> |
   
Se si sceglie un'opzione "abbastanza buona", sarà presto necessario iniziare a pianificare un altro aggiornamento al termine della migrazione da SharePoint Server 2007. 

>[!NOTE] 
>Le date di fine supporto sono soggette a modifiche. Controllare il [sito Ciclo di vita del prodotto.](https://support.microsoft.com/lifecycle)
  
## <a name="where-can-i-go-next"></a>Come si prosegue?

SharePoint Server può essere installato in locale nei propri server. In or you can use SharePoint Online, which is an online service that's part of Microsoft 365. Le opzioni disponibili sono:
  
- Eseguire la migrazione a SharePoint Online.
    
- Aggiornare SharePoint Server locale.
    
- Eseguire entrambe le operazioni precedenti.
    
- Implementare [una soluzione ibrida di SharePoint.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
    
Tenere presenti i costi nascosti associati alla gestione di una server farm, alla gestione o alla migrazione delle personalizzazioni e all'aggiornamento dell'hardware necessario per SharePoint Server. Disporre di una farm di SharePoint Server locale è gratificante, se necessario. Tuttavia, se si esegue la farm in SharePoint Server legacy senza una personalizzazione pesante, è possibile trarre vantaggio dalla migrazione a SharePoint Online.
  
> [!IMPORTANT]
> Esiste un'altra opzione se il contenuto in SharePoint 2007 viene utilizzato raramente. Alcuni amministratori di SharePoint scelgono di creare un abbonamento a Microsoft 365, configurare un nuovo sito di SharePoint Online e quindi di eliminare SharePoint 2007 in modo pulito, portando solo i documenti essenziali nei nuovi siti di SharePoint Online. I dati possono quindi essere scaricati dal sito di SharePoint 2007 negli archivi. Considerare il modo in cui gli utenti lavorano con i dati dell'installazione di SharePoint 2007. Ci possono essere modi creativi per gestire le tue esigenze.
  
|**SharePoint Online (SPO)**|**SharePoint Server locale**|
|:-----|:-----|
|Costo elevato nel tempo (pianificazione/esecuzione/verifica)  <br/> |Costo elevato nel tempo (pianificazione/esecuzione/verifica)  <br/> |
|Costo inferiore in fondi (nessun acquisto di hardware)  <br/> |Costo maggiore in fondi (hardware + sviluppatori/amministratori)  <br/> |
|Costo una sola volta per la migrazione  <br/> |Costo una volta ripetuto per migrazione futura  <br/> |
|Basso costo totale di proprietà/manutenzione  <br/> |Costo totale elevato di proprietà/manutenzione  <br/> |
   
Quando si esegue la migrazione a Microsoft 365, lo spostamento una sola volta avrà un costo più pesante in anticipo, mentre si organizzano i dati e si decide cosa portare nel cloud e cosa lasciarsi alle spalle. Tuttavia, gli aggiornamenti futuri saranno automatici e non sarà più necessario gestire gli aggiornamenti hardware e software. Inoltre, il tempo di up della farm sarà supportato da un Contratto di servizio Microsoft ([SLA).](https://go.microsoft.com/fwlink/?linkid=843153)
  
### <a name="migrate-to-sharepoint-online"></a>Eseguire la migrazione a SharePoint Online

Assicurarsi che SharePoint Online abbia tutte le funzionalità necessarie. Vedere le descrizioni dei [servizi di Microsoft 365 e Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)
  
Non è possibile eseguire la migrazione direttamente da SharePoint 2007 a SharePoint Online. Il passaggio a SharePoint Online verrà eseguito manualmente. Se si esegue l'aggiornamento a SharePoint Server 2013 o SharePoint Server 2016, è possibile utilizzare l'API di migrazione di SharePoint (ad esempio, per eseguire la migrazione delle informazioni in OneDrive for Business).
  
|**Online pro**|**Online con**|
|:-----|:-----|
|Microsoft fornisce l'hardware spo e tutta l'amministrazione dell'hardware.  <br/> |Le funzionalità disponibili possono differire tra SharePoint Server locale e SharePoint Server 2013.  <br/> |
|L'utente è l'amministratore globale della sottoscrizione e può assegnare amministratori ai siti di SharePoint Online.  <br/> |Alcune azioni disponibili per un amministratore di farm in SharePoint Server locale non esistono o non sono necessariamente incluse nel ruolo di amministratore di SharePoint in Microsoft 365.  <br/> |
|Microsoft applica patch, correzioni e aggiornamenti all'hardware e al software sottostanti. <br/> |Poiché nel servizio non è disponibile alcun accesso al file system sottostante, la personalizzazione è limitata.  <br/> |
|Microsoft pubblica i [contratti di servizio e](https://go.microsoft.com/fwlink/?linkid=843153) si sposta rapidamente per risolvere gli incidenti a livello di servizio. <br/> |Backup e ripristino e altre opzioni di ripristino sono automatizzate dal servizio in SharePoint Online. Se non vengono utilizzati, i backup vengono sovrascritti. <br/> |
|I test di sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguiti regolarmente nel servizio da Microsoft. <br/> |Le modifiche apportate all'interfaccia utente e ad altre caratteristiche di SharePoint vengono installate dal servizio e possono essere attivate o disattivate. <br/> |
|Microsoft 365 soddisfa molti standard di settore: [offerte di conformità Microsoft.](https://go.microsoft.com/fwlink/?linkid=843165)  <br/> |[L'assistenza di FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) per la migrazione è limitata.  <br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di SharePoint Online e OneDrive descritta nella Guida di orientamento al contenuto per la migrazione [di SharePoint Online e OneDrive.](https://go.microsoft.com/fwlink/?linkid=843184)  <br/> |
|I tecnici del supporto Tecnico Microsoft e i dipendenti del datacenter non diservino accesso di amministratore illimitato all'abbonamento. <br/> |Possono verificarsi costi aggiuntivi se è necessario aggiornare l'hardware per supportare la versione più recente di SharePoint o se è necessaria una farm secondaria per l'aggiornamento.  <br/> |
|I partner possono assistere nel processo di migrazione dei dati a SharePoint Online una sola volta.  <br/> ||
|I prodotti online vengono aggiornati automaticamente. Anche se le funzionalità possono essere deprecate, non esiste una vera fine del supporto. <br/> ||
   
Se si è deciso di creare un nuovo sito di Microsoft 365 e si eseguirà manualmente la migrazione dei dati in base alle esigenze, controllare le opzioni [di Microsoft 365.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Aggiornare SharePoint Server locale

Non è possibile ignorare le versioni negli aggiornamenti di SharePoint. Gli aggiornamenti vengono evasi in serie:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Passare da SharePoint 2007 a SharePoint Server 2016 significa un investimento significativo di tempo e comporta costi in hardware (è necessario aggiornare anche i server SQL), software e amministrazione. Le personalizzazioni dovranno essere aggiornate o abbandonate.
  
> [!NOTE]
> È possibile mantenere la farm di SharePoint 2007 di fine vita, installare una farm di SharePoint Server 2016 in un nuovo hardware (in modo che le farm separate vengono eseguite affiancate), quindi pianificare ed eseguire una migrazione manuale del contenuto (ad esempio per il download e il ricaricamento del contenuto). Tuttavia, attenzione ad alcune delle insidie degli spostamenti manuali, ad esempio gli spostamenti di documenti che sostituiscono l'account modificato per ultima con l'alias dell'account che effettua lo spostamento manuale. Considerare inoltre il lavoro da eseguire in anticipo, ad esempio la ricreazione di siti, siti secondari, autorizzazioni e strutture di elenchi. Considerare in anticipo i dati che è possibile spostare nell'archiviazione o eliminare per ridurre l'impatto della migrazione.
  
È importante pulire l'ambiente prima di eseguire l'aggiornamento. Prima di eseguire l'aggiornamento, è necessario essere certi che la farm esistente sia funzionante e sicuramente prima di rimuovere le autorizzazioni.
  
Ricordarsi di esaminare *i percorsi di aggiornamento supportati e non supportati:* 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Se sono presenti personalizzazioni, è fondamentale disporre di un piano per ogni passaggio del percorso di migrazione: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**On-premises pro**|**Con locale**|
|:-----|:-----|
|Controllo completo di tutti gli aspetti della farm di SharePoint, dall'hardware del server in su.  <br/> |Tutte le interruzioni e le correzioni sono responsabilità dell'azienda (è possibile coinvolgere il supporto Microsoft a pagamento se il prodotto non è oltre la fine del supporto).  <br/> |
|Set di funzionalità completo di SharePoint Server locale con l'opzione per connettere la farm locale a una sottoscrizione di SharePoint Online tramite ibrida.  <br/> |Aggiornamento, patch, correzioni per la sicurezza e tutta la manutenzione di SharePoint Server gestito in locale.  <br/> |
|Accesso completo per una maggiore personalizzazione.  <br/> |[Le offerte di conformità](https://go.microsoft.com/fwlink/?linkid=843165) Microsoft devono essere configurate manualmente in locale.  <br/> |
|I test di sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguiti in locale (sotto il controllo dell'utente).  <br/> |Microsoft 365 potrebbe rendere disponibili funzionalità per SharePoint Online che non interagisce con SharePoint Server locale.  <br/> |
|I partner possono facilitare la migrazione dei dati alla versione successiva di SharePoint Server (e oltre).  <br/> |I siti di SharePoint Server non utilizzerà automaticamente i [certificati SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) come illustrato in SharePoint Online.  <br/> |
|Controllo completo delle convenzioni di denominazione, backup e ripristino e altre opzioni di ripristino in SharePoint Server locale.  <br/> |SharePoint Server locale è sensibile al ciclo di vita dei prodotti.  <br/> |
   
### <a name="upgrade-resources"></a>Aggiornare le risorse

Verificare che l'ambiente soddisfi i requisiti hardware e software e quindi seguire i metodi di aggiornamento supportati.
  
- **Requisiti hardware/software per:** 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Limiti software per:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Panoramica del processo di aggiornamento per:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creare una soluzione ibrida di SharePoint tra SharePoint Online e locale

Se la risposta alle esigenze di migrazione è compresa tra l'auto-controllo offerto dall'ambiente locale e il costo di proprietà inferiore offerto da SharePoint Online, è possibile connettere le farm di SharePoint Server 2013 o 2016 a SharePoint Online tramite ibride. [Informazioni sulle soluzioni ibride di SharePoint.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Se si decide che una farm ibrida di SharePoint Server trarrà vantaggio dall'azienda, acquisire familiarità con i tipi di ibridi esistenti e come configurare la connessione tra la farm di SharePoint locale e l'abbonamento a Microsoft 365.
  
| Opzione | Descrizione |
|:-----|:-----|
[Offerte per la conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165)  <br/> |[L'assistenza di FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) per la migrazione è limitata.  <br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di SharePoint Online e OneDrive descritta nella Guida di orientamento al contenuto per la migrazione [di SharePoint Online e OneDrive.](https://go.microsoft.com/fwlink/?linkid=843184)  <br/> |
|I tecnici del supporto Tecnico Microsoft e i dipendenti del data center non hanno accesso amministratore illimitato all'abbonamento.<br/> |Possono verificarsi costi aggiuntivi se è necessario aggiornare l'infrastruttura hardware per supportare la versione più recente di SharePoint o se è necessaria una farm secondaria per l'aggiornamento.  <br/> |
|I partner possono assistere nel processo di migrazione dei dati a SharePoint Online una sola volta.  <br/> ||
|I prodotti online vengono aggiornati automaticamente nel servizio. Anche se le funzionalità possono essere deprecate, non esiste una vera fine del supporto.<br/> ||
   
Se si è deciso di creare un nuovo sito di Microsoft 365 e si eseguirà manualmente la migrazione dei dati in base alle esigenze, controllare le opzioni [di Microsoft 365.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Aggiornare SharePoint Server locale

Non è possibile ignorare le versioni negli aggiornamenti di SharePoint. Gli aggiornamenti vengono evasi in serie:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Passare da SharePoint 2007 a SharePoint Server 2016 significa un investimento significativo di tempo e comporta costi per l'hardware (è necessario aggiornare anche i server SQL), il software e l'amministrazione. Le personalizzazioni dovranno essere aggiornate o abbandonate.
  
> [!NOTE]
> È possibile mantenere la farm di SharePoint 2007 di fine vita, installare una farm di SharePoint Server 2016 in un nuovo hardware (in modo che le farm separate vengono eseguite affiancate), quindi pianificare ed eseguire una migrazione manuale del contenuto (ad esempio per il download e il ricaricamento del contenuto). Tuttavia, attenzione ai potenziali insidie degli spostamenti manuali, ad esempio gli spostamenti di documenti che sostituiscono l'account modificato per ultima con l'alias dell'account che effettua lo spostamento manuale e il lavoro che deve essere eseguito in anticipo, ad esempio la ricreazione di siti, siti secondari, autorizzazioni ed elenchi. Considerare quali dati è possibile spostare nell'archiviazione o eliminare per ridurre l'impatto della migrazione.
  
Pulire l'ambiente prima dell'aggiornamento. Prima di eseguire l'aggiornamento e prima di rimuovere le autorizzazioni, è necessario essere certi che la farm esistente sia funzionante. 
  
Ricordarsi di esaminare *i percorsi di aggiornamento supportati e non supportati:* 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Se si dispone *di personalizzazioni,* è fondamentale pianificare l'aggiornamento per ogni passaggio del percorso di migrazione: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Pro locale**|**Con locale**|
|:-----|:-----|
|Controllo completo di tutti gli aspetti della farm di SharePoint, dall'hardware del server in su.  <br/> |Tutte le interruzioni e le correzioni sono responsabilità dell'azienda. Se il prodotto non è oltre la fine del supporto, è possibile coinvolgere il supporto Microsoft a pagamento.  <br/> |
|Set di funzionalità completo di SharePoint Server locale con l'opzione per connettere la farm locale a una sottoscrizione di SharePoint Online tramite ibrida.  <br/> |Aggiornamento, patch, correzioni per la sicurezza e tutta la manutenzione di SharePoint Server gestito in locale.  <br/> |
|Accesso completo per una maggiore personalizzazione.  <br/> |[Le offerte di conformità](https://go.microsoft.com/fwlink/?linkid=843165) Microsoft devono essere configurate manualmente in locale.  <br/> |
|I test di sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguiti in locale sotto il controllo dell'utente.  <br/> |Microsoft 365 potrebbe rendere disponibili funzionalità per SharePoint Online che non interagisce con SharePoint Server locale  <br/> |
|I partner possono facilitare la migrazione dei dati alla versione successiva di SharePoint Server (e oltre).  <br/> |I siti di SharePoint Server non utilizzeranno automaticamente [i certificati SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) come illustrato in SharePoint Online.  <br/> |
|Controllo completo delle convenzioni di denominazione, backup e ripristino e altre opzioni di ripristino in SharePoint Server locale.  <br/> |SharePoint Server locale è sensibile al ciclo di vita dei prodotti.  <br/> |
   
### <a name="upgrade-resources"></a>Aggiornare le risorse

Verificare che l'ambiente soddisfi i requisiti hardware e software. Seguire quindi i metodi di aggiornamento supportati.
  
- **Requisiti hardware/software per:** 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Limiti software per:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Panoramica del processo di aggiornamento per:** 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creare una soluzione ibrida di SharePoint tra SharePoint Online e locale

Se la risposta alle esigenze di migrazione è compresa tra l'auto-controllo offerto dall'ambiente locale e il costo di proprietà inferiore offerto da SharePoint Online, è possibile connettere le farm di SharePoint Server 2013 o 2016 a SharePoint Online tramite ibride. [Informazioni sulle soluzioni ibride di SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Se si decide che una farm ibrida di SharePoint Server trarrà vantaggio dall'azienda, acquisire familiarità con i tipi di ibridi esistenti e come configurare la connessione tra la farm di SharePoint locale e l'abbonamento a Microsoft 365.
  
Un buon modo per vedere come funziona è creare un ambiente di sviluppo/test di Microsoft 365, che è possibile configurare con le guide dei [laboratori di testing.](m365-enterprise-test-lab-guides.md) Dopo aver acquistato una sottoscrizione di valutazione o di Microsoft 365, è possibile creare le raccolte siti, i Web e le raccolte documenti in SharePoint Online in cui è possibile eseguire la migrazione dei dati. È possibile eseguire la migrazione manualmente, tramite l'API di migrazione o, se si desidera eseguire la migrazione del contenuto del sito personale in OneDrive for Business, tramite la procedura guidata ibrida.
  
> [!NOTE]
> Tenere presente che per utilizzare l'opzione ibrida, la farm di SharePoint 2007 dovrà essere aggiornata in locale a SharePoint Server 2013 o SharePoint Server 2016.
  
## <a name="related-topics"></a>Argomenti correlati

[Risolvere i problemi e riprendere l'aggiornamento (Office SharePoint Server 2007)](https://go.microsoft.com/fwlink/?linkid=843192)
  
[Risolvere i problemi di aggiornamento (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=843194)
  
[Risolvere i problemi relativi all'aggiornamento dei database in SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Cercare partner Microsoft per assistenza con l'aggiornamento](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Risorse per l'aggiornamento da server e client di Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
