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
ms.openlocfilehash: 224b0af90d6a314aa15a2c0dab7b60626e5abde8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924869"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Guida sulla fine del supporto di SharePoint Server 2007

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Il **10 ottobre 2017,** Microsoft Office SharePoint Server 2007 ha raggiunto la fine del supporto. Se non è stata eseguita la migrazione da SharePoint Server 2007 a Microsoft 365 o a una versione più recente di SharePoint Server locale, è il momento di iniziare la pianificazione. In questo articolo vengono fornite risorse che consentono di eseguire la migrazione dei dati a SharePoint Online o di aggiornare il SharePoint Server locale.
  
## <a name="what-does-end-of-support-mean"></a>Cosa significa *fine del* supporto?

SharePoint Il server, come la maggior parte dei prodotti Microsoft, ha un ciclo di vita del supporto, durante il quale Microsoft fornisce nuove funzionalità, correzioni di bug, correzioni per la sicurezza e così via. Questo ciclo di vita in genere dura 10 anni dal rilascio iniziale del prodotto. La fine di questo ciclo di vita è nota come fine del supporto del prodotto. Dopo la fine del supporto, Microsoft non fornisce più:
  
- Supporto tecnico per i problemi che possono verificarsi.
    
- Correzioni di bug per i problemi che possono influire sulla stabilità e sull'usabilità del server.
    
- Correzioni della sicurezza per le vulnerabilità che possono rendere il server vulnerabile alle violazioni della sicurezza.
    
- Aggiornamenti del fuso orario.
    
La farm di SharePoint Server 2007 sarà ancora operativa dopo il 10 ottobre 2017, ma non verranno rilasciati ulteriori aggiornamenti, patch o correzioni per il prodotto, incluse le patch/correzioni di sicurezza. Il Supporto Tecnico Microsoft ha completamente spostato i propri sforzi di supporto a versioni più recenti del prodotto. Poiché l'installazione non è più supportata o con patch, è consigliabile aggiornare il prodotto o eseguire la migrazione di dati importanti.
  
> [!TIP]
> Se non è già stato pianificato l'aggiornamento o la migrazione, vedere: SharePoint [2007 migration options to consider](sharepoint-2007-migration-options.md) for some examples of where to begin. È inoltre possibile cercare i [partner Microsoft che](https://go.microsoft.com/fwlink/?linkid=841249) possono aiutare con l'aggiornamento o Microsoft 365 migrazione (o entrambi).
  
