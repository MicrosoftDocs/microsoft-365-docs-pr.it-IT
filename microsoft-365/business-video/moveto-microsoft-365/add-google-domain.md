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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come spostare il dominio da Google Workspace a Microsoft 365 for business.
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794673"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Aggiungere il dominio di Google Workspace a Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Aggiungere il dominio di Google Workspace a Microsoft 365 for business in modo da poter continuare a utilizzare l'indirizzo di posta elettronica aziendale.

## <a name="try-it"></a>Perché non provarlo?

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).
1. Nell'interfaccia di amministrazione di Microsoft 365, nella barra di spostamento sinistra, selezionare **Mostra tutto**, **Impostazioni** e quindi **domini**.
1. Scegliere **Aggiungi dominio**, immettere il proprio nome di dominio, quindi selezionare **Usa questo dominio**. 
1. Scegliere, **aggiungere un record TXT ai record DNS dei domini**, selezionare **continua** e copiare il valore txt. 
1. Tornare alla console di [amministrazione di Google](https://admin.google.com), scegliere **Domains**, **Manage** Domains, **View details**, **Manage Domain**, **DNS**, quindi scorrere verso il basso fino a **record di risorse personalizzati**. 
1. Aprire il menu a discesa tipo di record, scegliere **txt**, incollare il valore txt copiato e quindi selezionare **Aggiungi**. 

    L'aggiornamento di solito richiede un dato di fatto in pochi minuti, ma può richiedere fino a 48 ore. 
1. Tornare all'interfaccia di amministrazione di Microsoft 365, selezionare **Verifica** e quindi **Chiudi**. 
1. Per impostare il dominio come messaggio di posta elettronica principale per gli utenti, nel NAV **sinistro selezionare utenti**  >  **attivi**. 
1. Scegliere un utente, selezionare **Gestisci nome utente e posta elettronica**, **modifica**, selezionare il dominio dall'elenco a discesa, quindi fare clic su **fine** e **salvare le modifiche**. 
1. Ripetere questa procedura per ogni utente. 

    Al termine dell'installazione, sarà possibile installare le app di Office e migrare gli elementi di posta elettronica e del calendario a Microsoft 365. 