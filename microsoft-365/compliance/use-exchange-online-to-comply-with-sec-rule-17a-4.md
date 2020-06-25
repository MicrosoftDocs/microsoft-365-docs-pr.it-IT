---
title: Usare Exchange Online e il Centro sicurezza e conformità per conformarsi alla regola SEC 17a-4
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Configurare Exchange Online e il Centro conformità per soddisfare i requisiti normativi della regola CFTC 1.31 (c)-(d), della regola FINRA 4511, e della regola SEC 17a-4.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 6dc53ec9dd016a2423ca96886bba400e2f17e17a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819076"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a>Usare Exchange Online e il Centro sicurezza e conformità per conformarsi alla regola SEC 17a-4

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online. This includes the ability to retain, audit, search, and export your data. These capabilities are sufficient to meet the needs of most organizations.

However, some organizations in highly regulated industries are subject to more stringent regulatory requirements. For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC). Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.

Per aiutare queste organizzazioni a comprendere meglio in che modo è possibile sfruttare il Centro sicurezza e conformità per soddisfare gli obblighi normativi per Exchange Online, in modo specifico in relazione ai requisiti della regola 17a-4, è stata rilasciata una valutazione in collaborazione con Cohasset Associates.

Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4. We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.

## <a name="download-the-cohasset-assessment"></a>Scaricare la valutazione Cohasset

È possibile [scaricare la valutazione Cohasset qui](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).

![Pagina del titolo della valutazione scaricabile di Cohasset Associates](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a>La valutazione è specifica per Exchange Online

Note that this assessment is specific to Exchange Online. The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.

It's important to understand that Skype for Business and Teams also store data in Exchange Online. Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a>L'uso della protezione dell'archiviazione è fondamentale per la configurazione consigliata

Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement. The WORM requirement dictates a storage solution in which a record must be:

- Conservato per un periodo di conservazione necessario che non può essere abbreviato, ma solo aumentato.
- Non modificabile, ovvero il record non può essere sovrascritto, cancellato né modificato durante il periodo di conservazione necessario.

In Exchange Online, when a [retention policy](retention-policies.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy. In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox. Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.

By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified. In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:

- Il periodo di conservazione dei criteri può essere solo aumentato, ma non ridotto.
- È possibile aggiungere gli utenti ai criteri, ma non rimuoverli.
- Un amministratore non può eliminare il criterio di conservazione.

La protezione dell'archiviazione consente di soddisfare i requisiti normativi della regola SEC 17a-4.

## <a name="how-to-set-up-preservation-lock"></a>Come configurare la protezione dell'archiviazione

È possibile bloccare i criteri di conservazione con PowerShell. Per altre informazioni, vedere [Usare la protezione dell'archiviazione per la conformità ai requisiti normativi](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).

## <a name="known-limitations"></a>Limitazioni note

Sono attualmente previste alcune limitazioni per Exchange Online:

- Le comunicazioni in thread non sono disponibili per i messaggi di chat e canali di Teams.
- Gli apprezzamenti per i messaggi di chat e canali di Teams non vengono conservati.

> [!NOTE]
> Il controllo a livello di elemento è ora disponibile per le cassette postali di gruppo di Microsoft 365. Per altre informazioni, vedere [Gestire il controllo delle cassette postali](enable-mailbox-auditing.md).
