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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1636b1deb5f35d8286b33238a8f4bbfff0b33521
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288126"
---
# <a name="microsoft-365-defender-preview-features"></a>Funzionalità di anteprima di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Le versioni di anteprima vengono fornite senza un contratto di servizio e non sono consigliate per i carichi di lavoro di produzione. Alcune funzionalità potrebbero non essere supportate o avere funzionalità vincolate.

**Si applica a:**
- Microsoft 365 Defender

Il servizio Microsoft 365 Defender viene costantemente aggiornato per includere nuovi miglioramenti e funzionalità.

Informazioni sulle nuove funzionalità della versione di anteprima di Microsoft 365 Defender ed essere tra i primi a provare le funzionalità future attivando l'esperienza di anteprima.

Per altre informazioni sulle nuove funzionalità generalmente disponibili, vedere Novità [di Microsoft 365 Defender.](whats-new.md)

## <a name="required-permissions"></a>Autorizzazioni necessarie

Gli account assegnati ai ruoli di Azure Active Directory (Azure AD) seguenti possono attivare le funzionalità di Microsoft 365 Defender Preview:

- Amministratore globale
- Amministratore della sicurezza
- Operatore della sicurezza

## <a name="turn-on-preview-features"></a>Attivare funzionalità di anteprima

Avrai accesso alle funzionalità future su cui puoi fornire feedback per migliorare l'esperienza complessiva prima che le funzionalità siano disponibili in generale.

Attivare l'opzione esperienza di anteprima per essere tra i primi a provare le funzionalità che saranno introdotte.

1. Nel riquadro di spostamento selezionare **Impostazioni**.
2. Selezionare **Microsoft 365 Defender.**
3. Selezionare **Funzionalità di anteprima** > **Attivare le funzionalità di anteprima**. 
4. Selezionare **Salva**.

Se la casella di controllo **Attivare le funzionalità di anteprima** è selezionata, significa che le funzionalità di anteprima sono attivate. 

## <a name="preview-features"></a>Funzionalità di anteprima

Le caratteristiche e i miglioramenti seguenti sono attualmente disponibili in anteprima:

### <a name="improved-microsoft-365-security-center"></a>Centro sicurezza Microsoft 365 migliorato
Il nuovo [Centro sicurezza Microsoft 365](https://security.microsoft.com) è ora disponibile in anteprima pubblica. Questa nuova esperienza porta Defender per Endpoint, Defender per Office 365, Microsoft 365 Defender e altro ancora nel Centro sicurezza Microsoft 365. Questa è la nuova casa in cui gestire i controlli di sicurezza. [Informazioni sulle novità](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).

- Report analisi delle minacce di **[Microsoft 365 Defender:](threat-analytics.md)** l'analisi delle minacce consente di rispondere e ridurre al minimo l'impatto degli attacchi attivi. È inoltre possibile conoscere i tentativi di attacco bloccati dalle soluzioni di Microsoft 365 Defender ed eseguire azioni preventive che attenuano il rischio di ulteriore esposizione e aumentano la resilienza. Come parte dell'esperienza di sicurezza unificata, l'analisi delle minacce è ora disponibile per i titolari della licenza di Microsoft Defender per Endpoint e Microsoft Defender per Office E5.
- API di **[Microsoft 365 Defender:](api-overview.md)** le API di Microsoft 365 Defender di primo livello consentono di automatizzare i flussi di lavoro in base all'evento condiviso e alle tabelle di ricerca avanzata. 
- **[Intervenire nella ricerca avanzata:](advanced-hunting-take-action.md)** è possibile contenere rapidamente minacce o risolvere le risorse compromesse che si trovano nella [ricerca avanzata.](advanced-hunting-overview.md)
- **[Informazioni di riferimento sullo schema nel](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** portale: informazioni sulle tabelle dello schema di ricerca avanzata direttamente nel Centro sicurezza. Oltre alle descrizioni di tabelle e colonne, questo riferimento include tipi di evento supportati `ActionType` (valori) e query di esempio.
- **[Funzione DeviceFromIP():](advanced-hunting-devicefromip-function.md)** consente di ottenere informazioni sui dispositivi a cui è stato assegnato uno o più indirizzi IP specifici in un determinato intervallo di tempo.
