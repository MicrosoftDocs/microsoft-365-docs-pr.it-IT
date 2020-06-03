---
title: Come segnalare falsi positivi o falsi negativi nell'analisi e nella risposta automatizzata di Office 365
description: Si è verificato un errore o rilevato erroneamente da Office 365 Advanced Threat Protection? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 837232550ca392a364b9842f64a1c3f0d790a502
ms.sourcegitcommit: 33be6075fcc89d4c0a48fa7e59f3b3ebc605d9f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "44520159"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="7dd6b-105">Come segnalare falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="7dd6b-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="7dd6b-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7dd6b-106">**Applies to:**</span></span>
- <span data-ttu-id="7dd6b-107">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7dd6b-107">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="7dd6b-108">[Le funzionalità di analisi e risposta automatizzate in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) non hanno o rilevato erroneamente qualcosa?</span><span class="sxs-lookup"><span data-stu-id="7dd6b-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="7dd6b-109">Per risolvere il problema, è possibile eseguire la procedura.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="7dd6b-110">È possibile:</span><span class="sxs-lookup"><span data-stu-id="7dd6b-110">You can:</span></span>
- <span data-ttu-id="7dd6b-111">[Segnala un falso positivo/negativo a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="7dd6b-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="7dd6b-112">[Modificare gli avvisi](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessario); e</span><span class="sxs-lookup"><span data-stu-id="7dd6b-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="7dd6b-113">[Annullare le azioni di correzione eseguite](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="7dd6b-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="7dd6b-114">Utilizzare questo articolo come guida.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="7dd6b-115">Segnalare un falso positivo/negativo a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="7dd6b-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="7dd6b-116">Se Office 365 AIR ha perso un messaggio di posta elettronica, un allegato di posta elettronica, un URL in un messaggio di posta elettronica o un URL in un file di Office, è possibile [inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft per l'analisi di office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span><span class="sxs-lookup"><span data-stu-id="7dd6b-116">If Office 365 AIR missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="7dd6b-117">È inoltre possibile [inviare un file a Microsoft per l'analisi antimalware](https://www.microsoft.com/wdsi/filesubmission).</span><span class="sxs-lookup"><span data-stu-id="7dd6b-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="7dd6b-118">Modificare un avviso per evitare che i falsi positivi vengano ricorrenti</span><span class="sxs-lookup"><span data-stu-id="7dd6b-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="7dd6b-119">Se un avviso viene attivato tramite un utilizzo legittimo o se l'avviso non è accurato, è possibile [gestire gli avvisi nel portale di cloud app Security](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="7dd6b-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="7dd6b-120">Se l'organizzazione utilizza [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) oltre a Office 365 e un file, un indirizzo IP, un URL o un dominio viene considerato come malware su un dispositivo, anche se è sicuro, è possibile [creare un indicatore personalizzato con un'azione "Consenti" per il dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="7dd6b-120">If your organization is using [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="7dd6b-121">Annullare un'azione di correzione</span><span class="sxs-lookup"><span data-stu-id="7dd6b-121">Undo a remediation action</span></span>

<span data-ttu-id="7dd6b-122">Nella maggior parte dei casi, se è stata eseguita un'azione di correzione su un messaggio di posta elettronica, un allegato di posta elettronica o un URL e l'elemento non è effettivamente una minaccia, il team delle operazioni di sicurezza può annullare l'azione di correzione e intraprendere le operazioni necessarie per impedire il ripetersi del falso positivo.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="7dd6b-123">È possibile utilizzare [Esplora minacce](#undo-an-action-using-threat-explorer) o la [scheda azioni per un'analisi](#undo-an-action-using-the-actions-tab-for-an-investigation) per annullare un'azione.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7dd6b-124">Accertarsi di disporre delle autorizzazioni necessarie prima di tentare di eseguire le attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="7dd6b-125">Annullamento di un'azione tramite Esplora minacce</span><span class="sxs-lookup"><span data-stu-id="7dd6b-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="7dd6b-126">Con Esplora minacce, il team delle operazioni di sicurezza può trovare un messaggio di posta elettronica influenzato da un'azione e potenzialmente annullare l'azione.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="7dd6b-127">Scenario</span><span class="sxs-lookup"><span data-stu-id="7dd6b-127">Scenario</span></span>  |<span data-ttu-id="7dd6b-128">Opzioni di annullamento</span><span class="sxs-lookup"><span data-stu-id="7dd6b-128">Undo Options</span></span>  |<span data-ttu-id="7dd6b-129">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="7dd6b-129">Learn more</span></span> |
|---------|---------|---------|
|<span data-ttu-id="7dd6b-130">Un messaggio di posta elettronica è stato instradato alla cartella posta indesiderata di un utente</span><span class="sxs-lookup"><span data-stu-id="7dd6b-130">An email message was routed to a user's Junk Email folder</span></span>     |<span data-ttu-id="7dd6b-131">-Spostare il messaggio nella cartella Posta eliminata dell'utente</span><span class="sxs-lookup"><span data-stu-id="7dd6b-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="7dd6b-132">-Spostare il messaggio nella cartella posta in arrivo dell'utente</span><span class="sxs-lookup"><span data-stu-id="7dd6b-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="7dd6b-133">-Eliminare il messaggio</span><span class="sxs-lookup"><span data-stu-id="7dd6b-133">- Delete the message</span></span>          |[<span data-ttu-id="7dd6b-134">Individuare e studiare messaggi di posta elettronica dannosi che sono stati recapitati in Office 365</span><span class="sxs-lookup"><span data-stu-id="7dd6b-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|<span data-ttu-id="7dd6b-135">Un messaggio di posta elettronica o un file è stato messo in quarantena</span><span class="sxs-lookup"><span data-stu-id="7dd6b-135">An email message or a file was quarantined</span></span>     |<span data-ttu-id="7dd6b-136">-Rilasciare il messaggio di posta elettronica o il file</span><span class="sxs-lookup"><span data-stu-id="7dd6b-136">- Release the email or file</span></span> <br/><span data-ttu-id="7dd6b-137">-Eliminare il messaggio di posta elettronica o il file</span><span class="sxs-lookup"><span data-stu-id="7dd6b-137">- Delete the email or file</span></span>         |[<span data-ttu-id="7dd6b-138">Gestire i messaggi e i file in quarantena come amministratore in Office 365</span><span class="sxs-lookup"><span data-stu-id="7dd6b-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="7dd6b-139">Annullamento di un'azione tramite la scheda azioni per un'analisi</span><span class="sxs-lookup"><span data-stu-id="7dd6b-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="7dd6b-140">Nel centro azioni, è possibile visualizzare le azioni di correzione eseguite e potenzialmente annullare l'azione.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="7dd6b-141">Andare su [https://protection.office.com](https://protection.office.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="7dd6b-142">Questo porta al centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="7dd6b-143">Andare a indagini sulla **gestione delle minacce**  >  **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="7dd6b-144">Nell'elenco delle indagini selezionare l'icona **Apri in nuova finestra** accanto all'ID di un elemento.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="7dd6b-145">Selezionare la scheda **azioni** .</span><span class="sxs-lookup"><span data-stu-id="7dd6b-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="7dd6b-146">Selezionare un elemento con stato **completato**e cercare un collegamento, ad esempio **approvato**, nella colonna **decisione** .</span><span class="sxs-lookup"><span data-stu-id="7dd6b-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="7dd6b-147">Verrà aperto un riquadro a comparsa con maggiori dettagli sull'azione.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="7dd6b-148">Per annullare l'azione, selezionare **Elimina correzione**.</span><span class="sxs-lookup"><span data-stu-id="7dd6b-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7dd6b-149">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="7dd6b-149">Related articles</span></span>

[<span data-ttu-id="7dd6b-150">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7dd6b-150">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="7dd6b-151">Iniziare a usare l'analisi e la risposta automatizzate (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="7dd6b-151">Get started using Automated investigation and response (AIR) in Office 365</span></span>](office-365-air.md)
