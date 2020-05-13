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
description: Gli amministratori possono conoscere le notifiche di posta indesiderata degli utenti finali per i messaggi in quarantena in Exchange Online Protection (EOP).
ms.openlocfilehash: 7dd6b2d14bbb4a1771c59c8a1e654e36f0f83d3e
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208550"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Utilizzare le notifiche di posta indesiderata utente per rilasciare e segnalare messaggi in quarantena

In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati. Per ulteriori informazioni, vedere [messaggi in quarantena in EOP](quarantine-email-messages.md).

Per impostazione predefinita, le notifiche di posta indesiderata dell'utente finale sono disattivate nei criteri di protezione dalla posta Quando un amministratore [consente di abilitare le notifiche di posta indesiderata dell'utente finale](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), i destinatari ricevono notifiche periodiche sui messaggi che sono stati messi in quarantena come posta indesiderata o in blocco, o (al 2020 aprile).

> [!NOTE]
> I messaggi che sono stati messi in quarantena come phishing ad alta sicurezza, malware o regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori. Per ulteriori informazioni, vedere [gestire i messaggi e i file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).

Una notifica di posta indesiderata dell'utente finale contiene le informazioni seguenti per ogni messaggio in quarantena:

- **Sender**: il nome e l'indirizzo di posta elettronica del messaggio in quarantena.

- **Oggetto**: testo della riga dell'oggetto del messaggio in quarantena.

- **Date**: la data e l'ora (in formato UTC) in cui il messaggio è stato messo in quarantena.

- **Blocca mittente**: fare clic su questo collegamento per aggiungere il mittente all'elenco dei mittenti bloccati. Per ulteriori informazioni, vedere [bloccare un mittente di posta elettronica in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Release**: per i messaggi di posta indesiderata (non phishing), è possibile rilasciare il messaggio qui senza andare a mettere in quarantena il centro sicurezza & Compliance.

- **Recensione**: fare clic su questo collegamento per accedere alla quarantena nel centro sicurezza & Compliance, in cui è possibile rilasciare, eliminare o segnalare i messaggi in quarantena. Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come utente in EOP](find-and-release-quarantined-messages-as-a-user.md).

![Esempio di notifica di posta indesiderata dell'utente finale](../../media/end-user-spam-notification.png)
