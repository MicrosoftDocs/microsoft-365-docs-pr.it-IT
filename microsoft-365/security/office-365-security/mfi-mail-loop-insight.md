---
title: Correggere possibili informazioni dettagliate sul ciclo di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare le informazioni sulla correzione dei possibili loop di posta nel dashboard del flusso di posta nel Centro sicurezza & conformità per identificare e correggere i loop di posta nell'organizzazione.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206343"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="61565-103">Risolvere le possibili informazioni dettagliate sul ciclo di posta nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="61565-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="61565-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="61565-104">**Applies to**</span></span>
- [<span data-ttu-id="61565-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="61565-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="61565-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="61565-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="61565-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61565-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="61565-108">I cicli di posta non sono erri perché:</span><span class="sxs-lookup"><span data-stu-id="61565-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="61565-109">Sprecano risorse di sistema.</span><span class="sxs-lookup"><span data-stu-id="61565-109">They waste system resources.</span></span>
- <span data-ttu-id="61565-110">Utilizzano la quota del volume di posta dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="61565-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="61565-111">Inviano rapporti di mancato recapito confusi (noti anche come rapporti di mancato recapito o messaggi di mancato recapito) ai mittenti dei messaggi originali.</span><span class="sxs-lookup"><span data-stu-id="61565-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="61565-112">**L'analisi fix possible mail loop** nell'area Recommended for **you** del [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità notifica quando viene rilevato un ciclo di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="61565-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="61565-113">Questa analisi viene visualizzata solo dopo che la condizione è stata rilevata (se non sono presenti loop di posta, non verranno visualizzate le informazioni dettagliate).</span><span class="sxs-lookup"><span data-stu-id="61565-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Correggere le informazioni dettagliate sulle regole del flusso di posta lento nell'area Consigliato per l'utente del dashboard del flusso di posta](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="61565-115">Quando si fa **clic su Visualizza dettagli** nel widget, viene visualizzato un riquadro a comparsa con ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="61565-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="61565-116">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="61565-116">**Domain**</span></span>
- <span data-ttu-id="61565-117">**Numero di messaggi**: è possibile **fare** clic su Visualizza messaggi di esempio per visualizzare i risultati della traccia dei messaggi per un esempio dei messaggi interessati dal ciclo. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="61565-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="61565-118">**Tipo di** dominio " Ad esempio Autorevole o Non autorevole.</span><span class="sxs-lookup"><span data-stu-id="61565-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="61565-119">**Record MX**: l'host (**Server** di posta ) e i valori **priority** del record MX per il dominio.</span><span class="sxs-lookup"><span data-stu-id="61565-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="61565-120">**Motivo del** ciclo **e Come risolvere**: identificheremo gli scenari di ciclo di posta più comuni e forniremo le azioni consigliate per correggere il ciclo.</span><span class="sxs-lookup"><span data-stu-id="61565-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Riquadro a comparsa Dettagli visualizzato dopo aver fatto clic su Visualizza dettagli nella finestra di dialogo Correggi possibile informazioni dettagliate sul ciclo di posta](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="61565-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61565-122">See also</span></span>

<span data-ttu-id="61565-123">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="61565-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
