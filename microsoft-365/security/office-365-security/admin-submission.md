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
description: Gli amministratori possono imparare a usare il portale invii nel centro sicurezza Microsoft 365 per inviare messaggi di posta elettronica sospetti, messaggi di phishing sospetti, posta indesiderata e altri messaggi, URL e allegati di posta elettronica potenzialmente dannosi a Microsoft per la nuova analisi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878689"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="5680a-103">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5680a-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5680a-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="5680a-104">**Applies to**</span></span>
- [<span data-ttu-id="5680a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5680a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5680a-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="5680a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="5680a-107">Nelle Microsoft 365 con cassette postali in Exchange Online, gli amministratori possono utilizzare il portale invii nel Centro sicurezza & conformità per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="5680a-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="5680a-108">Quando invii un messaggio di posta elettronica, ottieni:</span><span class="sxs-lookup"><span data-stu-id="5680a-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="5680a-109">**Controllo dell'autenticazione della** posta elettronica : Dettagli sul fatto che l'autenticazione della posta elettronica sia stata superata o meno al momento del recapito.</span><span class="sxs-lookup"><span data-stu-id="5680a-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="5680a-110">**Riscontri criteri:** informazioni su eventuali criteri che potrebbero aver consentito o bloccato la posta elettronica in arrivo nel tenant, ignorando i verdetti del filtro del servizio.</span><span class="sxs-lookup"><span data-stu-id="5680a-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="5680a-111">**Reputazione/detonazione del payload**: esame di eventuali URL e allegati nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="5680a-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="5680a-112">**Analisi grader**: Revisione eseguita dai grader umani per verificare se i messaggi sono dannosi.</span><span class="sxs-lookup"><span data-stu-id="5680a-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5680a-113">La reputazione/detonazione del payload e l'analisi del grado non vengono eseguite in tutti i tenant.</span><span class="sxs-lookup"><span data-stu-id="5680a-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="5680a-114">Le informazioni non possono uscire dall'organizzazione quando i dati non devono uscire dal limite del tenant per motivi di conformità.</span><span class="sxs-lookup"><span data-stu-id="5680a-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="5680a-115">Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="5680a-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5680a-116">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5680a-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5680a-117">Si apre il centro Microsoft 365 sicurezza all'indirizzo <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="5680a-117">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="5680a-118">Per passare direttamente alla **pagina Invii,** usa <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="5680a-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="5680a-119">Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="5680a-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="5680a-120">**Gestione dell'organizzazione** **o Lettore sicurezza** [nel centro sicurezza Microsoft 365 sicurezza](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="5680a-120">**Organization Management** or **Security Reader** in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  - <span data-ttu-id="5680a-121">**Gestione organizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="5680a-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="5680a-122">Si noti che l'appartenenza a questo gruppo di ruoli è necessaria per [visualizzare gli](#view-user-submissions-to-the-custom-mailbox) invii degli utenti alla cassetta postale personalizzata, come descritto più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5680a-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="5680a-123">Per ulteriori informazioni su come gli utenti possono inviare messaggi e file a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="5680a-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="5680a-124">Segnalare contenuti sospetti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5680a-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="5680a-125">Nel centro [Microsoft 365](../defender/overview-security-center.md)sicurezza, passare **a** Invii e verificare  di essere nella scheda Inviato per l'analisi e quindi fare clic su Invia a **Microsoft per la revisione.**</span><span class="sxs-lookup"><span data-stu-id="5680a-125">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Submissions** and verify that you're on the **Submitted for analysis** tab, and then click **Submit to Microsoft for review**.</span></span>

2. <span data-ttu-id="5680a-126">Usa il **riquadro a comparsa Invia** a Microsoft per la revisione che viene visualizzato per inviare il messaggio, l'URL o l'allegato di posta elettronica, come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5680a-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="5680a-127">Inviare un messaggio di posta elettronica discutibile a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5680a-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="5680a-128">Nella sezione **Seleziona il tipo di invio** seleziona Posta **elettronica.**</span><span class="sxs-lookup"><span data-stu-id="5680a-128">In the **Select the submission type** section, select **Email**.</span></span> <span data-ttu-id="5680a-129">Nella sezione **Aggiungere l'ID del messaggio di rete o caricare il file di posta** elettronica, utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5680a-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>

   - <span data-ttu-id="5680a-130">**Aggiungere l'ID** del messaggio di rete di posta elettronica : si tratta di un valore GUID disponibile nell'intestazione **X-MS-Exchange-Organization-Network-Message-Id** nel messaggio o nell'intestazione **X-MS-Office365-Filtering-Correlation-Id** nei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="5680a-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="5680a-131">**Upload il file di posta elettronica**: fare clic su Sfoglia **file**.</span><span class="sxs-lookup"><span data-stu-id="5680a-131">**Upload the email file**: Click **Browse files**.</span></span> <span data-ttu-id="5680a-132">Nella finestra di dialogo visualizzata individuare e selezionare il file con estensione eml o msg e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="5680a-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5680a-133">La possibilità di inviare messaggi vecchi di 30 giorni è stata temporaneamente sospesa per Defender per Office 365 clienti.</span><span class="sxs-lookup"><span data-stu-id="5680a-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="5680a-134">Gli amministratori potranno tornare indietro di 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="5680a-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="5680a-135">Nella sezione **Scegliere un destinatario con un problema** specificare il destinatario per cui si desidera eseguire un controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="5680a-135">In the **Choose a recipient who had an issue** section, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="5680a-136">Il controllo dei criteri determinerà se l'analisi dei messaggi di posta elettronica è stata ignorata a causa dei criteri dell'utente o dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5680a-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="5680a-137">Nella sezione **Selezionare un motivo per l'invio a Microsoft** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5680a-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>

   - <span data-ttu-id="5680a-138">**Non dovrebbe essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="5680a-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5680a-139">**Dovrebbe essere stato bloccato:** Selezionare **Posta indesiderata,** **Phishing** o **Malware.**</span><span class="sxs-lookup"><span data-stu-id="5680a-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="5680a-140">Se non sei sicuro, usa il tuo miglior giudizio.</span><span class="sxs-lookup"><span data-stu-id="5680a-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="5680a-141">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="5680a-141">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di invio di un nuovo URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="5680a-143">Inviare un URL sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5680a-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="5680a-144">Nella sezione **Seleziona il tipo di invio** seleziona **URL.**</span><span class="sxs-lookup"><span data-stu-id="5680a-144">In the **Select the submission type** section, select **URL**.</span></span> <span data-ttu-id="5680a-145">Nella casella visualizzata immettere l'URL completo, ad esempio `https://www.fabrikam.com/marketing.html` .</span><span class="sxs-lookup"><span data-stu-id="5680a-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="5680a-146">Nella sezione **Motivo invio** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5680a-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="5680a-147">**Non dovrebbe essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="5680a-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5680a-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span><span class="sxs-lookup"><span data-stu-id="5680a-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="5680a-149">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="5680a-149">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di nuovo invio di posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="5680a-151">Inviare un allegato di posta elettronica sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5680a-151">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="5680a-152">Nella sezione **Selezionare il tipo di invio** selezionare Allegato di posta **elettronica.**</span><span class="sxs-lookup"><span data-stu-id="5680a-152">In the **Select the submission type** section, select **Email attachment**.</span></span>

2. <span data-ttu-id="5680a-153">Fare **clic su Scegli file**.</span><span class="sxs-lookup"><span data-stu-id="5680a-153">Click **Choose File**.</span></span> <span data-ttu-id="5680a-154">Nella finestra di dialogo visualizzata individuare e selezionare il file e quindi fare clic su **Apri.**</span><span class="sxs-lookup"><span data-stu-id="5680a-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="5680a-155">Nella sezione **Motivo invio** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5680a-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="5680a-156">**Non dovrebbe essere stato bloccato**</span><span class="sxs-lookup"><span data-stu-id="5680a-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5680a-157">**Dovrebbe essere stato bloccato:** **il malware** è l'unica scelta e viene selezionato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5680a-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="5680a-158">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="5680a-158">When you're finished, click the **Submit** button.</span></span>

   ![Esempio di nuovo invio allegato](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="5680a-160">Visualizzare gli elementi inviati per l'analisi</span><span class="sxs-lookup"><span data-stu-id="5680a-160">View items Submitted for analysis</span></span>

<span data-ttu-id="5680a-161">Nel centro Microsoft 365 sicurezza, passare **a** Invii e verificare di essere nella **scheda Inviato per l'analisi**</span><span class="sxs-lookup"><span data-stu-id="5680a-161">In the Microsoft 365 security center, go to **Submissions**, and verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="5680a-162">Nella barra dei comandi al centro della pagina è possibile immettere una data di inizio, una data di fine e, per impostazione predefinita, è possibile filtrare in base **all'ID** invio (un valore GUID assegnato a ogni invio) immettendo un valore nella casella e facendo clic sul pulsante ![ Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="5680a-162">In the command bar in the middle of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5680a-163">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="5680a-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5680a-164">Per modificare i criteri di filtro, fare clic **sul pulsante Filtro** e scegliere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5680a-164">To change the filter criteria, click the **Filter** button and choose one of the following values:</span></span>

- <span data-ttu-id="5680a-165">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5680a-165">**Sender**</span></span>
- <span data-ttu-id="5680a-166">**Subject/URL/File name**</span><span class="sxs-lookup"><span data-stu-id="5680a-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="5680a-167">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="5680a-167">**Submitted by**</span></span>
- <span data-ttu-id="5680a-168">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="5680a-168">**Submission type**</span></span>
- <span data-ttu-id="5680a-169">**Stato**</span><span class="sxs-lookup"><span data-stu-id="5680a-169">**Status**</span></span>

![Nuove opzioni di filtro per gli invii di amministratori](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="5680a-171">Per esportare i risultati, fare clic **su Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.**</span><span class="sxs-lookup"><span data-stu-id="5680a-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5680a-172">Nella finestra di dialogo visualizzata, salvare il file .csv file.</span><span class="sxs-lookup"><span data-stu-id="5680a-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="5680a-173">Sotto il grafico sono disponibili tre schede: **Posta** elettronica (impostazione predefinita), **URL** e **Allegato di posta elettronica.**</span><span class="sxs-lookup"><span data-stu-id="5680a-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Email attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="5680a-174">Visualizzare gli invii di posta elettronica dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="5680a-174">View admin email submissions</span></span>

<span data-ttu-id="5680a-175">È possibile fare clic **sul pulsante Personalizza** colonne nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="5680a-175">You can click the **Customize columns** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5680a-176">**Data**</span><span class="sxs-lookup"><span data-stu-id="5680a-176">**Date**</span></span>
- <span data-ttu-id="5680a-177">**ID invio:** valore GUID assegnato a ogni invio.</span><span class="sxs-lookup"><span data-stu-id="5680a-177">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="5680a-178">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-178">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-179">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-179">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-180">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5680a-180">**Sender**</span></span>
- <span data-ttu-id="5680a-181">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-181">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-182">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="5680a-182">**Submission type**</span></span>
- <span data-ttu-id="5680a-183">**Motivo recapito**</span><span class="sxs-lookup"><span data-stu-id="5680a-183">**Delivery reason**</span></span>
- <span data-ttu-id="5680a-184">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-184">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="5680a-185"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="5680a-185"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="5680a-186">Dettagli dell'analisi dell'invio dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="5680a-186">Admin submission rescan details</span></span>

<span data-ttu-id="5680a-187">I messaggi inviati negli invii di amministratori vengono sottoposti a nuova analisi e i risultati vengono visualizzati nel riquadro a comparsa dei dettagli degli invii:</span><span class="sxs-lookup"><span data-stu-id="5680a-187">Messages that are submitted in admin submissions are rescanned and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="5680a-188">Se si è verificato un errore nell'autenticazione della posta elettronica del mittente al momento del recapito.</span><span class="sxs-lookup"><span data-stu-id="5680a-188">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="5680a-189">Informazioni su eventuali riscontri dei criteri che potrebbero aver influenzato o sostituito il verdetto di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="5680a-189">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="5680a-190">Risultati della detonazione correnti per verificare se gli URL o i file contenuti nel messaggio erano dannosi o meno.</span><span class="sxs-lookup"><span data-stu-id="5680a-190">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="5680a-191">Feedback dei gradi.</span><span class="sxs-lookup"><span data-stu-id="5680a-191">Feedback from graders.</span></span>

<span data-ttu-id="5680a-192">Se è stata trovata una sostituzione, la nuova analisi dovrebbe essere completata dopo alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="5680a-192">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="5680a-193">Se non si è verificato un problema nell'autenticazione della posta elettronica o il recapito non è stato influenzato da una sostituzione, il feedback dei voti potrebbe richiedere fino a un giorno.</span><span class="sxs-lookup"><span data-stu-id="5680a-193">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="5680a-194">Visualizzare gli invii di URL di amministratore</span><span class="sxs-lookup"><span data-stu-id="5680a-194">View admin URL submissions</span></span>

<span data-ttu-id="5680a-195">Fare clic **sulla scheda URL.**</span><span class="sxs-lookup"><span data-stu-id="5680a-195">Click the **URL** tab.</span></span>

<span data-ttu-id="5680a-196">È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="5680a-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5680a-197">**Data**</span><span class="sxs-lookup"><span data-stu-id="5680a-197">**Date**</span></span>
- <span data-ttu-id="5680a-198">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="5680a-198">**Submission ID**</span></span>
- <span data-ttu-id="5680a-199">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-200">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-200">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-201">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="5680a-201">**Submission type**</span></span>
- <span data-ttu-id="5680a-202">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="5680a-203"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="5680a-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-email-attachment-submissions"></a><span data-ttu-id="5680a-204">Visualizzare gli invii di allegati di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5680a-204">View email attachment submissions</span></span>

<span data-ttu-id="5680a-205">Fare clic **sulla scheda** Allegati.</span><span class="sxs-lookup"><span data-stu-id="5680a-205">Click the **Attachments** tab.</span></span>

<span data-ttu-id="5680a-206">È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="5680a-206">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5680a-207">**Data**</span><span class="sxs-lookup"><span data-stu-id="5680a-207">**Date**</span></span>
- <span data-ttu-id="5680a-208">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="5680a-208">**Submission ID**</span></span>
- <span data-ttu-id="5680a-209">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-209">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-210">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-210">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-211">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="5680a-211">**Submission type**</span></span>
- <span data-ttu-id="5680a-212">**Stato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-212">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="5680a-213"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="5680a-213"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="5680a-214">Visualizzare gli invii degli utenti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5680a-214">View user submissions to Microsoft</span></span>

<span data-ttu-id="5680a-215">Se è stato distribuito il componente aggiuntivo Segnala [messaggio,](enable-the-report-message-add-in.md)il componente aggiuntivo Segnala [phishing](enable-the-report-phish-add-in.md)o gli utenti utilizzano la creazione di report  incorporati in [Outlook sul Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)è possibile visualizzare i report degli utenti nella scheda Invii utente.</span><span class="sxs-lookup"><span data-stu-id="5680a-215">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="5680a-216">Nel Centro sicurezza & conformità passare a **Gestione minacce** \> **Invii**.</span><span class="sxs-lookup"><span data-stu-id="5680a-216">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="5680a-217">Seleziona la **scheda Invii utente** e quindi fai clic su **Nuovo invio.**</span><span class="sxs-lookup"><span data-stu-id="5680a-217">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="5680a-218">È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="5680a-218">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5680a-219">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="5680a-219">**Submitted on**</span></span>
- <span data-ttu-id="5680a-220">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-220">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-221">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-221">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-222">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5680a-222">**Sender**</span></span>
- <span data-ttu-id="5680a-223">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-223">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-224">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="5680a-224">**Submission type**</span></span>

<span data-ttu-id="5680a-225"><sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="5680a-225"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="5680a-226">Nella parte superiore della pagina è possibile immettere una data di inizio, una  data di fine e, per impostazione predefinita, è possibile filtrare in base al mittente immettendo un valore nella casella e facendo clic sul ![ pulsante Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="5680a-226">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5680a-227">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="5680a-227">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5680a-228">Per modificare i criteri di filtro, fare clic **sul pulsante Mittente** e scegliere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5680a-228">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="5680a-229">**Dominio del mittente**</span><span class="sxs-lookup"><span data-stu-id="5680a-229">**Sender domain**</span></span>
- <span data-ttu-id="5680a-230">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="5680a-230">**Subject**</span></span>
- <span data-ttu-id="5680a-231">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="5680a-231">**Submitted by**</span></span>
- <span data-ttu-id="5680a-232">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="5680a-232">**Submission type**</span></span>
- <span data-ttu-id="5680a-233">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="5680a-233">**Sender IP**</span></span>

![Nuove opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

<span data-ttu-id="5680a-235">Per esportare i risultati, fare clic **su Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.**</span><span class="sxs-lookup"><span data-stu-id="5680a-235">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5680a-236">Nella finestra di dialogo visualizzata, salvare il file .csv file.</span><span class="sxs-lookup"><span data-stu-id="5680a-236">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="5680a-237">Visualizzare gli invii utente alla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="5680a-237">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="5680a-238">**Se** è stata [configurata una cassetta](user-submission.md) postale personalizzata per ricevere i messaggi segnalati dall'utente, è possibile visualizzare e inviare i messaggi recapitati alla cassetta postale di segnalazione.</span><span class="sxs-lookup"><span data-stu-id="5680a-238">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="5680a-239">Nel Centro sicurezza & conformità passare a **Gestione minacce** \> **Invii**.</span><span class="sxs-lookup"><span data-stu-id="5680a-239">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="5680a-240">Selezionare la **scheda Cassetta postale** personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5680a-240">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="5680a-241">È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:</span><span class="sxs-lookup"><span data-stu-id="5680a-241">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5680a-242">**Inviato il**</span><span class="sxs-lookup"><span data-stu-id="5680a-242">**Submitted on**</span></span>
- <span data-ttu-id="5680a-243">**Inviato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-243">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-244">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-244">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-245">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5680a-245">**Sender**</span></span>
- <span data-ttu-id="5680a-246">**Indirizzo IP mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5680a-246">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5680a-247">**Tipo di invio**</span><span class="sxs-lookup"><span data-stu-id="5680a-247">**Submission type**</span></span>

<span data-ttu-id="5680a-248">Nella parte superiore della pagina è possibile immettere una data di inizio, una data di fine e filtrare in base a **Inviato** immettendo un valore nella casella e facendo clic sul ![ pulsante Aggiorna ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="5680a-248">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5680a-249">È possibile immettere più valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="5680a-249">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5680a-250">Per esportare i risultati, fare clic **su Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.**</span><span class="sxs-lookup"><span data-stu-id="5680a-250">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5680a-251">Nella finestra di dialogo visualizzata, salvare il file .csv file.</span><span class="sxs-lookup"><span data-stu-id="5680a-251">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="5680a-252">Se le organizzazioni sono configurate per l'invio solo alla cassetta postale personalizzata, i messaggi segnalati non verranno inviati per la nuova analisi e i risultati nel portale Messaggi segnalati dall'utente saranno sempre vuoti.</span><span class="sxs-lookup"><span data-stu-id="5680a-252">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="5680a-253">Annullare gli invii utente</span><span class="sxs-lookup"><span data-stu-id="5680a-253">Undo user submissions</span></span>

<span data-ttu-id="5680a-254">Una volta che un utente invia un messaggio di posta elettronica sospetto alla cassetta postale personalizzata, l'utente e l'amministratore non hanno la possibilità di annullare l'invio.</span><span class="sxs-lookup"><span data-stu-id="5680a-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="5680a-255">Se l'utente desidera recuperare la posta elettronica, sarà disponibile per il ripristino nelle cartelle Posta eliminata o Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="5680a-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="5680a-256">Inviare messaggi a Microsoft dalla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="5680a-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="5680a-257">Se la cassetta postale personalizzata è stata configurata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="5680a-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="5680a-258">Questo sposta in modo efficace un invio utente a un invio da amministratore.</span><span class="sxs-lookup"><span data-stu-id="5680a-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="5680a-259">Nella scheda **Messaggi segnalati dall'utente** selezionare un messaggio nell'elenco, fare clic sul pulsante **Azione** ed effettuare una delle seguenti selezioni:</span><span class="sxs-lookup"><span data-stu-id="5680a-259">On the **User reported messages** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="5680a-260">**Segnala pulito**</span><span class="sxs-lookup"><span data-stu-id="5680a-260">**Report clean**</span></span>
- <span data-ttu-id="5680a-261">**Segnalare phishing**</span><span class="sxs-lookup"><span data-stu-id="5680a-261">**Report phishing**</span></span>
- <span data-ttu-id="5680a-262">**Segnalare malware**</span><span class="sxs-lookup"><span data-stu-id="5680a-262">**Report malware**</span></span>
- <span data-ttu-id="5680a-263">**Segnalare posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="5680a-263">**Report spam**</span></span>

![Nuove opzioni sul pulsante Azione](../../media/user-submission-custom-mailbox-action-button.png)
