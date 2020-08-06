---
title: Informazioni sul flusso di posta nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Gli amministratori possono ottenere informazioni sulle intuizioni e sui report disponibili nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 977dcef82a4f32980898c7b4392d011340e3d0a2
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577790"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Informazioni dettagliate sul flusso di posta nel Centro sicurezza e conformità

Gli amministratori possono utilizzare il dashboard del flusso di posta elettronica nel centro sicurezza & Compliance per individuare le tendenze, le intuizioni e intraprendere azioni per risolvere i problemi relativi al flusso di posta nella propria organizzazione.

![Dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/mail-flow-dashboard-v2.png)

Le informazioni disponibili sono le seguenti:

- [Insight dei messaggi con inoltro automatico](mfi-auto-forwarded-messages-report.md)

- [Fix possible mail loop Insight](mfi-mail-loop-insight.md)<sup>1</sup>

- [Correggere le regole del flusso di posta lenta Insight](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [Mappa del flusso di posta](mfi-mail-flow-map-report.md)

- [Nuovi domini inoltrati tramite posta elettronica Insight](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Nuovi utenti che inoltrano la posta elettronica Insight](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Report di dominio non accettato](mfi-non-accepted-domain-report.md)

- [Rapporto di mancato recapito](mfi-non-delivery-report.md)

- [Insight sul flusso di posta in uscita e in ingresso](mfi-outbound-and-inbound-mail-flow.md)

- [Insight nelle code](mfi-queue-alerts-and-queues.md)

- [Insight e report dei client auth SMTP](mfi-smtp-auth-clients-report.md)

- [Informazioni dettagliate sullo stato del flusso di posta del dominio principale](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> questa intuizione viene visualizzata nell'area **consigliata per l'utente** del dashboard del flusso di posta solo dopo che il problema è stato rilevato. In caso contrario, non verrà visualizzato.

<sup>2</sup> questo Insight non viene visualizzato nel dashboard del flusso di posta, ma è visibile nella pagina del [rapporto di inoltro](view-mail-flow-reports.md#forwarding-report) dopo che il problema è stato rilevato. In caso contrario, non verrà visualizzato.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Autorizzazioni necessarie per visualizzare il dashboard del flusso di posta

Il dashboard del flusso di posta è disponibile per i membri dei gruppi di route seguenti:

- **Gestione dell'organizzazione** nel centro sicurezza & Compliance (Global Admins).

- **[Amministratore di Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure ad.

- **Amministratore del flusso** di posta nel centro sicurezza & conformità: se un membro di questo gruppo di ruoli non è anche membro dei gruppi di ruoli amministratore globale o amministratore di Exchange, tenere presente i problemi e i requisiti seguenti:

  - L'utente deve accedere al centro sicurezza & conformità direttamente a <https://protection.office.com> .
  - L'utente avrà solo l'autorizzazione di sola lettura per il dashboard del flusso di posta.
  - L'utente non avrà accesso all'interfaccia di amministrazione di Microsoft 365.

Per ulteriori informazioni sulle autorizzazioni nel centro sicurezza & Compliance, vedere [Permissions in the security & Compliance Center](permissions-in-the-security-and-compliance-center.md) e [fornire agli utenti l'accesso al centro sicurezza & Compliance](grant-access-to-the-security-and-compliance-center.md).

## <a name="where-to-find-the-mail-flow-dashboard"></a>Dove trovare il dashboard del flusso di posta

Aprire il Centro sicurezza & Compliance all'indirizzo <https://protection.office.com> , espandere **flusso di posta**e quindi fare clic su **Dashboard**.

Per accedere direttamente al dashboard del flusso di posta, Apri <https://protection.office.com/mailflow/dashboard> .
