---
title: Invii di amministratore
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare il portale per gli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica sospetti, sospette mail di phishing, posta indesiderata e altre informazioni potenzialmente nocive, URL e file a Microsoft per l'analisi.
ms.openlocfilehash: 0c01afff2e9e5a656099192f3867bb3a6f1cee23
ms.sourcegitcommit: 7e003ee0a06f61bfb9f80441c3479fa3148afafe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "49568591"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="9b5ba-103">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b5ba-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9b5ba-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online, gli amministratori possono utilizzare il portale degli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="9b5ba-105">Quando si invia un messaggio di posta elettronica, si ottengono informazioni su tutti i criteri che possono aver consentito la posta elettronica in arrivo nel tenant, nonché l'esame degli URL e degli allegati della posta.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="9b5ba-106">I criteri che possono aver consentito a un messaggio di posta elettronica includono l'elenco dei mittenti attendibili di un singolo utente e i criteri di livello tenant, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto)</span><span class="sxs-lookup"><span data-stu-id="9b5ba-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="9b5ba-107">Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9b5ba-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9b5ba-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9b5ba-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9b5ba-109">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9b5ba-110">Per passare direttamente alla pagina **invio** , utilizzare <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="9b5ba-111">Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="9b5ba-112">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9b5ba-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="9b5ba-113">**Gestione dell'organizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="9b5ba-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="9b5ba-114">Si noti che l'appartenenza a questo gruppo di ruoli è necessaria per [visualizzare gli invii degli utenti alla cassetta postale personalizzata](#view-user-submissions-to-the-custom-mailbox) come descritto più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="9b5ba-115">Per ulteriori informazioni sul modo in cui gli utenti possono inviare messaggi e file a Microsoft, vedere [segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9b5ba-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="9b5ba-116">Segnalare contenuti sospetti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b5ba-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="9b5ba-117">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**, verificare di essere nella scheda invii di **Amministrazione** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="9b5ba-118">Utilizzare il riquadro a comparsa **nuovo invio** che sembra inviare il messaggio, l'URL o l'allegato come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="9b5ba-119">Inviare un messaggio di posta elettronica discutibile a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b5ba-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="9b5ba-120">Nella sezione **tipo oggetto** selezionare **posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="9b5ba-121">Nella sezione **formato invio** , utilizzare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="9b5ba-122">**ID messaggio di rete**: questo è un valore GUID disponibile nell'intestazione **x-MS-Exchange-Organization-network-Message-ID** del messaggio o nell'intestazione **x-ms-Office365-Filtering-Correlation-ID** nei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="9b5ba-123">**File**: fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="9b5ba-124">Nella finestra di dialogo che si apre, individuare e selezionare il file. eml o. msg, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9b5ba-125">Gli amministratori con Defender per Office 365 piano 1 o piano 2 sono in grado di inviare messaggi vecchi come 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="9b5ba-126">Altri amministratori saranno in grado di tornare indietro di 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="9b5ba-127">Nella sezione **destinatari** specificare uno o più destinatari a cui si desidera eseguire il controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="9b5ba-128">Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa di criteri dell'organizzazione o dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="9b5ba-129">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9b5ba-130">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9b5ba-131">**Avrebbe dovuto essere bloccato**: selezionare **posta indesiderata**, **phishing** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="9b5ba-132">Se non si è sicuri, utilizzare il miglior giudizio.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="9b5ba-133">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-133">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio di URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="9b5ba-135">Inviare un URL sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b5ba-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="9b5ba-136">Nella sezione **tipo oggetto** selezionare **URL**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="9b5ba-137">Nella casella che viene visualizzata, immettere l'URL completo (ad esempio, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="9b5ba-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="9b5ba-138">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9b5ba-139">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9b5ba-140">**Avrebbe dovuto essere bloccato**: selezionare **phishing** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="9b5ba-141">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-141">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio tramite posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="9b5ba-143">Inviare un file sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b5ba-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="9b5ba-144">Nella sezione **tipo oggetto** selezionare **allegato**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="9b5ba-145">Fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-145">Click **Choose File**.</span></span> <span data-ttu-id="9b5ba-146">Nella finestra di dialogo che si apre, individuare e selezionare il file e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="9b5ba-147">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9b5ba-148">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9b5ba-149">**Avrebbe dovuto essere bloccato**: il **malware** è l'unica scelta e viene selezionato automaticamente..</span><span class="sxs-lookup"><span data-stu-id="9b5ba-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="9b5ba-150">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-150">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio degli allegati](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="9b5ba-152">Visualizzazione di invii di amministratore</span><span class="sxs-lookup"><span data-stu-id="9b5ba-152">View admin submissions</span></span>

