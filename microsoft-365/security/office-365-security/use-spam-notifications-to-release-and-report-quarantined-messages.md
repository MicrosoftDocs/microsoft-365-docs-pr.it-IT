---
title: Notifiche di posta indesiderata dell'utente finale in Office 36
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Quando un amministratore abilita le notifiche di posta indesiderata dell'utente finale nei criteri di protezione da posta indesiderata, i destinatari del messaggio riceveranno notifiche periodiche sui messaggi in quarantena
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895060"
---
# <a name="end-user-spam-notifications-in-office-365"></a>Notifiche di posta indesiderata dell'utente finale in Office 365

La quarantena contiene messaggi potenzialmente pericolosi o indesiderati nelle organizzazioni di Office 365 con cassette postali nelle organizzazioni Exchange Online o Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online. Per altre informazioni, vedere [Quarantena in Office 365](quarantine-email-messages.md).

Per impostazione predefinita, le notifiche di posta indesiderata dell'utente finale sono disattivate nei criteri di protezione dalla posta Quando un amministratore [Abilita le notifiche di posta indesiderata dell'utente finale](configure-your-spam-filter-policies.md), i destinatari dei messaggi riceveranno notifiche periodiche sui loro messaggi che sono stati messi in quarantena come posta indesiderata o in blocco, o (da aprile 2020).

> [!NOTE]
> Nell'ottobre 2019, è stata rimossa la possibilità di rilasciare i messaggi in quarantena direttamente dalle notifiche di posta indesiderata dell'utente finale. Al contrario, gli utenti possono ora accedere al centro sicurezza & conformità di Office 365 per rilasciare i messaggi in quarantena (direttamente o facendo clic su **Verifica** nella notifica). Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come utente in Office 365](find-and-release-quarantined-messages-as-a-user.md). <br/><br/> I messaggi che sono stati messi in quarantena come phishing ad alta sicurezza, malware o regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori. Per ulteriori informazioni, vedere [gestire i messaggi e i file in quarantena come amministratore in Office 365](manage-quarantined-messages-and-files.md).

Una notifica di posta indesiderata dell'utente finale contiene le informazioni seguenti per ogni messaggio in quarantena:

- **Sender**: il nome e l'indirizzo di posta elettronica del messaggio in quarantena.

- **Oggetto**: testo della riga dell'oggetto del messaggio in quarantena.

- **Date**: la data e l'ora (in formato UTC) in cui il messaggio è stato messo in quarantena.

- **Blocca mittente**: fare clic su questo collegamento per aggiungere il mittente all'elenco dei mittenti bloccati.

- **Recensione**: fare clic su questo collegamento per passare alla quarantena nel centro sicurezza & conformità, in cui è possibile rilasciare, eliminare o segnalare i messaggi in quarantena.

![Esempio di notifica di posta indesiderata dell'utente finale](../../media/end-user-spam-notification.png)
