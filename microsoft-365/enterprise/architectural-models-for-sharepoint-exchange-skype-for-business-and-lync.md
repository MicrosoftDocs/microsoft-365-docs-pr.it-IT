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
description: Get IT poster che descrivono i modelli architetturali, la distribuzione e le opzioni della piattaforma per SharePoint, Exchange, Skype for business e Lync.
ms.openlocfilehash: 6d5cda89fb67f5c41dcf161abe7258c4600ee8ce
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919821"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Modelli architetturali per SharePoint, Exchange, Skype for Business e Lync

I poster IT in questo articolo descrivono i modelli di architettura e le opzioni di distribuzione per SharePoint, Exchange, Skype for business e Lync. Sono inoltre disponibili informazioni sulla progettazione per la distribuzione di SharePoint in Microsoft Azure.
  
Utilizzando Microsoft 365, è possibile fornire servizi di comunicazione e collaborazione familiari tramite il cloud. Con alcune eccezioni, l'esperienza utente rimane invariata se si sta mantenendo una distribuzione locale o si utilizza Microsoft 365. 

Questa esperienza utente unificata complica la scelta di dove collocare ogni carico di lavoro. Vengono inoltre sollevate domande:
  
- Come si sceglie una piattaforma per i singoli carichi di lavoro?
    
- Ha senso mantenere i servizi in locale?
    
- In quale scenario è necessaria una distribuzione ibrida?
    
- Come si inserisce Azure nell'immagine?
    
- Quali configurazioni dei carichi di lavoro di Office Server sono supportate da Azure?
    
> [!TIP]
> La maggior parte dei manifesti in questo articolo è disponibile in più lingue. Le lingue disponibili sono cinese, inglese, francese, tedesco, italiano, giapponese, coreano, portoghese, russo e spagnolo. Per scaricare un poster in una di queste lingue, sotto l'immagine di anteprima del poster, selezionare **altre lingue**.
  
