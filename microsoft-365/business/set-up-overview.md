---
title: Panoramica dell'installazione
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informazioni sui passaggi di configurazione per Microsoft 365 Business Premium, dalla sottoscrizione, all'aggiunta di un dominio e di utenti, alla configurazione dei criteri di sicurezza e altro ancora.
ms.openlocfilehash: 9d92aefb3b5666bb7c2fd2e13c9a00f074f107a7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912491"
---
# <a name="overview-of-setup"></a>Panoramica dell'installazione

Guarda un breve video sulla configurazione di Microsoft 365 Business Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Se il video è stato utile, consultare la [serie dei corsi di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

La maggior parte dei passaggi di configurazione può essere eseguita nella configurazione guidata, ma sono elencate anche le altre opzioni.

## <a name="step-1-add-your-domain-and-users"></a>Passaggio 1: Aggiungere il dominio e gli utenti

   - **[Aggiungi il dominio](set-up.md#add-your-domain-to-personalize-sign-in)** (se hai acquistato il dominio durante l'iscrizione, questo passaggio è già stato eseguito). [](sign-up.md)

   - **Aggiungere utenti**. È possibile aggiungere utenti in uno dei tre modi seguenti:
        - Nella configurazione [guidata](set-up.md#add-users-in-the-wizard).
        - Usare la sincronizzazione della directory [per aggiungere utenti tramite Azure AD Connect](../enterprise/set-up-directory-synchronization.md) se si dispone di active directory locale.
        - È inoltre possibile [aggiungere utenti in un secondo momento](../admin/add-users/add-users.md) nell'interfaccia di amministrazione.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Passaggio 2: Configurare i criteri di sicurezza e configurare i dispositivi 

  - Usa la [configurazione guidata per](set-up.md#protect-your-organization) configurare i criteri dei dispositivi. 
  - Puoi anche aggiungerne altri o modificarli in un secondo momento [nell'interfaccia di amministrazione](view-policies-and-devices.md) e nel portale di [Intune.](/intune/tutorial-walkthrough-intune-portal)
  - L'installazione guidata configura anche le impostazioni di base per la protezione dalle minacce e la prevenzione della perdita di dati.
  
  Oltre alle impostazioni di sicurezza dell'installazione guidata, è possibile aumentare la sicurezza aggiungendo le impostazioni seguenti:

- **Protezione antimalware della posta elettronica**
- **Anti-phishing in Defender per Office 365**
- **Archiviazione Exchange Online**
- **Azure Information Protection (Piano1)**

Per iniziare, vedi Aumentare [la protezione dalle minacce](increase-threat-protection.md) e configurare le funzionalità di [conformità.](set-up-compliance.md)

Vedi anche i 10 modi principali per proteggere [Microsoft 365 Business Premium](/office365/admin/security-and-compliance/secure-your-business-data) per una road map delle procedure consigliate per la sicurezza.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Passaggio 3: Configurare e gestire i dispositivi Windows 10

Dopo aver completato la configurazione guidata, è necessario proteggere tutti i computer Windows 10 nell'organizzazione.
  
- Windows 10 Pro è un [prerequisito](pre-requisites-for-data-protection.md) per Microsoft 365 Business Premium, ma se hai Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, l'abbonamento ti autorizza a un aggiornamento a [Windows 10 Pro.](./upgrade-to-windows-pro-creators-update.md)
- Segui i passaggi descritti in Proteggere i [PC Windows 10 per](secure-win-10-pcs.md) configurare i criteri per i dispositivi Windows 10.

Quando si aggiunge un dispositivo Windows 10 ad Azure AD, vengono applicati i criteri impostati per i computer Windows 10. Per altre informazioni, vedi [Configurare i dispositivi Windows per gli utenti di Microsoft 365.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Passaggio 4: Installare Microsoft 365 Apps for business
- È possibile installare automaticamente Office nei dispositivi Windows utilizzando [l'installazione guidata.](set-up.md#deploy-office-365-client-apps)
- Consenti agli [utenti di installare le app di Office](/office365/admin/setup/install-applications) per Windows e i dispositivi.
     
## <a name="advanced"></a>Impostazioni avanzate
- **Usare Autopilot per configurare nuovi dispositivi**
            
     Puoi usare [Windows Autopilot](add-autopilot-devices-and-profile.md) per **pre-configurare** automaticamente i nuovi dispositivi Windows 10 per un utente, ma potrebbe essere più semplice ottenere un [partner](https://www.microsoft.com/solution-providers/search) che possa farlo automaticamente. Puoi anche accedere a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)e chiedere a un esperto di tecnologia cloud di configurare nuovi dispositivi acquistati.

- **Accedere alle risorse locali**

     - Se l'organizzazione usa Windows Server Active Directory in locale, puoi configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale. Segui i passaggi descritti in Abilitare i dispositivi Windows 10 aggiunti al dominio per essere gestiti da [Microsoft 365 Business Premium](manage-windows-devices.md) per configurare questa configurazione. Questo è il metodo preferito e i dispositivi in questo stato sono denominati dispositivi aggiunti ad Azure AD ibridi.

    - Se l'azienda ha un Active Directory locale che contiene alcune risorse locali (ad esempio condivisioni file e stampanti), è possibile concedere ai dispositivi aggiunti ad Azure AD l'accesso a queste risorse seguendo la procedura seguente: Accedere alle risorse locali da un dispositivo aggiunto ad [Azure AD in Microsoft 365 Business Premium.](access-resources.md)

## <a name="see-also"></a>Vedere anche

[Video di formazione su Microsoft 365 per le aziende](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)