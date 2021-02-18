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
description: Gli amministratori possono ottenere informazioni sul report Dei messaggi inoltrati automaticamente nel dashboard del flusso di posta nel Centro sicurezza & conformità.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8f5e7088a88307576a054a1f6833101789d68d01
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290634"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="2650d-103">Informazioni dettagliate sui messaggi inoltrati automaticamente nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="2650d-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2650d-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="2650d-104">**Applies to**</span></span>
- [<span data-ttu-id="2650d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2650d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2650d-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="2650d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2650d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2650d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="2650d-108">Le **informazioni dettagliate** sui messaggi inoltrati automaticamente nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità visualizzano informazioni sui messaggi che vengono inoltrati automaticamente dall'organizzazione ai destinatari in domini esterni.</span><span class="sxs-lookup"><span data-stu-id="2650d-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget Messaggi inoltrati automaticamente nel Centro sicurezza & conformità](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="2650d-110">Dettagli dei messaggi inoltrati automaticamente</span><span class="sxs-lookup"><span data-stu-id="2650d-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="2650d-111">Quando si fa clic sul numero di messaggi nel widget, viene visualizzato un riquadro a comparsa che mostra ulteriori informazioni sui messaggi inoltrati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="2650d-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="2650d-112">**Messaggi inoltrati automaticamente tramite i metodi di inoltro:**</span><span class="sxs-lookup"><span data-stu-id="2650d-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="2650d-113">**Per regole del flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="2650d-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="2650d-114">**Per regole posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="2650d-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="2650d-115">**Tramite l'inoltro SMTP:** questo metodo indica l'inoltro automatico che gli amministratori possono configurare in una cassetta postale, come descritto in Configurare l'inoltro della posta [elettronica per una cassetta postale.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="2650d-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="2650d-116">Per ulteriori [dettagli, fare](view-mail-flow-reports.md#forwarding-report) clic su un collegamento al report Di inoltro.</span><span class="sxs-lookup"><span data-stu-id="2650d-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="2650d-117">**Messaggi inoltrati automaticamente da domini e utenti:**</span><span class="sxs-lookup"><span data-stu-id="2650d-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="2650d-118">**Primi 5 domini inoltrati a**</span><span class="sxs-lookup"><span data-stu-id="2650d-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="2650d-119">**Nuovi domini (ultima settimana)**</span><span class="sxs-lookup"><span data-stu-id="2650d-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="2650d-120">**Primi 5 utenti di inoltro**</span><span class="sxs-lookup"><span data-stu-id="2650d-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="2650d-121">**Nuovi utenti (ultima settimana)**</span><span class="sxs-lookup"><span data-stu-id="2650d-121">**New users (last week)**</span></span>
  - <span data-ttu-id="2650d-122">Per ulteriori dettagli, fare clic su un collegamento al [report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) Modifiche inoltro.</span><span class="sxs-lookup"><span data-stu-id="2650d-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Riquadro a comparsa Dettagli per il report Messaggi inoltrati automaticamente nel Centro sicurezza & conformità](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="2650d-124">Dati analitici</span><span class="sxs-lookup"><span data-stu-id="2650d-124">Insights</span></span>

<span data-ttu-id="2650d-125">Vengono generate due informazioni dettagliate in base ai dati del report:</span><span class="sxs-lookup"><span data-stu-id="2650d-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="2650d-126">Nuovi utenti che inoltrano la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2650d-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="2650d-127">Nuovi domini inoltrati tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2650d-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="2650d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2650d-128">See also</span></span>

<span data-ttu-id="2650d-129">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="2650d-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
