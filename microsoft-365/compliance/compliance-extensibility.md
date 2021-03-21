---
title: Estendibilità della conformità di Microsoft 365
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
description: Informazioni sull'estensione delle soluzioni di conformità di Microsoft 365 tramite connettori dati di terze parti e API di Microsoft Graph.
ms.openlocfilehash: 676c0ba41e517dd0c3692fec29a1d4034641b634
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919722"
---
# <a name="microsoft-365-compliance-extensibility"></a>Estendibilità della conformità di Microsoft 365

Le soluzioni di conformità Di Microsoft 365 aiutano le organizzazioni a valutare in modo intelligente i rischi di conformità, a governare e proteggere i dati sensibili e a rispondere in modo efficace ai requisiti normativi. La conformità di Microsoft 365 è ricca di scenari di estendibilità e consente alle organizzazioni di adattare, estendere, integrare, accelerare e supportare le soluzioni di conformità.

Esistono due blocchi predefiniti chiave per l'estendibilità della conformità:

- **Connettori dati**. Consente di importare e archiviare dati non Microsoft in modo da poter applicare le funzionalità di protezione e governance di Microsoft 365 ai dati di terze parti.

- **API**. Consente l'accesso a livello di codice alle funzionalità di conformità di Microsoft 365.

## <a name="data-connectors"></a>Connettori dati

