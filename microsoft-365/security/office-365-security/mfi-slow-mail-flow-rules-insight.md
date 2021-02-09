---
title: Correggere informazioni dettagliate sulle regole del flusso di posta lento
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare le informazioni dettagliate sulle regole del flusso di posta lente nel Centro sicurezza & conformità per identificare e correggere regole del flusso di posta inefficienti o interrotte (note anche come regole di trasporto) nell'organizzazione.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7f084735decda922b5bcc57c029f2b384114d30
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150785"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="197b1-103">Correggere le informazioni dettagliate sulle regole del flusso di posta lente nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="197b1-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="197b1-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="197b1-104">**Applies to**</span></span>
- [<span data-ttu-id="197b1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="197b1-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="197b1-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="197b1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="197b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="197b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="197b1-108">Le regole del flusso di posta inefficienti (note anche come regole di trasporto) possono causare ritardi nel flusso di posta per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="197b1-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="197b1-109">Queste informazioni dettagliate segnalano le regole del flusso di posta che hanno un impatto sul flusso di posta dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="197b1-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="197b1-110">Di seguito sono riportati alcuni esempi di questi tipi di regole:</span><span class="sxs-lookup"><span data-stu-id="197b1-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="197b1-111">Condizioni che utilizzano **Is member of** per gruppi di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="197b1-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="197b1-112">Condizioni che utilizzano la corrispondenza di criteri di espressione regolare complessa (regex).</span><span class="sxs-lookup"><span data-stu-id="197b1-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="197b1-113">Condizioni che utilizzano l'archiviazione del contenuto negli allegati.</span><span class="sxs-lookup"><span data-stu-id="197b1-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="197b1-114">**L'analisi** delle regole del flusso di posta lento nell'area  Consigliata per l'utente del [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità notifica quando il completamento di una regola del flusso di posta sta prendendo troppo tempo.</span><span class="sxs-lookup"><span data-stu-id="197b1-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="197b1-115">Queste informazioni vengono visualizzate solo dopo che la condizione è stata rilevata (se non sono presenti loop di posta, non verranno visualizzate le informazioni dettagliate).</span><span class="sxs-lookup"><span data-stu-id="197b1-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="197b1-116">È possibile utilizzare questa notifica per identificare e ottimizzare le regole del flusso di posta per ridurre i ritardi del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="197b1-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Correggere le informazioni dettagliate sulle regole del flusso di posta lente nell'area Consigliata per l'utente del dashboard del flusso di posta](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="197b1-118">Quando si fa **clic su Visualizza** dettagli nel widget, viene visualizzato un riquadro a comparsa con ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="197b1-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="197b1-119">**Regola:** è possibile passare il puntatore del mouse sul riepilogo per visualizzare tutte le condizioni, le eccezioni e le azioni della regola.</span><span class="sxs-lookup"><span data-stu-id="197b1-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="197b1-120">È possibile fare clic sul riepilogo per modificare la regola nell'interfaccia di amministrazione di Exchange ( EAC).</span><span class="sxs-lookup"><span data-stu-id="197b1-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="197b1-121">**Numero di messaggi valutati:** è possibile [](message-trace-scc.md) fare clic su Visualizza messaggi di esempio per visualizzare i risultati della traccia dei messaggi per un campione dei messaggi interessati dalla regola. </span><span class="sxs-lookup"><span data-stu-id="197b1-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="197b1-122">**Tempo medio dedicato a ogni messaggio**</span><span class="sxs-lookup"><span data-stu-id="197b1-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="197b1-123">**Tempo mediano dedicato a un messaggio:** valore intermedio che separa la metà superiore dai dati della metà inferiore del tempo.</span><span class="sxs-lookup"><span data-stu-id="197b1-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Riquadro a comparsa Dettagli che viene visualizzato dopo aver fatto clic su Visualizza dettagli nel riquadro a comparsa Correggi informazioni dettagliate sulle regole del flusso di posta lento](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="197b1-125">Per ulteriori informazioni sulle condizioni e le eccezioni nelle regole del flusso di posta, vedere Condizioni ed eccezioni delle regole del flusso di posta [(predicati) in Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="197b1-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="197b1-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="197b1-126">See also</span></span>

<span data-ttu-id="197b1-127">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="197b1-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
