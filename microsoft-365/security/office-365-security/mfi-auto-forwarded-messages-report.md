---
title: Insight dei messaggi con inoltro automatico
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Gli amministratori possono ottenere informazioni sul rapporto messaggi auto-inoltrati nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance.
ms.openlocfilehash: 05e3f62610c32bc95caf579ef4dd46bf1ed90275
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577820"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="fb4d6-103">Insight dei messaggi auto-inoltrati nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="fb4d6-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

<span data-ttu-id="fb4d6-104">L'Insight dei **messaggi auto-inoltrati** nel [Dashboard del flusso di posta elettronica](mail-flow-insights-v2.md) nel centro sicurezza & conformità Visualizza informazioni sui messaggi che vengono inoltrati automaticamente dall'organizzazione ai destinatari nei domini esterni.</span><span class="sxs-lookup"><span data-stu-id="fb4d6-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget messaggi auto-inoltrati nel centro sicurezza & Compliance](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="fb4d6-106">Dettagli dei messaggi inoltrati automaticamente</span><span class="sxs-lookup"><span data-stu-id="fb4d6-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="fb4d6-107">Quando si fa clic sul numero di messaggi nel widget, viene visualizzato un riquadro a comparsa che consente di visualizzare ulteriori informazioni sui messaggi auto-inoltrati:</span><span class="sxs-lookup"><span data-stu-id="fb4d6-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="fb4d6-108">Inoltro **automatico dei messaggi tramite i metodi di inoltro**:</span><span class="sxs-lookup"><span data-stu-id="fb4d6-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="fb4d6-109">**Regole del flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="fb4d6-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="fb4d6-110">**Dalle regole di posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="fb4d6-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="fb4d6-111">**Per inoltro SMTP**</span><span class="sxs-lookup"><span data-stu-id="fb4d6-111">**By SMTP forwarding**</span></span>
  - <span data-ttu-id="fb4d6-112">Un collegamento al [rapporto di inoltro](view-mail-flow-reports.md#forwarding-report) per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="fb4d6-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="fb4d6-113">**Messaggi auto-inoltrati da domini e utenti**:</span><span class="sxs-lookup"><span data-stu-id="fb4d6-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="fb4d6-114">**Top 5 domini inoltrati a**</span><span class="sxs-lookup"><span data-stu-id="fb4d6-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="fb4d6-115">**Nuovi domini (la settimana scorsa)**</span><span class="sxs-lookup"><span data-stu-id="fb4d6-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="fb4d6-116">**Top 5 utenti di inoltro**</span><span class="sxs-lookup"><span data-stu-id="fb4d6-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="fb4d6-117">**Nuovi utenti (la settimana scorsa)**</span><span class="sxs-lookup"><span data-stu-id="fb4d6-117">**New users (last week)**</span></span>
  - <span data-ttu-id="fb4d6-118">Un collegamento al [rapporto di modifica di inoltro](mfi-new-users-forwarding-email.md#forwarding-modifications-report) per ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="fb4d6-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Riquadro a comparsa dettagli per il rapporto messaggi auto-inoltrati nel centro sicurezza & Compliance](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="fb4d6-120">Approfondimenti</span><span class="sxs-lookup"><span data-stu-id="fb4d6-120">Insights</span></span>

<span data-ttu-id="fb4d6-121">Vengono generate due intuizioni in base ai dati del rapporto:</span><span class="sxs-lookup"><span data-stu-id="fb4d6-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="fb4d6-122">Nuovi utenti che inoltrano messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="fb4d6-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="fb4d6-123">Nuovi domini che vengono inoltrati tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="fb4d6-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="fb4d6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb4d6-124">See also</span></span>

<span data-ttu-id="fb4d6-125">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="fb4d6-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
