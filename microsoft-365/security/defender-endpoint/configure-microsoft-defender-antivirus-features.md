---
title: Configurare le funzionalità di Microsoft Defender Antivirus
description: Puoi configurare le funzionalità di Microsoft Defender Antivirus con Intune, Microsoft Endpoint Configuration Manager, Criteri di gruppo e PowerShell.
keywords: Microsoft Defender Antivirus, antimalware, sicurezza, defender, configurare, configurazione, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, gestione dei dispositivi mobili, Criteri di gruppo, Criteri di gruppo, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3dcf0ab24541a8837fbab91049fed0157b7f1fc9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690295"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="3c936-104">Configurare le funzionalità di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="3c936-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3c936-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3c936-105">**Applies to:**</span></span>

- [<span data-ttu-id="3c936-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="3c936-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3c936-107">Puoi configurare Microsoft Defender Antivirus con diversi strumenti, tra cui:</span><span class="sxs-lookup"><span data-stu-id="3c936-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="3c936-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3c936-108">Microsoft Intune</span></span>
- <span data-ttu-id="3c936-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3c936-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="3c936-110">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="3c936-110">Group Policy</span></span>
- <span data-ttu-id="3c936-111">Cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c936-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="3c936-112">Strumentazione gestione Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="3c936-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="3c936-113">È possibile configurare le seguenti ampie categorie di funzionalità:</span><span class="sxs-lookup"><span data-stu-id="3c936-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="3c936-114">Protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="3c936-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="3c936-115">Protezione sempre in tempo reale, tra cui protezione comportamentale, euristica e basata sull'apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="3c936-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="3c936-116">Interazione degli utenti finali con il client su singoli endpoint</span><span class="sxs-lookup"><span data-stu-id="3c936-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="3c936-117">Gli articoli seguenti descrivono come eseguire le attività principali durante la configurazione di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="3c936-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="3c936-118">Ogni articolo include istruzioni per lo strumento o gli strumenti di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="3c936-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="3c936-119">Articolo</span><span class="sxs-lookup"><span data-stu-id="3c936-119">Article</span></span>  |<span data-ttu-id="3c936-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c936-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="3c936-121">Utilizzare la protezione Microsoft Defender Antivirus fornita dal cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="3c936-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="3c936-122">Usa la protezione basata sul cloud per un rilevamento antivirus avanzato, veloce e affidabile.</span><span class="sxs-lookup"><span data-stu-id="3c936-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="3c936-123">Configurare la protezione comportamentale, euristica e in tempo reale</span><span class="sxs-lookup"><span data-stu-id="3c936-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="3c936-124">Abilitare la protezione antivirus basata sul comportamento, euristica e in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="3c936-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="3c936-125">Configurare l'interazione dell'utente finale con Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="3c936-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="3c936-126">Configura il modo in cui gli utenti finali nell'organizzazione interagiscono con Microsoft Defender Antivirus, quali notifiche visualizzano e se possono ignorare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3c936-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="3c936-127">È inoltre possibile consultare gli argomenti [di riferimento](configuration-management-reference-microsoft-defender-antivirus.md) per gli strumenti di gestione e configurazione per una panoramica di ogni strumento e collegamenti a ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="3c936-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>