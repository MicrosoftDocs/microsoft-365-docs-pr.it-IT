---
title: Panoramica della configurazione
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Panoramica dei passaggi di configurazione per Microsoft 365 business.
ms.openlocfilehash: 4be0a8aa1b050ee3e20a045eb2c07666765118ed
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37440538"
---
# <a name="overview-of-setup"></a>Panoramica dell’installazione

La maggior parte dei passaggi di configurazione può essere effettuata nell'installazione guidata, ma anche le altre opzioni sono elencate.


## <a name="step-1-add-your-domain-and-users"></a>Passaggio 1: aggiungere il dominio e gli utenti

   - **[Aggiungere il dominio](set-up.md#add-your-domain-to-personalize-sign-in)** (se è stato acquistato il dominio durante l' [iscrizione](sign-up.md), questo passaggio è già stato fatto).

    - **Aggiungere utenti**. È possibile eseguire questa operazione in uno dei tre modi seguenti:
        - Nella [procedura guidata](set-up.md#add-users-in-the-wizard).
        - Utilizzare la sincronizzazione della directory per [aggiungere utenti utilizzando Azure ad Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) se si dispone di Active Directory locale.
        - È inoltre possibile [aggiungere gli utenti in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Passaggio 2: impostare i criteri di sicurezza e configurare i dispositivi 

  - Utilizzare l' [installazione guidata](set-up.md#protect-data-and-devices) per configurare i criteri di sicurezza e dispositivi. 
  - È inoltre possibile aggiungerne altri o modificarli in un secondo momento nell'interfaccia di [Amministrazione](view-policies-and-devices.md) e nel [portale di Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - Oltre alle impostazioni di sicurezza nell'installazione guidata, è possibile aumentare la sicurezza aggiungendo le seguenti impostazioni:

      - **Protezione antimalware per la posta elettronica**
      - **Collegamenti sicuri di Advanced Threat Protection (ATP)**
      - **Allegati sicuri di ATP**
      - **Anti-phishing ATP**
      - **Archiviazione Exchange Online**
      - **prevenzione della perdita di dati (DLP)**
      - **Protezione delle informazioni di Azure (PLAN1**)

          Per iniziare, vedere, [impostare i criteri di sicurezza avanzati](set-up-advanced-security.md).

        Vedere anche [i primi 10 modi per proteggere l'azienda Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) per una roadmap delle migliori procedure di sicurezza.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Passaggio 3: configurare e gestire i dispositivi Windows 10

   Quando si aggiunge un dispositivo Windows 10 ad Azure AD, i criteri impostati nel [passaggio 2](#step-2-set-up-security-policies-and-configure-devices) vengono applicati.

   - Windows 10 Pro è un [requisito indispensabile](pre-requisites-for-data-protection.md) per Microsoft 365 business, ma se si dispone di Windows 7 Pro, Windows 8 Pro o Windows 8,1 Pro, l'abbonamento dà diritto a un [aggiornamento a Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
    - Utilizzare l' [installazione guidata](set-up.md#protect-data-and-devices) per configurare i criteri per i dispositivi Windows 10.

## <a name="stes-4-install-office-365-business"></a>Stes 4: installare Office 365 business
- È possibile installare automaticamente Office nei dispositivi Windows utilizzando l' [installazione guidata](set-up.md#deploy-office-365-client-apps).
- [Installare automaticamente Office](auto-install-or-uninstall-office.md) dall'interfaccia di amministrazione.
- Consente agli utenti di [installare le app di Office](https://docs.microsoft.com/office365/admin/setup/install-applications) per Windows e i dispositivi.
     
## <a name="advanced"></a>Impostazioni avanzate
- **Utilizzare Autopilot per configurare nuovi dispositivi**
            
     È possibile usare [Windows Autopilot](add-autopilot-devices-and-profile.md) per preconfigurare automaticamente i **nuovi** dispositivi Windows 10 per un utente, ma potrebbe essere più facile ottenere un [partner](https://www.microsoft.com/solution-providers/search) che può eseguire questa operazione. È inoltre possibile accedere a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) e chiedere a un esperto di tecnologia cloud di configurare nuovi dispositivi acquistati per l'utente.

- **Accedere alle risorse locali**

     - Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 business per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale. Seguire la procedura descritta in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 business](manage-windows-devices.md) to set this up. Questo è il metodo preferito e i dispositivi in questo stato sono denominati dispositivi ibridi di Azure AD Uniti.

    - Se l'azienda dispone di un Active Directory locale che contiene alcune risorse locali, ad esempio condivisioni di file e stampanti, è possibile consentire ai dispositivi di Azure AD-join di accedere a tali risorse attenendosi alla procedura seguente: [accesso alle risorse locali da un Dispositivo di Azure AD-joined in Microsoft 365 business](access-resources.md).

  