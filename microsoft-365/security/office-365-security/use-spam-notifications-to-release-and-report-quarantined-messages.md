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
ms.openlocfilehash: 67dbf311c37ae61c007b78110522033d79c0b161
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857146"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="af4b9-103">Notifiche di posta indesiderata dell'utente finale in Office 365</span><span class="sxs-lookup"><span data-stu-id="af4b9-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="af4b9-104">La quarantena contiene messaggi potenzialmente pericolosi o indesiderati in Office 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="af4b9-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="af4b9-105">Per ulteriori informazioni, vedere [Quarantine in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="af4b9-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="af4b9-106">Per impostazione predefinita, le notifiche di posta indesiderata dell'utente finale sono disattivate nei criteri di protezione dalla posta</span><span class="sxs-lookup"><span data-stu-id="af4b9-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="af4b9-107">Quando un amministratore [Abilita le notifiche di posta indesiderata dell'utente finale](configure-your-spam-filter-policies.md), i destinatari dei messaggi riceveranno notifiche periodiche sui loro messaggi che sono stati messi in quarantena come posta indesiderata o in blocco, o (da aprile 2020).</span><span class="sxs-lookup"><span data-stu-id="af4b9-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="af4b9-108">Nell'ottobre 2019, è stata rimossa la possibilità di rilasciare i messaggi in quarantena direttamente dalle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="af4b9-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="af4b9-109">Al contrario, gli utenti possono ora accedere al centro sicurezza & conformità di Office 365 per rilasciare i messaggi in quarantena (direttamente o facendo clic su **Verifica** nella notifica).</span><span class="sxs-lookup"><span data-stu-id="af4b9-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="af4b9-110">Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come utente in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="af4b9-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="af4b9-111">I messaggi che sono stati messi in quarantena come phishing ad alta sicurezza, malware o regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="af4b9-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="af4b9-112">Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come amministratore in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span><span class="sxs-lookup"><span data-stu-id="af4b9-112">For more information, see [Find and release quarantined messages as an admin in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

<span data-ttu-id="af4b9-113">Una notifica di posta indesiderata dell'utente finale contiene le informazioni seguenti per ogni messaggio in quarantena:</span><span class="sxs-lookup"><span data-stu-id="af4b9-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="af4b9-114">**Sender**: il nome e l'indirizzo di posta elettronica del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="af4b9-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="af4b9-115">**Oggetto**: testo della riga dell'oggetto del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="af4b9-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="af4b9-116">**Date**: la data e l'ora (in formato UTC) in cui il messaggio è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="af4b9-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="af4b9-117">**Blocca mittente**: fare clic su questo collegamento per aggiungere il mittente all'elenco dei mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="af4b9-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="af4b9-118">**Recensione**: fare clic su questo collegamento per passare alla quarantena nel centro sicurezza & conformità, in cui è possibile rilasciare, eliminare o segnalare i messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="af4b9-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![Esempio di notifica di posta indesiderata dell'utente finale](../../media/end-user-spam-notification.png)
