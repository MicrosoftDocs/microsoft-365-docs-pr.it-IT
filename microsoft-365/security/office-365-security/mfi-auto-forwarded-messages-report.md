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
description: Gli amministratori possono ottenere informazioni sul report Dei messaggi inoltrati automaticamente nel dashboard del flusso di posta nel Centro sicurezza & conformità.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8f5e7088a88307576a054a1f6833101789d68d01
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290634"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Informazioni dettagliate sui messaggi inoltrati automaticamente nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Le **informazioni dettagliate** sui messaggi inoltrati automaticamente nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità visualizzano informazioni sui messaggi che vengono inoltrati automaticamente dall'organizzazione ai destinatari in domini esterni.

![Widget Messaggi inoltrati automaticamente nel Centro sicurezza & conformità](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Dettagli dei messaggi inoltrati automaticamente

Quando si fa clic sul numero di messaggi nel widget, viene visualizzato un riquadro a comparsa che mostra ulteriori informazioni sui messaggi inoltrati automaticamente:

- **Messaggi inoltrati automaticamente tramite i metodi di inoltro:**

  - **Per regole del flusso di posta**
  - **Per regole posta in arrivo**
  - **Tramite l'inoltro SMTP:** questo metodo indica l'inoltro automatico che gli amministratori possono configurare in una cassetta postale, come descritto in Configurare l'inoltro della posta [elettronica per una cassetta postale.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)
  - Per ulteriori [dettagli, fare](view-mail-flow-reports.md#forwarding-report) clic su un collegamento al report Di inoltro.

- **Messaggi inoltrati automaticamente da domini e utenti:**

  - **Primi 5 domini inoltrati a**
  - **Nuovi domini (ultima settimana)**
  - **Primi 5 utenti di inoltro**
  - **Nuovi utenti (ultima settimana)**
  - Per ulteriori dettagli, fare clic su un collegamento al [report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) Modifiche inoltro.

![Riquadro a comparsa Dettagli per il report Messaggi inoltrati automaticamente nel Centro sicurezza & conformità](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Dati analitici

Vengono generate due informazioni dettagliate in base ai dati del report:

- [Nuovi utenti che inoltrano la posta elettronica](mfi-new-users-forwarding-email.md)
- [Nuovi domini inoltrati tramite posta elettronica](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Vedere anche

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)
