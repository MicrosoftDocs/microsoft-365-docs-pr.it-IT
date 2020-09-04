---
title: Informazioni sullo stato del flusso di posta del dominio principale nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su come utilizzare la panoramica dello stato del flusso di posta del dominio principale nel dashboard del flusso di posta nel centro sicurezza & Compliance per risolvere i problemi relativi al flusso di posta relativi ai record MX nei domini di posta elettronica.
ms.openlocfilehash: 34b80bee48bd91524fbd95961c473f50fbe394b7
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358313"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Informazioni sullo stato del flusso di posta del dominio principale nel centro sicurezza & Compliance

La panoramica dello **stato del flusso di posta del dominio principale** nel [Dashboard del flusso di posta elettronica](mail-flow-insights-v2.md) nel [Centro sicurezza & conformità](https://protection.office.com) fornisce lo stato corrente dei domini dell'organizzazione in termini di flusso di posta. Questo Insight consente di identificare e risolvere i problemi relativi ai domini che si verificano problemi di ***flusso di posta*** (ad esempio, non è possibile ricevere messaggi di posta elettronica esterni), in particolare le scadenze o i domini di dominio con record MX non corretti.

![Widget dello stato del flusso di dominio principale nel dashboard del flusso di posta elettronica nel centro sicurezza & conformità](../../media/mfi-top-domain-mail-flow-status-widget.png)

Quando si fa clic su **Visualizza dettagli** nel widget, viene visualizzato un riquadro a comparsa di **stato del dominio** che Mostra più dettagli per lo stato di ogni dominio:

- **Dominio**
- **Record MX precedente**
- **Record MX corrente**
- **Stato di ricezione della posta elettronica**
- **Stato del dominio**: un segno di spunta verde indica che il record MX corrente (quando si è fatto clic sul widget) corrisponde al valore che abbiamo registrato e che il dominio ha ricevuto la posta elettronica nelle ultime due ore.

  Una X rossa indica che il record MX è stato modificato e che il dominio non ha ricevuto alcun messaggio di posta elettronica nelle ultime 6 ore. Questo indica probabilmente che il dominio è scaduto o che il record MX è stato aggiornato in modo errato. Verificare con il registrar o con il servizio di hosting DNS se il dominio è scaduto o se il record MX del dominio non è corretto.

È possibile fare clic su **Visualizza altro** per visualizzare le stesse informazioni relative a più domini.

![Riquadro a comparsa dettagli nell'Insight sullo stato del flusso di posta di dominio superiore](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>Argomenti correlati

Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
