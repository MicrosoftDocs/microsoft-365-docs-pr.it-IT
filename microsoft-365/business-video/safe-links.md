---
title: Gestire Cassaforte collegamenti
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come gestire i Cassaforte per proteggere l'azienda da siti dannosi.
ms.openlocfilehash: 7e6b4507cd363a448812b48e3eafc7f4c077be3c
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177514"
---
# <a name="manage-safe-links"></a>Gestire Cassaforte collegamenti

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender per Office 365 , in precedenza denominato Microsoft 365 ATP o Advanced Threat Protection, consente di proteggere l'azienda da siti dannosi quando gli utenti fa clic sui collegamenti nelle Office app.

## <a name="try-it"></a>Perché non provarlo?

1. Accedere [all'interfaccia di amministrazione](https://admin.microsoft.com)e selezionare **Installazione**.
2. Scorrere verso il basso **fino a Aumentare la protezione dalle minacce avanzate.** Selezionare **Gestisci** e quindi fare clic **Cassaforte collegamenti.**
3. Selezionare **Global Impostazioni** e in Block the following **URLs** immettere l'URL che si desidera bloccare.
4. Seleziona Usa collegamenti **Cassaforte nell'app Office 365**, seleziona Non tenere traccia quando gli utenti fanno clic su collegamenti protetti nelle app **Office 365** e seleziona Non consentire agli utenti di passare all'URL originale nelle app **Office 365**. Questi criteri potrebbero essere già selezionati se si configura il criterio predefinito. Selezionare **Salva**.

Cassaforte I collegamenti sono ora configurati. Consentire fino a 30 minuti per l'applicazione delle modifiche.

Quando un utente riceve un messaggio di posta elettronica con collegamenti, i collegamenti vengono analizzati. Se i collegamenti sono considerati sicuri, saranno selezionabili. Tuttavia, se il collegamento si trova nell'elenco bloccato, gli utenti visualizzano un messaggio che indica che è stato bloccato.
