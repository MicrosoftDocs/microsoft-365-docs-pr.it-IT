---
title: Guida sulla fine del supporto di Project Server 2007
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: Il 10 ottobre 2017, il supporto è terminato per Project Server 2007, Project Portfolio Server e Project 2007. Utilizzare questo articolo per pianificare l'aggiornamento ora.
ms.openlocfilehash: 12447eb2a021b3f92e3557b2c3ea87e859841346
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927349"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Guida sulla fine del supporto di Project Server 2007

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Il supporto è terminato per i server e le applicazioni di Office 2007 nel 2017 ed è necessario prendere in considerazione i piani per la migrazione. Se attualmente si utilizza Project Server 2007 e i prodotti correlati, prendere nota delle date di fine supporto seguenti:
  
|**Prodotto**|**Data fine supporto**|
|:-----|:-----|
|Project Server 2007  <br/> |10 ottobre 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 ottobre 2017  <br/> |
|Project 2007 Standard  <br/> |10 ottobre 2017  <br/> |
|Project 2007 Professional  <br/> |10 ottobre 2017  <br/> |
   
Per ulteriori informazioni sui server Office 2007 che stanno per ritirarsi, vedere [Upgrade from Office 2007 servers and client products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>Cosa significa *fine del* supporto?

La maggior parte dei prodotti Microsoft ha un ciclo di vita del supporto durante il quale ottengono nuove funzionalità, correzioni di bug, correzioni di sicurezza e così via. Questo ciclo di vita in genere dura 10 anni dal rilascio iniziale del prodotto. La fine di questo ciclo di vita è nota come fine del supporto del prodotto. Poiché Project Server 2007 ha raggiunto la fine del supporto il 10 ottobre 2017, Microsoft non fornisce più:
  
- Supporto tecnico per i problemi che possono verificarsi.
    
- Correzioni di bug per i problemi che possono influire sulla stabilità e sull'usabilità del server.
    
- Correzioni della sicurezza per le vulnerabilità che possono rendere il server vulnerabile alle violazioni della sicurezza.
    
- Aggiornamenti del fuso orario.
    
L'installazione di Project Server 2007 continuerà a essere eseguita dopo questa data. Tuttavia, a causa delle modifiche elencate in precedenza, è consigliabile eseguire la migrazione da Project Server 2007 non appena possibile.
  
## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

Se si utilizza Project Server 2007, è necessario esplorare le opzioni di migrazione, ovvero:
  
- Eseguire la migrazione a Project Online
    
- Eseguire la migrazione a una versione locale più recente di Project Server (preferibilmente Project Server 2016)
    
|**Perché preferirei eseguire la migrazione a Project Online**|**Perché preferirei eseguire la migrazione a Project Server 2016**|
|:-----|:-----|
| Ho utenti mobili.  <br/> <br/>I costi per la migrazione sono un problema significativo (hardware, software, ore e impegno da implementare). <br/><br/>  Dopo la migrazione, i costi per la manutenzione dell'ambiente sono una delle principali preoccupazioni (ad esempio, aggiornamenti automatici, tempi di attività garantiti e così via).  <br/> | Le regole business mi limitano a utilizzare la mia azienda nel cloud.<br/><br/>  È necessario controllare gli aggiornamenti dell'ambiente.  |
   
> [!NOTE]
> Per ulteriori informazioni sulle opzioni per lo spostamento dai server Office 2007, vedere [Resources to help you upgrade from Office 2007 servers and clients](upgrade-from-office-2007-servers-and-products.md). Si noti che Project Server non supporta una configurazione ibrida, perché Project Server e Project Online non possono condividere lo stesso pool di risorse. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Considerazioni importanti per la migrazione da Project Server 2007

Quando si prevede di eseguire la migrazione da Project Server 2007, considerare quanto segue:
  
- **Ottenere assistenza da un partner Microsoft** - L'aggiornamento da Project Server 2007 può essere impegnativo e richiede una preparazione e una pianificazione molto impegnative. Potrebbe essere particolarmente difficile se non si è la persona che ha configurato inizialmente Project Server 2007. Fortunatamente, ci sono partner Microsoft che possono aiutare, sia che si prevede di eseguire la migrazione a Project Server 2016 o a Project Online. Cercare un partner Microsoft per facilitare la migrazione nel [Centro per i partner Microsoft.](https://go.microsoft.com/fwlink/p/?linkid=841249) Cercare il termine  *Gold Project and Portfolio Management* per visualizzare un elenco di tutti i partner Microsoft con esperienza in Project. 
    
- **Pianificare le personalizzazioni:** molte delle personalizzazioni apportate nell'ambiente Project Server 2007 potrebbero non funzionare quando si esegue la migrazione a Project Server 2016 o Project Online. Esistono differenze significative nell'architettura di Project Server tra le versioni. Anche i sistemi operativi, i server di database e i Web browser client supportati sono diversi. Pianificare come testare o ricreare le personalizzazioni per il nuovo ambiente. La pianificazione offre inoltre una buona opportunità per valutare se ogni personalizzazione è ancora necessaria. Per ulteriori informazioni, vedere [Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013). 
    
- **Tempo e pazienza:** la pianificazione, l'esecuzione e il testing dell'aggiornamento richiederanno tempo e fatica, soprattutto se si esegue l'aggiornamento a Project Server 2016. Ad esempio, se si esegue la migrazione da Project Server 2007 a Project Server 2016, è innanzitutto necessario eseguire la migrazione a Project Server 2010, controllare i dati e quindi eseguire la stessa operazione quando si esegue la migrazione a ogni versione successiva. È consigliabile rivolgersi a un partner Microsoft per ottenere stime del tempo necessario e del costo.
    
## <a name="migrate-to-project-online"></a>Eseguire la migrazione a Project Online

Se si sceglie di eseguire la migrazione da Project Server 2007 a Project Online, è possibile eseguire le operazioni seguenti per eseguire manualmente la migrazione dei dati del piano di progetto:
  
1. Salvare i piani di progetto da Project Server 2003 in formato mpp.
    
2. In Project Professional 2013, Project Professional 2016 o project online Desktop Client, aprire ogni file mpp e quindi salvarlo e pubblicarlo in Project Online.
    
È possibile creare manualmente la configurazione di Microsoft Project Web App (PWA) in Project Online. Ad esempio, ricreare i campi personalizzati o i calendari dell'organizzazione necessari. I partner Microsoft possono anche aiutare con questo processo.
  
Risorse chiave:
  
|**Risorsa**|**Descrizione**|
|:-----|:-----|
|[Introduzione a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Come configurare e usare Project Online <br/> |
|[Descrizioni dei servizi di Project Online](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |Informazioni sui diversi piani di Project Online disponibili <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Eseguire la migrazione a una versione locale più recente di Project Server

Riteniamo fermamente di ottenere il miglior valore e l'esperienza utente eseguendo la migrazione a Project Online. Tuttavia, sappiamo anche che alcune organizzazioni devono conservare i dati del progetto in un ambiente locale. Se si sceglie di mantenere i dati del progetto in locale, è possibile eseguire la migrazione dell'ambiente di Project Server 2007 a Project Server 2010, Project Server 2013 o Project Server 2016.
  
Se non è possibile eseguire la migrazione a Project Online, è consigliabile eseguire la migrazione a Project Server 2016. Project Server 2016 include tutte le funzionalità delle versioni precedenti di Project Server. Corrisponde maggiormente all'esperienza disponibile con Project Online, anche se alcune funzionalità sono disponibili solo in Project Online.
  
Dopo ogni migrazione, è consigliabile verificare che la migrazione dei dati sia stata eseguita correttamente.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Come si esegue la migrazione a Project Server 2016?

Le differenze architetturali tra Project Server 2007 e Project Server 2016 impediscono un percorso di migrazione diretta. È quindi necessario eseguire la migrazione dei dati di Project Server 2007 a ogni versione successiva di Project Server fino a raggiungere Project Server 2016.
  
Seguire questa procedura per Project Server 2016:
  
1. Eseguire la migrazione da Project Server 2007 a Project Server 2010.
    
2. Eseguire la migrazione da Project Serve 2010 a Project Server 2013.
    
3. Eseguire la migrazione da Project Server 2013 a Project Server 2016.
    
Dopo ogni migrazione, verificare che la migrazione dei dati sia stata eseguita correttamente.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Passaggio 1: Eseguire la migrazione da Project Server 2007 a Project Server 2010

Per una descrizione completa delle attività da eseguire per l'aggiornamento da Project Server 2007 a Project Server 2010, vedere [Upgrade to Project Server 2010](/previous-versions/office/project-server-2010/gg502590(v=office.14)).
  
Risorse chiave:
  
|**Risorsa**|**Descrizione**|
|:-----|:-----|
|[Panoramica dell'aggiornamento a Project Server 2010](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |Una visualizzazione di alto livello delle attività da eseguire per l'aggiornamento da Project Server 2007 a Project Server 2010 <br/> |
|[Pianificare l'aggiornamento a Project Server 2010](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |Considerazioni sulla pianificazione quando si esegue l'aggiornamento da Project Server 2007 a Project Server 2010, inclusi i requisiti di sistema  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Come si esegue l'aggiornamento?

Per informazioni dettagliate, [vedere Upgrade to Project Server 2010](/previous-versions/office/project-server-2010/gg502590(v=office.14)). Tuttavia, è importante comprendere che esistono due metodi distinti che è possibile utilizzare per l'aggiornamento:
  
- **Aggiornamento basato sul collegamento di database:** Questo metodo aggiorna solo il contenuto dell'ambiente, non le impostazioni di configurazione. È necessario se si esegue l'aggiornamento da Office Project Server 2007 distribuito su hardware che supporta solo un sistema operativo server a 32 bit. Esistono due tipi di metodi di aggiornamento basato sul collegamento di database:
    
  - **Aggiornamento completo basato sul collegamento di** database: consente di eseguire la migrazione dei dati del progetto archiviati nei database di Office Project Server 2007, oltre ai dati del sito di Microsoft Project Web App archiviati in un database del contenuto di SharePoint.
    
  - **Aggiornamento di base *basato sul collegamento di database-*** Esegue la migrazione solo dei dati del progetto archiviati nei database di Project Server.
    
- **Aggiornamento sul posto**: i dati di configurazione per la farm e tutto il contenuto della farm vengono aggiornati nell'hardware esistente in un ordine fisso. Quando si avvia il processo di aggiornamento, l'installazione porta offline l'intera farm. I siti Web e i siti di Microsoft Project Web App non sono disponibili fino al termine dell'aggiornamento e quindi il programma di installazione riavvia il server. Dopo aver iniziato un aggiornamento sul posto, non è possibile sospendere l'aggiornamento o eseguire il rollback alla versione precedente. È meglio creare un'immagine speculare dell'ambiente di produzione ed eseguire l'aggiornamento sul posto a questo ambiente, non nell'ambiente di produzione. 
    
Risorse aggiuntive:
  
- [SuperFlow per l'aggiornamento a Microsoft Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Migrazione da Project Server 2007 a Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Considerazioni sull'aggiornamento per Project Web App Web part](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Project Software Development Kit (SDK)](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>Passaggio 2: Eseguire la migrazione a Project Server 2013

Dopo aver verificato la corretta migrazione dei dati, il passaggio successivo consiste nel eseguire la migrazione a Project Server 2013.
  
Per una descrizione completa delle attività da eseguire per l'aggiornamento da Project Server 2010 a Project Server 2013, vedere [Upgrade to Project Server 2013](/project/upgrade-to-project-server-2016). 
  
Risorse chiave:
  
|**Risorsa**|**Descrizione**|
|:-----|:-----|
|[Panoramica del processo di aggiornamento a Project Server 2013](/project/upgrade-to-project-server-2016) <br/> |Panoramica delle attività da eseguire per l'aggiornamento da Project Server 2010 a Project Server 2013  <br/> |
|[Pianificare l'aggiornamento a Project Server 2013](/project/plan-for-upgrade-to-project-server-2016) <br/> |Considerazioni sulla pianificazione quando si esegue l'aggiornamento da Project Server 2010 a Project Server 2013, inclusi i requisiti di sistema <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Informazioni sull'aggiornamento a questa versione

[What's new in Project Server 2013 upgrade](/project/what-s-new-in-project-server-2013-upgrade) describes important changes for upgrade for this version. I più importanti sono: 
  
- Non è disponibile alcun aggiornamento sul posto a Project Server 2013. Il metodo basato sul collegamento di database è l'unico metodo supportato per l'aggiornamento da Project Server 2010 a Project Server 2013.
    
- Il processo di aggiornamento non solo convertirà i dati di Project Server 2010 nel formato di Project Server 2013, ma consoliderà anche i quattro database di Project Server 2010 in un singolo database di Project Web App.
    
- Nelle versioni 2013, Sia SharePoint Server che Project Server sono stati modificati nell'autenticazione basata sulle attestazioni. Se si utilizza l'autenticazione classica, è necessario considerare questo fattore per l'aggiornamento. Per ulteriori informazioni, vedere [Eseguire la migrazione dall'autenticazione in modalità classica a quella basata su attestazioni in SharePoint 2013](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server).
    
Risorse aggiuntive:
  
- [Panoramica del processo di aggiornamento a Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [Aggiornare i database e le raccolte siti di Project Web App (Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Diagramma del processo di aggiornamento di Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Il grande consolidamento dei database, migrazione da Project Server 2010 a 2013 in 8 semplici passaggi](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Passaggio 3: Eseguire la migrazione a Project Server 2016

Dopo aver verificato la corretta migrazione dei dati, il passaggio successivo consiste nel eseguire la migrazione a Project Server 2016.
  
Per una descrizione completa delle attività da eseguire per eseguire l'aggiornamento da Project Server 2013 a Project Server 2016, vedere [Upgrade to Project Server 2016](//project/upgrading-to-project-server-2016).
  
Risorse chiave:
  
|**Risorsa**|**Descrizione**|
|:-----|:-----|
|[Panoramica del processo di aggiornamento a Project Server 2013](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |Panoramica delle attività necessarie per eseguire l'aggiornamento da Project Server 2013 a Project Server 2016 <br/> |
|[Pianificare l'aggiornamento a Project Server 2013](/project/plan-for-upgrade-to-project-server-2016) <br/> |Considerazioni sulla pianificazione dell'aggiornamento da Project Server 2013 a Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Informazioni sull'aggiornamento a questa versione

[Le informazioni necessarie sull'aggiornamento a Project Server 2016](/project/plan-for-upgrade-to-project-server-2016) illustrano alcune importanti modifiche per l'aggiornamento per questa versione, tra cui:
  
- Quando si crea l'ambiente di Project Server 2016 in cui si eseguirà la migrazione dei dati di Project Server 2013, i file di installazione di Project Server 2016 sono inclusi in SharePoint Server 2016. Per ulteriori informazioni, vedere [Deploy Project Server 2016](/project/deploy-project-server-2016).
    
- I piani delle risorse sono deprecati in Project Server 2016. I piani delle risorse di Project Server 2013 verranno migrati in Impegni risorse in Project Server 2016 e in Project Online. Vedi [Panoramica: impegni delle risorse](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) per altre informazioni. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Eseguire la migrazione da Portfolio Server 2007

Project Portfolio Server 2007 è stato utilizzato con Project Server 2007 per la strategia, la definizione delle priorità e l'ottimizzazione del portfolio. Dopo questa versione non sono state create altre versioni di Project Portfolio Server. Tuttavia, le funzionalità di gestione del portfolio sono disponibili in Project Server 2016 e nella versione Premium di Project Online. Non è tuttavia possibile eseguire la migrazione dei dati di Project Portfolio Server 2007. I dati, ad esempio i driver di business, doranno essere ricreati.
  
Altre risorse:
  
- [Descrizioni dei servizi di Project Online:](/office365/servicedescriptions/project-online-service-description/project-online-service-description) Vedere le funzionalità di gestione del portfolio incluse in Project Server 2016 e Project Online Premium.
    
- [Microsoft Office migrazione di Project Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Argomenti correlati

[Guida di orientamento alla fine del supporto di SharePoint Server 2007](sharepoint-2007-end-of-support.md)
  
[Risorse per l'aggiornamento da server e client di Office 2007](upgrade-from-office-2007-servers-and-products.md)
