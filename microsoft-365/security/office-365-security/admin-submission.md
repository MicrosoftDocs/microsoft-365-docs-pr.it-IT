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
description: Gli amministratori possono imparare a usare il portale Invii nel Centro sicurezza & conformità per inviare messaggi di posta elettronica sospetti, messaggi di phishing sospetti, posta indesiderata e altri messaggi, URL e file potenzialmente dannosi a Microsoft per l'analisi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7b4e6dfcb5900ed41ad3ab0b44fada93599f0b4b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288790"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="1cf3c-103">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1cf3c-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1cf3c-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-104">**Applies to**</span></span>
- [<span data-ttu-id="1cf3c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1cf3c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1cf3c-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="1cf3c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)


<span data-ttu-id="1cf3c-107">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online, gli amministratori possono usare il portale Invii nel Centro sicurezza & conformità per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="1cf3c-108">Quando si invia un messaggio di posta elettronica, si riceverà:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="1cf3c-109">**Controllo dell'autenticazione della posta** elettronica: dettagli sul fatto che l'autenticazione della posta elettronica sia stata superata o meno al momento del recapito.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="1cf3c-110">**Risultati dei criteri:** informazioni su eventuali criteri che potrebbero aver consentito o bloccato la posta elettronica in arrivo nel tenant, ignorando i verdetti del filtro del servizio.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="1cf3c-111">**Reputazione/detonazione del payload:** esame di eventuali URL e allegati nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="1cf3c-112">**Analisi dei voti:** revisione eseguita dai voti degli utenti per verificare se i messaggi sono dannosi o meno.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cf3c-113">La reputazione/detonazione del payload e l'analisi del grado non vengono eseguite in tutti i tenant.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="1cf3c-114">Le informazioni non possono uscire dall'organizzazione quando i dati non devono uscire dal limite del tenant per motivi di conformità.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="1cf3c-115">Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="1cf3c-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1cf3c-116">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="1cf3c-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1cf3c-117">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1cf3c-118">Per passare direttamente alla pagina **di** invio, usa <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="1cf3c-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="1cf3c-119">Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei seguenti gruppi di ruoli:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="1cf3c-120">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1cf3c-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="1cf3c-121">**Gestione dell'organizzazione** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="1cf3c-121">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="1cf3c-122">Si noti che l'appartenenza a questo gruppo di ruoli è necessaria per visualizzare gli invii degli utenti alla cassetta postale [personalizzata,](#view-user-submissions-to-the-custom-mailbox) come descritto più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="1cf3c-123">Per ulteriori informazioni su come gli utenti possono inviare messaggi e file a Microsoft, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="1cf3c-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="1cf3c-124">Segnalare contenuti sospetti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1cf3c-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="1cf3c-125">Nel Centro sicurezza & conformità passare  a Invii di gestione delle minacce, verificare di essere nella scheda Invii dell'amministratore e quindi fare clic \> su **Nuovo invio.** </span><span class="sxs-lookup"><span data-stu-id="1cf3c-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="1cf3c-126">Usa **il riquadro a comparsa** Nuovo invio visualizzato per inviare il messaggio, l'URL o l'allegato, come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="1cf3c-127">Inviare un messaggio di posta elettronica discutibile a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1cf3c-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="1cf3c-128">Nella sezione **Tipo di oggetto** selezionare Posta **elettronica.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="1cf3c-129">Nella sezione **Formato invio** usa una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="1cf3c-130">**ID** messaggio di rete: si tratta di un valore GUID disponibile nell'intestazione **X-MS-Exchange-Organization-Network-Message-Id** del messaggio o nell'intestazione **X-MS-Office365-Filtering-Correlation-Id** nei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="1cf3c-131">**File**: fare **clic su Scegli file.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="1cf3c-132">Nella finestra di dialogo visualizzata individuare e selezionare il file con estensione eml o msg e quindi fare clic su **Apri.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1cf3c-133">Gli amministratori con Defender per Office 365 Piano 1 o Piano 2 sono in grado di inviare messaggi vecchi di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="1cf3c-134">Gli altri amministratori potranno tornare indietro di 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="1cf3c-135">Nella sezione **Destinatari** specificare uno o più destinatari per i quali si desidera eseguire un controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="1cf3c-136">Il controllo dei criteri determinerà se l'analisi della posta elettronica ha ignorato l'analisi a causa dei criteri utente o dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="1cf3c-137">Nella sezione **Motivo dell'invio** seleziona una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="1cf3c-138">**Non dovrebbe essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="1cf3c-139">**Dovrebbe essere stato bloccato:** Selezionare **Posta indesiderata,** **Phishing** o **Malware.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="1cf3c-140">Se non sei sicuro, usa il tuo buon senso.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="1cf3c-141">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-141">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di invio di URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="1cf3c-143">Inviare un URL sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1cf3c-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="1cf3c-144">Nella sezione **Tipo di oggetto** selezionare **URL.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="1cf3c-145">Nella casella visualizzata immettere l'URL completo, ad esempio `https://www.fabrikam.com/marketing.html` .</span><span class="sxs-lookup"><span data-stu-id="1cf3c-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="1cf3c-146">Nella sezione **Motivo dell'invio** seleziona una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="1cf3c-147">**Non dovrebbe essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="1cf3c-148">**Dovrebbe essere stato bloccato:** selezionare **Phishing** o **Malware.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="1cf3c-149">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-149">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di invio di posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="1cf3c-151">Inviare un file sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1cf3c-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="1cf3c-152">Nella sezione **Tipo oggetto** selezionare **Allegato.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="1cf3c-153">Fare **clic su Scegli file.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-153">Click **Choose File**.</span></span> <span data-ttu-id="1cf3c-154">Nella finestra di dialogo visualizzata individuare e selezionare il file e quindi fare clic su **Apri.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="1cf3c-155">Nella sezione **Motivo dell'invio** seleziona una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="1cf3c-156">**Non dovrebbe essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="1cf3c-157">**Dovrebbe essere stato bloccato:** **il malware** è l'unica scelta ed è selezionato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="1cf3c-158">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-158">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di invio di allegati](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="1cf3c-160">Visualizzare gli invii di amministratori</span><span class="sxs-lookup"><span data-stu-id="1cf3c-160">View admin submissions</span></span>

