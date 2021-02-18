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
description: Gli amministratori possono ottenere informazioni sulle notifiche di posta indesiderata dell'utente finale per i messaggi in quarantena in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb347f7fd3d3793b563714e8116316b30165ef9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287546"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Utilizzare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati. Per ulteriori informazioni, vedere [Quarantined messages in EOP.](quarantine-email-messages.md)

Per impostazione predefinita, le notifiche di posta indesiderata dell'utente finale sono disabilitate nei criteri di protezione da posta indesiderata. Quando un amministratore abilita le notifiche di posta indesiderata dell'utente [finale,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)i destinatari (incluse le cassette postali condivise con il mapping automatico abilitato) riceveranno notifiche periodiche sui messaggi messi in quarantena come posta indesiderata, posta elettronica in blocco o phishing (a partire da aprile 2020).

Per le cassette postali condivise, le notifiche di posta indesiderata dell'utente finale sono supportate solo per gli utenti a cui è stata concessa l'autorizzazione FullAccess per la cassetta postale condivisa. Per ulteriori informazioni, vedere [Utilizzo dell'interfaccia di amministrazione di Exchange per modificare la delega delle cassette postali condivise.](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)

La notifica di posta indesiderata dell'utente finale non è supportata per i gruppi.

> [!NOTE]
> I messaggi messi in quarantena come phishing ad alta probabilità, malware o dalle regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori. Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).

Una notifica di posta indesiderata dell'utente finale contiene le informazioni seguenti per ogni messaggio in quarantena:

- **Mittente:** il nome di invio e l'indirizzo di posta elettronica del messaggio in quarantena.

- **Oggetto:** il testo della riga dell'oggetto del messaggio in quarantena.

- **Data**: data e ora (in formato UTC) in cui il messaggio è stato messo in quarantena.

- **Blocca mittente:** fare clic su questo collegamento per aggiungere il mittente all'elenco Mittenti bloccati. Per ulteriori informazioni, vedere [Bloccare un mittente di posta.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)

- **Rilascio:** per i messaggi di posta indesiderata (non di phishing), è possibile rilasciare il messaggio qui senza andare in quarantena nel Centro sicurezza & conformità.

- **Revisione:** fare clic su questo collegamento per passare alla quarantena nel Centro sicurezza & conformità, dove è possibile (a seconda del motivo per cui il messaggio è stato messo in quarantena) visualizzare, rilasciare, eliminare o segnalare i messaggi in quarantena. Per ulteriori informazioni, vedere [Trovare e rilasciare i messaggi in quarantena come utente in EOP.](find-and-release-quarantined-messages-as-a-user.md)

![Notifica di posta indesiderata dell'utente finale di esempio](../../media/end-user-spam-notification.png)

> [!NOTE]
> Un mittente bloccato può comunque inviare messaggi di posta elettronica. Tutti i messaggi inviati da questo mittente alla cassetta postale verranno spostati immediatamente nella cartella Posta indesiderata. I messaggi futuri provenienti da questo mittente verranno inviati alla cartella Posta indesiderata o alla quarantena dell'utente finale. Se si desidera eliminare questi messaggi al momento dell'arrivo invece di mettere in stato di messa in sicurezza questi messaggi, utilizzare le regole del flusso di posta [(note](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) anche come regole di trasporto) per eliminare i messaggi all'arrivo.
