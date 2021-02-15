---
title: Modifiche per la migrazione ai servizi di Office 365 nelle nuove aree data center tedesche
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: 'Riepilogo: informazioni su cosa è cambiato per il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area data center tedesca.'
ms.openlocfilehash: 0415f7b95cb9a9f2625798311946dac0f1f7c2c0
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688623"
---
# <a name="what-has-changed-for-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Modifiche per la migrazione ai servizi di Office 365 nelle nuove aree data center tedesche

Le migrazioni tenant sono progettate per avere un effetto minimo su amministratori e utenti. Esistono tuttavia alcune considerazioni su ciascun carico di lavoro. Leggere le sezioni seguenti per comprendere meglio l'esperienza di migrazione per i carichi di lavoro.

Di seguito sono riportate le differenze principali tra Microsoft Cloud Deutschland e i servizi di Office 365 nelle nuove aree data center tedesche.

| Categoria | Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) | I servizi di Office 365 nelle nuove aree data center tedesche |
|:-------|:-----|:-------|
| Servizi Microsoft 365 disponibili per la sottoscrizione a un solo tenant di Office 365 | 15 servizi | 29 servizi <br><br> Per ulteriori informazioni, vedere Qual è la disponibilità del servizio tra le diverse offerte di servizi cloud di [Office 365?](ms-cloud-germany-transition.md#serv-avail). |
| Nuove funzionalità | Nessuna nuova funzionalità disponibile. | Le nuove funzionalità saranno disponibili in modo coerente con i servizi di Office 365. |
| Trustee dei dati | Sì | No |
| Collaborazione tra il tenant e i tenant globali di Office 365 | No | Sì |
| Residenza dei dati dei clienti | I dati dei clienti verranno archiviati esclusivamente all'interno dei data center tedeschi. | Microsoft archivierà i dati dei clienti seguenti esclusivamente in Germania: <ul><li> Contenuto della cassetta postale di Exchange Online (corpo del messaggio di posta elettronica, voci del calendario e contenuto degli allegati di posta elettronica) </li><li> Contenuto del sito di SharePoint Online, file archiviati all'interno del sito e file caricati in OneDrive for Business </li></ul> |
| Condizioni applicabili | [Condizioni dei Servizi online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) con questo [supplemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Condizioni dei Servizi online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

Cosa non cambia:

- Il dominio iniziale del tenant (ad `contoso.onmicrosoft.de` esempio) con ID tenant (GUID) e domini personalizzati verrà mantenuto dopo la migrazione. 

- Le richieste di autenticazione per le risorse migrate ai servizi di Office 365 vengono concesse dal servizio di autenticazione di Azure dei servizi di Office 365 ( `login.microsoftonline.com` ). Durante la migrazione, le risorse che rimangono ancora in Office 365 Germany vengono autenticate dal servizio Azure per la Germania esistente ( `login.microsoftonline.de` ).

Considerazioni da tenere presente:

- Per gli account di dominio gestito, dopo aver copiato il tenant iniziale di Azure Active Directory (Azure AD) è stato completato (che è il primo passaggio della migrazione di Azure AD al servizio Azure AD dei servizi di Office 365), le modifiche delle password, le modifiche della reimpostazione della password self-service (SSPR) e le reimpostazioni delle password da parte degli amministratori devono essere eseguite dai portali dei servizi di Office 365. Le richieste di aggiornamento delle password dal servizio Germania non hanno esito positivo a questo punto, perché il tenant di Azure AD è stato migrato ai servizi di Office 365. Le reimpostazioni delle password dei domini federati non sono interessate, perché vengono completate nella directory locale.

- Gli accessi di Azure vengono presentati nel portale in cui l'utente tenta di accedere. I log di controllo sono disponibili solo dall'endpoint dei servizi di Office 365 dopo la transizione. Prima di eseguire la migrazione fino al completamento della migrazione, è consigliabile salvare i log di accesso e di controllo dal portale di Microsoft Cloud Deutschland.

- Le reimpostazioni delle password, le modifiche delle password, la reimpostazione della password da parte di un amministratore per le organizzazioni gestite (che non utilizzano Active Directory Federation Services) devono essere eseguite tramite il portale dei servizi di Office 365. I tentativi degli utenti che accedono ai portali di Microsoft Cloud Deutschland di reimpostare le password avranno esito negativo.

- Le richieste DSR (Data Subject Requests) del Regolamento generale sulla protezione dei dati (GDPR) vengono eseguite dal portale di amministrazione di Azure dei servizi di Office 365 per le richieste future. Tutti i dati di diagnostica legacy o non dei clienti residenti in Microsoft Cloud Deutschland vengono eliminati entro 30 giorni.

## <a name="subscriptions--licenses"></a>Sottoscrizioni & licenze

- Gli abbonamenti a Office 365 e Dynamics da Microsoft Cloud Deutschland vengono transitati nell'area tedesca con il trasferimento di Azure AD. L'organizzazione viene quindi aggiornata per riflettere i nuovi abbonamenti ai servizi di Office 365. Durante il breve processo di trasferimento della sottoscrizione, le modifiche apportate alle sottoscrizioni vengono bloccate.

- Durante la transizione del tenant ai servizi di Office 365, le sottoscrizioni e le licenze specifiche per la Germania sono standardizzate con nuove offerte di servizi di Office 365. Le sottoscrizioni ai servizi di Office 365 corrispondenti vengono acquistate per gli abbonamenti in Germania trasferiti. Agli utenti che dispongono di licenze germania verranno assegnate le licenze dei servizi di Office 365. Al termine, le sottoscrizioni germania legacy vengono annullate e rimosse dal tenant dei servizi di Office 365 corrente.

- Dopo la migrazione dei singoli carichi di lavoro, le funzionalità aggiuntive vengono rese disponibili tramite i servizi di Office 365 (ad esempio Microsoft Planner e Microsoft Flow) a causa dei nuovi abbonamenti ai servizi di Office 365. Se appropriato per l'organizzazione, l'amministratore del tenant o delle licenze può disabilitare i nuovi piani di servizio durante la pianificazione della gestione delle modifiche per introdurre i nuovi servizi. Per indicazioni su come disabilitare i piani di servizio assegnati alle licenze degli utenti, vedere Disabilitare l'accesso ai servizi di [Microsoft 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)durante l'assegnazione delle licenze utente.

## <a name="exchange-online"></a>Exchange Online

- Gli URL delle risorse di Exchange passano dall'endpoint germania legacy `outlook.office.de` all'endpoint dei servizi di Office 365 dopo la `outlook.office365.com` migrazione. Gli utenti possono accedere alla cassetta postale migrata utilizzando l'URL legacy fino al completamento della migrazione. I clienti devono eseguire la transizione degli utenti al nuovo URL il prima possibile dopo l'inizio della migrazione di Exchange per evitare effetti sul ritiro dell'ambiente germania. Gli URL dei servizi di Office 365 per i servizi outlook diventano disponibili solo dopo l'inizio della migrazione di Exchange.

- Le cassette postali vengono migrate come processo back-end. Gli utenti dell'organizzazione possono essere in Microsoft Cloud Deutschland o nell'area tedesca durante la transizione e fanno parte della stessa organizzazione di Exchange (nello stesso elenco indirizzi globale).

- Agli utenti di Outlook Web App che accedono al servizio utilizzando un URL in cui la cassetta postale non risiede verrà visualizzata una richiesta di autenticazione aggiuntiva. Ad esempio, se la cassetta postale dell'utente si trova nei servizi di Office 365 e la connessione di Outlook Web App dell'utente utilizza l'endpoint legacy, l'utente eseguirà prima l'autenticazione in e quindi `outlook.office.de` `login.microsoftonline.de` in `login.microsoftonline.com` . Al termine della migrazione, l'utente può accedere al nuovo URL ( ) e potrà visualizzare solo la singola richiesta di accesso `https://outlook.office365.com` prevista. 

## <a name="office-services"></a>Servizi di Office

I servizi Office Online sono accessibili tramite `office.de` prima e durante la transizione. Dopo la transizione delle cassette postali degli utenti ai servizi di Office 365, gli utenti devono iniziare a usare gli URL dei servizi di Office 365. Quando i carichi di lavoro successivi vengono migrati ai servizi di Office 365, la loro interfaccia dal portale office.com inizierà a funzionare.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Le funzionalità di Exchange Online Protection (EOP) back-end vengono copiate nella nuova area geografica germania.
- Gli utenti del Centro sicurezza e conformità di Office 365 devono passare all'uso degli URL `https://protection.office.com` globali, come parte della migrazione.

## <a name="skype-for-business-online"></a>Skype for Business Online

I clienti esistenti di Skype for Business online verranno trasferiti a Microsoft Teams. Per ulteriori informazioni, vedere [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) .

## <a name="office-365-video"></a>Office 365 Video

Office 365 Video verrà ritirato il 1° marzo 2021 e Office 365 Video non sarà supportato dopo il completamento della migrazione di SharePoint Online alle nuove aree data center tedesche. Il contenuto di Office 365 Video verrà migrato come parte della migrazione di SharePoint Online. Tuttavia, i video in Office 365 Video non vengono riprodotti nell'interfaccia utente di Office 365 Video dopo la migrazione di SharePoint. Ulteriori informazioni sulla sequenza temporale della migrazione nella panoramica della transizione di [Office 365 Video a Microsoft Stream (classico).](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="next-step"></a>Passaggio successivo

[Comprendere le azioni e gli impatti delle fasi di migrazione](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland ai servizi di Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)

Spostamento attraverso la transizione:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Ulteriori informazioni per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [AD FS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
