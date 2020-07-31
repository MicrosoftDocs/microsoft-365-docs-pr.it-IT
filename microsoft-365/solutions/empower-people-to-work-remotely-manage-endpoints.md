---
title: Passaggio 4. Distribuire la gestione degli endpoint per dispositivi, PC e altri endpoint
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
- m365solution-remotework
ms.custom: ''
description: Usare Microsoft Endpoint Manager per gestire dispositivi, PC e altri endpoint.
ms.openlocfilehash: 0f13d36a2943367e751123c724cda28b503a51d2
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521542"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>Passaggio 4. Distribuire la gestione degli endpoint per dispositivi, PC e altri endpoint

Con i lavoratori remoti, è necessario supportare un numero crescente di dispositivi personali. La gestione degli endpoint è un approccio alla sicurezza basato su criteri che richiede che i dispositivi siano conformi a criteri specifici prima che gli venga consentito l'accesso alle risorse. Microsoft Endpoint Manager offre strumenti moderni per la gestione che garantiscono la sicurezza dei dati sia nel cloud sia in locale. 

Endpoint Manager include servizi e strumenti che consentono di gestire dispositivi mobili, computer desktop, macchine virtuali, dispositivi incorporati e server combinando i servizi seguenti, probabilmente già noti e usati.

![I componenti per la gestione degli endpoint](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune è un servizio basato sul cloud che è incentrato sulla gestione di dispositivi mobili (MDM) e sulla gestione di applicazioni mobili (MAM) incluso in Microsoft 365. 

- **MDM:** per i dispositivi di proprietà dell'organizzazione, è possibile esercitare un controllo completo che include impostazioni, caratteristiche e sicurezza. I dispositivi sono "registrati" in Intune, dove ricevono criteri di Intune con regole e impostazioni. Ad esempio, è possibile impostare PIN e password, creare una connessione VPN, configurare la protezione contro le minacce e così via.

- **MAM:** i lavoratori remoti potrebbero non voler concedere il controllo completo sui propri dispositivi personali, noti anche come dispositivi di BYOD (bring-your-own). È possibile fornire opzioni ai lavoratori remoti e continuare a proteggere l'organizzazione. Ad esempio, i lavoratori remoti possono registrare i propri dispositivi, per avere accesso completo alle risorse dell'organizzazione. In alternativa, se desiderano accedere solo alla posta elettronica o a Microsoft Teams, gli utenti possono usare i criteri di protezione delle app che richiedono l'autenticazione a più fattori (MFA) per l'uso di queste app.

Per altre informazioni, vedere questa [panoramica di Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager è una soluzione di gestione locale per gestire desktop, server e computer portatili collegati nella rete aziendale o in Internet. Usare Configuration Manager per distribuire app, aggiornamenti software e sistemi operativi. È anche possibile monitorare la conformità, eseguire query, intervenire sui client in tempo reale e molto altro ancora. È possibile abilitare la soluzione per il cloud e integrarla con Intune, Azure AD, Microsoft Defender ATP e altri servizi cloud. 

Per altre informazioni, vedere questa [panoramica di Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Co-gestione

La co-gestione integra l'investimento esistente in Configuration Manager locale con il cloud, tramite l'uso di Intune e di altri servizi cloud Microsoft 365. È possibile scegliere Configuration Manager o Intune come autorità di gestione per carichi di lavoro diversi. 

La co-gestione usa funzionalità cloud basate su Intune, tra cui l'accesso condizionale e l'applicazione della conformità del dispositivo. Alcune attività restano in locale, mentre altre vengono eseguite nel cloud.

Per altre informazioni, vedere questa [panoramica della co-gestione](https://docs.microsoft.com/mem/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics è un servizio basato sul cloud che si integra con Configuration Manager e fornisce dati analitici e intelligence utili per prendere decisioni informate sui client Windows. Combina i dati dell'organizzazione con i dati aggregati di milioni di dispositivi connessi ai servizi cloud Microsoft. 

Con Desktop Analytics, è possibile:

- Creare un inventario delle app eseguite nell'organizzazione.
- Valutare la compatibilità delle app con gli aggiornamenti delle caratteristiche più recenti di Windows 10.
- Individuare i problemi di compatibilità e ricevere suggerimenti di mitigazione in base alle informazioni sui dati abilitati per il cloud.
- Creare gruppi pilota che rappresentino l'intera applicazione e le proprietà del driver in un insieme minimo di dispositivi.
- Distribuire Windows 10 ai dispositivi pilota e gestiti dalla produzione.

Per altre informazioni, vedere questa [panoramica di Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview).

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot è una piattaforma per la distribuzione di Windows in modalità self-service con gestione automatizzata. Include una raccolta di tecnologie usate per impostare e preconfigurare nuovi dispositivi, preparandoli per l'uso. È anche possibile usare Windows Autopilot per reimpostare, riconfigurare e ripristinare i dispositivi. 

Windows Autopilot consente al reparto IT di preconfigurare dispositivi gestendo poche infrastrutture o persino nessuna, con un processo semplice e immediato. 

- Dal punto di vista dell'utente, bastano poche semplici operazioni per rendere il proprio dispositivo pronto per l'uso. 
- Dal punto di vista dell'IT, l'unica interazione richiesta all'utente finale consiste nel connettersi a una rete e verificare le credenziali.

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

Proseguire con il [Passaggio 5](empower-people-to-work-remotely-teams-productivity-apps.md) per incoraggiare i lavoratori remoti a utilizzare le app di produttività Microsoft 365, come Microsoft Teams.
