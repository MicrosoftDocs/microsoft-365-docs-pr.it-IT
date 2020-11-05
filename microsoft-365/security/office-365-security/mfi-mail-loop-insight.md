---
title: Correggere possibili informazioni dettagliate sul ciclo di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su come utilizzare l'Insight del ciclo di posta elettronica Fix possible nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance per identificare e correggere i loop di posta nell'organizzazione.
ms.openlocfilehash: 1d49fd93b2ea068986e003b36077672215a2dd57
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920567"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="493cd-103">FIX possible Insight del loop di posta elettronica nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="493cd-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="493cd-104">I loop di posta sono negativi perché:</span><span class="sxs-lookup"><span data-stu-id="493cd-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="493cd-105">Sprecano risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="493cd-105">They waste system resources.</span></span>
- <span data-ttu-id="493cd-106">Consumano la quota del volume di posta dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="493cd-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="493cd-107">Inviano rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo) ai mittenti dei messaggi originali.</span><span class="sxs-lookup"><span data-stu-id="493cd-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="493cd-108">L'Insight del **ciclo di posta di Fix possibile** nell'area **consigliata per l'utente** del dashboard del flusso di [posta](mail-flow-insights-v2.md) nel [Centro sicurezza & Compliance](https://protection.office.com) notifica quando viene rilevato un loop di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="493cd-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="493cd-109">Questa intuizione viene visualizzata solo dopo che è stata rilevata la condizione (se non si dispone di alcun loop di posta elettronica, non si vedrà l'Insight).</span><span class="sxs-lookup"><span data-stu-id="493cd-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Fix Slow Mail Flow Rules Insight nelle aree consigliate per l'area del dashboard del flusso di posta](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="493cd-111">Quando si fa clic su **Visualizza dettagli** nel widget, viene visualizzato un riquadro a comparsa con ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="493cd-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="493cd-112">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="493cd-112">**Domain**</span></span>
- <span data-ttu-id="493cd-113">**Numero di messaggi** : è possibile fare clic su **Visualizza messaggi di esempio** per visualizzare i risultati di [traccia](message-trace-scc.md) dei messaggi per un esempio di messaggi che sono stati interessati dal ciclo.</span><span class="sxs-lookup"><span data-stu-id="493cd-113">**Number of messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="493cd-114">**Tipo di dominio** "ad esempio, autorevole o non autorevole.</span><span class="sxs-lookup"><span data-stu-id="493cd-114">**Domain type** " For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="493cd-115">**Record MX** : host ( **mail server** ) e valori di **priorità** del record MX per il dominio.</span><span class="sxs-lookup"><span data-stu-id="493cd-115">**MX record** : The host ( **Mail server** ) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="493cd-116">**Motivo ciclo** e **correzione** : verranno identificati gli scenari più comuni del ciclo di posta elettronica e vengono fornite azioni consigliate per correggere il ciclo.</span><span class="sxs-lookup"><span data-stu-id="493cd-116">**Loop reason** and **How to fix** : We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Riquadro a comparsa dettagli che viene visualizzato dopo aver fatto clic su Visualizza dettagli sull'Insight del ciclo di posta di Fix possible](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="493cd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="493cd-118">See also</span></span>

<span data-ttu-id="493cd-119">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="493cd-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
