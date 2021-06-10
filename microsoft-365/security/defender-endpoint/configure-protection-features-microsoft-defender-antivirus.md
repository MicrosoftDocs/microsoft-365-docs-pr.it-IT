---
title: Abilitare e configurare le Antivirus Microsoft Defender di protezione dei dati
description: Abilitare la protezione basata sul comportamento, euristica e in tempo reale in Microsoft Defender AV.
keywords: euristica, machine learning, monitoraggio del comportamento, protezione in tempo reale, always-on, Antivirus Microsoft Defender, antimalware, sicurezza, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 53b1e1474e0870388ec1cfaf214190eb0bdf7beb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274609"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="a2359-104">Configurare la protezione comportamentale, euristica e in tempo reale</span><span class="sxs-lookup"><span data-stu-id="a2359-104">Configure behavioral, heuristic, and real-time protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a2359-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a2359-105">**Applies to:**</span></span>

- [<span data-ttu-id="a2359-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a2359-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a2359-107">Antivirus Microsoft Defender diversi metodi per fornire la protezione dalle minacce:</span><span class="sxs-lookup"><span data-stu-id="a2359-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="a2359-108">Protezione basata sul cloud per il rilevamento quasi immediato e il blocco di minacce nuove ed emergenti</span><span class="sxs-lookup"><span data-stu-id="a2359-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="a2359-109">Analisi sempre attiva, con monitoraggio del comportamento di file e processi e altre euristiche (note anche come "protezione in tempo reale")</span><span class="sxs-lookup"><span data-stu-id="a2359-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="a2359-110">Aggiornamenti dedicati alla protezione basati sul machine learning, sull'analisi di big data automatica o manuale e sulla ricerca approfondita delle minacce.</span><span class="sxs-lookup"><span data-stu-id="a2359-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="a2359-111">È possibile configurare il modo Antivirus Microsoft Defender questi metodi con Criteri di gruppo, gestione configurazione System Center, cmdlet di PowerShell e Strumentazione gestione Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="a2359-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="a2359-112">In questa sezione viene illustrata la configurazione per l'analisi sempre attiva, inclusa la modalità di rilevamento e blocco delle app ritenute non sicure, ma che potrebbero non essere rilevate come malware.</span><span class="sxs-lookup"><span data-stu-id="a2359-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="a2359-113">Vedi [Usare tecnologie di Antivirus Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) di nuova generazione tramite la protezione basata sul cloud per informazioni su come abilitare e configurare Antivirus Microsoft Defender di protezione cloud.</span><span class="sxs-lookup"><span data-stu-id="a2359-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a2359-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a2359-114">In this section</span></span>

 <span data-ttu-id="a2359-115">Argomento</span><span class="sxs-lookup"><span data-stu-id="a2359-115">Topic</span></span> | <span data-ttu-id="a2359-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2359-116">Description</span></span>
---|---
[<span data-ttu-id="a2359-117">Rilevare e bloccare applicazioni potenzialmente indesiderate</span><span class="sxs-lookup"><span data-stu-id="a2359-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="a2359-118">Rilevare e bloccare le app che potrebbero essere indesiderate nella rete, ad esempio adware, modificatori del browser e barre degli strumenti e app antivirus non autorizzate o contraffatte</span><span class="sxs-lookup"><span data-stu-id="a2359-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="a2359-119">Abilitare e configurare le funzionalità Antivirus Microsoft Defender protezione dei dati</span><span class="sxs-lookup"><span data-stu-id="a2359-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="a2359-120">Abilitare e configurare la protezione in tempo reale, l'euristica e altre funzionalità di monitoraggio Antivirus Microsoft Defender always-on</span><span class="sxs-lookup"><span data-stu-id="a2359-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>