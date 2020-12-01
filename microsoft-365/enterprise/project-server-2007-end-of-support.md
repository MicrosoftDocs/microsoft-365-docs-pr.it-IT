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
description: Il 10 ottobre 2017, il supporto è stato terminato per Project Server 2007, Project Portfolio Server e Project 2007. Utilizzare questo articolo per pianificare l'aggiornamento.
ms.openlocfilehash: f59b319ec39c6b2d1df0876c916332491f1bb0f6
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519800"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Guida sulla fine del supporto di Project Server 2007

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Il supporto è terminato per i server e le applicazioni di Office 2007 nel 2017 ed è necessario prendere in considerazione i piani per la migrazione. Se si sta attualmente utilizzando Project Server 2007 e prodotti correlati, tenere presente quanto segue:
  
|**Prodotto**|**Data di fine del supporto**|
|:-----|:-----|
|Project Server 2007  <br/> |10 ottobre 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 ottobre 2017  <br/> |
|Project 2007 standard  <br/> |10 ottobre 2017  <br/> |
|Project 2007 Professional  <br/> |10 ottobre 2017  <br/> |
   
Per ulteriori informazioni sui server di Office 2007 che raggiungono il pensionamento, vedere [upgrade from office 2007 Servers and client Products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-does-end-of-support-mean"></a>Cosa significa *fine del supporto* ?

La maggior parte dei prodotti Microsoft ha un ciclo di vita di supporto durante il quale ottengono nuove funzionalità, correzioni di bug, correzioni di sicurezza e così via. Questo ciclo di vita in genere ha una durata di 10 anni rispetto alla versione iniziale del prodotto. La fine del ciclo di vita è nota come fine del supporto del prodotto. Poiché Project Server 2007 ha raggiunto la fine del supporto il 10 ottobre 2017, Microsoft non fornisce più:
  
- Supporto tecnico per i problemi che possono verificarsi.
    
- Correzioni degli errori relativi a problemi che possono influire sulla stabilità e sull'usabilità del server.
    
- Correzioni per la sicurezza per vulnerabilità che potrebbero rendere il server vulnerabile alle violazioni della sicurezza.
    
- Aggiornamenti del fuso orario.
    
L'installazione di Project Server 2007 continuerà a essere eseguita dopo questa data. Tuttavia, a causa delle modifiche elencate in precedenza, è consigliabile eseguire la migrazione da Project Server 2007 non appena pratico.
  
## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

Se si sta utilizzando Project Server 2007, è necessario esplorare le opzioni di migrazione, che sono:
  
- Eseguire la migrazione a Project online
    
- Eseguire la migrazione a una nuova versione locale di Project Server (preferibilmente Project Server 2016)
    
|**Perché preferirei eseguire la migrazione a Project online**|**Perché preferirei eseguire la migrazione a Project Server 2016**|
|:-----|:-----|
| Gli utenti di dispositivi mobili.  <br/> <br/>I costi di migrazione rappresentano un problema significativo (hardware, software, ore e sforzo da implementare). <br/><br/>  Dopo la migrazione, i costi per la gestione dell'ambiente rappresentano una preoccupazione importante (ad esempio, aggiornamenti automatici, tempo di uptime garantito e così via).  <br/> | Le regole business mi impediscono di gestire l'attività nel cloud.<br/><br/>  È necessario controllare gli aggiornamenti per l'ambiente.  |
   
> [!NOTE]
> Per ulteriori informazioni sulle opzioni per lo spostamento dai server di Office 2007, vedere [risorse che consentono di eseguire l'aggiornamento da server e client di office 2007](upgrade-from-office-2007-servers-and-products.md). Si noti che Project Server non supporta una configurazione ibrida perché Project Server e Project online non possono condividere lo stesso pool di risorse. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Considerazioni importanti quando si esegue la migrazione da Project Server 2007

Quando si prevede di eseguire la migrazione da Project Server 2007, tenere presente quanto segue:
  
- **Ottenere assistenza da un partner Microsoft-l'** aggiornamento da Project Server 2007 può essere impegnativo e richiede una preparazione e una pianificazione molto elevate. Potrebbe essere particolarmente difficile se non si è in origine la persona che ha configurato Project Server 2007. Fortunatamente, esistono partner Microsoft che possono essere di aiuto, se si prevede di eseguire la migrazione a Project Server 2016 o a Project online. Cercare un partner Microsoft per facilitare la migrazione nel [centro partner Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841249). Ricercare il termine  *Gold Project e la gestione del portfolio* per visualizzare un elenco di tutti i partner Microsoft che hanno esperienza in Project. 
    
- **Pianificare le personalizzazioni** : molte delle personalizzazioni apportate nell'ambiente di project Server 2007 potrebbero non funzionare quando si esegue la migrazione a project server 2016 o Project online. Sono presenti differenze significative nell'architettura di Project Server tra le versioni. Sono inoltre disponibili i sistemi operativi necessari, i server di database e i browser Web client che sono supportati. Pianificare come testare o ricreare le personalizzazioni per il nuovo ambiente. La pianificazione fornisce anche una buona occasione per valutare se ogni personalizzazione è ancora necessaria. Per ulteriori informazioni, vedere [Create a plan for current customizations during upgrade to SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061). 
    
- **Tempo e pazienza** : la pianificazione, l'esecuzione e il testing dell'aggiornamento richiedono tempo e risorse, soprattutto se si esegue l'aggiornamento a Project Server 2016. Ad esempio, se si esegue la migrazione da Project Server 2007 a Project Server 2016, è prima necessario eseguire la migrazione a Project Server 2010, controllare i dati e quindi eseguire la stessa operazione quando si esegue la migrazione a ogni versione successiva. Potrebbe essere necessario controllare con un partner Microsoft per ottenere stime sul tempo necessario e su cosa costerà.
    
## <a name="migrate-to-project-online"></a>Eseguire la migrazione a Project online

Se si sceglie di eseguire la migrazione da Project Server 2007 a Project online, è possibile eseguire le operazioni seguenti per eseguire la migrazione manuale dei dati del piano del progetto:
  
1. Salvare i piani di progetto da Project Server 2003 in formato MPP.
    
2. In Project Professional 2013, Project Professional 2016 o il client desktop di Project online, aprire ogni file con estensione MPP e quindi salvarlo e pubblicarlo in Project online.
    
È possibile creare manualmente la configurazione di Microsoft Project Web App (PWA) in Project online. Ad esempio, ricreare tutti i campi personalizzati o i calendari dell'organizzazione necessari. Microsoft Partners può anche contribuire a questo processo.
  
Risorse chiave:
  
|**Risorsa**|**Descrizione**|
|:-----|:-----|
|[Introduzione a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Come configurare e utilizzare Project online <br/> |
|[Descrizioni dei servizi di Project online](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Informazioni sui diversi piani di Project online disponibili per l'utente <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Eseguire la migrazione a una nuova versione locale di Project Server

Si ritiene fortemente che sia possibile ottenere il miglior valore e l'esperienza utente eseguendo la migrazione a Project online. Tuttavia, si capisce anche che alcune organizzazioni devono mantenere i dati del progetto in un ambiente locale. Se si sceglie di mantenere i dati del progetto in locale, è possibile eseguire la migrazione dell'ambiente Project Server 2007 a Project Server 2010, Project Server 2013 o Project Server 2016.
  
Se non è possibile eseguire la migrazione a Project online, è consigliabile eseguire la migrazione a Project Server 2016. Project Server 2016 include tutte le funzionalità delle versioni precedenti di Project Server. La maggior parte dei casi corrisponde all'esperienza disponibile con Project online, anche se alcune funzionalità sono disponibili solo in Project online.
  
Dopo ogni migrazione, è necessario verificare che i dati siano stati migrati correttamente.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Come si esegue la migrazione a Project Server 2016?

Le differenze architettoniche tra Project Server 2007 e Project Server 2016 impediscono un percorso di migrazione diretto. Pertanto, è necessario eseguire la migrazione dei dati di Project Server 2007 a ogni versione successiva di Project Server finché non si raggiunge Project Server 2016.
  
Eseguire la procedura seguente per Project Server 2016:
  
1. Eseguire la migrazione da Project Server 2007 a Project Server 2010.
    
2. Eseguire la migrazione da Project serv 2010 a Project Server 2013.
    
3. Eseguire la migrazione da Project Server 2013 a Project Server 2016.
    
Dopo ogni migrazione, verificare che i dati siano stati migrati correttamente.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Passaggio 1: eseguire la migrazione da Project Server 2007 a Project Server 2010

Per una descrizione completa delle operazioni da eseguire per l'aggiornamento da Project Server 2007 a Project Server 2010, vedere [upgrade to Project server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812).
  
Risorse chiave:
  
|**Risorsa**|**Descrizione**|
|:-----|:-----|
|[Panoramica dell'aggiornamento di Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Visualizzazione di alto livello delle operazioni da eseguire per l'aggiornamento da Project Server 2007 a Project Server 2010 <br/> |
|[Pianificare l'aggiornamento a Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Considerazioni sulla pianificazione quando si esegue l'aggiornamento da Project Server 2007 a Project Server 2010, inclusi i requisiti di sistema  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Come si esegue l'aggiornamento?

Per ulteriori informazioni, vedere [upgrade to Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812). Tuttavia, è importante comprendere che esistono due metodi distinti che è possibile utilizzare per eseguire l'aggiornamento:
  
- **Aggiornamento basato sul collegamento di database:** Questo metodo aggiorna solo il contenuto per l'ambiente, non le impostazioni di configurazione. È necessario se si sta eseguendo l'aggiornamento da Office Project Server 2007 distribuito su hardware che supporta solo un sistema operativo server a 32 bit. Sono disponibili due tipi di metodi di aggiornamento basato sul collegamento di database:
    
  - ***Aggiornamento completo*** basato sul collegamento di database: consente di eseguire la migrazione dei dati di progetto archiviati nei database di Office Project Server 2007, oltre ai dati del sito di Microsoft Project Web App archiviati in un database del contenuto di SharePoint.
    
  - ***Aggiornamento di base*** basato sul collegamento di database: consente di eseguire la migrazione solo dei dati di progetto archiviati nei database di Project Server.
    
- **Aggiornamento sul posto**: i dati di configurazione per la farm e tutto il contenuto della farm vengono aggiornati sull'hardware esistente in un ordine fisso. Quando si avvia il processo di aggiornamento, il programma di installazione utilizza l'intera farm offline. I siti Web e quelli di Microsoft Project Web App non sono disponibili fino al termine dell'aggiornamento e quindi il programma di installazione riavvia il server. Dopo aver avviato un aggiornamento sul posto, non è possibile sospendere l'aggiornamento o eseguire il rollback alla versione precedente. È preferibile creare un'immagine speculare dell'ambiente di produzione e eseguire l'aggiornamento sul posto a questo ambiente, non nell'ambiente di produzione. 
    
Risorse aggiuntive:
  
- [Aggiornamento di SuperFlow per Microsoft Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Migrazione da Project Server 2007 a Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Considerazioni sull'aggiornamento per le web part di Project Web App](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Project Software Development Kit (SDK)](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Passaggio 2: eseguire la migrazione a Project Server 2013

Dopo aver verificato che i dati sono stati migrati correttamente, il passaggio successivo consiste nella migrazione a Project Server 2013.
  
Per una descrizione completa delle operazioni da eseguire per l'aggiornamento da Project Server 2010 a Project Server 2013, vedere [upgrade to Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822). 
  
Risorse chiave:
  
|**Risorsa**|**Descrizione**|
|:-----|:-----|
|[Panoramica del processo di aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Panoramica delle operazioni da eseguire per l'aggiornamento da Project Server 2010 a Project Server 2013  <br/> |
|[Pianificare l'aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Considerazioni sulla pianificazione quando si esegue l'aggiornamento da Project Server 2010 a Project Server 2013, inclusi i requisiti di sistema <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Elementi da sapere sull'aggiornamento a questa versione

[What ' s New in Project Server 2013 upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) descrive importanti modifiche per l'aggiornamento per questa versione. Le più importanti sono le seguenti: 
  
- Non è previsto alcun aggiornamento sul posto a Project Server 2013. Il metodo basato sul collegamento di database è l'unico metodo supportato per l'aggiornamento da Project Server 2010 a Project Server 2013.
    
- Il processo di aggiornamento non solo convertirà i dati di Project Server 2010 nel formato di Project Server 2013, ma consoliderà anche i quattro database di Project Server 2010 in un singolo database di Project Web App.
    
- Nelle versioni 2013, sia SharePoint Server che Project Server sono stati modificati per l'autenticazione basata sulle attestazioni. Se si utilizza l'autenticazione classica, è necessario prendere in considerazione questo fattore per l'aggiornamento. Per ulteriori informazioni, vedere [Eseguire la migrazione dall'autenticazione in modalità classica a quella basata su attestazioni in SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825).
    
Risorse aggiuntive:
  
- [Panoramica del processo di aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Aggiornare i database e le raccolte siti di Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Diagramma del processo di aggiornamento di Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Grande consolidamento dei database, Project Server 2010 to 2013 Migration in 8 semplici passaggi](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Passaggio 3: eseguire la migrazione a Project Server 2016

Dopo aver verificato che i dati sono stati migrati correttamente, il passaggio successivo consiste nella migrazione a Project Server 2016.
  
Per una descrizione completa delle operazioni da eseguire per l'aggiornamento da Project Server 2013 a Project Server 2016, vedere [upgrade to Project server 2016](https://docs.microsoft.com//project/upgrading-to-project-server-2016).
  
Risorse chiave:
  
|**Risorsa**|**Descrizione**|
|:-----|:-----|
|[Panoramica del processo di aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Panoramica delle operazioni da eseguire per l'aggiornamento da Project Server 2013 a Project Server 2016 <br/> |
|[Pianificare l'aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Considerazioni sulla pianificazione per l'aggiornamento da Project Server 2013 a Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Elementi da sapere sull'aggiornamento a questa versione

[Le operazioni necessarie per l'aggiornamento a Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841827) indicano alcune importanti modifiche per l'aggiornamento per questa versione, tra cui:
  
- Quando si crea l'ambiente di Project Server 2016 in cui si esegue la migrazione dei dati di Project Server 2013, i file di installazione di Project Server 2016 sono inclusi in SharePoint Server 2016. Per ulteriori informazioni, vedere [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- I piani delle risorse sono deprecati in Project Server 2016. I piani delle risorse di Project Server 2013 verranno migrati negli impegni delle risorse in Project Server 2016 e in Project online. Per ulteriori informazioni, vedere [Panoramica: impegni delle risorse](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) . 
    
## <a name="migrate-from-portfolio-server-2007"></a>Eseguire la migrazione da Portfolio Server 2007

Project Portfolio Server 2007 è stato utilizzato con Project Server 2007 per la strategia di portfolio, la definizione di priorità e l'ottimizzazione. Non sono state create altre versioni del server del portfolio di progetti dopo questa versione. Tuttavia, le funzionalità di gestione del portfolio sono disponibili in Project Server 2016 e nella versione Premium di Project online. Tuttavia, non è possibile eseguire la migrazione dei dati di Project Portfolio Server 2007. I dati, ad esempio i driver di business, dovranno essere ricreati.
  
Altre risorse:
  
- [Descrizioni dei servizi di Project online:](https://go.microsoft.com/fwlink/p/?linkid=841280) Vedere le funzionalità di gestione del portfolio incluse in Project Server 2016 e Project Online Premium.
    
- [Guida alla migrazione di Microsoft Office Project Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Argomenti correlati

[Guida di orientamento alla fine del supporto di SharePoint Server 2007](sharepoint-2007-end-of-support.md)
  
[Risorse utili per l'aggiornamento da server e client di Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
