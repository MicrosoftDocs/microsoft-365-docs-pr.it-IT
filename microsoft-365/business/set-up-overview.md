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
description: Per ulteriori informazioni, vedere la procedura di installazione di Microsoft 365 Business Premium, dalla sottoscrizione all'aggiunta di un dominio e degli utenti, alla configurazione dei criteri di sicurezza e altro ancora.
ms.openlocfilehash: 80243fac6ca2efcfca030b6ee1c1113c026a80ce
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402979"
---
# <a name="overview-of-setup"></a>Panoramica dell'installazione

Guardare un breve video sulla configurazione di Microsoft 365 Business Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

La maggior parte dei passaggi di installazione può essere effettuata nell'installazione guidata, ma anche le altre opzioni sono elencate.

## <a name="step-1-add-your-domain-and-users"></a>Passaggio 1: aggiungere il dominio e gli utenti

   - **[Aggiungere il dominio](set-up.md#add-your-domain-to-personalize-sign-in)** (se è stato acquistato il dominio durante l' [iscrizione](sign-up.md), questo passaggio è già stato fatto).

    - **Aggiungere utenti**. È possibile aggiungere utenti in uno dei tre modi seguenti:
        - Nella [procedura guidata](set-up.md#add-users-in-the-wizard).
        - Utilizzare la sincronizzazione della directory per [aggiungere utenti utilizzando Azure ad Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) se si dispone di Active Directory locale.
        - È inoltre possibile [aggiungere gli utenti in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Passaggio 2: impostare i criteri di sicurezza e configurare i dispositivi 

  - Utilizzare l' [installazione guidata](set-up.md#protect-your-organization) per configurare i criteri per i dispositivi. 
  - È inoltre possibile aggiungerne altri o modificarli in un secondo momento nell'interfaccia di [Amministrazione](view-policies-and-devices.md) e nel [portale di Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - L'installazione guidata consentirà anche di configurare le impostazioni di protezione delle minacce di base e di prevenzione della perdita dei dati
  
  Oltre alle impostazioni di sicurezza nell'installazione guidata, è possibile aumentare la sicurezza aggiungendo le seguenti impostazioni:

- **Protezione antimalware per la posta elettronica**
- **Anti-phishing ATP**
- **Archiviazione Exchange Online**
- **Protezione delle informazioni di Azure (PLAN1**)

Per iniziare, vedere [aumentare la protezione dalle minacce](increase-threat-protection.md) e configurare le funzionalità di [conformità](set-up-compliance.md).

Vedere anche [i primi 10 modi per proteggere il premio Microsoft 365 business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) per una roadmap delle migliori procedure di sicurezza.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Passaggio 3: configurare e gestire i dispositivi Windows 10

Dopo aver eseguito la configurazione guidata, è necessario proctect tutti i computer di Windwos 10 nell'organizzazione.
  
- Windows 10 Pro è un [prerequisito](pre-requisites-for-data-protection.md) per Microsoft 365 Business Premium, ma se si dispone di Windows 7 Pro, Windows 8 Pro o Windows 8,1 Pro, l'abbonamento dà diritto a un [aggiornamento a Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
- Seguire la procedura descritta in [Secure Windows 10 PC](secure-win-10-pcs.md) per impostare i criteri per i dispositivi Windows 10.

Quando si aggiunge un dispositivo Windows 10 ad Azure AD, i criteri impostati per i computer Windows 10 vengono applicati. Per ulteriori informazioni, vedere [configurare i dispositivi Windows per gli utenti di Microsoft 365](set-up-windows-devices.md).

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Passaggio 4: installazione di Microsoft 365 Apps for business
- È possibile installare automaticamente Office nei dispositivi Windows utilizzando l' [installazione guidata](set-up.md#deploy-office-365-client-apps).
- Consente agli utenti di [installare le app di Office](https://docs.microsoft.com/office365/admin/setup/install-applications) per Windows e i dispositivi.
     
## <a name="advanced"></a>Impostazioni avanzate
- **Utilizzare Autopilot per configurare nuovi dispositivi**
            
     È possibile usare [Windows Autopilot](add-autopilot-devices-and-profile.md) per preconfigurare automaticamente i **nuovi** dispositivi Windows 10 per un utente, ma potrebbe essere più facile ottenere un [partner](https://www.microsoft.com/solution-providers/search) che può eseguire questa operazione. È inoltre possibile accedere a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)e chiedere a un esperto di tecnologia cloud di configurare nuovi dispositivi acquistati.

- **Accedere alle risorse locali**

     - Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale. Seguire la procedura descritta in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) per configurarlo. Questo è il metodo preferito e i dispositivi in questo stato sono denominati dispositivi ibridi di Azure AD Uniti.

    - Se l'azienda dispone di un Active Directory locale che contiene alcune risorse locali (ad esempio condivisioni di file e stampanti), è possibile consentire ai dispositivi di Azure AD-join di accedere a tali risorse attenendosi alla procedura seguente: [accesso alle risorse locali da un dispositivo di Azure ad-join in Microsoft 365 Business Premium](access-resources.md).

## <a name="see-also"></a>Vedere anche

[Video di formazione su Microsoft 365 per le aziende](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
