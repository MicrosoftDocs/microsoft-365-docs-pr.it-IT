---
title: Insight nelle code nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Gli amministratori possono imparare a usare il widget code nel dashboard del flusso di posta nel centro sicurezza & conformità per monitorare il flusso di posta non riuscito nelle loro organizzazioni locali o partner su connettori in uscita.
ms.openlocfilehash: fdc3f44041990e3860deb04a36a69a3d506d334a
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577308"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="760ad-103">Insight nelle code nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="760ad-103">Queues insight in the Security & Compliance Center</span></span>

<span data-ttu-id="760ad-104">Quando i messaggi non possono essere inviati dall'organizzazione ai server di posta elettronica locali o partner utilizzando i connettori, i messaggi vengono accodati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="760ad-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="760ad-105">Esempi comuni che causano questa condizione sono:</span><span class="sxs-lookup"><span data-stu-id="760ad-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="760ad-106">Il connettore non è configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="760ad-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="760ad-107">Sono state apportate modifiche alla rete o al firewall nell'ambiente locale.</span><span class="sxs-lookup"><span data-stu-id="760ad-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="760ad-108">Microsoft 365 continuerà a riprovare al recapito per 24 ore.</span><span class="sxs-lookup"><span data-stu-id="760ad-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="760ad-109">Dopo 24 ore, i messaggi scadranno e verranno restituiti ai mittenti nei rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo).</span><span class="sxs-lookup"><span data-stu-id="760ad-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="760ad-110">Se il volume della posta in coda supera la soglia predefinita (il valore predefinito è 200 messaggi), le informazioni sono disponibili nelle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="760ad-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="760ad-111">Le **Code** Insight nel dashboard del [flusso di posta elettronica](mail-flow-insights-v2.md) nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="760ad-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="760ad-112">Per ulteriori informazioni, vedere l'articolo relativo alle [code nella sezione Dashboard del flusso di posta](#queues-insight-in-the-mail-flow-dashboard) di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="760ad-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>
  
