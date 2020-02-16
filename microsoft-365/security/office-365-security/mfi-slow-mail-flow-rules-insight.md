---
title: Informazioni dettagliate sulle regole del flusso di posta lento
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 5/3/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: Gli amministratori possono ottenere informazioni sull'Insight nelle regole del flusso di posta lenta nel dashboard del flusso di posta elettronica nel centro sicurezza & conformità.
ms.openlocfilehash: d5317f2d45aacb91e51131bc5b8aa6e67d3ae4c7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088357"
---
# <a name="slow-mail-flow-rules-insight"></a>Informazioni dettagliate sulle regole del flusso di posta lento

Inefficienti regole del flusso di posta (note anche come regole di trasporto) possono causare ritardi del flusso di posta per l'organizzazione. Questo Insight segnala le regole del flusso di posta che hanno un impatto sul flusso di posta dell'organizzazione. Esempi di questi tipi di regole sono:

- Le condizioni che utilizzano **sono membri di** per gruppi di grandi dimensioni.

- Condizioni che utilizzano la corrispondenza del modello di espressione regolare (Regex) complessa.

- Condizioni che utilizzano il controllo del contenuto negli allegati.

L'Insight consentirà di identificare e ottimizzare le regole del flusso di posta per contribuire a ridurre i ritardi del flusso di posta.

![Informazioni sulle regole del flusso di posta lenta nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

Quando si fa clic su **Visualizza dettagli**, viene visualizzato un riquadro a comparsa dove è possibile esaminare la regola. Nel riquadro a comparsa, è anche possibile fare clic su **Visualizza messaggi di esempio** per visualizzare il tipo di messaggi interessati dalla regola.

![Riquadro a comparsa dopo aver fatto clic su Visualizza dettagli in una panoramica delle regole del flusso di posta lenta nel dashboard del flusso di posta](../../media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="see-also"></a>Vedere anche

Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
