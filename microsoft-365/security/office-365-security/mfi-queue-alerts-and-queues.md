---
title: Informazioni dettagliate sulle code nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Gli amministratori possono imparare a usare il widget Code nel dashboard del flusso di posta nel Centro sicurezza & conformità per monitorare il flusso di posta non riuscito per le organizzazioni locali o partner tramite connettori in uscita.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65452b0ad7c31673c910ba48c9c6709995e563ce
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599984"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="4218e-103">Informazioni dettagliate sulle code nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="4218e-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4218e-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="4218e-104">**Applies to**</span></span>
- [<span data-ttu-id="4218e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4218e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4218e-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="4218e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4218e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4218e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4218e-108">Quando non è possibile inviare messaggi dall'organizzazione ai server di posta elettronica locali o partner utilizzando i connettori, i messaggi vengono accodati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4218e-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="4218e-109">Esempi comuni che causano questa condizione sono:</span><span class="sxs-lookup"><span data-stu-id="4218e-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="4218e-110">Il connettore non è configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="4218e-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="4218e-111">Sono state apportate modifiche alla rete o al firewall nell'ambiente locale.</span><span class="sxs-lookup"><span data-stu-id="4218e-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="4218e-112">Microsoft 365 continuerà a ripetere il recapito per 24 ore.</span><span class="sxs-lookup"><span data-stu-id="4218e-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="4218e-113">Dopo 24 ore, i messaggi scadranno e verranno restituiti ai mittenti nei rapporti di mancato recapito (noti anche come rapporti di mancato recapito o messaggi di mancato recapito).</span><span class="sxs-lookup"><span data-stu-id="4218e-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="4218e-114">Se il volume di posta elettronica in coda supera la soglia predefinita (il valore predefinito è 200 messaggi), le informazioni sono disponibili nelle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4218e-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="4218e-115">Informazioni **dettagliate** sulle code nel [dashboard del flusso di](mail-flow-insights-v2.md) posta nel Centro sicurezza & [conformità](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="4218e-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="4218e-116">Per ulteriori informazioni, vedere la sezione Informazioni dettagliate sulle [code nel dashboard del flusso di](#queues-insight-in-the-mail-flow-dashboard) posta in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4218e-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="4218e-117">Un avviso viene visualizzato in **Avvisi** recenti nel dashboard Avvisi nel Centro [sicurezza & conformità](https://protection.office.com) ( Dashboard **avvisi** \>  o <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="4218e-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Avvisi recenti nel dashboard Avvisi nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="4218e-119">Gli amministratori riceveranno una notifica tramite posta elettronica in base alla configurazione del criterio di avviso predefinito denominato **Messaggi ritardati.**</span><span class="sxs-lookup"><span data-stu-id="4218e-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="4218e-120">Per configurare le impostazioni di notifica per questo avviso, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="4218e-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="4218e-121">Per ulteriori informazioni sui criteri di avviso, vedere [Alert policies in the Security & Compliance Center.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4218e-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="4218e-122">Personalizzare gli avvisi delle code</span><span class="sxs-lookup"><span data-stu-id="4218e-122">Customize queue alerts</span></span>

1. <span data-ttu-id="4218e-123">Nel Centro [sicurezza & conformità](https://protection.office.com)passare a **Avvisi** Criteri \> **di avviso** o aprire <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="4218e-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="4218e-124">Nella pagina **Criteri di** avviso individuare e selezionare il criterio denominato **Messaggi ritardati.**</span><span class="sxs-lookup"><span data-stu-id="4218e-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="4218e-125">Nel **riquadro a comparsa Messaggio in ritardo** che si apre, puoi attivare o disattivare l'avviso e configurare le impostazioni di notifica.</span><span class="sxs-lookup"><span data-stu-id="4218e-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![I messaggi sono stati ritardati nei dettagli dei criteri di avviso nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="4218e-127">**Stato:** è possibile attivare o disattivare l'avviso.</span><span class="sxs-lookup"><span data-stu-id="4218e-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="4218e-128">**Destinatari di posta** elettronica **e Limite notifiche giornaliere**: fare clic **su Modifica** per configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4218e-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="4218e-129">Per configurare le impostazioni di notifica, fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="4218e-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="4218e-130">Nel riquadro **a comparsa** Modifica criterio visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4218e-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="4218e-131">**Invia notifiche tramite posta** elettronica : il valore predefinito è on.</span><span class="sxs-lookup"><span data-stu-id="4218e-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="4218e-132">**Destinatari di posta** elettronica : il valore predefinito è **TenantAdmins.**</span><span class="sxs-lookup"><span data-stu-id="4218e-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="4218e-133">**Limite notifiche giornaliere**: il valore predefinito è **No limit**.</span><span class="sxs-lookup"><span data-stu-id="4218e-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="4218e-134">**Soglia**: il valore predefinito è 200.</span><span class="sxs-lookup"><span data-stu-id="4218e-134">**Threshold**: The default value is 200.</span></span>

   ![Le impostazioni di notifica nei criteri di avviso Messaggi sono stati ritardati nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="4218e-136">Al termine, fare clic su **Salva** e **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="4218e-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="4218e-137">Informazioni dettagliate sulle code nel dashboard del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="4218e-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="4218e-138">Anche se il volume dei messaggi in coda non ha superato la  soglia e generato un avviso, è comunque possibile utilizzare le informazioni dettagliate sulle code nel [dashboard](mail-flow-insights-v2.md) del flusso di posta per visualizzare i messaggi che sono stati accodati per più di un'ora ed eseguire un'azione prima che il numero di messaggi in coda diventi troppo grande.</span><span class="sxs-lookup"><span data-stu-id="4218e-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Widget Code nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-queues-widget.png)

<span data-ttu-id="4218e-140">Se si fa clic sul numero di messaggi nel widget, viene visualizzato un riquadro **a** comparsa Messaggi accodati con le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4218e-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="4218e-141">**Numero di messaggi in coda**</span><span class="sxs-lookup"><span data-stu-id="4218e-141">**Number of queued messages**</span></span>
- <span data-ttu-id="4218e-142">**Nome connettore**: fare clic sul nome del connettore per gestire il connettore nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="4218e-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="4218e-143">**Ora di inizio coda**</span><span class="sxs-lookup"><span data-stu-id="4218e-143">**Queue started time**</span></span>
- <span data-ttu-id="4218e-144">**Messaggi meno recenti scaduti**</span><span class="sxs-lookup"><span data-stu-id="4218e-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="4218e-145">**Server di destinazione**</span><span class="sxs-lookup"><span data-stu-id="4218e-145">**Destination server**</span></span>
- <span data-ttu-id="4218e-146">**Ultimo indirizzo IP**</span><span class="sxs-lookup"><span data-stu-id="4218e-146">**Last IP address**</span></span>
- <span data-ttu-id="4218e-147">**Ultimo errore**</span><span class="sxs-lookup"><span data-stu-id="4218e-147">**Last error**</span></span>
- <span data-ttu-id="4218e-148">**Come risolvere:** sono disponibili problemi e soluzioni comuni.</span><span class="sxs-lookup"><span data-stu-id="4218e-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="4218e-149">Se è disponibile un collegamento **Correggi** ora, fare clic su di esso per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="4218e-149">If a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="4218e-150">In caso contrario, fare clic sui collegamenti disponibili per ulteriori informazioni sull'errore e sulle possibili soluzioni.</span><span class="sxs-lookup"><span data-stu-id="4218e-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Dettagli dopo aver fatto clic su Informazioni dettagliate sulle code nel dashboard del flusso di posta](../../media/mfi-queues-details.png)

<span data-ttu-id="4218e-152">Lo stesso riquadro a comparsa viene visualizzato dopo aver fatto clic **su Visualizza** coda nei dettagli di un avviso **Messaggi ritardati.**</span><span class="sxs-lookup"><span data-stu-id="4218e-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![I messaggi sono stati ritardati dettagli dell'avviso nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="4218e-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4218e-154">See also</span></span>

<span data-ttu-id="4218e-155">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="4218e-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
