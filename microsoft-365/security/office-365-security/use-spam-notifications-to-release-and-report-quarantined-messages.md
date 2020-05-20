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
ms.openlocfilehash: 7d4cf21ade504e999dc5b53ad9062977369561c6
ms.sourcegitcommit: 4ce28ad4d17d336106c1720d65349f19f9e90e04
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294242"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="6f83e-103">Utilizzare le notifiche di posta indesiderata utente per rilasciare e segnalare messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="6f83e-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="6f83e-104">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="6f83e-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="6f83e-105">Per ulteriori informazioni, vedere [messaggi in quarantena in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="6f83e-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="6f83e-106">Per impostazione predefinita, le notifiche di posta indesiderata dell'utente finale sono disattivate nei criteri di protezione dalla posta</span><span class="sxs-lookup"><span data-stu-id="6f83e-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="6f83e-107">Quando un amministratore [Abilita le notifiche di posta indesiderata dell'utente finale](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), i destinatari (incluse le cassette postali condivise) ricevono notifiche periodiche sui loro messaggi che sono stati messi in quarantena come posta indesiderata, posta in blocco o (da aprile 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="6f83e-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="6f83e-108">I messaggi che sono stati messi in quarantena come phishing ad alta sicurezza, malware o regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="6f83e-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="6f83e-109">Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="6f83e-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="6f83e-110">Una notifica di posta indesiderata dell'utente finale contiene le informazioni seguenti per ogni messaggio in quarantena:</span><span class="sxs-lookup"><span data-stu-id="6f83e-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="6f83e-111">**Sender**: il nome e l'indirizzo di posta elettronica del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="6f83e-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="6f83e-112">**Oggetto**: testo della riga dell'oggetto del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="6f83e-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="6f83e-113">**Date**: la data e l'ora (in formato UTC) in cui il messaggio è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="6f83e-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="6f83e-114">**Blocca mittente**: fare clic su questo collegamento per aggiungere il mittente all'elenco dei mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="6f83e-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="6f83e-115">Per ulteriori informazioni, vedere [bloccare un mittente di posta elettronica in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="6f83e-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="6f83e-116">**Release**: per i messaggi di posta indesiderata (non phishing), è possibile rilasciare il messaggio qui senza andare a mettere in quarantena il centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="6f83e-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="6f83e-117">**Recensione**: fare clic su questo collegamento per accedere alla quarantena nel centro sicurezza & Compliance, in cui è possibile rilasciare, eliminare o segnalare i messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="6f83e-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="6f83e-118">Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come utente in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="6f83e-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Esempio di notifica di posta indesiderata dell'utente finale](../../media/end-user-spam-notification.png)
