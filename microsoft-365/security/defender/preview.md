---
title: Funzionalità di anteprima in Microsoft 365 Defender
description: Ulteriori informazioni sulle nuove funzionalità nella Sicurezza Microsoft 365
keywords: anteprima, novità, sicurezza m365, sicurezza, 365, funzionalità
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8ad5ffe2b175a8f7a42b2fad353fcde13a60cfec
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730523"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Funzionalità di anteprima di Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Le versioni di anteprima vengono fornite senza un contratto di servizio e non sono consigliate per i carichi di lavoro di produzione. Alcune funzionalità potrebbero non essere supportate o avere funzionalità vincolate.

**Si applica a:**
- Microsoft 365 Defender

Il Microsoft 365 Defender è costantemente aggiornato per includere nuovi miglioramenti e funzionalità.

Scopri le nuove funzionalità nella versione di Microsoft 365 Defender Preview ed essere tra i primi a provare le funzionalità future attivando l'esperienza di anteprima.

Per altre informazioni sulle nuove funzionalità disponibili in genere, vedi Novità [di Microsoft 365 Defender.](whats-new.md)

## <a name="required-permissions"></a>Autorizzazioni necessarie

Gli account assegnati ai ruoli Azure Active Directory (Azure AD) seguenti possono attivare Microsoft 365 Defender Preview:

- Amministratore globale
- Amministratore della sicurezza
- Operatore della sicurezza

## <a name="turn-on-preview-features"></a>Attivare funzionalità di anteprima

Avrai accesso alle funzionalità future su cui puoi fornire feedback per migliorare l'esperienza complessiva prima che le funzionalità siano generalmente disponibili.

Attivare l'opzione esperienza di anteprima per essere tra i primi a provare le funzionalità che saranno introdotte.

1. Nel riquadro di spostamento selezionare **Impostazioni**.
2. Selezionare **Microsoft 365 Defender**.
3. Selezionare **Funzionalità di anteprima** > **Attivare le funzionalità di anteprima**. 
4. Selezionare **Salva**.

Se la casella di controllo **Attivare le funzionalità di anteprima** è selezionata, significa che le funzionalità di anteprima sono attivate. 

## <a name="preview-features"></a>Funzionalità di anteprima

Le caratteristiche e i miglioramenti seguenti sono attualmente disponibili in anteprima:

- **[API di streaming:](../defender-endpoint/raw-data-export.md)** Microsoft 365 Defender supporta lo streaming di tutti gli eventi disponibili tramite Advanced Hunting a un hub eventi e/o a un account di archiviazione di Azure.
- **[Microsoft 365 Defender API:](api-overview.md)** le API di Microsoft 365 Defender di primo livello ti consentiranno di automatizzare i flussi di lavoro in base agli eventi imprevisti condivisi e alle tabelle di ricerca avanzate. 
- **[Eseguire azioni nella ricerca avanzata-](advanced-hunting-take-action.md)** Contiene rapidamente minacce o indirizzi di asset compromessi che si trovano nella [ricerca avanzata.](advanced-hunting-overview.md)
- **[Informazioni di riferimento sullo schema nel](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** portale- Ottenere informazioni sulle tabelle dello schema di ricerca avanzata direttamente nel Centro sicurezza. Oltre alle descrizioni di tabelle e colonne, questo riferimento include tipi di eventi supportati `ActionType` (valori) e query di esempio.
- **[Funzione DeviceFromIP():](advanced-hunting-devicefromip-function.md)** consente di ottenere informazioni sui dispositivi a cui è stato assegnato uno o più indirizzi IP specifici in un determinato intervallo di tempo.
