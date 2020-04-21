---
title: Ripristinare un gruppo eliminato
ms.reviewer: arvaradh
f1.keywords: CSH
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Informazioni su come ripristinare un gruppo di Microsoft 365 eliminato.
ms.openlocfilehash: a0e7aef090528b3fa183fe08f9c4d06c86f94a10
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630032"
---
# <a name="restore-a-deleted-group"></a>Ripristinare un gruppo eliminato

Se si è eliminato un gruppo, questo verrà mantenuto per 30 giorni per impostazione predefinita. Questo periodo di 30 giorni è considerato "soft-delete" perché è ancora possibile ripristinare il gruppo. Dopo 30 giorni, il gruppo e il relativo contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.

Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:
  
- Oggetto, proprietà e membri di Azure Active Directory (AD) Microsoft 365 groups.
    
- Indirizzi di posta elettronica del gruppo.
    
- Posta in arrivo condivisa e calendario di Exchange Online.
    
- Sito e file del team di SharePoint Online.
    
- Blocco appunti di OneNote
    
- Planner
    
- Teams

- Gruppo di Yammer e contenuto del gruppo (se il gruppo Microsoft 365 è stato creato da Yammer)

## <a name="restore-a-group-that-you-own-by-using-outlook"></a>Ripristinare un gruppo personalizzato tramite Outlook

Se si è il proprietario di un gruppo di Microsoft 365, è possibile ripristinare il gruppo manualmente in Outlook attenendosi alla procedura seguente:

1. Nella [pagina Gruppi eliminati](https://outlook.office.com/people/group/deleted)selezionare l'opzione **Gestisci gruppi** nel nodo **gruppi** e quindi scegliere **eliminata**.

2. Fare clic sulla scheda **Ripristina** accanto al gruppo che si desidera ripristinare.

Se il gruppo eliminato non viene visualizzato, contattare un amministratore.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Ripristinare un gruppo nell'interfaccia di amministrazione di Microsoft 365

Se si è amministratori globali o amministratori di gruppi, è possibile ripristinare un gruppo eliminato nell'interfaccia di amministrazione di Microsoft 365:

1. Accedere all'interfaccia di [Amministrazione](https://admin.microsoft.com).
2. Espandere **gruppi**e quindi fare clic su **gruppi eliminati**.
3. Selezionare il gruppo che si desidera ripristinare e quindi fare clic su **Ripristina gruppo**.
  
## <a name="permanently-delete-a-microsoft-365-group"></a>Eliminare definitivamente un gruppo di Microsoft 365

A volte è possibile che si desideri eliminare definitivamente un gruppo senza attendere la scadenza del periodo di cancellazione di 30 giorni. A tale scopo, avviare PowerShell ed eseguire questo comando per ottenere l'ID oggetto del gruppo:
  
```
Get-AzureADMSDeletedGroup
```

Prendere nota dell'ID oggetto del gruppo o dei gruppi che si desidera eliminare definitivamente.
  
> [!CAUTION]
> Il gruppo e i dati che contiene vengono eliminati in modo definitivo. 
  
Per eliminare il gruppo, eseguire questo comando in PowerShell:
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

Per verificare che il gruppo sia stato eliminato correttamente, eseguire di nuovo il cmdlet  *Get-AzureADMSDeletedGroup*  per controllare che il gruppo non compaia più nell'elenco dei gruppi eliminati temporaneamente. In alcuni casi l'eliminazione definitiva del gruppo e di tutti i suoi dati può richiedere fino a 24 ore. 
  
## <a name="got-questions-about-microsoft-365-groups"></a>Hai domande sui gruppi di Microsoft 365?

Visitare la [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per inviare domande e partecipare a conversazioni sui gruppi di Microsoft 365. 
  
## <a name="related-articles"></a>Articoli correlati

[Gestire i gruppi Microsoft 365 con PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[Eliminare gruppi usando il cmdlet Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Gestire le impostazioni del sito del team connesso al gruppo](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Eliminare un gruppo in Outlook](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
