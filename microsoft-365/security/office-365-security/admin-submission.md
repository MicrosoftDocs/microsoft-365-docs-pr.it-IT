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
ms.openlocfilehash: 4d0737d881334db9cc4aeda43037ab89d7444618
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577871"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="d0ca5-103">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0ca5-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="d0ca5-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online, gli amministratori possono utilizzare il portale degli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="d0ca5-105">Quando si invia un messaggio di posta elettronica, si ottengono informazioni su tutti i criteri che possono aver consentito la posta elettronica in arrivo nel tenant, nonché l'esame degli URL e degli allegati della posta.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="d0ca5-106">I criteri che possono aver consentito a un messaggio di posta elettronica includono l'elenco dei mittenti attendibili di un singolo utente e i criteri di livello tenant, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto)</span><span class="sxs-lookup"><span data-stu-id="d0ca5-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="d0ca5-107">Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="d0ca5-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d0ca5-108">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="d0ca5-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d0ca5-109">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d0ca5-110">Per passare direttamente alla pagina **invio** , utilizzare <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="d0ca5-111">È necessario disporre delle autorizzazioni per eseguire le procedure di questo argomento:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="d0ca5-112">Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d0ca5-113">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d0ca5-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d0ca5-114">**Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d0ca5-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="d0ca5-115">Per l'accesso in sola lettura al portale degli invii, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d0ca5-116">**Lettore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d0ca5-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d0ca5-117">**Gestione organizzazione in sola lettura** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d0ca5-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="d0ca5-118">Per ulteriori informazioni sul modo in cui gli utenti possono inviare messaggi e file a Microsoft, vedere [segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="d0ca5-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="d0ca5-119">Segnalare contenuti sospetti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0ca5-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="d0ca5-120">Nel centro sicurezza & conformità, accedere ai messaggi di invio dell'amministratore di **gestione delle minacce** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="d0ca5-121">Nella pagina **invii** che viene visualizzata, fare clic sul pulsante **nuovo invio** .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="d0ca5-122">Utilizzare il riquadro a comparsa **nuovo invio** che sembra inviare il messaggio, l'URL o l'allegato come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="d0ca5-123">Inviare un messaggio di posta elettronica discutibile a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0ca5-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="d0ca5-124">Nella sezione **tipo oggetto** selezionare **posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="d0ca5-125">Nella sezione **formato invio** , utilizzare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="d0ca5-126">**ID messaggio di rete**: questo è un valore GUID disponibile nell'intestazione **X-MS-Exchange-Organization-network-Message-ID** del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="d0ca5-127">**File**: fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="d0ca5-128">Nella finestra di dialogo che si apre, individuare e selezionare il file. eml o. msg, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="d0ca5-129">Nella sezione **destinatari** specificare uno o più destinatari a cui si desidera eseguire il controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="d0ca5-130">Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa di criteri dell'organizzazione o dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="d0ca5-131">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d0ca5-132">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d0ca5-133">**Avrebbe dovuto essere bloccato**: selezionare **posta indesiderata**, **phishing**o **malware**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="d0ca5-134">Se non si è sicuri, utilizzare il miglior giudizio.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="d0ca5-135">Se il filtro è stato ignorato a causa di criteri al momento dell'invio, verranno visualizzate le informazioni relative a tale criterio.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="d0ca5-136">Se il filtro non è stato bypassato a causa di uno o più criteri, l'analisi verrà completata in alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="d0ca5-137">Vedrai altre informazioni sull'invio facendo clic sul collegamento di stato.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="d0ca5-138">Questo include i risultati del controllo dei criteri e il verdetto di rianalisi.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="d0ca5-139">Si noti che non viene eseguito di nuovo il messaggio di posta elettronica tramite lo stack filtro completo ATP di Office 365 ma viene eseguita una nuova analisi parziale in base a determinati attributi di posta, URL o file.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="d0ca5-140">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-140">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio di URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="d0ca5-142">Inviare un URL sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0ca5-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="d0ca5-143">Nella sezione **tipo oggetto** selezionare **URL**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="d0ca5-144">Nella casella che viene visualizzata, immettere l'URL completo (ad esempio, <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="d0ca5-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="d0ca5-145">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d0ca5-146">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d0ca5-147">**Avrebbe dovuto essere bloccato**: selezionare **phishing** o **malware**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="d0ca5-148">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-148">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio tramite posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="d0ca5-150">Inviare un file sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0ca5-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="d0ca5-151">Nella sezione **tipo oggetto** selezionare **allegato**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="d0ca5-152">Fare clic su **Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-152">Click **Choose File**.</span></span> <span data-ttu-id="d0ca5-153">Nella finestra di dialogo che si apre, individuare e selezionare il file e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="d0ca5-154">Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="d0ca5-155">**Non deve essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="d0ca5-156">**Avrebbe dovuto essere bloccato**: il **malware** è l'unica scelta e viene selezionato automaticamente..</span><span class="sxs-lookup"><span data-stu-id="d0ca5-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="d0ca5-157">Al termine, fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-157">When you're finished, click the **Submit** button.</span></span>

![Esempio di invio degli allegati](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="d0ca5-159">Visualizzazione di invii di amministratore</span><span class="sxs-lookup"><span data-stu-id="d0ca5-159">View admin submissions</span></span>

1. <span data-ttu-id="d0ca5-160">Nel centro sicurezza & conformità, accedere ai messaggi di invio dell'amministratore di **gestione delle minacce** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="d0ca5-161">Nella pagina **invii** che viene visualizzata, verificare che la scheda **invii amministratore** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="d0ca5-162">Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare per **ID invio** (un valore GUID assegnato a ogni invio) immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d0ca5-163">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d0ca5-164">Per modificare i criteri di filtro, fare clic sul pulsante **ID invio** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="d0ca5-165">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-165">**Sender**</span></span>
- <span data-ttu-id="d0ca5-166">**Oggetto/URL/nome file**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="d0ca5-167">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-167">**Submitted by**</span></span>
- <span data-ttu-id="d0ca5-168">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-168">**Submission type**</span></span>
- <span data-ttu-id="d0ca5-169">**Stato**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-169">**Status**</span></span>

![Opzioni di filtro per invii di amministratore](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="d0ca5-171">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d0ca5-172">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="d0ca5-173">Al di sotto del grafico sono disponibili tre schede: **posta elettronica** (impostazione predefinita), **URL**e **allegato**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="d0ca5-174">Visualizzazione di invii di posta elettronica di amministratore</span><span class="sxs-lookup"><span data-stu-id="d0ca5-174">View admin email submissions</span></span>

<span data-ttu-id="d0ca5-175">Fare clic sulla scheda **posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-175">Click the **Email** tab.</span></span>

<span data-ttu-id="d0ca5-176">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d0ca5-177">**Data**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-177">**Date**</span></span>
- <span data-ttu-id="d0ca5-178">**ID invio**: valore GUID assegnato a ogni invio.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="d0ca5-179">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-180">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-181">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-181">**Sender**</span></span>
- <span data-ttu-id="d0ca5-182">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-183">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-183">**Submission type**</span></span>
- <span data-ttu-id="d0ca5-184">**Motivo per il recapito**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-184">**Delivery reason**</span></span>
- <span data-ttu-id="d0ca5-185">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-186">**Tipo di controllo**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-186">**Control type**</span></span>
- <span data-ttu-id="d0ca5-187">**Origine di controllo**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-187">**Control source**</span></span>

  <span data-ttu-id="d0ca5-188"><sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="d0ca5-189">Visualizzazione di invii di URL di amministrazione</span><span class="sxs-lookup"><span data-stu-id="d0ca5-189">View admin URL submissions</span></span>

<span data-ttu-id="d0ca5-190">Fare clic sulla scheda **URL** .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-190">Click the **URL** tab.</span></span>

<span data-ttu-id="d0ca5-191">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d0ca5-192">**Data**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-192">**Date**</span></span>
- <span data-ttu-id="d0ca5-193">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-193">**Submission ID**</span></span>
- <span data-ttu-id="d0ca5-194">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-195">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-196">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-196">**Submission type**</span></span>
- <span data-ttu-id="d0ca5-197">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="d0ca5-198"><sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="d0ca5-199">Visualizza invii degli allegati di amministratore</span><span class="sxs-lookup"><span data-stu-id="d0ca5-199">View admin attachment submissions</span></span>

<span data-ttu-id="d0ca5-200">Fare clic sulla scheda **allegati** .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="d0ca5-201">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d0ca5-202">**Data**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-202">**Date**</span></span>
- <span data-ttu-id="d0ca5-203">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-203">**Submission ID**</span></span>
- <span data-ttu-id="d0ca5-204">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-205">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-206">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-206">**Submission type**</span></span>
- <span data-ttu-id="d0ca5-207">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="d0ca5-208"><sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="d0ca5-209">Visualizzazione degli invii degli utenti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d0ca5-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="d0ca5-210">Se è stato distribuito il [componente aggiuntivo](enable-the-report-message-add-in.md)per i messaggi di report o si utilizza la creazione di report [incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), è possibile visualizzare gli utenti che segnalano nella scheda **invii utente** .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="d0ca5-211">Nel centro sicurezza & conformità, accedere ai messaggi di invio dell'amministratore di **gestione delle minacce** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="d0ca5-212">Nella pagina **invii** che viene visualizzata, fare clic sulla scheda **invii utente** .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="d0ca5-213">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d0ca5-214">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-214">**Submitted on**</span></span>
- <span data-ttu-id="d0ca5-215">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-216">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-217">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-217">**Sender**</span></span>
- <span data-ttu-id="d0ca5-218">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-219">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-219">**Submission type**</span></span>

<span data-ttu-id="d0ca5-220"><sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="d0ca5-221">Nella parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare in base al **mittente** immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d0ca5-222">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d0ca5-223">Per modificare i criteri di filtro, fare clic sul pulsante **mittente** e scegliere uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="d0ca5-224">**Dominio mittente**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-224">**Sender domain**</span></span>
- <span data-ttu-id="d0ca5-225">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-225">**Subject**</span></span>
- <span data-ttu-id="d0ca5-226">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-226">**Submitted by**</span></span>
- <span data-ttu-id="d0ca5-227">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-227">**Submission type**</span></span>
- <span data-ttu-id="d0ca5-228">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-228">**Sender IP**</span></span>

![Opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

<span data-ttu-id="d0ca5-230">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d0ca5-231">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="d0ca5-232">Visualizzare gli invii degli utenti alla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="d0ca5-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="d0ca5-233">Se è stata [configurata una cassetta postale personalizzata](user-submission.md) per la ricezione di messaggi segnalati dall'utente, è possibile visualizzare e inviare anche messaggi che sono stati recapitati alla cassetta postale di Reporting.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="d0ca5-234">Nel centro sicurezza & conformità, accedere ai messaggi di invio dell'amministratore di **gestione delle minacce** \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="d0ca5-235">Nella pagina **invii** che viene visualizzata, fare clic sulla scheda **cassetta postale personalizzata** .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="d0ca5-236">È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="d0ca5-237">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-237">**Submitted on**</span></span>
- <span data-ttu-id="d0ca5-238">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-239">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-240">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-240">**Sender**</span></span>
- <span data-ttu-id="d0ca5-241">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d0ca5-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="d0ca5-242">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-242">**Submission type**</span></span>

<span data-ttu-id="d0ca5-243">Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine ed è possibile filtrare in base a quanto **inserito** inserendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="d0ca5-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="d0ca5-244">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="d0ca5-245">Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="d0ca5-246">Nella finestra di dialogo che viene visualizzata, salvare il file. csv.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="d0ca5-247">Inviare messaggi a Microsoft dalla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="d0ca5-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="d0ca5-248">Se è stata configurata la cassetta postale personalizzata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="d0ca5-249">Questo consente di spostare efficacemente l'invio di un utente a un invio di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d0ca5-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="d0ca5-250">Nella scheda **cassetta postale personalizzata** , selezionare un messaggio nell'elenco, fare clic sul pulsante **azione** ed eseguire una delle selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0ca5-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="d0ca5-251">**Relazione pulita**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-251">**Report clean**</span></span>
- <span data-ttu-id="d0ca5-252">**Notifica di phishing**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-252">**Report phishing**</span></span>
- <span data-ttu-id="d0ca5-253">**Segnala malware**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-253">**Report malware**</span></span>
- <span data-ttu-id="d0ca5-254">**Segnalare la posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d0ca5-254">**Report spam**</span></span>

![Opzioni sul pulsante azione](../../media/user-submission-custom-mailbox-action-button.png)
