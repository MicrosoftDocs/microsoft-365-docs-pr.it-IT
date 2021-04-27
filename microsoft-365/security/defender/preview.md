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
ms.openlocfilehash: c82e1abf9e539ad169bbc488ade9cd21bb8e6727
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029075"
---
# <a name="microsoft-365-defender-preview-features"></a>Funzionalità di anteprima di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Le versioni di anteprima vengono fornite senza un contratto di servizio e non sono consigliate per i carichi di lavoro di produzione. Alcune funzionalità potrebbero non essere supportate o avere funzionalità vincolate.

**Si applica a:**
- Microsoft 365 Defender

Il servizio Microsoft 365 Defender viene costantemente aggiornato per includere nuovi miglioramenti e funzionalità.

Informazioni sulle nuove funzionalità nella versione di anteprima di Microsoft 365 Defender e essere tra i primi a provare le funzionalità future attivando l'esperienza di anteprima.

Per ulteriori informazioni sulle nuove funzionalità disponibili in genere, vedere [Novità di Microsoft 365 Defender.](whats-new.md)

## <a name="required-permissions"></a>Autorizzazioni necessarie

Gli account assegnati ai ruoli di Azure Active Directory (Azure AD) seguenti possono attivare le funzionalità di Microsoft 365 Defender Preview:

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

- **[API di Microsoft 365 Defender:](api-overview.md)** le API di Microsoft 365 Defender di primo livello ti consentiranno di automatizzare i flussi di lavoro in base alle tabelle di ricerca avanzate e degli eventi imprevisti condivisi. 
- **[Intervenire nella ricerca avanzata:](advanced-hunting-take-action.md)** è possibile contenere rapidamente minacce o affrontare asset compromessi che si trovano nella [ricerca avanzata.](advanced-hunting-overview.md)
- **[Riferimento allo schema nel portale:](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** informazioni sulle tabelle dello schema di ricerca avanzate direttamente nel Centro sicurezza. Oltre alle descrizioni di tabelle e colonne, questo riferimento include tipi di eventi supportati `ActionType` (valori) e query di esempio.
- **[Funzione DeviceFromIP():](advanced-hunting-devicefromip-function.md)** consente di ottenere informazioni sui dispositivi a cui è stato assegnato uno o più indirizzi IP specifici in un determinato intervallo di tempo.
