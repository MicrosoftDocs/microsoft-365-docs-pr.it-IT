---
title: Invii di amministratori
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
description: Gli amministratori possono imparare a usare il portale invii nel Centro sicurezza e conformità & per inviare messaggi di posta elettronica sospetti, messaggi di phishing sospetti, posta indesiderata e altri messaggi, URL e file potenzialmente dannosi a Microsoft per l'analisi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96a5469b1093c71997747b2c4c3b49bc1964f72b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581071"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="71d50-103">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="71d50-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="71d50-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="71d50-104">**Applies to**</span></span>
- [<span data-ttu-id="71d50-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="71d50-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="71d50-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="71d50-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="71d50-107">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online, gli amministratori possono utilizzare il portale invii nel Centro sicurezza & conformità per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="71d50-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="71d50-108">Quando invii un messaggio di posta elettronica, ottieni:</span><span class="sxs-lookup"><span data-stu-id="71d50-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="71d50-109">**Controllo dell'autenticazione della** posta elettronica : Dettagli sul fatto che l'autenticazione della posta elettronica sia stata superata o meno al momento del recapito.</span><span class="sxs-lookup"><span data-stu-id="71d50-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="71d50-110">**Riscontri criteri:** informazioni su eventuali criteri che potrebbero aver consentito o bloccato la posta elettronica in arrivo nel tenant, ignorando i verdetti del filtro del servizio.</span><span class="sxs-lookup"><span data-stu-id="71d50-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="71d50-111">**Reputazione/detonazione del payload**: esame di eventuali URL e allegati nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="71d50-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="71d50-112">**Analisi grader**: Revisione eseguita dai grader umani per verificare se i messaggi sono dannosi.</span><span class="sxs-lookup"><span data-stu-id="71d50-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71d50-113">La reputazione/detonazione del payload e l'analisi del grado non vengono eseguite in tutti i tenant.</span><span class="sxs-lookup"><span data-stu-id="71d50-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="71d50-114">Le informazioni non possono uscire dall'organizzazione quando i dati non devono uscire dal limite del tenant per motivi di conformità.</span><span class="sxs-lookup"><span data-stu-id="71d50-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="71d50-115">Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="71d50-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="71d50-116">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="71d50-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="71d50-117">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="71d50-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="71d50-118">Per passare direttamente alla **pagina Invio,** usa <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="71d50-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="71d50-119">Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="71d50-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="71d50-120">**Gestione dell'organizzazione** **o Lettore sicurezza** nel [Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="71d50-120">**Organization Management** or **Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="71d50-121">**Gestione dell'organizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="71d50-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="71d50-122">Si noti che l'appartenenza a questo gruppo di ruoli è necessaria per [visualizzare gli](#view-user-submissions-to-the-custom-mailbox) invii degli utenti alla cassetta postale personalizzata, come descritto più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="71d50-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="71d50-123">Per ulteriori informazioni su come gli utenti possono inviare messaggi e file a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="71d50-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="71d50-124">Segnalare contenuti sospetti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="71d50-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="71d50-125">Nel Centro sicurezza & conformità passare  a Invii di gestione delle minacce, verificare di essere nella scheda \>  **Invii** dell'amministratore e quindi fare clic su **Nuovo invio.**</span><span class="sxs-lookup"><span data-stu-id="71d50-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="71d50-126">Usa **il riquadro a** comparsa Nuovo invio visualizzato per inviare il messaggio, l'URL o l'allegato come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="71d50-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="71d50-127">Inviare un messaggio di posta elettronica discutibile a Microsoft</span><span class="sxs-lookup"><span data-stu-id="71d50-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="71d50-128">Nella sezione **Tipo oggetto** selezionare Posta **elettronica.**</span><span class="sxs-lookup"><span data-stu-id="71d50-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="71d50-129">Nella sezione **Formato invio** usa una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="71d50-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="71d50-130">**ID** messaggio di rete: si tratta di un valore GUID disponibile nell'intestazione **X-MS-Exchange-Organization-Network-Message-Id** del messaggio o nell'intestazione **X-MS-Office365-Filtering-Correlation-Id** nei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="71d50-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="71d50-131">**File**: fare clic **su Scegli file.**</span><span class="sxs-lookup"><span data-stu-id="71d50-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="71d50-132">Nella finestra di dialogo visualizzata individuare e selezionare il file con estensione eml o msg e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="71d50-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="71d50-133">Gli amministratori con Defender per Office 365 Piano 1 o Piano 2 possono inviare messaggi vecchi fino a 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="71d50-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="71d50-134">Altri amministratori potranno tornare indietro di 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="71d50-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="71d50-135">Nella sezione **Destinatari** specificare uno o più destinatari per i quali si desidera eseguire un controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="71d50-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="71d50-136">Il controllo dei criteri determinerà se l'analisi dei messaggi di posta elettronica è stata ignorata a causa dei criteri dell'utente o dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="71d50-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="71d50-137">Nella sezione **Motivo invio** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="71d50-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="71d50-138">**Non dovrebbe essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="71d50-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="71d50-139">**Dovrebbe essere stato bloccato:** Selezionare **Posta indesiderata,** **Phishing** o **Malware.**</span><span class="sxs-lookup"><span data-stu-id="71d50-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="71d50-140">Se non sei sicuro, usa il tuo miglior giudizio.</span><span class="sxs-lookup"><span data-stu-id="71d50-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="71d50-141">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="71d50-141">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di invio di URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="71d50-143">Inviare un URL sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="71d50-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="71d50-144">Nella sezione **Tipo oggetto** selezionare **URL**.</span><span class="sxs-lookup"><span data-stu-id="71d50-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="71d50-145">Nella casella visualizzata immettere l'URL completo, ad esempio `https://www.fabrikam.com/marketing.html` .</span><span class="sxs-lookup"><span data-stu-id="71d50-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="71d50-146">Nella sezione **Motivo invio** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="71d50-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="71d50-147">**Non dovrebbe essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="71d50-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="71d50-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span><span class="sxs-lookup"><span data-stu-id="71d50-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="71d50-149">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="71d50-149">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di invio di posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="71d50-151">Inviare un file sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="71d50-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="71d50-152">Nella sezione **Tipo oggetto** selezionare **Allegato.**</span><span class="sxs-lookup"><span data-stu-id="71d50-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="71d50-153">Fare **clic su Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="71d50-153">Click **Choose File**.</span></span> <span data-ttu-id="71d50-154">Nella finestra di dialogo visualizzata individuare e selezionare il file e quindi fare clic su **Apri.**</span><span class="sxs-lookup"><span data-stu-id="71d50-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="71d50-155">Nella sezione **Motivo invio** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="71d50-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="71d50-156">**Non dovrebbe essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="71d50-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="71d50-157">**Dovrebbe essere stato bloccato:** **il malware** è l'unica scelta e viene selezionato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="71d50-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="71d50-158">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="71d50-158">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di invio di allegati](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="71d50-160">Visualizzare gli elementi inviati per l'analisi</span><span class="sxs-lookup"><span data-stu-id="71d50-160">View items Submitted for analysis</span></span>

<span data-ttu-id="71d50-161">Nel Centro sicurezza & conformità passare **a** Invii di gestione delle minacce , verificare di essere \> nella scheda Inviato **per l'analisi**</span><span class="sxs-lookup"><span data-stu-id="71d50-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="71d50-162">Nella parte superiore della pagina è possibile immettere una data di inizio, una data di fine e, per impostazione predefinita, è possibile filtrare in base **all'ID** invio (un valore GUID assegnato a ogni invio) immettendo un valore nella casella e facendo clic sul pulsante ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="71d50-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="71d50-163">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="71d50-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="71d50-164">Per modificare i criteri di filtro, fare clic sul pulsante **ID invio** e scegliere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="71d50-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="71d50-165">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="71d50-165">**Sender**</span></span>
- <span data-ttu-id="71d50-166">**Subject/URL/File name**</span><span class="sxs-lookup"><span data-stu-id="71d50-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="71d50-167">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="71d50-167">**Submitted by**</span></span>
- <span data-ttu-id="71d50-168">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="71d50-168">**Submission type**</span></span>
- <span data-ttu-id="71d50-169">**Stato**</span><span class="sxs-lookup"><span data-stu-id="71d50-169">**Status**</span></span>

![Opzioni di filtro per gli invii di amministratori](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="71d50-171">Per esportare i risultati, fare clic **su Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.**</span><span class="sxs-lookup"><span data-stu-id="71d50-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="71d50-172">Nella finestra di dialogo visualizzata salvare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="71d50-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="71d50-173">Sotto il grafico sono disponibili tre schede: **Posta elettronica** (impostazione predefinita), **URL** e **Allegato.**</span><span class="sxs-lookup"><span data-stu-id="71d50-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="71d50-174">Visualizzare gli invii di posta elettronica dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="71d50-174">View admin email submissions</span></span>

<span data-ttu-id="71d50-175">Fare clic sulla **scheda Posta** elettronica.</span><span class="sxs-lookup"><span data-stu-id="71d50-175">Click the **Email** tab.</span></span>

<span data-ttu-id="71d50-176">È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="71d50-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="71d50-177">**Data**</span><span class="sxs-lookup"><span data-stu-id="71d50-177">**Date**</span></span>
- <span data-ttu-id="71d50-178">**ID invio:** valore GUID assegnato a ogni invio.</span><span class="sxs-lookup"><span data-stu-id="71d50-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="71d50-179">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-180">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-181">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="71d50-181">**Sender**</span></span>
- <span data-ttu-id="71d50-182">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-183">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="71d50-183">**Submission type**</span></span>
- <span data-ttu-id="71d50-184">**Motivo recapito**</span><span class="sxs-lookup"><span data-stu-id="71d50-184">**Delivery reason**</span></span>
- <span data-ttu-id="71d50-185">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="71d50-186"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="71d50-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="71d50-187">Dettagli dell'analisi dell'invio dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="71d50-187">Admin submission rescan details</span></span>

<span data-ttu-id="71d50-188">I messaggi inviati negli invii di amministratori vengono sottoposti a nuova analisi e i risultati vengono visualizzati nel riquadro a comparsa dei dettagli:</span><span class="sxs-lookup"><span data-stu-id="71d50-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="71d50-189">Se si è verificato un errore nell'autenticazione della posta elettronica del mittente al momento del recapito.</span><span class="sxs-lookup"><span data-stu-id="71d50-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="71d50-190">Informazioni su eventuali riscontri dei criteri che potrebbero aver influenzato o sostituito il verdetto di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="71d50-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="71d50-191">Risultati della detonazione correnti per verificare se gli URL o i file contenuti nel messaggio erano dannosi o meno.</span><span class="sxs-lookup"><span data-stu-id="71d50-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="71d50-192">Feedback dei gradi.</span><span class="sxs-lookup"><span data-stu-id="71d50-192">Feedback from graders.</span></span>

<span data-ttu-id="71d50-193">Se è stata trovata una sostituzione, la nuova analisi dovrebbe essere completata dopo alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="71d50-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="71d50-194">Se non si è verificato un problema nell'autenticazione della posta elettronica o il recapito non è stato influenzato da una sostituzione, il feedback dei voti potrebbe richiedere fino a un giorno.</span><span class="sxs-lookup"><span data-stu-id="71d50-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="71d50-195">Visualizzare gli invii di URL di amministratore</span><span class="sxs-lookup"><span data-stu-id="71d50-195">View admin URL submissions</span></span>

<span data-ttu-id="71d50-196">Fare clic **sulla scheda URL.**</span><span class="sxs-lookup"><span data-stu-id="71d50-196">Click the **URL** tab.</span></span>

<span data-ttu-id="71d50-197">È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="71d50-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="71d50-198">**Data**</span><span class="sxs-lookup"><span data-stu-id="71d50-198">**Date**</span></span>
- <span data-ttu-id="71d50-199">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="71d50-199">**Submission ID**</span></span>
- <span data-ttu-id="71d50-200">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-202">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="71d50-202">**Submission type**</span></span>
- <span data-ttu-id="71d50-203">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="71d50-204"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="71d50-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="71d50-205">Visualizzare gli invii di allegati dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="71d50-205">View admin attachment submissions</span></span>

<span data-ttu-id="71d50-206">Fare clic **sulla scheda** Allegati.</span><span class="sxs-lookup"><span data-stu-id="71d50-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="71d50-207">È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="71d50-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="71d50-208">**Data**</span><span class="sxs-lookup"><span data-stu-id="71d50-208">**Date**</span></span>
- <span data-ttu-id="71d50-209">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="71d50-209">**Submission ID**</span></span>
- <span data-ttu-id="71d50-210">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-211">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-212">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="71d50-212">**Submission type**</span></span>
- <span data-ttu-id="71d50-213">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="71d50-214"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="71d50-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="71d50-215">Visualizzare gli invii degli utenti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="71d50-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="71d50-216">Se è stato distribuito il componente aggiuntivo Segnala [messaggio,](enable-the-report-message-add-in.md)il componente aggiuntivo Segnala [phishing](enable-the-report-phish-add-in.md)o gli utenti utilizzano la creazione di  report predefinita in [Outlook sul Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)è possibile visualizzare le segnalazioni degli utenti nella scheda Invii utente.</span><span class="sxs-lookup"><span data-stu-id="71d50-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="71d50-217">Nel Centro sicurezza & conformità passare a **Gestione minacce** \> **Invii**.</span><span class="sxs-lookup"><span data-stu-id="71d50-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="71d50-218">Seleziona la **scheda Invii utente** e quindi fai clic su **Nuovo invio.**</span><span class="sxs-lookup"><span data-stu-id="71d50-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="71d50-219">È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="71d50-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="71d50-220">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="71d50-220">**Submitted on**</span></span>
- <span data-ttu-id="71d50-221">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-222">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-223">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="71d50-223">**Sender**</span></span>
- <span data-ttu-id="71d50-224">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-225">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="71d50-225">**Submission type**</span></span>

<span data-ttu-id="71d50-226"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="71d50-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="71d50-227">Nella parte superiore della pagina è possibile immettere una data di inizio, una  data di fine e, per impostazione predefinita, è possibile filtrare in base al mittente immettendo un valore nella casella e facendo clic sul ![ pulsante Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="71d50-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="71d50-228">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="71d50-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="71d50-229">Per modificare i criteri di filtro, fare clic **sul pulsante Mittente** e scegliere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="71d50-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="71d50-230">**Dominio del mittente**</span><span class="sxs-lookup"><span data-stu-id="71d50-230">**Sender domain**</span></span>
- <span data-ttu-id="71d50-231">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="71d50-231">**Subject**</span></span>
- <span data-ttu-id="71d50-232">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="71d50-232">**Submitted by**</span></span>
- <span data-ttu-id="71d50-233">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="71d50-233">**Submission type**</span></span>
- <span data-ttu-id="71d50-234">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="71d50-234">**Sender IP**</span></span>

![Opzioni di filtro per gli invii utente](../../media/user-submissions-filter-options.png)

<span data-ttu-id="71d50-236">Per esportare i risultati, fare clic **su Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.**</span><span class="sxs-lookup"><span data-stu-id="71d50-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="71d50-237">Nella finestra di dialogo visualizzata salvare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="71d50-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="71d50-238">Visualizzare gli invii utente alla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="71d50-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="71d50-239">**Se** è stata [configurata una cassetta](user-submission.md) postale personalizzata per ricevere i messaggi segnalati dall'utente, è possibile visualizzare e inviare i messaggi recapitati alla cassetta postale di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="71d50-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="71d50-240">Nel Centro sicurezza & conformità passare a **Gestione minacce** \> **Invii**.</span><span class="sxs-lookup"><span data-stu-id="71d50-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="71d50-241">Selezionare la **scheda Cassetta postale** personalizzata.</span><span class="sxs-lookup"><span data-stu-id="71d50-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="71d50-242">È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="71d50-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="71d50-243">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="71d50-243">**Submitted on**</span></span>
- <span data-ttu-id="71d50-244">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-245">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-246">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="71d50-246">**Sender**</span></span>
- <span data-ttu-id="71d50-247">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71d50-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="71d50-248">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="71d50-248">**Submission type**</span></span>

<span data-ttu-id="71d50-249">Nella parte superiore della pagina è possibile immettere una data di inizio, una data di fine e filtrare in base a **Inviato** immettendo un valore nella casella e facendo clic sul ![ pulsante Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="71d50-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="71d50-250">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="71d50-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="71d50-251">Per esportare i risultati, fare clic **su Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.**</span><span class="sxs-lookup"><span data-stu-id="71d50-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="71d50-252">Nella finestra di dialogo visualizzata salvare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="71d50-252">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="71d50-253">Se le organizzazioni sono configurate per l'invio solo alla cassetta postale personalizzata, i messaggi segnalati non verranno inviati per la nuova analisi e i risultati nel portale Messaggi segnalati dall'utente saranno sempre vuoti.</span><span class="sxs-lookup"><span data-stu-id="71d50-253">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="71d50-254">Annullare gli invii utente</span><span class="sxs-lookup"><span data-stu-id="71d50-254">Undo user submissions</span></span>

<span data-ttu-id="71d50-255">Una volta che un utente invia un messaggio di posta elettronica sospetto alla cassetta postale personalizzata, l'utente e l'amministratore non hanno la possibilità di annullare l'invio.</span><span class="sxs-lookup"><span data-stu-id="71d50-255">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="71d50-256">Se l'utente desidera recuperare la posta elettronica, sarà disponibile per il ripristino nelle cartelle Posta eliminata o Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="71d50-256">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="71d50-257">Inviare messaggi a Microsoft dalla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="71d50-257">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="71d50-258">Se la cassetta postale personalizzata è stata configurata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="71d50-258">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="71d50-259">Questo sposta in modo efficace un invio utente a un invio da amministratore.</span><span class="sxs-lookup"><span data-stu-id="71d50-259">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="71d50-260">Nella scheda **Cassetta postale** personalizzata selezionare un messaggio nell'elenco, fare clic sul pulsante **Azione** ed effettuare una delle seguenti selezioni:</span><span class="sxs-lookup"><span data-stu-id="71d50-260">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="71d50-261">**Segnala pulito**</span><span class="sxs-lookup"><span data-stu-id="71d50-261">**Report clean**</span></span>
- <span data-ttu-id="71d50-262">**Segnalare phishing**</span><span class="sxs-lookup"><span data-stu-id="71d50-262">**Report phishing**</span></span>
- <span data-ttu-id="71d50-263">**Segnalare malware**</span><span class="sxs-lookup"><span data-stu-id="71d50-263">**Report malware**</span></span>
- <span data-ttu-id="71d50-264">**Segnalare posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="71d50-264">**Report spam**</span></span>

![Opzioni del pulsante Azione](../../media/user-submission-custom-mailbox-action-button.png)