Per ulteriori informazioni sui Office 2007 e sulla fine del supporto, vedere Resources to help you [upgrade from Office 2007 servers and clients](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

Il primo arresto deve essere il [sito ciclo di vita del prodotto](/lifecycle/products/?alpha=Microsoft+Office+SharePoint+Server+2007). Se si dispone di un prodotto Microsoft locale obsoleto, controllare la data di fine del supporto in modo da avere un anno o meno per pianificare un aggiornamento o una migrazione. Quando scegli il passaggio successivo, valuta quali funzionalità del prodotto sarebbero sufficientemente buone, migliori e migliori. Di seguito viene riportato un esempio: 
  
|**Buone**|**Meglio**|**Elevate**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||Ambiente ibrido di SharePoint  <br/> |SharePoint Server 2016  <br/> |
| | |Ambiente ibrido di SharePoint  <br/> |
   
Se si sceglie un'opzione "abbastanza buona", sarà presto necessario iniziare a pianificare un altro aggiornamento al termine della migrazione da SharePoint Server 2007. 

>[!NOTE] 
>Le date di fine supporto sono soggette a modifiche. Controllare il [sito ciclo di vita del prodotto](https://support.microsoft.com/lifecycle).
  
## <a name="where-can-i-go-next"></a>Come si prosegue?

SharePoint Il server può essere installato in locale nei propri server. Oppure puoi usare SharePoint Online, che è un servizio online che fa parte di Microsoft 365. Le opzioni disponibili sono:
  
- Eseguire la migrazione a SharePoint Online.
    
- Aggiornare SharePoint Server locale.
    
- Eseguire entrambe le operazioni precedenti.
    
- Implementare una [SharePoint ibrida.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
    
Tenere presente i costi nascosti associati alla gestione di una server farm, alla gestione o alla migrazione delle personalizzazioni e all'aggiornamento dell'hardware necessario SharePoint Server. La presenza di una SharePoint server farm locale è gratificante se necessario. Tuttavia, se si esegue la farm su server SharePoint legacy senza una personalizzazione pesante, è possibile trarre vantaggio dalla migrazione a SharePoint Online.
  
> [!IMPORTANT]
> Esiste un'altra opzione se il contenuto in SharePoint 2007 viene utilizzato raramente. Alcuni amministratori di SharePoint scelgono di creare una sottoscrizione di Microsoft 365, configurare un nuovo sito di SharePoint Online e quindi eliminare SharePoint 2007 in modo pulito, portando solo i documenti essenziali nei nuovi siti di SharePoint Online. I dati possono quindi essere scaricati dal SharePoint 2007 negli archivi. Considerare il modo in cui gli utenti lavorano con i dati dell'SharePoint 2007. Ci possono essere modi creativi per gestire le tue esigenze.
  
|**SharePoint Online (SPO)**|**SharePoint Server locale**|
|:-----|:-----|
|Costo elevato nel tempo (pianificazione/esecuzione/verifica)  <br/> |Costo elevato nel tempo (pianificazione/esecuzione/verifica)  <br/> |
|Costo inferiore per i fondi (nessun acquisto di hardware)  <br/> |Costi più elevati per i fondi (hardware + sviluppatori/amministratori)  <br/> |
|Costo una sola volta per la migrazione  <br/> |Costo una sola volta ripetuto per migrazione futura  <br/> |
|Basso costo totale di proprietà/manutenzione  <br/> |Costo totale elevato di proprietà/manutenzione  <br/> |
   
Quando si esegue la migrazione a Microsoft 365, lo spostamento una sola volta avrà un costo più elevato in anticipo, mentre si organizzano i dati e si decide cosa portare nel cloud e cosa lasciare indietro. Tuttavia, gli aggiornamenti futuri saranno automatici e non sarà più necessario gestire gli aggiornamenti hardware e software. Inoltre, il tempo di esecuzione della farm sarà supportato da un Contratto di servizio Microsoft ([SLA](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)).
  
### <a name="migrate-to-sharepoint-online"></a>Eseguire la migrazione a SharePoint Online

Assicurati che SharePoint Online abbia tutte le funzionalità necessarie. Vedere [Microsoft 365 e Office 365 dei servizi .](/office365/servicedescriptions/office-365-service-descriptions-technet-library)
  
Non è possibile eseguire la migrazione direttamente da SharePoint 2007 a SharePoint Online. Il passaggio a SharePoint Online verrà eseguito manualmente. Se si esegue l'aggiornamento a SharePoint Server 2013 o SharePoint Server 2016, è possibile utilizzare l'API di migrazione di SharePoint (ad esempio, per eseguire la migrazione delle informazioni in OneDrive for Business).
  
|**Online pro**|**Online con**|
|:-----|:-----|
|Microsoft fornisce l'hardware spo e tutta l'amministrazione dell'hardware.  <br/> |Le funzionalità disponibili possono differire tra SharePoint Server locale e SpO.  <br/> |
|L'utente è l'amministratore globale della sottoscrizione e può assegnare gli amministratori ai siti di SharePoint Online.  <br/> |Alcune azioni disponibili per un amministratore di farm in SharePoint Server locale non esistono o non sono necessariamente incluse nel ruolo amministratore di SharePoint in Microsoft 365.  <br/> |
|Microsoft applica patch, correzioni e aggiornamenti all'hardware e al software sottostanti. <br/> |Poiché nel servizio non è disponibile alcun accesso al file system sottostante, la personalizzazione è limitata.  <br/> |
|Microsoft pubblica i [contratti di servizio e](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) si sposta rapidamente per risolvere gli incidenti a livello di servizio. <br/> |Backup e ripristino e altre opzioni di ripristino sono automatizzate dal servizio in SharePoint Online. Se non vengono utilizzati, i backup vengono sovrascritti. <br/> |
|I test di sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguiti continuamente nel servizio da Microsoft. <br/> |Le modifiche apportate all'interfaccia utente e ad altre SharePoint vengono installate dal servizio e potrebbero essere necessarie attivate o disattivate. <br/> |
|Microsoft 365 soddisfa molti standard di settore: [offerte di conformità Microsoft.](/compliance/regulatory/offering-home)  <br/> |[L'assistenza FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) per la migrazione è limitata.  <br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di SpO descritta in [SharePoint Online and OneDrive Migration Content Roadmap](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).  <br/> |
|I tecnici del supporto Tecnico Microsoft e i dipendenti del datacenter non hanno accesso amministrativo illimitato all'abbonamento. <br/> |Possono essere previsti costi aggiuntivi se è necessario aggiornare l'hardware per supportare la versione più recente di SharePoint o se è necessaria una farm secondaria per l'aggiornamento.  <br/> |
|I partner possono assistere nel processo di migrazione dei dati a SharePoint Online.  <br/> ||
|I prodotti online vengono aggiornati automaticamente. Anche se le funzionalità possono essere deprecate, non esiste una vera fine del supporto. <br/> ||
   
Se si è deciso di creare un nuovo sito di Microsoft 365 e si eseguirà manualmente la migrazione dei dati in base alle esigenze, controllare le opzioni [Microsoft 365.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Aggiornare SharePoint Server locale

Non è possibile ignorare le versioni in SharePoint aggiornamenti. Gli aggiornamenti vengono evasi in serie:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Passare da SharePoint 2007 a SharePoint Server 2016 significa un investimento significativo di tempo e comporta costi in hardware (anche i server SQL devono essere aggiornati), software e amministrazione. Le personalizzazioni dovranno essere aggiornate o abbandonate.
  
> [!NOTE]
> È possibile mantenere la farm di SharePoint 2007 di fine vita, installare una farm di SharePoint Server 2016 in un nuovo hardware (in modo che le farm separate esemplino affiancate) e quindi pianificare ed eseguire una migrazione manuale del contenuto (ad esempio per il download e il ricaricamento del contenuto). Tuttavia, fai attenzione ad alcune delle insidie degli spostamenti manuali, ad esempio gli spostamenti di documenti che sostituiscono l'account modificato per ultima con l'alias dell'account che effettua lo spostamento manuale. Considerare inoltre il lavoro da eseguire in anticipo, ad esempio la ricreazione di siti, siti secondari, autorizzazioni e strutture di elenchi. Valutare in anticipo quali dati è possibile spostare nell'archiviazione o eliminare per ridurre l'impatto della migrazione.
  
È importante pulire l'ambiente prima di eseguire l'aggiornamento. Prima di eseguire l'aggiornamento, è necessario essere certi che la farm esistente sia funzionante e sicuramente prima di rimuovere le autorizzazioni.
  
Ricordarsi di esaminare i percorsi di aggiornamento supportati e non *supportati:* 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Se si dispone di personalizzazioni, è fondamentale disporre di un piano per ogni passaggio nel percorso di migrazione: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**On-premises pro**|**Con locale**|
|:-----|:-----|
|Controllo completo di tutti gli aspetti della SharePoint farm, dall'hardware del server verso l'alto.  <br/> |Tutte le interruzioni e le correzioni sono responsabilità dell'azienda (è possibile coinvolgere il supporto Microsoft a pagamento se il prodotto non è oltre la fine del supporto).  <br/> |
|Set di funzionalità completo di SharePoint Server locale con la possibilità di connettere la farm locale a una sottoscrizione SharePoint Online tramite ibrido.  <br/> |Aggiornamento, patch, correzioni per la sicurezza e tutta la manutenzione di SharePoint Server gestito in locale.  <br/> |
|Accesso completo per una maggiore personalizzazione.  <br/> |[Le offerte di conformità Microsoft](/compliance/regulatory/offering-home) devono essere configurate manualmente in locale.  <br/> |
|I test di sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguiti in locale (sotto il controllo dell'utente).  <br/> |Microsoft 365 rendere disponibili funzionalità per SharePoint Online che non interagisce con SharePoint Server locale.  <br/> |
|I partner possono assistere nella migrazione dei dati alla versione successiva di SharePoint Server (e oltre).  <br/> |I siti SharePoint Server non utilizzerà automaticamente i [certificati SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) come illustrato in SharePoint Online.  <br/> |
|Controllo completo delle convenzioni di denominazione, backup e ripristino e altre opzioni di ripristino in SharePoint Server locale.  <br/> |SharePoint Il server locale è sensibile ai cicli di vita dei prodotti.  <br/> |
   
### <a name="upgrade-resources"></a>Aggiornare le risorse

Verificare che l'ambiente soddisfi i requisiti hardware e software e quindi seguire i metodi di aggiornamento supportati.
  
- **Requisiti hardware/software per**: 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Limiti software e limiti per**: 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **Panoramica del processo di aggiornamento per**: 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creare una SharePoint ibrida tra SharePoint Online e locale

Se la risposta alle esigenze di migrazione è compresa tra l'auto-controllo offerto dall'ambiente locale e il costo di proprietà inferiore offerto da SharePoint Online, è possibile connettere le farm di SharePoint Server 2013 o 2016 a SharePoint Online tramite ibridi. [Informazioni sulle SharePoint ibride.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Se si decide che una farm di SharePoint Server ibrida sarà utile per l'azienda, acquisire familiarità con i tipi esistenti di ibridi e come configurare la connessione tra la farm di SharePoint locale e la sottoscrizione Microsoft 365.
  
| Opzione | Descrizione |
|:-----|:-----|
[Offerte per la conformità Microsoft](/compliance/regulatory/offering-home)  <br/> |[L'assistenza FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) per la migrazione è limitata.  <br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di [SpO](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)descritta in SharePoint Online and OneDrive Migration Content Roadmap .  <br/> |
|I tecnici del supporto Microsoft e i dipendenti del data center non hanno accesso amministrativo illimitato all'abbonamento.<br/> |Possono essere previsti costi aggiuntivi se è necessario aggiornare l'infrastruttura hardware per supportare la versione più recente di SharePoint o se è necessaria una farm secondaria per l'aggiornamento.  <br/> |
|I partner possono assistere nel processo di migrazione dei dati a SharePoint Online.  <br/> ||
|I prodotti online vengono aggiornati automaticamente nel servizio. Anche se le funzionalità possono essere deprecate, non esiste una vera fine del supporto.<br/> ||
   
Se si è deciso di creare un nuovo sito di Microsoft 365 e si eseguirà manualmente la migrazione dei dati in base alle esigenze, controllare le opzioni [Microsoft 365.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Aggiornare SharePoint Server locale

Non è possibile ignorare le versioni in SharePoint aggiornamenti. Gli aggiornamenti vengono evasi in serie:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Per passare da SharePoint 2007 a SharePoint Server 2016 significa un investimento significativo di tempo e comporterà costi per hardware (anche i server SQL devono essere aggiornati), software e amministrazione. Le personalizzazioni dovranno essere aggiornate o abbandonate.
  
> [!NOTE]
> È possibile mantenere la farm di SharePoint 2007 di fine vita, installare una farm di SharePoint Server 2016 in un nuovo hardware (in modo che le farm separate esemplino affiancate) e quindi pianificare ed eseguire una migrazione manuale del contenuto (ad esempio per il download e il ricaricamento del contenuto). Tuttavia, attenzione ai potenziali insidie degli spostamenti manuali, ad esempio gli spostamenti di documenti che sostituiscono l'account modificato per ultima con l'alias dell'account che effettua lo spostamento manuale e il lavoro che deve essere eseguito in anticipo, ad esempio la ricreazione di siti, siti secondari, autorizzazioni e strutture di elenchi. Considerare quali dati è possibile spostare nell'archiviazione o eliminare per ridurre l'impatto della migrazione.
  
Pulire l'ambiente prima dell'aggiornamento. Prima di eseguire l'aggiornamento e prima di rimuovere le autorizzazioni, è necessario essere certi che la farm esistente sia funzionante. 
  
Ricordarsi di esaminare i percorsi di aggiornamento supportati e non *supportati:* 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Se si dispone *di personalizzazioni,* è fondamentale pianificare l'aggiornamento per ogni passaggio del percorso di migrazione: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**Locale Pro**|**Con locale**|
|:-----|:-----|
|Controllo completo di tutti gli aspetti della SharePoint farm, dall'hardware del server verso l'alto.  <br/> |Tutte le interruzioni e le correzioni sono responsabilità dell'azienda. È possibile coinvolgere il supporto Microsoft a pagamento se il prodotto non è oltre la fine del supporto.  <br/> |
|Set di funzionalità completo di SharePoint Server locale con la possibilità di connettere la farm locale a una sottoscrizione SharePoint Online tramite ibrido.  <br/> |Aggiornamento, patch, correzioni per la sicurezza e tutta la manutenzione di SharePoint Server gestito in locale.  <br/> |
|Accesso completo per una maggiore personalizzazione.  <br/> |[Le offerte di conformità Microsoft](/compliance/regulatory/offering-home) devono essere configurate manualmente in locale.  <br/> |
|I test di sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguiti in locale sotto il tuo controllo.  <br/> |Microsoft 365 rendere disponibili funzionalità per SharePoint Online che non interagisce con SharePoint Server locale  <br/> |
|I partner possono aiutare a eseguire la migrazione dei dati alla versione successiva di SharePoint Server (e oltre).  <br/> |I siti SharePoint Server non utilizzeranno automaticamente i [certificati SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) come illustrato in SharePoint Online.  <br/> |
|Controllo completo delle convenzioni di denominazione, backup e ripristino e altre opzioni di ripristino in SharePoint Server locale.  <br/> |SharePoint Il server locale è sensibile ai cicli di vita dei prodotti.  <br/> |
   
### <a name="upgrade-resources"></a>Aggiornare le risorse

Verificare che l'ambiente soddisfi i requisiti hardware e software. Seguire quindi i metodi di aggiornamento supportati.
  
- **Requisiti hardware/software per:** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Limiti software e limiti per:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **Panoramica del processo di aggiornamento per:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creare una SharePoint ibrida tra SharePoint Online e locale

Se la risposta alle esigenze di migrazione è compresa tra l'auto-controllo offerto dall'ambiente locale e il costo di proprietà inferiore offerto da SharePoint Online, è possibile connettere le farm di SharePoint Server 2013 o 2016 a SharePoint Online tramite ibridi. [Informazioni sulle SharePoint ibride](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Se si decide che una farm di SharePoint Server ibrida sarà utile per l'azienda, acquisire familiarità con i tipi esistenti di ibridi e come configurare la connessione tra la farm di SharePoint locale e la sottoscrizione Microsoft 365.
  
Un ottimo modo per vedere come funziona è quello di creare un ambiente di sviluppo/test Microsoft 365, che è possibile configurare con [Test Lab Guides.](m365-enterprise-test-lab-guides.md) Dopo aver acquistato una sottoscrizione di valutazione Microsoft 365, è possibile creare raccolte siti, Web e raccolte documenti in SharePoint Online in cui è possibile eseguire la migrazione dei dati. È possibile eseguire la migrazione manualmente, tramite l'API di migrazione o, se si desidera eseguire la migrazione del contenuto dei siti OneDrive for Business, tramite la procedura guidata ibrida.
  
> [!NOTE]
> Tenere presente che per utilizzare l'opzione ibrida, la farm di SharePoint 2007 dovrà essere aggiornata, in locale, a SharePoint Server 2013 o SharePoint Server 2016.
  
## <a name="related-topics"></a>Argomenti correlati

[Risolvere i problemi e riprendere l'aggiornamento (Office SharePoint Server 2007)](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262967(v=office.12))
  
[Risolvere i problemi di aggiornamento (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/cc262967(v=office.14))
  
[Risolvere i problemi relativi all'aggiornamento dei database in SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)
  
[Cercare partner Microsoft utili per l'aggiornamento](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Risorse per l'aggiornamento da server e client Office 2007](upgrade-from-office-2007-servers-and-products.md)
