---
title: Migrazione da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree data center tedesche
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
audience: ITPro
ms.topic: article
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
ms.openlocfilehash: ad6c81f04b9e8551ad6eeb6521f7562243df53e9
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346305"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migrazione da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree data center tedesche

> [!NOTE]
> Questo articolo si applica solo ai clienti idonei di Microsoft Cloud Deutschland.

Nell'agosto 2018, Microsoft ha annunciato l'intenzione di fornire il cloud Microsoft completo ( Azure, Office 365, Dynamics 365 e Power Platform) dalle nuove aree cloud in Germania per consentire al meglio la trasformazione digitale dei nostri clienti. Nel mese di agosto 2019, abbiamo annunciato che le nuove aree cloud in Germania erano in fase di apertura. Da allora abbiamo annunciato la disponibilità di Azure, Office 365, Dynamics 365 e Power Platform.

Le nuove aree geografiche sono progettate per soddisfare le esigenze in evoluzione dei clienti tedeschi con maggiore flessibilità, i servizi cloud intelligenti più recenti e la connettività completa alla rete cloud dei servizi Microsoft 365 e alla residenza dei dati dei clienti in Germania.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>Come eseguire la migrazione alle nuove aree data center tedesche

I clienti esistenti di Microsoft Cloud Deutschland possono ora iniziare a eseguire la migrazione dei clienti Office 365, Dynamics 365 Customer Engagement e Power Platform. Il primo passaggio consiste nel [consenso esplicito alla migrazione gestita da Microsoft](./ms-cloud-germany-migration-opt-in.md) nelle nuove aree data center tedesche.

Per le organizzazioni che acconsentino esplicitamente all'approccio basato su Microsoft, le migrazioni dovrebbero iniziare all'inizio del 2021 e verranno completate entro il 29 ottobre 2021. A seguito della migrazione, gli abbonamenti e i dati principali dei clienti verranno spostati nelle nuove aree geografiche tedesche.

In questo articolo viene fornita una panoramica dell'approccio basato su Microsoft per la migrazione, chiarezza sulle esperienze per utenti e amministratori durante e dopo la migrazione e sulle azioni che possono essere necessarie per i clienti in base ai carichi di lavoro utilizzati.

Come parte dell'approccio gestito da Microsoft, verrà eseguita la migrazione dei servizi seguenti:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business
- Skype for Business Online\*\*
- Gruppi di Office 365
- Dynamics 365 / Power Platform\*\*\*

