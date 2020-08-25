---
title: Segnalare messaggi di posta indesiderata e di phishing in Outlook per iOS e Android
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sulle opzioni di creazione di report di posta indesiderata, non indesiderata e di phishing in Outlook per iOS e Android.
ms.openlocfilehash: 216f60eb168190603c7c9aba58cef27c2bf15b01
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867442"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="34383-103">Segnalare messaggi di posta indesiderata e di phishing in Outlook per iOS e Android in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="34383-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

<span data-ttu-id="34383-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o nelle cassette postali locali che usano l' [autenticazione moderna ibrida](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview?view=o365-worldwide), è possibile utilizzare le opzioni predefinite di Reporting in Outlook per iOS e Android per inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="34383-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview?view=o365-worldwide), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="34383-105">Cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="34383-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="34383-106">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale degli invii nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="34383-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="34383-107">Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="34383-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="34383-108">È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="34383-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="34383-109">Per ulteriori informazioni, vedere [specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing in Exchange Online](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="34383-109">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="34383-110">Per ulteriori informazioni sul reporting dei messaggi a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="34383-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="34383-111">Se la segnalazione della posta indesiderata è disabilitata per Outlook nel criterio di invio dell'utente, i messaggi di posta indesiderata o di phishing verranno spostati nella cartella posta indesiderata e non riportati nell'amministratore o Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34383-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="34383-112">Segnalare messaggi di posta indesiderata e di phishing in Outlook per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="34383-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="34383-113">Per i messaggi nella posta in arrivo o in qualsiasi altra cartella di posta elettronica, tranne la posta indesiderata, attenersi alla procedura seguente per segnalare messaggi di posta indesiderata e di phishing per iOS e Android:</span><span class="sxs-lookup"><span data-stu-id="34383-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="34383-114">Selezionare uno o più messaggi.</span><span class="sxs-lookup"><span data-stu-id="34383-114">Select one or more messages.</span></span>
2. <span data-ttu-id="34383-115">Nell'angolo superiore destro toccare i tre punti verticali.</span><span class="sxs-lookup"><span data-stu-id="34383-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="34383-116">Verrà aperto il menu azione.</span><span class="sxs-lookup"><span data-stu-id="34383-116">The action menu opens.</span></span>

   ![Segnalare messaggi di posta indesiderata o di phishing dal menu azione](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="34383-118">Toccare **segnala indesiderata** e quindi fare clic su **posta indesiderata** o **phishing**.</span><span class="sxs-lookup"><span data-stu-id="34383-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Segnalare messaggi di posta indesiderata o di phishing](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="34383-120">Nella finestra di dialogo che viene visualizzata, è possibile scegliere **segnala** o **No grazie**.</span><span class="sxs-lookup"><span data-stu-id="34383-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="34383-121">Se si seleziona **No Thanks**, se si utilizza la posta **indesiderata** , il messaggio viene spostato nella cartella posta indesiderata, se il messaggio viene toccato tramite **phishing** , la cartella degli elementi eliminati viene spostata.</span><span class="sxs-lookup"><span data-stu-id="34383-121">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="34383-122">Selezionare **segnala** anche per inviare una copia del messaggio a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34383-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Segnalare le opzioni di segnalazione di posta indesiderata o phishing](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="34383-124">Se si cambia idea, selezionare **Annulla** nella notifica del toast che viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="34383-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="34383-125">Il messaggio rimane nella cartella posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="34383-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="34383-126">Segnalare i messaggi non di posta indesiderata dalla cartella posta indesiderata in Outlook per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="34383-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="34383-127">Nella cartella posta indesiderata, attenersi alla procedura seguente per segnalare la posta indesiderata dei falsi positivi:</span><span class="sxs-lookup"><span data-stu-id="34383-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="34383-128">Selezionare uno o più messaggi.</span><span class="sxs-lookup"><span data-stu-id="34383-128">Select one or more messages.</span></span>
2. <span data-ttu-id="34383-129">Nell'angolo superiore destro toccare i tre punti verticali.</span><span class="sxs-lookup"><span data-stu-id="34383-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="34383-130">Verrà aperto il menu azione.</span><span class="sxs-lookup"><span data-stu-id="34383-130">The action menu opens.</span></span>

   ![Segnala non posta indesiderata dal menu azione](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="34383-132">Toccare **non indesiderato**.</span><span class="sxs-lookup"><span data-stu-id="34383-132">Tap **Not junk**.</span></span>

<span data-ttu-id="34383-133">Viene visualizzata una notifica del brindisi che il messaggio di posta elettronica è stato spostato nella cartella posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="34383-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="34383-134">Se si cambia idea, selezionare **Annulla** sulla notifica del toast.</span><span class="sxs-lookup"><span data-stu-id="34383-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="34383-135">Il messaggio di posta elettronica rimane nella cartella di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="34383-135">The email remains in the Junk folder.</span></span>
