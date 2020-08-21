---
title: Correggere possibili informazioni dettagliate sul ciclo di posta
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su come utilizzare l'Insight del ciclo di posta elettronica Fix possible nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance per identificare e correggere i loop di posta nell'organizzazione.
ms.openlocfilehash: 162752ce6981e27d6ae2923aeb0fc33aec42bb0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826954"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>FIX possible Insight del loop di posta elettronica nel centro sicurezza & Compliance

Un loop di posta non è valido perché spreca risorse di sistema, consuma la quota del volume di posta dell'organizzazione e invia rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo) ai mittenti originali.

L'Insight del **ciclo di posta di Fix possibile** nell'area **consigliata per l'utente** del dashboard del flusso di [posta](mail-flow-insights-v2.md) nel centro sicurezza & Compliance notifica quando viene rilevato un loop di posta nell'organizzazione. Questa intuizione viene visualizzata solo dopo che è stata rilevata la condizione (se non si dispone di alcun loop di posta elettronica, non si vedrà l'Insight).

![Fix Slow Mail Flow Rules Insight nelle aree consigliate per l'area del dashboard del flusso di posta](../../media/mfi-fix-possible-mail-loop.png)

Quando si fa clic su **Visualizza dettagli** nel widget, viene visualizzato un riquadro a comparsa con ulteriori informazioni:

- **Dominio**
- **Numero di messaggi**: è possibile fare clic su **Visualizza messaggi di esempio** per visualizzare i risultati di [traccia](message-trace-scc.md) dei messaggi per un esempio di messaggi che sono stati interessati dal ciclo.
- **Tipo di dominio**"ad esempio, autorevole o non autorevole.
- **Record MX**: host (**mail server**) e valori di **priorità** del record MX per il dominio.
- **Motivo ciclo** e **correzione**: si cercherà di identificare gli scenari più comuni del ciclo di posta elettronica e di fornire le azioni consigliate (se disponibili) per correggere il ciclo.

![Riquadro a comparsa dettagli che viene visualizzato dopo aver fatto clic su Visualizza dettagli sull'Insight del ciclo di posta di Fix possible](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a>Argomenti correlati

Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
