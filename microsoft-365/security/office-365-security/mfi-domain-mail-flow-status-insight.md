---
title: Informazioni sullo stato del flusso di posta del dominio principale nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su come utilizzare la panoramica dello stato del flusso di posta del dominio principale nel dashboard del flusso di posta nel centro sicurezza & Compliance per risolvere i problemi relativi al flusso di posta relativi ai record MX nei domini di posta elettronica.
ms.openlocfilehash: 9640d5e37932efeb7c0c8f8c56d0a15bc7f07e5b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827016"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="7834a-103">Informazioni sullo stato del flusso di posta del dominio principale nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="7834a-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

<span data-ttu-id="7834a-104">La panoramica dello **stato del flusso di posta del dominio principale** nel [Dashboard del flusso di posta elettronica](mail-flow-insights-v2.md) nel centro sicurezza & conformità fornisce lo stato corrente dei domini dell'organizzazione in termini di flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="7834a-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="7834a-105">Questo Insight consente di identificare e risolvere i problemi relativi ai domini che si verificano problemi di ***flusso di posta*** (ad esempio, non è possibile ricevere messaggi di posta elettronica esterni), in particolare le scadenze o i domini di dominio con record MX non corretti.</span><span class="sxs-lookup"><span data-stu-id="7834a-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Widget dello stato del flusso di dominio principale nel dashboard del flusso di posta elettronica nel centro sicurezza & conformità](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="7834a-107">Quando si fa clic su **Visualizza dettagli** nel widget, viene visualizzato un riquadro a comparsa di **stato del dominio** che Mostra più dettagli per lo stato di ogni dominio:</span><span class="sxs-lookup"><span data-stu-id="7834a-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="7834a-108">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="7834a-108">**Domain**</span></span>
- <span data-ttu-id="7834a-109">**Record MX precedente**</span><span class="sxs-lookup"><span data-stu-id="7834a-109">**Previous MX record**</span></span>
- <span data-ttu-id="7834a-110">**Record MX corrente**</span><span class="sxs-lookup"><span data-stu-id="7834a-110">**Current MX record**</span></span>
- <span data-ttu-id="7834a-111">**Stato di ricezione della posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="7834a-111">**Email receiving status**</span></span>
- <span data-ttu-id="7834a-112">**Stato del dominio**: un segno di spunta verde indica che il record MX corrente (quando si è fatto clic sul widget) corrisponde al valore che abbiamo registrato e che il dominio ha ricevuto la posta elettronica nelle ultime due ore.</span><span class="sxs-lookup"><span data-stu-id="7834a-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="7834a-113">Una X rossa indica che il record MX è stato modificato e che il dominio non ha ricevuto alcun messaggio di posta elettronica nelle ultime 6 ore.</span><span class="sxs-lookup"><span data-stu-id="7834a-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="7834a-114">Questo indica probabilmente che il dominio è scaduto o che il record MX è stato aggiornato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="7834a-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="7834a-115">Verificare con il registrar o con il servizio di hosting DNS se il dominio è scaduto o se il record MX del dominio non è corretto.</span><span class="sxs-lookup"><span data-stu-id="7834a-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="7834a-116">È possibile fare clic su **Visualizza altro** per visualizzare le stesse informazioni relative a più domini.</span><span class="sxs-lookup"><span data-stu-id="7834a-116">You can click **View more** to see the same information for more domains.</span></span>

![Riquadro a comparsa dettagli nell'Insight sullo stato del flusso di posta di dominio superiore](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="7834a-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7834a-118">Related topics</span></span>

<span data-ttu-id="7834a-119">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="7834a-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
