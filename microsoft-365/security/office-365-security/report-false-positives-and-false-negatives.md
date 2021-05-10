---
title: Segnalare i falsi positivi e i falsi negativi in Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Informazioni su come segnalare falsi positivi e falsi negativi in Outlook tramite la funzionalità Segnala messaggio.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e848595035501f5da7b6099efd2700ebac6f17e3
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291164"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="abf43-103">Segnalare i falsi positivi e i falsi negativi in Outlook</span><span class="sxs-lookup"><span data-stu-id="abf43-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="abf43-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="abf43-104">**Applies to**</span></span>
- [<span data-ttu-id="abf43-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="abf43-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="abf43-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="abf43-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="abf43-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abf43-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="abf43-108">Se si è un amministratore di un'organizzazione Microsoft 365 con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="abf43-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="abf43-109">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="abf43-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="abf43-110">Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o cassette postali locali che utilizzano l'autenticazione moderna ibrida, è possibile inviare falsi positivi (buona posta elettronica bloccata o inviata alla cartella posta indesiderata) e falsi negativi (posta elettronica indesiderata o phish recapitati nella posta in arrivo) a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="abf43-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="abf43-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="abf43-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="abf43-112">Per una migliore esperienza di invio da parte dell'utente, usa il componente aggiuntivo Segnala messaggio o Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="abf43-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="abf43-113">Tieni presente che questo componente aggiuntivo funziona Outlook in tutte le piattaforme, ovvero sul Web, iOS, Android e Desktop.</span><span class="sxs-lookup"><span data-stu-id="abf43-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="abf43-114">Se si è un amministratore di un'organizzazione con Exchange Online cassette postali, utilizzare il portale invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="abf43-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="abf43-115">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="abf43-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="abf43-116">È possibile configurare l'invio dei messaggi direttamente a Microsoft, a una cassetta postale specificata o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="abf43-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="abf43-117">Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="abf43-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="abf43-118">Per ulteriori informazioni su come ottenere e abilitare i componenti aggiuntivi Segnala messaggio o Segnala phishing, vedere [Enable the Report Message or the Report Phishing add-ins.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="abf43-118">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="abf43-119">Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="abf43-119">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="abf43-120">Utilizzare la funzionalità Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="abf43-120">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="abf43-121">Segnalare messaggi di posta indesiderata e phishing</span><span class="sxs-lookup"><span data-stu-id="abf43-121">Report junk and phishing messages</span></span>

<span data-ttu-id="abf43-122">Per i messaggi in Posta in arrivo o qualsiasi altra cartella di posta elettronica ad eccezione della posta indesiderata, utilizzare il metodo seguente per segnalare messaggi di posta indesiderata e phishing:</span><span class="sxs-lookup"><span data-stu-id="abf43-122">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="abf43-123">Fare clic **sui puntini** di sospensione Altre azioni nell'angolo superiore destro del messaggio selezionato, fare clic su Segnala messaggio dal menu a discesa e quindi selezionare **Posta** indesiderata o **Phishing.** </span><span class="sxs-lookup"><span data-stu-id="abf43-123">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="abf43-124">![Report Message - More actions](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="abf43-124">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="abf43-125">![Segnala messaggio - Posta indesiderata e phishing](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="abf43-125">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="abf43-126">I messaggi selezionati verranno inviati a Microsoft per l'analisi e:</span><span class="sxs-lookup"><span data-stu-id="abf43-126">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="abf43-127">Spostato nella cartella Posta indesiderata se è stato segnalato come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="abf43-127">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="abf43-128">Eliminato se è stato segnalato come phishing.</span><span class="sxs-lookup"><span data-stu-id="abf43-128">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="abf43-129">Segnalare messaggi non indesiderati</span><span class="sxs-lookup"><span data-stu-id="abf43-129">Report messages that are not junk</span></span>

1. <span data-ttu-id="abf43-130">Fare clic **sui puntini** di sospensione Altre azioni nell'angolo superiore destro del messaggio selezionato, scegliere Segnala messaggio dal menu a discesa e quindi fare clic su **Non indesiderato.** </span><span class="sxs-lookup"><span data-stu-id="abf43-130">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="abf43-131">![Report Message - More actions](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="abf43-131">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="abf43-132">![Segnala messaggio - Non indesiderato](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="abf43-132">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="abf43-133">Il messaggio selezionato verrà inviato a Microsoft per l'analisi e spostato in Posta in arrivo o in qualsiasi altra cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="abf43-133">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="abf43-134">Visualizzare ed esaminare i messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="abf43-134">View and review reported messages</span></span>

<span data-ttu-id="abf43-135">Per esaminare i messaggi che gli utenti segnalano a Microsoft, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abf43-135">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="abf43-136">Usa il portale per gli invii di amministratori.</span><span class="sxs-lookup"><span data-stu-id="abf43-136">Use the Admin Submissions portal.</span></span> <span data-ttu-id="abf43-137">Per ulteriori informazioni, vedere [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="abf43-137">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="abf43-138">Creare una regola del flusso di posta (nota anche come regola di trasporto) per inviare copie dei messaggi segnalati.</span><span class="sxs-lookup"><span data-stu-id="abf43-138">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="abf43-139">Per istruzioni, vedere [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="abf43-139">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>