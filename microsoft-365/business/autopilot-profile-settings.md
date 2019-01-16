---
title: Informazioni sulle impostazioni dei profili AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: Profili autoPilot consentono di controllare la modalità Windows Ottiene installazione nei dispositivi utente. I profili contengono predefinito e impostazioni facoltative come annullare l'installazione Cortana.
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868305"
---
# <a name="about-autopilot-profile-settings"></a>Informazioni sulle impostazioni dei profili AutoPilot

## <a name="autopilot-profile-settings"></a>Impostazioni dei profili AutoPilot

È possibile controllare come Windows Ottiene installato nei dispositivi utente mediante i profili AutoPilot. I profili contengono le impostazioni seguenti.
  
 **AutoPilot le funzionalità predefinite (obbligatoria) che vengono impostate automaticamente:**
  
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|Ignora Cortana, OneDrive e la registrazione OEM  <br/> |Ignora l'installazione delle App consumer come Cortana e OneDrive personale. Utente del dispositivo può installare questi successive purché è un amministratore locale nel dispositivo. Registrazione produttore originale viene ignorata in quanto il dispositivo verrà gestito da Microsoft 365 Business.  <br/> |
|Esperienza di accesso con il tuo marchio aziendale  <br/> |Se la società dispone di una [personalizzazione in aggiunta all'azienda a Office 365 pagina di accesso](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), l'utente dispositivo otterrà tale esperienza durante l'accesso.  <br/> |
|Registrazione automatica in MDM con account AAD configurati.  <br/> |L'identità dell'utente verrà gestita da Azure Active Directory e l'utente eseguirà l'accesso a Windows e Office 365 con le proprie credenziali di Microsoft 365 Business.  <br/> |
   
 **Impostazioni facoltative:**
  
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|Ignora impostazioni della privacy (disattivato per impostazione predefinita)  <br/> |Se questa opzione è impostata su **attivato**, l'utente del dispositivo non vedrà il contratto di licenza per il dispositivo e Windows al primo accesso.  <br/> |
|Non consentire all'utente di diventare l'amministratore locale  <br/> |Se questa opzione è impostata su **attivato**, l'utente del dispositivo non potrà installare le app personali, ad esempio Cortana.  <br/> |
   
