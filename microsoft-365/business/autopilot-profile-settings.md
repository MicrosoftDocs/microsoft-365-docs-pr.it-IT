---
title: Informazioni sulle impostazioni dei profili AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: I profili AutoPilot consentono di controllare come Windows vengono installati nei dispositivi degli utenti. I profili contengono impostazioni predefinite e facoltative come ignorare l'installazione di Cortana.
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578508"
---
# <a name="about-autopilot-profile-settings"></a>Informazioni sulle impostazioni dei profili AutoPilot

## <a name="autopilot-profile-settings"></a>Impostazioni del profilo AutoPilot

Puoi usare i profili AutoPilot per controllare la modalità Windows'installazione nei dispositivi degli utenti. I profili contengono le impostazioni seguenti.
  
 **Funzionalità predefinite di AutoPilot (obbligatorie) impostate automaticamente:**
  
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|Ignorare la registrazione di Cortana, OneDrive e OEM  <br/> |Ignora l'installazione di app consumer come Cortana e OneDrive. L'utente del dispositivo può installarlo in un secondo momento, purché l'utente sia un amministratore locale nel dispositivo. La registrazione del produttore originale viene ignorata perché il dispositivo verrà gestito da Microsoft 365 Business Premium.  <br/> |
|Esperienza di accesso con il tuo marchio aziendale  <br/> |Se la tua azienda ha una pagina Aggiungi il marchio aziendale [Microsoft 365 accedi,](../admin/setup/customize-sign-in-page.md)l'utente del dispositivo otterrà tale esperienza quando esegue l'accesso.  <br/> |
|Registrazione automatica in MDM con account AAD configurati.  <br/> |L'identità utente verrà gestita da Azure Active Directory e gli utenti accederanno a Windows e Microsoft 365 con le Microsoft 365 Business Premium credenziali.  <br/> |
   
 **Impostazioni facoltative:**
  
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|Ignora impostazioni della privacy (disattivato per impostazione predefinita)  <br/> |Se questa opzione è impostata su **attivato**, l'utente del dispositivo non vedrà il contratto di licenza per il dispositivo e Windows al primo accesso.  <br/> |
|Non consentire all'utente di diventare l'amministratore locale  <br/> |Se questa opzione è impostata su **attivato**, l'utente del dispositivo non potrà installare le app personali, ad esempio Cortana.<br/> |