Microsoft fornisce connettori dati di terze parti che possono essere configurati nel Centro conformità Microsoft 365. Per un elenco dei connettori dati forniti da Microsoft, vedere [la tabella Dei](archiving-third-party-data.md#third-party-data-connectors) connettori dati di terze parti. La tabella dei connettori di dati di terze parti riepiloga inoltre le soluzioni di conformità che è possibile applicare ai dati di terze parti dopo l'importazione e l'archiviazione dei dati in Microsoft 365 e collegamenti alle istruzioni dettagliate per ogni connettore.

Per ulteriori informazioni sui connettori dati di Microsoft 365, vedere [Archiviazione di dati di terze parti.](archiving-third-party-data.md) Se un tipo di dati di terze parti non è supportato dai connettori dati disponibili nel Centro conformità Microsoft 365, è possibile collaborare con un partner in grado di fornire un connettore personalizzato. Per un elenco dei partner con cui è possibile lavorare e il processo dettagliato per questo metodo, vedere Collaborare con un partner per archiviare dati [di terze parti.](work-with-partner-to-archive-third-party-data.md)

### <a name="prerequisites-for-data-connectors"></a>Prerequisiti per i connettori dati

Molti dei connettori di dati disponibili nel Centro conformità Microsoft 365 per importare e archiviare dati di terze parti richiedono di preparare ed eseguire attività di configurazione nell'origine dati di terze parti. Questi prerequisiti sono documentati in dettaglio per ogni connettore dati di terze parti.

Per i connettori dati nel Centro conformità Microsoft 365 fornito da uno dei partner di Microsoft, l'organizzazione avrà bisogno di una relazione commerciale con il partner prima di poter distribuire un connettore.

I requisiti di licenza per i connettori di dati di terze parti sono presenti nel documento confronto delle licenze di conformità di [Microsoft 365.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

## <a name="apis"></a>API

Le API di conformità di Microsoft 365 sono disponibili in Microsoft Information Protection SDK, nell'API di Microsoft Graph e nell'API di attività di gestione di Office 365. Alcune API di conformità fanno parte di un nuovo set di API di sicurezza e conformità che consentono agli sviluppatori per clienti Di Microsoft 365, fornitori di software indipendenti, integratori di sistema e provider di servizi di sicurezza gestiti di creare soluzioni di sicurezza e conformità di alto valore.

Per altre informazioni su come accedere alle API graph, vedi [Panoramica di Microsoft Graph.](/graph/overview)

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

MIP SDK espone i servizi di etichettatura e protezione dei centri sicurezza e conformità di Microsoft 365 ad applicazioni e servizi di terze parti. Gli sviluppatori possono usare l'SDK per creare il supporto nativo per l'applicazione di etichette e protezione ai file. Gli sviluppatori possono determinare le azioni da eseguire quando vengono rilevate etichette specifiche e il motivo delle informazioni crittografate tramite MIP.

I casi d'uso di MIP SDK di alto livello includono:

- Applicazione line-of-business che applica etichette di classificazione ai file in corso di esportazione.

- Applicazione di progettazione CAD/CAM che fornisce supporto nativo per l'etichettatura MIP.

- Una soluzione di prevenzione della perdita dei dati o un gestore di sicurezza per l'accesso al cloud in grado di crittografare i dati con Azure Information Protection.

Per altre informazioni su SDK MIP, prerequisiti, scenari aggiuntivi ed esempi, vedi [Panoramica di MIP SDK.](/information-protection/develop/overview)

### <a name="microsoft-graph-api-for-teams-dlp"></a>API di Microsoft Graph per Dlp di Teams

Le funzionalità di prevenzione della perdita dei [dati (DLP)](dlp-microsoft-teams.md) sono ampiamente utilizzate in Microsoft Teams, in particolare quando le organizzazioni si sono spostate sul lavoro remoto. All'inizio di [quest'anno è stata annunciata l'anteprima pubblica](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) dell'API di notifica di modifica di Microsoft Graph per i messaggi in Teams. Questa API consente agli sviluppatori di creare app in grado di ascoltare i messaggi di Microsoft Teams in tempo quasi reale e quindi implementare scenari DLP per clienti e partner. Inoltre, l'API patch di Microsoft Graph consente di applicare azioni DLP ai messaggi di Teams.

Queste due API formano l'API di Microsoft Graph per DLP di Teams. Puoi iniziare provando [l'app di esempio](https://github.com/microsoftgraph/csharp-webhook-with-resource-data). Per ulteriori informazioni sui webhook di messaggistica di Microsoft Teams, vedere la [documentazione](/graph/api/subscription-post-subscriptions).

Per i requisiti di licenza per Dlp di Teams, vedere Indicazioni sulle licenze di [Microsoft 365 per la sicurezza & conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams).

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>API di Microsoft Graph per eDiscovery (anteprima)

Con [Advanced eDiscovery,](overview-ediscovery-20.md)le organizzazioni possono individuare i dati in cui si trova e gestire più flussi di lavoro eDiscovery end-to-end con funzionalità intelligenti di machine learning e analisi per ridurre i dati al set pertinente, il tutto mentre i dati rimangono entro il limite di sicurezza e conformità di Microsoft 365.

Le API graph per Advanced eDiscovery possono essere utilizzate per creare e gestire casi, rivedere set e rivedere le query impostate in modo scalabile e ripetibile. In questo modo i clienti e i partner possono creare app e flussi di lavoro per automatizzare processi comuni e ripetitivi, ad esempio la creazione di casi e la gestione dei depositati e dei blocchi legali.

Il primo set di API Graph per eDiscovery è disponibile in anteprima pubblica. Si prevede di aggiungere ulteriori funzionalità entro la fine dell'anno di calendario. Per ulteriori informazioni su queste API e altri aggiornamenti per Advanced eDiscovery, vedere questo [blog.](https://aka.ms/Ignite2020AeDAA)

Per i requisiti di licenza per Advanced eDiscovery e l'API, vedere la sezione "eDiscovery" nella guida alle licenze di [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)per la sicurezza & conformità .

### <a name="microsoft-graph-api-for-teams-export-preview"></a>API di Microsoft Graph per Teams Export (anteprima)

Enterprise Information Archiving (EIA) per Microsoft Teams è uno scenario chiave per i clienti in quanto consente loro di risolvere i requisiti normativi. Oltre alle funzionalità integrate per l'archiviazione dei contenuti in Microsoft Teams, i clienti e i partner possono ora usare le API di esportazione di Teams per risolvere gli scenari di integrazione e applicazione personalizzati. Le API di esportazione di Teams supportano l'esportazione in blocco (fino a 200 richieste al secondo/per app/per tenant) dei messaggi e degli allegati dei messaggi di Teams. I messaggi eliminati sono accessibili anche dall'API per un massimo di 30 giorni dopo l'eliminazione. Per altre informazioni su queste API di esportazione di Teams e su come usarle nelle tue applicazioni, vedi Esportare contenuto con le API di esportazione [di Microsoft Teams.](/microsoftteams/export-teams-content)

Per i requisiti di licenza per l'uso delle API di esportazione di Teams, vedi Indicazioni sulle licenze di [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)per la sicurezza & conformità .