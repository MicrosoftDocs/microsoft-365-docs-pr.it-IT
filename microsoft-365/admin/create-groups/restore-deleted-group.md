---
title: Ripristinare un gruppo di Microsoft 365 eliminato
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
description: Informazioni su come ripristinare un gruppo di Microsoft 365 eliminato.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753244"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Ripristinare un gruppo di Microsoft 365 eliminato

Se un gruppo è stato eliminato, per impostazione predefinita verrà conservato per 30 giorni. Questo periodo di 30 giorni è considerato una "eliminazione rescisa" perché è comunque possibile ripristinare il gruppo. Dopo 30 giorni, il gruppo e il contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.

Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:
  
- Oggetto, proprietà e membri dei gruppi di Microsoft 365 di Azure Active Directory (AD).
    
- Indirizzi di posta elettronica del gruppo.
    
- Posta in arrivo e calendario condivisi di Exchange Online.
    
- File e sito del team di SharePoint Online.
    
- Blocco appunti di OneNote
    
- Planner
    
- Teams

- Contenuto del gruppo e del gruppo di Yammer (se il gruppo di Microsoft 365 è stato creato da Yammer)

> [!NOTE]
> Questo articolo descrive il ripristino solo dei gruppi di Microsoft 365. Non è possibile ripristinare tutti gli altri gruppi dopo l'eliminazione.

## <a name="restore-a-group"></a>Ripristinare un gruppo

# <a name="outlook"></a>[Outlook](#tab/outlook)

Se si è proprietari di un gruppo di Microsoft 365, è possibile ripristinare il gruppo manualmente in Outlook sul Web seguendo questa procedura:

1. Nella pagina Gruppi [eliminati selezionare](https://outlook.office.com/people/group/deleted)l'opzione  **Gestisci** gruppi nel nodo Gruppi e quindi scegliere **Eliminato.**

2. Fare clic sulla **scheda** Ripristina accanto al gruppo che si desidera ripristinare.

Se il gruppo eliminato non viene visualizzato qui, contattare un amministratore.

# <a name="admin-center"></a>[Interfaccia di amministrazione](#tab/admin-center)

Gli amministratori globali o di gruppi possono ripristinare un gruppo eliminato nell'interfaccia di amministrazione di Microsoft 365:

1. Passare all'[interfaccia di amministrazione](https://admin.microsoft.com).
2. Espandere **Gruppi** e quindi fare clic **su Gruppi eliminati.**
3. Selezionare il gruppo che si desidera ripristinare e quindi fare clic **su Ripristina gruppo.**

> [!NOTE]
> In alcuni casi, il ripristino del gruppo e di tutti i relativi dati può richiedere fino a 24 ore. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Hai domande sui gruppi di Microsoft 365?

Visitare la [Community tecnica Microsoft](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per pubblicare domande e partecipare a conversazioni sui gruppi di Microsoft 365. 
  
## <a name="related-articles"></a>Articoli correlati

[Gestire i gruppi di Microsoft 365 con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[Eliminare gruppi usando il cmdlet Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Gestire le impostazioni del sito del team connesso al gruppo](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Eliminare un gruppo in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