<span data-ttu-id="1cf3c-161">Nel Centro sicurezza & conformità passare  a Invii di gestione delle minacce, verificare di essere nella scheda Invii dell'amministratore e quindi fare clic \> su **Nuovo invio.** </span><span class="sxs-lookup"><span data-stu-id="1cf3c-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="1cf3c-162">Nella parte superiore della pagina puoi immettere una data di inizio, una data di fine e , per impostazione predefinita, puoi filtrare in base **all'ID** invio (un valore GUID assegnato a ogni invio) immettendo un valore nella casella e facendo clic sul pulsante ![ ](../../media/scc-quarantine-refresh.png) Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="1cf3c-163">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="1cf3c-164">Per modificare i criteri di filtro, fai clic sul pulsante **ID invio** e scegli uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="1cf3c-165">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-165">**Sender**</span></span>
- <span data-ttu-id="1cf3c-166">**Oggetto/URL/Nome file**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="1cf3c-167">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-167">**Submitted by**</span></span>
- <span data-ttu-id="1cf3c-168">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-168">**Submission type**</span></span>
- <span data-ttu-id="1cf3c-169">**Stato**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-169">**Status**</span></span>

![Opzioni di filtro per gli invii di amministratori](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="1cf3c-171">Per esportare i risultati, fare clic su **Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="1cf3c-172">Nella finestra di dialogo visualizzata, salvare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="1cf3c-173">Sotto il grafico sono disponibili tre **schede:** Posta elettronica (impostazione predefinita), **URL** e **Allegato.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="1cf3c-174">Visualizzare gli invii di posta elettronica dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="1cf3c-174">View admin email submissions</span></span>

<span data-ttu-id="1cf3c-175">Fare clic sulla **scheda Posta** elettronica.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-175">Click the **Email** tab.</span></span>

<span data-ttu-id="1cf3c-176">È possibile fare clic **sul pulsante** Opzioni colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="1cf3c-177">**Data**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-177">**Date**</span></span>
- <span data-ttu-id="1cf3c-178">**ID invio:** un valore GUID assegnato a ogni invio.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="1cf3c-179">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-180">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-181">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-181">**Sender**</span></span>
- <span data-ttu-id="1cf3c-182">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-183">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-183">**Submission type**</span></span>
- <span data-ttu-id="1cf3c-184">**Motivo recapito**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-184">**Delivery reason**</span></span>
- <span data-ttu-id="1cf3c-185">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="1cf3c-186"><sup>\*</sup> Se si fa clic su questo valore, vengono visualizzate informazioni dettagliate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="1cf3c-187">Dettagli di nuova analisi dell'invio da parte dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="1cf3c-187">Admin submission rescan details</span></span>

<span data-ttu-id="1cf3c-188">I messaggi inviati negli invii di amministratori vengono nuovamente a scansione e i risultati vengono visualizzati nel riquadro a comparsa dei dettagli:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="1cf3c-189">Se si è verificato un errore nell'autenticazione della posta elettronica del mittente al momento del recapito.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="1cf3c-190">Informazioni su eventuali riscontri dei criteri che potrebbero aver influenzato o ignorato il verdetto di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="1cf3c-191">Risultati della detonazione correnti per verificare se gli URL o i file contenuti nel messaggio erano dannosi o meno.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="1cf3c-192">Feedback dei voti.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-192">Feedback from graders.</span></span>

<span data-ttu-id="1cf3c-193">Se è stata trovata una sostituzione, l'analisi dovrebbe essere completata dopo alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="1cf3c-194">Se non si è verificato un problema nell'autenticazione della posta elettronica o il recapito non è stato influenzato da una sostituzione, il feedback dei voti potrebbe richiedere fino a un giorno.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="1cf3c-195">Visualizzare gli invii di URL di amministrazione</span><span class="sxs-lookup"><span data-stu-id="1cf3c-195">View admin URL submissions</span></span>

<span data-ttu-id="1cf3c-196">Fare clic **sulla scheda URL.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-196">Click the **URL** tab.</span></span>

<span data-ttu-id="1cf3c-197">È possibile fare clic **sul pulsante** Opzioni colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="1cf3c-198">**Data**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-198">**Date**</span></span>
- <span data-ttu-id="1cf3c-199">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-199">**Submission ID**</span></span>
- <span data-ttu-id="1cf3c-200">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-202">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-202">**Submission type**</span></span>
- <span data-ttu-id="1cf3c-203">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="1cf3c-204"><sup>\*</sup> Se si fa clic su questo valore, vengono visualizzate informazioni dettagliate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="1cf3c-205">Visualizzare gli invii di allegati dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="1cf3c-205">View admin attachment submissions</span></span>

<span data-ttu-id="1cf3c-206">Fare clic **sulla scheda** Allegati.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="1cf3c-207">È possibile fare clic **sul pulsante** Opzioni colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="1cf3c-208">**Data**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-208">**Date**</span></span>
- <span data-ttu-id="1cf3c-209">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-209">**Submission ID**</span></span>
- <span data-ttu-id="1cf3c-210">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-211">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-212">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-212">**Submission type**</span></span>
- <span data-ttu-id="1cf3c-213">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="1cf3c-214"><sup>\*</sup> Se si fa clic su questo valore, vengono visualizzate informazioni dettagliate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="1cf3c-215">Visualizzare gli invii degli utenti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1cf3c-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="1cf3c-216">Se è stato distribuito il componente aggiuntivo [](enable-the-report-phish-add-in.md)Segnala [messaggio,](enable-the-report-message-add-in.md)Segnala phishing o gli utenti usano la segnalazione predefinita in Outlook  [sul Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)è possibile vedere quali utenti segnalano nella scheda Invii utente.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="1cf3c-217">Nel Centro sicurezza & conformità passare a **Invii di gestione** \> **delle minacce.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="1cf3c-218">Seleziona la **scheda Invii utente** e quindi fai clic su **Nuovo invio.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="1cf3c-219">È possibile fare clic **sul pulsante** Opzioni colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="1cf3c-220">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-220">**Submitted on**</span></span>
- <span data-ttu-id="1cf3c-221">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-222">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-223">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-223">**Sender**</span></span>
- <span data-ttu-id="1cf3c-224">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-225">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-225">**Submission type**</span></span>

<span data-ttu-id="1cf3c-226"><sup>\*</sup> Se si fa clic su questo valore, vengono visualizzate informazioni dettagliate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="1cf3c-227">Nella parte superiore della pagina è possibile immettere una data di inizio, una  data di fine e, per impostazione predefinita, è possibile filtrare in base al mittente immettendo un valore nella casella e facendo clic sul pulsante ![ ](../../media/scc-quarantine-refresh.png) Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="1cf3c-228">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="1cf3c-229">Per modificare i criteri di filtro, fare clic sul **pulsante Mittente** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="1cf3c-230">**Dominio del mittente**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-230">**Sender domain**</span></span>
- <span data-ttu-id="1cf3c-231">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-231">**Subject**</span></span>
- <span data-ttu-id="1cf3c-232">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-232">**Submitted by**</span></span>
- <span data-ttu-id="1cf3c-233">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-233">**Submission type**</span></span>
- <span data-ttu-id="1cf3c-234">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-234">**Sender IP**</span></span>

![Opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

<span data-ttu-id="1cf3c-236">Per esportare i risultati, fare clic su **Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="1cf3c-237">Nella finestra di dialogo visualizzata, salvare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="1cf3c-238">Visualizzare gli invii utente alla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="1cf3c-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="1cf3c-239">**Se** è stata [configurata una cassetta](user-submission.md) postale personalizzata per ricevere i messaggi segnalati dall'utente, è possibile visualizzare e inviare i messaggi recapitati alla cassetta postale di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="1cf3c-240">Nel Centro sicurezza & conformità passare a **Invii di gestione** \> **delle minacce.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="1cf3c-241">Selezionare la **scheda Cassetta postale** personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="1cf3c-242">È possibile fare clic **sul pulsante** Opzioni colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="1cf3c-243">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-243">**Submitted on**</span></span>
- <span data-ttu-id="1cf3c-244">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-245">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-246">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-246">**Sender**</span></span>
- <span data-ttu-id="1cf3c-247">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1cf3c-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="1cf3c-248">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-248">**Submission type**</span></span>

<span data-ttu-id="1cf3c-249">Nella parte superiore della pagina è possibile immettere una data di inizio, una data di fine e filtrare in base all'invio immettendo un valore nella casella e facendo clic sul pulsante  ![ ](../../media/scc-quarantine-refresh.png) Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="1cf3c-250">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="1cf3c-251">Per esportare i risultati, fare clic su **Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="1cf3c-252">Nella finestra di dialogo visualizzata, salvare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="1cf3c-253">Annullare gli invii utente</span><span class="sxs-lookup"><span data-stu-id="1cf3c-253">Undo user submissions</span></span>

<span data-ttu-id="1cf3c-254">Quando un utente invia un messaggio di posta elettronica sospetto alla cassetta postale personalizzata, l'utente e l'amministratore non hanno la possibilità di annullare l'invio.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="1cf3c-255">Se l'utente desidera recuperare la posta elettronica, sarà disponibile per il ripristino nelle cartelle Posta eliminata o Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="1cf3c-256">Inviare messaggi a Microsoft dalla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="1cf3c-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="1cf3c-257">Se la cassetta postale personalizzata è stata configurata per intercettare i messaggi segnalati dall'utente senza inviarli a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="1cf3c-258">In questo modo, l'invio di un utente viene spostato in un invio da amministratore.</span><span class="sxs-lookup"><span data-stu-id="1cf3c-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="1cf3c-259">Nella scheda **Cassetta postale** personalizzata, selezionare un messaggio nell'elenco, fare clic sul pulsante **Azione** ed effettuare una delle seguenti selezioni:</span><span class="sxs-lookup"><span data-stu-id="1cf3c-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="1cf3c-260">**Report pulito**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-260">**Report clean**</span></span>
- <span data-ttu-id="1cf3c-261">**Segnalare il phishing**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-261">**Report phishing**</span></span>
- <span data-ttu-id="1cf3c-262">**Segnalare malware**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-262">**Report malware**</span></span>
- <span data-ttu-id="1cf3c-263">**Segnalare la posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="1cf3c-263">**Report spam**</span></span>

![Opzioni del pulsante Azione](../../media/user-submission-custom-mailbox-action-button.png)
