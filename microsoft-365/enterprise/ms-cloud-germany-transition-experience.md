---
title: L'esperienza cliente durante la migrazione ai servizi di Office 365 nelle nuove aree data center tedesche
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: "Riepilogo: informazioni sull'esperienza di spostamento da Microsoft Cloud Germany (Microsoft Cloud Deutschland) a servizi di Office 365 nella nuova area datacenter tedesca."
ms.openlocfilehash: a44fbe504a9a710856deeb3baf258feb124ce7ae
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551696"
---
# <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>L'esperienza cliente durante la migrazione ai servizi di Office 365 nelle nuove aree data center tedesche

Le migrazioni tenant sono progettate in modo da avere un effetto minimo sugli amministratori e sugli utenti. Esistono tuttavia alcune considerazioni su ciascun carico di lavoro. Leggere le sezioni seguenti per una migliore comprensione dell'esperienza di migrazione per i carichi di lavoro.

Di seguito sono riportate le principali differenze tra Microsoft Cloud Deutschland e Office 365 Services nelle nuove aree del datacenter tedesco.

| Categoria | Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) | I servizi di Office 365 nelle nuove aree data center tedesche |
|:-------|:-----|:-------|
| Servizi Microsoft 365 disponibili per la sottoscrizione a un solo tenant di Office 365 | 15 servizi | 29 servizi <br><br> Per ulteriori informazioni, vedere [Qual è la disponibilità del servizio tra le diverse offerte di servizi cloud di Office 365?](ms-cloud-germany-transition.md#serv-avail). |
| Nuove funzionalità | Nessuna nuova funzionalità disponibile. | Le nuove funzionalità saranno disponibili in modo coerente con i servizi di Office 365. |
| Trustee dei dati | Sì | No |
| Collaborazione tra il tenant e i tenant globali di Office 365 | No | Sì |
| Residenza dei dati dei clienti | I dati dei clienti verranno archiviati esclusivamente all'interno dei data center tedeschi. | Microsoft memorizzerà i seguenti dati dei clienti a riposo esclusivamente in Germania: <ul><li> Contenuto delle cassette postali di Exchange Online (corpo del messaggio di posta elettronica, voci del calendario e contenuto degli allegati di posta elettronica) </li><li> Contenuto del sito di SharePoint Online e file archiviati all'interno del sito e file caricati in OneDrive for business </li></ul> |
| Condizioni applicabili | [Termini dei servizi online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) con questo [supplemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Condizioni dei Servizi online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

Cosa non cambia:

- Il dominio iniziale del tenant, ad esempio, `contoso.onmicrosoft.de` con ID tenant (Guid) e domini personalizzati persisterà dopo la migrazione. 

- Le richieste di autenticazione per le risorse di cui è stata eseguita la migrazione a Office 365 Services sono concesse dal servizio di autenticazione di Office 365 Services Azure ( `login.microsoftonline.com` ). Durante la migrazione, le risorse che rimangono ancora in Office 365 Germany vengono autenticate dal servizio di Azure in Germania esistente ( `login.microsoftonline.de` ).

Considerazioni da prendere in considerazione:

- Per gli account di dominio gestito, dopo la copia del tenant iniziale di Azure Active Directory (Azure AD) (che è il primo passaggio della migrazione di Azure ad al servizio di Azure AD di Office 365 Services), le modifiche alle password, le modifiche apportate alle password self-service (SSPR) e le reimpostazioni delle password da 365 parte degli amministratori devono essere eseguite dai portali di servizio di Le richieste di aggiornamento delle password dal servizio Germany non avranno esito positivo, in quanto il tenant di Azure AD è stato migrato ai servizi di Office 365. La reimpostazione delle password di dominio federato non è stata modificata, perché queste sono state completate nella directory locale.

- Gli accessi di Azure sono presentati nel portale in cui l'utente tenta di accedere. I registri di controllo sono disponibili solo dall'endpoint dei servizi di Office 365 dopo la transizione. Prima di eseguire la migrazione fino al completamento della migrazione, è consigliabile salvare i log di accesso e di controllo dal portale Microsoft Cloud Deutschland.

- Le reimpostazioni delle password, le modifiche alla password, la reimpostazione della password da parte di un amministratore per le organizzazioni gestite (che non utilizzano Active Directory Federation Services) devono essere eseguite tramite il portale dei servizi di Office 365. I tentativi degli utenti che accedono ai portali di Microsoft Cloud Deutschland per reimpostare le password avranno esito negativo.

- Le richieste del soggetto dei dati (richieste DSR) del regolamento generale sulla protezione dei dati (GDPR) vengono eseguite dal portale di amministrazione di Office 365 Services Azure per le richieste future. Tutti i dati di diagnostica legacy o non clienti che risiedono in Microsoft Cloud Deutschland vengono eliminati entro e non oltre 30 giorni.

## <a name="subscriptions--licenses"></a>Abbonamenti & licenze

- Le sottoscrizioni di Office 365 e Dynamics di Microsoft Cloud Deutschland sono state passate all'area tedesca con la rilocazione di Azure AD. L'organizzazione viene quindi aggiornata in modo da riflettere le nuove sottoscrizioni di servizi di Office 365. Durante il breve processo di trasferimento della sottoscrizione, le modifiche apportate agli abbonamenti vengono bloccate.

- Poiché il tenant viene inoltrato a servizi di Office 365, le relative sottoscrizioni e licenze specifiche per la Germania sono standardizzate con le nuove offerte di servizi di Office 365. Per gli abbonamenti a Germania trasferiti sono stati acquistati gli abbonamenti ai servizi di Office 365 corrispondenti. Agli utenti che dispongono di licenze tedesche verranno assegnate le licenze per i servizi di Office 365. Al termine, le sottoscrizioni legacy Germany vengono annullate e rimosse dal tenant corrente dei servizi di Office 365.

- Dopo la migrazione dei singoli carichi di lavoro, le funzionalità aggiuntive vengono rese disponibili tramite i servizi di Office 365 (ad esempio Microsoft Planner e Microsoft Flow) a causa delle nuove sottoscrizioni dei servizi di Office 365. Se appropriato per la propria organizzazione, il tenant o l'amministratore delle licenze può disabilitare i nuovi piani di servizio Man mano che si pianifica la gestione delle modifiche per introdurre i nuovi servizi. Per istruzioni su come disabilitare i piani di servizio assegnati alle licenze degli utenti, vedere [Disable access to Microsoft 365 Services while assigning User licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

## <a name="exchange-online"></a>Exchange Online

- Transizione degli URL delle risorse dall'endpoint legacy Germany `outlook.office.de` all'endpoint dei servizi di Office 365 `outlook.office365.com` dopo la migrazione. Gli utenti possono accedere alla propria cassetta postale migrata utilizzando l'URL legacy fino al completamento della migrazione. I clienti devono eseguire la transizione degli utenti al nuovo URL appena possibile dopo che la migrazione di Exchange ha iniziato a non influire sulla pensione dell'ambiente Germany. Gli URL dei servizi di Office 365 per i servizi Outlook diventano disponibili solo dopo l'avvio della migrazione di Exchange.

- Le cassette postali vengono migrate come processo back-end. Gli utenti dell'organizzazione possono trovarsi in Microsoft Cloud Deutschland o nell'area tedesca durante la transizione e fanno parte della stessa organizzazione di Exchange (nello stesso elenco indirizzi globale).

- Gli utenti di Outlook Web App che accedono al servizio utilizzando un URL in cui la cassetta postale non risiede vedranno un prompt di autenticazione supplementare. Ad esempio, se la cassetta postale dell'utente si trova nei servizi di Office 365 e la connessione Outlook Web App dell'utente utilizza l'endpoint legacy `outlook.office.de` , l'utente eseguirà prima l'autenticazione a `login.microsoftonline.de` e quindi a `login.microsoftonline.com` . Al termine della migrazione, l'utente può accedere al nuovo URL ( `https://outlook.office365.com` ) e vedrà solo la richiesta di accesso singola e prevista. 

## <a name="office-services"></a>Servizi di Office

I servizi Office Online sono accessibili tramite `office.de` prima e durante la transizione. Dopo che le cassette postali degli utenti sono state transizione ai servizi di Office 365, gli utenti devono iniziare a utilizzare gli URL dei servizi di Office 365. Dopo la migrazione dei carichi di lavoro successivi ai servizi di Office 365, l'interfaccia del portale di office.com inizierà a funzionare.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Le funzionalità di Exchange Online Protection (EOP) back-end vengono copiate nella nuova area di Germania.
- Gli utenti del Centro sicurezza e conformità di Office 365 devono passare all'utilizzo degli URL globali, `https://protection.office.com` come parte della migrazione.

## <a name="skype-for-business-online"></a>Skype for Business Online

I clienti esistenti di Skype for Business online verranno trasferiti a Microsoft Teams. Per ulteriori informazioni, vedere [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) .

## <a name="office-365-video"></a>Office 365 Video

Il video di Office 365 viene ritirato il 1 ° marzo 2021 e il video di Office 365 non è supportato dopo che è stata completata la migrazione di SharePoint Online alle nuove aree del datacenter tedesco. Il contenuto del video di Office 365 verrà migrato come parte della migrazione di SharePoint Online. Tuttavia, i video in Office 365 video non verranno riprodotti nell'interfaccia utente video di Office 365 dopo la migrazione di SharePoint. Per ulteriori informazioni sulla sequenza temporale della migrazione, vedere la [sezione transizione video di Office 365 a Microsoft Stream (Classic)](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="next-step"></a>Passaggio successivo

[Comprendere le operazioni e gli impatti delle fasi di migrazione](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)

Spostamento attraverso la transizione:

- [Operazioni e impatto delle fasi di migrazione](ms-cloud-germany-transition-phases.md)
- [Ulteriore prelavoro](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive su [Servizi](ms-cloud-germany-transition-add-general.md), [dispositivi](ms-cloud-germany-transition-add-devices.md), [esperienze](ms-cloud-germany-transition-add-experience.md)e [ad FS](ms-cloud-germany-transition-add-adfs.md).

App Cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
