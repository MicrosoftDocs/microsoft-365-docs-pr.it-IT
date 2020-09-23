---
title: Extensibility di conformità di Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come estendere le soluzioni di conformità di Microsoft 365 utilizzando connettori di dati di terze parti e API di Microsoft Graph.
ms.openlocfilehash: 284125db8243b10f5c8de7e0a37c1b7284709c28
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204401"
---
# <a name="microsoft-365-compliance-extensibility"></a>Extensibility di conformità di Microsoft 365

Le soluzioni di conformità di Microsoft 365 aiutano le organizzazioni a valutare intelligentemente i rischi di conformità, a governare e proteggere i dati sensibili e a rispondere efficacemente ai requisiti normativi. La conformità a Microsoft 365 è ricca di scenari di estensibilità e consente alle organizzazioni di adattarsi, estendere, integrare, accelerare e supportare le soluzioni di conformità.

Sono disponibili due blocchi predefiniti fondamentali per l'estensibilità della conformità:

- **Connettori di dati**. Consente di importare e archiviare i dati non Microsoft in modo da poter applicare le funzionalità di protezione e governance di Microsoft 365 ai dati di terze parti.

- **API**. Consente l'accesso programmatico alle funzionalità di conformità di Microsoft 365.

## <a name="data-connectors"></a>Connettori dati

