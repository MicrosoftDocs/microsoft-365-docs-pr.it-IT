---
title: Come segnalare falsi positivi o falsi negativi dopo un'indagine automatizzata in Microsoft Defender per Office 365
description: È stato rilevato qualcosa di sbagliato o mancato da AIR in Microsoft Defender per Office 365? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
keywords: automatizzato, indagine, avviso, trigger, azione, correzione, falso positivo, falso negativo
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 036ef1c97788f310c5b906ae5f80076ca2359cdb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275085"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="a4f58-105">Come segnalare falsi positivi/negativi nelle funzionalità di indagine e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="a4f58-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a4f58-106">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="a4f58-106">**Applies to**</span></span>
- [<span data-ttu-id="a4f58-107">Microsoft Defender per Office 365 Piano 2</span><span class="sxs-lookup"><span data-stu-id="a4f58-107">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a4f58-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4f58-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a4f58-109">Se le funzionalità di analisi e risposta [automatizzate (AIR) Office 365](automated-investigation-response-office.md) hanno perso o rilevato in modo errato qualcosa, il team delle operazioni di sicurezza può eseguire alcune operazioni per risolverlo.</span><span class="sxs-lookup"><span data-stu-id="a4f58-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="a4f58-110">Tali azioni includono:</span><span class="sxs-lookup"><span data-stu-id="a4f58-110">Such actions include:</span></span>

- <span data-ttu-id="a4f58-111">[Segnalazione di un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="a4f58-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="a4f58-112">[Regolazione degli avvisi](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessario); e</span><span class="sxs-lookup"><span data-stu-id="a4f58-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="a4f58-113">[Annullamento delle azioni di correzione eseguite](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="a4f58-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="a4f58-114">Usa questo articolo come guida.</span><span class="sxs-lookup"><span data-stu-id="a4f58-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="a4f58-115">Segnalare un falso positivo/negativo a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="a4f58-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="a4f58-116">Se AIR in Microsoft Defender per Office 365 ha perso un messaggio di posta elettronica, un allegato di posta elettronica, un URL in un messaggio di posta elettronica o un URL in un file Office, è possibile inviare a Microsoft la posta indesiderata, il [phish,](admin-submission.md)gli URL e i file sospetti per l'analisi di Office 365 .</span><span class="sxs-lookup"><span data-stu-id="a4f58-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="a4f58-117">È inoltre possibile [inviare un file a Microsoft per l'analisi del malware.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="a4f58-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="a4f58-118">Modificare un avviso per evitare che i falsi positivi si ricorrenti</span><span class="sxs-lookup"><span data-stu-id="a4f58-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="a4f58-119">Se un avviso viene attivato da un uso legittimo o l'avviso non è accurato, è possibile gestire gli avvisi nel portale [di Cloud App Security.](/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="a4f58-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="a4f58-120">Se l'organizzazione usa [Microsoft Defender per Endpoint](/windows/security/threat-protection) oltre a Office 365 e un file, un indirizzo IP, un URL o un dominio viene considerato come malware in un dispositivo, anche se è sicuro, puoi creare un indicatore personalizzato con un'azione ["Consenti"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a4f58-120">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="a4f58-121">Annullare un'azione di correzione</span><span class="sxs-lookup"><span data-stu-id="a4f58-121">Undo a remediation action</span></span>

<span data-ttu-id="a4f58-122">Nella maggior parte dei casi, se è stata eseguita un'azione di correzione su un messaggio di posta elettronica, un allegato di posta elettronica o un URL e l'elemento non è in realtà una minaccia, il team delle operazioni di sicurezza può annullare l'azione di correzione e adottare misure per evitare che il falso positivo si ripeta.</span><span class="sxs-lookup"><span data-stu-id="a4f58-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="a4f58-123">Puoi usare Esplora minacce [o](#undo-an-action-using-threat-explorer) la scheda [Azioni per un'indagine](#undo-an-action-in-the-action-center) per annullare un'azione.</span><span class="sxs-lookup"><span data-stu-id="a4f58-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4f58-124">Assicurarsi di disporre delle autorizzazioni necessarie prima di tentare di eseguire le attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="a4f58-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="a4f58-125">Annullare un'azione con Esplora minacce</span><span class="sxs-lookup"><span data-stu-id="a4f58-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="a4f58-126">Con Threat Explorer, il team delle operazioni di sicurezza può trovare un messaggio di posta elettronica interessato da un'azione e potenzialmente annullare l'azione.</span><span class="sxs-lookup"><span data-stu-id="a4f58-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="a4f58-127">Scenario</span><span class="sxs-lookup"><span data-stu-id="a4f58-127">Scenario</span></span>|<span data-ttu-id="a4f58-128">Opzioni annulla</span><span class="sxs-lookup"><span data-stu-id="a4f58-128">Undo Options</span></span>|<span data-ttu-id="a4f58-129">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="a4f58-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="a4f58-130">Un messaggio di posta elettronica è stato instradato alla cartella Posta indesiderata di un utente</span><span class="sxs-lookup"><span data-stu-id="a4f58-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="a4f58-131">- Spostare il messaggio nella cartella Posta eliminata dell'utente</span><span class="sxs-lookup"><span data-stu-id="a4f58-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="a4f58-132">- Spostare il messaggio nella cartella Posta in arrivo dell'utente</span><span class="sxs-lookup"><span data-stu-id="a4f58-132">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="a4f58-133">- Eliminare il messaggio</span><span class="sxs-lookup"><span data-stu-id="a4f58-133">- Delete the message</span></span>|[<span data-ttu-id="a4f58-134">Individuare e analizzare i messaggi di posta elettronica dannosi recapitati in Office 365</span><span class="sxs-lookup"><span data-stu-id="a4f58-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="a4f58-135">Un messaggio di posta elettronica o un file è stato messo in quarantena</span><span class="sxs-lookup"><span data-stu-id="a4f58-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="a4f58-136">- Rilasciare il messaggio di posta elettronica o il file</span><span class="sxs-lookup"><span data-stu-id="a4f58-136">- Release the email or file</span></span><br/><span data-ttu-id="a4f58-137">- Eliminare il messaggio di posta elettronica o il file</span><span class="sxs-lookup"><span data-stu-id="a4f58-137">- Delete the email or file</span></span>|[<span data-ttu-id="a4f58-138">Gestire i messaggi in quarantena come amministratore</span><span class="sxs-lookup"><span data-stu-id="a4f58-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="a4f58-139">Annullare un'azione nel centro notifiche</span><span class="sxs-lookup"><span data-stu-id="a4f58-139">Undo an action in the Action center</span></span>

<span data-ttu-id="a4f58-140">Nel centro notifiche è possibile visualizzare le azioni di correzione eseguite e potenzialmente annullare l'azione.</span><span class="sxs-lookup"><span data-stu-id="a4f58-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="a4f58-141">Accedere al centro Microsoft 365 sicurezza ( <https://security.microsoft.com> ).</span><span class="sxs-lookup"><span data-stu-id="a4f58-141">Go to the Microsoft 365 security center (<https://security.microsoft.com>).</span></span>
2. <span data-ttu-id="a4f58-142">Nel riquadro di spostamento selezionare **Centro notifiche.**</span><span class="sxs-lookup"><span data-stu-id="a4f58-142">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="a4f58-143">Selezionare la **scheda Cronologia** per visualizzare l'elenco delle azioni completate.</span><span class="sxs-lookup"><span data-stu-id="a4f58-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="a4f58-144">Selezionare un elemento.</span><span class="sxs-lookup"><span data-stu-id="a4f58-144">Select an item.</span></span> <span data-ttu-id="a4f58-145">Verrà visualizzato il riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="a4f58-145">Its flyout pane opens.</span></span>
5. <span data-ttu-id="a4f58-146">Nel riquadro a comparsa selezionare **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="a4f58-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="a4f58-147">Solo le azioni che possono essere annullate avranno un **pulsante** Annulla.</span><span class="sxs-lookup"><span data-stu-id="a4f58-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="a4f58-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4f58-148">See also</span></span>

- [<span data-ttu-id="a4f58-149">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="a4f58-149">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a4f58-150">Indagini automatizzate in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="a4f58-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
