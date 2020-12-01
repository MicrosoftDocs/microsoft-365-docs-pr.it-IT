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
description: Trovare informazioni e risorse per l'aggiornamento da SharePoint 2010 e SharePoint Server 2010. Supporto per entrambe le estremità del 13 aprile 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fba095a15164f8a09ce1e0a1cbd5ee9cd298aa74
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519764"
---
# <a name="upgrading-from-sharepoint-2010"></a>Aggiornamento da SharePoint 2010

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Microsoft SharePoint 2010 e SharePoint Server 2010 potranno raggiungere la fine del supporto del **13 aprile 2021**. In questo articolo vengono fornite risorse che consentono di eseguire la migrazione dei dati di SharePoint Server 2010 esistenti a SharePoint online in Microsoft 365 o di aggiornare l'ambiente SharePoint Server 2010 locale.

## <a name="what-is-end-of-support"></a>Che cos'è la *fine del supporto tecnico*?

La maggior parte dei prodotti Microsoft ha un ciclo di vita di supporto, durante il quale vengono riportate nuove funzionalità, correzioni di bug, correzioni di sicurezza e così via. Dopo la data di fine del supporto, il prodotto non smette di funzionare, ma Microsoft non fornisce più:

- Supporto tecnico per i problemi che possono verificarsi.

- Correzioni degli errori relativi a problemi che possono influire sulla stabilità e sull'usabilità del server.

- Correzioni per la sicurezza per vulnerabilità che potrebbero rendere il server vulnerabile alle violazioni della sicurezza.

- Aggiornamenti del fuso orario.

Questo significa che non saranno disponibili ulteriori aggiornamenti, patch o correzioni per il prodotto (incluse le patch di sicurezza/correzioni). Il supporto tecnico Microsoft avrà spostato completamente gli sforzi di supporto per le versioni più recenti.

Come la fine del supporto di SharePoint Server 2010 approcci, eliminare i dati che non sono più necessari prima di aggiornare il prodotto e migrare i dati importanti.

