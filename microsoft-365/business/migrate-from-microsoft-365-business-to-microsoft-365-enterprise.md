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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Informazioni su come spostare la propria azienda da Microsoft 365 Business Premium a Microsoft 365 E3.
ms.openlocfilehash: a41b27b91bd049abb2231a397a328f4f53af9500
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633176"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Eseguire la migrazione da Microsoft 365 Business Premium a Microsoft 365 E3

Microsoft 365 Business Premium offre tutto il necessario per le piccole aziende, combinando le app di produttività basate su cloud di Best-in-Class con la gestione e la sicurezza dei dispositivi semplici che consentono ai dipendenti di svolgere al meglio le proprie attività. In alcuni casi, tuttavia, potrebbe essere necessario eseguire la migrazione della sottoscrizione Microsoft 365 Business Premium a Microsoft 365 E3. 

Ad esempio, la tua azienda è cresciuta e ha bisogno di più di 300 licenze (Congratulazioni, tra l'altro).

In alternativa, l'azienda ha bisogno di funzionalità aziendali, ad esempio le app Microsoft 365 per Enterprise, Windows 10 Enterprise E3 o le licenze CAL (Enterprise Client Access License).

L'aggiornamento è semplice: è possibile avviare l'aggiornamento [dall'interfaccia di amministrazione](../commerce/subscriptions/upgrade-to-different-plan.md). Tutti i dati e la configurazione della sottoscrizione corrente vengono mantenuti. Non è necessario eseguire alcuna operazione per prepararsi per la migrazione e non è più possibile eseguire le nuove funzionalità.

>[!Note]
>È inoltre possibile utilizzare un abbonamento a Microsoft 365 Business Premium per un massimo di 300 posti a sedere e ottenere un abbonamento a Microsoft 365 E3 per più di 300 seggi. Tuttavia, Office 365 ATP non è incluso in Microsoft 365 E3. Per una continua protezione dalle minacce, è necessario aggiungere altre licenze ATP di Office 365, in modo che tutti gli utenti nell'ambito dei criteri di sicurezza ATP di Office 365 siano concessi in licenza.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Differenze tra Microsoft 365 Business Premium e Microsoft 365 Enterprise

In questa tabella vengono illustrate le differenze tra Microsoft 365 Business Premium e Microsoft 365 E3.

| Funzionalità    | Supporto in Microsoft 365 Business Premium    | Supporto in Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **Locale**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| App di Office *    | [Microsoft 365 Apps for business](#office-365-business)    | Microsoft 365 Apps for Enterprise | 
| **App per la produttività del cloud**        | | | 
| Exchange Online e Outlook    | 50 GB di spazio di archiviazione per cassetta postale e archiviazione Exchange Online illimitata    | 100 GB di spazio di archiviazione per cassetta postale e archiviazione Exchange Online illimitata | 
| Teams    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | limite di archiviazione di 1 TB per utente    | Illimitati | 
| Yammer, SharePoint Online, planner, Stream    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Gestione clienti di Outlook, MileIQ    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Protezione dalle minacce**        | | | 
| Funzionalità di riduzione della superficie di attacco    | [Vedere questo elenco](#threat-protection) | Gestione aziendale dell'isolamento basato sull'hardware per Microsoft Edge | 
| Piano 1 di Office 365 Advanced Threat Protection (ATP) | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | Non incluso, ma può essere aggiunto | 
| **Gestione delle identità**        | | | 
| Reimpostazione della password in modalità self-service per gli account di Azure Active Directory (Azure AD), l'autenticazione a più fattori di Azure (AMF), l'accesso condizionale, il writeback delle password per le identità locali|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Individuazione delle app Cloud, Azure AD Connect Health    |     | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Office 365 Apps Single Sign-on (SSO): 10 app per utente (app SaaS Galleria come Salesforce) * | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: No Limit (app locali attraverso il proxy di applicazione Azure AD e le app non di raccolta usando i modelli di integrazione delle app in modalità self-service)    |     | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| **Gestione di dispositivi e app**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
|Accesso desktop virtuale (VDA)    |  |     ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
|Desktop virtuale di Windows (WVD)    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
|Attivazione di computer condivisi (SCA)    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png) |     ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Pacchetto di ottimizzazione di Microsoft Desktop    | |     ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| **Protezione delle informazioni**        | | | 
| Prevenzione della perdita dei dati di Office 365, piano di protezione delle informazioni di Azure 1    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Protezione delle informazioni sulle finestre per Endpoint DLP    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| **Licenza di accesso client (CAL Rights)**    | | |     
| Famiglia di prodotti Enterprise CAL (Exchange, SharePoint, Skype, Windows, Microsoft endpoint Configuration Manager, Windows Rights Management)| |         ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| **Conformità**        | | | 
| Archiviazione di posta elettronica illimitata    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Punteggio di conformità/gestione conformità    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| eDiscovery    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Blocco sul posto e conservazione per controversia legale    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
| Tag e criteri di conservazione di Gestione record di messaggistica (MRM)    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Microsoft 365 E3](../media/check-mark.png) | 
||||

\*Gli utenti a cui è stato assegnato l'accesso alle app SaaS possono ottenere l'accesso SSO a un massimo di 10 app. Gli amministratori possono configurare SSO e modificare l'accesso degli utenti a diverse app SaaS, ma l'accesso SSO è consentito solo per 10 app per utente alla volta. Tutte le app di Office 365 vengono contate come una singola app.

## <a name="migration"></a>Migrazione

Per eseguire la migrazione, collaborare con il partner per spostare la sottoscrizione e le licenze di Microsoft 365 Business Premium a un abbonamento Microsoft 365 E3 appropriato con le relative licenze.

Nelle sezioni seguenti vengono descritte le modifiche che è necessario apportare, se presenti, e le operazioni che è possibile eseguire dopo la migrazione.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Configurazione e dati della sottoscrizione Microsoft 365

Non è necessario apportare modifiche alla sottoscrizione corrente o ai dati prima di eseguire la migrazione, che include:

- Configurazione della sottoscrizione, ad esempio i nomi di dominio DNS.
- Gli account utente e di gruppo e le impostazioni di autenticazione, ad esempio l'autenticazione a più fattori o i criteri di accesso condizionale.
- Configurazioni dei servizi di produttività e relativi dati, ad esempio Team, cassette postali di Exchange Online, siti di SharePoint Online, cartelle di OneDrive for business e blocchi appunti di OneNote.

Gli utenti possono ora usufruire dello spazio di archiviazione illimitato nelle cartelle di cassette postali di Exchange Online e OneDrive for business.

È possibile iniziare a utilizzare il servizio di individuazione delle app Cloud, Azure AD Connect Health e SSO per più di 10 app.

>[!Note]
>Gli utenti migrati a Microsoft 365 E3 non sono più in grado di utilizzare Gestione clienti di Outlook e MileIQ.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Protezione dalle minacce

Windows 10 business include queste protezioni:

- Applicazione dell'integrità del processo di avvio del sistema operativo
- Applicazione dell'integrità dei componenti operativi riservati
- Vulnerabilità avanzata e mitigazioni degli exploit zero-day
- Protezione della rete basata sulla reputazione per Microsoft Edge, Internet Explorer e Chrome
- Firewall basato su host
- Attenuazioni ransomware
- Isolamento basato sull'hardware per Microsoft Edge
- Controllo dell'applicazione alimentato dal grafico di sicurezza intelligente
- Controllo dispositivo (USB)
- Protezione della rete per le minacce basate sul Web
- Regole di prevenzione della intrusione host

Windows 10 Enterprise E3 include anche la gestione aziendale dell'isolamento basato sull'hardware per Microsoft Edge.

>[!Note]
>Gli utenti migrati a Microsoft 365 E3 dovranno richiedere una licenza ATP di Office 365 per la protezione dalle minacce continuate. Assicurarsi di acquistare altre licenze ATP di Office 365 in modo che tutti gli utenti nell'ambito della polizia ATP di Office 365 siano concessi in licenza. 
>

### <a name="device-management-with-intune"></a>Gestione dei dispositivi con Intune

Non è necessario apportare modifiche alla configurazione di Intune corrente prima di eseguire la migrazione, in cui sono inclusi i dispositivi registrati e le impostazioni di dispositivo e app.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium include Windows 10 business, che è possibile installare con Windows Autopilot. Quando si esegue la migrazione a Microsoft 365 E3, ogni licenza utente include Windows 10 Enterprise E3, che è possibile installare anche con Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Microsoft 365 Apps for business

Il client Microsoft 365 Apps for business installato nei dispositivi inizierà automaticamente a utilizzare le funzionalità di Microsoft 365 Apps for Enterprise. Dopo la migrazione, è ora possibile utilizzare:

 - Attivazione di contratti multilicenza tramite criteri di gruppo
 - Telemetria app
 - Controlli di aggiornamento
 - Confronto e richiesta del foglio di calcolo
 - Business intelligence

