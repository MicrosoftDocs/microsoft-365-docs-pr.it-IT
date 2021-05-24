---
title: Eseguire la migrazione a Microsoft 365 Business da Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
description: Se hai un abbonamento Office 365 E3 ma non hai più di 300 dipendenti, valuta la possibilità di passare a Microsoft 365 Business Premium.
ms.openlocfilehash: d139d07c946ff3efed3db3a73eb5e1a4ae66c190
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623606"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migrazione da Office 365 E3 a Microsoft 365 Business Premium

Microsoft 365 Business Premium ha tutto il necessario per la tua piccola azienda, combinando le migliori app di produttività basate sul cloud con semplici funzionalità di gestione e sicurezza dei dispositivi. Se attualmente si dispone di una sottoscrizione Office 365 E3, ma non si hanno più di 300 dipendenti, è consigliabile passare a Microsoft 365 Business Premium per aggiungere funzionalità di sicurezza.

La migrazione è semplice: prima di tutto si cambia licenza e vengono mantenuti tutti i dati e le informazioni utente nell'abbonamento corrente. Dopo la migrazione, è necessario configurare le funzionalità aggiunte in Microsoft 365 Business Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Differenze tra Office 365 E3 e Microsoft 365 Business Premium

Questa tabella mostra le differenze tra Microsoft 365 Business Premium e Office 365 E3.

| Funzionalità    | Supporto in Microsoft 365 Business Premium    | Supporto in Office 365 E3 |
|:-------|:-----|:-----|
| **Locale**        | | |
| Office app<sup>1</sup>    | Microsoft 365 Apps for business    | Microsoft 365 Apps for enterprise |
| **App per la produttività cloud**        | | |
| Exchange Online e Outlook    | Limite di archiviazione di 50 GB per cassetta postale e limite Archiviazione Exchange Online    | Limite di archiviazione di 100 GB per cassetta postale e limite Archiviazione Exchange Online |
| Teams    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png) | 
| OneDrive for Business    | Limite di archiviazione di 1 TB per utente    | Illimitati | 
| Yammer, SharePoint Online, Planner, Stream    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png) |
| **Threat Protection**        | | |
| Defender per Office 365 Piano 1 | ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | Non incluso, ma può essere aggiunto in |
| **Gestione delle identità**        | | |
| Reimpostazione della password self-service per account Azure Active Directory (Azure AD), Autenticazione a più fattori (MFA) di Azure AD, Accesso condizionale, writeback delle password per le identità locali|     ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| **Gestione di dispositivi e app**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| Attivazione di computer condivisi|     ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluso con Office 365 E3](../media/check-mark.png)| 
| Aggiornare i diritti Windows 10 Pro licenze win 7/8.1 Pro licenze|     ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)    ||
| **Protezione delle informazioni**        | | |
|Prevenzione della perdita di dati di Office 365|    ![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)|![Incluso con Office 365 E3](../media/check-mark.png)|
|Azure Information Protection Piano 1, BitLocker sicurezza|![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)||
|Azure Information Protection Piano 1, etichette di riservatezza|![Incluso con Microsoft 365 Business Premium](../media/check-mark.png)||
|**Licenza Accesso client (diritti CAL)**|||
|Enterprise Cal Suite (Exchange, SharePoint, Skype)||![Incluso con Office 365 E3](../media/check-mark.png)|

<sup>1</sup> La Microsoft 365 Business Premium delle app Office non include l'attivazione di contratti multilicenza tramite Criteri di gruppo, telemetria delle app, controlli di aggiornamento, confronto e richiesta di informazioni sui fogli di calcolo o business intelligence.

## <a name="migration"></a>Migrazione

Per eseguire la migrazione dell'abbonamento, vedere [Modificare](../commerce/subscriptions/change-plans-manually.md) i piani manualmente per istruzioni se si desidera spostare solo alcune persone Microsoft 365 Business Premium. È inoltre possibile [aggiornare automaticamente](../commerce/subscriptions/upgrade-to-different-plan.md)tutti gli utenti o collaborare con un partner per spostare la sottoscrizione e le licenze di E3 in una sottoscrizione Microsoft 365 Business Premium elettronica.
Nelle sezioni seguenti vengono descritte le modifiche da apportare, se presenti, e le operazioni che è possibile eseguire dopo la migrazione.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 Dati e configurazione della sottoscrizione E3
Non è necessario apportare modifiche alla sottoscrizione o ai dati correnti prima di eseguire la migrazione, tra cui:

