---
title: Informazioni dettagliate sulle regole del flusso di posta lento
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
ms.openlocfilehash: 34b2b0b3089dcb00668b0b9cd708691381a31ced
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084660"
---
# <a name="slow-mail-flow-rules-insight"></a>Informazioni dettagliate sulle regole del flusso di posta lento

Inefficienti regole del flusso di posta (note anche come regole di trasporto) possono causare ritardi del flusso di posta per l'organizzazione. Questo Insight segnala le regole del flusso di posta che hanno un impatto sul flusso di posta dell'organizzazione. Esempi di questi tipi di regole sono:

- Le condizioni che utilizzano **sono membri di** per gruppi di grandi dimensioni.

- Condizioni che utilizzano la corrispondenza del modello di espressione regolare (Regex) complessa.

- Condizioni che utilizzano il controllo del contenuto negli allegati.

L'Insight consentirà di identificare e ottimizzare le regole del flusso di posta per contribuire a ridurre i ritardi del flusso di posta.

![Informazioni sulle regole del flusso di posta lenta nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

Quando si fa clic su **Visualizza dettagli**, viene visualizzato un riquadro a comparsa dove è possibile esaminare la regola. Nel riquadro a comparsa, è anche possibile fare clic su **Visualizza messaggi di esempio** per visualizzare il tipo di messaggi interessati dalla regola.

![Riquadro a comparsa dopo aver fatto clic su Visualizza dettagli in una panoramica delle regole del flusso di posta lenta nel dashboard del flusso di posta](../media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="see-also"></a>Vedere anche

Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
