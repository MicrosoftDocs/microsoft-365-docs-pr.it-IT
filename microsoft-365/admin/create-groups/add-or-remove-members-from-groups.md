---
title: Aggiungere o rimuovere membri da Microsoft 365 gruppi
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Informazioni su come aggiungere un membro a un gruppo, rimuovere un membro dal gruppo e gestire lo stato del proprietario del gruppo nel interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 7eaa74a53ac5f27d801d1cf16c9af035c63c68b1
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393764"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Aggiungere o rimuovere membri da Microsoft 365 gruppi usando l'interfaccia di amministrazione

In Microsoft 365, i membri del gruppo in genere creano i propri gruppi, si aggiungono ai gruppi a cui vogliono partecipare o vengono invitati dai proprietari dei gruppi. Se la proprietà del gruppo cambia o se si determina che un membro deve essere aggiunto o rimosso, l'amministratore può anche apportare tale modifica. Solo un amministratore globale, Exchange, un amministratore di gruppi o un amministratore utente può apportare queste modifiche. [Che cos'è un Microsoft 365 gruppo?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Se non sei un amministratore, puoi [aggiungere o rimuovere](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de)membri usando Outlook .
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Aggiungere un membro a un gruppo nell'interfaccia di amministrazione

1. Nell'interfaccia di amministrazione passare alla [**pagina Gruppi**](https://admin.microsoft.com/Adminportal/Home?#/groups) attivi.  

2. Fare clic sul nome di un gruppo.

3. Nella scheda Membri del riquadro dei dettagli **selezionare** Visualizza tutti e **gestisci membri** e quindi **Aggiungi membri.**

4. Cercare o selezionare il nome del membro da aggiungere.

5. Selezionare **Salva**.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Aggiungere un gruppo a un membro nell'interfaccia di amministrazione

1. Nell'interfaccia di amministrazione passare alla [**pagina Utenti**](https://admin.microsoft.com/Adminportal/Home?#/users) attivi.  

2. Fare clic su un utente.

3. Nella scheda **Account** del riquadro dei dettagli selezionare **Gestisci gruppi**.

4. Cercare o selezionare il nome del gruppo che si desidera aggiungere.

5. Selezionare **Salva**.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Rimuovere un membro da un gruppo nell'interfaccia di amministrazione

> [!NOTE]
> Quando si rimuove un membro da un gruppo privato, sono necessari 5 minuti prima che la persona sia bloccata dal gruppo.

1. Nell'interfaccia di amministrazione passare alla [**pagina Gruppi**](https://admin.microsoft.com/Adminportal/Home?#/groups) attivi.  

2. Fare clic sul nome di un gruppo.

3. Nella scheda Membri del riquadro dei dettagli **selezionare** Visualizza tutti e **gestisci membri.**

4. Accanto al membro che si desidera rimuovere, selezionare la X.

5. Selezionare **Salva** per rimuovere il membro.

## <a name="manage-group-owner-status"></a>Gestire lo stato del proprietario del gruppo

Per impostazione predefinita, la persona che crea il gruppo ne è il proprietario. Spesso un gruppo include più proprietari a scopo di backup o per altri motivi. I membri possono essere alzati di livello allo stato di proprietari e i proprietari possono essere abbassati di livello allo stato di membri.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Alzare di livello un membro a proprietario nell'interfaccia di amministrazione

1. Nell'interfaccia di amministrazione passare alla [**pagina Gruppi**](https://admin.microsoft.com/Adminportal/Home?#/groups) attivi.  

2. Fare clic sul nome di un gruppo.

3. Nella scheda Membri del riquadro dei dettagli **selezionare** Visualizza tutti e **gestisci proprietari.**

4. Selezionare **Aggiungi proprietari**.

5. Selezionare la casella di controllo accanto al nome del membro che si desidera aggiungere.

6. Selezionare **Salva** e quindi **Chiudi.**

### <a name="remove-owner-status-in-the-admin-center"></a>Rimuovere lo stato del proprietario nell'interfaccia di amministrazione

1. Nell'interfaccia di amministrazione passare alla [**pagina Gruppi**](https://admin.microsoft.com/Adminportal/Home?#/groups) attivi.  

2. Fare clic sul nome di un gruppo.

3. Nella scheda Membri del riquadro dei dettagli **selezionare** Visualizza tutti e **gestisci proprietari.**

4. Seleziona la X accanto al nome del proprietario.

5. Selezionare **Salva**.

## <a name="next-steps"></a>Passaggi successivi

- [Gestire dinamicamente i gruppi in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal): vedere la sezione "Come si gestisce l'appartenenza a un gruppo dinamicamente?"

- Per aggiungere centinaia o migliaia di utenti ai gruppi, utilizzare [Add-UnifiedGroupLinks.](/powershell/module/exchange/add-unifiedgrouplinks)

- [Assegnare un nuovo proprietario a un gruppo orfano](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="related-content"></a>Contenuto correlato

[Aggiornare le liste di distribuzione Microsoft 365 gruppi in Outlook](../manage/upgrade-distribution-lists.md) (articolo)\
[Perché aggiornare le liste di distribuzione ai](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) gruppi in Outlook (articolo)\
[Gestire l'accesso guest nei Microsoft 365](manage-guest-access-in-groups.md) (articolo)\
[Gestire Microsoft 365 gruppi con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md): in questo articolo vengono presentati i cmdlet principali e vengono forniti esempi (articolo)\
[Microsoft 365 di denominazione dei gruppi di utenti](../../solutions/groups-naming-policy.md) (articolo)