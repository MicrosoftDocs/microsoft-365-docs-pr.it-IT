---
title: Abilitare l'ambiente di valutazione per Microsoft Defender for Identity, configurare l'istanza MDI, installare e configurare il sensore MDI, consentire al sensore MDI di rilevare gli amministratori locali
description: Configurare Microsoft Defender per l'identità Microsoft 365 Defender laboratorio di valutazione o ambiente pilota installando & configurando il sensore e individuando gli amministratori locali in altri computer.
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
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458074"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a><span data-ttu-id="27dd1-103">Abilitare l'ambiente di valutazione per Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="27dd1-103">Enable the evaluation environment for Microsoft Defender for Identity</span></span>

<span data-ttu-id="27dd1-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="27dd1-104">**Applies to:**</span></span>
- <span data-ttu-id="27dd1-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27dd1-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="27dd1-106">Questo articolo è [il passaggio 2 di 2](eval-defender-identity-overview.md) nel processo di configurazione dell'ambiente di valutazione per Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="27dd1-106">This article is [Step 2 of 2](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="27dd1-107">Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-identity-overview.md).</span><span class="sxs-lookup"><span data-stu-id="27dd1-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="27dd1-108">Usa la procedura seguente per configurare l'ambiente Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="27dd1-108">Use the following steps to set up your Microsoft Defender for Identity environment.</span></span> 

