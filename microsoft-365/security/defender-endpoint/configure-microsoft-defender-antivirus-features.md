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
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6ef9a2c34a88d7c9f5506c681088db9dc84cb0cc
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789028"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="ea803-104">Configurare la funzionalità di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="ea803-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ea803-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ea803-105">**Applies to:**</span></span>

- [<span data-ttu-id="ea803-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="ea803-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ea803-107">È possibile configurare Antivirus Microsoft Defender con diversi strumenti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ea803-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="ea803-108">Microsoft Endpoint Manager (che include Microsoft Intune e Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="ea803-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="ea803-109">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="ea803-109">Group Policy</span></span>
- <span data-ttu-id="ea803-110">Cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea803-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="ea803-111">Strumentazione gestione Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="ea803-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="ea803-112">È possibile configurare le seguenti ampie categorie di funzionalità:</span><span class="sxs-lookup"><span data-stu-id="ea803-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="ea803-113">Protezione basata sul cloud.</span><span class="sxs-lookup"><span data-stu-id="ea803-113">Cloud-delivered protection.</span></span> <span data-ttu-id="ea803-114">Vedi [Protezione e Antivirus Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ea803-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="ea803-115">Protezione sempre in tempo reale, inclusa la protezione comportamentale, euristica e basata sull'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="ea803-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="ea803-116">Vedi [Configurare la protezione comportamentale, euristica](configure-protection-features-microsoft-defender-antivirus.md)e in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ea803-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="ea803-117">Modalità di interazione degli utenti finali con il client su singoli endpoint.</span><span class="sxs-lookup"><span data-stu-id="ea803-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="ea803-118">Vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea803-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="ea803-119">Impedire agli utenti di visualizzare o interagire con l'Antivirus Microsoft Defender utente</span><span class="sxs-lookup"><span data-stu-id="ea803-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="ea803-120">Impedire o consentire agli utenti di modificare localmente Antivirus Microsoft Defender impostazioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="ea803-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="ea803-121">Esaminare [gli argomenti di riferimento per gli strumenti di gestione e configurazione.](configuration-management-reference-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ea803-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>