---
title: Correggere informazioni dettagliate sulle regole del flusso di posta lento
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su come utilizzare le & regole del flusso di posta indesiderata per identificare e correggere le regole del flusso di posta inefficienti o interrotte (note anche come regole di trasporto) nell'organizzazione.
ms.openlocfilehash: f51c5a577fc6d9c52e35a5217cae4ae94c546c9d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920549"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="9a760-103">Fix Slow Mail Flow Rules Insight nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="9a760-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9a760-104">Inefficienti regole del flusso di posta (note anche come regole di trasporto) possono causare ritardi del flusso di posta per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a760-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="9a760-105">Questo Insight segnala le regole del flusso di posta che hanno un impatto sul flusso di posta dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a760-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="9a760-106">Di seguito sono riportati alcuni esempi di questi tipi di regole:</span><span class="sxs-lookup"><span data-stu-id="9a760-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="9a760-107">Le condizioni che utilizzano **sono membri di** per gruppi di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9a760-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="9a760-108">Condizioni che utilizzano la corrispondenza del modello di espressione regolare (Regex) complessa.</span><span class="sxs-lookup"><span data-stu-id="9a760-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="9a760-109">Condizioni che utilizzano il controllo del contenuto negli allegati.</span><span class="sxs-lookup"><span data-stu-id="9a760-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="9a760-110">La **correzione delle regole del flusso di posta lenta** nell'area **consigliata per l'utente** del [Dashboard del flusso di posta elettronica](mail-flow-insights-v2.md) nel [Centro sicurezza & conformità](https://protection.office.com) informa quando una regola del flusso di posta richiede troppo tempo per essere completata.</span><span class="sxs-lookup"><span data-stu-id="9a760-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="9a760-111">Questa intuizione viene visualizzata solo dopo che è stata rilevata la condizione (se non si dispone di alcun loop di posta elettronica, non si vedrà l'Insight).</span><span class="sxs-lookup"><span data-stu-id="9a760-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="9a760-112">È possibile utilizzare questa notifica per identificare e ottimizzare le regole del flusso di posta per contribuire a ridurre i ritardi del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="9a760-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Fix Slow Mail Flow Rules Insight nelle aree consigliate per l'area del dashboard del flusso di posta](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="9a760-114">Quando si fa clic su **Visualizza dettagli** nel widget, viene visualizzato un riquadro a comparsa con ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="9a760-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="9a760-115">**Regola** : è possibile posizionare il puntatore del mouse sul riepilogo per visualizzare tutte le condizioni, le eccezioni e le azioni della regola.</span><span class="sxs-lookup"><span data-stu-id="9a760-115">**Rule** : You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="9a760-116">È possibile fare clic sul riepilogo per modificare la regola nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="9a760-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="9a760-117">**Numero di messaggi valutati** : è possibile fare clic su **Visualizza messaggi di esempio** per visualizzare i risultati di [traccia](message-trace-scc.md) dei messaggi per un esempio di messaggi che sono stati interessati dalla regola.</span><span class="sxs-lookup"><span data-stu-id="9a760-117">**Number of messages evaluated** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="9a760-118">**Tempo medio impiegato per ogni messaggio**</span><span class="sxs-lookup"><span data-stu-id="9a760-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="9a760-119">**Tempo mediano dedicato a un messaggio** : il valore medio che separa la metà superiore dalla metà inferiore dei dati temporali.</span><span class="sxs-lookup"><span data-stu-id="9a760-119">**Median time spent on a message** : The middle value that separates the upper half from the lower half of time data.</span></span>

![Riquadro a comparsa dettagli che viene visualizzato dopo aver fatto clic su Visualizza dettagli nell'Insight delle regole del flusso di posta lenta](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="9a760-121">Per ulteriori informazioni sulle condizioni e le eccezioni nelle regole del flusso di posta, vedere [Mail Flow Rule conditions and Exceptions (Predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="9a760-121">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="9a760-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a760-122">See also</span></span>

<span data-ttu-id="9a760-123">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="9a760-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
