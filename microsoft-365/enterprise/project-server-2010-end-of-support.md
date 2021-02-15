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
description: Il supporto per Project Server 2010 termina il 13 aprile 2021. Utilizzare questo articolo come guida per eseguire l'aggiornamento a Project Online o a una versione più recente di Project Server locale.
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519703"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Tabella di marcia della fine del supporto di Project Server 2010

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Project Server 2010 raggiungerà la fine del supporto il **13 aprile 2021.** Questa data è stata estesa dalla data di fine del supporto precedente del 13 ottobre 2020. Se attualmente si utilizza Project Server 2010, tenere presente che questi prodotti correlati hanno le date di fine del supporto seguenti:

|Prodotto |Data di fine del supporto|
|---|---|
|Project 2010 Standard|13 ottobre 2020|
|Project 2010 Professional|13 ottobre 2020|

Per ulteriori informazioni sul raggiungimento della fine del supporto, vedere [Upgrade from Office 2010 servers and client products.](plan-upgrade-previous-versions-office.md)

## <a name="what-does-end-of-support-mean"></a>Cosa significa *fine del supporto?*

Quasi tutti i prodotti Microsoft hanno un ciclo di vita del supporto, durante il quale ottengono nuove funzionalità, correzioni di bug e aggiornamenti della sicurezza. Questo ciclo di vita in genere dura 10 anni dalla versione iniziale del prodotto. La fine di questo ciclo di vita è nota come fine del supporto del prodotto. Dopo che Project Server 2010 raggiunge la fine del supporto il 13 aprile 2021, Microsoft non fornirà più:

- Supporto tecnico per i problemi che possono verificarsi.

- Correzioni di bug per i problemi rilevati e che possono influire sulla stabilità e sull'usabilità del server.

- Correzioni per la sicurezza per le vulnerabilità individuate e che possono rendere il server vulnerabile alle violazioni della sicurezza.

- Aggiornamenti del fuso orario.

L'installazione di Project Server 2010 continuerà a essere eseguita dopo questa data. Tuttavia, a causa delle modifiche elencate in precedenza, è consigliabile eseguire la migrazione da Project Server 2010 il prima possibile.

## <a name="what-are-my-options"></a>Quali sono le opzioni disponibili?

Le opzioni di migrazione sono:

- Eseguire la migrazione a Project Online

- Eseguire la migrazione a una versione locale più recente di Project Server (preferibilmente Project Server 2019)

Ecco i due percorsi che è possibile adottare per evitare la fine del supporto per Project Server 2010.

