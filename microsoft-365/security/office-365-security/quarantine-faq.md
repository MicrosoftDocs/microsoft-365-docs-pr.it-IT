---
title: Domande frequenti sulla quarantena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Risposte alle domande frequenti sulla quarantena in Office 365.
ms.openlocfilehash: 3947fbed2a17380a18320a8bffd08a8178ad2b3f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634425"
---
# <a name="quarantine-faq"></a><span data-ttu-id="15c11-103">Domande frequenti sulla quarantena</span><span class="sxs-lookup"><span data-stu-id="15c11-103">Quarantine FAQ</span></span>

<span data-ttu-id="15c11-104">In questo argomento sono riportate le domande frequenti e le risposte sulla quarantena per i clienti di Microsoft 365 con cassette postali in Exchange Online o autonomo Exchange Online Protection (EOP) clienti senza cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="15c11-104">This topic provides frequently asked questions and answers about quarantine for Microsoft 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="15c11-105">D: come si gestiscono i messaggi che sono stati messi in quarantena per malware?</span><span class="sxs-lookup"><span data-stu-id="15c11-105">Q: How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="15c11-106">Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena per malware.</span><span class="sxs-lookup"><span data-stu-id="15c11-106">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="15c11-107">Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="15c11-107">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

## <a name="q-how-do-i-quarantine-spam"></a><span data-ttu-id="15c11-108">D: come si esegue la quarantena della posta indesiderata?</span><span class="sxs-lookup"><span data-stu-id="15c11-108">Q: How do I quarantine spam?</span></span>

<span data-ttu-id="15c11-109">R.</span><span class="sxs-lookup"><span data-stu-id="15c11-109">A.</span></span> <span data-ttu-id="15c11-110">Per impostazione predefinita, i messaggi che vengono classificati come posta indesiderata o in blocco tramite filtro posta indesiderata vengono recapitati alla cassetta postale dell'utente e vengono spostati nella cartella posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="15c11-110">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="15c11-111">Tuttavia, è possibile creare e configurare criteri di protezione dalla posta indesiderata per la quarantena di posta indesiderata o messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="15c11-111">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="15c11-112">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="15c11-112">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="15c11-113">D: in che modo è possibile concedere agli utenti l'accesso alla quarantena?</span><span class="sxs-lookup"><span data-stu-id="15c11-113">Q: How do I give users access to the quarantine?</span></span>

