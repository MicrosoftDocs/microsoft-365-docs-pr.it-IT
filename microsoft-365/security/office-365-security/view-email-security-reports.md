---
title: Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Informazioni su come trovare e utilizzare i report sulla sicurezza della posta elettronica per l'organizzazione. I report sulla sicurezza della posta elettronica sono disponibili nel centro sicurezza & conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 568144c449d2f1a70082130cc847d48c3486d9da
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865105"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="ea80b-104">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="ea80b-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ea80b-105">Nel [Centro sicurezza & conformità](https://protection.office.com) è disponibile un'ampia gamma di report che consentono di visualizzare in che modo le funzionalità di sicurezza della posta elettronica, ad esempio la protezione da posta indesiderata, l'antimalware e la crittografia in Microsoft 365, proteggono l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea80b-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="ea80b-106">Se si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile visualizzare i report nel centro sicurezza & Compliance accedendo al  \> **Dashboard** report.</span><span class="sxs-lookup"><span data-stu-id="ea80b-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="ea80b-107">Per accedere direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="ea80b-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard dei report nel centro sicurezza & Compliance](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="ea80b-109">Report utenti compromessi</span><span class="sxs-lookup"><span data-stu-id="ea80b-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="ea80b-110">Questo report è disponibile nelle organizzazioni Microsoft 365 con le cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ea80b-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="ea80b-111">Non è disponibile nelle organizzazioni standalone di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="ea80b-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="ea80b-112">Nel rapporto **utenti compromessi** viene mostrato il numero di account utente contrassegnati come **sospetti** o **limitati** negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="ea80b-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="ea80b-113">Gli account in uno di questi Stati sono problematici o addirittura compromessi.</span><span class="sxs-lookup"><span data-stu-id="ea80b-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="ea80b-114">Con uso frequente, è possibile utilizzare il report per individuare picchi e persino tendenze, in account sospetti o limitati.</span><span class="sxs-lookup"><span data-stu-id="ea80b-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="ea80b-115">Per ulteriori informazioni sugli utenti compromessi, vedere [risposta a un account di posta elettronica compromesso](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget utenti compromessi nel dashboard dei report](../../media/compromised-users-report-widget.png)

<span data-ttu-id="ea80b-117">La visualizzazione aggregazione Mostra i dati per gli ultimi 90 giorni e la visualizzazione dettagli Mostra i dati per gli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="ea80b-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="ea80b-118">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al  \> **Dashboard** dei report e selezionare **utenti compromessi**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="ea80b-119">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="ea80b-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="ea80b-120">È possibile filtrare sia il grafico che la tabella Details facendo clic su **filtri** e selezionando uno o più dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ea80b-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="ea80b-121">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="ea80b-122">**Sospetti**: l'account utente ha inviato messaggi di posta elettronica sospetti ed è a rischio di essere limitato dall'invio di messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ea80b-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="ea80b-123">**Limitato**: l'account utente è stato limitato dall'invio di messaggi di posta elettronica a causa di modelli estremamente sospetti.</span><span class="sxs-lookup"><span data-stu-id="ea80b-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Visualizzazione report nel report utenti compromessi](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="ea80b-125">Se si fa clic su **Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="ea80b-126">**Ora di creazione**</span><span class="sxs-lookup"><span data-stu-id="ea80b-126">**Creation time**</span></span>
- <span data-ttu-id="ea80b-127">**ID utente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-127">**User ID**</span></span>
- <span data-ttu-id="ea80b-128">**Azione**</span><span class="sxs-lookup"><span data-stu-id="ea80b-128">**Action**</span></span>

<span data-ttu-id="ea80b-129">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="ea80b-130">Rapporto di crittografia</span><span class="sxs-lookup"><span data-stu-id="ea80b-130">Encryption report</span></span>

