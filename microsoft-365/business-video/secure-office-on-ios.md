---
title: Proteggere le app di Office in iOS
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come proteggere le app di Office in iOS con Microsoft 365 Business Premium.
ms.openlocfilehash: fd7fdd32500f9a2362ac29059abe9424d045c206
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928031"
---
# <a name="secure-office-apps-on-ios"></a>Proteggere le app di Office in iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Puoi configurare un criterio di accesso utente che richiede agli utenti mobili di immettere un PIN o un'impronta digitale per l'accesso e crittografa anche i file di lavoro archiviati nei dispositivi.

## <a name="try-it"></a>Perché non provarlo?

1. Accedere all'interfaccia di amministrazione di Microsoft 365.
1. In **Criteri** scegliere **Aggiungi criterio.**
1. Nel riquadro **Aggiungi criterio** immettere un nome **in** Nome criterio e scegliere il tipo di criterio desiderato in Tipo **di criterio.**
1. Attivare Gestisci **la modalità di accesso degli** utenti ai file di Office nei dispositivi mobili e quindi verificare che le tre impostazioni seguenti siano attivate:
    - **Richiedi un PIN o l'impronta digitale per accedere alle app di Office**
    - **Proteggere i file di lavoro quando i dispositivi vengono smarriti o rubati**
    - **Crittografare i file di lavoro**

1. In **File in queste app verranno protetti** selezionare le app di Office che si desidera proteggere nei dispositivi mobili.
1. In **Chi otterrà queste impostazioni,** tutti gli utenti sono  selezionati per impostazione predefinita, ma è possibile scegliere Cambia per selezionare i gruppi di sicurezza creati.
1. Per completare la creazione del criterio, scegliere **Aggiungi.**
1. Nella pagina **Aggiungi criterio** scegliere **Chiudi.**
1. Nella home page dell'interfaccia di amministrazione verificare  che il nuovo criterio sia stato aggiunto scegliendo Criteri ed esaminando il criterio nella **pagina** Criteri.