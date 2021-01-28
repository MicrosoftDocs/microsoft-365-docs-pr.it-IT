---
title: Informazioni sullo stato del flusso di posta del dominio principale nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su come utilizzare la panoramica dello stato del flusso di posta del dominio principale nel dashboard del flusso di posta nel centro sicurezza & conformità per risolvere i problemi relativi al flusso di posta relativo ai record MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 457675e7f32cd513f5593ede53a64aaef9d54904
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029907"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="21efa-103">Informazioni sullo stato del flusso di posta del dominio principale nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="21efa-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="21efa-104">La panoramica dello **stato del flusso di posta del dominio principale** nel [Dashboard del flusso di posta elettronica](mail-flow-insights-v2.md) nel [Centro sicurezza & conformità](https://protection.office.com) fornisce lo stato corrente del flusso di posta per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21efa-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="21efa-105">Questo Insight consente di identificare e risolvere i problemi relativi ai domini che si verificano \**_flussi di posta_* _.</span><span class="sxs-lookup"><span data-stu-id="21efa-105">This insight helps you identify and troubleshoot domains that are experiencing \**_mail flow_* _ issues.</span></span> <span data-ttu-id="21efa-106">Ad esempio, il dominio non è in grado di ricevere messaggi di posta elettronica esterni perché il dominio è scaduto o il dominio ha un record MX non corretto.</span><span class="sxs-lookup"><span data-stu-id="21efa-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Widget dello stato del flusso di dominio principale nel dashboard del flusso di posta elettronica nel centro sicurezza & conformità](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="21efa-108">Quando si fa clic su _ *Visualizza dettagli*\* nel widget, viene visualizzato un riquadro a comparsa di **stato del dominio** che Mostra più dettagli per lo stato di ogni dominio:</span><span class="sxs-lookup"><span data-stu-id="21efa-108">When you click _ *View details*\* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="21efa-109">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="21efa-109">**Domain**</span></span>
- <span data-ttu-id="21efa-110">**Record MX precedente**</span><span class="sxs-lookup"><span data-stu-id="21efa-110">**Previous MX record**</span></span>
- <span data-ttu-id="21efa-111">**Record MX corrente**</span><span class="sxs-lookup"><span data-stu-id="21efa-111">**Current MX record**</span></span>
- <span data-ttu-id="21efa-112">**Stato di ricezione della posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="21efa-112">**Email receiving status**</span></span>
- <span data-ttu-id="21efa-113">**Stato del dominio**: un segno di spunta verde indica che il record MX corrente (quando si è fatto clic sul widget) corrisponde al valore che abbiamo registrato e che il dominio ha ricevuto la posta elettronica nelle ultime due ore.</span><span class="sxs-lookup"><span data-stu-id="21efa-113">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="21efa-114">Una X rossa indica che il record MX è stato modificato e che il dominio non ha ricevuto alcun messaggio di posta elettronica nelle ultime 6 ore.</span><span class="sxs-lookup"><span data-stu-id="21efa-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="21efa-115">Questo indica probabilmente che il dominio è scaduto o che il record MX è stato aggiornato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="21efa-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="21efa-116">Verificare con il registrar o con il servizio di hosting DNS se il dominio è scaduto o se il record MX del dominio non è corretto.</span><span class="sxs-lookup"><span data-stu-id="21efa-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="21efa-117">È possibile fare clic su **Visualizza altro** per visualizzare le stesse informazioni relative a più domini.</span><span class="sxs-lookup"><span data-stu-id="21efa-117">You can click **View more** to see the same information for more domains.</span></span>

![Riquadro a comparsa dettagli nell'Insight sullo stato del flusso di posta di dominio superiore](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="21efa-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21efa-119">See also</span></span>

<span data-ttu-id="21efa-120">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="21efa-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
