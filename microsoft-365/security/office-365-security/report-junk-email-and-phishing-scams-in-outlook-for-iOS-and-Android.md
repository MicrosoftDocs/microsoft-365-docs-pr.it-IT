---
title: Segnalare posta indesiderata e phishing in Outlook per iOS e Android
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Gli amministratori possono conoscere le opzioni di segnalazione della posta indesiderata, non della posta indesiderata e di phishing incorporate in Outlook per iOS e Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166820"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="bbcdb-103">Segnalare posta indesiderata e phishing in Outlook per iOS e Android in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bbcdb-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bbcdb-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="bbcdb-104">**Applies to**</span></span>
- [<span data-ttu-id="bbcdb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bbcdb-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="bbcdb-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="bbcdb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="bbcdb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbcdb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="bbcdb-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle cassette postali locali che utilizzano l'autenticazione moderna [ibrida,](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)è possibile utilizzare le opzioni di creazione di report predefinite in Outlook per iOS e Android per inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="bbcdb-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bbcdb-109">Cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="bbcdb-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="bbcdb-110">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, si consiglia di utilizzare il portale Invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="bbcdb-111">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="bbcdb-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="bbcdb-112">È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-112">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="bbcdb-113">Per altre informazioni, vedi [Criteri per gli invii degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="bbcdb-113">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="bbcdb-114">Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="bbcdb-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="bbcdb-115">Se la segnalazione della posta indesiderata è disabilitata per Outlook nei criteri di invio degli utenti, i messaggi di posta indesiderata o di phishing verranno spostati nella cartella Posta indesiderata e non segnalati all'amministratore o a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-115">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="bbcdb-116">Segnalare messaggi di posta indesiderata e phishing in Outlook per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="bbcdb-116">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="bbcdb-117">Per i messaggi nella Cartella Posta in arrivo o in qualsiasi altra cartella di posta ad eccezione della posta indesiderata, utilizzare la procedura seguente per segnalare i messaggi di posta indesiderata e phishing per iOS e Android:</span><span class="sxs-lookup"><span data-stu-id="bbcdb-117">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="bbcdb-118">Selezionare uno o più messaggi.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-118">Select one or more messages.</span></span>
2. <span data-ttu-id="bbcdb-119">Nell'angolo superiore destro tocca i tre punti verticali.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-119">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="bbcdb-120">Verrà visualizzato il menu azioni.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-120">The action menu opens.</span></span>

   ![Segnalare posta indesiderata o phishing dal menu azione](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="bbcdb-122">Toccare **Segnala posta** indesiderata e quindi selezionare Posta **indesiderata** **o Phishing.**</span><span class="sxs-lookup"><span data-stu-id="bbcdb-122">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Segnalare posta indesiderata o phishing](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="bbcdb-124">Nella finestra di dialogo visualizzata, è possibile scegliere **Segnala** o **No Grazie.**</span><span class="sxs-lookup"><span data-stu-id="bbcdb-124">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="bbcdb-125">Se si **seleziona No Grazie,** se il messaggio viene toccato viene spostato nella cartella Posta indesiderata, se si tocca **Phishing,** il messaggio viene spostato nella cartella Posta eliminata. </span><span class="sxs-lookup"><span data-stu-id="bbcdb-125">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="bbcdb-126">Selezionare **Segnala** anche per inviare una copia del messaggio a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-126">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Opzioni di segnalazione della posta indesiderata o di phishing](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="bbcdb-128">Se cambi idea, seleziona **Annulla** nella notifica di tipo avviso popup visualizzata.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-128">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="bbcdb-129">Il messaggio rimane nella cartella Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-129">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="bbcdb-130">Segnalare i messaggi non indesiderati dalla cartella Posta indesiderata in Outlook per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="bbcdb-130">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="bbcdb-131">Nella cartella Posta indesiderata, utilizzare la procedura seguente per segnalare falsi positivi della posta indesiderata:</span><span class="sxs-lookup"><span data-stu-id="bbcdb-131">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="bbcdb-132">Selezionare uno o più messaggi.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-132">Select one or more messages.</span></span>
2. <span data-ttu-id="bbcdb-133">Nell'angolo superiore destro tocca i tre punti verticali.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-133">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="bbcdb-134">Verrà visualizzato il menu azioni.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-134">The action menu opens.</span></span>

   ![Segnalare la posta non indesiderata dal menu azioni](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="bbcdb-136">Toccare **Non indesiderato**.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-136">Tap **Not junk**.</span></span>

<span data-ttu-id="bbcdb-137">Viene visualizzata una notifica di tipo avviso popup che indica che il messaggio di posta elettronica è stato spostato nella posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-137">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="bbcdb-138">Se cambi idea, seleziona Annulla **nella** notifica di tipo avviso popup.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-138">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="bbcdb-139">Il messaggio di posta elettronica rimane nella cartella Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="bbcdb-139">The email remains in the Junk folder.</span></span>
