---
title: Informazioni sullo stato del flusso di posta del dominio principale nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
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
ms.openlocfilehash: d4abc311e96df87894d5f059328f1a16a00190b8
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877510"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="d4e87-103">Informazioni sullo stato del flusso di posta del dominio principale nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="d4e87-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d4e87-104">La panoramica dello **stato del flusso di posta del dominio principale** nel [Dashboard del flusso di posta elettronica](mail-flow-insights-v2.md) nel [Centro sicurezza & conformità](https://protection.office.com) fornisce lo stato corrente dei domini dell'organizzazione in termini di flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="d4e87-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="d4e87-105">Questo Insight consente di identificare e risolvere i problemi dei domini che stanno riscontrando un *_impatto sul flusso di posta_* (ad esempio, non è possibile ricevere messaggi di posta elettronica esterni), in particolare le scadenze del dominio o i domini con record MX non corretti.</span><span class="sxs-lookup"><span data-stu-id="d4e87-105">This insight helps you identify and troubleshoot domains that are experiencing \* *_mail flow impacting_* _ issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Widget dello stato del flusso di dominio principale nel dashboard del flusso di posta elettronica nel centro sicurezza & conformità](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="d4e87-107">Quando si fa clic su _ *Visualizza dettagli* \* nel widget, viene visualizzato un riquadro a comparsa di **stato del dominio** che Mostra più dettagli per lo stato di ogni dominio:</span><span class="sxs-lookup"><span data-stu-id="d4e87-107">When you click _ *View details* \* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="d4e87-108">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="d4e87-108">**Domain**</span></span>
- <span data-ttu-id="d4e87-109">**Record MX precedente**</span><span class="sxs-lookup"><span data-stu-id="d4e87-109">**Previous MX record**</span></span>
- <span data-ttu-id="d4e87-110">**Record MX corrente**</span><span class="sxs-lookup"><span data-stu-id="d4e87-110">**Current MX record**</span></span>
- <span data-ttu-id="d4e87-111">**Stato di ricezione della posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d4e87-111">**Email receiving status**</span></span>
- <span data-ttu-id="d4e87-112">**Stato del dominio** : un segno di spunta verde indica che il record MX corrente (quando si è fatto clic sul widget) corrisponde al valore che abbiamo registrato e che il dominio ha ricevuto la posta elettronica nelle ultime due ore.</span><span class="sxs-lookup"><span data-stu-id="d4e87-112">**Domain status** : A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="d4e87-113">Una X rossa indica che il record MX è stato modificato e che il dominio non ha ricevuto alcun messaggio di posta elettronica nelle ultime 6 ore.</span><span class="sxs-lookup"><span data-stu-id="d4e87-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="d4e87-114">Questo indica probabilmente che il dominio è scaduto o che il record MX è stato aggiornato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="d4e87-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="d4e87-115">Verificare con il registrar o con il servizio di hosting DNS se il dominio è scaduto o se il record MX del dominio non è corretto.</span><span class="sxs-lookup"><span data-stu-id="d4e87-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="d4e87-116">È possibile fare clic su **Visualizza altro** per visualizzare le stesse informazioni relative a più domini.</span><span class="sxs-lookup"><span data-stu-id="d4e87-116">You can click **View more** to see the same information for more domains.</span></span>

![Riquadro a comparsa dettagli nell'Insight sullo stato del flusso di posta di dominio superiore](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="d4e87-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d4e87-118">Related topics</span></span>

<span data-ttu-id="d4e87-119">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="d4e87-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
