---
title: Aggiornamento da SharePoint 2010
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: Trovare informazioni e risorse per l'aggiornamento da SharePoint 2010 e SharePoint Server 2010, come supporto per entrambe le estremità del 13 ottobre 2020.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 57e44cf14a74f6a5a2098512e0a2339037d70655
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690945"
---
# <a name="upgrading-from-sharepoint-2010"></a>Aggiornamento da SharePoint 2010

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Microsoft SharePoint 2010 e SharePoint Server 2010 potranno raggiungere la fine del supporto del **13 aprile 2021**. In questo articolo vengono illustrate le risorse che consentono di eseguire la migrazione dei dati di SharePoint Server 2010 esistenti a SharePoint online in Microsoft 365 o di aggiornare l'ambiente di SharePoint Server 2010 locale.
  
## <a name="what-is-end-of-support"></a>Che cos'è la fine del supporto tecnico?

Quando il software SharePoint Server 2010 e SharePoint Foundation 2010 raggiunge la fine del ciclo di vita del supporto tecnico (ovvero il tempo durante il quale Microsoft fornisce nuove funzionalità, correzioni di bug, correzioni di sicurezza e così via), questo è denominato "fine del supporto" del software o, a volte, la sua ' Pensione '. Al termine del supporto (o EOS) di un prodotto, niente si spegne o smette di funzionare. Tuttavia, alla fine del supporto del software, Microsoft non fornisce più:
  
- Supporto tecnico per i problemi che possono verificarsi;
    
- Correzioni dei bug per i problemi individuati e che possono influire sulla stabilità e sull'usabilità del server;
    
- Correzioni per la sicurezza per le vulnerabilità individuate e che possono rendere il server vulnerabile alle violazioni della sicurezza;
    
- Aggiornamenti del fuso orario.
    
Ciò significa che non verranno inviati ulteriori aggiornamenti, patch o correzioni per il prodotto (incluse le patch per la sicurezza/correzioni) e il supporto tecnico Microsoft avrà spostato completamente gli sforzi di supporto per le versioni più recenti. Al termine del supporto degli approcci di SharePoint Server 2010, è consigliabile sfruttare le opportunità di tagliare i dati che non sono più necessari prima di eseguire l'aggiornamento del prodotto e/o di migrare i dati importanti.
  
> [!NOTE]
> Un ciclo di vita del software è in genere pari a dieci anni dalla data di rilascio iniziale del prodotto. È possibile cercare i [provider di soluzioni Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) che possono essere utili per l'aggiornamento alla versione successiva del software o a Microsoft 365 Migration (o entrambi). Accertarsi di essere a conoscenza delle date di fine del supporto per le tecnologie sottostanti critiche, in particolare della versione di SQL Server che si sta utilizzando con SharePoint. Per informazioni dettagliate sul ciclo di vita del prodotto, vedere [criteri del ciclo](https://support.microsoft.com/help/14085) di vita fisso.
  
## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

In primo luogo, controllare la data di fine del supporto nel [sito del ciclo](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)di vita del prodotto. Successivamente, assicurarsi di pianificare l'aggiornamento o il tempo di migrazione con la conoscenza di questa data. Tenere presente che il prodotto  *non smetterà di funzionare*  alla data in cui è elencato ed è possibile continuare a usarlo, ma che, poiché l'installazione non verrà più applicata dopo tale data, si vorrà una strategia che consenta di eseguire una transizione più agevole alla versione successiva del prodotto. 
  
Questa matrice consente di tracciare un corso quando si tratta di eseguire la migrazione di caratteristiche del prodotto e dati utente:
  
| Fine del prodotto di supporto | Buone | Elevate |
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013 (in locale)  <br/> |SharePoint Online  <br/> |
||SharePoint Server 2013 ibrido con SharePoint Online  <br/> |SharePoint Server 2016 (in locale)  <br/> |
| | |Ricerca ibrida cloud di SharePoint  <br/> |
   
Se si scelgono le opzioni sulla parte bassa della scala (opzioni valide), sarà necessario iniziare a pianificare un altro aggiornamento subito dopo la migrazione da SharePoint Server 2010 completata. 

