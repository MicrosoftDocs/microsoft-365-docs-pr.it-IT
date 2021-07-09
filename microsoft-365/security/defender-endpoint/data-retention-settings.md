---
title: Verificare il percorso di archiviazione dei dati e aggiornare le impostazioni di conservazione dei dati
description: Verificare il percorso di archiviazione dei dati e aggiornare le impostazioni di conservazione dei dati per Microsoft Defender for Endpoint
keywords: dati, archiviazione, impostazioni, conservazione, aggiornamento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: eb9e4b905112d3d144b10d68418695df3cda29cb
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339251"
---
# <a name="verify-data-storage-location-and-update-data-retention-settings-for-microsoft-defender-for-endpoint"></a>Verificare il percorso di archiviazione dei dati e aggiornare le impostazioni di conservazione dei dati per Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-gensettings-abovefoldlink)

Durante il processo di onboarding, una procedura guidata consente di passare attraverso le impostazioni di archiviazione e conservazione dei dati di Defender per Endpoint. 

Dopo aver completato l'onboarding, puoi verificare la selezione nella pagina delle impostazioni di conservazione dei dati.

## <a name="verify-data-storage-location"></a>Verificare il percorso di archiviazione dei dati
Durante la [fase di configurazione,](production-deployment.md)è necessario selezionare la posizione in cui archiviare i dati. 

È possibile verificare la posizione dei dati accedendo a **Impostazioni**  >  **endpoint Conservazione** dei  >  **dati**.

## <a name="update-data-retention-settings"></a>Aggiornare le impostazioni di conservazione dei dati

È possibile aggiornare le impostazioni di conservazione dei dati. Per impostazione predefinita, il periodo di conservazione è 180 giorni. 

1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **endpoint**  >  **Conservazione dati**.

2. Selezionare la durata di conservazione dei dati nell'elenco a discesa.

    > [!NOTE]
    > Altre impostazioni non sono modificabili.

3. Fare **clic su Salva preferenze.**


## <a name="related-topics"></a>Argomenti correlati
- [Aggiornare le impostazioni di conservazione dei dati](data-retention-settings.md)
- [Configurare le notifiche di avviso in Defender per Endpoint](configure-email-notifications.md)
- [Configurare le funzionalità avanzate](advanced-features.md)
