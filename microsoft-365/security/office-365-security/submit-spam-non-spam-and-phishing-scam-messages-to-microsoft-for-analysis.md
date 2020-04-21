---
title: Inviare manualmente messaggi a Microsoft per l'analisi
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: "Gli utenti possono inviare messaggi di posta indesiderata falsi negativi e falsi positivi a Microsoft per l'analisi. "
ms.openlocfilehash: f6dbd808fac54ae273c21773bf8caeabce09b7fb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631242"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="2faf9-103">Inviare manualmente messaggi a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="2faf9-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="2faf9-104">Se si è un amministratore in un'organizzazione di Microsoft 365 con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="2faf9-104">If you're an admin in an Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="2faf9-105">Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="2faf9-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="2faf9-106">Può essere frustrante quando gli utenti dell'organizzazione ricevono messaggi di posta indesiderata o messaggi di phishing nella cartella posta in arrivo o se non ricevono un messaggio di posta elettronica legittimo perché sono contrassegnati come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="2faf9-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="2faf9-107">La correzione dei filtri per la posta indesiderata è sempre più accurata.</span><span class="sxs-lookup"><span data-stu-id="2faf9-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="2faf9-108">L'utente e gli utenti possono aiutare questo processo inviando falsi positivi (buon messaggio di posta elettronica contrassegnato come cattivo), falsi negativi (posta errata consentita) e messaggi di phishing a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="2faf9-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="2faf9-109">A causa dell'elevato volume di invii ricevuti, potrebbe non essere possibile rispondere a tutte le richieste di analisi.</span><span class="sxs-lookup"><span data-stu-id="2faf9-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="2faf9-110">Inviare falsi negativi a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2faf9-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="2faf9-111">Invece di utilizzare le procedure seguenti per segnalare falsi negativi, gli utenti in Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) possono utilizzare il componente aggiuntivo per i messaggi di report per Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="2faf9-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="2faf9-112">Per informazioni su come installare e utilizzare questo strumento, vedere [Enable the report Message Add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="2faf9-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="2faf9-113">Se si riceve un messaggio che passa attraverso il filtro di posta indesiderata che dovrebbe essere stato identificato come posta indesiderata o phishing, è possibile inviare il messaggio ai team di analisi di posta indesiderata di Microsoft e Microsoft Phishing Analysis come appropriato.</span><span class="sxs-lookup"><span data-stu-id="2faf9-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="2faf9-114">Gli analisti rivedranno il messaggio e lo aggiungeranno ai filtri a livello di servizio, se soddisfano i criteri di classificazione.</span><span class="sxs-lookup"><span data-stu-id="2faf9-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="2faf9-115">Creare un nuovo messaggio di posta elettronica vuoto con uno dei destinatari seguenti:</span><span class="sxs-lookup"><span data-stu-id="2faf9-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="2faf9-116">**Posta indesiderata**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="2faf9-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="2faf9-117">**Phishing**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="2faf9-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="2faf9-118">Trascinare e rilasciare il messaggio di posta indesiderata o di phishing nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="2faf9-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="2faf9-119">In questo modo verrà salvato il messaggio di posta indesiderata o di phishing come allegato nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="2faf9-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="2faf9-120">Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale, in modo da poter ispezionare le intestazioni del messaggio).</span><span class="sxs-lookup"><span data-stu-id="2faf9-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="2faf9-121">È possibile allegare più messaggi nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="2faf9-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="2faf9-122">Assicurarsi che tutti i messaggi siano dello stesso tipo: messaggi di truffa di phishing o messaggi di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="2faf9-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="2faf9-123">Lasciare vuoto il corpo del nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="2faf9-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="2faf9-124">Utilizzare i formati. msg (formato Outlook predefinito) o. eml (predefinito di Outlook sul Web Format) per i messaggi allegati.</span><span class="sxs-lookup"><span data-stu-id="2faf9-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="2faf9-125">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="2faf9-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="2faf9-126">Gli amministratori dispongono di diversi modi per bloccare messaggi specifici che vengono erroneamente identificati come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="2faf9-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="2faf9-127">Per ulteriori informazioni, vedere [creare elenchi di mittenti bloccati in Office 365](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="2faf9-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="2faf9-128">Inviare falsi positivi a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2faf9-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="2faf9-129">Invece di utilizzare le procedure seguenti per segnalare falsi positivi, gli utenti di Outlook e Outlook sul Web possono utilizzare il componente aggiuntivo per i messaggi di report per Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="2faf9-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="2faf9-130">Per informazioni su come installare e utilizzare questo strumento, vedere [Enable the report Message Add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="2faf9-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="2faf9-131">Se un messaggio è stato erroneamente identificato come posta indesiderata, è possibile inviare il messaggio al team di analisi di posta indesiderata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2faf9-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="2faf9-132">Gli analisti valuteranno il messaggio e (a seconda dei risultati dell'analisi), i filtri a livello di servizio possono essere modificati in modo da consentire il passaggio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="2faf9-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="2faf9-133">Creare un nuovo messaggio di posta elettronica vuoto `not_junk@office365.microsoft.com` come destinatario:</span><span class="sxs-lookup"><span data-stu-id="2faf9-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="2faf9-134">Trascinare e rilasciare il messaggio erroneamente identificato nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="2faf9-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="2faf9-135">In questo modo verrà salvato il messaggio erroneamente identificato come allegato nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="2faf9-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="2faf9-136">Non copiare e incollare il contenuto del messaggio o inoltrare il messaggio (è necessario il messaggio originale, in modo da poter ispezionare le intestazioni del messaggio).</span><span class="sxs-lookup"><span data-stu-id="2faf9-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="2faf9-137">È possibile allegare più messaggi nel nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="2faf9-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="2faf9-138">Verificare che tutti i messaggi siano dello stesso tipo, ovvero messaggi di phishing o messaggi di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="2faf9-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="2faf9-139">Lasciare vuoto il corpo del nuovo messaggio.</span><span class="sxs-lookup"><span data-stu-id="2faf9-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="2faf9-140">Utilizzare i formati. msg (formato Outlook predefinito) o. eml (predefinito di Outlook sul Web Format) per i messaggi allegati.</span><span class="sxs-lookup"><span data-stu-id="2faf9-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="2faf9-141">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="2faf9-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="2faf9-142">Gli amministratori dispongono di diversi modi per consentire ai messaggi specifici di ignorare il filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="2faf9-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="2faf9-143">Per ulteriori informazioni, vedere [creare elenchi di mittenti attendibili in Office 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="2faf9-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="2faf9-144">Creare una regola del flusso di posta elettronica per ricevere le copie dei messaggi segnalati a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2faf9-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="2faf9-145">È possibile creare una regola del flusso di posta (nota anche come regola di trasporto) che consente di cercare i messaggi di posta elettronica segnalati a Microsoft utilizzando i metodi descritti in questo argomento ed è possibile configurare i destinatari Ccn in modo che ricevano le copie dei messaggi segnalati.</span><span class="sxs-lookup"><span data-stu-id="2faf9-145">You can create a mail flow rule (also known as a transport rule) that looks for email messages that are reported to Microsoft by using the methods described in this topic, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="2faf9-146">È possibile creare la regola del flusso di posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e in PowerShell (Exchange Online PowerShell per i clienti di Microsoft 365; PowerShell di Exchange Online Protection per clienti EOP autonomi.</span><span class="sxs-lookup"><span data-stu-id="2faf9-146">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2faf9-147">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2faf9-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2faf9-148">Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2faf9-148">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="2faf9-149">In particolare, è necessario che venga assegnato il ruolo **regole di trasporto** , assegnato ai ruoli Gestione **organizzazione**, **Gestione conformità**e **record** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2faf9-149">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="2faf9-150">Per altre informazioni, vedere [Gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="2faf9-150">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="2faf9-151">Per aprire EAC in Exchange Online, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="2faf9-151">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="2faf9-152">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2faf9-152">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2faf9-153">Per connettersi a PowerShell per Exchange Online Protection autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2faf9-153">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2faf9-154">Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e EOP autonomo, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="2faf9-154">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="2faf9-155">Regole del flusso di posta (regole di trasporto) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2faf9-155">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="2faf9-156">Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2faf9-156">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="2faf9-157">Azioni delle regole del flusso di posta in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2faf9-157">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="2faf9-158">Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta elettronica per ricevere copie dei messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="2faf9-158">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="2faf9-159">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="2faf9-159">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="2faf9-160">Fare **Add** ![clic su Aggiungi](../../media/ITPro-EAC-AddIcon.png) icona e quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="2faf9-160">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="2faf9-161">Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2faf9-161">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="2faf9-162">**Nome**: immettere un nome univoco descrittivo per la regola.</span><span class="sxs-lookup"><span data-stu-id="2faf9-162">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="2faf9-163">Ad esempio, i messaggi Ccn segnalati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2faf9-163">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="2faf9-164">Fare clic su **altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="2faf9-164">Click **More Options**.</span></span>

   - <span data-ttu-id="2faf9-165">**Applica questa regola se**: selezionare **l'indirizzo del destinatario** \> **include una**o più delle seguenti parole: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti, fare clic](../../media/ITPro-EAC-AddIcon.png)su **Aggiungi** ![icona e ripetere fino a quando non sono stati immessi tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="2faf9-165">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="2faf9-166">Per modificare una voce, selezionarla e fare **Edit** ![clic su modifica](../../media/ITPro-EAC-EditIcon.png)icona modifica.</span><span class="sxs-lookup"><span data-stu-id="2faf9-166">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="2faf9-167">Per rimuovere una voce, selezionarla e fare **Remove** ![clic su Rimuovi](../../media/ITPro-EAC-DeleteIcon.png)icona Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="2faf9-167">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="2faf9-168">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2faf9-168">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="2faf9-169">**Eseguire le operazioni seguenti**: selezionare **Aggiungi destinatari** \> **alla casella Ccn**.</span><span class="sxs-lookup"><span data-stu-id="2faf9-169">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="2faf9-170">Nella finestra di dialogo che viene visualizzata, individuare e selezionare i destinatari che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="2faf9-170">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="2faf9-171">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2faf9-171">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="2faf9-172">È possibile effettuare selezioni aggiuntive per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2faf9-172">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="2faf9-173">È consigliabile testare la regola prima di applicarla.</span><span class="sxs-lookup"><span data-stu-id="2faf9-173">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="2faf9-174">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2faf9-174">When you're finished, click **Save**.</span></span>

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="2faf9-175">Utilizzo di PowerShell per creare una regola del flusso di posta elettronica per ricevere copie dei messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="2faf9-175">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="2faf9-176">In questo esempio viene creata una nuova regola del flusso di posta denominata Ccn messaggi segnalati a Microsoft che consente di cercare i messaggi di posta elettronica segnalati a Microsoft tramite i metodi descritti in questo argomento e di aggiungere gli utenti laura@contoso.com e julia@contoso.com come destinatari Ccn.</span><span class="sxs-lookup"><span data-stu-id="2faf9-176">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="2faf9-177">Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="2faf9-177">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2faf9-178">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="2faf9-178">How do you know this worked?</span></span>

<span data-ttu-id="2faf9-179">Per verificare di aver configurato le regole del flusso di posta elettronica per ricevere le copie dei messaggi segnalati, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2faf9-179">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="2faf9-180">Nell'interfaccia di amministrazione di Exchange, andare a **regole** \> del **flusso** \> di **Edit** ![posta selezionare la](../../media/ITPro-EAC-EditIcon.png)regola \> fare clic su Modifica icona modifica e verificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2faf9-180">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="2faf9-181">In PowerShell, eseguire il comando riportato di seguito per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2faf9-181">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="2faf9-182">Inviare un messaggio di prova a uno degli indirizzi di posta elettronica per la creazione di report e verificare i risultati.</span><span class="sxs-lookup"><span data-stu-id="2faf9-182">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
