---
title: Informazioni sulle impostazioni dei profili AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: I profili Autopilot consentono di controllare il modo in cui viene installato Windows nei dispositivi utente. I profili contengono impostazioni predefinite e facoltative come l'installazione di Skip Cortana.
ms.openlocfilehash: 912a24e3d458986a4bcf7dcf903f80211996aca2
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38321786"
---
# <a name="about-autopilot-profile-settings"></a>Informazioni sulle impostazioni dei profili AutoPilot

## <a name="autopilot-profile-settings"></a>Impostazioni del profilo Autopilot

È possibile utilizzare i profili Autopilot per controllare la modalità di installazione di Windows nei dispositivi utente. I profili contengono le impostazioni seguenti.
  
 **Funzionalità predefinite del pilota automatico (obbligatorio) impostate automaticamente:**
  
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|Ignorare la registrazione di Cortana, OneDrive e OEM  <br/> |Ignora l'installazione delle app consumer come Cortana e Personal OneDrive. L'utente del dispositivo può installarli in un secondo momento, purché l'utente sia un amministratore locale del dispositivo. La registrazione del produttore originale viene ignorata perché il dispositivo verrà gestito da Microsoft 365 Business.  <br/> |
|Esperienza di accesso con il tuo marchio aziendale  <br/> |Se la tua azienda ha una [pagina di accesso Aggiungi la tua azienda a Office 365](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), l'utente del dispositivo otterrà quell'esperienza al momento dell'accesso.  <br/> |
|Registrazione automatica in MDM con account AAD configurati.  <br/> |L'identità dell'utente verrà gestita da Azure Active Directory e gli utenti si consentiranno di accedere a Windows e Office 365 con le proprie credenziali di Microsoft 365 business.  <br/> |
   
 **Impostazioni facoltative:**
  
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|Ignora impostazioni della privacy (disattivato per impostazione predefinita)  <br/> |Se questa opzione è impostata su **attivato**, l'utente del dispositivo non vedrà il contratto di licenza per il dispositivo e Windows al primo accesso.  <br/> |
|Non consentire all'utente di diventare l'amministratore locale  <br/> |Se questa opzione è impostata su **attivato**, l'utente del dispositivo non potrà installare le app personali, ad esempio Cortana.<br/> |
   
