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
ms.openlocfilehash: 5d9f6d12fef8a2ef6241fbbd5e0e2a980284e9cc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206242"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="f9f93-104">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="f9f93-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f9f93-105">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="f9f93-105">**Applies to**</span></span>
- [<span data-ttu-id="f9f93-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f9f93-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f9f93-107">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="f9f93-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f9f93-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9f93-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f9f93-109">Nel Centro sicurezza e conformità è disponibile [un'ampia](https://protection.office.com) gamma di report che consentono di verificare in che modo le funzionalità di sicurezza della posta elettronica, ad esempio la protezione da posta indesiderata, antimalware e crittografia in Microsoft 365, proteggono l'organizzazione. &</span><span class="sxs-lookup"><span data-stu-id="f9f93-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="f9f93-110">Se si dispone delle [autorizzazioni necessarie,](#what-permissions-are-needed-to-view-these-reports)è possibile visualizzare questi report nel Centro sicurezza & conformità andando a **Dashboard** \> **report.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="f9f93-111">Per passare direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="f9f93-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard dei report nel Centro sicurezza & conformità](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="f9f93-113">Report utenti compromessi</span><span class="sxs-lookup"><span data-stu-id="f9f93-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="f9f93-114">Questo report è disponibile nelle organizzazioni di Microsoft 365 con cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f9f93-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="f9f93-115">Non è disponibile nelle organizzazioni autonome di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="f9f93-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="f9f93-116">Il **report Utenti compromessi** mostra il numero di  account  utente contrassegnati come sospetti o con restrizioni negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="f9f93-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="f9f93-117">Gli account in uno di questi stati sono problematici o addirittura compromessi.</span><span class="sxs-lookup"><span data-stu-id="f9f93-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="f9f93-118">Con un uso frequente, è possibile utilizzare il report per individuare picchi e persino tendenze in account sospetti o con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="f9f93-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="f9f93-119">Per ulteriori informazioni sugli utenti compromessi, vedere [Risposta a un account di posta elettronica compromesso.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Utenti compromessi nel dashboard report](../../media/compromised-users-report-widget.png)

<span data-ttu-id="f9f93-121">La visualizzazione aggregata mostra i dati degli ultimi 90 giorni e la visualizzazione dettagli mostra i dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f9f93-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="f9f93-122">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Utenti compromessi.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="f9f93-123">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="f9f93-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="f9f93-124">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtri** e selezionando uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="f9f93-125">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="f9f93-126">**Sospetto:** l'account utente ha inviato messaggi di posta elettronica sospetti ed è a rischio di essere limitato a inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f9f93-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="f9f93-127">**Con restrizioni**: all'account utente è stato limitato l'invio di posta elettronica a causa di modelli altamente sospetti.</span><span class="sxs-lookup"><span data-stu-id="f9f93-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Visualizzazione report nel report Utenti compromessi](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="f9f93-129">Se si fa **clic su Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="f9f93-130">**Ora creazione**</span><span class="sxs-lookup"><span data-stu-id="f9f93-130">**Creation time**</span></span>
- <span data-ttu-id="f9f93-131">**ID utente**</span><span class="sxs-lookup"><span data-stu-id="f9f93-131">**User ID**</span></span>
- <span data-ttu-id="f9f93-132">**Azione**</span><span class="sxs-lookup"><span data-stu-id="f9f93-132">**Action**</span></span>

<span data-ttu-id="f9f93-133">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="f9f93-134">Report crittografia</span><span class="sxs-lookup"><span data-stu-id="f9f93-134">Encryption report</span></span>

<span data-ttu-id="f9f93-135">Il **report Crittografia** è disponibile in EOP (sottoscrizioni con cassette postali in Exchange Online o EOP autonomo senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="f9f93-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="f9f93-136">Il team di sicurezza dell'organizzazione può utilizzare le informazioni contenute in questo report per identificare i modelli e applicare o modificare in modo proattivo i criteri per i messaggi di posta elettronica sensibili.</span><span class="sxs-lookup"><span data-stu-id="f9f93-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="f9f93-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f9f93-137">For example:</span></span>

- <span data-ttu-id="f9f93-138">Se viene visualizzato un numero elevato di messaggi di posta elettronica crittografati dagli utenti, è possibile aggiungere un criterio di crittografia per automatizzare la crittografia per determinati casi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="f9f93-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="f9f93-139">Per ulteriori informazioni, vedere [Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Microsoft 365.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="f9f93-140">Se sono disponibili diversi modelli di crittografia ma nessuno li utilizza, è possibile verificare se gli utenti necessitano di formazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f9f93-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="f9f93-141">La visualizzazione aggregata consente il filtro per gli ultimi 90 giorni, mentre la visualizzazione dettagli consente il filtro per 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="f9f93-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="f9f93-142">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Report di crittografia.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="f9f93-143">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="f9f93-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="f9f93-144">Per ulteriori informazioni sulla crittografia, vedere [Crittografia della posta elettronica in Microsoft 365.](../../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="f9f93-145">Visualizzazione report per il report Crittografia</span><span class="sxs-lookup"><span data-stu-id="f9f93-145">Report view for the Encryption report</span></span>

<span data-ttu-id="f9f93-146">Nel grafico è possibile utilizzare i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="f9f93-147">**Visualizzare i dati per: Rapporto crittografia** messaggi **e Suddivide per: Metodo** di crittografia : sono disponibili i metodi di crittografia seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="f9f93-148">**Crittografia per utente**</span><span class="sxs-lookup"><span data-stu-id="f9f93-148">**Encryption by user**</span></span>
  - <span data-ttu-id="f9f93-149">**Crittografia in base ai criteri**</span><span class="sxs-lookup"><span data-stu-id="f9f93-149">**Encryption by policy**</span></span>

  <span data-ttu-id="f9f93-150">Se si fa **clic su Filtri**, è possibile modificare il grafico con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="f9f93-151">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f9f93-152">Metodo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="f9f93-152">Encryption method.</span></span>
  - <span data-ttu-id="f9f93-153">Modello di crittografia.</span><span class="sxs-lookup"><span data-stu-id="f9f93-153">Encryption template.</span></span>

- <span data-ttu-id="f9f93-154">**Visualizzare i dati per: Rapporto crittografia messaggi** **ed Suddivide per: Modello** di crittografia : sono disponibili i metodi di crittografia seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="f9f93-155">**Non inoltrare**</span><span class="sxs-lookup"><span data-stu-id="f9f93-155">**Do not forward**</span></span>
  - <span data-ttu-id="f9f93-156">**Crittografa solo**</span><span class="sxs-lookup"><span data-stu-id="f9f93-156">**Encrypt only**</span></span>
  - <span data-ttu-id="f9f93-157">**OME precedente**</span><span class="sxs-lookup"><span data-stu-id="f9f93-157">**OME previous**</span></span>
  - <span data-ttu-id="f9f93-158">**Personalizzata**</span><span class="sxs-lookup"><span data-stu-id="f9f93-158">**Custom**</span></span>

  <span data-ttu-id="f9f93-159">Se si fa **clic su Filtri**, è possibile modificare il grafico con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="f9f93-160">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f9f93-161">Metodo di crittografia</span><span class="sxs-lookup"><span data-stu-id="f9f93-161">Encryption method</span></span>
  - <span data-ttu-id="f9f93-162">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="f9f93-162">Encryption template</span></span>

- <span data-ttu-id="f9f93-163">**Visualizzare i dati per: Top 5 recipient domains**: Questa visualizzazione mostra un grafico a torta con i conteggi dei messaggi inviati per i primi 5 domini destinatario.</span><span class="sxs-lookup"><span data-stu-id="f9f93-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="f9f93-164">Se si fa **clic su Filtri**, è possibile selezionare una data di inizio **e** una data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="f9f93-165">Visualizzazione tabella dettagli per il report Crittografia</span><span class="sxs-lookup"><span data-stu-id="f9f93-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="f9f93-166">Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="f9f93-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f9f93-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span><span class="sxs-lookup"><span data-stu-id="f9f93-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="f9f93-168">**Data**</span><span class="sxs-lookup"><span data-stu-id="f9f93-168">**Date**</span></span>
  - <span data-ttu-id="f9f93-169">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="f9f93-169">**Sender address**</span></span>
  - <span data-ttu-id="f9f93-170">**Modello di crittografia**</span><span class="sxs-lookup"><span data-stu-id="f9f93-170">**Encryption template**</span></span>
  - <span data-ttu-id="f9f93-171">**Metodo di crittografia**</span><span class="sxs-lookup"><span data-stu-id="f9f93-171">**Encryption method**</span></span>
  - <span data-ttu-id="f9f93-172">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="f9f93-172">**Recipient address**</span></span>
  - <span data-ttu-id="f9f93-173">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="f9f93-173">**Subject**</span></span>

- <span data-ttu-id="f9f93-174">**Visualizzare i dati per: Top 5 recipient domains**:</span><span class="sxs-lookup"><span data-stu-id="f9f93-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="f9f93-175">**Data**</span><span class="sxs-lookup"><span data-stu-id="f9f93-175">**Date**</span></span>
  - <span data-ttu-id="f9f93-176">**Dominio destinatario**</span><span class="sxs-lookup"><span data-stu-id="f9f93-176">**Recipient domain**</span></span>
  - <span data-ttu-id="f9f93-177">**Conteggio messaggi**</span><span class="sxs-lookup"><span data-stu-id="f9f93-177">**Message count**</span></span>

<span data-ttu-id="f9f93-178">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9f93-179">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9f93-180">Metodo di crittografia</span><span class="sxs-lookup"><span data-stu-id="f9f93-180">Encryption method</span></span>
- <span data-ttu-id="f9f93-181">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="f9f93-181">Encryption template</span></span>

<span data-ttu-id="f9f93-182">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="f9f93-183">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="f9f93-183">Mailflow status report</span></span>

<span data-ttu-id="f9f93-184">Il **rapporto sullo stato del flusso di posta** contiene informazioni su malware, posta indesiderata, phishing e messaggi bloccati perimetrali.</span><span class="sxs-lookup"><span data-stu-id="f9f93-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="f9f93-185">Per ulteriori dettagli, vedere [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span><span class="sxs-lookup"><span data-stu-id="f9f93-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="f9f93-186">Rilevamenti di malware nel report di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f9f93-186">Malware detections in email report</span></span>

<span data-ttu-id="f9f93-187">Il **rapporto Rilevamenti malware nel** rapporto di posta elettronica mostra informazioni sui rilevamenti di malware nei messaggi di posta elettronica in arrivo e in uscita (malware rilevato da Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="f9f93-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="f9f93-188">Per ulteriori informazioni sulla protezione da malware in EOP, vedere [Protezione antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="f9f93-189">Il filtro di visualizzazione aggregata consente 90 giorni, mentre il filtro della tabella dei dettagli consente solo 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="f9f93-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="f9f93-190">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e  \>  selezionare **Rilevamenti malware nella posta elettronica.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="f9f93-191">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="f9f93-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Rilevamenti di malware nel widget di posta elettronica nel dashboard dei report](../../media/malware-detections-widget.png)

<span data-ttu-id="f9f93-193">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic **su Filtri** e selezionando:</span><span class="sxs-lookup"><span data-stu-id="f9f93-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="f9f93-194">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9f93-195">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="f9f93-195">**Inbound**</span></span>
- <span data-ttu-id="f9f93-196">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="f9f93-196">**Outbound**</span></span>

![Visualizzazione report nel report Rilevamento malware nei messaggi di posta elettronica](../../media/malware-detections-report-view.png)

<span data-ttu-id="f9f93-198">Se si fa **clic su Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="f9f93-199">**Data**</span><span class="sxs-lookup"><span data-stu-id="f9f93-199">**Date**</span></span>
- <span data-ttu-id="f9f93-200">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="f9f93-200">**Sender address**</span></span>
- <span data-ttu-id="f9f93-201">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="f9f93-201">**Recipient address**</span></span>
- <span data-ttu-id="f9f93-202">**ID messaggio**: Disponibile nel **campo di intestazione Message-ID** nell'intestazione del messaggio e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="f9f93-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="f9f93-203">Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="f9f93-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="f9f93-204">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="f9f93-204">**Subject**</span></span>
- <span data-ttu-id="f9f93-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="f9f93-205">**Filename**</span></span>
- <span data-ttu-id="f9f93-206">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="f9f93-206">**Malware name**</span></span>

<span data-ttu-id="f9f93-207">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="f9f93-208">Rapporto latenza della posta</span><span class="sxs-lookup"><span data-stu-id="f9f93-208">Mail latency report</span></span>

<span data-ttu-id="f9f93-209">Il **report Latenza della posta** contiene informazioni sulla latenza di recapito e detonazione della posta riscontrata all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f9f93-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="f9f93-210">Per ulteriori informazioni, vedere [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="f9f93-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="f9f93-211">Rapporto di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="f9f93-211">Sent and received email report</span></span>

<span data-ttu-id="f9f93-212">Il **report Posta inviata e** ricevuta contiene informazioni su malware, posta indesiderata, regole del flusso di posta (note anche come regole di trasporto) e rilevamenti di malware avanzati dopo l'ingresso della posta elettronica nel servizio.</span><span class="sxs-lookup"><span data-stu-id="f9f93-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="f9f93-213">Per ulteriori informazioni, vedere Report di posta elettronica inviati [e ricevuti.](view-mail-flow-reports.md#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="f9f93-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="f9f93-214">Report sui rilevamenti della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="f9f93-214">Spam detections report</span></span>

<span data-ttu-id="f9f93-215">Il **report Rilevamenti posta indesiderata** mostra i messaggi di posta elettronica di posta indesiderata bloccati da EOP.</span><span class="sxs-lookup"><span data-stu-id="f9f93-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="f9f93-216">I messaggi vengono conteggiati singolarmente, non per destinatario.</span><span class="sxs-lookup"><span data-stu-id="f9f93-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="f9f93-217">Ad esempio, se lo stesso messaggio di posta indesiderata è stato inviato a 100 destinatari nell'organizzazione, viene conteggiato come un unico messaggio.</span><span class="sxs-lookup"><span data-stu-id="f9f93-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="f9f93-218">La visualizzazione aggregata consente un filtro di 90 giorni, mentre la tabella dei dettagli consente un filtro di 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="f9f93-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="f9f93-219">Per visualizzare il report, aprire [il Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report  \>  e selezionare **Rilevamenti posta indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="f9f93-220">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="f9f93-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget Rilevamenti posta indesiderata nel dashboard report](../../media/spam-detections-report-widget.png)

<span data-ttu-id="f9f93-222">Per ulteriori informazioni sulla protezione da posta indesiderata, vedere Protezione da posta indesiderata [in EOP.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="f9f93-223">Visualizzazione report per il report Rilevamenti posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="f9f93-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="f9f93-224">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f9f93-225">**Scomporsi per: Azione**: vengono visualizzati i tipi di evento seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="f9f93-226">**Contenuto di posta indesiderata filtrato**</span><span class="sxs-lookup"><span data-stu-id="f9f93-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="f9f93-227">**Blocco IP di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="f9f93-227">**Spam IP block**</span></span>
  - <span data-ttu-id="f9f93-228">**Blocco busta di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="f9f93-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="f9f93-229">**Filtro DBEB di posta indesiderata**: blocco perimetrale basato su directory (DBEB)</span><span class="sxs-lookup"><span data-stu-id="f9f93-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="f9f93-230">Quando si passa il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti elementi sono stati bloccati quel giorno, nonché come tali elementi vengono categorizzati.</span><span class="sxs-lookup"><span data-stu-id="f9f93-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Visualizzazione Azioni nel report Rilevamenti posta indesiderata](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="f9f93-232">**Scomporsi per: Direzione**: vengono visualizzate le seguenti indicazioni:</span><span class="sxs-lookup"><span data-stu-id="f9f93-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="f9f93-233">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="f9f93-233">**Inbound**</span></span>
  - <span data-ttu-id="f9f93-234">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="f9f93-234">**Outbound**</span></span>

  ![Visualizzazione della direzione nel report Rilevamenti posta indesiderata](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="f9f93-236">Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9f93-237">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9f93-238">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="f9f93-238">Direction values</span></span>
- <span data-ttu-id="f9f93-239">Valori del tipo di evento</span><span class="sxs-lookup"><span data-stu-id="f9f93-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="f9f93-240">Visualizzazione tabella dettagli per il report Rilevamenti posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="f9f93-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="f9f93-241">Se si fa **clic su Visualizza tabella dettagli** in qualsiasi visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="f9f93-242">**Data**</span><span class="sxs-lookup"><span data-stu-id="f9f93-242">**Date**</span></span>
- <span data-ttu-id="f9f93-243">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="f9f93-243">**Sender address**</span></span>
- <span data-ttu-id="f9f93-244">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="f9f93-244">**Recipient address**</span></span>
- <span data-ttu-id="f9f93-245">**Tipo evento**</span><span class="sxs-lookup"><span data-stu-id="f9f93-245">**Event type**</span></span>
- <span data-ttu-id="f9f93-246">**Azione**</span><span class="sxs-lookup"><span data-stu-id="f9f93-246">**Action**</span></span>
- <span data-ttu-id="f9f93-247">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="f9f93-247">**Subject**</span></span>

<span data-ttu-id="f9f93-248">Se si fa **clic su Filtri** in una tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9f93-249">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9f93-250">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="f9f93-250">Direction values</span></span>
- <span data-ttu-id="f9f93-251">Valori del tipo di evento</span><span class="sxs-lookup"><span data-stu-id="f9f93-251">Event type values</span></span>

<span data-ttu-id="f9f93-252">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="f9f93-253">Report rilevamenti di spoofing</span><span class="sxs-lookup"><span data-stu-id="f9f93-253">Spoof detections report</span></span>

<span data-ttu-id="f9f93-254">Il **report Rilevamenti di** spoofing mostra il numero di messaggi di posta contraffatti rilevati e di quelli considerati "buoni" (messaggi di spoofing per motivi aziendali legittimi).</span><span class="sxs-lookup"><span data-stu-id="f9f93-254">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="f9f93-255">Per ulteriori informazioni sullo spoofing, vedere [Protezione anti-spoofing in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-255">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="f9f93-256">La visualizzazione aggregata del report consente 90 giorni di filtro, mentre la visualizzazione dettagli consente solo dieci giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="f9f93-256">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="f9f93-257">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Rilevamenti spoofing**.</span><span class="sxs-lookup"><span data-stu-id="f9f93-257">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="f9f93-258">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="f9f93-258">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widget Rilevamenti di spoofing nel dashboard dei report](../../media/spoof-detections-widget.png)

<span data-ttu-id="f9f93-260">Quando si passa il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile visualizzare il numero di messaggi di posta contraffatti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="f9f93-260">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="f9f93-261">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtri** e selezionando uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-261">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="f9f93-262">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-262">**Start date** and **End date**</span></span>

- <span data-ttu-id="f9f93-263">**Posta buona**</span><span class="sxs-lookup"><span data-stu-id="f9f93-263">**Good mail**</span></span>

- <span data-ttu-id="f9f93-264">**Intercettato come posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="f9f93-264">**Caught as spam**</span></span>

![Visualizzazione report nel report Rilevamenti spoofing](../../media/spoof-detections-report-view.png)

<span data-ttu-id="f9f93-266">Se si fa **clic su Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-266">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="f9f93-267">**Data**</span><span class="sxs-lookup"><span data-stu-id="f9f93-267">**Date**</span></span>
- <span data-ttu-id="f9f93-268">**Mittente contraffatto**</span><span class="sxs-lookup"><span data-stu-id="f9f93-268">**Spoofed sender**</span></span>
- <span data-ttu-id="f9f93-269">**True sender**</span><span class="sxs-lookup"><span data-stu-id="f9f93-269">**True sender**</span></span>
- <span data-ttu-id="f9f93-270">**Indirizzo IP mittente**</span><span class="sxs-lookup"><span data-stu-id="f9f93-270">**Sender IP**</span></span>
- <span data-ttu-id="f9f93-271">**Azione**</span><span class="sxs-lookup"><span data-stu-id="f9f93-271">**Action**</span></span>
- <span data-ttu-id="f9f93-272">**Conteggio messaggi**</span><span class="sxs-lookup"><span data-stu-id="f9f93-272">**Message count**</span></span>

<span data-ttu-id="f9f93-273">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-273">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="f9f93-274">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="f9f93-274">Threat protection status report</span></span>

<span data-ttu-id="f9f93-275">La **relazione sullo stato di Protezione** dalle minacce è disponibile sia in EOP che in Microsoft Defender per Office 365. Tuttavia, i report contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="f9f93-275">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="f9f93-276">Ad esempio, i clienti EOP possono visualizzare le informazioni sul malware rilevato nella posta elettronica, ma non informazioni sui file dannosi rilevati da Allegati sicuri [per SharePoint, OneDrive e Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-276">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="f9f93-277">Il report fornisce il conteggio dei messaggi di posta elettronica con contenuto dannoso, ad esempio file o indirizzi di siti Web (URL) che sono stati bloccati [](safe-attachments.md)dal motore antimalware, eliminazione automatica a zero ore [(ZAP)](zero-hour-auto-purge.md)e funzionalità di Defender per Office 365 come collegamenti [sicuri,](safe-links.md)allegati sicuri e [anti-phishing.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-277">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="f9f93-278">È possibile utilizzare queste informazioni per identificare le tendenze o determinare se i criteri dell'organizzazione devono essere rettificati.</span><span class="sxs-lookup"><span data-stu-id="f9f93-278">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="f9f93-279">**Nota:** è importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="f9f93-279">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="f9f93-280">Per visualizzare il report, aprire [il Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard  \> **report** e selezionare **Stato di Protezione dalle minacce**.</span><span class="sxs-lookup"><span data-stu-id="f9f93-280">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="f9f93-281">Per passare direttamente al report, aprire uno degli URL seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-281">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="f9f93-282">Microsoft Defender per Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="f9f93-282">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="f9f93-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="f9f93-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Widget Stato di Protezione dalle minacce nel dashboard dei report](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="f9f93-285">Per impostazione predefinita, il grafico mostra i dati degli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="f9f93-285">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="f9f93-286">Se si fa **clic su Filtri**, è possibile selezionare un intervallo di date di 90 giorni (le sottoscrizioni di valutazione potrebbero essere limitate a 30 giorni).</span><span class="sxs-lookup"><span data-stu-id="f9f93-286">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="f9f93-287">La visualizzazione della tabella dei dettagli consente il filtro per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f9f93-287">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="f9f93-288">Visualizzazione dei report per il rapporto sullo stato di Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f9f93-288">Report view for the Threat protection status report</span></span>

<span data-ttu-id="f9f93-289">Sono disponibili le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-289">The following views are available:</span></span>

- <span data-ttu-id="f9f93-290">**Visualizzare i dati per: Panoramica**: vengono visualizzate le seguenti informazioni di rilevamento:</span><span class="sxs-lookup"><span data-stu-id="f9f93-290">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="f9f93-291">**Malware di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="f9f93-291">**Email malware**</span></span>
  - <span data-ttu-id="f9f93-292">**Phish di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="f9f93-292">**Email phish**</span></span>
  - <span data-ttu-id="f9f93-293">**Malware contenuto**</span><span class="sxs-lookup"><span data-stu-id="f9f93-293">**Content malware**</span></span>

  ![Visualizzazione panoramica nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="f9f93-295">**Visualizzare i dati per: Contenuto \> Malware**<sup>1:</sup>vengono visualizzate le informazioni seguenti per Microsoft Defender per le organizzazioni di Office 365:</span><span class="sxs-lookup"><span data-stu-id="f9f93-295">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="f9f93-296">**Motore antimalware:** file dannosi rilevati in Sharepoint, OneDrive e Microsoft Teams dal rilevamento di [virus incorporato in Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-296">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="f9f93-297">**Detonazione file:** file dannosi rilevati [da allegati sicuri per SharePoint, OneDrive e Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-297">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![Visualizzazione malware contenuto nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="f9f93-299">**Visualizza dati per: Sostituzione messaggio**: vengono visualizzate le seguenti informazioni sul motivo dell'override:</span><span class="sxs-lookup"><span data-stu-id="f9f93-299">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="f9f93-300">**Ignora locale**</span><span class="sxs-lookup"><span data-stu-id="f9f93-300">**On-premises skip**</span></span>
  - <span data-ttu-id="f9f93-301">**IP Allow**</span><span class="sxs-lookup"><span data-stu-id="f9f93-301">**IP Allow**</span></span>
  - <span data-ttu-id="f9f93-302">**Regola del flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="f9f93-302">**Mail flow rule**</span></span>
  - <span data-ttu-id="f9f93-303">**Mittente consentito**</span><span class="sxs-lookup"><span data-stu-id="f9f93-303">**Sender allow**</span></span>
  - <span data-ttu-id="f9f93-304">**Dominio consentito**</span><span class="sxs-lookup"><span data-stu-id="f9f93-304">**Domain allow**</span></span>
  - <span data-ttu-id="f9f93-305">**ZAP non abilitato**</span><span class="sxs-lookup"><span data-stu-id="f9f93-305">**ZAP not enabled**</span></span>
  - <span data-ttu-id="f9f93-306">**Cartella Posta indesiderata non abilitata**</span><span class="sxs-lookup"><span data-stu-id="f9f93-306">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="f9f93-307">**Mittente sicuro utente**</span><span class="sxs-lookup"><span data-stu-id="f9f93-307">**User Safe Sender**</span></span>
  - <span data-ttu-id="f9f93-308">**Dominio sicuro dall'utente**</span><span class="sxs-lookup"><span data-stu-id="f9f93-308">**User Safe Domain**</span></span>

  ![Visualizzazione sostituzione messaggio nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="f9f93-310">**Scomporsi per: Tecnologia di rilevamento** **e Visualizzazione dati per: E-mail \> Phish**: Vengono visualizzate le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="f9f93-310">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="f9f93-311">**Reputazione URL generata da ATP**<sup>1</sup>: reputazione url dannosa generata dalle detonazioni di Defender per Office 365 in altri clienti di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9f93-311">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="f9f93-312">**Filtro phish avanzato:** segnali di phishing basati sull'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="f9f93-312">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="f9f93-313">**Anti-spoof - Errore DMARC**: errore di autenticazione DMARC nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="f9f93-313">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="f9f93-314">**Anti-spoofing - intra-org:** il mittente sta tentando di eseguire lo spoofing del dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="f9f93-314">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="f9f93-315">**Anti-spoofing - dominio esterno:** il mittente sta tentando di eseguire lo spoofing di un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="f9f93-315">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="f9f93-316">**Rappresentazione del marchio**: Rappresentazione di marchi noti in base ai mittenti.</span><span class="sxs-lookup"><span data-stu-id="f9f93-316">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="f9f93-317">**Rappresentazione di dominio**<sup>1</sup>: Rappresentazione dei domini che il cliente possiede o definisce.</span><span class="sxs-lookup"><span data-stu-id="f9f93-317">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="f9f93-318">**Reputazione URL EOP**: reputazione URL dannoso.</span><span class="sxs-lookup"><span data-stu-id="f9f93-318">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="f9f93-319">**Filtro phish generale**: Segnali di phishing basati sulle regole degli analisti.</span><span class="sxs-lookup"><span data-stu-id="f9f93-319">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="f9f93-320">**Altri**</span><span class="sxs-lookup"><span data-stu-id="f9f93-320">**Others**</span></span>
  - <span data-ttu-id="f9f93-321">**Phish ZAP**<sup>2</sup>: Eliminazione automatica a zero ore dei messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="f9f93-321">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="f9f93-322">**Detonazione URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f9f93-322">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="f9f93-323">**Rappresentazione utente**<sup>1</sup>: Rappresentazione degli utenti definiti dall'amministratore o appresi tramite l'intelligence delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="f9f93-323">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Visualizzazione della tecnologia di rilevamento per la posta elettronica di phishing nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="f9f93-325">**Scomporsi per: Tecnologia di rilevamento** e Visualizzazione dati per: Malware di posta elettronica : Vengono visualizzate le informazioni seguenti: **\>**</span><span class="sxs-lookup"><span data-stu-id="f9f93-325">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="f9f93-326">**Reputazione file generata da ATP**<sup>1:</sup>tutta la reputazione dei file dannosi generata da Defender per le detonazioni di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9f93-326">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="f9f93-327">**Motore antimalware**<sup>1</sup>: Rilevamento da motori antimalware.</span><span class="sxs-lookup"><span data-stu-id="f9f93-327">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="f9f93-328">**Blocco del tipo di file dei** criteri antimalware: si tratta di messaggi di posta elettronica filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="f9f93-328">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="f9f93-329">**Detonazione file**<sup>1</sup>: rilevamento tramite allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="f9f93-329">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="f9f93-330">**Reputazione di file dannosi**</span><span class="sxs-lookup"><span data-stu-id="f9f93-330">**Malicious file reputation**</span></span>
  - <span data-ttu-id="f9f93-331">**Malware ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f9f93-331">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="f9f93-332">**Altri**</span><span class="sxs-lookup"><span data-stu-id="f9f93-332">**Others**</span></span>

  ![Visualizzazione della tecnologia di rilevamento per il malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="f9f93-334">**Scomporsi per: Tipo di criterio** e Visualizza dati **per: \> E-mail Phish** o Visualizza dati **per: Email \> Malware**: Vengono visualizzate le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="f9f93-334">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="f9f93-335">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="f9f93-335">**Anti-malware**</span></span>
  - <span data-ttu-id="f9f93-336">**Allegati sicuri**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f9f93-336">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="f9f93-337">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="f9f93-337">**Anti-phish**</span></span>
  - <span data-ttu-id="f9f93-338">**Protezione da posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="f9f93-338">**Anti-spam**</span></span>
  - <span data-ttu-id="f9f93-339">**Regola del flusso di** posta (nota anche come regola di trasporto)</span><span class="sxs-lookup"><span data-stu-id="f9f93-339">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="f9f93-340">**Altri**</span><span class="sxs-lookup"><span data-stu-id="f9f93-340">**Others**</span></span>

  ![Visualizzazione del tipo di criterio per la posta elettronica di phishing nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="f9f93-342">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span><span class="sxs-lookup"><span data-stu-id="f9f93-342">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="f9f93-343">**Recapito non riuscito**</span><span class="sxs-lookup"><span data-stu-id="f9f93-343">**Delivery failed**</span></span>
  - <span data-ttu-id="f9f93-344">**Rilasciato**</span><span class="sxs-lookup"><span data-stu-id="f9f93-344">**Dropped**</span></span>
  - <span data-ttu-id="f9f93-345">**Inoltrato**</span><span class="sxs-lookup"><span data-stu-id="f9f93-345">**Forwarded**</span></span>
  - <span data-ttu-id="f9f93-346">**Cassetta postale ospitata: cartella personalizzata**</span><span class="sxs-lookup"><span data-stu-id="f9f93-346">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="f9f93-347">**Cassetta postale ospitata: Elementi eliminati**</span><span class="sxs-lookup"><span data-stu-id="f9f93-347">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="f9f93-348">**Cassetta postale ospitata: Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="f9f93-348">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="f9f93-349">**Cassetta postale ospitata: Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="f9f93-349">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="f9f93-350">**Server locale: recapitato**</span><span class="sxs-lookup"><span data-stu-id="f9f93-350">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="f9f93-351">**Quarantena**</span><span class="sxs-lookup"><span data-stu-id="f9f93-351">**Quarantine**</span></span>

  ![Visualizzazione dello stato del recapito per la posta elettronica di phishing nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="f9f93-353"><sup>1</sup> Defender solo per Office 365</span><span class="sxs-lookup"><span data-stu-id="f9f93-353"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="f9f93-354"><sup>2</sup> L'eliminazione automatica a zero ore (ZAP) non è disponibile in EOP autonomo (funziona solo nelle cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="f9f93-354"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="f9f93-355">Se si fa **clic su Filtri**, i filtri disponibili dipendono dal grafico che si stava esaminando:</span><span class="sxs-lookup"><span data-stu-id="f9f93-355">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f9f93-356">Per **Visualizza dati per: \> Malware** contenuto, è possibile modificare il report in base alla data di inizio **e** alla data **di fine** e al **valore di** rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f9f93-356">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="f9f93-357">Per **Visualizza dati per: Sostituzione messaggio**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-357">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f9f93-358">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-358">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f9f93-359">**Motivo sostituzione**</span><span class="sxs-lookup"><span data-stu-id="f9f93-359">**Override Reason**</span></span>
  - <span data-ttu-id="f9f93-360">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="f9f93-360">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f9f93-361">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="f9f93-361">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="f9f93-362">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f9f93-362">**Domain**</span></span>

- <span data-ttu-id="f9f93-363">Per tutte le altre visualizzazioni, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-363">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f9f93-364">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-364">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f9f93-365">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="f9f93-365">**Detection**</span></span>
  - <span data-ttu-id="f9f93-366">**Protetto da**: **ATP** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="f9f93-366">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="f9f93-367">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="f9f93-367">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f9f93-368">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="f9f93-368">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="f9f93-369">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f9f93-369">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="f9f93-370">Visualizzazione tabella dettagli per il rapporto sullo stato di Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f9f93-370">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="f9f93-371">Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="f9f93-371">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f9f93-372">**Visualizza dati per: Panoramica**: non **è disponibile** il pulsante Visualizza tabella dettagli.</span><span class="sxs-lookup"><span data-stu-id="f9f93-372">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="f9f93-373">**Visualizzare i dati per: Contenuto \> Malware**:</span><span class="sxs-lookup"><span data-stu-id="f9f93-373">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="f9f93-374">**Data**</span><span class="sxs-lookup"><span data-stu-id="f9f93-374">**Date**</span></span>
  - <span data-ttu-id="f9f93-375">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="f9f93-375">**Location**</span></span>
  - <span data-ttu-id="f9f93-376">**Diretto da**</span><span class="sxs-lookup"><span data-stu-id="f9f93-376">**Directed by**</span></span>
  - <span data-ttu-id="f9f93-377">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="f9f93-377">**Malware name**</span></span>

  <span data-ttu-id="f9f93-378">Se si fa **clic su** Filtri in questa visualizzazione, è possibile modificare il report in base alla data di **inizio** e alla data **di fine** e al **valore di** rilevamento.</span><span class="sxs-lookup"><span data-stu-id="f9f93-378">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="f9f93-379">**Visualizzare i dati per: Sostituzione messaggio**:</span><span class="sxs-lookup"><span data-stu-id="f9f93-379">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="f9f93-380">**Data**</span><span class="sxs-lookup"><span data-stu-id="f9f93-380">**Date**</span></span>
  - <span data-ttu-id="f9f93-381">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="f9f93-381">**Subject**</span></span>
  - <span data-ttu-id="f9f93-382">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="f9f93-382">**Sender**</span></span>
  - <span data-ttu-id="f9f93-383">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="f9f93-383">**Recipients**</span></span>
  - <span data-ttu-id="f9f93-384">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="f9f93-384">**Detected by**</span></span>
  - <span data-ttu-id="f9f93-385">**Motivo sostituzione**</span><span class="sxs-lookup"><span data-stu-id="f9f93-385">**Override Reason**</span></span>
  - <span data-ttu-id="f9f93-386">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="f9f93-386">**Source of Compromise**</span></span>
  - <span data-ttu-id="f9f93-387">**Tag**</span><span class="sxs-lookup"><span data-stu-id="f9f93-387">**Tags**</span></span>

  <span data-ttu-id="f9f93-388">Se si fa **clic su** Filtri in questa visualizzazione, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-388">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f9f93-389">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-389">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f9f93-390">**Motivo sostituzione**</span><span class="sxs-lookup"><span data-stu-id="f9f93-390">**Override Reason**</span></span>
  - <span data-ttu-id="f9f93-391">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="f9f93-391">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f9f93-392">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="f9f93-392">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="f9f93-393">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f9f93-393">**Domain**</span></span>
  - <span data-ttu-id="f9f93-394">**Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="f9f93-394">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="f9f93-395">Tutti gli altri grafici:</span><span class="sxs-lookup"><span data-stu-id="f9f93-395">All other charts:</span></span>

  - <span data-ttu-id="f9f93-396">**Data**</span><span class="sxs-lookup"><span data-stu-id="f9f93-396">**Date**</span></span>
  - <span data-ttu-id="f9f93-397">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="f9f93-397">**Subject**</span></span>
  - <span data-ttu-id="f9f93-398">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="f9f93-398">**Sender**</span></span>
  - <span data-ttu-id="f9f93-399">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="f9f93-399">**Recipients**</span></span>
  - <span data-ttu-id="f9f93-400">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="f9f93-400">**Detected by**</span></span>
  - <span data-ttu-id="f9f93-401">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="f9f93-401">**Delivery Status**</span></span>
  - <span data-ttu-id="f9f93-402">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="f9f93-402">**Source of Compromise**</span></span>
  - <span data-ttu-id="f9f93-403">**Tag**</span><span class="sxs-lookup"><span data-stu-id="f9f93-403">**Tags**</span></span>

  <span data-ttu-id="f9f93-404">Se si fa **clic su Filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-404">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f9f93-405">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="f9f93-405">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f9f93-406">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="f9f93-406">**Detection**</span></span>
  - <span data-ttu-id="f9f93-407">**Protetto da**: **Defender per Office 365** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="f9f93-407">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="f9f93-408">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="f9f93-408">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="f9f93-409">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="f9f93-409">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="f9f93-410">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f9f93-410">**Domain**</span></span>
  - <span data-ttu-id="f9f93-411">**Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="f9f93-411">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="f9f93-412">Report principale sul malware</span><span class="sxs-lookup"><span data-stu-id="f9f93-412">Top malware report</span></span>

<span data-ttu-id="f9f93-413">Il **report Top malware** mostra i vari tipi di malware rilevati dalla protezione [antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-413">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="f9f93-414">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Malware principale.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-414">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="f9f93-415">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="f9f93-415">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Widget malware principale nel dashboard dei report](../../media/top-malware-report-widget.png)

<span data-ttu-id="f9f93-417">Quando si passa il mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi rilevati come malware.</span><span class="sxs-lookup"><span data-stu-id="f9f93-417">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Visualizzazione dei report principali sul malware](../../media/top-malware-report-view.png)

<span data-ttu-id="f9f93-419">Se si fa **clic su Visualizza tabella dettagli**, è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-419">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="f9f93-420">**Malware principale**</span><span class="sxs-lookup"><span data-stu-id="f9f93-420">**Top malware**</span></span>
- <span data-ttu-id="f9f93-421">**Numero**</span><span class="sxs-lookup"><span data-stu-id="f9f93-421">**Count**</span></span>

<span data-ttu-id="f9f93-422">Se si fa **clic su Filtri** nella visualizzazione report o nella visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="f9f93-422">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="f9f93-423">Report di protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="f9f93-423">URL threat protection report</span></span>

<span data-ttu-id="f9f93-424">Il **report di protezione dalle minacce URL** è disponibile in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9f93-424">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f9f93-425">Per ulteriori informazioni, vedere [Report di protezione dalle minacce URL](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="f9f93-425">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="f9f93-426">Rapporto messaggi segnalati dall'utente</span><span class="sxs-lookup"><span data-stu-id="f9f93-426">User-reported messages report</span></span>

<span data-ttu-id="f9f93-427">Il **rapporto** Messaggi segnalati dall'utente mostra informazioni sui messaggi di posta elettronica segnalati [](enable-the-report-message-add-in.md) dagli utenti come posta indesiderata, tentativi di phishing o buona posta utilizzando il componente aggiuntivo Segnala messaggio o Il componente aggiuntivo Segnala [phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="f9f93-427">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="f9f93-428">Sono disponibili dettagli per ogni messaggio, incluso il motivo del recapito, ad esempio un'eccezione del criterio di posta indesiderata o una regola del flusso di posta configurata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f9f93-428">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="f9f93-429">Per visualizzare i dettagli, selezionare un elemento nell'elenco dei report utente e quindi visualizzare le informazioni nelle **schede Riepilogo** **e** Dettagli.</span><span class="sxs-lookup"><span data-stu-id="f9f93-429">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![Il User-Reported messaggi mostra i messaggi che gli utenti etichettano come posta indesiderata, non come posta indesiderata o tentativi di phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="f9f93-431">Per visualizzare questo report, nel [Centro sicurezza & conformità](https://protection.office.com)eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9f93-431">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="f9f93-432">Vai a **Dashboard di gestione delle** \> **minacce** Messaggi \> **segnalati dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="f9f93-432">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="f9f93-433">Passare a **Gestione delle minacce** \> **Esaminare** i messaggi segnalati \> **dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="f9f93-433">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![Nel Centro sicurezza & conformità scegliere Gestione delle minacce \> Esaminare i messaggi segnalati \> dall'utente](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="f9f93-435">Per il corretto funzionamento del report Messaggi segnalati dall'utente, è necessario che la registrazione di controllo sia **attivata** per l'ambiente office 365.</span><span class="sxs-lookup"><span data-stu-id="f9f93-435">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="f9f93-436">Questa operazione viene in genere eseguita da un utente a cui è assegnato il ruolo Log di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f9f93-436">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="f9f93-437">Per ulteriori informazioni, vedere Attivare o disattivare la ricerca nel log di [controllo di Microsoft 365.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-437">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="f9f93-438">Quali autorizzazioni sono necessarie per visualizzare questi report?</span><span class="sxs-lookup"><span data-stu-id="f9f93-438">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="f9f93-439">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="f9f93-439">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f9f93-440">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="f9f93-440">**Organization Management**</span></span>
- <span data-ttu-id="f9f93-441">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="f9f93-441">**Security Administrator**</span></span>
- <span data-ttu-id="f9f93-442">**Lettore sicurezza**</span><span class="sxs-lookup"><span data-stu-id="f9f93-442">**Security Reader**</span></span>
- <span data-ttu-id="f9f93-443">**Lettore globale**</span><span class="sxs-lookup"><span data-stu-id="f9f93-443">**Global Reader**</span></span>

<span data-ttu-id="f9f93-444">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f9f93-444">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="f9f93-445">**Nota:** l'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di  Microsoft 365 offre agli utenti le autorizzazioni necessarie nel Centro sicurezza e conformità di & e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9f93-445">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f9f93-446">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f9f93-446">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="f9f93-447">Cosa succede se i report non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="f9f93-447">What if the reports aren't showing data?</span></span>

<span data-ttu-id="f9f93-448">Se i dati nei report non vengono visualizzati, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="f9f93-448">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="f9f93-449">Per ulteriori informazioni, vedere [Protezione dalle minacce.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="f9f93-449">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f9f93-450">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f9f93-450">Related topics</span></span>

[<span data-ttu-id="f9f93-451">Protezione da posta indesiderata e antimalware in EOP</span><span class="sxs-lookup"><span data-stu-id="f9f93-451">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="f9f93-452">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="f9f93-452">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f9f93-453">Visualizzare i report del flusso di posta nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="f9f93-453">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="f9f93-454">Visualizzare i report per Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="f9f93-454">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
