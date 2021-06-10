---
title: Informazioni dettagliate sui messaggi inoltrati automaticamente
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Gli amministratori possono ottenere informazioni sul report Messaggi inoltrati automaticamente nel dashboard del flusso di posta nel Centro sicurezza & conformità.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1882c0506093816e9bb85ae3ba90decd4e0e0d74
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206403"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Informazioni dettagliate sui messaggi inoltrati automaticamente nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Le **informazioni dettagliate** sui messaggi inoltrati automaticamente nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [& conformità](https://protection.office.com) visualizza informazioni sui messaggi che vengono inoltrati automaticamente dall'organizzazione ai destinatari in domini esterni.

![Widget Messaggi inoltrati automaticamente nel Centro sicurezza & conformità](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Dettagli dei messaggi inoltrati automaticamente

Quando si fa clic sul numero di messaggi nel widget, viene visualizzato un riquadro a comparsa che mostra ulteriori informazioni sui messaggi inoltrati automaticamente:

- **Messaggi inoltrati automaticamente tramite metodi di inoltro:**

  - **Per regole del flusso di posta**
  - **Per regole posta in arrivo**
  - **By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).
  - Collegamento al [report Inoltro per](view-mail-flow-reports.md#forwarding-report) ulteriori dettagli.

- **Messaggi inoltrati automaticamente da domini e utenti:**

  - **Primi 5 domini inoltrati a**
  - **Nuovi domini (settimana scorsa)**
  - **Primi 5 utenti di inoltro**
  - **Nuovi utenti (settimana scorsa)**
  - Collegamento al [report Modifiche inoltro per](mfi-new-users-forwarding-email.md#forwarding-modifications-report) ulteriori dettagli.

![Riquadro a comparsa Dettagli per il report Messaggi inoltrati automaticamente nel Centro sicurezza & conformità](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Dati analitici

In base ai dati del report vengono generate due informazioni dettagliate:

- [Nuovi utenti che inoltrano la posta elettronica](mfi-new-users-forwarding-email.md)
- [Nuovi domini inoltrati tramite posta elettronica](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Vedere anche

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)