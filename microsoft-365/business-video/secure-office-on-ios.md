---
title: Proteggere le app di Office su iOS
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
description: Informazioni su come proteggere le app di Office su iOS con Microsoft 365 Business Premium.
ms.openlocfilehash: 1703faa7cd7731f0779bacc3d2fa3ad3e4556910
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702061"
---
# <a name="secure-office-apps-on-ios"></a>Proteggere le app di Office su iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

È possibile configurare un criterio di accesso utente che richiede agli utenti di dispositivi mobili di immettere un PIN o un'impronta digitale per accedere e crittografare i file di lavoro archiviati nei propri dispositivi.

## <a name="try-it"></a>Perché non provarlo?

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
1. In **criteri** scegliere **Aggiungi criterio**.
1. Nel riquadro **Aggiungi criterio** , immettere un nome in **Nome criterio** e scegliere il tipo di criteri desiderato in **tipo** di criterio.
1. Attiva **gestire la modalità di accesso degli utenti ai file di Office nei dispositivi mobili** e quindi verificare che siano attivate le tre impostazioni seguenti:
    - **Richiedi un PIN o l'impronta digitale per accedere alle app di Office**
    - **Proteggere i file di lavoro quando i dispositivi vengono persi o rubati**
    - **Crittografare i file di lavoro**

1. In **file in queste applicazioni verrà protetto**, selezionare le app di Office che si desidera proteggere nei dispositivi mobili.
1. In **chi otterrà queste impostazioni?**, tutti gli utenti sono selezionati per impostazione predefinita, ma è possibile scegliere **Cambia** per selezionare i gruppi di sicurezza creati.
1. Per completare la creazione del criterio, scegliere **Aggiungi**.
1. Nella pagina **Aggiungi criterio** scegliere **Chiudi**.
1. Nella Home page dell'interfaccia di amministrazione, verificare che il nuovo criterio sia stato aggiunto scegliendo **criteri** e rivedendo i criteri nella pagina **criteri** .