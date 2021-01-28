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
description: Informazioni su come abilitare il componente aggiuntivo per i messaggi di report per Outlook e Outlook sul Web, per singoli utenti o per l'intera organizzazione.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1f8cffaa6346ec7f426da3c862014ed85a9a367
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029233"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="e4da2-103">Abilitare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="e4da2-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="e4da2-104">Se si è un amministratore in un'organizzazione di Microsoft 365 con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="e4da2-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="e4da2-105">Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e4da2-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="e4da2-106">Il messaggio di report e i componenti aggiuntivi di phishing dei report per Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) consentono agli utenti di segnalare facilmente falsi positivi (buona posta elettronica contrassegnata come difettosa) o falsi negativi (messaggi di posta elettronica non consentiti) a Microsoft e ai suoi affiliati per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="e4da2-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="e4da2-107">Microsoft utilizza questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e4da2-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="e4da2-108">Ad esempio, se gli utenti segnalano numerosi messaggi che sono stati contrassegnati come posta indesiderata come non indesiderata utilizzando il componente aggiuntivo segnala messaggio, il team di sicurezza dell'organizzazione potrebbe dover regolare i criteri di protezione da [posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e4da2-108">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="e4da2-109">È possibile installare il messaggio di report o il componente aggiuntivo di phishing del report.</span><span class="sxs-lookup"><span data-stu-id="e4da2-109">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="e4da2-110">Se si desidera che gli utenti riportino solo i messaggi di phishing, distribuire il componente aggiuntivo per il phishing dei report nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4da2-110">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="e4da2-111">Per ulteriori informazioni, vedere [Enable the report phishing Add-in](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="e4da2-111">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="e4da2-112">Il componente aggiuntivo segnala messaggio fornisce la possibilità di segnalare sia messaggi di posta indesiderata che di phishing.</span><span class="sxs-lookup"><span data-stu-id="e4da2-112">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="e4da2-113">Gli amministratori possono abilitare il componente aggiuntivo per i messaggi di report per l'organizzazione e i singoli utenti possono installarli personalmente.</span><span class="sxs-lookup"><span data-stu-id="e4da2-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="e4da2-114">Se si è un singolo utente, è possibile [abilitare il componente aggiuntivo per i messaggi di report](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="e4da2-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="e4da2-115">Se si è un amministratore globale o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile [abilitare il componente aggiuntivo per i messaggi di report per l'organizzazione](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="e4da2-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="e4da2-116">La Add-In del messaggio di report è ora disponibile tramite la [distribuzione centralizzata](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="e4da2-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e4da2-117">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e4da2-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e4da2-118">Il componente aggiuntivo segnala messaggio è compatibile con la maggior parte delle sottoscrizioni Microsoft 365 e i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4da2-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="e4da2-119">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="e4da2-119">Outlook on the web</span></span>
  - <span data-ttu-id="e4da2-120">Outlook 2013 SP1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="e4da2-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="e4da2-121">Outlook 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="e4da2-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="e4da2-122">Outlook incluso con Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="e4da2-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="e4da2-123">Il componente aggiuntivo per i messaggi di report non è disponibile per le cassette postali nelle organizzazioni Exchange locali.</span><span class="sxs-lookup"><span data-stu-id="e4da2-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="e4da2-124">È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="e4da2-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="e4da2-125">Per ulteriori informazioni, vedere [criteri degli invii degli utenti](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e4da2-125">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="e4da2-126">Il Web browser esistente dovrebbe funzionare con il componente aggiuntivo per i messaggi di report.</span><span class="sxs-lookup"><span data-stu-id="e4da2-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="e4da2-127">Tuttavia, se si nota che il componente aggiuntivo non è disponibile o non funziona come previsto, provare con un altro browser.</span><span class="sxs-lookup"><span data-stu-id="e4da2-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="e4da2-128">Per le installazioni organizzative, l'organizzazione deve essere configurata per l'utilizzo dell'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="e4da2-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="e4da2-129">Per ulteriori informazioni, vedere [determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="e4da2-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="e4da2-130">Gli amministratori devono essere membri del gruppo di ruoli Global Admins.</span><span class="sxs-lookup"><span data-stu-id="e4da2-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="e4da2-131">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e4da2-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="e4da2-132">Ottenere il componente aggiuntivo per i messaggi di report</span><span class="sxs-lookup"><span data-stu-id="e4da2-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="e4da2-133">Accedere a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> e cercare il componente aggiuntivo per i messaggi di report.</span><span class="sxs-lookup"><span data-stu-id="e4da2-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="e4da2-134">Per accedere direttamente al componente aggiuntivo per i messaggi di report, passare a <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="e4da2-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="e4da2-135">Fare clic su **Ottieni subito**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-135">Click **GET IT NOW**.</span></span>

   ![Segnala messaggio-ottienilo subito](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="e4da2-137">Nella finestra di dialogo che viene visualizzata, esaminare le condizioni di utilizzo e i criteri di privacy, quindi fare clic su **continua**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="e4da2-138">Accedere con l'account aziendale o dell'Istituto di istruzione (per uso commerciale) o con il proprio account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="e4da2-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="e4da2-139">Dopo aver installato e abilitato il componente aggiuntivo, vengono visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4da2-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="e4da2-140">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e4da2-140">In Outlook, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo per i messaggi di report per Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="e4da2-142">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e4da2-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo messaggio di Outlook sul Web report](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="e4da2-144">Per informazioni su come utilizzare il componente aggiuntivo, vedere [use the report Message Add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="e4da2-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="e4da2-145">Ottenere e attivare il componente aggiuntivo per i messaggi di report per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e4da2-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="e4da2-146">La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="e4da2-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="e4da2-147">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina Vai alla pagina dei componenti aggiuntivi per le **Impostazioni** , \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> se la pagina del **componente aggiuntivo** non è visualizzata, passare al collegamento **Impostazioni** \> componenti aggiuntivi delle **app integrate** \>  nella parte superiore della pagina delle **app integrate** .</span><span class="sxs-lookup"><span data-stu-id="e4da2-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="e4da2-148">Selezionare **Distribuisci componente aggiuntivo nella** parte superiore della pagina e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="e4da2-150">Nel riquadro a comparsa **Distribuisci un nuovo componente aggiuntivo** che viene visualizzato, esaminare le informazioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="e4da2-151">Nella pagina successiva fare clic su **Scegli nell'archivio**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-151">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="e4da2-153">Nella pagina **Seleziona componente aggiuntivo** visualizzata, fare clic nella casella di **ricerca** , immettere il **messaggio di rapporto** e quindi fare clic su icona ricerca ricerca  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="e4da2-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="e4da2-154">Nell'elenco dei risultati, trovare il **messaggio di rapporto** , quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-154">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Selezionare i risultati di ricerca del componente aggiuntivo](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="e4da2-156">Nella finestra di dialogo che viene visualizzata, esaminare la gestione delle licenze e le informazioni sulla privacy, quindi fare clic su **continua**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-156">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="e4da2-157">Nella pagina **Configura componente aggiuntivo** che viene visualizzata, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="e4da2-157">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e4da2-158">**Utenti assegnati**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4da2-158">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="e4da2-159">**Tutti** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="e4da2-159">**Everyone** (default)</span></span>
     - <span data-ttu-id="e4da2-160">**Utenti/gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="e4da2-160">**Specific users / groups**</span></span>
     - <span data-ttu-id="e4da2-161">**Solo io**</span><span class="sxs-lookup"><span data-stu-id="e4da2-161">**Just me**</span></span>

   - <span data-ttu-id="e4da2-162">**Metodo di distribuzione**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4da2-162">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="e4da2-163">**Fixed (impostazione predefinita)**: il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non è possibile rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="e4da2-163">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="e4da2-164">**Disponibile**: gli utenti possono installare il componente aggiuntivo in **casa** per \> **ottenere i componenti** aggiuntivi gestiti dall' \> **amministratore**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-164">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="e4da2-165">**Facoltativo**: il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma è possibile sceglierlo per rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="e4da2-165">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Configurare la pagina del componente aggiuntivo](../../media/configure-add-in.png)

   <span data-ttu-id="e4da2-167">Al termine, fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-167">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="e4da2-168">Nella pagina **Distribuisci messaggio di report** che viene visualizzata, verrà visualizzato un rapporto sullo stato seguito da una conferma che il componente aggiuntivo è stato distribuito.</span><span class="sxs-lookup"><span data-stu-id="e4da2-168">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="e4da2-169">Dopo aver letto le informazioni, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-169">After you read the information, click **Next**.</span></span>

   ![Pagina di distribuzione del messaggio di report](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="e4da2-171">Nella pagina del **componente aggiuntivo annunciare** che viene visualizzata, esaminare le informazioni e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-171">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Pagina del componente aggiuntivo di avviso](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="e4da2-173">Informazioni su come utilizzare il componente aggiuntivo per i messaggi di report</span><span class="sxs-lookup"><span data-stu-id="e4da2-173">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="e4da2-174">Gli utenti a cui è assegnato il componente aggiuntivo vedranno le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4da2-174">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="e4da2-175">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e4da2-175">In Outlook, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo per i messaggi di report per Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="e4da2-177">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e4da2-177">In Outlook on the web, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo messaggio di Outlook sul Web report](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="e4da2-179">Quando si informa gli utenti sul componente aggiuntivo per i messaggi di report, includere un collegamento per [l'utilizzo del componente aggiuntivo per i messaggi di report](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="e4da2-179">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="e4da2-180">Esaminare o modificare le impostazioni per il componente aggiuntivo per i messaggi di report</span><span class="sxs-lookup"><span data-stu-id="e4da2-180">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="e4da2-181">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina Vai alla pagina dei componenti aggiuntivi per le **Impostazioni** , \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> se la pagina del **componente aggiuntivo** non è visualizzata, passare al collegamento **Impostazioni** \> componenti aggiuntivi delle **app integrate** \>  nella parte superiore della pagina delle **app integrate** .</span><span class="sxs-lookup"><span data-stu-id="e4da2-181">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Pagina Servizi e Add-Ins nella nuova interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="e4da2-183">Individuare e selezionare il componente aggiuntivo per i **messaggi di report** .</span><span class="sxs-lookup"><span data-stu-id="e4da2-183">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="e4da2-184">Nel riquadro a comparsa del **messaggio di modifica** che viene visualizzato, esaminare e modificare le impostazioni appropriate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4da2-184">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="e4da2-185">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e4da2-185">When you're finished, click **Save**.</span></span>

   ![Impostazioni per il componente aggiuntivo per i messaggi di report](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="e4da2-187">Visualizzazione e revisione dei messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="e4da2-187">View and review reported messages</span></span>

<span data-ttu-id="e4da2-188">Per esaminare i messaggi che gli utenti riferiscono a Microsoft, sono disponibili le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="e4da2-188">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="e4da2-189">Utilizzare il portale degli invii di amministratore.</span><span class="sxs-lookup"><span data-stu-id="e4da2-189">Use the Admin Submissions portal.</span></span> <span data-ttu-id="e4da2-190">Per ulteriori informazioni, vedere [visualizzare gli invii degli utenti a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="e4da2-190">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="e4da2-191">Creare una regola del flusso di posta (nota anche come regola di trasporto) per inviare copie dei messaggi segnalati.</span><span class="sxs-lookup"><span data-stu-id="e4da2-191">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="e4da2-192">Per istruzioni, vedere [utilizzo delle regole del flusso di posta per vedere cosa gli utenti stanno segnalando a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="e4da2-192">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
