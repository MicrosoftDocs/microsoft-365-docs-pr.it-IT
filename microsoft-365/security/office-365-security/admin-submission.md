---
title: Invii di amministratore
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
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare il portale per gli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica sospetti, sospette mail di phishing, posta indesiderata e altre informazioni potenzialmente nocive, URL e file a Microsoft per l'analisi.
ms.openlocfilehash: ae84c9ca111c7e7056ae97abff20471c474dccb2
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209752"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="4b21e-103">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b21e-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="4b21e-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online, gli amministratori possono utilizzare il portale degli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="4b21e-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="4b21e-105">Quando si invia un messaggio di posta elettronica, si ottengono informazioni su tutti i criteri che possono aver consentito la posta elettronica in arrivo nel tenant, nonché l'esame degli URL e degli allegati della posta.</span><span class="sxs-lookup"><span data-stu-id="4b21e-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="4b21e-106">I criteri che possono aver consentito a un messaggio di posta elettronica includono l'elenco dei mittenti attendibili di un singolo utente e i criteri di livello tenant, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto)</span><span class="sxs-lookup"><span data-stu-id="4b21e-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="4b21e-107">Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="4b21e-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4b21e-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4b21e-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4b21e-109">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4b21e-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4b21e-110">Per passare direttamente alla pagina **invio** , utilizzare <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="4b21e-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="4b21e-111">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="4b21e-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="4b21e-112">Per aggiungere, modificare ed eliminare i criteri di protezione da posta indesiderata, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione**, **amministratore sicurezza**o **lettore di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="4b21e-112">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="4b21e-113">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4b21e-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="4b21e-114">Per ulteriori informazioni sul modo in cui gli utenti possono inviare messaggi e file a Microsoft, vedere [segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="4b21e-114">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="4b21e-115">Segnalare contenuti sospetti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b21e-115">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="4b21e-116">Nel centro sicurezza & conformità, accedere ai messaggi di invio dell'amministratore di **gestione delle minacce** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-116">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="4b21e-117">Nella pagina **invii** che viene visualizzata, fare clic sul pulsante **nuovo invio** .</span><span class="sxs-lookup"><span data-stu-id="4b21e-117">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="4b21e-118">Utilizzare il riquadro a comparsa **nuovo invio** che sembra inviare il messaggio, l'URL o l'allegato come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4b21e-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="4b21e-119">Inviare un messaggio di posta elettronica discutibile a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b21e-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="4b21e-120">Nella sezione **tipo oggetto** selezionare **posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="4b21e-121">Nella sezione **formato invio** , utilizzare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="4b21e-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="4b21e-122">**ID messaggio di rete**: questo è un valore GUID disponibile nell'intestazione **X-MS-Exchange-Organization-network-Message-ID** del messaggio.</span><span class="sxs-lookup"><span data-stu-id="4b21e-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="4b21e-123">**File**: fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="4b21e-124">Nella finestra di dialogo che si apre, individuare e selezionare il file. eml o. msg, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="4b21e-125">Nella sezione **destinatari** specificare uno o più destinatari a cui si desidera eseguire il controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="4b21e-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="4b21e-126">Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa di criteri dell'organizzazione o dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4b21e-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="4b21e-127">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b21e-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="4b21e-128">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="4b21e-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="4b21e-129">**Avrebbe dovuto essere bloccato**: selezionare **posta indesiderata**, **phishing**o **malware**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="4b21e-130">Se non si è sicuri, utilizzare il miglior giudizio.</span><span class="sxs-lookup"><span data-stu-id="4b21e-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="4b21e-131">Se il filtro è stato ignorato a causa di criteri al momento dell'invio, verranno visualizzate le informazioni relative a tale criterio.</span><span class="sxs-lookup"><span data-stu-id="4b21e-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="4b21e-132">Se il filtro non è stato bypassato a causa di uno o più criteri, l'analisi verrà completata in alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="4b21e-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="4b21e-133">Vedrai altre informazioni sull'invio facendo clic sul collegamento di stato.</span><span class="sxs-lookup"><span data-stu-id="4b21e-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="4b21e-134">Questo include i risultati del controllo dei criteri e il verdetto di rianalisi.</span><span class="sxs-lookup"><span data-stu-id="4b21e-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="4b21e-135">Si noti che non viene eseguito di nuovo il messaggio di posta elettronica tramite lo stack filtro completo ATP di Office 365 ma viene eseguita una nuova analisi parziale in base a determinati attributi di posta, URL o file.</span><span class="sxs-lookup"><span data-stu-id="4b21e-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="4b21e-136">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="4b21e-136">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio di URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="4b21e-138">Inviare un URL sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b21e-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="4b21e-139">Nella sezione **tipo oggetto** selezionare **URL**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="4b21e-140">Nella casella che viene visualizzata, immettere l'URL completo (ad esempio, <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="4b21e-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="4b21e-141">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b21e-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="4b21e-142">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="4b21e-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="4b21e-143">**Avrebbe dovuto essere bloccato**: selezionare **phishing** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="4b21e-144">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="4b21e-144">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio tramite posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="4b21e-146">Inviare un file sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b21e-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="4b21e-147">Nella sezione **tipo oggetto** selezionare **allegato**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="4b21e-148">Fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-148">Click **Choose File**.</span></span> <span data-ttu-id="4b21e-149">Nella finestra di dialogo che si apre, individuare e selezionare il file e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="4b21e-150">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b21e-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="4b21e-151">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="4b21e-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="4b21e-152">**Avrebbe dovuto essere bloccato**: il **malware** è l'unica scelta e viene selezionato automaticamente..</span><span class="sxs-lookup"><span data-stu-id="4b21e-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="4b21e-153">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="4b21e-153">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio degli allegati](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="4b21e-155">Visualizzazione di invii di amministratore</span><span class="sxs-lookup"><span data-stu-id="4b21e-155">View admin submissions</span></span>

