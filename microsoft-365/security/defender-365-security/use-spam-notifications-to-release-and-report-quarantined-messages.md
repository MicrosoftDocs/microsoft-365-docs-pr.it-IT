---
title: Notifiche di posta indesiderata dell'utente finale in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulle notifiche di posta indesiderata degli utenti finali per i messaggi in quarantena in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9cff91be399bd98eb7e6e5a2a6d91a4a8bb602ec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061866"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Usare le notifiche di posta indesiderata degli utenti per rilasciare e segnalare i messaggi in quarantena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati. Per ulteriori informazioni, vedere [Quarantined messages in EOP](quarantine-email-messages.md).

Per impostazione predefinita, le notifiche di posta indesiderata dell'utente finale sono disabilitate nei criteri di protezione da posta indesiderata. Quando un amministratore abilita le notifiche di posta indesiderata dell'utente [finale,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)i destinatari (incluse le cassette postali condivise con il mapping automatico abilitato) riceveranno notifiche periodiche sui messaggi messi in quarantena come posta indesiderata, posta elettronica in blocco o phishing (a partire da aprile 2020).

Per le cassette postali condivise, le notifiche di posta indesiderata dell'utente finale sono supportate solo per gli utenti a cui viene concessa l'autorizzazione FullAccess per la cassetta postale condivisa. Per ulteriori informazioni, vedere [Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).

La notifica di posta indesiderata dell'utente finale non è supportata per i gruppi.

> [!NOTE]
> I messaggi messi in quarantena come phishing ad alta probabilità, malware o da regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori. Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).

Una notifica di posta indesiderata dell'utente finale contiene le informazioni seguenti per ogni messaggio in quarantena:

- **Sender**: Il nome di invio e l'indirizzo di posta elettronica del messaggio in quarantena.

- **Subject**: Testo della riga dell'oggetto del messaggio in quarantena.

- **Date**: data e ora (in UTC) in cui il messaggio è stato messo in quarantena.

- **Blocca mittente:** fare clic su questo collegamento per aggiungere il mittente all'elenco Mittenti bloccati. Per ulteriori informazioni, vedere [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Rilascio**: per i messaggi di posta indesiderata (non di phishing), è possibile rilasciare il messaggio qui senza andare in quarantena nel Centro sicurezza & conformità.

- **Revisione:** fare clic su questo collegamento per passare a Quarantena nel Centro sicurezza & conformità, in cui è possibile visualizzare, rilasciare, eliminare o segnalare i messaggi in quarantena, a seconda del motivo per cui il messaggio è stato messo in quarantena. Per ulteriori informazioni, vedere Trovare e rilasciare i messaggi in quarantena [come utente in EOP.](find-and-release-quarantined-messages-as-a-user.md)

![Notifica di posta indesiderata dell'utente finale di esempio](../../media/end-user-spam-notification.png)

> [!NOTE]
> Un mittente bloccato può comunque inviare posta. Tutti i messaggi provenienti da questo mittente che vengono inviati alla cassetta postale verranno spostati immediatamente nella cartella Posta indesiderata. I messaggi futuri provenienti da questo mittente verranno inviati alla cartella Posta indesiderata o alla quarantena dell'utente finale. Se si desidera eliminare questi messaggi all'arrivo invece di quarantarli, utilizzare le regole del flusso di posta [(note](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) anche come regole di trasporto) per eliminare i messaggi all'arrivo.