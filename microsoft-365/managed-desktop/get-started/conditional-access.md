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

Dopo aver completato la registrazione in Microsoft Managed Desktop, potrebbe essere necessario modificare alcune impostazioni di gestione. Per controllare e regolare se necessario, eseguire la procedura seguente:

1. Esaminare le impostazioni di Microsoft Intune e Azure Active Directory descritte nella sezione successiva.
2. Se gli elementi sono validi per l'ambiente in uso, apportare le modifiche descritte.
3. Se si desidera verificare che tutte le impostazioni siano corrette, è possibile rieseguire lo [strumento di valutazione della conformità](https://aka.ms/mmdart) per verificare che non vi siano conflitti con Microsoft Managed Desktop.

> [!NOTE]
> Quando le operazioni continuano nei mesi seguenti, se si apportano modifiche dopo la registrazione ai criteri in Microsoft Intune, Azure Active Directory o Microsoft 365 che influiscono su Microsoft Managed Desktop, è possibile che Microsoft Managed Desktop possa smettere di funzionare correttamente. Per evitare problemi con il servizio, verificare le impostazioni specifiche descritte in [risolvere i problemi rilevati dallo strumento di valutazione della conformità](../get-ready/readiness-assessment-fix.md) prima di modificare i criteri elencati. È inoltre possibile rieseguire lo strumento di valutazione della conformità in qualsiasi momento.


## <a name="microsoft-intune-settings"></a>Impostazioni di Microsoft Intune

- Profilo di distribuzione Autopilot: se si utilizzano i criteri Autopilot, aggiornare ognuno per escludere i **dispositivi di lavoro moderni-tutti i** gruppi di Azure ad. Per aggiornarli, nella sezione **gruppi esclusi** in **assegnazioni** Selezionare i **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad creati durante la registrazione di Microsoft Managed Desktop. Microsoft Managed Desktop avrà creato anche un profilo Autopilot, che avrà il nome "ambiente di lavoro moderno" (il **profilo Autopilot del posto di lavoro moderno**). Quando si aggiornano i profili Autopilot personali, assicurarsi di *non* escludere i **dispositivi di lavoro moderni: tutti** i gruppi di Azure ad del **profilo Autopilot del posto di lavoro moderno** creato da Microsoft Managed Desktop.

- Criteri di accesso condizionale: se si creano nuovi criteri di accesso condizionale relativi ad Azure AD, Microsoft Intune o Microsoft Defender per endpoint dopo la registrazione di Microsoft Managed Desktop, escludere il gruppo di Azure AD degli **account del servizio di lavoro moderno** . Per i passaggi, vedere [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop gestisce criteri di accesso condizionale separati per limitare l'accesso a tali account. Per esaminare il criterio di accesso condizionale di Microsoft Managed Desktop (**ambiente di lavoro moderno – Secure Workstation**), andare a Microsoft Endpoint Manager e passare a **accesso condizionale** in **Endpoint Security**. Non modificare tutti i criteri di accesso condizionale di Azure AD creati da Microsoft Managed Desktop con il nome "ambiente di lavoro moderno".

- Autenticazione a più fattori: se si creano nuovi requisiti di autenticazione a più fattori nei criteri di accesso condizionale relativi ad Azure AD, Intune o Microsoft Defender per endpoint dopo la registrazione di Microsoft Managed Desktop, escludere il gruppo di Azure AD degli **account del servizio di lavoro moderno** . Per i passaggi, vedere [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop gestisce criteri di accesso condizionale separati per limitare l'accesso ai membri di questo gruppo. Per esaminare il criterio di accesso condizionale di Microsoft Managed Desktop (**ambiente di lavoro moderno**), passare a Microsoft Endpoint Manager e passare a **accesso condizionale** in **Endpoint Security**. 

- Windows 10 Update Ring: per tutti i criteri dell'anello di aggiornamento di Windows 10 creati, escludere i **dispositivi di lavoro moderni-tutti i** gruppi di Azure ad per ogni criterio. Per i passaggi, vedere [creare e assegnare gli anelli di aggiornamento](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings). Microsoft Managed Desktop avrà inoltre creato alcuni criteri per l'aggiornamento delle suonerie, ognuno dei quali avrà "luogo di lavoro moderno" nel nome (ad esempio, i criteri di aggiornamento dei luoghi di lavoro moderni [ **generali**], i criteri di aggiornamento sul posto di lavoro moderni [ **Fast]**, i criteri di aggiornamento sul posto di lavoro moderni [ **First]** e i **criteri di aggiornamento sul posto di lavoro** Quando si aggiornano i criteri personali, assicurarsi di *non* escludere i **dispositivi di lavoro moderni-tutti** i gruppi di Azure ad da quelli creati da desktop Microsoft.


## <a name="azure-active-directory-settings"></a>Impostazioni di Azure Active Directory

Reimpostazione della password self-service: se si utilizza la reimpostazione della password in modalità self-service per tutti gli utenti, modificare l'assegnazione per escludere gli account di servizio Microsoft Managed Desktop. Per modificare questa assegnazione, creare un gruppo dinamico di Azure AD per tutti gli utenti, *ad eccezione* degli account di servizio di Microsoft Managed Desktop, e quindi utilizzare tale gruppo per l'assegnazione invece di "tutti gli utenti".

Per facilitare l'individuazione e l'esclusione degli account di servizio, ecco un esempio di una query dinamica che è possibile utilizzare:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

In questa query sostituire @TENANT con il nome di dominio del tenant.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Passaggi per iniziare a utilizzare Microsoft Managed Desktop

1. [Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione](add-admin-contacts.md)
2. Modificare le impostazioni dopo la registrazione (questo articolo)
3. [Assegnare licenze](assign-licenses.md)
4. [Distribuire il Portale aziendale Intune](company-portal.md)
5. [Abilitare Enterprise State Roaming](enterprise-state-roaming.md)
6. [Configurare i dispositivi](set-up-devices.md)
7. [Preparare gli utenti a usare i dispositivi](get-started-devices.md)
8. [Distribuire le app](deploy-apps.md)