\*\*Durante la migrazione da Microsoft Cloud Deutschland alle aree data center tedesche, i clienti di Skype for Business Online esistenti passano a Microsoft Teams. Per altre informazioni, vedere [Guida introduttiva per l'aggiornamento di Microsoft Teams](/microsoftteams/upgrade-start-here).

\*\*\*I prerequisiti e l'impatto della migrazione per questi servizi sono descritti nell'articolo Coinvolgimento dei clienti [di Dynamics 365.](/dynamics365/get-started/migrate-data-german-region)

Office 365 Video verrà ritirato il 1° marzo 2021. Se si sceglie di eseguire la migrazione del tenant di Office 365 nelle nuove aree data center tedesche, Office 365 Video non verrà più supportato dopo il completamento della migrazione di SharePoint Online. Per ulteriori informazioni, vedere [Sequenza temporale di Microsoft Cloud Deutschland.](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-is-the-migration-organized"></a>Come è organizzata la migrazione?

Questa figura mostra le dieci fasi della migrazione ai nuovi datacenter tedeschi.

![Le dieci fasi della migrazione ai nuovi datacenter tedeschi](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Queste fasi iniziano quando si [acconsente esplicitamente alla migrazione](./ms-cloud-germany-migration-opt-in.md). La maggior parte delle fasi di migrazione viene eseguita come operazioni di servizio back-end con un'interazione minima del cliente necessaria e viene eseguita una fase dopo l'altra. L'inizio di ulteriori attività guidate dai clienti e lo stato complessivo della migrazione verranno comunicati tramite il Centro messaggi dell'interfaccia di amministrazione di Microsoft 365 durante il processo di migrazione. Un esempio di attività può includere aggiornamenti DNS gestiti dal cliente, riconfigurazione della configurazione ibrida per Exchange clienti ibridi o migrazione di Azure.

La migrazione non viene avviata immediatamente quando si verifica il consenso esplicito. L'organizzazione viene aggiunta all'elenco dei tenant pianificati per la migrazione successiva. È possibile iniziare le fasi pre-lavorative ora in quanto sono fondamentali per garantire la corretta migrazione e l'utilizzo al termine:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)

Una settimana prima dell'inizio della migrazione del tenant, si riceverà un avviso nel servizio Centro messaggi come avviso finale che indica che tutti i prerequisiti devono essere completati.

La migrazione sposterà il tenant di Azure AD dal servizio Azure AD per la Germania sovrana all'istanza dei servizi Office 365 di Azure AD nell'area DELL'UE.

La fase successiva è la migrazione delle sottoscrizioni&#39;tenant e delle licenze utente da prodotti specifici della Germania a prodotti globali.

Una volta completati tutti i passaggi, inclusa la migrazione di Azure del cliente, il tenant viene finalizzato nel servizio Office 365 e la migrazione viene contrassegnata come completata. A questo punto, viene fornito l'aggiornamento finale al Centro messaggi. Il tenant è ora un'organizzazione Office 365 globale.

Viene notificato l'avanzamento della migrazione con i post del Centro messaggi. I post si verificheranno in fasi cardine specifiche e forniranno indicazioni sull'avanzamento di un passaggio e informazioni importanti su cui i clienti possono agire in base ai requisiti del processo. Le notifiche del Centro messaggi vengono fornite nelle attività cardine seguenti:

- Inizio della migrazione (5 giorni lavorativi prima dell'inizio della migrazione di Azure AD)
- Migrazione di Azure AD completata
- Migrazione di sottoscrizioni e licenze completata
- SharePoint migrazione completata
- Exchange migrazione completata
- Skype for Business completato
- Dynamics complete
- Power BI completato
- Completamento del cutover finale dei servizi

Dopo il cutover finale di Azure AD al servizio globale, è previsto che tutti i client e le applicazioni siano completamente transitati per usare gli endpoint corretti. Dopo il cutover finale è disponibile una finestra di 30 giorni in cui potrebbe essere possibile continuare a ottenere token Azure AD dal servizio Microsoft Cloud Deutschland. Alla scadenza della finestra di 30 giorni, i client e le applicazioni non saranno più in grado di accedere agli endpoint di Azure AD di Microsoft Cloud Deutschland. Le applicazioni o l'accesso utente avranno esito negativo da questo punto. È necessario verificare che tutti gli utenti e le applicazioni siano migrati agli endpoint corretti prima della chiusura di questo intervallo di tempo. 

## <a name="moving-to-the-new-german-datacenter-regions"></a>Passaggio alle nuove aree data center tedesche

I clienti esistenti di Microsoft Cloud Deutschland possono ora iniziare a eseguire la migrazione dei servizi Office 365, Dynamics 365 Customer Engagement e Power Platform. Il primo passaggio consiste nel [consenso esplicito alla migrazione gestita da Microsoft](./ms-cloud-germany-migration-opt-in.md) nelle nuove aree data center tedesche. Quando si rinnova l'abbonamento, si acconsente automaticamente al consenso esplicito per una migrazione assistita da Microsoft. Microsoft invierà una notifica agli amministratori tenant dei clienti tramite posta elettronica e nel Centro messaggi dell Microsoft 365 di amministrazione quando si è verificato questo problema. Tuttavia, se preferisci avviare il processo [](./ms-cloud-germany-migration-opt-in.md) ora, puoi acconsentire esplicitamente direttamente Microsoft 365'interfaccia di amministrazione oggi. Le migrazioni dovrebbero iniziare all'inizio del 2021 e verranno completate entro il 29 ottobre 2021. 

Come risultato della migrazione, i dati e le sottoscrizioni dei clienti di base vengono spostati nelle nuove aree data center tedesche.

> [!NOTE]
> Questo articolo include indicazioni per la migrazione dei Office 365 solo. Se si eseguono carichi di lavoro di Azure aggiuntivi in Microsoft Cloud Deutschland, vedere le linee guida [per la migrazione per Azure Germania.](/azure/germany/germany-migration-main)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Come prepararsi per la migrazione ai servizi di Office 365 nelle nuove aree data center tedesche

Il primo passaggio consiste nel notificare a Microsoft l'autorizzazione a eseguire la migrazione dell'abbonamento e dei dati da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree data center tedesche. Per istruzioni, [fai](./ms-cloud-germany-migration-opt-in.md) riferimento al processo di consenso esplicito e tieni presente che:

- Tutti i clienti che effettuano la migrazione devono verificare la connettività agli URL Office 365 Services Office 365 e agli indirizzi [IP](urls-and-ip-address-ranges.md), che includono le nuove aree data center tedesche. L'inazione può causare un errore del servizio e del client.
- Esaminare l'elenco [delle attività pre-lavorative](ms-cloud-germany-transition-add-pre-work.md) per assicurarsi che l'organizzazione sia informata e preparata per le modifiche.
- È consigliabile esaminare la descrizione Office 365 servizio della piattaforma per comprendere quali funzionalità e servizi saranno disponibili per l'organizzazione dopo la migrazione nell'area tedesca.
- Le sottoscrizioni di valutazione non verranno migrate e blocteranno la migrazione di tutte le sottoscrizioni a pagamento. È necessario annullare eventuali versioni di valutazione o convertirsi in sottoscrizioni a pagamento prima dell'inizio della migrazione.

## <a name="where-do-i-go-from-here"></a>Dove posso andare da qui?

Esaminare la sezione Domande frequenti seguente.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="is-migration-required"></a>È obbligatoria la migrazione?

Microsoft offre Office 365 tenant da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree data center tedesche senza costi aggiuntivi. Anche se ti consigliamo vivamente di acconsentire esplicitamente alla migrazione alle nuove aree data center tedesche, continueremo a fornire gli aggiornamenti della sicurezza necessari per l'area Microsoft Cloud Deutschland.

Office 365 servizi nelle nuove aree data center tedesche:

- Offrono prezzi di mercato competitivi per [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) e [Power BI](https://powerbi.microsoft.com/pricing/).
- Sono connessi alla rete globale di Microsoft&#39;, offrendo centinaia di siti perimetrali di rete, posizioni di peering e punti di uscita per offrire un'esperienza utente affidabile in qualsiasi parte del mondo.
- Consentono ai clienti locali di rispettare i requisiti di residenza dei dati in Germania.
- Offri la nostra offerta cloud globale completa con le versioni più recenti dei nostri servizi e nuove funzionalità, tra cui Microsoft Teams e Multi-Geo in Office 365. Confrontano i prodotti per area geografica per [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)e [Dynamics 365](/dynamics365/get-started/availability).
- Offrono funzionalità complete e sicurezza di livello aziendale che consentono ai clienti di soddisfare i requisiti normativi e di conformità.
- Sono accessibili tramite i contratti dei servizi online esistenti.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Qual è la disponibilità dei servizi tra le diverse offerte di servizi cloud di Office 365?
<h2 id="serv-avail"></h2>

Nell'offerta di servizi cloud Microsoft Cloud Deutschland sono disponibili i 15 servizi seguenti. Non stiamo aggiungendo nuovi servizi a Microsoft Cloud Deutschland.

1. Exchange Online
2. Customer Lockbox (Exchange Online)
3. Gruppi (gruppi moderni)
4. Profilo di Delve
5. Exchange Online Protection
6. Defender per Office 365
7. Advanced eDiscovery
8. Advanced Data Governance
9. SharePoint Online
10. Customer Lockbox (SharePoint Online)
11. OneDrive for Business
12. Skype for Business Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

Attualmente sono disponibili 39 servizi come parte dei Office 365 nelle nuove aree data center tedesche. I nuovi servizi e funzionalità saranno disponibili regolarmente con i servizi globali di Office 365.

1. Exchange Online
2. Customer Lockbox per Exchange Online
3. Gruppi di Microsoft 365
4. Profilo di Delve
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Defender per Office 365
9. Advanced eDiscovery
10. Advanced Security Management
11. Information Protection per Office 365 
12. Advanced Data Governance
13. SharePoint Online
14. Customer Lockbox per SharePoint Online
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (verrà eseguita la migrazione a Microsoft Teams durante la migrazione)
18. Cloud PBX
19. Servizi di conferenza PSTN
20. Chiamate PSTN
21. Microsoft Teams
22. Report degli amministratori/report sull'uso
23. Office per il web
24. Planner
25. Sway
26. Microsoft 365 Apps
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune e Rights Management Service)
29. Yammer Enterprise
30. Microsoft Forms
31. Power Automate per Office 365
32. Power Virtual Agents per Office 365
33. PowerApps per Office 365
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. Elenchi

### <a name="when-will-migration-happen"></a>Quando viene eseguita la migrazione?

**Azure**

Se sei solo un cliente di Azure, puoi iniziare a eseguire la [migrazione](/azure/germany/germany-migration-main) delle risorse di Azure in un'altra area geografica. 

Se si dispone di Azure con Office 365, Dynamics 365 o Power BI, è necessario seguire il processo di migrazione per garantire la corretta migrazione di AzureAD prima di iniziare la migrazione di Azure con guida autonoma. È necessario completare la migrazione di Azure prima della chiusura del servizio per mantenere i carichi di lavoro di Azure con AzureAD e Office 365'organizzazione.

**Office 365**

[Consenso esplicito](./ms-cloud-germany-migration-opt-in.md) alla migrazione gestita da Microsoft in data odierna. Quando siamo pronti per avviare la migrazione, ti informeremo tramite il Centro messaggi nell'Microsoft 365 di amministrazione.

**Dynamics 365 e Power BI**

Acconsentire esplicitamente alla migrazione guidata da Microsoft per [Dynamics 365 Customer Engagement](/dynamics365/get-started/migrate-data-german-region) [e](/power-bi/admin/service-admin-migrate-data-germany) Power BI oggi. Quando saremo pronti per avviare la migrazione, forniremo informazioni tramite il Centro messaggi nell'interfaccia di amministrazione di Microsoft 365.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Il prezzo cambia per i Office 365 che uso?

Sì. I prezzi nelle aree cloud globali di Microsoft&#39;(incluse le nuove aree data center) sono in genere inferiori.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Durante la migrazione della sottoscrizione, quali SKU e licenze verranno applicati all'organizzazione e agli utenti?

Durante la migrazione da Microsoft Cloud Deutschland ai servizi Office 365, le SKU specifiche del servizio germania vengono sostituite con versioni globali dello stesso SKU o simili. Per la maggior parte dei casi, lo SKU nei servizi Office 365 è lo stesso, tuttavia esistono poche sostituzioni in cui la SKU in Germania non è più disponibile nei servizi di Office 365. Se si desidera aggiornare lo SKU assegnato all'organizzazione al termine della migrazione, contattare il venditore per aggiungere o modificare i servizi assegnati.

| Microsoft Cloud Deutschland - Product SKU (DE) | Microsoft Cloud Global - Product SKU (WW) |
| --- | --- |
| Customer Lockbox \_ DE (LOCKBOX \_ DE) | Customer Lockbox (LOCKBOX) |
| Dynamics 365 edizione Enterprise - Database Archiviazione \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 edizione Enterprise - Database aggiuntivo Archiviazione (CRMSTORAGE) |
| Dynamics 365 edizione Enterprise - Istanza aggiuntiva non di produzione \_ DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 edizione Enterprise - Istanza aggiuntiva non di produzione (CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service edizione Enterprise \_ DE (DYN365 \_ ENTERPRISE CUSTOMER SERVICE \_ \_ \_ DE) | Dynamics 365 for Customer Service edizione Enterprise (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales edizione Enterprise \_ DE (DYN365 \_ ENTERPRISE SALES \_ \_ DE) | Dynamics 365 for Sales edizione Enterprise (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 for Team Members edizione Enterprise \_ DE (DYN365 \_ ENTERPRISE TEAM MEMBERS \_ \_ \_ DE) | Dynamics 365 for Team Members edizione Enterprise (MEMBRI DEL TEAM DYN365 \_ \_ \_ ENTERPRISE) |
| Dynamics 365 Piano 1 edizione Enterprise \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 Piano 1 edizione Enterprise (DYN365 \_ ENTERPRISE \_ PLAN1) |
| \_ECAL Services (EOA, EOP, DLP) DE (ECAL \_ SERVICES \_ DE) | ECAL Services (EOA, EOP, DLP) (SERVIZI \_ ECAL) |
| \_Enterprise Mobility + Security E3 DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| \_Exchange Online (Piano 1) DE (EXCHANGESTANDARD \_ DE) | Exchange Online (Piano 1) (EXCHANGESTANDARD) |
| \_Exchange Online (Piano 2) DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (Piano 2) (EXCHANGEENTERPRISE) |
| \_Archiviazione Exchange Online per Exchange Online DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Archiviazione Exchange Online per Exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| \_Archiviazione Exchange Online per Exchange Server DE (EXCHANGEARCHIVE \_ DE) | Archiviazione Exchange Online per Exchange Server (EXCHANGEARCHIVE) |
| \_Exchange Online Essentials DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS) |
| \_Chiosco Exchange Online DE (EXCHANGEDESKLESS \_ DE) | Chiosco Exchange Online (EXCHANGEDESKLESS) |
| \_Exchange Online Protection DE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Microsoft Dynamics CRM Online Istanza \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online Istanza (CRMINSTANCE) |
| Office 365 A1 per faculty \_ DE (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 per i docenti (FACOLTÀ \_ STANDARDWOFFPACK) |
| Office 365 A1 per gli \_ studenti DE (STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1 per studenti (STANDARDWOFFPACK \_ STUDENT) |
| \_Office 365 Advanced Compliance DE (EQUIVIO \_ ANALYTICS \_ DE) | Microsoft 365 E5 Compliance (CONFORMITÀ DI INFORMATION \_ \_ PROTECTION) |
|Microsoft Defender per Office 365 (Piano 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender per Office 365 (Piano 1) (ATP \_ ENTERPRISE) |
| \_Office 365 Business Essentials DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic (O365 \_ BUSINESS \_ ESSENTIALS) |
| \_Office 365 Business Premium DE (O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| \_Office 365 Business DE (O365 \_ BUSINESS \_ DE) | Microsoft 365 Apps for business (O365 \_ BUSINESS) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 senza ProPlus \_ DE (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 senza ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE (STANDARDPACK \_ DE) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 File Archiviazione DE \_ (SHAREPOINTSTORAGE \_ DE) | Office 365 File Archiviazione (SHAREPOINTSTORAGE) |
| \_Office 365 F1 DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus per Faculty \_ DE (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus per istituti di docente (OFFICESUBSCRIPTION \_ FACULTY) |
| Office 365 ProPlus for Students \_ DE (OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 ProPlus per studenti (OFFICESUBSCRIPTION \_ STUDENT) |
| \_Office 365 ProPlus DE (OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| \_OneDrive for Business (Piano 1) DE (WACONEDRIVESTANDARD \_ DE) | OneDrive for Business (Piano 1) (WACONEDRIVESTANDARD) |
| \_OneDrive for Business (Piano 2) DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive for Business (Piano 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro per i docenti \_ DE (POWER \_ BI \_ PRO \_ FACULTY \_ DE) | Power BI Pro per istituti di docente (POWER \_ BI \_ PRO \_ FACULTY) |
| \_Power BI Pro DE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| \_Project Online Essentials DE (PROJECTESSENTIALS \_ DE) | Project Online Essentials (PROJECTESSENTIALS) |
| \_Project Online Premium DE (PROJECTPREMIUM \_ DE) | Project Online Premium (PROJECTPREMIUM) |
| \_Project Online Professional DE (PROJECTPROFESSIONAL \_ DE) | Project Online Professional (PROJECTPROFESSIONAL) |
| \_Project - Piano 3 DE (PROJECTPROFESSIONAL \_ DE) | Project - Piano 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| \_SharePoint Online (Piano 1) DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (Piano 1) (SHAREPOINTSTANDARD) |
| \_SharePoint Online (Piano 2) DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (Piano 2) (SHAREPOINTENTERPRISE) |
| Skype for Business Online (Piano 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype for Business Online (Piano 1) \_ DE (MCOIMP \_ DE) | Skype for Business Online (piano 1) (MCOIMP) |
| Skype for Business Online (Piano 2) \_ DE (MCOSTANDARD \_ DE) | Skype for Business Online (Piano 2) (MCOSTANDARD) |
| Skype for Business Plus CAL \_ DE (MCOPLUSCAL \_ DE) | Skype for Business Plus CAL (MCOPLUSCAL) |
| Visio Piano online 1 per docenti \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio Piano online 1 per i docenti (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Piano online 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Piano online 1 (VISIOONLINE \_ PLAN1) |
| Visio Piano online 2 per faculty \_ DE (VISIOCLIENT \_ FACULTY \_ DE) | Visio Piano online 2 per i docenti (VISIOCLIENT \_ FACULTY) |
| Visio Piano online 2 \_ DE (VISIOCLIENT \_ DE) | Visio Piano online 2 (VISIOCLIENT) |
| \_Visio - Piano 1 DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio - Piano 1 (VISIOONLINE \_ PLAN1) |
| \_Visio - Piano 2 DE (VISIOCLIENT \_ DE) | Visio - Piano 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Come possono ottenere assistenza da Microsoft per la migrazione a una nuova area oppure le risposte alle domande relative al supporto?

Se hai domande, puoi contattarci o il tuo partner:

- Per Azure, è possibile inviare le [nuove richieste di supporto](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) nel portale di Azure.
- Ad Office 365, è possibile inviare domande utilizzando il collegamento Serve &quot; assistenza? &quot; [dell'Microsoft 365 di amministrazione.](https://portal.office.de/)
- Se si è clienti di Dynamics 365 Customer Engagement e Power BI e si dispone anche di Office 365, è possibile inviare domande utilizzando il collegamento Serve assistenza? dell'interfaccia di amministrazione di &quot; &quot; [Microsoft 365](https://portal.office.de/). Le opzioni di supporto per Dynamics 365 Customer Engagement sono disponibili [qui](/dynamics365/get-started/support/). Le opzioni di supporto per Power BI sono disponibili [qui](https://powerbi.microsoft.com/support/).

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>Il cliente ha già un tenant M365 nel cloud Microsoft globale oltre a un tenant Microsoft Cloud Deutschland. Questi due tenant possono essere uniti in uno come parte della migrazione?

No, non esiste alcuna funzionalità di unione tenant. I tenant rimarranno separati e univoci poiché ogni tenant dispone di uno spazio dei nomi e di un ID univoco. Microsoft eseguirà la migrazione di un tenant Microsoft Cloud Deutschland nel cloud globale, se lo si desidera, altrimenti il cliente può annullarlo e abbandonarlo.


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>Quali azioni devono essere eseguite dalla maggior parte degli utenti finali durante la migrazione?
La migrazione è progettata per avere un impatto minimo sugli utenti finali/clienti.
- Verificare che Office applicazioni esercitino le versioni più recenti disponibili. 
- I clienti Skype for Business transizione a Teams come parte della migrazione e potrebbero dover scaricare e installare Teams [nei](/deployoffice/teams-install) dispositivi.
- Gli utenti finali potrebbero dover disconnettersi dalle applicazioni Office ed eseguire di nuovo l'accesso al termine della migrazione. 
- I clienti che eseguono il client OneDrive Sync devono disconnettersi dalla workstation e accedere di nuovo per consentire al client di sincronizzazione di OneDrive di accedere al servizio Azure Active Directory globale.
- Tenere presenti i nuovi URL globali al termine della migrazione, in particolare Outlook Web Access (ad esempio, utilizzare outlook.office365.com). SharePoint I client online continueranno a connettersi allo spazio dei nomi MCD usando l'URL esistente (ad esempio: contoso.sharepoint.de).


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>Quali clienti sono interessati dalla Azure Active Directory migrazione? 

Tutti i clienti di Office365 dipendono Azure Active Directory per autenticare e archiviare i componenti di servizio critici necessari per il funzionamento dei servizi ospitati da Microsoft. 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Quali sono gli effetti della migrazione Azure Active Directory migrazione?

La migrazione iniziale di Azure Active Directory nella fase iniziale non ha alcun impatto sull'esperienza del cliente. Dopo la fase di migrazione finale, tutti i servizi per il tenant del cliente sono completamente nel servizio globale. Dopo questa fase finale, il servizio Azure Active Directory in Microsoft Cloud Deutschland potrebbe non accettare più richieste di autorizzazione o fornire token di accesso a Office servizi.


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>Cosa significa garantire la connettività di rete Office 365 url e indirizzi IP dei [servizi?](./urls-and-ip-address-ranges.md)

In questo articolo vengono descritti gli URL e gli indirizzi IP necessari per il corretto funzionamento del servizio globale per garantire una buona esperienza del cliente. In casi relativamente rari, alcuni clienti tentano di configurare la sicurezza perimetrale di rete in modo da ridurre al minimo i flussi di traffico e hanno limitato l'accesso ai servizi solo nell'ambito degli intervalli IP del servizio Microsoft Cloud Deutschland.


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>Come si gestiscono le modifiche DNS per Exchange Online in modo che la posta continui a scorrere?

Gli intervalli IP gestiti da Microsoft e le zone DNS vengono transizione durante e come parte della migrazione al servizio globale. 

Le zone DNS gestite dal cliente, ad esempio i record MX di dominio personalizzati, sono responsabilità del cliente, tuttavia, semplificare questa migrazione che il record MX gestito dal cliente punta a un endpoint del servizio Office 365 nella zona di office.de e Microsoft gestisce automaticamente la migrazione di questo endpoint di servizio.


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>Come si gestiscono le modifiche DNS per Skype for Business? 
 
Tutti Skype per le aziende in verranno transizione a Microsoft Teams. La transizione delle zone DNS Skype clienti non è necessaria nella migrazione a Teams. I clienti potranno accedere immediatamente Teams con tutte le funzionalità dopo la migrazione.
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>La Outlook per iOS e Android funzionerà dopo la migrazione? 

Sì. Il consiglio di Microsoft è che tutti i clienti eseguono le versioni più recenti Office client, tra cui Outlook per i client iOS e Android. Al termine della migrazione al servizio globale Office 365, tutti i client Office dovranno disconnettersi e accedere di nuovo per ottenere un nuovo token di accesso Azure Active Directory dal servizio globale. 



## <a name="next-step"></a>Passaggio successivo

[Acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Passaggio attraverso la transizione:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [ADFS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Informazioni sul programma di migrazione di Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](/microsoftteams/upgrade-start-here)
