---
title: Risolvere il possibile Insight del loop di posta elettronica
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su come utilizzare l'Insight del ciclo di posta elettronica Fix possible nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance per identificare e correggere i loop di posta nell'organizzazione.
ms.openlocfilehash: 54240cffc534b4be708492b37b827636edab280e
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577628"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="122ac-103">FIX possible Insight del loop di posta elettronica nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="122ac-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

<span data-ttu-id="122ac-104">Un loop di posta non è valido perché spreca risorse di sistema, consuma la quota del volume di posta dell'organizzazione e invia rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo) ai mittenti originali.</span><span class="sxs-lookup"><span data-stu-id="122ac-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span>

<span data-ttu-id="122ac-105">L'Insight del **ciclo di posta di Fix possibile** nell'area **consigliata per l'utente** del dashboard del flusso di [posta](mail-flow-insights-v2.md) nel centro sicurezza & Compliance notifica quando viene rilevato un loop di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="122ac-105">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail loop is detected in your organization.</span></span> <span data-ttu-id="122ac-106">Questa intuizione viene visualizzata solo dopo che è stata rilevata la condizione (se non si dispone di alcun loop di posta elettronica, non si vedrà l'Insight).</span><span class="sxs-lookup"><span data-stu-id="122ac-106">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Fix Slow Mail Flow Rules Insight nelle aree consigliate per l'area del dashboard del flusso di posta](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="122ac-108">Quando si fa clic su **Visualizza dettagli** nel widget, viene visualizzato un riquadro a comparsa con ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="122ac-108">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="122ac-109">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="122ac-109">**Domain**</span></span>
- <span data-ttu-id="122ac-110">**Numero di messaggi**: è possibile fare clic su **Visualizza messaggi di esempio** per visualizzare i risultati di [traccia](message-trace-scc.md) dei messaggi per un esempio di messaggi che sono stati interessati dal ciclo.</span><span class="sxs-lookup"><span data-stu-id="122ac-110">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="122ac-111">**Tipo di dominio**"ad esempio, autorevole o non autorevole.</span><span class="sxs-lookup"><span data-stu-id="122ac-111">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="122ac-112">**Record MX**: host (**mail server**) e valori di **priorità** del record MX per il dominio.</span><span class="sxs-lookup"><span data-stu-id="122ac-112">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="122ac-113">**Motivo ciclo** e **correzione**: si cercherà di identificare gli scenari più comuni del ciclo di posta elettronica e di fornire le azioni consigliate (se disponibili) per correggere il ciclo.</span><span class="sxs-lookup"><span data-stu-id="122ac-113">**Loop reason** and **How to fix**: We'll try to identify the most common mail loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![Riquadro a comparsa dettagli che viene visualizzato dopo aver fatto clic su Visualizza dettagli sull'Insight del ciclo di posta di Fix possible](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a><span data-ttu-id="122ac-115">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="122ac-115">Related topics</span></span>

<span data-ttu-id="122ac-116">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="122ac-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