<span data-ttu-id="ea80b-131">Il **rapporto di crittografia** è disponibile in EOP (abbonamenti con cassette postali in Exchange Online o EOP autonomo senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="ea80b-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="ea80b-132">Il team di sicurezza dell'organizzazione può utilizzare le informazioni contenute in questo report per identificare modelli e applicare o modificare in modo proattivo i criteri per i messaggi di posta elettronica sensibili.</span><span class="sxs-lookup"><span data-stu-id="ea80b-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="ea80b-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ea80b-133">For example:</span></span>

- <span data-ttu-id="ea80b-134">Se viene visualizzato un numero elevato di messaggi di posta elettronica crittografati dagli utenti, potrebbe essere necessario aggiungere un criterio di crittografia per automatizzare la crittografia per alcuni casi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="ea80b-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="ea80b-135">Per ulteriori informazioni, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="ea80b-136">Se si dispone di un numero di modelli di crittografia disponibili ma nessuno li utilizza, è possibile esaminare se gli utenti hanno bisogno di una formazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ea80b-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="ea80b-137">La visualizzazione aggregazione consente il filtro per gli ultimi 90 giorni, mentre la visualizzazione dettagli consente il filtraggio per 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="ea80b-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="ea80b-138">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al  \> **Dashboard** dei report e selezionare **rapporto di crittografia**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="ea80b-139">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="ea80b-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="ea80b-140">Per ulteriori informazioni sulla crittografia, vedere la [crittografia della posta elettronica in Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="ea80b-141">Visualizzazione report per il rapporto di crittografia</span><span class="sxs-lookup"><span data-stu-id="ea80b-141">Report view for the Encryption report</span></span>

<span data-ttu-id="ea80b-142">Nel grafico è possibile utilizzare i seguenti filtri:</span><span class="sxs-lookup"><span data-stu-id="ea80b-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="ea80b-143">**Visualizzare i dati in base a: rapporto di crittografia dei messaggi** e **scomposizione in base a: metodo di** crittografia: sono disponibili i seguenti metodi di crittografia:</span><span class="sxs-lookup"><span data-stu-id="ea80b-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="ea80b-144">**Crittografia per utente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-144">**Encryption by user**</span></span>
  - <span data-ttu-id="ea80b-145">**Crittografia per criterio**</span><span class="sxs-lookup"><span data-stu-id="ea80b-145">**Encryption by policy**</span></span>

  <span data-ttu-id="ea80b-146">Se si fa clic su **filtri**, è possibile modificare il grafico con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="ea80b-147">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ea80b-148">Metodo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="ea80b-148">Encryption method.</span></span>
  - <span data-ttu-id="ea80b-149">Modello di crittografia.</span><span class="sxs-lookup"><span data-stu-id="ea80b-149">Encryption template.</span></span>

- <span data-ttu-id="ea80b-150">**Visualizzare i dati in base a: rapporto di crittografia dei messaggi** e **scomposizione in base a: modello di crittografia**: sono disponibili i seguenti metodi di crittografia:</span><span class="sxs-lookup"><span data-stu-id="ea80b-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="ea80b-151">**Non inoltrare**</span><span class="sxs-lookup"><span data-stu-id="ea80b-151">**Do not forward**</span></span>
  - <span data-ttu-id="ea80b-152">**Solo crittografia**</span><span class="sxs-lookup"><span data-stu-id="ea80b-152">**Encrypt only**</span></span>
  - <span data-ttu-id="ea80b-153">**OME precedente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-153">**OME previous**</span></span>
  - <span data-ttu-id="ea80b-154">**Personalizzato**</span><span class="sxs-lookup"><span data-stu-id="ea80b-154">**Custom**</span></span>

  <span data-ttu-id="ea80b-155">Se si fa clic su **filtri**, è possibile modificare il grafico con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="ea80b-156">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ea80b-157">Metodo di crittografia</span><span class="sxs-lookup"><span data-stu-id="ea80b-157">Encryption method</span></span>
  - <span data-ttu-id="ea80b-158">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="ea80b-158">Encryption template</span></span>

- <span data-ttu-id="ea80b-159">**Visualizzare i dati per: Top 5 Domains Recipient**: questa visualizzazione Mostra un grafico a torta con i conteggi dei messaggi inviati per i primi 5 domini dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="ea80b-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="ea80b-160">Se si fa clic su **filtri**, è possibile selezionare una data di **inizio** e una **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="ea80b-161">Visualizzazione della tabella dei dettagli per il rapporto di crittografia</span><span class="sxs-lookup"><span data-stu-id="ea80b-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="ea80b-162">Se si fa clic su **Visualizza tabella dettagli**, le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="ea80b-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ea80b-163">**Scomposizione per: metodo di crittografia** o **scomposizione in base a: modello di crittografia**: vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="ea80b-164">**Data**</span><span class="sxs-lookup"><span data-stu-id="ea80b-164">**Date**</span></span>
  - <span data-ttu-id="ea80b-165">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-165">**Sender address**</span></span>
  - <span data-ttu-id="ea80b-166">**Modello di crittografia**</span><span class="sxs-lookup"><span data-stu-id="ea80b-166">**Encryption template**</span></span>
  - <span data-ttu-id="ea80b-167">**Metodo di crittografia**</span><span class="sxs-lookup"><span data-stu-id="ea80b-167">**Encryption method**</span></span>
  - <span data-ttu-id="ea80b-168">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="ea80b-168">**Recipient address**</span></span>
  - <span data-ttu-id="ea80b-169">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ea80b-169">**Subject**</span></span>

- <span data-ttu-id="ea80b-170">**Visualizzare i dati per: Top 5 Domains Recipient**:</span><span class="sxs-lookup"><span data-stu-id="ea80b-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="ea80b-171">**Data**</span><span class="sxs-lookup"><span data-stu-id="ea80b-171">**Date**</span></span>
  - <span data-ttu-id="ea80b-172">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="ea80b-172">**Recipient domain**</span></span>
  - <span data-ttu-id="ea80b-173">**Numero di messaggi**</span><span class="sxs-lookup"><span data-stu-id="ea80b-173">**Message count**</span></span>

<span data-ttu-id="ea80b-174">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="ea80b-175">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="ea80b-176">Metodo di crittografia</span><span class="sxs-lookup"><span data-stu-id="ea80b-176">Encryption method</span></span>
- <span data-ttu-id="ea80b-177">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="ea80b-177">Encryption template</span></span>

<span data-ttu-id="ea80b-178">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="ea80b-179">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="ea80b-179">Mailflow status report</span></span>

<span data-ttu-id="ea80b-180">Il **rapporto di stato del flusso** di lavoro contiene informazioni su malware, posta indesiderata, phishing e messaggi bloccati Edge.</span><span class="sxs-lookup"><span data-stu-id="ea80b-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="ea80b-181">Per ulteriori informazioni, vedere [rapporto sullo stato del flusso](view-mail-flow-reports.md#mailflow-status-report)di posta.</span><span class="sxs-lookup"><span data-stu-id="ea80b-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="ea80b-182">Rilevamenti di malware nel rapporto di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ea80b-182">Malware detections in email report</span></span>

<span data-ttu-id="ea80b-183">I rilevamenti di **malware nel rapporto di posta elettronica** mostrano informazioni sui rilevamenti di malware nei messaggi di posta elettronica in arrivo e in uscita (malware rilevati da Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="ea80b-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="ea80b-184">Per ulteriori informazioni sulla protezione antimalware in EOP, vedere [anti-malware Protection in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="ea80b-185">Il filtro visualizzazione aggregazione consente 90 giorni, mentre il filtro tabella Dettagli consente solo 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="ea80b-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="ea80b-186">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al  \> **Dashboard** dei report e selezionare **rilevamenti di malware nel messaggio di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="ea80b-187">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="ea80b-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Rilevamenti di malware nel widget di posta elettronica nel dashboard report](../../media/malware-detections-widget.png)

<span data-ttu-id="ea80b-189">È possibile filtrare sia il grafico che la tabella Details facendo clic su **filtri** e selezionando:</span><span class="sxs-lookup"><span data-stu-id="ea80b-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="ea80b-190">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="ea80b-191">**Inbound**</span><span class="sxs-lookup"><span data-stu-id="ea80b-191">**Inbound**</span></span>
- <span data-ttu-id="ea80b-192">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="ea80b-192">**Outbound**</span></span>

![Visualizzazione report nel rapporto di rilevamento di malware nel messaggio di posta elettronica](../../media/malware-detections-report-view.png)

<span data-ttu-id="ea80b-194">Se si fa clic su **Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="ea80b-195">**Data**</span><span class="sxs-lookup"><span data-stu-id="ea80b-195">**Date**</span></span>
- <span data-ttu-id="ea80b-196">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-196">**Sender address**</span></span>
- <span data-ttu-id="ea80b-197">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="ea80b-197">**Recipient address**</span></span>
- <span data-ttu-id="ea80b-198">**ID messaggio**: disponibile nel campo di intestazione **Message-ID** nell'intestazione del messaggio e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="ea80b-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="ea80b-199">Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="ea80b-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="ea80b-200">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ea80b-200">**Subject**</span></span>
- <span data-ttu-id="ea80b-201">**Filename**</span><span class="sxs-lookup"><span data-stu-id="ea80b-201">**Filename**</span></span>
- <span data-ttu-id="ea80b-202">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="ea80b-202">**Malware name**</span></span>

<span data-ttu-id="ea80b-203">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-203">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="ea80b-204">Rapporto latenza posta</span><span class="sxs-lookup"><span data-stu-id="ea80b-204">Mail latency report</span></span>

<span data-ttu-id="ea80b-205">Il **rapporto latenza posta** contiene informazioni sul recapito della posta e sulla latenza di detonazione vissute all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea80b-205">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="ea80b-206">Per ulteriori informazioni, vedere [rapporto latenza della posta](view-reports-for-atp.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="ea80b-206">For more information, see [Mail latency report](view-reports-for-atp.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="ea80b-207">Report di posta elettronica inviati e ricevuti</span><span class="sxs-lookup"><span data-stu-id="ea80b-207">Sent and received email report</span></span>

<span data-ttu-id="ea80b-208">Il rapporto **messaggi di posta elettronica inviati e ricevuti** contiene informazioni su malware, posta indesiderata, regole del flusso di posta (note anche come regole di trasporto) e rilevamenti di malware avanzati dopo che la posta elettronica entra nel servizio.</span><span class="sxs-lookup"><span data-stu-id="ea80b-208">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="ea80b-209">Per ulteriori informazioni, vedere [report di posta elettronica inviata e ricevuta](view-mail-flow-reports.md#sent-and-received-email-report).</span><span class="sxs-lookup"><span data-stu-id="ea80b-209">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="ea80b-210">Report sui rilevamenti della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ea80b-210">Spam detections report</span></span>

<span data-ttu-id="ea80b-211">Il rapporto sui **rilevamenti di posta indesiderata** Visualizza messaggi di posta indesiderata bloccati da EOP.</span><span class="sxs-lookup"><span data-stu-id="ea80b-211">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="ea80b-212">I messaggi vengono conteggiati singolarmente e non per destinatario.</span><span class="sxs-lookup"><span data-stu-id="ea80b-212">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="ea80b-213">Ad esempio, se lo stesso messaggio di posta indesiderata è stato inviato a 100 destinatari nell'organizzazione, viene conteggiato come un solo messaggio.</span><span class="sxs-lookup"><span data-stu-id="ea80b-213">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="ea80b-214">La visualizzazione aggregazione consente il filtraggio di 90 giorni, mentre la tabella Details consente il filtraggio di 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="ea80b-214">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="ea80b-215">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al  \> **Dashboard** dei report e selezionare **rilevamenti di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-215">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="ea80b-216">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="ea80b-216">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget per i rilevamenti di posta indesiderata nel dashboard report](../../media/spam-detections-report-widget.png)

<span data-ttu-id="ea80b-218">Per ulteriori informazioni sulla protezione da posta indesiderata, vedere [protezione da posta](anti-spam-protection.md)indesiderata in EOP.</span><span class="sxs-lookup"><span data-stu-id="ea80b-218">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="ea80b-219">Visualizzazione report per il rapporto rilevamento posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ea80b-219">Report view for the Spam detections report</span></span>

<span data-ttu-id="ea80b-220">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-220">The following charts are available in the report view:</span></span>

- <span data-ttu-id="ea80b-221">**Scomposizione per: azione**: vengono visualizzati i tipi di evento seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-221">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="ea80b-222">**Contenuto di posta indesiderata filtrato**</span><span class="sxs-lookup"><span data-stu-id="ea80b-222">**Spam content filtered**</span></span>
  - <span data-ttu-id="ea80b-223">**Blocco IP di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="ea80b-223">**Spam IP block**</span></span>
  - <span data-ttu-id="ea80b-224">**Blocco busta posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="ea80b-224">**Spam envelope block**</span></span>
  - <span data-ttu-id="ea80b-225">**Filtro per la posta indesiderata DBEB**: blocco Edge basato su directory (DBEB)</span><span class="sxs-lookup"><span data-stu-id="ea80b-225">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="ea80b-226">Quando si posiziona il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti elementi sono stati bloccati in quel giorno, nonché come tali elementi sono categorizzati.</span><span class="sxs-lookup"><span data-stu-id="ea80b-226">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Visualizzazione azione nel rapporto rilevamento posta indesiderata](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="ea80b-228">**Scomposizione per: direzione**: vengono visualizzate le indicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-228">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="ea80b-229">**Inbound**</span><span class="sxs-lookup"><span data-stu-id="ea80b-229">**Inbound**</span></span>
  - <span data-ttu-id="ea80b-230">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="ea80b-230">**Outbound**</span></span>

  ![Visualizzazione direzione nel rapporto rilevamento posta indesiderata](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="ea80b-232">Se si fa clic su **filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-232">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="ea80b-233">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-233">**Start date** and **End date**</span></span>
- <span data-ttu-id="ea80b-234">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="ea80b-234">Direction values</span></span>
- <span data-ttu-id="ea80b-235">Valori del tipo di evento</span><span class="sxs-lookup"><span data-stu-id="ea80b-235">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="ea80b-236">Visualizzazione tabella dettagli per il rapporto rilevamento posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ea80b-236">Details table view for the Spam detections report</span></span>

<span data-ttu-id="ea80b-237">Se si fa clic su **Visualizza tabella dettagli** in qualsiasi visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-237">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="ea80b-238">**Data**</span><span class="sxs-lookup"><span data-stu-id="ea80b-238">**Date**</span></span>
- <span data-ttu-id="ea80b-239">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-239">**Sender address**</span></span>
- <span data-ttu-id="ea80b-240">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="ea80b-240">**Recipient address**</span></span>
- <span data-ttu-id="ea80b-241">**Tipo evento**</span><span class="sxs-lookup"><span data-stu-id="ea80b-241">**Event type**</span></span>
- <span data-ttu-id="ea80b-242">**Azione**</span><span class="sxs-lookup"><span data-stu-id="ea80b-242">**Action**</span></span>
- <span data-ttu-id="ea80b-243">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ea80b-243">**Subject**</span></span>

<span data-ttu-id="ea80b-244">Se si fa clic su **filtri** in una tabella Details, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-244">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="ea80b-245">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-245">**Start date** and **End date**</span></span>
- <span data-ttu-id="ea80b-246">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="ea80b-246">Direction values</span></span>
- <span data-ttu-id="ea80b-247">Valori del tipo di evento</span><span class="sxs-lookup"><span data-stu-id="ea80b-247">Event type values</span></span>

<span data-ttu-id="ea80b-248">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-248">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="ea80b-249">Rapporto rilevamenti spoof</span><span class="sxs-lookup"><span data-stu-id="ea80b-249">Spoof detections report</span></span>

<span data-ttu-id="ea80b-250">Il rapporto sui rilevamenti **spoof** indica il numero di messaggi di posta elettronica contraffatti individuati e di quelli che sono stati considerati "buoni" (la posta contraffatta è stata realizzata per motivi aziendali legittimi).</span><span class="sxs-lookup"><span data-stu-id="ea80b-250">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="ea80b-251">Per ulteriori informazioni sullo spoofing, vedere [protezione anti-spoofing in EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-251">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="ea80b-252">La visualizzazione aggregazione del report consente 90 giorni di filtraggio, mentre la visualizzazione dettagli consente solo dieci giorni di filtraggio.</span><span class="sxs-lookup"><span data-stu-id="ea80b-252">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="ea80b-253">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al  \> **Dashboard** dei report e selezionare **rilevamenti spoof**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-253">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="ea80b-254">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="ea80b-254">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widget spoofing detections nel dashboard report](../../media/spoof-detections-widget.png)

<span data-ttu-id="ea80b-256">Quando si posiziona il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile visualizzare il numero di messaggi di posta elettronica contraffatti.</span><span class="sxs-lookup"><span data-stu-id="ea80b-256">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="ea80b-257">È possibile filtrare sia il grafico che la tabella Details facendo clic su **filtri** e selezionando uno o più dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ea80b-257">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="ea80b-258">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-258">**Start date** and **End date**</span></span>

- <span data-ttu-id="ea80b-259">**Posta elettronica buona**</span><span class="sxs-lookup"><span data-stu-id="ea80b-259">**Good mail**</span></span>

- <span data-ttu-id="ea80b-260">**Catturato come posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="ea80b-260">**Caught as spam**</span></span>

![Visualizzazione report nel rapporto rilevamenti spoof](../../media/spoof-detections-report-view.png)

<span data-ttu-id="ea80b-262">Se si fa clic su **Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-262">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="ea80b-263">**Data**</span><span class="sxs-lookup"><span data-stu-id="ea80b-263">**Date**</span></span>
- <span data-ttu-id="ea80b-264">**Mittente falsificato**</span><span class="sxs-lookup"><span data-stu-id="ea80b-264">**Spoofed sender**</span></span>
- <span data-ttu-id="ea80b-265">**Mittente vero**</span><span class="sxs-lookup"><span data-stu-id="ea80b-265">**True sender**</span></span>
- <span data-ttu-id="ea80b-266">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-266">**Sender IP**</span></span>
- <span data-ttu-id="ea80b-267">**Azione**</span><span class="sxs-lookup"><span data-stu-id="ea80b-267">**Action**</span></span>
- <span data-ttu-id="ea80b-268">**Numero di messaggi**</span><span class="sxs-lookup"><span data-stu-id="ea80b-268">**Message count**</span></span>

<span data-ttu-id="ea80b-269">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-269">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="ea80b-270">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ea80b-270">Threat protection status report</span></span>

<span data-ttu-id="ea80b-271">Il rapporto **sullo stato della protezione dalle minacce** è disponibile sia in EOP che in Microsoft Defender per Office 365; Tuttavia, i report contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="ea80b-271">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="ea80b-272">Ad esempio, i clienti di EOP possono visualizzare informazioni sui malware rilevati tramite posta elettronica, ma non informazioni sui file dannosi rilevati da [ATP per SharePoint, OneDrive o Microsoft teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-272">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [ATP for SharePoint, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="ea80b-273">Il rapporto fornisce il numero di messaggi di posta elettronica con contenuti dannosi, ad esempio i file o gli indirizzi del sito Web (URL) bloccati dal motore antimalware, da [zero-hour auto Purge (ZAP)](zero-hour-auto-purge.md)e Defender per Office 365 caratteristiche come [collegamenti sicuri](atp-safe-links.md), [allegati sicuri](atp-safe-attachments.md)e [anti-phishing](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-273">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="ea80b-274">È possibile utilizzare queste informazioni per identificare le tendenze o determinare se i criteri dell'organizzazione devono essere rettificati.</span><span class="sxs-lookup"><span data-stu-id="ea80b-274">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="ea80b-275">**Nota**: è importante comprendere che se un messaggio viene inviato a cinque destinatari, è necessario contarlo come cinque messaggi diversi e non con un solo messaggio.</span><span class="sxs-lookup"><span data-stu-id="ea80b-275">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="ea80b-276">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al  \> **Dashboard** dei report e selezionare **lo stato di protezione dalle minacce**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-276">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="ea80b-277">Per passare direttamente al report, aprire uno degli URL seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-277">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="ea80b-278">Microsoft Defender per Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="ea80b-278">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="ea80b-279">EOP <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="ea80b-279">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Widget dello stato di protezione dalle minacce nel dashboard dei report](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="ea80b-281">Per impostazione predefinita, il grafico Visualizza i dati negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="ea80b-281">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="ea80b-282">Se si fa clic su **filtri**, è possibile selezionare un intervallo di date di 90 giorni (gli abbonamenti di valutazione potrebbero essere limitati a 30 giorni).</span><span class="sxs-lookup"><span data-stu-id="ea80b-282">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="ea80b-283">La visualizzazione tabella Dettagli consente di filtrare per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="ea80b-283">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="ea80b-284">Visualizzazione report per il rapporto sullo stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ea80b-284">Report view for the Threat protection status report</span></span>

<span data-ttu-id="ea80b-285">Sono disponibili le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-285">The following views are available:</span></span>

- <span data-ttu-id="ea80b-286">**Visualizzare i dati in base a: Panoramica**: vengono visualizzate le informazioni di rilevamento seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-286">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="ea80b-287">**Malware per la posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="ea80b-287">**Email malware**</span></span>
  - <span data-ttu-id="ea80b-288">**Phishing di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="ea80b-288">**Email phish**</span></span>
  - <span data-ttu-id="ea80b-289">**Malware contenuto**</span><span class="sxs-lookup"><span data-stu-id="ea80b-289">**Content malware**</span></span>

  ![Visualizzazione panoramica nel rapporto sullo stato di protezione di minacce](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="ea80b-291">**Visualizzare i dati in base a: content \> Malware**<sup>1</sup>: vengono visualizzate le seguenti informazioni per Microsoft Defender per le organizzazioni di Office 365:</span><span class="sxs-lookup"><span data-stu-id="ea80b-291">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="ea80b-292">**Motore antimalware**: i file dannosi rilevati in SharePoint, OneDrive e Microsoft teams dal [rilevamento dei virus incorporato in Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-292">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="ea80b-293">**Detonazione dei file**: file dannosi rilevati da [ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-293">**File detonation**: Malicious files detected by [ATP for Sharepoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

  ![Visualizzazione malware contenuto nel rapporto sullo stato della protezione dalle minacce](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="ea80b-295">**Visualizzare i dati in base a: override del messaggio**: vengono visualizzate le informazioni relative al motivo di sostituzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-295">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="ea80b-296">**Ignora locale**</span><span class="sxs-lookup"><span data-stu-id="ea80b-296">**On-premises skip**</span></span>
  - <span data-ttu-id="ea80b-297">**Consenti IP**</span><span class="sxs-lookup"><span data-stu-id="ea80b-297">**IP Allow**</span></span>
  - <span data-ttu-id="ea80b-298">**Regola del flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="ea80b-298">**Mail flow rule**</span></span>
  - <span data-ttu-id="ea80b-299">**Consenti mittente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-299">**Sender allow**</span></span>
  - <span data-ttu-id="ea80b-300">**Consenti dominio**</span><span class="sxs-lookup"><span data-stu-id="ea80b-300">**Domain allow**</span></span>
  - <span data-ttu-id="ea80b-301">**ZAP non abilitato**</span><span class="sxs-lookup"><span data-stu-id="ea80b-301">**ZAP not enabled**</span></span>
  - <span data-ttu-id="ea80b-302">**Cartella posta indesiderata non abilitata**</span><span class="sxs-lookup"><span data-stu-id="ea80b-302">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="ea80b-303">**Mittente sicuro dell'utente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-303">**User Safe Sender**</span></span>
  - <span data-ttu-id="ea80b-304">**Dominio sicuro dell'utente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-304">**User Safe Domain**</span></span>

  ![Visualizzazione di sostituzione dei messaggi nel rapporto sullo stato della protezione dalle minacce](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="ea80b-306">**Scomposizione per: tecnologia di rilevamento** e **visualizzazione dei dati in base a: e-mail \> phishing**: vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-306">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="ea80b-307">**Reputazione URL generata dal trifosfato di adenosina**<sup>1</sup>: reputazione di URL dannosi generata dal difensore per le detonazioni di Office 365 in altri clienti di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea80b-307">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="ea80b-308">**Filtro Advanced phishing**: segnali di phishing basati sull'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="ea80b-308">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="ea80b-309">**Errore di anti-spoofing-DMARC**: errore di autenticazione di DMARC nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ea80b-309">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="ea80b-310">**Anti-spoofing-intra-org**: il mittente sta tentando di falsificare il dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="ea80b-310">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="ea80b-311">**Anti-spoofing-dominio esterno**: il mittente sta provando a falsificare un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="ea80b-311">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="ea80b-312">**Rappresentazione del marchio**: rappresentazione di marche ben note basate su mittenti.</span><span class="sxs-lookup"><span data-stu-id="ea80b-312">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="ea80b-313">**Rappresentazione di dominio**<sup>1</sup>: rappresentazione dei domini posseduti o definiti dal cliente.</span><span class="sxs-lookup"><span data-stu-id="ea80b-313">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="ea80b-314">**Reputazione URL EOP**: reputazione URL dannosi.</span><span class="sxs-lookup"><span data-stu-id="ea80b-314">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="ea80b-315">**Filtro generale phishing**: segnali di phishing basati sulle regole dell'analista.</span><span class="sxs-lookup"><span data-stu-id="ea80b-315">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="ea80b-316">**Altri**</span><span class="sxs-lookup"><span data-stu-id="ea80b-316">**Others**</span></span>
  - <span data-ttu-id="ea80b-317">**Phishing zap**<sup>2</sup>: zero hour auto purge dei messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="ea80b-317">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="ea80b-318">**Detonazione URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ea80b-318">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="ea80b-319">**Rappresentazione utente**<sup>1</sup>: rappresentazione degli utenti definiti dall'amministratore o appresa tramite Intelligence delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="ea80b-319">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Visualizzazione della tecnologia di rilevamento per la posta elettronica di phishing nel rapporto sullo stato della protezione dalle minacce](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="ea80b-321">**Scomposizione per: tecnologia di rilevamento** e **visualizzazione dei dati in base a: posta elettronica \> malware**: vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-321">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="ea80b-322">**Reputazione dei file generati dal trifosfato di adenosina**<sup>1</sup>: tutti i file dannosi reputazione generati da Defender per Office 365 detonazioni.</span><span class="sxs-lookup"><span data-stu-id="ea80b-322">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="ea80b-323">**Motore anti-malware**<sup>1</sup>: rilevamento da motori antimalware.</span><span class="sxs-lookup"><span data-stu-id="ea80b-323">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="ea80b-324">**Blocco dei tipi di file di criteri antimalware**: si tratta di messaggi di posta elettronica filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="ea80b-324">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="ea80b-325">**Detonazione dei file**<sup>1</sup>: rilevamento tramite allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="ea80b-325">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="ea80b-326">**Reputazione di file dannosi**</span><span class="sxs-lookup"><span data-stu-id="ea80b-326">**Malicious file reputation**</span></span>
  - <span data-ttu-id="ea80b-327">**Malware zap**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ea80b-327">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="ea80b-328">**Altri**</span><span class="sxs-lookup"><span data-stu-id="ea80b-328">**Others**</span></span>

  ![Visualizzazione della tecnologia di rilevamento per malware nel rapporto sullo stato della protezione dalle minacce](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="ea80b-330">**Scomposizione per: tipo di criterio** e **visualizzazione dei dati in base a: posta elettronica \> phishing** o **visualizzazione dati per: posta elettronica \> malware**: vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-330">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="ea80b-331">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="ea80b-331">**Anti-malware**</span></span>
  - <span data-ttu-id="ea80b-332">**Allegati sicuri**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ea80b-332">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="ea80b-333">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="ea80b-333">**Anti-phish**</span></span>
  - <span data-ttu-id="ea80b-334">**Protezione da posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="ea80b-334">**Anti-spam**</span></span>
  - <span data-ttu-id="ea80b-335">**Regola del flusso di posta** (nota anche come regola di trasporto)</span><span class="sxs-lookup"><span data-stu-id="ea80b-335">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="ea80b-336">**Altri**</span><span class="sxs-lookup"><span data-stu-id="ea80b-336">**Others**</span></span>

  ![Visualizzazione dei tipi di criteri per la posta elettronica di phishing nel rapporto sullo stato di protezione di minacce](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="ea80b-338">**Scomposizione per: stato di recapito** e **visualizzazione dei dati in base a: posta elettronica \> phishing** oppure **visualizzare i dati per: posta elettronica \> malware**: vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-338">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="ea80b-339">**Recapito non riuscito**</span><span class="sxs-lookup"><span data-stu-id="ea80b-339">**Delivery failed**</span></span>
  - <span data-ttu-id="ea80b-340">**Interrotte**</span><span class="sxs-lookup"><span data-stu-id="ea80b-340">**Dropped**</span></span>
  - <span data-ttu-id="ea80b-341">**Inoltrato**</span><span class="sxs-lookup"><span data-stu-id="ea80b-341">**Forwarded**</span></span>
  - <span data-ttu-id="ea80b-342">**Cassetta postale ospitata: cartella personalizzata**</span><span class="sxs-lookup"><span data-stu-id="ea80b-342">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="ea80b-343">**Cassetta postale ospitata: elementi eliminati**</span><span class="sxs-lookup"><span data-stu-id="ea80b-343">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="ea80b-344">**Cassetta postale ospitata: posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="ea80b-344">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="ea80b-345">**Cassetta postale ospitata: posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="ea80b-345">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="ea80b-346">**Server locale: recapitato**</span><span class="sxs-lookup"><span data-stu-id="ea80b-346">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="ea80b-347">**Quarantena**</span><span class="sxs-lookup"><span data-stu-id="ea80b-347">**Quarantine**</span></span>

  ![Visualizzazione stato di recapito per il messaggio di posta elettronica di phishing nel rapporto sullo stato di protezione](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="ea80b-349"><sup>1</sup> difensore solo per Office 365</span><span class="sxs-lookup"><span data-stu-id="ea80b-349"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="ea80b-350"><sup>2</sup> zero-hour auto Purge (ZAP) non è disponibile in EOP autonomo (funziona solo nelle cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="ea80b-350"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="ea80b-351">Se si fa clic su **filtri**, i filtri disponibili dipendono dal grafico che si sta cercando:</span><span class="sxs-lookup"><span data-stu-id="ea80b-351">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ea80b-352">Per **visualizzare i dati in base a: contenuto di \> malware**, è possibile modificare il rapporto per data di **inizio** e **Data di fine** e il valore di **rilevamento** .</span><span class="sxs-lookup"><span data-stu-id="ea80b-352">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="ea80b-353">Per la **visualizzazione dei dati in base a: override dei messaggi**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-353">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ea80b-354">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-354">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ea80b-355">**Motivo dell'override**</span><span class="sxs-lookup"><span data-stu-id="ea80b-355">**Override Reason**</span></span>
  - <span data-ttu-id="ea80b-356">**Tag**: filtrare i risultati in base agli utenti o ai gruppi a cui è stato applicato il tag utente specificato (compresi gli account prioritari).</span><span class="sxs-lookup"><span data-stu-id="ea80b-356">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ea80b-357">Per ulteriori informazioni sui tag degli utenti, vedere [tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-357">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="ea80b-358">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="ea80b-358">**Domain**</span></span>

- <span data-ttu-id="ea80b-359">Per tutte le altre visualizzazioni, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-359">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ea80b-360">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-360">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ea80b-361">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="ea80b-361">**Detection**</span></span>
  - <span data-ttu-id="ea80b-362">**Protetto da**: **ATP** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="ea80b-362">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="ea80b-363">**Tag**: filtrare i risultati in base agli utenti o ai gruppi a cui è stato applicato il tag utente specificato (compresi gli account prioritari).</span><span class="sxs-lookup"><span data-stu-id="ea80b-363">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ea80b-364">Per ulteriori informazioni sui tag degli utenti, vedere [tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-364">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="ea80b-365">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="ea80b-365">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="ea80b-366">Visualizzazione della tabella dei dettagli per il rapporto sullo stato della protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ea80b-366">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="ea80b-367">Se si fa clic su **Visualizza tabella dettagli**, le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="ea80b-367">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ea80b-368">**Visualizzazione dei dati per: Panoramica**: non è disponibile alcun pulsante **Visualizza dettagli tabella** .</span><span class="sxs-lookup"><span data-stu-id="ea80b-368">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="ea80b-369">**Visualizzare i dati in base a: content \> Malware**:</span><span class="sxs-lookup"><span data-stu-id="ea80b-369">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="ea80b-370">**Data**</span><span class="sxs-lookup"><span data-stu-id="ea80b-370">**Date**</span></span>
  - <span data-ttu-id="ea80b-371">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="ea80b-371">**Location**</span></span>
  - <span data-ttu-id="ea80b-372">**Diretto da**</span><span class="sxs-lookup"><span data-stu-id="ea80b-372">**Directed by**</span></span>
  - <span data-ttu-id="ea80b-373">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="ea80b-373">**Malware name**</span></span>

  <span data-ttu-id="ea80b-374">Se si fa clic su **filtri** in questa visualizzazione, è possibile modificare il rapporto per data di **inizio** e **Data di fine** e il valore di **rilevamento** .</span><span class="sxs-lookup"><span data-stu-id="ea80b-374">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="ea80b-375">**Visualizzare i dati in base a: override del messaggio**:</span><span class="sxs-lookup"><span data-stu-id="ea80b-375">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="ea80b-376">**Data**</span><span class="sxs-lookup"><span data-stu-id="ea80b-376">**Date**</span></span>
  - <span data-ttu-id="ea80b-377">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ea80b-377">**Subject**</span></span>
  - <span data-ttu-id="ea80b-378">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-378">**Sender**</span></span>
  - <span data-ttu-id="ea80b-379">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="ea80b-379">**Recipients**</span></span>
  - <span data-ttu-id="ea80b-380">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="ea80b-380">**Detected by**</span></span>
  - <span data-ttu-id="ea80b-381">**Motivo dell'override**</span><span class="sxs-lookup"><span data-stu-id="ea80b-381">**Override Reason**</span></span>
  - <span data-ttu-id="ea80b-382">**Origine del compromesso**</span><span class="sxs-lookup"><span data-stu-id="ea80b-382">**Source of Compromise**</span></span>
  - <span data-ttu-id="ea80b-383">**Tag**</span><span class="sxs-lookup"><span data-stu-id="ea80b-383">**Tags**</span></span>

  <span data-ttu-id="ea80b-384">Se si fa clic su **filtri** in questa visualizzazione, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-384">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ea80b-385">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-385">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ea80b-386">**Motivo dell'override**</span><span class="sxs-lookup"><span data-stu-id="ea80b-386">**Override Reason**</span></span>
  - <span data-ttu-id="ea80b-387">**Tag**: filtrare i risultati in base agli utenti o ai gruppi a cui è stato applicato il tag utente specificato (compresi gli account prioritari).</span><span class="sxs-lookup"><span data-stu-id="ea80b-387">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ea80b-388">Per ulteriori informazioni sui tag degli utenti, vedere [tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-388">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="ea80b-389">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="ea80b-389">**Domain**</span></span>
  - <span data-ttu-id="ea80b-390">**Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella Dettagli)</span><span class="sxs-lookup"><span data-stu-id="ea80b-390">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="ea80b-391">Tutti gli altri grafici:</span><span class="sxs-lookup"><span data-stu-id="ea80b-391">All other charts:</span></span>

  - <span data-ttu-id="ea80b-392">**Data**</span><span class="sxs-lookup"><span data-stu-id="ea80b-392">**Date**</span></span>
  - <span data-ttu-id="ea80b-393">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ea80b-393">**Subject**</span></span>
  - <span data-ttu-id="ea80b-394">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="ea80b-394">**Sender**</span></span>
  - <span data-ttu-id="ea80b-395">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="ea80b-395">**Recipients**</span></span>
  - <span data-ttu-id="ea80b-396">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="ea80b-396">**Detected by**</span></span>
  - <span data-ttu-id="ea80b-397">**Stato del recapito**</span><span class="sxs-lookup"><span data-stu-id="ea80b-397">**Delivery Status**</span></span>
  - <span data-ttu-id="ea80b-398">**Origine del compromesso**</span><span class="sxs-lookup"><span data-stu-id="ea80b-398">**Source of Compromise**</span></span>
  - <span data-ttu-id="ea80b-399">**Tag**</span><span class="sxs-lookup"><span data-stu-id="ea80b-399">**Tags**</span></span>

  <span data-ttu-id="ea80b-400">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-400">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ea80b-401">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ea80b-401">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ea80b-402">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="ea80b-402">**Detection**</span></span>
  - <span data-ttu-id="ea80b-403">**Protetto da**: **difensore per Office 365** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="ea80b-403">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="ea80b-404">**Tag**: filtrare i risultati in base agli utenti o ai gruppi a cui è stato applicato il tag utente specificato (compresi gli account prioritari).</span><span class="sxs-lookup"><span data-stu-id="ea80b-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ea80b-405">Per ulteriori informazioni sui tag degli utenti, vedere [tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="ea80b-406">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="ea80b-406">**Domain**</span></span>
  - <span data-ttu-id="ea80b-407">**Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella Dettagli)</span><span class="sxs-lookup"><span data-stu-id="ea80b-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="ea80b-408">Rapporto malware principale</span><span class="sxs-lookup"><span data-stu-id="ea80b-408">Top malware report</span></span>

<span data-ttu-id="ea80b-409">Il rapporto **malware principale** illustra i diversi tipi di malware rilevati dalla [protezione antimalware in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-409">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="ea80b-410">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al  \> **Dashboard** dei report e selezionare **malware principale**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-410">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="ea80b-411">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="ea80b-411">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Widget malware principale nel dashboard report](../../media/top-malware-report-widget.png)

<span data-ttu-id="ea80b-413">Quando si posiziona il puntatore del mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi che sono stati rilevati come aventi quel malware.</span><span class="sxs-lookup"><span data-stu-id="ea80b-413">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Visualizzazione del rapporto di malware principale](../../media/top-malware-report-view.png)

<span data-ttu-id="ea80b-415">Se si fa clic su **Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-415">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="ea80b-416">**Malware principale**</span><span class="sxs-lookup"><span data-stu-id="ea80b-416">**Top malware**</span></span>
- <span data-ttu-id="ea80b-417">**Numero**</span><span class="sxs-lookup"><span data-stu-id="ea80b-417">**Count**</span></span>

<span data-ttu-id="ea80b-418">Se si fa clic su **filtri** nella visualizzazione visualizzazione report o tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-418">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="ea80b-419">Report sulla protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="ea80b-419">URL threat protection report</span></span>

<span data-ttu-id="ea80b-420">Il **rapporto sulla protezione delle minacce URL** è disponibile in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea80b-420">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ea80b-421">Per ulteriori informazioni, vedere [URL Threat Protection report](view-reports-for-atp.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="ea80b-421">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="ea80b-422">Report dei messaggi segnalati dall'utente</span><span class="sxs-lookup"><span data-stu-id="ea80b-422">User-reported messages report</span></span>

<span data-ttu-id="ea80b-423">Il rapporto **messaggi segnalati dall'utente** Visualizza informazioni sui messaggi di posta elettronica che gli utenti hanno segnalato come posta indesiderata, tentativi di phishing o una buona corrispondenza tramite il componente aggiuntivo del [messaggio di report](enable-the-report-message-add-in.md) o il componente aggiuntivo di [phishing del report](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-423">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="ea80b-424">I dettagli sono disponibili per ogni messaggio, incluso il motivo del recapito, una regola di protezione da posta indesiderata o un flusso di posta configurata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea80b-424">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="ea80b-425">Per visualizzare i dettagli, selezionare un elemento nell'elenco User-Reports e quindi visualizzare le informazioni nelle schede **Riepilogo** e **Dettagli** .</span><span class="sxs-lookup"><span data-stu-id="ea80b-425">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![Il rapporto messaggi di User-Reported Visualizza i messaggi che gli utenti sono contrassegnati come posta indesiderata, non indesiderata o tentativi di phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="ea80b-427">Per visualizzare il report, nel [Centro sicurezza & Compliance](https://protection.office.com)eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea80b-427">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="ea80b-428">Accedere a  \>  \> **messaggi segnalati dall'utente** del dashboard di gestione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="ea80b-428">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="ea80b-429">Passare a **gestione minacce** \> **esaminare** \> **i messaggi segnalati dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="ea80b-429">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![Nel centro sicurezza & conformità, scegliere \> \> messaggi segnalati dall'utente di Threat Management Review](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="ea80b-431">Affinché il rapporto messaggi segnalati dall'utente funzioni correttamente, **è necessario che la registrazione di controllo sia attivata** per l'ambiente Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea80b-431">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="ea80b-432">Questa operazione viene in genere fatta da una persona a cui è stato assegnato il ruolo registri di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ea80b-432">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="ea80b-433">Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca del registro di controllo di Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="ea80b-433">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="ea80b-434">Quali autorizzazioni sono necessarie per visualizzare i rapporti?</span><span class="sxs-lookup"><span data-stu-id="ea80b-434">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="ea80b-435">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel centro sicurezza & Compliance:</span><span class="sxs-lookup"><span data-stu-id="ea80b-435">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ea80b-436">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="ea80b-436">**Organization Management**</span></span>
- <span data-ttu-id="ea80b-437">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="ea80b-437">**Security Administrator**</span></span>
- <span data-ttu-id="ea80b-438">**Lettore di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="ea80b-438">**Security Reader**</span></span>
- <span data-ttu-id="ea80b-439">**Ruolo con autorizzazioni di lettura globali**</span><span class="sxs-lookup"><span data-stu-id="ea80b-439">**Global Reader**</span></span>

<span data-ttu-id="ea80b-440">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-440">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="ea80b-441">**Nota**: l'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro sicurezza & Compliance _e_ le autorizzazioni per altre caratteristiche in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea80b-441">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ea80b-442">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ea80b-442">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="ea80b-443">Cosa succede se i rapporti non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="ea80b-443">What if the reports aren't showing data?</span></span>

<span data-ttu-id="ea80b-444">Se i dati non vengono visualizzati nei rapporti, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="ea80b-444">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="ea80b-445">Per ulteriori informazioni, vedere [protezione dalle minacce](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="ea80b-445">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ea80b-446">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ea80b-446">Related topics</span></span>

[<span data-ttu-id="ea80b-447">Protezione da posta indesiderata e anti-malware in EOP</span><span class="sxs-lookup"><span data-stu-id="ea80b-447">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="ea80b-448">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="ea80b-448">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="ea80b-449">Visualizzare i report sul flusso di posta elettronica nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="ea80b-449">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="ea80b-450">Visualizzare i report per il difensore per Office 365</span><span class="sxs-lookup"><span data-stu-id="ea80b-450">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
