---
title: Assegnare ruoli di amministratore interfaccia di amministrazione di Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Informazioni su come assegnare ruoli di amministratore a uno o più utenti dell'azienda in modo che possano eseguire attività specifiche nell'interfaccia di amministrazione.
ms.openlocfilehash: 575d1d8c6b0ffce40877fb41d28df82c24e84d04
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393776"
---
# <a name="assign-admin-roles"></a>Assegnare i ruoli di amministratore

Se sei la persona che ha acquistato l'abbonamento a Microsoft Business, sei l'amministratore globale. Ciò significa che hai un controllo illimitato sui prodotti nelle tue sottoscrizioni e puoi accedere alla maggior parte dei dati.

Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](about-admin-roles.md).

Quando si aggiungono nuovi utenti, se non si assegna loro  un ruolo di amministratore, questi sono nel ruolo utente e non hanno privilegi di amministratore per nessuna delle centri di amministrazione Microsoft. Tuttavia, se hai bisogno di assistenza per eseguire le operazioni, puoi assegnare un ruolo di amministratore a un utente. Ad esempio, se è necessario che qualcuno aiuti a reimpostare le password, non è consigliabile assegnare loro il ruolo di amministratore globale, è consigliabile assegnare loro il ruolo di amministratore delle password. La presenza di troppi amministratori globali, con accesso illimitato ai dati e all'azienda online, rappresenta un rischio per la sicurezza.

## <a name="watch-add-an-adminbrbr"></a>Watch: Add an admin<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Se il video è stato utile, consultare la [serie dei corsi di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](../../business-video/index.yml).

## <a name="assign-admin-roles"></a>Assegnare i ruoli di amministratore 

È possibile assegnare gli utenti a un ruolo in due modi diversi:

- È possibile accedere ai dettagli dell'utente e **Gestire i ruoli** per assegnare un ruolo all'utente.
- In caso contrario, è **possibile passare a Ruoli** e selezionare il ruolo e quindi aggiungervi più utenti.

### <a name="assign-admin-roles-to-users-using-roles"></a>Assegnare ruoli di amministratore agli utenti tramite Ruoli

1. Nell'interfaccia di amministrazione passare a **Ruoli**. Scegliere le **schede Azure AD** o **Intune** per visualizzare i ruoli di amministratore disponibili per l'organizzazione.
2. Selezionare il ruolo di amministratore a cui si desidera assegnare l'utente.
3. Selezionare **Amministratori assegnati**  >  **Aggiungi**.
4. Digitare il nome visualizzato o il **nome** **utente** dell'utente e quindi selezionare l'utente nell'elenco dei suggerimenti.
5. Aggiungi più utenti finché non hai finito.
6. Selezionare **Salva** e quindi l'utente verrà aggiunto all'elenco degli amministratori assegnati.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Assegnare un utente a un ruolo di amministratore tramite l'opzione Utenti attivi

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla **pagina Utenti** > [utenti](https://go.microsoft.com/fwlink/p/?linkid=834822) attivi.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

::: moniker-end

2. Nella pagina **Utenti attivi** selezionare l'utente di cui si desidera modificare il ruolo di amministratore. Nel riquadro a comparsa, in **Ruoli,** selezionare **Gestisci ruoli.**

3. Selezionare il ruolo di amministratore da assegnare all'utente. Se il ruolo che si sta cercando non è visualizzato, selezionare **Mostra tutto** nella parte inferiore dell'elenco.

## <a name="assign-admin-roles-to-multiple-users"></a>Assegnare ruoli di amministratore a più utenti

Se si conosce PowerShell, vedere [Assegnare ruoli agli account utente con PowerShell.](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) È la soluzione ideale per assegnare i ruoli a centinaia di utenti.
  
Usare le istruzioni seguenti per assegnare i ruoli a decine di utenti.

## <a name="check-admin-roles-in-your-organization"></a>Controllare i ruoli di amministratore nell'organizzazione

È possibile che non si dispone delle autorizzazioni corrette per assegnare ruoli di amministratore ad altri utenti. Verificare di disporre delle autorizzazioni corrette o chiedere a un altro amministratore di assegnare automaticamente i ruoli.

È possibile controllare le autorizzazioni del ruolo di amministratore in due modi diversi:

- Puoi accedere ai dettagli dell'utente e guardare in **Ruoli** nella **pagina Account.**
- In caso contrario, è **possibile passare a Ruoli** e selezionare il ruolo di amministratore e selezionare gli amministratori assegnati per vedere quali utenti sono assegnati.

## <a name="related-content"></a>Contenuto correlato

[Informazioni Microsoft 365 ruoli di amministratore](about-admin-roles.md) (articolo)\
[Autorizzazioni del ruolo amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (articolo)\
[Assegnare ruoli agli account utente con PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (articolo)\
[Autorizzare o rimuovere relazioni con i partner](../misc/add-partner.md) (articolo)