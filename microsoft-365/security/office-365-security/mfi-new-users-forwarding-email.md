---
title: Informazioni dettagliate sui messaggi di posta elettronica dei nuovi utenti inoltrati
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono scoprire come utilizzare i nuovi utenti per l'inoltro della posta elettronica nel centro sicurezza & Compliance per esaminare quando gli utenti dell'organizzazione stanno inoltrando i messaggi ai nuovi domini.
ms.openlocfilehash: af66a84efbd4c0b8f1ccdacf4b71d1caca1c3929
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877526"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="3139c-103">Nuovi utenti che inoltrano informazioni sulla posta elettronica nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="3139c-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3139c-104">È sospetto che i nuovi account utente dell'organizzazione inizino improvvisamente a inoltrare messaggi di posta elettronica ai domini esterni.</span><span class="sxs-lookup"><span data-stu-id="3139c-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="3139c-105">I **nuovi domini che vengono inoltrati tramite posta elettronica** nel [Centro sicurezza & Compliance](https://protection.office.com) notifica quando gli utenti appena creati nell'organizzazione stanno inoltrando i messaggi a domini esterni.</span><span class="sxs-lookup"><span data-stu-id="3139c-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="3139c-106">Questa condizione potrebbe indicare che sono stati utilizzati account di amministrazione compromessi per creare i nuovi utenti.</span><span class="sxs-lookup"><span data-stu-id="3139c-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="3139c-107">Se si sospetta che gli account siano stati compromessi, vedere [rispondere a un account di posta elettronica compromesso](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span><span class="sxs-lookup"><span data-stu-id="3139c-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="3139c-108">Questa intuizione viene visualizzata solo quando il problema viene rilevato e viene visualizzato nella pagina del [rapporto di inoltro](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="3139c-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Informazioni dettagliate sui messaggi di posta elettronica dei nuovi utenti inoltrati](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="3139c-110">Quando si fa clic sul widget, viene visualizzato un riquadro a comparsa in cui è possibile trovare ulteriori dettagli sui messaggi inoltrati, incluso un collegamento al [rapporto modifiche di inoltro](#forwarding-modifications-report) come descritto più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3139c-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this topic.</span></span>

![Riquadro a comparsa Dettagli visualizzato dopo aver fatto clic sul nuovo messaggio di posta elettronica di inoltro degli utenti](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="3139c-112">È inoltre possibile accedere a questa pagina dei dettagli quando si seleziona l'Insight dopo aver fatto clic su **Visualizza tutti** nell'area **suggerimenti & consigliati** (dashboard dei **report** \> **Dashboard** o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="3139c-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on ( **Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="3139c-113">È possibile fare clic sul collegamento **Visualizza rapporto associato a Insight** per passare al **rapporto modifiche di inoltro** come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="3139c-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="3139c-114">Report sulle modifiche di inoltro</span><span class="sxs-lookup"><span data-stu-id="3139c-114">Forwarding modifications report</span></span>

<span data-ttu-id="3139c-115">Il **rapporto modifiche di inoltro** Visualizza i dettagli sui messaggi che vengono inoltrati automaticamente dai mittenti nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="3139c-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="3139c-116">Account appena creati che inoltrano messaggi a domini esterni.</span><span class="sxs-lookup"><span data-stu-id="3139c-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="3139c-117">Account che inoltrano messaggi a domini esterni che non sono mai stati inoltrati da altri mittenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3139c-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="3139c-118">Questi tipi di messaggi inoltrati possono rappresentare un rischio per la sicurezza o la conformità e potrebbero indicare account compromessi.</span><span class="sxs-lookup"><span data-stu-id="3139c-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="3139c-119">Il report contiene dati per un massimo di 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="3139c-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="3139c-120">Per impostazione predefinita, il report Visualizza i dati per gli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="3139c-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="3139c-121">Questo report non è disponibile direttamente nel [Dashboard del flusso di posta](mail-flow-insights-v2.md) o nel [dashboard dei report](view-mail-flow-reports.md).</span><span class="sxs-lookup"><span data-stu-id="3139c-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="3139c-122">Oltre a fare clic sul collegamento **Visualizza rapporto associato a Insight** nell'Insight della **posta elettronica per l'inoltro di nuovi utenti** , è possibile accedere al rapporto:</span><span class="sxs-lookup"><span data-stu-id="3139c-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="3139c-123">Facendo clic sul collegamento **segnala notifiche di inoltro** nei dettagli dei [nuovi domini che vengono inoltrati tramite posta elettronica Insight](mfi-new-domains-being-forwarded-email.md).</span><span class="sxs-lookup"><span data-stu-id="3139c-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="3139c-124">Apertura <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="3139c-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="3139c-125">Visualizzazione report per il rapporto modifiche di inoltro</span><span class="sxs-lookup"><span data-stu-id="3139c-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="3139c-126">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="3139c-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="3139c-127">**Mostra dati per: nuovi utenti di inoltro** :</span><span class="sxs-lookup"><span data-stu-id="3139c-127">**Show data for: New forwarding users** :</span></span>

  ![Visualizzazione di nuovi utenti di inoltro nel rapporto modifiche di inoltro](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="3139c-129">**Mostra dati per: nuovi domini di inoltro** :</span><span class="sxs-lookup"><span data-stu-id="3139c-129">**Show data for: New forwarding domains** :</span></span>

  ![Nuova visualizzazione domini inoltrati nel rapporto modifiche di inoltro](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="3139c-131">Se si fa clic su **filtri** in una visualizzazione report, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="3139c-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="3139c-132">Visualizzazione tabella dettagli per il report modifiche di inoltro</span><span class="sxs-lookup"><span data-stu-id="3139c-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="3139c-133">Se si fa clic su **Visualizza tabella dettagli** , le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="3139c-133">If you click **View details table** , the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="3139c-134">**Mostra dati per: nuovi utenti di inoltro** :</span><span class="sxs-lookup"><span data-stu-id="3139c-134">**Show data for: New forwarding users** :</span></span>

  - <span data-ttu-id="3139c-135">**Nome** : l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="3139c-135">**Name** : The email address of the sender.</span></span>
  - <span data-ttu-id="3139c-136">**Tipo di inoltro**</span><span class="sxs-lookup"><span data-stu-id="3139c-136">**Forwarding type**</span></span>
  - <span data-ttu-id="3139c-137">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="3139c-137">**Recipient address**</span></span>
  - <span data-ttu-id="3139c-138">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="3139c-138">**Details**</span></span>
  - <span data-ttu-id="3139c-139">**Numero**</span><span class="sxs-lookup"><span data-stu-id="3139c-139">**Count**</span></span>
  - <span data-ttu-id="3139c-140">**Prima data di inoltro**</span><span class="sxs-lookup"><span data-stu-id="3139c-140">**First forward date**</span></span>

- <span data-ttu-id="3139c-141">**Mostra dati per: nuovi domini di inoltro** :</span><span class="sxs-lookup"><span data-stu-id="3139c-141">**Show data for: New forwarding domains** :</span></span>

  - <span data-ttu-id="3139c-142">**Nome** : il dominio di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="3139c-142">**Name** : The email domain of the sender.</span></span>
  - <span data-ttu-id="3139c-143">**Tipo di inoltro**</span><span class="sxs-lookup"><span data-stu-id="3139c-143">**Forwarding type**</span></span>
  - <span data-ttu-id="3139c-144">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="3139c-144">**Recipient address**</span></span>
  - <span data-ttu-id="3139c-145">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="3139c-145">**Details**</span></span>
  - <span data-ttu-id="3139c-146">**Numero**</span><span class="sxs-lookup"><span data-stu-id="3139c-146">**Count**</span></span>
  - <span data-ttu-id="3139c-147">**Prima data di inoltro**</span><span class="sxs-lookup"><span data-stu-id="3139c-147">**First forward date**</span></span>

<span data-ttu-id="3139c-148">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="3139c-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="3139c-149">Se si seleziona una riga dalla tabella, verrà visualizzato un riquadro a comparsa **Dettagli** con le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3139c-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="3139c-150">**Nome** : questo è l'indirizzo di posta elettronica del mittente (da Mostra **dati per: nuova visualizzazione utenti di inoltro** ) o il dominio di posta elettronica del mittente (da Mostra **dati per: nuova visualizzazione domini di inoltro** ).</span><span class="sxs-lookup"><span data-stu-id="3139c-150">**Name** : This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="3139c-151">**Tipo di inoltro**</span><span class="sxs-lookup"><span data-stu-id="3139c-151">**Forwarding type**</span></span>
- <span data-ttu-id="3139c-152">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="3139c-152">**Recipient**</span></span>
- <span data-ttu-id="3139c-153">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="3139c-153">**Details**</span></span>
- <span data-ttu-id="3139c-154">**Numero**</span><span class="sxs-lookup"><span data-stu-id="3139c-154">**Count**</span></span>
- <span data-ttu-id="3139c-155">**Data di inizio**</span><span class="sxs-lookup"><span data-stu-id="3139c-155">**Start date**</span></span>
- <span data-ttu-id="3139c-156">**Suggerimento** : da qui, è possibile fare clic sul collegamento per gestire l'utente nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3139c-156">**Recommendation** : From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Riquadro a comparsa dettagli dalla tabella dei dettagli della nuova visualizzazione utenti di inoltro nel rapporto modifiche di inoltro](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="3139c-158">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="3139c-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3139c-159">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3139c-159">Related topics</span></span>

<span data-ttu-id="3139c-160">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="3139c-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