- <span data-ttu-id="760ad-113">Viene visualizzato un avviso in **avvisi recenti** il dashboard avvisi nel [Centro sicurezza & conformità](https://protection.office.com) (Dashboard**avvisi** \> **Dashboard** o <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="760ad-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Avvisi recenti nel dashboard avvisi nel centro sicurezza & Compliance](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="760ad-115">Gli amministratori riceveranno una notifica tramite posta elettronica in base alla configurazione del criterio di avviso predefinito denominato **messaggi che sono stati posticipati**.</span><span class="sxs-lookup"><span data-stu-id="760ad-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="760ad-116">Per configurare le impostazioni di notifica per questo avviso, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="760ad-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="760ad-117">Per ulteriori informazioni sui criteri di avviso, vedere [criteri di avviso nel centro sicurezza & conformità](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="760ad-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="760ad-118">Personalizzare gli avvisi delle code</span><span class="sxs-lookup"><span data-stu-id="760ad-118">Customize queue alerts</span></span>

1. <span data-ttu-id="760ad-119">Nel [Centro sicurezza & conformità](https://protection.office.com), accedere a criteri **Alerts** di \> **avviso** avvisi o Apri <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="760ad-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="760ad-120">Nella pagina **criteri di avviso** individuare e selezionare i criteri denominati **messaggi sono stati posticipati**.</span><span class="sxs-lookup"><span data-stu-id="760ad-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="760ad-121">Nel riquadro a comparsa **ritardato** che si apre, è possibile abilitare o disabilitare l'avviso e configurare le impostazioni di notifica.</span><span class="sxs-lookup"><span data-stu-id="760ad-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![I messaggi sono stati ritardati dettagli dei criteri di avviso il Centro sicurezza & Compliance](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="760ad-123">**Stato**: è possibile attivare o disattivare l'avviso.</span><span class="sxs-lookup"><span data-stu-id="760ad-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="760ad-124">**Destinatari della posta elettronica** e **limite di notifica giornaliero**: fare clic su **modifica** per configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="760ad-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="760ad-125">Per configurare le impostazioni di notifica, fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="760ad-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="760ad-126">Nel riquadro a comparsa dei **criteri di modifica** che viene visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="760ad-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="760ad-127">**Invia notifiche tramite posta elettronica**: il valore predefinito è attivato.</span><span class="sxs-lookup"><span data-stu-id="760ad-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="760ad-128">**Destinatari della posta elettronica**: il valore predefinito è **TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="760ad-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="760ad-129">**Limite di notifica giornaliero**: il valore predefinito è **Nessun limite**.</span><span class="sxs-lookup"><span data-stu-id="760ad-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="760ad-130">**Soglia**: il valore predefinito è 200.</span><span class="sxs-lookup"><span data-stu-id="760ad-130">**Threshold**: The default value is 200.</span></span>

   ![Le impostazioni di notifica nei messaggi sono state ritardate dettagli dei criteri di avviso il Centro sicurezza & conformità](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="760ad-132">Al termine, fare clic su **Salva** e **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="760ad-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="760ad-133">Insight nelle code nel dashboard del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="760ad-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="760ad-134">Anche se il volume del messaggio in coda non ha superato la soglia e ha generato un avviso, è comunque possibile utilizzare le **Code** Insight nel [Dashboard del flusso di posta](mail-flow-insights-v2.md) per visualizzare i messaggi accodati per più di un'ora e intervenire prima che il numero di messaggi in coda diventi troppo elevato.</span><span class="sxs-lookup"><span data-stu-id="760ad-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Widget code nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/mfi-queues-widget.png)

<span data-ttu-id="760ad-136">Se si fa clic sul numero di messaggi sul widget, viene visualizzato un riquadro a comparsa in **coda dei messaggi** con le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="760ad-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="760ad-137">**Numero di messaggi in coda**</span><span class="sxs-lookup"><span data-stu-id="760ad-137">**Number of queued messages**</span></span>
- <span data-ttu-id="760ad-138">**Nome connettore**: fare clic sul nome del connettore per gestire il connettore nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="760ad-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="760ad-139">**Ora di inizio coda**</span><span class="sxs-lookup"><span data-stu-id="760ad-139">**Queue started time**</span></span>
- <span data-ttu-id="760ad-140">**Messaggi meno recenti scaduti**</span><span class="sxs-lookup"><span data-stu-id="760ad-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="760ad-141">**Server di destinazione**</span><span class="sxs-lookup"><span data-stu-id="760ad-141">**Destination server**</span></span>
- <span data-ttu-id="760ad-142">**Ultimo indirizzo IP**</span><span class="sxs-lookup"><span data-stu-id="760ad-142">**Last IP address**</span></span>
- <span data-ttu-id="760ad-143">**Ultimo errore**</span><span class="sxs-lookup"><span data-stu-id="760ad-143">**Last error**</span></span>
- <span data-ttu-id="760ad-144">**Come risolvere il**problema: sono disponibili problemi e soluzioni comuni.</span><span class="sxs-lookup"><span data-stu-id="760ad-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="760ad-145">Se è disponibile un collegamento **Correggi ora** , fare clic su di esso per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="760ad-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="760ad-146">In caso contrario, fare clic su tutti i collegamenti disponibili per ulteriori informazioni sull'errore e le possibili soluzioni.</span><span class="sxs-lookup"><span data-stu-id="760ad-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Dettagli dopo aver fatto clic su informazioni sulle code nel dashboard del flusso di posta](../../media/mfi-queues-details.png)

<span data-ttu-id="760ad-148">Lo stesso riquadro a comparsa visualizzato dopo aver fatto clic su **Visualizza coda** nei dettagli di un **messaggio è stato ritardato** .</span><span class="sxs-lookup"><span data-stu-id="760ad-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![I messaggi sono stati ritardati dettagli dell'avviso nel centro sicurezza & conformità](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="760ad-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="760ad-150">See also</span></span>

<span data-ttu-id="760ad-151">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="760ad-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
