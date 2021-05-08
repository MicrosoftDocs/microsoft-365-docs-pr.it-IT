---
title: Configurare la funzionalità di Microsoft Defender Antivirus
description: È possibile configurare Antivirus Microsoft Defender con Intune, Microsoft Endpoint Configuration Manager, Criteri di gruppo e PowerShell.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, defender, configurare, configurazione, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, gestione dei dispositivi mobili, Criteri di gruppo, Criteri di gruppo, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275109"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="eed93-104">Configurare la funzionalità di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="eed93-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="eed93-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="eed93-105">**Applies to:**</span></span>

- [<span data-ttu-id="eed93-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="eed93-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="eed93-107">È possibile configurare Antivirus Microsoft Defender con una serie di strumenti, tra cui:</span><span class="sxs-lookup"><span data-stu-id="eed93-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="eed93-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="eed93-108">Microsoft Intune</span></span>
- <span data-ttu-id="eed93-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eed93-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="eed93-110">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="eed93-110">Group Policy</span></span>
- <span data-ttu-id="eed93-111">Cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="eed93-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="eed93-112">Strumentazione gestione Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="eed93-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="eed93-113">È possibile configurare le seguenti ampie categorie di funzionalità:</span><span class="sxs-lookup"><span data-stu-id="eed93-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="eed93-114">Protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="eed93-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="eed93-115">Protezione sempre in tempo reale, tra cui protezione comportamentale, euristica e basata sull'apprendimento automatico</span><span class="sxs-lookup"><span data-stu-id="eed93-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="eed93-116">Interazione degli utenti finali con il client su singoli endpoint</span><span class="sxs-lookup"><span data-stu-id="eed93-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="eed93-117">Gli articoli seguenti descrivono come eseguire attività chiave durante la configurazione Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="eed93-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="eed93-118">Ogni articolo include istruzioni per lo strumento o gli strumenti di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="eed93-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="eed93-119">Articolo</span><span class="sxs-lookup"><span data-stu-id="eed93-119">Article</span></span>  |<span data-ttu-id="eed93-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eed93-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="eed93-121">Utilizzare la protezione basata Antivirus Microsoft Defender cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="eed93-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="eed93-122">Usa la protezione basata sul cloud per un rilevamento antivirus avanzato, veloce e affidabile.</span><span class="sxs-lookup"><span data-stu-id="eed93-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="eed93-123">Configurare la protezione comportamentale, euristica e in tempo reale</span><span class="sxs-lookup"><span data-stu-id="eed93-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="eed93-124">Abilitare la protezione antivirus basata sul comportamento, euristica e in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="eed93-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="eed93-125">Configurare l'interazione dell'utente finale con Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="eed93-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="eed93-126">Configurare il modo in cui gli utenti finali dell'organizzazione interagiscono con Antivirus Microsoft Defender, quali notifiche visualizzano e se possono ignorare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="eed93-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="eed93-127">È inoltre possibile consultare gli argomenti [di riferimento](configuration-management-reference-microsoft-defender-antivirus.md) per gli strumenti di gestione e configurazione per una panoramica di ogni strumento e collegamenti a ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="eed93-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>