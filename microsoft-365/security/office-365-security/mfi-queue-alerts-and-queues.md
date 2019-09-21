---
title: Avvisi di coda e code
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Gli amministratori possono ottenere informazioni sugli avvisi e le code in coda nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance.
ms.openlocfilehash: ef8b4acd4008f3039030049893f83a5e49e1efc2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084676"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="42235-103">Avvisi di coda e code</span><span class="sxs-lookup"><span data-stu-id="42235-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="42235-104">Avvisi di coda</span><span class="sxs-lookup"><span data-stu-id="42235-104">Queue alerts</span></span>

<span data-ttu-id="42235-105">Quando i messaggi non possono essere inviati dall'organizzazione di Office 365 ai server di posta elettronica locali o partner utilizzando i connettori, i messaggi vengono accodati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="42235-105">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365.</span></span> <span data-ttu-id="42235-106">Esempi comuni che causano questa condizione sono:</span><span class="sxs-lookup"><span data-stu-id="42235-106">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="42235-107">Il connettore non è configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="42235-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="42235-108">Sono state apportate modifiche alla rete o al firewall nell'ambiente locale.</span><span class="sxs-lookup"><span data-stu-id="42235-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="42235-109">Office 365 continuerà a essere recapitato per 48 ore.</span><span class="sxs-lookup"><span data-stu-id="42235-109">Office 365 will continue to retry to delivery for 48 hours.</span></span> <span data-ttu-id="42235-110">Dopo 48 ore, i messaggi scadranno e verranno restituiti ai mittenti nei rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo).</span><span class="sxs-lookup"><span data-stu-id="42235-110">After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="42235-111">Se il volume della posta in coda supera la soglia predefinita (il valore predefinito è 2000 messaggi), gli avvisi saranno disponibili nel dashboard del flusso di posta in **avvisi recenti**e gli amministratori riceveranno una notifica tramite posta elettronica (per il loro indirizzo di posta elettronica alternativo) .</span><span class="sxs-lookup"><span data-stu-id="42235-111">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address).</span></span> <span data-ttu-id="42235-112">Per configurare la soglia di avviso, il limite di notifica giornaliero e/o i destinatari dell'avviso, vedere la sezione **personalizzare gli avvisi di coda** riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="42235-112">To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![Avvisi di coda nell'area avvisi recenti del dashboard del flusso di posta elettronica nel centro sicurezza & conformità](../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="42235-114">Personalizzare gli avvisi delle code</span><span class="sxs-lookup"><span data-stu-id="42235-114">Customize queue alerts</span></span>

<span data-ttu-id="42235-115">Informazioni sul flusso di posta per creare un criterio di avviso denominato **messaggi sono stati ritardati** (la casella di controllo **Invia notifiche tramite posta elettronica** nella schermata di esempio seguente) rilevata nei **criteri di avviso** **avvisi** \> .</span><span class="sxs-lookup"><span data-stu-id="42235-115">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**.</span></span> <span data-ttu-id="42235-116">È possibile modificare la soglia e i destinatari degli avvisi facendo clic sul criterio.</span><span class="sxs-lookup"><span data-stu-id="42235-116">You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![Spostamento avvisi](../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="42235-118">Verrà visualizzato un nuovo Blade informazioni sui criteri, è ora possibile fare clic su **modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="42235-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![Criterio di modifica ](../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="42235-120">Il Blade delle informazioni verrà modificato nel **criterio di modifica**.</span><span class="sxs-lookup"><span data-stu-id="42235-120">The information blade will change to the **Edit Policy**.</span></span> <span data-ttu-id="42235-121">Ora è possibile modificare i destinatari per la posta elettronica di avviso, il limite per il numero di notifiche inviate al giorno e la soglia minima per attivare l'avviso (200 o più).</span><span class="sxs-lookup"><span data-stu-id="42235-121">You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![Modifica del Blade del criterio](../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="42235-123">Dettagli avviso coda</span><span class="sxs-lookup"><span data-stu-id="42235-123">Queue alert details</span></span>

<span data-ttu-id="42235-124">Quando si fa clic sull'avviso, i dettagli degli avvisi vengono visualizzati in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="42235-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![Selezionare un avviso di coda nell'area avvisi recenti del dashboard del flusso di posta elettronica nel centro sicurezza & conformità](../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![Riquadro a comparsa Dettagli avviso coda nel centro sicurezza & conformità](../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="42235-127">È possibile fare clic su **Visualizza coda** nei dettagli degli avvisi per visualizzare i dettagli della coda, i problemi e i collegamenti alle correzioni disponibili in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="42235-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![Riquadro a comparsa Dettagli avviso coda nel centro sicurezza & conformità](../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Visualizza coda nei dettagli degli avvisi](../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="42235-130">Code</span><span class="sxs-lookup"><span data-stu-id="42235-130">Queues</span></span>

<span data-ttu-id="42235-131">Anche se il volume del messaggio in coda non ha superato la soglia, è comunque possibile utilizzare l'area **Code** del dashboard del flusso di posta per visualizzare i messaggi che sono stati accodati per più di un'ora.</span><span class="sxs-lookup"><span data-stu-id="42235-131">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour.</span></span> <span data-ttu-id="42235-132">È possibile utilizzare l'area **Code** per monitorare il numero di messaggi in coda (il valore 0 indica che il flusso di posta è OK) ed eseguire un'azione prima che il numero di messaggi in coda diventi troppo elevato.</span><span class="sxs-lookup"><span data-stu-id="42235-132">You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Code nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="42235-134">Quando si fa clic sul numero di messaggi in coda nelle **Code**, i dettagli della coda e le indicazioni su come risolvere il problema verranno visualizzati in un riquadro a comparsa (lo stesso riquadro a comparsa visualizzato dopo aver fatto clic su **Visualizza coda** nei dettagli di un avviso di coda).</span><span class="sxs-lookup"><span data-stu-id="42235-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![Dettagli coda](../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a><span data-ttu-id="42235-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42235-136">See also</span></span>

<span data-ttu-id="42235-137">Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="42235-137">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
