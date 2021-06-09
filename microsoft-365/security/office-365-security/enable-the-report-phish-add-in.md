---
title: Abilitare il componente aggiuntivo Report Phish
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Informazioni su come abilitare il componente aggiuntivo Segnala phishing per Outlook e Outlook sul Web, per singoli utenti o per l'intera organizzazione.
ms.openlocfilehash: 44fa55a82462de336982d3af2e3996c14699fd7c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625390"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="377b9-103">Abilitare il componente aggiuntivo Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="377b9-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="377b9-104">Se si è un amministratore di un'organizzazione Microsoft 365 con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="377b9-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="377b9-105">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="377b9-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="377b9-106">I componenti aggiuntivi Segnala messaggio e Segnala phishing per Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) consentono agli utenti di segnalare facilmente falsi positivi (buona posta elettronica contrassegnata come non buona) o falsi negativi (posta elettronica non consentita) a Microsoft e alle relative affiliate per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="377b9-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="377b9-107">Microsoft usa questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="377b9-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="377b9-108">Si supponga, ad esempio, che gli utenti segnalano molti messaggi utilizzando il componente aggiuntivo Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="377b9-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="377b9-109">Queste informazioni vengono visualizzate nel [dashboard di sicurezza](security-dashboard.md) e in altri report.</span><span class="sxs-lookup"><span data-stu-id="377b9-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="377b9-110">Il team di sicurezza dell'organizzazione può utilizzare queste informazioni per indicare che potrebbe essere necessario aggiornare i criteri anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="377b9-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="377b9-111">È possibile installare il componente aggiuntivo Segnala messaggio o Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="377b9-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="377b9-112">Se si desidera che gli utenti segnalano messaggi di posta indesiderata e di phishing, distribuire il componente aggiuntivo Segnala messaggio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="377b9-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="377b9-113">Per ulteriori informazioni, vedere [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="377b9-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="377b9-114">Il componente aggiuntivo Segnala phishing consente di segnalare solo i messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="377b9-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="377b9-115">Gli amministratori possono abilitare il componente aggiuntivo Segnala phishing per l'organizzazione e i singoli utenti possono installarlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="377b9-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="377b9-116">Se si è un singolo utente, è possibile abilitare il componente aggiuntivo Segnala phishing [per se stessi.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="377b9-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="377b9-117">Se si è un amministratore globale o un amministratore di Exchange Online e Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile abilitare il componente aggiuntivo Segnala phishing per [l'organizzazione.](#get-and-enable-the-report-phishing-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="377b9-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="377b9-118">L'Add-In di phishing dei report è ora disponibile tramite [distribuzione centralizzata.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="377b9-118">The Report Phishing Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="377b9-119">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="377b9-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="377b9-120">Il componente aggiuntivo Segnala phishing funziona con la maggior parte Microsoft 365 sottoscrizioni e i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="377b9-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="377b9-121">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="377b9-121">Outlook on the web</span></span>
  - <span data-ttu-id="377b9-122">Outlook 2013 SP1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="377b9-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="377b9-123">Outlook 2016 per Mac o versioni successive</span><span class="sxs-lookup"><span data-stu-id="377b9-123">Outlook 2016 for Mac or later</span></span>
  - <span data-ttu-id="377b9-124">Outlook incluse nelle app Microsoft 365 per Enterprise</span><span class="sxs-lookup"><span data-stu-id="377b9-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="377b9-125">Outlook app per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="377b9-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="377b9-126">Il componente aggiuntivo Segnala phishing non è disponibile per le cassette postali condivise o le cassette postali nelle organizzazioni Exchange locali.</span><span class="sxs-lookup"><span data-stu-id="377b9-126">The Report Phishing add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="377b9-127">È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="377b9-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="377b9-128">Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="377b9-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="377b9-129">Il Web browser esistente dovrebbe funzionare con il componente aggiuntivo Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="377b9-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="377b9-130">Tuttavia, se si nota che il componente aggiuntivo non è disponibile o non funziona come previsto, provare un browser diverso.</span><span class="sxs-lookup"><span data-stu-id="377b9-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="377b9-131">Per le installazioni dell'organizzazione, l'organizzazione deve essere configurata per l'utilizzo dell'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="377b9-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="377b9-132">Per ulteriori informazioni, vedere [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="377b9-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="377b9-133">Gli amministratori devono essere membri del gruppo di ruoli Amministratori globali.</span><span class="sxs-lookup"><span data-stu-id="377b9-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="377b9-134">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="377b9-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="377b9-135">Ottenere il componente aggiuntivo Segnala phishing per se stessi</span><span class="sxs-lookup"><span data-stu-id="377b9-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="377b9-136">Vai a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> all'indirizzo e cerca il componente aggiuntivo Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="377b9-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="377b9-137">Fai **clic su SCARICA ORA**.</span><span class="sxs-lookup"><span data-stu-id="377b9-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="377b9-138">Nella finestra di dialogo visualizzata esaminare le condizioni per l'utilizzo e l'informativa sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="377b9-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="377b9-139">Accedi usando l'account aziendale o dell'istituto di istruzione (per uso aziendale) o l'account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="377b9-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="377b9-140">Dopo aver installato e abilitato il componente aggiuntivo, verranno visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="377b9-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="377b9-141">In Outlook, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="377b9-141">In Outlook, the icon looks like this:</span></span>

  ![Segnalare l'icona del componente aggiuntivo phishing per Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="377b9-143">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="377b9-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook sul Web Segnala l'icona del componente aggiuntivo phishing](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="377b9-145">Ottenere e abilitare il componente aggiuntivo Segnala phishing per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="377b9-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="377b9-146">La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="377b9-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="377b9-147">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina Componenti aggiuntivi di **Impostazioni** \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> all'indirizzo ,   \>  \>   Se la pagina del componente aggiuntivo non è visualizzata, passare al collegamento Componenti aggiuntivi app integrate di Impostazioni nella parte superiore della pagina App integrate.</span><span class="sxs-lookup"><span data-stu-id="377b9-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="377b9-148">Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="377b9-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nell'Microsoft 365 di amministrazione](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="377b9-150">Nel riquadro **a comparsa Distribuisci un** nuovo componente aggiuntivo visualizzato esaminare le informazioni e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="377b9-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="377b9-151">Nella pagina successiva fai clic su **Scegli dallo Store.**</span><span class="sxs-lookup"><span data-stu-id="377b9-151">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="377b9-153">Nella pagina **Seleziona componente aggiuntivo visualizzata** fare clic nella casella **Di** ricerca, immettere **Segnala phishing** e quindi fare clic su **Cerca** ![ icona ](../../media/search-icon.png) Ricerca.</span><span class="sxs-lookup"><span data-stu-id="377b9-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="377b9-154">Nell'elenco dei risultati, individuare **Segnala phishing** e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="377b9-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="377b9-155">Nella finestra di dialogo visualizzata esaminare le informazioni sulla licenza e sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="377b9-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="377b9-156">Nella pagina **Configura componente aggiuntivo visualizzata** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="377b9-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="377b9-157">**Utenti assegnati**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="377b9-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="377b9-158">**Tutti** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="377b9-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="377b9-159">**Utenti/gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="377b9-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="377b9-160">**Solo io**</span><span class="sxs-lookup"><span data-stu-id="377b9-160">**Just me**</span></span>

   - <span data-ttu-id="377b9-161">**Metodo di distribuzione:** selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="377b9-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="377b9-162">**Risolto (impostazione predefinita):** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non può essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="377b9-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="377b9-163">**Disponibile**: gli utenti possono installare il componente aggiuntivo in **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="377b9-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="377b9-164">**Facoltativo:** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma può scegliere di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="377b9-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="377b9-165">Al termine, fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="377b9-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="377b9-166">Nella pagina **Distribuisci phishing** report visualizzata verrà visualizzato un rapporto sullo stato seguito da una conferma della distribuzione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="377b9-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="377b9-167">Dopo aver letto le informazioni, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="377b9-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="377b9-168">Nella pagina **Annuncia componente aggiuntivo visualizzata** esaminare le informazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="377b9-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="377b9-169">Informazioni su come usare il componente aggiuntivo Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="377b9-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="377b9-170">Gli utenti a cui è assegnato il componente aggiuntivo visualizzano le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="377b9-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="377b9-171">In Outlook, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="377b9-171">In Outlook, the icon looks like this:</span></span>

  ![Segnalare l'icona del componente aggiuntivo phishing per Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="377b9-173">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="377b9-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook sull'icona del componente aggiuntivo phishing report Web](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="377b9-175">Rivedere o modificare le impostazioni per il componente aggiuntivo Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="377b9-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="377b9-176">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina Componenti aggiuntivi di **Impostazioni** \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> all'indirizzo ,   \>  \>   Se la pagina del componente aggiuntivo non è visualizzata, passare al collegamento Componenti aggiuntivi app integrate di Impostazioni nella parte superiore della pagina App integrate.</span><span class="sxs-lookup"><span data-stu-id="377b9-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="377b9-177">Individuare e selezionare il **componente aggiuntivo Segnala** phishing.</span><span class="sxs-lookup"><span data-stu-id="377b9-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="377b9-178">Nel riquadro **a comparsa Modifica rapporto Phishing** visualizzato, esaminare e modificare le impostazioni in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="377b9-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="377b9-179">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="377b9-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="377b9-180">Visualizzare ed esaminare i messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="377b9-180">View and review reported messages</span></span>

<span data-ttu-id="377b9-181">Per esaminare i messaggi che gli utenti segnalano a Microsoft, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="377b9-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="377b9-182">Usa il portale per gli invii di amministratori.</span><span class="sxs-lookup"><span data-stu-id="377b9-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="377b9-183">Per ulteriori informazioni, vedere [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="377b9-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="377b9-184">Creare una regola del flusso di posta (nota anche come regola di trasporto) per inviare copie dei messaggi segnalati.</span><span class="sxs-lookup"><span data-stu-id="377b9-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="377b9-185">Per istruzioni, vedere [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="377b9-185">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