<span data-ttu-id="9b5ba-153">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**, verificare di essere nella scheda invii di **Amministrazione** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="9b5ba-154">Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare per **ID invio** (un valore GUID assegnato a ogni invio) immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9b5ba-155">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9b5ba-156">Per modificare i criteri di filtro, fare clic sul pulsante **ID invio** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="9b5ba-157">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-157">**Sender**</span></span>
- <span data-ttu-id="9b5ba-158">**Oggetto/URL/nome file**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="9b5ba-159">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-159">**Submitted by**</span></span>
- <span data-ttu-id="9b5ba-160">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-160">**Submission type**</span></span>
- <span data-ttu-id="9b5ba-161">**Stato**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-161">**Status**</span></span>

![Opzioni di filtro per invii di amministratore](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="9b5ba-163">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9b5ba-164">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="9b5ba-165">Al di sotto del grafico sono disponibili tre schede: **posta elettronica** (impostazione predefinita), **URL** e **allegato**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="9b5ba-166">Visualizzazione di invii di posta elettronica di amministratore</span><span class="sxs-lookup"><span data-stu-id="9b5ba-166">View admin email submissions</span></span>

<span data-ttu-id="9b5ba-167">Fare clic sulla scheda **posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-167">Click the **Email** tab.</span></span>

<span data-ttu-id="9b5ba-168">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9b5ba-169">**Data**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-169">**Date**</span></span>
- <span data-ttu-id="9b5ba-170">**ID invio**: valore GUID assegnato a ogni invio.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="9b5ba-171">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-172">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-173">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-173">**Sender**</span></span>
- <span data-ttu-id="9b5ba-174">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-175">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-175">**Submission type**</span></span>
- <span data-ttu-id="9b5ba-176">**Motivo per il recapito**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-176">**Delivery reason**</span></span>
- <span data-ttu-id="9b5ba-177">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9b5ba-178"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="9b5ba-179">Dettagli di rianalisi dell'invio dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="9b5ba-179">Admin submission rescan details</span></span>

<span data-ttu-id="9b5ba-180">I messaggi inviati in invii di amministratore vengono rianalizzati e i risultati vengono visualizzati nel riquadro a comparsa dei dettagli:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="9b5ba-181">Se si è verificato un errore nell'autenticazione della posta elettronica del mittente al momento del recapito.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="9b5ba-182">Informazioni su eventuali hit di criteri che potrebbero aver influenzato o ignorato il verdetto di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="9b5ba-183">Risultati di detonazione correnti per verificare se gli URL o i file contenuti nel messaggio sono stati dannosi o meno.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="9b5ba-184">Commenti e suggerimenti dei selezionatori.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-184">Feedback from graders.</span></span>

<span data-ttu-id="9b5ba-185">Se è stata trovata una sostituzione, la rianalisi deve essere completata in alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="9b5ba-186">Se non è stato riscontrato un problema nell'autenticazione della posta elettronica o se il recapito non è stato influenzato da una sostituzione, il feedback dei selezionatori potrebbe richiedere fino a un giorno.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="9b5ba-187">Visualizzazione di invii di URL di amministrazione</span><span class="sxs-lookup"><span data-stu-id="9b5ba-187">View admin URL submissions</span></span>

<span data-ttu-id="9b5ba-188">Fare clic sulla scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-188">Click the **URL** tab.</span></span>

<span data-ttu-id="9b5ba-189">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9b5ba-190">**Data**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-190">**Date**</span></span>
- <span data-ttu-id="9b5ba-191">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-191">**Submission ID**</span></span>
- <span data-ttu-id="9b5ba-192">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-194">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-194">**Submission type**</span></span>
- <span data-ttu-id="9b5ba-195">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9b5ba-196"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="9b5ba-197">Visualizza invii degli allegati di amministratore</span><span class="sxs-lookup"><span data-stu-id="9b5ba-197">View admin attachment submissions</span></span>

<span data-ttu-id="9b5ba-198">Fare clic sulla scheda **allegati** .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="9b5ba-199">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9b5ba-200">**Data**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-200">**Date**</span></span>
- <span data-ttu-id="9b5ba-201">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-201">**Submission ID**</span></span>
- <span data-ttu-id="9b5ba-202">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-203">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-204">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-204">**Submission type**</span></span>
- <span data-ttu-id="9b5ba-205">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9b5ba-206"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="9b5ba-207">Visualizzazione degli invii degli utenti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b5ba-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="9b5ba-208">Se è stato distribuito il [componente aggiuntivo](enable-the-report-message-add-in.md)per i messaggi di report o si utilizza la creazione di report [incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), è possibile visualizzare gli utenti che segnalano nella scheda **invii utente** .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="9b5ba-209">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="9b5ba-210">Selezionare la scheda **invii utente** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="9b5ba-211">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9b5ba-212">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-212">**Submitted on**</span></span>
- <span data-ttu-id="9b5ba-213">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-214">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-215">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-215">**Sender**</span></span>
- <span data-ttu-id="9b5ba-216">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-217">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-217">**Submission type**</span></span>

<span data-ttu-id="9b5ba-218"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="9b5ba-219">Nella parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare in base al **mittente** immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9b5ba-220">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9b5ba-221">Per modificare i criteri di filtro, fare clic sul pulsante **mittente** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="9b5ba-222">**Dominio mittente**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-222">**Sender domain**</span></span>
- <span data-ttu-id="9b5ba-223">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-223">**Subject**</span></span>
- <span data-ttu-id="9b5ba-224">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-224">**Submitted by**</span></span>
- <span data-ttu-id="9b5ba-225">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-225">**Submission type**</span></span>
- <span data-ttu-id="9b5ba-226">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-226">**Sender IP**</span></span>

![Opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

<span data-ttu-id="9b5ba-228">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9b5ba-229">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="9b5ba-230">Visualizzare gli invii degli utenti alla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="9b5ba-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="9b5ba-231">**Se** è stata [configurata una cassetta postale personalizzata](user-submission.md) per la ricezione di messaggi segnalati dall'utente, è possibile visualizzare e inviare anche messaggi che sono stati recapitati alla cassetta postale di Reporting.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="9b5ba-232">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="9b5ba-233">Selezionare la scheda **cassetta postale personalizzata** .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="9b5ba-234">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9b5ba-235">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-235">**Submitted on**</span></span>
- <span data-ttu-id="9b5ba-236">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-237">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-238">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-238">**Sender**</span></span>
- <span data-ttu-id="9b5ba-239">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9b5ba-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9b5ba-240">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-240">**Submission type**</span></span>

<span data-ttu-id="9b5ba-241">Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine ed è possibile filtrare in base a quanto **inserito** inserendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="9b5ba-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9b5ba-242">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9b5ba-243">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9b5ba-244">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="9b5ba-245">Annullamento degli invii degli utenti</span><span class="sxs-lookup"><span data-stu-id="9b5ba-245">Undo user submissions</span></span>

<span data-ttu-id="9b5ba-246">Dopo che un utente ha inviato un messaggio di posta elettronica sospetto alla cassetta postale personalizzata, l'utente e l'amministratore non dispongono di un'opzione per annullare l'invio.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="9b5ba-247">Se l'utente desidera recuperare il messaggio di posta elettronica, sarà disponibile per il ripristino negli elementi eliminati o nelle cartelle di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="9b5ba-248">Inviare messaggi a Microsoft dalla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="9b5ba-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="9b5ba-249">Se è stata configurata la cassetta postale personalizzata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="9b5ba-250">Questo consente di spostare efficacemente l'invio di un utente a un invio di amministratore.</span><span class="sxs-lookup"><span data-stu-id="9b5ba-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="9b5ba-251">Nella scheda **cassetta postale personalizzata** , selezionare un messaggio nell'elenco, fare clic sul pulsante **azione** ed eseguire una delle selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b5ba-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="9b5ba-252">**Relazione pulita**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-252">**Report clean**</span></span>
- <span data-ttu-id="9b5ba-253">**Notifica di phishing**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-253">**Report phishing**</span></span>
- <span data-ttu-id="9b5ba-254">**Segnala malware**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-254">**Report malware**</span></span>
- <span data-ttu-id="9b5ba-255">**Segnalare la posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="9b5ba-255">**Report spam**</span></span>

![Opzioni sul pulsante azione](../../media/user-submission-custom-mailbox-action-button.png)
