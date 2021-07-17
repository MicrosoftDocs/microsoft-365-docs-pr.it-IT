---
title: Pilotare Microsoft Defender for Identity, configurare benchmark di configurazione, standard, linee guida ed eseguire esercitazioni sul rilevamento e la correzione di varie minacce di identità come ricognizione, credenziali compromesse, movimento laterale, dominio dominante e avvisi di esfiltrazione, condurre indagini su utenti, computer, entità e percorsi di movimento laterale.
description: Pilota Microsoft Defender for Identity, imposta benchmark, esercitazioni sulla ricognizione, credenziali compromesse, movimento laterale, dominio dominante e avvisi di exfiltration, tra gli altri.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458055"
---
# <a name="pilot-microsoft-defender-for-identity"></a><span data-ttu-id="0d0a6-103">Pilota di Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="0d0a6-103">Pilot Microsoft Defender for Identity</span></span>


<span data-ttu-id="0d0a6-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0d0a6-104">**Applies to:**</span></span>
- <span data-ttu-id="0d0a6-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d0a6-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="0d0a6-106">Questo articolo è [il passaggio 3 di 3 del](eval-defender-identity-overview.md) processo di configurazione dell'ambiente di valutazione per Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-106">This article is [Step 3 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="0d0a6-107">Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-identity-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0d0a6-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="0d0a6-108">Usa la procedura seguente per configurare il progetto pilota per Microsoft Defender per l'identità.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-108">Use the following steps to setup and configure the pilot for Microsoft Defender for identity.</span></span> <span data-ttu-id="0d0a6-109">Si noti che i suggerimenti non includono la configurazione di un gruppo pilota.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-109">Note that the recommendations don't include setting up a pilot group.</span></span> <span data-ttu-id="0d0a6-110">La procedura consigliata consiste nell'installare il sensore in tutti i server che eseguono Servizi di dominio Active Directory e Active Directory Federated Services (AD FS).</span><span class="sxs-lookup"><span data-stu-id="0d0a6-110">The best practice is to go ahead and install the sensor on all of your servers running Active Directory Domain Services (AD DS) and Active Directory Federated Services (AD FS).</span></span>

![Passaggi per l'aggiunta di Microsoft Defender per l'identità all'ambiente di valutazione di Defender](../../media/defender/m365-defender-identity-pilot-steps.png)

<span data-ttu-id="0d0a6-112">Nella tabella seguente vengono descritti i passaggi illustrati nell'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-112">The following table describes the steps in the illustration.</span></span>

- [<span data-ttu-id="0d0a6-113">Passaggio 1: Configurare i suggerimenti di benchmark per l'ambiente di identità</span><span class="sxs-lookup"><span data-stu-id="0d0a6-113">Step 1: Configure benchmark recommendations for your identity environment</span></span>](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [<span data-ttu-id="0d0a6-114">Passaggio 2: provare le funzionalità - Esercitazioni dettagliate per identificare e correggere diversi tipi di attacco </span><span class="sxs-lookup"><span data-stu-id="0d0a6-114">Step 2: Try out capabilities — Walk through tutorials for identifying and remediating different attack types </span></span>](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a><span data-ttu-id="0d0a6-115">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-115">Step 1.</span></span> <span data-ttu-id="0d0a6-116">Configurare i suggerimenti di benchmark per l'ambiente di identità</span><span class="sxs-lookup"><span data-stu-id="0d0a6-116">Configure benchmark recommendations for your identity environment</span></span>

<span data-ttu-id="0d0a6-117">Microsoft fornisce consigli di benchmark di sicurezza per i clienti che usano i servizi Cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-117">Microsoft provides security benchmark recommendations for customers using Microsoft Cloud services.</span></span> <span data-ttu-id="0d0a6-118">[Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) fornisce procedure consigliate e suggerimenti prescrittivi per migliorare la sicurezza di carichi di lavoro, dati e servizi in Azure.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-118">The [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) provides prescriptive best practices and recommendations to help improve the security of workloads, data, and services on Azure.</span></span>

<span data-ttu-id="0d0a6-119">Questi consigli di benchmark includono [la linea di base della sicurezza di Azure per Microsoft Defender per l'identità.](/security/benchmark/azure/baselines/defender-for-identity-security-baseline)</span><span class="sxs-lookup"><span data-stu-id="0d0a6-119">These benchmark recommendations include [Azure security baseline for Microsoft Defender for Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline).</span></span> <span data-ttu-id="0d0a6-120">L'implementazione di questi suggerimenti può richiedere del tempo per la pianificazione e l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-120">Implementing these recommendations can take some time to plan and implement.</span></span> <span data-ttu-id="0d0a6-121">Anche se questi incrementeranno notevolmente la sicurezza dell'ambiente di identità, non dovrebbero impedirti di continuare a valutare e implementare Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-121">While these will greatly increase the security of your identity environment, they shouldn't prevent you from continuing to evaluate and implement Microsoft Defender for Identity.</span></span> <span data-ttu-id="0d0a6-122">Questi sono disponibili qui per la tua consapevolezza.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-122">These are provided here for your awareness.</span></span>

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a><span data-ttu-id="0d0a6-123">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-123">Step 2.</span></span> <span data-ttu-id="0d0a6-124">Funzionalità di prova: esercitazioni per identificare e correggere diversi tipi di attacco</span><span class="sxs-lookup"><span data-stu-id="0d0a6-124">Try out capabilities — Walk through tutorials for identifying and remediating different attack types</span></span>

<span data-ttu-id="0d0a6-125">La documentazione di Microsoft Defender for Identity include una serie di esercitazioni che illustrano il processo di identificazione e correzione di vari tipi di attacco.</span><span class="sxs-lookup"><span data-stu-id="0d0a6-125">The Microsoft Defender for Identity documentation includes a series of tutorials that walk through the process of identifying and remediating various attack types.</span></span>

<span data-ttu-id="0d0a6-126">Prova le esercitazioni su Defender per l'identità:</span><span class="sxs-lookup"><span data-stu-id="0d0a6-126">Try out Defender for Identity tutorials:</span></span>
- [<span data-ttu-id="0d0a6-127">Avvisi di ricognizione</span><span class="sxs-lookup"><span data-stu-id="0d0a6-127">Reconnaissance alerts</span></span>](/defender-for-identity/reconnaissance-alerts)
- [<span data-ttu-id="0d0a6-128">Avvisi credenziali compromesse</span><span class="sxs-lookup"><span data-stu-id="0d0a6-128">Compromised credential alerts</span></span>](/defender-for-identity/compromised-credentials-alerts)
- [<span data-ttu-id="0d0a6-129">Avvisi di movimento laterale</span><span class="sxs-lookup"><span data-stu-id="0d0a6-129">Lateral movement alerts</span></span>](/defender-for-identity/lateral-movement-alerts)
- [<span data-ttu-id="0d0a6-130">Avvisi di dominio dominante</span><span class="sxs-lookup"><span data-stu-id="0d0a6-130">Domain dominance alerts</span></span>](/defender-for-identity/domain-dominance-alerts)
- [<span data-ttu-id="0d0a6-131">Avvisi di esfiltrazione</span><span class="sxs-lookup"><span data-stu-id="0d0a6-131">Exfiltration alerts</span></span>](/defender-for-identity/exfiltration-alerts)
- [<span data-ttu-id="0d0a6-132">Analizzare un utente</span><span class="sxs-lookup"><span data-stu-id="0d0a6-132">Investigate a user</span></span>](/defender-for-identity/investigate-a-user)
- [<span data-ttu-id="0d0a6-133">Analizzare un computer</span><span class="sxs-lookup"><span data-stu-id="0d0a6-133">Investigate a computer</span></span>](/defender-for-identity/investigate-a-computer)
- [<span data-ttu-id="0d0a6-134">Analizzare i percorsi di movimento laterale</span><span class="sxs-lookup"><span data-stu-id="0d0a6-134">Investigate lateral movement paths</span></span>](/defender-for-identity/investigate-lateral-movement-path)
- [<span data-ttu-id="0d0a6-135">Analizzare le entità</span><span class="sxs-lookup"><span data-stu-id="0d0a6-135">Investigate entities</span></span>](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a><span data-ttu-id="0d0a6-136">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0d0a6-136">Next steps</span></span>

[<span data-ttu-id="0d0a6-137">Valutare Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="0d0a6-137">Evaluate Microsoft Defender for Office 365</span></span>](eval-defender-office-365-overview.md)

<span data-ttu-id="0d0a6-138">Torna alla panoramica di [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0d0a6-138">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="0d0a6-139">Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0d0a6-139">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>