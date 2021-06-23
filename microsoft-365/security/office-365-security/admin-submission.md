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
description: Gli amministratori possono imparare a usare il portale invii nel portale di Microsoft 365 Defender per inviare messaggi di posta elettronica sospetti, messaggi di phishing sospetti, posta indesiderata e altri messaggi, URL e allegati di posta elettronica potenzialmente dannosi a Microsoft per la nuova analisi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab25757c79b7978400e98fa36d48163e1681e7c1
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062033"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="dfa01-103">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="dfa01-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dfa01-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="dfa01-104">**Applies to**</span></span>
- [<span data-ttu-id="dfa01-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dfa01-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="dfa01-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="dfa01-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="dfa01-107">Nelle Microsoft 365 con cassette postali di Exchange Online, gli amministratori possono utilizzare il portale invii nel portale di Microsoft 365 Defender per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="dfa01-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="dfa01-108">Quando invii un messaggio di posta elettronica, ottieni:</span><span class="sxs-lookup"><span data-stu-id="dfa01-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="dfa01-109">**Controllo dell'autenticazione della** posta elettronica : Dettagli sul fatto che l'autenticazione della posta elettronica sia stata superata o meno al momento del recapito.</span><span class="sxs-lookup"><span data-stu-id="dfa01-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="dfa01-110">**Riscontri criteri:** informazioni su eventuali criteri che potrebbero aver consentito o bloccato la posta elettronica in arrivo nel tenant, ignorando i verdetti del filtro del servizio.</span><span class="sxs-lookup"><span data-stu-id="dfa01-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="dfa01-111">**Reputazione/detonazione del payload**: esame di eventuali URL e allegati nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="dfa01-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="dfa01-112">**Analisi grader**: Revisione eseguita dai grader umani per verificare se i messaggi sono dannosi.</span><span class="sxs-lookup"><span data-stu-id="dfa01-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfa01-113">La reputazione/detonazione del payload e l'analisi del grado non vengono eseguite in tutti i tenant.</span><span class="sxs-lookup"><span data-stu-id="dfa01-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="dfa01-114">Le informazioni non possono uscire dall'organizzazione quando i dati non devono uscire dal limite del tenant per motivi di conformità.</span><span class="sxs-lookup"><span data-stu-id="dfa01-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="dfa01-115">Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="dfa01-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dfa01-116">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="dfa01-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dfa01-117">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="dfa01-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="dfa01-118">Per passare direttamente alla **pagina Invii,** usa <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="dfa01-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="dfa01-119">Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfa01-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="dfa01-120">**Gestione dell'organizzazione** **o Lettore sicurezza** [nel portale Microsoft 365 Defender sicurezza](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="dfa01-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="dfa01-121">**Gestione organizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="dfa01-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="dfa01-122">Si noti che l'appartenenza a questo gruppo di ruoli è necessaria per [visualizzare gli](#view-user-submissions-to-microsoft) invii degli utenti alla cassetta postale personalizzata, come descritto più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="dfa01-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="dfa01-123">Per ulteriori informazioni su come gli utenti possono inviare messaggi e file a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="dfa01-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="dfa01-124">Segnalare contenuti sospetti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="dfa01-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="dfa01-125">Nel portale Microsoft 365 Defender, passare a Invia tramite **posta elettronica & collaborazione** \> **Invii.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-125">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="dfa01-126">Nella pagina **Invii** verificare  che la scheda Inviato per l'analisi sia selezionata e quindi fare clic su Icona Annuncio ![ Invia a Microsoft per ](../../media/m365-cc-sc-create-icon.png) **l'analisi.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-126">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="dfa01-127">Usa il **riquadro a comparsa Invia** a Microsoft per la revisione che viene visualizzato per inviare il messaggio, l'URL o l'allegato di posta elettronica, come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="dfa01-127">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="dfa01-128">Inviare un messaggio di posta elettronica discutibile a Microsoft</span><span class="sxs-lookup"><span data-stu-id="dfa01-128">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="dfa01-129">Nella casella **Seleziona il tipo di invio,** verificare che l'opzione **Posta** elettronica sia selezionata nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="dfa01-129">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="dfa01-130">Nella sezione **Aggiungere l'ID del messaggio di rete o caricare il file di posta** elettronica, utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfa01-130">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="dfa01-131">**Aggiungere l'ID** del messaggio di rete di posta elettronica : si tratta di un valore GUID disponibile nell'intestazione **X-MS-Exchange-Organization-Network-Message-Id** nel messaggio o nell'intestazione **X-MS-Office365-Filtering-Correlation-Id** nei messaggi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="dfa01-131">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="dfa01-132">**Upload il file di posta elettronica (con estensione msg o eml):** fare clic **su Sfoglia file**.</span><span class="sxs-lookup"><span data-stu-id="dfa01-132">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="dfa01-133">Nella finestra di dialogo visualizzata individuare e selezionare il file con estensione eml o msg e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="dfa01-133">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dfa01-134">La possibilità di inviare messaggi vecchi di 30 giorni è stata temporaneamente sospesa per Defender per Office 365 clienti.</span><span class="sxs-lookup"><span data-stu-id="dfa01-134">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="dfa01-135">Gli amministratori potranno tornare indietro di 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="dfa01-135">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="dfa01-136">Nella casella **Scegliere un destinatario che ha avuto un** problema specificare il destinatario per cui si desidera eseguire un controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="dfa01-136">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="dfa01-137">Il controllo dei criteri determinerà se l'analisi dei messaggi di posta elettronica è stata ignorata a causa dei criteri dell'utente o dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dfa01-137">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="dfa01-138">Nella sezione **Selezionare un motivo per l'invio a Microsoft** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfa01-138">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="dfa01-139">**Non dovrebbe essere stato bloccato (falso positivo)**</span><span class="sxs-lookup"><span data-stu-id="dfa01-139">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="dfa01-140">**Dovrebbe essere stato** bloccato: nella sezione Il messaggio di posta elettronica dovrebbe essere stato categorizzato come visualizzato, selezionare uno dei valori seguenti (se non si è sicuri, utilizzare la valutazione migliore): </span><span class="sxs-lookup"><span data-stu-id="dfa01-140">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="dfa01-141">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="dfa01-141">**Phish**</span></span>
     - <span data-ttu-id="dfa01-142">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="dfa01-142">**Spam**</span></span>
     - <span data-ttu-id="dfa01-143">**Malware**</span><span class="sxs-lookup"><span data-stu-id="dfa01-143">**Malware**</span></span>

5. <span data-ttu-id="dfa01-144">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="dfa01-144">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dfa01-145">![Esempio di invio di un nuovo URL](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="dfa01-145">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="dfa01-146">Inviare un URL sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="dfa01-146">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="dfa01-147">Nella casella **Seleziona il tipo di invio** seleziona **URL** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="dfa01-147">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="dfa01-148">Nella casella **URL** visualizzata immettere l'URL completo, ad esempio `https://www.fabrikam.com/marketing.html` .</span><span class="sxs-lookup"><span data-stu-id="dfa01-148">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="dfa01-149">Nella sezione **Selezionare un motivo per l'invio a Microsoft** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfa01-149">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="dfa01-150">**Non dovrebbe essere stato bloccato (falso positivo)**</span><span class="sxs-lookup"><span data-stu-id="dfa01-150">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="dfa01-151">**Dovrebbe essere stato bloccato:** nella sezione **Questo URL** dovrebbe essere stato classificato come visualizzato, selezionare **Phish** o **Malware.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-151">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="dfa01-152">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="dfa01-152">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dfa01-153">![Esempio di nuovo invio di posta elettronica](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="dfa01-153">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="dfa01-154">Inviare un allegato di posta elettronica sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="dfa01-154">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="dfa01-155">Nella casella **Seleziona il tipo di invio** seleziona **File** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="dfa01-155">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="dfa01-156">Nella sezione **File** visualizzata fare clic su **Sfoglia file.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-156">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="dfa01-157">Nella finestra di dialogo visualizzata individuare e selezionare il file e quindi fare clic su **Apri.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-157">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="dfa01-158">Nella sezione **Selezionare un motivo per l'invio a Microsoft** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfa01-158">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="dfa01-159">**Non dovrebbe essere stato bloccato (falso positivo)**</span><span class="sxs-lookup"><span data-stu-id="dfa01-159">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="dfa01-160">**Dovrebbe essere stato bloccato:** nella sezione Questo **URL** dovrebbe essere stato classificato come visualizzato, **Malware** è l'unica scelta e viene selezionato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dfa01-160">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="dfa01-161">Al termine, fare clic sul **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="dfa01-161">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dfa01-162">![Esempio di nuovo invio allegato](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="dfa01-162">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="dfa01-163">Visualizzare gli invii di amministratori a Microsoft</span><span class="sxs-lookup"><span data-stu-id="dfa01-163">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="dfa01-164">Nel portale Microsoft 365 Defender, passare a Invia tramite **posta elettronica & collaborazione** \> **Invii.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-164">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="dfa01-165">Nella pagina **Invii** verificare che la scheda **Inviato per l'analisi** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="dfa01-165">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="dfa01-166">È possibile ordinare le voci facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="dfa01-166">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="dfa01-167">Fare **clic su Personalizza** colonne per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="dfa01-167">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="dfa01-168">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="dfa01-168">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="dfa01-169">**Nome invio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-169">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-170">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-170">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-171">**Data di invio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-171">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-172">**Tipo di invio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-172">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-173">**Motivo dell'invio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-173">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-174">**Stato nuova analisi**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-174">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-175">**Risultato dell'analisi**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-175">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-176">**Verdetto filtro**</span><span class="sxs-lookup"><span data-stu-id="dfa01-176">**Filter verdict**</span></span>
     - <span data-ttu-id="dfa01-177">**Motivo recapito/blocco**</span><span class="sxs-lookup"><span data-stu-id="dfa01-177">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="dfa01-178">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="dfa01-178">**Submission ID**</span></span>
     - <span data-ttu-id="dfa01-179">**ID messaggio di rete/ID oggetto**</span><span class="sxs-lookup"><span data-stu-id="dfa01-179">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="dfa01-180">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="dfa01-180">**Direction**</span></span>
     - <span data-ttu-id="dfa01-181">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="dfa01-181">**Sender IP**</span></span>
     - <span data-ttu-id="dfa01-182">**Livello di conformità in blocco (BCL)**</span><span class="sxs-lookup"><span data-stu-id="dfa01-182">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="dfa01-183">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="dfa01-183">**Destination**</span></span>
     - <span data-ttu-id="dfa01-184">**Azione dei criteri**</span><span class="sxs-lookup"><span data-stu-id="dfa01-184">**Policy action**</span></span>
     - <span data-ttu-id="dfa01-185">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="dfa01-185">**Submitted by**</span></span>

     <span data-ttu-id="dfa01-186">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-186">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="dfa01-187">Per filtrare le voci, fare clic su **Filtro.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-187">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="dfa01-188">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="dfa01-188">The available filters are:</span></span>
     - <span data-ttu-id="dfa01-189">**Date submitted**: **Start date e** End **date**.</span><span class="sxs-lookup"><span data-stu-id="dfa01-189">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="dfa01-190">**Tipo di invio:** **Posta** elettronica, **URL** o **File.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-190">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="dfa01-191">**ID invio:** valore GUID assegnato a ogni invio.</span><span class="sxs-lookup"><span data-stu-id="dfa01-191">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="dfa01-192">**ID messaggio di rete**</span><span class="sxs-lookup"><span data-stu-id="dfa01-192">**Network Message ID**</span></span>
     - <span data-ttu-id="dfa01-193">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="dfa01-193">**Sender**</span></span>

     <span data-ttu-id="dfa01-194">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-194">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="dfa01-195">![Nuove opzioni di filtro per gli invii di amministratori](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="dfa01-195">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="dfa01-196">Per raggruppare le voci, fare clic **su Gruppo** e selezionare uno dei valori seguenti nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="dfa01-196">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="dfa01-197">**Nessuna**</span><span class="sxs-lookup"><span data-stu-id="dfa01-197">**None**</span></span>
     - <span data-ttu-id="dfa01-198">**Type**</span><span class="sxs-lookup"><span data-stu-id="dfa01-198">**Type**</span></span>
     - <span data-ttu-id="dfa01-199">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="dfa01-199">**Reason**</span></span>
     - <span data-ttu-id="dfa01-200">**Stato**</span><span class="sxs-lookup"><span data-stu-id="dfa01-200">**Status**</span></span>
     - <span data-ttu-id="dfa01-201">**Risultato dell'analisi**</span><span class="sxs-lookup"><span data-stu-id="dfa01-201">**Rescan result**</span></span>

   - <span data-ttu-id="dfa01-202">Per esportare le voci, fare clic su **Esporta.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-202">To export the entries, click **Export**.</span></span> <span data-ttu-id="dfa01-203">Nella finestra di dialogo visualizzata, salvare il file .csv file.</span><span class="sxs-lookup"><span data-stu-id="dfa01-203">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="dfa01-204">Dettagli dell'analisi dell'invio dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="dfa01-204">Admin submission rescan details</span></span>

<span data-ttu-id="dfa01-205">I messaggi inviati negli invii di amministratori vengono esaminati e i risultati vengono visualizzati nel riquadro a comparsa dettagli invii:</span><span class="sxs-lookup"><span data-stu-id="dfa01-205">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="dfa01-206">Se si è verificato un errore nell'autenticazione della posta elettronica del mittente al momento del recapito.</span><span class="sxs-lookup"><span data-stu-id="dfa01-206">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="dfa01-207">Informazioni su eventuali riscontri dei criteri che potrebbero aver influenzato o sostituito il verdetto di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="dfa01-207">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="dfa01-208">Risultati della detonazione correnti per verificare se gli URL o i file contenuti nel messaggio erano dannosi o meno.</span><span class="sxs-lookup"><span data-stu-id="dfa01-208">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="dfa01-209">Feedback dei gradi.</span><span class="sxs-lookup"><span data-stu-id="dfa01-209">Feedback from graders.</span></span>

<span data-ttu-id="dfa01-210">Se è stata trovata una sostituzione, la nuova analisi dovrebbe essere completata dopo alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="dfa01-210">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="dfa01-211">Se non si è verificato un problema nell'autenticazione della posta elettronica o il recapito non è stato influenzato da una sostituzione, il feedback dei voti potrebbe richiedere fino a un giorno.</span><span class="sxs-lookup"><span data-stu-id="dfa01-211">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="dfa01-212">Visualizzare gli invii degli utenti a Microsoft</span><span class="sxs-lookup"><span data-stu-id="dfa01-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="dfa01-213">Se è stato distribuito il componente aggiuntivo Segnala [messaggio,](enable-the-report-message-add-in.md)il componente aggiuntivo Segnala [phishing](enable-the-report-phish-add-in.md)o gli utenti utilizzano la segnalazione predefinita [in Outlook sul web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), è possibile visualizzare i report degli utenti nella scheda **Messaggio** segnalato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="dfa01-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="dfa01-214">Nel portale Microsoft 365 Defender, passare a Invia tramite **posta elettronica & collaborazione** \> **Invii.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-214">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="dfa01-215">Nella pagina **Invii** seleziona la **scheda Messaggi segnalati dall'utente.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-215">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="dfa01-216">È possibile ordinare le voci facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="dfa01-216">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="dfa01-217">Fare **clic su Personalizza** colonne per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="dfa01-217">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="dfa01-218">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="dfa01-218">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="dfa01-219">**Oggetto del messaggio di posta elettronica**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-219">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-220">**Segnalato da**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-220">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-221">**Data riportata**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-221">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-222">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-222">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-223">**Motivo segnalato**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-223">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-224">**Risultato dell'analisi**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dfa01-224">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="dfa01-225">**ID segnalato messaggio**</span><span class="sxs-lookup"><span data-stu-id="dfa01-225">**Message reported ID**</span></span>
     - <span data-ttu-id="dfa01-226">**ID messaggio di rete**</span><span class="sxs-lookup"><span data-stu-id="dfa01-226">**Network Message ID**</span></span>
     - <span data-ttu-id="dfa01-227">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="dfa01-227">**Sender IP**</span></span>
     - <span data-ttu-id="dfa01-228">**Simulazione phish**</span><span class="sxs-lookup"><span data-stu-id="dfa01-228">**Phish simulation**</span></span>

     <span data-ttu-id="dfa01-229">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-229">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="dfa01-230">Per filtrare le voci, fare clic su **Filtro.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-230">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="dfa01-231">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="dfa01-231">The available filters are:</span></span>
     - <span data-ttu-id="dfa01-232">**Data riportata**: **Data inizio** e **Data fine**.</span><span class="sxs-lookup"><span data-stu-id="dfa01-232">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="dfa01-233">**Segnalato da**</span><span class="sxs-lookup"><span data-stu-id="dfa01-233">**Reported by**</span></span>
     - <span data-ttu-id="dfa01-234">**Oggetto e-mail**</span><span class="sxs-lookup"><span data-stu-id="dfa01-234">**Email subject**</span></span>
     - <span data-ttu-id="dfa01-235">**ID segnalato messaggio**</span><span class="sxs-lookup"><span data-stu-id="dfa01-235">**Message reported ID**</span></span>
     - <span data-ttu-id="dfa01-236">**ID messaggio di rete**</span><span class="sxs-lookup"><span data-stu-id="dfa01-236">**Network Message ID**</span></span>
     - <span data-ttu-id="dfa01-237">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="dfa01-237">**Sender**</span></span>
     - <span data-ttu-id="dfa01-238">**Motivo segnalato**: **Non posta indesiderata,** **Phish** o **Posta indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-238">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="dfa01-239">**Simulazione phish**: **Sì** o **No**</span><span class="sxs-lookup"><span data-stu-id="dfa01-239">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="dfa01-240">Al termine, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-240">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="dfa01-241">![Nuove opzioni di filtro per gli invii degli utenti](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="dfa01-241">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="dfa01-242">Per raggruppare le voci, fare clic **su Gruppo** e selezionare uno dei valori seguenti nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="dfa01-242">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="dfa01-243">**Nessuna**</span><span class="sxs-lookup"><span data-stu-id="dfa01-243">**None**</span></span>
     - <span data-ttu-id="dfa01-244">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="dfa01-244">**Reason**</span></span>
     - <span data-ttu-id="dfa01-245">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="dfa01-245">**Sender**</span></span>
     - <span data-ttu-id="dfa01-246">**Segnalato da**</span><span class="sxs-lookup"><span data-stu-id="dfa01-246">**Reported by**</span></span>
     - <span data-ttu-id="dfa01-247">**Risultato dell'analisi**</span><span class="sxs-lookup"><span data-stu-id="dfa01-247">**Rescan result**</span></span>
     - <span data-ttu-id="dfa01-248">**Simulazione phish**</span><span class="sxs-lookup"><span data-stu-id="dfa01-248">**Phish simulation**</span></span>

   - <span data-ttu-id="dfa01-249">Per esportare le voci, fare clic su **Esporta.**</span><span class="sxs-lookup"><span data-stu-id="dfa01-249">To export the entries, click **Export**.</span></span> <span data-ttu-id="dfa01-250">Nella finestra di dialogo visualizzata, salvare il file .csv file.</span><span class="sxs-lookup"><span data-stu-id="dfa01-250">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="dfa01-251">Se le organizzazioni sono configurate per inviare messaggi segnalati dall'utente solo alla cassetta postale personalizzata, i messaggi segnalati non verranno inviati per la nuova analisi e i risultati in **Messaggi** segnalati dall'utente saranno sempre vuoti.</span><span class="sxs-lookup"><span data-stu-id="dfa01-251">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="dfa01-252">Annullare gli invii utente</span><span class="sxs-lookup"><span data-stu-id="dfa01-252">Undo user submissions</span></span>

<span data-ttu-id="dfa01-253">Una volta che un utente invia un messaggio di posta elettronica sospetto alla cassetta postale personalizzata, l'utente e l'amministratore non hanno la possibilità di annullare l'invio.</span><span class="sxs-lookup"><span data-stu-id="dfa01-253">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="dfa01-254">Se l'utente desidera recuperare la posta elettronica, sarà disponibile per il ripristino nelle cartelle Posta eliminata o Posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="dfa01-254">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="dfa01-255">Inviare messaggi a Microsoft dalla cassetta postale personalizzata</span><span class="sxs-lookup"><span data-stu-id="dfa01-255">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="dfa01-256">Se la cassetta postale personalizzata è stata configurata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="dfa01-256">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="dfa01-257">Questo sposta in modo efficace un invio utente a un invio da amministratore.</span><span class="sxs-lookup"><span data-stu-id="dfa01-257">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="dfa01-258">Nella scheda **Messaggi segnalati dall'utente** selezionare un messaggio nell'elenco, fare clic su Invia a **Microsoft** per l'analisi e quindi selezionare uno dei valori seguenti nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="dfa01-258">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="dfa01-259">**Segnala pulito**</span><span class="sxs-lookup"><span data-stu-id="dfa01-259">**Report clean**</span></span>
- <span data-ttu-id="dfa01-260">**Segnalare phishing**</span><span class="sxs-lookup"><span data-stu-id="dfa01-260">**Report phishing**</span></span>
- <span data-ttu-id="dfa01-261">**Segnalare malware**</span><span class="sxs-lookup"><span data-stu-id="dfa01-261">**Report malware**</span></span>
- <span data-ttu-id="dfa01-262">**Segnalare posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="dfa01-262">**Report spam**</span></span>
- <span data-ttu-id="dfa01-263">**Attivare l'indagine**</span><span class="sxs-lookup"><span data-stu-id="dfa01-263">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dfa01-264">![Nuove opzioni sul pulsante Azione](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="dfa01-264">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>
