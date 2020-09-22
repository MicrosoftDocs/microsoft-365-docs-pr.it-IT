---
title: Informazioni dettagliate sui messaggi di posta elettronica dei nuovi domini inoltrati
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono scoprire come utilizzare i nuovi domini che vengono inoltrati tramite posta elettronica nell'interfaccia di amministrazione di Exchange moderna per esaminare quando gli utenti dell'organizzazione stanno inoltrando messaggi a domini esterni che non sono mai stati inoltrati.
ms.openlocfilehash: 62e254e324322aec55d692cfe3128e8e4dd60e4b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200736"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="d2829-103">Nuovi domini che vengono inoltrati Insight di posta elettronica nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="d2829-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d2829-104">Anche se è possibile che si disponga di motivi aziendali validi per inoltrare messaggi di posta elettronica a destinatari esterni in domini specifici, è sospetto quando gli utenti dell'organizzazione iniziano improvvisamente a inoltrare messaggi a domini esterni e nessuno nell'organizzazione ha mai inoltrato i messaggi a tali domini prima (nuovi domini).</span><span class="sxs-lookup"><span data-stu-id="d2829-104">Although you might have valid business reasons to forward email messages to external recipients in specific domains, it's suspicious when users in your organization suddenly start forwarding messages to external domains, and no one in the organization has ever forwarded messages to those domains before (new domains).</span></span> <span data-ttu-id="d2829-105">Questa condizione potrebbe indicare che gli account utente sono compromessi.</span><span class="sxs-lookup"><span data-stu-id="d2829-105">This condition could indicate the user accounts are compromised.</span></span> <span data-ttu-id="d2829-106">Se si sospetta che gli account siano stati compromessi, vedere [rispondere a un account di posta elettronica compromesso](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span><span class="sxs-lookup"><span data-stu-id="d2829-106">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="d2829-107">I **nuovi domini che vengono inoltrati tramite posta elettronica** nel [Centro sicurezza & Compliance](https://protection.office.com) notifica quando gli utenti dell'organizzazione stanno inoltrando i messaggi ai nuovi domini.</span><span class="sxs-lookup"><span data-stu-id="d2829-107">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="d2829-108">Questa intuizione viene visualizzata solo quando il problema viene rilevato e viene visualizzato nella pagina del [rapporto di inoltro](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="d2829-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Informazioni dettagliate sui messaggi di posta elettronica dei nuovi domini inoltrati](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="d2829-110">Quando si fa clic sul widget, viene visualizzato un riquadro a comparsa in cui è possibile trovare ulteriori dettagli sui messaggi inoltrati, incluso un collegamento al [rapporto di inoltro](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="d2829-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Riquadro a comparsa dettagli che viene visualizzato dopo aver fatto clic sui nuovi domini che vengono inoltrati Insight della posta elettronica](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="d2829-112">È inoltre possibile accedere a questa pagina dei dettagli quando si seleziona l'Insight dopo aver fatto clic su **Visualizza tutti** nell'area **suggerimenti & consigliati** (dashboard dei**report** \> **Dashboard** o <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="d2829-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="d2829-113">Per impedire l'inoltro automatico dei messaggi ai domini esterni, configurare un dominio remoto per alcuni o per tutti i domini esterni.</span><span class="sxs-lookup"><span data-stu-id="d2829-113">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="d2829-114">Per ulteriori informazioni, vedere [Manage Remote Domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span><span class="sxs-lookup"><span data-stu-id="d2829-114">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d2829-115">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d2829-115">Related topics</span></span>

<span data-ttu-id="d2829-116">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="d2829-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
