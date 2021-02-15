---
title: Eseguire la migrazione a Microsoft 365 Business da Office 365 E3
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Informazioni su come trasferire l'azienda a Microsoft 365 Business Premium da Office 365 E3.
ms.openlocfilehash: eebf78c24ed4bfd1a4fc2d843f37aebbe3d35e31
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558259"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrazione da Office 365 E3 a Microsoft 365 Business Premium 

Microsoft 365 Business Premium ha tutto il necessario per le piccole imprese, combinando le migliori app di produttività basate sul cloud con semplici funzionalità di gestione e sicurezza dei dispositivi. Se attualmente si ha un abbonamento a Office 365 E3, ma non si hanno più di 300 dipendenti, è consigliabile passare a Microsoft 365 Business Premium per aggiungere funzionalità di sicurezza.

La migrazione è semplice: prima di tutto si cambia licenza e vengono mantenuti tutti i dati e le informazioni utente nell'abbonamento corrente. Dopo la migrazione, è necessario configurare le funzionalità aggiunte in Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Differenze tra Office 365 E3 e Microsoft 365 Business Premium

Questa tabella mostra le differenze tra Microsoft 365 Business Premium e Office 365 E3.

| Funzionalità    | Supporto in Microsoft 365 Business Premium    | Supporto in Office 365 E3 | 
|:-------|:-----|:-----|
| **Locale**        | | | 
| App di Office<sup>1</sup>    | Microsoft 365 Apps for business    | Microsoft 365 Apps for enterprise | 
| **App per la produttività cloud**        | | | 
| Exchange Online e Outlook    | Limite di archiviazione di 50 GB per cassetta postale e spazio di archiviazione Archiviazione Exchange Online    | Limite di archiviazione di 100 GB per cassetta postale e spazio di archiviazione Archiviazione Exchange Online | 
| Teams    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Office 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | Limite di archiviazione di 1 TB per utente    | Illimitati | 
| Yammer, SharePoint Online, Planner, Stream    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Office 365 E3](../media/check-mark.png) | 
| Outlook Customer Manager, MileIQ    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Protezione dalle minacce**        | | | 
| Defender per Office 365 Piano 1 | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | Non incluso, ma può essere aggiunto in | 
| **Gestione delle identità**        | | | 
| Reimpostazione della password in modalità self-service per gli account ibridi di Azure Active Directory (Azure AD), Autenticazione a più fattori (MFA) di Azure AD, accesso condizionale, writeback delle password per identità locali|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| **Gestione di dispositivi e app**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Attivazione di computer condivisi|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso in Office 365 E3](../media/check-mark.png)| 
| Aggiornare i diritti a Windows 10 Pro dalle licenze Win 7/8.1 Pro|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    || 
| **Protezione delle informazioni**        | | |
|Prevenzione della perdita di dati di Office 365|    ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)|![Incluso in Office 365 E3](../media/check-mark.png)|
|Azure Information Protection Piano 1, imposizione di Bitlocker|![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)||
|Azure Information Protection Piano 1, etichette di riservatezza|![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)||
|**Licenza CAL (Client Access License)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Incluso in Office 365 E3](../media/check-mark.png)|

<sup>1</sup> La versione Microsoft 365 Business Premium delle app di Office non include l'attivazione di contratti multilicenza tramite Criteri di gruppo, telemetria delle app, controlli di aggiornamento, confronto e richiesta di informazioni sui fogli di calcolo o business intelligence.

## <a name="migration"></a>Migrazione

Per eseguire la [](../commerce/subscriptions/change-plans-manually.md) migrazione dell'abbonamento, vedere Modificare i piani manualmente per istruzioni se si desidera spostare solo poche persone in Microsoft 365 Business Premium. È inoltre possibile [aggiornare automaticamente](../commerce/subscriptions/upgrade-to-different-plan.md)tutti gli utenti oppure collaborare con un partner per spostare l'abbonamento e le licenze di E3 in un abbonamento a Microsoft 365 Business Premium.
Nelle sezioni seguenti vengono descritte le modifiche da apportare, se presenti, e le operazioni che è possibile eseguire dopo la migrazione.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Dati e configurazione dell'abbonamento a Office 365 E3
Non è necessario apportare modifiche all'abbonamento corrente o ai dati prima della migrazione, tra cui:

- Configurazione della sottoscrizione, ad esempio record DNS e nomi di dominio.
- Account utente e di gruppo e impostazioni di autenticazione, ad esempio l'autenticazione a più fattori o i criteri di accesso condizionale.
- Configurazioni dei servizi di produttività e relativi dati, ad esempio Teams, cassette postali di Exchange Online, siti di SharePoint Online, cartelle di OneDrive for Business e blocchi appunti di OneNote.
- Le applicazioni di Office verranno ridimensionate automaticamente. Le licenze moderne di Office 365 controllano l'assegnazione della licenza dell'utente ogni 72 ore e convertono le applicazioni di Office nella versione corrispondente all'abbonamento dell'utente.

### <a name="windows-10"></a>Windows 10

Se Windows non è già in Windows Pro Creator Update, [aggiornarlo a Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Configurare criteri per proteggere i dispositivi e i file degli utenti

> [!NOTE]
> Se si configurano i criteri e i dispositivi MDM di  Office 365, tali dispositivi verranno elencati nella pagina Dispositivi nell'interfaccia di amministrazione di Microsoft 365. Tutti i criteri impostati verranno visualizzati nell'elenco dei criteri classici nel [portale di Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

Dopo aver assegnato le licenze a Microsoft 365 Business Premium, è possibile iniziare a proteggere i dispositivi e i file degli utenti.

Se tutti gli utenti dell'organizzazione sono stati aggiornati a Microsoft 365 Business Premium, la configurazione guidata verrà visualizzata nella home page e sarà possibile seguire la procedura di configurazione di [Microsoft 365 Business Premium](set-up.md) nella procedura guidata per proteggere i file e i dispositivi mobili.

Puoi anche completare questi passaggi nella pagina Dispositivi:
  
1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione passare a **Criteri** \> **dispositivi.**
    
2. Nella pagina **Criteri dispositivo** scegliere **Aggiungi.**
    
3. Nel riquadro **Aggiungi criterio** assegnare un nome al criterio e quindi scegliere un tipo **di criterio** nell'elenco a discesa. 
    
     Puoi configurare criteri di applicazione per proteggere i file nei dispositivi Android e iPhone, nonché in Windows 10, e puoi configurare i criteri di configurazione dei dispositivi per i dispositivi Windows 10 di proprietà dell'azienda. Per informazioni dettagliate, vedere i collegamenti seguenti:
    
  - [Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Configurare le impostazioni di protezione delle app per i dispositivi Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Configurare le impostazioni di protezione dei dispositivi per i PC Windows 10](protection-settings-for-windows-10-pcs.md)
  
4. Dopo aver configurato i criteri, l'utente e i dipendenti possono configurare i dispositivi:
    
  - Per la procedura per i dispositivi Windows, vedere Configurare i dispositivi Windows per gli utenti di [Microsoft 365 Business](set-up-windows-devices.md) Premium. 
    
  - Vedere [Configurare i dispositivi mobili per gli utenti di Microsoft 365 Business Premium](set-up-mobile-devices.md) per la procedura per telefoni Android e iPhone. 
  
### <a name="mailbox-size"></a>Dimensione cassetta postale

Microsoft 365 Business Premium ha un limite di archiviazione di 50 GB perché usa Exchange Online Piano 1. Durante la migrazione a Microsoft 365 Business Premium, se uno degli utenti supera i 50 GB di spazio di archiviazione delle cassette postali, è consigliabile assegnare a questo utente un Piano 2 di Exchange Online e rimuovere Exchange Online Piano 1 poiché non è possibile assegnare entrambi.


### <a name="threat-protection"></a>Protezione dalle minacce

Dopo la migrazione a Microsoft 365 Business Premium, si dispone di Defender per Office 365. Per [una panoramica, vedere Microsoft Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) Per la configurazione, vedere [configurare collegamenti](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)sicuri, [configurare](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)allegati sicuri e configurare [l'anti-phishing in Defender per Office 365.](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Per iniziare a usare le etichette di riservatezza, vedere [Panoramica delle](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) etichette di riservatezza e creare e gestire il video sulle [etichette di](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) riservatezza.
