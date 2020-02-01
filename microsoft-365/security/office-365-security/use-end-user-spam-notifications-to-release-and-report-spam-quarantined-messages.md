---
title: Utilizzare le notifiche di posta indesiderata dell'utente finale per segnalare i messaggi di posta indesiderata in quarantena
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: "Gli utenti che visualizzano un messaggio di notifica di posta indesiderata dell'utente finale dall'amministratore relativo alla posta in quarantena possono eseguire queste azioni nei messaggi. "
ms.openlocfilehash: 4d53e4866733ba0d3de96f068297a342c134e5ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598083"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a><span data-ttu-id="76fff-103">Utilizzare le notifiche di posta indesiderata dell'utente finale per segnalare i messaggi di posta indesiderata in quarantena</span><span class="sxs-lookup"><span data-stu-id="76fff-103">Use end-user spam notifications to release and report spam-quarantined messages</span></span>

<span data-ttu-id="76fff-p101">Se l'amministratore abilita le notifiche di posta indesiderata dell'utente finale, si riceve un messaggio di notifica in cui vengono elencati i messaggi destinati alla propria cassetta postale che sono stati identificati come posta indesiderata e messi in quarantena. Nel messaggio verrà incluso il numero di messaggi di posta indesiderata e in quarantena e il giorno e l'ora, in formato UTC (Coordinated Universal Time) dell'ultimo messaggio presente nell'elenco. Dall'elenco, è possibile visualizzare le seguenti informazioni su ciascun messaggio:</span><span class="sxs-lookup"><span data-stu-id="76fff-p101">If your administrator enables end-user spam notifications, you'll receive a notification message that lists messages intended for your mailbox that were identified as spam and quarantined instead. This message includes the number of spam-quarantined messages listed, and the date and time (in Universal Coordinated Time (UTC)) of the last message in the list. From this list, you can view the following information about each message:</span></span>

- <span data-ttu-id="76fff-107">**Sender**: il nome del mittente e l'indirizzo di posta elettronica del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="76fff-107">**Sender**: The sender name and email address of the quarantined message.</span></span>

- <span data-ttu-id="76fff-108">**Oggetto**: testo della riga dell'oggetto del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="76fff-108">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="76fff-109">**Date**: la data e l'ora (in formato UTC) in cui il messaggio è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="76fff-109">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="76fff-110">**Dimensioni**: la dimensione del messaggio in quarantena, espressa in kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="76fff-110">**Size**: The size of the quarantined message, in kilobytes (KBs).</span></span>

<span data-ttu-id="76fff-111">È possibile eseguire le seguenti azioni sul ciascun messaggio:</span><span class="sxs-lookup"><span data-stu-id="76fff-111">You can perform the following actions on each message:</span></span>

- <span data-ttu-id="76fff-112">**Rilascia in posta in arrivo**: facendo clic su questo collegamento, il messaggio viene inviato alla posta in arrivo in cui è possibile visualizzarla.</span><span class="sxs-lookup"><span data-stu-id="76fff-112">**Release to Inbox**: Clicking this link sends the message to your inbox where you can view it.</span></span>

- <span data-ttu-id="76fff-113">**Segnala come non indesiderato: se**si fa clic su questo collegamento, viene inviata una copia del messaggio a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="76fff-113">**Report as Not Junk**: Clicking this link sends a copy of the message to Microsoft for analysis.</span></span> <span data-ttu-id="76fff-114">Il team di analisi di posta indesiderata, valuta e analizza il messaggio e a seconda dei risultati dell'analisi, regola il filtro di protezione da posta indesiderata per consentire l'inoltro del messaggio.</span><span class="sxs-lookup"><span data-stu-id="76fff-114">The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span>

> [!NOTE]
> <span data-ttu-id="76fff-115">I messaggi messi in quarantena a causa di una regola del flusso di posta (nota anche come a) non sono inclusi nei messaggi di posta indesiderata in quarantena dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="76fff-115">Messages that are quarantined due to a mail flow rule (also known as a ) match are not included in end user spam quarantined messages.</span></span> <span data-ttu-id="76fff-116">Nell'elenco sono presenti solo i messaggi di posta indesiderata in quarantena.</span><span class="sxs-lookup"><span data-stu-id="76fff-116">Only spam-quarantined messages are listed.</span></span> <br/><br/>  <span data-ttu-id="76fff-117">È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.</span><span class="sxs-lookup"><span data-stu-id="76fff-117">You can only release a message and report it as a false positive (not junk) once.</span></span>
