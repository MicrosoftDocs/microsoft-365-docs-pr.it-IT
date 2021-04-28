---
title: Note sulla versione di Microsoft Defender for Endpoint API
description: Note sulla versione per gli aggiornamenti apportati al set di API di Microsoft Defender for Endpoint.
keywords: Note sulla versione di Microsoft Defender for Endpoint API, mde, API, Microsoft Defender for Endpoint API, aggiornamenti, note, rilascio
search.product: eADQiWindows 10XVcnh
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5093bf64614f30c7daa145484453d7c9000ef2c7
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "52060886"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Note sulla versione di Microsoft Defender for Endpoint API

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Le informazioni seguenti elencano gli aggiornamenti apportati alle API di Microsoft Defender per endpoint e le date in cui sono stati effettuati.

> [!TIP]
> Feed RSS: ricevere una notifica quando questa pagina viene aggiornata copiando e incollando l'URL seguente nel lettore di feed:
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```


## <a name="release-notes---newest-to-oldest"></a>Note sulla versione - dal più recente al meno recente

### <a name="23042021"></a>23.04.2021

- È stata aggiunta una nuova API: [proprietà e metodi di attività di correzione.](get-remediation-methods-properties.md)

### <a name="10022021"></a>10.02.2021

- Aggiunta nuova API: [Avvisi di aggiornamento in batch](batch-update-alerts.md).

### <a name="25012021"></a>25.01.2021

- Limitazioni di frequenza aggiornate per [l'API Advanced Hunting](run-advanced-query-api.md) da 15 a 45 richieste al minuto.

### <a name="21012021"></a>21.01.2021

- Aggiunta di una nuova API: [Trova i dispositivi in base al tag](machine-tags.md).
- Aggiunta nuova API: [Importa indicatori](import-ti-indicators.md).

### <a name="03012021"></a>03.01.2021

- Evidenza dell'avviso aggiornata: aggiunte ***proprietà detectionStatus** _, _*_parentProcessFilePath_*_ e _ *_parentProcessFileName_** .
- Entità [alert aggiornata](alerts.md): aggiunta della proprietà ***detectorId.***

### <a name="15122020"></a>15.12.2020

- Entità [Device](machine.md) aggiornata: aggiunto ***l'elenco IpInterfaces.*** Vedi [Elencare i dispositivi](get-machines.md).

### <a name="04112020"></a>04.11.2020

- Aggiunta nuova API: [Imposta valore dispositivo](set-device-value.md).
- Entità [Device](machine.md) aggiornata: aggiunta ***della proprietà deviceValue.***

### <a name="01092020"></a>01.09.2020

- È stata aggiunta un'opzione per espandere l'entità Avviso con l'evidenza correlata. Vedere [Avvisi elenco](get-alerts.md).
