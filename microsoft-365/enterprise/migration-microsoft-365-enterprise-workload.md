---
title: Migrazione a Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Procedura per la migrazione delle versioni di Microsoft Office, Office Server e Windows a Microsoft 365 Enterprise all'interno dell'organizzazione.
ms.openlocfilehash: 53d50321ffa2870fb0e94e9f6b7f005b8c666c2d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631538"
---
# <a name="migration-to-microsoft-365-enterprise"></a>Migrazione a Microsoft 365 Enterprise

La maggior parte delle organizzazioni aziendali presenta un ambiente eterogeneo con più versioni di sistemi operativi, software client e prodotti server. Microsoft 365 Enterprise include le versioni più sicure dei componenti chiave dell'infrastruttura IT, con funzionalità di produttività progettate per sfruttare le tecnologie cloud.

Per ottimizzare il valore aziendale della famiglia integrata dei prodotti Microsoft 365 Enterprise, iniziare a pianificare e implementare una strategia per eseguire la migrazione delle versioni di quanto segue:

- Il client Office installato nei computer per Microsoft 365 Apps for enterprise
- Office Server installato sui server ai servizi equivalenti in Office 365
- Windows 7 e Windows 8.1 sui dispositivi a Windows 10 Enterprise

>[!Note]
>Il **14 gennaio 2020** Windows 7 ha raggiunto la fine del supporto. Per altre informazioni, fare clic [qui](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).
>

Eseguire gradualmente tutte le suddette migrazioni permetterà all'organizzazione di diventare un'[area di lavoro moderna](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/), un ambiente sicuro e integrato che non pone restrizioni al lavoro in team e alla creatività all'interno dell'organizzazione, il tutto gestito attraverso Microsoft 365 Enterprise. 

Per informazioni sulla migrazione degli utenti e dei dati per carichi di lavoro specifici di Office 365:

- Casette postali utente da Exchange Server a Exchange Online, vedere [Carico di lavoro di Exchange Online](exchangeonline-workload.md).
- Dati di SharePoint da SharePoint Server a SharePoint Online, vedere [Carico di lavoro di SharePoint Online](sharepoint-online-onedrive-workload.md).
- Da Skype for Business Online a Microsoft Teams, vedere [Carico di lavoro di Microsoft Teams](teams-workload.md).

## <a name="migration-for-microsoft-office-client-products"></a>Migrazione per i prodotti client di Microsoft Office

In molte organizzazioni, sia grandi che piccole, è molto comune l'utilizzo di versioni precedenti dei prodotti client di Office, come Word, Excel e PowerPoint. Queste versioni precedenti:

- Possono essere [aggiornate](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) con i più recenti aggiornamenti della sicurezza e di risoluzione dei problemi, ma talvolta la procedura è manuale e non applicabile all'organizzazione.
- Non sono abilitate in modo ottimale per sfruttare le tecnologie cloud di Microsoft e consentire la trasformazione digitale della propria azienda.
- Non contengono nuove funzionalità.
 
Microsoft 365 Enterprise include Microsoft 365 Apps for enterprise, una versione dei prodotti client di Office disponibile con una licenza di Microsoft 365 Enterprise, installata e aggiornata da Microsoft Cloud. Microsoft 365 Apps for enterprise include aggiornamenti della sicurezza e le funzionalità più recenti. Per saperne di più, consultare le [informazioni su Microsoft 365 Apps for enterprise nelle grandi imprese](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).

### <a name="office-2007"></a>Office 2007

Per le versioni di Office nel rilascio di Office 2007, la data della fine del supporto è già trascorsa. Per ulteriori informazioni, vedere [Guida sulla fine del supporto di Office 2007](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap).

Anziché aggiornare i computer che eseguono Office 2007 a Office 2010, Office 2013 o Office 2016, è consigliabile:

1. Ottenere e assegnare una licenza Microsoft 365 agli utenti.
2. Disinstallare Office 2007 dai computer.
3. Installazione di Microsoft 365 Apps for enterprise, singolarmente o in combinazione con un'implementazione IT. Per altre informazioni, vedere [Fase 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md).

Microsoft 365 Apps for enterprise installa automaticamente gli aggiornamenti e sfrutta servizi basati sul cloud per la protezione avanzata e la produttività.

### <a name="office-2010"></a>Office 2010

Per le versioni di Office nel rilascio di Office 2010, la fine del supporto è il **13 ottobre 2020**. Per altre informazioni, vedere [Roadmap della fine del supporto di Office 2010](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap).

Anziché aggiornare i computer che eseguono Office 2010 a Office 2013 o Office 2016 (entrambi da aggiornare manualmente), è consigliabile: 

