---
title: Invii di amministratore
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare il portale per gli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica sospetti, sospette mail di phishing, posta indesiderata e altre informazioni potenzialmente nocive, URL e file a Microsoft per l'analisi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed417db93bc2f3efa6b85b0ef97c10b5941cd8eb
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029515"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="47512-103">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="47512-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="47512-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online, gli amministratori possono utilizzare il portale degli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="47512-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="47512-105">Quando si invia un messaggio di posta elettronica, si otterrà quanto segue:</span><span class="sxs-lookup"><span data-stu-id="47512-105">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="47512-106">**Verifica dell'autenticazione della posta elettronica**: informazioni sull'autenticazione del messaggio di posta elettronica superato o meno quando è stato recapitato.</span><span class="sxs-lookup"><span data-stu-id="47512-106">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="47512-107">**Hit dei criteri**: informazioni su tutti i criteri che possono aver consentito o bloccato la posta elettronica in arrivo nel tenant, sovrascrivendo i verdetti del filtro di servizio.</span><span class="sxs-lookup"><span data-stu-id="47512-107">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="47512-108">**Reputazione payload/detonazione**: esame degli URL e degli allegati del messaggio.</span><span class="sxs-lookup"><span data-stu-id="47512-108">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="47512-109">**Analisi del Grader**: recensione condotta dai selezionatori umani per confermare se i messaggi sono dannosi o meno.</span><span class="sxs-lookup"><span data-stu-id="47512-109">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47512-110">La reputazione payload/la detonazione e l'analisi del selezionatore non vengono eseguite in tutti i tenant.</span><span class="sxs-lookup"><span data-stu-id="47512-110">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="47512-111">Le informazioni vengono bloccate all'esterno dell'organizzazione quando i dati non dovrebbero lasciare il limite del tenant ai fini della conformità.</span><span class="sxs-lookup"><span data-stu-id="47512-111">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="47512-112">Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="47512-112">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="47512-113">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="47512-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="47512-114">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="47512-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="47512-115">Per passare direttamente alla pagina **invio** , utilizzare <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="47512-115">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="47512-116">Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="47512-116">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="47512-117">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="47512-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="47512-118">**Gestione dell'organizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="47512-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="47512-119">Si noti che l'appartenenza a questo gruppo di ruoli è necessaria per [visualizzare gli invii degli utenti alla cassetta postale personalizzata](#view-user-submissions-to-the-custom-mailbox) come descritto più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="47512-119">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="47512-120">Per ulteriori informazioni sul modo in cui gli utenti possono inviare messaggi e file a Microsoft, vedere [segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="47512-120">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="47512-121">Segnalare contenuti sospetti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="47512-121">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="47512-122">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> , verificare di essere nella scheda invii di **Amministrazione** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="47512-122">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="47512-123">Utilizzare il riquadro a comparsa **nuovo invio** che sembra inviare il messaggio, l'URL o l'allegato come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="47512-123">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="47512-124">Inviare un messaggio di posta elettronica discutibile a Microsoft</span><span class="sxs-lookup"><span data-stu-id="47512-124">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="47512-125">Nella sezione **tipo oggetto** selezionare **posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="47512-125">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="47512-126">Nella sezione **formato invio** , utilizzare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="47512-126">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="47512-127">**ID messaggio di rete**: questo è un valore GUID disponibile nell'intestazione **x-MS-Exchange-Organization-network-Message-ID** del messaggio o nell'intestazione **x-ms-Office365-Filtering-Correlation-ID** nei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="47512-127">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="47512-128">**File**: fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="47512-128">**File**: Click **Choose file**.</span></span> <span data-ttu-id="47512-129">Nella finestra di dialogo che si apre, individuare e selezionare il file. eml o. msg, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="47512-129">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="47512-130">Gli amministratori con Defender per Office 365 piano 1 o piano 2 sono in grado di inviare messaggi vecchi come 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="47512-130">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="47512-131">Altri amministratori saranno in grado di tornare indietro di 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="47512-131">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="47512-132">Nella sezione **destinatari** specificare uno o più destinatari a cui si desidera eseguire il controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="47512-132">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="47512-133">Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa di criteri dell'organizzazione o dell'utente.</span><span class="sxs-lookup"><span data-stu-id="47512-133">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="47512-134">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="47512-134">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="47512-135">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="47512-135">**Should not have been blocked**</span></span>

   - <span data-ttu-id="47512-136">**Avrebbe dovuto essere bloccato**: selezionare **posta indesiderata**, **phishing** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="47512-136">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="47512-137">Se non si è sicuri, utilizzare il miglior giudizio.</span><span class="sxs-lookup"><span data-stu-id="47512-137">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="47512-138">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="47512-138">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di invio di URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="47512-140">Inviare un URL sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="47512-140">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="47512-141">Nella sezione **tipo oggetto** selezionare **URL**.</span><span class="sxs-lookup"><span data-stu-id="47512-141">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="47512-142">Nella casella che viene visualizzata, immettere l'URL completo (ad esempio, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="47512-142">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="47512-143">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="47512-143">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="47512-144">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="47512-144">**Should not have been blocked**</span></span>

   - <span data-ttu-id="47512-145">**Avrebbe dovuto essere bloccato**: selezionare **phishing** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="47512-145">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="47512-146">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="47512-146">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di invio tramite posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="47512-148">Inviare un file sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="47512-148">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="47512-149">Nella sezione **tipo oggetto** selezionare **allegato**.</span><span class="sxs-lookup"><span data-stu-id="47512-149">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="47512-150">Fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="47512-150">Click **Choose File**.</span></span> <span data-ttu-id="47512-151">Nella finestra di dialogo che si apre, individuare e selezionare il file e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="47512-151">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="47512-152">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="47512-152">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="47512-153">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="47512-153">**Should not have been blocked**</span></span>

   - <span data-ttu-id="47512-154">**Avrebbe dovuto essere bloccato**: il **malware** è l'unica scelta e viene selezionato automaticamente..</span><span class="sxs-lookup"><span data-stu-id="47512-154">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="47512-155">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="47512-155">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di invio degli allegati](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="47512-157">Visualizzazione di invii di amministratore</span><span class="sxs-lookup"><span data-stu-id="47512-157">View admin submissions</span></span>

<span data-ttu-id="47512-158">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> , verificare di essere nella scheda invii di **Amministrazione** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="47512-158">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="47512-159">Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare per **ID invio** (un valore GUID assegnato a ogni invio) immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="47512-159">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="47512-160">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="47512-160">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="47512-161">Per modificare i criteri di filtro, fare clic sul pulsante **ID invio** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="47512-161">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="47512-162">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="47512-162">**Sender**</span></span>
- <span data-ttu-id="47512-163">**Oggetto/URL/nome file**</span><span class="sxs-lookup"><span data-stu-id="47512-163">**Subject/URL/File name**</span></span>
- <span data-ttu-id="47512-164">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="47512-164">**Submitted by**</span></span>
- <span data-ttu-id="47512-165">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="47512-165">**Submission type**</span></span>
- <span data-ttu-id="47512-166">**Stato**</span><span class="sxs-lookup"><span data-stu-id="47512-166">**Status**</span></span>

![Opzioni di filtro per invii di amministratore](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="47512-168">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="47512-168">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="47512-169">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="47512-169">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="47512-170">Al di sotto del grafico sono disponibili tre schede: **posta elettronica** (impostazione predefinita), **URL** e **allegato**.</span><span class="sxs-lookup"><span data-stu-id="47512-170">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="47512-171">Visualizzazione di invii di posta elettronica di amministratore</span><span class="sxs-lookup"><span data-stu-id="47512-171">View admin email submissions</span></span>

<span data-ttu-id="47512-172">Fare clic sulla scheda **posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="47512-172">Click the **Email** tab.</span></span>

<span data-ttu-id="47512-173">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="47512-173">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="47512-174">**Data**</span><span class="sxs-lookup"><span data-stu-id="47512-174">**Date**</span></span>
- <span data-ttu-id="47512-175">**ID invio**: valore GUID assegnato a ogni invio.</span><span class="sxs-lookup"><span data-stu-id="47512-175">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="47512-176">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-176">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-177">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-177">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-178">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="47512-178">**Sender**</span></span>
- <span data-ttu-id="47512-179">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-179">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-180">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="47512-180">**Submission type**</span></span>
- <span data-ttu-id="47512-181">**Motivo per il recapito**</span><span class="sxs-lookup"><span data-stu-id="47512-181">**Delivery reason**</span></span>
- <span data-ttu-id="47512-182">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-182">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="47512-183"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="47512-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="47512-184">Dettagli di rianalisi dell'invio dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="47512-184">Admin submission rescan details</span></span>

<span data-ttu-id="47512-185">I messaggi inviati in invii di amministratore vengono rianalizzati e i risultati vengono visualizzati nel riquadro a comparsa dei dettagli:</span><span class="sxs-lookup"><span data-stu-id="47512-185">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="47512-186">Se si è verificato un errore nell'autenticazione della posta elettronica del mittente al momento del recapito.</span><span class="sxs-lookup"><span data-stu-id="47512-186">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="47512-187">Informazioni su eventuali hit di criteri che potrebbero aver influenzato o ignorato il verdetto di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="47512-187">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="47512-188">Risultati di detonazione correnti per verificare se gli URL o i file contenuti nel messaggio sono stati dannosi o meno.</span><span class="sxs-lookup"><span data-stu-id="47512-188">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="47512-189">Commenti e suggerimenti dei selezionatori.</span><span class="sxs-lookup"><span data-stu-id="47512-189">Feedback from graders.</span></span>

<span data-ttu-id="47512-190">Se è stata trovata una sostituzione, la rianalisi deve essere completata in alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="47512-190">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="47512-191">Se non è stato riscontrato un problema nell'autenticazione della posta elettronica o se il recapito non è stato influenzato da una sostituzione, il feedback dei selezionatori potrebbe richiedere fino a un giorno.</span><span class="sxs-lookup"><span data-stu-id="47512-191">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="47512-192">Visualizzazione di invii di URL di amministrazione</span><span class="sxs-lookup"><span data-stu-id="47512-192">View admin URL submissions</span></span>

<span data-ttu-id="47512-193">Fare clic sulla scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="47512-193">Click the **URL** tab.</span></span>

<span data-ttu-id="47512-194">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="47512-194">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="47512-195">**Data**</span><span class="sxs-lookup"><span data-stu-id="47512-195">**Date**</span></span>
- <span data-ttu-id="47512-196">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="47512-196">**Submission ID**</span></span>
- <span data-ttu-id="47512-197">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-197">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-198">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-198">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-199">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="47512-199">**Submission type**</span></span>
- <span data-ttu-id="47512-200">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-200">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="47512-201"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="47512-201"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="47512-202">Visualizza invii degli allegati di amministratore</span><span class="sxs-lookup"><span data-stu-id="47512-202">View admin attachment submissions</span></span>

<span data-ttu-id="47512-203">Fare clic sulla scheda **allegati** .</span><span class="sxs-lookup"><span data-stu-id="47512-203">Click the **Attachments** tab.</span></span>

<span data-ttu-id="47512-204">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="47512-204">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="47512-205">**Data**</span><span class="sxs-lookup"><span data-stu-id="47512-205">**Date**</span></span>
- <span data-ttu-id="47512-206">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="47512-206">**Submission ID**</span></span>
- <span data-ttu-id="47512-207">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-207">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-208">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-208">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-209">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="47512-209">**Submission type**</span></span>
- <span data-ttu-id="47512-210">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-210">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="47512-211"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="47512-211"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="47512-212">Visualizzazione degli invii degli utenti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="47512-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="47512-213">Se è stato distribuito il [componente](enable-the-report-message-add-in.md)aggiuntivo per i messaggi di report, il [componente aggiuntivo](enable-the-report-phish-add-in.md)per il phishing dei report o gli utenti che utilizzano la creazione di report [incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), è possibile visualizzare gli elementi segnalati nella scheda **invii utente** .</span><span class="sxs-lookup"><span data-stu-id="47512-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="47512-214">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> .</span><span class="sxs-lookup"><span data-stu-id="47512-214">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="47512-215">Selezionare la scheda **invii utente** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="47512-215">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="47512-216">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="47512-216">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="47512-217">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="47512-217">**Submitted on**</span></span>
- <span data-ttu-id="47512-218">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-218">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-219">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-219">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-220">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="47512-220">**Sender**</span></span>
- <span data-ttu-id="47512-221">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-221">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-222">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="47512-222">**Submission type**</span></span>

<span data-ttu-id="47512-223"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="47512-223"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="47512-224">Nella parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare in base al **mittente** immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="47512-224">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="47512-225">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="47512-225">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="47512-226">Per modificare i criteri di filtro, fare clic sul pulsante **mittente** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="47512-226">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="47512-227">**Dominio del mittente**</span><span class="sxs-lookup"><span data-stu-id="47512-227">**Sender domain**</span></span>
- <span data-ttu-id="47512-228">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="47512-228">**Subject**</span></span>
- <span data-ttu-id="47512-229">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="47512-229">**Submitted by**</span></span>
- <span data-ttu-id="47512-230">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="47512-230">**Submission type**</span></span>
- <span data-ttu-id="47512-231">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="47512-231">**Sender IP**</span></span>

![Opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

<span data-ttu-id="47512-233">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="47512-233">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="47512-234">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="47512-234">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="47512-235">Visualizzare gli invii degli utenti alla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="47512-235">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="47512-236">**Se** è stata [configurata una cassetta postale personalizzata](user-submission.md) per la ricezione di messaggi segnalati dall'utente, è possibile visualizzare e inviare anche messaggi che sono stati recapitati alla cassetta postale di Reporting.</span><span class="sxs-lookup"><span data-stu-id="47512-236">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="47512-237">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> .</span><span class="sxs-lookup"><span data-stu-id="47512-237">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="47512-238">Selezionare la scheda **cassetta postale personalizzata** .</span><span class="sxs-lookup"><span data-stu-id="47512-238">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="47512-239">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="47512-239">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="47512-240">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="47512-240">**Submitted on**</span></span>
- <span data-ttu-id="47512-241">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-241">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-242">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-242">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-243">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="47512-243">**Sender**</span></span>
- <span data-ttu-id="47512-244">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47512-244">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="47512-245">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="47512-245">**Submission type**</span></span>

<span data-ttu-id="47512-246">Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine ed è possibile filtrare in base a quanto **inserito** inserendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="47512-246">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="47512-247">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="47512-247">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="47512-248">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="47512-248">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="47512-249">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="47512-249">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="47512-250">Annullamento degli invii degli utenti</span><span class="sxs-lookup"><span data-stu-id="47512-250">Undo user submissions</span></span>

<span data-ttu-id="47512-251">Dopo che un utente ha inviato un messaggio di posta elettronica sospetto alla cassetta postale personalizzata, l'utente e l'amministratore non dispongono di un'opzione per annullare l'invio.</span><span class="sxs-lookup"><span data-stu-id="47512-251">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="47512-252">Se l'utente desidera recuperare il messaggio di posta elettronica, sarà disponibile per il ripristino negli elementi eliminati o nelle cartelle di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="47512-252">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="47512-253">Inviare messaggi a Microsoft dalla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="47512-253">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="47512-254">Se è stata configurata la cassetta postale personalizzata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="47512-254">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="47512-255">Questo consente di spostare efficacemente l'invio di un utente a un invio di amministratore.</span><span class="sxs-lookup"><span data-stu-id="47512-255">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="47512-256">Nella scheda **cassetta postale personalizzata** , selezionare un messaggio nell'elenco, fare clic sul pulsante **azione** ed eseguire una delle selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="47512-256">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="47512-257">**Relazione pulita**</span><span class="sxs-lookup"><span data-stu-id="47512-257">**Report clean**</span></span>
- <span data-ttu-id="47512-258">**Notifica di phishing**</span><span class="sxs-lookup"><span data-stu-id="47512-258">**Report phishing**</span></span>
- <span data-ttu-id="47512-259">**Segnala malware**</span><span class="sxs-lookup"><span data-stu-id="47512-259">**Report malware**</span></span>
- <span data-ttu-id="47512-260">**Segnalare la posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="47512-260">**Report spam**</span></span>

![Opzioni sul pulsante azione](../../media/user-submission-custom-mailbox-action-button.png)
