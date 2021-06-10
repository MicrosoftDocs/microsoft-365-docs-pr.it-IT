---
title: Informazioni dettagliate sui messaggi di posta elettronica dei nuovi utenti inoltrati
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono imparare a usare le informazioni dettagliate sui nuovi utenti che inoltrano la posta elettronica nel Centro sicurezza & conformità per analizzare quando gli utenti dell'organizzazione inoltrano i messaggi a nuovi domini.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206193"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="b7c87-103">Informazioni dettagliate sulla posta elettronica inoltrate da nuovi utenti nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="b7c87-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b7c87-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="b7c87-104">**Applies to**</span></span>
- [<span data-ttu-id="b7c87-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b7c87-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b7c87-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="b7c87-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b7c87-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7c87-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b7c87-108">È sospetto quando i nuovi account utente nell'organizzazione iniziano improvvisamente ad inoltrare i messaggi di posta elettronica ai domini esterni.</span><span class="sxs-lookup"><span data-stu-id="b7c87-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="b7c87-109">Le **informazioni dettagliate** sui nuovi domini inoltrati tramite posta elettronica nel Centro sicurezza [&](https://protection.office.com) conformità notificano quando gli utenti appena creati nell'organizzazione inoltrano i messaggi ai domini esterni.</span><span class="sxs-lookup"><span data-stu-id="b7c87-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="b7c87-110">Questa condizione potrebbe indicare che sono stati utilizzati account amministratore compromessi per creare i nuovi utenti.</span><span class="sxs-lookup"><span data-stu-id="b7c87-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="b7c87-111">Se si sospetta che gli account siano stati compromessi, vedere [Risposta a un account di posta elettronica compromesso.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="b7c87-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="b7c87-112">Questa panoramica viene visualizzata solo quando viene rilevato il problema e viene visualizzata nella pagina [Rapporto di inoltro.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="b7c87-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Informazioni dettagliate sui messaggi di posta elettronica dei nuovi utenti inoltrati](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="b7c87-114">Quando si fa clic sul widget, viene visualizzato un riquadro a comparsa in cui è possibile trovare ulteriori dettagli sui messaggi inoltrati, incluso un collegamento al [report Modifiche](#forwarding-modifications-report) di inoltro, come descritto più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b7c87-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Riquadro a comparsa Dettagli visualizzato dopo aver fatto clic su Informazioni dettagliate sui nuovi utenti che inoltrano la posta elettronica](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="b7c87-116">È inoltre possibile accedere **a** questa pagina dei  dettagli quando si selezionano le informazioni dettagliate dopo aver fatto clic su Visualizza tutto nell'area Principali & suggerimenti su ( \> **Dashboard** report o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="b7c87-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="b7c87-117">È possibile fare clic **sul collegamento** Visualizza report associato a informazioni dettagliate per passare al **report Modifiche** di inoltro come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="b7c87-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="b7c87-118">Rapporto modifiche inoltro</span><span class="sxs-lookup"><span data-stu-id="b7c87-118">Forwarding modifications report</span></span>

<span data-ttu-id="b7c87-119">Il **report Modifiche inoltro mostra i** dettagli sui messaggi che vengono inoltrati automaticamente dai mittenti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="b7c87-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="b7c87-120">Account appena creati che inoltrano messaggi a domini esterni.</span><span class="sxs-lookup"><span data-stu-id="b7c87-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="b7c87-121">Account che inoltrano messaggi a domini esterni che non sono mai stati inoltrati da altri mittenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b7c87-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="b7c87-122">Questi tipi di messaggi inoltrati possono rappresentare un rischio per la sicurezza o la conformità e possono indicare account compromessi.</span><span class="sxs-lookup"><span data-stu-id="b7c87-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="b7c87-123">Il report contiene dati per un massimo di 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="b7c87-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="b7c87-124">Per impostazione predefinita, il report mostra i dati degli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="b7c87-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="b7c87-125">Questo report non è disponibile direttamente nel [dashboard del flusso di posta](mail-flow-insights-v2.md) o nel dashboard [report.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="b7c87-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="b7c87-126">Oltre a fare clic sul collegamento Visualizza  **report** associato alle informazioni dettagliate in Informazioni dettagliate sui nuovi utenti che inoltrano la posta elettronica, è possibile accedere al report tramite:</span><span class="sxs-lookup"><span data-stu-id="b7c87-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="b7c87-127">Facendo clic **sul collegamento Rapporto notifiche di inoltro** nei dettagli di Informazioni sui nuovi domini [inoltrati tramite posta elettronica.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="b7c87-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="b7c87-128">Apertura <https://protection.office.com/reportv2?id=MailFlowNewForwarding> di .</span><span class="sxs-lookup"><span data-stu-id="b7c87-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="b7c87-129">Visualizzazione report per il report Modifiche inoltro</span><span class="sxs-lookup"><span data-stu-id="b7c87-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="b7c87-130">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7c87-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b7c87-131">**Mostra dati per: Nuovi utenti di inoltro**:</span><span class="sxs-lookup"><span data-stu-id="b7c87-131">**Show data for: New forwarding users**:</span></span>

  ![Visualizzazione Nuovi utenti di inoltro nel report Modifiche di inoltro](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="b7c87-133">**Mostra dati per: Nuovi domini di inoltro**:</span><span class="sxs-lookup"><span data-stu-id="b7c87-133">**Show data for: New forwarding domains**:</span></span>

  ![Nuova visualizzazione dei domini inoltrati nel report Modifiche di inoltro](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="b7c87-135">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="b7c87-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="b7c87-136">Visualizzazione tabella dettagli per il report Modifiche inoltro</span><span class="sxs-lookup"><span data-stu-id="b7c87-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="b7c87-137">Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="b7c87-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b7c87-138">**Mostra dati per: Nuovi utenti di inoltro**:</span><span class="sxs-lookup"><span data-stu-id="b7c87-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="b7c87-139">**Nome**: Indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="b7c87-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="b7c87-140">**Tipo di inoltro**</span><span class="sxs-lookup"><span data-stu-id="b7c87-140">**Forwarding type**</span></span>
  - <span data-ttu-id="b7c87-141">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="b7c87-141">**Recipient address**</span></span>
  - <span data-ttu-id="b7c87-142">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="b7c87-142">**Details**</span></span>
  - <span data-ttu-id="b7c87-143">**Numero**</span><span class="sxs-lookup"><span data-stu-id="b7c87-143">**Count**</span></span>
  - <span data-ttu-id="b7c87-144">**Prima data di inoltro**</span><span class="sxs-lookup"><span data-stu-id="b7c87-144">**First forward date**</span></span>

- <span data-ttu-id="b7c87-145">**Mostra dati per: Nuovi domini di inoltro**:</span><span class="sxs-lookup"><span data-stu-id="b7c87-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="b7c87-146">**Name**: Il dominio di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="b7c87-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="b7c87-147">**Tipo di inoltro**</span><span class="sxs-lookup"><span data-stu-id="b7c87-147">**Forwarding type**</span></span>
  - <span data-ttu-id="b7c87-148">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="b7c87-148">**Recipient address**</span></span>
  - <span data-ttu-id="b7c87-149">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="b7c87-149">**Details**</span></span>
  - <span data-ttu-id="b7c87-150">**Numero**</span><span class="sxs-lookup"><span data-stu-id="b7c87-150">**Count**</span></span>
  - <span data-ttu-id="b7c87-151">**Prima data di inoltro**</span><span class="sxs-lookup"><span data-stu-id="b7c87-151">**First forward date**</span></span>

<span data-ttu-id="b7c87-152">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="b7c87-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b7c87-153">Se si seleziona una riga dalla tabella, **verrà** visualizzato un riquadro a comparsa Dettagli con le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7c87-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="b7c87-154">**Nome**: si tratta dell'indirizzo di posta elettronica del mittente (da Mostra dati **per:** Visualizzazione nuovi utenti di inoltro) o del dominio di posta elettronica del mittente (da Mostra dati **per: Nuova** visualizzazione domini di inoltro).</span><span class="sxs-lookup"><span data-stu-id="b7c87-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="b7c87-155">**Tipo di inoltro**</span><span class="sxs-lookup"><span data-stu-id="b7c87-155">**Forwarding type**</span></span>
- <span data-ttu-id="b7c87-156">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="b7c87-156">**Recipient**</span></span>
- <span data-ttu-id="b7c87-157">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="b7c87-157">**Details**</span></span>
- <span data-ttu-id="b7c87-158">**Numero**</span><span class="sxs-lookup"><span data-stu-id="b7c87-158">**Count**</span></span>
- <span data-ttu-id="b7c87-159">**Data di inizio**</span><span class="sxs-lookup"><span data-stu-id="b7c87-159">**Start date**</span></span>
- <span data-ttu-id="b7c87-160">**Suggerimento:** da qui è possibile fare clic sul collegamento per gestire l'utente nell'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="b7c87-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Riquadro a comparsa Dettagli dalla tabella dei dettagli della visualizzazione Nuovi utenti di inoltro nel report Modifiche inoltro](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="b7c87-162">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="b7c87-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b7c87-163">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b7c87-163">Related topics</span></span>

<span data-ttu-id="b7c87-164">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="b7c87-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
