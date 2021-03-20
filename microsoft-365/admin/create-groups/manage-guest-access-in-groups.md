---
title: Gestire l'accesso guest nei gruppi di Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Informazioni su come aggiungere guest a un gruppo di Microsoft 365, visualizzare gli utenti guest e usare PowerShell per controllare l'accesso guest.
ms.openlocfilehash: 114fc1b5262f1632c7e7a8d1aa339c2470223288
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908607"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gestire l'accesso guest nei gruppi di Microsoft 365

Per impostazione predefinita, l'accesso guest per i gruppi di Microsoft 365 è attivato per l'organizzazione. Gli amministratori possono controllare se consentire l'accesso guest ai gruppi per l'intera organizzazione o per singoli gruppi.

Quando è attivato, i membri del gruppo possono invitare utenti guest a un gruppo di Microsoft 365 tramite Outlook sul Web. Gli inviti vengono inviati al proprietario del gruppo per l'approvazione.

Dopo l'approvazione, l'utente guest viene aggiunto alla directory e al gruppo.

> [!Note]
> Le reti Yammer Enterprise in modalità nativa o [l'area geografica dell'UE](/yammer/manage-security-and-compliance/manage-data-compliance) non supportano i guest di rete.
> I gruppi di Yammer connessi a Microsoft 365 attualmente non supportano l'accesso guest, ma è possibile creare gruppi esterni non connessi nella rete Yammer. Per [istruzioni, vedere Creare e gestire gruppi esterni in Yammer.](/yammer/work-with-external-users/create-and-manage-external-groups)

L'accesso guest nei gruppi viene spesso utilizzato come parte di uno scenario più ampio che include SharePoint o Teams. Questi servizi hanno le proprie impostazioni di condivisione guest. Per istruzioni complete sulla configurazione della condivisione guest tra gruppi, SharePoint e Teams, vedere:

- [Collaborare con gli utenti guest a un sito](../../solutions/collaborate-in-site.md)
- [Collaborare con gli utenti guest in un team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gestire l'accesso guest ai gruppi

Se si desidera abilitare o disabilitare l'accesso guest nei gruppi, è possibile farlo nell'interfaccia di amministrazione di Microsoft 365.

1. Nell'interfaccia di amministrazione passare a **Mostra tutte le** impostazioni dell'organizzazione e nella scheda \>  \>  **Servizi** selezionare Gruppi di **Microsoft 365.**
  
2. Nella pagina **Gruppi di Microsoft 365** scegliere se consentire alle persone esterne all'organizzazione di accedere alle risorse del gruppo o consentire ai proprietari di gruppi di aggiungere persone esterne all'organizzazione ai gruppi.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Aggiungere utenti guest a un gruppo di Microsoft 365 dall'interfaccia di amministrazione

Se il guest esiste già nella directory, è possibile aggiungerlo ai gruppi dall'interfaccia di amministrazione di Microsoft 365. I gruppi con appartenenza dinamica devono [essere gestiti in Azure Active Directory.](/azure/active-directory/enterprise-users/groups-create-rule)
  
1. Nell'interfaccia di amministrazione passare alla **pagina**  >  **Gruppi di** gruppi.
  
2. Fare clic sul gruppo a cui si desidera aggiungere il guest e selezionare **Visualizza tutti** e gestisci membri nella **scheda** Membri. 
  
4. Selezionare **Aggiungi membri** e scegliere il nome del guest che si desidera aggiungere.
    
5. Selezionare **Salva**.

Se si desidera aggiungere direttamente un guest alla directory, è possibile aggiungere utenti di collaborazione [B2B](/azure/active-directory/b2b/add-users-administrator)di Azure Active Directory nel portale di Azure.

Se si desidera modificare le informazioni di un guest, è possibile aggiungere o aggiornare le informazioni del profilo di un utente [usando Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="see-also"></a>Vedere anche

[Bloccare gli utenti guest da un gruppo specifico](../../solutions/per-group-guest-access.md)

[Gestire l'appartenenza ai gruppi nell'interfaccia di amministrazione di Microsoft 365](add-or-remove-members-from-groups.md)
  
[Verifiche di accesso ad Azure Active Directory](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)