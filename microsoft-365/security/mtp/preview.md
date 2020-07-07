---
title: Funzionalità di anteprima di Microsoft Threat Protection
description: Informazioni sulle nuove funzionalità di sicurezza di Microsoft 365
keywords: anteprima, nuovo, sicurezza di M365, sicurezza, 365, funzionalità
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 45bc42e825c55ca228b13e8d308f9a1384301d07
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048268"
---
# <a name="microsoft-threat-protection-preview-features"></a>Funzionalità di anteprima di Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection


Il servizio Microsoft Threat Protection viene costantemente aggiornato per includere nuove funzionalità e miglioramenti delle funzionalità.

Informazioni sulle nuove funzionalità di Microsoft Threat Protection Preview Release ed essere tra i primi a provare le funzionalità imminenti attivando l'esperienza di anteprima.

Per altre informazioni sulle nuove funzionalità disponibili a livello generale, vedere [Novità di Microsoft Threat Protection](whats-new.md).

## <a name="turn-on-preview-features"></a>Abilitare le funzionalità di anteprima
È possibile accedere alle funzionalità imminenti che possono fornire commenti e suggerimenti utili per migliorare l'esperienza complessiva prima che le funzionalità siano generalmente disponibili.

Attiva l'impostazione Anteprima esperienza per essere tra i primi a provare le funzionalità imminenti.

1. Nel riquadro di spostamento, selezionare **Impostazioni**.

2. Selezionare **Microsoft Threat Protection**.


3. Seleziona **funzionalità**  >  **di anteprima attiva le funzionalità di anteprima**. 

3. Seleziona **Salva**.

Quando si vede che è selezionata la casella di controllo attiva le caratteristiche di **Anteprima** , si noterà che è attiva la funzionalità di anteprima. 

## <a name="preview-features"></a>Funzionalità di anteprima
Le caratteristiche e i miglioramenti seguenti sono attualmente disponibili in anteprima:

- **[Riferimenti allo schema in-Portal](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** -informazioni sulle tabelle dello schema disponibili direttamente nel centro sicurezza. Oltre alle descrizioni di tabelle e colonne, questo riferimento fornisce informazioni sui tipi di evento supportati ( `ActionType` valori) e sulle query di esempio.  

- **[Tabelle di identità e app](advanced-hunting-schema-tables.md)** : consente di ottenere visibilità negli eventi di autenticazione, nelle query di Active Directory e nell'attività correlata all'applicazione con le tabelle [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)e [AppFileEvents](advanced-hunting-appfileevents-table.md) nello schema di caccia avanzato.

- **[Vai a cercare](advanced-hunting-go-hunt.md)** : rapidamente pivot dall'indagine di un incidente per esaminare un evento specifico, un utente, un dispositivo o altri tipi di entità che utilizzano funzionalità di [ricerca avanzata](advanced-hunting-overview.md) basate su query.

- **[Funzione fileprofile ()](advanced-hunting-fileprofile-function.md)** : utilizzare nelle query di [caccia avanzate](advanced-hunting-overview.md) per incorporare informazioni complete sui file.
