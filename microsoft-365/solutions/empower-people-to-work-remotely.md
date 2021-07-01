---
title: Configurare l'infrastruttura per il lavoro ibrido con Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
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
ms.custom: seo-marvel-jun2020
keywords: lavorare da casa, lavoro da casa, ibrido, lavoratore remoto, lavoro ibrido, dipendenti remoti, connettività ibrida, accesso remoto, lavoro remoto, lavorare a distanza, telelavorare, lavoro in movimento, lavorare in remoto, lavorare ovunque, ambienti di lavoro flessibili
description: Esaminare i vari livelli dell'infrastruttura in modo che i lavoratori ibridi possano accedere in modo sicuro alle risorse locali e di Microsoft 365.
ms.openlocfilehash: fed23a4607cfb47049a6540dfb592d9a8baf9d21
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229372"
---
# <a name="set-up-your-infrastructure-for-hybrid-work-with-microsoft-365"></a>Configurare l'infrastruttura per il lavoro ibrido con Microsoft 365

Per proteggere e ottimizzare la produttività e la collaborazione dei lavoratori, è necessario consentire ai lavoratori in sede e da remoto di accedere in modo facile e sicuro alle informazioni, gli strumenti e le risorse locali e basate sul cloud dell'organizzazione. Questa soluzione illustra i passaggi per la distribuzione dei livelli chiave dell'infrastruttura che consentono ai dipendenti di lavorare al meglio, ovunque si trovino.

I lavoratori ibridi possono lavorare in sede o da remoto alternando le postazioni lavorative. Per molte organizzazioni, consentire al personale di lavorare al di fuori dell'ufficio tradizionale è importante per:

- Assumere e trattenere i lavoratori che non desiderano trasferirsi o necessitano di un ambiente di lavoro flessibile.
- Ridurre il pendolarismo, lasciando così ai lavoratori più tempo per essere produttivi e ridurre lo stress.
- Risparmiare spazio fisico.

Microsoft 365 offre funzionalità che consentono ai lavoratori ibridi di lavorare presso la sede o da remoto.

