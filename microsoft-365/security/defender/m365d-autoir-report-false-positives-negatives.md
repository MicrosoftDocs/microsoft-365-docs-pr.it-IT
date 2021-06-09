---
title: Risolvere i falsi positivi o i falsi negativi in Microsoft 365 Defender
description: Qualcosa non è stato rilevato o rilevato in modo errato da AIR in Microsoft 365 Defender? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
keywords: automatizzato, indagine, avviso, correzione, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 3cffa97d26b2b28de8d9e45d7030e0931a7ba072
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269579"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a><span data-ttu-id="56bd1-105">Risolvere i falsi positivi o i falsi negativi in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56bd1-105">Address false positives or false negatives in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="56bd1-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="56bd1-106">**Applies to:**</span></span>
- <span data-ttu-id="56bd1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56bd1-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="56bd1-108">Talvolta possono verificarsi falsi positivi o negativi con qualsiasi soluzione di protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="56bd1-108">False positives or negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="56bd1-109">Se [le funzionalità di analisi e risposta](m365d-autoir.md) automatizzate in Microsoft 365 Defender hanno perso o rilevato qualcosa in modo errato, il team delle operazioni di sicurezza può eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="56bd1-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- [<span data-ttu-id="56bd1-110">Segnalare un falso positivo/negativo a Microsoft</span><span class="sxs-lookup"><span data-stu-id="56bd1-110">Report a false positive/negative to Microsoft</span></span>](#report-a-false-positivenegative-to-microsoft-for-analysis)
- <span data-ttu-id="56bd1-111">[Modificare gli avvisi](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessario)</span><span class="sxs-lookup"><span data-stu-id="56bd1-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed)</span></span>
- [<span data-ttu-id="56bd1-112">Annullare le azioni di correzione eseguite nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="56bd1-112">Undo remediation actions that were taken on devices</span></span>](#undo-a-remediation-action-that-was-taken-on-a-device)

<span data-ttu-id="56bd1-113">Nelle sezioni seguenti viene descritto come eseguire queste attività.</span><span class="sxs-lookup"><span data-stu-id="56bd1-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="56bd1-114">Segnalare un falso positivo/negativo a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="56bd1-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="56bd1-115">Elemento perso o rilevato in modo errato</span><span class="sxs-lookup"><span data-stu-id="56bd1-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="56bd1-116">Servizio</span><span class="sxs-lookup"><span data-stu-id="56bd1-116">Service</span></span>  |<span data-ttu-id="56bd1-117">Soluzione</span><span class="sxs-lookup"><span data-stu-id="56bd1-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="56bd1-118">- Messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="56bd1-118">- Email message</span></span> <br/><span data-ttu-id="56bd1-119">- Allegato di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="56bd1-119">- Email attachment</span></span> <br/><span data-ttu-id="56bd1-120">- URL in un messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="56bd1-120">- URL in an email message</span></span><br/><span data-ttu-id="56bd1-121">- URL in un Office file</span><span class="sxs-lookup"><span data-stu-id="56bd1-121">- URL in an Office file</span></span>      |[<span data-ttu-id="56bd1-122">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="56bd1-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="56bd1-123">Inviare posta indesiderata sospetta, phish, URL e file a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="56bd1-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="56bd1-124">File o app in un dispositivo</span><span class="sxs-lookup"><span data-stu-id="56bd1-124">File or app on a device</span></span>    |[<span data-ttu-id="56bd1-125">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="56bd1-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="56bd1-126">Inviare un file a Microsoft per l'analisi del malware</span><span class="sxs-lookup"><span data-stu-id="56bd1-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="56bd1-127">Modificare un avviso per evitare che i falsi positivi si ricorrenti</span><span class="sxs-lookup"><span data-stu-id="56bd1-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="56bd1-128">Scenario</span><span class="sxs-lookup"><span data-stu-id="56bd1-128">Scenario</span></span> |<span data-ttu-id="56bd1-129">Servizio</span><span class="sxs-lookup"><span data-stu-id="56bd1-129">Service</span></span> |<span data-ttu-id="56bd1-130">Soluzione</span><span class="sxs-lookup"><span data-stu-id="56bd1-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="56bd1-131">- Un avviso viene attivato da un uso legittimo</span><span class="sxs-lookup"><span data-stu-id="56bd1-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="56bd1-132">- Un avviso non è accurato</span><span class="sxs-lookup"><span data-stu-id="56bd1-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="56bd1-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="56bd1-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="56bd1-134">oppure</span><span class="sxs-lookup"><span data-stu-id="56bd1-134">or</span></span> <br/>[<span data-ttu-id="56bd1-135">Azure Threat Protection</span><span class="sxs-lookup"><span data-stu-id="56bd1-135">Azure threat protection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="56bd1-136">Gestire gli avvisi nel Cloud App Security portale</span><span class="sxs-lookup"><span data-stu-id="56bd1-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="56bd1-137">Un file, un indirizzo IP, un URL o un dominio viene considerato come malware in un dispositivo, anche se è sicuro</span><span class="sxs-lookup"><span data-stu-id="56bd1-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="56bd1-138">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="56bd1-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="56bd1-139">Creare un indicatore personalizzato con un'azione "Consenti"</span><span class="sxs-lookup"><span data-stu-id="56bd1-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="56bd1-140">Annullare un'azione di correzione eseguita in un dispositivo</span><span class="sxs-lookup"><span data-stu-id="56bd1-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="56bd1-141">Se è stata eseguita un'azione di correzione su un'entità (ad esempio un dispositivo o un messaggio di posta elettronica) e l'entità interessata non è effettivamente una minaccia, il team delle operazioni di sicurezza può annullare l'azione di correzione nel centro [notifiche.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="56bd1-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="56bd1-142">Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="56bd1-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="56bd1-143">Nel riquadro di spostamento, scegliere **Centro notifiche**.</span><span class="sxs-lookup"><span data-stu-id="56bd1-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="56bd1-144">Nella scheda **Cronologia** selezionare un'azione che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="56bd1-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="56bd1-145">Verrà visualizzato il riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="56bd1-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="56bd1-146">Nel riquadro a comparsa selezionare **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="56bd1-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="56bd1-147">Vedi [Annullare le azioni completate.](m365d-autoir-actions.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="56bd1-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="56bd1-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56bd1-148">See also</span></span>

- [<span data-ttu-id="56bd1-149">Visualizzare i dettagli e i risultati di un'indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="56bd1-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="56bd1-150">Ricerca proattiva di minacce con ricerca avanzata in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56bd1-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="56bd1-151">Indirizzare i falsi positivi/negativi in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="56bd1-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)