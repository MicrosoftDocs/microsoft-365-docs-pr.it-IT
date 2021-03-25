---
title: Installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Informazioni su come installare e utilizzare il componente aggiuntivo Segnalazione posta indesiderata Microsoft per segnalare messaggi di posta indesiderata, non indesiderata e phishing a Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e120ceec355ffc135e00e13a89a0f29085946a3b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205465"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="7b16d-103">Installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="7b16d-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7b16d-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="7b16d-104">**Applies to**</span></span>
- [<span data-ttu-id="7b16d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7b16d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7b16d-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="7b16d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7b16d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b16d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="7b16d-108">Se al momento non si utilizza il componente aggiuntivo Per [](enable-the-report-message-add-in.md) la segnalazione della posta indesiderata, è consigliabile utilizzare il componente aggiuntivo Segnala messaggio o Segnala [phishing.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="7b16d-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="7b16d-109">Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7b16d-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="7b16d-110">Il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook consente agli utenti di inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7b16d-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="7b16d-111">Se l'organizzazione non utilizza Exchange Online Protection (ad esempio, exchange locale o servizi di posta elettronica diversi da Exchange Online), l'invio del rapporto di posta indesiderata non influisce sul filtro della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7b16d-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="7b16d-112">In questo argomento viene illustrato come installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7b16d-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7b16d-113">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7b16d-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7b16d-114">Per installare il componente aggiuntivo per la segnalazione della posta indesiderata, vedere la sezione [Installare il](#install-the-junk-email-reporting-add-in) componente aggiuntivo per la segnalazione della posta indesiderata più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="7b16d-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="7b16d-115">Il componente aggiuntivo Per la segnalazione della posta indesiderata funziona con le versioni seguenti di Outlook:</span><span class="sxs-lookup"><span data-stu-id="7b16d-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="7b16d-116">Outlook 2013 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="7b16d-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="7b16d-117">Outlook incluso in Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="7b16d-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="7b16d-118">Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7b16d-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="7b16d-119">Utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per segnalare messaggi di posta indesiderata e phishing</span><span class="sxs-lookup"><span data-stu-id="7b16d-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="7b16d-120">Per i messaggi nella cartella Posta in arrivo o in qualsiasi altra cartella di posta elettronica ad eccezione della posta indesiderata, utilizzare uno dei metodi seguenti per segnalare messaggi di posta indesiderata e phishing:</span><span class="sxs-lookup"><span data-stu-id="7b16d-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="7b16d-121">Selezionare il messaggio o aprire il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7b16d-121">Select the message or open the message.</span></span> <span data-ttu-id="7b16d-122">Nella scheda **Home o** **Messaggio** della barra multifunzione fare clic **su** Posta indesiderata e quindi **selezionare** Segnala come posta indesiderata o Segnala come **phishing.**</span><span class="sxs-lookup"><span data-stu-id="7b16d-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Segnalare posta indesiderata o phishing dalla barra multifunzione](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="7b16d-124">Fai clic con il pulsante destro del mouse sul messaggio, **seleziona** Posta indesiderata e quindi segnala come posta **indesiderata** **o Segnala come phishing.**</span><span class="sxs-lookup"><span data-stu-id="7b16d-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Segnalare posta indesiderata o phishing dal clic con il pulsante destro del mouse](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="7b16d-126">Selezionare più messaggi, fare clic con il pulsante destro del mouse e **quindi** scegliere Segnala come posta indesiderata o Segnala **come phishing**.</span><span class="sxs-lookup"><span data-stu-id="7b16d-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Segnalare più messaggi di posta indesiderata o phishing da clic con il pulsante destro del mouse](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="7b16d-128">Nella finestra di dialogo visualizzata, leggere le informazioni e fare clic su **Report.**</span><span class="sxs-lookup"><span data-stu-id="7b16d-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="7b16d-129">Se si cambia idea, fare clic **su Non segnalare**.</span><span class="sxs-lookup"><span data-stu-id="7b16d-129">If you change your mind, click **Don't Report**.</span></span>

   ![Segnala come finestra di dialogo posta indesiderata](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Finestra di dialogo Segnala come phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="7b16d-132">I messaggi selezionati verranno inviati a Microsoft per l'analisi e:</span><span class="sxs-lookup"><span data-stu-id="7b16d-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="7b16d-133">Spostato nella cartella Posta indesiderata se è stato segnalato come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7b16d-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="7b16d-134">Eliminato se è stato segnalato come phishing.</span><span class="sxs-lookup"><span data-stu-id="7b16d-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="7b16d-135">Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="7b16d-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="7b16d-136">Utilizzare il componente aggiuntivo Per la segnalazione della posta indesiderata per segnalare messaggi non di posta indesiderata e phishing dalla cartella Posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="7b16d-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="7b16d-137">Nella cartella Posta indesiderata utilizzare uno dei metodi seguenti per segnalare falsi positivi o messaggi di phishing di posta indesiderata:</span><span class="sxs-lookup"><span data-stu-id="7b16d-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="7b16d-138">Selezionare il messaggio o aprire il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7b16d-138">Select the message or open the message.</span></span> <span data-ttu-id="7b16d-139">Nella scheda **Home o** **Messaggio** della barra multifunzione fare clic **su** Non posta indesiderata e quindi **selezionare** Segnala come non indesiderato o Segnala come **phishing.**</span><span class="sxs-lookup"><span data-stu-id="7b16d-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Segnalare messaggi di posta elettronica non indesiderati o di phishing dalla barra multifunzione nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="7b16d-141">Fai clic con il pulsante destro del mouse sul messaggio, scegli **Posta** indesiderata e quindi seleziona Segnala come non **indesiderato** **o Segnala come phishing.**</span><span class="sxs-lookup"><span data-stu-id="7b16d-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Segnalare messaggi di posta elettronica non indesiderati o di phishing da fare clic con il pulsante destro del mouse nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="7b16d-143">Selezionare più messaggi, fare clic con il pulsante destro del mouse e **quindi** scegliere Segnala come non indesiderato o Segnala **come phishing**.</span><span class="sxs-lookup"><span data-stu-id="7b16d-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Segnalare più messaggi di posta elettronica non indesiderati o di phishing da fare clic con il pulsante destro del mouse nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="7b16d-145">Nella finestra di dialogo visualizzata, leggere le informazioni e fare clic su **Report.**</span><span class="sxs-lookup"><span data-stu-id="7b16d-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="7b16d-146">Se si cambia idea, fare clic **su Non segnalare**.</span><span class="sxs-lookup"><span data-stu-id="7b16d-146">If you change your mind, click **Don't Report**.</span></span>

   ![Segnala come non indesiderato finestra di dialogo](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Finestra di dialogo Segnala come phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="7b16d-149">I messaggi selezionati verranno inviati a Microsoft per l'analisi e:</span><span class="sxs-lookup"><span data-stu-id="7b16d-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="7b16d-150">Spostato nella cartella Posta indesiderata se è stato segnalato come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7b16d-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="7b16d-151">Eliminato se è stato segnalato come phishing.</span><span class="sxs-lookup"><span data-stu-id="7b16d-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="7b16d-152">Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.</span><span class="sxs-lookup"><span data-stu-id="7b16d-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="7b16d-153">Installare il componente aggiuntivo per la segnalazione della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="7b16d-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="7b16d-154">È necessario disporre dei privilegi di amministratore nel computer in cui si sta installando il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="7b16d-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="7b16d-155">Passare a e scaricare il file MSI appropriato per la versione di Office in un percorso facile <https://www.microsoft.com/download/details.aspx?id=18275> da trovare:</span><span class="sxs-lookup"><span data-stu-id="7b16d-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="7b16d-156">**32 bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7b16d-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="7b16d-157">**64 bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7b16d-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="7b16d-158">Per Outlook 2013 o versioni successive, l'unico prerequisito è Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="7b16d-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="7b16d-159">In Windows 10 non installi la versione .NET Framework 2.0 da un download.</span><span class="sxs-lookup"><span data-stu-id="7b16d-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="7b16d-160">Installare il componente aggiuntivo per la segnalazione della posta indesiderata tramite l'installazione guidata</span><span class="sxs-lookup"><span data-stu-id="7b16d-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="7b16d-161">Chiudere Outlook nel proprio computer.</span><span class="sxs-lookup"><span data-stu-id="7b16d-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="7b16d-162">In Windows 10, verificare che la .NET Framework 2.0 sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="7b16d-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="7b16d-163">Per istruzioni, vedere [Enable the .NET Framework 3.5 nel Pannello di controllo.](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)</span><span class="sxs-lookup"><span data-stu-id="7b16d-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="7b16d-164">Individuare il file MSI scaricato e fare doppio clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="7b16d-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="7b16d-165">Nella pagina **Installazione del componente aggiuntivo per la segnalazione della posta indesiderata** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7b16d-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="7b16d-166">Rivedere il contratto di licenza, fare clic su Accetto i termini del Contratto di **Licenza** se si accettano le condizioni e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7b16d-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="7b16d-167">Al termine della procedura guidata, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7b16d-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="7b16d-168">Avviare Outlook.</span><span class="sxs-lookup"><span data-stu-id="7b16d-168">Start Outlook.</span></span>

<span data-ttu-id="7b16d-p109">Cerare il pulsante **Posta indesiderata** sulla barra multifunzione di Outlook. A questo punto sarà possibile segnalare i messaggi di posta indesiderata a Microsoft, selezionandoli nella Posta in arrivo e facendo clic sul pulsante **Segnala posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="7b16d-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="7b16d-p110">Scegliere la freccia in giù accanto a **Posta indesiderata** per visualizzare altre opzioni, ad esempio **Segnala come phishing** per segnalare tentativi di phishing a Microsoft. Nella cartella della posta indesiderata, è inoltre possibile selezionare **Segnala come attendibile** se un messaggio di posta elettronica è stato identificato erroneamente come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7b16d-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="7b16d-173">Installazione del componente aggiuntivo di report di posta indesiderata in modalità invisibile</span><span class="sxs-lookup"><span data-stu-id="7b16d-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="7b16d-174">Chiudere Outlook nel proprio computer.</span><span class="sxs-lookup"><span data-stu-id="7b16d-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="7b16d-175">In Windows 10 installa il .NET Framework 2.0 eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7b16d-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="7b16d-176">Per installare il componente aggiuntivo senza alcuna interazione dell'utente, aprire un prompt dei comandi e utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="7b16d-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="7b16d-177">`MaxMessageSelection` specifica il numero massimo di messaggi che è possibile selezionare per un singolo invio.</span><span class="sxs-lookup"><span data-stu-id="7b16d-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="7b16d-178">I valori validi sono da 1 a 50.</span><span class="sxs-lookup"><span data-stu-id="7b16d-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="7b16d-179">Il valore predefinito è 15.</span><span class="sxs-lookup"><span data-stu-id="7b16d-179">The default value is 15.</span></span>

   - <span data-ttu-id="7b16d-180">`BccEmailAddress` specifica altri destinatari Ccn che riceveranno una copia di tutti gli invii degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7b16d-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="7b16d-181">Il valore predefinito è vuoto (nessun destinatario Ccn aggiuntivo).</span><span class="sxs-lookup"><span data-stu-id="7b16d-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="7b16d-182">In questo esempio viene installata la versione a 64 bit del componente aggiuntivo dal percorso specificato con le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="7b16d-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="7b16d-183">In questo esempio viene installata la versione a 32 bit del componente aggiuntivo dal percorso specificato con le impostazioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b16d-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="7b16d-184">È possibile selezionare fino a 20 messaggi in un singolo invio.</span><span class="sxs-lookup"><span data-stu-id="7b16d-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="7b16d-185">junkreports@contoso.com e hollyd@treyresearch.net ricevere copie Ccn di tutti gli invii.</span><span class="sxs-lookup"><span data-stu-id="7b16d-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7b16d-186">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="7b16d-186">How do you know this worked?</span></span>

<span data-ttu-id="7b16d-187">Per verificare di aver installato correttamente il componente aggiuntivo per la segnalazione della posta indesiderata, eseguire una delle operazioni seguenti in Outlook:</span><span class="sxs-lookup"><span data-stu-id="7b16d-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="7b16d-188">Selezionare il messaggio o aprire il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7b16d-188">Select the message or open the message.</span></span> <span data-ttu-id="7b16d-189">Nella scheda **Home** o **Messaggio** della barra multifunzione fare clic **su** Posta indesiderata e verificare che siano disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b16d-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7b16d-190">**Segnala come posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7b16d-190">**Report as Junk**</span></span>
  - <span data-ttu-id="7b16d-191">**Segnala come phishing**</span><span class="sxs-lookup"><span data-stu-id="7b16d-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="7b16d-192">**Opzioni di segnalazione della posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7b16d-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="7b16d-193">**Segnalare la Guida in linea per la posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7b16d-193">**Report Junk Online Help**</span></span>

  ![Segnalare posta indesiderata o phishing dalla barra multifunzione](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="7b16d-195">Fare clic con il pulsante destro del mouse sul messaggio, **selezionare** Posta indesiderata e verificare che siano disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b16d-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7b16d-196">**Segnala come posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7b16d-196">**Report as Junk**</span></span>
  - <span data-ttu-id="7b16d-197">**Segnala come phishing**</span><span class="sxs-lookup"><span data-stu-id="7b16d-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="7b16d-198">**Opzioni di segnalazione della posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7b16d-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="7b16d-199">**Segnalare la Guida in linea per la posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7b16d-199">**Report Junk Online Help**</span></span>

  ![Segnalare posta indesiderata o phishing dal clic con il pulsante destro del mouse](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="7b16d-201">Selezionare più messaggi, fare clic con il pulsante destro del mouse e verificare che siano disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b16d-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7b16d-202">**Segnala come posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7b16d-202">**Report as Junk**</span></span>
  - <span data-ttu-id="7b16d-203">**Segnala come phishing**</span><span class="sxs-lookup"><span data-stu-id="7b16d-203">**Report as Phishing**</span></span>

  ![Segnalare più messaggi di posta indesiderata o phishing da clic con il pulsante destro del mouse](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="7b16d-205">Eseguire le azioni precedenti nella **cartella Posta** indesiderata e verificare che le **opzioni** di segnalazione della posta indesiderata precedenti siano ora Non **posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="7b16d-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Segnalare messaggi di posta elettronica non indesiderati o di phishing dalla barra multifunzione nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Segnalare messaggi di posta elettronica non indesiderati o di phishing da fare clic con il pulsante destro del mouse nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Segnalare più messaggi di posta elettronica non indesiderati o di phishing da fare clic con il pulsante destro del mouse nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="7b16d-209">Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="7b16d-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="7b16d-210">Dopo aver chiuso Outlook, utilizzare una delle procedure seguenti per disinstallare il componente aggiuntivo per la segnalazione della posta indesiderata:</span><span class="sxs-lookup"><span data-stu-id="7b16d-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="7b16d-211">**Pannello di** controllo : premere il tasto Windows + R. Nella finestra **di dialogo** Esegui visualizzata immettere e quindi fare clic `control appwiz.cpl` su **OK.**</span><span class="sxs-lookup"><span data-stu-id="7b16d-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="7b16d-212">Individuare e selezionare Il componente aggiuntivo per la **segnalazione** della posta indesiderata Microsoft nell'elenco e quindi fare clic su **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="7b16d-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="7b16d-213">**Pacchetto di Windows Installer:** trovare o scaricare il file MSI appropriato e fare doppio clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="7b16d-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="7b16d-214">**32 bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7b16d-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="7b16d-215">**64 bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7b16d-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="7b16d-216">Nella finestra di dialogo visualizzata selezionare **Rimuovi componente aggiuntivo** per la segnalazione della posta indesiderata microsoft per Outlook e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="7b16d-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="7b16d-217">**Modalità invisibile** all'utente : trova o scarica il file MSI appropriato.</span><span class="sxs-lookup"><span data-stu-id="7b16d-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="7b16d-218">In una finestra del prompt dei comandi sostituire \<PathToFile\> con il percorso del file msi ed eseguire uno dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b16d-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="7b16d-219">**32 bit**:</span><span class="sxs-lookup"><span data-stu-id="7b16d-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="7b16d-220">**64 bit**:</span><span class="sxs-lookup"><span data-stu-id="7b16d-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="7b16d-221">Quando si apre Outlook dopo la disinstallazione, le opzioni di segnalazione della posta indesiderata, non della posta indesiderata e di phishing dovrebbero essere finite.</span><span class="sxs-lookup"><span data-stu-id="7b16d-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="7b16d-222">Risoluzione dei problemi relativi al componente aggiuntivo per la segnalazione della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="7b16d-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="7b16d-223">In alcuni casi, potrebbero verificarsi problemi con Outlook dopo l'aggiunta del componente aggiuntivo per la segnalazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7b16d-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="7b16d-224">In questa sezione vengono descritti i problemi che possono verificarsi, insieme ai suggerimenti per la risoluzione di questi problemi.</span><span class="sxs-lookup"><span data-stu-id="7b16d-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="7b16d-225">Risoluzione dei problemi per gli utenti</span><span class="sxs-lookup"><span data-stu-id="7b16d-225">Troubleshooting for users</span></span>

<span data-ttu-id="7b16d-226">Si verificano uno o più dei seguenti problemi:</span><span class="sxs-lookup"><span data-stu-id="7b16d-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="7b16d-227">Non accade nulla quando si fa clic su **Segnala posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="7b16d-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="7b16d-228">Outlook si blocca dopo la selezione di un messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7b16d-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="7b16d-229">La posta indesiderata segnalata non viene recapitata perché "non recapitabile"</span><span class="sxs-lookup"><span data-stu-id="7b16d-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="7b16d-230">Per risolvere il problema, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="7b16d-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="7b16d-231">Chiudere e riavviare Outlook.</span><span class="sxs-lookup"><span data-stu-id="7b16d-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="7b16d-232">Creare e inviare un messaggio di prova e verificare che il destinatario lo ha ricevuto.</span><span class="sxs-lookup"><span data-stu-id="7b16d-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="7b16d-233">Se il problema persiste, contattare l'amministratore.</span><span class="sxs-lookup"><span data-stu-id="7b16d-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="7b16d-234">Per altri metodi che è possibile utilizzare per inviare messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7b16d-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="7b16d-235">Risoluzione dei problemi per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="7b16d-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="7b16d-236">Problema: viene visualizzato continuamente un messaggio di errore che chiede agli utenti di contattare l'amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="7b16d-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="7b16d-237">Verificare o impostare la chiave `LoggingLevel` del Registro di sistema sul valore "Verbose":</span><span class="sxs-lookup"><span data-stu-id="7b16d-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="7b16d-238">**Outlook a 32 bit in Windows a 32 bit**:</span><span class="sxs-lookup"><span data-stu-id="7b16d-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="7b16d-239">**Outlook a 32 bit in Windows a 64 bit**:</span><span class="sxs-lookup"><span data-stu-id="7b16d-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="7b16d-240">**Outlook a 64 bit**:</span><span class="sxs-lookup"><span data-stu-id="7b16d-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="7b16d-241">Riavviare Outlook e chiedere agli utenti di segnalare quando viene visualizzato il messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="7b16d-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="7b16d-242">Raccogliere i registri nei percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b16d-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="7b16d-243">Contattare il supporto tecnico di Exchange Online Protection per fornire i registri.</span><span class="sxs-lookup"><span data-stu-id="7b16d-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="7b16d-244">Problema: gli utenti hanno selezionato di non ricevere una richiesta di conferma quando segnalano i messaggi e ora desiderano che la richiesta venga nuovamente visualizzata</span><span class="sxs-lookup"><span data-stu-id="7b16d-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="7b16d-245">Creare la `ConfirmReportJunk` chiave del Registro di sistema con il valore "True":</span><span class="sxs-lookup"><span data-stu-id="7b16d-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="7b16d-246">Riavviare Outlook.</span><span class="sxs-lookup"><span data-stu-id="7b16d-246">Restart Outlook.</span></span>