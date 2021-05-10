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
ms.openlocfilehash: dc54c5b74697ac41a1d4ff0818467dba662b31f5
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295820"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="40a77-103">Abilitare i componenti aggiuntivi Segnala messaggio o Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="40a77-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="40a77-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="40a77-104">**Applies to**</span></span>
- [<span data-ttu-id="40a77-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="40a77-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="40a77-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="40a77-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="40a77-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40a77-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="40a77-108">Se si è un amministratore di un'organizzazione Microsoft 365 con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="40a77-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="40a77-109">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="40a77-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="40a77-110">I componenti aggiuntivi Segnala messaggio e Segnala phishing per Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) consentono agli utenti di segnalare facilmente falsi positivi (buona posta elettronica contrassegnata come non buona) o falsi negativi (posta elettronica non consentita) a Microsoft e alle relative affiliate per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="40a77-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="40a77-111">Microsoft usa questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="40a77-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="40a77-112">Si supponga, ad esempio, che gli utenti segnalano molti messaggi utilizzando il componente aggiuntivo Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="40a77-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="40a77-113">Queste informazioni vengono visualizzate nel dashboard di sicurezza e in altri report.</span><span class="sxs-lookup"><span data-stu-id="40a77-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="40a77-114">Il team di sicurezza dell'organizzazione può utilizzare queste informazioni per indicare che potrebbe essere necessario aggiornare i criteri anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="40a77-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="40a77-115">È possibile installare il componente aggiuntivo Segnala messaggio o Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="40a77-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="40a77-116">Se si desidera che gli utenti segnalano messaggi di posta indesiderata e di phishing, distribuire il componente aggiuntivo Segnala messaggio nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40a77-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="40a77-117">Per ulteriori informazioni, vedere Enable the Report Message add-in.</span><span class="sxs-lookup"><span data-stu-id="40a77-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="40a77-118">Il componente aggiuntivo Segnala messaggio consente di segnalare sia i messaggi di posta indesiderata che i messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="40a77-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="40a77-119">Gli amministratori possono abilitare il componente aggiuntivo Segnala messaggio per l'organizzazione e i singoli utenti possono installarlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="40a77-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="40a77-120">Il componente aggiuntivo Segnala phishing consente di segnalare solo i messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="40a77-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="40a77-121">Gli amministratori possono abilitare il componente aggiuntivo Segnala phishing per l'organizzazione e i singoli utenti possono installarlo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="40a77-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="40a77-122">Se si è un singolo utente, è possibile abilitare entrambi i componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="40a77-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="40a77-123">se si è un amministratore globale o un amministratore di Exchange Online e Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile abilitare il componente aggiuntivo Segnala messaggio e il componente aggiuntivo Segnala phishing per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40a77-123">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="40a77-124">Entrambi i componenti aggiuntivi sono ora disponibili tramite [distribuzione centralizzata.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="40a77-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="40a77-125">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="40a77-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="40a77-126">Sia il componente aggiuntivo Segnala messaggio che il componente aggiuntivo Segnala phishing funzionano con la maggior parte delle sottoscrizioni Microsoft 365 e i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a77-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="40a77-127">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="40a77-127">Outlook on the web</span></span>
  - <span data-ttu-id="40a77-128">Outlook 2013 SP1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="40a77-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="40a77-129">Outlook 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="40a77-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="40a77-130">Outlook incluse nelle app Microsoft 365 per Enterprise</span><span class="sxs-lookup"><span data-stu-id="40a77-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="40a77-131">Outlook app per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="40a77-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="40a77-132">Entrambi i componenti aggiuntivi non sono disponibili per le cassette postali condivise o le cassette postali nelle organizzazioni Exchange locali.</span><span class="sxs-lookup"><span data-stu-id="40a77-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="40a77-133">Il Web browser esistente dovrebbe funzionare sia con i componenti aggiuntivi Segnala messaggio che Segnala phishing. Tuttavia, se si nota che il componente aggiuntivo non è disponibile o non funziona come previsto, provare un browser diverso.</span><span class="sxs-lookup"><span data-stu-id="40a77-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="40a77-134">Per le installazioni dell'organizzazione, l'organizzazione deve essere configurata per l'utilizzo dell'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="40a77-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="40a77-135">Per ulteriori informazioni, vedere [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="40a77-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="40a77-136">Gli amministratori devono essere membri del gruppo di ruoli Amministratori globali.</span><span class="sxs-lookup"><span data-stu-id="40a77-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="40a77-137">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="40a77-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="40a77-138">Per ulteriori informazioni su come segnalare un messaggio utilizzando la funzionalità Segnala messaggio, vedere Segnalare falsi positivi e falsi negativi [in Outlook](report-false-positives-and-false-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="40a77-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="40a77-139">Ottenere il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="40a77-139">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="40a77-140">Ottenere il componente aggiuntivo per se stessi</span><span class="sxs-lookup"><span data-stu-id="40a77-140">Get the add-in for yourself</span></span>

1. <span data-ttu-id="40a77-141">Passare a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> all'indirizzo e cercare il componente aggiuntivo Segnala messaggio.</span><span class="sxs-lookup"><span data-stu-id="40a77-141">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="40a77-142">Per passare direttamente al componente aggiuntivo Segnala messaggio, passare a <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="40a77-142">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="40a77-143">Fai **clic su SCARICA ORA**.</span><span class="sxs-lookup"><span data-stu-id="40a77-143">Click **GET IT NOW**.</span></span>

   ![Segnala messaggio - Scaricalo subito](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="40a77-145">Nella finestra di dialogo visualizzata esaminare le condizioni per l'utilizzo e l'informativa sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="40a77-145">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="40a77-146">Accedi usando l'account aziendale o dell'istituto di istruzione (per uso aziendale) o l'account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="40a77-146">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="40a77-147">Dopo aver installato e abilitato il componente aggiuntivo, verranno visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a77-147">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="40a77-148">In Outlook, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="40a77-148">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="40a77-149">![Icona del componente aggiuntivo Segnala messaggio per Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="40a77-149">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="40a77-150">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="40a77-150">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="40a77-151">![Outlook sul Web Segnala icona del componente aggiuntivo Messaggio](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="40a77-151">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="40a77-152">Ottenere il componente aggiuntivo per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="40a77-152">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="40a77-153">La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="40a77-153">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="40a77-154">Nell'Microsoft 365 di amministrazione passare alla pagina Impostazioni  componenti \> **aggiuntivi** all'indirizzo <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="40a77-154">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="40a77-155">Se la pagina del  componente aggiuntivo non è  visualizzata, passare al collegamento componenti aggiuntivi Impostazioni app integrate nella parte superiore della pagina \>  \>  **App** integrate.</span><span class="sxs-lookup"><span data-stu-id="40a77-155">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="40a77-156">Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="40a77-156">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nell'Microsoft 365 di amministrazione](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="40a77-158">Nel riquadro **a comparsa Distribuisci un** nuovo componente aggiuntivo visualizzato esaminare le informazioni e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="40a77-158">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="40a77-159">Nella pagina successiva fai clic su **Scegli dallo Store.**</span><span class="sxs-lookup"><span data-stu-id="40a77-159">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="40a77-161">Nella pagina **Seleziona componente aggiuntivo visualizzata** fare clic nella casella **Di** ricerca, immettere **Segnala** messaggio e quindi fare clic su **Cerca** ![ icona ](../../media/search-icon.png) Ricerca.</span><span class="sxs-lookup"><span data-stu-id="40a77-161">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="40a77-162">Nell'elenco dei risultati, trovare **Segnala messaggio e** quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="40a77-162">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Selezionare i risultati della ricerca di componenti aggiuntivi](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="40a77-164">Nella finestra di dialogo visualizzata esaminare le informazioni sulla licenza e sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="40a77-164">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="40a77-165">Nella pagina **Configura componente aggiuntivo visualizzata** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a77-165">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="40a77-166">**Utenti assegnati**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a77-166">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="40a77-167">**Tutti** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="40a77-167">**Everyone** (default)</span></span>
     - <span data-ttu-id="40a77-168">**Utenti/gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="40a77-168">**Specific users / groups**</span></span>
     - <span data-ttu-id="40a77-169">**Solo io**</span><span class="sxs-lookup"><span data-stu-id="40a77-169">**Just me**</span></span>

   - <span data-ttu-id="40a77-170">**Metodo di distribuzione:** selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a77-170">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="40a77-171">**Risolto (impostazione predefinita):** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non può essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="40a77-171">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="40a77-172">**Disponibile**: gli utenti possono installare il componente aggiuntivo in **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="40a77-172">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="40a77-173">**Facoltativo:** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma può scegliere di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="40a77-173">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Pagina Configura componente aggiuntivo](../../media/configure-add-in.png)

   <span data-ttu-id="40a77-175">Al termine, fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="40a77-175">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="40a77-176">Nella pagina **Deploy Report Message** visualizzata verrà visualizzato un rapporto sullo stato seguito da una conferma della distribuzione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="40a77-176">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="40a77-177">Dopo aver letto le informazioni, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="40a77-177">After you read the information, click **Next**.</span></span>

   ![Pagina Distribuisci messaggio di report](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="40a77-179">Nella pagina **Annuncia componente aggiuntivo visualizzata** esaminare le informazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="40a77-179">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Pagina Annuncia componente aggiuntivo](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="40a77-181">Rivedere o modificare le impostazioni per il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="40a77-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="40a77-182">Nell'Microsoft 365 di amministrazione passare alla pagina Impostazioni  componenti \> **aggiuntivi** all'indirizzo <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="40a77-182">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="40a77-183">Se la pagina del  componente aggiuntivo non è  visualizzata, passare al collegamento componenti aggiuntivi Impostazioni app integrate nella parte superiore della pagina \>  \>  **App** integrate.</span><span class="sxs-lookup"><span data-stu-id="40a77-183">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Pagina Servizi e Add-Ins nella nuova interfaccia Microsoft 365 amministrazione](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="40a77-185">Individuare e selezionare il componente aggiuntivo **Segnala** messaggio.</span><span class="sxs-lookup"><span data-stu-id="40a77-185">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="40a77-186">Nel riquadro **a comparsa Modifica messaggio** rapporto visualizzato esaminare e modificare le impostazioni in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40a77-186">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="40a77-187">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="40a77-187">When you're finished, click **Save**.</span></span>

   ![Impostazioni per il componente aggiuntivo Segnala messaggio](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="40a77-189">Ottenere il componente aggiuntivo Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="40a77-189">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="40a77-190">Ottenere il componente aggiuntivo per se stessi</span><span class="sxs-lookup"><span data-stu-id="40a77-190">Get the add-in for yourself</span></span>

1. <span data-ttu-id="40a77-191">Vai a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> all'indirizzo e cerca il componente aggiuntivo Segnala phishing.</span><span class="sxs-lookup"><span data-stu-id="40a77-191">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="40a77-192">Fai **clic su SCARICA ORA**.</span><span class="sxs-lookup"><span data-stu-id="40a77-192">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="40a77-193">Nella finestra di dialogo visualizzata esaminare le condizioni per l'utilizzo e l'informativa sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="40a77-193">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="40a77-194">Accedi usando l'account aziendale o dell'istituto di istruzione (per uso aziendale) o l'account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="40a77-194">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="40a77-195">Dopo aver installato e abilitato il componente aggiuntivo, verranno visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a77-195">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="40a77-196">In Outlook, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="40a77-196">In Outlook, the icon looks like this:</span></span>

  ![Segnalare l'icona del componente aggiuntivo phishing per Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="40a77-198">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="40a77-198">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="40a77-199">![Outlook sul Web Segnala l'icona del componente aggiuntivo phishing](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="40a77-199">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="40a77-200">Ottenere il componente aggiuntivo per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="40a77-200">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="40a77-201">La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="40a77-201">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="40a77-202">Nell'Microsoft 365 di amministrazione passare alla pagina Impostazioni  componenti \> **aggiuntivi** all'indirizzo <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="40a77-202">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="40a77-203">Se la pagina del  componente aggiuntivo non è  visualizzata, passare al collegamento componenti aggiuntivi Impostazioni app integrate nella parte superiore della pagina \>  \>  **App** integrate.</span><span class="sxs-lookup"><span data-stu-id="40a77-203">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="40a77-204">Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="40a77-204">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nell'Microsoft 365 di amministrazione](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="40a77-206">Nel riquadro **a comparsa Distribuisci un** nuovo componente aggiuntivo visualizzato esaminare le informazioni e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="40a77-206">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="40a77-207">Nella pagina successiva fai clic su **Scegli dallo Store.**</span><span class="sxs-lookup"><span data-stu-id="40a77-207">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="40a77-209">Nella pagina **Seleziona componente aggiuntivo visualizzata** fare clic nella casella **Di** ricerca, immettere **Segnala phishing** e quindi fare clic su **Cerca** ![ icona ](../../media/search-icon.png) Ricerca.</span><span class="sxs-lookup"><span data-stu-id="40a77-209">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="40a77-210">Nell'elenco dei risultati, individuare **Segnala phishing** e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="40a77-210">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="40a77-211">Nella finestra di dialogo visualizzata esaminare le informazioni sulla licenza e sulla privacy e quindi fare clic su **Continua.**</span><span class="sxs-lookup"><span data-stu-id="40a77-211">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="40a77-212">Nella pagina **Configura componente aggiuntivo visualizzata** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a77-212">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="40a77-213">**Utenti assegnati**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a77-213">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="40a77-214">**Tutti** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="40a77-214">**Everyone** (default)</span></span>
     - <span data-ttu-id="40a77-215">**Utenti/gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="40a77-215">**Specific users / groups**</span></span>
     - <span data-ttu-id="40a77-216">**Solo io**</span><span class="sxs-lookup"><span data-stu-id="40a77-216">**Just me**</span></span>

   - <span data-ttu-id="40a77-217">**Metodo di distribuzione:** selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a77-217">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="40a77-218">**Risolto (impostazione predefinita):** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non può essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="40a77-218">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="40a77-219">**Disponibile**: gli utenti possono installare il componente aggiuntivo in **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="40a77-219">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="40a77-220">**Facoltativo:** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma può scegliere di rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="40a77-220">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="40a77-221">Al termine, fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="40a77-221">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="40a77-222">Nella pagina **Distribuisci phishing** report visualizzata verrà visualizzato un rapporto sullo stato seguito da una conferma della distribuzione del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="40a77-222">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="40a77-223">Dopo aver letto le informazioni, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="40a77-223">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="40a77-224">Nella pagina **Annuncia componente aggiuntivo visualizzata** esaminare le informazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="40a77-224">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="40a77-225">Rivedere o modificare le impostazioni per il componente aggiuntivo Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="40a77-225">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="40a77-226">Nell'Microsoft 365 di amministrazione passare alla pagina Impostazioni  componenti \> **aggiuntivi** all'indirizzo <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="40a77-226">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="40a77-227">Se la pagina del  componente aggiuntivo non è  visualizzata, passare al collegamento componenti aggiuntivi Impostazioni app integrate nella parte superiore della pagina \>  \>  **App** integrate.</span><span class="sxs-lookup"><span data-stu-id="40a77-227">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="40a77-228">Individuare e selezionare il **componente aggiuntivo Segnala** phishing.</span><span class="sxs-lookup"><span data-stu-id="40a77-228">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="40a77-229">Nel riquadro **a comparsa Modifica rapporto Phishing** visualizzato, esaminare e modificare le impostazioni in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40a77-229">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="40a77-230">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="40a77-230">When you're finished, click **Save**.</span></span>