1. Ottenere e assegnare una licenza Microsoft 365 agli utenti.
2. Disinstallare Office 2010 dai computer.
3. Installazione di Microsoft 365 Apps for enterprise, singolarmente o in combinazione con un'implementazione IT. Per altre informazioni, vedere [Fase 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md).

Microsoft 365 Apps for enterprise installa automaticamente gli aggiornamenti della sicurezza e le nuove funzionalità e sfrutta servizi basati sul cloud in Microsoft 365 per la protezione avanzata e la produttività.

### <a name="office-2013-and-office-2016"></a>Office 2013 e Office 2016

La roadmap per la fine del supporto per le versioni di Office 2013 e Office 2016 non è stata ancora definita. Tuttavia, come per Office 2010, è necessario [installare gli aggiornamenti della sicurezza](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5), che potrebbero non fornire la scalabilità adeguata a seconda delle dimensioni dell'organizzazione.

Anziché continuare ad aggiornare i computer in uso con gli aggiornamenti della sicurezza più recenti per Office 2013 o Office 2016 o anziché aggiornare i computer in uso da Office 2013 a Office 2016, prendere in considerazione quanto segue:

1. Ottenere e assegnare una licenza Microsoft 365 agli utenti.
2. Disinstallare Office 2013 o Office 2016 dai computer.
3. Installazione di Microsoft 365 Apps for enterprise, singolarmente o in combinazione con un'implementazione IT. Per altre informazioni, vedere [Fase 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md).

Microsoft 365 Apps for enterprise installa automaticamente gli aggiornamenti della sicurezza e le nuove funzionalità e sfrutta servizi basati sul cloud in Microsoft 365 per la protezione avanzata e la produttività.

## <a name="migration-for-microsoft-office-server-products"></a>Migrazione per i prodotti server di Microsoft Office

In molte organizzazioni, sia grandi che piccole, è molto comune l'utilizzo di versioni precedenti dei prodotti di Office Server, come Exchange Server e SharePoint Server. Queste versioni precedenti:

- Devono essere aggiornate con gli aggiornamenti più recenti della sicurezza e di risoluzione dei problemi. In alcuni casi, tali aggiornamenti vengono rilasciati mensilmente.
- Non sono abilitate in modo ottimale per sfruttare le tecnologie cloud di Microsoft e consentire la trasformazione digitale della propria azienda.
- Non includono nuove applicazioni per la produttività, come Microsoft Teams.
- Non includono le funzionalità di sicurezza più recenti, come Exchange Advanced Threat Protection.

Microsoft 365 Enterprise include Office 365, che presenta versioni basate sul cloud dei servizi server di Office che sfruttano alcuni degli stessi strumenti delle versioni locali del prodotto server di Office, come Web browser e il client di Outlook. Questi servizi vengono continuamente aggiornati in termini di sicurezza senza coinvolgere l'IT, consentendo agli utenti di risparmiare tempo per gestire e aggiornare i server locali. Questi servizi dispongono anche di nuovi miglioramenti delle funzionalità che non sono presenti nel prodotto server di Office. 

### <a name="office-server-2007"></a>Office Server 2007

Per i prodotti server nel rilascio di Office 2007, la data della fine del supporto è già trascorsa. Vedere i seguenti articoli per i dettagli:

