---
title: Informazioni dettagliate sui messaggi di posta elettronica dei nuovi domini inoltrati
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono imparare a usare le informazioni dettagliate sui nuovi domini inoltrati tramite posta elettronica nel dashboard del flusso di posta nel Centro sicurezza & conformità per analizzare quando gli utenti inoltrano i messaggi a domini esterni a cui non sono mai stati inoltrati.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1310350bd4ff6b43d321f5888c9436ac71debb82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929349"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="19fd8-103">Informazioni dettagliate sui nuovi domini inoltrati tramite posta elettronica nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="19fd8-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="19fd8-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="19fd8-104">**Applies to**</span></span>
- [<span data-ttu-id="19fd8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="19fd8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="19fd8-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="19fd8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="19fd8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19fd8-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="19fd8-108">Esistono validi motivi aziendali per inoltrare i messaggi di posta elettronica a destinatari esterni in domini specifici.</span><span class="sxs-lookup"><span data-stu-id="19fd8-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="19fd8-109">Tuttavia, è sospetto quando gli utenti dell'organizzazione iniziano improvvisamente a inoltrare i messaggi a un dominio a cui nessuno nell'organizzazione ha mai inoltrato i messaggi (un nuovo dominio).</span><span class="sxs-lookup"><span data-stu-id="19fd8-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="19fd8-110">Questa condizione potrebbe indicare che gli account utente sono compromessi.</span><span class="sxs-lookup"><span data-stu-id="19fd8-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="19fd8-111">Se si sospetta che gli account siano stati compromessi, vedere [Risposta a un account di posta elettronica compromesso.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="19fd8-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="19fd8-112">Le **informazioni dettagliate sui** nuovi domini inoltrati tramite posta elettronica nel Centro sicurezza [&](https://protection.office.com) conformità notificano quando gli utenti dell'organizzazione inoltrano i messaggi a nuovi domini.</span><span class="sxs-lookup"><span data-stu-id="19fd8-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="19fd8-113">Questa panoramica viene visualizzata solo quando viene rilevato il problema e viene visualizzata nella pagina [Rapporto di inoltro.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="19fd8-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Informazioni dettagliate sui messaggi di posta elettronica dei nuovi domini inoltrati](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="19fd8-115">Quando si fa clic sul widget, viene visualizzato un riquadro a comparsa in cui è possibile trovare ulteriori dettagli sui messaggi inoltrati, incluso un collegamento al [report Inoltro.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="19fd8-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Riquadro a comparsa Dettagli visualizzato dopo aver fatto clic su Informazioni dettagliate sui nuovi domini inoltrati tramite posta elettronica](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="19fd8-117">È inoltre possibile accedere **a** questa pagina dei  dettagli quando si selezionano le informazioni dettagliate dopo aver fatto clic su Visualizza tutto nell'area Principali & suggerimenti su ( \> **Dashboard** report o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="19fd8-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="19fd8-118">Per impedire l'inoltro automatico dei messaggi a domini esterni, configurare un dominio remoto per alcuni o tutti i domini esterni.</span><span class="sxs-lookup"><span data-stu-id="19fd8-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="19fd8-119">Per ulteriori informazioni, vedere [Manage remote domains in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="19fd8-119">For more information, see [Manage remote domains in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="19fd8-120">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="19fd8-120">Related topics</span></span>

<span data-ttu-id="19fd8-121">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="19fd8-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>