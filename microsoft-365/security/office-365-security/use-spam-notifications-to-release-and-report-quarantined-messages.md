---
title: Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
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
description: Se l'amministratore abilita le notifiche per gli utenti, riceverà un messaggio di notifica che elenca i messaggi inviati alla cassetta postale che sono stati identificati come posta indesiderata, in blocco o in messaggi di phishing. È possibile rilasciare o segnalare i messaggi dopo la notifica.
ms.openlocfilehash: 51fcdefc08987b153d045994927f56df3b670fd0
ms.sourcegitcommit: 836bd8135cc49d6db37e78a7cfeb7d2cc4159e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722037"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="5e1af-104">Usare le notifiche di posta indesiderata dell'utente per rilasciare e segnalare i messaggi in quarantena in Office 365</span><span class="sxs-lookup"><span data-stu-id="5e1af-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="5e1af-105">Se l'amministratore abilita le notifiche di posta indesiderata per gli utenti, riceverà un messaggio di notifica che elenca i messaggi indirizzati alla cassetta postale che sono stati identificati come posta indesiderata, bulk o phishing e in quarantena.</span><span class="sxs-lookup"><span data-stu-id="5e1af-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam, bulk, or phish and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="5e1af-106">Se si è un amministratore e si desidera abilitare questa funzionalità, è possibile scegliere l'opzione quando si [modifica un criterio di protezione da posta indesiderata predefinito](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5e1af-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="5e1af-107">Il messaggio ricevuto include il numero di messaggi di posta indesiderata in quarantena e la data e l'ora (in formato UTC (Universal Coordinated Time) dell'ultimo messaggio nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5e1af-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="5e1af-108">L'elenco include quanto segue per ogni messaggio:</span><span class="sxs-lookup"><span data-stu-id="5e1af-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="5e1af-109">**Mittente** Il nome e l'indirizzo di posta elettronica del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="5e1af-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="5e1af-110">**Oggetto** Oggetto del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="5e1af-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="5e1af-111">**Data** Data e ora (in formato UTC) del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="5e1af-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="5e1af-112">Di seguito sono riportate le azioni che è possibile eseguire con un messaggio in quarantena:</span><span class="sxs-lookup"><span data-stu-id="5e1af-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="5e1af-113">**Blocca mittente** se si desidera che in Office 365 venga aggiunto il mittente all'elenco dei mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="5e1af-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="5e1af-114">**Rilascia** se il messaggio non è posta indesiderata e si desidera che Office 365 invii il messaggio alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="5e1af-114">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="5e1af-115">**Revisione** per passare al portale di quarantena all'interno del Centro sicurezza e conformità se si desidera eseguire altre operazioni, ad esempio l'anteprima o il rilascio.</span><span class="sxs-lookup"><span data-stu-id="5e1af-115">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="5e1af-116">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5e1af-116">Be aware of the following:</span></span>

- <span data-ttu-id="5e1af-117">I messaggi di phishing e i messaggi di posta indesiderata che vengono messi in quarantena perché hanno trovato una regola per il flusso del messaggio non sono inclusi nelle notifiche di spam degli utenti.</span><span class="sxs-lookup"><span data-stu-id="5e1af-117">Malware and high confidence phishing messages and messages that are quarantined because they matched a mail flow rule are not included in user spam notifications.</span></span> 

- <span data-ttu-id="5e1af-118">È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.</span><span class="sxs-lookup"><span data-stu-id="5e1af-118">You can only release a message and report it as a false positive (not junk) once.</span></span>