Di seguito sono riportati i tre percorsi che è possibile eseguire per evitare la fine del supporto per SharePoint Server 2010.

![Percorsi di aggiornamento di SharePoint Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

>[!Note]
>La fine del supporto per SharePoint Server 2010 e SharePoint Foundation 2010 è programmata per il 13 aprile 2021, ma tenere *presente* che è sempre necessario controllare il [sito del ciclo](https://support.microsoft.com/lifecycle) di vita del prodotto per la data più recente.
>

  
## <a name="where-should-i-go-next"></a>Dove devo andare dopo?

SharePoint Server 2013 e SharePoint Foundation 2013 possono essere installati in locale nei propri server. In caso contrario, è possibile utilizzare SharePoint Online, che è un servizio online che fa parte di Microsoft Microsoft 365. È possibile scegliere di:
  
- Eseguire la migrazione a SharePoint Online
    
- Aggiornare SharePoint Server o SharePoint Foundation in locale
    
- Eseguire entrambe le operazione sopra riportate
    
- Implementazione di una soluzione [ibrida di SharePoint](https://docs.microsoft.com/sharepoint/hybrid/hybrid) 
    
Tenere presente che i costi nascosti associati alla gestione di una server farm vengono inoltrati, la gestione o la migrazione delle personalizzazioni e l'aggiornamento dell'hardware da cui dipende SharePoint Server. Se si è in grado di tenere conto di tutte queste funzionalità, sarà più facile continuare a eseguire l'aggiornamento in locale. In caso contrario, se si esegue la farm nei server di SharePoint Legacy senza una personalizzazione pesante, è possibile trarre vantaggio da una migrazione pianificata a SharePoint Online. È inoltre possibile che per l'ambiente SharePoint Server locale, si potrebbe scegliere di inserire alcuni dati in SharePoint Online per ridurre la quantità di gestione hardware che consente di mantenere tutti i dati in locale. Potrebbe essere più economico spostare alcuni dei dati in SharePoint Online.
  
> [!NOTE]
> Gli amministratori di SharePoint possono creare un abbonamento a Microsoft 365, impostare un nuovo sito di SharePoint Online e quindi eliminare SharePoint Server 2010, eliminando in modo pulito solo i documenti più essenziali per i siti di SharePoint Online freschi. Da qui, tutti i dati rimanenti possono essere svuotati dal sito di SharePoint Server 2010 in archivi locali. 
  
|**SharePoint Online**|**SharePoint Server locale**|
|:-----|:-----|
|Costo elevato nel tempo (piano/esecuzione/verifica)  <br/> |Costo elevato nel tempo (piano/esecuzione/verifica)  <br/> |
|Costi inferiori per i fondi (nessun acquisto hardware)  <br/> |Costo maggiore nei fondi (acquisti hardware)  <br/> |
|Costo di una tantum nella migrazione  <br/> |Costo di una tantum ripetuto per la migrazione futura  <br/> |
|Costo totale di proprietà/manutenzione basso  <br/> |Costo totale elevato di proprietà/manutenzione  <br/> |
   
Quando si esegue la migrazione a Microsoft 365, lo spostamento di una tantum avrà un costo più pesante nel tempo trascorso la pianificazione, l'up-front (durante l'organizzazione dei dati e la scelta di cosa prendere per il cloud e cosa lasciarsi alle spalle). Tuttavia, dopo la migrazione dei dati, gli aggiornamenti saranno automatici da quel momento, visto che non sarà più necessario gestire gli aggiornamenti hardware e software e il tempo di attesa della farm verrà eseguito da un contratto di servizio di Microsoft Service Level Agreement ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)).
  
### <a name="migrate-to-sharepoint-online"></a>Eseguire la migrazione a SharePoint Online

Assicurarsi che SharePoint Online offra tutte le funzionalità necessarie rivedendo la relativa [Descrizione del servizio](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).
  
