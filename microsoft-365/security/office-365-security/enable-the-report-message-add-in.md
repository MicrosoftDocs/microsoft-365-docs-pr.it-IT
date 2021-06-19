---
title: Abilitare i componenti aggiuntivi Segnala messaggio o Segnala phishing
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Informazioni su come abilitare i componenti aggiuntivi Segnala messaggio o Segnala phishing per Outlook e Outlook sul Web, per singoli utenti o per l'intera organizzazione.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8949322b0b691d59e59e5f7b80d2b9650e4115d5
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029910"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="52de3-103">Abilitare i componenti aggiuntivi Segnala messaggio o Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="52de3-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="52de3-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="52de3-104">**Applies to**</span></span>
- [<span data-ttu-id="52de3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="52de3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="52de3-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="52de3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="52de3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52de3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="52de3-108">Se si è un amministratore di un'organizzazione di Microsoft 365 con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel portale di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="52de3-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="52de3-109">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="52de3-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="52de3-110">I componenti aggiuntivi Segnala messaggio e Segnala phishing per Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) consentono agli utenti di segnalare facilmente falsi positivi (buona posta elettronica contrassegnata come non buona) o falsi negativi (posta elettronica non consentita) a Microsoft e alle sue affiliate per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="52de3-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="52de3-111">Microsoft usa questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="52de3-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="52de3-112">Si supponga, ad esempio, che gli utenti segnalano molti messaggi utilizzando il componente aggiuntivo Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="52de3-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="52de3-113">Queste informazioni vengono visualizzate nel dashboard di sicurezza e in altri report.</span><span class="sxs-lookup"><span data-stu-id="52de3-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="52de3-114">Il team di sicurezza dell'organizzazione può utilizzare queste informazioni per indicare che potrebbe essere necessario aggiornare i criteri anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="52de3-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="52de3-115">È possibile installare il componente aggiuntivo Segnala messaggio o Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="52de3-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="52de3-116">Se si desidera che gli utenti segnalano messaggi di posta indesiderata e di phishing, distribuire il componente aggiuntivo Segnala messaggio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52de3-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="52de3-117">Per ulteriori informazioni, vedere Enable the Report Message add-in.</span><span class="sxs-lookup"><span data-stu-id="52de3-117">For more information, see Enable the Report Message add-in.</span></span>

<span data-ttu-id="52de3-118">Il componente aggiuntivo Segnala messaggio consente di segnalare sia i messaggi di posta indesiderata che i messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="52de3-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="52de3-119">Gli amministratori possono abilitare il componente aggiuntivo Segnala messaggio per l'organizzazione e i singoli utenti possono installarlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="52de3-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="52de3-120">Il componente aggiuntivo Segnala phishing consente di segnalare solo i messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="52de3-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="52de3-121">Gli amministratori possono abilitare il componente aggiuntivo Segnala phishing per l'organizzazione e i singoli utenti possono installarlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="52de3-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="52de3-122">Se si è un singolo utente, è possibile abilitare entrambi i componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="52de3-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="52de3-123">Se si è un amministratore globale o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile abilitare il componente aggiuntivo Segnala messaggio e il componente aggiuntivo Segnala phishing per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52de3-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="52de3-124">Entrambi i componenti aggiuntivi sono ora disponibili tramite [distribuzione centralizzata.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="52de3-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="52de3-125">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="52de3-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="52de3-126">Sia il componente aggiuntivo Segnala messaggio che il componente aggiuntivo Segnala phishing funzionano con la maggior parte delle sottoscrizioni di Microsoft 365 e i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="52de3-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>
  - <span data-ttu-id="52de3-127">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="52de3-127">Outlook on the web</span></span>
  - <span data-ttu-id="52de3-128">Outlook 2013 SP1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="52de3-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="52de3-129">Outlook 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="52de3-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="52de3-130">Outlook incluso con le app di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="52de3-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="52de3-131">App Outlook per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="52de3-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="52de3-132">Entrambi i componenti aggiuntivi non sono disponibili per le cassette postali condivise o le cassette postali nelle organizzazioni exchange locali.</span><span class="sxs-lookup"><span data-stu-id="52de3-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="52de3-133">Il Web browser esistente dovrebbe funzionare sia con i componenti aggiuntivi Segnala messaggio che Segnala phishing. Tuttavia, se si nota che il componente aggiuntivo non è disponibile o non funziona come previsto, provare un browser diverso.</span><span class="sxs-lookup"><span data-stu-id="52de3-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="52de3-134">Per le installazioni dell'organizzazione, l'organizzazione deve essere configurata per l'utilizzo dell'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="52de3-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="52de3-135">Per ulteriori informazioni, vedere [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="52de3-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="52de3-136">Gli amministratori devono essere membri del gruppo di ruoli Amministratori globali.</span><span class="sxs-lookup"><span data-stu-id="52de3-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="52de3-137">Per ulteriori informazioni, vedere [Autorizzazioni nel portale di Microsoft 365 Defender.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="52de3-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="52de3-138">Per ulteriori informazioni su come segnalare un messaggio utilizzando la funzionalità Segnala messaggio, vedere Segnalare falsi positivi e [falsi negativi in Outlook.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="52de3-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52de3-139">Non è consigliabile utilizzare l'esperienza di creazione di report incorporata in Outlook perché non è possibile utilizzare i criteri di invio [degli utenti.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="52de3-139">We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="52de3-140">È consigliabile usare invece il componente aggiuntivo Segnala messaggio o Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="52de3-140">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="52de3-141">Ottenere il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="52de3-141">Get the Report Message add-in</span></span>

### <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="52de3-142">Ottenere il componente aggiuntivo Segnala messaggio per se stessi</span><span class="sxs-lookup"><span data-stu-id="52de3-142">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="52de3-143">Passare a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> all'indirizzo e cercare il componente aggiuntivo Segnala messaggio.</span><span class="sxs-lookup"><span data-stu-id="52de3-143">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="52de3-144">Per passare direttamente al componente aggiuntivo Segnala messaggio, passare a <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="52de3-144">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="52de3-145">Fai **clic su SCARICA ORA**.</span><span class="sxs-lookup"><span data-stu-id="52de3-145">Click **GET IT NOW**.</span></span>

   ![Segnala messaggio - Scaricalo subito](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="52de3-147">Nella finestra di dialogo visualizzata esaminare le condizioni per l'utilizzo e l'informativa sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="52de3-147">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="52de3-148">Accedi usando l'account aziendale o dell'istituto di istruzione (per uso aziendale) o l'account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="52de3-148">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="52de3-149">Dopo aver installato e abilitato il componente aggiuntivo, verranno visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="52de3-149">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="52de3-150">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="52de3-150">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="52de3-151">![Icona del componente aggiuntivo Segnala messaggio per Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="52de3-151">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="52de3-152">In Outlook sul Web l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="52de3-152">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="52de3-153">![Icona del componente aggiuntivo Report di Outlook sul Web](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="52de3-153">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="52de3-154">Ottenere il componente aggiuntivo Segnala messaggio per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="52de3-154">Get the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="52de3-155">La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="52de3-155">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="52de3-156">Nell'interfaccia di amministrazione di Microsoft 365 passare **alla** pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="52de3-156">In the Microsoft 365 admin center, go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="52de3-157">Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.</span><span class="sxs-lookup"><span data-stu-id="52de3-157">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="52de3-158">Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="52de3-158">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="52de3-160">Nel riquadro **a comparsa Distribuisci un** nuovo componente aggiuntivo visualizzato esaminare le informazioni e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="52de3-160">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="52de3-161">Nella pagina successiva fai clic su **Scegli dallo Store.**</span><span class="sxs-lookup"><span data-stu-id="52de3-161">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="52de3-163">Nella pagina **Seleziona componente aggiuntivo visualizzata** fare clic nella casella **Di** ricerca, immettere **Segnala** messaggio e quindi fare clic su **Cerca** ![ icona ](../../media/search-icon.png) Ricerca.</span><span class="sxs-lookup"><span data-stu-id="52de3-163">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="52de3-164">Nell'elenco dei risultati, trovare **Segnala messaggio e** quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="52de3-164">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Selezionare i risultati della ricerca di componenti aggiuntivi](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="52de3-166">Nella finestra di dialogo visualizzata esaminare le informazioni sulla licenza e sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="52de3-166">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="52de3-167">Nella pagina **Configura componente aggiuntivo visualizzata** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52de3-167">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="52de3-168">**Utenti assegnati**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="52de3-168">**Assigned users**: Select one of the following values:</span></span>
     - <span data-ttu-id="52de3-169">**Tutti** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="52de3-169">**Everyone** (default)</span></span>
     - <span data-ttu-id="52de3-170">**Utenti/gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="52de3-170">**Specific users / groups**</span></span>
     - <span data-ttu-id="52de3-171">**Solo io**</span><span class="sxs-lookup"><span data-stu-id="52de3-171">**Just me**</span></span>

   - <span data-ttu-id="52de3-172">**Metodo di distribuzione:** selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="52de3-172">**Deployment method**: Select one of the following values:</span></span>
     - <span data-ttu-id="52de3-173">**Risolto (impostazione predefinita):** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non può essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="52de3-173">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="52de3-174">**Disponibile**: gli utenti possono installare il componente aggiuntivo in **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="52de3-174">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="52de3-175">**Facoltativo:** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma può scegliere di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="52de3-175">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Pagina Configura componente aggiuntivo](../../media/configure-add-in.png)

   <span data-ttu-id="52de3-177">Al termine, fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="52de3-177">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="52de3-178">Nella pagina **Deploy Report Message** visualizzata verrà visualizzato un rapporto sullo stato seguito da una conferma della distribuzione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="52de3-178">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="52de3-179">Dopo aver letto le informazioni, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="52de3-179">After you read the information, click **Next**.</span></span>

   ![Pagina Distribuisci messaggio di report](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="52de3-181">Nella pagina **Annuncia componente aggiuntivo visualizzata** esaminare le informazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="52de3-181">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Pagina Annuncia componente aggiuntivo](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="52de3-183">Rivedere o modificare le impostazioni per il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="52de3-183">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="52de3-184">Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="52de3-184">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="52de3-185">Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.</span><span class="sxs-lookup"><span data-stu-id="52de3-185">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Pagina Servizi e Add-Ins nella nuova interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="52de3-187">Individuare e selezionare il componente aggiuntivo **Segnala** messaggio.</span><span class="sxs-lookup"><span data-stu-id="52de3-187">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="52de3-188">Nel riquadro **a comparsa Modifica messaggio** rapporto visualizzato esaminare e modificare le impostazioni in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52de3-188">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="52de3-189">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="52de3-189">When you're finished, click **Save**.</span></span>

   ![Impostazioni per il componente aggiuntivo Segnala messaggio](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="52de3-191">Ottenere il componente aggiuntivo Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="52de3-191">Get the Report Phishing add-in</span></span>

### <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="52de3-192">Ottenere il componente aggiuntivo Segnala phishing per se stessi</span><span class="sxs-lookup"><span data-stu-id="52de3-192">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="52de3-193">Vai a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> all'indirizzo e cerca il componente aggiuntivo Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="52de3-193">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="52de3-194">Fai **clic su SCARICA ORA**.</span><span class="sxs-lookup"><span data-stu-id="52de3-194">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="52de3-195">Nella finestra di dialogo visualizzata esaminare le condizioni per l'utilizzo e l'informativa sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="52de3-195">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="52de3-196">Accedi usando l'account aziendale o dell'istituto di istruzione (per uso aziendale) o l'account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="52de3-196">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="52de3-197">Dopo aver installato e abilitato il componente aggiuntivo, verranno visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="52de3-197">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="52de3-198">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="52de3-198">In Outlook, the icon looks like this:</span></span>

  ![Segnalare l'icona del componente aggiuntivo phishing per Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="52de3-200">In Outlook sul Web l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="52de3-200">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="52de3-201">![Icona del componente aggiuntivo Di phishing per i report di Outlook sul Web](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="52de3-201">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="52de3-202">Ottenere il componente aggiuntivo Segnala phishing per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="52de3-202">Get the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="52de3-203">La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="52de3-203">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="52de3-204">Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="52de3-204">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="52de3-205">Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.</span><span class="sxs-lookup"><span data-stu-id="52de3-205">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="52de3-206">Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="52de3-206">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="52de3-208">Nel riquadro **a comparsa Distribuisci un** nuovo componente aggiuntivo visualizzato esaminare le informazioni e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="52de3-208">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="52de3-209">Nella pagina successiva fai clic su **Scegli dallo Store.**</span><span class="sxs-lookup"><span data-stu-id="52de3-209">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="52de3-211">Nella pagina **Seleziona componente aggiuntivo visualizzata** fare clic nella casella **Di** ricerca, immettere **Segnala phishing** e quindi fare clic su **Cerca** ![ icona ](../../media/search-icon.png) Ricerca.</span><span class="sxs-lookup"><span data-stu-id="52de3-211">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="52de3-212">Nell'elenco dei risultati, individuare **Segnala phishing** e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="52de3-212">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="52de3-213">Nella finestra di dialogo visualizzata esaminare le informazioni sulla licenza e sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="52de3-213">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="52de3-214">Nella pagina **Configura componente aggiuntivo visualizzata** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52de3-214">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="52de3-215">**Utenti assegnati**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="52de3-215">**Assigned users**: Select one of the following values:</span></span>
     - <span data-ttu-id="52de3-216">**Tutti** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="52de3-216">**Everyone** (default)</span></span>
     - <span data-ttu-id="52de3-217">**Utenti/gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="52de3-217">**Specific users / groups**</span></span>
     - <span data-ttu-id="52de3-218">**Solo io**</span><span class="sxs-lookup"><span data-stu-id="52de3-218">**Just me**</span></span>

   - <span data-ttu-id="52de3-219">**Metodo di distribuzione:** selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="52de3-219">**Deployment method**: Select one of the following values:</span></span>
     - <span data-ttu-id="52de3-220">**Risolto (impostazione predefinita):** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non può essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="52de3-220">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="52de3-221">**Disponibile**: gli utenti possono installare il componente aggiuntivo in **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="52de3-221">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="52de3-222">**Facoltativo:** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma può scegliere di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="52de3-222">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="52de3-223">Al termine, fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="52de3-223">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="52de3-224">Nella pagina **Distribuisci phishing** report visualizzata verrà visualizzato un rapporto sullo stato seguito da una conferma della distribuzione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="52de3-224">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="52de3-225">Dopo aver letto le informazioni, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="52de3-225">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="52de3-226">Nella pagina **Annuncia componente aggiuntivo visualizzata** esaminare le informazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="52de3-226">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="52de3-227">Rivedere o modificare le impostazioni per il componente aggiuntivo Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="52de3-227">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="52de3-228">Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="52de3-228">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="52de3-229">Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.</span><span class="sxs-lookup"><span data-stu-id="52de3-229">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="52de3-230">Individuare e selezionare il **componente aggiuntivo Segnala** phishing.</span><span class="sxs-lookup"><span data-stu-id="52de3-230">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="52de3-231">Nel riquadro **a comparsa Modifica rapporto Phishing** visualizzato, esaminare e modificare le impostazioni in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="52de3-231">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="52de3-232">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="52de3-232">When you're finished, click **Save**.</span></span>
