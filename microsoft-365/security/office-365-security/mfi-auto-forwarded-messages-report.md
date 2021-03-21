---
title: Informazioni dettagliate sui messaggi inoltrati automaticamente
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Gli amministratori possono ottenere informazioni sul report Messaggi inoltrati automaticamente nel dashboard del flusso di posta nel Centro sicurezza & conformità.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 75cf060d9a597bb991fc8af2c4c70f9ecc592ad7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929361"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="d5324-103">Informazioni dettagliate sui messaggi inoltrati automaticamente nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="d5324-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d5324-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="d5324-104">**Applies to**</span></span>
- [<span data-ttu-id="d5324-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d5324-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d5324-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="d5324-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d5324-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5324-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="d5324-108">Le **informazioni dettagliate** sui messaggi inoltrati automaticamente nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [& conformità](https://protection.office.com) visualizza informazioni sui messaggi che vengono inoltrati automaticamente dall'organizzazione ai destinatari in domini esterni.</span><span class="sxs-lookup"><span data-stu-id="d5324-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget Messaggi inoltrati automaticamente nel Centro sicurezza & conformità](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="d5324-110">Dettagli dei messaggi inoltrati automaticamente</span><span class="sxs-lookup"><span data-stu-id="d5324-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="d5324-111">Quando si fa clic sul numero di messaggi nel widget, viene visualizzato un riquadro a comparsa che mostra ulteriori informazioni sui messaggi inoltrati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="d5324-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="d5324-112">**Messaggi inoltrati automaticamente tramite metodi di inoltro:**</span><span class="sxs-lookup"><span data-stu-id="d5324-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="d5324-113">**Per regole del flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="d5324-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="d5324-114">**Per regole posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="d5324-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="d5324-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="d5324-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="d5324-116">Collegamento al [report Inoltro per](view-mail-flow-reports.md#forwarding-report) ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="d5324-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="d5324-117">**Messaggi inoltrati automaticamente da domini e utenti:**</span><span class="sxs-lookup"><span data-stu-id="d5324-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="d5324-118">**Primi 5 domini inoltrati a**</span><span class="sxs-lookup"><span data-stu-id="d5324-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="d5324-119">**Nuovi domini (settimana scorsa)**</span><span class="sxs-lookup"><span data-stu-id="d5324-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="d5324-120">**Primi 5 utenti di inoltro**</span><span class="sxs-lookup"><span data-stu-id="d5324-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="d5324-121">**Nuovi utenti (settimana scorsa)**</span><span class="sxs-lookup"><span data-stu-id="d5324-121">**New users (last week)**</span></span>
  - <span data-ttu-id="d5324-122">Collegamento al [report Modifiche inoltro per](mfi-new-users-forwarding-email.md#forwarding-modifications-report) ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="d5324-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Riquadro a comparsa Dettagli per il report Messaggi inoltrati automaticamente nel Centro sicurezza & conformità](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="d5324-124">Approfondimenti</span><span class="sxs-lookup"><span data-stu-id="d5324-124">Insights</span></span>

<span data-ttu-id="d5324-125">In base ai dati del report vengono generate due informazioni dettagliate:</span><span class="sxs-lookup"><span data-stu-id="d5324-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="d5324-126">Nuovi utenti che inoltrano la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d5324-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="d5324-127">Nuovi domini inoltrati tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d5324-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="d5324-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5324-128">See also</span></span>

<span data-ttu-id="d5324-129">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="d5324-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>