---
title: Migrazione da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nelle nuove aree data center tedesche
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 07/09/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Riepilogo: Informazioni sulla migrazione da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area data center tedesca.'
ms.openlocfilehash: cfbd3b7406f7c7824f736633e3a4dba6fa5c4bff
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691382"
---
# <a name="migration-from-microsoft-cloud-germany-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migrazione da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nelle nuove aree data center tedesche


>[!Note]
>Questo articolo interessa solo i clienti idonei di Microsoft Cloud Germania/Deutschland.
>

## <a name="cloud-service-offerings-in-germany"></a>Offerte di servizi cloud in Germania

Nel mese di agosto 2018, abbiamo annunciato l'intenzione di offrire il cloud completo di Microsoft, ovvero Azure, Office 365, Dynamics 365 e Power Platform, dalle nuove aree cloud in Germania, per consentire una migliore trasformazione digitale dei nostri clienti. Nel mese di agosto 2019, abbiamo annunciato che le nuove aree cloud in Germania erano in fase di apertura. Abbiamo anche annunciato la disponibilità di Azure dal mese di agosto e di Office 365 da dicembre.  La disponibilità di Dynamics 365 e Power Platform è prevista per il primo trimestre del 2020.  

Le nuove aree sono state progettate per rispondere alle crescenti esigenze dei clienti tedeschi con maggiore flessibilità, con i servizi cloud intelligenti più recenti e la connettività completa alla rete cloud globale, nonché con la residenza dei dati in Germania.

## <a name="moving-to-the-new-german-regions"></a>Spostamento nelle nuove aree tedesche

