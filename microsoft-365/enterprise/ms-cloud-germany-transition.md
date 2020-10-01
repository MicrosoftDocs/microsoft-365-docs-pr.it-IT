---
title: Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 09/30/2020
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
ms.openlocfilehash: a77dc43c4c30992d2e50aad94878f9269573db52
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327118"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco

> [!NOTE]
> Questo articolo si applica solo ai clienti Microsoft Cloud Deutschland idonei.

Nell'agosto 2018, Microsoft ha annunciato la nostra intenzione di fornire l'intera Microsoft Cloud – Azure, Office 365, Dynamics 365 e Power Platform – dalle nuove aree cloud in Germania per meglio abilitare la trasformazione digitale dei clienti. Nel mese di agosto 2019, abbiamo annunciato che le nuove aree cloud in Germania erano in fase di apertura. Da allora, è stata annunciata la disponibilità di Azure, Office 365, Dynamics 365 e Power Platform.

Le nuove aree geografiche sono progettate per rispondere alle esigenze evolutive dei clienti tedeschi con una maggiore flessibilità, i più recenti servizi cloud intelligenti e la connettività completa alla rete cloud di Microsoft 365 Services, nonché la residenza dei dati del cliente in Germania.

## <a name="how-to-migrate-to-the-new-german-regions"></a>Come eseguire la migrazione alle nuove aree geografiche tedesche

