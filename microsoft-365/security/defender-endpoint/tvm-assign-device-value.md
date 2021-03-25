---
title: Assegnare il valore del dispositivo - gestione delle minacce e delle vulnerabilità
description: Scopri come assegnare un valore basso, normale o elevato a un dispositivo per distinguere le priorità degli asset.
keywords: valore del dispositivo microsoft defender atp, valore del dispositivo di gestione delle minacce e delle vulnerabilità, dispositivi ad alto valore, punteggio di esposizione al valore del dispositivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: be578158e18d55bb25d450749c3fb4373854456b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065997"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a>Assegnare il valore del dispositivo - gestione delle minacce e delle vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Gestione di minacce e vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

La definizione del valore di un dispositivo consente di distinguere le priorità degli asset. Il valore del dispositivo viene utilizzato per incorporare la propensione al rischio di un singolo asset nel calcolo del punteggio di esposizione alla gestione delle minacce e delle vulnerabilità. I dispositivi assegnati come "valore elevato" riceveranno più peso.

Puoi anche usare [l'API set device value](set-device-value.md).

Opzioni valore dispositivo:

- Basso
- Normale (impostazione predefinita)
- Alto

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

- [Panoramica della gestione delle minacce e delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Punteggio di esposizione](tvm-exposure-score.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)