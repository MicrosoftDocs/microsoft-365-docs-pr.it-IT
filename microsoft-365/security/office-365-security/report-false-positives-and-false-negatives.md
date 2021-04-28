---
title: Segnalare falsi positivi e falsi negativi in Outlook
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
description: Informazioni su come segnalare falsi positivi e falsi negativi in Outlook e abilitare i componenti aggiuntivi Segnala messaggio e Segnala phishing.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065175"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="e0b80-103">Segnalare falsi positivi e falsi negativi in Outlook</span><span class="sxs-lookup"><span data-stu-id="e0b80-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e0b80-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="e0b80-104">**Applies to**</span></span>
- [<span data-ttu-id="e0b80-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e0b80-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e0b80-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="e0b80-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e0b80-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0b80-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="e0b80-108">Se si è un amministratore in un'organizzazione di Microsoft 365 con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="e0b80-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="e0b80-109">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e0b80-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="e0b80-110">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle cassette postali locali che utilizzano l'autenticazione moderna ibrida, è possibile inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata) e falsi negativi (posta elettronica non consentita e phish consentiti) a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="e0b80-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email marked as spam) and false negatives (bad email and phish allowed) to Exchange Online Protection (EOP).</span></span>

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a><span data-ttu-id="e0b80-111">Aspetti da ricordare prima di utilizzare la funzionalità Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="e0b80-111">Things to remember before you use the Report Message feature</span></span>

- <span data-ttu-id="e0b80-112">Per una migliore esperienza di invio da parte dell'utente, usa il componente aggiuntivo Segnala messaggio o Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="e0b80-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="e0b80-113">Si noti che questo componente aggiuntivo funziona per Outlook in tutte le piattaforme, ovvero sul Web, iOS, Android e Desktop.</span><span class="sxs-lookup"><span data-stu-id="e0b80-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="e0b80-114">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, utilizzare il portale invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="e0b80-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="e0b80-115">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e0b80-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="e0b80-116">È possibile configurare l'invio dei messaggi direttamente a Microsoft, a una cassetta postale specificata o a entrambi.</span><span class="sxs-lookup"><span data-stu-id="e0b80-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="e0b80-117">Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="e0b80-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="e0b80-118">Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="e0b80-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="e0b80-119">Utilizzare la funzionalità Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="e0b80-119">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="e0b80-120">Segnalare messaggi di posta indesiderata e phishing</span><span class="sxs-lookup"><span data-stu-id="e0b80-120">Report junk and phishing messages</span></span>

<span data-ttu-id="e0b80-121">Per i messaggi in Posta in arrivo o qualsiasi altra cartella di posta elettronica ad eccezione della posta indesiderata, utilizzare il metodo seguente per segnalare messaggi di posta indesiderata e phishing:</span><span class="sxs-lookup"><span data-stu-id="e0b80-121">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="e0b80-122">Fare clic **sui puntini** di sospensione Altre azioni nell'angolo superiore destro del messaggio selezionato, fare clic su Segnala messaggio dal menu a discesa e quindi selezionare **Posta** indesiderata o **Phishing.** </span><span class="sxs-lookup"><span data-stu-id="e0b80-122">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0b80-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="e0b80-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0b80-124">![Segnala messaggio - Posta indesiderata e phishing](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="e0b80-124">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="e0b80-125">I messaggi selezionati verranno inviati a Microsoft per l'analisi e:</span><span class="sxs-lookup"><span data-stu-id="e0b80-125">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="e0b80-126">Spostato nella cartella Posta indesiderata se è stato segnalato come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e0b80-126">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="e0b80-127">Eliminato se è stato segnalato come phishing.</span><span class="sxs-lookup"><span data-stu-id="e0b80-127">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="e0b80-128">Segnalare messaggi non indesiderati</span><span class="sxs-lookup"><span data-stu-id="e0b80-128">Report messages that are not junk</span></span>

1. <span data-ttu-id="e0b80-129">Fare clic **sui puntini** di sospensione Altre azioni nell'angolo superiore destro del messaggio selezionato, scegliere Segnala messaggio dal menu a discesa e quindi fare clic su **Non indesiderato.** </span><span class="sxs-lookup"><span data-stu-id="e0b80-129">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0b80-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="e0b80-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0b80-131">![Segnala messaggio - Non indesiderato](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="e0b80-131">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="e0b80-132">Il messaggio selezionato verrà inviato a Microsoft per l'analisi e spostato in Posta in arrivo o in qualsiasi altra cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="e0b80-132">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a><span data-ttu-id="e0b80-133">Abilitare i componenti aggiuntivi Segnala messaggio e Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="e0b80-133">Enable the Report Message and Report Phishing add-ins</span></span>

