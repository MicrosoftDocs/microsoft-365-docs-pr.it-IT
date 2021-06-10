---
title: Report dispositivi vulnerabili - gestione di minacce e vulnerabilità
description: Report che mostra le tendenze dei dispositivi vulnerabili e le statistiche correnti. L'obiettivo è comprendere il respiro e l'ambito dell'esposizione del dispositivo.
keywords: Microsoft Defender for Endpoint-tvm vulnerable devices, Microsoft Defender for Endpoint, tvm, reduce threat & vulnerability exposure, reduce threat and vulnerability, monitor security configuration
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
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245481"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>Report dispositivi vulnerabili - gestione di minacce e vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Minaccia e gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Il report mostra grafici e grafici a barre con tendenze dei dispositivi vulnerabili e statistiche correnti. L'obiettivo è comprendere il respiro e l'ambito dell'esposizione del dispositivo.

Accedere al report nel Microsoft Defender Security Center accedendo a **Report > dispositivi vulnerabili**

Sono disponibili due colonne:

- Tendenze (nel tempo). Può mostrare gli ultimi 30 giorni, 3 mesi, 6 mesi o un intervallo di date personalizzato.
- Oggi (informazioni correnti)

**Filtro:** è possibile filtrare i dati in base ai livelli di gravità della vulnerabilità, alla disponibilità degli exploit, al periodo di validità della vulnerabilità, alla piattaforma del sistema operativo, Windows 10 versione o al gruppo di dispositivi.

**Drill-down:** se sono disponibili informazioni approfondite che si desidera esplorare ulteriormente, selezionare il grafico a barre pertinente per visualizzare un elenco filtrato di dispositivi nella pagina Inventario dispositivi. Da qui è possibile esportare l'elenco.

## <a name="severity-level-graphs"></a>Grafici del livello di gravità

Ogni dispositivo viene conteggiato una sola volta in base alla vulnerabilità più grave riscontrata in tale dispositivo.

![Un grafico dei livelli di gravità della vulnerabilità del dispositivo corrente e un grafico che mostra i livelli nel tempo.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a>Grafici sulla disponibilità degli exploit

Ogni dispositivo viene conteggiato una sola volta in base al livello più alto di exploit noto.

![Un grafico della disponibilità degli exploit del dispositivo corrente e un grafico che mostra la disponibilità nel tempo.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a>Grafici dell'età delle vulnerabilità

Ogni dispositivo viene conteggiato una sola volta alla data di pubblicazione della vulnerabilità meno recente. Le vulnerabilità precedenti hanno maggiori probabilità di essere sfruttate.

![Un grafico dell'età della vulnerabilità del dispositivo corrente e un grafico che mostra l'età nel tempo.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>Dispositivi vulnerabili in base ai grafici della piattaforma del sistema operativo

Numero di dispositivi in ogni sistema operativo esposti a causa di vulnerabilità software.

![Un grafico dei dispositivi vulnerabili correnti per piattaforma del sistema operativo e un grafico che mostra i dispositivi vulnerabili da parte delle piattaforme del sistema operativo nel tempo.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a>Dispositivi vulnerabili per grafici Windows 10 versione

Numero di dispositivi in ogni versione Windows 10 esposta a causa di applicazioni vulnerabili o del sistema operativo.

![Un grafico dei dispositivi vulnerabili correnti per Windows 10 versione e un grafico che mostra i dispositivi vulnerabili Windows 10 versione nel tempo.](images/tvm-report-version.png)

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica delle minacce gestione delle vulnerabilità sicurezza](next-gen-threat-and-vuln-mgt.md)
- [Consigli sulla sicurezza](tvm-security-recommendation.md)
