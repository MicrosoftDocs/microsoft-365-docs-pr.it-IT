---
title: Assegnare le licenze Microsoft 365 agli account utente
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Descrive come assegnare le licenze Microsoft 365 agli account utente, individualmente o in base all'appartenenza ai gruppi.
ms.openlocfilehash: e132a8c2d65c401899624b9d255050385f2cb721
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417099"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Assegnare le licenze Microsoft 365 agli account utente

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Per il modello di identità solo cloud, è possibile assegnare le licenze Microsoft 365 agli account utente quando vengono creati, a seconda della modalità di creazione.

Per il modello di identità ibrida, quando gli account utente di servizi di dominio Active Directory (AD DS) vengono sincronizzati per la prima volta, non viene assegnata automaticamente una licenza Microsoft 365. Prima di tutto, è necessario configurare ogni account utente con un percorso utente.

In entrambi i casi, è necessario assegnare una licenza agli account utente in modo che gli utenti possano accedere ai servizi Microsoft 365, ad esempio la posta elettronica e Microsoft teams.

È possibile assegnare le licenze agli account utente singolarmente o automaticamente tramite l'appartenenza al gruppo.

Per assegnare le licenze Microsoft 365 ai singoli account utente, è possibile utilizzare:

- [L'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell per Microsoft 365](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

Per l'assegnazione di licenze automatiche, vedere [Group-based Licensing in Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

## <a name="next-steps"></a>Passaggi successivi

Con l'intero set di account utente a cui sono state assegnate le licenze, ora è possibile eseguire le operazioni seguenti:

- [Implementare la sicurezza](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [Distribuire il software client, ad esempio le app Microsoft 365](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [Configurare la sicurezza e la mobilità di base in Microsoft 365](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [Configurare servizi e applicazioni](configure-services-and-applications.md)
