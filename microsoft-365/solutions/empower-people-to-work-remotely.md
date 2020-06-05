---
title: Aumentare la produttività dei lavoratori remoti con Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Configurare le funzionalità di sicurezza e l'infrastruttura di servizio necessarie per consentire ai lavoratori di lavorare in remoto ovunque e in qualsiasi momento.
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560463"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Aumentare la produttività dei lavoratori remoti con Microsoft 365

L'azienda potrebbe dover consentire ai lavoratori di avere accesso sicuro alle informazioni, agli strumenti e alle risorse locali e basate sul cloud dalle proprie case. Per molte organizzazioni, consentire al personale di lavorare facilmente e in sicurezza fuori dall'ufficio è importante per:

- Risparmiare spazio fisico.
- Assumere e trattenere dipendenti che non sono disposti al trasferimento.
- Ridurre il pendolarismo, lasciando così ai lavoratori più tempo per essere produttivi e ridurre lo stress.

Il lavoro remoto, o telelavoro, può includere uno spettro che include:

- Lavoratori che sono lontani dall'ufficio solo occasionalmente, per convegni o riunioni con i clienti.
- Alcuni lavoratori che lavorano da remoto a tempo pieno.
- Un'organizzazione completamente remota in cui non ci sono uffici e tutti sono telelavoratori.

Da qualunque parte del mondo e in qualsiasi momento, i lavoratori remoti devono poter accedere a:

- Risorse dell'organizzazione, ad esempio quelle offerte dai data center delle applicazioni locali.
- Dati e servizi basati sul cloud nell'abbonamento a Microsoft 365, come Teams, Exchange Online, SharePoint e OneDrive.

Per un'esperienza di accesso senza soluzione di continuità, è necessario sincronizzare gli account utente di Active Directory Domain Services (AD DS) con Azure Active Directory (Azure AD). Per proteggere i dispositivi Windows 10, è necessario registrarli in Intune. Ecco una panoramica generale dell'infrastruttura.

![Infrastruttura di base per i lavoratori remoti con Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


Per supportare i lavoratori remoti, ad esempio in risposta all'emergenza COVID-19, Microsoft 365 offre una serie di funzionalità che consentono di collaborare in modo estremamente semplice da remoto, ad esempio:

- Riunioni online e sessioni di chat.
- Aree di lavoro condivise per l'archiviazione di file basata sul cloud, con accessibilità globale e collaborazione in tempo reale.
- Attività e flussi di lavoro condivisi per dividere il lavoro e portare a termine le attività.

Per la massima sicurezza, Microsoft 365 include:

- Applicazione di requisiti di autenticazione, con rilevamento e risposta agli accessi ad alto rischio e blocco di app selezionate e dispositivi non conformi.
- Connessioni crittografate e risorse digitali nel cloud.
- Autorizzazioni per definire le operazioni che possono essere eseguite da ciascun utente sui file.
- Funzionalità di sicurezza complete per proteggere i dispositivi Windows 10.

Per soddisfare questi criteri per i lavoratori remoti, usare queste capacità e funzionalità di Microsoft 365.

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| MFA applicata con le impostazioni predefinite per la sicurezza   | Proteggere le identità e i dispositivi dalla compromissione richiedendo una seconda forma di autenticazione per gli accessi. Le impostazioni predefinite per la sicurezza richiedono l'autenticazione a più fattori per tutti gli account utente.   | Microsoft 365 E3 ed E5 |
| MFA applicata con l'accesso condizionale| Richiedere l'autenticazione a più fattori in base alle proprietà dell'accesso con i criteri di accesso condizionale.    | Microsoft 365 E3 ed E5 | 
| MFA applicata con l'accesso condizionale basato sul rischio   | Richiedere l'autenticazione a più fattori in base al rischio di accesso dell'utente con Azure Advanced Threat Protection. | Microsoft 365 E5 o E3 con licenze di Azure AD Premium P2 | 
| Reimpostazione della password self-service    | Consentire agli utenti di reimpostare o sbloccare le password o gli account personali.  | Microsoft 365 E3 ed E5 |
| Azure AD Application Proxy    | Offrire un accesso remoto sicuro per le applicazioni basate sul Web ospitate nei server Intranet.   | Richiede una sottoscrizione di Azure a pagamento separata |
| VPN da punto a sito di Azure   | Stabilire una connessione sicura dal dispositivo di un lavoratore remoto alla Intranet aziendale tramite una rete virtuale di Azure.   | Richiede una sottoscrizione di Azure a pagamento separata |
| Desktop virtuale Windows   | Supportare i lavoratori remoti che possono usare solo i propri dispositivi personali e non gestiti con desktop virtuali in esecuzione in Azure. | Richiede una sottoscrizione di Azure a pagamento separata |
| Servizi Desktop remoto | Consentire ai dipendenti di connettersi a computer basati su Windows nella Intranet aziendale. | Microsoft 365 E3 ed E5 | 
| Gateway di Servizi Desktop remoto   | Crittografare le comunicazioni e impedire che gli host RDS siano esposti direttamente a Internet. | Richiede licenze di Windows Server separate |
| Microsoft Intune | Gestire dispositivi e applicazioni.   | Microsoft 365 E3 ed E5 | 
| Configuration Manager | Gestire installazioni, aggiornamenti e impostazioni del software nei dispositivi | Richiede licenze di Configuration Manager separate |
| Desktop Analytics | Determinare l'adozione degli aggiornamenti dei client Windows.   | Richiede licenze di Configuration Manager separate |
| Windows Autopilot | Impostare e preconfigurare nuovi dispositivi Windows 10 in modo da predisporli per l'uso.   | Microsoft 365 E3 ed E5 |
| Microsoft Teams, Exchange Online, SharePoint Online e OneDrive, Microsoft 365 Apps, Microsoft Power Platform, Yammer, Power Apps | Creare, comunicare e collaborare. | Microsoft 365 E3 ed E5 |
||||

Utilizzare i seguenti passaggi per proteggere e ottimizzare l'accesso ai server, ai dati e ai servizi cloud dell'organizzazione e consentire la massima produttività dei lavoratori.

1. [Aumentare la sicurezza dell'accesso con la MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Fornire l'accesso remoto alle app e ai servizi locali](empower-people-to-work-remotely-remote-access.md)
3. [Distribuire la gestione degli endpoint per dispositivi, PC e altri endpoint](empower-people-to-work-remotely-manage-endpoints.md)
4. [Distribuire le app e i servizi per la produttività dei lavoratori remoti](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [Creare spazi di comunicazione](empower-people-to-work-remotely-communication-venues.md)
6. [Formare i lavoratori remoti e rispondere al feedback sull'utilizzo](empower-people-to-work-remotely-train-monitor-usage.md)

![Passaggi per aumentare la produttività dei lavoratori remoti con Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

Per le ultime informazioni da Microsoft sul supporto dei lavoratori remoti, vedere la pagina sull'[abilitazione del lavoro remoto nel sito Microsoft Tech Community](https://resources.techcommunity.microsoft.com/enabling-remote-work/).
