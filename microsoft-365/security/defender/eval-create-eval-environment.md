---
title: Creare l'Microsoft 365 Defender di valutazione. Attivare o abilitare le licenze di valutazione e passare a Microsoft Defender for Identity (MDI).
description: Configurare il laboratorio di Microsoft 365 Defender o l'ambiente pilota attivando le licenze di valutazione. Configura quindi Microsoft Defender for Identity (MDI) e tutte le altre valutazioni M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 04f7a746788ebcf67525020515cdc7bb20c41bb6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458268"
---
# <a name="create-the-microsoft-365-defender-evaluation-environment"></a><span data-ttu-id="2a167-105">Creare l'Microsoft 365 Defender di valutazione</span><span class="sxs-lookup"><span data-stu-id="2a167-105">Create the Microsoft 365 Defender Evaluation Environment</span></span>

<span data-ttu-id="2a167-106">Esistono due modi comuni per eseguire questo passaggio successivo nella valutazione.</span><span class="sxs-lookup"><span data-stu-id="2a167-106">There are two common ways to do this next step in evaluation.</span></span> <span data-ttu-id="2a167-107">Questo documento presuppone che tu abbia già un tenant M365 di produzione e attiverà le licenze di valutazione E5 per valutare M365 Defender *nell'ambiente corrente.*</span><span class="sxs-lookup"><span data-stu-id="2a167-107">This document assumes you already have a production M365 tenant, and will activate E5 trial licenses to evaluate M365 Defender in *the current environment*.</span></span> <span data-ttu-id="2a167-108">Una valutazione sul posto consente di mantenere tutti i metodi di sicurezza con l'acquisto di licenze dopo il periodo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="2a167-108">An in-place evaluation will let you keep any security methods with the purchase of licenses after the evaluation period.</span></span>

<span data-ttu-id="2a167-109">Il secondo è configurare [l'ambiente Microsoft 365 Defender lab](setup-m365deval.md) di valutazione ai fini della valutazione.</span><span class="sxs-lookup"><span data-stu-id="2a167-109">The second is to  [Set up your Microsoft 365 Defender trial lab environment](setup-m365deval.md) for the purpose of evaluation.</span></span> <span data-ttu-id="2a167-110">Potrebbe non avere molti segnali reali dall'azienda, quindi tenere presente tale avvertenza.</span><span class="sxs-lookup"><span data-stu-id="2a167-110">It may not have many real signals from the business, so be aware of that caveat.</span></span>

## <a name="to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a><span data-ttu-id="2a167-111">Per attivare le licenze di valutazione di E5 per valutare Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a167-111">To activate E5 trial licenses to evaluate Microsoft 365 Defender</span></span> 
1. <span data-ttu-id="2a167-112">Accedere al portale di amministrazione tenant M365 esistente.</span><span class="sxs-lookup"><span data-stu-id="2a167-112">Log on to your existing M365 tenant administration portal.</span></span>
2. <span data-ttu-id="2a167-113">Seleziona *Acquista servizi* dal menu di spostamento.</span><span class="sxs-lookup"><span data-stu-id="2a167-113">Select *Purchase Services* from the navigation menu.</span></span>
3. <span data-ttu-id="2a167-114">Scorri verso il basso *fino alla Office 365* e seleziona il pulsante "Dettagli" sotto Office 365 E5 licenza.</span><span class="sxs-lookup"><span data-stu-id="2a167-114">Scroll down to the *Office 365* section and select "Details" button under Office 365 E5 license.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="La Office 365 contiene un pulsante Dettagli su cui fare clic.":::

4. <span data-ttu-id="2a167-116">Seleziona *Avvia il collegamento per la versione di valutazione* gratuita.</span><span class="sxs-lookup"><span data-stu-id="2a167-116">Select *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Fai clic su &quot;Avvia versione di valutazione gratuita&quot; (è disponibile una tariffa di 35$).":::

5. <span data-ttu-id="2a167-118">Conferma la richiesta e fai clic *sul pulsante Prova.*</span><span class="sxs-lookup"><span data-stu-id="2a167-118">Confirm your request and click *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="C'è un pulsante &quot;Prova ora&quot; nel pannello &quot;Estrai, conferma l'ordine&quot; (per una versione di valutazione di Office 365 E5 di un mese per 25 utenti).":::

## <a name="next-steps"></a><span data-ttu-id="2a167-120">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2a167-120">Next steps</span></span>
[<span data-ttu-id="2a167-121">Abilitare Microsoft 365 per l'identità</span><span class="sxs-lookup"><span data-stu-id="2a167-121">Enable Microsoft 365 for Identity</span></span>](eval-defender-identity-overview.md)

<span data-ttu-id="2a167-122">Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2a167-122">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>