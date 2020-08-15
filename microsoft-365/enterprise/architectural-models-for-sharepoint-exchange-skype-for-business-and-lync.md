---
title: Modelli architetturali per SharePoint, Exchange, Skype for Business e Lync
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
ms.assetid: 5b49fa68-f8f2-4705-af96-5f5475e8539a
search.appverid:
- MET150
description: 'Riepilogo: ottenere i poster IT in cui vengono descritti i modelli architetturali, la distribuzione e le opzioni delle piattaforme per SharePoint, Exchange, Skype for Business e Lync.'
ms.openlocfilehash: 67f1018c70dfc86306b0d1e7ceb6061a166b3db8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691357"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Modelli architetturali per SharePoint, Exchange, Skype for Business e Lync

In questi poster IT vengono descritti i modelli architetturali e le opzioni di distribuzione per SharePoint, Exchange, Skype for Business e Lync; sono inoltre disponibili informazioni relative alla progettazione per distribuire SharePoint in Microsoft Azure.
  
Con Microsoft 365 è possibile fornire servizi di comunicazione e collaborazione noti agli utenti con un servizio basato sul cloud. Con alcune eccezioni, l'esperienza utente rimane la stessa sia se si mantiene una distribuzione locale che se si utilizza Microsoft 365. Questa esperienza utente unificata rende meno facile decidere dove posizionare ogni carico di lavoro e fa sorgere domande come le seguenti:
  
- Come si determina l'opzione di piattaforma da scegliere per i carichi di lavoro individuali?
    
- Ha senso mantenere i servizi in locale?
    
- Quale può essere uno scenario in cui è adatta una distribuzione ibrida?
    
- Come si integra Microsoft Azure?
    
- Quali sono le configurazioni supportate per i carichi di lavoro di Office Server in Azure?
    
> [!TIP]
> La maggior parte dei poster in questa pagina è disponibile in più lingue, tra cui cinese, inglese, francese, tedesco, italiano, giapponese, coreano, portoghese, russo e spagnolo. Per scaricare un poster in una di queste lingue, scegliere il collegamento **Altre lingue**.
  
Inviare commenti e suggerimenti all'indirizzo [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
In questa pagina sono disponibili i collegamenti ai poster seguenti:
  
