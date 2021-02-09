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
ms.openlocfilehash: 7b86d726979991a55e7d4e43bf3581a4a664ee4f
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150256"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="a703d-103">Nuovi utenti che inoltrano informazioni dettagliate sulla posta elettronica nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="a703d-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a703d-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="a703d-104">**Applies to**</span></span>
- [<span data-ttu-id="a703d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a703d-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="a703d-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="a703d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="a703d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a703d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="a703d-108">È sospetto quando i nuovi account utente nell'organizzazione iniziano improvvisamente ad inoltrare i messaggi di posta elettronica ai domini esterni.</span><span class="sxs-lookup"><span data-stu-id="a703d-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="a703d-109">I **nuovi domini inoltrati** tramite posta elettronica nel Centro sicurezza [&](https://protection.office.com) conformità notificano quando gli utenti appena creati nell'organizzazione inoltrano i messaggi ai domini esterni.</span><span class="sxs-lookup"><span data-stu-id="a703d-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="a703d-110">Questa condizione potrebbe indicare che sono stati usati account amministratore compromessi per creare i nuovi utenti.</span><span class="sxs-lookup"><span data-stu-id="a703d-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="a703d-111">Se si sospetta che gli account siano stati compromessi, vedere [Rispondere a un account di posta elettronica compromesso.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="a703d-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="a703d-112">Queste informazioni vengono visualizzate solo quando viene rilevato il problema e vengono visualizzate nella pagina [del rapporto di](view-mail-flow-reports.md#forwarding-report) inoltro.</span><span class="sxs-lookup"><span data-stu-id="a703d-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Informazioni dettagliate sui messaggi di posta elettronica dei nuovi utenti inoltrati](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="a703d-114">Quando si fa clic sul widget, viene visualizzato un riquadro a comparsa in cui è possibile trovare ulteriori dettagli sui messaggi inoltrati, incluso un collegamento al [report](#forwarding-modifications-report) Modifiche di inoltro, come descritto più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a703d-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Riquadro a comparsa Dettagli che viene visualizzato dopo aver fatto clic su Informazioni dettagliate sui nuovi utenti che inoltrano i messaggi di posta elettronica](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="a703d-116">È inoltre possibile accedere **a** questa pagina dei  dettagli quando si selezionano le informazioni dettagliate dopo aver fatto clic su Visualizza tutto nell'area Principali & suggerimenti in **(** \> **Dashboard** report o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="a703d-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="a703d-117">È possibile fare clic **sul collegamento** Visualizza report associato alle informazioni dettagliate per passare al **report** Modifiche inoltro come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="a703d-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="a703d-118">Rapporto modifiche inoltro</span><span class="sxs-lookup"><span data-stu-id="a703d-118">Forwarding modifications report</span></span>

<span data-ttu-id="a703d-119">Il **rapporto Modifiche inoltro mostra** i dettagli sui messaggi che vengono inoltrati automaticamente dai mittenti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="a703d-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="a703d-120">Account appena creati che inoltrano messaggi a domini esterni.</span><span class="sxs-lookup"><span data-stu-id="a703d-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="a703d-121">Account che inoltrano messaggi a domini esterni a cui non sono mai stati inoltrati altri mittenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a703d-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="a703d-122">Questi tipi di messaggi inoltrati possono rappresentare un rischio per la sicurezza o la conformità e possono indicare account compromessi.</span><span class="sxs-lookup"><span data-stu-id="a703d-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="a703d-123">Il report contiene dati per un massimo di 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="a703d-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="a703d-124">Per impostazione predefinita, il report mostra i dati degli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="a703d-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="a703d-125">Questo report non è disponibile direttamente nel dashboard del [flusso di posta](mail-flow-insights-v2.md) o nel dashboard [report.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="a703d-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="a703d-126">Oltre a fare clic sul collegamento Visualizza  **report** associato alle informazioni dettagliate in Informazioni dettagliate sui nuovi utenti che inoltrano i messaggi di posta elettronica, è possibile accedere al report tramite:</span><span class="sxs-lookup"><span data-stu-id="a703d-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="a703d-127">Facendo clic **sul collegamento del rapporto notifiche** di inoltro nei dettagli dei nuovi domini inoltrati, informazioni [dettagliate sulla posta elettronica.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="a703d-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="a703d-128">Apertura <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="a703d-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="a703d-129">Visualizzazione report per il report Modifiche inoltro</span><span class="sxs-lookup"><span data-stu-id="a703d-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="a703d-130">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="a703d-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a703d-131">**Mostra dati per: Nuovi utenti di inoltro:**</span><span class="sxs-lookup"><span data-stu-id="a703d-131">**Show data for: New forwarding users**:</span></span>

  ![Visualizzazione Nuovi utenti di inoltro nel report Modifiche inoltro](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="a703d-133">**Mostra dati per: Nuovi domini di inoltro:**</span><span class="sxs-lookup"><span data-stu-id="a703d-133">**Show data for: New forwarding domains**:</span></span>

  ![Nuova visualizzazione dei domini inoltrati nel report Modifiche inoltro](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="a703d-135">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="a703d-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="a703d-136">Visualizzazione tabella dettagli per il report Modifiche inoltro</span><span class="sxs-lookup"><span data-stu-id="a703d-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="a703d-137">Se si **fa clic su Visualizza tabella dettagli,** le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="a703d-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a703d-138">**Mostra dati per: Nuovi utenti di inoltro:**</span><span class="sxs-lookup"><span data-stu-id="a703d-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="a703d-139">**Nome:** l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="a703d-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="a703d-140">**Tipo di inoltro**</span><span class="sxs-lookup"><span data-stu-id="a703d-140">**Forwarding type**</span></span>
  - <span data-ttu-id="a703d-141">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="a703d-141">**Recipient address**</span></span>
  - <span data-ttu-id="a703d-142">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="a703d-142">**Details**</span></span>
  - <span data-ttu-id="a703d-143">**Numero**</span><span class="sxs-lookup"><span data-stu-id="a703d-143">**Count**</span></span>
  - <span data-ttu-id="a703d-144">**First forward date**</span><span class="sxs-lookup"><span data-stu-id="a703d-144">**First forward date**</span></span>

- <span data-ttu-id="a703d-145">**Mostra dati per: Nuovi domini di inoltro:**</span><span class="sxs-lookup"><span data-stu-id="a703d-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="a703d-146">**Name**: Il dominio di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="a703d-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="a703d-147">**Tipo di inoltro**</span><span class="sxs-lookup"><span data-stu-id="a703d-147">**Forwarding type**</span></span>
  - <span data-ttu-id="a703d-148">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="a703d-148">**Recipient address**</span></span>
  - <span data-ttu-id="a703d-149">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="a703d-149">**Details**</span></span>
  - <span data-ttu-id="a703d-150">**Numero**</span><span class="sxs-lookup"><span data-stu-id="a703d-150">**Count**</span></span>
  - <span data-ttu-id="a703d-151">**First forward date**</span><span class="sxs-lookup"><span data-stu-id="a703d-151">**First forward date**</span></span>

<span data-ttu-id="a703d-152">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="a703d-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a703d-153">Se si seleziona una riga dalla tabella, verrà **visualizzato** un riquadro a comparsa Dettagli con le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a703d-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="a703d-154">**Nome**: Si tratta dell'indirizzo di posta elettronica del mittente (da Mostra dati **per:** Visualizzazione nuovi utenti di inoltro) o del dominio di posta elettronica del mittente (da Mostra dati **per:** Visualizzazione nuovi domini di inoltro).</span><span class="sxs-lookup"><span data-stu-id="a703d-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="a703d-155">**Tipo di inoltro**</span><span class="sxs-lookup"><span data-stu-id="a703d-155">**Forwarding type**</span></span>
- <span data-ttu-id="a703d-156">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="a703d-156">**Recipient**</span></span>
- <span data-ttu-id="a703d-157">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="a703d-157">**Details**</span></span>
- <span data-ttu-id="a703d-158">**Numero**</span><span class="sxs-lookup"><span data-stu-id="a703d-158">**Count**</span></span>
- <span data-ttu-id="a703d-159">**Data di inizio**</span><span class="sxs-lookup"><span data-stu-id="a703d-159">**Start date**</span></span>
- <span data-ttu-id="a703d-160">**Suggerimento:** da qui è possibile fare clic sul collegamento per gestire l'utente nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a703d-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Riquadro a comparsa Dettagli dalla tabella dei dettagli della visualizzazione Nuovi utenti di inoltro nel report Modifiche inoltro](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="a703d-162">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="a703d-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a703d-163">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a703d-163">Related topics</span></span>

<span data-ttu-id="a703d-164">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="a703d-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
