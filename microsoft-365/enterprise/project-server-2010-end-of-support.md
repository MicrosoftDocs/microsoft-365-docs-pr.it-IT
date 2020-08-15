---
title: Guida di orientamento alla fine del supporto di Project Server 2010
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
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
description: La terminazione del supporto per Project Server 2010 termina il 13 aprile 2021. Utilizzare questo articolo come guida per l'aggiornamento a Project online o a una versione più recente di Project Server locale.
ms.openlocfilehash: e20c8752b088b783f622fabf30302bbb8d4b8975
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696086"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Tabella di marcia della fine del supporto di Project Server 2010

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Project Server 2010 raggiungerà la fine del supporto il **13 aprile 2021**. Questa data è stata estesa dalla data di fine del supporto precedente del 13 ottobre 2020. Se si sta attualmente utilizzando Project Server 2010, tenere presente che gli altri prodotti correlati hanno le seguenti date di supporto:
  
| Prodotto |Data di fine del supporto|
|:-----|:-----|
|Project 2010 standard <br/> |13 ottobre 2020  <br/> |
|Project 2010 Professional  <br/> |13 ottobre 2020  <br/> |

   
Per ulteriori informazioni sui server di Office 2010 che raggiungono la fine del supporto, vedere [upgrade from office 2010 Servers and client Products](plan-upgrade-previous-versions-office.md).
  
## <a name="what-does-end-of-support-mean"></a>Cosa significa fine del supporto?

Project Server, come quasi tutti i prodotti Microsoft, ha un ciclo di vita di supporto durante il quale vengono fornite nuove funzionalità, correzioni di bug e aggiornamenti della sicurezza. Questo ciclo di vita di solito dura 10 anni a partire dalla data di rilascio iniziale del prodotto e la fine di questo ciclo di vita è nota come fine del prodotto di supporto. Quando Project Server 2010 raggiunge la fine del supporto del 13 aprile 2021, Microsoft non fornirà più:
  
- Supporto tecnico per i problemi che possono verificarsi.
    
- Correzioni dei bug per i problemi individuati e che possono influire sulla stabilità e sull'usabilità del server.
    
- Correzioni per la sicurezza per le vulnerabilità individuate e che possono rendere il server vulnerabile alle violazioni della sicurezza.
    
- Aggiornamenti del fuso orario.
    
L'installazione di Project Server 2010 continuerà a essere eseguita dopo questa data. Tuttavia, a causa delle modifiche elencate in alto, è consigliabile eseguire la migrazione da Project Server 2010 appena possibile.
  
## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

Se si utilizza Project Server 2010, è necessario esplorare le opzioni di migrazione, che sono le seguenti:
  
- Eseguire la migrazione a Project online
    
- Eseguire la migrazione a una nuova versione locale di Project Server (preferibilmente Project Server 2019).

Di seguito sono riportate le due strade che è possibile eseguire per evitare la fine del supporto per Project Server 2010.