> [!NOTE]
> Il ciclo di vita del software è in genere di dieci anni rispetto alla versione iniziale. I [provider di soluzioni Microsoft](https://go.microsoft.com/fwlink/?linkid=841249) possono essere utili per eseguire l'aggiornamento alla versione successiva del software o per eseguire la migrazione a Microsoft 365 Migration (o entrambi). Assicurarsi di essere a conoscenza delle date di fine del supporto per le tecnologie sottostanti critiche, in particolare per la versione di Microsoft SQL Server che si sta utilizzando con SharePoint. Per ulteriori informazioni, vedere [criterio del ciclo](https://support.microsoft.com/help/14085)di vita fisso.

## <a name="plan-ahead"></a>Pianificare in anticipo

Controllare le date di fine del supporto nel [sito del ciclo](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)di vita del prodotto. Pianificare gli aggiornamenti o le migrazioni con queste date in mente. Tenere presente che il prodotto *non smetterà di funzionare* alla data indicata. Tuttavia, dal momento che l'installazione non verrà più applicata dopo tale data, sarà necessario pianificare una transizione graduale alla versione successiva del prodotto.

Questa matrice consente di tracciare un corso tra le opzioni di migrazione:

|Fine del prodotto di supporto|Buone |Elevate|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (in locale)|SharePoint Online|
||SharePoint Server 2013 ibrido con SharePoint Online|SharePoint Server 2016 (in locale)|
|||Ricerca ibrida cloud di SharePoint|

Se si sceglie un'opzione all'estremità bassa della scala (buona), sarà necessario iniziare a pianificare un altro aggiornamento subito dopo la migrazione da SharePoint Server 2010.

Di seguito sono riportati i tre percorsi che è possibile eseguire per evitare la fine del supporto per SharePoint Server 2010.

![Percorsi di aggiornamento di SharePoint Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> La fine del supporto per SharePoint Server 2010 e SharePoint Foundation 2010 è attualmente pianificata per il 13 aprile 2021. Assicurarsi tuttavia di controllare il [sito del ciclo](https://support.microsoft.com/lifecycle) di vita del prodotto per le date più aggiornate.

## <a name="whats-next"></a>Operazioni successive

SharePoint Server 2013 e SharePoint Foundation 2013 possono essere installati in locale nei propri server. In alternativa, è possibile utilizzare SharePoint Online, che è un servizio online che fa parte di Microsoft 365. È possibile scegliere di:

- Eseguire la migrazione a SharePoint Online.

- Aggiornare SharePoint Server o SharePoint Foundation in locale.

- Eseguire entrambe le operazione sopra riportate.

- Implementare una soluzione [ibrida di SharePoint](https://docs.microsoft.com/sharepoint/hybrid/hybrid) .

Si consideri i costi nascosti della gestione di una server farm, tra cui la gestione o la migrazione delle personalizzazioni e l'aggiornamento dell'hardware. Se sono stati contabilizzati questi fattori, sarà più facile eseguire l'aggiornamento in locale. Se si esegue la farm nei server di SharePoint Legacy senza una personalizzazione pesante, è possibile trarre vantaggio da una migrazione pianificata a SharePoint Online. Per un ambiente SharePoint Server locale, è anche possibile prendere in considerazione lo spostamento di alcuni dati in SharePoint Online per ridurre il sovraccarico di gestione hardware.

> [!NOTE]
> Gli amministratori di SharePoint possono creare una sottoscrizione di Microsoft 365, impostare nuovi siti di SharePoint Online e quindi eliminare da SharePoint Server 2010 in modo pulito, tenendo solo i documenti essenziali per i siti recenti. Successivamente, tutti i dati rimanenti possono essere svuotati dal sito di SharePoint Server 2010 in archivi locali.

|SharePoint Online|SharePoint Server locale|
|---|---|
|Costo elevato nel tempo (piano/esecuzione/verifica)|Costo elevato nel tempo (piano/esecuzione/verifica)|
|Costi inferiori per i fondi (nessun acquisto hardware)|Costo maggiore nei fondi (acquisti hardware)|
|Costo di una tantum nella migrazione|Costo di una tantum ripetuto per la migrazione futura|
|Costo totale di proprietà/manutenzione basso|Costo totale elevato di proprietà/manutenzione|

Un trasferimento di una tantum a Microsoft 365 avrà un costo maggiore durante l'organizzazione dei dati e deciderà cosa prendere nel cloud e cosa lasciarsi alle spalle. Tuttavia, dopo la migrazione dei dati, gli aggiornamenti futuri saranno automatici, in quanto non è più necessario gestire gli aggiornamenti hardware e software. Il tempo di attesa della farm verrà eseguito da un [contratto di servizio di Microsoft Service Level Agreement (SLA)](https://go.microsoft.com/fwlink/?linkid=843153).

### <a name="migrate-to-sharepoint-online"></a>Eseguire la migrazione a SharePoint Online

Assicurarsi che SharePoint Online offra tutte le funzionalità necessarie. Vedere la [Descrizione del servizio SharePoint](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

Non è possibile eseguire la migrazione direttamente da SharePoint Server 2010 (o SharePoint Foundation 2010) a SharePoint Online. La maggior parte del lavoro di migrazione è manuale. Tuttavia, in questa fase è possibile potare dati e siti non più necessari prima dello spostamento. È possibile archiviare altri dati nello spazio di archiviazione. 

Tenere presente che SharePoint Server 2010 e SharePoint Foundation 2010 non smetteranno di funzionare al termine del supporto. In questo modo gli amministratori possono disporre di un periodo in cui SharePoint è ancora in esecuzione se i clienti dimenticano di spostare alcuni dati.

Se si esegue l'aggiornamento a SharePoint Server 2013 o SharePoint Server 2016 e si decide di inserire i dati in SharePoint Online, è possibile utilizzare l' [API di migrazione di SharePoint](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) per eseguire la migrazione delle informazioni in OneDrive for business.

|Vantaggio di SharePoint Online|Svantaggi di SharePoint Online|
|---|---|
|Microsoft fornisce l'hardware di SPO e tutte le amministrazioni hardware.|Le funzionalità disponibili possono variare tra SharePoint Server locale e SPO.|
|L'utente è l'amministratore globale dell'abbonamento e può assegnare gli amministratori ai siti SPO.|Alcune azioni disponibili per un amministratore di farm in SharePoint Server locale non esistono (o non sono necessarie) nel ruolo di amministratore di SharePoint in Microsoft 365. Tuttavia, l'amministrazione di SharePoint, l'amministrazione della raccolta siti e la proprietà del sito sono locali per l'organizzazione.|
|Microsoft applica patch, correzioni e aggiornamenti per l'hardware e il software sottostanti, inclusi i server SQL su cui viene eseguito SharePoint Online.|Poiché non è possibile accedere al file system sottostante nel servizio, la personalizzazione è limitata.|
|Microsoft pubblica [contratti a livello di servizio](https://go.microsoft.com/fwlink/?linkid=843153) e si sposta rapidamente per risolvere gli incidenti a livello di servizio.|Backup e ripristino e altre opzioni di ripristino vengono automatizzate dal servizio in SharePoint Online. I backup vengono sovrascritti se non utilizzati.|
|Test di sicurezza e ottimizzazione delle prestazioni del server vengono eseguite continuamente nel servizio da Microsoft.|Le modifiche apportate all'interfaccia utente e ad altre funzionalità di SharePoint vengono installate dal servizio e possono essere attivate o disattivate.|
|Microsoft 365 soddisfa molti standard del settore: [offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).|L'assistenza di [FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) per la migrazione è limitata.  <br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di SPO descritta nella Guida di [orientamento al contenuto di SharePoint Online e OneDrive Migration](https://go.microsoft.com/fwlink/?linkid=843184).|
|Gli ingegneri del supporto tecnico Microsoft e i dipendenti del datacenter non dispongono dell'accesso di amministratore illimitato all'abbonamento.|Se è necessario aggiornare l'infrastruttura hardware per supportare la versione più recente di SharePoint o se è necessaria una farm secondaria per l'aggiornamento, è possibile che siano presenti costi aggiuntivi.|
|I provider di soluzioni consentono di eseguire la migrazione dei dati in SharePoint online in una sola volta.|Non tutte le modifiche apportate a SharePoint Online sono all'interno del controllo. Dopo la migrazione, la progettazione delle differenze nei menu, nelle raccolte e in altre funzionalità può influire temporaneamente sull'usabilità.|
|I prodotti online vengono aggiornati automaticamente all'interno del servizio. Le funzionalità potrebbero essere obsolete, ma non esiste alcun ciclo di vita del supporto.|È presente un ciclo di vita di fine del supporto per SharePoint Server o SharePoint Foundation e server SQL sottostanti.|

Se si è deciso di creare un nuovo sito Microsoft 365 e di eseguirne manualmente la migrazione dei dati, vedere le [Opzioni di microsoft 365](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Aggiornare SharePoint Server locale

A partire da SharePoint Server 2019, gli aggiornamenti devono andare in  *sequenza*. Non è possibile eseguire l'aggiornamento da SharePoint Server 2010 a SharePoint Server 2016 o a SharePoint 2019 direttamente. Percorso di aggiornamento seriale:

- SharePoint Server 2010 \> SharePoint server 2013 \> sharepoint server 2016

Richiederà tempo e pianificazione per seguire l'intero percorso da SharePoint 2010 a SharePoint Server 2016. Gli aggiornamenti coinvolgono i costi per l'hardware (devono essere aggiornati anche i server SQL), il software e l'amministrazione. Inoltre, potrebbe essere necessario aggiornare o persino abbandonare le personalizzazioni. Assicurarsi di documentare le personalizzazioni critiche prima di eseguire l'aggiornamento della farm di SharePoint Server.

> [!NOTE]
> È possibile mantenere la farm di SharePoint 2010 di supporto finale, installare una farm di SharePoint Server 2016 su un nuovo hardware (in modo che le farm separate vengano eseguite affiancate) e quindi pianificare ed eseguire una migrazione manuale del contenuto (per il download e il caricamento del contenuto, ad esempio). Tuttavia, esistono possibili insidie per questi spostamenti manuali, ad esempio i documenti provenienti da 2010 che dispongono di un account Last-modified corrente con l'alias dell'account che esegue lo spostamento manuale. Alcuni lavori devono essere eseguiti in anticipo, ad esempio la ricreazione di siti, sottositi, autorizzazioni e strutture di elenchi. Assicurarsi di pulire l'ambiente prima dell'aggiornamento. Si consideri quali dati è possibile spostare nello spazio di archiviazione o non è più necessario. Ciò può ridurre l'impatto della migrazione. Accertarsi che la farm esistente sia funzionale prima di eseguire l'aggiornamento e (certamente) prima di rimuovere le autorizzazioni.

Tenere presente i *percorsi di aggiornamento supportati e non consolidati*:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Se si dispone di *personalizzazioni*, è importante pianificare ogni passaggio del percorso di migrazione:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Vantaggi locali|Svantaggi locali|
|---|---|
|Controllo completo di tutti gli aspetti della farm di SharePoint (e del relativo SQL), dall'hardware del server verso l'alto.|Tutte le interruzioni e le correzioni sono responsabili della società. Tuttavia, è possibile coinvolgere il supporto tecnico Microsoft se il prodotto non è stato superato.|
|Set di funzionalità completo di SharePoint Server locale con l'opzione di connettere la farm locale a un abbonamento a SharePoint Online tramite ibrido.|L'aggiornamento, le patch, le correzioni per la sicurezza, gli aggiornamenti hardware e tutte le operazioni di manutenzione di SharePoint Server e della relativa farm SQL vengono gestite in locale.|
|Accesso completo per le opzioni di personalizzazione maggiori rispetto a SharePoint Online.|Le [offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devono essere configurate manualmente in locale.|
|I test di sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguite nella propria sede sotto il proprio controllo.|Microsoft 365 può rendere disponibili le funzionalità di SharePoint Online che non interagiscono con SharePoint Server locale.|
|I provider di soluzioni possono contribuire alla migrazione dei dati alla prossima versione di SharePoint Server e oltre.|I siti di SharePoint Server non utilizzeranno automaticamente i certificati [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) come mostrato in SharePoint Online.|
|Controllo completo delle convenzioni di denominazione e backup e ripristino e altre opzioni di ripristino in SharePoint Server locale.|SharePoint Server locale è sensibile ai ciclo di vita del prodotto.|

### <a name="upgrade-resources"></a>Risorse per l'aggiornamento

Iniziare confrontando i requisiti hardware e software. Se l'ambiente corrente non soddisfa i requisiti di base, potrebbe essere necessario aggiornare prima l'hardware della farm o dei server SQL. 

È possibile decidere di spostare alcuni dei siti nell'hardware "Evergreen" di SharePoint Online. Dopo aver effettuato la valutazione, seguire i percorsi e i metodi di aggiornamento supportati.

- *Requisiti hardware e software per:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Limiti software e limitazioni per:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *Panoramica del processo di aggiornamento per:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Creare una soluzione ibrida con SharePoint Online e SharePoint Server locale

Un programma di installazione ibrido fornisce il meglio sia in locale che online per alcune esigenze di migrazione. È possibile connettere le farm di SharePoint Server 2013, 2016 o 2019 a SharePoint Online per creare un ambiente ibrido di SharePoint: [informazioni sulle soluzioni ibride](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)di SharePoint.

Se una farm di SharePoint Server ibrida è l'obiettivo di migrazione, determinare quali siti e utenti spostare online e che devono rimanere in locale. Classificare il contenuto della farm di SharePoint Server come impatto alto, medio o basso per la società può essere di aiuto per questa decisione. Potrebbe essere necessario condividere solo gli account utente per l'accesso e l'indice di ricerca di SharePoint Server con SharePoint Online. Tuttavia, questo fattore potrebbe non essere chiaro fino a quando non si esamina la modalità di utilizzo dei siti. Se successivamente la società decide di eseguire la migrazione di tutto il contenuto in SharePoint Online, è possibile spostare tutti gli account e i dati rimanenti online e rimuovere le autorizzazioni per la farm locale. La gestione e l'amministrazione della farm di SharePoint verranno eseguite tramite le console di Microsoft 365 da quel momento in poi.

Assicurarsi di acquisire familiarità con i tipi di ibridi esistenti e come configurare la connessione tra la farm di SharePoint locale e la sottoscrizione Microsoft 365.

|Opzione|Descrizione|
|---|---|
|[Offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165).|L'assistenza di [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) per la migrazione è limitata.<br/><br/> Gran parte dell'aggiornamento sarà manuale o tramite l'API di migrazione di SPO descritta nella Guida di [orientamento al contenuto di SharePoint Online e OneDrive Migration](https://go.microsoft.com/fwlink/?linkid=843184).|
|Gli ingegneri del supporto tecnico Microsoft e i dipendenti del datacenter non dispongono dell'accesso di amministratore illimitato all'abbonamento.|Se è necessario aggiornare l'infrastruttura hardware per supportare la versione più recente di SharePoint o se è necessaria una farm secondaria, potrebbero essere necessari ulteriori costi.|
|I partner possono assistere con il processo monouso di migrazione dei dati a SharePoint Online.||
|I prodotti online vengono aggiornati automaticamente all'interno del servizio. Le funzionalità potrebbero essere obsolete, ma non esiste alcun vero fine del supporto.||

Se si è deciso di creare un nuovo sito Microsoft 365 e di eseguire manualmente la migrazione dei dati in base alle esigenze, vedere le [Opzioni di microsoft 365](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Aggiornare SharePoint Server locale

Non è possibile ignorare le versioni negli aggiornamenti di SharePoint. Questo significa che gli aggiornamenti vanno in sequenza:

- SharePoint 2007 \> SharePoint server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016

Per utilizzare l'intero percorso da SharePoint 2007 a SharePoint Server 2016, si verificherà un notevole investimento nel tempo e si verificherà l'hardware (devono essere aggiornati anche SQL Server), i costi di gestione e di software. Le personalizzazioni dovranno essere aggiornate o abbandonate, in base alla criticità della caratteristica.

> [!NOTE]
> È possibile mantenere la farm di SharePoint 2007 di fine vita, installare una farm di SharePoint Server 2016 su un nuovo hardware (in modo che le farm separate vengano eseguite affiancate) e quindi pianificare ed eseguire una migrazione manuale del contenuto, ad esempio per il download e il caricamento del contenuto. Tuttavia, sono presenti alcuni svantaggi di questi spostamenti manuali, ad esempio lo spostamento di documenti che sostituiscono l'ultimo account modificato con l'alias dell'account che esegue il trasferimento manuale. È necessario che il lavoro venga svolto in anticipo, ad esempio ricreando siti, sottositi, autorizzazioni e strutture di elenchi. In ogni caso, prendere in considerazione i dati che è possibile spostare nello spazio di archiviazione o non è più necessario ridurre l'impatto della migrazione.

Assicurarsi di pulire l'ambiente prima dell'aggiornamento. Accertarsi che la farm esistente sia funzionale prima di eseguire l'aggiornamento e, certamente, prima di rimuovere le autorizzazioni.

Tenere presente i *percorsi di aggiornamento supportati e non consolidati*:

- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Se si dispone di *personalizzazioni*, è importante pianificare l'aggiornamento per ogni passaggio del percorso di migrazione:

- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Pro locale|Con in locale|
|---|---|
|Controllo completo di tutti gli aspetti della farm di SharePoint, dall'hardware del server verso l'alto.|Tutte le interruzioni e le correzioni sono responsabili della società. Tuttavia, è possibile coinvolgere il supporto tecnico Microsoft se il prodotto non è stato superato.|
|Set di funzionalità completo di SharePoint Server locale con l'opzione di connettere la farm locale a un abbonamento a SharePoint Online tramite ibrido.|Aggiornamento, patch, correzioni per la sicurezza e tutte le operazioni di manutenzione di SharePoint Server gestite in locale.|
|Accesso completo per una maggiore personalizzazione.|Le [offerte di conformità Microsoft](https://go.microsoft.com/fwlink/?linkid=843165) devono essere configurate manualmente in locale.|
|La verifica della sicurezza e l'ottimizzazione delle prestazioni del server vengono eseguite nella propria sede sotto il proprio controllo.|Microsoft 365 può rendere disponibili le funzionalità di SharePoint Online che non interagiscono con SharePoint Server locale.|
|I partner possono contribuire alla migrazione dei dati alla prossima versione di SharePoint Server e oltre.|I siti di SharePoint Server non utilizzeranno automaticamente i certificati [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) come mostrato in SharePoint Online.|
|Controllo completo delle convenzioni di denominazione e backup e ripristino e altre opzioni di ripristino in SharePoint Server locale.|SharePoint Server locale è sensibile ai ciclo di vita del prodotto.|

### <a name="upgrade-resources"></a>Risorse per l'aggiornamento

Per iniziare, è necessario conoscere i requisiti hardware e software e quindi seguire i metodi di aggiornamento supportati.

- *Requisiti hardware e software per*:

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Limiti software e limitazioni per*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *Panoramica del processo di aggiornamento per*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Creare una soluzione ibrida di SharePoint tra SharePoint Online e in locale

Se la risposta alla migrazione deve essere compresa tra il controllo offerto da locale e il costo di proprietà più basso offerto da SharePoint Online, è possibile connettere le farm di SharePoint Server 2013 o 2016 a SharePoint Online tramite ibridi. [Informazioni sulle soluzioni ibride di SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Se si decide che una farm di SharePoint Server ibrida trarrà vantaggio dalla propria azienda, acquisire familiarità con i tipi di ibridi esistenti e come configurare la connessione tra la farm di SharePoint locale e la sottoscrizione Microsoft 365.

È possibile creare un ambiente di sviluppo e di testing di Microsoft 365, che è possibile configurare con le [guide dei laboratori di testing](m365-enterprise-test-lab-guides.md). Dopo aver ottenuto un abbonamento di valutazione o acquistato Microsoft 365, è possibile creare le raccolte siti, i siti Web e le raccolte documenti in SharePoint Online a cui è possibile eseguire la migrazione dei dati. È possibile eseguire la migrazione manuale, tramite l'API di migrazione, oppure, se si desidera eseguire la migrazione del contenuto del sito personale a OneDrive for business, tramite la procedura guidata ibrida.

> [!NOTE]
> Per utilizzare l'opzione ibrido, è necessario che la farm di SharePoint Server 2010 sia stata aggiornata in locale a SharePoint Server 2013 o 2016. SharePoint Foundation 2010 e SharePoint Foundation 2013 non supportano connessioni ibride con SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Riepilogo delle opzioni per il client e i server di Office 2010 e Windows 7

Per un riepilogo visivo delle opzioni di aggiornamento, migrazione e passaggio al cloud per i client e i server di Office 2010 e Windows 7, vedere il [poster relativo alla fine del supporto](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fine del supporto per i client e i server di Office 2010 e il poster di Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

In questo poster vengono illustrati i vari percorsi che è possibile eseguire per evitare i prodotti client e server di Office 2010 e la fine del supporto di Windows 7, con i percorsi e i supporti di opzione Preferiti in Microsoft 365 Enterprise evidenziati.

È anche possibile [scaricare](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) questo poster e stamparlo nel formato lettera, legale o tabloid (11 x 17).

## <a name="related-articles"></a>Articoli correlati

[Risorse utili per l'aggiornamento da server e client di Office 2007 o 2010](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)

[Procedure consigliate per l'aggiornamento da SharePoint 2010 a SharePoint 2013](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)

[Risolvere i problemi relativi all'aggiornamento dei database in SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)

[Cercare i provider di soluzioni Microsoft per agevolare l'aggiornamento](https://go.microsoft.com/fwlink/?linkid=841249)

[Criterio di manutenzione del prodotto aggiornato per SharePoint 2013](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)

[Criteri di manutenzione del prodotto aggiornati per SharePoint Server 2016](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
