---
title: Passaggio 4. Migrazione per i tenant di Microsoft 365 per Enterprise
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
description: Migrare i dispositivi Windows, le app client di Office e i server di Office per i tenant Microsoft 365.
ms.openlocfilehash: 3230f7e1087b573691f04b9335a15b4ad6d20b65
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908627"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Passaggio 4. Migrazione per i tenant di Microsoft 365 per Enterprise

La maggior parte delle organizzazioni dell'organizzazione dispone di un ambiente eterogeneo che include più versioni di sistemi operativi, software client e server. Microsoft 365 per Enterprise include le versioni più sicure dei componenti chiave dell'infrastruttura IT. Include anche funzionalità di produttività progettate per sfruttare le tecnologie cloud.

Per massimizzare il valore aziendale della famiglia di prodotti integrata Microsoft 365 for Enterprise, iniziare la pianificazione e l'implementazione di una strategia per la migrazione delle versioni seguenti:

| Da | A |
|:-------|:-----|
| Windows 7 e Windows 8,1 | Windows 10 Enterprise |
| Prodotti client di Office installati nei dispositivi del lavoratore | Microsoft 365 Apps for enterprise |
| Prodotti di Office Server installati nei server locali | Servizi basati su cloud equivalenti in Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Migrazione a Windows 10

Ogni licenza di Microsoft 365 per Enterprise include una licenza per Windows 10 Enterprise. Per eseguire la migrazione dei dispositivi che eseguono Windows 7 o Windows 8,1, è possibile eseguire un aggiornamento sul posto. Supporto finito per Windows 7 *gennaio 14 2020*. 

Per ulteriori metodi di installazione di Windows 10 Enterprise oltre a un aggiornamento sul posto, vedere [scenari di distribuzione di Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). È anche possibile [pianificare la distribuzione di Windows 10](https://aka.ms/planforwin10deployment) autonomamente.

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Migrazione a Microsoft 365 Apps for Enterprise

Microsoft 365 per Enterprise include Microsoft 365 Apps for Enterprise, una versione dei prodotti client di Office (Word, PowerPoint, Excel e Outlook) installata e aggiornata da Microsoft Cloud. Per ulteriori informazioni, vedere [About Microsoft 365 Apps for Enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).

Anziché mantenere aggiornati i computer per le versioni di Office 2019 o versione precedente, eseguire le operazioni seguenti:

1. Ottenere e assegnare una licenza Microsoft 365 per gli utenti.
2. Disinstallare Office 2013 o Office 2016 nei propri computer.
3. Installare le app Microsoft 365 per Enterprise, individualmente o durante un'implementazione IT. Per ulteriori informazioni, vedere [Deployment Guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).

Microsoft 365 Apps for Enterprise installa automaticamente sia gli aggiornamenti della sicurezza che i nuovi aggiornamenti delle funzionalità e può avvalersi dei servizi basati su cloud in Microsoft 365 per garantire una maggiore sicurezza e produttività.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>Migrazione di dati e server locali a Microsoft 365

Microsoft 365 per Enterprise include versioni basate su cloud dei servizi di Office Server che utilizzano alcuni degli stessi strumenti delle versioni locali del software di Office Server, ad esempio i Web browser e il client di Outlook. Questi servizi basati sul cloud vengono aggiornati automaticamente per la sicurezza e le nuove funzionalità. Dopo la migrazione, il reparto IT può salvare il tempo necessario per gestire e aggiornare i server locali.

Utilizzare le risorse seguenti per informazioni sulla migrazione di utenti e dati per carichi di lavoro specifici di Microsoft 365:

- [Spostare le cassette postali dal server Exchange locale a Exchange Online](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [Eseguire la migrazione dei dati di SharePoint da SharePoint Server a SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [Eseguire la migrazione di Skype for business online a Microsoft Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Transizione dell'intera organizzazione

Per ottenere un'immagine migliore di come spostare l'intera organizzazione ai prodotti e ai servizi in Microsoft 365 for Enterprise, scaricare questo poster di transizione:

[![Immagine che mostra la transizione al poster di Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Questo poster di due pagine è modo rapido per inventariare l'infrastruttura esistente. Utilizzarlo per ottenere indicazioni per il passaggio a un prodotto o a un servizio in Microsoft 365 per Enterprise. Vengono visualizzati i prodotti Windows e Office e altri elementi di infrastruttura e sicurezza, quali gestione dei dispositivi, identità e protezione delle minacce e protezione delle informazioni e conformità.

## <a name="results-of-step-4"></a>Risultati del Passaggio 4

Per la migrazione per il tenant di Microsoft 365, sono state determinate le seguenti operazioni:

- Quali dispositivi eseguono Windows 7 o Windows 8,1 e il piano per aggiornarli a Windows 10 Enterprise.
- Quali dispositivi eseguono le app client di Office e il piano di aggiornamento a Microsoft 365 Apps for Enterprise.
- Quali servizi di Office Server locali devono essere migrati nell'equivalente Microsoft 365 e il piano per la migrazione e i relativi dati.

Di seguito è riportato un esempio di un tenant con una migrazione completata dei server locali.

![Esempio di un tenant con una migrazione completata dei server locali](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

In questa figura, l'organizzazione dispone di:

- È stata eseguita la migrazione delle cassette postali di Exchange Server locali a Exchange Online.
- Sono stati migrati i siti e i dati di SharePoint Server locali in SharePoint in Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Manutenzione continua per la migrazione

Su base continuativa, potrebbe essere necessario eseguire le operazioni seguenti:

- A seconda dello stato della migrazione delle cassette postali di Exchange, continuare a eseguire il passaggio a Exchange Online all'organizzazione.
- A seconda dello stato della migrazione del sito di SharePoint locale, continuare a eseguire il passaggio a SharePoint in Microsoft 365 all'organizzazione.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 5. Distribuire la gestione di dispositivi e app](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Continuare con la [gestione di dispositivi e app](tenant-management-device-management.md) per distribuire la gestione di dispositivi e app.