1. <span data-ttu-id="4b21e-156">Nel centro sicurezza & conformità, accedere ai messaggi di invio dell'amministratore di **gestione delle minacce** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-156">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="4b21e-157">Nella pagina **invii** che viene visualizzata, verificare che la scheda **invii amministratore** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="4b21e-157">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="4b21e-158">Vicino alla parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare in base all' **ID di invio** immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="4b21e-158">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="4b21e-159">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="4b21e-159">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="4b21e-160">Per modificare i criteri di filtro, fare clic sul pulsante **ID invio** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="4b21e-160">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="4b21e-161">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="4b21e-161">**Sender**</span></span>
- <span data-ttu-id="4b21e-162">**Oggetto/URL/nome file**</span><span class="sxs-lookup"><span data-stu-id="4b21e-162">**Subject/URL/File name**</span></span>
- <span data-ttu-id="4b21e-163">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="4b21e-163">**Submitted by**</span></span>
- <span data-ttu-id="4b21e-164">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="4b21e-164">**Submission type**</span></span>
- <span data-ttu-id="4b21e-165">**Stato**</span><span class="sxs-lookup"><span data-stu-id="4b21e-165">**Status**</span></span>

![Opzioni di filtro per invii di amministratore](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="4b21e-167">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-167">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="4b21e-168">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="4b21e-168">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="4b21e-169">Al di sotto del grafico sono disponibili tre schede: **posta elettronica** (impostazione predefinita), **URL**e **allegato**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-169">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="4b21e-170">Visualizzazione di invii di posta elettronica di amministratore</span><span class="sxs-lookup"><span data-stu-id="4b21e-170">View admin email submissions</span></span>

<span data-ttu-id="4b21e-171">Fare clic sulla scheda **posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="4b21e-171">Click the **Email** tab.</span></span>

<span data-ttu-id="4b21e-172">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="4b21e-172">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4b21e-173">**Data**</span><span class="sxs-lookup"><span data-stu-id="4b21e-173">**Date**</span></span>
- <span data-ttu-id="4b21e-174">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="4b21e-174">**Submission ID**</span></span>
- <span data-ttu-id="4b21e-175">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-175">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-176">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-176">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-177">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="4b21e-177">**Sender**</span></span>
- <span data-ttu-id="4b21e-178">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-178">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-179">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="4b21e-179">**Submission type**</span></span>
- <span data-ttu-id="4b21e-180">**Motivo per il recapito**</span><span class="sxs-lookup"><span data-stu-id="4b21e-180">**Delivery reason**</span></span>
- <span data-ttu-id="4b21e-181">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-181">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-182">**Tipo di controllo**</span><span class="sxs-lookup"><span data-stu-id="4b21e-182">**Control type**</span></span>
- <span data-ttu-id="4b21e-183">**Origine di controllo**</span><span class="sxs-lookup"><span data-stu-id="4b21e-183">**Control source**</span></span>

  <span data-ttu-id="4b21e-184"><sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="4b21e-184"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="4b21e-185">Visualizzazione di invii di URL di amministrazione</span><span class="sxs-lookup"><span data-stu-id="4b21e-185">View admin URL submissions</span></span>

<span data-ttu-id="4b21e-186">Fare clic sulla scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="4b21e-186">Click the **URL** tab.</span></span>

<span data-ttu-id="4b21e-187">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="4b21e-187">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4b21e-188">**Data**</span><span class="sxs-lookup"><span data-stu-id="4b21e-188">**Date**</span></span>
- <span data-ttu-id="4b21e-189">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="4b21e-189">**Submission ID**</span></span>
- <span data-ttu-id="4b21e-190">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-190">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-191">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-191">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-192">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="4b21e-192">**Submission type**</span></span>
- <span data-ttu-id="4b21e-193">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-193">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="4b21e-194"><sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="4b21e-194"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="4b21e-195">Visualizza invii degli allegati di amministratore</span><span class="sxs-lookup"><span data-stu-id="4b21e-195">View admin attachment submissions</span></span>

<span data-ttu-id="4b21e-196">Fare clic sulla scheda **allegati** .</span><span class="sxs-lookup"><span data-stu-id="4b21e-196">Click the **Attachments** tab.</span></span>

<span data-ttu-id="4b21e-197">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="4b21e-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4b21e-198">**Data**</span><span class="sxs-lookup"><span data-stu-id="4b21e-198">**Date**</span></span>
- <span data-ttu-id="4b21e-199">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="4b21e-199">**Submission ID**</span></span>
- <span data-ttu-id="4b21e-200">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-201">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-201">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-202">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="4b21e-202">**Submission type**</span></span>
- <span data-ttu-id="4b21e-203">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="4b21e-204"><sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="4b21e-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="4b21e-205">Visualizzazione degli invii degli utenti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b21e-205">View user submissions to Microsoft</span></span>

<span data-ttu-id="4b21e-206">Se è stato distribuito il [componente aggiuntivo](enable-the-report-message-add-in.md)per i messaggi di report o si utilizza la creazione di report [incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), è possibile visualizzare gli utenti che segnalano nella scheda **invii utente** .</span><span class="sxs-lookup"><span data-stu-id="4b21e-206">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="4b21e-207">Nel centro sicurezza & conformità, accedere ai messaggi di invio dell'amministratore di **gestione delle minacce** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-207">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="4b21e-208">Nella pagina **invii** che viene visualizzata, fare clic sulla scheda **invii utente** .</span><span class="sxs-lookup"><span data-stu-id="4b21e-208">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="4b21e-209">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="4b21e-209">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4b21e-210">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="4b21e-210">**Submitted on**</span></span>
- <span data-ttu-id="4b21e-211">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-211">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-212">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-212">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-213">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="4b21e-213">**Sender**</span></span>
- <span data-ttu-id="4b21e-214">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-214">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-215">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="4b21e-215">**Submission type**</span></span>

<span data-ttu-id="4b21e-216"><sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="4b21e-216"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="4b21e-217">Nella parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare in base al **mittente** immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="4b21e-217">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="4b21e-218">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="4b21e-218">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="4b21e-219">Per modificare i criteri di filtro, fare clic sul pulsante **mittente** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="4b21e-219">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="4b21e-220">**Dominio del mittente**</span><span class="sxs-lookup"><span data-stu-id="4b21e-220">**Sender domain**</span></span>
- <span data-ttu-id="4b21e-221">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="4b21e-221">**Subject**</span></span>
- <span data-ttu-id="4b21e-222">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="4b21e-222">**Submitted by**</span></span>
- <span data-ttu-id="4b21e-223">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="4b21e-223">**Submission type**</span></span>
- <span data-ttu-id="4b21e-224">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="4b21e-224">**Sender IP**</span></span>

![Opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

<span data-ttu-id="4b21e-226">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-226">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="4b21e-227">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="4b21e-227">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="4b21e-228">Visualizzare gli invii degli utenti alla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="4b21e-228">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="4b21e-229">Se è stata [configurata una cassetta postale personalizzata](user-submission.md) per la ricezione di messaggi segnalati dall'utente, è possibile visualizzare e inviare anche messaggi che sono stati recapitati alla cassetta postale di Reporting.</span><span class="sxs-lookup"><span data-stu-id="4b21e-229">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="4b21e-230">Nel centro sicurezza & conformità, accedere ai messaggi di invio dell'amministratore di **gestione delle minacce** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-230">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="4b21e-231">Nella pagina **invii** che viene visualizzata, fare clic sulla scheda **cassetta postale personalizzata** .</span><span class="sxs-lookup"><span data-stu-id="4b21e-231">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="4b21e-232">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="4b21e-232">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4b21e-233">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="4b21e-233">**Submitted on**</span></span>
- <span data-ttu-id="4b21e-234">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-234">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-235">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-235">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-236">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="4b21e-236">**Sender**</span></span>
- <span data-ttu-id="4b21e-237">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4b21e-237">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="4b21e-238">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="4b21e-238">**Submission type**</span></span>

<span data-ttu-id="4b21e-239">Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine ed è possibile filtrare in base a quanto **inserito** inserendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="4b21e-239">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="4b21e-240">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="4b21e-240">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="4b21e-241">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="4b21e-241">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="4b21e-242">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="4b21e-242">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="4b21e-243">Inviare messaggi a Microsoft dalla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="4b21e-243">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="4b21e-244">Se è stata configurata la cassetta postale personalizzata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="4b21e-244">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="4b21e-245">Questo consente di spostare efficacemente l'invio di un utente a un invio di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4b21e-245">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="4b21e-246">Nella scheda **cassetta postale personalizzata** , selezionare un messaggio nell'elenco, fare clic sul pulsante **azione** ed eseguire una delle selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b21e-246">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="4b21e-247">**Relazione pulita**</span><span class="sxs-lookup"><span data-stu-id="4b21e-247">**Report clean**</span></span>
- <span data-ttu-id="4b21e-248">**Notifica di phishing**</span><span class="sxs-lookup"><span data-stu-id="4b21e-248">**Report phishing**</span></span>
- <span data-ttu-id="4b21e-249">**Segnala malware**</span><span class="sxs-lookup"><span data-stu-id="4b21e-249">**Report malware**</span></span>
- <span data-ttu-id="4b21e-250">**Segnalare la posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="4b21e-250">**Report spam**</span></span>

![Opzioni sul pulsante azione](../../media/user-submission-custom-mailbox-action-button.png)
