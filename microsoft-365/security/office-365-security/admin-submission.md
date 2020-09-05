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
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare il portale per gli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica sospetti, sospette mail di phishing, posta indesiderata e altre informazioni potenzialmente nocive, URL e file a Microsoft per l'analisi.
ms.openlocfilehash: 08d1633142bba7348cbc899f9cf9b2a1288c3743
ms.sourcegitcommit: 916fa2dacbc13287b49823176375259d7af03f86
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2020
ms.locfileid: "47394736"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="f8e43-103">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8e43-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="f8e43-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online, gli amministratori possono utilizzare il portale degli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="f8e43-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="f8e43-105">Quando si invia un messaggio di posta elettronica, si ottengono informazioni su tutti i criteri che possono aver consentito la posta elettronica in arrivo nel tenant, nonché l'esame degli URL e degli allegati della posta.</span><span class="sxs-lookup"><span data-stu-id="f8e43-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="f8e43-106">I criteri che possono aver consentito a un messaggio di posta elettronica includono l'elenco dei mittenti attendibili di un singolo utente e i criteri di livello tenant, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto)</span><span class="sxs-lookup"><span data-stu-id="f8e43-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="f8e43-107">Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f8e43-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f8e43-108">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="f8e43-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f8e43-109">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f8e43-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f8e43-110">Per passare direttamente alla pagina **invio** , utilizzare <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="f8e43-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="f8e43-111">Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8e43-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="f8e43-112">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f8e43-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="f8e43-113">**Gestione dell'organizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f8e43-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="f8e43-114">Si noti che l'appartenenza a questo gruppo di ruoli è necessaria per [visualizzare gli invii degli utenti alla cassetta postale personalizzata](#view-user-submissions-to-the-custom-mailbox) come descritto più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f8e43-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="f8e43-115">Per ulteriori informazioni sul modo in cui gli utenti possono inviare messaggi e file a Microsoft, vedere [segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f8e43-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="f8e43-116">Segnalare contenuti sospetti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8e43-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="f8e43-117">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**, verificare di essere nella scheda invii di **Amministrazione** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="f8e43-118">Utilizzare il riquadro a comparsa **nuovo invio** che sembra inviare il messaggio, l'URL o l'allegato come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f8e43-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="f8e43-119">Inviare un messaggio di posta elettronica discutibile a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8e43-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="f8e43-120">Nella sezione **tipo oggetto** selezionare **posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="f8e43-121">Nella sezione **formato invio** , utilizzare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="f8e43-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="f8e43-122">**ID messaggio di rete**: questo è un valore GUID disponibile nell'intestazione **X-MS-Exchange-Organization-network-Message-ID** del messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8e43-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="f8e43-123">**File**: fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="f8e43-124">Nella finestra di dialogo che si apre, individuare e selezionare il file. eml o. msg, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="f8e43-125">Nella sezione **destinatari** specificare uno o più destinatari a cui si desidera eseguire il controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="f8e43-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="f8e43-126">Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa di criteri dell'organizzazione o dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f8e43-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="f8e43-127">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8e43-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="f8e43-128">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="f8e43-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="f8e43-129">**Avrebbe dovuto essere bloccato**: selezionare **posta indesiderata**, **phishing**o **malware**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="f8e43-130">Se non si è sicuri, utilizzare il miglior giudizio.</span><span class="sxs-lookup"><span data-stu-id="f8e43-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="f8e43-131">Se il filtro è stato ignorato a causa di criteri al momento dell'invio, verranno visualizzate le informazioni relative a tale criterio.</span><span class="sxs-lookup"><span data-stu-id="f8e43-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="f8e43-132">Se il filtro non è stato bypassato a causa di uno o più criteri, l'analisi verrà completata in alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="f8e43-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="f8e43-133">Vedrai altre informazioni sull'invio facendo clic sul collegamento di stato.</span><span class="sxs-lookup"><span data-stu-id="f8e43-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="f8e43-134">Questo include i risultati del controllo dei criteri e il verdetto di rianalisi.</span><span class="sxs-lookup"><span data-stu-id="f8e43-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="f8e43-135">Si noti che non viene eseguito di nuovo il messaggio di posta elettronica tramite lo stack filtro completo ATP di Office 365 ma viene eseguita una nuova analisi parziale in base a determinati attributi di posta, URL o file.</span><span class="sxs-lookup"><span data-stu-id="f8e43-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="f8e43-136">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="f8e43-136">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio di URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="f8e43-138">Inviare un URL sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8e43-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="f8e43-139">Nella sezione **tipo oggetto** selezionare **URL**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="f8e43-140">Nella casella che viene visualizzata, immettere l'URL completo (ad esempio, <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="f8e43-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="f8e43-141">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8e43-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="f8e43-142">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="f8e43-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="f8e43-143">**Avrebbe dovuto essere bloccato**: selezionare **phishing** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="f8e43-144">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="f8e43-144">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio tramite posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="f8e43-146">Inviare un file sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8e43-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="f8e43-147">Nella sezione **tipo oggetto** selezionare **allegato**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="f8e43-148">Fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-148">Click **Choose File**.</span></span> <span data-ttu-id="f8e43-149">Nella finestra di dialogo che si apre, individuare e selezionare il file e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="f8e43-150">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8e43-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="f8e43-151">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="f8e43-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="f8e43-152">**Avrebbe dovuto essere bloccato**: il **malware** è l'unica scelta e viene selezionato automaticamente..</span><span class="sxs-lookup"><span data-stu-id="f8e43-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="f8e43-153">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="f8e43-153">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio degli allegati](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="f8e43-155">Visualizzazione di invii di amministratore</span><span class="sxs-lookup"><span data-stu-id="f8e43-155">View admin submissions</span></span>

<span data-ttu-id="f8e43-156">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**, verificare di essere nella scheda invii di **Amministrazione** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="f8e43-157">Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare per **ID invio** (un valore GUID assegnato a ogni invio) immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="f8e43-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="f8e43-158">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="f8e43-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="f8e43-159">Per modificare i criteri di filtro, fare clic sul pulsante **ID invio** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="f8e43-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="f8e43-160">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="f8e43-160">**Sender**</span></span>
- <span data-ttu-id="f8e43-161">**Oggetto/URL/nome file**</span><span class="sxs-lookup"><span data-stu-id="f8e43-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="f8e43-162">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="f8e43-162">**Submitted by**</span></span>
- <span data-ttu-id="f8e43-163">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="f8e43-163">**Submission type**</span></span>
- <span data-ttu-id="f8e43-164">**Stato**</span><span class="sxs-lookup"><span data-stu-id="f8e43-164">**Status**</span></span>

![Opzioni di filtro per invii di amministratore](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="f8e43-166">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="f8e43-167">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="f8e43-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="f8e43-168">Al di sotto del grafico sono disponibili tre schede: **posta elettronica** (impostazione predefinita), **URL**e **allegato**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-168">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="f8e43-169">Visualizzazione di invii di posta elettronica di amministratore</span><span class="sxs-lookup"><span data-stu-id="f8e43-169">View admin email submissions</span></span>

<span data-ttu-id="f8e43-170">Fare clic sulla scheda **posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="f8e43-170">Click the **Email** tab.</span></span>

<span data-ttu-id="f8e43-171">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="f8e43-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f8e43-172">**Data**</span><span class="sxs-lookup"><span data-stu-id="f8e43-172">**Date**</span></span>
- <span data-ttu-id="f8e43-173">**ID invio**: valore GUID assegnato a ogni invio.</span><span class="sxs-lookup"><span data-stu-id="f8e43-173">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="f8e43-174">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-175">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-176">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="f8e43-176">**Sender**</span></span>
- <span data-ttu-id="f8e43-177">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-178">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="f8e43-178">**Submission type**</span></span>
- <span data-ttu-id="f8e43-179">**Motivo per il recapito**</span><span class="sxs-lookup"><span data-stu-id="f8e43-179">**Delivery reason**</span></span>
- <span data-ttu-id="f8e43-180">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-181">**Tipo di controllo**</span><span class="sxs-lookup"><span data-stu-id="f8e43-181">**Control type**</span></span>
- <span data-ttu-id="f8e43-182">**Origine di controllo**</span><span class="sxs-lookup"><span data-stu-id="f8e43-182">**Control source**</span></span>

  <span data-ttu-id="f8e43-183"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="f8e43-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="f8e43-184">Visualizzazione di invii di URL di amministrazione</span><span class="sxs-lookup"><span data-stu-id="f8e43-184">View admin URL submissions</span></span>

<span data-ttu-id="f8e43-185">Fare clic sulla scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="f8e43-185">Click the **URL** tab.</span></span>

<span data-ttu-id="f8e43-186">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="f8e43-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f8e43-187">**Data**</span><span class="sxs-lookup"><span data-stu-id="f8e43-187">**Date**</span></span>
- <span data-ttu-id="f8e43-188">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="f8e43-188">**Submission ID**</span></span>
- <span data-ttu-id="f8e43-189">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-191">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="f8e43-191">**Submission type**</span></span>
- <span data-ttu-id="f8e43-192">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="f8e43-193"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="f8e43-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="f8e43-194">Visualizza invii degli allegati di amministratore</span><span class="sxs-lookup"><span data-stu-id="f8e43-194">View admin attachment submissions</span></span>

<span data-ttu-id="f8e43-195">Fare clic sulla scheda **allegati** .</span><span class="sxs-lookup"><span data-stu-id="f8e43-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="f8e43-196">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="f8e43-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f8e43-197">**Data**</span><span class="sxs-lookup"><span data-stu-id="f8e43-197">**Date**</span></span>
- <span data-ttu-id="f8e43-198">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="f8e43-198">**Submission ID**</span></span>
- <span data-ttu-id="f8e43-199">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-200">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-201">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="f8e43-201">**Submission type**</span></span>
- <span data-ttu-id="f8e43-202">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="f8e43-203"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="f8e43-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="f8e43-204">Visualizzazione degli invii degli utenti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f8e43-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="f8e43-205">Se è stato distribuito il [componente aggiuntivo](enable-the-report-message-add-in.md)per i messaggi di report o si utilizza la creazione di report [incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), è possibile visualizzare gli utenti che segnalano nella scheda **invii utente** .</span><span class="sxs-lookup"><span data-stu-id="f8e43-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="f8e43-206">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="f8e43-207">Selezionare la scheda **invii utente** e quindi fare clic su **nuovo invio**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="f8e43-208">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="f8e43-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f8e43-209">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="f8e43-209">**Submitted on**</span></span>
- <span data-ttu-id="f8e43-210">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-211">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-212">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="f8e43-212">**Sender**</span></span>
- <span data-ttu-id="f8e43-213">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-214">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="f8e43-214">**Submission type**</span></span>

<span data-ttu-id="f8e43-215"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="f8e43-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="f8e43-216">Nella parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare in base al **mittente** immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="f8e43-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="f8e43-217">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="f8e43-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="f8e43-218">Per modificare i criteri di filtro, fare clic sul pulsante **mittente** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="f8e43-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="f8e43-219">**Dominio mittente**</span><span class="sxs-lookup"><span data-stu-id="f8e43-219">**Sender domain**</span></span>
- <span data-ttu-id="f8e43-220">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="f8e43-220">**Subject**</span></span>
- <span data-ttu-id="f8e43-221">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="f8e43-221">**Submitted by**</span></span>
- <span data-ttu-id="f8e43-222">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="f8e43-222">**Submission type**</span></span>
- <span data-ttu-id="f8e43-223">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="f8e43-223">**Sender IP**</span></span>

![Opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

<span data-ttu-id="f8e43-225">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="f8e43-226">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="f8e43-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="f8e43-227">Visualizzare gli invii degli utenti alla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="f8e43-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="f8e43-228">**Se** è stata [configurata una cassetta postale personalizzata](user-submission.md) per la ricezione di messaggi segnalati dall'utente, è possibile visualizzare e inviare anche messaggi che sono stati recapitati alla cassetta postale di Reporting.</span><span class="sxs-lookup"><span data-stu-id="f8e43-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="f8e43-229">Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="f8e43-230">Selezionare la scheda **cassetta postale personalizzata** .</span><span class="sxs-lookup"><span data-stu-id="f8e43-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="f8e43-231">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="f8e43-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f8e43-232">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="f8e43-232">**Submitted on**</span></span>
- <span data-ttu-id="f8e43-233">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-234">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-235">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="f8e43-235">**Sender**</span></span>
- <span data-ttu-id="f8e43-236">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f8e43-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="f8e43-237">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="f8e43-237">**Submission type**</span></span>

<span data-ttu-id="f8e43-238">Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine ed è possibile filtrare in base a quanto **inserito** inserendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="f8e43-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="f8e43-239">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="f8e43-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="f8e43-240">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="f8e43-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="f8e43-241">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="f8e43-241">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="f8e43-242">Inviare messaggi a Microsoft dalla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="f8e43-242">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="f8e43-243">Se è stata configurata la cassetta postale personalizzata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="f8e43-243">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="f8e43-244">Questo consente di spostare efficacemente l'invio di un utente a un invio di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f8e43-244">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="f8e43-245">Nella scheda **cassetta postale personalizzata** , selezionare un messaggio nell'elenco, fare clic sul pulsante **azione** ed eseguire una delle selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8e43-245">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="f8e43-246">**Relazione pulita**</span><span class="sxs-lookup"><span data-stu-id="f8e43-246">**Report clean**</span></span>
- <span data-ttu-id="f8e43-247">**Notifica di phishing**</span><span class="sxs-lookup"><span data-stu-id="f8e43-247">**Report phishing**</span></span>
- <span data-ttu-id="f8e43-248">**Segnala malware**</span><span class="sxs-lookup"><span data-stu-id="f8e43-248">**Report malware**</span></span>
- <span data-ttu-id="f8e43-249">**Segnalare la posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="f8e43-249">**Report spam**</span></span>

![Opzioni sul pulsante azione](../../media/user-submission-custom-mailbox-action-button.png)
