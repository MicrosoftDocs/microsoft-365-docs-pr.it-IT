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
ms.openlocfilehash: ca919798480698f92bba094c3755b3eccce30888
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867971"
---
# <a name="adjust-settings-after-enrollment"></a>Modificare le impostazioni dopo la registrazione

Dopo aver completato la registrazione in Microsoft Managed Desktop, potrebbe essere necessario modificare alcune impostazioni di gestione. Per verificare e modificare, se necessario, attenersi alla seguente procedura:

1. Esaminare le impostazioni di Microsoft Intune e Azure Active Directory descritte nella sezione successiva.
2. Se uno degli elementi si applica all'ambiente, apportare le modifiche descritte.
3. Se si desidera verificare che tutte le impostazioni siano [](https://aka.ms/mmdart) corrette, è possibile eseguire di nuovo lo strumento di valutazione della conformità per assicurarsi che non vi siano conflitti con Microsoft Managed Desktop.

> [!NOTE]
> Mentre le operazioni continuano nei mesi successivi, se si apportano modifiche dopo la registrazione ai criteri in Microsoft Intune, Azure Active Directory o Microsoft 365 che influiscono su Microsoft Managed Desktop, è possibile che Microsoft Managed Desktop non funzioni correttamente. Per evitare problemi con il servizio, controllare le impostazioni specifiche descritte in [Risolvere](../get-ready/readiness-assessment-fix.md) i problemi rilevati dallo strumento di valutazione della conformità prima di modificare i criteri elencati. È inoltre possibile eseguire di nuovo lo strumento di valutazione della conformità in qualsiasi momento.


## <a name="microsoft-intune-settings"></a>Impostazioni di Microsoft Intune

- Profilo di distribuzione Autopilot: se usi criteri Autopilot, aggiorna ognuno di essi per escludere i dispositivi workplace moderni **- Tutti i** gruppi di Azure AD. Per aggiornarli, nella sezione **Gruppi** esclusi **in** Assegnazioni selezionare il gruppo Dispositivi aziendali moderni **-** Tutti Azure AD creato durante la registrazione di Microsoft Managed Desktop. Microsoft Managed Desktop avrà anche creato un profilo Autopilot, che avrà "Ambiente di lavoro moderno" nel nome **(il profilo Autopilot** di Workplace moderno). Quando aggiorni i tuoi profili Autopilot, assicurati di non escludere il gruppo Modern **Workplace Devices -All** Azure AD dal **profilo Autopilot** workplace moderno creato da Microsoft Managed Desktop. 

- Criteri di accesso condizionale: se si creano nuovi criteri di accesso condizionale correlati ad Azure AD,  Microsoft Intune o Microsoft Defender for Endpoint dopo la registrazione di Microsoft Managed Desktop, escludere il gruppo Azure AD account del servizio aziendale moderno. Per la procedura, vedere [Accesso condizionale: Utenti e gruppi.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop gestisce criteri di accesso condizionale separati per limitare l'accesso a questi account. Per esaminare i criteri di accesso condizionale di Microsoft Managed Desktop (**Modern Workplace – Secure Workstation),** passare a Microsoft Endpoint Manager e passare ad Accesso **condizionale** in **Endpoint Security.** Non modificare i criteri di accesso condizionale di Azure AD creati da Microsoft Managed Desktop con "Area di lavoro moderna" nel nome.

- Autenticazione a più fattori: se si creano nuovi requisiti di autenticazione a più fattori nei criteri di accesso condizionale  correlati ad Azure AD, Intune o Microsoft Defender for Endpoint dopo la registrazione di Microsoft Managed Desktop, escludere il gruppo Azure AD account del servizio aziendale moderno. Per la procedura, vedere [Accesso condizionale: Utenti e gruppi.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop gestisce criteri di accesso condizionale separati per limitare l'accesso ai membri di questo gruppo. Per esaminare i criteri di accesso condizionale di Microsoft Managed Desktop ( Area di lavoro moderna **-**), passare a Microsoft Endpoint Manager e passare ad **Accesso condizionale** in Endpoint **Security.** 

- Anello di aggiornamento di Windows 10: per tutti i criteri dell'anello di aggiornamento di Windows 10 che hai creato, escludi il gruppo **Modern Workplace Devices -All** Azure AD da ogni criterio. Per la procedura, vedere [Creare e assegnare anelli di aggiornamento.](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) Microsoft Managed Desktop avrà anche creato alcuni criteri dell'anello di aggiornamento, che avranno tutti "Modern Workplace" nel nome (ad esempio, Modern **Workplace Update Policy [Broad]**, **Modern Workplace Update Policy [Fast]**, **Modern Workplace Update Policy [First]** e **Modern Workplace Update Policy [Test]**). Quando aggiorni i tuoi criteri, assicurati di non *escludere* il gruppo Modern Workplace **Devices -All** Azure AD da quelli creati da Microsoft Managed Desktop.


## <a name="azure-active-directory-settings"></a>Impostazioni di Azure Active Directory

Reimpostazione della password in modalità self-service: se si utilizza la reimpostazione della password in modalità self-service per tutti gli utenti, modificare l'assegnazione per escludere gli account del servizio Microsoft Managed Desktop. Per modificare questa assegnazione, creare un gruppo dinamico di Azure AD per tutti gli utenti ad eccezione degli account del servizio *Microsoft* Managed Desktop e quindi usare tale gruppo per l'assegnazione anziché "tutti gli utenti".

Per individuare ed escludere gli account di servizio, di seguito è riportato un esempio di query dinamica che è possibile utilizzare:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

In questa query, sostituire @TENANT con il nome di dominio del tenant.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Procedura per iniziare a usare Microsoft Managed Desktop

1. [Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione](add-admin-contacts.md)
2. Modificare le impostazioni dopo la registrazione (questo articolo)
3. [Assegnare licenze](assign-licenses.md)
4. [Distribuire il Portale aziendale Intune](company-portal.md)
5. [Abilitare Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurare i dispositivi](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. [Distribuire le app](deploy-apps.md)
