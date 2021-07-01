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
description: Scopri come spostare l'azienda da Microsoft 365 Business Premium a Microsoft 365 E3.
ms.openlocfilehash: 6502d79dbb283db37b00e4fccf89b15ab4291ce5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227620"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Eseguire la migrazione da Microsoft 365 Business Premium a Microsoft 365 E3

Microsoft 365 Business Premium ha tutto ciò di cui hai bisogno per la tua piccola azienda, combinando le migliori app di produttività basate sul cloud con una semplice gestione dei dispositivi e sicurezza che consentono ai dipendenti di lavorare al meglio. In alcuni casi, tuttavia, potrebbe essere necessario eseguire la migrazione della sottoscrizione Microsoft 365 Business Premium a Microsoft 365 E3.

Ad esempio, l'azienda è aumentata e necessita di più di 300 licenze (congratulazioni, tra l'altro).

In caso contrario, l'azienda necessita di funzionalità aziendali, ad esempio Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3 o Enterprise licenze CAL (Client Access License).

L'aggiornamento è semplice: è possibile avviare [l'aggiornamento dall'interfaccia di amministrazione.](../commerce/subscriptions/upgrade-to-different-plan.md) Vengono mantenuti tutti i dati e la configurazione dell'abbonamento corrente. Non c'è nulla da fare per prepararsi alla migrazione e niente da fare in seguito, tranne sfruttare le nuove funzionalità.

> [!NOTE]
> Puoi anche usare un abbonamento Microsoft 365 Business Premium per un massimo di 300 postazioni e ottenere un abbonamento Microsoft 365 E3 per più di 300 postazioni. Tuttavia, Microsoft Defender per Office 365 non è incluso in Microsoft 365 E3. Per continuare a proteggere le minacce, devi aggiungere ulteriori licenze defender per Office 365 in modo che tutti gli utenti nell'ambito del tuo Defender per i criteri Office 365 siano concessi in licenza.

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Differenze tra Microsoft 365 Business Premium e Microsoft 365 Enterprise

Questa tabella mostra le differenze tra Microsoft 365 Business Premium e Microsoft 365 E3.

