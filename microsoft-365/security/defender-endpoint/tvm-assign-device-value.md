---
title: Assegna valore dispositivo - gestione di minacce e vulnerabilità
description: Scopri come assegnare un valore basso, normale o elevato a un dispositivo per distinguere le priorità degli asset.
keywords: Valore del dispositivo Microsoft Defender for Endpoint, gestione di minacce e vulnerabilità dispositivo, dispositivi ad alto valore, punteggio di esposizione al valore del dispositivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ca6c88b08b331eb65035387a9c070d0914b1651d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935198"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a>Assegna valore dispositivo - gestione di minacce e vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Minaccia e gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

La definizione del valore di un dispositivo consente di distinguere le priorità degli asset. Il valore del dispositivo viene usato per incorporare la propensione al rischio di un singolo asset nel calcolo gestione di minacce e vulnerabilità del punteggio di esposizione. I dispositivi assegnati come "valore elevato" riceveranno più peso.

Puoi anche usare [l'API set device value](set-device-value.md).

Opzioni valore dispositivo:

- Bassa
- Normale (impostazione predefinita)
- Fortemente

Esempi di dispositivi a cui assegnare un valore elevato:

- Controller di dominio, Active Directory
- Dispositivi con connessione Internet
- Dispositivi VIP
- Dispositivi che ospitano servizi di produzione interni/esterni

## <a name="choose-device-value"></a>Scegliere il valore del dispositivo

1. Passare a qualsiasi pagina del dispositivo, il posto più semplice è dall'inventario dei dispositivi.

2. Seleziona **Valore dispositivo** da tre punti accanto alla barra delle azioni nella parte superiore della pagina.

    ![Esempio dell'elenco a discesa del valore del dispositivo.](images/tvm-device-value-dropdown.png)

3. Verrà visualizzato un riquadro a comparsa con il valore corrente del dispositivo e il relativo significato. Esamina il valore del dispositivo e scegli quello più adatto al tuo dispositivo.
![Esempio del riquadro a comparsa del valore del dispositivo.](images/tvm-device-value-flyout.png)

## <a name="how-device-value-impacts-your-exposure-score"></a>Impatto del valore del dispositivo sul punteggio di esposizione

Il punteggio di esposizione è una media ponderata in tutti i dispositivi. Se hai gruppi di dispositivi, puoi anche filtrare il punteggio in base al gruppo di dispositivi.

- I dispositivi normali hanno un peso di 1
- I dispositivi a basso valore hanno un peso di 0,75
- I dispositivi ad alto valore hanno un peso di NumberOfAssets / 10.
    - Se hai 100 dispositivi, ogni dispositivo ad alto valore avrà un peso di 10 (100/10)

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica delle minacce gestione delle vulnerabilità sicurezza](next-gen-threat-and-vuln-mgt.md)
- [Punteggio di esposizione](tvm-exposure-score.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)