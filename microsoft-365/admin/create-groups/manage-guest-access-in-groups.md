---
title: Gestire l'accesso guest nei gruppi di Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: Informazioni su come aggiungere gli ospiti a un gruppo di Microsoft 365, visualizzare gli utenti guest e utilizzare PowerShell per controllare l'accesso guest.
ms.openlocfilehash: 640a35cbb1a3eb395453b224cadcf0d0db82fab8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326520"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gestire l'accesso guest nei gruppi di Microsoft 365

Per impostazione predefinita, l'accesso guest per i gruppi di Microsoft 365 è attivato per l'organizzazione. Gli amministratori possono controllare se consentire l'accesso Guest ai gruppi per l'intera organizzazione o per i singoli gruppi.

Quando è attivata, i membri del gruppo possono invitare gli utenti Guest a un gruppo di Microsoft 365 tramite Outlook sul Web. Gli inviti vengono inviati al proprietario del gruppo per l'approvazione.

Una volta approvato, l'utente ospite viene aggiunto alla directory e al gruppo.

> [!Note]
> Le reti aziendali di Yammer che si trovano in modalità nativa o l' [eu Geo](https://go.microsoft.com/fwlink/?linkid=2107357) non supportano gli utenti della rete.
> I gruppi di Yammer connessi a Microsoft 365 non supportano attualmente l'accesso guest, ma è possibile creare gruppi esterni non connessi nella rete Yammer. Per istruzioni, vedere [creare e gestire gruppi esterni in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) .

L'accesso guest nei gruppi è spesso utilizzato come parte di uno scenario più ampio che include SharePoint o teams. Tali servizi dispongono di impostazioni di condivisione Guest. Per istruzioni complete su come configurare la condivisione Guest tra gruppi, SharePoint e team, vedere:

- [Collaborare con gli utenti guest a un sito](../../solutions/collaborate-in-site.md)
- [Collaborare con gli utenti guest in un team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gestione degli accessi ai gruppi

Se si desidera abilitare o disabilitare l'accesso guest nei gruppi, è possibile farlo nell'interfaccia di amministrazione di Microsoft 365.

1. Nell'interfaccia di amministrazione, andare a **Mostra tutte** le impostazioni \> **Settings** \> **org** impostazioni e nella scheda **Servizi** , selezionare **Microsoft 365 gruppi**.
  
2. Nella pagina **Microsoft 365 groups** , scegliere se si desidera consentire agli utenti esterni all'organizzazione di accedere alle risorse del gruppo o consentire ai proprietari di gruppi di aggiungere persone esterne all'organizzazione.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Aggiungere gli utenti a un gruppo di Microsoft 365 dall'interfaccia di amministrazione

Se l'ospite è già presente nella directory, è possibile aggiungerli ai gruppi dall'interfaccia di amministrazione di Microsoft 365.
  
1. Nell'interfaccia di amministrazione, andare alla pagina **gruppi**  >  **Groups** .
  
2. Fare clic sul gruppo a cui si desidera aggiungere l'ospite e selezionare **Visualizza tutti e Gestisci membri** nella scheda **membri** . 
  
4. Selezionare **Aggiungi membri**e scegliere il nome del Guest che si desidera aggiungere.
    
5. Selezionare **Salva**.

Se si desidera aggiungere direttamente un guest alla directory, è possibile [aggiungere gli utenti di collaborazione B2B di Azure Active Directory nel portale di Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Se si desidera modificare le informazioni di un ospite, è possibile [aggiungere o aggiornare le informazioni del profilo di un utente utilizzando Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="see-also"></a>Vedere anche

[Bloccare gli utenti Guest da un gruppo specifico](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Gestire l'appartenenza ai gruppi nell'interfaccia di amministrazione di Microsoft 365](add-or-remove-members-from-groups.md)
  
[Recensioni di Azure Active Directory Access](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