<span data-ttu-id="e0b80-134">I componenti aggiuntivi Segnala messaggio e Segnala phishing per Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) consentono agli utenti di segnalare facilmente falsi positivi (buona posta elettronica contrassegnata come non buona) o falsi negativi (posta elettronica non consentita) a Microsoft e alle sue affiliate per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="e0b80-134">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="e0b80-135">Microsoft usa questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e0b80-135">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="e0b80-136">Si supponga, ad esempio, che gli utenti segnalano molti messaggi utilizzando il componente aggiuntivo Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="e0b80-136">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="e0b80-137">Queste informazioni vengono visualizzate nel dashboard di sicurezza e in altri report.</span><span class="sxs-lookup"><span data-stu-id="e0b80-137">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="e0b80-138">Il team di sicurezza dell'organizzazione può utilizzare queste informazioni per indicare che potrebbe essere necessario aggiornare i criteri anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="e0b80-138">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="e0b80-139">È possibile installare il componente aggiuntivo Segnala messaggio o Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="e0b80-139">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="e0b80-140">Se si desidera che gli utenti segnalano messaggi di posta indesiderata e di phishing, distribuire il componente aggiuntivo Segnala messaggio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0b80-140">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="e0b80-141">Per ulteriori informazioni, vedere Enable the Report Message add-in.</span><span class="sxs-lookup"><span data-stu-id="e0b80-141">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="e0b80-142">Il componente aggiuntivo Segnala messaggio consente di segnalare sia i messaggi di posta indesiderata che i messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="e0b80-142">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="e0b80-143">Gli amministratori possono abilitare il componente aggiuntivo Segnala messaggio per l'organizzazione e i singoli utenti possono installarlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e0b80-143">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="e0b80-144">Il componente aggiuntivo Segnala phishing consente di segnalare solo i messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="e0b80-144">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="e0b80-145">Gli amministratori possono abilitare il componente aggiuntivo Segnala phishing per l'organizzazione e i singoli utenti possono installarlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e0b80-145">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="e0b80-146">Se si è un singolo utente, è possibile abilitare entrambi i componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e0b80-146">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="e0b80-147">se si è un amministratore globale o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile abilitare il componente aggiuntivo Segnala messaggio e il componente aggiuntivo Segnala phishing per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0b80-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="e0b80-148">Entrambi i componenti aggiuntivi sono ora disponibili tramite [distribuzione centralizzata.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="e0b80-148">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e0b80-149">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="e0b80-149">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e0b80-150">Sia il componente aggiuntivo Segnala messaggio che il componente aggiuntivo Segnala phishing funzionano con la maggior parte delle sottoscrizioni di Microsoft 365 e i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0b80-150">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="e0b80-151">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="e0b80-151">Outlook on the web</span></span>
  - <span data-ttu-id="e0b80-152">Outlook 2013 SP1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="e0b80-152">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="e0b80-153">Outlook 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="e0b80-153">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="e0b80-154">Outlook incluso con le app di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="e0b80-154">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="e0b80-155">App Outlook per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="e0b80-155">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="e0b80-156">Entrambi i componenti aggiuntivi non sono disponibili per le cassette postali condivise o le cassette postali nelle organizzazioni exchange locali.</span><span class="sxs-lookup"><span data-stu-id="e0b80-156">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="e0b80-157">Il Web browser esistente dovrebbe funzionare sia con i componenti aggiuntivi Segnala messaggio che Segnala phishing. Tuttavia, se si nota che il componente aggiuntivo non è disponibile o non funziona come previsto, provare un browser diverso.</span><span class="sxs-lookup"><span data-stu-id="e0b80-157">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="e0b80-158">Per le installazioni dell'organizzazione, l'organizzazione deve essere configurata per l'utilizzo dell'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="e0b80-158">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="e0b80-159">Per ulteriori informazioni, vedere [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="e0b80-159">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="e0b80-160">Gli amministratori devono essere membri del gruppo di ruoli Amministratori globali.</span><span class="sxs-lookup"><span data-stu-id="e0b80-160">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="e0b80-161">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e0b80-161">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="e0b80-162">Ottenere il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="e0b80-162">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="e0b80-163">Ottenere il componente aggiuntivo per se stessi</span><span class="sxs-lookup"><span data-stu-id="e0b80-163">Get the add-in for yourself</span></span>

1. <span data-ttu-id="e0b80-164">Passare a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> all'indirizzo e cercare il componente aggiuntivo Segnala messaggio.</span><span class="sxs-lookup"><span data-stu-id="e0b80-164">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="e0b80-165">Per passare direttamente al componente aggiuntivo Segnala messaggio, passare a <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="e0b80-165">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="e0b80-166">Fai **clic su SCARICA ORA**.</span><span class="sxs-lookup"><span data-stu-id="e0b80-166">Click **GET IT NOW**.</span></span>

   ![Segnala messaggio - Scaricalo subito](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="e0b80-168">Nella finestra di dialogo visualizzata esaminare le condizioni per l'utilizzo e l'informativa sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-168">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="e0b80-169">Accedi usando l'account aziendale o dell'istituto di istruzione (per uso aziendale) o l'account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="e0b80-169">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="e0b80-170">Dopo aver installato e abilitato il componente aggiuntivo, verranno visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0b80-170">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="e0b80-171">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e0b80-171">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e0b80-172">![Icona del componente aggiuntivo Segnala messaggio per Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="e0b80-172">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="e0b80-173">In Outlook sul Web l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e0b80-173">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e0b80-174">![Icona del componente aggiuntivo Report di Outlook sul Web](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="e0b80-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="e0b80-175">Ottenere il componente aggiuntivo per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e0b80-175">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="e0b80-176">La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="e0b80-176">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="e0b80-177">Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e0b80-177">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e0b80-178">Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.</span><span class="sxs-lookup"><span data-stu-id="e0b80-178">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="e0b80-179">Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-179">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="e0b80-181">Nel riquadro **a comparsa Distribuisci un** nuovo componente aggiuntivo visualizzato esaminare le informazioni e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-181">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="e0b80-182">Nella pagina successiva fai clic su **Scegli dallo Store.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-182">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="e0b80-184">Nella pagina **Seleziona componente aggiuntivo visualizzata** fare clic nella casella **Di** ricerca, immettere **Segnala** messaggio e quindi fare clic su **Cerca** ![ icona ](../../media/search-icon.png) Ricerca.</span><span class="sxs-lookup"><span data-stu-id="e0b80-184">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="e0b80-185">Nell'elenco dei risultati, trovare **Segnala messaggio e** quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-185">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Selezionare i risultati della ricerca di componenti aggiuntivi](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="e0b80-187">Nella finestra di dialogo visualizzata esaminare le informazioni sulla licenza e sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-187">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="e0b80-188">Nella pagina **Configura componente aggiuntivo visualizzata** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0b80-188">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e0b80-189">**Utenti assegnati**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0b80-189">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="e0b80-190">**Tutti** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="e0b80-190">**Everyone** (default)</span></span>
     - <span data-ttu-id="e0b80-191">**Utenti/gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="e0b80-191">**Specific users / groups**</span></span>
     - <span data-ttu-id="e0b80-192">**Solo io**</span><span class="sxs-lookup"><span data-stu-id="e0b80-192">**Just me**</span></span>

   - <span data-ttu-id="e0b80-193">**Metodo di distribuzione:** selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0b80-193">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="e0b80-194">**Risolto (impostazione predefinita):** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non può essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="e0b80-194">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="e0b80-195">**Disponibile**: gli utenti possono installare il componente aggiuntivo in **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="e0b80-195">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="e0b80-196">**Facoltativo:** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma può scegliere di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="e0b80-196">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Pagina Configura componente aggiuntivo](../../media/configure-add-in.png)

   <span data-ttu-id="e0b80-198">Al termine, fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="e0b80-198">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="e0b80-199">Nella pagina **Deploy Report Message** visualizzata verrà visualizzato un rapporto sullo stato seguito da una conferma della distribuzione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e0b80-199">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="e0b80-200">Dopo aver letto le informazioni, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-200">After you read the information, click **Next**.</span></span>

   ![Pagina Distribuisci messaggio di report](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="e0b80-202">Nella pagina **Annuncia componente aggiuntivo visualizzata** esaminare le informazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-202">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Pagina Annuncia componente aggiuntivo](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="e0b80-204">Rivedere o modificare le impostazioni per il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="e0b80-204">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="e0b80-205">Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e0b80-205">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e0b80-206">Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.</span><span class="sxs-lookup"><span data-stu-id="e0b80-206">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Pagina Servizi e Add-Ins nella nuova interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="e0b80-208">Individuare e selezionare il componente aggiuntivo **Segnala** messaggio.</span><span class="sxs-lookup"><span data-stu-id="e0b80-208">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="e0b80-209">Nel riquadro **a comparsa Modifica messaggio** rapporto visualizzato esaminare e modificare le impostazioni in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0b80-209">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="e0b80-210">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e0b80-210">When you're finished, click **Save**.</span></span>

   ![Impostazioni per il componente aggiuntivo Segnala messaggio](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="e0b80-212">Ottenere il componente aggiuntivo Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="e0b80-212">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="e0b80-213">Ottenere il componente aggiuntivo per se stessi</span><span class="sxs-lookup"><span data-stu-id="e0b80-213">Get the add-in for yourself</span></span>

1. <span data-ttu-id="e0b80-214">Vai a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> all'indirizzo e cerca il componente aggiuntivo Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="e0b80-214">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="e0b80-215">Fai **clic su SCARICA ORA**.</span><span class="sxs-lookup"><span data-stu-id="e0b80-215">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="e0b80-216">Nella finestra di dialogo visualizzata esaminare le condizioni per l'utilizzo e l'informativa sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-216">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="e0b80-217">Accedi usando l'account aziendale o dell'istituto di istruzione (per uso aziendale) o l'account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="e0b80-217">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="e0b80-218">Dopo aver installato e abilitato il componente aggiuntivo, verranno visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0b80-218">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="e0b80-219">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e0b80-219">In Outlook, the icon looks like this:</span></span>

  ![Segnalare l'icona del componente aggiuntivo phishing per Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="e0b80-221">In Outlook sul Web l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e0b80-221">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e0b80-222">![Icona del componente aggiuntivo Di phishing per i report di Outlook sul Web](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="e0b80-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="e0b80-223">Ottenere il componente aggiuntivo per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e0b80-223">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="e0b80-224">La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="e0b80-224">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="e0b80-225">Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e0b80-225">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e0b80-226">Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.</span><span class="sxs-lookup"><span data-stu-id="e0b80-226">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="e0b80-227">Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-227">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="e0b80-229">Nel riquadro **a comparsa Distribuisci un** nuovo componente aggiuntivo visualizzato esaminare le informazioni e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-229">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="e0b80-230">Nella pagina successiva fai clic su **Scegli dallo Store.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-230">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="e0b80-232">Nella pagina **Seleziona componente aggiuntivo visualizzata** fare clic nella casella **Di** ricerca, immettere **Segnala phishing** e quindi fare clic su **Cerca** ![ icona ](../../media/search-icon.png) Ricerca.</span><span class="sxs-lookup"><span data-stu-id="e0b80-232">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="e0b80-233">Nell'elenco dei risultati, individuare **Segnala phishing** e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-233">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="e0b80-234">Nella finestra di dialogo visualizzata esaminare le informazioni sulla licenza e sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-234">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="e0b80-235">Nella pagina **Configura componente aggiuntivo visualizzata** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0b80-235">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e0b80-236">**Utenti assegnati**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0b80-236">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="e0b80-237">**Tutti** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="e0b80-237">**Everyone** (default)</span></span>
     - <span data-ttu-id="e0b80-238">**Utenti/gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="e0b80-238">**Specific users / groups**</span></span>
     - <span data-ttu-id="e0b80-239">**Solo io**</span><span class="sxs-lookup"><span data-stu-id="e0b80-239">**Just me**</span></span>

   - <span data-ttu-id="e0b80-240">**Metodo di distribuzione:** selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0b80-240">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="e0b80-241">**Risolto (impostazione predefinita):** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non può essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="e0b80-241">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="e0b80-242">**Disponibile**: gli utenti possono installare il componente aggiuntivo in **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="e0b80-242">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="e0b80-243">**Facoltativo:** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma può scegliere di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="e0b80-243">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="e0b80-244">Al termine, fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="e0b80-244">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="e0b80-245">Nella pagina **Distribuisci phishing** report visualizzata verrà visualizzato un rapporto sullo stato seguito da una conferma della distribuzione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e0b80-245">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="e0b80-246">Dopo aver letto le informazioni, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-246">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="e0b80-247">Nella pagina **Annuncia componente aggiuntivo visualizzata** esaminare le informazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="e0b80-247">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="e0b80-248">Rivedere o modificare le impostazioni per il componente aggiuntivo Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="e0b80-248">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="e0b80-249">Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e0b80-249">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e0b80-250">Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.</span><span class="sxs-lookup"><span data-stu-id="e0b80-250">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="e0b80-251">Individuare e selezionare il **componente aggiuntivo Segnala** phishing.</span><span class="sxs-lookup"><span data-stu-id="e0b80-251">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="e0b80-252">Nel riquadro **a comparsa Modifica rapporto Phishing** visualizzato, esaminare e modificare le impostazioni in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0b80-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="e0b80-253">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e0b80-253">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="e0b80-254">Visualizzare ed esaminare i messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="e0b80-254">View and review reported messages</span></span>

<span data-ttu-id="e0b80-255">Per esaminare i messaggi che gli utenti segnalano a Microsoft, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0b80-255">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="e0b80-256">Usa il portale per gli invii di amministratori.</span><span class="sxs-lookup"><span data-stu-id="e0b80-256">Use the Admin Submissions portal.</span></span> <span data-ttu-id="e0b80-257">Per ulteriori informazioni, vedere [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="e0b80-257">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="e0b80-258">Creare una regola del flusso di posta (nota anche come regola di trasporto) per inviare copie dei messaggi segnalati.</span><span class="sxs-lookup"><span data-stu-id="e0b80-258">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="e0b80-259">Per istruzioni, vedere [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="e0b80-259">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>