---
title: Abilitare il componente aggiuntivo Segnala messaggio
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: Informazioni su come abilitare il componente aggiuntivo Segnala messaggio per Outlook e Outlook sul Web, per singoli utenti o per l'intera organizzazione.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fe47bcb4db42514f3a5252a567421ad792967cd1
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167576"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="bf261-103">Abilitare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="bf261-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bf261-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="bf261-104">**Applies to**</span></span>
- [<span data-ttu-id="bf261-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bf261-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="bf261-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="bf261-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="bf261-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf261-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> <span data-ttu-id="bf261-108">Gli amministratori di un'organizzazione di Microsoft 365 con cassette postali di Exchange Online consigliano di usare il portale Invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="bf261-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="bf261-109">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="bf261-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="bf261-110">I componenti aggiuntivi Segnala messaggio e Segnala phishing per Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) consentono di segnalare facilmente falsi positivi (messaggi di posta elettronica non consentiti) o falsi negativi (posta elettronica non consentita) a Microsoft e alle relative consociati per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="bf261-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="bf261-111">Microsoft usa questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bf261-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="bf261-112">Ad esempio, se gli utenti segnalano molti messaggi contrassegnati come posta indesiderata come non indesiderata utilizzando il componente aggiuntivo Segnala messaggio, il team di sicurezza dell'organizzazione potrebbe dover modificare i criteri di protezione dalla posta [indesiderata.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="bf261-112">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="bf261-113">È possibile installare il componente aggiuntivo Segnala messaggio o Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="bf261-113">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="bf261-114">Se si desidera che gli utenti segnalano solo messaggi di phishing, distribuire il componente aggiuntivo Segnala phishing nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bf261-114">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="bf261-115">Per ulteriori informazioni, vedere [Abilitare il componente aggiuntivo Segnala phishing.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="bf261-115">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="bf261-116">Il componente aggiuntivo Segnala messaggio consente di segnalare sia i messaggi di posta indesiderata che i messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="bf261-116">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="bf261-117">Gli amministratori possono abilitare il componente aggiuntivo Segnala messaggio per l'organizzazione e i singoli utenti possono installarlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bf261-117">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="bf261-118">Se si è un singolo utente, è possibile abilitare manualmente il [componente aggiuntivo Segnala messaggio.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="bf261-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="bf261-119">Se si è un amministratore globale o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile abilitare il componente aggiuntivo Segnala messaggio [per l'organizzazione.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="bf261-119">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="bf261-120">La funzionalità Segnala messaggio Add-In è ora disponibile tramite [la distribuzione centralizzata.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="bf261-120">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bf261-121">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="bf261-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bf261-122">Il componente aggiuntivo Segnala messaggio funziona con la maggior parte degli abbonamenti a Microsoft 365 e dei prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf261-122">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="bf261-123">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="bf261-123">Outlook on the web</span></span>
  - <span data-ttu-id="bf261-124">Outlook 2013 SP1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="bf261-124">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="bf261-125">Outlook 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="bf261-125">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="bf261-126">Outlook incluso nelle app di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="bf261-126">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="bf261-127">App Outlook per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="bf261-127">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="bf261-128">Il componente aggiuntivo Segnala messaggio non è disponibile per le cassette postali nelle organizzazioni Exchange locali.</span><span class="sxs-lookup"><span data-stu-id="bf261-128">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="bf261-129">È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="bf261-129">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="bf261-130">Per altre informazioni, vedi [Criteri di invio degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="bf261-130">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="bf261-131">Il Web browser esistente dovrebbe funzionare con il componente aggiuntivo Segnala messaggio.</span><span class="sxs-lookup"><span data-stu-id="bf261-131">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="bf261-132">Tuttavia, se si nota che il componente aggiuntivo non è disponibile o non funziona come previsto, provare un browser diverso.</span><span class="sxs-lookup"><span data-stu-id="bf261-132">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="bf261-133">Per le installazioni dell'organizzazione, l'organizzazione deve essere configurata per l'utilizzo dell'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="bf261-133">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="bf261-134">Per ulteriori informazioni, vedere [Determine if Centralized Deployment of add-ins works for your organization.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="bf261-134">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="bf261-135">Gli amministratori devono essere membri del gruppo di ruoli Amministratori globali.</span><span class="sxs-lookup"><span data-stu-id="bf261-135">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="bf261-136">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bf261-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="bf261-137">Ottenere il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="bf261-137">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="bf261-138">Passare a Microsoft AppSource e cercare il componente aggiuntivo <https://appsource.microsoft.com/marketplace/apps> Segnala messaggio.</span><span class="sxs-lookup"><span data-stu-id="bf261-138">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="bf261-139">Per passare direttamente al componente aggiuntivo Segnala messaggio, passare a <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="bf261-139">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="bf261-140">Fare **clic su SCARICA ORA.**</span><span class="sxs-lookup"><span data-stu-id="bf261-140">Click **GET IT NOW**.</span></span>

   ![Segnala messaggio - Scaricalo subito](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="bf261-142">Nella finestra di dialogo visualizzata, esaminare le condizioni per l'utilizzo e l'informativa sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="bf261-142">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="bf261-143">Accedi usando l'account aziendale o dell'istituto di istruzione (per uso aziendale) o l'account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="bf261-143">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="bf261-144">Dopo aver installato e abilitato il componente aggiuntivo, verranno visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf261-144">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="bf261-145">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="bf261-145">In Outlook, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo Segnala messaggio per Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="bf261-147">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="bf261-147">In Outlook on the web, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo Segnala messaggio di Outlook sul Web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="bf261-149">Per informazioni su come utilizzare il componente aggiuntivo, vedere Utilizzare il componente [aggiuntivo Segnala messaggio.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="bf261-149">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="bf261-150">Ottenere e abilitare il componente aggiuntivo Segnala messaggio per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="bf261-150">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="bf261-151">La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="bf261-151">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="bf261-152">Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Componenti aggiuntivi impostazioni \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> all'indirizzo  ,  Se la pagina del componente aggiuntivo non è visualizzata, passare al collegamento Impostazioni componenti aggiuntivi app integrate nella parte superiore della pagina App \>  \>  integrate. </span><span class="sxs-lookup"><span data-stu-id="bf261-152">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="bf261-153">Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="bf261-153">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="bf261-155">Nel riquadro **a comparsa Distribuisci un** nuovo componente aggiuntivo visualizzato, esaminare le informazioni e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="bf261-155">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="bf261-156">Nella pagina successiva fai clic su **Scegli dallo Store.**</span><span class="sxs-lookup"><span data-stu-id="bf261-156">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="bf261-158">Nella pagina **Seleziona componente aggiuntivo visualizzata** fare clic nella casella **di** ricerca, immettere **Segnala** messaggio e quindi fare clic **sull'icona** ![ ](../../media/search-icon.png) Cerca.</span><span class="sxs-lookup"><span data-stu-id="bf261-158">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="bf261-159">Nell'elenco dei risultati, trovare **Segnala messaggio e** quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="bf261-159">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Selezionare i risultati della ricerca dei componenti aggiuntivi](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="bf261-161">Nella finestra di dialogo visualizzata esaminare le informazioni sulla licenza e sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="bf261-161">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="bf261-162">Nella pagina **Configura componente** aggiuntivo visualizzata configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf261-162">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="bf261-163">**Utenti assegnati:** selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="bf261-163">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="bf261-164">**Tutti** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="bf261-164">**Everyone** (default)</span></span>
     - <span data-ttu-id="bf261-165">**Utenti/gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="bf261-165">**Specific users / groups**</span></span>
     - <span data-ttu-id="bf261-166">**Solo io**</span><span class="sxs-lookup"><span data-stu-id="bf261-166">**Just me**</span></span>

   - <span data-ttu-id="bf261-167">**Metodo di distribuzione:** selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf261-167">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="bf261-168">**Risolto (impostazione predefinita):** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non può essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="bf261-168">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="bf261-169">**Disponibile:** gli utenti possono installare il componente aggiuntivo in **Home** \> **Get add-ins** \> **Gestito dall'amministratore.**</span><span class="sxs-lookup"><span data-stu-id="bf261-169">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="bf261-170">**Facoltativo:** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma può scegliere di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="bf261-170">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Pagina Configura componente aggiuntivo](../../media/configure-add-in.png)

   <span data-ttu-id="bf261-172">Al termine, fare clic su **Distribuisci.**</span><span class="sxs-lookup"><span data-stu-id="bf261-172">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="bf261-173">Nella pagina **Deploy Report Message** visualizzata verrà visualizzato un rapporto sullo stato seguito da una conferma della distribuzione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="bf261-173">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="bf261-174">Dopo aver letto le informazioni, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="bf261-174">After you read the information, click **Next**.</span></span>

   ![Pagina Distribuisci messaggio rapporto](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="bf261-176">Nella pagina **Annuncia componente aggiuntivo visualizzata** esaminare le informazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="bf261-176">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Pagina Notifica componente aggiuntivo](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="bf261-178">Informazioni su come usare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="bf261-178">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="bf261-179">Gli utenti a cui è assegnato il componente aggiuntivo visualizzano le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf261-179">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="bf261-180">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="bf261-180">In Outlook, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo Segnala messaggio per Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="bf261-182">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="bf261-182">In Outlook on the web, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo Per i messaggi di report di Outlook sul Web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="bf261-184">Quando si invia una notifica agli utenti sul componente aggiuntivo Segnala messaggio, includere un collegamento per utilizzare il componente aggiuntivo [Segnala messaggio.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="bf261-184">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="bf261-185">Rivedere o modificare le impostazioni per il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="bf261-185">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="bf261-186">Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Componenti aggiuntivi impostazioni \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> all'indirizzo  ,  Se la pagina del componente aggiuntivo non è visualizzata, passare al collegamento Impostazioni componenti aggiuntivi app integrate nella parte superiore della pagina App \>  \>  integrate. </span><span class="sxs-lookup"><span data-stu-id="bf261-186">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Pagina Servizi e Add-Ins nella nuova interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="bf261-188">Trovare e selezionare il **componente aggiuntivo Segnala** messaggio.</span><span class="sxs-lookup"><span data-stu-id="bf261-188">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="bf261-189">Nel riquadro **a comparsa Modifica** messaggio rapporto visualizzato, rivedere e modificare le impostazioni in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bf261-189">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="bf261-190">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bf261-190">When you're finished, click **Save**.</span></span>

   ![Impostazioni per il componente aggiuntivo Segnala messaggio](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="bf261-192">Visualizzare ed esaminare i messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="bf261-192">View and review reported messages</span></span>

<span data-ttu-id="bf261-193">Per esaminare i messaggi che gli utenti segnalano a Microsoft, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf261-193">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="bf261-194">Usa il portale invii di amministratori.</span><span class="sxs-lookup"><span data-stu-id="bf261-194">Use the Admin Submissions portal.</span></span> <span data-ttu-id="bf261-195">Per altre informazioni, vedi [Visualizzare gli invii degli utenti a Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="bf261-195">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="bf261-196">Creare una regola del flusso di posta (nota anche come regola di trasporto) per inviare copie dei messaggi segnalati.</span><span class="sxs-lookup"><span data-stu-id="bf261-196">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="bf261-197">Per istruzioni, vedere [Usare le regole del flusso di posta per vedere cosa segnalano gli](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)utenti a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bf261-197">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
