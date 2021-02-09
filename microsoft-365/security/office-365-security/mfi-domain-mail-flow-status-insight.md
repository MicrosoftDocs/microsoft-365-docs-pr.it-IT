---
title: Informazioni dettagliate sullo stato del flusso di posta del dominio principale nel dashboard del flusso di posta
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
description: Gli amministratori possono imparare a usare le informazioni dettagliate sullo stato del flusso di posta del dominio principale nel dashboard del flusso di posta nel Centro sicurezza & conformità per risolvere i problemi del flusso di posta correlati ai record MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df0f571d29d72b23e7b2e210b61a4fb1676175aa
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150208"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="d676d-103">Informazioni dettagliate sullo stato del flusso di posta del dominio principale nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="d676d-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d676d-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="d676d-104">**Applies to**</span></span>
- [<span data-ttu-id="d676d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d676d-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="d676d-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="d676d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="d676d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d676d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="d676d-108">Le **informazioni dettagliate sullo** stato del flusso di posta del dominio principale nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità forniscono lo stato corrente del flusso di posta per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d676d-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="d676d-109">Queste informazioni consentono di identificare e risolvere i problemi relativi ai domini in cui si verificano ***problemi relativi al flusso di*** posta.</span><span class="sxs-lookup"><span data-stu-id="d676d-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="d676d-110">Ad esempio, il dominio non è in grado di ricevere posta elettronica esterna perché il dominio è scaduto o il dominio ha un record MX non corretto.</span><span class="sxs-lookup"><span data-stu-id="d676d-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![Widget stato flusso dominio principale nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="d676d-112">Quando si fa **clic su Visualizza** dettagli nel widget, viene visualizzato un riquadro a comparsa Stato dominio che mostra ulteriori dettagli sullo stato di ogni dominio: </span><span class="sxs-lookup"><span data-stu-id="d676d-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="d676d-113">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="d676d-113">**Domain**</span></span>
- <span data-ttu-id="d676d-114">**Record MX precedente**</span><span class="sxs-lookup"><span data-stu-id="d676d-114">**Previous MX record**</span></span>
- <span data-ttu-id="d676d-115">**Record MX corrente**</span><span class="sxs-lookup"><span data-stu-id="d676d-115">**Current MX record**</span></span>
- <span data-ttu-id="d676d-116">**Stato ricezione posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d676d-116">**Email receiving status**</span></span>
- <span data-ttu-id="d676d-117">**Stato dominio**: un segno di spunta verde indica che il record MX corrente (nel momento in cui si è fatto clic sul widget) corrisponde al valore che abbiamo nel record e il dominio ha ricevuto posta elettronica nelle ultime due ore.</span><span class="sxs-lookup"><span data-stu-id="d676d-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="d676d-118">Una X rossa indica che il record MX è stato modificato e che il dominio non ha ricevuto messaggi di posta elettronica nelle ultime 6 ore.</span><span class="sxs-lookup"><span data-stu-id="d676d-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="d676d-119">Questo probabilmente indica che il dominio è scaduto o che il record MX è stato aggiornato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="d676d-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="d676d-120">Rivolgersi al registrar o al servizio di hosting DNS per verificare se il dominio è scaduto o se il record MX del dominio non è corretto.</span><span class="sxs-lookup"><span data-stu-id="d676d-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="d676d-121">È possibile fare **clic su Visualizza** altro per visualizzare le stesse informazioni per altri domini.</span><span class="sxs-lookup"><span data-stu-id="d676d-121">You can click **View more** to see the same information for more domains.</span></span>

![Riquadro a comparsa Dettagli in Informazioni dettagliate sullo stato del flusso di posta del dominio principale](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="d676d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d676d-123">See also</span></span>

<span data-ttu-id="d676d-124">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="d676d-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
