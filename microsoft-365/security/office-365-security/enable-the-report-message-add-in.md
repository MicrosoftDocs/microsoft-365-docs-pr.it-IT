---
title: Abilitare il componente aggiuntivo Segnala messaggio
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Informazioni su come abilitare il componente aggiuntivo per i messaggi di report per Outlook e Outlook sul Web, per singoli utenti o per l'intera organizzazione.
ms.openlocfilehash: 22ce1c8e8084cb0bcbcb2f9fa4c0c80e1a59bf9c
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939476"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="38150-103">Abilitare il componente aggiuntivo Segnala messaggio</span><span class="sxs-lookup"><span data-stu-id="38150-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="38150-104">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale degli invii nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="38150-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="38150-105">Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="38150-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="38150-106">Il componente aggiuntivo segnala messaggio per Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) consente agli utenti di segnalare facilmente falsi positivi (buona posta elettronica contrassegnata come difettosa) o falsi negativi (messaggi di posta elettronica non consentiti) a Microsoft e ai suoi affiliati per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="38150-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="38150-107">Microsoft utilizza questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="38150-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="38150-108">Si supponga, ad esempio, che le persone riferiscono un gran quantità di messaggi come phishing.</span><span class="sxs-lookup"><span data-stu-id="38150-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="38150-109">Queste informazioni si riferiscono al [dashboard di sicurezza](security-dashboard.md) e ad altri report.</span><span class="sxs-lookup"><span data-stu-id="38150-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="38150-110">Il team di sicurezza dell'organizzazione può utilizzare queste informazioni per indicare che potrebbe essere necessario aggiornare i criteri di protezione anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="38150-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="38150-111">In alternativa, se la gente segnala un gran quantità di messaggi che sono stati contrassegnati come posta indesiderata come non indesiderata utilizzando il componente aggiuntivo segnala messaggio, il team di sicurezza dell'organizzazione potrebbe dover adeguare i criteri di protezione da [posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="38150-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="38150-112">Inoltre, se l'organizzazione utilizza [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) o [Plan 2](office-365-ti.md), il componente aggiuntivo segnala messaggio fornisce al team di sicurezza dell'organizzazione informazioni utili che è possibile utilizzare per esaminare e aggiornare i criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="38150-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="38150-113">Gli amministratori possono abilitare il componente aggiuntivo per i messaggi di report per l'organizzazione e i singoli utenti possono installarli personalmente.</span><span class="sxs-lookup"><span data-stu-id="38150-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="38150-114">Se si è un singolo utente, è possibile [abilitare il componente aggiuntivo per i messaggi di report](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="38150-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="38150-115">Se si è un amministratore globale o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile [abilitare il componente aggiuntivo per i messaggi di report per l'organizzazione](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="38150-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="38150-116">Il componente aggiuntivo segnala messaggio è ora disponibile tramite la [distribuzione centralizzata](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="38150-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="38150-117">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="38150-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="38150-118">Il componente aggiuntivo segnala messaggio è compatibile con la maggior parte delle sottoscrizioni Microsoft 365 e i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="38150-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="38150-119">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="38150-119">Outlook on the web</span></span>
  - <span data-ttu-id="38150-120">Outlook 2013 SP1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="38150-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="38150-121">Outlook 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="38150-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="38150-122">Outlook incluso con Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="38150-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="38150-123">Il componente aggiuntivo per i messaggi di report non è attualmente disponibile per:</span><span class="sxs-lookup"><span data-stu-id="38150-123">The Report Message add-in is currently not available for:</span></span>

  - <span data-ttu-id="38150-124">Cassette postali in organizzazioni di Exchange locali</span><span class="sxs-lookup"><span data-stu-id="38150-124">Mailboxes in on-premises Exchange organizations</span></span>
  - <span data-ttu-id="38150-125">Abbonamenti a GCC, GCC HIGH o DoD</span><span class="sxs-lookup"><span data-stu-id="38150-125">GCC, GCC HIGH, or DoD subscriptions</span></span>

- <span data-ttu-id="38150-126">È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="38150-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="38150-127">Per ulteriori informazioni, vedere [specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing in Office 365](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="38150-127">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Office 365](user-submission.md).</span></span>

- <span data-ttu-id="38150-128">Il Web browser esistente dovrebbe funzionare con il componente aggiuntivo per i messaggi di report.</span><span class="sxs-lookup"><span data-stu-id="38150-128">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="38150-129">Tuttavia, se si nota che il componente aggiuntivo non è disponibile o non funziona come previsto, provare con un altro browser.</span><span class="sxs-lookup"><span data-stu-id="38150-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="38150-130">Per le installazioni organizzative, l'organizzazione deve essere configurata per l'utilizzo dell'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="38150-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="38150-131">Per ulteriori informazioni, vedere [determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="38150-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="38150-132">Gli amministratori devono essere membri del gruppo di ruoli Global Admins.</span><span class="sxs-lookup"><span data-stu-id="38150-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="38150-133">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="38150-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="38150-134">Ottenere il componente aggiuntivo per i messaggi di report</span><span class="sxs-lookup"><span data-stu-id="38150-134">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="38150-135">Accedere a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> e cercare il componente aggiuntivo per i messaggi di report.</span><span class="sxs-lookup"><span data-stu-id="38150-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="38150-136">Per accedere direttamente al componente aggiuntivo per i messaggi di report, passare <https://appsource.microsoft.com/product/office/wa104381180>a.</span><span class="sxs-lookup"><span data-stu-id="38150-136">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="38150-137">Fare clic su **Ottieni subito**.</span><span class="sxs-lookup"><span data-stu-id="38150-137">Click **GET IT NOW**.</span></span>

   ![Segnala messaggio-ottienilo subito](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="38150-139">Nella finestra di dialogo che viene visualizzata, esaminare le condizioni di utilizzo e i criteri di privacy, quindi fare clic su **continua**.</span><span class="sxs-lookup"><span data-stu-id="38150-139">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="38150-140">Accedere con l'account aziendale o dell'Istituto di istruzione (per uso commerciale) o con il proprio account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="38150-140">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="38150-141">Dopo aver installato e abilitato il componente aggiuntivo, vengono visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="38150-141">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="38150-142">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="38150-142">In Outlook, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo per i messaggi di report per Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="38150-144">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="38150-144">In Outlook on the web, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo messaggio di Outlook sul Web report](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="38150-146">Per informazioni su come utilizzare il componente aggiuntivo, vedere [use the report Message Add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="38150-146">To learn how to use the add-in, see [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="38150-147">Ottenere e attivare il componente aggiuntivo per i messaggi di report per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="38150-147">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="38150-148">La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="38150-148">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="38150-149">Nell'interfaccia di amministrazione di Microsoft 365 passare alla <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>pagina **Servizi & componenti** aggiuntivi e quindi fare clic su **Distribuisci componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="38150-149">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="38150-151">Nel riquadro a comparsa **Distribuisci un nuovo componente aggiuntivo** che viene visualizzato, esaminare le informazioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="38150-151">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="38150-152">Nella pagina successiva fare clic su **Scegli nell'archivio**.</span><span class="sxs-lookup"><span data-stu-id="38150-152">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="38150-154">Nella pagina **Seleziona componente aggiuntivo** visualizzata, fare clic nella casella di **ricerca** , immettere il **messaggio di rapporto**e quindi fare clic su ![icona](../../media/search-icon.png) **ricerca ricerca.**</span><span class="sxs-lookup"><span data-stu-id="38150-154">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="38150-155">Nell'elenco dei risultati, trovare il **messaggio di rapporto** , quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="38150-155">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Selezionare i risultati di ricerca del componente aggiuntivo](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="38150-157">Nella finestra di dialogo che viene visualizzata, esaminare la gestione delle licenze e le informazioni sulla privacy, quindi fare clic su **continua**.</span><span class="sxs-lookup"><span data-stu-id="38150-157">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="38150-158">Nella pagina **Configura componente aggiuntivo** che viene visualizzata, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="38150-158">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="38150-159">**Utenti assegnati**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="38150-159">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="38150-160">**Tutti** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="38150-160">**Everyone** (default)</span></span>
     - <span data-ttu-id="38150-161">**Utenti/gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="38150-161">**Specific users / groups**</span></span>
     - <span data-ttu-id="38150-162">**Solo io**</span><span class="sxs-lookup"><span data-stu-id="38150-162">**Just me**</span></span>

   - <span data-ttu-id="38150-163">**Metodo di distribuzione**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="38150-163">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="38150-164">**Fixed (impostazione predefinita)**: il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non è possibile rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="38150-164">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="38150-165">**Disponibile**: gli utenti possono installare il componente aggiuntivo in **casa** \> per **ottenere i componenti** \> aggiuntivi **gestiti dall'amministratore**.</span><span class="sxs-lookup"><span data-stu-id="38150-165">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="38150-166">**Facoltativo**: il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma è possibile sceglierlo per rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="38150-166">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Configurare la pagina del componente aggiuntivo](../../media/configure-add-in.png)

   <span data-ttu-id="38150-168">Al termine, fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="38150-168">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="38150-169">Nella pagina **Distribuisci messaggio di report** che viene visualizzata, verrà visualizzato un rapporto sullo stato seguito da una conferma che il componente aggiuntivo è stato distribuito.</span><span class="sxs-lookup"><span data-stu-id="38150-169">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="38150-170">Dopo aver letto le informazioni, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="38150-170">After you read the information, click **Next**.</span></span>

   ![Pagina di distribuzione del messaggio di report](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="38150-172">Nella pagina del **componente aggiuntivo annunciare** che viene visualizzata, esaminare le informazioni e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="38150-172">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Pagina del componente aggiuntivo di avviso](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="38150-174">Informazioni su come utilizzare il componente aggiuntivo per i messaggi di report</span><span class="sxs-lookup"><span data-stu-id="38150-174">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="38150-175">Gli utenti a cui è assegnato il componente aggiuntivo vedranno le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="38150-175">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="38150-176">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="38150-176">In Outlook, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo per i messaggi di report per Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="38150-178">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="38150-178">In Outlook on the web, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo messaggio di Outlook sul Web report](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="38150-180">Quando si informa gli utenti sul componente aggiuntivo per i messaggi di report, includere un collegamento per [l'utilizzo del componente aggiuntivo per i messaggi di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="38150-180">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="38150-181">Esaminare o modificare le impostazioni per il componente aggiuntivo per i messaggi di report</span><span class="sxs-lookup"><span data-stu-id="38150-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="38150-182">Nell'interfaccia di amministrazione di Microsoft 365, accedere alla pagina **servizi & componenti** aggiuntivi in <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span><span class="sxs-lookup"><span data-stu-id="38150-182">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nella nuova interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="38150-184">Individuare e selezionare il componente aggiuntivo per i **messaggi di report** .</span><span class="sxs-lookup"><span data-stu-id="38150-184">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="38150-185">Nel riquadro a comparsa del **messaggio di modifica** che viene visualizzato, esaminare e modificare le impostazioni appropriate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38150-185">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="38150-186">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="38150-186">When you're finished, click **Save**.</span></span>

   ![Impostazioni per il componente aggiuntivo per i messaggi di report](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="38150-188">Visualizzazione e revisione dei messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="38150-188">View and review reported messages</span></span>

<span data-ttu-id="38150-189">Per esaminare i messaggi che gli utenti riferiscono a Microsoft, sono disponibili le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="38150-189">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="38150-190">Utilizzare il portale degli invii di amministratore.</span><span class="sxs-lookup"><span data-stu-id="38150-190">Use the Admin Submissions portal.</span></span> <span data-ttu-id="38150-191">Per ulteriori informazioni, vedere [visualizzare gli invii degli utenti a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="38150-191">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="38150-192">Creare una regola del flusso di posta (nota anche come regola di trasporto) per inviare copie dei messaggi segnalati.</span><span class="sxs-lookup"><span data-stu-id="38150-192">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="38150-193">Per istruzioni, vedere [utilizzo delle regole del flusso di posta per vedere cosa gli utenti stanno segnalando a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="38150-193">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
