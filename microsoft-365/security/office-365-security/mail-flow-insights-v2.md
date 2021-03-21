---
title: Informazioni dettagliate sul flusso di posta nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Gli amministratori possono conoscere le informazioni dettagliate e i report disponibili nel dashboard del flusso di posta nel Centro sicurezza & conformità.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce252535d472cc4941a1353aa2be94759daebf4a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926857"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Informazioni dettagliate sul flusso di posta nel Centro sicurezza e conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Gli amministratori possono usare il dashboard del flusso di posta nel Centro sicurezza & conformità per individuare tendenze, approfondimenti ed eseguire azioni per risolvere i problemi relativi al flusso di posta nell'organizzazione.

![Dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mail-flow-dashboard-v2.png)

Le informazioni dettagliate disponibili sono:

- [Informazioni dettagliate sui messaggi inoltrati automaticamente](mfi-auto-forwarded-messages-report.md)

- [Risolvere i possibili problemi di analisi del ciclo di](mfi-mail-loop-insight.md)posta<sup>1</sup>

- [Risolvere le lentezza delle regole del flusso di](mfi-slow-mail-flow-rules-insight.md)posta<sup>1</sup>

- [Mappa del flusso di posta](mfi-mail-flow-map-report.md)

- [Nuovi domini inoltrati tramite informazioni dettagliate sulla posta](mfi-new-domains-being-forwarded-email.md)<sup>elettronica 2</sup>

- [Nuovi utenti che inoltrano informazioni dettagliate sulla posta](mfi-new-users-forwarding-email.md)<sup>elettronica 2</sup>

- [Report di dominio non accettato](mfi-non-accepted-domain-report.md)

- [Rapporto di mancato recapito](mfi-non-delivery-report.md)

- [Informazioni dettagliate sul flusso di posta in ingresso e in uscita](mfi-outbound-and-inbound-mail-flow.md)

- [Dati analitici sulle code](mfi-queue-alerts-and-queues.md)

- [Informazioni dettagliate e report sui client di autenticazione SMTP](mfi-smtp-auth-clients-report.md)

- [Informazioni dettagliate sullo stato del flusso di posta del dominio principale](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Questa panoramica viene visualizzata nell'area Consigliato per **l'utente** del dashboard del flusso di posta solo dopo aver rilevato il problema. In caso contrario, non verrà visualizzato.

<sup>2</sup> Questa panoramica non viene visualizzata nel dashboard del [](view-mail-flow-reports.md#forwarding-report) flusso di posta, ma è visibile nella pagina Rapporto di inoltro dopo aver rilevato il problema. In caso contrario, non verrà visualizzato.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Autorizzazioni necessarie per visualizzare il dashboard del flusso di posta

Il dashboard del flusso di posta è disponibile per i membri dei gruppi di ruoli seguenti:

- **Gestione dell'organizzazione** nel Centro sicurezza & conformità (amministratori globali).

- **[Amministratore di Exchange](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure Active Directory.

- **MailFlow Administrator** nel Centro sicurezza & conformità. Se l'account non è anche membro dei gruppi di ruoli Gestione organizzazione o Amministratore di Exchange, considerare i seguenti problemi:
  - L'utente deve accedere al Centro sicurezza & conformità direttamente all'indirizzo <https://protection.office.com> .
  - L'utente avrà solo l'autorizzazione di sola lettura per il dashboard del flusso di posta.
  - L'utente non ha accesso all'interfaccia di amministrazione di Microsoft 365.

Per ulteriori informazioni sulle autorizzazioni, vedere [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) e Give users access to the Security & Compliance [Center.](grant-access-to-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>Dove trovare il dashboard del flusso di posta

Aprire il Centro sicurezza & conformità <https://protection.office.com> in , espandere Flusso di **posta** e quindi selezionare **Dashboard**.

Per passare direttamente al dashboard del flusso di posta, aprire <https://protection.office.com/mailflow/dashboard> .