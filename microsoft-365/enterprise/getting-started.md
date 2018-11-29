---
title: Guida introduttiva - Centro di distribuzione desktop moderno
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Introduzione al processo di distribuzione desktop moderno.
ms.openlocfilehash: bb5c1433554e984676884fd2bac4fa5120c76996
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868691"
---
# <a name="getting-started---modern-desktop-deployment"></a>Guida introduttiva - Centro di distribuzione desktop moderno

Il cloud sta cambiando il modo in cui viene gestita la gestione del PC grazie a Microsoft Intelligent Cloud, che fornisce informazioni dettagliate per aiutare i professionisti IT nel passaggio a un desktop moderno. Quest'articolo ha lo scopo di aiutare l'utente nell'attività di pianificazione e nel passaggio a un desktop moderno basato su Windows 10 e Office 365 ProPlus.

<img src="media/getting-started-media/getting-started-media-1.png" alt="Desktop Deployment Wheel" style="background-color: #fff;" />

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-1.png" alt="Getting Started" height="130" width="130" /></td>
<td><p><strong>Guida introduttiva: indicazioni su utenti, processi e tecnologia</strong></p>
<p>Informazioni sui vantaggi di un desktop moderno, le modifiche principali e considerazioni sulla distribuzione precedente e procedure consigliate per garantire una transizione a Windows 10 e Office 365 ProPlus priva di problemi.</p></td>
<td><a href="https://aka.ms/ddev0" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-13.png" alt="Getting Started" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>In quest'articolo verranno illustrati i modi migliori per utilizzare gli strumenti esistenti e verranno presentate nuove tecnologie, servizi e metodi abilitati dal cloud. Per vedere il processo di distribuzione desktop completo, visitare il [centro di distribuzione desktop moderno](https://aka.ms/HowToShift).
>

Nel Centro di distribuzione desktop moderno verrà illustrato come pianificare ed effettuare il passaggio al desktop moderno, che consentirà di sfruttare uno spazio di lavoro sicuro, alimentato dalle ultime esperienze di produttività, lavoro di squadra e collaborazione.

Il processo di distribuzione è fortemente migliorato. Anche se già da qualche tempo non sono stati implementati nuovi ambienti desktop, oggi è possibile affidarsi con serenità ai nuovi strumenti e alle nuove informazioni dettagliate fornite dal cloud che consentono di superare gli ostacoli del passato, quali ad esempio la compatibilità delle applicazioni, in modo più rapido ed efficiente che mai.

Nella presente introduzione verrà descritto cosa è cambiato nel diagramma circolare del Desktop Deployment. Questo diagramma guiderà l'utente attraverso i passaggi consigliati per il passaggio a Windows 10 e Office 365 ProPlus, illustrando man mano come utilizzare al meglio gli strumenti e i processi esistenti, mediante l'adozione di tecnologie di gestione e approcci moderni.

## <a name="why-upgrade"></a>Scopo dell'aggiornamento

L'uso combinato di Windows 10 e Microsoft Intelligence Cloud consente di offrire agli utenti un'area di lavoro più stimolante, elaborata e protetta e di semplificare l'infrastruttura di supporto.

Uno dei principali responsabili delle moderne pratiche di gestione consiste nei dispositivi sempre aggiornati. Il presente articolo riporta le nuove funzionalità fornite per aiutare nel passaggio a Windows 10 e Office 365 ProPlus e per rimanere aggiornati con le versioni semestrali di entrambi.

