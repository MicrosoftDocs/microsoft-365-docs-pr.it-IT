---
title: Passaggio 4. Distribuire la gestione degli endpoint per dispositivi, PC e altri endpoint
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
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
- m365solution-scenario
ms.custom: ''
description: Usare Microsoft Endpoint Manager per gestire dispositivi, PC e altri endpoint.
ms.openlocfilehash: 116f2a92ccae43a36a8a4ceafcd598c532a852c3
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028993"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>Passaggio 4. Distribuire la gestione degli endpoint per dispositivi, PC e altri endpoint

Con i lavoratori remoti, è necessario supportare un numero crescente di dispositivi personali. La gestione degli endpoint è un approccio alla sicurezza basato su criteri che richiede che i dispositivi siano conformi a criteri specifici prima che gli venga consentito l'accesso alle risorse. Microsoft Endpoint Manager offre strumenti moderni per la gestione che garantiscono la sicurezza dei dati sia nel cloud sia in locale. 

[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) include servizi e strumenti che consentono di gestire dispositivi mobili, computer desktop, macchine virtuali, dispositivi incorporati e server combinando i servizi seguenti, probabilmente già noti e usati.

![Componenti di gestione degli endpoint per Microsoft 365](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune è un servizio basato sul cloud che è incentrato sulla gestione di dispositivi mobili (MDM) e sulla gestione di applicazioni mobili (MAM) incluso in Microsoft 365. 

- **MDM:** per i dispositivi di proprietà dell'organizzazione, è possibile esercitare un controllo completo che include impostazioni, caratteristiche e sicurezza. I dispositivi sono "registrati" in Intune, dove ricevono criteri di Intune con regole e impostazioni. Ad esempio, è possibile impostare PIN e password, creare una connessione VPN, configurare la protezione contro le minacce e così via.

- **MAM:** i lavoratori remoti potrebbero non voler concedere il controllo completo sui propri dispositivi personali, noti anche come dispositivi di BYOD (bring-your-own). È possibile fornire opzioni ai lavoratori remoti e continuare a proteggere l'organizzazione. Ad esempio, i lavoratori remoti possono registrare i propri dispositivi, per avere accesso completo alle risorse dell'organizzazione. In alternativa, se desiderano accedere solo alla posta elettronica o a Microsoft Teams, gli utenti possono usare i criteri di protezione delle app che richiedono l'autenticazione a più fattori (MFA) per l'uso di queste app.

Per altre informazioni, vedere questa [panoramica di Microsoft Intune](/intune/fundamentals/what-is-intune).

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager è una soluzione di gestione locale per gestire desktop, server e computer portatili collegati nella rete aziendale o in Internet. Usare Configuration Manager per distribuire app, aggiornamenti software e sistemi operativi. È anche possibile monitorare la conformità, eseguire query, intervenire sui client in tempo reale e molto altro ancora. È possibile abilitare la soluzione per il cloud e integrarla con Intune, Azure AD, Microsoft Defender per endpoint e altri servizi cloud. 

Per altre informazioni, vedere questa [panoramica di Configuration Manager](/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Co-gestione

La co-gestione integra l'investimento esistente in Configuration Manager locale con il cloud, tramite l'uso di Intune e di altri servizi cloud Microsoft 365. È possibile scegliere Configuration Manager o Intune come autorità di gestione per carichi di lavoro diversi. 

La co-gestione usa funzionalità cloud basate su Intune, tra cui l'accesso condizionale e l'applicazione della conformità del dispositivo. Alcune attività restano in locale, mentre altre vengono eseguite nel cloud.

Per altre informazioni, vedere questa [panoramica della co-gestione](/mem/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics è un servizio basato sul cloud che si integra con Configuration Manager e fornisce dati analitici e intelligence utili per prendere decisioni informate sui client Windows. Combina i dati dell'organizzazione con i dati aggregati di milioni di altri dispositivi connessi ai servizi cloud Microsoft. 

Con Desktop Analytics, è possibile:

- Creare un inventario delle app eseguite nell'organizzazione.
- Valutare la compatibilità delle app con gli aggiornamenti delle caratteristiche più recenti di Windows 10.
- Individuare i problemi di compatibilità e ricevere suggerimenti di mitigazione in base alle informazioni dettagliate sui dati abilitati per il cloud.
- Creare gruppi pilota che rappresentino l'intera applicazione e le proprietà del driver in un insieme minimo di dispositivi.
- Distribuire Windows 10 ai dispositivi pilota e gestiti dalla produzione.

Per altre informazioni, vedere questa [panoramica di Desktop Analytics](/mem/configmgr/desktop-analytics/overview).

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot è una piattaforma per la distribuzione di Windows in modalità self-service con gestione automatizzata. Include una raccolta di tecnologie usate per impostare e preconfigurare nuovi dispositivi, preparandoli per l'uso. È anche possibile usare Windows Autopilot per reimpostare, riconfigurare e ripristinare i dispositivi. 

Windows Autopilot consente al reparto IT di preconfigurare dispositivi gestendo poche infrastrutture o persino nessuna, con un processo semplice e immediato. 

- Dal punto di vista dell'utente, bastano poche semplici operazioni per rendere il proprio dispositivo pronto per l'uso. 
- Dal punto di vista dell'IT, l'unica interazione richiesta all'utente finale consiste nel connettersi a una rete e verificare le credenziali.

Per altre informazioni, vedere questa [panoramica di Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Risorse amministrative tecniche per la gestione degli endpoint

- [Roadmap di gestione dei dispositivi per Microsoft 365](../enterprise/device-management-roadmap-microsoft-365.md)
- [Come registrare tipi diversi di dispositivi per la gestione di dispositivi mobili](/mem/intune/enrollment/device-enrollment)
- [Come formare gli utenti finali su Microsoft Intune](/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-4"></a>Risultati del Passaggio 4

Si usano le caratteristiche e le funzionalità di Endpoint Manager per gestire dispositivi mobili, computer desktop, macchine virtuali dispositivi incorporati e server.

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 5: distribuire le app e i servizi per la produttività dei lavoratori remoti](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)

Proseguire con il [Passaggio 5](empower-people-to-work-remotely-teams-productivity-apps.md) per incoraggiare i lavoratori remoti a utilizzare le app di produttività Microsoft 365, come Microsoft Teams.