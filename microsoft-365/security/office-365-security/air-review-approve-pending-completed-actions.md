---
title: Esaminare e gestire le azioni di correzione in Microsoft Defender per Office 365
keywords: AIR, autoIR, ATP, automatizzato, indagine, risposta, correzione, minacce, avanzate, minacce, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Informazioni sulle azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 61e9df45419cc73dae27b86dad47e1938183593d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205145"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="f6714-104">Esaminare e gestire le azioni di correzione in Office 365</span><span class="sxs-lookup"><span data-stu-id="f6714-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="f6714-105">Poiché le indagini automatizzate sulla posta elettronica & contenuto di  collaborazione comportano verdetti, ad esempio dannosi o *sospetti,* vengono create determinate azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="f6714-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="f6714-106">In Microsoft Defender per Office 365, le azioni di correzione possono includere:</span><span class="sxs-lookup"><span data-stu-id="f6714-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="f6714-107">Blocco di un URL (ora del clic)</span><span class="sxs-lookup"><span data-stu-id="f6714-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="f6714-108">Eliminazione recisa dei messaggi di posta elettronica o dei cluster</span><span class="sxs-lookup"><span data-stu-id="f6714-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="f6714-109">Quaranta allegati di posta elettronica o di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="f6714-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="f6714-110">Disattivazione dell'inoltro della posta esterna</span><span class="sxs-lookup"><span data-stu-id="f6714-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="f6714-111">Queste azioni di correzione non vengono eseguite a meno che il team delle operazioni di sicurezza non le approvi.</span><span class="sxs-lookup"><span data-stu-id="f6714-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="f6714-112">È consigliabile rivedere e approvare tutte le azioni in sospeso il prima possibile, in modo che le indagini automatizzate si completino in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="f6714-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="f6714-113">In alcuni casi, è possibile annullare un'azione di correzione.</span><span class="sxs-lookup"><span data-stu-id="f6714-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="f6714-114">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="f6714-114">**Applies to**</span></span>
- [<span data-ttu-id="f6714-115">Microsoft Defender per Office 365 Piano 2</span><span class="sxs-lookup"><span data-stu-id="f6714-115">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f6714-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6714-116">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="f6714-117">Approvare (o rifiutare) le azioni in sospeso</span><span class="sxs-lookup"><span data-stu-id="f6714-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="f6714-118">Accedere al Centro sicurezza Microsoft 365 ( <https://security.microsoft.com> ) e accedere.</span><span class="sxs-lookup"><span data-stu-id="f6714-118">Go to the Microsoft 365 security center (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="f6714-119">Nel riquadro di spostamento selezionare **Centro notifiche.**</span><span class="sxs-lookup"><span data-stu-id="f6714-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="f6714-120">Nella scheda **In** sospeso esaminare l'elenco delle azioni in attesa di approvazione.</span><span class="sxs-lookup"><span data-stu-id="f6714-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="f6714-121">Selezionare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f6714-121">Select an item in the list.</span></span> <span data-ttu-id="f6714-122">Verrà visualizzato il riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="f6714-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="f6714-123">Esaminare le informazioni nel riquadro a comparsa e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6714-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="f6714-124">Selezionare **Apri pagina di indagine** per visualizzare ulteriori dettagli sull'indagine.</span><span class="sxs-lookup"><span data-stu-id="f6714-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="f6714-125">Selezionare **Approva** per avviare un'azione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="f6714-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="f6714-126">Selezionare **Rifiuta** per impedire l'esecuzione di un'azione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="f6714-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="f6714-127">Annullare un'azione di correzione</span><span class="sxs-lookup"><span data-stu-id="f6714-127">Undo one remediation action</span></span>

1. <span data-ttu-id="f6714-128">Vai al centro notifiche ( <https://security.microsoft.com/action-center> ) e accedi.</span><span class="sxs-lookup"><span data-stu-id="f6714-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="f6714-129">Nella scheda **Cronologia** selezionare un'azione che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="f6714-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="f6714-130">Nel riquadro sul lato destro dello schermo selezionare **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="f6714-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="f6714-131">Annullare più azioni di correzione</span><span class="sxs-lookup"><span data-stu-id="f6714-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="f6714-132">Vai al centro notifiche ( <https://security.microsoft.com/action-center> ) e accedi.</span><span class="sxs-lookup"><span data-stu-id="f6714-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="f6714-133">Nella scheda **Cronologia** selezionare le azioni che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="f6714-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="f6714-134">Assicurarsi di selezionare gli elementi con lo stesso tipo di azione.</span><span class="sxs-lookup"><span data-stu-id="f6714-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="f6714-135">Verrà visualizzato un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="f6714-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="f6714-136">Nel riquadro a comparsa selezionare Annulla.</span><span class="sxs-lookup"><span data-stu-id="f6714-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="f6714-137">Per rimuovere un file dalla quarantena su più dispositivi</span><span class="sxs-lookup"><span data-stu-id="f6714-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="f6714-138">Vai al centro notifiche ( <https://security.microsoft.com/action-center> ) e accedi.</span><span class="sxs-lookup"><span data-stu-id="f6714-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="f6714-139">Nella scheda **Cronologia** selezionare un file con il tipo di azione **File quarantena.**</span><span class="sxs-lookup"><span data-stu-id="f6714-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="f6714-140">Nel riquadro sul lato destro dello schermo, selezionare Applica a X altre istanze **del file** e quindi scegliere **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="f6714-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6714-141">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f6714-141">Next steps</span></span>

- [<span data-ttu-id="f6714-142">Usare Esplora minacce</span><span class="sxs-lookup"><span data-stu-id="f6714-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="f6714-143">Come segnalare falsi positivi/negativi nelle funzionalità di indagine e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="f6714-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="f6714-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6714-144">See also</span></span>

- [<span data-ttu-id="f6714-145">Visualizzare i dettagli e i risultati di un'indagine automatizzata in Office 365</span><span class="sxs-lookup"><span data-stu-id="f6714-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