I clienti esistenti di Microsoft Cloud Germania (Microsoft Cloud Deutschland) possono ora eseguire la migrazione dei propri clienti di Office 365, Dynamics 365 Customer Engagement e Power Platform BI.  Il primo passaggio consiste nel [consenso esplicito alla migrazione gestita da Microsoft](https://aka.ms/office365germanymoveoptin) nelle nuove aree data center tedesche.

Per le organizzazioni che hanno acconsentito all'approccio gestito da Microsoft, le migrazioni sono previste nel corso del 2020. A seguito della migrazione, gli abbonamenti e i dati principali dei clienti verranno spostati nelle nuove aree geografiche tedesche. 

Come parte dell'approccio gestito da Microsoft, verrà eseguita la migrazione dei servizi seguenti:

- Azure Active Directory
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business
- Skype for Business Online

Durante la migrazione da Microsoft Cloud Germania alle aree data center tedesche, verrà eseguita la transizione dei clienti esistenti di Skype for Business Online a Microsoft Teams. Per altre informazioni, vedere [Guida introduttiva per l'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home).

- Gruppi di Office 365
- Dynamics 365/Power Platform

I prerequisiti e l'impatto della migrazione per questi servizi sono descritti nell'articolo [Dynamics 365 Customer Engagement](https://aka.ms/d365ceoptin).

Office 365 Video verrà ritirato il 1° marzo 2021. Se si sceglie di eseguire la migrazione del tenant di Office 365 nelle nuove aree data center tedesche, Office 365 Video non verrà più supportato dopo il completamento della migrazione di SharePoint Online. [Altre informazioni](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Come prepararsi per la migrazione ai servizi di Office 365 nelle nuove aree data center tedesche

Il primo passaggio consiste nell'inviare una notifica a Microsoft in modo che saremo autorizzati a eseguire la migrazione della sottoscrizione e dei dati, da Microsoft Cloud Germania/Deutschland ai servizi di Office 365 nelle nuove aree data center tedesche.  Per le istruzioni, fare riferimento al [processo di consenso esplicito](ms-cloud-germany-migration-opt-in.md).

- Tutti i clienti che effettuano la migrazione devono verificare la connettività agli [URL e indirizzi IP di Office 365](urls-and-ip-address-ranges.md) in tutto il mondo, tra cui le nuove aree data center tedesche.
- Rivedere la descrizione del servizio della piattaforma di Office 365 per comprendere quali funzionalità e servizi saranno disponibili per l'organizzazione dopo il completamento della migrazione nell'area tedesca. 
- La migrazione effettuerà la transizione delle sottoscrizioni a pagamento.  Non è possibile eseguire la migrazione delle sottoscrizioni di valutazione.

Le migrazioni dei tenant vengono eseguite come servizio di back-end con la minima necessità di interazione con i clienti.  Durante il processo di migrazione, verranno comunicate le eventuali altre attività gestite dai clienti e lo stato di migrazione complessivo.  Esempi di attività sono gli aggiornamenti DNS eseguiti dai clienti o la riconfigurazione dell'installazione ibrida per clienti di Exchange.

## <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>L'esperienza cliente durante la migrazione ai servizi di Office 365 nelle nuove aree data center tedesche

Le migrazioni dei tenant sono progettate per avere un impatto minimo sugli utenti finali e sugli amministratori.  Esistono tuttavia alcune considerazioni su ciascun carico di lavoro.  

### <a name="azure-active-directory"></a>Azure Active Directory

Le sottoscrizioni a Office/Dynamics da Microsoft Cloud Germania vengono spostate nell'area tedesca con il trasferimento di Azure Active Directory (Azure AD). L'organizzazione verrà poi aggiornata in modo da riflettere le nuove sottoscrizioni ai servizi in tutto il mondo. Durante il breve processo di trasferimento della sottoscrizione, le relative modifiche verranno bloccate.

### <a name="exchange-online"></a>Exchange Online

I clienti ibridi di Exchange Online devono eseguire di nuovo la configurazione ibrida guidata per aggiornare quella locale per Microsoft Cloud Germania prima della transizione, nonché rieseguire la configurazione ibrida guidata al momento della pulizia in previsione del servizio in ambito internazionale. È possibile che vengano richiesti altri aggiornamenti DNS per i clienti con domini personalizzati.

La migrazione delle cassette postali viene eseguita come processo di back-end, gli utenti dell'organizzazione potrebbero essere presenti in Microsoft Cloud Germania o nell'area tedesca durante la transizione e fanno parte della stessa organizzazione di Exchange (elenco indirizzi globale).

### <a name="exchange-online-protection"></a>Exchange Online Protection

Le funzionalità di back-end di Exchange Online Protection di vengono copiate nella nuova area tedesca.

### <a name="sharepoint-online"></a>SharePoint Online

Dopo aver completato la migrazione di SharePoint Online all'area tedesca, vengono ricreati gli indici dei dati. Le funzionalità dipendenti dagli indici di ricerca possono essere interessate durante il completamento della reindicizzazione.

Gli URL di sharepoint.de esistenti vengono mantenuti per le organizzazioni in transizione.

### <a name="onedrive-for-business"></a>OneDrive for Business

Dopo aver completato la migrazione di OneDrive for Business all'area tedesca, vengono ricreati gli indici dei dati. Le funzionalità dipendenti dagli indici di ricerca possono essere interessate durante il completamento della reindicizzazione.

### <a name="skype-for-business-online"></a>Skype for Business Online

I clienti esistenti di Skype for Business online verranno trasferiti a Microsoft Teams. Per altre informazioni, vedere [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home).

### <a name="office-365-video"></a>Office 365 Video
I contenuti di Office 365 Video saranno trasferiti come parte della migrazione di SharePoint Online. Tuttavia, Office 365 Video verrà ritirato e non sarà più supportato dopo il completamento della migrazione di SharePoint Online nelle nuove aree data center tedesche. I video non potranno essere riprodotti nell’interfaccia utente di Office 365 Video dopo migrazione di SharePoint.

Microsoft Stream non verrà distribuito in Microsoft Deutschland e al momento non è disponibile una sequenza temporale della distribuzione di Microsoft Stream nelle nuove aree data center tedesche. Di conseguenza, in questa area non saranno disponibili strumenti per la migrazione di Office 365 Video in Microsoft Stream. Per mantenere i contenuti, sarà necessario scaricarli o spostarli manualmente prima del 1° marzo 2021. [Altre informazioni](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)


## <a name="key-differences-between-microsoft-cloud-germany-microsoft-cloud-deutschland-and-office-365-services-in-the-new-german-datacenter-regions"></a>Principali differenze tra Microsoft Cloud Germania (Microsoft Cloud Deutschland) e i servizi di Office 365 nelle nuove aree data center tedesche


|| Microsoft Cloud Germania (Microsoft Cloud Deutschland) | I servizi di Office 365 nelle nuove aree data center tedesche |
|:-------|:-----|:-----|
| Servizi Microsoft 365 disponibili per la sottoscrizione a un solo tenant di Office 365 | 15 servizi (vedere REF) | 29 servizi (vedere REF) |
| Nuove funzionalità | Nessuna nuova funzionalità disponibile. | Le nuove funzionalità saranno disponibili con i servizi globali di Office 365. |
| Trustee dei dati | Sì | No |
| Collaborazione tra il tenant e i tenant globali di Office 365 | No | Sì |
| Residenza dei dati dei clienti | I dati dei clienti verranno archiviati esclusivamente all'interno dei data center tedeschi. | Microsoft archivierà i seguenti dati dei clienti esclusivamente in Germania: il contenuto delle cassette postali di Exchange Online (corpo dei messaggi di posta elettronica, voci di calendario e il contenuto degli allegati della posta elettronica), il contenuto del sito di SharePoint Online e i relativi file archiviati, nonché i file caricati in OneDrive for Business. |
| Condizioni applicabili | [Condizioni dei Servizi online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) con [supplemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Condizioni dei Servizi online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="is-migration-required"></a>È obbligatoria la migrazione?

Microsoft offre la migrazione del tenant di Office 365 da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nelle nuove aree data center tedesche senza costi aggiuntivi.  Anche se consigliamo vivamente di acconsentire esplicitamente alla migrazione alle nuove aree data center tedesche, continueremo a fornire gli aggiornamenti di sicurezza necessari all'area Microsoft Cloud Germania.  

I servizi di Office 365 nelle nuove aree data center tedesche dispongono di benefici aggiuntivi:

- Offrono prezzi di mercato competitivi per [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) e [Power BI](https://powerbi.microsoft.com/pricing/). 
- Sono connessi alla rete globale Microsoft, con centinaia di siti di rete perimetrale, posizioni di peering e punti di uscita per offrire un'esperienza utente affidabile in qualsiasi parte del mondo. 
- Consentono ai clienti locali di rispettare i requisiti di residenza dei dati in Germania. 
- Propongono l'offerta cloud globale completa, che comprende la versione più recente dei servizi e le nuove funzionalità, tra cui Microsoft Teams e Multi-Geo in Office 365. Confrontano i prodotti per area geografica per [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)e [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Offrono funzionalità complete e sicurezza di livello aziendale che consentono ai clienti di soddisfare i requisiti normativi e di conformità. 
- Sono accessibili tramite i contratti dei servizi online esistenti.

#### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Qual è la disponibilità dei servizi tra le diverse offerte di servizi cloud di Office 365?

I 15 servizi seguenti sono disponibili nell'offerta dei servizi cloud di Microsoft Cloud Germania (Microsoft Cloud Deutschland).  Non verranno aggiunti altri servizi all'offerta cloud di Microsoft Cloud Germania.

1. Exchange Online
2. Customer Lockbox (Exchange Online)
3. Gruppi (gruppi moderni)
4. Profilo di Delve
5. Exchange Online Protection
6. Advanced Threat Protection (ATP)
7. Advanced eDiscovery
8. Advanced Data Governance
9. SharePoint Online
10. Customer Lockbox (SharePoint Online)
11. OneDrive for Business
12. Skype for Business
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

Attualmente sono disponibili 29 servizi nell'ambito dell'offerta di Office 365 nelle nuove aree data center tedesche.  I nuovi servizi e funzionalità saranno disponibili regolarmente con i servizi globali di Office 365.

1. Exchange Online
2. Customer Lockbox (Exchange Online)
3. Gruppi (gruppi moderni)
4. Profilo di Delve
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Advanced Threat Protection (ATP)
9. Advanced eDiscovery
10. Advanced Security Management
11. Information Rights Management
12. Advanced Data Governance
13. SharePoint Online
14. Customer Lockbox (SharePoint Online)
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (transizione a Microsoft Teams durante la migrazione)
18. Cloud PBX
19. Servizi di conferenza PSTN
20. Chiamate PSTN
21. Microsoft Teams
22. Report degli amministratori/report sull'uso
23. Word Online, Excel Online, PowerPoint, OneNote e Visio Online
24. Planner
25. Sway
26. Office 365 Pro Plus
27. Outlook Mobile
28. EMS E3 (Azure Active Directory Premium P1, Intune e Rights Management Service)
29. Yammer Online

### <a name="when-will-migration-happen"></a>Quando viene eseguita la migrazione?

#### <a name="azure"></a>Azure 

È possibile iniziare la [migrazione](https://docs.microsoft.com/azure/germany/germany-migration-main) delle risorse di Azure in un'altra area oggi stesso. Se si dispone di Azure con Office 365, Dynamics 365 e/o Power BI, attenersi alla seguente procedura.

#### <a name="office-365"></a>Office 365

[Consenso esplicito](https://aka.ms/office365germanymoveoptin) alla migrazione gestita da Microsoft in data odierna. Quando saremo pronti per avviare la migrazione, forniremo informazioni tramite il [Centro messaggi](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) nell'interfaccia di amministrazione di Microsoft 365.

#### <a name="dynamics-365-and-power-bi"></a>Dynamics 365 e Power BI

Il consenso esplicito alla migrazione gestita da Microsoft per [Dynamics 365 Customer Engagement](https://aka.ms/D365ceOptIn) e [Power BI](https://aka.ms/PBIOptIn) in data odierna. Quando saremo pronti per avviare la migrazione, forniremo informazioni tramite il [Centro messaggi](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) nell'interfaccia di amministrazione di Microsoft 365.

### <a name="will-the-price-change-for-the-office-services-that-i-use"></a>Cambierà il prezzo dei servizi Office utilizzati?

Sì, i prezzi nelle aree globali di Microsoft, incluse le nuove aree data center, sono in genere inferiori.

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Come possono ottenere assistenza da Microsoft per la migrazione a una nuova area oppure le risposte alle domande relative al supporto?

In caso di domande, è possibile contattarci nel modo seguente oppure tramite il partner:

- Per Azure, è possibile inviare le [nuove richieste di supporto](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) nel portale di Azure.
- Per Office 365, è possibile inviare domande tramite il collegamento "Serve aiuto?" collegamento all'[interfaccia di amministrazione di Microsoft 365](https://portal.office.de/).
- Per i clienti Dynamics 365 Customer Engagement e Power BI che dispongono anche di Office 365, è possibile inviare domande tramite il collegamento "Serve aiuto?" collegamento all'[interfaccia di amministrazione di Microsoft 365](https://portal.office.de/). Le opzioni di supporto per Dynamics 365 Customer Engagement sono disponibili [qui](https://docs.microsoft.com/dynamics365/get-started/support/). Le opzioni di supporto per Power BI sono disponibili [qui](https://powerbi.microsoft.com/support/).

## <a name="more-information"></a>Altre informazioni

- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](https://aka.ms/office365germanymoveoptin)
- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [URL e intervalli di indirizzi IP per Office 365](https://aka.ms/o365endpoints)
- [Configurazione ibrida guidata di Office 365](https://aka.ms/HybridWizard)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