<span data-ttu-id="15c11-114">R.</span><span class="sxs-lookup"><span data-stu-id="15c11-114">A.</span></span> <span data-ttu-id="15c11-115">Un utente deve disporre di un account valido per accedere ai propri messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="15c11-115">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="15c11-116">EOP autonomo richiede che gli utenti siano rappresentati come utenti di posta elettronica in EOP (creato manualmente o creato tramite la sincronizzazione della directory).</span><span class="sxs-lookup"><span data-stu-id="15c11-116">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="15c11-117">Per ulteriori informazioni sulla gestione degli utenti in ambienti EOP autonomi, vedere [Manage mail Users in EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="15c11-117">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="15c11-118">D: quali messaggi possono essere consentiti per l'accesso degli utenti in quarantena?</span><span class="sxs-lookup"><span data-stu-id="15c11-118">Q: What messages can end users access in quarantine?</span></span>

<span data-ttu-id="15c11-119">R.</span><span class="sxs-lookup"><span data-stu-id="15c11-119">A.</span></span> <span data-ttu-id="15c11-120">Gli utenti possono accedere alla posta indesiderata, alla massa e ai messaggi di phishing di aprile 2020 in cui si trova un destinatario.</span><span class="sxs-lookup"><span data-stu-id="15c11-120">Users can access spam, bulk email, and (as of April, 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="15c11-121">Gli utenti finali non possono accedere ai messaggi di posta elettronica in quarantena, al phishing ad alta sicurezza o ai messaggio che sono stati messi in quarantena a causa del **recapito dell'azione di quarantena ospitata** nelle regole del flusso di mail (note anche come regole</span><span class="sxs-lookup"><span data-stu-id="15c11-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="15c11-122">Per ulteriori informazioni sugli utenti che accedono ai messaggi in quarantena, vedere [trovare e rilasciare i messaggi in quarantena come utente in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="15c11-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="15c11-123">D: per quanto tempo i messaggi vengono mantenuti in quarantena?</span><span class="sxs-lookup"><span data-stu-id="15c11-123">Q: How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="15c11-124">R.</span><span class="sxs-lookup"><span data-stu-id="15c11-124">A.</span></span> <span data-ttu-id="15c11-125">È possibile configurare la durata della disattivazione della posta indesiderata, del phishing e della posta elettronica in blocco utilizzando i criteri di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="15c11-125">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="15c11-126">Il valore predefinito è 30 giorni, che è anche il numero massimo.</span><span class="sxs-lookup"><span data-stu-id="15c11-126">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="15c11-127">Per ulteriori informazioni, vedere [configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="15c11-127">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="15c11-128">Per i messaggi che sono stati messi in quarantena dall'azione della regola del flusso di posta **recapitare il messaggio alla quarantena ospitata**, i messaggi vengono mantenuti in quarantena per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="15c11-128">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="15c11-129">Non è possibile configurare questa durata.</span><span class="sxs-lookup"><span data-stu-id="15c11-129">You can't configure this duration.</span></span>

<span data-ttu-id="15c11-130">Dopo la scadenza del periodo di tempo, i messaggi vengono eliminati e non possono essere recuperati.</span><span class="sxs-lookup"><span data-stu-id="15c11-130">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="15c11-131">D: è possibile rilasciare o segnalare più di un messaggio in quarantena alla volta?</span><span class="sxs-lookup"><span data-stu-id="15c11-131">Q: Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="15c11-132">R.</span><span class="sxs-lookup"><span data-stu-id="15c11-132">A.</span></span> <span data-ttu-id="15c11-133">Nel centro sicurezza & conformità, è possibile selezionare e rilasciare fino a 100 messaggi alla volta.</span><span class="sxs-lookup"><span data-stu-id="15c11-133">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="15c11-134">Gli amministratori possono utilizzare i cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) e [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) in PowerShell di Exchange Online o PowerShell autonomo di Exchange Online Protection per individuare e rilasciare i messaggi in quarantena in blocco e per segnalare falsi positivi in blocco.</span><span class="sxs-lookup"><span data-stu-id="15c11-134">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="15c11-135">D: i caratteri jolly sono supportati durante la ricerca di messaggi in quarantena?</span><span class="sxs-lookup"><span data-stu-id="15c11-135">Q: Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="15c11-136">Posso cercare i messaggi in quarantena in base a un dominio specifico?</span><span class="sxs-lookup"><span data-stu-id="15c11-136">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="15c11-137">R.</span><span class="sxs-lookup"><span data-stu-id="15c11-137">A.</span></span> <span data-ttu-id="15c11-138">I caratteri jolly non sono supportati nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="15c11-138">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="15c11-139">Ad esempio, quando si esegue la ricerca di un mittente, è necessario specificare l'indirizzo di posta elettronica completo.</span><span class="sxs-lookup"><span data-stu-id="15c11-139">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="15c11-140">Tuttavia, è possibile utilizzare i caratteri jolly in PowerShell di Exchange Online o Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15c11-140">But, you can use wildcards in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

<span data-ttu-id="15c11-141">Ad esempio, utilizzare il seguente comando per trovare messaggi di posta indesiderata in quarantena da tutti i mittenti nel dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="15c11-141">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="15c11-142">Successivamente, eseguire il seguente comando per rilasciare tali messaggi a tutti i destinatari originali:</span><span class="sxs-lookup"><span data-stu-id="15c11-142">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="15c11-143">Dopo aver rilasciato un messaggio, non è possibile rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="15c11-143">After you release a message, you can't release it again.</span></span>
