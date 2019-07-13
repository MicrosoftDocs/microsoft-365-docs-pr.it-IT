---
title: Dettagli del tenant di Azure Active Directory
description: In questo argomento vengono descritte le modifiche apportate all'account AAD quando si effettua la registrazione in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643947"
---
# <a name="azure-active-directory-tenant-details"></a>Dettagli del tenant di Azure Active Directory
{dettagli cruenti sugli account, le chiamate API, le permanenti e così via, ecc.}


## <a name="data-transmitted-to-and-from-your-aad-account"></a>Dati trasmessi da e verso l'account AAD


Dati inviati all'account da Microsoft:

- Nomi di gruppi
- Configurazione del criterio di sicurezza
- Ordini di dispositivi
- Account utente (MSadmin, MSTest, mwaas_soc_ro, mwaas_wdgsoc)
- Assegnazione della licenza E5 agli account utente
- Criteri di Windows Update per gli anelli di aggiornamento

Dati inviati a Microsoft dall'account:

- Aggiornamento dei dispositivi, dati di utilizzo e affidabilità
- Dati di distribuzione e affidabilità delle app
- Dati sulla distribuzione dei criteri di aggiornamento e di sicurezza
- Utenti assegnati ai dispositivi  

I dati trasmessi dall'account sono archiviati nei database SQL di Azure nel tenant Microsoft ospitato negli Stati Uniti. I dati vengono archiviati e gestiti secondo i criteri descritti in {Microsoft Azure Security}. 

## <a name="api-permissions-and-calls"></a>Autorizzazioni e chiamate API

**Durante la registrazione:**

Autorizzazioni API:
- DeviceManagementServiceConfig. ReadWrite. All
- Directory. AccessAsUser. All
- User. ReadWrite. All
- DeviceManagementConfiguration. ReadWrite. All
- DeviceManagementManagedDevices. ReadWrite. All
- Group. ReadWrite. All

Chiamate API:
- POST/organization/{organizationId}/setMobileDeviceManagementAuthority
- GET/POST/directoryRoles/{id}/members
- GET/POST/Users
- GET/POST/groups
- PATCH/groups/{ID}
- GET/POST/deviceManagement/deviceConfigurations
- OTTENERE/deviceManagement/detectedApps

**Dopo la registrazione, durante la gestione ordinaria:**

Autorizzazioni API:
- DeviceManagementManagedDevices. ReadWrite. All
- DeviceManagementApps. ReadWrite. All
- DeviceManagementConfiguration. ReadWrite. All
- Reports. Read. All
- User. ReadWrite. All
- Group. ReadWrite. All
- Directory. AccessAsUser. All

Chiamate API:
- GET/POST/directoryRoles/{id}/members
- GET/PATCH/POST/Users
- GET/POST/groups
- PATCH/groups/{ID}
- GET/POST/deviceManagement/deviceConfigurations
- GET/POST/deviceAppManagement/mobileApps
- OTTENERE/deviceManagement/detectedApps
- OTTENERE/Devices
- POST/Users/{ID | userPrincipalName}/assignLicense
- OTTENERE/subscribedSkus

## <a name="accounts-used-by-microsoft-managed-desktop"></a>Account utilizzati da Microsoft Managed Desktop





| Account | Descrizione  | Accesso condizionale  | Autenticazione a più fattori  | Perché questo è OK |
|---------|---------|---------|---------|--------------|
| MSadmin @ * onmmicrosoft. com | Account del servizio limitato con privilegi di amministratore, utilizzato come amministratore di Microsoft Intune e utente {che cos'è?} per definire e configurare il tenant per i dispositivi desktop Microsoft moderni.Non dispone di autorizzazioni di accesso interattive; esegue operazioni solo tramite il servizio.  | Escluso, perché non è originato dalla rete        | Escluso perché non è disponibile alcun accesso interattivo        | Password memorizzata in Azure Key Vault |
| MSTest @ * onmmicrosoft. com     |         |         |         |
| mssupport @ * onmmicrosoft. com     |         |         |         |
| msadminint @ * onmmicrosoft. com     |         |         |         |
