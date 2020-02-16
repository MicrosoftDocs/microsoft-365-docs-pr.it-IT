---
title: Informazioni dettagliate sullo stato del flusso di posta del dominio principale
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono ottenere informazioni sulla panoramica dello stato del flusso di posta del dominio principale nel dashboard del flusso di posta nel centro sicurezza & conformità.
ms.openlocfilehash: 42ce0545dad2804829d15572ce6e1f5a0ca6b49f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082845"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="d1ffd-103">Informazioni dettagliate sullo stato del flusso di posta del dominio principale</span><span class="sxs-lookup"><span data-stu-id="d1ffd-103">Top domain mail flow status insight</span></span>

<span data-ttu-id="d1ffd-104">L'Insight **sullo stato del flusso di posta di dominio principale** offre lo stato corrente dei domini dell'organizzazione in termini di flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="d1ffd-104">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="d1ffd-105">Questo Insight consente di identificare e risolvere i problemi relativi ai domini che si verificano problemi di ***flusso di posta*** (ad esempio, non è possibile ricevere messaggi di posta elettronica esterni), in particolare le scadenze o i domini di dominio con record MX non corretti.</span><span class="sxs-lookup"><span data-stu-id="d1ffd-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Informazioni sullo stato del flusso di dominio principale nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/domain-mail-flow-status-selected.png)

<span data-ttu-id="d1ffd-107">Quando si fa clic su **Visualizza dettagli** nell'Insight, viene visualizzato un riquadro a comparsa per visualizzare ulteriori dettagli sullo stato di ciascun dominio.</span><span class="sxs-lookup"><span data-stu-id="d1ffd-107">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="d1ffd-108">Un segno di spunta verde per un dominio indica che il record MX corrente (quando si è visualizzato il dashboard per la visualizzazione del flusso di posta) corrisponde al valore che abbiamo registrato e che il dominio ha ricevuto la posta elettronica nelle ultime due ore.</span><span class="sxs-lookup"><span data-stu-id="d1ffd-108">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="d1ffd-109">Una x rossa per un dominio indica che il record MX è stato modificato e che il dominio non ha ricevuto messaggi di posta elettronica nelle ultime 6 ore.</span><span class="sxs-lookup"><span data-stu-id="d1ffd-109">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="d1ffd-110">Questo indica probabilmente che il dominio è scaduto o che il record MX è stato aggiornato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="d1ffd-110">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="d1ffd-111">Verificare con il registrar o con il servizio di hosting DNS se il dominio è scaduto o se il record MX del dominio non è corretto.</span><span class="sxs-lookup"><span data-stu-id="d1ffd-111">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![Il riquadro a comparsa dettagli nell'Insight sullo stato del flusso di dominio superiore](../../media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a><span data-ttu-id="d1ffd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1ffd-113">See also</span></span>

<span data-ttu-id="d1ffd-114">Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="d1ffd-114">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