| Funzionalità    | Supporto in Microsoft 365 Business Premium    | Supporto in Microsoft 365 E3 |
|:-------|:-----|:-----|
| **Locale**        | | |
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3|
| Office app*    | [Microsoft 365 Apps for business](#office-365-business)    | Microsoft 365 Apps for enterprise |
| **App per la produttività cloud**        | | |
| Exchange Online e Outlook    | Limite di archiviazione di 50 GB per cassetta postale e archiviazione Exchange Online illimitata    | Limite di archiviazione di 100 GB per cassetta postale e archiviazione Exchange Online illimitata |
| Teams    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| OneDrive for Business    | Limite di archiviazione di 1 TB per utente    | Illimitati |
| Yammer, SharePoint Online, Planner, Stream    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| **Threat Protection**        | | |
| Funzionalità di riduzione della superficie di attacco    | [Vedi questo elenco](#threat-protection) | Enterprise gestione dell'isolamento basato su hardware per Microsoft Edge |
| Defender per Office 365 Piano 1 | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | Non incluso, ma può essere aggiunto in |
| **Gestione delle identità**        | | |
| Reimpostazione della password self-service per account Azure Active Directory (Azure AD), Autenticazione a più fattori (MFA) di Azure AD, Accesso condizionale, writeback delle password per le identità locali|     ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| Cloud App Discovery, Azure AD Connessione Health    |     | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| App azure AD Office 365 Single Sign-On (SSO): 10 app per utente (app SaaS della raccolta come Salesforce)* | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Premium 1 SSO: nessun limite (app locali tramite proxy di applicazione Azure AD e app non di raccolta con modelli di integrazione app Self-Service app)    |     | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| **Gestione di dispositivi e app**        | | |
| Microsoft Intune, Windows Autopilot|     ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
|Virtual Desktop Access (VDA)    |  |     ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
|Windows Desktop virtuale (WVD)    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
|Attivazione computer condiviso    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| Pacchetto Ottimizzazione desktop Microsoft    | |     ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| **Protezione delle informazioni**        | | |
| Office 365 Prevenzione della perdita dei dati, Azure Information Protection Piano 1    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| Window Information Protection per dlp endpoint    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| **Licenza Accesso client (diritti CAL)**    | | |
| Enterprise Cal Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| **Conformità**        | | |
| Archiviazione illimitata della posta elettronica    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| Compliance Manager    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| eDiscovery    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| Conservazione sul posto e conservazione per controversia legale    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
| Tag e criteri di conservazione di Gestione record di messaggistica (MRM)    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Microsoft 365 E3](../media/check-mark.png) |
||||

\* Gli utenti a cui è stato assegnato l'accesso alle app SaaS possono ottenere l'accesso SSO a un massimo di 10 app. Gli amministratori possono configurare SSO e modificare l'accesso utente a diverse app SaaS, ma l'accesso SSO è consentito solo per 10 app per utente alla volta. Tutte Office 365 app vengono conteggiate come una singola app.

## <a name="migration"></a>Migrazione

Per eseguire la migrazione, collaborare con il partner per spostare la sottoscrizione Microsoft 365 Business Premium e le licenze in un abbonamento Microsoft 365 E3 appropriato con le relative licenze.

Nelle sezioni seguenti vengono descritte le eventuali modifiche da apportare e le operazioni che è possibile eseguire dopo la migrazione.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 configurazione e dati della sottoscrizione

Non è necessario apportare modifiche alla sottoscrizione o ai dati correnti prima di eseguire la migrazione, tra cui:

- Configurazione della sottoscrizione, ad esempio i nomi di dominio DNS.
- Account utente e di gruppo e impostazioni di autenticazione, ad esempio l'autenticazione a più fattori o i criteri di accesso condizionale.
- Configurazioni dei servizi di produttività e relativi dati, ad esempio Teams, cassette postali Exchange Online, siti di SharePoint Online, cartelle OneDrive for Business e OneNote blocchi appunti.

Gli utenti possono ora usufruire di uno spazio di archiviazione illimitato Exchange Online cassette postali e OneDrive for Business cartelle.

Puoi iniziare a usare Cloud App Discovery, Azure AD Connessione Health e SSO per più di 10 app.

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Protezione dalle minacce

Windows 10 Business include queste protezioni:

- Applicazione dell'integrità del processo di avvio del sistema operativo
- Applicazione dell'integrità dei componenti operativi sensibili
- Mitigazioni avanzate delle vulnerabilità e degli exploit zero-day
- Protezione di rete basata sulla reputazione per Microsoft Edge, Internet Explorer e Chrome
- Firewall basato su host
- Mitigazioni ransomware
- Isolamento basato su hardware per Microsoft Edge
- Controllo delle applicazioni basato sull'intelligent security Graph
- Controllo dispositivo (USB)
- Protezione di rete per le minacce basate sul Web
- Regole di prevenzione delle intrusioni host

Windows 10 Enterprise E3 include anche la gestione aziendale dell'isolamento basato su hardware per Microsoft Edge.

> [!NOTE]
> Gli utenti migrati a Microsoft 365 E3 richiederanno una licenza di Microsoft Defender Office 365 per la protezione dalle minacce continua. Assicurati di acquistare ulteriori licenze defender per Office 365 in modo che tutti gli utenti nell'ambito del tuo Defender per i Office 365 siano concessi in licenza.

### <a name="device-management-with-intune"></a>Gestione dei dispositivi con Intune

Non è necessario apportare modifiche alla configurazione corrente di Intune prima di eseguire la migrazione, che include i dispositivi registrati e le impostazioni dei dispositivi e delle app.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium include Windows 10 Business, che è possibile installare con Windows AutoPilot. Quando esegui la migrazione a Microsoft 365 E3, ogni licenza utente include Windows 10 Enterprise E3, che puoi installare anche con Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps for business

Il Microsoft 365 Apps for business client installato nei dispositivi inizierà automaticamente a usare le funzionalità di Microsoft 365 Apps for enterprise. Dopo la migrazione, è ora possibile usare:

- Supporto di Criteri di gruppo
- Confronto e richiesta di informazioni sui fogli di calcolo
- Business intelligence