Microsoft fornisce connettori di dati di terze parti che possono essere configurati nel centro conformità di Microsoft 365. Per un elenco dei connettori di dati forniti da Microsoft, vedere la tabella [dei connettori di dati di terze parti](archiving-third-party-data.md#third-party-data-connectors) . La tabella dei connettori di dati di terze parti riepiloga anche le soluzioni di conformità che è possibile applicare ai dati di terze parti dopo l'importazione e l'archiviazione dei dati in Microsoft 365 e collegamenti alle istruzioni dettagliate per ogni connettore.

Per ulteriori informazioni sui connettori di dati di Microsoft 365, vedere [archiviazione dei dati di terze parti](archiving-third-party-data.md). Se un tipo di dati di terze parti non è supportato dai connettori dati disponibili nel centro conformità di Microsoft 365, è possibile collaborare con un partner che può fornire un connettore personalizzato. Per un elenco di partner che è possibile utilizzare e per il processo dettagliato per questo metodo, vedere [collaborare con un partner per archiviare i dati di terze parti](work-with-partner-to-archive-third-party-data.md).

### <a name="prerequisites-for-data-connectors"></a>Prerequisiti per i connettori dati

Molti dei connettori dati disponibili nel centro conformità di Microsoft 365 per importare e archiviare i dati di terze parti richiedono la preparazione e l'esecuzione di attività di configurazione nell'origine dati di terze parti. Questi prerequisiti sono documentati in dettaglio per ogni connettore di dati di terze parti.

Per i connettori dati nel centro conformità di Microsoft 365 fornito da uno dei partner di Microsoft, l'organizzazione avrà bisogno di una relazione commerciale con il partner prima di poter distribuire un connettore.

È possibile trovare i requisiti di licenza per i connettori di dati di terze parti nel documento di [confronto di Microsoft 365 Compliance Licensing](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) .

## <a name="apis"></a>API

Le API di conformità di Microsoft 365 sono disponibili nell'SDK di Microsoft Information Protection, nell'API di Microsoft Graph e nell'API di gestione delle attività di Office 365. Alcune API di conformità fanno parte di un nuovo set di API per la sicurezza e la conformità che consentono agli sviluppatori di clienti Microsoft 365, fornitori di software indipendenti, System Integrator e provider di servizi di sicurezza gestiti per creare soluzioni di sicurezza e conformità di alto valore.

Per ulteriori informazioni su come accedere alle API del grafico, vedere [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).

### <a name="microsoft-information-protection-mip-sdk"></a>SDK di Microsoft Information Protection (MIP)

L'SDK MIP espone i servizi di etichettatura e protezione dai centri di sicurezza e conformità di Microsoft 365 a applicazioni e servizi di terze parti. Gli sviluppatori possono utilizzare l'SDK per creare il supporto nativo per l'applicazione di etichette e la protezione ai file. Gli sviluppatori possono determinare quali azioni devono essere intraprese quando vengono rilevate etichette specifiche e la causa delle informazioni crittografate tramite MIP.

I casi di utilizzo di High-Level MIP SDK includono:

- Applicazione line-of-business che applica etichette di classificazione ai file all'esportazione.

- Applicazione di progettazione CAD/CAM che fornisce il supporto nativo per l'etichettatura MIP.

- Una soluzione per la prevenzione della perdita di dati o un cloud Access che consente di crittografare i dati con Azure Information Protection.

Per ulteriori informazioni sull'SDK MIP, sui prerequisiti, sugli scenari aggiuntivi e sugli esempi, vedere [MIP SDK Overview](https://docs.microsoft.com/information-protection/develop/overview).

### <a name="microsoft-graph-api-for-teams-dlp"></a>API di Microsoft Graph per Team DLP

Le funzionalità di [prevenzione della perdita di dati (DLP)](dlp-microsoft-teams.md) sono ampiamente utilizzate in Microsoft teams in particolare, in quanto le organizzazioni hanno spostato il lavoro a distanza. All'inizio di quest'anno è stata [annunciata l'anteprima pubblica](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) dell'API di notifica delle modifiche di Microsoft Graph per i messaggi in teams. Questa API consente agli sviluppatori di creare app che possono ascoltare i messaggi di Microsoft teams in tempo quasi reale e quindi implementare gli scenari DLP per clienti e partner. Inoltre, Microsoft Graph patch API consente di applicare azioni DLP ai messaggi dei team.

Queste due API formano l'API di Microsoft Graph per i team DLP. È possibile iniziare provando l' [app di esempio](https://github.com/microsoftgraph/csharp-webhook-with-resource-data). Per ulteriori informazioni sui webhook di messaggistica di Microsoft teams, vedere la [documentazione](https://docs.microsoft.com/graph/api/subscription-post-subscriptions).

Per i requisiti di licenza per i team DLP, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>API di Microsoft Graph per eDiscovery (anteprima)

Con [Advanced eDiscovery](overview-ediscovery-20.md), le organizzazioni possono individuare i dati in cui vive e gestire più flussi di lavoro di eDiscovery end-to-end con funzionalità di apprendimento e analisi intelligente dei computer per ridurre i dati al set pertinente: tutti i dati rimangono all'interno del limite di sicurezza e conformità di Microsoft 365.

Le API del grafico per Advanced eDiscovery possono essere utilizzate per creare e gestire i casi, i set di revisione e esaminare le query di set in modo scalabile e ripetibile. In questo modo i clienti e i partner possono creare app e flussi di lavoro per automatizzare processi comuni e ripetitivi, ad esempio la creazione di casi e la gestione dei depositari e delle detenute legali.

Il primo set di API del grafico per eDiscovery è disponibile in anteprima pubblica. Si prevede di aggiungere altre funzionalità entro la fine dell'anno di calendario. Per ulteriori informazioni su queste API e altri aggiornamenti per Advanced eDiscovery, vedere questo [Blog](https://aka.ms/Ignite2020AeDAA).

Per i requisiti di licenza per Advanced eDiscovery e l'API, vedere la sezione "eDiscovery" in [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery).

### <a name="microsoft-graph-api-for-teams-export-preview"></a>API di Microsoft Graph per l'esportazione di Team (anteprima)

Enterprise Information Archiving (EIA) per Microsoft teams è uno scenario fondamentale per i clienti in quanto consente loro di risolvere i requisiti normativi. Oltre alle funzionalità predefinite per l'archiviazione del contenuto in Microsoft teams, i clienti e i partner possono ora utilizzare le API di esportazione dei team per la risoluzione di scenari di integrazione e applicazioni personalizzate. Le API di esportazione di Team supportano l'esportazione di massa (fino a 200 richieste al secondo/per app/per tenant) dei messaggi e degli allegati ai messaggi di team. I messaggi eliminati sono accessibili anche dall'API fino a 30 giorni dopo l'eliminazione. Per ulteriori informazioni su queste API di esportazione di team e su come utilizzarle nelle applicazioni, vedere [esportare il contenuto con le API di esportazione di Microsoft teams](https://docs.microsoft.com/microsoftteams/export-teams-content).

Per i requisiti di licenza per l'utilizzo delle API di esportazione dei team, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).