Fateci sapere cosa ne pensate! Inviare un messaggio di posta elettronica a [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
Utilizzare i seguenti collegamenti per ottenere i manifesti necessari:
  
- **Modelli architetturali** : utilizzare queste risorse per determinare la piattaforma e la configurazione ideali per SharePoint 2016 e Skype for business 2015.
    
  - [Modelli architetturali di Microsoft SharePoint 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [Database di SharePoint Server 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Modelli architetturali di Microsoft Skype for business 2015](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Piattaforma** : utilizzare queste risorse per determinare la piattaforma e la configurazione ideali per SharePoint 2013, Exchange 2013 e Lync 2013.
    
  - [Opzioni della piattaforma SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Opzioni della piattaforma Exchange 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Opzioni della piattaforma Lync 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint server 2013 in Azure** : utilizzare questi poster it per progettare e configurare i carichi di lavoro di sharepoint Server 2013 nei servizi di infrastruttura di Azure.
    
  - [Siti Internet in Azure con SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Esempio di progettazione: siti Internet in Azure per SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [Ripristino di emergenza di SharePoint in Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Poster dei modelli architetturali

I poster IT per SharePoint 2016 e Skype for business 2015 consentono di confrontare i metodi di distribuzione in un formato di facile stampa. I poster elencano tutte le opzioni di configurazione o piattaforma. Forniscono le informazioni seguenti per ogni opzione:
  
- **Panoramica** : un breve riepilogo della piattaforma, compreso un diagramma concettuale.
    
- Ideale **per** : scenari comuni adatti alla piattaforma.
    
- **Requisiti di licenza** : le licenze necessarie per la distribuzione.
    
- **Attività dell'architettura** : le decisioni che è necessario prendere come architetto.
    
- **Attività o responsabilità per professionisti IT** : le responsabilità quotidiane che il personale IT deve pianificare.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Modelli architetturali di Microsoft SharePoint Server 2016

|Elemento|Descrizione|
|---|---|
|[![Anteprima del poster dei modelli architetturali di SharePoint Server 2016.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf) \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=52650)|In questo poster IT vengono descritte le configurazioni locali di SharePoint Online, Azure e SharePoint che i decision maker aziendali e gli architetti di soluzioni devono conoscere. <br/><br/> - **SharePoint Online (SaaS)** : utilizzare SharePoint tramite un modello di sottoscrizione software as a Service (SaaS). <br/> - **SharePoint ibrido** : spostare i siti e le app di SharePoint nel cloud con i propri ritmi. <br/> - **SharePoint in Azure (IaaS)** : estendere l'ambiente locale in Azure e distribuire i server di SharePoint 2016. Questo modello è consigliato per ambienti a disponibilità elevata o di ripristino di emergenza e ambienti di sviluppo/test. <br/> - **SharePoint locale** : pianificare, distribuire, gestire e personalizzare l'ambiente di SharePoint in un datacenter gestito.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>Database di SharePoint Server 2016

|Elemento|Descrizione|
|---|---|
|[![Anteprima del poster dei database di SharePoint Server 2016.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf) \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55041)|Questo poster IT è una guida di riferimento rapida per i database di SharePoint Server 2016. Verranno visualizzati i dettagli per ogni database: <br/><br/> - Dimensioni <br/> - Linee guida sul ridimensionamento <br/> - Modello di I/O <br/> - Requisiti <br/><br/>  Nella prima pagina vengono illustrati i database di sistema di SharePoint e le applicazioni di servizio con più database. Nella seconda pagina vengono illustrate tutte le applicazioni di servizio che dispongono di singoli database. <br/><br/>  Per ulteriori informazioni, vedere [tipi di database e descrizioni in SharePoint Server 2016](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions).|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Modelli architetturali di Microsoft Skype for Business 2015

|Elemento|Descrizione|
|---|---|
|[![Anteprima del poster dei modelli architetturali di Skype for business.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf) \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55022)|Questo poster descrive Skype for business online, in locale, ibrido e PBX (Private Branch Exchange). Descrive inoltre l'integrazione con le configurazioni di Exchange e SharePoint che i decision maker aziendali e gli architetti di soluzioni devono conoscere. <br/><br/> Il poster è destinato ai professionisti IT per sensibilizzare i modelli architettonici fondamentali attraverso i quali è possibile consumare Skype for business online e Skype for business in locale. <br/><br/>Iniziare con la configurazione più adatta alle esigenze e ai piani dell'organizzazione. Prendere in considerazione e utilizzare altre configurazioni in base alle esigenze. Ad esempio, è possibile prendere in considerazione l'integrazione con Exchange e SharePoint o una soluzione che sfrutta l'offerta di Microsoft Cloud PBX.|
   
## <a name="platform-options-posters"></a>Poster delle opzioni della piattaforma

I manifesti IT per SharePoint 2013, Exchange 2013 e Lync 2013 consentono di confrontare i metodi di distribuzione a colpo d'occhio. Ogni poster elenca tutte le opzioni di configurazione o piattaforma. Vengono fornite le informazioni seguenti per ogni opzione:
  
- **Panoramica** : un breve riepilogo della piattaforma, compreso un diagramma concettuale.
    
- Ideale **per** : scenari comuni adatti alla piattaforma.
    
- **Requisiti di licenza** : le licenze necessarie per la distribuzione.
    
- **Attività dell'architettura** : le decisioni che è necessario prendere come architetto.
    
- **Attività o responsabilità per professionisti IT** : le responsabilità quotidiane che il personale IT deve pianificare.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>Opzioni della piattaforma SharePoint 2013

|Elemento|Descrizione|
|---|---|
|[![Immagine di anteprima del poster delle opzioni della piattaforma SharePoint 2013.](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=40332)|Per i decisori e gli architetti di business, questo poster illustra le opzioni della piattaforma per SharePoint 2013, SharePoint in Microsoft 365, ibrido locale con le distribuzioni di Microsoft 365, Azure e locali. Include una panoramica di ogni architettura, consigli, requisiti di licenza ed elenchi di attività di architetti e professionisti IT per ogni piattaforma. Il poster evidenzia diverse soluzioni SharePoint in Azure.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Opzioni della piattaforma Exchange 2013

|Elemento|Descrizione|
|---|---|
|[![Immagine di anteprima del poster delle opzioni della piattaforma Exchange.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=42676)|Per i decisori e gli architetti di business, questo poster descrive le opzioni della piattaforma per Exchange 2013. I clienti possono scegliere da Exchange Online con Microsoft 365, Exchange ibrido, Exchange Server locale e Exchange ospitato. Nel poster vengono illustrate tutte le opzioni di architettura, inclusi gli scenari ideali per ognuno, i requisiti di licenza e le responsabilità per i professionisti IT.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Opzioni della piattaforma Lync 2013

|Elemento|Descrizione|
|---|---|
|[![Immagine di anteprima del poster delle opzioni della piattaforma Lync 2013.](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41677)|Per i decisori e gli architetti di business, questo poster descrive le opzioni della piattaforma per Lync 2013. I clienti possono scegliere tra Lync Online con Microsoft 365, Lync ibrido, Lync Server locale e Lync ospitato. Nel poster IT vengono illustrate tutte le opzioni di architettura, inclusi gli scenari ideali per ognuno, i requisiti di licenza e le responsabilità per i professionisti IT.|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Poster di SharePoint nelle soluzioni di Azure

I poster IT per SharePoint in Azure mostrano soluzioni basate su Azure che utilizzano SharePoint Server 2013.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Siti Internet in Microsoft Azure che utilizzano SharePoint Server 2013

|Elemento|Descrizione|
|---|---|
|[![Immagine dei siti Internet in Azure con SharePoint Server 2013 poster.](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41992)|Questo poster descrive le attività di progettazione chiave e l'architettura consigliata per i siti Internet in Azure.  <br/><br/> Per altre informazioni, vedere gli articoli seguenti:  <br/><br/> - [Siti Internet in Azure con SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Architetture di Azure per SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Siti Internet in Azure per SharePoint 2013

|Elemento|Descrizione|
|---|---|
|[![Immagine dei siti Internet in Microsoft Azure per SharePoint Server 2013 poster.](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41991)|Utilizzare questo esempio di progettazione come punto di partenza per la propria architettura di un sito con connessione Internet in Azure con SharePoint Server 2013. <br/><br/> Per altre informazioni, vedere gli articoli seguenti:  <br/><br/> - [Siti Internet in Azure con SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Architetture di Azure per SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Ripristino di emergenza di SharePoint in Microsoft Azure

|Elemento|Descrizione|
|---|---|
|[![Immagine del poster per il processo di ripristino di emergenza di SharePoint in Azure.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554) \| [Altre lingue](https://www.microsoft.com/download/details.aspx?id=41993)|In questo poster IT vengono illustrati i principi di architettura per un ambiente di ripristino di emergenza in Azure. <br/><br/> Per ulteriori informazioni, vedere gli articoli seguenti:  <br/><br/> - [Ripristino di emergenza di SharePoint Server 2013 in Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Architetture di Azure per SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>Vedere anche

- [Microsoft 365 Solution and Architecture Center](../solutions/solution-architecture-center.md)
  
- [Modelli di architettura cloud Microsoft](../solutions/cloud-architecture-models.md)
  
- [Guide del laboratorio di testing di Microsoft 365](m365-enterprise-test-lab-guides.md)
  
- [Soluzioni ibride](hybrid-solutions.md)

