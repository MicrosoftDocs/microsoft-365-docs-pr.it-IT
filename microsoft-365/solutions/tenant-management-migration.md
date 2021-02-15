---
title: Passaggio 4. Migrazione per i tenant di Microsoft 365 per le aziende
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Eseguire la migrazione dei dispositivi Windows, delle app client di Office e dei server Office per i tenant di Microsoft 365.
ms.openlocfilehash: 3230f7e1087b573691f04b9335a15b4ad6d20b65
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908627"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Passaggio 4. Migrazione per i tenant di Microsoft 365 per le aziende

La maggior parte delle organizzazioni aziendali dispone di un ambiente eterogeneo che include più versioni di sistemi operativi, software client e software server. Microsoft 365 per le aziende include le versioni più sicure dei componenti chiave dell'infrastruttura IT. Include anche funzionalità di produttività progettate per sfruttare le tecnologie cloud.

Per ottimizzare il valore aziendale della famiglia di prodotti integrata di Microsoft 365 per le aziende, iniziare a pianificare e implementare una strategia per eseguire la migrazione di queste versioni:

| Da | A |
|:-------|:-----|
| Windows 7 e Windows 8.1 | Windows 10 Enterprise |
| Prodotti client di Office installati nei dispositivi dei lavoratori | Microsoft 365 Apps for enterprise |
| Prodotti server di Office installati nei server locali | Servizi basati su cloud equivalenti in Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Migrazione a Windows 10

Ogni licenza di Microsoft 365 per le aziende include una licenza per Windows 10 Enterprise. Per eseguire la migrazione dei dispositivi che eseguono Windows 7 o Windows 8.1, puoi eseguire un aggiornamento sul posto. Il supporto per Windows 7 è terminato *il 14 gennaio 2020.* 

Per altri metodi di installazione di Windows 10 Enterprise oltre a un aggiornamento sul posto, vedi Scenari di distribuzione [di Windows 10.](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios) È anche possibile [pianificare la distribuzione di Windows 10](https://aka.ms/planforwin10deployment) autonomamente.

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Migrazione a Microsoft 365 Apps for enterprise

Microsoft 365 per le aziende include Microsoft 365 Apps for enterprise, una versione dei prodotti client di Office (Word, PowerPoint, Excel e Outlook) installata e aggiornata dal cloud Microsoft. Per altre informazioni, vedere [Informazioni su Microsoft 365 Apps for enterprise.](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)

Anziché mantenere i computer correnti per Office 2019 o versioni precedenti, eseguire la procedura seguente:

1. Ottenere e assegnare una licenza di Microsoft 365 per gli utenti.
2. Disinstallare Office 2013 o Office 2016 nei propri computer.
3. Installare Microsoft 365 Apps for enterprise, singolarmente o durante un'implementazione IT. Per altre informazioni, vedere [Guida alla distribuzione di Microsoft 365 Apps.](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

Microsoft 365 Apps for enterprise installa automaticamente gli aggiornamenti della sicurezza e i nuovi aggiornamenti delle funzionalità e può sfruttare i servizi basati sul cloud in Microsoft 365 per una maggiore sicurezza e produttività.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>Migrazione di dati e server locali a Microsoft 365

Microsoft 365 per le aziende include versioni basate sul cloud dei servizi server di Office che utilizzano alcuni degli stessi strumenti delle versioni locali del software server di Office, ad esempio i Web browser e il client Outlook. Questi servizi basati sul cloud vengono aggiornati automaticamente per la sicurezza e le nuove funzionalità. Dopo la migrazione, il reparto IT può risparmiare tempo necessario per gestire e aggiornare i server locali.

Utilizzare le risorse seguenti per informazioni sulla migrazione di utenti e dati per carichi di lavoro di Microsoft 365 specifici:

- [Spostare le cassette postali dai Exchange Server locali a Exchange Online](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [Eseguire la migrazione dei dati di SharePoint da SharePoint Server a SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [Eseguire la migrazione di Skype for Business online a Microsoft Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Transizione dell'intera organizzazione

Per ottenere un quadro migliore di come spostare l'intera organizzazione nei prodotti e servizi in Microsoft 365 per le aziende, scaricare questo poster di transizione:

[![Immagine che mostra il poster transizione a Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Questo poster di due pagine è modo rapido per inventariare l'infrastruttura esistente. Usarlo per ottenere indicazioni per il passaggio a un prodotto o un servizio in Microsoft 365 per le aziende. Mostra i prodotti Windows e Office e altri elementi di infrastruttura e sicurezza come la gestione dei dispositivi, la protezione da identità e minacce, la protezione e la conformità delle informazioni.

## <a name="results-of-step-4"></a>Risultati del Passaggio 4

Per la migrazione per il tenant di Microsoft 365, è stato determinato:

- Quali dispositivi eseguono Windows 7 o Windows 8.1 e il piano per aggiornarli a Windows 10 Enterprise.
- Quali dispositivi eseguono le app client di Office e il piano per aggiornarli alle app di Microsoft 365 per le aziende.
- Quali servizi server di Office locali devono essere migrati nell'equivalente di Microsoft 365 e il piano per eseguirne la migrazione e i relativi dati.

Ecco un esempio di tenant con una migrazione completa dei server locali.

![Esempio di un tenant con una migrazione completata dei server locali](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

In questa figura, l'organizzazione ha:

- È stata eseguita la migrazione delle cassette postali Exchange Server locali a Exchange Online.
- È stata eseguita la migrazione dei siti e dei dati di SharePoint Server locali a SharePoint in Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Manutenzione continua per la migrazione

Su base continuativa, potrebbe essere necessario:

- A seconda dello stato della migrazione delle cassette postali di Exchange, continuare a eseguire la transizione a Exchange Online nell'organizzazione.
- A seconda dello stato della migrazione del sito di SharePoint locale, continuare a eseguire la transizione a SharePoint in Microsoft 365 all'organizzazione.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 5. Distribuire la gestione di dispositivi e app](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Continua con la [gestione di dispositivi e app](tenant-management-device-management.md) per distribuire la gestione di dispositivi e app.
