---
title: Invii di amministratore
f1.keywords:
- NOCSH
ms.author: chrisda
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
ms.openlocfilehash: 4bb0cd95daecfcba18ca1560e4c4780455b40157
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446720"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="84400-103">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="84400-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="84400-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online, gli amministratori possono utilizzare il portale degli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="84400-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="84400-105">Quando si invia un messaggio di posta elettronica, si ottengono informazioni su tutti i criteri che possono aver consentito la posta elettronica in arrivo nel tenant, nonché l'esame degli URL e degli allegati della posta.</span><span class="sxs-lookup"><span data-stu-id="84400-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="84400-106">I criteri che possono aver consentito a un messaggio di posta elettronica includono l'elenco dei mittenti attendibili di un singolo utente e i criteri di livello tenant, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto)</span><span class="sxs-lookup"><span data-stu-id="84400-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="84400-107">Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="84400-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="84400-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="84400-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="84400-109">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="84400-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="84400-110">Per passare direttamente alla pagina **invio** , utilizzare <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="84400-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="84400-111">Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="84400-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="84400-112">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="84400-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="84400-113">**Gestione dell'organizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="84400-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="84400-114">Si noti che l'appartenenza a questo gruppo di ruoli è necessaria per [visualizzare gli invii degli utenti alla cassetta postale personalizzata](#view-user-submissions-to-the-custom-mailbox) come descritto più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="84400-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="84400-115">Per ulteriori informazioni sul modo in cui gli utenti possono inviare messaggi e file a Microsoft, vedere [segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="84400-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="84400-116">Segnalare contenuti sospetti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="84400-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="84400-117">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**, verificare di essere nella scheda invii di **Amministrazione** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="84400-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="84400-118">Utilizzare il riquadro a comparsa **nuovo invio** che sembra inviare il messaggio, l'URL o l'allegato come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="84400-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="84400-119">Inviare un messaggio di posta elettronica discutibile a Microsoft</span><span class="sxs-lookup"><span data-stu-id="84400-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="84400-120">Nella sezione **tipo oggetto** selezionare **posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="84400-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="84400-121">Nella sezione **formato invio** , utilizzare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="84400-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="84400-122">**ID messaggio di rete**: questo è un valore GUID disponibile nell'intestazione **X-MS-Exchange-Organization-network-Message-ID** del messaggio.</span><span class="sxs-lookup"><span data-stu-id="84400-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="84400-123">**File**: fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="84400-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="84400-124">Nella finestra di dialogo che si apre, individuare e selezionare il file. eml o. msg, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="84400-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="84400-125">Nella sezione **destinatari** specificare uno o più destinatari a cui si desidera eseguire il controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="84400-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="84400-126">Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa di criteri dell'organizzazione o dell'utente.</span><span class="sxs-lookup"><span data-stu-id="84400-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="84400-127">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84400-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="84400-128">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="84400-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="84400-129">**Avrebbe dovuto essere bloccato**: selezionare **posta indesiderata**, **phishing**o **malware**.</span><span class="sxs-lookup"><span data-stu-id="84400-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="84400-130">Se non si è sicuri, utilizzare il miglior giudizio.</span><span class="sxs-lookup"><span data-stu-id="84400-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="84400-131">Se il filtro è stato ignorato a causa di criteri al momento dell'invio, verranno visualizzate le informazioni relative a tale criterio.</span><span class="sxs-lookup"><span data-stu-id="84400-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="84400-132">Se il filtro non è stato bypassato a causa di uno o più criteri, l'analisi verrà completata in alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="84400-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="84400-133">Vedrai altre informazioni sull'invio facendo clic sul collegamento di stato.</span><span class="sxs-lookup"><span data-stu-id="84400-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="84400-134">Questo include i risultati del controllo dei criteri e il verdetto di rianalisi.</span><span class="sxs-lookup"><span data-stu-id="84400-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="84400-135">Si noti che non viene eseguito di nuovo il messaggio di posta elettronica tramite lo stack filtro completo ATP di Office 365 ma viene eseguita una nuova analisi parziale in base a determinati attributi di posta, URL o file.</span><span class="sxs-lookup"><span data-stu-id="84400-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="84400-136">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="84400-136">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio di URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="84400-138">Inviare un URL sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="84400-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="84400-139">Nella sezione **tipo oggetto** selezionare **URL**.</span><span class="sxs-lookup"><span data-stu-id="84400-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="84400-140">Nella casella che viene visualizzata, immettere l'URL completo (ad esempio, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="84400-140">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="84400-141">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84400-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="84400-142">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="84400-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="84400-143">**Avrebbe dovuto essere bloccato**: selezionare **phishing** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="84400-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="84400-144">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="84400-144">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio tramite posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="84400-146">Inviare un file sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="84400-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="84400-147">Nella sezione **tipo oggetto** selezionare **allegato**.</span><span class="sxs-lookup"><span data-stu-id="84400-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="84400-148">Fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="84400-148">Click **Choose File**.</span></span> <span data-ttu-id="84400-149">Nella finestra di dialogo che si apre, individuare e selezionare il file e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="84400-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="84400-150">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84400-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="84400-151">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="84400-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="84400-152">**Avrebbe dovuto essere bloccato**: il **malware** è l'unica scelta e viene selezionato automaticamente..</span><span class="sxs-lookup"><span data-stu-id="84400-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="84400-153">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="84400-153">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio degli allegati](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="84400-155">Visualizzazione di invii di amministratore</span><span class="sxs-lookup"><span data-stu-id="84400-155">View admin submissions</span></span>

<span data-ttu-id="84400-156">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**, verificare di essere nella scheda invii di **Amministrazione** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="84400-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="84400-157">Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare per **ID invio** (un valore GUID assegnato a ogni invio) immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="84400-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="84400-158">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="84400-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="84400-159">Per modificare i criteri di filtro, fare clic sul pulsante **ID invio** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="84400-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="84400-160">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="84400-160">**Sender**</span></span>
- <span data-ttu-id="84400-161">**Oggetto/URL/nome file**</span><span class="sxs-lookup"><span data-stu-id="84400-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="84400-162">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="84400-162">**Submitted by**</span></span>
- <span data-ttu-id="84400-163">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="84400-163">**Submission type**</span></span>
- <span data-ttu-id="84400-164">**Stato**</span><span class="sxs-lookup"><span data-stu-id="84400-164">**Status**</span></span>

![Opzioni di filtro per invii di amministratore](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="84400-166">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="84400-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="84400-167">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="84400-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="84400-168">Al di sotto del grafico sono disponibili tre schede: **posta elettronica** (impostazione predefinita), **URL**e **allegato**.</span><span class="sxs-lookup"><span data-stu-id="84400-168">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="84400-169">Visualizzazione di invii di posta elettronica di amministratore</span><span class="sxs-lookup"><span data-stu-id="84400-169">View admin email submissions</span></span>

<span data-ttu-id="84400-170">Fare clic sulla scheda **posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="84400-170">Click the **Email** tab.</span></span>

<span data-ttu-id="84400-171">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="84400-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="84400-172">**Data**</span><span class="sxs-lookup"><span data-stu-id="84400-172">**Date**</span></span>
- <span data-ttu-id="84400-173">**ID invio**: valore GUID assegnato a ogni invio.</span><span class="sxs-lookup"><span data-stu-id="84400-173">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="84400-174">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-175">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-176">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="84400-176">**Sender**</span></span>
- <span data-ttu-id="84400-177">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-178">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="84400-178">**Submission type**</span></span>
- <span data-ttu-id="84400-179">**Motivo per il recapito**</span><span class="sxs-lookup"><span data-stu-id="84400-179">**Delivery reason**</span></span>
- <span data-ttu-id="84400-180">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-181">**Tipo di controllo**</span><span class="sxs-lookup"><span data-stu-id="84400-181">**Control type**</span></span>
- <span data-ttu-id="84400-182">**Origine di controllo**</span><span class="sxs-lookup"><span data-stu-id="84400-182">**Control source**</span></span>

  <span data-ttu-id="84400-183"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="84400-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="84400-184">Visualizzazione di invii di URL di amministrazione</span><span class="sxs-lookup"><span data-stu-id="84400-184">View admin URL submissions</span></span>

<span data-ttu-id="84400-185">Fare clic sulla scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="84400-185">Click the **URL** tab.</span></span>

<span data-ttu-id="84400-186">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="84400-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="84400-187">**Data**</span><span class="sxs-lookup"><span data-stu-id="84400-187">**Date**</span></span>
- <span data-ttu-id="84400-188">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="84400-188">**Submission ID**</span></span>
- <span data-ttu-id="84400-189">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-191">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="84400-191">**Submission type**</span></span>
- <span data-ttu-id="84400-192">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="84400-193"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="84400-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="84400-194">Visualizza invii degli allegati di amministratore</span><span class="sxs-lookup"><span data-stu-id="84400-194">View admin attachment submissions</span></span>

<span data-ttu-id="84400-195">Fare clic sulla scheda **allegati** .</span><span class="sxs-lookup"><span data-stu-id="84400-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="84400-196">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="84400-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="84400-197">**Data**</span><span class="sxs-lookup"><span data-stu-id="84400-197">**Date**</span></span>
- <span data-ttu-id="84400-198">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="84400-198">**Submission ID**</span></span>
- <span data-ttu-id="84400-199">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-200">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-201">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="84400-201">**Submission type**</span></span>
- <span data-ttu-id="84400-202">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="84400-203"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="84400-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="84400-204">Visualizzazione degli invii degli utenti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="84400-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="84400-205">Se è stato distribuito il [componente aggiuntivo](enable-the-report-message-add-in.md)per i messaggi di report o si utilizza la creazione di report [incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), è possibile visualizzare gli utenti che segnalano nella scheda **invii utente** .</span><span class="sxs-lookup"><span data-stu-id="84400-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="84400-206">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="84400-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="84400-207">Selezionare la scheda **invii utente** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="84400-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="84400-208">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="84400-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="84400-209">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="84400-209">**Submitted on**</span></span>
- <span data-ttu-id="84400-210">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-211">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-212">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="84400-212">**Sender**</span></span>
- <span data-ttu-id="84400-213">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-214">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="84400-214">**Submission type**</span></span>

<span data-ttu-id="84400-215"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="84400-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="84400-216">Nella parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare in base al **mittente** immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="84400-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="84400-217">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="84400-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="84400-218">Per modificare i criteri di filtro, fare clic sul pulsante **mittente** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="84400-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="84400-219">**Dominio mittente**</span><span class="sxs-lookup"><span data-stu-id="84400-219">**Sender domain**</span></span>
- <span data-ttu-id="84400-220">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="84400-220">**Subject**</span></span>
- <span data-ttu-id="84400-221">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="84400-221">**Submitted by**</span></span>
- <span data-ttu-id="84400-222">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="84400-222">**Submission type**</span></span>
- <span data-ttu-id="84400-223">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="84400-223">**Sender IP**</span></span>

![Opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

<span data-ttu-id="84400-225">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="84400-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="84400-226">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="84400-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="84400-227">Visualizzare gli invii degli utenti alla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="84400-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="84400-228">**Se** è stata [configurata una cassetta postale personalizzata](user-submission.md) per la ricezione di messaggi segnalati dall'utente, è possibile visualizzare e inviare anche messaggi che sono stati recapitati alla cassetta postale di Reporting.</span><span class="sxs-lookup"><span data-stu-id="84400-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="84400-229">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="84400-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="84400-230">Selezionare la scheda **cassetta postale personalizzata** .</span><span class="sxs-lookup"><span data-stu-id="84400-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="84400-231">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="84400-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="84400-232">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="84400-232">**Submitted on**</span></span>
- <span data-ttu-id="84400-233">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-234">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-235">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="84400-235">**Sender**</span></span>
- <span data-ttu-id="84400-236">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84400-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="84400-237">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="84400-237">**Submission type**</span></span>

<span data-ttu-id="84400-238">Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine ed è possibile filtrare in base a quanto **inserito** inserendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="84400-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="84400-239">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="84400-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="84400-240">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="84400-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="84400-241">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="84400-241">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="84400-242">Inviare messaggi a Microsoft dalla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="84400-242">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="84400-243">Se è stata configurata la cassetta postale personalizzata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="84400-243">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="84400-244">Questo consente di spostare efficacemente l'invio di un utente a un invio di amministratore.</span><span class="sxs-lookup"><span data-stu-id="84400-244">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="84400-245">Nella scheda **cassetta postale personalizzata** , selezionare un messaggio nell'elenco, fare clic sul pulsante **azione** ed eseguire una delle selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84400-245">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="84400-246">**Relazione pulita**</span><span class="sxs-lookup"><span data-stu-id="84400-246">**Report clean**</span></span>
- <span data-ttu-id="84400-247">**Notifica di phishing**</span><span class="sxs-lookup"><span data-stu-id="84400-247">**Report phishing**</span></span>
- <span data-ttu-id="84400-248">**Segnala malware**</span><span class="sxs-lookup"><span data-stu-id="84400-248">**Report malware**</span></span>
- <span data-ttu-id="84400-249">**Segnalare la posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="84400-249">**Report spam**</span></span>

![Opzioni sul pulsante azione](../../media/user-submission-custom-mailbox-action-button.png)
