---
title: Gestire Windows Defender nell'azienda
description: Informazioni su come usare Criteri di gruppo, Configuration Manager, PowerShell, WMI, Intune e la riga di comando per gestire Microsoft Defender AV
keywords: Criteri di gruppo, gpo, config manager, sccm, scep, powershell, wmi, intune, defender, antivirus, antimalware, sicurezza, protezione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/13/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f9ecade23964db88076347b3a89085b25c1b1538
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415564"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="4380d-104">Gestire Antivirus Microsoft Defender nell'azienda</span><span class="sxs-lookup"><span data-stu-id="4380d-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4380d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4380d-105">**Applies to:**</span></span>

- [<span data-ttu-id="4380d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="4380d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="4380d-107">Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4380d-107">Microsoft Defender Antivirus</span></span>](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)

<span data-ttu-id="4380d-108">È possibile gestire e configurare Antivirus Microsoft Defender con gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4380d-108">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="4380d-109">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (ora parte di Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="4380d-109">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="4380d-110">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (ora parte di Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="4380d-110">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="4380d-111">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="4380d-111">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4380d-112">Cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="4380d-112">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="4380d-113">Strumentazione gestione Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="4380d-113">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="4380d-114">Utilità da riga di comando di [Microsoft Malware Protection](./command-line-arguments-microsoft-defender-antivirus.md) (denominata utilità *mpcmdrun.exe* malware</span><span class="sxs-lookup"><span data-stu-id="4380d-114">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="4380d-115">Gli articoli seguenti forniscono ulteriori informazioni, collegamenti e risorse per l'utilizzo di questi strumenti per gestire e configurare Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="4380d-115">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="4380d-116">Articolo</span><span class="sxs-lookup"><span data-stu-id="4380d-116">Article</span></span> | <span data-ttu-id="4380d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4380d-117">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="4380d-118">Gestire Antivirus Microsoft Defender con Microsoft Intune e Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4380d-118">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="4380d-119">Informazioni sull'uso di Intune e Configuration Manager per distribuire, gestire, creare report e configurare Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4380d-119">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="4380d-120">Gestire Antivirus Microsoft Defender con le impostazioni di Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="4380d-120">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="4380d-121">Elenco di tutte le impostazioni di Criteri di gruppo disponibili nei modelli ADMX</span><span class="sxs-lookup"><span data-stu-id="4380d-121">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="4380d-122">Gestire Antivirus Microsoft Defender con i cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="4380d-122">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="4380d-123">Istruzioni per l'utilizzo dei cmdlet di PowerShell per gestire Antivirus Microsoft Defender, oltre a collegamenti alla documentazione per tutti i cmdlet e i parametri consentiti</span><span class="sxs-lookup"><span data-stu-id="4380d-123">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="4380d-124">Gestire Antivirus Microsoft Defender con Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="4380d-124">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="4380d-125">Istruzioni per l'utilizzo di WMI per gestire Antivirus Microsoft Defender, oltre a collegamenti alla documentazione per le API WMIv2 (incluse tutte le classi, i metodi e le proprietà)</span><span class="sxs-lookup"><span data-stu-id="4380d-125">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="4380d-126">Gestire Antivirus Microsoft Defender con lo MpCmdRun.exe da riga di comando</span><span class="sxs-lookup"><span data-stu-id="4380d-126">Manage Microsoft Defender Antivirus with the MpCmdRun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)| <span data-ttu-id="4380d-127">Istruzioni sull'utilizzo dello strumento da riga di comando dedicato per gestire e usare Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4380d-127">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |
