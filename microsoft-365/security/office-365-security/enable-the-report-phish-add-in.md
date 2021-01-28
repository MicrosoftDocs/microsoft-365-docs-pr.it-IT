---
title: Abilitare il componente aggiuntivo phishing report
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
description: Informazioni su come abilitare il componente aggiuntivo per il phishing dei report per Outlook e Outlook sul Web, per singoli utenti o per l'intera organizzazione.
ms.openlocfilehash: 6d86fdc710539bc3c74eb94f8931ca48a0c992c1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029139"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="60e39-103">Abilitare il componente aggiuntivo Segnala phishing</span><span class="sxs-lookup"><span data-stu-id="60e39-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="60e39-104">Se si è un amministratore in un'organizzazione di Microsoft 365 con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="60e39-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="60e39-105">Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="60e39-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="60e39-106">I componenti aggiuntivi per il report e i report di phishing per Outlook e Outlook sul Web (in precedenza noti come Outlook Web App) consentono agli utenti di segnalare facilmente i falsi positivi (messaggi di posta elettronica validi contrassegnati come negativi) o falsi negativi (messaggi di posta elettronica non consentiti) a Microsoft e ai suoi affiliati per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="60e39-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="60e39-107">Microsoft utilizza questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="60e39-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="60e39-108">Si supponga, ad esempio, che le persone stiano segnalando numerosi messaggi utilizzando il componente aggiuntivo di phishing dei report.</span><span class="sxs-lookup"><span data-stu-id="60e39-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="60e39-109">Queste informazioni si riferiscono al [dashboard di sicurezza](security-dashboard.md) e ad altri report.</span><span class="sxs-lookup"><span data-stu-id="60e39-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="60e39-110">Il team di sicurezza dell'organizzazione può utilizzare queste informazioni per indicare che potrebbe essere necessario aggiornare i criteri di protezione anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="60e39-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="60e39-111">È possibile installare il messaggio di report o il componente aggiuntivo di phishing del report.</span><span class="sxs-lookup"><span data-stu-id="60e39-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="60e39-112">Se si desidera che gli utenti riportino messaggi di posta indesiderata e di phishing, distribuire il componente aggiuntivo per i messaggi di report nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="60e39-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="60e39-113">Per ulteriori informazioni, vedere [Enable the report Message Add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="60e39-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="60e39-114">Il componente aggiuntivo per il phishing dei report consente di segnalare solo i messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="60e39-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="60e39-115">Gli amministratori possono abilitare il componente aggiuntivo per il phishing dei rapporti per l'organizzazione e i singoli utenti possono installarlo personalmente.</span><span class="sxs-lookup"><span data-stu-id="60e39-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="60e39-116">Se si è un singolo utente, è possibile [abilitare il componente aggiuntivo per il phishing dei report](#get-the-report-phishing-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="60e39-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="60e39-117">Se si è un amministratore globale o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile [abilitare il componente aggiuntivo per il phishing dei rapporti per l'organizzazione](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="60e39-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="60e39-118">Il Add-In di phishing dei report è ora disponibile tramite la [distribuzione centralizzata](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="60e39-118">The Report Phishing Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="60e39-119">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="60e39-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="60e39-120">Il componente aggiuntivo di phishing dei rapporti è compatibile con la maggior parte delle sottoscrizioni Microsoft 365 e i prodotti seguenti:</span><span class="sxs-lookup"><span data-stu-id="60e39-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="60e39-121">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="60e39-121">Outlook on the web</span></span>
  - <span data-ttu-id="60e39-122">Outlook 2013 SP1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="60e39-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="60e39-123">Outlook 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="60e39-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="60e39-124">Outlook incluso con Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="60e39-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="60e39-125">Il componente aggiuntivo di phishing dei report non è disponibile per le cassette postali nelle organizzazioni Exchange locali.</span><span class="sxs-lookup"><span data-stu-id="60e39-125">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="60e39-126">È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="60e39-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="60e39-127">Per ulteriori informazioni, vedere [criteri degli invii degli utenti](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="60e39-127">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="60e39-128">Il Web browser esistente dovrebbe funzionare con il componente aggiuntivo di phishing dei report.</span><span class="sxs-lookup"><span data-stu-id="60e39-128">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="60e39-129">Tuttavia, se si nota che il componente aggiuntivo non è disponibile o non funziona come previsto, provare con un altro browser.</span><span class="sxs-lookup"><span data-stu-id="60e39-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="60e39-130">Per le installazioni organizzative, l'organizzazione deve essere configurata per l'utilizzo dell'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="60e39-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="60e39-131">Per ulteriori informazioni, vedere [determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="60e39-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="60e39-132">Gli amministratori devono essere membri del gruppo di ruoli Global Admins.</span><span class="sxs-lookup"><span data-stu-id="60e39-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="60e39-133">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="60e39-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="60e39-134">Ottenere il componente aggiuntivo di phishing del rapporto per se stessi</span><span class="sxs-lookup"><span data-stu-id="60e39-134">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="60e39-135">Accedere a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> e cercare il componente aggiuntivo di phishing del report.</span><span class="sxs-lookup"><span data-stu-id="60e39-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="60e39-136">Fare clic su **Ottieni subito**.</span><span class="sxs-lookup"><span data-stu-id="60e39-136">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="60e39-137">Nella finestra di dialogo che viene visualizzata, esaminare le condizioni di utilizzo e i criteri di privacy, quindi fare clic su **continua**.</span><span class="sxs-lookup"><span data-stu-id="60e39-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="60e39-138">Accedere con l'account aziendale o dell'Istituto di istruzione (per uso commerciale) o con il proprio account Microsoft (per uso personale).</span><span class="sxs-lookup"><span data-stu-id="60e39-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="60e39-139">Dopo aver installato e abilitato il componente aggiuntivo, vengono visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="60e39-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="60e39-140">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="60e39-140">In Outlook, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo per il phishing dei rapporti per Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="60e39-142">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="60e39-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo di phishing del rapporto di Outlook sul Web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="60e39-144">Ottenere e attivare il componente aggiuntivo per il phishing dei rapporti per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="60e39-144">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="60e39-145">La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.</span><span class="sxs-lookup"><span data-stu-id="60e39-145">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="60e39-146">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina Vai alla pagina dei componenti aggiuntivi per le **Impostazioni** , \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> se la pagina del **componente aggiuntivo** non è visualizzata, passare al collegamento **Impostazioni** \> componenti aggiuntivi delle **app integrate** \>  nella parte superiore della pagina delle **app integrate** .</span><span class="sxs-lookup"><span data-stu-id="60e39-146">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="60e39-147">Selezionare **Distribuisci componente aggiuntivo nella** parte superiore della pagina e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="60e39-147">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="60e39-149">Nel riquadro a comparsa **Distribuisci un nuovo componente aggiuntivo** che viene visualizzato, esaminare le informazioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="60e39-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="60e39-150">Nella pagina successiva fare clic su **Scegli nell'archivio**.</span><span class="sxs-lookup"><span data-stu-id="60e39-150">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="60e39-152">Nella pagina **Seleziona componente aggiuntivo** visualizzata, fare clic nella casella di **ricerca** , immettere il **rapporto di phishing** e quindi fare clic su icona ricerca ricerca  ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="60e39-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="60e39-153">Nell'elenco dei risultati, trovare il **rapporto di phishing** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="60e39-153">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="60e39-154">Nella finestra di dialogo che viene visualizzata, esaminare la gestione delle licenze e le informazioni sulla privacy, quindi fare clic su **continua**.</span><span class="sxs-lookup"><span data-stu-id="60e39-154">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="60e39-155">Nella pagina **Configura componente aggiuntivo** che viene visualizzata, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="60e39-155">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="60e39-156">**Utenti assegnati**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="60e39-156">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="60e39-157">**Tutti** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="60e39-157">**Everyone** (default)</span></span>
     - <span data-ttu-id="60e39-158">**Utenti/gruppi specifici**</span><span class="sxs-lookup"><span data-stu-id="60e39-158">**Specific users / groups**</span></span>
     - <span data-ttu-id="60e39-159">**Solo io**</span><span class="sxs-lookup"><span data-stu-id="60e39-159">**Just me**</span></span>

   - <span data-ttu-id="60e39-160">**Metodo di distribuzione**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="60e39-160">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="60e39-161">**Fixed (impostazione predefinita)**: il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non è possibile rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="60e39-161">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="60e39-162">**Disponibile**: gli utenti possono installare il componente aggiuntivo in **casa** per \> **ottenere i componenti** aggiuntivi gestiti dall' \> **amministratore**.</span><span class="sxs-lookup"><span data-stu-id="60e39-162">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="60e39-163">**Facoltativo**: il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma è possibile sceglierlo per rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="60e39-163">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="60e39-164">Al termine, fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="60e39-164">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="60e39-165">Nella pagina **Distribuisci rapporto di phishing** che viene visualizzata, verrà visualizzato un rapporto sullo stato seguito da una conferma che il componente aggiuntivo è stato distribuito.</span><span class="sxs-lookup"><span data-stu-id="60e39-165">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="60e39-166">Dopo aver letto le informazioni, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="60e39-166">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="60e39-167">Nella pagina del **componente aggiuntivo annunciare** che viene visualizzata, esaminare le informazioni e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="60e39-167">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="60e39-168">Informazioni su come utilizzare il componente aggiuntivo per il phishing dei report</span><span class="sxs-lookup"><span data-stu-id="60e39-168">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="60e39-169">Gli utenti a cui è assegnato il componente aggiuntivo vedranno le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="60e39-169">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="60e39-170">In Outlook l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="60e39-170">In Outlook, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo per il phishing dei rapporti per Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="60e39-172">In Outlook sul Web, l'icona è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="60e39-172">In Outlook on the web, the icon looks like this:</span></span>

  ![Icona del componente aggiuntivo di phishing del rapporto di Outlook sul Web](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="60e39-174">Esaminare o modificare le impostazioni per il componente aggiuntivo di phishing dei report</span><span class="sxs-lookup"><span data-stu-id="60e39-174">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="60e39-175">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina Vai alla pagina dei componenti aggiuntivi per le **Impostazioni** , \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> se la pagina del **componente aggiuntivo** non è visualizzata, passare al collegamento **Impostazioni** \> componenti aggiuntivi delle **app integrate** \>  nella parte superiore della pagina delle **app integrate** .</span><span class="sxs-lookup"><span data-stu-id="60e39-175">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="60e39-176">Individuare e selezionare il componente aggiuntivo per il **phishing dei report** .</span><span class="sxs-lookup"><span data-stu-id="60e39-176">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="60e39-177">Nel riquadro a comparsa del **rapporto di modifica** che viene visualizzato, esaminare e modificare le impostazioni appropriate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="60e39-177">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="60e39-178">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="60e39-178">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="60e39-179">Visualizzazione e revisione dei messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="60e39-179">View and review reported messages</span></span>

<span data-ttu-id="60e39-180">Per esaminare i messaggi che gli utenti riferiscono a Microsoft, sono disponibili le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="60e39-180">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="60e39-181">Utilizzare il portale degli invii di amministratore.</span><span class="sxs-lookup"><span data-stu-id="60e39-181">Use the Admin Submissions portal.</span></span> <span data-ttu-id="60e39-182">Per ulteriori informazioni, vedere [visualizzare gli invii degli utenti a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="60e39-182">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="60e39-183">Creare una regola del flusso di posta (nota anche come regola di trasporto) per inviare copie dei messaggi segnalati.</span><span class="sxs-lookup"><span data-stu-id="60e39-183">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="60e39-184">Per istruzioni, vedere [utilizzo delle regole del flusso di posta per vedere cosa gli utenti stanno segnalando a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="60e39-184">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>