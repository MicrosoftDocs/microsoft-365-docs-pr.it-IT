---
title: Assegnare Microsoft 365 licenze utente agli account utente
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
description: Descrive come assegnare licenze Microsoft 365 utenti agli account utente, singolarmente o in base all'appartenenza ai gruppi.
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051533"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Assegnare Microsoft 365 licenze utente agli account utente

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Per il modello di identità solo cloud, è possibile assegnare licenze Microsoft 365 agli account utente durante la creazione, a seconda di come vengono create.

Per il modello di identità ibrido, quando gli account utente di Servizi di dominio Active Directory (AD DS) vengono sincronizzati per la prima volta, non viene loro assegnata automaticamente una posizione o una Microsoft 365 licenza. **È necessario configurare ogni account utente con una posizione utente prima o insieme all'assegnazione di una licenza.**

In entrambi i casi, è necessario assegnare una licenza agli account utente in modo che gli utenti possano accedere ai servizi Microsoft 365, ad esempio posta elettronica e Microsoft Teams.

È possibile assegnare licenze agli account utente singolarmente o automaticamente tramite l'appartenenza ai gruppi.

Per assegnare Microsoft 365 licenze a singoli account utente, è possibile utilizzare:

- [L'interfaccia di amministrazione di Microsoft 365](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Interfaccia di amministrazione di Azure AD

## <a name="group-based-licensing"></a>Licenze basate sui gruppi

È possibile configurare i gruppi di sicurezza in Azure AD per assegnare automaticamente le licenze da un set di sottoscrizioni a tutti i membri del gruppo. Questa operazione è denominata *licenze basate sui gruppi*. Se un account utente viene aggiunto o rimosso dal gruppo, le licenze per gli abbonamenti del gruppo verranno automaticamente assegnate o rimosse dall'account utente.

Assicurarsi di avere a disposizione abbastanza licenze per tutti i membri del gruppo. Se le licenze a disposizione terminano, i nuovi utenti non potranno ottenerne una finché non ne saranno di nuovo disponibili.

>[!Note]
>Non è necessario configurare l'assegnazione delle licenze basate su gruppo per i gruppi contenenti account Azure business to business (B2B).
>

Per altre informazioni, vedi Licenze [basate su gruppo in Azure AD.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)

## <a name="next-steps"></a>Passaggi successivi

Con il set appropriato di account utente a cui sono state assegnate licenze, è ora possibile:

- [Implementare la sicurezza](../security/defender-365-security/security-roadmap.md)
- [Distribuire software client, ad esempio Microsoft 365 Apps](/DeployOffice/deployment-guide-microsoft-365-apps)
- [Configurare la gestione dei dispositivi](device-management-roadmap-microsoft-365.md)
- [Configurare servizi e applicazioni](configure-services-and-applications.md)