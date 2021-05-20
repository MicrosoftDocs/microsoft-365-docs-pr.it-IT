---
title: Gestire l'accesso guest in Microsoft 365 gruppi
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
description: Informazioni su come aggiungere ospiti a un gruppo Microsoft 365, visualizzare utenti guest e usare PowerShell per controllare l'accesso guest.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571938"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gestire l'accesso guest in Microsoft 365 gruppi

Per impostazione predefinita, l'accesso guest per Microsoft 365 gruppi è attivato per l'organizzazione. Gli amministratori possono controllare se consentire l'accesso guest ai gruppi per l'intera organizzazione o per i singoli gruppi.

Quando è attivato, i membri del gruppo possono invitare utenti guest a un gruppo Microsoft 365 gruppo tramite Outlook sul Web. Gli inviti vengono inviati al proprietario del gruppo per l'approvazione.

Una volta approvato, l'utente guest viene aggiunto alla directory e al gruppo.

> [!Note]
> Yammer Enterprise reti native o EU [Geo non supportano](/yammer/manage-security-and-compliance/manage-data-compliance) gli ospiti della rete.
> Microsoft 365 I Yammer di accesso non supportano attualmente l'accesso guest, ma è possibile creare gruppi esterni non connessi nella rete Yammer rete. Per [istruzioni, vedere Creare e gestire gruppi Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) in un'80 esterne.

L'accesso guest nei gruppi viene spesso utilizzato come parte di uno scenario più ampio che include SharePoint o Teams. Questi servizi hanno le proprie impostazioni di condivisione degli ospiti. Per istruzioni complete sulla configurazione della condivisione degli ospiti tra gruppi, SharePoint e Teams, vedere:

- [Collaborare con gli utenti guest a un sito](../../solutions/collaborate-in-site.md)
- [Collaborare con gli utenti guest in un team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gestire l'accesso guest dei gruppi

Se si desidera abilitare o disabilitare l'accesso guest nei gruppi, è possibile farlo nell'interfaccia Microsoft 365 di amministrazione.

1. Nell'interfaccia di amministrazione passare **a** \> **Mostra tutte le Impostazioni** \> **dell'organizzazione** e **nella scheda** Servizi selezionare **Microsoft 365 gruppi**.
  
2. Nella pagina **Microsoft 365 gruppi scegliere se** si desidera che persone esterne all'organizzazione accedono alle risorse del gruppo o che i proprietari dei gruppi aggigano persone esterne all'organizzazione ai gruppi.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Aggiungere ospiti a un gruppo Microsoft 365 dall'interfaccia di amministrazione

Se l'ospite esiste già nella directory, è possibile aggiungerlo ai gruppi dall'interfaccia di Microsoft 365 di amministrazione. I gruppi con appartenenza dinamica devono [essere gestiti in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).
  
1. Nell'interfaccia di amministrazione passare alla **pagina**  >  **Gruppi** gruppi.
  
2. Fare clic sul gruppo a cui si vuole aggiungere l'ospite e **selezionare Visualizza tutti e gestisci** membri nella **scheda** Membri. 
  
4. Selezionare **Aggiungi membri** e scegliere il nome dell'ospite da aggiungere.
    
5. Selezionare **Salva**.

Se si desidera aggiungere direttamente un guest alla directory, è possibile [aggiungere Azure Active Directory di collaborazione B2B nel portale di Azure](/azure/active-directory/b2b/add-users-administrator).

Se si desidera modificare una delle informazioni di un ospite, è possibile [aggiungere o aggiornare le informazioni del profilo di un utente utilizzando Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="related-content"></a>Contenuti correlati

[Bloccare gli utenti guest da un gruppo specifico](../../solutions/per-group-guest-access.md) (articolo)

[Gestire l'appartenenza a gruppi nell'Microsoft 365 di amministrazione](add-or-remove-members-from-groups.md) (articolo)
  
[Azure Active Directory di accesso (articolo)](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (articolo)