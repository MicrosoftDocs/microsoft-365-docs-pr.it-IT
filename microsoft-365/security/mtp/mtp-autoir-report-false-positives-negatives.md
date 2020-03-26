---
title: Gestire falsi positivi o falsi negativi in aria in Microsoft Threat Protection
description: Si è verificato un errore o rilevato erroneamente da AIR in Microsoft Threat Protection? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
keywords: automatizzato, indagine, avviso, trigger, azione, correzione, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 90651aa258adb9f7fe46f99bcadf1d4d552a5b76
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955662"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="7aa0e-105">Gestire i falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="7aa0e-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="7aa0e-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7aa0e-106">**Applies to:**</span></span>
- <span data-ttu-id="7aa0e-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7aa0e-107">Microsoft Threat Protection</span></span>

<span data-ttu-id="7aa0e-108">[Le funzionalità di ricerca e risposta automatizzate](mtp-autoir.md) in Microsoft Threat Protection non hanno o rilevato erroneamente qualcosa?</span><span class="sxs-lookup"><span data-stu-id="7aa0e-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="7aa0e-109">Per risolvere il problema, è possibile eseguire la procedura.</span><span class="sxs-lookup"><span data-stu-id="7aa0e-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="7aa0e-110">È possibile:</span><span class="sxs-lookup"><span data-stu-id="7aa0e-110">You can:</span></span>