- [Guida sulla fine del supporto di Exchange 2007](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [Guida sulla fine del supporto di SharePoint Server 2007](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [Guida sulla fine del supporto di Project Server 2007](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [Guida sulla fine del supporto di Office Communications Server](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [Guida sulla fine del supporto di PerformancePoint Server 2007](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

Anziché aggiornare i prodotti server nel rilascio di Office 2007 con i prodotti server nel rilascio di Office 2010, Office 2013 o Office 2016, è consigliabile:

1. Eseguire la migrazione dei dati sui server di Office 2007 a Office 365. Per ricevere assistenza durante questa procedura, contattare un partner Microsoft.
2. Presentare le nuove funzionalità e i processi di lavoro agli utenti.
3. Se i server locali che eseguono prodotti server di Office 2007 non sono più necessari, rimuoverli.

### <a name="office-server-2010"></a>Office Server 2010

La fine del supporto per [Exchange Server 2010](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support) è prevista per il **13 ottobre 2020**.

La fine del supporto per [SharePoint Server 2010](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010) è prevista per il **13 aprile 2021**.

Anziché aggiornare questi prodotti server nel rilascio di Office 2010 con i prodotti server nel rilascio di Office 2013 o Office 2016, è consigliabile:

1. Eseguire la migrazione dei dati sui server di Office 2010 a Microsoft 365. Per informazioni in merito, vedere [FastTrack per Microsoft 365](https://fasttrack.microsoft.com/microsoft365) o assumere un partner Microsoft.
2. Presentare le nuove funzionalità e i processi di lavoro agli utenti.
3. Se i server locali che eseguono prodotti server di Office 2010 non sono più necessari, rimuoverli.

### <a name="office-server-2013"></a>Office Server 2013

Per i prodotti server nel rilascio di Office 2013, la data della fine del supporto non è ancora stata determinata. Anziché aggiornare i prodotti server nel rilascio di Office 2013 con i prodotti server nel rilascio di Office 2016, è consigliabile:

1. Eseguire la migrazione dei dati sui server di Office 2013 a Office 365. Per ricevere assistenza durante questa procedura, vedere [FastTrack per Microsoft 365](https://fasttrack.microsoft.com/microsoft365) o contattare un partner Microsoft.
2. Presentare le nuove funzionalità e i processi di lavoro agli utenti.
3. Se i server locali che eseguono prodotti server di Office 2013 non sono più necessari, rimuoverli.

### <a name="office-server-2016"></a>Office Server 2016

Per i prodotti server nel rilascio di Office 2016, la data della fine del supporto non è ancora stata determinata. Per sfruttare il servizio basato sul cloud e i miglioramenti nella trasformazione digitale della propria azienda, è consigliabile:

1. Eseguire la migrazione dei dati sui server di Office 2016 a Office 365. Per ricevere assistenza durante questa procedura, vedere [FastTrack per Microsoft 365](https://fasttrack.microsoft.com/microsoft365) o contattare un partner Microsoft.
2. Presentare le nuove funzionalità e i processi di lavoro agli utenti.
3. Se i server locali che eseguono prodotti server di Office 2016 non sono più necessari, rimuoverli.

## <a name="migration-for-microsoft-windows-7-and-81"></a>Migrazione per Microsoft Windows 7 e 8.1

Il **14 gennaio 2020** Windows 7 ha raggiunto la fine del supporto. Per eseguire la migrazione dei dispositivi con sistema operativo Windows 7 o Windows 8.1, è possibile eseguire un [aggiornamento sul posto](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade). 

Per altri metodi, vedere [Scenari di distribuzione di Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). È anche possibile [pianificare la distribuzione di Windows 10](https://aka.ms/planforwin10deployment) autonomamente.

## <a name="summary-of-options-for-office-2010-clients-and-servers-and-windows-7"></a>Riepilogo delle opzioni per i client e server di Office 2010 e Windows 7

Per un riepilogo visivo delle opzioni di aggiornamento, migrazione e passaggio al cloud per questi prodotti, vedere il [poster relativo alla fine del supporto](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf).

[![Immagine del poster per la fine del supporto per client e server di Office 2010 e Windows 7](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)

Questo poster di una pagina rappresenta un modo rapido per comprendere i vari percorsi che è possibile eseguire per evitare che i prodotti client e server di Office 2010 e Windows 7 raggiungano la fine del supporto, evidenziando i percorsi preferiti e il supporto delle opzioni in Microsoft 365 Enterprise.

È possibile [scaricare il poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Informazioni su come gli esperti IT di Microsoft hanno eseguito la migrazione della società a Microsoft 365 Enterprise con queste risorse: 

- [Distribuzione e aggiornamento di Microsoft 365 Apps for enterprise](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft esegue la migrazione di 150.000 cassette postali a Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [SharePoint nel cloud: informazioni su come Microsoft ha eseguito la migrazione](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [Distribuzione di Windows 10 in Microsoft come aggiornamento sul posto](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Distribuzione di Windows 10: suggerimenti e consigli da IT Microsoft](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)

## <a name="transition-your-entire-organization"></a>Transizione dell'intera organizzazione

Per avere un quadro più completo su come spostare l'intera organizzazione ai prodotti e servizi in Microsoft 365 Enterprise, vedere il [poster di transizione](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf).

[![Immagine per il poster di transizione a Microsoft 365](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)

Questo poster con due pagine rappresenta un modo rapido per inventariare l'infrastruttura esistente e accedere alle indicazioni per passare al prodotto o al servizio corrispondente in Microsoft 365 Enterprise. Include i prodotti Windows e Office e altri elementi di infrastruttura e sicurezza, come la gestione dei dispositivi, l'identità e le informazioni e la protezione dalle minacce.

È possibile [scaricare il poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).

## <a name="result"></a>Risultato

L'organizzazione ha eseguito la migrazione delle precedenti versioni di Microsoft Office, Office Server e Windows a Microsoft 365 Enterprise.
