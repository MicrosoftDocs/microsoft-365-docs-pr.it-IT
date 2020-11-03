---
title: Eseguire la migrazione a Microsoft 365 business da Office 365 E3
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
description: Informazioni su come spostare la propria azienda in Microsoft 365 Business Premium da Office 365 E3.
ms.openlocfilehash: b8aa58f1f050ec6247479ed02e142507a2df45fc
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842161"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrazione da Office 365 E3 a Microsoft 365 Business Premium 

Microsoft 365 Business Premium offre tutto il necessario per le piccole aziende, combinando le app di produttività basate su cloud di Best-in-Class con la gestione e la sicurezza dei dispositivi semplici. Se attualmente si dispone di un abbonamento a Office 365 E3, ma non si dispone di più di 300 dipendenti, valutare la possibilità di passare a Microsoft 365 Business Premium per aggiungere funzionalità di sicurezza.

La migrazione è semplice: prima di tutto si cambia la licenza e tutti i dati e le informazioni degli utenti nell'abbonamento corrente vengono mantenuti. Dopo la migrazione, sarà necessario configurare le caratteristiche aggiunte in Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Differenze tra Office 365 E3 e Microsoft 365 Business Premium

In questa tabella vengono illustrate le differenze tra Microsoft 365 Business Premium e Office 365 E3.

| Funzionalità    | Supporto in Microsoft 365 Business Premium    | Supporto in Office 365 E3 | 
|:-------|:-----|:-----|
| **Locale**        | | | 
| App di Office<sup>1</sup>    | Microsoft 365 Apps for business    | Microsoft 365 Apps for enterprise | 
| **App per la produttività del cloud**        | | | 
| Exchange Online e Outlook    | 50 GB di spazio di archiviazione per cassetta postale e archiviazione Exchange Online illimitata    | 100 GB di spazio di archiviazione per cassetta postale e archiviazione Exchange Online illimitata | 
| Teams    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | limite di archiviazione di 1 TB per utente    | Illimitati | 
| Yammer, SharePoint Online, planner, Stream    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png) | 
| Gestione clienti di Outlook, MileIQ    | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| **Protezione dalle minacce**        | | | 
| Difensore per Office 365 piano 1 | ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | Non incluso, ma può essere aggiunto | 
| **Gestione delle identità**        | | | 
| Reimpostazione della password in modalità self-service per gli account di Azure Active Directory (Azure AD), l'autenticazione a più fattori di Azure (AMF), l'accesso condizionale, il writeback delle password per le identità locali|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| **Gestione di dispositivi e app**        | | |
| Microsoft Intune, Windows Autopilot|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Attivazione di computer condivisi|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png)| 
| Diritti di aggiornamento a Windows 10 Pro dalle licenze Win 7/8.1 Pro|     ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)    || 
| **Protezione delle informazioni**        | | |
|Prevenzione della perdita di dati di Office 365|    ![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)|![Incluso con Office 365 E3](../media/check-mark.png)|
|Azure Information Protection piano 1, applicazione di BitLocker|![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)||
|Piano di protezione delle informazioni di Azure 1, etichette di riservatezza|![Incluso in Microsoft 365 Business Premium](../media/check-mark.png)||
|**Licenza di accesso client (CAL Rights)**|||
|Famiglia di prodotti Enterprise CAL (Exchange, SharePoint, Skype)||![Incluso con Office 365 E3](../media/check-mark.png)|

<sup>1</sup> la versione Microsoft 365 Business Premium delle app di Office non include l'attivazione di contratti multilicenza tramite criteri di gruppo, la telemetria delle app, i controlli di aggiornamento, il confronto dei fogli di calcolo e la richiesta o la Business Intelligence

## <a name="migration"></a>Migrazione

Per eseguire la migrazione della sottoscrizione, vedere [modificare i piani manualmente](../commerce/subscriptions/change-plans-manually.md) per le istruzioni se si desidera spostare solo poche persone a Microsoft 365 Business Premium. È inoltre possibile [aggiornare automaticamente tutti gli utenti](../commerce/subscriptions/upgrade-to-different-plan.md)o collaborare con un partner per spostare la sottoscrizione E3 e le licenze a un abbonamento a Microsoft 365 Business Premium.
Nelle sezioni seguenti vengono descritte le modifiche che è necessario apportare, se presenti, e le operazioni che è possibile eseguire dopo la migrazione.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Configurazione e dati dell'abbonamento a Office 365 E3
Non è necessario apportare modifiche alla sottoscrizione corrente o ai dati prima di eseguire la migrazione, che include:

