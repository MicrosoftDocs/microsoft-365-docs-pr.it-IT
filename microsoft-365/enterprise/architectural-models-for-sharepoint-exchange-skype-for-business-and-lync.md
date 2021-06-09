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
description: Ottenere poster IT che descrivono i modelli architettonici, la distribuzione e le opzioni della piattaforma per SharePoint, Exchange, Skype for Business e Lync.
ms.openlocfilehash: 6c8aea1f6389c5007adb1800639488972483d5fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905513"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Modelli architetturali per SharePoint, Exchange, Skype for Business e Lync

Nei poster IT di questo articolo vengono descritti i modelli architettonici e le opzioni di distribuzione per SharePoint, Exchange, Skype for Business e Lync. Forniscono inoltre informazioni di progettazione per la distribuzione di SharePoint in Microsoft Azure.
  
Utilizzando il Microsoft 365, è possibile fornire servizi familiari di collaborazione e comunicazione tramite il cloud. Con alcune eccezioni, l'esperienza utente rimane la stessa sia che si manteni una distribuzione locale o che si utilizzi Microsoft 365. 

Questa esperienza utente unificata complica la decisione di collocare ogni carico di lavoro. Pone anche domande:
  
- Come si sceglie una piattaforma per i singoli carichi di lavoro?
    
- Ha senso mantenere i servizi in locale?
    
- In quale scenario è appropriata una distribuzione ibrida?
    
- Come si inserisce Azure nell'immagine?
    
- Quali configurazioni dei Office server supportati da Azure?
    
> [!TIP]
> La maggior parte dei poster in questo articolo è disponibile in più lingue. Le lingue disponibili includono cinese, inglese, francese, tedesco, italiano, giapponese, coreano, portoghese, russo e spagnolo. Per scaricare un poster in una di queste lingue, sotto l'immagine di anteprima del poster seleziona **Altre lingue.**
  
Inviare commenti e suggerimenti all'indirizzo [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
Usa i collegamenti seguenti per ottenere i poster necessari:
  
