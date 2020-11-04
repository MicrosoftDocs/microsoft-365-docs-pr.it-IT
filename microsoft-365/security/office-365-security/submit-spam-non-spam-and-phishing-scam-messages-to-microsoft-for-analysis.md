---
title: Inviare manualmente messaggi a Microsoft per l'analisi
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Gli amministratori e gli utenti finali possono imparare a inviare messaggi di posta elettronica (buona posta contrassegnata come cattiva o cattiva posta elettronica consentita) a Microsoft per l'analisi.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68a0921f85e5b916cd53ebe84e4ea7d35e39967e
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877706"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="78f84-103">Inviare manualmente messaggi a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="78f84-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="78f84-104">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale degli invii nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="78f84-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="78f84-105">Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="78f84-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="78f84-106">Può essere frustrante quando gli utenti dell'organizzazione ricevono messaggi di posta indesiderata o messaggi di phishing nella cartella posta in arrivo o se non ricevono un messaggio di posta elettronica legittimo perché sono contrassegnati come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="78f84-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="78f84-107">La correzione dei filtri per la posta indesiderata è sempre più accurata.</span><span class="sxs-lookup"><span data-stu-id="78f84-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="78f84-108">L'utente e gli utenti possono aiutare questo processo inviando falsi positivi (buon messaggio di posta elettronica contrassegnato come cattivo), falsi negativi (posta errata consentita) e messaggi di phishing a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="78f84-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="78f84-109">A causa dell'elevato volume di invii ricevuti, potrebbe non essere possibile rispondere a tutte le richieste di analisi.</span><span class="sxs-lookup"><span data-stu-id="78f84-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="78f84-110">Inviare falsi negativi a Microsoft</span><span class="sxs-lookup"><span data-stu-id="78f84-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="78f84-111">Invece di utilizzare le procedure seguenti per segnalare falsi negativi, gli utenti in Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) possono utilizzare il componente aggiuntivo per i messaggi di report per Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="78f84-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="78f84-112">Per informazioni su come installare e utilizzare questo strumento, vedere [Enable the report Message Add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="78f84-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="78f84-113">Se si riceve un messaggio che passa attraverso il filtro di posta indesiderata che dovrebbe essere stato identificato come posta indesiderata o phishing, è possibile inviare il messaggio ai team di analisi di posta indesiderata di Microsoft e Microsoft Phishing Analysis come appropriato.</span><span class="sxs-lookup"><span data-stu-id="78f84-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="78f84-114">Gli analisti rivedranno il messaggio e lo aggiungeranno ai filtri a livello di servizio, se soddisfano i criteri di classificazione.</span><span class="sxs-lookup"><span data-stu-id="78f84-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="78f84-115">Creare un nuovo messaggio di posta elettronica vuoto con uno dei destinatari seguenti:</span><span class="sxs-lookup"><span data-stu-id="78f84-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="78f84-116">**Posta indesiderata** : `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="78f84-116">**Junk** : `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="78f84-117">**Phishing** : `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="78f84-117">**Phishing** : `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="78f84-118">Trascinare e rilasciare il messaggio di posta indesiderata o di phishing nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="78f84-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="78f84-119">In questo modo verrà salvato il messaggio di posta indesiderata o di phishing come allegato nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="78f84-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="78f84-120">Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale, in modo da poter ispezionare le intestazioni del messaggio).</span><span class="sxs-lookup"><span data-stu-id="78f84-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="78f84-121">È possibile allegare più messaggi nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="78f84-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="78f84-122">Verificare che tutti i messaggi siano dello stesso tipo, ovvero messaggi di phishing o messaggi di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="78f84-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="78f84-123">Lasciare vuoto il corpo del nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="78f84-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="78f84-124">Utilizzare i formati. msg (formato Outlook predefinito) o. eml (predefinito di Outlook sul Web Format) per i messaggi allegati.</span><span class="sxs-lookup"><span data-stu-id="78f84-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="78f84-125">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="78f84-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="78f84-126">Gli amministratori dispongono di diversi modi per bloccare messaggi specifici che vengono erroneamente identificati come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="78f84-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="78f84-127">Per ulteriori informazioni, vedere [creare elenchi di mittenti bloccati in EOP](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="78f84-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="78f84-128">Inviare falsi positivi a Microsoft</span><span class="sxs-lookup"><span data-stu-id="78f84-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="78f84-129">Invece di utilizzare le procedure seguenti per segnalare falsi positivi, gli utenti di Outlook e Outlook sul Web possono utilizzare il componente aggiuntivo per i messaggi di report per Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="78f84-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="78f84-130">Per informazioni su come installare e utilizzare questo strumento, vedere [Enable the report Message Add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="78f84-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="78f84-131">Se un messaggio è stato erroneamente identificato come posta indesiderata, è possibile inviare il messaggio al team di analisi di posta indesiderata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78f84-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="78f84-132">Gli analisti valuteranno il messaggio e (a seconda dei risultati dell'analisi), i filtri a livello di servizio possono essere modificati in modo da consentire il passaggio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="78f84-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="78f84-133">Creare un nuovo messaggio di posta elettronica vuoto `not_junk@office365.microsoft.com` come destinatario:</span><span class="sxs-lookup"><span data-stu-id="78f84-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="78f84-134">Trascinare e rilasciare il messaggio erroneamente identificato nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="78f84-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="78f84-135">In questo modo verrà salvato il messaggio erroneamente identificato come allegato nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="78f84-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="78f84-136">Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale, in modo da poter ispezionare le intestazioni del messaggio).</span><span class="sxs-lookup"><span data-stu-id="78f84-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="78f84-137">È possibile allegare più messaggi nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="78f84-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="78f84-138">Verificare che tutti i messaggi siano dello stesso tipo, ovvero messaggi di phishing o messaggi di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="78f84-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="78f84-139">Lasciare vuoto il corpo del nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="78f84-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="78f84-140">Utilizzare i formati. msg (formato Outlook predefinito) o. eml (predefinito di Outlook sul Web Format) per i messaggi allegati.</span><span class="sxs-lookup"><span data-stu-id="78f84-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="78f84-141">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="78f84-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="78f84-142">Gli amministratori dispongono di diversi modi per consentire ai messaggi specifici di ignorare il filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="78f84-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="78f84-143">Per informazioni dettagliate, vedere [creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="78f84-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="78f84-144">Creare una regola del flusso di posta elettronica per ricevere le copie dei messaggi segnalati a Microsoft</span><span class="sxs-lookup"><span data-stu-id="78f84-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="78f84-145">Per istruzioni, vedere [utilizzo delle regole del flusso di posta per vedere cosa gli utenti stanno segnalando a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="78f84-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
