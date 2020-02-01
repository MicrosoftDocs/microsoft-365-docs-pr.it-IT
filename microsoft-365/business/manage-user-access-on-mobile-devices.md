---
title: Gestire la modalità di accesso ai documenti di Office nei dispositivi mobili
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Informazioni sui criteri di protezione che consentono di accedere in modo sicuro alle app di Office dai dispositivi mobili.
ms.openlocfilehash: 39d28a3a78fb06d0020c484b1782b544f6a8c656
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593822"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>Gestire la modalità di accesso ai documenti di Office nei dispositivi mobili

 Le impostazioni dei criteri che controllano la modalità di accesso degli utenti ai file di Office dai dispositivi mobili sono **disattivate** per impostazione predefinita. È consigliabile accettare i valori predefiniti durante l'installazione per creare i criteri di applicazione per Android, iOS e Windows 10 che si applicano a tutti gli utenti. È possibile creare altri criteri al termine dell'installazione. 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Impostazioni che controllano la modalità di accesso degli utenti ai file di Office nei dispositivi mobili

Le impostazioni seguenti sono disponibili per la gestione della modalità di accesso degli utenti ai file di lavoro di Office:
  
|||
|:-----|:-----|
|Impostazione  <br/> |Descrizione  <br/> |
|Richiedi un PIN o l'impronta digitale per accedere alle app di Office  <br/> |Se questa impostazione è **attiva**, gli utenti devono fornire un'altra forma di autenticazione, oltre a nome utente e password, prima di poter utilizzare le app di Office nel dispositivo mobile.  <br/> |
|Reimposta il PIN dopo il numero di tentativi di accesso falliti seguente  <br/> |Per impedire a un utente non autorizzato di indovinare casualmente un PIN, il PIN verrà reimpostato dopo il numero specificato di tentativi di immissione non riusciti.  <br/> |
|Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per  <br/> |Questa impostazione determina per quanto tempo un utente può rimanere inattivo prima che venga richiesto di eseguire nuovamente l'accesso.  <br/> |
|Nega l'accesso ai file di lavoro nei dispositivi jailbroken o rooted  <br/> |È possibile che gli utenti esperti abbiano un dispositivo sottoposto a jailbreak o root. Questo significa che l'utente può modificare il sistema operativo, il che può rendere il dispositivo più suscettibile al malware. Questi dispositivi sono bloccati quando l'impostazione è **attivata**.  <br/> |
|Non consentire agli utenti di copiare il contenuto da app di Office in app personali  <br/> |Quando l'impostazione è **attiva**, l'utente non è in grado di copiare le informazioni in un file di lavoro in un file personale. Se l'impostazione è **disattivata**, l'utente può copiare informazioni da un file di lavoro a un'app personale o a un account personale.  <br/> |
   

