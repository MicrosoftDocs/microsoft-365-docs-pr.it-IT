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
ms.openlocfilehash: 0440056e8e31d24e659f9d0ff6662f86f31a6189
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600298"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="e4516-103">Utilizzare le notifiche di posta indesiderata utente per rilasciare e segnalare messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4516-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e4516-104">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="e4516-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="e4516-105">Per ulteriori informazioni, vedere [messaggi in quarantena in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e4516-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e4516-106">Per impostazione predefinita, le notifiche di posta indesiderata dell'utente finale sono disattivate nei criteri di protezione dalla posta</span><span class="sxs-lookup"><span data-stu-id="e4516-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="e4516-107">Quando un amministratore [Abilita le notifiche di posta indesiderata dell'utente finale](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), i destinatari (incluse le cassette postali condivise con automapping abilitato) ricevono notifiche periodiche sui loro messaggi che sono stati messi in quarantena come posta indesiderata, posta in blocco o (al 2020 aprile).</span><span class="sxs-lookup"><span data-stu-id="e4516-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="e4516-108">Per le cassette postali condivise, le notifiche di posta indesiderata degli utenti finali sono supportate solo per gli utenti che dispongono dell'autorizzazione FullAccess per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="e4516-108">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="e4516-109">Per ulteriori informazioni, vedere [utilizzo dell'interfaccia di amministrazione di Exchange per modificare la delega delle cassette postali condivise](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span><span class="sxs-lookup"><span data-stu-id="e4516-109">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="e4516-110">La notifica di posta indesiderata dell'utente finale non è supportata per i gruppi.</span><span class="sxs-lookup"><span data-stu-id="e4516-110">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="e4516-111">I messaggi che sono stati messi in quarantena come phishing ad alta sicurezza, malware o regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="e4516-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="e4516-112">Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="e4516-112">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="e4516-113">Una notifica di posta indesiderata dell'utente finale contiene le informazioni seguenti per ogni messaggio in quarantena:</span><span class="sxs-lookup"><span data-stu-id="e4516-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="e4516-114">**Sender**: il nome e l'indirizzo di posta elettronica del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="e4516-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="e4516-115">**Oggetto**: testo della riga dell'oggetto del messaggio in quarantena.</span><span class="sxs-lookup"><span data-stu-id="e4516-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="e4516-116">**Date**: la data e l'ora (in formato UTC) in cui il messaggio è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="e4516-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="e4516-117">**Blocca mittente**: fare clic su questo collegamento per aggiungere il mittente all'elenco dei mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="e4516-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="e4516-118">Per ulteriori informazioni, vedere [bloccare un mittente della posta](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="e4516-118">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="e4516-119">**Release**: per i messaggi di posta indesiderata (non di phishing), è possibile rilasciare il messaggio qui senza andare a mettere in quarantena il centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="e4516-119">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="e4516-120">**Recensione**: fare clic su questo collegamento per accedere alla quarantena nel centro sicurezza & Compliance, in cui è possibile, a seconda del motivo per cui il messaggio è stato messo in quarantena, visualizzare, rilasciare, eliminare o segnalare i messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="e4516-120">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="e4516-121">Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come utente in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="e4516-121">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Esempio di notifica di posta indesiderata dell'utente finale](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="e4516-123">Un mittente bloccato può continuare A inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e4516-123">A blocked sender can still send you mail.</span></span> <span data-ttu-id="e4516-124">Tutti i messaggi provenienti da questo mittente che lo rendono alla cassetta postale verranno immediatamente spostati nella cartella posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e4516-124">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="e4516-125">I messaggi futuri provenienti da questo mittente andranno alla cartella posta indesiderata o alla quarantena dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="e4516-125">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="e4516-126">Se si desidera eliminare questi messaggi all'arrivo invece di metterli in quarantena, utilizzare le [regole del flusso di posta](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (note anche come regole di trasporto) per eliminare i messaggi all'arrivo.</span><span class="sxs-lookup"><span data-stu-id="e4516-126">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>
