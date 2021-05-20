---
title: Ripristinare un gruppo Microsoft 365 eliminato
ms.reviewer: arvaradh
f1.keywords: CSH
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
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Un gruppo eliminato viene conservato per 30 giorni ed è comunque possibile ripristinarlo. Dopo 30 giorni, il gruppo e il relativo contenuto vengono eliminati definitivamente.
ms.openlocfilehash: 285796ec45b1e6d77d46d7a0c39706f566bb8cf6
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582681"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Ripristinare un gruppo Microsoft 365 eliminato

Se un gruppo è stato eliminato, verrà conservato per 30 giorni per impostazione predefinita. Questo periodo di 30 giorni è considerato una "eliminazione recidiva" perché è comunque possibile ripristinare il gruppo. Dopo 30 giorni, il gruppo e il contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.

Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:
  
- Azure Active Directory (AD) Microsoft 365 gruppi, proprietà e membri.
    
- Indirizzi di posta elettronica del gruppo.
    
- Exchange Online posta in arrivo e calendario condivisi.
    
- SharePoint File e sito del team online.
    
- Blocco appunti di OneNote
    
- Planner
    
- Teams

- Yammer gruppo e gruppo (se il gruppo Microsoft 365 è stato creato da Yammer)

> [!NOTE]
> In questo articolo viene descritto il ripristino solo Microsoft 365 gruppi. Non è possibile ripristinare tutti gli altri gruppi dopo l'eliminazione.

## <a name="restore-a-group"></a>Ripristinare un gruppo

# <a name="outlook"></a>[Outlook](#tab/outlook)

Se si è il proprietario di un Microsoft 365, è possibile ripristinare il gruppo manualmente in Outlook sul Web seguendo la procedura seguente:

1. Nella pagina Gruppi [eliminati](https://outlook.office.com/people/group/deleted)selezionare l'opzione  **Gestisci** gruppi nel nodo Gruppi e quindi scegliere **Eliminato.**

2. Fare clic **sulla scheda** Ripristina accanto al gruppo che si desidera ripristinare.

Se il gruppo eliminato non viene visualizzato qui, contattare un amministratore.

# <a name="admin-center"></a>[Interfaccia di amministrazione](#tab/admin-center)

Se si è un amministratore globale o un amministratore di gruppi, è possibile ripristinare un gruppo eliminato nell'Microsoft 365 di amministrazione:

1. Passare all'[interfaccia di amministrazione](https://admin.microsoft.com).
2. Espandere **Gruppi** e quindi fare clic su **Gruppi eliminati.**
3. Selezionare il gruppo che si desidera ripristinare e quindi fare clic **su Ripristina gruppo.**

> [!NOTE]
> In alcuni casi, il ripristino del gruppo e di tutti i relativi dati può richiedere fino a 24 ore. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Hai domande su Microsoft 365 gruppi?

Visitare il [sito Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per inviare domande e partecipare a conversazioni su Microsoft 365 gruppi. 
  
## <a name="related-content"></a>Contenuto correlato

[Gestire Microsoft 365 gruppi con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (articolo)
  
[Eliminare gruppi utilizzando il cmdlet Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) (articolo)
  
[Gestire le impostazioni del sito del team connesso al gruppo](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (articolo)
  
[Eliminare un gruppo in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (articolo)