---
title: Aggiungere il dominio di Google Workspace
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come spostare il dominio da Google Workspace a Microsoft 365 per le aziende.
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925003"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Aggiungere il dominio di Google Workspace a Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Aggiungere il dominio di Google Workspace a Microsoft 365 per le aziende in modo da poter continuare a usare l'indirizzo di posta elettronica dell'azienda.

## <a name="try-it"></a>Perché non provarlo?

1. Passare all'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com)
1. Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento sinistro, selezionare **Mostra tutto**, **Impostazioni** e quindi **Domini.**
1. Choose **Add domain**, enter your domain name then select Use this **domain.** 
1. Choose, **Add a TXT record to the domains DNS records,** select **Continue**, and copy the TXT value. 
1. Tornare alla Console di amministrazione di [Google,](https://admin.google.com)scegliere **Domini,** Gestisci **domini,** Visualizza **dettagli,** Gestisci **dominio,** **DNS** e quindi scorrere verso il basso fino a Record di **risorse personalizzati.** 
1. Aprire l'elenco a discesa relativo al tipo di record, scegliere **TXT,** incollare il valore TXT copiato e selezionare **Aggiungi.** 

    L'aggiornamento in genere richiede alcuni minuti, ma può richiedere fino a 48 ore. 
1. Tornare all'interfaccia di amministrazione di Microsoft 365, selezionare **Verifica** e quindi **Chiudi.** 
1. Per impostare il dominio come posta elettronica principale per gli utenti, nel riquadro di spostamento sinistro selezionare **Utenti**  >  **attivi.** 
1. Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**. 
1. Ripetere questo processo per ogni utente. 

    Al termine, sarà possibile installare le app di Office ed eseguire la migrazione della posta elettronica e degli elementi del calendario a Microsoft 365. 