Attualmente, non è possibile eseguire direttamente la migrazione da SharePoint Server 2010 (o SharePoint Foundation 2010) a SharePoint Online, in modo che gran parte del lavoro sia manuale. In questo modo è possibile archiviare e potare dati e siti non più necessari prima dello spostamento. È possibile archiviare altri dati nello spazio di archiviazione. Tenere inoltre presente che né SharePoint Server 2010 né SharePoint Foundation 2010 smetteranno di funzionare al termine del supporto, in modo che gli amministratori possano disporre di un periodo di tempo durante il quale SharePoint è ancora in esecuzione se i clienti dimenticano di spostare alcuni dati.
  
Se si esegue l'aggiornamento a SharePoint Server 2013 o SharePoint Server 2016 e si decide di inserire i dati in SharePoint Online, è possibile che lo spostamento comporti anche l'utilizzo dell' [API di migrazione di SharePoint](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) (per eseguire la migrazione delle informazioni in OneDrive for business). 
  
|**Vantaggio di SharePoint Online**|**Svantaggi di SharePoint Online**|
|:-----|:-----|
|Microsoft fornisce l'hardware di SPO e tutte le amministrazioni hardware.  <br/> |Le funzionalità disponibili possono essere diverse tra SharePoint Server locale e SPO.  <br/> |
|L'utente è l'amministratore globale dell'abbonamento e può assegnare gli amministratori ai siti SPO.  <br/> |Alcune azioni disponibili per un amministratore di farm in SharePoint Server locale non esistono (o non sono necessarie) nel ruolo di amministratore di SharePoint in Microsoft 365, ma l'amministrazione di SharePoint, l'amministrazione della raccolta siti e la proprietà del sito sono locali per l'organizzazione.  <br/> |
|Microsoft applica patch, correzioni e aggiornamenti per l'hardware e il software sottostante (inclusi i server SQL in cui viene eseguito SharePoint Online).  <br/> |Poiché non è disponibile alcun accesso al file system sottostante nel servizio, alcune personalizzazioni sono limitate.  <br/> |
|Microsoft pubblica [contratti a livello di servizio](https://go.microsoft.com/fwlink/?linkid=843153) e si sposta rapidamente per risolvere gli incidenti a livello di servizio.  <br/> |Il backup e il ripristino e altre opzioni di ripristino vengono automatizzati dal servizio in SharePoint Online-i backup vengono sovrascritti se non utilizzati.  <br/> |
|I test di sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguite su base continuativa del servizio da Microsoft.  <br/> |Le modifiche apportate all'interfaccia utente e ad altre funzionalità di SharePoint vengono installate dal servizio e possono essere attivate o disattivate.  <br/> |
|Microsoft 365 soddisfa molti standard del settore: [offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |L'assistenza di [FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) per la migrazione è limitata.  <br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di SPO descritta nella Guida di [orientamento al contenuto di SharePoint Online e OneDrive Migration](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Né gli ingegneri del supporto Microsoft né i dipendenti del datacenter dispongono dell'accesso amministratore illimitato all'abbonamento.  <br/> |Se è necessario aggiornare l'infrastruttura hardware per supportare la versione più recente di SharePoint o se è necessaria una farm secondaria per l'aggiornamento, è possibile che siano presenti costi aggiuntivi.  <br/> |
|I provider di soluzioni possono assistere con il processo di migrazione dei dati in una sola volta in SharePoint Online.  <br/> |Non tutte le modifiche apportate a SharePoint Online sono all'interno del controllo. Dopo la migrazione, la progettazione delle differenze nei menu, nelle raccolte e in altre funzionalità può influire temporaneamente sull'usabilità.  <br/> |
|I prodotti online vengono aggiornati automaticamente nel servizio, il che significa che se le funzionalità possono essere deprecate, non esiste un ciclo di vita di supporto reale.  <br/> |È presente una fine del ciclo di vita del supporto per SharePoint Server (o SharePoint Foundation), nonché per i server SQL sottostanti.  <br/> |
   
Se si è deciso di creare un nuovo sito Microsoft 365 e la migrazione dei dati viene eseguita manualmente come necessario, è possibile esaminare le opzioni di [microsoft 365](https://www.microsoft.com/microsoft-365/).
  

  
### <a name="upgrade-sharepoint-server-on-premises"></a>Aggiornare SharePoint Server locale

A partire dalla versione più recente del prodotto SharePoint locale (SharePoint Server 2019), gli aggiornamenti di SharePoint Server devono andare in  *serie*, il che significa che non esiste alcun modo per eseguire l'aggiornamento da sharepoint server 2010 a sharepoint server 2016 o a SharePoint 2019 direttamente. 
  
Percorso di aggiornamento seriale: 

- SharePoint Server 2010 \> SharePoint server 2013 \> sharepoint server 2016
   
Se si sceglie di seguire l'intero percorso da SharePoint 2010 a SharePoint Server 2016, questa operazione richiederà tempo e pianificazione. Gli aggiornamenti prevedono un costo in termini di hardware aggiornato (tenere presente che è necessario aggiornare anche SQL Server), il software e l'amministrazione. Inoltre, potrebbe essere necessario aggiornare o addirittura abbandonare le personalizzazioni. Prima di eseguire l'aggiornamento della farm di SharePoint Server, assicurarsi di raccogliere note su tutte le personalizzazioni critiche.
  
> [!NOTE]
> È possibile mantenere la fine del supporto per la farm di SharePoint 2010, installare una farm di SharePoint Server 2016 su un nuovo hardware (in modo che le farm separate vengano eseguite affiancate) e quindi pianificare ed eseguire una migrazione manuale del contenuto (per il download e il caricamento del contenuto, ad esempio). Sono possibili insidie per queste operazioni manuali, ad esempio i documenti provenienti da 2010 che dispongono di un account di Ultima modifica corrente con l'alias dell'account che esegue lo spostamento manuale, e che alcuni lavori devono essere eseguiti in anticipo (ricreare siti, siti secondari, autorizzazioni e strutture elenco). È opportuno prendere in considerazione i dati che è possibile spostare nello spazio di archiviazione o non è più necessario. Ciò può ridurre l'impatto della migrazione. In entrambi i casi, pulire l'ambiente prima dell'aggiornamento. Accertarsi che la farm esistente sia funzionale prima di eseguire l'aggiornamento e (di sicuro) prima di rimuovere le autorizzazioni. 
  
Tenere presente i **percorsi di aggiornamento supportati e non consolidati**: 
  
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Se si dispone di **personalizzazioni**, è importante disporre di un piano di aggiornamento per ogni passaggio del percorso di migrazione: 
  
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Vantaggi locali**|**Svantaggi locali**|
|:-----|:-----|
|Controllo completo di tutti gli aspetti della farm di SharePoint (ed è SQL), dall'hardware del server verso l'alto.  <br/> |Tutte le interruzioni e le correzioni sono responsabili della società (ma è possibile coinvolgere il supporto tecnico Microsoft se il prodotto non è alla fine del supporto tecnico):  <br/> |
|Set di funzionalità completo di SharePoint Server locale con l'opzione di connettere la farm locale a un abbonamento a SharePoint Online tramite ibrido.  <br/> |L'aggiornamento, le patch, le correzioni alla sicurezza, gli aggiornamenti hardware e tutte le operazioni di manutenzione di SharePoint Server e della farm SQL sono gestiti in locale.  <br/> |
|Accesso completo per le opzioni di personalizzazione maggiori rispetto a SharePoint Online.  <br/> |Le [offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devono essere configurate manualmente in locale.  <br/> |
|Test di sicurezza e ottimizzazione delle prestazioni del server, eseguite nei locali (sotto il controllo).  <br/> |Microsoft 365 può rendere disponibili le funzionalità di SharePoint Online che non interagiscono con SharePoint Server locale  <br/> |
|I provider di soluzioni possono assistere alla migrazione dei dati alla prossima versione di SharePoint Server e oltre.  <br/> |I siti di SharePoint Server non utilizzeranno automaticamente i certificati [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) come mostrato in SharePoint Online.  <br/> |
|Controllo completo delle convenzioni di denominazione, del backup e del ripristino e di altre opzioni di ripristino in SharePoint Server locale.  <br/> |SharePoint Server locale è sensibile ai ciclo di vita del prodotto.  <br/> |
   
### <a name="upgrade-resources"></a>Risorse per l'aggiornamento

Iniziare confrontando i requisiti hardware e software. Se non si soddisfano i requisiti di base per l'aggiornamento sull'hardware corrente, ciò può significare che è necessario aggiornare prima l'hardware della farm o SQL Server oppure che è possibile decidere di spostare una determinata percentuale dei siti nell'hardware ' Evergreen ' di SharePoint Online. Dopo aver effettuato la valutazione, seguire i percorsi e i metodi di aggiornamento supportati.
  
- **Requisiti hardware e software per**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Limiti software e limitazioni per**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Panoramica del processo di aggiornamento per**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-sharepoint-server-on-premises"></a>Creare una soluzione ibrida di SharePoint tra SharePoint Online e SharePoint Server locale

Un'altra opzione (che potrebbe essere la migliore sia dei mondi locali che di quelli online per alcune esigenze di migrazione) è un ibrido, è possibile connettere le farm di SharePoint Server 2013 o 2016 o 2019 a SharePoint Online per creare un ibrido di SharePoint: [informazioni sulle soluzioni ibride di SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).
  
Se si decide che la farm di SharePoint Server ibrida è l'obiettivo della migrazione, assicurarsi di pianificare i siti e gli utenti che devono essere spostati in linea e che devono rimanere in locale. La revisione e la classificazione del contenuto della farm di SharePoint Server (determinare quali dati sono ad alto, medio o basso impatto per la società) possono essere utili per prendere questa decisione. Potrebbe essere che l'unica cosa che è necessario condividere con SharePoint Online è (a) gli account utente per l'accesso e (b) l'indice di ricerca di SharePoint Server--potrebbe non essere chiaro fino a quando non si esamina la modalità di utilizzo dei siti. Se successivamente la società decide di eseguire la migrazione di tutti i contenuti in SharePoint Online, è possibile spostare tutti gli account e i dati rimanenti online e rimuovere le autorizzazioni per la farm locale e la gestione e l'amministrazione della farm di SharePoint verranno eseguite tramite le console di Microsoft 365 da quel momento in poi.
  
Assicurarsi di acquisire familiarità con i tipi di ibrido esistenti e come configurare la connessione tra la farm di SharePoint locale e la sottoscrizione Microsoft 365.

| Opzione | Descrizione |
|:-----|:-----|
|[Offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).  <br/> |L'assistenza di [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) per la migrazione è limitata.  <br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di SPO descritta nella Guida di [orientamento al contenuto di SharePoint Online e OneDrive Migration](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
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
> Tenere presente che la farm di SharePoint Server 2010 deve prima essere aggiornata, in locale, a SharePoint Server 2013 o SharePoint Server 2016 per utilizzare l'opzione ibrida. SharePoint Foundation 2010 e SharePoint Foundation 2013 non sono in grado di creare connessioni ibride con SharePoint Online. 

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Riepilogo delle opzioni per il client e i server di Office 2010 e Windows 7

Per un riepilogo visivo delle opzioni di aggiornamento, migrazione e passaggio al cloud per i client e i server di Office 2010 e Windows 7, vedere il [poster relativo alla fine del supporto](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Immagine del poster per la fine del supporto per client e server di Office 2010 e Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Questo poster di una pagina rappresenta un modo rapido per comprendere i vari percorsi che è possibile eseguire per evitare che i prodotti client e server di Office 2010 e Windows 7 raggiungano la fine del supporto, evidenziando i percorsi preferiti e il supporto delle opzioni in Microsoft 365 Enterprise.

È anche possibile [scaricare il poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).
        
## <a name="related-topics"></a>Argomenti correlati

[Risorse utili per l'aggiornamento da server e client di Office 2007 o 2010](upgrade-from-office-2010-servers-and-products.md)
  
[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)
  
[Procedure consigliate per l'aggiornamento da SharePoint 2010 a SharePoint 2013](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)
  
[Risolvere i problemi relativi all'aggiornamento dei database in SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Cercare i provider di soluzioni Microsoft per agevolare l'aggiornamento](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Criterio di manutenzione del prodotto aggiornato per SharePoint 2013](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)
  
[Criteri di manutenzione del prodotto aggiornati per SharePoint Server 2016](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
  

