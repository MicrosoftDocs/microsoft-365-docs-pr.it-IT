---
title: 'Passaggio 3: Distribuire la gestione degli endpoint per dispositivi, PC e altri endpoint'
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
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
description: Usare Microsoft Endpoint Manager per gestire dispositivi, PC e altri endpoint.
ms.openlocfilehash: c7149295c24e5339e87db55998ec48fe9f0e9a93
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560494"
---
# <a name="step-3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>Passaggio 3: Distribuire la gestione degli endpoint per dispositivi, PC e altri endpoint

Con i lavoratori remoti, è necessario supportare un numero crescente di dispositivi personali. La gestione degli endpoint è un approccio alla sicurezza basato su criteri che richiede che i dispositivi siano conformi a criteri specifici prima che gli venga consentito l'accesso alle risorse. Microsoft Endpoint Manager offre strumenti moderni per la gestione che garantiscono la sicurezza dei dati sia nel cloud sia in locale. 

Endpoint Manager include servizi e strumenti che consentono di gestire dispositivi mobili, computer desktop, macchine virtuali, dispositivi incorporati e server combinando i servizi seguenti, probabilmente già noti e usati.

![I componenti per la gestione degli endpoint](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Intune è studiato per proteggere i dati quando non si gestiscono i dispositivi usati per accedere ai dati dell'organizzazione. I criteri di protezione delle app di Intune, combinati con l'accesso condizionale di Azure Active Directory (Azure AD) offrono un controllo granulare sui dati nei dispositivi mobili. Intune permette inoltre di definire criteri completi che consentono solo alle persone e nelle condizioni giuste di accedere ai dati aziendali e garantire la protezione dei dati controllando il modo in cui vengono utilizzati all'interno di Office, Outlook e di altre app per dispositivi mobili.

Per altre informazioni, vedere questa [panoramica di Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager è una soluzione di gestione locale per gestire desktop, server e computer portatili collegati nella rete aziendale o in Internet. È possibile abilitare la soluzione per il cloud e integrarla con Intune, Azure AD, Microsoft Defender ATP e altri servizi cloud. Usare Configuration Manager per distribuire app, aggiornamenti software e sistemi operativi. È anche possibile monitorare la conformità, eseguire query, intervenire sui client in tempo reale e molto altro ancora.

Per altre informazioni, vedere questa [panoramica di Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Co-gestione

La co-gestione integra l'investimento esistente in Configuration Manager locale con il cloud, tramite l'uso di Intune e di altri servizi cloud Microsoft 365. È possibile scegliere Configuration Manager o Intune come autorità di gestione per i sette diversi gruppi di carico di lavoro.

Nel contesto di Endpoint Manager la co-gestione usa funzionalità cloud, incluso l'accesso condizionale. Alcune attività restano in locale, mentre altre vengono eseguite nel cloud con Intune.

Per altre informazioni, vedere questa [panoramica della co-gestione](https://docs.microsoft.com/mem/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics è un servizio basato sul cloud che si integra con Configuration Manager e fornisce dati analitici e intelligence utili per prendere decisioni informate sui client Windows. Combina i dati dell'organizzazione con i dati aggregati di milioni di dispositivi connessi ai servizi cloud Microsoft. Con Desktop Analytics è possibile creare un inventario delle app in esecuzione nell'organizzazione, valutare la compatibilità delle app con gli ultimi aggiornamenti delle funzionalità di Windows 10, identificare i problemi di compatibilità e ricevere suggerimenti sulla mitigazione in base alle informazioni dettagliate sui dati abilitati per il cloud, creare gruppi pilota che rappresentino lo stato complessivo dell'applicazione e dei driver in un set minimo di dispositivi e distribuire Windows 10 a dispositivi pilota e gestiti dalla produzione.

Per altre informazioni, vedere questa [panoramica di Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview).

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot è una piattaforma per la distribuzione di Windows in modalità self-service con gestione automatizzata. Include una raccolta di tecnologie usate per impostare e preconfigurare nuovi dispositivi, preparandoli per l'uso. È anche possibile usare Windows Autopilot per reimpostare, riconfigurare e ripristinare i dispositivi. Questa soluzione consente al reparto IT di ottenere quanto descritto sopra gestendo poche infrastrutture o persino nessuna, con un processo semplice e immediato. Dal punto di vista dell'utente, bastano poche semplici operazioni per rendere il proprio dispositivo pronto per l'uso. Dal punto di vista dell'IT, l'unica interazione richiesta all'utente finale consiste nel connettersi a una rete e verificare le credenziali.

Per altre informazioni, vedere questa [panoramica di Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Risorse amministrative tecniche per la gestione degli endpoint

- [Il video parte 3 sulla gestione dei dispositivi Windows 10 per i lavoratori remoti](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [Il video parte 5 sulla gestione dei desktop e browser dell'utente per lavoratori remoti](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [Distribuzione di un'infrastruttura di mobilità per Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [Come registrare tipi diversi di dispositivi per la gestione di dispositivi mobili](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [Come formare gli utenti finali su Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a>Risultati del Passaggio 3

Si usano le caratteristiche e le funzionalità di Endpoint Manager per gestire dispositivi mobili, computer desktop, macchine virtuali dispositivi incorporati e server.

## <a name="next-step"></a>Passaggio successivo

Proseguire con [Passaggio 4](empower-people-to-work-remotely-teams-productivity-apps.md) per fornire l'accesso remoto alle app e ai servizi locali.
