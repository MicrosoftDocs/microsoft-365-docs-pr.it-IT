---
title: Informazioni sulle impostazioni dei profili AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: I profili Autopilot consentono di controllare il modo in cui viene installato Windows nei dispositivi utente. I profili contengono impostazioni predefinite e facoltative come l'installazione di Skip Cortana.
ms.openlocfilehash: d43a15e5f3dc83596b5c23dd0ceb416b24810298
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276942"
---
# <a name="about-autopilot-profile-settings"></a>Informazioni sulle impostazioni dei profili AutoPilot

## <a name="autopilot-profile-settings"></a>Impostazioni dei profili AutoPilot

È possibile controllare la modalità di installazione di Windows nei dispositivi utente utilizzando i profili Autopilot. I profili contengono le impostazioni seguenti.
  
 **Funzionalità predefinite del pilota automatico (obbligatorio) impostate automaticamente:**
  
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|Ignora Cortana, OneDrive e la registrazione OEM  <br/> |Ignora l'installazione delle app consumer come Cortana e Personal OneDrive. L'utente del dispositivo potrà installarle successivamente, purché sia un amministratore locale del dispositivo. La registrazione del produttore originale viene ignorata perché il dispositivo verrà gestito da Microsoft 365 Business.  <br/> |
|Esperienza di accesso con il tuo marchio aziendale  <br/> |Se la tua azienda ha una [pagina di accesso Aggiungi la tua azienda a Office 365](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), l'utente del dispositivo otterrà quell'esperienza al momento dell'accesso.  <br/> |
|Registrazione automatica in MDM con account AAD configurati.  <br/> |L'identità dell'utente verrà gestita da Azure Active Directory e l'utente eseguirà l'accesso a Windows e Office 365 con le proprie credenziali di Microsoft 365 Business.  <br/> |
   
 **Impostazioni facoltative:**
  
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|Ignora impostazioni della privacy (disattivato per impostazione predefinita)  <br/> |Se questa opzione è impostata su **attivato**, l'utente del dispositivo non vedrà il contratto di licenza per il dispositivo e Windows al primo accesso.  <br/> |
|Non consentire all'utente di diventare l'amministratore locale  <br/> |Se questa opzione è impostata su **attivato**, l'utente del dispositivo non potrà installare le app personali, ad esempio Cortana.  <br/> |
   