![Percorsi di aggiornamento di Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Perché si preferisce eseguire la migrazione a Project Server 2019?|Perché è preferibile eseguire la migrazione a Project Online?|
|---|---|
|Le regole business mi limitano a non utilizzare la mia azienda nel cloud.  <br/><br/>  Ho bisogno del controllo degli aggiornamenti per il mio ambiente.|Ho utenti mobili o remoti.<br/><br/>  I costi per la migrazione dei server locali sono un problema significativo (hardware, software, tempo e impegno per l'implementazione e così via). <br/><br/>  Dopo la migrazione, i costi per la manutenzione dell'ambiente sono un problema (ad esempio, aggiornamenti automatici, tempo di attività garantito e così via).|

> [!NOTE]
> Per ulteriori informazioni sulle opzioni di migrazione, vedere [Resources to help you upgrade from Office 2010 servers and clients.](upgrade-from-office-2010-servers-and-products.md) Si noti che Project Server non supporta la configurazione ibrida perché Project Server e Project Online non possono condividere lo stesso pool di risorse.

### <a name="what-are-my-options-for-project-client"></a>Quali sono le opzioni disponibili per il client project?

Se si utilizza Project Professional 2010 o Project Standard 2010, le opzioni disponibili sono:

- Passare a una versione più recente di Project Professional o Project Standard
- Passare a una soluzione online, ad esempio Project Online o Project per il Web

#### <a name="move-to-a-newer-version-of-project-client"></a>Passare a una versione più recente del client project

Se si esegue la migrazione da Project Standard 2010, è possibile passare a una versione più recente di Project Standard (Project Standard 2016 o Project Standard 2019). È consigliabile passare alla versione più recente per sfruttare le funzionalità più recenti. La migrazione a una versione meno recente (Project Standard 2016) significa anche che sarà necessario eseguire di nuovo la migrazione prima.

Analogamente, se si esegue la migrazione da Project Professional 2010, è possibile passare a una versione più recente (Project Professional 2019 o Project Professional 2016). Anche in questo caso, passare alla versione più recente, se possibile. Se si utilizza Project Professional per connettersi a Project Server, assicurarsi di eseguire la migrazione a una versione di Project Professional che si connette alla versione di Project Server in uso.

Gli utenti di Project Professional 2010 possono inoltre eseguire la migrazione al client Desktop di Project Online, una versione basata su sottoscrizione di Project Professional 2019. È incluso nelle sottoscrizioni del piano 3 e del piano 5 di Project.

#### <a name="move-to-an-online-solution"></a>Passare a una soluzione online

È inoltre possibile eseguire la migrazione da Project Professional 2010 o Project Standard 2010 a una soluzione online basata su sottoscrizione di Project. Project Piano 3 e Piano 5 includono Project Online e l'offerta cloud più recente, [Project per il Web.](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1) Entrambe offrono nuove funzionalità e vantaggi che vale la pena esplorare.

Per ulteriori informazioni sulle caratteristiche e sulle licenze, vedere la descrizione [del servizio Microsoft Project.](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description)

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Considerazioni importanti per la migrazione da Project Server 2010

Quando si prevede di eseguire la migrazione da Project Server 2010, tenere presente quanto segue:

- **Ottenere assistenza da un provider di soluzioni Microsoft:** un aggiornamento da Project Server 2010 può essere una sfida. Richiede molte attività di preparazione e pianificazione. Può essere particolarmente difficile se non si è la persona che ha originariamente configurato Project Server 2010. I provider di soluzioni Microsoft sono disponibili per facilitare la migrazione a Project Server 2019 o a Project Online. Cercare un provider di soluzioni nel [Centro provider di soluzioni Microsoft.](https://go.microsoft.com/fwlink/p/?linkid=841249)

- **Pianificare le personalizzazioni:** le personalizzazioni nell'ambiente project server 2010 potrebbero non funzionare quando si esegue la migrazione a Project Server 2019 o Project Online. Esistono differenze significative nell'architettura di Project Server tra le versioni. Inoltre, i sistemi operativi, i server di database e i Web browser necessari che funzionano con le versioni sono diversi. Pianificare come testare o ricreare le personalizzazioni nel nuovo ambiente. Sfruttare questa opportunità per determinare se sono ancora necessarie personalizzazioni specifiche. Per ulteriori informazioni, vedere [Create a plan for current customizations during upgrade to SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- **Tempo e pazienza:** la pianificazione, l'esecuzione e il testing dell'aggiornamento richiederanno molto tempo e impegno, in particolare per un aggiornamento a Project Server 2019. Se si esegue la migrazione da Project Server 2010 a Project Server 2019, è innanzitutto necessario eseguire la migrazione a Project Server 2013, controllare i dati, quindi eseguire la migrazione a Project Server 2016 e quindi a Project Server 2019. È consigliabile rivolgersi a un provider di soluzioni Microsoft per un intervallo di tempo e un costo stimato per l'assistenza.

## <a name="migrate-to-project-online"></a>Eseguire la migrazione a Project Online

Se si sceglie di eseguire la migrazione da Project Server 2010 a Project Online, è possibile eseguire la procedura seguente per eseguire manualmente la migrazione dei dati del piano di progetto:

1. Salvare i piani di progetto da Project Server 2010 al formato mpp.

2. Utilizzando Project Professional 2016, Project Professional 2019 o il client desktop di Project Online, aprire ogni file con estensione mpp e quindi salvarlo e pubblicarlo in Project Online.

È possibile creare manualmente la configurazione di Project Web Access in Project Online (ad esempio, ricreare i campi personalizzati o i calendari dell'organizzazione necessari). I provider di soluzioni Microsoft possono essere utili anche per questo processo.

Risorse chiave:

|Risorsa|Descrizione|
|---|---|
|[Introduzione a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Come configurare e usare Project Online|
|[Descrizione del servizio Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088)|Informazioni sui diversi piani di Project Online disponibili|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Eseguire la migrazione a una versione locale più recente di Project Server

Siamo fermamente dell'esperienza utente e del valore aggiunto eseguendo la migrazione a Project Online. Tuttavia, sappiamo anche che alcune organizzazioni devono mantenere i dati dei progetti in locale. Se si sceglie di mantenere i dati del progetto in locale, è possibile eseguire la migrazione dell'ambiente di Project Server 2010 a Project Server 2013, Project Server 2016 o Project Server 2019.

Se non è possibile eseguire la migrazione a Project Online, è consigliabile eseguire la migrazione a Project Server 2019. Project Server 2019 include la maggior parte delle funzionalità principali delle versioni precedenti di Project Server. Inoltre, corrisponde maggiormente all'esperienza disponibile con Project Online, anche se alcune funzionalità sono disponibili solo in Project Online.

Dopo aver completato ogni migrazione, verificare che la migrazione dei dati sia stata eseguita correttamente.

> [!NOTE]
> Se si è limitati a una soluzione locale e si sta valutando la possibilità di eseguire solo la migrazione a Project Server 2013, è necessario considerare che questa versione ha ancora qualche anno di supporto. Data di fine del supporto per Project Server 2013 con Service Pack 2 13 ottobre 2023. Per ulteriori informazioni sulle date di fine del supporto, vedere Criteri [relativi al ciclo di vita dei prodotti Microsoft.](https://go.microsoft.com/fwlink/p/?linkid=842066)

### <a name="how-do-i-migrate-to-project-server-2019"></a>Come eseguire la migrazione a Project Server 2019

Le differenze architetturali tra Project Server 2010 e Project Server 2019 impediscono un percorso di migrazione diretto. Sarà quindi necessario eseguire la migrazione dei dati di Project Server 2010 a ogni versione successiva di Project Server fino a quando non si raggiunge Project Server 2019. Passaggi per aggiornare Project Server 2010 a Project Server 2019:

1. Eseguire la migrazione a Project Server 2013.

2. Eseguire la migrazione da Project Serve 2013 a Project Server 2016.

3. Eseguire la migrazione da Project Server 2016 a Project Server 2019.

Dopo aver completato ogni migrazione, verificare che la migrazione dei dati sia stata eseguita correttamente.

### <a name="step-1-migrate-to-project-server-2013"></a>Passaggio 1: eseguire la migrazione a Project Server 2013

Per informazioni complete sull'aggiornamento da Project Server 2010 a Project Server 2013, vedere [Upgrade to Project Server 2013.](https://go.microsoft.com/fwlink/p/?linkid=841822)

Risorse chiave:

- [Panoramica del processo di aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Panoramica generale dell'aggiornamento da Project Server 2010 a Project Server 2013.
- [Pianificare l'aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  Esaminare le considerazioni sulla pianificazione durante l'aggiornamento da Project Server 2010 a Project Server 2013, inclusi i requisiti di sistema.

- [Le novità dell'aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841824) riguardano importanti modifiche per questa versione, tra cui:

   - Non è disponibile alcun aggiornamento sul posto a Project Server 2013. Il metodo basato sul collegamento di database è l'unico modo supportato per eseguire l'aggiornamento da Project Server 2010 a Project Server 2013.

   - Il processo di aggiornamento non solo converte i dati di Project Server 2010 nel formato di Project Server 2013, ma consolida anche i quattro database di Project Server 2010 in un singolo database di Project Web App.

   - Sia SharePoint Server 2013 che Project Server 2013 sono stati modificati per l'autenticazione basata sulle attestazioni rispetto alla versione precedente. Se si utilizza l'autenticazione classica, è necessario tenere presente questa considerazione durante l'aggiornamento. Per ulteriori informazioni, vedere [Eseguire la migrazione dall'autenticazione in modalità classica a quella basata su attestazioni in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).

Risorse chiave:

- [Panoramica del processo di aggiornamento a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Aggiornare i database e le raccolte siti di Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Diagramma del processo di aggiornamento di Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [Il grande consolidamento dei database, migrazione da Project Server 2010 a 2013 in 8 semplici passaggi](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Passaggio 2: eseguire la migrazione a Project Server 2016

Dopo il passaggio a Project Server 2013 e la verifica della corretta migrazione dei dati, il passaggio successivo consiste nel eseguire la migrazione a Project Server 2016.

Per ulteriori informazioni, vedere [Upgrade to Project Server 2016.](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)

Risorse chiave:

- [Panoramica del processo di aggiornamento a Project Server 2013](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Comprendere cosa è necessario fare per eseguire l'aggiornamento da Project Server 2013 a Project Server 2016.

- [Pianificare l'aggiornamento a Project Server 2013](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Esaminare le considerazioni sulla pianificazione da tenere in considerazione durante l'aggiornamento da Project Server 2013 a Project Server 2016.

Le informazioni necessarie sull'aggiornamento a [Project Server 2016](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) riguardano importanti modifiche per l'aggiornamento a questa versione, tra cui:

- Quando si crea l'ambiente di Project Server 2016, tenere presente che i file di installazione di Project Server 2016 sono inclusi in SharePoint Server 2016. Per ulteriori informazioni, vedere [Deploy Project Server 2016.](https://go.microsoft.com/fwlink/p/?linkid=841829)

- I piani delle risorse sono deprecati in Project Server 2016. I piani delle risorse di Project Server 2013 verranno migrati agli impegni delle risorse in Project Server 2016 e in Project Online. Per [altre informazioni, vedi Panoramica: impegni delle](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) risorse.

### <a name="step-3-migrate-to-project-server-2019"></a>Passaggio 3: eseguire la migrazione a Project Server 2019

Dopo aver eseguito la migrazione a Project Server 2016 e aver verificato la corretta migrazione dei dati, il passaggio successivo consiste nel eseguire la migrazione dei dati a Project Server 2019.

Per informazioni sulle attività necessarie per eseguire l'aggiornamento da Project Server 2016 a Project Server 2019, vedere Eseguire l'aggiornamento a [Project Server 2019.](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)

Risorse chiave:

- [Panoramica del processo di aggiornamento di Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Informazioni di alto livello sulle attività da eseguire per eseguire l'aggiornamento da Project Server 2013 a Project Server 2016.

- [Pianificare l'aggiornamento a Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Esaminare le considerazioni sulla pianificazione per l'aggiornamento da Project Server 2016 a Project Server 2019.

- [Informazioni necessarie sull'aggiornamento a Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>Informazioni sulle modifiche importanti per l'aggiornamento a questa versione, tra cui:

   - Il processo di aggiornamento eseguirà la migrazione dei dati dal database di Project Server 2016 al database del contenuto di SharePoint Server 2019.  Project Server 2019 non creerà più il proprio database di Project Server nella farm di SharePoint Server.

   - Dopo l'aggiornamento, tenere presenti diverse modifiche in Project Web App.  Per informazioni dettagliate, [vedere Novità di Project Server 2019.](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)

**Altre risorse:**

- [Descrizioni del servizio Project Online:](https://go.microsoft.com/fwlink/p/?linkid=841280)vedere le funzionalità di gestione del portfolio incluse in Project Server 2016 e Project Online Premium.

- [Microsoft Office migrazione di Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Riepilogo delle opzioni per i client e i server di Office 2010 e Windows 7

Per un riepilogo visivo delle opzioni di aggiornamento, migrazione e passaggio al cloud per i client e i server di Office 2010 e Windows 7, vedere il [poster relativo alla fine del supporto](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Fine del supporto per client e server di Office 2010 e poster di Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Questo poster illustra i diversi percorsi che è possibile adottare per evitare la fine del supporto per i prodotti client e server di Office 2010 e Windows 7, con percorsi preferiti e supporto delle opzioni in Microsoft 365 Enterprise evidenziato.

Puoi anche [scaricare questo](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) poster e stamparlo in formato lettera, legale o tabloid (11 x 17).

## <a name="related-topics"></a>Argomenti correlati

[Aggiornamento da SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Aggiornare i server e i client di Office 2010](upgrade-from-office-2010-servers-and-products.md)
