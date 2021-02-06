---
title: Eseguire la migrazione da Microsoft 365 Business a Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Informazioni su come spostare l'azienda da Microsoft 365 Business Premium a Microsoft 365 E3.
ms.openlocfilehash: 019a422bb879389f42a32cf30f9a8094f776078a
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126202"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Eseguire la migrazione da Microsoft 365 Business Premium a Microsoft 365 E3

Microsoft 365 Business Premium ha tutto il necessario per le piccole imprese, combinando le migliori app di produttività basate sul cloud con semplici funzionalità di gestione e sicurezza dei dispositivi che consentono ai dipendenti di lavorare al meglio. In alcuni casi, tuttavia, potrebbe essere necessario eseguire la migrazione dell'abbonamento a Microsoft 365 Business Premium a Microsoft 365 E3. 

Ad esempio, l'azienda è aumentata e necessita di più di 300 licenze (congratulazioni, tra l'altro).

Oppure, l'azienda ha bisogno di funzionalità aziendali, come Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3 o Enterprise Client Access Licenses (CAL).

L'aggiornamento è semplice: è possibile avviare [l'aggiornamento dall'interfaccia di amministrazione.](../commerce/subscriptions/upgrade-to-different-plan.md) Vengono mantenuti tutti i dati e la configurazione dell'abbonamento corrente. Non c'è niente da fare per prepararsi alla migrazione e niente da fare in seguito, tranne sfruttare le nuove funzionalità.

>[!Note]
>È anche possibile usare un abbonamento a Microsoft 365 Business Premium per un massimo di 300 postazioni e ottenere un abbonamento a Microsoft 365 E3 per più di 300 postazioni. Tuttavia, Microsoft Defender per Office 365 non è incluso in Microsoft 365 E3. Per una protezione continua dalle minacce, è consigliabile aggiungere ulteriori licenze di Defender per Office 365 in modo che tutti gli utenti nell'ambito dei criteri di Defender per Office 365 siano concessi in licenza.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Differenze tra Microsoft 365 Business Premium e Microsoft 365 Enterprise

Questa tabella mostra le differenze tra Microsoft 365 Business Premium e Microsoft 365 E3.