- **Poster dei modelli architetturali** È possibile utilizzare queste risorse per determinare la piattaforma e la configurazione ideali per SharePoint 2016 e Skype for Business 2015.
    
  - [Modelli architetturali di Microsoft SharePoint 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [Database di SharePoint Server 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Modelli architetturali di Microsoft Skype for Business 2015](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Poster delle opzioni delle piattaforme** È possibile utilizzare queste risorse per determinare la piattaforma e la configurazione ideali per SharePoint 2013, Exchange 2013 e Lync 2013.
    
  - [Opzioni della piattaforma SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Opzioni della piattaforma Exchange 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Opzioni della piattaforma Lync 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **Poster di SharePoint Server 2013 nelle soluzioni di Azure** È possibile utilizzare questi poster IT per determinare la progettazione per i carichi di lavoro di SharePoint Server 2013 nei servizi infrastruttura di Azure.
    
  - [Siti Internet in Microsoft Azure che utilizzano SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Esempio di progettazione: siti Internet in Microsoft Azure per SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [Ripristino di emergenza di SharePoint in Microsoft Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Poster dei modelli architetturali

Questi nuovi poster IT per SharePoint 2016 e Skype for Business 2015 forniscono uno strumento per confrontare i vari metodi di distribuzione in un formato facile da stampare. In ogni poster è riportato un elenco di tutte le opzioni di piattaforme o configurazioni disponibili, oltre alle informazioni seguenti per ciascuna opzione:
  
- **Panoramica** Un breve riepilogo della piattaforma, compreso un diagramma concettuale.
    
- **Compatibilità** Scenari comuni particolarmente adatti a una determinata piattaforma.
    
- **Requisiti di licenza** Le licenze necessarie per la distribuzione.
    
- **Attività dell'architettura** Le decisioni necessarie per un architetto.
    
- **Responsabilità o attività dei professionisti IT** Le responsabilità giornaliere che devono essere pianificate dal personale IT.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-2016-architectural-models"></a>Modelli architetturali di Microsoft SharePoint 2016

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Anteprima del poster dei modelli architetturali di SharePoint 2016](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=52650) <br/> | In questo poster IT vengono descritte le configurazioni locali di SharePoint Online, Microsoft Azure e SharePoint che i decision maker aziendali e gli architetti di soluzioni devono conoscere. <br/><br/> - **SharePoint Online (SaaS)**: utilizzare SharePoint tramite un modello di sottoscrizione Software as a Service (SaaS). <br/> - **SharePoint ibrido**: spostare i siti e le app di SharePoint nel cloud secondo le proprie esigenze. <br/> - **SharePoint in Azure (IaaS)**: estendere l'ambiente locale in Microsoft Azure e distribuirvi i server di SharePoint 2016. Questa è l'opzione consigliata per il ripristino di emergenza a disponibilità elevata e gli ambienti di sviluppo/test.<br/> - **SharePoint locale**: l'ambiente di SharePoint viene pianificato, distribuito, conservato e personalizzato in un data center gestito dall'utente. <br/> |
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>Database di SharePoint Server 2016

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Anteprima del poster dei database di SharePoint Server 2016.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)          ](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55041) <br/> | Questo poster IT è una guida di riferimento rapido per i database di SharePoint Server 2016. Ogni database fornisce quanto segue: <br/><br/> - Dimensioni <br/> - Linee guida sul ridimensionamento <br/> - Modello di I/O <br/> - Requisiti <br/><br/>  La prima pagina contiene i database di sistema di SharePoint e le applicazioni di servizio che dispongono di più database. La seconda pagina mostra tutte le applicazioni di servizio con database singoli. <br/><br/>  Per ulteriori informazioni sui database di SharePoint Server 2016, vedere [Tipi di database e relative descrizioni in SharePoint Server 2016](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions) <br/> |
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Modelli architetturali di Microsoft Skype for Business 2015

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Anteprima del poster dei modelli architetturali di Skype for Business](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)          ](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55022) <br/> |In questo poster vengono descritte le configurazioni di Skype for Business Online, ambiente locale, ambiente ibrido, Cloud PBX e integrazione con Exchange e SharePoint che i decision maker aziendali e gli architetti di soluzioni devono conoscere. <br/><br/> È rivolto ai professionisti IT e ha lo scopo di rendere più familiari i vari modelli architetturali fondamentali che consentono di utilizzare Skype for Business Online e Skype for Business in locale. <br/><br/>È importante iniziare con la configurazione che si adatta maggiormente alle esigenze dell'organizzazione e ai piani futuri. È consigliabile prendere in considerazione e utilizzare le altre configurazioni in base alle esigenze. Ad esempio, è opportuno considerare l'integrazione con Exchange e SharePoint o una soluzione che consenta di sfruttare i vantaggi offerti da Cloud PBX di Microsoft.  <br/> |
   
## <a name="platform-options-posters"></a>Poster delle opzioni della piattaforma

In questi poster IT per SharePoint 2013, Exchange 2013 e Lync 2013 è disponibile uno strumento per confrontare i vari metodi di distribuzione velocemente in un poster di grandi dimensioni. In ogni poster è riportato un elenco di tutte le opzioni di piattaforme o configurazioni disponibili, oltre alle informazioni seguenti per ciascuna opzione:
  
- **Panoramica** Un breve riepilogo della piattaforma, compreso un diagramma concettuale.
    
- **Compatibilità** Scenari comuni particolarmente adatti a una determinata piattaforma.
    
- **Requisiti di licenza** Le licenze necessarie per la distribuzione.
    
- **Attività dell'architettura** Le decisioni necessarie per un architetto.
    
- **Responsabilità o attività dei professionisti IT** Le responsabilità giornaliere che devono essere pianificate dal personale IT.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>Opzioni della piattaforma SharePoint 2013