- **Modelli architettonici:** utilizzare queste risorse per determinare la piattaforma e la configurazione ideali per SharePoint 2016 e Skype for Business 2015.
    
  - [Modelli architetturali di Microsoft SharePoint 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint Database server 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Modelli architetturali di Microsoft Skype for Business 2015](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Piattaforma:** utilizzare queste risorse per determinare la piattaforma e la configurazione ideali per SharePoint 2013, Exchange 2013 e Lync 2013.
    
  - [SharePoint opzioni della piattaforma 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Exchange della piattaforma 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Opzioni della piattaforma Lync 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint Server 2013 in Azure**: usare questi poster IT per progettare e configurare i carichi di lavoro di SharePoint Server 2013 nei servizi di infrastruttura di Azure.
    
  - [Siti Internet in Azure con SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Esempio di progettazione: siti Internet in Azure per SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [SharePoint ripristino di emergenza in Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Poster dei modelli architetturali

I poster IT per SharePoint 2016 e Skype for Business 2015 consentono di confrontare i metodi di distribuzione in un formato facile da stampare. I poster elencano tutte le opzioni di configurazione o della piattaforma. Forniscono le informazioni seguenti per ogni opzione:
  
- **Panoramica**: breve riepilogo della piattaforma, incluso un diagramma concettuale.
    
- **Ideale per**: scenari comuni ideali per la piattaforma.
    
- **Requisiti di licenza:** le licenze necessarie per la distribuzione.
    
- **Attività di architettura:** le decisioni da prendere come architetti.
    
- **Attività o responsabilità dei professionisti IT**: responsabilità quotidiane che il personale IT deve pianificare.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Modelli architetturali di Microsoft SharePoint Server 2016

|Elemento|Descrizione|
|---|---|
|[![Anteprima del poster SharePoint modelli architettonici di SharePoint Server 2016.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf) \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=52650)|Questo poster IT descrive le configurazioni locali di SharePoint Online, Azure e SharePoint locali necessarie per i decision maker aziendali e gli architetti di soluzioni. <br/><br/> - **SharePoint Online (SaaS):** utilizzare SharePoint tramite un modello di sottoscrizione SaaS (Software as a Service). <br/> - **SharePoint ibrido:** spostare i siti SharePoint e le app nel cloud al proprio ritmo. <br/> - **SharePoint in Azure (IaaS):** estendere l'ambiente locale in Azure e distribuire i server SharePoint 2016. Questo modello è consigliato per ambienti a disponibilità elevata o di ripristino di emergenza e ambienti di sviluppo/test. <br/> - **SharePoint locale:** pianificare, distribuire, gestire e personalizzare l'ambiente SharePoint in un datacenter gestito dall'utente.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>Database di SharePoint Server 2016

|Elemento|Descrizione|
|---|---|
|[![Anteprima del poster SharePoint Database di SharePoint Server 2016.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf) \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55041)|Questo poster IT è un riferimento rapido per i SharePoint Server 2016. Verranno visualizzati i dettagli per ogni database: <br/><br/> - Dimensioni <br/> - Linee guida sul ridimensionamento <br/> - Modello di I/O <br/> - Requisiti <br/><br/>  Nella prima pagina vengono mostrati SharePoint di sistema e le applicazioni di servizio che dispongono di più database. Nella seconda pagina vengono illustrate tutte le applicazioni di servizio che dispongono di singoli database. <br/><br/>  Per ulteriori informazioni, vedere [Tipi di database e descrizioni in SharePoint Server 2016.](/SharePoint/technical-reference/database-types-and-descriptions)|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Modelli architetturali di Microsoft Skype for Business 2015

|Elemento|Descrizione|
|---|---|
|[![Anteprima per il poster Skype for Business modelli architettonici.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf) \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55022)|Questo poster descrive Skype for Business, PBX (Private Branch Exchange) online, locale, ibrido e cloud. Descrive inoltre l'integrazione con Exchange e SharePoint aziendali che i decision maker aziendali e gli architetti di soluzioni devono conoscere. <br/><br/> Il poster è destinato ai professionisti IT per sensibilizzare i professionisti IT sui modelli architettonici fondamentali attraverso i quali è possibile utilizzare Skype for Business Online e Skype for Business locale. <br/><br/>Iniziare con la configurazione più adatta alle esigenze e ai piani dell'organizzazione. Considerare e utilizzare altre configurazioni in base alle esigenze. Ad esempio, è consigliabile considerare l'integrazione con Exchange e SharePoint o una soluzione che sfrutta l'offerta cloud PBX Microsoft.|
   
## <a name="platform-options-posters"></a>Poster delle opzioni della piattaforma

I poster IT per SharePoint 2013, Exchange 2013 e Lync 2013 consentono di confrontare rapidamente i metodi di distribuzione. Ogni poster elenca tutte le configurazioni o le opzioni della piattaforma. Fornisce le informazioni seguenti per ogni opzione:
  
- **Panoramica**: breve riepilogo della piattaforma, incluso un diagramma concettuale.
    
- **Ideale per**: scenari comuni ideali per la piattaforma.
    
- **Requisiti di licenza:** le licenze necessarie per la distribuzione.
    
- **Attività di architettura:** le decisioni da prendere come architetti.
    
- **Attività o responsabilità dei professionisti IT**: responsabilità quotidiane che il personale IT deve pianificare.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>Opzioni della piattaforma SharePoint 2013

|Elemento|Descrizione|
|---|---|
|[![Immagine di anteprima del poster SharePoint opzioni della piattaforma 2013.](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=40332)|Per i decision maker e gli architetti aziendali, questo poster mostra le opzioni della piattaforma per SharePoint 2013, SharePoint in Microsoft 365, ibrido locale con distribuzioni di Microsoft 365, Azure e solo locale. Include una panoramica di ogni architettura, consigli, requisiti di licenza ed elenchi di attività di architetti e professionisti IT per ogni piattaforma. Il poster evidenzia diverse SharePoint in Azure.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Opzioni della piattaforma Exchange 2013

|Elemento|Descrizione|
|---|---|
|[![Immagine di anteprima del poster Exchange Opzioni piattaforma.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=42676)|Per i decision maker e gli architetti aziendali, questo poster descrive le opzioni della piattaforma per Exchange 2013. I clienti possono scegliere tra Exchange Online con Microsoft 365, Exchange ibridi, Exchange Server locali e hosted Exchange. Il poster dettaglia ogni opzione architetturale, inclusi gli scenari ideali per ognuna, i requisiti di licenza e le responsabilità dei professionisti IT.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Opzioni della piattaforma Lync 2013

|Elemento|Descrizione|
|---|---|
|[![Immagine di anteprima del poster Opzioni piattaforma Lync 2013.](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41677)|Per i decision maker e gli architetti aziendali, questo poster descrive le opzioni della piattaforma per Lync 2013. I clienti possono scegliere da Lync Online con Microsoft 365, Lync ibrido, Lync Server locale e Lync ospitato. Il poster IT dettaglia ogni opzione architetturale, inclusi gli scenari ideali per ognuna, i requisiti di licenza e le responsabilità dei professionisti IT.|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Poster di SharePoint nelle soluzioni di Azure

I poster IT per SharePoint in Azure mostrano soluzioni basate su Azure che usano SharePoint Server 2013.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Siti Internet in Microsoft Azure using SharePoint Server 2013

|Elemento|Descrizione|
|---|---|
|[![Immagine dei siti Internet in Azure con il poster SharePoint Server 2013.](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41992)|Questo poster descrive le principali attività di progettazione e l'architettura consigliata per i siti con connessione a Internet in Azure.  <br/><br/> Per altre informazioni, vedere gli articoli seguenti:  <br/><br/> - [Siti Internet in Azure con SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Architetture di Azure per SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Siti Internet in Azure per SharePoint 2013

|Elemento|Descrizione|
|---|---|
|[![Immagine dei siti Internet in Microsoft Azure per SharePoint Poster di Server 2013.](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41991)|Usare questo esempio di progettazione come punto di partenza per la propria architettura di un sito con connessione a Internet in Azure con SharePoint Server 2013. <br/><br/> Per altre informazioni, vedere gli articoli seguenti:  <br/><br/> - [Siti Internet in Azure con SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Architetture di Azure per SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Ripristino di emergenza di SharePoint in Microsoft Azure

|Elemento|Descrizione|
|---|---|
|[![Immagine del poster per il processo di SharePoint di ripristino di emergenza in Azure.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41993)|In questo poster IT vengono illustrati i principi di architettura per un ambiente di ripristino di emergenza in Azure. <br/><br/> Per ulteriori informazioni, vedere gli articoli seguenti:  <br/><br/> - [SharePoint Ripristino di emergenza di Server 2013 in Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Architetture di Azure per SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>Vedere anche

- [Centro soluzioni e architetture di Microsoft 365](../solutions/index.yml)
  
- [Modelli di architettura cloud Microsoft](../solutions/cloud-architecture-models.md)
  
- [Microsoft 365 del laboratorio di testing](m365-enterprise-test-lab-guides.md)
  
- [Soluzioni ibride](hybrid-solutions.md)