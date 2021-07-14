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
ms.openlocfilehash: 088dbd16c3667331843ff934c80f85aa8d3a837f
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430817"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender funzionalità di anteprima

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Il Microsoft 365 Defender viene costantemente aggiornato per includere nuovi miglioramenti e funzionalità.

Informazioni sulle nuove funzionalità nella versione Microsoft 365 Defender anteprima ed essere tra i primi a provare le funzionalità future attivando l'esperienza di anteprima.

Per ulteriori informazioni sulle nuove funzionalità disponibili in genere, vedere [Novità di Microsoft 365 Defender](whats-new.md).

 ## <a name="what-you-need-to-know"></a>Cosa è necessario sapere

Quando si lavora con le funzionalità in anteprima pubblica, queste funzionalità:

- Può avere funzionalità limitate o limitate. Ad esempio, la funzionalità può essere applicata solo a una piattaforma.
- In genere, le modifiche delle funzionalità vengono apportate prima che siano disponibili in genere.
- Sono completamente supportati da Microsoft.
- Può essere disponibile solo in aree geografiche o ambienti cloud selezionati. Ad esempio, la funzionalità potrebbe non esistere nel cloud per enti pubblici.
- Le singole funzionalità in anteprima possono avere più restrizioni di utilizzo e supporto. In tal caso, queste informazioni vengono in genere riportate nella documentazione relativa alle funzionalità.
- Le versioni di anteprima sono fornite con un livello di supporto standard e possono essere utilizzate per gli ambienti di produzione. 



## <a name="required-permissions"></a>Autorizzazioni necessarie

Gli account assegnati ai ruoli Azure Active Directory (Azure AD) seguenti possono attivare le funzionalità Microsoft 365 Defender Preview:

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

- **[Visualizzare report per tag di minaccia:](threat-analytics.md#view-reports-per-threat-tags)** i tag di minaccia consentono di concentrarsi su categorie di minacce specifiche ed esaminare i report più rilevanti.
- **[API di streaming:](../defender-endpoint/raw-data-export.md)** Microsoft 365 Defender supporta lo streaming di tutti gli eventi disponibili tramite Advanced Hunting a un hub eventi e/o a un account di archiviazione di Azure.
- **[Microsoft 365 Defender API:](api-overview.md)** le API di Microsoft 365 Defender di primo livello consentono di automatizzare i flussi di lavoro in base alle tabelle di ricerca avanzate e degli eventi imprevisti condivisi. 
- **[Eseguire azioni nella ricerca avanzata-](advanced-hunting-take-action.md)** Contiene rapidamente minacce o indirizzi di asset compromessi che si trovano nella [ricerca avanzata.](advanced-hunting-overview.md)
- **[Informazioni di riferimento sullo schema nel](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** portale- Ottenere informazioni sulle tabelle dello schema di ricerca avanzata direttamente nel Centro sicurezza. Oltre alle descrizioni di tabelle e colonne, questo riferimento include tipi di eventi supportati `ActionType` (valori) e query di esempio.
- **[Funzione DeviceFromIP():](advanced-hunting-devicefromip-function.md)** consente di ottenere informazioni sui dispositivi a cui è stato assegnato uno o più indirizzi IP specifici in un determinato intervallo di tempo.
