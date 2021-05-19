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
ms.openlocfilehash: 11fe6fd76d21b2dbd7a3e651d40efaa79f675a43
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52531027"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="a0bfa-104">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="a0bfa-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a0bfa-105">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-105">**Applies to**</span></span>
- [<span data-ttu-id="a0bfa-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a0bfa-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a0bfa-107">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="a0bfa-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a0bfa-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0bfa-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a0bfa-109">Nel Centro sicurezza e conformità è disponibile [un'ampia](https://protection.office.com) gamma di report che consentono di verificare in che modo le funzionalità di sicurezza della posta elettronica, ad esempio la protezione da posta indesiderata, antimalware e crittografia in Microsoft 365, proteggono l'organizzazione. &</span><span class="sxs-lookup"><span data-stu-id="a0bfa-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="a0bfa-110">Se si dispone delle [autorizzazioni necessarie,](#what-permissions-are-needed-to-view-these-reports)è possibile visualizzare questi report nel Centro sicurezza & conformità andando a **Dashboard** \> **report.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="a0bfa-111">Per passare direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="a0bfa-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard dei report nel Centro sicurezza & conformità](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="a0bfa-113">Report utenti compromessi</span><span class="sxs-lookup"><span data-stu-id="a0bfa-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="a0bfa-114">Questo report è disponibile nelle organizzazioni Microsoft 365 con Exchange Online cassette postali.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="a0bfa-115">Non è disponibile nelle organizzazioni autonome Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="a0bfa-116">Il **report Utenti compromessi** mostra il numero di  account  utente contrassegnati come sospetti o con restrizioni negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="a0bfa-117">Gli account in uno di questi stati sono problematici o addirittura compromessi.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="a0bfa-118">Con un uso frequente, è possibile utilizzare il report per individuare picchi e persino tendenze in account sospetti o con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="a0bfa-119">Per ulteriori informazioni sugli utenti compromessi, vedere [Risposta a un account di posta elettronica compromesso.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Utenti compromessi nel dashboard report](../../media/compromised-users-report-widget.png)

<span data-ttu-id="a0bfa-121">La visualizzazione aggregata mostra i dati degli ultimi 90 giorni e la visualizzazione dettagli mostra i dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="a0bfa-122">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Utenti compromessi.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="a0bfa-123">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="a0bfa-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="a0bfa-124">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtri** e selezionando uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="a0bfa-125">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="a0bfa-126">**Sospetto:** l'account utente ha inviato messaggi di posta elettronica sospetti ed è a rischio di essere limitato a inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="a0bfa-127">**Con restrizioni**: all'account utente è stato limitato l'invio di posta elettronica a causa di modelli altamente sospetti.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Visualizzazione report nel report Utenti compromessi](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="a0bfa-129">Se si fa **clic su Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="a0bfa-130">**Ora creazione**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-130">**Creation time**</span></span>
- <span data-ttu-id="a0bfa-131">**ID utente**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-131">**User ID**</span></span>
- <span data-ttu-id="a0bfa-132">**Azione**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-132">**Action**</span></span>

<span data-ttu-id="a0bfa-133">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="a0bfa-134">Report crittografia</span><span class="sxs-lookup"><span data-stu-id="a0bfa-134">Encryption report</span></span>

<span data-ttu-id="a0bfa-135">Il **report Crittografia** è disponibile in EOP (sottoscrizioni con cassette postali in Exchange Online o EOP autonomo senza Exchange Online cassette postali).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="a0bfa-136">Il team di sicurezza dell'organizzazione può utilizzare le informazioni contenute in questo report per identificare i modelli e applicare o modificare in modo proattivo i criteri per i messaggi di posta elettronica sensibili.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="a0bfa-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-137">For example:</span></span>

- <span data-ttu-id="a0bfa-138">Se viene visualizzato un numero elevato di messaggi di posta elettronica crittografati dagli utenti, è possibile aggiungere un criterio di crittografia per automatizzare la crittografia per determinati casi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="a0bfa-139">Per ulteriori informazioni, vedere [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="a0bfa-140">Se sono disponibili diversi modelli di crittografia ma nessuno li utilizza, è possibile verificare se gli utenti necessitano di formazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="a0bfa-141">La visualizzazione aggregata consente il filtro per gli ultimi 90 giorni, mentre la visualizzazione dettagli consente il filtro per 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="a0bfa-142">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Report di crittografia.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="a0bfa-143">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="a0bfa-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="a0bfa-144">Per ulteriori informazioni sulla crittografia, vedere [Crittografia della posta elettronica in Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="a0bfa-145">Visualizzazione report per il report Crittografia</span><span class="sxs-lookup"><span data-stu-id="a0bfa-145">Report view for the Encryption report</span></span>

<span data-ttu-id="a0bfa-146">Nel grafico è possibile utilizzare i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="a0bfa-147">**Visualizzare i dati per: Rapporto crittografia** messaggi **e Suddivide per: Metodo** di crittografia : sono disponibili i metodi di crittografia seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="a0bfa-148">**Crittografia per utente**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-148">**Encryption by user**</span></span>
  - <span data-ttu-id="a0bfa-149">**Crittografia in base ai criteri**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-149">**Encryption by policy**</span></span>

  <span data-ttu-id="a0bfa-150">Se si fa **clic su Filtri**, è possibile modificare il grafico con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="a0bfa-151">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a0bfa-152">Metodo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-152">Encryption method.</span></span>
  - <span data-ttu-id="a0bfa-153">Modello di crittografia.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-153">Encryption template.</span></span>

- <span data-ttu-id="a0bfa-154">**Visualizzare i dati per: Rapporto crittografia messaggi** **ed Suddivide per: Modello** di crittografia : sono disponibili i metodi di crittografia seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="a0bfa-155">**Non inoltrare**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-155">**Do not forward**</span></span>
  - <span data-ttu-id="a0bfa-156">**Crittografa solo**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-156">**Encrypt only**</span></span>
  - <span data-ttu-id="a0bfa-157">**OME precedente**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-157">**OME previous**</span></span>
  - <span data-ttu-id="a0bfa-158">**Personalizzato**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-158">**Custom**</span></span>

  <span data-ttu-id="a0bfa-159">Se si fa **clic su Filtri**, è possibile modificare il grafico con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="a0bfa-160">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a0bfa-161">Metodo di crittografia</span><span class="sxs-lookup"><span data-stu-id="a0bfa-161">Encryption method</span></span>
  - <span data-ttu-id="a0bfa-162">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="a0bfa-162">Encryption template</span></span>

- <span data-ttu-id="a0bfa-163">**Visualizzare i dati per: Top 5 recipient domains**: Questa visualizzazione mostra un grafico a torta con i conteggi dei messaggi inviati per i primi 5 domini destinatario.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="a0bfa-164">Se si fa **clic su Filtri**, è possibile selezionare una data di inizio **e** una data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="a0bfa-165">Visualizzazione tabella dettagli per il report Crittografia</span><span class="sxs-lookup"><span data-stu-id="a0bfa-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="a0bfa-166">Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a0bfa-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="a0bfa-168">**Data**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-168">**Date**</span></span>
  - <span data-ttu-id="a0bfa-169">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-169">**Sender address**</span></span>
  - <span data-ttu-id="a0bfa-170">**Modello di crittografia**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-170">**Encryption template**</span></span>
  - <span data-ttu-id="a0bfa-171">**Metodo di crittografia**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-171">**Encryption method**</span></span>
  - <span data-ttu-id="a0bfa-172">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-172">**Recipient address**</span></span>
  - <span data-ttu-id="a0bfa-173">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-173">**Subject**</span></span>

- <span data-ttu-id="a0bfa-174">**Visualizzare i dati per: Top 5 recipient domains**:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="a0bfa-175">**Data**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-175">**Date**</span></span>
  - <span data-ttu-id="a0bfa-176">**Dominio destinatario**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-176">**Recipient domain**</span></span>
  - <span data-ttu-id="a0bfa-177">**Conteggio messaggi**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-177">**Message count**</span></span>

<span data-ttu-id="a0bfa-178">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a0bfa-179">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="a0bfa-180">Metodo di crittografia</span><span class="sxs-lookup"><span data-stu-id="a0bfa-180">Encryption method</span></span>
- <span data-ttu-id="a0bfa-181">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="a0bfa-181">Encryption template</span></span>

<span data-ttu-id="a0bfa-182">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="a0bfa-183">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="a0bfa-183">Mailflow status report</span></span>

<span data-ttu-id="a0bfa-184">Il **rapporto sullo stato del flusso di posta** contiene informazioni su malware, posta indesiderata, phishing e messaggi bloccati perimetrali.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="a0bfa-185">Per ulteriori dettagli, vedere [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="a0bfa-186">Rilevamenti di malware nel report di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a0bfa-186">Malware detections in email report</span></span>

<span data-ttu-id="a0bfa-187">Il **rapporto Rilevamenti malware nel** report di posta elettronica mostra informazioni sui rilevamenti di malware nei messaggi di posta elettronica in arrivo e in uscita (malware rilevato da Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="a0bfa-188">Per ulteriori informazioni sulla protezione da malware in EOP, vedere [Protezione antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="a0bfa-189">Il filtro di visualizzazione aggregata consente 90 giorni, mentre il filtro della tabella dei dettagli consente solo 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="a0bfa-190">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e  \>  selezionare **Rilevamenti malware nella posta elettronica.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="a0bfa-191">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="a0bfa-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Rilevamenti di malware nel widget di posta elettronica nel dashboard dei report](../../media/malware-detections-widget.png)

<span data-ttu-id="a0bfa-193">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic **su Filtri** e selezionando:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="a0bfa-194">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="a0bfa-195">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-195">**Inbound**</span></span>
- <span data-ttu-id="a0bfa-196">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-196">**Outbound**</span></span>

![Visualizzazione report nel report Rilevamento malware nei messaggi di posta elettronica](../../media/malware-detections-report-view.png)

<span data-ttu-id="a0bfa-198">Se si fa **clic su Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="a0bfa-199">**Data**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-199">**Date**</span></span>
- <span data-ttu-id="a0bfa-200">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-200">**Sender address**</span></span>
- <span data-ttu-id="a0bfa-201">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-201">**Recipient address**</span></span>
- <span data-ttu-id="a0bfa-202">**ID messaggio**: Disponibile nel **campo di intestazione Message-ID** nell'intestazione del messaggio e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="a0bfa-203">Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="a0bfa-204">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-204">**Subject**</span></span>
- <span data-ttu-id="a0bfa-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-205">**Filename**</span></span>
- <span data-ttu-id="a0bfa-206">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-206">**Malware name**</span></span>

<span data-ttu-id="a0bfa-207">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="a0bfa-208">Rapporto latenza della posta</span><span class="sxs-lookup"><span data-stu-id="a0bfa-208">Mail latency report</span></span>

<span data-ttu-id="a0bfa-209">Il **report Latenza della posta** contiene informazioni sulla latenza di recapito e detonazione della posta riscontrata all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="a0bfa-210">Per ulteriori informazioni, vedere [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="a0bfa-211">Rapporto di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="a0bfa-211">Sent and received email report</span></span>

<span data-ttu-id="a0bfa-212">Il **report Posta inviata e** ricevuta contiene informazioni su malware, posta indesiderata, regole del flusso di posta (note anche come regole di trasporto) e rilevamenti di malware avanzati dopo l'ingresso della posta elettronica nel servizio.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="a0bfa-213">Per ulteriori informazioni, vedere Report di posta elettronica inviati [e ricevuti.](view-mail-flow-reports.md#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="a0bfa-214">Report sui rilevamenti della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="a0bfa-214">Spam detections report</span></span>

<span data-ttu-id="a0bfa-215">Il **report Rilevamenti posta indesiderata** mostra i messaggi di posta elettronica di posta indesiderata bloccati da EOP.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="a0bfa-216">I messaggi vengono conteggiati singolarmente, non per destinatario.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="a0bfa-217">Ad esempio, se lo stesso messaggio di posta indesiderata è stato inviato a 100 destinatari nell'organizzazione, viene conteggiato come un unico messaggio.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="a0bfa-218">La visualizzazione aggregata consente un filtro di 90 giorni, mentre la tabella dei dettagli consente un filtro di 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="a0bfa-219">Per visualizzare il report, aprire [il Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report  \>  e selezionare **Rilevamenti posta indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="a0bfa-220">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="a0bfa-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget Rilevamenti posta indesiderata nel dashboard report](../../media/spam-detections-report-widget.png)

<span data-ttu-id="a0bfa-222">Per ulteriori informazioni sulla protezione da posta indesiderata, vedere Protezione da posta indesiderata [in EOP.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="a0bfa-223">Visualizzazione report per il report Rilevamenti posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="a0bfa-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="a0bfa-224">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a0bfa-225">**Scomporsi per: Azione**: vengono visualizzati i tipi di evento seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="a0bfa-226">**Contenuto di posta indesiderata filtrato**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="a0bfa-227">**Blocco IP di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-227">**Spam IP block**</span></span>
  - <span data-ttu-id="a0bfa-228">**Blocco busta di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="a0bfa-229">**Filtro DBEB di posta indesiderata**: blocco perimetrale basato su directory (DBEB)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="a0bfa-230">Quando si passa il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti elementi sono stati bloccati quel giorno, nonché come tali elementi vengono categorizzati.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Visualizzazione Azioni nel report Rilevamenti posta indesiderata](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="a0bfa-232">**Scomporsi per: Direzione**: vengono visualizzate le seguenti indicazioni:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="a0bfa-233">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-233">**Inbound**</span></span>
  - <span data-ttu-id="a0bfa-234">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-234">**Outbound**</span></span>

  ![Visualizzazione della direzione nel report Rilevamenti posta indesiderata](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="a0bfa-236">Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a0bfa-237">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="a0bfa-238">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="a0bfa-238">Direction values</span></span>
- <span data-ttu-id="a0bfa-239">Valori del tipo di evento</span><span class="sxs-lookup"><span data-stu-id="a0bfa-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="a0bfa-240">Visualizzazione tabella dettagli per il report Rilevamenti posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="a0bfa-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="a0bfa-241">Se si fa **clic su Visualizza tabella dettagli** in qualsiasi visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="a0bfa-242">**Data**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-242">**Date**</span></span>
- <span data-ttu-id="a0bfa-243">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-243">**Sender address**</span></span>
- <span data-ttu-id="a0bfa-244">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-244">**Recipient address**</span></span>
- <span data-ttu-id="a0bfa-245">**Tipo evento**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-245">**Event type**</span></span>
- <span data-ttu-id="a0bfa-246">**Azione**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-246">**Action**</span></span>
- <span data-ttu-id="a0bfa-247">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-247">**Subject**</span></span>

<span data-ttu-id="a0bfa-248">Se si fa **clic su Filtri** in una tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a0bfa-249">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="a0bfa-250">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="a0bfa-250">Direction values</span></span>
- <span data-ttu-id="a0bfa-251">Valori del tipo di evento</span><span class="sxs-lookup"><span data-stu-id="a0bfa-251">Event type values</span></span>

<span data-ttu-id="a0bfa-252">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="a0bfa-253">Report rilevamenti di spoofing</span><span class="sxs-lookup"><span data-stu-id="a0bfa-253">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="a0bfa-254">Il report dei rilevamenti di spoofing migliorato, come descritto in questo articolo, è in Anteprima, è soggetto a modifiche e non è disponibile in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-254">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="a0bfa-255">La versione precedente del report mostrava solo **Posta buona** e Posta indesiderata rilevata come **posta indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-255">The older version of the report showed only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="a0bfa-256">Il **report Rilevamenti di** spoofing mostra informazioni sui messaggi bloccati o consentiti a causa dello spoofing.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-256">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="a0bfa-257">Per ulteriori informazioni sullo spoofing, vedere [Protezione anti-spoofing in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-257">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="a0bfa-258">La visualizzazione aggregata del report consente 45 giorni di filtro, mentre la visualizzazione dettagli consente solo <sup>\*</sup> dieci giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-258">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="a0bfa-259"><sup>\*</sup> Infine, sarà possibile utilizzare fino a 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-259"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="a0bfa-260">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Rilevamenti spoofing**.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-260">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="a0bfa-261">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="a0bfa-261">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widget Rilevamenti di spoofing nel dashboard dei report](../../media/spoof-detections-widget.png)

<span data-ttu-id="a0bfa-263">Quando si passa il mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti messaggi falsificati sono stati rilevati e perché.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-263">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="a0bfa-264">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtri** e selezionando uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-264">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="a0bfa-265">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-265">**Start date** and **End date**</span></span>

- <span data-ttu-id="a0bfa-266">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-266">**Result**</span></span>
  - <span data-ttu-id="a0bfa-267">**Pass**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-267">**Pass**</span></span>
  - <span data-ttu-id="a0bfa-268">**Fail**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-268">**Fail**</span></span>
  - <span data-ttu-id="a0bfa-269">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-269">**SoftPass**</span></span>
  - <span data-ttu-id="a0bfa-270">**Nessuna**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-270">**None**</span></span>
  - <span data-ttu-id="a0bfa-271">**Altro**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-271">**Other**</span></span>

- <span data-ttu-id="a0bfa-272">**Tipo spoof**: **interno** ed **esterno**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-272">**Spoof type**: **Internal** and **External**</span></span>

![Visualizzazione report nel report Rilevamenti spoofing](../../media/spoof-detections-report-view.png)

<span data-ttu-id="a0bfa-274">Se si fa **clic su Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-274">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="a0bfa-275">**Data**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-275">**Date**</span></span>
- <span data-ttu-id="a0bfa-276">**Utente contraffatto**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-276">**Spoofed user**</span></span>
- <span data-ttu-id="a0bfa-277">**Infrastruttura di invio**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-277">**Sending infrastructure**</span></span>
- <span data-ttu-id="a0bfa-278">**Tipo spoofing**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-278">**Spoof type**</span></span>
- <span data-ttu-id="a0bfa-279">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-279">**Result**</span></span>
- <span data-ttu-id="a0bfa-280">**Codice risultato**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-280">**Result code**</span></span>
- <span data-ttu-id="a0bfa-281">**SPF**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-281">**SPF**</span></span>
- <span data-ttu-id="a0bfa-282">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-282">**DKIM**</span></span>
- <span data-ttu-id="a0bfa-283">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-283">**DMARC**</span></span>
- <span data-ttu-id="a0bfa-284">**Conteggio messaggi**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-284">**Message count**</span></span>

<span data-ttu-id="a0bfa-285">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-285">To go back to the report view, click **View report**.</span></span>

<span data-ttu-id="a0bfa-286">Per ulteriori informazioni sui codici dei risultati dell'autenticazione composita, vedere Intestazioni dei messaggi di posta indesiderata [in Microsoft 365](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-286">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="a0bfa-287">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="a0bfa-287">Threat protection status report</span></span>

<span data-ttu-id="a0bfa-288">La **relazione sullo stato di Protezione** dalle minacce è disponibile sia in EOP che in Microsoft Defender per Office 365; Tuttavia, i report contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-288">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="a0bfa-289">Ad esempio, i clienti EOP possono visualizzare le informazioni sul malware rilevato nella posta elettronica, ma non informazioni sui file dannosi rilevati dagli allegati sicuri per [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)e Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="a0bfa-289">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="a0bfa-290">Il report fornisce il conteggio dei messaggi di posta elettronica con contenuto dannoso, ad esempio file o indirizzi di siti Web (URL) bloccati dal motore [](safe-attachments.md)antimalware, eliminazione automatica a zero ore [(ZAP)](zero-hour-auto-purge.md)e Defender per funzionalità di Office 365 come collegamenti [sicuri,](safe-links.md)allegati sicuri e [anti-phishing.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-290">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="a0bfa-291">È possibile utilizzare queste informazioni per identificare le tendenze o determinare se i criteri dell'organizzazione devono essere rettificati.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-291">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="a0bfa-292">**Nota:** è importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-292">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="a0bfa-293">Per visualizzare il report, aprire [il Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard  \> **report** e selezionare **Stato di Protezione dalle minacce**.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-293">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="a0bfa-294">Per passare direttamente al report, aprire uno degli URL seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-294">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="a0bfa-295">Microsoft Defender per Office 365:<https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="a0bfa-295">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="a0bfa-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="a0bfa-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Widget Stato di Protezione dalle minacce nel dashboard dei report](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="a0bfa-298">Per impostazione predefinita, il grafico mostra i dati degli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-298">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="a0bfa-299">Se si fa **clic su Filtri**, è possibile selezionare un intervallo di date di 90 giorni (le sottoscrizioni di valutazione potrebbero essere limitate a 30 giorni).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-299">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="a0bfa-300">La visualizzazione della tabella dei dettagli consente il filtro per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-300">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="a0bfa-301">Visualizzazione dei report per il rapporto sullo stato di Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a0bfa-301">Report view for the Threat protection status report</span></span>

<span data-ttu-id="a0bfa-302">Sono disponibili le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-302">The following views are available:</span></span>

- <span data-ttu-id="a0bfa-303">**Visualizzare i dati per: Panoramica**: vengono visualizzate le seguenti informazioni di rilevamento:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-303">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="a0bfa-304">**Malware di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-304">**Email malware**</span></span>
  - <span data-ttu-id="a0bfa-305">**Phish di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-305">**Email phish**</span></span>
  - <span data-ttu-id="a0bfa-306">**Malware contenuto**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-306">**Content malware**</span></span>

  ![Visualizzazione panoramica nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="a0bfa-308">**Visualizzare i dati per: Contenuto \> Malware**<sup>1</sup>: Vengono visualizzate le informazioni seguenti per Microsoft Defender per Office 365 organizzazioni:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-308">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="a0bfa-309">**Motore antimalware:** file dannosi rilevati in Sharepoint, OneDrive e Microsoft Teams dal rilevamento di [virus incorporato in Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-309">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="a0bfa-310">**Detonazione file:** file dannosi rilevati dagli allegati sicuri per [SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-310">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![Visualizzazione malware contenuto nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="a0bfa-312">**Visualizza dati per: Sostituzione messaggio**: vengono visualizzate le seguenti informazioni sul motivo dell'override:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-312">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="a0bfa-313">**Ignora locale**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-313">**On-premises skip**</span></span>
  - <span data-ttu-id="a0bfa-314">**IP Allow**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-314">**IP Allow**</span></span>
  - <span data-ttu-id="a0bfa-315">**Regola del flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-315">**Mail flow rule**</span></span>
  - <span data-ttu-id="a0bfa-316">**Mittente consentito**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-316">**Sender allow**</span></span>
  - <span data-ttu-id="a0bfa-317">**Dominio consentito**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-317">**Domain allow**</span></span>
  - <span data-ttu-id="a0bfa-318">**ZAP non abilitato**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-318">**ZAP not enabled**</span></span>
  - <span data-ttu-id="a0bfa-319">**Cartella Posta indesiderata non abilitata**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-319">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="a0bfa-320">**Mittente sicuro utente**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-320">**User Safe Sender**</span></span>
  - <span data-ttu-id="a0bfa-321">**Dominio sicuro dall'utente**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-321">**User Safe Domain**</span></span>

  ![Visualizzazione sostituzione messaggio nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="a0bfa-323">**Scomporsi per: Tecnologia di rilevamento** **e Visualizzazione dati per: E-mail \> Phish**: Vengono visualizzate le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="a0bfa-324">**Reputazione URL generata da ATP**<sup>1</sup>: reputazione url dannosa generata da Defender per Office 365 detonazioni in altri Microsoft 365 clienti.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-324">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="a0bfa-325">**Filtro phish avanzato:** segnali di phishing basati sull'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-325">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="a0bfa-326">**Anti-spoof - Errore DMARC**: errore di autenticazione DMARC nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-326">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="a0bfa-327">**Anti-spoofing - intra-org:** il mittente sta tentando di eseguire lo spoofing del dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="a0bfa-328">**Anti-spoofing - dominio esterno:** il mittente sta tentando di eseguire lo spoofing di un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-328">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="a0bfa-329">**Rappresentazione del marchio**: Rappresentazione di marchi noti in base ai mittenti.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-329">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="a0bfa-330">**Rappresentazione di dominio**<sup>1</sup>: Rappresentazione dei domini che il cliente possiede o definisce.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-330">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="a0bfa-331">**Reputazione URL EOP**: reputazione URL dannoso.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-331">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="a0bfa-332">**Filtro phish generale**: Segnali di phishing basati sulle regole degli analisti.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-332">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="a0bfa-333">**Altri**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-333">**Others**</span></span>
  - <span data-ttu-id="a0bfa-334">**Phish ZAP**<sup>2</sup>: Eliminazione automatica a zero ore dei messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-334">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="a0bfa-335">**Detonazione URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a0bfa-335">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="a0bfa-336">**Rappresentazione utente**<sup>1</sup>: Rappresentazione degli utenti definiti dall'amministratore o appresi tramite l'intelligence delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-336">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Visualizzazione della tecnologia di rilevamento per la posta elettronica di phishing nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="a0bfa-338">**Scomporsi per: Tecnologia di rilevamento** e Visualizzazione dati per: Malware di posta elettronica : Vengono visualizzate le informazioni seguenti: **\>**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="a0bfa-339">**Reputazione file generata da ATP**<sup>1:</sup>tutta la reputazione dei file dannosi generata da Defender per Office 365 detonazioni.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-339">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="a0bfa-340">**Motore antimalware**<sup>1</sup>: Rilevamento da motori antimalware.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-340">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="a0bfa-341">**Blocco del tipo di file dei** criteri antimalware: si tratta di messaggi di posta elettronica filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-341">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="a0bfa-342">**Detonazione file**<sup>1</sup>: rilevamento tramite allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-342">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="a0bfa-343">**Reputazione di file dannosi**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-343">**Malicious file reputation**</span></span>
  - <span data-ttu-id="a0bfa-344">**Malware ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a0bfa-344">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="a0bfa-345">**Altri**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-345">**Others**</span></span>

  ![Visualizzazione della tecnologia di rilevamento per il malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="a0bfa-347">**Scomporsi per: Tipo di criterio** e Visualizza dati **per: \> E-mail Phish** o Visualizza dati **per: Email \> Malware**: Vengono visualizzate le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-347">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="a0bfa-348">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-348">**Anti-malware**</span></span>
  - <span data-ttu-id="a0bfa-349">**Allegati sicuri**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a0bfa-349">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="a0bfa-350">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-350">**Anti-phish**</span></span>
  - <span data-ttu-id="a0bfa-351">**Protezione da posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-351">**Anti-spam**</span></span>
  - <span data-ttu-id="a0bfa-352">**Regola del flusso di** posta (nota anche come regola di trasporto)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-352">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="a0bfa-353">**Altri**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-353">**Others**</span></span>

  ![Visualizzazione del tipo di criterio per la posta elettronica di phishing nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="a0bfa-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="a0bfa-356">**Recapito non riuscito**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-356">**Delivery failed**</span></span>
  - <span data-ttu-id="a0bfa-357">**Rilasciato**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-357">**Dropped**</span></span>
  - <span data-ttu-id="a0bfa-358">**Inoltrato**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-358">**Forwarded**</span></span>
  - <span data-ttu-id="a0bfa-359">**Cassetta postale ospitata: cartella personalizzata**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-359">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="a0bfa-360">**Cassetta postale ospitata: Elementi eliminati**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-360">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="a0bfa-361">**Cassetta postale ospitata: Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-361">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="a0bfa-362">**Cassetta postale ospitata: Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-362">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="a0bfa-363">**Server locale: recapitato**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-363">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="a0bfa-364">**Quarantena**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-364">**Quarantine**</span></span>

  ![Visualizzazione dello stato del recapito per la posta elettronica di phishing nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="a0bfa-366"><sup>1</sup> Defender per Office 365 solo</span><span class="sxs-lookup"><span data-stu-id="a0bfa-366"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="a0bfa-367"><sup>2</sup> L'eliminazione automatica a zero ore (ZAP) non è disponibile in EOP autonomo (funziona solo in Exchange Online cassette postali).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-367"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="a0bfa-368">Se si fa **clic su Filtri**, i filtri disponibili dipendono dal grafico che si stava esaminando:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-368">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a0bfa-369">Per **Visualizza dati per: \> Malware** contenuto, è possibile modificare il report in base alla data di inizio **e** alla data **di fine** e al **valore di** rilevamento.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="a0bfa-370">Per **Visualizza dati per: Sostituzione messaggio**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-370">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a0bfa-371">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-371">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a0bfa-372">**Motivo sostituzione**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-372">**Override Reason**</span></span>
  - <span data-ttu-id="a0bfa-373">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-373">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="a0bfa-374">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-374">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="a0bfa-375">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-375">**Domain**</span></span>

- <span data-ttu-id="a0bfa-376">Per tutte le altre visualizzazioni, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-376">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a0bfa-377">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-377">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a0bfa-378">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-378">**Detection**</span></span>
  - <span data-ttu-id="a0bfa-379">**Protetto da**: **ATP** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-379">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="a0bfa-380">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-380">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="a0bfa-381">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-381">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="a0bfa-382">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-382">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="a0bfa-383">Visualizzazione tabella dettagli per il rapporto sullo stato di Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a0bfa-383">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="a0bfa-384">Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-384">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a0bfa-385">**Visualizza dati per: Panoramica**: non **è disponibile** il pulsante Visualizza tabella dettagli.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-385">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="a0bfa-386">**Visualizzare i dati per: Contenuto \> Malware**:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-386">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="a0bfa-387">**Data**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-387">**Date**</span></span>
  - <span data-ttu-id="a0bfa-388">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-388">**Location**</span></span>
  - <span data-ttu-id="a0bfa-389">**Diretto da**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-389">**Directed by**</span></span>
  - <span data-ttu-id="a0bfa-390">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-390">**Malware name**</span></span>

  <span data-ttu-id="a0bfa-391">Se si fa **clic su** Filtri in questa visualizzazione, è possibile modificare il report in base alla data di **inizio** e alla data **di fine** e al **valore di** rilevamento.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-391">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="a0bfa-392">**Visualizzare i dati per: Sostituzione messaggio**:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-392">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="a0bfa-393">**Data**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-393">**Date**</span></span>
  - <span data-ttu-id="a0bfa-394">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-394">**Subject**</span></span>
  - <span data-ttu-id="a0bfa-395">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-395">**Sender**</span></span>
  - <span data-ttu-id="a0bfa-396">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-396">**Recipients**</span></span>
  - <span data-ttu-id="a0bfa-397">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-397">**Detected by**</span></span>
  - <span data-ttu-id="a0bfa-398">**Motivo sostituzione**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-398">**Override Reason**</span></span>
  - <span data-ttu-id="a0bfa-399">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-399">**Source of Compromise**</span></span>
  - <span data-ttu-id="a0bfa-400">**Tag**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-400">**Tags**</span></span>

  <span data-ttu-id="a0bfa-401">Se si fa **clic su** Filtri in questa visualizzazione, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-401">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a0bfa-402">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-402">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a0bfa-403">**Motivo sostituzione**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-403">**Override Reason**</span></span>
  - <span data-ttu-id="a0bfa-404">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="a0bfa-405">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="a0bfa-406">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-406">**Domain**</span></span>
  - <span data-ttu-id="a0bfa-407">**Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="a0bfa-408">Tutti gli altri grafici:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-408">All other charts:</span></span>

  - <span data-ttu-id="a0bfa-409">**Data**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-409">**Date**</span></span>
  - <span data-ttu-id="a0bfa-410">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-410">**Subject**</span></span>
  - <span data-ttu-id="a0bfa-411">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-411">**Sender**</span></span>
  - <span data-ttu-id="a0bfa-412">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-412">**Recipients**</span></span>
  - <span data-ttu-id="a0bfa-413">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-413">**Detected by**</span></span>
  - <span data-ttu-id="a0bfa-414">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-414">**Delivery Status**</span></span>
  - <span data-ttu-id="a0bfa-415">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-415">**Source of Compromise**</span></span>
  - <span data-ttu-id="a0bfa-416">**Tag**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-416">**Tags**</span></span>

  <span data-ttu-id="a0bfa-417">Se si fa **clic su Filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-417">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a0bfa-418">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-418">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a0bfa-419">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-419">**Detection**</span></span>
  - <span data-ttu-id="a0bfa-420">**Protetto da**: **Defender per Office 365** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-420">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="a0bfa-421">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="a0bfa-422">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="a0bfa-423">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-423">**Domain**</span></span>
  - <span data-ttu-id="a0bfa-424">**Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-424">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="a0bfa-425">Report principale sul malware</span><span class="sxs-lookup"><span data-stu-id="a0bfa-425">Top malware report</span></span>

<span data-ttu-id="a0bfa-426">Il **report Top malware** mostra i vari tipi di malware rilevati dalla protezione [antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-426">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="a0bfa-427">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Malware principale.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-427">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="a0bfa-428">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="a0bfa-428">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Widget malware principale nel dashboard dei report](../../media/top-malware-report-widget.png)

<span data-ttu-id="a0bfa-430">Quando si passa il mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi rilevati come malware.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-430">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Visualizzazione dei report principali sul malware](../../media/top-malware-report-view.png)

<span data-ttu-id="a0bfa-432">Se si fa **clic su Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-432">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="a0bfa-433">**Malware principale**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-433">**Top malware**</span></span>
- <span data-ttu-id="a0bfa-434">**Numero**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-434">**Count**</span></span>

<span data-ttu-id="a0bfa-435">Se si fa **clic su Filtri** nella visualizzazione report o nella visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-435">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="a0bfa-436">Report di protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="a0bfa-436">URL threat protection report</span></span>

<span data-ttu-id="a0bfa-437">Il **report di protezione dalle minacce URL** è disponibile in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-437">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a0bfa-438">Per ulteriori informazioni, vedere [Report di protezione dalle minacce URL](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-438">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="a0bfa-439">Rapporto messaggi segnalati dall'utente</span><span class="sxs-lookup"><span data-stu-id="a0bfa-439">User-reported messages report</span></span>

<span data-ttu-id="a0bfa-440">Il **rapporto** Messaggi segnalati dall'utente mostra informazioni sui messaggi di posta elettronica segnalati [](enable-the-report-message-add-in.md) dagli utenti come posta indesiderata, tentativi di phishing o buona posta utilizzando il componente aggiuntivo Segnala messaggio o Il componente aggiuntivo Segnala [phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-440">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="a0bfa-441">Sono disponibili dettagli per ogni messaggio, incluso il motivo del recapito, ad esempio un'eccezione del criterio di posta indesiderata o una regola del flusso di posta configurata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-441">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="a0bfa-442">Per visualizzare i dettagli, selezionare un elemento nell'elenco dei report utente e quindi visualizzare le informazioni nelle **schede Riepilogo** **e** Dettagli.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-442">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![Il User-Reported messaggi mostra i messaggi che gli utenti etichettano come posta indesiderata, non come posta indesiderata o tentativi di phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="a0bfa-444">Per visualizzare questo report, nel [Centro sicurezza & conformità](https://protection.office.com)eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-444">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="a0bfa-445">Vai a **Dashboard di gestione delle** \> **minacce** Messaggi \> **segnalati dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-445">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="a0bfa-446">Passare a **Gestione delle minacce** \> **Esaminare** i messaggi segnalati \> **dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-446">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![Nel Centro sicurezza & conformità scegliere Gestione delle minacce \> Esaminare i messaggi segnalati \> dall'utente](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="a0bfa-448">Per il corretto funzionamento del rapporto Messaggi  segnalati dall'utente, è necessario che la registrazione di controllo sia attivata per l'Office 365 locale.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-448">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="a0bfa-449">Questa operazione viene in genere eseguita da un utente a cui è assegnato il ruolo Log di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-449">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="a0bfa-450">Per ulteriori informazioni, vedere [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-450">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="a0bfa-451">Quali autorizzazioni sono necessarie per visualizzare questi report?</span><span class="sxs-lookup"><span data-stu-id="a0bfa-451">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="a0bfa-452">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="a0bfa-452">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="a0bfa-453">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-453">**Organization Management**</span></span>
- <span data-ttu-id="a0bfa-454">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-454">**Security Administrator**</span></span>
- <span data-ttu-id="a0bfa-455">**Ruolo con autorizzazioni di lettura per la sicurezza**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-455">**Security Reader**</span></span>
- <span data-ttu-id="a0bfa-456">**Lettore globale**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-456">**Global Reader**</span></span>

<span data-ttu-id="a0bfa-457">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-457">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="a0bfa-458">**Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre  agli utenti le autorizzazioni necessarie nel Centro sicurezza e conformità di & e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-458">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a0bfa-459">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a0bfa-459">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="a0bfa-460">Cosa succede se i report non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="a0bfa-460">What if the reports aren't showing data?</span></span>

<span data-ttu-id="a0bfa-461">Se i dati nei report non vengono visualizzati, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-461">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="a0bfa-462">Per ulteriori informazioni, vedere [Protezione dalle minacce.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-462">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0bfa-463">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a0bfa-463">Related topics</span></span>

[<span data-ttu-id="a0bfa-464">Protezione da posta indesiderata e antimalware in EOP</span><span class="sxs-lookup"><span data-stu-id="a0bfa-464">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="a0bfa-465">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="a0bfa-465">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="a0bfa-466">Visualizzare i report del flusso di posta nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="a0bfa-466">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="a0bfa-467">Visualizzare i report per Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="a0bfa-467">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
