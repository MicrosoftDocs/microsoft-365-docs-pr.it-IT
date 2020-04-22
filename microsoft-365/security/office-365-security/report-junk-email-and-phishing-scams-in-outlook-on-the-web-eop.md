---
title: 'Segnalare posta indesiderata e tentativi di phishing in Outlook sul web '
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
description: Microsoft 365 gli utenti con cassette postali di Exchange Online possono utilizzare Outlook sul Web (Outlook Web App) per inviare messaggi di posta indesiderata, non di posta indesiderata e di phishing a Microsoft per l'analisi.
ms.openlocfilehash: 858224074ef7258d59318eef0c685a4ea4f9130f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632620"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="f4ebd-103">Segnalare messaggi di posta indesiderata e di phishing in Outlook sul Web in Office 365</span><span class="sxs-lookup"><span data-stu-id="f4ebd-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="f4ebd-104">Se si è un cliente Microsoft 365 con cassette postali di Exchange Online, è possibile utilizzare le opzioni predefinite per la creazione di report in Outlook sul Web (in precedenza noto come Outlook Web App) per inviare falsi positivi (messaggi di posta elettronica segnalati come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="f4ebd-104">If you're a Microsoft 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f4ebd-105">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f4ebd-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f4ebd-106">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale degli invii nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f4ebd-107">Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="f4ebd-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="f4ebd-108">Gli amministratori possono disabilitare o abilitare la possibilità per gli utenti di segnalare i messaggi a Microsoft in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="f4ebd-109">Per informazioni dettagliate, vedere la sezione [disabilitare o abilitare la creazione di report di posta indesiderata in Outlook sul Web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="f4ebd-110">Per ulteriori informazioni sul reporting dei messaggi a Microsoft, vedere [segnalare i messaggi e i file a Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f4ebd-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="f4ebd-111">Segnalare messaggi di posta indesiderata e di phishing in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="f4ebd-111">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="f4ebd-112">Per i messaggi nella cartella posta in arrivo o in altre cartelle di posta elettronica, ad eccezione della posta indesiderata, utilizzare uno dei metodi seguenti per segnalare messaggi di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="f4ebd-112">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="f4ebd-113">Selezionare il messaggio, fare clic su **posta indesiderata** sulla barra degli strumenti, quindi selezionare **posta indesiderata** o **phishing**.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-113">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Segnalare messaggi di posta indesiderata o di phishing dalla barra multifunzione](../../media/owa-report-junk.png)

   - <span data-ttu-id="f4ebd-115">Selezionare uno o più messaggi, fare clic con il pulsante destro del mouse, quindi selezionare **Segna come posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-115">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="f4ebd-116">Nella finestra di dialogo visualizzata fare clic su **segnala**.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-116">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="f4ebd-117">Se si cambia idea, fare clic su **non segnalare**.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-117">If you change your mind, click **Don't Report**.</span></span>

   ![Segnala come finestra di dialogo indesiderata](../../media/owa-report-as-junk-dialog.png)

   ![Segnala come finestra di dialogo di phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="f4ebd-120">I messaggi selezionati verranno inviati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-120">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="f4ebd-121">Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-121">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="f4ebd-122">Segnalare messaggi non di posta indesiderata e di phishing dalla cartella posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="f4ebd-122">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="f4ebd-123">Nella cartella posta indesiderata, utilizzare uno dei metodi seguenti per segnalare la posta indesiderata o i messaggi di phishing:</span><span class="sxs-lookup"><span data-stu-id="f4ebd-123">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="f4ebd-124">Selezionare il messaggio, fare clic su **non indesiderato** sulla barra degli strumenti, quindi selezionare **non indesiderato** o **phishing**.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-124">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Segnalare messaggi di posta indesiderata o di phishing dalla barra multifunzione](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="f4ebd-126">Selezionare uno o più messaggi, fare clic con il pulsante destro del mouse, quindi selezionare **Segna come non indesiderato**.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-126">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="f4ebd-127">Nella finestra di dialogo che viene visualizzata, leggere le informazioni e fare clic su **segnala**.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-127">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="f4ebd-128">Se si cambia idea, fare clic su **non segnalare**.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-128">If you change your mind, click **Don't Report**.</span></span>

   ![Segnala come finestra di dialogo non indesiderata](../../media/owa-report-as-not-junk-dialog.png)

   ![Segnala come finestra di dialogo di phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="f4ebd-131">I messaggi selezionati verranno inviati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-131">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="f4ebd-132">Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-132">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="f4ebd-133">Disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="f4ebd-133">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="f4ebd-134">Per impostazione predefinita, gli utenti possono segnalare messaggi di posta indesiderata falsi positivi, falsi negativi e phishing a Microsoft per l'analisi in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-134">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="f4ebd-135">Gli amministratori possono configurare i criteri cassetta postale di Outlook sul Web in Exchange Online PowerShell per impedire agli utenti di segnalare la posta indesiderata falsi positivi e falsi negativi di posta indesiderata a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-135">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="f4ebd-136">Non è possibile disabilitare la possibilità per gli utenti di segnalare i messaggi di phishing a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-136">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f4ebd-137">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f4ebd-137">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f4ebd-138">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f4ebd-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f4ebd-139">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-139">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="f4ebd-140">In particolare, è necessario che i **criteri destinatario** o i **destinatari di posta elettronica** in Exchange Online, assegnati ai gruppi di ruoli Gestione **organizzazione** **e destinatari** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-140">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="f4ebd-141">Per ulteriori informazioni sui gruppi di ruoli in Exchange Online, vedere [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="f4ebd-141">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="f4ebd-142">Ogni organizzazione ha un criterio predefinito denominato OwaMailboxPolicy-Default, ma è possibile creare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-142">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="f4ebd-143">I criteri personalizzati vengono applicati agli utenti con ambito prima del criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-143">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="f4ebd-144">Per ulteriori informazioni sui criteri cassetta postale di Outlook sul Web, vedere [criteri cassetta postale di Outlook sul Web in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="f4ebd-144">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="f4ebd-145">La disattivazione della segnalazione della posta indesiderata non rimuove la possibilità di contrassegnare un messaggio come posta indesiderata o non indesiderata in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-145">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="f4ebd-146">Selezionando un messaggio nella cartella posta indesiderata e facendo clic su **non** \> **indesiderata** , il messaggio viene spostato di nuovo nella posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-146">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="f4ebd-147">Selezionando un messaggio in qualsiasi altra cartella di posta elettronica **e facendo clic su** \> posta indesiderata, il messaggio viene spostato nella cartella posta indesiderata. **Junk**</span><span class="sxs-lookup"><span data-stu-id="f4ebd-147">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="f4ebd-148">Ciò che non è più disponibile è l'opzione per segnalare il messaggio a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-148">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="f4ebd-149">Utilizzo di PowerShell di Exchange Online per disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="f4ebd-149">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="f4ebd-150">Per trovare i criteri cassetta postale di Outlook sul Web e lo stato della segnalazione della posta indesiderata, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="f4ebd-150">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="f4ebd-151">Per disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f4ebd-151">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="f4ebd-152">In questo esempio viene disabilitata la segnalazione della posta indesiderata nel criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-152">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="f4ebd-153">In questo esempio viene abilitata la segnalazione della posta indesiderata nel criterio personalizzato denominato contoso managers.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-153">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="f4ebd-154">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) e [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="f4ebd-154">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f4ebd-155">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="f4ebd-155">How do you know this worked?</span></span>

<span data-ttu-id="f4ebd-156">Per verificare la corretta abilitazione o disabilitazione della creazione di report di posta indesiderata in Outlook sul Web, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4ebd-156">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="f4ebd-157">In PowerShell di Exchange Online, eseguire il comando riportato di seguito e verificare il valore della proprietà **ReportJunkEmailEnabled** :</span><span class="sxs-lookup"><span data-stu-id="f4ebd-157">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="f4ebd-158">Aprire una cassetta postale di un utente in questione in Outlook sul Web, selezionare un messaggio nella posta in arrivo **, fare clic** \> **su posta** indesiderata e verificare che la richiesta di segnalazione del messaggio a Microsoft sia o non sia visualizzata.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4ebd-158">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="f4ebd-159">Aprire una cassetta postale di un utente in questione in Outlook sul Web, selezionare un messaggio nella cartella posta indesiderata **, fare clic su** \> posta indesiderata **e verificare** che la richiesta di segnalazione del messaggio a Microsoft sia o non sia visualizzata.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4ebd-159">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="f4ebd-160"><sup>\*</sup>Gli utenti possono nascondere il prompt per segnalare il messaggio mentre segnalano il messaggio.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-160"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="f4ebd-161">Per controllare questa impostazione in Outlook sul Web:</span><span class="sxs-lookup"><span data-stu-id="f4ebd-161">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="f4ebd-162">Fare clic su **Impostazioni** ![di Outlook sull'icona](../../media/owa-settings-icon.png) \> impostazioni Web **Visualizza tutte le impostazioni** \> di **posta indesiderata**di Outlook.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-162">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="f4ebd-163">Nella sezione **report** verificare il valore: Chiedi a **me prima di inviare un rapporto**.</span><span class="sxs-lookup"><span data-stu-id="f4ebd-163">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Impostazioni di segnalazione della posta indesiderata di Outlook sul Web](../../media/owa-junk-email-reporting-options.png)
