---
title: Ricezione dell'errore "Non è stato possibile trovare una cassetta postale per" in Outlook sul web
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: L'errore **Non è stato possibile trovare una cassetta postale per** indica che l'account usato per connettersi a Outlook sul web non ha una licenza di Exchange Online.
ms.openlocfilehash: cb82f917adca8f1fc183fd9516321a524c63eb69
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635787"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a>Si sta ricevendo l'errore "Non è stato possibile trovare una cassetta postale per" in Outlook sul web?

Se si usa Outlook sul web e viene visualizzato l'errore **Non è stato possibile trovare una cassetta postale per**, l'account usato per connettersi a Outlook sul Web non ha una licenza di Exchange Online. Pertanto, nessuna cassetta postale è associata all'account. 

## <a name="assign-a-license-to-your-account"></a>Assegnare una licenza all'account

L'amministratore può assegnare una licenza all'account seguendo questa procedura:

1. Aprire l'[interfaccia di amministrazione di Microsoft 365](https://portal.office.com/adminportal/home#/homepage) e passare a **Utenti attivi** nella sezione **Utenti** e infine scegliere l'utente che sta visualizzando l'errore.
1. Nella pagina utente che si apre, passare alla sezione **Licenze e app**, selezionare il valore **Posizione** appropriato e assegnare una licenza contente Exchange Online (espandere la licenza per visualizzare i dettagli). 
1. Al termine, fare clic su **Salva modifiche**.

## <a name="related-content"></a>Contenuto correlato

[Aggiungere un altro alias di posta elettronica per un utente](../email/add-another-email-alias-for-a-user.md) (articolo)\
[Configurare l'inoltro della posta elettronica in Microsoft 365](../email/configure-email-forwarding.md) (articolo)\
[Creare una cassetta postale condivisa](../email/create-a-shared-mailbox.md) (articolo)