---
title: Segnalare posta indesiderata e phishing in Outlook sul Web
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
description: Gli amministratori possono conoscere le opzioni di segnalazione della posta indesiderata, non della posta indesiderata e di phishing incorporate in Outlook sul Web (Outlook Web App) in Exchange Online e su come disabilitare queste opzioni di segnalazione per gli utenti.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0bd2da9b774b3557ebb820102ba86c17ebe44c69
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289222"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="bc857-103">Segnalare posta indesiderata e phishing in Outlook sul Web in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bc857-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bc857-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="bc857-104">**Applies to**</span></span>
- [<span data-ttu-id="bc857-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bc857-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bc857-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="bc857-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="bc857-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc857-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="bc857-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online, è possibile utilizzare le opzioni di creazione di report predefinite in Outlook sul Web (in precedenza noto come Outlook Web App) per inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="bc857-108">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bc857-109">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="bc857-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bc857-110">Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, si consiglia di utilizzare il portale Invii nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="bc857-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="bc857-111">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="bc857-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="bc857-112">Gli amministratori possono disabilitare o abilitare la possibilità per gli utenti di segnalare messaggi a Microsoft in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="bc857-112">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="bc857-113">Per informazioni dettagliate, vedere la sezione Disabilitare o abilitare [la segnalazione della](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) posta indesiderata in Outlook sul Web più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="bc857-113">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="bc857-114">È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="bc857-114">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="bc857-115">Per altre informazioni, vedi [Criteri di invio degli utenti.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="bc857-115">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="bc857-116">Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="bc857-116">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="bc857-117">Segnalare messaggi di posta indesiderata e di phishing in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="bc857-117">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="bc857-118">Per i messaggi nella Cartella Posta in arrivo o in qualsiasi altra cartella di posta elettronica ad eccezione della posta indesiderata, utilizzare uno dei metodi seguenti per segnalare messaggi di posta indesiderata e di phishing:</span><span class="sxs-lookup"><span data-stu-id="bc857-118">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="bc857-119">Selezionare il messaggio, fare clic **su Posta** indesiderata sulla barra degli strumenti e quindi selezionare **Posta indesiderata** o **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="bc857-119">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Segnalare posta indesiderata o phishing dalla barra multifunzione](../../media/owa-report-junk.png)

   - <span data-ttu-id="bc857-121">Selezionare uno o più messaggi, fare clic con il pulsante destro del mouse e scegliere **Segna come posta indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="bc857-121">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="bc857-122">Nella finestra di dialogo visualizzata fare clic su **Report.**</span><span class="sxs-lookup"><span data-stu-id="bc857-122">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="bc857-123">Se si cambia idea, fare clic **su Non segnalare.**</span><span class="sxs-lookup"><span data-stu-id="bc857-123">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="bc857-124">Posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="bc857-124">Junk</span></span>|<span data-ttu-id="bc857-125">Phishing</span><span class="sxs-lookup"><span data-stu-id="bc857-125">Phishing</span></span>|
   |:---:|:---:|
   |![Segnala come finestra di dialogo posta indesiderata](../../media/owa-report-as-junk-dialog.png)|![Finestra di dialogo Segnala come phishing](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="bc857-128">I messaggi selezionati verranno inviati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="bc857-128">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="bc857-129">Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="bc857-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="bc857-130">Segnalare messaggi non di posta indesiderata e di phishing dalla cartella Posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="bc857-130">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="bc857-131">Nella cartella Posta indesiderata, utilizzare uno dei metodi seguenti per segnalare falsi positivi o messaggi di phishing della posta indesiderata:</span><span class="sxs-lookup"><span data-stu-id="bc857-131">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="bc857-132">Selezionare il messaggio, fare **clic su Non indesiderato** sulla barra degli strumenti e quindi selezionare **Non indesiderato** o **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="bc857-132">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Segnalare messaggi di posta elettronica non indesiderati o non di phishing dalla barra multifunzione](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="bc857-134">Selezionare uno o più messaggi, fare clic con il pulsante destro del mouse e scegliere **Segna come non indesiderato.**</span><span class="sxs-lookup"><span data-stu-id="bc857-134">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="bc857-135">Nella finestra di dialogo visualizzata leggere le informazioni e fare clic su **Report.**</span><span class="sxs-lookup"><span data-stu-id="bc857-135">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="bc857-136">Se si cambia idea, fare clic **su Non segnalare.**</span><span class="sxs-lookup"><span data-stu-id="bc857-136">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="bc857-137">Non indesiderato</span><span class="sxs-lookup"><span data-stu-id="bc857-137">Not Junk</span></span>|<span data-ttu-id="bc857-138">Phishing</span><span class="sxs-lookup"><span data-stu-id="bc857-138">Phishing</span></span>|
   |:---:|:---:|
   |![Segnala come non indesiderato finestra di dialogo](../../media/owa-report-as-not-junk-dialog.png)|![Finestra di dialogo Segnala come phishing](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="bc857-141">I messaggi selezionati verranno inviati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="bc857-141">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="bc857-142">Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="bc857-142">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="bc857-143">Disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="bc857-143">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="bc857-144">Per impostazione predefinita, gli utenti possono segnalare falsi positivi, falsi negativi e messaggi di phishing a Microsoft per l'analisi in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="bc857-144">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="bc857-145">Gli amministratori possono configurare i criteri cassetta postale di Outlook sul Web in PowerShell di Exchange Online per impedire agli utenti di segnalare falsi positivi e falsi negativi della posta indesiderata a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc857-145">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="bc857-146">Non è possibile disabilitare la possibilità per gli utenti di segnalare messaggi di phishing a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc857-146">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bc857-147">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="bc857-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bc857-148">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="bc857-148">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="bc857-149">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bc857-149">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="bc857-150">In particolare, sono necessari i ruoli **Criteri** destinatario o Destinatari **di** posta, assegnati ai gruppi di ruoli Gestione organizzazione e **Gestione** destinatari per impostazione predefinita. </span><span class="sxs-lookup"><span data-stu-id="bc857-150">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="bc857-151">Per ulteriori informazioni sui gruppi di ruoli in Exchange Online, vedere [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) e Modificare i gruppi di ruoli in Exchange [Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="bc857-151">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="bc857-152">Ogni organizzazione dispone di un criterio predefinito denominato OwaMailboxPolicy-Default, ma è possibile creare criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="bc857-152">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="bc857-153">I criteri personalizzati vengono applicati agli utenti con ambito prima del criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="bc857-153">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="bc857-154">Per ulteriori informazioni sui criteri cassetta postale di Outlook sul Web, vedere Criteri cassetta postale di Outlook sul [Web in Exchange Online.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="bc857-154">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="bc857-155">La disabilitazione della segnalazione della posta indesiderata non rimuove la possibilità di contrassegnare un messaggio come indesiderato o non indesiderato in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="bc857-155">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="bc857-156">Se si seleziona un messaggio  nella cartella Posta indesiderata e si fa clic su Non indesiderato, il messaggio viene comunque spostato \>  di nuovo nella cartella Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="bc857-156">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="bc857-157">Se si seleziona un messaggio  in qualsiasi altra cartella di posta elettronica e si fa clic su Posta indesiderata, il messaggio viene comunque spostato \>  nella cartella Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="bc857-157">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="bc857-158">Ciò che non è più disponibile è l'opzione per segnalare il messaggio a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc857-158">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="bc857-159">Utilizzare PowerShell di Exchange Online per disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="bc857-159">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="bc857-160">Per trovare i criteri cassetta postale di Outlook sul Web esistenti e lo stato della segnalazione della posta indesiderata, eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="bc857-160">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="bc857-161">Per disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="bc857-161">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="bc857-162">In questo esempio viene disabilitata la segnalazione della posta indesiderata nel criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="bc857-162">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="bc857-163">In questo esempio viene abilitata la segnalazione della posta indesiderata nel criterio personalizzato denominato Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="bc857-163">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="bc857-164">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) e [Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="bc857-164">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bc857-165">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="bc857-165">How do you know this worked?</span></span>

<span data-ttu-id="bc857-166">Per verificare che la segnalazione della posta indesiderata in Outlook sul Web sia stata abilitata o disabilitata correttamente, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc857-166">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="bc857-167">In PowerShell di Exchange Online, eseguire il comando seguente e verificare il valore della proprietà **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="bc857-167">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="bc857-168">Aprire la cassetta postale di un utente interessato in Outlook sul  Web, selezionare un messaggio nella Posta in arrivo, fare clic su Posta indesiderata e verificare che la richiesta di segnalare il messaggio a Microsoft sia o non sia \>  visualizzata.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bc857-168">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="bc857-169">Aprire la cassetta postale di un utente interessato in Outlook sul Web, selezionare un messaggio nella cartella Posta indesiderata, fare clic su Posta indesiderata e verificare che la richiesta di segnalare il messaggio a Microsoft sia o non sia  \>  visualizzata.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bc857-169">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="bc857-170"><sup>\*</sup> Gli utenti possono nascondere la richiesta di segnalare il messaggio pur segnalando il messaggio.</span><span class="sxs-lookup"><span data-stu-id="bc857-170"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="bc857-171">Per controllare questa impostazione in Outlook sul Web:</span><span class="sxs-lookup"><span data-stu-id="bc857-171">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="bc857-172">Fare **clic su Impostazioni** Icona Impostazioni outlook sul Web Visualizza tutte le impostazioni di ![ ](../../media/owa-settings-icon.png) \> **Outlook** Posta \> **indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="bc857-172">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="bc857-173">Nella sezione **Report** verificare il valore: **Chiedi conferma prima di inviare un report.**</span><span class="sxs-lookup"><span data-stu-id="bc857-173">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Impostazioni per la segnalazione della posta indesiderata di Outlook sul Web](../../media/owa-junk-email-reporting-options.png)
