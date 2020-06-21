---
title: Informazioni dettagliate sullo stato del flusso di posta del dominio principale
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulla panoramica dello stato del flusso di posta del dominio principale nel dashboard del flusso di posta nel centro sicurezza & conformità.
ms.openlocfilehash: 22b0f8cefe8baacac682550126de55dcbf880d73
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818592"
---
# <a name="top-domain-mail-flow-status-insight"></a>Informazioni dettagliate sullo stato del flusso di posta del dominio principale

L'Insight **sullo stato del flusso di posta di dominio principale** offre lo stato corrente dei domini dell'organizzazione in termini di flusso di posta. Questo Insight consente di identificare e risolvere i problemi relativi ai domini che si verificano problemi di ***flusso di posta*** (ad esempio, non è possibile ricevere messaggi di posta elettronica esterni), in particolare le scadenze o i domini di dominio con record MX non corretti.

![Informazioni sullo stato del flusso di dominio principale nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/domain-mail-flow-status-selected.png)

Quando si fa clic su **Visualizza dettagli** nell'Insight, viene visualizzato un riquadro a comparsa per visualizzare ulteriori dettagli sullo stato di ciascun dominio.

Un segno di spunta verde per un dominio indica che il record MX corrente (quando si è visualizzato il dashboard per la visualizzazione del flusso di posta) corrisponde al valore che abbiamo registrato e che il dominio ha ricevuto la posta elettronica nelle ultime due ore.

Una x rossa per un dominio indica che il record MX è stato modificato e che il dominio non ha ricevuto messaggi di posta elettronica nelle ultime 6 ore. Questo indica probabilmente che il dominio è scaduto o che il record MX è stato aggiornato in modo errato. Verificare con il registrar o con il servizio di hosting DNS se il dominio è scaduto o se il record MX del dominio non è corretto.

![Il riquadro a comparsa dettagli nell'Insight sullo stato del flusso di dominio superiore](../../media/domain-mail-flow-status-flyout.png)

## <a name="related-topics"></a>Argomenti correlati

Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