| Funzionalità    | Supporto in Microsoft 365 Business Premium    | Supporto in Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **Locale**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| App di Office*    | [Microsoft 365 Apps for business](#office-365-business)    | Microsoft 365 Apps for enterprise | 
| **App per la produttività cloud**        | | | 
| Exchange Online e Outlook    | Limite di archiviazione di 50 GB per cassetta postale e archiviazione illimitata di Exchange Online    | Limite di archiviazione di 100 GB per cassetta postale e archiviazione illimitata di Exchange Online | 
| Teams    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | Limite di archiviazione di 1 TB per utente    | Illimitati | 
| Yammer, SharePoint Online, Planner, Stream    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| MileIQ    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Protezione dalle minacce**        | | | 
| Funzionalità di riduzione della superficie di attacco    | [Vedi questo elenco](#threat-protection) | Gestione aziendale dell'isolamento basato su hardware per Microsoft Edge | 
| Defender per Office 365 Piano 1 | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | Non incluso, ma può essere aggiunto in | 
| **Gestione delle identità**        | | | 
| Reimpostazione della password in modalità self-service per gli account ibridi di Azure Active Directory (Azure AD), Autenticazione a più fattori (MFA) di Azure AD, accesso condizionale, writeback delle password per identità locali|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Cloud App Discovery, Azure AD Connect Health    |     | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| App di Office 365 di Azure AD single Sign-On (SSO): 10 app per utente (raccolta di app SaaS come Salesforce)* | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| SSO Di Azure AD Premium 1: nessun limite (app locali tramite proxy di applicazione di Azure AD e app non della raccolta con Self-Service modelli di integrazione app)    |     | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| **Gestione di dispositivi e app**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
|Virtual Desktop Access (VDA)    |  |     ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
|Desktop virtuale Windows (WVD)    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
|Attivazione di computer condivisi    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Pacchetto di Ottimizzazione desktop Microsoft    | |     ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| **Protezione delle informazioni**        | | | 
| Prevenzione della perdita dei dati di Office 365, Azure Information Protection Piano 1    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Windows Information Protection per endpoint DLP    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| **Licenza CAL (Client Access License)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| **Conformità**        | | | 
| Archiviazione illimitata della posta elettronica    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Compliance Manager    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| eDiscovery    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Blocco sul posto e conservazione per controversia legale    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Tag e criteri di conservazione di Gestione record di messaggistica (MRM)    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
||||

\* Gli utenti a cui è stato assegnato l'accesso alle app SaaS possono ottenere l'accesso SSO a un massimo di 10 app. Gli amministratori possono configurare SSO e modificare l'accesso utente a diverse app SaaS, ma l'accesso SSO è consentito solo per 10 app per utente alla volta. Tutte le app di Office 365 vengono conteggiate come una singola app.

## <a name="migration"></a>Migrazione

Per eseguire la migrazione, collaborare con il partner per spostare l'abbonamento a Microsoft 365 Business Premium e le licenze a un abbonamento a Microsoft 365 E3 appropriato con le relative licenze.

Nelle sezioni seguenti vengono descritte le eventuali modifiche da apportare e le operazioni che è possibile eseguire dopo la migrazione.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Dati e configurazione dell'abbonamento a Microsoft 365

Non è necessario apportare modifiche all'abbonamento corrente o ai dati prima della migrazione, tra cui:

- Configurazione della sottoscrizione, ad esempio i nomi di dominio DNS.
- Account utente e di gruppo e impostazioni di autenticazione, ad esempio l'autenticazione a più fattori o i criteri di accesso condizionale.
- Configurazioni dei servizi di produttività e relativi dati, ad esempio Teams, cassette postali di Exchange Online, siti di SharePoint Online, cartelle di OneDrive for Business e blocchi appunti di OneNote.

Gli utenti possono ora usufruire di spazio di archiviazione illimitato nelle cassette postali di Exchange Online e nelle cartelle di OneDrive for Business.

Puoi iniziare a usare Cloud App Discovery, Azure AD Connect Health e SSO per più di 10 app.

>[!Note]
>Gli utenti migrati a Microsoft 365 E3 non possono più usare MileIQ.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Protezione dalle minacce

Windows 10 Business include queste protezioni:

- Imposizione dell'integrità del processo di avvio del sistema operativo
- Applicazione dell'integrità dei componenti operativi sensibili
- Prevenzione avanzata delle vulnerabilità e degli exploit zero-day
- Protezione di rete basata sulla reputazione per Microsoft Edge, Internet Explorer e Chrome
- Firewall basato sull'host
- Mitigazioni ransomware
- Isolamento basato su hardware per Microsoft Edge
- Controllo delle applicazioni basato su Intelligent Security Graph
- Controllo dispositivo (USB)
- Protezione di rete per le minacce basate sul Web
- Regole di prevenzione delle intrusioni nell'host

Windows 10 Enterprise E3 include anche la gestione aziendale dell'isolamento basato su hardware per Microsoft Edge.

>[!Note]
>Gli utenti migrati a Microsoft 365 E3 richiederanno ognuno una licenza di Microsoft Defender per Office 365 per una protezione continua dalle minacce. Assicurarsi di acquistare altre licenze di Defender per Office 365 in modo che tutti gli utenti nell'ambito dei propri agenti di Defender per Office 365 siano concessi in licenza. 
>

### <a name="device-management-with-intune"></a>Gestione dei dispositivi con Intune

Non è necessario apportare modifiche alla configurazione corrente di Intune prima della migrazione, che include i dispositivi registrati e le impostazioni dei dispositivi e delle app.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium include Windows 10 Business, che è possibile installare con Windows AutoPilot. Quando si esegue la migrazione a Microsoft 365 E3, ogni licenza utente include Windows 10 Enterprise E3, che può essere installato anche con Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps for business

Il client Microsoft 365 Apps for business installato nei dispositivi inizierà automaticamente a usare le funzionalità di Microsoft 365 Apps for enterprise. Dopo la migrazione, è ora possibile utilizzare:

 - Supporto di Criteri di gruppo
 - Confronto e richiesta di fogli di calcolo
 - Business intelligence

