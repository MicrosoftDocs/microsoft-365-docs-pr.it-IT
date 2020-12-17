---
title: Gestire i criteri per i dispositivi Windows 10 Pro con Microsoft 365 Business Premium
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
description: Informazioni su come gestire i criteri per i dispositivi Windows 10 Pro con Microsoft 365 Business Premium.
ms.openlocfilehash: 9052859f03035a76bf69b7c8c23c75ae00353846
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703194"
---
# <a name="manage-windows-10-pro-device-policies"></a>Gestire i criteri per i dispositivi Windows 10 Pro

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

È possibile utilizzare Microsoft 365 business per garantire che Windows Defender antivirus sia attivato nei dispositivi Windows 10 e che Microsoft Updates venga scaricato automaticamente nei dispositivi degli utenti.

## <a name="try-it"></a>Perché non provarlo?

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
1. In **criteri** scegliere Aggiungi criterio.
1. Nel riquadro **Aggiungi criterio** , immettere un nome in **Nome criterio** e quindi selezionare **Configurazione dispositivo Windows 10** in tipo di **criterio**.
1. Scegliere **Secure Windows 10 Devices** per visualizzare le impostazioni secondarie.
1. Assicurarsi che la **protezione dei PC da virus e altre minacce tramite Windows Defender Antivirus** e che i **dispositivi Windows 10** siano aggiornati automaticamente siano attivati.
1. In **chi otterrà queste impostazioni?**, tutti gli utenti sono selezionati per impostazione predefinita, ma è possibile scegliere **Cambia** per selezionare i gruppi di sicurezza creati.
1. Per completare la creazione del criterio, scegliere **Aggiungi**.
1. Nella pagina **Aggiungi criterio** scegliere **Chiudi**.
1. Nella Home page dell'interfaccia di amministrazione, verificare che il nuovo criterio sia stato aggiunto scegliendo **criteri** e rivedendo i criteri nella pagina **criteri** .
1. Per verificare che il criterio abbia avuto effetto, nel dispositivo Windows 10 di un utente passare a Windows Update, scegliere **Opzioni avanzate** e verificare che le impostazioni siano disabilitate.

    Fare quindi clic su **Scegli la modalità** di recapito degli aggiornamenti e verificare che le impostazioni siano disabilitate e che venga visualizzato il messaggio seguente: **alcune impostazioni sono nascoste o gestite dall'organizzazione**.