[Windows 10 per IT Pro](https://www.microsoft.com/it-IT/itpro/windows-10)

## <a name="what-has-changed"></a>Che cosa è cambiato

Iniziamo ad osservare cosa è cambiato ed è stato migliorato dall'ultima distribuzione desktop. Se non è stato cambiato l'ambiente desktop da qualche tempo, probabilmente si utilizza Windows 7 e Office 2010 o Office 2013. In tal caso, si noterà che alcune cose sono cambiate dall'ultimo aggiornamento principale (di seguito vengono riportati alcuni dei cambiamenti principali):

**Gestione delle identità e accesso**. Il desktop moderno, con la sua connettività ai servizi di produttività, sicurezza e gestione del cloud, ha al suo interno un nuovo servizio di gestione delle identità e accesso: Azure Active Directory, che consente Single Sign-On e connettività sicura tra i servizi cloud. Pertanto, sarà necessario disporre di Azure AD sul posto, per usufruire dei servizi Microsoft 365 come Office 365, Intune o Windows Autopilot.

[Microsoft 365](https://www.microsoft.com/it-IT/microsoft-365/default.aspx)

**Protezione dell'ambiente di preavvio**. Il firmware UEFI a 64 bit sostituisce il BIOS. Questo non solo accelera i tempi di avvio, ma risulta anche necessario per abilitare molte delle moderne funzionalità di sicurezza di Windows 10. Windows 10 verrà eseguito su BIOS, tuttavia UEFI è fortemente raccomandato. Se ancora non è stato effettuato il passaggio dal BIOS a UEFI a 64-bit, questo è il momento giusto. Esistono strumenti che facilitano il passaggio sia durante che dopo l'aggiornamento a Windows 10.

[Conversione da BIOS a UEFI con MBR2GPT](https://technet.microsoft.com/it-IT/windows/mt782786.aspx)

**Gestione di dispositivi basati su cloud**. Grazie a servizi come Microsoft Intune è possibile gestire dispositivi Windows 10 e altri dispositivi mobili, tutti da un'unica posizione. Ciò che rende unico Microsoft Intune è la possibilità di gestire contemporaneamente i dispositivi Windows 10 con System Center Configuration Manager. È possibile utilizzare System Center Configuration Manager per facilitare il passaggio a Windows 10 e quindi aggiungere Microsoft Intune, che consente a System Center Configuration Manager di divenire una rete perimetrale intelligente all'interno dell'organizzazione, connesso al cloud intelligente Microsoft. In questo modo, i dispositivi degli utenti possono essere gestiti in modo sicuro ovunque essi siano, sia connessi alla propria organizzazione sia nel cloud pubblico.

[Gestione contemporanea di dispositivi Windows 10](https://docs.microsoft.com/it-IT/sccm/core/clients/manage/co-management-overview)

**Servizio di distribuzione basata su cloud**. Nei nuovi PC disponibili per l'acquisto è stato introdotto un nuovo servizio cloud per la distribuzione di dispositivi Microsoft 365. Si tratta del servizio di distribuzione Windows Autopilot. AutoPilot è integrato nei provider di hardware e i nuovi PC vengono registrati automaticamente in AutoPilot con la vendita all'utente finale. Alla prima accensione del PC, questo viene rapidamente configurato con la configurazione dell'organizzazione e può essere personalizzato in base a specifiche esigenze dell'utente.

[Windows Autopilot](https://www.microsoft.com/it-IT/windowsforbusiness/windows-autopilot)

**Distribuzione a portata di clic**. Quando si esegue il provisioning delle app desktop di Office, Office 365 ProPlus è l'opzione preferita. Ciò consente di accedere alle più recenti innovazioni di Office man mano che vengono sviluppate, quindi non sarà necessario aspettare anni prima di ottenere nuove funzionalità. Inoltre verrà utilizzata una nuova installazione chiamata A portata di clic.

"A portata di clic" è molto diversa dai pacchetti basati su MSI del passato. È più veloce, più leggera e utilizza lo streaming del programma per consentire agli utenti di essere operativi in pochi minuti e di essere aggiornati in background. Ad ogni modo, è pur sempre una copia locale di Office e l'utente può continuare a utilizzare gli strumenti di distribuzione esistenti, come System Center Configuration Manager, per eseguire il provisioning e configurare le app.

[Guida alla distribuzione di Office 365 ProPlus](https://docs.microsoft.com/it-IT/DeployOffice/deployment-guide-for-office-365-proplus)

**Aggiornamenti semestrali**. Una volta effettuato il passaggio a Windows 10 e Office 365 ProPlus, gli aggiornamenti vengono offerti ogni sei mesi con nuove funzionalità. Tuttavia, poiché Microsoft è in grado di fornire informazioni dettagliate dal cloud, l'utente può distribuire questi aggiornamenti a centinaia o migliaia di dispositivi in modo rapido e sicuro. Analogamente a un aggiornamento sul posto, Feature Update conserva app, dati e configurazioni della versione precedente.

## <a name="the-deployment-process-wheel"></a>Diagramma circolare del processo di distribuzione

Prima di iniziare, sarà necessario creare un piano di alto livello e trascinare a bordo i finanziatori necessari. Il diagramma circolare del processo di distribuzione delinea i passaggi critici che consentono di identificare i membri del nucleo centrale e le risorse da gestire nelle seguenti aree di implementazione.

**[Passaggio 1: conformità di dispositivi e app](https://aka.ms/mdd1)**. Per una distribuzione di successo è necessario sapere cosa si ha a disposizione, ovvero, fare un inventario di dispositivi e app e verificarne la compatibilità.

A tale scopo, è possibile utilizzare gli strumenti disponibili nel servizio basato su cloud, Windows Analytics. Windows Analytics consente di sfruttare l'intelligenza di compatibilità e telemetria raccolte da centinaia di milioni di PC, per valutare le app e i driver in esecuzione sul dispositivo in modo da poter stabilire la disponibilità del desktop. È anche possibile esportare un elenco di "PC pronti per la distribuzione" da Windows Analytics a System Center Configuration Manager, se utilizzato, per creare raccolte di PC specifici basate sui dati non appena disponibili.

[Introduzione alla preparazione aggiornamenti](https://docs.microsoft.com/it-IT/windows/deployment/upgrade/upgrade-readiness-get-started)

**[Passaggio 2: preparazione di rete e directory](https://aka.ms/mdd2)**. Se non è stato implementato Azure Active Directory per la gestione di identità e accessi, lo consigliamo vivamente. Sarà inoltre necessario preparare la rete allo spostamento di immagini di sistema, pacchetti di applicazioni, file utente e aggiornamenti, ovvero una grande quantità di dati aggiuntivi. La rete dovrà avere la capacità di gestire questo carico extra senza avere alcun impatto sul lavoro quotidiano dell'organizzazione. A tale scopo è disponibile una vasta gamma di ottimizzazioni della rete, dalla limitazione della larghezza di banda e opzioni peer-to-peer allo scavenging dinamico della larghezza di banda e l'aggiornamento differenziale.

[BranchCache versus Peer cache](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**[Passaggio 3: offerta di app Office e line-of-business](https://aka.ms/mdd3)**. Pur continuando a supportare le installazioni basate su MSI, Microsoft ora supporta anche i più recenti meccanismi di installazione, ottimizzati per la distribuzione automatizzata e gli aggiornamenti continui. I client Office 365 ProPlus e Windows 2019 utilizzano A portata di clic, tuttavia è possibile scegliere tra una vasta gamma di app UWP e sono sempre più disponibili app di implementazione di terze parti e app line-of-business sviluppate internamente che utilizzano nuove app per il packaging basate su MSIX. Questo passaggio assicura che le app siano pronte per l'implementazione automatizzata e che l'utente ne tragga giovamento indipendentemente dall'uso di applicazioni implementate tramite A portata di clic, MSIX, app convenzionali basate su MSI o app UWP distribuite da Microsoft Store da un'azienda configurata.

[Introduzione a MSIX](https://blogs.msdn.microsoft.com/sgern/2018/06/15/msix-intro/)

**[Passaggio 4: migrazione di impostazioni e file dell'utente](https://aka.ms/mdd4)**. Si tratta di un passaggio fondamentale in qualsiasi ciclo di sostituzione o aggiornamento del PC: è necessario garantire che i file, i dati e le impostazioni degli utenti vengano trasferiti correttamente e che vengano preservati durante la migrazione. Questo passaggio copre le opzioni disponibili per le migrazioni manuali o automatizzate, comprese le opzioni già note e quelle nuove.

Analogamente a quanto accadeva negli aggiornamenti precedenti, l'utilità di migrazione stato utente continua ad essere uno strumento prezioso per automatizzare questo processo e rimane parte integrante delle migrazioni orchestrate mediante System Center Configuration Manager o Microsoft Deployment Toolkit. Tuttavia, spostare tutti questi dati durante la migrazione può essere causa di un punto debole temporaneo nella sostituzione del PC, a causa della fisica coinvolta nel doppio trasferimento talvolta di centinaia di gigabyte per PC (prima dal desktop esistente, quindi al nuovo desktop). La nuova opzione abilitata da OneDrive è la funzione Known Folder Move, che sincronizza documenti, immagini e file desktop dell'utente, su larga scala, nel cloud, prima dell'implementazione.

[Reindirizzare e spostare le cartelle note di Windows su OneDrive](https://docs.microsoft.com/it-IT/onedrive/redirect-known-folders)

**[Passaggio 5: sicurezza e conformità](https://aka.ms/mdd5)**. La sicurezza e la conformità sono caratteristiche molto vantaggiose del passaggio a Windows 10 e Office 365 ProPlus. È importante familiarizzare con le nuove funzionalità integrate e confrontarle con quelle già note. Ad esempio, le nuove funzionalità di Windows 10 che utilizzano la sicurezza basata sulla virtualizzazione possono prevenire il furto delle credenziali, proteggere dagli exploit basati su browser e dall'esecuzione di codice dannoso isolando i processi principali e le informazioni riservate dal sistema operativo. Inoltre, i servizi cloud come Advanced Threat Protection offrono una piattaforma unificata per la protezione della sicurezza, il rilevamento post-violazione, l'analisi e la risposta. Advanced Threat Protection può anche proteggere l'utente da allegati e-mail dannosi, collegamenti ipertestuali non sicuri e altro ancora.

[Protezione Microsoft](https://www.microsoft.com/it-IT/security/default.aspx)

**[Passaggio 6: distribuzione del sistema operativo e aggiornamenti delle funzionalità](https://aka.ms/mdd6)**. Una volta preparato tutto, il passo successivo è quello di implementare le immagini del sistema operativo. È possibile eseguire le attività più complesse utilizzando sequenze di attività e infrastruttura System Center Configuration Manage. L'approccio consigliato consiste nell'implementazione in fasi, il per prima cosa individuando un "gruppo di utenti iniziali" dell'organizzazione su cui operare l'implementazione mediante un insieme rappresentativo di hardware e app. Quindi è possibile utilizzare i dati di tali dispositivi e utenti per individuare gradualmente un numero sempre maggiore di PC.

[Introduzione all'implementazione del sistema operativo in System Center Configuration Manager](https://docs.microsoft.com/it-IT/sccm/osd/understand/introduction-to-operating-system-deployment)

**[Passaggio 7: Office e Windows as a Service](https://aka.ms/mdd7)**. Si tratta di un importante cambiamento nel modo in cui si mantiene la proprietà desktop degli utenti. Con il passaggio a Windows 10 (e Office 365 ProPlus) è possibile passare alla gestione di Windows (e Office) as a Service. Anziché eseguire un enorme cambiamento tecnologico dopo pochi anni, introdurrete continuamente nuove capacità, esperienze e sistemi di protezione agli utenti. Gli aggiornamenti semestrali (in autunno e in primavera) delle funzionalità forniscono nuove funzionalità ogni anno, mentre gli aggiornamenti qualitativi mensili conterranno sicurezza, affidabilità e correzioni di bug. Mentre distribuire i client Office 2019 è una scelta, consigliamo vivamente di passare a Office ProPlus, che segue un piano di servizio simile a Windows, quindi anche gli utenti ricevono regolarmente aggiornamenti alle app di Office.

![](media/getting-started-media/getting-started-media-2.png)

[Panoramica di Windows as a Service](https://docs.microsoft.com/it-IT/windows/deployment/update/waas-overview)

**[Passaggio 8: formazione e comunicazione degli utenti](https://aka.ms/mdd8)**. Quest'ultimo passaggio è fondamentale per guidare l'utilizzo di nuove funzionalità volte a migliorare il lavoro di squadra, le comunicazioni, la sicurezza e altro ancora. Prima che l'implementazione estesa sia rivolta agli utenti al di fuori delle prime fasi di adozione, consigliamo di implementare la comunicazione e la formazione degli utenti. Questo aiuterà a guidare i cambiamenti desiderati nel modo in cui le persone usano nuove funzionalità in Office, Windows o altre app e servizi line-of-business. Può risultare utile il servizio di formazione online gratuita tramite Microsoft FastTrack, messo a disposizione dell'utente. Inoltre, sono stati pubblicati piani di comunicazione e tempistiche di esempio gratuiti insieme a modelli di posta elettronica, social e intranet per facilitare il lancio di Windows 10. Come organizzazione di Microsoft 365 o Office 365, anche l'organizzazione potrebbe essere idonea per il supporto diretto.

## <a name="next-step"></a>Passaggio successivo

Ora che sono state illustrate le novità e i cambiamenti ed è stato esaminato il diagramma circolare del processo di distribuzione consigliato, è possibile utilizzare le indicazioni end-to-end e gli strumenti disponibili per iniziare il passaggio a desktop moderno.

## <a name="step-1-device-and-app-readinesshttpsakamsmdd1"></a>[Passaggio 1: conformità di dispositivi e app](https://aka.ms/mdd1)