****

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Immagine di anteprima delle opzioni della piattaforma SharePoint 2013](../media/SP-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=40332) <br/> |Per i decision maker aziendali (BDMs) e gli architetti, questo modello mostra le opzioni della piattaforma per SharePoint 2013, SharePoint in Microsoft 365, ibrido locale con distribuzioni Microsoft 365, Azure e solo locali. Include una panoramica di ogni architettura, consigli, requisiti di licenza ed elenchi di attività per architetti e professionisti IT per ogni piattaforma. Sono evidenziate diverse soluzioni di SharePoint su Azure. <br/> |
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Opzioni della piattaforma Exchange 2013

****

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Immagine di anteprima delle opzioni della piattaforma Exchange](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=42676) <br/> |Destinato a BDM e architetti, questo modello descrive le opzioni della piattaforma disponibili per Exchange 2013. I clienti possono scegliere da Exchange Online con Microsoft 365, una distribuzione ibrida di Exchange, Exchange Server in locale e Hosted Exchange. Il poster include le informazioni su ogni opzione architetturale, compresi gli scenari ideali per ciascuna di esse, i requisiti di licenze e le responsabilità dei professionisti IT. <br/> |
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Opzioni della piattaforma Lync 2013

****

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Immagine di anteprima delle opzioni della piattaforma Lync](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41677) <br/> |Destinato a BDM e architetti, questo modello descrive le opzioni della piattaforma disponibili per Lync 2013. I clienti possono scegliere da Lync Online con Microsoft 365, una distribuzione ibrida di Lync, Lync Server in locale e Hosted Lync. Il poster IT include le informazioni su ogni opzione architetturale, compresi gli scenari ideali per ciascuna di esse, i requisiti di licenze e le responsabilità dei professionisti IT.  <br/> |
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Poster di SharePoint nelle soluzioni di Azure

In questi poster IT vengono illustrate le soluzioni basate su Azure che utilizzano SharePoint Server 2013 in un formato di grandi dimensioni.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Siti Internet in Microsoft Azure che utilizzano SharePoint Server 2013

****

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Immagine di siti Internet in Azure con SharePoint](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41992) <br/> |In questo poster vengono descritte le attività di progettazione di base e le scelte di architettura consigliate per i siti Internet in Azure.  <br/><br/> Per ulteriori informazioni, vedere gli articoli seguenti:  <br/><br/> - [Siti Internet in Microsoft Azure che utilizzano SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Architetture di Microsoft Azure per SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
<a name="DesignSampleInternetSites"> </a>
### <a name="design-sample-internet-sites-in-microsoft-azure-for-sharepoint-2013"></a>Esempio di progettazione: siti Internet in Microsoft Azure per SharePoint 2013

****

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Immagine con esempio di progettazione: siti Internet in Microsoft Azure per SharePoint 2013](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41991) <br/> |Utilizzare questo esempio di progettazione come punto di partenza per l'architettura del proprio sito Internet in Azure con SharePoint Server 2013. <br/><br/> Per ulteriori informazioni, vedere gli articoli seguenti:  <br/><br/> - [Siti Internet in Microsoft Azure che utilizzano SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Architetture di Microsoft Azure per SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Ripristino di emergenza di SharePoint in Microsoft Azure

****

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Processo di ripristino di emergenza di SharePoint in Azure](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41993) <br/> |In questo poster IT vengono illustrati i principi di architettura per un ambiente di ripristino di emergenza in Azure. <br/><br/> Per ulteriori informazioni, vedere gli articoli seguenti:  <br/><br/> - [Ripristino di emergenza di SharePoint Server 2013 in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Architetture di Microsoft Azure per SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) <br/> |
   
## <a name="see-also"></a>Vedere anche

[Microsoft 365 Solution and Architecture Center](../solutions/solution-architecture-center.md)
  
[Illustrazioni di Microsoft Cloud per Enterprise Architects](../solutions/cloud-architecture-models.md)
  
[Guide del laboratorio di testing di Microsoft 365](m365-enterprise-test-lab-guides.md)
  
[Soluzioni ibride](hybrid-solutions.md)

