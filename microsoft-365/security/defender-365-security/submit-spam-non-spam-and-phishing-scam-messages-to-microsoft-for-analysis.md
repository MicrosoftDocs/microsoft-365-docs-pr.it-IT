---
title: Inviare manualmente i messaggi a Microsoft per l'analisi
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Gli amministratori e gli utenti finali possono imparare a inviare messaggi di posta elettronica (posta elettronica buona contrassegnata come posta non buona o non consentita) a Microsoft per l'analisi.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e0a6f564d82750c5ab8156680854c2453cda6971
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064453"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="d3224-103">Inviare manualmente i messaggi a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="d3224-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d3224-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="d3224-104">**Applies to**</span></span>
- [<span data-ttu-id="d3224-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d3224-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d3224-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="d3224-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d3224-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3224-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="d3224-108">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="d3224-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="d3224-109">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="d3224-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="d3224-110">Può essere frustrante quando gli utenti dell'organizzazione ricevono messaggi di posta indesiderata (posta indesiderata) o phishing nella posta in arrivo o se non ricevono un messaggio di posta elettronica legittimo perché è contrassegnato come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="d3224-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="d3224-111">Stiamo costantemente per ottimizzare i filtri per la posta indesiderata per essere più accurati.</span><span class="sxs-lookup"><span data-stu-id="d3224-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="d3224-112">L'utente e gli utenti possono contribuire a questo processo inviando falsi positivi (buona posta elettronica contrassegnata come non buona), falsi negativi (posta non consentita) e messaggi di phishing a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="d3224-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="d3224-113">A causa dell'elevato volume di invii ricevuti, potrebbe non essere possibile rispondere a tutte le richieste di analisi.</span><span class="sxs-lookup"><span data-stu-id="d3224-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="d3224-114">Inviare falsi negativi a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d3224-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="d3224-115">Anziché utilizzare le procedure seguenti per segnalare falsi negativi, gli utenti in Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) possono utilizzare il componente aggiuntivo Segnala messaggio o Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="d3224-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="d3224-116">Per informazioni su come installare e utilizzare questi strumenti, vedere [Enable the Report Message add-in](enable-the-report-message-add-in.md) e Enable the Report Phishing [add-in.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="d3224-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="d3224-117">Se si riceve un messaggio che passa attraverso il filtro posta indesiderata che dovrebbe essere stato identificato come posta indesiderata o phishing, è possibile inviare il messaggio ai team di analisi della posta indesiderata Microsoft e analisi di phishing Microsoft in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d3224-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="d3224-118">Gli analisti rivedranno il messaggio e lo aggiungeranno ai filtri a livello di servizio se soddisfano i criteri di classificazione.</span><span class="sxs-lookup"><span data-stu-id="d3224-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="d3224-119">Creare un nuovo messaggio di posta elettronica vuoto con uno dei seguenti destinatari:</span><span class="sxs-lookup"><span data-stu-id="d3224-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="d3224-120">**Posta indesiderata**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="d3224-120">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="d3224-121">**Phishing**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="d3224-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="d3224-122">Trascinare e rilasciare il messaggio di posta indesiderata o phishing nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3224-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="d3224-123">In questo modo il messaggio di posta indesiderata o phishing verrà salvato come allegato nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3224-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="d3224-124">Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale in modo da poter esaminare le intestazioni del messaggio).</span><span class="sxs-lookup"><span data-stu-id="d3224-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="d3224-125">È possibile allegare più messaggi nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3224-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="d3224-126">Assicurarsi che tutti i messaggi siano dello stesso tipo: messaggi di phishing o messaggi di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="d3224-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="d3224-127">Lasciare vuoto il corpo del nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3224-127">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="d3224-128">Utilizzare i formati .msg (formato predefinito di Outlook) o .eml (formato predefinito di Outlook sul Web) per i messaggi allegati.</span><span class="sxs-lookup"><span data-stu-id="d3224-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="d3224-129">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="d3224-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="d3224-130">Gli amministratori hanno diversi modi per bloccare messaggi specifici che vengono maldentificati come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="d3224-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="d3224-131">Per informazioni dettagliate, vedere [Create blocked sender lists in EOP.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="d3224-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="d3224-132">Inviare falsi positivi a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d3224-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="d3224-133">Anziché utilizzare le procedure seguenti per segnalare falsi positivi, gli utenti in Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) possono utilizzare il componente aggiuntivo Segnala messaggio o Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="d3224-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="d3224-134">Per informazioni su come installare e utilizzare questi strumenti, vedere [Enable the Report Message add-in](enable-the-report-message-add-in.md) e Enable the Report Phishing [add-in.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="d3224-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="d3224-135">Se un messaggio è stato erroneamente identificato come posta indesiderata, è possibile inviarlo al team di analisi della posta indesiderata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3224-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="d3224-136">Gli analisti valuteranno il messaggio e, a seconda dei risultati dell'analisi, i filtri a livello di servizio possono essere modificati per consentire l'invio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3224-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="d3224-137">Creare un nuovo messaggio di posta elettronica vuoto con `not_junk@office365.microsoft.com` come destinatario:</span><span class="sxs-lookup"><span data-stu-id="d3224-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="d3224-138">Trascinare il messaggio non identificato nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3224-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="d3224-139">In questo modo il messaggio non identificato verrà salvato come allegato nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3224-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="d3224-140">Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale in modo da poter esaminare le intestazioni del messaggio).</span><span class="sxs-lookup"><span data-stu-id="d3224-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="d3224-141">È possibile allegare più messaggi nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3224-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="d3224-142">Assicurarsi che tutti i messaggi siano dello stesso tipo: messaggi di phishing o messaggi di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="d3224-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="d3224-143">Lasciare vuoto il corpo del nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3224-143">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="d3224-144">Utilizzare i formati .msg (formato predefinito di Outlook) o .eml (formato predefinito di Outlook sul Web) per i messaggi allegati.</span><span class="sxs-lookup"><span data-stu-id="d3224-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="d3224-145">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="d3224-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="d3224-146">Gli amministratori hanno diversi modi per consentire a messaggi specifici di ignorare il filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="d3224-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="d3224-147">Per informazioni dettagliate, vedere [Create safe sender lists in EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="d3224-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="d3224-148">Dove vengono archiviati i dati degli invii a Microsoft?</span><span class="sxs-lookup"><span data-stu-id="d3224-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="d3224-149">I dati si trovano nel limite di conformità di Office 365 nei data center nordamericani.</span><span class="sxs-lookup"><span data-stu-id="d3224-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="d3224-150">I dati vengono esaminati dagli analisti del team di progettazione per migliorare l'efficacia dei filtri.</span><span class="sxs-lookup"><span data-stu-id="d3224-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="d3224-151">Creare una regola del flusso di posta per ricevere copie dei messaggi segnalati a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d3224-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="d3224-152">Per istruzioni, vedere [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="d3224-152">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
