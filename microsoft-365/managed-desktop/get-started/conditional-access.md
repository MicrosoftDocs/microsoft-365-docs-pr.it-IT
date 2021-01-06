---
title: Modificare le impostazioni dopo la registrazione
description: Come escludere determinati account Microsoft
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d7fe410f114d43d4f6c983aaf23d949298635318
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760104"
---
# <a name="adjust-settings-after-enrollment"></a>Modificare le impostazioni dopo la registrazione

Dopo aver completato la registrazione in Microsoft Managed Desktop, è necessario modificare determinate impostazioni di Microsoft Intune e Azure Active Directory (Azure AD) per consentire la gestione e mantenere la sicurezza. Impostare le impostazioni seguenti per escludere i gruppi di Azure AD che contengono i dispositivi e gli utenti di Microsoft Managed Desktop. Per i passaggi da escludere i gruppi, vedere [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).

> [!NOTE]
> Se si apportano modifiche dopo la registrazione ai criteri in Microsoft Intune, Azure Active Directory o Microsoft 365, è possibile che Microsoft Managed Desktop smetta di funzionare correttamente. Per evitare problemi con le operazioni di Microsoft Managed Desktop, controllare le impostazioni specifiche descritte in [correggere i problemi trovati dallo strumento di valutazione della conformità](../get-ready/readiness-assessment-fix.md) prima di modificare i criteri.


## <a name="microsoft-intune-settings"></a>Impostazioni di Microsoft Intune

- Profilo di distribuzione Autopilot: Escludi i **dispositivi di lavoro moderni-tutti i gruppi di**  Azure ad. Per i passaggi, vedere [registrazione dei dispositivi Windows in Intune tramite Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).
- Criteri di accesso condizionale: Escludi il gruppo di Azure AD degli **account del servizio di lavoro moderno** . Per i passaggi, vedere [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).
- Autenticazione a più fattori: verificare che tutti i criteri di accesso condizionale che richiedono l'autenticazione a più fattori escludano il gruppo di Azure AD degli **account di servizio sul posto di lavoro moderno** . Per ulteriori informazioni, vedere [criteri di accesso condizionale](../get-ready/readiness-assessment-fix.md#conditional-access-policies) e [accesso condizionale: require Mae per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).
- Baseline di sicurezza: Escludi i **dispositivi di lavoro moderni-tutti i gruppi di**  Azure ad. Per i passaggi, vedere [utilizzare le linee di base di sicurezza per configurare i dispositivi Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).
- Ring Windows 10 Update: Escludi i **dispositivi di lavoro moderni-tutti i gruppi di**  Azure ad. Per i passaggi, vedere [gestire gli aggiornamenti software di Windows 10 in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).


## <a name="azure-active-directory-settings"></a>Impostazioni di Azure Active Directory

Reimpostazione della password in modalità self-service: scegliere l'impostazione **selezionata** , quindi selezionare **dispositivi di lavoro moderni-tutti i gruppi di** Azure ad. Per ulteriori informazioni, vedere [esercitazione: consentire agli utenti di sbloccare l'account o reimpostare le password tramite la reimpostazione della password self-service di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Passaggi per iniziare a utilizzare Microsoft Managed Desktop

1. [Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione](add-admin-contacts.md)
2. Modificare le impostazioni dopo la registrazione (questo articolo)
3. [Assegnare licenze](assign-licenses.md)
4. [Distribuire il Portale aziendale Intune](company-portal.md)
5. [Abilitare Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurare i dispositivi](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. [Distribuire le app](deploy-apps.md)