- <span data-ttu-id="7aa0e-111">[Segnala un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="7aa0e-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="7aa0e-112">[Modificare gli avvisi](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessario); e</span><span class="sxs-lookup"><span data-stu-id="7aa0e-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="7aa0e-113">[Annullare le azioni di correzione eseguite nei dispositivi](#undo-a-remediation-action-that-was-taken-on-a-device).</span><span class="sxs-lookup"><span data-stu-id="7aa0e-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="7aa0e-114">Utilizzare questo articolo come guida.</span><span class="sxs-lookup"><span data-stu-id="7aa0e-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="7aa0e-115">Segnalare un falso positivo/negativo a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="7aa0e-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="7aa0e-116">Elemento mancante o rilevato erroneamente</span><span class="sxs-lookup"><span data-stu-id="7aa0e-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="7aa0e-117">Servizio</span><span class="sxs-lookup"><span data-stu-id="7aa0e-117">Service</span></span>  |<span data-ttu-id="7aa0e-118">Procedura</span><span class="sxs-lookup"><span data-stu-id="7aa0e-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7aa0e-119">-Messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7aa0e-119">- Email message</span></span> <br/><span data-ttu-id="7aa0e-120">-Allegato di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7aa0e-120">- Email attachment</span></span> <br/><span data-ttu-id="7aa0e-121">-URL in un messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7aa0e-121">- URL in an email message</span></span><br/><span data-ttu-id="7aa0e-122">-URL in un file di Office</span><span class="sxs-lookup"><span data-stu-id="7aa0e-122">- URL in an Office file</span></span>      |[<span data-ttu-id="7aa0e-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7aa0e-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="7aa0e-124">Inviare messaggi di posta indesiderata sospetti, phishing, URL e file a Microsoft per l'analisi di Office 365</span><span class="sxs-lookup"><span data-stu-id="7aa0e-124">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="7aa0e-125">File o app in un dispositivo</span><span class="sxs-lookup"><span data-stu-id="7aa0e-125">File or app on a device</span></span>    |[<span data-ttu-id="7aa0e-126">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7aa0e-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="7aa0e-127">Inviare un file a Microsoft per l'analisi antimalware</span><span class="sxs-lookup"><span data-stu-id="7aa0e-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="7aa0e-128">Modificare un avviso per evitare che i falsi positivi vengano ricorrenti</span><span class="sxs-lookup"><span data-stu-id="7aa0e-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="7aa0e-129">Scenario</span><span class="sxs-lookup"><span data-stu-id="7aa0e-129">Scenario</span></span> |<span data-ttu-id="7aa0e-130">Servizio</span><span class="sxs-lookup"><span data-stu-id="7aa0e-130">Service</span></span> |<span data-ttu-id="7aa0e-131">Procedura</span><span class="sxs-lookup"><span data-stu-id="7aa0e-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="7aa0e-132">-Un avviso viene attivato da un utilizzo legittimo</span><span class="sxs-lookup"><span data-stu-id="7aa0e-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="7aa0e-133">-Un avviso non è accurato</span><span class="sxs-lookup"><span data-stu-id="7aa0e-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="7aa0e-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7aa0e-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="7aa0e-135">oppure</span><span class="sxs-lookup"><span data-stu-id="7aa0e-135">or</span></span> <br/>[<span data-ttu-id="7aa0e-136">Rilevamento delle minacce avanzato di Azure</span><span class="sxs-lookup"><span data-stu-id="7aa0e-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="7aa0e-137">Gestire gli avvisi nel cloud app Security Portal</span><span class="sxs-lookup"><span data-stu-id="7aa0e-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="7aa0e-138">Un file, un indirizzo IP, un URL o un dominio viene considerato come malware su un dispositivo, anche se è sicuro</span><span class="sxs-lookup"><span data-stu-id="7aa0e-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="7aa0e-139">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7aa0e-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="7aa0e-140">Creare un indicatore personalizzato con un'azione "Consenti"</span><span class="sxs-lookup"><span data-stu-id="7aa0e-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="7aa0e-141">Annullare un'azione di correzione eseguita su un dispositivo</span><span class="sxs-lookup"><span data-stu-id="7aa0e-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="7aa0e-142">Se è stata eseguita un'azione di correzione su un dispositivo, ad esempio un dispositivo Windows 10, e l'elemento non è effettivamente una minaccia, il team delle operazioni di sicurezza può annullare l'azione di correzione nell' [Action Center](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="7aa0e-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7aa0e-143">Verificare di disporre delle [autorizzazioni necessarie](mtp-action-center.md#required-permissions-for-action-center-tasks) prima di tentare di eseguire l'attività seguente.</span><span class="sxs-lookup"><span data-stu-id="7aa0e-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="7aa0e-144">Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7aa0e-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="7aa0e-145">Nel riquadro di spostamento, scegliere **Centro notifiche**.</span><span class="sxs-lookup"><span data-stu-id="7aa0e-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="7aa0e-146">Nella scheda **cronologia** selezionare un'azione che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="7aa0e-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="7aa0e-147">Verrà aperto un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="7aa0e-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="7aa0e-148">Utilizzare i filtri per limitare l'elenco dei risultati.</span><span class="sxs-lookup"><span data-stu-id="7aa0e-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="7aa0e-149">Nel riquadro a comparsa per l'elemento selezionato, selezionare **Apri pagina di analisi**.</span><span class="sxs-lookup"><span data-stu-id="7aa0e-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="7aa0e-150">Nella visualizzazione dettagli analisi selezionare la scheda **azioni** .</span><span class="sxs-lookup"><span data-stu-id="7aa0e-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="7aa0e-151">Selezionare un elemento con stato **completato**e cercare un collegamento, ad esempio **approvato**, nella colonna **decisioni** .</span><span class="sxs-lookup"><span data-stu-id="7aa0e-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="7aa0e-152">Verrà aperto un riquadro a comparsa con maggiori dettagli sull'azione.</span><span class="sxs-lookup"><span data-stu-id="7aa0e-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="7aa0e-153">Per annullare l'azione, selezionare **Elimina correzione**.</span><span class="sxs-lookup"><span data-stu-id="7aa0e-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7aa0e-154">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="7aa0e-154">Related articles</span></span>

- [<span data-ttu-id="7aa0e-155">Approvare o rifiutare le azioni relative all'indagine e reazione automatizzate</span><span class="sxs-lookup"><span data-stu-id="7aa0e-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

- [<span data-ttu-id="7aa0e-156">Altre informazioni sul centro notifiche</span><span class="sxs-lookup"><span data-stu-id="7aa0e-156">Learn more about the Action center</span></span>](mtp-action-center.md)

- [<span data-ttu-id="7aa0e-157">Cercare in modo proattivo minacce con la ricerca avanzata di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7aa0e-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