![Percorsi di aggiornamento di Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

    


|**Perché è consigliabile eseguire la migrazione a Project Server 2019?**|**Perché è consigliabile eseguire la migrazione a Project online?**|
|:-----|:-----|
|Le regole business mi impediscono di gestire l'attività nel cloud.  <br/>  È necessario controllare gli aggiornamenti per l'ambiente.  <br/> | Sono utenti mobili o remoti.  <br/>  I costi per la migrazione dei server locali sono una grande preoccupazione (hardware, software, ore e tentativi di implementazione e così via).  <br/>  Dopo la migrazione, i costi per il mantenimento dell'ambiente sono una grande preoccupazione (ad esempio, aggiornamenti automatici, tempo di uptime garantito e così via).  <br/>  |

   
> [!NOTE]
> Per ulteriori informazioni sulle opzioni per lo spostamento dai server di Office 2010, vedere [risorse che consentono di eseguire l'aggiornamento da server e client di office 2010](upgrade-from-office-2010-servers-and-products.md). Si noti che Project Server non supporta una configurazione ibrida poiché Project Server e Project online non possono condividere lo stesso pool di risorse. 

### <a name="what-are-my-options-for-project-client"></a>Quali sono le opzioni per il client del progetto?
Se si utilizza Project Professional 2010 o Project Standard 2010 e si desidera esplorare le opzioni di migrazione, è possibile scegliere tra:
- Passare a una versione più recente di Project Professional o Project standard.
- Passare a una soluzione online come Project online o Project per il Web.
 
#### <a name="moving-to-a-newer-version-of-project-client"></a>Passaggio a una versione più recente di Project client

Se si esegue la migrazione da Project Standard 2010, è possibile eseguire la migrazione a una versione più recente di Project standard (Project standard 2016 o Project standard 2019).  È consigliabile passare alla versione più recente per sfruttare le caratteristiche e le funzionalità più recenti. Inoltre, la migrazione a una versione meno recente (Project standard 2016) significa che sarà necessario eseguire la migrazione da questa versione prima che venga aggiornata la data di fine del supporto.

Analogamente, se si esegue la migrazione da Project Professional 2010, è possibile scegliere di eseguire la migrazione a una versione più recente (Project Professional 2019 o Project Professional 2016). Se possibile, è consigliabile passare alla versione più recente.  Se si utilizza Project Professional per connettersi a Project Server, assicurarsi di eseguire la migrazione a una versione di Project Professional supportata per la connessione con la versione di Project Server in uso.

Project Professional 2010 gli utenti possono anche scegliere di eseguire la migrazione al client desktop di Project online. Si tratta di una versione basata su sottoscrizione di Project Professional 2019 ed è inclusa in Project Plan 3 e Project Plan 5 abbonamenti. 

#### <a name="moving-to-an-online-solution"></a>Passaggio a una soluzione online

È inoltre possibile scegliere di eseguire la migrazione da Project Professional 2010 o Project Standard 2010 alle soluzioni online basate su sottoscrizione del progetto. Sia il piano del progetto 3 che il piano 5 includono Project online e l'offerta cloud più recente, [Project for the Web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Entrambe offrono una serie di nuove funzionalità e vantaggi che meritano di essere esplorate.

Per ulteriori informazioni sulle funzionalità incluse in entrambi, nonché sulle licenze per il piano di progetto in cui sono incluse, vedere la [Descrizione del servizio Microsoft Project](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).



  
## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2010"></a>Considerazioni importanti che è necessario apportare quando si pianifica la migrazione da Project Server 2010

Quando si pianifica la migrazione da Project Server 2010, è necessario tenere presente quanto segue:
  
- **Ottenere assistenza da un provider di soluzioni Microsoft** : l'aggiornamento da Project Server 2010 può essere una sfida e richiede molta preparazione e pianificazione. Può essere particolarmente difficile se non si è in grado di installare e configurare Project Server 2010 in origine. Fortunatamente, esistono provider di soluzioni Microsoft che è possibile rivolgersi a chi lo può fare per vivere, se si prevede di eseguire la migrazione a Project Server 2019 o a Project online. È possibile cercare un provider di soluzioni Microsoft per facilitare la migrazione in [Microsoft Solution Provider Center](https://go.microsoft.com/fwlink/p/?linkid=841249). 
    
- **Pianificare le personalizzazioni** : tenere presente che molte delle personalizzazioni che si utilizzano nell'ambiente di project Server 2010 potrebbero non funzionare durante la migrazione a project server 2019 o a Project online. Esistono grandi differenze nell'architettura di Project Server tra le versioni, così come i sistemi operativi necessari, i server di database e i browser Web client supportati per l'utilizzo con la versione più recente. Disporre di un piano su come testare o ricreare le personalizzazioni in base alle esigenze nel nuovo ambiente. La pianificazione dell'aggiornamento sarà anche una buona occasione per verificare se è necessaria una specifica personalizzazione quando ci si sposta in avanti. [La creazione di un piano per le personalizzazioni correnti durante l'aggiornamento a SharePoint 2013]( https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013) contiene alcune informazioni generali sulla valutazione e la pianificazione delle personalizzazioni correnti durante l'aggiornamento. 
    
- **Tempo e pazienza** : la pianificazione, l'esecuzione e il testing dell'aggiornamento richiederanno molto tempo ed energie, soprattutto se si esegue l'aggiornamento a Project Server 2019. Ad esempio, se si esegue la migrazione da Project Server 2010 a Project Server 2019, è necessario innanzitutto eseguire la migrazione da Project Server 2010 a Project Server 2013 e quindi controllare i dati e quindi eseguire la stessa operazione quando si esegue la migrazione a ogni versione successiva (in Project Server 2016 e quindi a Project Server 2019). È possibile verificare con un provider di soluzioni Microsoft la possibilità di confrontare i costi stimati con le stime relative al tempo necessario per la loro attività e a quale costo. 
    
## <a name="migrate-to-project-online"></a>Eseguire la migrazione a Project online

Se si sceglie di eseguire la migrazione da Project Server 2010 a Project online, è possibile eseguire le operazioni seguenti per eseguire la migrazione manuale dei dati del piano del progetto:
  
1. Salvare i piani di progetto da Project Server 2010 a. Formato MPP.
    
2. Utilizzando Project Professional 2016, Project Professional 2019 o il client desktop di Project online, aprire ogni file con estensione MPP e quindi salvarlo e pubblicarlo in Project online.
    
È possibile creare manualmente la configurazione di Project Web Access in Project online, ad esempio ricreare tutti i campi personalizzati o i calendari dell'organizzazione necessari. Anche i provider di soluzioni Microsoft possono aiutarti.
  
Risorse chiave:
  
|**Risorsa**|**Descrizione**|
|:-----|:-----|
|[Introduzione a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Come eseguire l'installazione e l'utilizzo di Project online.  <br/> |
|[Descrizione del servizio Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Informazioni sui diversi piani di Project online che sono disponibili per l'utente.  <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Eseguire la migrazione a una nuova versione locale di Project Server

Anche se si ritiene che sia possibile ottenere il miglior valore e l'esperienza utente eseguendo la migrazione a Project online, è inoltre necessario che alcune organizzazioni debbano mantenere i dati del progetto in un ambiente locale. Se si sceglie di mantenere i dati del progetto in locale, è possibile eseguire la migrazione dell'ambiente Project Server 2010 a Project Server 2013, Project Server 2016 o Project Server 2019.
  
È consigliabile eseguire la migrazione a Project Server 2019 se non è possibile eseguire la migrazione a Project online. In Project Server 2019 è inclusa la maggior parte delle funzionalità e dei miglioramenti inclusi nelle versioni precedenti di Project Server e corrisponde più fedelmente all'esperienza disponibile con Project Online (anche se alcune funzionalità sono disponibili solo in Project online).
  
Dopo aver completato ogni migrazione, è necessario controllare i dati per verificare che la migrazione sia stata eseguita correttamente.
  
> [!NOTE]
> Se si sta prendendo in considerazione la migrazione a Project Server 2013 solo se si è limitati a una soluzione locale, è importante tenere presente che sono rimasti solo alcuni anni di supporto. La data di fine del supporto di Project Server 2013 con Service Pack 2 è 10/13/2023. Per ulteriori informazioni sulle date di fine del supporto, vedere Criteri del ciclo di vita dei [prodotti Microsoft](https://go.microsoft.com/fwlink/p/?linkid=842066). 
  
### <a name="how-do-i-migrate-to-project-server-2019"></a>Come si esegue la migrazione a Project Server 2019?

Le differenze architettoniche tra Project Server 2010 e Project Server 2019 impediscono un percorso di migrazione diretto. Questo significa che sarà necessario eseguire la migrazione dei dati di Project Server 2010 alla successiva versione successive di Project Server finché non si esegue l'aggiornamento a Project Server 2019.
  
Sarà necessario eseguire la procedura seguente per aggiornare Project Server 2010 a Project Server 2019:
  
1. Eseguire la migrazione a Project Server 2013.
    
2. Eseguire la migrazione da Project serv 2013 a Project Server 2016.
    
3. Eseguire la migrazione da Project Server 2016 a Project Server 2019.
    
Dopo aver completato ogni migrazione, è necessario controllare i dati per verificare che la migrazione sia stata eseguita correttamente.
  
    
### <a name="step-1-migrate-to-project-server-2013"></a>Passaggio 1: eseguire la migrazione a Project Server 2013

Il primo passaggio per la migrazione dei dati di Project Server 2010 a Project Server 2019 consiste nella prima migrazione a Project Server 2013. 
  
Per una descrizione completa delle operazioni da eseguire per l'aggiornamento da Project Server 2010 a Project Server 2013, vedere [upgrade to Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822). 
  
Risorse chiave:
  
- [Panoramica del processo di aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Ottenere informazioni di alto livello su ciò che è necessario eseguire per eseguire l'aggiornamento da Project Server 2010 a Project Server 2013.
- [Pianificare l'aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) 

  Esaminare le considerazioni relative alla pianificazione che è necessario eseguire durante l'aggiornamento da Project Server 2010 a Project Server 2013, inclusi i requisiti di sistema.
   
[What ' s New in Project Server 2013 upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) indica alcune importanti modifiche per l'aggiornamento per questa versione, la più importante è: 
  
- Non è presente alcun aggiornamento sul posto a Project Server 2013. Il metodo basato sul collegamento di database è l'unico metodo supportato per l'aggiornamento da Project Server 2010 a Project Server 2013.
    
- Il processo di aggiornamento non solo convertirà i dati di Project Server 2010 nel formato di Project Server 2013, ma consoliderà anche i quattro database di Project Server 2010 in un singolo database di Project Web App.
    
- Sia SharePoint Server 2013 che Project Server 2013 sono stati modificati per l'autenticazione basata sulle attestazioni dalla versione precedente. Quando si utilizza l'autenticazione classica, è necessario prendere in considerazione le considerazioni relative all'aggiornamento. Per ulteriori informazioni, vedere [Eseguire la migrazione dall'autenticazione in modalità classica a quella basata su attestazioni in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).
    
Risorse chiave:
  
- [Panoramica del processo di aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Aggiornare i database e le raccolte siti di Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Diagramma del processo di aggiornamento di Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [Grande consolidamento dei database, Project Server 2010 to 2013 Migration in 8 semplici passaggi](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-2-migrate-to-project-server-2016"></a>Passaggio 2: eseguire la migrazione a Project Server 2016

Dopo aver eseguito la migrazione a Project Server 2013 e aver verificato che i dati sono stati migrati correttamente, il passaggio successivo consiste nella migrazione dei dati a Project Server 2016.
  
Per una descrizione completa delle operazioni da eseguire per l'aggiornamento da Project Server 2013 a Project Server 2016, vedere [upgrade to Project server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).
  
Risorse chiave:
  
- [Panoramica del processo di aggiornamento a Project Server 2013](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Ottenere informazioni di alto livello su ciò che è necessario eseguire per eseguire l'aggiornamento da Project Server 2013 a Project Server 2016.

- [Pianificare l'aggiornamento a Project Server 2013](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Esaminare le considerazioni relative alla pianificazione che è necessario eseguire durante l'aggiornamento da Project Server 2013 a Project Server 2016.
   
[Le operazioni necessarie per l'aggiornamento a Project Server 2016](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) indicano alcune importanti modifiche per l'aggiornamento a questa versione, tra cui: 
  
- Quando si crea l'ambiente Project Server 2016 in cui verrà eseguita la migrazione dei dati di Project Server 2013, tenere presente che i file di installazione di Project Server 2016 sono inclusi in SharePoint Server 2016. Per ulteriori informazioni, vedere [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- I piani delle risorse sono deprecati in Project Server 2016. I piani delle risorse di Project Server 2013 verranno migrati negli impegni delle risorse in Project Server 2016 e in Project online. Per ulteriori informazioni, vedere [Panoramica: impegni delle risorse](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) . 
    
### <a name="step-3-migrate-to-project-server-2019"></a>Passaggio 3: eseguire la migrazione a Project Server 2019

Dopo aver eseguito la migrazione a Project Server 2016 e aver verificato che i dati sono stati migrati correttamente, il passaggio successivo consiste nella migrazione dei dati a Project Server 2019.
  
Per una descrizione completa delle operazioni da eseguire per l'aggiornamento da Project Server 2016 a Project Server 2019, vedere [upgrade to Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).
  
Risorse chiave:
  
- [Panoramica del processo di aggiornamento di Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Ottenere informazioni di alto livello su ciò che è necessario eseguire per eseguire l'aggiornamento da Project Server 2013 a Project Server 2016.

- [Pianificare l'aggiornamento a Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Esaminare le considerazioni relative alla pianificazione che è necessario eseguire durante l'aggiornamento da Project Server 2016 a Project Server 2019.
   
[Le operazioni necessarie per l'aggiornamento a Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=841827) indicano alcune importanti modifiche per l'aggiornamento a questa versione, tra cui: 
  
- Il processo di aggiornamento eseguirà la migrazione dei dati dal database di Project Server 2016 al database del contenuto di SharePoint Server 2019.  Project Server 2019 non creerà più il proprio database di Project Server nella farm di SharePoint Server.

- Dopo l'aggiornamento, tenere conto di diverse modifiche in Project Web App.  Per una descrizione di questi elementi, vedere [What ' s New in Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

  
Altre risorse:
  
- [Descrizioni dei servizi di Project Online](https://go.microsoft.com/fwlink/p/?linkid=841280): vedere le funzionalità di gestione del portfolio incluse in project server 2016 e Project Online Premium.
    
- [Guida alla migrazione di Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Riepilogo delle opzioni per il client e i server di Office 2010 e Windows 7

Per un riepilogo visivo delle opzioni di aggiornamento, migrazione e passaggio al cloud per i client e i server di Office 2010 e Windows 7, vedere il [poster relativo alla fine del supporto](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Immagine del poster per la fine del supporto per client e server di Office 2010 e Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Questo poster di una pagina rappresenta un modo rapido per comprendere i vari percorsi che è possibile eseguire per evitare che i prodotti client e server di Office 2010 e Windows 7 raggiungano la fine del supporto, evidenziando i percorsi preferiti e il supporto delle opzioni in Microsoft 365 Enterprise.

È anche possibile [scaricare il poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).
   
## <a name="related-topics"></a>Argomenti correlati

[Aggiornamento da SharePoint 2010](upgrade-from-sharepoint-2010.md)
  
[Aggiornare i server e i client di Office 2010](upgrade-from-office-2010-servers-and-products.md)
  

