---
title: Notifiche di posta indesiderata dell'utente finale in Microsoft 365
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
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni sulle notifiche di posta indesiderata degli utenti finali per i messaggi in quarantena.
ms.openlocfilehash: 2a865130bf1fa0c09b5b68254fb604795b204c22
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034999"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Utilizzare le notifiche di posta indesiderata utente per rilasciare e segnalare messaggi in quarantena

La quarantena contiene messaggi potenzialmente pericolosi o indesiderati nelle organizzazioni di Microsoft 365 con cassette postali nelle organizzazioni Exchange Online o Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online. Per altre informazioni, vedere [Quarantena in Office 365](quarantine-email-messages.md).

Per impostazione predefinita, le notifiche di posta indesiderata dell'utente finale sono disattivate nei criteri di protezione dalla posta Quando un amministratore [Abilita le notifiche di posta indesiderata dell'utente finale](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), i destinatari ricevono notifiche periodiche sui loro messaggi che sono stati messi in quarantena come posta indesiderata o in blocco, o (da aprile 2020), phishing.

> [!NOTE]
> I messaggi che sono stati messi in quarantena come phishing ad alta sicurezza, malware o regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori. Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in Office 365](manage-quarantined-messages-and-files.md).

Una notifica di posta indesiderata dell'utente finale contiene le informazioni seguenti per ogni messaggio in quarantena:

- **Sender**: il nome e l'indirizzo di posta elettronica del messaggio in quarantena.

- **Oggetto**: testo della riga dell'oggetto del messaggio in quarantena.

- **Date**: la data e l'ora (in formato UTC) in cui il messaggio è stato messo in quarantena.

- **Blocca mittente**: fare clic su questo collegamento per aggiungere il mittente all'elenco dei mittenti bloccati. Per ulteriori informazioni, vedere [bloccare un mittente di posta elettronica in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Release**: per i messaggi di posta indesiderata (non phishing), è possibile rilasciare il messaggio qui senza andare a mettere in quarantena il centro sicurezza & Compliance.

- **Recensione**: fare clic su questo collegamento per accedere alla quarantena nel centro sicurezza & Compliance, in cui è possibile rilasciare, eliminare o segnalare i messaggi in quarantena. Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come utente in Office 365](find-and-release-quarantined-messages-as-a-user.md).

![Esempio di notifica di posta indesiderata dell'utente finale](../../media/end-user-spam-notification.png)
