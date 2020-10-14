---
title: Aumentare la produttività dei lavoratori remoti con Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: ''
description: Configurare le funzionalità di sicurezza e l'infrastruttura di servizio necessarie per consentire ai lavoratori di lavorare in remoto ovunque e in qualsiasi momento.
ms.openlocfilehash: 122df0f81200462f85d52985ccf3e42ce5d925f7
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446824"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Aumentare la produttività dei lavoratori remoti con Microsoft 365

L'azienda potrebbe dover consentire ai lavoratori di avere accesso sicuro alle informazioni, agli strumenti e alle risorse locali e basate sul cloud dalle proprie case. Per molte organizzazioni, consentire al personale di lavorare fuori dall’ufficio è importante per:

- Risparmiare spazio fisico.
- Assumere e trattenere dipendenti che non sono disposti al trasferimento.
- Ridurre il pendolarismo, lasciando così ai lavoratori più tempo per essere produttivi e ridurre lo stress.

Microsoft 365 offre funzionalità che consentono ai tuoi dipendenti di lavorare a distanza.

![Aumentare la produttività dei lavoratori remoti con Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

Guardare questo video per una panoramica del processo di distribuzione.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

Questa soluzione include queste funzionalità chiave.

- Connesso

  Da qualunque parte del mondo e in qualsiasi momento, i dipendenti che lavorano a distanza possono accedere a: 

  - Dati e servizi basati su cloud tramite la propria sottoscrizione a Microsoft 365. 
  - Risorse dell'organizzazione, ad esempio quelle offerte dai data center delle applicazioni locali.

- Protezione

  Gli accessi sono garantiti con l’autenticazione a più fattori (MFA), e le caratteristiche di sicurezza predefinite di Microsoft 365 e Windows 10 proteggono contro malware, attacchi dannosi e perdite dei dati.

- Gestione

  I dispositivi dei lavoratori remoti possono essere gestiti dal cloud tramite le impostazioni di sicurezza, le app consentite e la richiesta della conformità con i sistemi sanitari.

- Collaborazione e produttività

  I dipendenti che lavorano a distanza possono essere produttivi come quelli in ufficio in modi altamente collaborativi, tramite: 
  - Riunioni online e sessioni di chat con Teams. 
  - Aree di lavoro condivise per l’archiviazione di file basata su cloud, con l’accessibilità globale e la collaborazione in tempo reale di SharePoint e OneDrive.
  - Attività e flussi di lavoro condivisi per suddividere il lavoro e portare a termine le attività. 

Per un’esperienza di accesso senza soluzione di continuità, è necessario sincronizzare gli account utente locali di Active Directory Domain Services (AD DS) con Azure Active Directory (Azure AD). Per proteggere i dispositivi Windows 10, è necessario registrarli in Intune. Ecco una panoramica generale dell'infrastruttura.

![Infrastruttura di base per i lavoratori remoti con Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Per soddisfare i criteri per i lavoratori remoti, usare queste capacità e funzionalità di Microsoft 365.

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| MFA applicata con le impostazioni predefinite per la sicurezza   | Proteggere le identità e i dispositivi dalla compromissione richiedendo una seconda forma di autenticazione per gli accessi. Le impostazioni predefinite per la sicurezza richiedono l'autenticazione a più fattori per tutti gli account utente.   | Microsoft 365 E3 o E5 |
| MFA applicata con l'accesso condizionale| Richiedere l'autenticazione a più fattori in base alle proprietà dell'accesso con i criteri di accesso condizionale.    | Microsoft 365 E3 o E5 | 
| MFA applicata con l'accesso condizionale basato sul rischio   | Richiedere l'autenticazione a più fattori in base al rischio di accesso dell'utente con Azure Advanced Threat Protection. | Microsoft 365 E5 o E3 con licenze di Azure AD Premium P2 | 
| Reimpostazione della password self-service    | Consentire agli utenti di reimpostare o sbloccare le password o gli account personali.  | Microsoft 365 E3 o E5 |
| Azure AD Application Proxy    | Offrire un accesso remoto sicuro per le applicazioni basate sul Web ospitate nei server Intranet.   | Richiede una sottoscrizione di Azure a pagamento separata |
| VPN da punto a sito di Azure   | Stabilire una connessione sicura dal dispositivo di un lavoratore remoto alla Intranet aziendale tramite una rete virtuale di Azure.   | Richiede una sottoscrizione di Azure a pagamento separata |
| Desktop virtuale Windows   | Supportare i lavoratori remoti che possono usare solo i propri dispositivi personali e non gestiti con desktop virtuali in esecuzione in Azure. | Richiede una sottoscrizione di Azure a pagamento separata |
| Servizi Desktop remoto | Consentire ai dipendenti di connettersi a computer basati su Windows nella Intranet aziendale. | Microsoft 365 E3 o E5 | 
| Gateway di Servizi Desktop remoto   | Crittografare le comunicazioni e impedire che gli host RDS siano esposti direttamente a Internet. | Richiede licenze di Windows Server separate |
| Microsoft Intune | Gestire dispositivi e applicazioni.   | Microsoft 365 E3 o E5 | 
| Configuration Manager | Gestire installazioni, aggiornamenti e impostazioni del software nei dispositivi | Richiede licenze di Configuration Manager separate |
| Desktop Analytics | Determinare l'adozione degli aggiornamenti dei client Windows.   | Richiede licenze di Configuration Manager separate |
| Windows Autopilot | Impostare e preconfigurare nuovi dispositivi Windows 10 in modo da predisporli per l'uso.   | Microsoft 365 E3 o E5 |
| Microsoft Teams, Exchange Online, SharePoint Online e OneDrive, Microsoft 365 Apps, Microsoft Power Platform, Yammer, Power Apps | Creare, comunicare e collaborare. | Microsoft 365 E3 o E5 |
||||

Per i criteri di sicurezza e conformità, vedere [Distribuire sicurezza e conformità per i lavoratori remoti](empower-people-to-work-remotely-security-compliance.md).

<a name="poster"></a> Per un riepilogo di 2 pagine di questa soluzione, vedere il [poster Supportare i lavoratori remoti](../downloads/empower-remote-workers.pdf).

[![Poster Supportare i lavoratori remoti](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)

È anche possibile scaricare il poster in formato [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).

Utilizzare i seguenti passaggi per proteggere e ottimizzare l'accesso ai server, ai dati e ai servizi cloud dell'organizzazione e consentire la massima produttività dei lavoratori.

1. [Aumentare la sicurezza dell'accesso con la MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Fornire l'accesso remoto alle app e ai servizi locali](empower-people-to-work-remotely-remote-access.md)
3. [Distribuire servizi di sicurezza e conformità](empower-people-to-work-remotely-security-compliance.md)
4. [Distribuire la gestione degli endpoint per dispositivi, PC e altri endpoint](empower-people-to-work-remotely-manage-endpoints.md)
5. [Distribuire le app e i servizi per la produttività dei lavoratori remoti](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Formare i lavoratori remoti e rispondere al feedback sull'utilizzo](empower-people-to-work-remotely-train-monitor-usage.md)

[![Passaggi per aumentare la produttività dei lavoratori remoti con Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)

Per le ultime informazioni da Microsoft sul supporto dei lavoratori remoti, vedere la pagina sull'[abilitazione del lavoro remoto nel sito Microsoft Tech Community](https://resources.techcommunity.microsoft.com/enabling-remote-work/).
