---
title: Cosa cambia dopo la migrazione ai servizi Office 365 nelle nuove aree data center tedesche
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
description: 'Riepilogo: informazioni su cosa è cambiato per il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) a Office 365 servizi nella nuova area data center tedesca.'
ms.openlocfilehash: e503df16cfdbe0985e635b07cb6b4a45bc55d367
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930404"
---
# <a name="what-will-change-after-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Cosa cambia dopo la migrazione ai servizi Office 365 nelle nuove aree data center tedesche

Le migrazioni tenant sono progettate per avere un effetto minimo su amministratori e utenti. Esistono tuttavia alcune considerazioni su ciascun carico di lavoro. Leggere le sezioni seguenti per comprendere meglio l'esperienza di migrazione per i carichi di lavoro.

Di seguito sono riportate le differenze principali tra Microsoft Cloud Deutschland e i servizi Office 365 nelle nuove aree data center tedesche.

| Categoria | Microsoft Cloud Germania (Microsoft Cloud Deutschland) | I servizi di Office 365 nelle nuove aree data center tedesche |
|:-------|:-----|:-------|
| Servizi Microsoft 365 disponibili per la sottoscrizione a un solo tenant di Office 365 | 15 servizi | 29 servizi <br><br> Per ulteriori informazioni, vedere Qual è la disponibilità del servizio tra le diverse Office 365 offerte di servizi [cloud?](ms-cloud-germany-transition.md#serv-avail). |
| Nuove funzionalità | Non saranno disponibili nuove funzionalità. | Saranno disponibili nuove funzionalità coerenti con Office 365 servizi. |
| Trustee dei dati | Sì | No |
| Collaborazione tra il tenant e i tenant globali di Office 365 | No | Sì |
| Residenza dei dati dei clienti | I dati dei clienti verranno archiviati esclusivamente all'interno dei data center tedeschi. | Microsoft archivierà i seguenti dati dei clienti in pausa esclusivamente in Germania: <ul><li> Exchange Online della cassetta postale (corpo della posta elettronica, voci del calendario e contenuto degli allegati di posta elettronica) </li><li> SharePoint Contenuto del sito online e file archiviati in tale sito e file caricati in OneDrive for Business </li></ul> |
| Condizioni applicabili | [Condizioni per i Servizi online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) con questo [supplemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Condizioni dei Servizi online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

Cosa non cambia:

- Il dominio iniziale del tenant (ad esempio `contoso.onmicrosoft.de` ) con ID tenant (GUID) e domini personalizzati verrà mantenuto dopo la migrazione. 

- Le richieste di autenticazione per le risorse migrate nei Office 365 vengono concesse dal servizio Office 365 servizi di autenticazione di Azure ( `login.microsoftonline.com` ). Durante la migrazione, le risorse che rimangono ancora in Office 365 Germania vengono autenticate dal servizio Azure germania esistente ( `login.microsoftonline.de` ).

Considerazioni da tenere presente:

- Per gli account di dominio gestiti, al termine della copia del tenant di Azure Active Directory (Azure AD) iniziale (che è il primo passaggio della migrazione di Azure AD al servizio azure AD dei servizi Office 365), le modifiche delle password, la reimpostazione della password self-service (SSPR) e le reimpostazioni delle password da parte degli amministratori devono essere eseguite dai portali del servizio Office 365. Le richieste di aggiornamento delle password dal servizio Germania non hanno esito positivo a questo punto, perché il tenant di Azure AD è stato migrato a Office 365 servizi. Le reimpostazioni delle password dei domini federati non sono interessate, perché vengono completate nella directory locale.

- Gli accessi di Azure vengono presentati nel portale in cui l'utente tenta di accedere. I log di controllo sono disponibili solo dall'endpoint Office 365 services dopo la transizione. Prima di eseguire la migrazione fino al completamento della migrazione, è consigliabile salvare i log di accesso e di controllo dal portale di Microsoft Cloud Deutschland.

- Le reimpostazioni delle password, le modifiche delle password, la reimpostazione della password da parte di un amministratore per le organizzazioni gestite (che non utilizzano Active Directory Federation Services) devono essere eseguite tramite il portale Office 365 Services. I tentativi degli utenti che accedono ai portali di Microsoft Cloud Deutschland di reimpostare le password avranno esito negativo.

- Le richieste DSR (General Data Protection Regulation) (GDPR) vengono eseguite dal portale di amministrazione di Azure Office 365 services per le richieste future. Tutti i dati di diagnostica legacy o non dei clienti residenti in Microsoft Cloud Deutschland vengono eliminati entro o prima di 30 giorni.

## <a name="subscriptions--licenses"></a>Sottoscrizioni & licenze

- Office 365 e Dynamics da Microsoft Cloud Deutschland vengono transizione all'area tedesca con la ricollocazione di Azure AD. L'organizzazione viene quindi aggiornata per riflettere le nuove sottoscrizioni Office 365 services. Durante il breve processo di trasferimento della sottoscrizione, le modifiche apportate alle sottoscrizioni vengono bloccate.

- Quando il tenant viene transizione ai Office 365, le sue sottoscrizioni e licenze specifiche per la Germania sono standardizzate con nuove Office 365 offerte di servizi. Le sottoscrizioni Office 365 servizi di assistenza vengono acquistate per le sottoscrizioni germania trasferite. Agli utenti che dispongono di licenze germania verranno assegnate Office 365 licenze dei servizi. Al termine, le sottoscrizioni germania legacy vengono annullate e rimosse dal tenant Office 365 services.

- Dopo la migrazione dei singoli carichi di lavoro, le funzionalità aggiuntive vengono rese disponibili tramite i servizi di Office 365 (ad esempio Microsoft Planner e Microsoft Flow) a causa delle nuove sottoscrizioni Office 365 Services. Se appropriato per l'organizzazione, il tenant o l'amministratore delle licenze può disabilitare i nuovi piani di servizio durante la pianificazione della gestione delle modifiche per introdurre i nuovi servizi. Per istruzioni su come disabilitare i piani di servizio assegnati alle licenze degli utenti, vedere [Disable access to Microsoft 365 services while assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

## <a name="exchange-online"></a>Exchange Online

- Exchange gli URL delle risorse passano dall'endpoint Germania legacy `outlook.office.de` all'endpoint Office 365 services dopo la `outlook.office365.com` migrazione. Gli utenti possono accedere alla cassetta postale migrata utilizzando l'URL legacy fino al completamento della migrazione. I clienti devono eseguire la transizione degli utenti al nuovo URL il prima possibile dopo Exchange la migrazione per evitare di influire sul ritiro dell'ambiente Germania. Gli URL Office 365 servizi di Outlook diventano disponibili solo dopo l'inizio Exchange migrazione.

- Le cassette postali vengono migrate come processo back-end. Gli utenti dell'organizzazione possono essere in Microsoft Cloud Deutschland o nell'area tedesca durante la transizione e fanno parte della stessa organizzazione Exchange (nello stesso elenco indirizzi globale).

- Gli utenti del Outlook Web App che accedono al servizio utilizzando un URL in cui la cassetta postale non risiede, verrà visualizzata una richiesta di autenticazione aggiuntiva. Ad esempio, se la cassetta postale dell'utente si trova nei servizi Office 365 e la connessione Outlook Web App dell'utente utilizza l'endpoint legacy, l'utente eseguirà prima l'autenticazione in e quindi `outlook.office.de` `login.microsoftonline.de` in `login.microsoftonline.com` . Al termine della migrazione, l'utente può accedere al nuovo URL ( ) e verrà visualizzata solo la singola richiesta di `https://outlook.office365.com` accesso prevista. 

## <a name="sharepoint-online"></a>SharePoint Online

In SharePoint Online e OneDrive for Business, è possibile condividere elementi tramite Outlook. Dopo aver premuto il Outlook, viene creato un collegamento condivisibile e inserito in un nuovo messaggio nel Outlook Web App.

La condivisione di elementi in SharePoint Online e OneDrive for Business tramite Outlook non funziona più dopo il completamento della migrazione di SharePoint Online. Riconosciamo che si tratta di un problema noto. Tuttavia, poiché questa Outlook è nel percorso della deprecazione, la correzione del problema non è pianificata fino all'implementazione della deprecazione.

## <a name="office-services"></a>Office Servizi

Office I servizi online sono accessibili tramite `office.de` prima e durante la transizione. Dopo la transizione delle cassette postali degli utenti ai servizi Office 365, gli utenti devono iniziare a utilizzare Office 365 URL dei servizi. Quando i carichi di lavoro successivi vengono migrati Office 365 servizi, la loro interfaccia dal portale office.com inizierà a funzionare.

L'ultimo servizio usato (MRU) in Office è un cutover da Microsoft Cloud Deutschland a Office 365 servizi globali, non una migrazione. Dopo la migrazione dal portale Office 365 Office.com, saranno visibili solo i collegamenti MRU dal lato dei servizi globali. I collegamenti MRU da Microsoft Cloud Deutschland non sono visibili come collegamenti MRU nei Office 365 globali. In Office 365 servizi globali, i collegamenti MRU sono accessibili solo dopo che la migrazione del tenant ha raggiunto la fase 9.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Le funzionalità di Exchange Online Protection back-end (EOP) vengono copiate nella nuova area geografica germania.
- Office 365 Gli utenti del Centro sicurezza e conformità devono passare all'utilizzo di URL globali, `https://protection.office.com` , come parte della migrazione.

## <a name="skype-for-business-online"></a>Skype for Business Online

I clienti esistenti di Skype for Business online verranno trasferiti a Microsoft Teams. Per ulteriori informazioni, vedere [https://aka.ms/SkypeToTeams-Home](/microsoftteams/upgrade-start-here) .

## <a name="office-365-video"></a>Office 365 Video

Office 365 Il video verrà ritirato il 1° marzo 2021 e Office 365 Video non sarà supportato dopo il completamento della migrazione di SharePoint Online alle nuove aree data center tedesche. Il contenuto di Office 365 Video verrà migrato come parte della migrazione SharePoint Online. Tuttavia, i video in Office 365 Video non vengono riprodotti nell'interfaccia utente di Office 365 Video dopo la SharePoint migrazione. Altre informazioni sulla sequenza temporale della migrazione Office 365 panoramica della [transizione video a Microsoft Stream (classico).](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="next-step"></a>Passaggio successivo

[Comprendere le azioni e gli impatti delle fasi di migrazione](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)

Passaggio attraverso la transizione:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [ADFS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Informazioni sul programma di migrazione di Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](/microsoftteams/upgrade-start-here)
