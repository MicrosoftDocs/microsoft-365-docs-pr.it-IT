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
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519703"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Tabella di marcia della fine del supporto di Project Server 2010

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Project Server 2010 raggiungerà la fine del supporto il **13 aprile 2021**. Questa data è stata estesa dalla data di fine del supporto precedente del 13 ottobre 2020. Se si sta attualmente utilizzando Project Server 2010, tenere presente che questi prodotti correlati presentano le seguenti date di supporto:

|Prodotto |Data di fine del supporto|
|---|---|
|Project 2010 standard|13 ottobre 2020|
|Project 2010 Professional|13 ottobre 2020|

Per ulteriori informazioni su come raggiungere la fine del supporto, vedere [upgrade from Office 2010 Servers and client Products](plan-upgrade-previous-versions-office.md).

## <a name="what-does-end-of-support-mean"></a>Cosa significa *fine del supporto* ?

Quasi tutti i prodotti Microsoft dispongono di un ciclo di vita di supporto, durante il quale vengono riportate nuove funzionalità, correzioni di bug e aggiornamenti della sicurezza. Questo ciclo di vita in genere ha una durata di 10 anni rispetto alla versione iniziale del prodotto. La fine del ciclo di vita è nota come fine del supporto del prodotto. Dopo che Project Server 2010 raggiunge la fine del supporto del 13 aprile 2021, Microsoft non fornirà più:

- Supporto tecnico per i problemi che possono verificarsi.

- Correzioni dei bug per i problemi individuati e che possono influire sulla stabilità e sull'usabilità del server.

- Correzioni per la sicurezza per le vulnerabilità individuate e che possono rendere il server vulnerabile alle violazioni della sicurezza.

- Aggiornamenti del fuso orario.

L'installazione di Project Server 2010 continuerà a essere eseguita dopo questa data. Tuttavia, a causa delle modifiche elencate in precedenza, è consigliabile eseguire la migrazione da Project Server 2010 non appena possibile.

## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

Le opzioni di migrazione sono le seguenti:

- Eseguire la migrazione a Project online

- Eseguire la migrazione a una nuova versione locale di Project Server (preferibilmente Project Server 2019)

Di seguito sono riportate le due strade che è possibile eseguire per evitare la fine del supporto per Project Server 2010.