- Configurazione della sottoscrizione, ad esempio record DNS e nomi di dominio.
- Account utente e di gruppo e impostazioni di autenticazione, ad esempio l'autenticazione a più fattori o i criteri di accesso condizionale.
- Configurazioni dei servizi di produttività e relativi dati, ad esempio Teams, cassette postali Exchange Online, siti di SharePoint Online, cartelle OneDrive for Business e OneNote blocchi appunti.
- Office le applicazioni verranno ridimensionate automaticamente. Office 365 licenze moderne controllano l'assegnazione delle licenze dell'utente ogni 72 ore e convertono le applicazioni Office nella versione corrispondente all'abbonamento dell'utente.

### <a name="windows-10"></a>Windows 10

Se il Windows non è già in Windows Pro Creator, aggiornali [a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Configurare criteri per proteggere i dispositivi e i file degli utenti

> [!NOTE]
> Se si configurano Office 365 e dispositivi MDM, tali dispositivi  verranno elencati nella pagina Dispositivi nell'interfaccia di amministrazione Microsoft 365 aziendale. Tutti i criteri impostati verranno visualizzati nell'elenco dei criteri classici nel [portale di Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

Dopo aver assegnato le licenze a Microsoft 365 Business Premium, puoi iniziare a proteggere i dispositivi e i file degli utenti.

Se tutti gli utenti dell'organizzazione sono stati aggiornati a Microsoft 365 Business Premium, verrà visualizzata la configurazione guidata nella home page e sarà possibile seguire la procedura di configurazione [di Microsoft 365 Business Premium](set-up.md) nella procedura di configurazione guidata per proteggere file e dispositivi mobili.

Puoi anche completare questi passaggi nella pagina Dispositivi:
  
1. Nell'interfaccia di amministrazione, nel riquadro di spostamento sinistro, vai a **Criteri** \> **dispositivi.**

2. Nella pagina **Criteri dispositivo** scegliere **Aggiungi**.

3. Nel riquadro **Aggiungi** criterio assegna un nome al criterio e quindi scegli un **tipo di criterio** nell'elenco a discesa.

     Puoi configurare criteri di applicazione per la protezione dei file nei dispositivi Android e iPhone, nonché Windows 10 e puoi configurare i criteri di configurazione dei dispositivi per i dispositivi Windows 10 aziendali. Per informazioni dettagliate, vedere i collegamenti seguenti:

  - [Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS](app-protection-settings-for-android-and-ios.md)

  - [Configurare le impostazioni di protezione delle app per i dispositivi Windows 10](protection-settings-for-windows-10-devices.md)

  - [Impostare le impostazioni di protezione dei dispositivi Windows 10 PC](protection-settings-for-windows-10-pcs.md)
  
4. Dopo aver configurato i criteri, tu e i tuoi dipendenti puoi configurare i dispositivi:

  - Vedi [Configurare i Windows per Microsoft 365 Business Premium utenti](set-up-windows-devices.md) per la procedura per Windows dispositivi. 

  - Vedi [Configurare i dispositivi mobili per Microsoft 365 Business Premium utenti per](set-up-mobile-devices.md) la procedura per telefoni Android e iPhone. 
  
### <a name="mailbox-size"></a>Dimensione cassetta postale

Microsoft 365 Business Premium ha un limite di archiviazione di 50 GB in quanto utilizza Exchange Online Piano 1. Durante la migrazione a Microsoft 365 Business Premium, se uno degli utenti supera i 50 GB di spazio di archiviazione delle cassette postali, è consigliabile assegnare a questo utente un piano 2 di Exchange Online e rimuovere il piano Exchange Online 1 poiché non è possibile assegnare entrambi.

### <a name="threat-protection"></a>Protezione dalle minacce

Dopo la migrazione a Microsoft 365 Business Premium, hai Defender per Office 365. Per [una panoramica, vedi Microsoft Defender Office 365](../security/office-365-security/defender-for-office-365.md) informazioni generali. Per la configurazione, vedere [configurare collegamenti](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)sicuri, [configurare](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)allegati sicuri e configurare [anti-phishing in Defender per Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Per iniziare a usare le etichette di riservatezza, vedi [Panoramica delle etichette di riservatezza](../compliance/sensitivity-labels.md) e video sulla creazione e gestione delle etichette [di](../business-video/create-sensitivity-labels.md) riservatezza.

## <a name="related-content"></a>Contenuto correlato

[Modificare i piani manualmente](../commerce/subscriptions/change-plans-manually.md) (articolo)\
[Aggiornare Windows dispositivi a Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (video)\
[Configurare le impostazioni di protezione delle app per i dispositivi Android](app-protection-settings-for-android-and-ios.md) o iOS (articolo)\
[Impostare o modificare le impostazioni di protezione delle applicazioni Windows 10 dispositivi](protection-settings-for-windows-10-devices.md) mobili (articolo)\
[]