I clienti esistenti di Microsoft Cloud Deutschland possono ora iniziare a eseguire la migrazione dei clienti di Office 365, Dynamics 365 e Power Platform. Il primo passaggio consiste nel [consenso esplicito alla migrazione gestita da Microsoft](https://aka.ms/office365germanymoveoptin) nelle nuove aree data center tedesche.

Per le organizzazioni che scelgono l'approccio basato su Microsoft, le migrazioni dovrebbero iniziare all'inizio del 2021 e verranno completate entro il 29 ottobre 2021. A seguito della migrazione, gli abbonamenti e i dati principali dei clienti verranno spostati nelle nuove aree geografiche tedesche.

In questo articolo viene fornita una panoramica dell'approccio basato su Microsoft per la migrazione, la chiarezza sulle esperienze sia per gli utenti che per gli amministratori durante e dopo la migrazione e le azioni che potrebbero essere necessarie per i clienti in base ai carichi di lavoro utilizzati.

Come parte dell'approccio gestito da Microsoft, verrà eseguita la migrazione dei servizi seguenti:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business

- Skype for business online\*\*
- Gruppi di Office 365
- Dynamics 365/Power Platform\*\*\*

\*\*Durante la migrazione da Microsoft Cloud Deutschland alle aree di datacenter tedesche, i clienti esistenti di Skype for business online potranno passare a Microsoft teams. Per altre informazioni, vedere [Guida introduttiva per l'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home).

\*\*\*I prerequisiti e l'impatto della migrazione per questi servizi sono descritti nell'articolo relativo all' [impegno dei clienti Dynamics 365](https://aka.ms/d365ceoptin) .

Office 365 Video verrà ritirato il 1° marzo 2021. Se si sceglie di eseguire la migrazione del tenant di Office 365 nelle nuove aree data center tedesche, Office 365 Video non verrà più supportato dopo il completamento della migrazione di SharePoint Online. Per ulteriori informazioni, fare clic [qui](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline) .

## <a name="how-is-the-migration-organized"></a>Come viene organizzata la migrazione?

Questa figura rappresenta i vari componenti di Office 365 e Dynamics 365 nella migrazione ai nuovi Data Center tedeschi.

![Componenti di Office 365 e Dynamics 365 nella migrazione ai nuovi datacenter in Germania](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

La migrazione viene eseguita in fasi che vengono avviate tutti quando si effettua l' [opt-in per la migrazione](https://aka.ms/office365germanymoveoptin). La maggior parte delle fasi di migrazione viene eseguita come operazioni di servizio back-end con un'interazione minima dei clienti e viene eseguita una fase dopo l'altra. La data di inizio per altre attività guidate dai clienti e lo stato di migrazione generale verrà comunicata tramite il centro messaggi dell'interfaccia di amministrazione di Microsoft 365 durante il processo di migrazione. L'esempio di attività può includere gli aggiornamenti DNS gestiti dal cliente, la riconfigurazione della configurazione ibrida per i clienti ibridi di Exchange o la migrazione di Azure.

La migrazione non inizia immediatamente quando si verifica l'opzione opt-in. L'organizzazione viene aggiunta all'elenco dei tenant pianificati per la migrazione successiva. È possibile iniziare le fasi di prelavoro ora, poiché queste sono fondamentali per garantire la corretta migrazione e l'utilizzo al termine.

Una settimana prima dell'inizio della migrazione del tenant, si riceverà un avviso nel servizio centro messaggi come avviso finale che tutti i prerequisiti devono essere completati.

La migrazione sposterà il tenant di Azure AD dal servizio di Azure ad di Sovereign Germany all'istanza di servizi di Office 365 di Azure AD nell'area dell'Unione europea.

La fase successiva è la migrazione delle sottoscrizioni del tenant&#39;s e delle licenze utente provenienti da prodotti specifici per la Germania.

Dopo aver completato tutti i passaggi, inclusa la migrazione di Azure dei clienti, il tenant è stato finalizzato nel servizio servizi di Office 365 e la migrazione è contrassegnata come completata. A questo punto, viene fornito l'aggiornamento finale al centro messaggi. Il tenant non è ora un'organizzazione di Office 365 completamente globale.

Viene notificato lo stato di avanzamento della migrazione con i post del centro messaggi. I post si verificheranno in tappe specifiche e forniranno indicazioni relative allo stato di avanzamento di un passaggio, nonché informazioni importanti per i clienti affinché agiscano in base ai requisiti del processo. Le notifiche del centro messaggi vengono fornite nelle tappe seguenti:

- Inizio della migrazione (5 giorni lavorativi prima dell'inizio della migrazione di Azure AD)
- Migrazione di Azure AD completata
- Completamento della migrazione delle licenze e della sottoscrizione
- Completamento della migrazione di SharePoint
- Completamento della migrazione di Exchange
- Completamento di Skype for business
- Dinamica completata
- Power BI completo
- La completa finale dei servizi è stata completata

## <a name="moving-to-the-new-german-regions"></a>Spostamento nelle nuove aree tedesche

I clienti di Microsoft Cloud Germany (Microsoft Cloud Deutschland) esistenti possono ora iniziare a eseguire la migrazione dei clienti di Office 365, Dynamics 365 e Power Platform. Il primo passaggio consiste nel [consenso esplicito alla migrazione gestita da Microsoft](https://aka.ms/office365germanymoveoptin) nelle nuove aree data center tedesche. Quando si rinnova l'abbonamento, si opta automaticamente per una migrazione assistita da Microsoft. Microsoft notificherà agli amministratori tenant del cliente la posta elettronica e nel centro messaggi dell'interfaccia di amministrazione di Microsoft 365 quando questo è avvenuto. Tuttavia, se si preferisce avviare il processo ora, è possibile effettuare l' [opt-in](https://aka.ms/office365germanymoveoptin) direttamente nell'interfaccia di amministrazione di Microsoft 365 oggi. Le migrazioni dovrebbero iniziare all'inizio del 2021 e verranno completate entro il 29 ottobre 2021. 

A seguito della migrazione, gli abbonamenti e i dati principali dei clienti verranno spostati nelle nuove aree geografiche tedesche.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Come prepararsi per la migrazione ai servizi di Office 365 nelle nuove aree data center tedesche

Il primo passaggio consiste nel informare Microsoft in modo che sia possibile eseguire la migrazione dell'abbonamento e dei dati da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco. Fare riferimento al [processo di opt-in](https://aka.ms/office365germanymoveoptin) per le istruzioni e tenere presente che:

- Tutti i clienti che eseguono la migrazione devono verificare la connettività a Office 365 Services [office 365 URL e indirizzi IP](urls-and-ip-address-ranges.md), tra cui le nuove aree del datacenter tedesco. L'inazione può causare un errore del servizio e del client.
- È consigliabile consultare la descrizione del servizio piattaforma Office 365 per comprendere le caratteristiche e i servizi resi disponibili per l'organizzazione dopo la migrazione all'area tedesca.
- Gli abbonamenti di valutazione non verranno migrati e bloccherà la migrazione di tutti gli abbonamenti a pagamento. Prima di iniziare la migrazione, è necessario annullare qualsiasi prova o conversione in abbonamenti pagati.

## <a name="where-do-i-go-from-here"></a>Dove si va da qui?

Esaminare la sezione delle domande frequenti riportate di seguito.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="is-migration-required"></a>È obbligatoria la migrazione?

Microsoft offre la migrazione di Office 365 tenant da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco senza costi aggiuntivi. Anche se si consiglia di eseguire la migrazione alle nuove aree del datacenter tedesco, si continuerà a fornire gli aggiornamenti di sicurezza necessari per l'area di Microsoft Cloud Deutschland.

Servizi di Office 365 nelle nuove aree del datacenter tedesco:

- Offrono prezzi di mercato competitivi per [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) e [Power BI](https://powerbi.microsoft.com/pricing/).
- Sono connessi alla rete globale di Microsoft&#39;, offrendo centinaia di siti perimetrali di rete, posizioni di peering e punti di uscita per offrire un'esperienza utente affidabile in qualsiasi parte del mondo.
- Consentono ai clienti locali di rispettare i requisiti di residenza dei dati in Germania.
- Offrire la nostra offerta cloud globale completa con le versioni più recenti dei nostri servizi e nuove funzionalità, tra cui Microsoft teams e multi-Geo in Office 365. Confrontano i prodotti per area geografica per [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)e [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Offrono funzionalità complete e sicurezza di livello aziendale che consentono ai clienti di soddisfare i requisiti normativi e di conformità.
- Sono accessibili tramite i contratti dei servizi online esistenti.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Qual è la disponibilità dei servizi tra le diverse offerte di servizi cloud di Office 365?

I seguenti 15 servizi sono disponibili nell'offerta cloud di cloud Deutschland Microsoft. Non vengono aggiunti nuovi servizi a Microsoft Cloud Deutschland.

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
12. Skype for Business Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

Attualmente sono disponibili 29 servizi nell'ambito dell'offerta di Office 365 nelle nuove aree data center tedesche. I nuovi servizi e funzionalità saranno disponibili regolarmente con i servizi globali di Office 365.

1. Exchange Online
2. Archivio protetto dei clienti per Exchange Online
3. Gruppi di Microsoft 365
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
14. Archivio protetto dei clienti per SharePoint Online
15. OneDrive for Business
16. Microsoft Stream
17. Skype for business (eseguirà la migrazione a Microsoft teams durante la migrazione)
18. Cloud PBX
19. Servizi di conferenza PSTN
20. Chiamate PSTN
21. Microsoft Teams
22. Report degli amministratori/report sull'uso
23. Word Online, Excel Online, PowerPoint, OneNote e Visio Online
24. Planner
25. Sway
26. Microsoft 365 Apps
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune e Rights Management Service)
29. Yammer Online

### <a name="when-will-migration-happen"></a>Quando viene eseguita la migrazione?

**Azure**

Se si è solo clienti di Azure, è possibile iniziare a eseguire la [migrazione](https://docs.microsoft.com/azure/germany/germany-migration-main) delle risorse di Azure in un'altra area di oggi. Se si dispone di Azure con Office 365, Dynamics 365 o Power BI, attenersi alla procedura riportata di seguito.

**Office 365**

[Consenso esplicito](https://aka.ms/office365germanymoveoptin) alla migrazione gestita da Microsoft in data odierna. Quando si è pronti per iniziare la migrazione, verrà informato il centro messaggi nell'interfaccia di amministrazione di Microsoft 365.

**Dynamics 365 e Power BI**

Opt-in per la migrazione Microsoft-driven per [Dynamics 365 Customer Engagement](https://aka.ms/D365ceOptIn) e [Power bi](https://aka.ms/PBIOptIn) oggi. Quando saremo pronti per avviare la migrazione, forniremo informazioni tramite il Centro messaggi nell'interfaccia di amministrazione di Microsoft 365.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>La variazione dei prezzi per i servizi di Office 365 che utilizzo?

Sì. I prezzi nelle aree cloud globali di Microsoft&#39;(incluse le nuove aree dei datacenter) sono in genere inferiori.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Durante la migrazione della sottoscrizione, quali SKU e licenze verranno applicate all'organizzazione e agli utenti?

Durante la migrazione da Microsoft Cloud Deutschland ai servizi di Office 365, le SKU specifiche per il servizio in Germania sono state sostituite con versioni globali dello stesso SKU o similari. Per la maggior parte dei casi, l'USK dei servizi di Office 365 è la stessa, tuttavia esistono poche sostituzioni in cui l'USK in Germania non è più disponibile nei servizi di Office 365. Se si desidera aggiornare l'SKU assegnato all'organizzazione al termine della migrazione, contattare il venditore per aggiungere o modificare i servizi assegnati.

| Microsoft Cloud Deutschland-SKU di prodotto (DE) | Microsoft cloud Global-SKU prodotto (WW) |
| --- | --- |
| Cassaforte del cliente \_ de (archivio protetto \_ ) | Archivio protetto dei clienti (protetto) |
| Dynamics 365 Enterprise Edition-database di archiviazione aggiuntivo \_ de (CRMSTORAGE \_ de) | Dynamics 365 Enterprise Edition-archivio di database aggiuntivo (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition-ulteriore istanza di non produzione \_ de (CRMTESTINSTANCE \_ de) | Dynamics 365 Enterprise Edition-istanza ulteriore di non produzione (CRMTESTINSTANCE) |
| Dynamics 365 per il servizio clienti Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Customer \_ Service \_ de) | Dynamics 365 per Customer Service Enterprise Edition ( \_ servizio clienti di DYN365 Enterprise \_ \_ ) |
| Dynamics 365 per Sales Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Sales \_ de) | Dynamics 365 per Sales Enterprise Edition (DYN365 \_ Enterprise \_ Sales) |
| Dynamics 365 per i membri del team Enterprise Edition \_ de (membri del team di DYN365 \_ Enterprise \_ \_ \_ de) | Dynamics 365 per i membri del team Enterprise Edition (membri del team dell'organizzazione di DYN365 \_ \_ \_ ) |
| Dynamics 365 Plan 1 Enterprise Edition \_ de (DYN365 \_ Enterprise \_ PLAN1 \_ de) | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ Enterprise \_ PLAN1) |
| Servizi di ECAL (EOA, EOP, DLP) \_ de (ECAL \_ Services \_ de) | Servizi di ECAL (EOA, EOP, DLP) ( \_ servizi di ECAL) |
| Enterprise Mobility + Security E3 \_ de (EMS \_ de) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (piano 1) \_ de (EXCHANGESTANDARD \_ de) | Exchange Online (piano 1) (EXCHANGESTANDARD) |
| Exchange Online (piano 2) \_ de (EXCHANGEENTERPRISE \_ de) | Exchange Online (piano 2) (EXCHANGEENTERPRISE) |
| Archiviazione Exchange Online per Exchange Online \_ de (EXCHANGEARCHIVE \_ addon \_ de) | Archiviazione Exchange Online per Exchange Online (addon EXCHANGEARCHIVE \_ ) |
| Archiviazione Exchange Online per Exchange Server \_ de (EXCHANGEARCHIVE \_ de) | Archiviazione Exchange Online per Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ de (Exchange \_ S \_ Essentials \_ de) | Exchange Online Essentials (EXCHANGE \_ S \_ Essentials) |
| Exchange Online Kiosk \_ de (EXCHANGEDESKLESS \_ de) | Chiosco di Exchange Online (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ de (EOP \_ Enterprise \_ de) | Exchange Online Protection (EOP \_ Enterprise) |
| Microsoft 365 business standard (O365 \_ business \_ Premium) | Microsoft 365 business standard (O365 \_ business \_ Premium) |
| Istanza di Microsoft Dynamics CRM Online \_ de (CRMINSTANCE \_ de) | Istanza di Microsoft Dynamics CRM Online (CRMINSTANCE) |
| Office 365 a1 per i docenti \_ de (STANDARDWOFFPACK \_ facoltà \_ de) | Office 365 a1 per i docenti (facoltà di STANDARDWOFFPACK \_ ) |
| Office 365 a1 per studenti \_ de (STANDARDWOFFPACK \_ Student \_ de) | Office 365 a1 per gli studenti ( \_ allievo di STANDARDWOFFPACK) |
| Office 365 Advanced Compliance \_ de (EQUIVIO \_ Analytics \_ de) | Conformità Microsoft 365 E5 (conformità di protezione delle informazioni \_ \_ ) |
| Office 365 Advanced Threat Protection (piano 1) \_ de (ATP \_ Enterprise \_ de) | Office 365 Advanced Threat Protection (piano 1) (ATP \_ Enterprise) |
| Office 365 Business Essentials \_ de (O365 \_ business \_ Essentials \_ de) | Microsoft 365 Business Basic (O365 \_ business \_ Essentials) |
| Office 365 Business Premium \_ de (O365 \_ business \_ Premium \_ de) | Microsoft 365 business standard (O365 \_ business \_ Premium) |
| Office 365 business \_ de (O365 \_ business \_ de) | Microsoft 365 Apps for business (O365 \_ Business) |
| Office 365 E1 \_ de (STANDARDPACK \_ de) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 senza ProPlus \_ de (ENTERPRISEPACKWITHOUTPROPLUS \_ de) | Office 365 E3 senza ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ de (STANDARDPACK \_ de) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 extra file storage \_ de (SHAREPOINTSTORAGE \_ de) | Office 365 extra file storage (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ de (DESKLESSPACK \_ de) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus per i docenti \_ de (OFFICESUBSCRIPTION \_ facoltà \_ de) | Office 365 ProPlus per docenti ( \_ facoltà di OFFICESUBSCRIPTION) |
| Office 365 ProPlus for students \_ de (OFFICESUBSCRIPTION \_ Student \_ de) | Office 365 ProPlus for students ( \_ allievo di OFFICESUBSCRIPTION) |
| Office 365 ProPlus \_ de (OFFICESUBSCRIPTION \_ de) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive for business (piano 1) \_ de (WACONEDRIVESTANDARD \_ de) | OneDrive for business (piano 1) (WACONEDRIVESTANDARD) |
| OneDrive for business (piano 2) \_ de (WACONEDRIVEENTERPRISE \_ de) | OneDrive for business (piano 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro per i docenti \_ de (Power \_ bi \_ Pro \_ facoltà \_ de) | Power BI Pro per i docenti (POWER \_ bi \_ Pro \_ facoltà) |
| Power BI Pro \_ de (Power \_ bi \_ Pro \_ de) | Power BI Pro (POWER \_ bi \_ Pro) |
| Project Online Essentials \_ de (PROJECTESSENTIALS \_ de) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ de (PROJECTPREMIUM \_ de) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ de (PROJECTPROFESSIONAL \_ de) | Project Online Professional (PROJECTPROFESSIONAL) |
| Piano di progetto 3 \_ de (PROJECTPROFESSIONAL \_ de) | Piano di progetto 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ de (ENTERPRISEWITHSCAL \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (piano 1) \_ de (SHAREPOINTSTANDARD \_ de) | SharePoint Online (piano 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (piano 2) \_ de (SHAREPOINTENTERPRISE \_ de) | SharePoint Online (piano 2) (SHAREPOINTENTERPRISE) |
| Skype for business online (piano 1) \_ de (MCOIMP \_ de) | Office 365 E1 (STANDARDPACK) |
| Skype for business online (piano 1) \_ de (MCOIMP \_ de) | Skype for business online (piano 1) (MCOIMP) |
| Skype for business online (piano 2) \_ de (MCOSTANDARD \_ de) | Skype for business online (piano 2) (MCOSTANDARD) |
| Skype for Business Plus CAL \_ de (MCOPLUSCAL \_ de) | Skype for Business Plus CAL (MCOPLUSCAL) |
| Visio online piano 1 per i docenti \_ de (VISIOONLINE \_ PLAN1 \_ fac \_ de) | Visio online piano 1 per i docenti (VISIOONLINE \_ PLAN1 \_ fac) |
| Visio online piano 1 \_ de (VISIOONLINE \_ PLAN1 \_ de) | Visio online, piano 1 (VISIOONLINE \_ PLAN1) |
| Visio online piano 2 per i docenti \_ de (VISIOCLIENT \_ facoltà \_ de) | Visio online piano 2 per i docenti (facoltà di VISIOCLIENT \_ ) |
| Visio online piano 2 \_ de (VISIOCLIENT \_ de) | Visio online piano 2 (VISIOCLIENT) |
| Visio Plan 1 \_ de (VISIOONLINE \_ PLAN1 \_ de) | Visio piano 1 (VISIOONLINE \_ PLAN1) |
| Visio piano 2 \_ de (VISIOCLIENT \_ de) | Visio piano 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Come possono ottenere assistenza da Microsoft per la migrazione a una nuova area oppure le risposte alle domande relative al supporto?

In caso di domande, è possibile contattarci o contattare il partner:

- Per Azure, è possibile inviare le [nuove richieste di supporto](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) nel portale di Azure.
- Per Office 365, è possibile inviare domande utilizzando l'interfaccia &quot; &quot; di [amministrazione di Microsoft 365](https://portal.office.de/).
- Se si è clienti Dynamics 365 Customer Engagement and Power BI e anche Office 365, è possibile che vengano inviate domande utilizzando l'interfaccia &quot; &quot; di [amministrazione di Microsoft 365](https://portal.office.de/). Le opzioni di supporto per Dynamics 365 Customer Engagement sono disponibili [qui](https://docs.microsoft.com/dynamics365/get-started/support/). Le opzioni di supporto per Power BI sono disponibili [qui](https://powerbi.microsoft.com/support/).

## <a name="more-information"></a>Altre informazioni

Addizionale vengono fornite informazioni sulla migrazione alle nuove aree del datacenter tedesco. Bookmark questa pagina in modo che sia possibile archiviare e mantenere corrente.

- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](https://aka.ms/office365germanymoveoptin)
- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [URL e intervalli di indirizzi IP per Office 365](https://aka.ms/o365endpoints)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
