---
title: Come segnalare falsi positivi o falsi negativi in aria in Microsoft Threat Protection
description: Si è verificato un errore o rilevato erroneamente da AIR in Microsoft Threat Protection? Informazioni su come inviare falsi positivi o falsi negativi a Microsoft per l'analisi.
keywords: automatizzato, indagine, avviso, trigger, azione, correzione, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260194"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="c5e0e-105">Come segnalare falsi positivi/negativi nelle funzionalità di analisi e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="c5e0e-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="c5e0e-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c5e0e-106">**Applies to:**</span></span>
- <span data-ttu-id="c5e0e-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c5e0e-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c5e0e-108">[Le funzionalità di ricerca e risposta automatizzate](mtp-autoir.md) in Microsoft Threat Protection non hanno o rilevato erroneamente qualcosa?</span><span class="sxs-lookup"><span data-stu-id="c5e0e-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="c5e0e-109">È possibile segnalarlo a Microsoft o regolare gli avvisi (se necessario).</span><span class="sxs-lookup"><span data-stu-id="c5e0e-109">You can report it to Microsoft or adjust your alerts (if needed).</span></span> <span data-ttu-id="c5e0e-110">Utilizzare la tabella seguente come guida:</span><span class="sxs-lookup"><span data-stu-id="c5e0e-110">Use the following table as a guide:</span></span> 


|<span data-ttu-id="c5e0e-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="c5e0e-111">Item</span></span>  |<span data-ttu-id="c5e0e-112">Rilevato da</span><span class="sxs-lookup"><span data-stu-id="c5e0e-112">Detected by</span></span>  |<span data-ttu-id="c5e0e-113">Come segnalarlo</span><span class="sxs-lookup"><span data-stu-id="c5e0e-113">How to report it</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c5e0e-114">Messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c5e0e-114">Email message</span></span> <br/><span data-ttu-id="c5e0e-115">Allegato di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c5e0e-115">Email attachment</span></span> <br/><span data-ttu-id="c5e0e-116">URL in un messaggio di posta elettronica o in un file di Office</span><span class="sxs-lookup"><span data-stu-id="c5e0e-116">URL in an email message or Office file</span></span>      |[<span data-ttu-id="c5e0e-117">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c5e0e-117">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="c5e0e-118">Inviare messaggi di posta indesiderata sospetti, phishing, URL e file a Microsoft per l'analisi di Office 365</span><span class="sxs-lookup"><span data-stu-id="c5e0e-118">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="c5e0e-119">File o app in un dispositivo</span><span class="sxs-lookup"><span data-stu-id="c5e0e-119">File or app on a device</span></span>    |[<span data-ttu-id="c5e0e-120">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c5e0e-120">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="c5e0e-121">Inviare un file a Microsoft per l'analisi antimalware</span><span class="sxs-lookup"><span data-stu-id="c5e0e-121">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |
|<span data-ttu-id="c5e0e-122">Avviso attivato da un utilizzo legittimo</span><span class="sxs-lookup"><span data-stu-id="c5e0e-122">Alert triggered by legitimate use</span></span> <br/><span data-ttu-id="c5e0e-123">Avviso inesatto</span><span class="sxs-lookup"><span data-stu-id="c5e0e-123">Inaccurate alert</span></span>    |[<span data-ttu-id="c5e0e-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c5e0e-124">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="c5e0e-125">oppure</span><span class="sxs-lookup"><span data-stu-id="c5e0e-125">or</span></span> <br/>[<span data-ttu-id="c5e0e-126">Rilevamento delle minacce avanzato di Azure</span><span class="sxs-lookup"><span data-stu-id="c5e0e-126">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="c5e0e-127">Gestire gli avvisi nel cloud app Security Portal</span><span class="sxs-lookup"><span data-stu-id="c5e0e-127">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a><span data-ttu-id="c5e0e-128">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c5e0e-128">Next steps</span></span>

- [<span data-ttu-id="c5e0e-129">Approvare o rifiutare le azioni relative all'indagine e reazione automatizzate</span><span class="sxs-lookup"><span data-stu-id="c5e0e-129">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="c5e0e-130">Altre informazioni sul centro notifiche</span><span class="sxs-lookup"><span data-stu-id="c5e0e-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="c5e0e-131">Cercare in modo proattivo minacce con la ricerca avanzata di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c5e0e-131">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
