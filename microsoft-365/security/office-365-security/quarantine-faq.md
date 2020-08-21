---
title: Domande frequenti sui messaggi in quarantena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Gli amministratori possono visualizzare le domande frequenti e le risposte sui messaggi in quarantena in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 896a83d4a09e8d0fcafeb6885cf2c63b6d8bb045
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826790"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="d973f-103">Domande frequenti sui messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="d973f-103">Quarantined messages FAQ</span></span>

<span data-ttu-id="d973f-104">In questo argomento vengono fornite domande e risposte frequenti sui messaggi di posta elettronica in quarantena per le organizzazioni Microsoft 365 con cassette postali in Exchange Online o organizzazioni di Exchange Online Protection (EOP) indipendenti senza cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d973f-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="d973f-105">Per domande e risposte sulla protezione dalla posta indesiderata, vedere [domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d973f-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="d973f-106">Per domande e risposte sulla protezione anti-malware, vedere [anti-malware Protection FAQ](anti-malware-protection-faq-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d973f-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="d973f-107">Per domande e risposte sulla protezione anti-spoofing, vedere domande [frequenti sulla protezione anti-spoofing](anti-spoofing-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d973f-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="d973f-108">Come si gestiscono i messaggi che sono stati messi in quarantena per malware?</span><span class="sxs-lookup"><span data-stu-id="d973f-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="d973f-109">Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena per malware.</span><span class="sxs-lookup"><span data-stu-id="d973f-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="d973f-110">Per ulteriori informazioni, vedere [gestire i messaggi e i file in quarantena come amministratore](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="d973f-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="d973f-111">Come si esegue la quarantena della posta indesiderata?</span><span class="sxs-lookup"><span data-stu-id="d973f-111">How do I quarantine spam?</span></span>

<span data-ttu-id="d973f-112">Per impostazione predefinita, i messaggi che vengono classificati come posta indesiderata o in blocco tramite filtro posta indesiderata vengono recapitati alla cassetta postale dell'utente e vengono spostati nella cartella posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="d973f-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="d973f-113">Tuttavia, è possibile creare e configurare criteri di protezione dalla posta indesiderata per la quarantena di posta indesiderata o messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d973f-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="d973f-114">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d973f-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="d973f-115">In che modo è possibile consentire agli utenti di accedere alla quarantena?</span><span class="sxs-lookup"><span data-stu-id="d973f-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="d973f-116">Un utente deve disporre di un account valido per accedere ai propri messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="d973f-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="d973f-117">EOP autonomo richiede che gli utenti siano rappresentati come utenti di posta elettronica in EOP (creato manualmente o creato tramite la sincronizzazione della directory).</span><span class="sxs-lookup"><span data-stu-id="d973f-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="d973f-118">Per ulteriori informazioni sulla gestione degli utenti in ambienti EOP autonomi, vedere [Manage mail Users in EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d973f-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="d973f-119">Quali messaggi possono accedere all'accesso degli utenti in quarantena?</span><span class="sxs-lookup"><span data-stu-id="d973f-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="d973f-120">Gli utenti possono accedere alla posta indesiderata, all'invio in massa e ai messaggi di phishing (da aprile 2020) dove sono destinatari.</span><span class="sxs-lookup"><span data-stu-id="d973f-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="d973f-121">Gli utenti finali non possono accedere ai messaggi di posta elettronica in quarantena, al phishing ad alta sicurezza o ai messaggio che sono stati messi in quarantena a causa del **recapito dell'azione di quarantena ospitata** nelle regole del flusso di mail (note anche come regole</span><span class="sxs-lookup"><span data-stu-id="d973f-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="d973f-122">Per ulteriori informazioni sugli utenti che accedono ai messaggi in quarantena, vedere [trovare e rilasciare i messaggi in quarantena come utente](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="d973f-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="d973f-123">Per quanto tempo i messaggi vengono mantenuti in quarantena?</span><span class="sxs-lookup"><span data-stu-id="d973f-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="d973f-124">È possibile configurare la durata della disattivazione della posta indesiderata, del phishing e della posta elettronica in blocco utilizzando i criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="d973f-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="d973f-125">Il valore predefinito è 30 giorni, che è anche il numero massimo.</span><span class="sxs-lookup"><span data-stu-id="d973f-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="d973f-126">Per ulteriori informazioni, vedere [configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d973f-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="d973f-127">Per i messaggi che sono stati messi in quarantena dall'azione della regola del flusso di posta **recapitare il messaggio alla quarantena ospitata**, i messaggi vengono mantenuti in quarantena per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="d973f-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="d973f-128">Non è possibile configurare questa durata.</span><span class="sxs-lookup"><span data-stu-id="d973f-128">You can't configure this duration.</span></span>

<span data-ttu-id="d973f-129">Dopo la scadenza del periodo di tempo, i messaggi vengono eliminati e non possono essere recuperati.</span><span class="sxs-lookup"><span data-stu-id="d973f-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="d973f-130">È possibile rilasciare o segnalare più di un messaggio in quarantena alla volta?</span><span class="sxs-lookup"><span data-stu-id="d973f-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="d973f-131">Nel centro sicurezza & conformità, è possibile selezionare e rilasciare fino a 100 messaggi alla volta.</span><span class="sxs-lookup"><span data-stu-id="d973f-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="d973f-132">Gli amministratori possono utilizzare i cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) e [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) in Exchange Online PowerShell o standalone EOP PowerShell per individuare e rilasciare i messaggi in quarantena in blocco e per segnalare falsi positivi in blocco.</span><span class="sxs-lookup"><span data-stu-id="d973f-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="d973f-133">Sono supportati i caratteri jolly nella ricerca dei messaggi in quarantena?</span><span class="sxs-lookup"><span data-stu-id="d973f-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="d973f-134">Posso cercare i messaggi in quarantena in base a un dominio specifico?</span><span class="sxs-lookup"><span data-stu-id="d973f-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="d973f-135">I caratteri jolly non sono supportati nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="d973f-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="d973f-136">Ad esempio, quando si esegue la ricerca di un mittente, è necessario specificare l'indirizzo di posta elettronica completo.</span><span class="sxs-lookup"><span data-stu-id="d973f-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="d973f-137">Tuttavia, è possibile utilizzare i caratteri jolly in PowerShell di Exchange Online o in EOP PowerShell autonomo.</span><span class="sxs-lookup"><span data-stu-id="d973f-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="d973f-138">Ad esempio, utilizzare il seguente comando per trovare messaggi di posta indesiderata in quarantena da tutti i mittenti nel dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="d973f-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="d973f-139">Successivamente, eseguire il seguente comando per rilasciare tali messaggi a tutti i destinatari originali:</span><span class="sxs-lookup"><span data-stu-id="d973f-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="d973f-140">Dopo aver rilasciato un messaggio, non è possibile rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="d973f-140">After you release a message, you can't release it again.</span></span>
