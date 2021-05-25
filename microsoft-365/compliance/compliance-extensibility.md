---
title: Microsoft 365 estendibilità della conformità
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
description: Informazioni sull'estensione Microsoft 365 soluzioni di conformità tramite connettori dati di terze parti e API microsoft Graph.
ms.openlocfilehash: 1fed5ac72c7dbfa4b1be370ec03678e1beecdcd2
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651057"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 estendibilità della conformità

Microsoft 365 soluzioni di conformità consentono alle organizzazioni di valutare in modo intelligente i rischi di conformità, governare e proteggere i dati sensibili e rispondere in modo efficace ai requisiti normativi. Microsoft 365 conformità è ricca di scenari di estendibilità e consente alle organizzazioni di adattare, estendere, integrare, accelerare e supportare le soluzioni di conformità.

Esistono due blocchi predefiniti chiave per l'estendibilità della conformità:

- **Connettori dati**. Consente di importare e archiviare dati non Microsoft in modo da poter applicare Microsoft 365 di protezione e governance ai dati di terze parti.

- **API**. Consente l'accesso programmatico alle Microsoft 365 conformità.

## <a name="data-connectors"></a>Connettori dati

Microsoft fornisce connettori di dati di terze parti che possono essere configurati nel Centro Microsoft 365 conformità. Per un elenco dei connettori dati forniti da Microsoft, vedere [la tabella Dei](archiving-third-party-data.md#third-party-data-connectors) connettori dati di terze parti. La tabella dei connettori di dati di terze parti riepiloga inoltre le soluzioni di conformità che è possibile applicare ai dati di terze parti dopo l'importazione e l'archiviazione dei dati in Microsoft 365 e collegamenti alle istruzioni dettagliate per ogni connettore.

Per ulteriori informazioni sui connettori Microsoft 365 dati, vedere [Archiviazione di dati di terze parti.](archiving-third-party-data.md) Se un tipo di dati di terze parti non è supportato dai connettori dati disponibili nel Centro conformità Microsoft 365, è possibile collaborare con un partner in grado di fornire un connettore personalizzato. Per un elenco dei partner con cui è possibile lavorare e il processo dettagliato per questo metodo, vedere Collaborare con un partner per archiviare dati [di terze parti.](work-with-partner-to-archive-third-party-data.md)

### <a name="prerequisites-for-data-connectors"></a>Prerequisiti per i connettori dati

Molti dei connettori di dati disponibili nel Centro conformità Microsoft 365 per importare e archiviare dati di terze parti richiedono di preparare ed eseguire attività di configurazione nell'origine dati di terze parti. Questi prerequisiti sono documentati in dettaglio per ogni connettore dati di terze parti.

Per i connettori di dati nel Microsoft 365 di conformità fornito da uno dei partner Microsoft, l'organizzazione avrà bisogno di una relazione commerciale con il partner prima di poter distribuire un connettore.

È possibile trovare i requisiti di licenza per i connettori di dati di terze parti [nel documento Microsoft 365 confronto delle](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) licenze di conformità.

## <a name="apis"></a>API

Microsoft 365 api di conformità sono disponibili in Microsoft Information Protection SDK, nell'API di Microsoft Graph e nell'API Office 365 Management Activity. Alcune API di conformità fanno parte di un nuovo set di API di sicurezza e conformità che consentono agli sviluppatori per clienti di Microsoft 365, fornitori di software indipendenti, integratori di sistema e provider di servizi di sicurezza gestiti di creare soluzioni di sicurezza e conformità di alto valore.

Per altre informazioni su come accedere Graph API, vedi [Panoramica di Microsoft Graph](/graph/overview).

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

MIP SDK espone i servizi di etichettatura e protezione dai Microsoft 365 sicurezza e conformità ad applicazioni e servizi di terze parti. Gli sviluppatori possono usare l'SDK per creare il supporto nativo per l'applicazione di etichette e protezione ai file. Gli sviluppatori possono determinare le azioni da eseguire quando vengono rilevate etichette specifiche e il motivo delle informazioni crittografate tramite MIP.

I casi d'uso di MIP SDK di alto livello includono:

- Applicazione line-of-business che applica etichette di classificazione ai file in corso di esportazione.

- Applicazione di progettazione CAD/CAM che fornisce supporto nativo per l'etichettatura MIP.

- Una soluzione di prevenzione della perdita dei dati o un gestore di sicurezza per l'accesso al cloud in grado di crittografare i dati con Azure Information Protection.

Per altre informazioni su SDK MIP, prerequisiti, scenari aggiuntivi ed esempi, vedi [Panoramica di MIP SDK.](/information-protection/develop/overview)

### <a name="microsoft-graph-api-for-teams-dlp"></a>API microsoft Graph per Teams DLP

Le funzionalità di prevenzione della perdita dei dati [(DLP)](dlp-microsoft-teams.md) sono ampiamente utilizzate Microsoft Teams in particolare quando le organizzazioni si sono spostate sul lavoro remoto. All'inizio di [quest'anno abbiamo annunciato l'anteprima](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) pubblica dell'API di notifica di modifica di Microsoft Graph per i messaggi in Teams. Questa API consente agli sviluppatori di creare app in grado di ascoltare Microsoft Teams messaggi in tempo quasi reale e quindi implementare scenari DLP per clienti e partner. Inoltre, Microsoft Graph Patch API consente di applicare azioni DLP ai Teams messaggi.

Queste due API formano l'API microsoft Graph per Teams DLP. Puoi iniziare provando [l'app di esempio](https://github.com/microsoftgraph/csharp-webhook-with-resource-data). Per ulteriori informazioni sui webhook Microsoft Teams messaggistica, vedere la [documentazione](/graph/api/subscription-post-subscriptions).

Per i requisiti di licenza per Teams DLP, vedere Microsoft 365 [di licenza per la](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)sicurezza & conformità .

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>API microsoft Graph per eDiscovery (anteprima)

Con [Advanced eDiscovery](overview-ediscovery-20.md), le organizzazioni possono individuare i dati in cui si trova e gestire più flussi di lavoro eDiscovery end-to-end con funzionalità intelligenti di machine learning e analisi per ridurre i dati al set pertinente, il tutto mentre i dati rimangono entro il limite di sicurezza e conformità di Microsoft 365.

Graph Le API per Advanced eDiscovery possono essere usate per creare e gestire casi, rivedere set e rivedere le query di set in modo scalabile e ripetibile. In questo modo i clienti e i partner possono creare app e flussi di lavoro per automatizzare processi comuni e ripetitivi, ad esempio la creazione di casi e la gestione dei depositati e dei blocchi legali.

Il primo set di Graph API per eDiscovery sono disponibili in anteprima pubblica. Si prevede di aggiungere ulteriori funzionalità entro la fine dell'anno di calendario. Per altre informazioni su queste API e altri aggiornamenti per Advanced eDiscovery, vedi questo [blog.](https://aka.ms/Ignite2020AeDAA)

Per i requisiti di licenza per Advanced eDiscovery e l'API, vedere la sezione "eDiscovery" nella guida alle licenze di Microsoft 365 per la sicurezza [& conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery).

### <a name="microsoft-graph-api-for-teams-export-preview"></a>API di Microsoft Graph per l Teams esporto (anteprima)

Enterprise L'archiviazione delle informazioni (EIA) per Microsoft Teams è uno scenario chiave per i clienti in quanto consente loro di risolvere i requisiti normativi. Oltre alle funzionalità incorporate per l'archiviazione del contenuto in Microsoft Teams, i clienti e i partner possono ora usare le API di esportazione di Teams per risolvere gli scenari di integrazione e applicazione personalizzati. Le API di Teams di esportazione supportano l'esportazione in blocco (fino a 200 richieste al secondo/per app/per tenant) di Teams messaggi e allegati dei messaggi. I messaggi eliminati sono accessibili anche dall'API per un massimo di 30 giorni dopo l'eliminazione. Per altre informazioni su Teams le API di esportazione e su come usarle nelle tue applicazioni, vedi Esportare contenuto con le API di Microsoft Teams [esporta.](/microsoftteams/export-teams-content)

Per i requisiti di licenza per l'uso delle API di Teams di esportazione, vedi indicazioni sulle licenze Microsoft 365 per la sicurezza [& conformità.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

### <a name="microsoft-graph-connector-apis-preview"></a>API di Microsoft Graph Connector (anteprima)

Con [i connettori Graph](/microsoftsearch/connectors-overview)Microsoft , le organizzazioni possono indicizzare i dati di terze parti in modo che appaino nei risultati di Microsoft Search. Questa funzionalità espande i tipi di origini di contenuto disponibili per la ricerca nelle app di produttività Microsoft 365 e nell'ecosistema Microsoft più ampio. I dati di terze parti possono essere ospitati in locale o in cloud pubblici o privati. A partire da Advanced eDiscovery, stiamo abilitando l'anteprima per sviluppatori del valore di conformità predefinito di Microsoft 365 app connesse. Ciò consente la conformità per le app che si integrano nell'ecosistema Microsoft 365 per consentire agli utenti di ottenere esperienze di conformità senza problemi. Per altre informazioni su come incorporare le API di Microsoft Graph Connector nella visualizzazione delle app, vedi [Creare, aggiornare](/graph/search-index-manage-connections)ed eliminare connessioni in Microsoft Graph .

