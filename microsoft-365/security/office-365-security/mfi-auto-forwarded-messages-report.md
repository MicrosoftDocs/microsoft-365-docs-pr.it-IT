---
title: Insight dei messaggi con inoltro automatico
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Gli amministratori possono ottenere informazioni sul rapporto messaggi auto-inoltrati nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance.
ms.openlocfilehash: 05e3f62610c32bc95caf579ef4dd46bf1ed90275
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577820"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Insight dei messaggi auto-inoltrati nel centro sicurezza & Compliance

L'Insight dei **messaggi auto-inoltrati** nel [Dashboard del flusso di posta elettronica](mail-flow-insights-v2.md) nel centro sicurezza & conformità Visualizza informazioni sui messaggi che vengono inoltrati automaticamente dall'organizzazione ai destinatari nei domini esterni.

![Widget messaggi auto-inoltrati nel centro sicurezza & Compliance](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Dettagli dei messaggi inoltrati automaticamente

Quando si fa clic sul numero di messaggi nel widget, viene visualizzato un riquadro a comparsa che consente di visualizzare ulteriori informazioni sui messaggi auto-inoltrati:

- Inoltro **automatico dei messaggi tramite i metodi di inoltro**:

  - **Regole del flusso di posta**
  - **Dalle regole di posta in arrivo**
  - **Per inoltro SMTP**
  - Un collegamento al [rapporto di inoltro](view-mail-flow-reports.md#forwarding-report) per ulteriori dettagli.

- **Messaggi auto-inoltrati da domini e utenti**:

  - **Top 5 domini inoltrati a**
  - **Nuovi domini (la settimana scorsa)**
  - **Top 5 utenti di inoltro**
  - **Nuovi utenti (la settimana scorsa)**
  - Un collegamento al [rapporto di modifica di inoltro](mfi-new-users-forwarding-email.md#forwarding-modifications-report) per ulteriori dettagli.

![Riquadro a comparsa dettagli per il rapporto messaggi auto-inoltrati nel centro sicurezza & Compliance](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Approfondimenti

Vengono generate due intuizioni in base ai dati del rapporto:

- [Nuovi utenti che inoltrano messaggi di posta elettronica](mfi-new-users-forwarding-email.md)
- [Nuovi domini che vengono inoltrati tramite posta elettronica](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Vedere anche

Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