![Passaggi per abilitare Microsoft Defender for Identity nell'ambiente di valutazione di Microsoft Defender](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [<span data-ttu-id="27dd1-110">Passaggio 1. Configurare Defender per l'istanza di identità</span><span class="sxs-lookup"><span data-stu-id="27dd1-110">Step 1. Set up the Defender for Identity Instance</span></span>](#step-1-set-up-the-defender-for-identity-instance)
- [<span data-ttu-id="27dd1-111">Passaggio 2. Installare e configurare il sensore</span><span class="sxs-lookup"><span data-stu-id="27dd1-111">Step 2. Install and configure the sensor</span></span>](#step-2-install-and-configure-the-sensor)
- [<span data-ttu-id="27dd1-112">Passaggio 3. Configurare le impostazioni del registro eventi e del proxy nei computer con il sensore</span><span class="sxs-lookup"><span data-stu-id="27dd1-112">Step 3. Configure event log and proxy settings on machines with the sensor</span></span>](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [<span data-ttu-id="27dd1-113">Passaggio 4. Consenti a Defender for Identity di identificare gli amministratori locali in altri computer</span><span class="sxs-lookup"><span data-stu-id="27dd1-113">Step 4. Allow Defender for Identity to identify local admins on other computers</span></span>](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a><span data-ttu-id="27dd1-114">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="27dd1-114">Step 1.</span></span> <span data-ttu-id="27dd1-115">Configurare Defender per l'istanza di identità</span><span class="sxs-lookup"><span data-stu-id="27dd1-115">Set up the Defender for Identity Instance</span></span>

<span data-ttu-id="27dd1-116">Accedi al portale defender per l'identità per creare l'istanza e quindi connetti questa istanza all'ambiente Active Directory.</span><span class="sxs-lookup"><span data-stu-id="27dd1-116">Sign in to the Defender for Identity portal to create your instance and then connect this instance to your Active Directory environment.</span></span> 

|  |<span data-ttu-id="27dd1-117">Passaggio</span><span class="sxs-lookup"><span data-stu-id="27dd1-117">Step</span></span>     |<span data-ttu-id="27dd1-118">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="27dd1-118">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="27dd1-119">1 </span><span class="sxs-lookup"><span data-stu-id="27dd1-119">1</span></span>     | <span data-ttu-id="27dd1-120">Creare l'istanza defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="27dd1-120">Create the Defender for Identity instance</span></span>        | [<span data-ttu-id="27dd1-121">Guida introduttiva: Creare l'istanza di Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="27dd1-121">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/defender-for-identity/install-step1)        |
|<span data-ttu-id="27dd1-122">2 </span><span class="sxs-lookup"><span data-stu-id="27dd1-122">2</span></span>     | <span data-ttu-id="27dd1-123">Connessione'istanza di Defender for Identity nella foresta di Active Directory</span><span class="sxs-lookup"><span data-stu-id="27dd1-123">Connect the Defender for Identity instance to your Active Directory forest</span></span>   | [<span data-ttu-id="27dd1-124">Guida introduttiva: Connessione alla foresta di Active Directory</span><span class="sxs-lookup"><span data-stu-id="27dd1-124">Quickstart: Connect to your Active Directory Forest</span></span>](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a><span data-ttu-id="27dd1-125">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="27dd1-125">Step 2.</span></span> <span data-ttu-id="27dd1-126">Installare e configurare il sensore</span><span class="sxs-lookup"><span data-stu-id="27dd1-126">Install and configure the sensor</span></span>

<span data-ttu-id="27dd1-127">Successivamente, scaricare, installare e configurare il sensore Defender for Identity nei controller di dominio e nei server AD FS nell'ambiente locale.</span><span class="sxs-lookup"><span data-stu-id="27dd1-127">Next, download, install, and configure the Defender for Identity sensor on the domain controllers and AD FS servers in your on-premises environment.</span></span>

|  |<span data-ttu-id="27dd1-128">Passaggio</span><span class="sxs-lookup"><span data-stu-id="27dd1-128">Step</span></span>     |<span data-ttu-id="27dd1-129">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="27dd1-129">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="27dd1-130">1 </span><span class="sxs-lookup"><span data-stu-id="27dd1-130">1</span></span>     | <span data-ttu-id="27dd1-131">Determinare quanti sensori di Microsoft Defender for Identity sono necessari.</span><span class="sxs-lookup"><span data-stu-id="27dd1-131">Determine how many Microsoft Defender for Identity sensors you need.</span></span>        | [<span data-ttu-id="27dd1-132">Pianificare la capacità di Microsoft Defender per l'identità</span><span class="sxs-lookup"><span data-stu-id="27dd1-132">Plan capacity for Microsoft Defender for Identity</span></span>](/defender-for-identity/capacity-planning)   |
|<span data-ttu-id="27dd1-133">2 </span><span class="sxs-lookup"><span data-stu-id="27dd1-133">2</span></span>     | <span data-ttu-id="27dd1-134">Scaricare il pacchetto di installazione del sensore</span><span class="sxs-lookup"><span data-stu-id="27dd1-134">Download the sensor setup package</span></span>  |  [<span data-ttu-id="27dd1-135">Guida introduttiva: Scaricare il pacchetto di installazione del sensore di identità di Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="27dd1-135">Quickstart: Download the Microsoft Defender for Identity sensor setup package</span></span>](/defender-for-identity/install-step3)   |
|<span data-ttu-id="27dd1-136">3 </span><span class="sxs-lookup"><span data-stu-id="27dd1-136">3</span></span>     | <span data-ttu-id="27dd1-137">Installare il sensore Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="27dd1-137">Install the Defender for Identity sensor</span></span>    |  [<span data-ttu-id="27dd1-138">Guida introduttiva: Installare il sensore Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="27dd1-138">Quickstart: Install the Microsoft Defender for Identity sensor</span></span>](/defender-for-identity/install-step4)       |
|<span data-ttu-id="27dd1-139">4 </span><span class="sxs-lookup"><span data-stu-id="27dd1-139">4</span></span>     | <span data-ttu-id="27dd1-140">Configurare il sensore</span><span class="sxs-lookup"><span data-stu-id="27dd1-140">Configure the sensor</span></span>       |  [<span data-ttu-id="27dd1-141">Configurare le impostazioni del sensore di identità per Microsoft Defender </span><span class="sxs-lookup"><span data-stu-id="27dd1-141">Configure Microsoft Defender for Identity sensor settings </span></span>](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a><span data-ttu-id="27dd1-142">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="27dd1-142">Step 3.</span></span> <span data-ttu-id="27dd1-143">Configurare le impostazioni del registro eventi e del proxy nei computer con il sensore</span><span class="sxs-lookup"><span data-stu-id="27dd1-143">Configure event log and proxy settings on machines with the sensor</span></span>

<span data-ttu-id="27dd1-144">Nei computer in cui è installato il sensore, configurare Windows registro eventi e le impostazioni proxy Internet per abilitare e migliorare le funzionalità di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="27dd1-144">On the machines that you installed the sensor on, configure Windows event log collection and Internet proxy settings to enable and enhance detection capabilities.</span></span>

|  |<span data-ttu-id="27dd1-145">Passaggio</span><span class="sxs-lookup"><span data-stu-id="27dd1-145">Step</span></span>     |<span data-ttu-id="27dd1-146">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="27dd1-146">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="27dd1-147">1 </span><span class="sxs-lookup"><span data-stu-id="27dd1-147">1</span></span>     | <span data-ttu-id="27dd1-148">Configurare Windows del registro eventi</span><span class="sxs-lookup"><span data-stu-id="27dd1-148">Configure Windows event log collection</span></span>         | [<span data-ttu-id="27dd1-149">Configurare Windows event</span><span class="sxs-lookup"><span data-stu-id="27dd1-149">Configure Windows Event collection</span></span>](/defender-for-identity/configure-windows-event-collection)        |
|<span data-ttu-id="27dd1-150">2 </span><span class="sxs-lookup"><span data-stu-id="27dd1-150">2</span></span>     | <span data-ttu-id="27dd1-151">Configurare le impostazioni proxy Internet</span><span class="sxs-lookup"><span data-stu-id="27dd1-151">Configure Internet proxy settings</span></span>        | [<span data-ttu-id="27dd1-152">Configurare le impostazioni di connettività Internet e proxy endpoint per Il sensore di identità di Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="27dd1-152">Configure endpoint proxy and Internet connectivity settings for your Microsoft Defender for Identity Sensor</span></span>](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a><span data-ttu-id="27dd1-153">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="27dd1-153">Step 4.</span></span> <span data-ttu-id="27dd1-154">Consenti a Defender for Identity di identificare gli amministratori locali in altri computer</span><span class="sxs-lookup"><span data-stu-id="27dd1-154">Allow Defender for Identity to identify local admins on other computers</span></span>

<span data-ttu-id="27dd1-155">Il rilevamento del percorso di spostamento laterale di Microsoft Defender for Identity si basa su query che identificano gli amministratori locali in computer specifici.</span><span class="sxs-lookup"><span data-stu-id="27dd1-155">Microsoft Defender for Identity lateral movement path detection relies on queries that identify local admins on specific machines.</span></span> <span data-ttu-id="27dd1-156">Queste query vengono eseguite con il protocollo SAM-R, utilizzando l'account Defender for Identity Service.</span><span class="sxs-lookup"><span data-stu-id="27dd1-156">These queries are performed with the SAM-R protocol, using the Defender for Identity Service account.</span></span> 

<span data-ttu-id="27dd1-157">Per garantire che i client e i server di Windows consentano all'account Defender for Identity di eseguire SAM-R, è necessario apportare una modifica a Criteri di gruppo per aggiungere l'account del servizio Defender per l'identità oltre agli account configurati elencati nei criteri di accesso di rete.</span><span class="sxs-lookup"><span data-stu-id="27dd1-157">To ensure Windows clients and servers allow your Defender for Identity account to perform SAM-R, a modification to Group Policy must be made to add the Defender for Identity service account in addition to the configured accounts listed in the Network access policy.</span></span> <span data-ttu-id="27dd1-158">Assicurarsi di applicare criteri di gruppo a tutti i computer ad **eccezione dei controller di dominio**.</span><span class="sxs-lookup"><span data-stu-id="27dd1-158">Make sure to apply group policies to all computers **except domain controllers**.</span></span>

<span data-ttu-id="27dd1-159">Per istruzioni su come eseguire questa operazione, vedi Configurare Microsoft Defender per l'identità per [effettuare chiamate remote a SAM.](/defender-for-identity/install-step8-samr)</span><span class="sxs-lookup"><span data-stu-id="27dd1-159">For instructions on how to do this, see [Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="27dd1-160">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="27dd1-160">Next steps</span></span>

<span data-ttu-id="27dd1-161">Passaggio 3 di 3: [Pilotare Microsoft Defender per l'identità](eval-defender-identity-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="27dd1-161">Step 3 of 3: [Pilot Microsoft Defender for Identity](eval-defender-identity-pilot.md)</span></span>

<span data-ttu-id="27dd1-162">Tornare alla panoramica per [valutare Microsoft Defender for Identity](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="27dd1-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="27dd1-163">Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="27dd1-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>