![Percorsi di aggiornamento di Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Perché è consigliabile eseguire la migrazione a Project Server 2019?|Perché è consigliabile eseguire la migrazione a Project online?|
|---|---|
|Le regole business mi impediscono di gestire l'attività nel cloud.  <br/><br/>  È necessario controllare gli aggiornamenti per l'ambiente.|Sono utenti mobili o remoti.<br/><br/>  I costi per la migrazione dei server locali sono una preoccupazione significativa (hardware, software, tempo e sforzo da implementare e così via). <br/><br/>  Dopo la migrazione, i costi per la gestione dell'ambiente sono un problema (ad esempio, aggiornamenti automatici, uptime garantita e così via).|

> [!NOTE]
> Per ulteriori informazioni sulle opzioni di migrazione, vedere [risorse che consentono di eseguire l'aggiornamento da server e client di Office 2010](upgrade-from-office-2010-servers-and-products.md). Si noti che Project Server non supporta la configurazione ibrida perché Project Server e Project online non sono in grado di condividere lo stesso pool di risorse.

### <a name="what-are-my-options-for-project-client"></a>Quali sono le opzioni per il client del progetto?

Se si usa Project Professional 2010 o Project Standard 2010, le opzioni disponibili sono le seguenti:

- Passare a una versione più recente di Project Professional o Project standard
- Passare a una soluzione online, ad esempio Project online o Project per il Web

#### <a name="move-to-a-newer-version-of-project-client"></a>Passare a una versione più recente di Project client

Se si esegue la migrazione da Project Standard 2010, è possibile passare a una versione più recente di Project standard (Project standard 2016 o Project standard 2019). È consigliabile passare alla versione più recente per usufruire delle funzionalità più recenti. La migrazione a una versione meno recente (Project standard 2016) significa anche che sarà necessario eseguire di nuovo la migrazione prima.

Analogamente, se si esegue la migrazione da Project Professional 2010, è possibile passare a una versione più recente (Project Professional 2019 o Project Professional 2016). Anche in questo caso, passare alla versione più recente, se possibile. Se si utilizza Project Professional per connettersi a Project Server, è necessario eseguire la migrazione a una versione di Project Professional che si connette con la versione di Project Server utilizzata.

Project Professional 2010 gli utenti possono anche eseguire la migrazione al client desktop di Project online, che è una versione basata su sottoscrizione di Project Professional 2019. È incluso nelle sottoscrizioni di Project Plan 3 e Project Plan 5.

#### <a name="move-to-an-online-solution"></a>Passare a una soluzione online

È inoltre possibile eseguire la migrazione da Project Professional 2010 o Project Standard 2010 a una soluzione online basata su sottoscrizione di Project. Sia il piano del progetto 3 che il piano 5 includono Project online e l'offerta cloud più recente, [Project for the Web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Entrambe offrono nuove funzionalità e vantaggi che meritano di essere esplorate.

Per ulteriori informazioni sulle funzionalità e sulle licenze, vedere [Descrizione del servizio Microsoft Project](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Considerazioni importanti per la migrazione da Project Server 2010

Quando si prevede di eseguire la migrazione da Project Server 2010, tenere presente quanto segue:

- **Ottenere assistenza da un provider di soluzioni Microsoft** -un aggiornamento da Project Server 2010 può essere una sfida. Richiede molta preparazione e pianificazione. Può essere particolarmente arduo se non si è la persona che ha originariamente configurato Project Server 2010. I provider di soluzioni Microsoft sono disponibili per la guida, se si prevede di eseguire la migrazione a Project Server 2019 o a Project online. Cercare un provider di soluzioni in [Microsoft Solution Provider Center](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Pianificare le personalizzazioni** : le personalizzazioni nell'ambiente di project Server 2010 potrebbero non funzionare quando si esegue la migrazione a project server 2019 o Project online. Sono presenti differenze significative nell'architettura di Project Server tra le versioni. Inoltre, i sistemi operativi, i server di database e i Web browser necessari che funzionano con le versioni sono diversi. Pianificare la verifica o la ricostruzione delle personalizzazioni nel nuovo ambiente. Utilizzare questa opportunità per determinare se sono ancora necessarie personalizzazioni specifiche. Per ulteriori informazioni, vedere [Create a plan for current customizations during upgrade to SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- **Tempo e pazienza** : la pianificazione, l'esecuzione e il testing dell'aggiornamento richiederanno molto tempo ed energie, soprattutto per un aggiornamento a Project Server 2019. Se si esegue la migrazione da Project Server 2010 a Project Server 2019, è necessario prima eseguire la migrazione a Project Server 2013, controllare i dati, quindi eseguire la migrazione a Project Server 2016 e quindi a Project Server 2019. Potrebbe essere necessario controllare con un provider di soluzioni Microsoft una tempistica e un costo stimato per l'assistenza.

## <a name="migrate-to-project-online"></a>Eseguire la migrazione a Project online

Se si sceglie di eseguire la migrazione da Project Server 2010 a Project online, è possibile eseguire la procedura seguente per eseguire la migrazione manuale dei dati del piano del progetto:

1. Salvare i piani di progetto da Project Server 2010 in formato MPP.

2. Utilizzando Project Professional 2016, Project Professional 2019 o il client desktop di Project online, aprire ogni file con estensione MPP e quindi salvarlo e pubblicarlo in Project online.

È possibile creare manualmente la configurazione di Project Web Access in Project online, ad esempio ricreare tutti i campi personalizzati o i calendari dell'organizzazione necessari. I provider di soluzioni Microsoft possono anche contribuire a questo processo.

Risorse chiave:

|Risorsa|Descrizione|
|---|---|
|[Introduzione a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Come configurare e utilizzare Project online|
|[Descrizione del servizio Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088)|Informazioni sui diversi piani di Project online disponibili|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Eseguire la migrazione a una nuova versione locale di Project Server

Si ritiene fortemente che sia possibile ottenere il miglior valore e l'esperienza utente eseguendo la migrazione a Project online. Tuttavia, è anche possibile che alcune organizzazioni debbano mantenere i dati del progetto in locale. Se si sceglie di mantenere i dati del progetto in locale, è possibile eseguire la migrazione dell'ambiente Project Server 2010 a Project Server 2013, Project Server 2016 o Project Server 2019.

Se non è possibile eseguire la migrazione a Project online, è consigliabile eseguire la migrazione a Project Server 2019. Project Server 2019 include la maggior parte delle funzionalità principali nelle versioni precedenti di Project Server. La maggior parte dei casi corrisponde all'esperienza disponibile con Project online, anche se alcune funzionalità sono disponibili solo in Project online.

Dopo aver completato ogni migrazione, verificare che i dati siano stati migrati correttamente.

> [!NOTE]
> Se si è limitati a una soluzione locale e si considera solo la migrazione a Project Server 2013, tenere presente che questa versione ha solo pochi anni di supporto. La data di fine del supporto per Project Server 2013 con Service Pack 2 ottobre 13, 2023. Per ulteriori informazioni sulle date di fine del supporto, vedere Criteri del ciclo di vita dei [prodotti Microsoft](https://go.microsoft.com/fwlink/p/?linkid=842066).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Come si esegue la migrazione a Project Server 2019?

Le differenze architettoniche tra Project Server 2010 e Project Server 2019 impediscono un percorso di migrazione diretto. Sarà quindi necessario eseguire la migrazione dei dati di Project Server 2010 in ogni versione successiva di Project Server finché non si raggiunge Project Server 2019. Passaggi per l'aggiornamento di Project Server 2010 a Project Server 2019:

1. Eseguire la migrazione a Project Server 2013.

2. Eseguire la migrazione da Project serv 2013 a Project Server 2016.

3. Eseguire la migrazione da Project Server 2016 a Project Server 2019.

Dopo aver completato ogni migrazione, verificare che i dati siano stati migrati correttamente.

### <a name="step-1-migrate-to-project-server-2013"></a>Passaggio 1: eseguire la migrazione a Project Server 2013

Per informazioni esaustive sull'aggiornamento da Project Server 2010 a Project Server 2013, vedere [upgrade to Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822).

Risorse chiave:

- [Panoramica del processo di aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Ottenere una panoramica generale su come eseguire l'aggiornamento da Project Server 2010 a Project Server 2013.
- [Pianificare l'aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  Esaminare le considerazioni relative alla pianificazione per l'aggiornamento da Project Server 2010 a Project Server 2013, inclusi i requisiti di sistema.

- [What ' s New in Project Server 2013 upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) include importanti modifiche per questa versione, tra cui:

   - Non è previsto alcun aggiornamento sul posto a Project Server 2013. Il metodo basato sul collegamento di database è l'unico modo supportato per eseguire l'aggiornamento da Project Server 2010 a Project Server 2013.

   - Il processo di aggiornamento non solo convertirà i dati di Project Server 2010 nel formato di Project Server 2013, ma consoliderà anche i quattro database di Project Server 2010 in un singolo database di Project Web App.

   - Sia SharePoint Server 2013 che Project Server 2013 sono stati modificati per l'autenticazione basata sulle attestazioni dalla versione precedente. Se si utilizza l'autenticazione classica, è necessario prendere in considerazione questa operazione quando si esegue l'aggiornamento. Per ulteriori informazioni, vedere [Eseguire la migrazione dall'autenticazione in modalità classica a quella basata su attestazioni in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Risorse chiave:

- [Panoramica del processo di aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Aggiornare i database e le raccolte siti di Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Diagramma del processo di aggiornamento di Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [Grande consolidamento dei database, Project Server 2010 to 2013 Migration in 8 semplici passaggi](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Passaggio 2: eseguire la migrazione a Project Server 2016

Dopo aver eseguito lo spostamento in Project Server 2013 e verificare che i dati siano stati migrati correttamente, il passaggio successivo consiste nella migrazione a Project Server 2016.

Per ulteriori informazioni, vedere [upgrade to Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Risorse chiave:

- [Panoramica del processo di aggiornamento a Project Server 2013](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Informazioni su cosa è necessario fare per eseguire l'aggiornamento da Project Server 2013 a Project Server 2016.

- [Pianificare l'aggiornamento a Project Server 2013](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Esaminare le considerazioni relative alla pianificazione da effettuare durante l'aggiornamento da Project Server 2013 a Project Server 2016.

[Le operazioni necessarie per l'aggiornamento a Project Server 2016](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) riguardano importanti modifiche per l'aggiornamento a questa versione, tra cui:

- Quando si crea l'ambiente Project Server 2016, tenere presente che i file di installazione di Project Server 2016 sono inclusi in SharePoint Server 2016. Per ulteriori informazioni, vedere [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).

- I piani delle risorse sono deprecati in Project Server 2016. I piani delle risorse di Project Server 2013 verranno migrati negli impegni delle risorse in Project Server 2016 e in Project online. Per ulteriori informazioni, vedere [Panoramica: impegni delle risorse](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) .

### <a name="step-3-migrate-to-project-server-2019"></a>Passaggio 3: eseguire la migrazione a Project Server 2019

Dopo aver eseguito la migrazione a Project Server 2016 e aver verificato che i dati siano stati migrati correttamente, il passaggio successivo consiste nella migrazione dei dati a Project Server 2019.

Per informazioni sulle operazioni da eseguire per l'aggiornamento da Project Server 2016 a Project Server 2019, vedere [upgrade to Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).

Risorse chiave:

- [Panoramica del processo di aggiornamento di Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Ottenere informazioni di alto livello su ciò che è necessario eseguire per eseguire l'aggiornamento da Project Server 2013 a Project Server 2016.

- [Pianificare l'aggiornamento a Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Esaminare le considerazioni sulla pianificazione per l'aggiornamento da Project Server 2016 a Project Server 2019.

- [Elementi da sapere sull'aggiornamento a Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>Informazioni sulle modifiche importanti per l'aggiornamento a questa versione, tra cui:

   - Il processo di aggiornamento eseguirà la migrazione dei dati dal database di Project Server 2016 al database del contenuto di SharePoint Server 2019.  Project Server 2019 non creerà più il proprio database di Project Server nella farm di SharePoint Server.

   - Dopo l'aggiornamento, tenere conto di diverse modifiche in Project Web App.  Per ulteriori informazioni, vedere [What ' s New in Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

**Altre risorse**:

- [Descrizioni dei servizi di Project Online](https://go.microsoft.com/fwlink/p/?linkid=841280): vedere le funzionalità di gestione del portfolio incluse in project server 2016 e Project Online Premium.

- [Guida alla migrazione di Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Riepilogo delle opzioni per il client e i server di Office 2010 e Windows 7

Per un riepilogo visivo delle opzioni di aggiornamento, migrazione e passaggio al cloud per i client e i server di Office 2010 e Windows 7, vedere il [poster relativo alla fine del supporto](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fine del supporto per i client e i server di Office 2010 e il poster di Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

In questo poster vengono illustrati i vari percorsi che è possibile eseguire per evitare la fine del supporto per i prodotti client e server di Office 2010 e Windows 7, con percorsi preferiti e supporto delle opzioni in Microsoft 365 Enterprise evidenziato.

È anche possibile [scaricare](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) questo poster e stamparlo nel formato lettera, legale o tabloid (11 x 17).

## <a name="related-topics"></a>Argomenti correlati

[Aggiornamento da SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Aggiornare i server e i client di Office 2010](upgrade-from-office-2010-servers-and-products.md)
