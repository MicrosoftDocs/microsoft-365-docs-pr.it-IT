---
title: Gestire collegamenti sicuri
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
description: Informazioni su come gestire collegamenti sicuri per proteggere l'azienda da siti dannosi.
ms.openlocfilehash: 0f0cc6845f699ba5b05c30e21f876f4b4d47b6a6
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422244"
---
# <a name="manage-safe-links"></a>Gestire collegamenti sicuri

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender per Office 365, in precedenza denominato Microsoft 365 ATP o Advanced Threat Protection, consente di proteggere l'azienda da siti dannosi quando gli utenti selezionano collegamenti nelle app di Office.

## <a name="try-it"></a>Perché non provarlo?

1. Accedere [all'interfaccia di amministrazione](https://admin.microsoft.com)e selezionare **Installazione.**
1. Scorrere verso il basso **fino ad aumentare la protezione dalle minacce avanzate.** Selezionare **Visualizza,** **Gestisci** e quindi **Collegamenti sicuri ATP.**
1. In **Criteri applicabili all'intera organizzazione** scegliere il criterio predefinito e quindi selezionare l'icona Modifica.  
1. Immettere un URL che si desidera bloccare.
1. Selezionare **Usa collegamenti sicuri nelle app di Office, Office per iOS e Android;** selezionare **Non tenere traccia quando gli utenti fanno clic su collegamenti sicuri;** e selezionare **Non consentire agli utenti di fare clic su collegamenti sicuri all'URL originale.** Questi criteri potrebbero essere già selezionati se si configura il criterio predefinito. Selezionare **Salva**.
1. In **Criteri applicabili a destinatari specifici** scegliere Regola collegamenti sicuri **consigliati** e quindi selezionare l'icona Modifica. 
1. Selezionare **le** impostazioni, scorrere verso il basso, immettere l'URL che non si desidera controllare e quindi selezionare **l'icona** Aggiungi.
1. Selezionare **applicato a** e quindi selezionare il nome di dominio. Selezionare eventuali domini aggiuntivi a cui si desidera applicare la regola. Selezionare **Aggiungi**, **OK** e quindi **Salva.**

I collegamenti sicuri di ATP sono ora configurati. Consentire fino a 30 minuti per l'applicazione delle modifiche.

Quando un utente riceve un messaggio di posta elettronica con collegamenti, i collegamenti vengono analizzati. Se i collegamenti sono considerati sicuri, saranno selezionabili. Tuttavia, se il collegamento si trova nell'elenco dei contatti bloccati, gli utenti visualizzano un messaggio che indica che è stato bloccato.