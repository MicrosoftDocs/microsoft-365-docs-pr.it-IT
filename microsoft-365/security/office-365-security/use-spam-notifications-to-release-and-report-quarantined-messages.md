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
ms.openlocfilehash: 71f2a33ad83f94895c396f92c18753bfca7f2905
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933168"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="58346-103">Usare le notifiche di posta indesiderata degli utenti per rilasciare e segnalare i messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="58346-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="58346-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="58346-104">**Applies to**</span></span>
- [<span data-ttu-id="58346-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="58346-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="58346-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="58346-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="58346-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58346-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="58346-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="58346-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="58346-109">Per ulteriori informazioni, vedere [Quarantined messages in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="58346-109">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="58346-110">Per impostazione predefinita, le notifiche di posta indesiderata dell'utente finale sono disabilitate nei criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="58346-110">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="58346-111">Quando un amministratore abilita le notifiche di posta indesiderata dell'utente [finale,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)i destinatari (incluse le cassette postali condivise con il mapping automatico abilitato) riceveranno notifiche periodiche sui messaggi messi in quarantena come posta indesiderata, posta elettronica in blocco o phishing (a partire da aprile 2020).</span><span class="sxs-lookup"><span data-stu-id="58346-111">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="58346-112">Per le cassette postali condivise, le notifiche di posta indesiderata dell'utente finale sono supportate solo per gli utenti a cui viene concessa l'autorizzazione FullAccess per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="58346-112">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="58346-113">Per ulteriori informazioni, vedere [Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span><span class="sxs-lookup"><span data-stu-id="58346-113">For more information, see [Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="58346-114">La notifica di posta indesiderata dell'utente finale non è supportata per i gruppi.</span><span class="sxs-lookup"><span data-stu-id="58346-114">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="58346-115">I messaggi messi in quarantena come phishing ad alta probabilità, malware o da regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="58346-115">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="58346-116">Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="58346-116">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="58346-117">Una notifica di posta indesiderata dell'utente finale contiene le informazioni seguenti per ogni messaggio in quarantena:</span><span class="sxs-lookup"><span data-stu-id="58346-117">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="58346-118">**Sender**: Il nome di invio e l'indirizzo di posta elettronica del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="58346-118">**Sender**: The send name and email address of the quarantined message.</span></span>
- <span data-ttu-id="58346-119">**Subject**: Testo della riga dell'oggetto del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="58346-119">**Subject**: The subject line text of the quarantined message.</span></span>
- <span data-ttu-id="58346-120">**Date**: data e ora (in UTC) in cui il messaggio è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="58346-120">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>
- <span data-ttu-id="58346-121">**Blocca mittente:** fare clic su questo collegamento per aggiungere il mittente all'elenco Mittenti bloccati nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58346-121">**Block Sender**: Click this link to add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="58346-122">Per ulteriori informazioni, vedere [Blocca mittente di posta](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="58346-122">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>
- <span data-ttu-id="58346-123">**Rilascio**: per i messaggi di posta indesiderata (non di phishing), è possibile rilasciare il messaggio qui senza andare a **Mettere** in quarantena il portale Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="58346-123">**Release**: For spam (not phishing) messages, you can release the message here without going to **Quarantine** the Microsoft 365 Defender portal.</span></span>
- <span data-ttu-id="58346-124">**Revisione:** fare clic su  questo collegamento per passare a Quarantena nel portale di Microsoft 365 Defender, in cui è possibile visualizzare, rilasciare, eliminare o segnalare i messaggi in quarantena( a seconda del motivo per cui il messaggio è stato messo in quarantena).</span><span class="sxs-lookup"><span data-stu-id="58346-124">**Review**: Click this link to go to **Quarantine** in the Microsoft 365 Defender portal, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="58346-125">Per ulteriori informazioni, vedere Trovare e rilasciare i messaggi in quarantena [come utente in EOP.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="58346-125">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Notifica di posta indesiderata dell'utente finale di esempio](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="58346-127">Un mittente bloccato può comunque inviare posta.</span><span class="sxs-lookup"><span data-stu-id="58346-127">A blocked sender can still send you mail.</span></span> <span data-ttu-id="58346-128">Tutti i messaggi provenienti da questo mittente che vengono inviati alla cassetta postale verranno spostati immediatamente nella cartella Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="58346-128">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="58346-129">I messaggi futuri provenienti da questo mittente verranno inviati alla cartella Posta indesiderata o alla quarantena dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="58346-129">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="58346-130">Se si desidera eliminare questi messaggi all'arrivo invece di quarantarli, utilizzare le regole del flusso di posta [(note](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) anche come regole di trasporto) per eliminare i messaggi all'arrivo.</span><span class="sxs-lookup"><span data-stu-id="58346-130">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>
