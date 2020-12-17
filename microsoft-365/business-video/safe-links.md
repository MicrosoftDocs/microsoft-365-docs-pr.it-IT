---
title: Gestire i collegamenti sicuri
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Informazioni su come gestire i collegamenti sicuri per proteggere la propria azienda da siti dannosi.
ms.openlocfilehash: eabb2c1f71b1183867ffcb005ba4f7e44ed6e4b7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702069"
---
# <a name="manage-safe-links"></a>Gestire i collegamenti sicuri

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender per Office 365, precedentemente denominato Microsoft 365 ATP o Advanced Threat Protection, consente di proteggere la propria azienda da siti dannosi quando gli utenti fanno clic su collegamenti nelle app di Office.

## <a name="try-it"></a>Perché non provarlo?

1. Accedere all'interfaccia di [Amministrazione](https://admin.microsoft.com)e selezionare **Setup**.
1. Scorrere verso il basso per **aumentare la protezione dalle minacce avanzate**. Selezionare **Visualizza**, **Gestisci** e quindi **collegamenti sicuri ATP**.
1. In **criteri che si applicano all'intera organizzazione**, scegliere il criterio **predefinito** , quindi selezionare l'icona **modifica** .
1. Immettere un URL che si desidera bloccare.
1. Selezionare **Usa collegamenti sicuri nelle app di Office, Office per iOS e Android**; Selezionare non **monitorare quando gli utenti fanno clic su collegamenti sicuri**; e seleziona non **consentire agli utenti di fare clic su collegamenti sicuri all'URL originale**. Questi potrebbero essere già selezionati se si configura il criterio predefinito. Selezionare **Salva**.
1. In **criteri che si applicano a destinatari specifici**, scegliere **regola collegamenti sicuri consigliati**, quindi selezionare l'icona **modifica** .
1. Selezionare **Impostazioni**, scorrere verso il basso, immettere l'URL che non si desidera controllare e quindi selezionare l'icona **Aggiungi** .
1. Selezionare **applicato a**, quindi selezionare il nome di dominio. Selezionare gli eventuali domini aggiuntivi a cui si desidera applicare la regola. Fare clic su **Aggiungi**, **OK** e quindi su **Salva**.

I collegamenti sicuri ATP sono ora configurati. Consenti fino a 30 minuti affinché le modifiche abbiano effetto.

Quando un utente riceve un messaggio di posta elettronica con collegamenti, i collegamenti verranno analizzati. Se i collegamenti sono considerati sicuri, sarà possibile selezionarli. Tuttavia, se il collegamento è presente nell'elenco bloccato, gli utenti visualizzeranno un messaggio che è stato bloccato.