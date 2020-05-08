---
title: Informazioni sulle impostazioni dei profili AutoPilot
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 0c706d12ba262856ff40ea3bee57c64234fd77f7
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165842"
---
# <a name="about-autopilot-profile-settings"></a>Informazioni sulle impostazioni dei profili AutoPilot

## <a name="autopilot-profile-settings"></a>Impostazioni del profilo Autopilot

È possibile utilizzare i profili Autopilot per controllare la modalità di installazione di Windows nei dispositivi utente. I profili contengono le impostazioni seguenti.
  
 **Funzionalità predefinite del pilota automatico (obbligatorio) impostate automaticamente:**
  
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|Ignorare la registrazione di Cortana, OneDrive e OEM  <br/> |Ignora l'installazione delle app consumer come Cortana e Personal OneDrive. L'utente del dispositivo può installarli in un secondo momento, purché l'utente sia un amministratore locale del dispositivo. La registrazione del produttore originale viene ignorata perché il dispositivo sarà gestito da Microsoft 365 Business Premium.  <br/> |
|Esperienza di accesso con il tuo marchio aziendale  <br/> |Se l'azienda dispone [di un marchio Aggiungi la propria società alla pagina di accesso a Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), l'utente del dispositivo otterrà quell'esperienza al momento dell'accesso.  <br/> |
|Registrazione automatica in MDM con account AAD configurati.  <br/> |L'identità dell'utente verrà gestita da Azure Active Directory e gli utenti accederanno a Windows e Microsoft 365 con le credenziali di Microsoft 365 Business Premium.  <br/> |
   
 **Impostazioni facoltative:**
  
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|Ignora impostazioni della privacy (disattivato per impostazione predefinita)  <br/> |Se questa opzione è impostata su **attivato**, l'utente del dispositivo non vedrà il contratto di licenza per il dispositivo e Windows al primo accesso.  <br/> |
|Non consentire all'utente di diventare l'amministratore locale  <br/> |Se questa opzione è impostata su **attivato**, l'utente del dispositivo non potrà installare le app personali, ad esempio Cortana.<br/> |
   
