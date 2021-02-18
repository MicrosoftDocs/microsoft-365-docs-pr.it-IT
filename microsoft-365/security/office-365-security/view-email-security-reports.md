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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Informazioni su come trovare e utilizzare i report di sicurezza della posta elettronica per l'organizzazione. I report di sicurezza della posta elettronica sono disponibili nel Centro sicurezza & conformità.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f6d9f149c9e1c71532018e6b43a6e9e31eb04607
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290800"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="ec392-104">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="ec392-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ec392-105">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="ec392-105">**Applies to**</span></span>
- [<span data-ttu-id="ec392-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ec392-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ec392-107">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="ec392-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ec392-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec392-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ec392-109">Nel Centro sicurezza e conformità sono disponibili diversi report che consentono di vedere in che modo le funzionalità di sicurezza della posta elettronica, ad esempio la protezione da posta indesiderata, antimalware e crittografia in Microsoft 365, proteggono l'organizzazione. [&](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="ec392-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="ec392-110">Se si dispone delle [autorizzazioni necessarie,](#what-permissions-are-needed-to-view-these-reports)è possibile visualizzare questi report nel Centro sicurezza & conformità selezionando **Dashboard** \> **report.**</span><span class="sxs-lookup"><span data-stu-id="ec392-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="ec392-111">Per passare direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="ec392-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard report nel Centro sicurezza & conformità](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="ec392-113">Report degli utenti compromessi</span><span class="sxs-lookup"><span data-stu-id="ec392-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="ec392-114">Questo report è disponibile nelle organizzazioni di Microsoft 365 con cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ec392-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="ec392-115">Non è disponibile nelle organizzazioni Exchange Online Protection (EOP) autonome.</span><span class="sxs-lookup"><span data-stu-id="ec392-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="ec392-116">Il **report Utenti compromessi** mostra il numero di  account  utente contrassegnati come sospetti o con restrizioni negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="ec392-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="ec392-117">Gli account in uno di questi stati sono problematici o addirittura compromessi.</span><span class="sxs-lookup"><span data-stu-id="ec392-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="ec392-118">Con un uso frequente, puoi usare il report per individuare picchi e persino tendenze in account sospetti o con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="ec392-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="ec392-119">Per ulteriori informazioni sugli utenti compromessi, vedere [Risposta a un account di posta elettronica compromesso.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Utenti compromessi nel dashboard report](../../media/compromised-users-report-widget.png)

<span data-ttu-id="ec392-121">La visualizzazione aggregata mostra i dati degli ultimi 90 giorni e la visualizzazione dettagli mostra i dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="ec392-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="ec392-122">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **al** dashboard dei report e \>  selezionare **Utenti compromessi.**</span><span class="sxs-lookup"><span data-stu-id="ec392-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="ec392-123">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="ec392-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="ec392-124">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtri** e selezionando uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="ec392-125">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="ec392-126">**Sospetto:** l'account utente ha inviato messaggi di posta elettronica sospetti e rischia di essere limitato all'invio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ec392-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="ec392-127">**Con restrizioni:** all'account utente è stato limitato l'invio di posta elettronica a causa di modelli altamente sospetti.</span><span class="sxs-lookup"><span data-stu-id="ec392-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Visualizzazione report nel report Utenti compromessi](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="ec392-129">Se si fa **clic su Visualizza tabella dettagli,** è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="ec392-130">**Ora creazione**</span><span class="sxs-lookup"><span data-stu-id="ec392-130">**Creation time**</span></span>
- <span data-ttu-id="ec392-131">**ID utente**</span><span class="sxs-lookup"><span data-stu-id="ec392-131">**User ID**</span></span>
- <span data-ttu-id="ec392-132">**Azione**</span><span class="sxs-lookup"><span data-stu-id="ec392-132">**Action**</span></span>

<span data-ttu-id="ec392-133">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="ec392-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="ec392-134">Report Crittografia</span><span class="sxs-lookup"><span data-stu-id="ec392-134">Encryption report</span></span>

<span data-ttu-id="ec392-135">Il **rapporto crittografia** è disponibile in EOP (sottoscrizioni con cassette postali in Exchange Online o EOP autonomo senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="ec392-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="ec392-136">Il team di sicurezza dell'organizzazione può utilizzare le informazioni contenute in questo report per identificare i modelli e applicare o modificare in modo proattivo i criteri per i messaggi di posta elettronica sensibili.</span><span class="sxs-lookup"><span data-stu-id="ec392-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="ec392-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ec392-137">For example:</span></span>

- <span data-ttu-id="ec392-138">Se viene visualizzato un numero elevato di messaggi di posta elettronica crittografati dagli utenti, è possibile aggiungere un criterio di crittografia per automatizzare la crittografia per determinati casi d'uso.</span><span class="sxs-lookup"><span data-stu-id="ec392-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="ec392-139">Per ulteriori informazioni, vedere [Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Microsoft 365.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="ec392-140">Se sono disponibili diversi modelli di crittografia, ma nessuno li sta utilizzando, è possibile decidere se gli utenti necessitano di formazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ec392-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="ec392-141">La visualizzazione aggregata consente il filtro per gli ultimi 90 giorni, mentre la visualizzazione dettagli consente il filtro per 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="ec392-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="ec392-142">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **al** \> **dashboard dei report** e selezionare **Report di crittografia.**</span><span class="sxs-lookup"><span data-stu-id="ec392-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="ec392-143">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="ec392-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="ec392-144">Per ulteriori informazioni sulla crittografia, vedere [Crittografia della posta elettronica in Microsoft 365.](../../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="ec392-145">Visualizzazione report per il report Crittografia</span><span class="sxs-lookup"><span data-stu-id="ec392-145">Report view for the Encryption report</span></span>

<span data-ttu-id="ec392-146">Nel grafico è possibile utilizzare i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="ec392-147">**Visualizzare i dati in base a: Rapporto crittografia** messaggi e Scomposi **per: Metodo di crittografia**: Sono disponibili i seguenti metodi di crittografia:</span><span class="sxs-lookup"><span data-stu-id="ec392-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="ec392-148">**Crittografia per utente**</span><span class="sxs-lookup"><span data-stu-id="ec392-148">**Encryption by user**</span></span>
  - <span data-ttu-id="ec392-149">**Crittografia in base ai criteri**</span><span class="sxs-lookup"><span data-stu-id="ec392-149">**Encryption by policy**</span></span>

  <span data-ttu-id="ec392-150">Se si fa **clic su Filtri,** è possibile modificare il grafico con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="ec392-151">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ec392-152">Metodo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="ec392-152">Encryption method.</span></span>
  - <span data-ttu-id="ec392-153">Modello di crittografia.</span><span class="sxs-lookup"><span data-stu-id="ec392-153">Encryption template.</span></span>

- <span data-ttu-id="ec392-154">**Visualizzare i dati in base a: Rapporto crittografia** messaggi e Scomposi **per: Modello di crittografia:** sono disponibili i seguenti metodi di crittografia:</span><span class="sxs-lookup"><span data-stu-id="ec392-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="ec392-155">**Non inoltrare**</span><span class="sxs-lookup"><span data-stu-id="ec392-155">**Do not forward**</span></span>
  - <span data-ttu-id="ec392-156">**Solo crittografia**</span><span class="sxs-lookup"><span data-stu-id="ec392-156">**Encrypt only**</span></span>
  - <span data-ttu-id="ec392-157">**OME precedente**</span><span class="sxs-lookup"><span data-stu-id="ec392-157">**OME previous**</span></span>
  - <span data-ttu-id="ec392-158">**Personalizzato**</span><span class="sxs-lookup"><span data-stu-id="ec392-158">**Custom**</span></span>

  <span data-ttu-id="ec392-159">Se si fa **clic su Filtri,** è possibile modificare il grafico con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="ec392-160">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ec392-161">Metodo di crittografia</span><span class="sxs-lookup"><span data-stu-id="ec392-161">Encryption method</span></span>
  - <span data-ttu-id="ec392-162">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="ec392-162">Encryption template</span></span>

- <span data-ttu-id="ec392-163">**Visualizzare i dati per: Primi 5** domini destinatario : questa visualizzazione mostra un grafico a torta con i conteggi dei messaggi inviati per i primi 5 domini destinatario.</span><span class="sxs-lookup"><span data-stu-id="ec392-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="ec392-164">Se si fa **clic su Filtri,** è possibile selezionare una **data di inizio e** una di **fine.**</span><span class="sxs-lookup"><span data-stu-id="ec392-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="ec392-165">Visualizzazione della tabella dei dettagli per il report Crittografia</span><span class="sxs-lookup"><span data-stu-id="ec392-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="ec392-166">Se si **fa clic su Visualizza tabella dettagli,** le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="ec392-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ec392-167">**Scomporsi per: metodo di crittografia** o **scomporsi per: modello di crittografia**: vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="ec392-168">**Data**</span><span class="sxs-lookup"><span data-stu-id="ec392-168">**Date**</span></span>
  - <span data-ttu-id="ec392-169">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="ec392-169">**Sender address**</span></span>
  - <span data-ttu-id="ec392-170">**Modello di crittografia**</span><span class="sxs-lookup"><span data-stu-id="ec392-170">**Encryption template**</span></span>
  - <span data-ttu-id="ec392-171">**Metodo di crittografia**</span><span class="sxs-lookup"><span data-stu-id="ec392-171">**Encryption method**</span></span>
  - <span data-ttu-id="ec392-172">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="ec392-172">**Recipient address**</span></span>
  - <span data-ttu-id="ec392-173">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ec392-173">**Subject**</span></span>

- <span data-ttu-id="ec392-174">**Visualizzare i dati in base a: 5 domini destinatario principali:**</span><span class="sxs-lookup"><span data-stu-id="ec392-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="ec392-175">**Data**</span><span class="sxs-lookup"><span data-stu-id="ec392-175">**Date**</span></span>
  - <span data-ttu-id="ec392-176">**Dominio destinatario**</span><span class="sxs-lookup"><span data-stu-id="ec392-176">**Recipient domain**</span></span>
  - <span data-ttu-id="ec392-177">**Numero messaggi**</span><span class="sxs-lookup"><span data-stu-id="ec392-177">**Message count**</span></span>

<span data-ttu-id="ec392-178">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="ec392-179">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="ec392-180">Metodo di crittografia</span><span class="sxs-lookup"><span data-stu-id="ec392-180">Encryption method</span></span>
- <span data-ttu-id="ec392-181">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="ec392-181">Encryption template</span></span>

<span data-ttu-id="ec392-182">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="ec392-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="ec392-183">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="ec392-183">Mailflow status report</span></span>

<span data-ttu-id="ec392-184">Il **rapporto sullo stato del flusso di posta** contiene informazioni sui messaggi bloccati di malware, posta indesiderata, phishing e edge.</span><span class="sxs-lookup"><span data-stu-id="ec392-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="ec392-185">Per ulteriori dettagli, vedere [Mailflow status report.](view-mail-flow-reports.md#mailflow-status-report)</span><span class="sxs-lookup"><span data-stu-id="ec392-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="ec392-186">Rilevamenti di malware nel report di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ec392-186">Malware detections in email report</span></span>

<span data-ttu-id="ec392-187">I **rilevamenti di malware nel** rapporto di posta elettronica mostrano informazioni sui rilevamenti di malware nei messaggi di posta elettronica in arrivo e in uscita (malware rilevato da Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="ec392-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="ec392-188">Per ulteriori informazioni sulla protezione antimalware in EOP, vedere [Protezione antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="ec392-189">Il filtro di visualizzazione aggregata consente 90 giorni, mentre il filtro della tabella dei dettagli consente solo 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="ec392-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="ec392-190">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare al dashboard dei report e selezionare  \>  **Rilevamenti malware nella posta elettronica.**</span><span class="sxs-lookup"><span data-stu-id="ec392-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="ec392-191">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="ec392-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Rilevamenti di malware nel widget di posta elettronica nel dashboard dei report](../../media/malware-detections-widget.png)

<span data-ttu-id="ec392-193">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic **su Filtri** e selezionando:</span><span class="sxs-lookup"><span data-stu-id="ec392-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="ec392-194">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="ec392-195">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="ec392-195">**Inbound**</span></span>
- <span data-ttu-id="ec392-196">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="ec392-196">**Outbound**</span></span>

![Visualizzazione report nel report rilevamento malware nel report di posta elettronica](../../media/malware-detections-report-view.png)

<span data-ttu-id="ec392-198">Se si fa **clic su Visualizza tabella dettagli,** è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="ec392-199">**Data**</span><span class="sxs-lookup"><span data-stu-id="ec392-199">**Date**</span></span>
- <span data-ttu-id="ec392-200">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="ec392-200">**Sender address**</span></span>
- <span data-ttu-id="ec392-201">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="ec392-201">**Recipient address**</span></span>
- <span data-ttu-id="ec392-202">**ID messaggio:** disponibile nel campo **di intestazione Message-ID** nell'intestazione del messaggio e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="ec392-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="ec392-203">Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi uncinate).</span><span class="sxs-lookup"><span data-stu-id="ec392-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="ec392-204">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ec392-204">**Subject**</span></span>
- <span data-ttu-id="ec392-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="ec392-205">**Filename**</span></span>
- <span data-ttu-id="ec392-206">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="ec392-206">**Malware name**</span></span>

<span data-ttu-id="ec392-207">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="ec392-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="ec392-208">Rapporto latenza posta</span><span class="sxs-lookup"><span data-stu-id="ec392-208">Mail latency report</span></span>

<span data-ttu-id="ec392-209">Il **rapporto latenza della posta** contiene informazioni sulla latenza di recapito e detonazione della posta riscontrata all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ec392-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="ec392-210">Per ulteriori informazioni, vedere [Mail latency report.](view-reports-for-atp.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="ec392-210">For more information, see [Mail latency report](view-reports-for-atp.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="ec392-211">Rapporto di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="ec392-211">Sent and received email report</span></span>

<span data-ttu-id="ec392-212">Il **rapporto di posta elettronica** inviato e ricevuto contiene informazioni su malware, posta indesiderata, regole del flusso di posta (note anche come regole di trasporto) e rilevamenti di malware avanzati dopo l'ingresso della posta elettronica nel servizio.</span><span class="sxs-lookup"><span data-stu-id="ec392-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="ec392-213">Per ulteriori informazioni, vedere [Report di posta elettronica inviati e ricevuti.](view-mail-flow-reports.md#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="ec392-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="ec392-214">Report sui rilevamenti della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ec392-214">Spam detections report</span></span>

<span data-ttu-id="ec392-215">Il **rapporto rilevamenti posta indesiderata** mostra i messaggi di posta indesiderata bloccati da EOP.</span><span class="sxs-lookup"><span data-stu-id="ec392-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="ec392-216">I messaggi vengono conteggiati singolarmente, non per destinatario.</span><span class="sxs-lookup"><span data-stu-id="ec392-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="ec392-217">Ad esempio, se lo stesso messaggio di posta indesiderata è stato inviato a 100 destinatari nell'organizzazione, viene conteggiato come un unico messaggio.</span><span class="sxs-lookup"><span data-stu-id="ec392-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="ec392-218">La visualizzazione aggregata consente un filtro di 90 giorni, mentre la tabella dei dettagli consente un filtro di 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="ec392-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="ec392-219">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare al dashboard dei report  \> **e** selezionare **Rilevamenti posta indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="ec392-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="ec392-220">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="ec392-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget Rilevamenti posta indesiderata nel dashboard report](../../media/spam-detections-report-widget.png)

<span data-ttu-id="ec392-222">Per ulteriori informazioni sulla protezione da posta indesiderata, vedere Protezione da posta [indesiderata in EOP.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="ec392-223">Visualizzazione rapporto per il rapporto rilevamenti di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ec392-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="ec392-224">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="ec392-225">**Scomporsi per: Azione**: vengono visualizzati i tipi di evento seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="ec392-226">**Contenuto di posta indesiderata filtrato**</span><span class="sxs-lookup"><span data-stu-id="ec392-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="ec392-227">**Blocco IP di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="ec392-227">**Spam IP block**</span></span>
  - <span data-ttu-id="ec392-228">**Blocco di buste di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="ec392-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="ec392-229">**Filtro DBEB di posta indesiderata**: Blocco edge basato su directory (DBEB)</span><span class="sxs-lookup"><span data-stu-id="ec392-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="ec392-230">Quando si passa il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti elementi sono stati bloccati quel giorno e come tali elementi vengono categorizzati.</span><span class="sxs-lookup"><span data-stu-id="ec392-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Visualizzazione azioni nel rapporto rilevamenti posta indesiderata](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="ec392-232">**Scomporsi per: Direzione**: vengono visualizzate le seguenti indicazioni:</span><span class="sxs-lookup"><span data-stu-id="ec392-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="ec392-233">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="ec392-233">**Inbound**</span></span>
  - <span data-ttu-id="ec392-234">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="ec392-234">**Outbound**</span></span>

  ![Visualizzazione della direzione nel rapporto rilevamenti posta indesiderata](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="ec392-236">Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="ec392-237">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="ec392-238">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="ec392-238">Direction values</span></span>
- <span data-ttu-id="ec392-239">Valori del tipo di evento</span><span class="sxs-lookup"><span data-stu-id="ec392-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="ec392-240">Visualizzazione della tabella dei dettagli per il rapporto sui rilevamenti di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="ec392-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="ec392-241">Se si fa **clic su Visualizza tabella dettagli** in qualsiasi visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="ec392-242">**Data**</span><span class="sxs-lookup"><span data-stu-id="ec392-242">**Date**</span></span>
- <span data-ttu-id="ec392-243">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="ec392-243">**Sender address**</span></span>
- <span data-ttu-id="ec392-244">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="ec392-244">**Recipient address**</span></span>
- <span data-ttu-id="ec392-245">**Tipo evento**</span><span class="sxs-lookup"><span data-stu-id="ec392-245">**Event type**</span></span>
- <span data-ttu-id="ec392-246">**Azione**</span><span class="sxs-lookup"><span data-stu-id="ec392-246">**Action**</span></span>
- <span data-ttu-id="ec392-247">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ec392-247">**Subject**</span></span>

<span data-ttu-id="ec392-248">Se si fa **clic su Filtri** in una tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="ec392-249">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="ec392-250">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="ec392-250">Direction values</span></span>
- <span data-ttu-id="ec392-251">Valori del tipo di evento</span><span class="sxs-lookup"><span data-stu-id="ec392-251">Event type values</span></span>

<span data-ttu-id="ec392-252">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="ec392-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="ec392-253">Report rilevamenti spoof</span><span class="sxs-lookup"><span data-stu-id="ec392-253">Spoof detections report</span></span>

<span data-ttu-id="ec392-254">Il **report falsificazioni** mostra quanti messaggi di posta falsificati sono stati rilevati e di quelli considerati "buoni" (falsificati per motivi aziendali legittimi).</span><span class="sxs-lookup"><span data-stu-id="ec392-254">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="ec392-255">Per ulteriori informazioni sullo spoofing, vedere [Protezione anti-spoofing in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-255">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="ec392-256">La visualizzazione aggregata del report consente 90 giorni di filtro, mentre la visualizzazione dettagli consente solo dieci giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="ec392-256">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="ec392-257">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **al** \> **dashboard dei report e** selezionare **Rilevamenti spoofing.**</span><span class="sxs-lookup"><span data-stu-id="ec392-257">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="ec392-258">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="ec392-258">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widget Falsificazioni nel dashboard report](../../media/spoof-detections-widget.png)

<span data-ttu-id="ec392-260">Quando si passa il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti messaggi di posta falsificati sono stati ricevuti.</span><span class="sxs-lookup"><span data-stu-id="ec392-260">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="ec392-261">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtri** e selezionando uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-261">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="ec392-262">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-262">**Start date** and **End date**</span></span>

- <span data-ttu-id="ec392-263">**Posta buona**</span><span class="sxs-lookup"><span data-stu-id="ec392-263">**Good mail**</span></span>

- <span data-ttu-id="ec392-264">**Intercettato come posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="ec392-264">**Caught as spam**</span></span>

![Visualizzazione report nel report Rilevamenti spoofing](../../media/spoof-detections-report-view.png)

<span data-ttu-id="ec392-266">Se si fa **clic su Visualizza tabella dettagli,** è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-266">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="ec392-267">**Data**</span><span class="sxs-lookup"><span data-stu-id="ec392-267">**Date**</span></span>
- <span data-ttu-id="ec392-268">**Mittente falsificato**</span><span class="sxs-lookup"><span data-stu-id="ec392-268">**Spoofed sender**</span></span>
- <span data-ttu-id="ec392-269">**Mittente vero**</span><span class="sxs-lookup"><span data-stu-id="ec392-269">**True sender**</span></span>
- <span data-ttu-id="ec392-270">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="ec392-270">**Sender IP**</span></span>
- <span data-ttu-id="ec392-271">**Azione**</span><span class="sxs-lookup"><span data-stu-id="ec392-271">**Action**</span></span>
- <span data-ttu-id="ec392-272">**Numero messaggi**</span><span class="sxs-lookup"><span data-stu-id="ec392-272">**Message count**</span></span>

<span data-ttu-id="ec392-273">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="ec392-273">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="ec392-274">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ec392-274">Threat protection status report</span></span>

<span data-ttu-id="ec392-275">La **relazione sullo stato di** Protezione dalle minacce è disponibile sia in EOP che in Microsoft Defender per Office 365; Tuttavia, i report contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="ec392-275">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="ec392-276">Ad esempio, i clienti EOP possono visualizzare informazioni sul malware rilevato nella posta elettronica, ma non informazioni sui file dannosi rilevati da Allegati sicuri [per SharePoint, OneDrive e Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-276">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="ec392-277">Il report fornisce il conteggio dei messaggi di posta elettronica con contenuti dannosi, ad esempio file o indirizzi di siti Web (URL) bloccati dal motore antimalware, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md)e le funzionalità di Defender per Office 365 come collegamenti sicuri, allegati sicuri e [anti-phishing.](set-up-anti-phishing-policies.md) [](atp-safe-links.md) [](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-277">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="ec392-278">È possibile utilizzare queste informazioni per identificare le tendenze o determinare se i criteri dell'organizzazione devono essere rettificati.</span><span class="sxs-lookup"><span data-stu-id="ec392-278">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="ec392-279">**Nota:** è importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="ec392-279">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="ec392-280">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare al dashboard dei report  \> **e** selezionare Lo **stato di Protezione dalle minacce.**</span><span class="sxs-lookup"><span data-stu-id="ec392-280">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="ec392-281">Per passare direttamente al report, aprire uno degli URL seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-281">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="ec392-282">Microsoft Defender per Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="ec392-282">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="ec392-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="ec392-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Widget stato di protezione dalle minacce nel dashboard report](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="ec392-285">Per impostazione predefinita, il grafico mostra i dati degli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="ec392-285">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="ec392-286">Se si fa **clic su Filtri,** è possibile selezionare un intervallo di date di 90 giorni (le sottoscrizioni di valutazione potrebbero essere limitate a 30 giorni).</span><span class="sxs-lookup"><span data-stu-id="ec392-286">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="ec392-287">La visualizzazione della tabella dei dettagli consente il filtro per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="ec392-287">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="ec392-288">Visualizzazione report per il rapporto sullo stato di Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ec392-288">Report view for the Threat protection status report</span></span>

<span data-ttu-id="ec392-289">Sono disponibili le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-289">The following views are available:</span></span>

- <span data-ttu-id="ec392-290">**Visualizzare i dati in base a: Panoramica:** vengono visualizzate le seguenti informazioni di rilevamento:</span><span class="sxs-lookup"><span data-stu-id="ec392-290">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="ec392-291">**Malware di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="ec392-291">**Email malware**</span></span>
  - <span data-ttu-id="ec392-292">**E-mail phish**</span><span class="sxs-lookup"><span data-stu-id="ec392-292">**Email phish**</span></span>
  - <span data-ttu-id="ec392-293">**Malware contenuto**</span><span class="sxs-lookup"><span data-stu-id="ec392-293">**Content malware**</span></span>

  ![Visualizzazione Panoramica nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="ec392-295">**Visualizzare i dati per: contenuto \> Malware**<sup>1:</sup>vengono visualizzate le seguenti informazioni per Microsoft Defender per le organizzazioni di Office 365:</span><span class="sxs-lookup"><span data-stu-id="ec392-295">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="ec392-296">**Motore antimalware:** file dannosi rilevati in Sharepoint, OneDrive e Microsoft Teams dal rilevamento di [virus predefinito in Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-296">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="ec392-297">**Detonazione file:** file dannosi rilevati [da Allegati sicuri per SharePoint, OneDrive e Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-297">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

  ![Visualizzazione malware del contenuto nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="ec392-299">**Visualizzare i dati in base a: Sostituzione messaggio**: vengono visualizzate le seguenti informazioni sul motivo della sostituzione:</span><span class="sxs-lookup"><span data-stu-id="ec392-299">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="ec392-300">**Ignora locale**</span><span class="sxs-lookup"><span data-stu-id="ec392-300">**On-premises skip**</span></span>
  - <span data-ttu-id="ec392-301">**IP consentiti**</span><span class="sxs-lookup"><span data-stu-id="ec392-301">**IP Allow**</span></span>
  - <span data-ttu-id="ec392-302">**Regola del flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="ec392-302">**Mail flow rule**</span></span>
  - <span data-ttu-id="ec392-303">**Mittente consentito**</span><span class="sxs-lookup"><span data-stu-id="ec392-303">**Sender allow**</span></span>
  - <span data-ttu-id="ec392-304">**Dominio consentito**</span><span class="sxs-lookup"><span data-stu-id="ec392-304">**Domain allow**</span></span>
  - <span data-ttu-id="ec392-305">**ZAP non abilitato**</span><span class="sxs-lookup"><span data-stu-id="ec392-305">**ZAP not enabled**</span></span>
  - <span data-ttu-id="ec392-306">**Cartella Posta indesiderata non abilitata**</span><span class="sxs-lookup"><span data-stu-id="ec392-306">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="ec392-307">**Mittente sicuro dell'utente**</span><span class="sxs-lookup"><span data-stu-id="ec392-307">**User Safe Sender**</span></span>
  - <span data-ttu-id="ec392-308">**Dominio sicuro dell'utente**</span><span class="sxs-lookup"><span data-stu-id="ec392-308">**User Safe Domain**</span></span>

  ![Visualizzazione sostituzione messaggio nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="ec392-310">**Scomporsi per: tecnologia di rilevamento** **e visualizzazione dei dati per: e-mail \> phish**: Vengono visualizzate le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="ec392-310">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="ec392-311">**Reputazione URL generata da ATP**<sup>1:</sup>reputazione degli URL dannosi generata dalle detonazioni di Defender per Office 365 in altri clienti di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec392-311">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="ec392-312">**Filtro phishing avanzato:** segnali di phishing basati sull'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="ec392-312">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="ec392-313">**Anti-spoofing - Errore DMARC:** errore di autenticazione DMARC nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="ec392-313">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="ec392-314">**Anti-spoofing - intra-org:** il mittente sta tentando di effettuare lo spoofing del dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="ec392-314">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="ec392-315">**Anti-spoofing - dominio esterno:** il mittente sta tentando di effettuare lo spoofing di un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="ec392-315">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="ec392-316">**Rappresentazione del marchio**: rappresentazione di marchi noti in base ai mittenti.</span><span class="sxs-lookup"><span data-stu-id="ec392-316">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="ec392-317">**Rappresentazione del dominio**<sup>1</sup>: Rappresentazione dei domini che il cliente possiede o definisce.</span><span class="sxs-lookup"><span data-stu-id="ec392-317">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="ec392-318">**Reputazione URL EOP**: reputazione URL dannoso.</span><span class="sxs-lookup"><span data-stu-id="ec392-318">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="ec392-319">**Filtro phishing generale:** segnali di phishing basati sulle regole dell'analista.</span><span class="sxs-lookup"><span data-stu-id="ec392-319">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="ec392-320">**Altri**</span><span class="sxs-lookup"><span data-stu-id="ec392-320">**Others**</span></span>
  - <span data-ttu-id="ec392-321">**Phishing ZAP**<sup>2:</sup>eliminazione automatica dei messaggi di phishing a zero ore.</span><span class="sxs-lookup"><span data-stu-id="ec392-321">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="ec392-322">**Detonazione URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ec392-322">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="ec392-323">**Rappresentazione utente**<sup>1</sup>: Rappresentazione degli utenti definiti dall'amministratore o appresi tramite l'intelligence delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="ec392-323">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Visualizzazione della tecnologia di rilevamento per la posta elettronica di phishing nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="ec392-325">**Scomporsi per: tecnologia di rilevamento** **e visualizzazione dei dati per: \> Malware** di posta elettronica : vengono visualizzate le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="ec392-325">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="ec392-326">**Reputazione file generata da ATP**<sup>1:</sup>tutta la reputazione dei file dannosi generata da Defender per le detonazioni di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ec392-326">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="ec392-327">**Motore antimalware**<sup>1:</sup>rilevamento da motori antimalware.</span><span class="sxs-lookup"><span data-stu-id="ec392-327">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="ec392-328">**Blocco del tipo di file dei** criteri antimalware: si tratta di messaggi di posta elettronica filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="ec392-328">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="ec392-329">**Detonazione del file**<sup>1:</sup>rilevamento tramite allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="ec392-329">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="ec392-330">**Reputazione di file dannosi**</span><span class="sxs-lookup"><span data-stu-id="ec392-330">**Malicious file reputation**</span></span>
  - <span data-ttu-id="ec392-331">**Malware ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ec392-331">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="ec392-332">**Altri**</span><span class="sxs-lookup"><span data-stu-id="ec392-332">**Others**</span></span>

  ![Visualizzazione della tecnologia di rilevamento per il malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="ec392-334">**Scomporsi per: Tipo** di criterio e Visualizza dati **per: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span><span class="sxs-lookup"><span data-stu-id="ec392-334">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="ec392-335">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="ec392-335">**Anti-malware**</span></span>
  - <span data-ttu-id="ec392-336">**Allegati sicuri**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ec392-336">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="ec392-337">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="ec392-337">**Anti-phish**</span></span>
  - <span data-ttu-id="ec392-338">**Protezione da posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="ec392-338">**Anti-spam**</span></span>
  - <span data-ttu-id="ec392-339">**Regola del flusso di** posta (nota anche come regola di trasporto)</span><span class="sxs-lookup"><span data-stu-id="ec392-339">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="ec392-340">**Altri**</span><span class="sxs-lookup"><span data-stu-id="ec392-340">**Others**</span></span>

  ![Visualizzazione del tipo di criterio per la posta elettronica di phishing nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="ec392-342">**Scomporsi per: Stato del recapito** e Visualizza dati **per: \> E-mail Phish** o **View data by: Email \> Malware**: The following information is shown:</span><span class="sxs-lookup"><span data-stu-id="ec392-342">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="ec392-343">**Recapito non riuscito**</span><span class="sxs-lookup"><span data-stu-id="ec392-343">**Delivery failed**</span></span>
  - <span data-ttu-id="ec392-344">**Rilasciato**</span><span class="sxs-lookup"><span data-stu-id="ec392-344">**Dropped**</span></span>
  - <span data-ttu-id="ec392-345">**Inoltrato**</span><span class="sxs-lookup"><span data-stu-id="ec392-345">**Forwarded**</span></span>
  - <span data-ttu-id="ec392-346">**Cassetta postale ospitata: cartella personalizzata**</span><span class="sxs-lookup"><span data-stu-id="ec392-346">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="ec392-347">**Cassetta postale ospitata: elementi eliminati**</span><span class="sxs-lookup"><span data-stu-id="ec392-347">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="ec392-348">**Cassetta postale ospitata: Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="ec392-348">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="ec392-349">**Cassetta postale ospitata: Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="ec392-349">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="ec392-350">**Server locale: recapitato**</span><span class="sxs-lookup"><span data-stu-id="ec392-350">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="ec392-351">**Quarantena**</span><span class="sxs-lookup"><span data-stu-id="ec392-351">**Quarantine**</span></span>

  ![Visualizzazione dello stato del recapito per la posta elettronica di phishing nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="ec392-353"><sup>1</sup> Defender solo per Office 365</span><span class="sxs-lookup"><span data-stu-id="ec392-353"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="ec392-354"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span><span class="sxs-lookup"><span data-stu-id="ec392-354"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="ec392-355">Se si fa **clic su Filtri,** i filtri disponibili dipendono dal grafico che si stava osservando:</span><span class="sxs-lookup"><span data-stu-id="ec392-355">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ec392-356">Per **Visualizzare i dati in base a: \> Malware** contenuto, è possibile modificare il report in base alla data di inizio **e** alla data **di fine** e al **valore di** rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ec392-356">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="ec392-357">Per **Visualizza dati in base a: Sostituzione messaggio,** è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-357">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ec392-358">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-358">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ec392-359">**Motivo sostituzione**</span><span class="sxs-lookup"><span data-stu-id="ec392-359">**Override Reason**</span></span>
  - <span data-ttu-id="ec392-360">**Tag:** filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="ec392-360">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ec392-361">Per ulteriori informazioni sui tag utente, vedere [Tag utente.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-361">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="ec392-362">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="ec392-362">**Domain**</span></span>

- <span data-ttu-id="ec392-363">Per tutte le altre visualizzazioni, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-363">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ec392-364">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-364">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ec392-365">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="ec392-365">**Detection**</span></span>
  - <span data-ttu-id="ec392-366">**Protetto da**: **ATP** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="ec392-366">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="ec392-367">**Tag:** filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="ec392-367">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ec392-368">Per ulteriori informazioni sui tag utente, vedere [Tag utente.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-368">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="ec392-369">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="ec392-369">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="ec392-370">Visualizzazione della tabella dei dettagli per il rapporto sullo stato di Protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ec392-370">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="ec392-371">Se si **fa clic su Visualizza tabella dettagli,** le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="ec392-371">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ec392-372">**Visualizza dati in base a: Panoramica:** non **è disponibile** il pulsante Visualizza tabella dettagli.</span><span class="sxs-lookup"><span data-stu-id="ec392-372">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="ec392-373">**Visualizzare i dati per: contenuto \> Malware:**</span><span class="sxs-lookup"><span data-stu-id="ec392-373">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="ec392-374">**Data**</span><span class="sxs-lookup"><span data-stu-id="ec392-374">**Date**</span></span>
  - <span data-ttu-id="ec392-375">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="ec392-375">**Location**</span></span>
  - <span data-ttu-id="ec392-376">**Diretto da**</span><span class="sxs-lookup"><span data-stu-id="ec392-376">**Directed by**</span></span>
  - <span data-ttu-id="ec392-377">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="ec392-377">**Malware name**</span></span>

  <span data-ttu-id="ec392-378">Se si fa **clic su** Filtri in questa visualizzazione, è possibile modificare il report in base alla data di inizio **e** alla data **di fine** e al **valore di** rilevamento.</span><span class="sxs-lookup"><span data-stu-id="ec392-378">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="ec392-379">**Visualizzare i dati in base a: Sostituzione messaggio:**</span><span class="sxs-lookup"><span data-stu-id="ec392-379">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="ec392-380">**Data**</span><span class="sxs-lookup"><span data-stu-id="ec392-380">**Date**</span></span>
  - <span data-ttu-id="ec392-381">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ec392-381">**Subject**</span></span>
  - <span data-ttu-id="ec392-382">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="ec392-382">**Sender**</span></span>
  - <span data-ttu-id="ec392-383">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="ec392-383">**Recipients**</span></span>
  - <span data-ttu-id="ec392-384">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="ec392-384">**Detected by**</span></span>
  - <span data-ttu-id="ec392-385">**Motivo sostituzione**</span><span class="sxs-lookup"><span data-stu-id="ec392-385">**Override Reason**</span></span>
  - <span data-ttu-id="ec392-386">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="ec392-386">**Source of Compromise**</span></span>
  - <span data-ttu-id="ec392-387">**Tag**</span><span class="sxs-lookup"><span data-stu-id="ec392-387">**Tags**</span></span>

  <span data-ttu-id="ec392-388">Se si fa **clic su** Filtri in questa visualizzazione, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-388">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ec392-389">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-389">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ec392-390">**Motivo sostituzione**</span><span class="sxs-lookup"><span data-stu-id="ec392-390">**Override Reason**</span></span>
  - <span data-ttu-id="ec392-391">**Tag:** filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="ec392-391">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ec392-392">Per ulteriori informazioni sui tag utente, vedere [Tag utente.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-392">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="ec392-393">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="ec392-393">**Domain**</span></span>
  - <span data-ttu-id="ec392-394">**Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="ec392-394">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="ec392-395">Tutti gli altri grafici:</span><span class="sxs-lookup"><span data-stu-id="ec392-395">All other charts:</span></span>

  - <span data-ttu-id="ec392-396">**Data**</span><span class="sxs-lookup"><span data-stu-id="ec392-396">**Date**</span></span>
  - <span data-ttu-id="ec392-397">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ec392-397">**Subject**</span></span>
  - <span data-ttu-id="ec392-398">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="ec392-398">**Sender**</span></span>
  - <span data-ttu-id="ec392-399">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="ec392-399">**Recipients**</span></span>
  - <span data-ttu-id="ec392-400">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="ec392-400">**Detected by**</span></span>
  - <span data-ttu-id="ec392-401">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="ec392-401">**Delivery Status**</span></span>
  - <span data-ttu-id="ec392-402">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="ec392-402">**Source of Compromise**</span></span>
  - <span data-ttu-id="ec392-403">**Tag**</span><span class="sxs-lookup"><span data-stu-id="ec392-403">**Tags**</span></span>

  <span data-ttu-id="ec392-404">Se si fa **clic su Filtri,** è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-404">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ec392-405">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="ec392-405">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ec392-406">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="ec392-406">**Detection**</span></span>
  - <span data-ttu-id="ec392-407">**Protetto da**: **Defender per Office 365** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="ec392-407">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="ec392-408">**Tag:** filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="ec392-408">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ec392-409">Per ulteriori informazioni sui tag utente, vedere [Tag utente.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-409">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="ec392-410">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="ec392-410">**Domain**</span></span>
  - <span data-ttu-id="ec392-411">**Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="ec392-411">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="ec392-412">Report principale sul malware</span><span class="sxs-lookup"><span data-stu-id="ec392-412">Top malware report</span></span>

<span data-ttu-id="ec392-413">Il **report malware** principale mostra i vari tipi di malware rilevati dalla protezione [antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-413">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="ec392-414">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **al** \> **dashboard dei report e** selezionare **Malware principale.**</span><span class="sxs-lookup"><span data-stu-id="ec392-414">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="ec392-415">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="ec392-415">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Widget malware principale nel dashboard report](../../media/top-malware-report-widget.png)

<span data-ttu-id="ec392-417">Quando si passa il mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi rilevati come malware.</span><span class="sxs-lookup"><span data-stu-id="ec392-417">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Visualizzazione principale del report antimalware](../../media/top-malware-report-view.png)

<span data-ttu-id="ec392-419">Se si fa **clic su Visualizza tabella dettagli,** è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-419">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="ec392-420">**Malware principale**</span><span class="sxs-lookup"><span data-stu-id="ec392-420">**Top malware**</span></span>
- <span data-ttu-id="ec392-421">**Numero**</span><span class="sxs-lookup"><span data-stu-id="ec392-421">**Count**</span></span>

<span data-ttu-id="ec392-422">Se si fa **clic su Filtri** nella visualizzazione report o nella visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="ec392-422">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="ec392-423">Report di protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="ec392-423">URL threat protection report</span></span>

<span data-ttu-id="ec392-424">Il **report di protezione dalle minacce URL** è disponibile in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="ec392-424">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ec392-425">Per ulteriori informazioni, vedere il [report di protezione dalle minacce URL.](view-reports-for-atp.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="ec392-425">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="ec392-426">Rapporto messaggi segnalati dall'utente</span><span class="sxs-lookup"><span data-stu-id="ec392-426">User-reported messages report</span></span>

<span data-ttu-id="ec392-427">Il **rapporto** Messaggi segnalati dall'utente mostra informazioni sui messaggi di posta elettronica segnalati [](enable-the-report-message-add-in.md) dagli utenti come posta indesiderata, tentativi di phishing o buona posta utilizzando il componente aggiuntivo Segnala messaggio o Il componente aggiuntivo Segnala [phishing.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-427">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="ec392-428">Sono disponibili dettagli per ogni messaggio, incluso il motivo del recapito, ad esempio un'eccezione del criterio di posta indesiderata o una regola del flusso di posta configurata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ec392-428">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="ec392-429">Per visualizzare i dettagli, selezionare un elemento nell'elenco dei report utente e quindi visualizzare le informazioni nelle schede **Riepilogo** **e** Dettagli.</span><span class="sxs-lookup"><span data-stu-id="ec392-429">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![Il User-Reported messaggi di posta elettronica mostra i messaggi etichettati come posta indesiderata, non posta indesiderata o tentativi di phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="ec392-431">Per visualizzare questo report, nel [Centro sicurezza & conformità](https://protection.office.com)eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec392-431">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="ec392-432">Passare a **Messaggi segnalati dall'utente** nel \> **dashboard** \> **di gestione delle minacce.**</span><span class="sxs-lookup"><span data-stu-id="ec392-432">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="ec392-433">Passare a **Verifica messaggi segnalati** \>  \> **dall'utente nella gestione delle minacce.**</span><span class="sxs-lookup"><span data-stu-id="ec392-433">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![Nel Centro sicurezza & conformità scegliere Gestione minacce \> Esaminare i messaggi segnalati \> dall'utente](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="ec392-435">Per il corretto funzionamento del rapporto Messaggi  segnalati dall'utente, è necessario che la registrazione di controllo sia attivata per l'ambiente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ec392-435">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="ec392-436">Questa operazione viene in genere eseguita da un utente a cui è assegnato il ruolo Registri di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ec392-436">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="ec392-437">Per ulteriori informazioni, vedere Attivare o disattivare la ricerca nel log di [controllo di Microsoft 365.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-437">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="ec392-438">Quali autorizzazioni sono necessarie per visualizzare questi report?</span><span class="sxs-lookup"><span data-stu-id="ec392-438">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="ec392-439">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="ec392-439">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ec392-440">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="ec392-440">**Organization Management**</span></span>
- <span data-ttu-id="ec392-441">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="ec392-441">**Security Administrator**</span></span>
- <span data-ttu-id="ec392-442">**Lettore di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="ec392-442">**Security Reader**</span></span>
- <span data-ttu-id="ec392-443">**Lettore globale**</span><span class="sxs-lookup"><span data-stu-id="ec392-443">**Global Reader**</span></span>

<span data-ttu-id="ec392-444">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ec392-444">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="ec392-445">**Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft  365 offre agli utenti le autorizzazioni necessarie nel Centro sicurezza & e conformità e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec392-445">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ec392-446">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ec392-446">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="ec392-447">Cosa succede se i report non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="ec392-447">What if the reports aren't showing data?</span></span>

<span data-ttu-id="ec392-448">Se i dati nei report non vengono visualizzati, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="ec392-448">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="ec392-449">Per ulteriori informazioni, vedere [Protezione dalle minacce.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="ec392-449">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ec392-450">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ec392-450">Related topics</span></span>

[<span data-ttu-id="ec392-451">Protezione antispam e antimalware in EOP</span><span class="sxs-lookup"><span data-stu-id="ec392-451">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="ec392-452">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="ec392-452">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="ec392-453">Visualizzare i report del flusso di posta nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="ec392-453">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="ec392-454">Visualizzare i report per Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="ec392-454">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
