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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Informazioni sui criteri di protezione che consentono di gestire il modo in cui gli utenti accedono alle app di Office e ai file di lavoro dai dispositivi mobili.
ms.openlocfilehash: b2b828cf2e201360f12b8fadcb395e72958230f6
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471068"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>Gestire la modalità di accesso ai documenti di Office nei dispositivi mobili

Questo articolo si applica a Microsoft 365 Business Premium.

Le impostazioni dei criteri che controllano la modalità di accesso degli utenti ai file di Office dai dispositivi mobili sono **disattivate** per impostazione predefinita. Ti consigliamo di accettare i valori predefiniti durante l'installazione per creare criteri di applicazione per Android, iOS e Windows 10 che si applicano a tutti gli utenti. È possibile creare altri criteri al termine dell'installazione. 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Impostazioni che controllano la modalità di accesso degli utenti ai file di Office nei dispositivi mobili

Le impostazioni seguenti sono disponibili per la gestione della modalità di accesso degli utenti ai file di lavoro di Office:
  
|||
|:-----|:-----|
|Impostazione  <br/> |Descrizione  <br/> |
|Richiedi un PIN o l'impronta digitale per accedere alle app di Office  <br/> |Se questa impostazione è **attivata,** gli utenti devono fornire un'altra forma di autenticazione, oltre al nome utente e alla password, prima di poter usare le app di Office nel dispositivo mobile.  <br/> |
|Reimposta il PIN dopo il numero di tentativi di accesso falliti seguente  <br/> |Per impedire a un utente non autorizzato di indovinare casualmente un PIN, il PIN verrà reimpostato dopo il numero specificato di tentativi di immissione non riusciti.  <br/> |
|Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per  <br/> |Questa impostazione determina per quanto tempo un utente può essere inattivo prima che venga richiesto di accedere di nuovo.  <br/> |
|Nega l'accesso ai file di lavoro nei dispositivi jailbroken o rooted  <br/> |È possibile che gli utenti esperti abbiano un dispositivo sottoposto a jailbreak o root. Ciò significa che l'utente può modificare il sistema operativo, in modo da rendere il dispositivo più vulnerabile al malware. Questi dispositivi sono bloccati quando l'impostazione è **attivata**.  <br/> |
|Non consentire agli utenti di copiare il contenuto dalle app di Office nelle app personali  <br/> |Quando l'impostazione è **attivata,** l'utente non può copiare le informazioni in un file di lavoro in un file personale. Se l'impostazione è **Disattivata,** l'utente può copiare le informazioni da un file di lavoro a un'app personale o a un account personale.  <br/> |
   