![Aumentare la produttività dei lavoratori ibridi con Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

> [!NOTE]
> Se sei un nuovo utente di Microsoft 365, vedi [queste risorse](https://www.microsoft.com/microsoft-365).

Guarda questo video per una panoramica sulla procedura di implementazione.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

Per i professionisti IT che gestiscono infrastrutture locali e basate su cloud per sostenere la produttività dei lavoratori ibridi, questa soluzione offre le seguenti funzionalità chiave:

- Connessione

  Da qualunque parte del mondo e in qualsiasi momento, i dipendenti possono accedere a:

  - Dati e servizi basati su cloud tramite la propria sottoscrizione a Microsoft 365.

  - Risorse dell'organizzazione, ad esempio quelle offerte dai data center delle applicazioni locali.

- Protezione

  Gli accessi sono garantiti con l’autenticazione a più fattori (MFA), e le caratteristiche di sicurezza predefinite di Microsoft 365 e Windows 10 proteggono contro malware, attacchi dannosi e perdite dei dati.

- Gestione

  I dispositivi dei lavoratori ibridi possono essere gestiti dal cloud tramite le impostazioni di sicurezza, le app consentite e la richiesta di conformità con l'integrità del sistema.

- Collaborazione e produttività

  I lavoratori ibridi che lavorano a distanza possono essere produttivi come quelli in ufficio in modi altamente collaborativi, tramite: 

  - Riunioni online e sessioni di chat con Teams.

  - Aree di lavoro condivise per l’archiviazione di file basata su cloud, con l’accessibilità globale e la collaborazione in tempo reale di SharePoint e OneDrive.

  - Attività e flussi di lavoro condivisi per suddividere il lavoro e portare a termine le attività.

Per un’esperienza di accesso senza soluzione di continuità, è necessario sincronizzare gli account utente locali di Active Directory Domain Services (AD DS) con Azure Active Directory (Azure AD). Per proteggere i dispositivi Windows 10, è necessario registrarli in Intune. Ecco una panoramica generale dell'infrastruttura.

![Infrastruttura di base per i lavoratori ibridi con Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Per abilitare le capacità di Microsoft 365 per i lavoratori ibridi, usare queste funzionalità di Microsoft 365.

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| MFA applicata con le impostazioni predefinite per la sicurezza   | Proteggere le identità e i dispositivi dalla compromissione richiedendo una seconda forma di autenticazione per gli accessi. Le impostazioni predefinite per la sicurezza richiedono l'autenticazione a più fattori per tutti gli account utente.   | Microsoft 365 E3 o E5 |
| MFA applicata con l'accesso condizionale| Richiedere l'autenticazione a più fattori in base alle proprietà dell'accesso con i criteri di accesso condizionale.    | Microsoft 365 E3 o E5 |
| MFA applicata con l'accesso condizionale basato sul rischio   | Richiedere l'autenticazione a più fattori in base al rischio di accesso dell'utente con Microsoft Defender per identità. | Microsoft 365 E5 o E3 con licenze di Azure AD Premium P2 |
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
| Microsoft Teams, Exchange Online, SharePoint Online e OneDrive, Microsoft 365 Apps, Microsoft Power Platform e Yammer | Creare, comunicare e collaborare. | Microsoft 365 E3 o E5 |
||||

Per i criteri di sicurezza e conformità, vedere [Distribuire sicurezza e conformità per i lavoratori remoti](empower-people-to-work-remotely-security-compliance.md).

<a name="poster"></a> Per un riepilogo di 2 pagine di questa soluzione, vedere il [poster Supportare i lavoratori ibridi](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf).

[![Poster Supportare i lavoratori ibridi](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)

È anche possibile scaricare il poster in formato [PowerPoint](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pptx) e stamparlo in formato lettera, legale o tabloid (27,9 x 43,2 cm).

## <a name="provide-hybrid-working-for-all-of-your-workers"></a>Consentire il lavoro ibrido a tutti.

Con i dispositivi seguenti i dipendenti possono rimanere produttivi ovunque:

- I dispositivi moderni, come Surface Laptop e Windows 10, che dispongono di funzionalità, sicurezza e prestazioni per accedere alle app e ai servizi cloud di Microsoft 365 direttamente sul Web.

- Tutti i dispositivi, tra cui dispositivi e desktop meno recenti usati da casa, che possono accedere alle app e ai servizi cloud di Microsoft 365 indirettamente tramite una distribuzione veloce di un [desktop virtuale basato su Windows 10](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices). Questa opzione offre prestazioni elevate, piena sicurezza e gestione IT semplificata.

## <a name="next-steps"></a>Passaggi successivi

Utilizzare la procedura seguente per proteggere e ottimizzare l'accesso ai server e ai servizi cloud dell'organizzazione e massimizzare la produttività dei dipendenti ibridi.

1. [Aumentare la sicurezza dell'accesso con la MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Fornire l'accesso remoto alle app e ai servizi locali](empower-people-to-work-remotely-remote-access.md)
3. [Distribuire servizi di sicurezza e conformità](empower-people-to-work-remotely-security-compliance.md)
4. [Distribuire la gestione degli endpoint per dispositivi, PC e altri endpoint](empower-people-to-work-remotely-manage-endpoints.md)
5. [Distribuire le app e i servizi per la produttività dei lavoratori ibridi](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Formare i lavoratori e rispondere al feedback sull'utilizzo](empower-people-to-work-remotely-train-monitor-usage.md)

[![La procedura per configurare l'infrastruttura per il lavoro ibrido con Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)

Per scoprire in che modo un'organizzazione multinazionale fittizia ma rappresentativa ha configurato la propria infrastruttura per il lavoro ibrido, vedere [Risposta al COVID-19 e infrastruttura per il lavoro ibrido di Contoso](contoso-remote-onsite-work.md).