- Configurazione della sottoscrizione, ad esempio i record DNS e i nomi di dominio.
- Gli account utente e di gruppo e le impostazioni di autenticazione, ad esempio l'autenticazione a più fattori o i criteri di accesso condizionale.
- Configurazioni dei servizi di produttività e relativi dati, ad esempio Team, cassette postali di Exchange Online, siti di SharePoint Online, cartelle di OneDrive for business e blocchi appunti di OneNote.
- Le applicazioni di Office verranno scalate automaticamente. Office 365 Modern Licensing controllerà l'assegnazione della licenza dell'utente ogni 72 ore e convertirà le applicazioni di Office nella versione corrispondente alla sottoscrizione dell'utente.

### <a name="windows-10"></a>Windows 10

Se le finestre non sono già presenti nell'aggiornamento di Windows Pro Creator, è possibile aggiornarle [nell'aggiornamento a Windows Pro Creators](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Impostare i criteri per la protezione dei dispositivi e dei file utente

> [!NOTE]
> Se si configurano i criteri e i dispositivi di Office 365 MDM, tali dispositivi verranno elencati nella pagina **dispositivi** nell'interfaccia di amministrazione di Microsoft 365. Tutti i criteri configurati verranno visualizzati nell'elenco dei criteri classici nel portale di [Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).

Dopo aver assegnato le licenze a Microsoft 365 Business Premium, è possibile iniziare a proteggere i dispositivi e i file degli utenti.

Se tutti gli utenti dell'organizzazione sono stati aggiornati a Microsoft 365 Business Premium, verrà visualizzata la procedura guidata di installazione nella Home page e sarà possibile seguire la procedura di installazione [guidata di microsoft 365 Business Premium nei](set-up.md) passaggi di configurazione per proteggere i file e i dispositivi mobili.

È inoltre possibile eseguire questi passaggi nella pagina dispositivi:
  
1. Nell'interfaccia di amministrazione, nella barra di spostamento a sinistra, passare ai criteri dei **dispositivi** \> **Policies**.
    
2. Nella pagina **Criteri dispositivo** scegliere **Aggiungi**.
    
3. Nel riquadro **Aggiungi criterio** assegnare un nome al criterio e quindi scegliere un tipo di **criterio** dall'elenco a discesa. 
    
     È possibile configurare i criteri di applicazione per la protezione dei file su dispositivi Android e iPhone, oltre a Windows 10, ed è possibile configurare i criteri di configurazione del dispositivo per i dispositivi Windows 10 di proprietà dell'azienda. Per informazioni dettagliate, vedere i seguenti collegamenti:
    
  - [Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Configurare le impostazioni di protezione delle app per i dispositivi Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Impostazione delle impostazioni di protezione dei dispositivi per PC Windows 10](protection-settings-for-windows-10-pcs.md)
  
4. Dopo aver configurato i criteri, gli utenti e i dipendenti possono configurare i dispositivi:
    
  - Per i dispositivi Windows, vedere [configurare i dispositivi Windows per gli utenti di Microsoft 365 Business Premium](set-up-windows-devices.md) . 
    
  - Per i passaggi per telefoni Android e iPhone, vedere [configurare i dispositivi mobili per gli utenti di Microsoft 365 Business Premium](set-up-mobile-devices.md) . 
  
### <a name="mailbox-size"></a>Dimensione della cassetta postale

Microsoft 365 Business Premium ha un limite di archiviazione di 50 GB poiché utilizza Exchange Online piano 1. Durante la migrazione a Microsoft 365 Business Premium, se uno degli utenti supera 50 GB di spazio di archiviazione delle cassette postali, si consiglia di assegnare l'utente a Exchange Online piano 2 e rimuovere il piano di Exchange Online 1 in quanto non è possibile assegnare entrambi.


### <a name="threat-protection"></a>Protezione dalle minacce

Dopo aver eseguito la migrazione a Microsoft 365 Business Premium, si ha il difensore per Office 365. Per una panoramica, vedere [Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) . Per impostare, vedere [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)e [set up anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Per iniziare a utilizzare le etichette di riservatezza, vedere [Overview of Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) e [Create and Manage Sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.
