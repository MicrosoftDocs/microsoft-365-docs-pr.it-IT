---
title: Installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Informazioni su come installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata di Microsoft per segnalare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft.
ms.openlocfilehash: be087a15071114b2d1ec564cbb118dcd85e32429
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638501"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook-in-office-365"></a><span data-ttu-id="7ebac-103">Installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook in Office 365</span><span class="sxs-lookup"><span data-stu-id="7ebac-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="7ebac-104">Se attualmente non si utilizza il componente aggiuntivo per la segnalazione della posta indesiderata, è consigliabile utilizzare il [componente aggiuntivo per i messaggi di report](enable-the-report-message-add-in.md) .</span><span class="sxs-lookup"><span data-stu-id="7ebac-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span>

<span data-ttu-id="7ebac-105">Il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook consente agli utenti di inviare falsi positivi (posta elettronica buona contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="7ebac-105">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span> <span data-ttu-id="7ebac-106">Se l'organizzazione non utilizza EOP, l'invio del rapporto di posta indesiderata non influirà sul filtro della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7ebac-106">If your organization doesn't use EOP, your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="7ebac-107">In questo argomento viene descritto come installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7ebac-107">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7ebac-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7ebac-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7ebac-109">Per installare il componente aggiuntivo per la segnalazione della posta indesiderata, vedere la sezione [installazione del componente aggiuntivo per la segnalazione della posta indesiderata](#install-the-junk-email-reporting-add-in) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7ebac-109">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="7ebac-110">Il componente aggiuntivo per la segnalazione della posta indesiderata è compatibile con le seguenti versioni di Outlook:</span><span class="sxs-lookup"><span data-stu-id="7ebac-110">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="7ebac-111">Outlook 2013 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="7ebac-111">Outlook 2013 or later</span></span>
  - <span data-ttu-id="7ebac-112">Outlook incluso con Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="7ebac-112">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="7ebac-113">Per ulteriori informazioni sul reporting dei messaggi a Microsoft, vedere [segnalare i messaggi e i file a Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7ebac-113">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="7ebac-114">Utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per segnalare messaggi di posta indesiderata e phishing</span><span class="sxs-lookup"><span data-stu-id="7ebac-114">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="7ebac-115">Per i messaggi nella cartella posta in arrivo o in altre cartelle di posta elettronica, ad eccezione della posta indesiderata, utilizzare uno dei metodi seguenti per segnalare messaggi di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="7ebac-115">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="7ebac-116">Selezionare il messaggio o aprire il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7ebac-116">Select the message or open the message.</span></span> <span data-ttu-id="7ebac-117">Nella scheda **Home** o **Message** della barra multifunzione fare clic su **posta indesiderata**e quindi selezionare **segnala come posta indesiderata** o **segnala come phishing**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-117">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Segnalare messaggi di posta indesiderata o di phishing dalla barra multifunzione](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="7ebac-119">Fare clic con il pulsante destro del mouse sul messaggio, selezionare **indesiderato**e quindi selezionare **segnala come posta indesiderata** o **segnala come phishing**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-119">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Segnalare messaggi di posta indesiderata o di phishing dal pulsante destro del mouse](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="7ebac-121">Selezionare più messaggi, fare clic con il pulsante destro del mouse e quindi scegliere **segnala come posta indesiderata** o **segnala come phishing**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-121">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Segnalare più messaggi di posta indesiderata o di phishing tramite il pulsante destro del mouse](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="7ebac-123">Nella finestra di dialogo che viene visualizzata, leggere le informazioni e fare clic su **segnala**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-123">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="7ebac-124">Se si cambia idea, fare clic su **non segnalare**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-124">If you change your mind, click **Don't Report**.</span></span>

   ![Segnala come finestra di dialogo indesiderata](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Segnala come finestra di dialogo di phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="7ebac-p104">I messaggi selezionati saranno inviati a Microsoft per l'analisi e spostati nella cartella Posta indesiderata. Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="7ebac-p104">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="7ebac-129">Utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per segnalare messaggi non di posta indesiderata e di phishing dalla cartella posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="7ebac-129">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="7ebac-130">Nella cartella posta indesiderata, utilizzare uno dei metodi seguenti per segnalare messaggi di posta indesiderata falsi positivi o di phishing:</span><span class="sxs-lookup"><span data-stu-id="7ebac-130">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="7ebac-131">Selezionare il messaggio o aprire il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7ebac-131">Select the message or open the message.</span></span> <span data-ttu-id="7ebac-132">Nella scheda **Home** o **Message** della barra multifunzione fare clic su **non indesiderata**e quindi selezionare **segnala come non indesiderato** o **segnala come phishing**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-132">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Segnalare messaggi di posta indesiderata o di phishing dalla barra multifunzione nella cartella posta indesiderata](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="7ebac-134">Fai clic con il pulsante destro del mouse sul messaggio, fai clic su **posta indesiderata**e quindi seleziona **segnala come non indesiderato** o **segnala come phishing**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-134">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Segnala la posta elettronica non indesiderata o di phishing dal pulsante destro del mouse nella cartella posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="7ebac-136">Seleziona più messaggi, fai clic con il pulsante destro del mouse e quindi seleziona **segnala come non indesiderato** o **segnala come phishing**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-136">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Segnalare più messaggi di posta elettronica non indesiderati o di phishing dal pulsante destro del mouse nella cartella posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="7ebac-138">Nella finestra di dialogo che viene visualizzata, leggere le informazioni e fare clic su **segnala**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-138">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="7ebac-139">Se si cambia idea, fare clic su **non segnalare**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-139">If you change your mind, click **Don't Report**.</span></span>

   ![Segnala come finestra di dialogo non indesiderata](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Segnala come finestra di dialogo di phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="7ebac-p107">I messaggi selezionati saranno inviati a Microsoft per l'analisi e spostati nella cartella Posta indesiderata. Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="7ebac-p107">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="7ebac-144">Installare il componente aggiuntivo per la segnalazione della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="7ebac-144">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="7ebac-145">È necessario disporre dei privilegi di amministratore nel computer in cui si sta installando il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="7ebac-145">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="7ebac-146">Andare a <https://www.microsoft.com/download/details.aspx?id=18275> e scaricare il file. msi appropriato per la versione di Office in un percorso facile da trovare:</span><span class="sxs-lookup"><span data-stu-id="7ebac-146">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="7ebac-147">**32 bit**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7ebac-147">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="7ebac-148">**64 bit**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7ebac-148">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="7ebac-149">Per Outlook 2013 o versione successiva, l'unico prerequisito è Microsoft .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="7ebac-149">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="7ebac-150">In Windows 10 non è possibile installare .NET Framework 2,0 da un download.</span><span class="sxs-lookup"><span data-stu-id="7ebac-150">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="7ebac-151">Installazione del componente aggiuntivo per la segnalazione della posta indesiderata tramite l'installazione guidata</span><span class="sxs-lookup"><span data-stu-id="7ebac-151">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="7ebac-152">Chiudere Outlook nel proprio computer.</span><span class="sxs-lookup"><span data-stu-id="7ebac-152">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="7ebac-153">In Windows 10, verificare che .NET Framework 2,0 sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="7ebac-153">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="7ebac-154">Per istruzioni, vedere [Enable the .NET Framework 3,5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="7ebac-154">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="7ebac-155">Individuare il file con estensione msi scaricato e fare doppio clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="7ebac-155">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="7ebac-156">Nella pagina **Installazione del componente aggiuntivo per la segnalazione della posta indesiderata** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-156">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="7ebac-157">Esaminare il contratto di licenza, fare clic su **Accetto i termini del contratto di licenza** se si accettano i termini e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-157">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="7ebac-158">Al termine della procedura guidata, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-158">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="7ebac-159">Avviare Outlook.</span><span class="sxs-lookup"><span data-stu-id="7ebac-159">Start Outlook.</span></span>

<span data-ttu-id="7ebac-p110">Cerare il pulsante **Posta indesiderata** sulla barra multifunzione di Outlook. A questo punto sarà possibile segnalare i messaggi di posta indesiderata a Microsoft, selezionandoli nella Posta in arrivo e facendo clic sul pulsante **Segnala posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-p110">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="7ebac-p111">Scegliere la freccia in giù accanto a **Posta indesiderata** per visualizzare altre opzioni, ad esempio **Segnala come phishing** per segnalare tentativi di phishing a Microsoft. Nella cartella della posta indesiderata, è inoltre possibile selezionare **Segnala come attendibile** se un messaggio di posta elettronica è stato identificato erroneamente come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7ebac-p111">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="7ebac-164">Installazione del componente aggiuntivo di report di posta indesiderata in modalità invisibile</span><span class="sxs-lookup"><span data-stu-id="7ebac-164">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="7ebac-165">Chiudere Outlook nel proprio computer.</span><span class="sxs-lookup"><span data-stu-id="7ebac-165">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="7ebac-166">In Windows 10, installare .NET Framework 2,0 eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7ebac-166">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="7ebac-167">Per installare il componente aggiuntivo senza interazione dell'utente, aprire un prompt dei comandi e utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="7ebac-167">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="7ebac-168">`MaxMessageSelection`Specifica il numero massimo di messaggi che è possibile selezionare per un singolo invio.</span><span class="sxs-lookup"><span data-stu-id="7ebac-168">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="7ebac-169">I valori validi sono compresi tra 1 e 50.</span><span class="sxs-lookup"><span data-stu-id="7ebac-169">Valid values are from 1 to 50.</span></span> <span data-ttu-id="7ebac-170">Il valore predefinito è 15.</span><span class="sxs-lookup"><span data-stu-id="7ebac-170">The default value is 15.</span></span>

   - <span data-ttu-id="7ebac-171">`BccEmailAddress`Specifica i destinatari Ccn aggiuntivi che riceveranno una copia di tutti gli invii degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7ebac-171">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="7ebac-172">Il valore predefinito è vuoto (nessun destinatario Ccn aggiuntivo).</span><span class="sxs-lookup"><span data-stu-id="7ebac-172">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="7ebac-173">In questo esempio viene installata la versione a 64 bit del componente aggiuntivo dal percorso specificato con le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="7ebac-173">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="7ebac-174">In questo esempio viene installata la versione a 32 bit del componente aggiuntivo dal percorso specificato con le seguenti impostazioni aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="7ebac-174">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="7ebac-175">Un massimo di 20 messaggi può essere selezionato in un singolo invio.</span><span class="sxs-lookup"><span data-stu-id="7ebac-175">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="7ebac-176">junkreports@contoso.com e hollyd@treyresearch.net ricevono copie BCC di tutti gli invii.</span><span class="sxs-lookup"><span data-stu-id="7ebac-176">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7ebac-177">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="7ebac-177">How do you know this worked?</span></span>

<span data-ttu-id="7ebac-178">Per verificare che il componente aggiuntivo per la segnalazione della posta indesiderata sia stato installato correttamente, eseguire una delle operazioni seguenti in Outlook:</span><span class="sxs-lookup"><span data-stu-id="7ebac-178">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="7ebac-179">Selezionare il messaggio o aprire il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7ebac-179">Select the message or open the message.</span></span> <span data-ttu-id="7ebac-180">Nella scheda **Home** o **Message** della barra multifunzione fare clic su **posta indesiderata**e verificare che siano disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ebac-180">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7ebac-181">**Segnala come posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7ebac-181">**Report as Junk**</span></span>
  - <span data-ttu-id="7ebac-182">**Segnala come phishing**</span><span class="sxs-lookup"><span data-stu-id="7ebac-182">**Report as Phishing**</span></span>
  - <span data-ttu-id="7ebac-183">**Opzioni di segnalazione della posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7ebac-183">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="7ebac-184">**Segnalare la Guida in linea di indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7ebac-184">**Report Junk Online Help**</span></span>

  ![Segnalare messaggi di posta indesiderata o di phishing dalla barra multifunzione](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="7ebac-186">Fare clic con il pulsante destro del mouse sul messaggio, selezionare **indesiderato**e verificare che siano disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ebac-186">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7ebac-187">**Segnala come posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7ebac-187">**Report as Junk**</span></span>
  - <span data-ttu-id="7ebac-188">**Segnala come phishing**</span><span class="sxs-lookup"><span data-stu-id="7ebac-188">**Report as Phishing**</span></span>
  - <span data-ttu-id="7ebac-189">**Opzioni di segnalazione della posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7ebac-189">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="7ebac-190">**Segnalare la Guida in linea di indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7ebac-190">**Report Junk Online Help**</span></span>

  ![Segnalare messaggi di posta indesiderata o di phishing dal pulsante destro del mouse](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="7ebac-192">Selezionare più messaggi, fare clic con il pulsante destro del mouse e verificare che siano disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ebac-192">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7ebac-193">**Segnala come posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7ebac-193">**Report as Junk**</span></span>
  - <span data-ttu-id="7ebac-194">**Segnala come phishing**</span><span class="sxs-lookup"><span data-stu-id="7ebac-194">**Report as Phishing**</span></span>

  ![Segnalare più messaggi di posta indesiderata o di phishing tramite il pulsante destro del mouse](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="7ebac-196">Eseguire le azioni precedenti nella cartella **posta indesiderata** e verificare che le opzioni precedenti per i report di **posta** indesiderata **non siano indesiderate**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-196">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Segnalare messaggi di posta indesiderata o di phishing dalla barra multifunzione nella cartella posta indesiderata](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Segnala la posta elettronica non indesiderata o di phishing dal pulsante destro del mouse nella cartella posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Segnalare più messaggi di posta elettronica non indesiderati o di phishing dal pulsante destro del mouse nella cartella posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="7ebac-200">Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="7ebac-200">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="7ebac-201">Dopo aver chiuso Outlook, utilizzare una delle procedure seguenti per disinstallare il componente aggiuntivo per la segnalazione della posta indesiderata:</span><span class="sxs-lookup"><span data-stu-id="7ebac-201">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="7ebac-202">**Pannello di controllo**: premere il tasto Windows + R. Nella finestra di dialogo **Esegui** che viene visualizzata `control appwiz.cpl` , immettere e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-202">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="7ebac-203">Individuare e selezionare il **componente aggiuntivo per la segnalazione della posta indesiderata di Microsoft** nell'elenco e quindi fare clic su **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-203">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="7ebac-204">**Pacchetto di Windows Installer**: trovare o scaricare il file. msi appropriato e fare doppio clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="7ebac-204">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="7ebac-205">**32 bit**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7ebac-205">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="7ebac-206">**64 bit**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7ebac-206">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="7ebac-207">Nella finestra di dialogo visualizzata, selezionare **Rimuovi componente aggiuntivo per la segnalazione della posta indesiderata di Microsoft per Outlook** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7ebac-207">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="7ebac-208">**Modalità invisibile all'utente**: trovare o scaricare il file. msi appropriato.</span><span class="sxs-lookup"><span data-stu-id="7ebac-208">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="7ebac-209">In una finestra del prompt dei comandi \<,\> sostituire parametro PathToFile con il percorso del file con estensione msi ed eseguire uno dei seguenti comandi:</span><span class="sxs-lookup"><span data-stu-id="7ebac-209">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="7ebac-210">**32 bit**:</span><span class="sxs-lookup"><span data-stu-id="7ebac-210">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="7ebac-211">**64 bit**:</span><span class="sxs-lookup"><span data-stu-id="7ebac-211">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="7ebac-212">Quando si apre Outlook dopo la disinstallazione, la posta indesiderata, non la posta indesiderata e le opzioni di phishing devono essere scomparse.</span><span class="sxs-lookup"><span data-stu-id="7ebac-212">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="7ebac-213">Risoluzione dei problemi relativi al componente aggiuntivo per la segnalazione della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="7ebac-213">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="7ebac-214">In alcuni casi, potrebbe verificarsi un problema con Outlook dopo l'aggiunta del componente aggiuntivo per la segnalazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7ebac-214">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="7ebac-215">In questa sezione vengono descritti i problemi che potrebbero verificarsi, insieme ai suggerimenti per risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="7ebac-215">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="7ebac-216">Risoluzione dei problemi per gli utenti</span><span class="sxs-lookup"><span data-stu-id="7ebac-216">Troubleshooting for users</span></span>

<span data-ttu-id="7ebac-217">È possibile riscontrare uno o più dei problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ebac-217">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="7ebac-218">Non accade nulla quando si fa clic su **Segnala posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7ebac-218">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="7ebac-219">Outlook si blocca dopo la selezione di un messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7ebac-219">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="7ebac-220">La posta indesiderata segnalata non viene recapitata perché "non recapitabile"</span><span class="sxs-lookup"><span data-stu-id="7ebac-220">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="7ebac-221">Per risolvere il problema, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ebac-221">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="7ebac-222">Chiudere e riavviare Outlook.</span><span class="sxs-lookup"><span data-stu-id="7ebac-222">Close and restart Outlook.</span></span>
2. <span data-ttu-id="7ebac-223">Creare e inviare un messaggio di prova e verificare che il destinatario abbia ricevuto il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7ebac-223">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="7ebac-224">Se il problema persiste, contattare l'amministratore.</span><span class="sxs-lookup"><span data-stu-id="7ebac-224">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="7ebac-225">Per gli altri metodi che è possibile utilizzare per inviare messaggi a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7ebac-225">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="7ebac-226">Risoluzione dei problemi per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="7ebac-226">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="7ebac-227">Problema: viene visualizzato continuamente un messaggio di errore che chiede agli utenti di contattare l'amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="7ebac-227">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="7ebac-228">Verificare o impostare la `LoggingLevel` chiave del registro di sistema sul valore "verbose":</span><span class="sxs-lookup"><span data-stu-id="7ebac-228">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="7ebac-229">**Outlook a 32 bit su Windows a 32 bit**:</span><span class="sxs-lookup"><span data-stu-id="7ebac-229">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="7ebac-230">**Outlook a 32 bit su Windows a 64 bit**:</span><span class="sxs-lookup"><span data-stu-id="7ebac-230">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="7ebac-231">**Outlook a 64 bit**:</span><span class="sxs-lookup"><span data-stu-id="7ebac-231">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="7ebac-232">Riavviare Outlook e chiedere agli utenti di riferire quando visualizzano il messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="7ebac-232">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="7ebac-233">Raccogliere i registri nei percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ebac-233">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="7ebac-234">Contattare il supporto tecnico di Exchange Online Protection per fornire i registri.</span><span class="sxs-lookup"><span data-stu-id="7ebac-234">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="7ebac-235">Problema: gli utenti hanno scelto di non ricevere una richiesta di conferma quando segnalano i messaggi e ora richiedano il prompt.</span><span class="sxs-lookup"><span data-stu-id="7ebac-235">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="7ebac-236">Creare la `ConfirmReportJunk`chiave del registro di sistema wih il valore "true":</span><span class="sxs-lookup"><span data-stu-id="7ebac-236">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="7ebac-237">Riavviare Outlook.</span><span class="sxs-lookup"><span data-stu-id="7ebac-237">Restart Outlook.</span></span>
