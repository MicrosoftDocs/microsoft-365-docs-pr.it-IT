---
title: Esaminare i requisiti e i concetti chiave dell'architettura di Microsoft Defender per endpoint
description: Il diagramma tecnico per Microsoft Defender for Endpoint in Microsoft 365 Defender ti aiuterà a comprendere l'identità in Microsoft 365 prima di creare il laboratorio di valutazione o l'ambiente pilota.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
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
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458128"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a><span data-ttu-id="5bed0-103">Esaminare i requisiti e i concetti chiave dell'architettura di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5bed0-103">Review Microsoft Defender for Endpoint architecture requirements and key concepts</span></span>

<span data-ttu-id="5bed0-104">**Si applica a:** Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5bed0-104">**Applies to:** Microsoft 365 Defender</span></span>

<span data-ttu-id="5bed0-105">Questo articolo ti guiderà nel processo di configurazione della valutazione per Microsoft Defender per l'ambiente endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bed0-105">This article will guide you in the process of setting up the evaluation for Microsoft Defender for Endpoint environment.</span></span>

<span data-ttu-id="5bed0-106">Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-endpoint-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5bed0-106">For more information about this process, see the [overview article](eval-defender-endpoint-overview.md).</span></span>

<span data-ttu-id="5bed0-107">Prima di abilitare Microsoft Defender per Endpoint, assicurati di aver compreso l'architettura e di poter soddisfare i requisiti.</span><span class="sxs-lookup"><span data-stu-id="5bed0-107">Before enabling Microsoft Defender for Endpoint, be sure you understand the architecture and can meet the requirements.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="5bed0-108">Informazioni sull'architettura</span><span class="sxs-lookup"><span data-stu-id="5bed0-108">Understand the architecture</span></span>

<span data-ttu-id="5bed0-109">Il diagramma seguente illustra l'architettura e le integrazioni di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bed0-109">The following diagram illustrates Microsoft Defender for Endpoint architecture and integrations.</span></span> 

![Passaggi per l'aggiunta di Microsoft Defender per Office all'ambiente di valutazione di Defender](../../media/defender/m365-defender-endpoint-architecture.png)

<span data-ttu-id="5bed0-111">Nella tabella seguente viene descritta l'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="5bed0-111">The following table describes the illustration.</span></span>

<span data-ttu-id="5bed0-112">Call-out</span><span class="sxs-lookup"><span data-stu-id="5bed0-112">Call-out</span></span> | <span data-ttu-id="5bed0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5bed0-113">Description</span></span>
:---|:---|
<span data-ttu-id="5bed0-114">1</span><span class="sxs-lookup"><span data-stu-id="5bed0-114">1</span></span> | <span data-ttu-id="5bed0-115">I dispositivi sono a bordo tramite uno degli strumenti di gestione supportati.</span><span class="sxs-lookup"><span data-stu-id="5bed0-115">Devices are on-boarded through one of the supported management tools.</span></span> 
<span data-ttu-id="5bed0-116">2 </span><span class="sxs-lookup"><span data-stu-id="5bed0-116">2</span></span> | <span data-ttu-id="5bed0-117">I dispositivi a bordo forniscono e rispondono ai dati del segnale di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bed0-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span></span>
<span data-ttu-id="5bed0-118">3 </span><span class="sxs-lookup"><span data-stu-id="5bed0-118">3</span></span> | <span data-ttu-id="5bed0-119">I dispositivi gestiti vengono aggiunti e/o registrati in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5bed0-119">Managed devices are joined and/or enrolled in Azure Active Directory.</span></span>
<span data-ttu-id="5bed0-120">4 </span><span class="sxs-lookup"><span data-stu-id="5bed0-120">4</span></span> | <span data-ttu-id="5bed0-121">I dispositivi Windows 10 aggiunti a un dominio vengono sincronizzati con Azure Active Directory tramite Azure Active Directory Connessione.</span><span class="sxs-lookup"><span data-stu-id="5bed0-121">Domain-joined Windows 10 devices are synchronized to Azure Active Directory using Azure Active Directory Connect.</span></span>
<span data-ttu-id="5bed0-122">5 </span><span class="sxs-lookup"><span data-stu-id="5bed0-122">5</span></span> | <span data-ttu-id="5bed0-123">Gli avvisi, le indagini e le risposte di Microsoft Defender per endpoint vengono gestiti in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5bed0-123">Microsoft Defender for Endpoint alerts, investigations, and responses are managed in Microsoft 365 Defender.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="5bed0-124">Comprendere i concetti chiave</span><span class="sxs-lookup"><span data-stu-id="5bed0-124">Understand key concepts</span></span>

<span data-ttu-id="5bed0-125">Nella tabella seguente sono stati identificati i concetti chiave importanti da comprendere durante la valutazione, la configurazione e la distribuzione di Microsoft Defender per Endpoint:</span><span class="sxs-lookup"><span data-stu-id="5bed0-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Endpoint:</span></span> 

<span data-ttu-id="5bed0-126">Concetti</span><span class="sxs-lookup"><span data-stu-id="5bed0-126">Concept</span></span> | <span data-ttu-id="5bed0-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5bed0-127">Description</span></span> | <span data-ttu-id="5bed0-128">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="5bed0-128">More information</span></span>
:---|:---|:---|
<span data-ttu-id="5bed0-129">Portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="5bed0-129">Administration Portal</span></span> | <span data-ttu-id="5bed0-130">Microsoft 365 Defender portale per monitorare e aiutare a rispondere agli avvisi di potenziali attività avanzate di minacce persistenti o violazioni dei dati.</span><span class="sxs-lookup"><span data-stu-id="5bed0-130">Microsoft 365 Defender portal to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> | [<span data-ttu-id="5bed0-131">Panoramica del portale di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5bed0-131">Microsoft Defender for Endpoint portal overview</span></span>](/defender-endpoint/portal-overview)
<span data-ttu-id="5bed0-132">Riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="5bed0-132">Attack Surface Reduction</span></span> | <span data-ttu-id="5bed0-133">Aiuta a ridurre le superfici di attacco riducendo al minimo i luoghi in cui l'organizzazione è vulnerabile a minacce informatiche e attacchi.</span><span class="sxs-lookup"><span data-stu-id="5bed0-133">Help reduce your attack surfaces by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> | [<span data-ttu-id="5bed0-134">Panoramica della riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="5bed0-134">Overview of attack surface reduction</span></span>](/defender-endpoint/overview-attack-surface-reduction)
<span data-ttu-id="5bed0-135">Rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="5bed0-135">Endpoint Detection and Response</span></span> | <span data-ttu-id="5bed0-136">Le funzionalità di risposta e rilevamento degli endpoint offrono rilevamenti di attacchi avanzati quasi in tempo reale e utilizzabili.</span><span class="sxs-lookup"><span data-stu-id="5bed0-136">Endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> | [<span data-ttu-id="5bed0-137">Panoramica delle funzionalità di rilevamento e risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="5bed0-137">Overview of endpoint detection and response capabilities</span></span>](/defender-endpoint/overview-endpoint-detection-response)
<span data-ttu-id="5bed0-138">Blocco e contenimento comportamentali</span><span class="sxs-lookup"><span data-stu-id="5bed0-138">Behavioral Blocking and Containment</span></span> | <span data-ttu-id="5bed0-139">Le funzionalità di blocco e contenimento comportamentali possono aiutare a identificare e arrestare le minacce, in base ai comportamenti e agli alberi di processo, anche quando la minaccia ha iniziato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5bed0-139">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> | [<span data-ttu-id="5bed0-140">Blocco e contenimento comportamentale</span><span class="sxs-lookup"><span data-stu-id="5bed0-140">Behavioral blocking and containment</span></span>](/defender-endpoint/behavioral-blocking-containment)
<span data-ttu-id="5bed0-141">Analisi e risposta automatizzate</span><span class="sxs-lookup"><span data-stu-id="5bed0-141">Automated Investigation and Response</span></span> | <span data-ttu-id="5bed0-142">L'indagine automatizzata utilizza vari algoritmi di ispezione basati su processi utilizzati dagli analisti della sicurezza e progettati per esaminare gli avvisi e intervenire immediatamente per risolvere le violazioni.</span><span class="sxs-lookup"><span data-stu-id="5bed0-142">Automated investigation uses various inspection algorithms based on processes that are used by security analysts and designed to examine alerts and take immediate action to resolve breaches.</span></span> | [<span data-ttu-id="5bed0-143">Usare indagini automatizzate per analizzare e correggere le minacce</span><span class="sxs-lookup"><span data-stu-id="5bed0-143">Use automated investigations to investigate and remediate threats</span></span>](/defender-endpoint/automated-investigations)
<span data-ttu-id="5bed0-144">Rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="5bed0-144">Advanced Hunting</span></span> | <span data-ttu-id="5bed0-145">La ricerca avanzata è uno strumento di ricerca delle minacce basato su query che consente di esplorare fino a 30 giorni di dati non elaborati in modo da poter esaminare in modo proattivo gli eventi nella rete per individuare gli indicatori e le entità delle minacce.</span><span class="sxs-lookup"><span data-stu-id="5bed0-145">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data so that you can proactively inspect events in your network to locate threat indicators and entities.</span></span> | [<span data-ttu-id="5bed0-146">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="5bed0-146">Overview of advanced hunting</span></span>](/defender-endpoint/advanced-hunting-overview)
<span data-ttu-id="5bed0-147">Analisi delle minacce</span><span class="sxs-lookup"><span data-stu-id="5bed0-147">Threat Analytics</span></span> | <span data-ttu-id="5bed0-148">L'analisi delle minacce è una serie di report di esperti ricercatori di sicurezza Microsoft che coprono le minacce più rilevanti.</span><span class="sxs-lookup"><span data-stu-id="5bed0-148">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats.</span></span> | [<span data-ttu-id="5bed0-149">Monitorare e rispondere alle nuove minacce</span><span class="sxs-lookup"><span data-stu-id="5bed0-149">Track and respond to emerging threats</span></span>](/defender-endpoint/threat-analytics)


<span data-ttu-id="5bed0-150">Per informazioni più dettagliate sulle funzionalità incluse in Microsoft Defender for Endpoint, vedi Che cos'è [Microsoft Defender per Endpoint](/defender-endpoint/microsoft-defender-endpoint).</span><span class="sxs-lookup"><span data-stu-id="5bed0-150">For more detailed information about the capabilities included with Microsoft Defender for Endpoint, see [What is Microsoft Defender for Endpoint](/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="5bed0-151">Integrazione SIEM</span><span class="sxs-lookup"><span data-stu-id="5bed0-151">SIEM integration</span></span>

<span data-ttu-id="5bed0-152">Puoi integrare Microsoft Defender for Endpoint con Azure Sentinel per analizzare in modo più completo gli eventi di sicurezza all'interno dell'organizzazione e creare playbook per una risposta efficace e immediata.</span><span class="sxs-lookup"><span data-stu-id="5bed0-152">You can integrate Microsoft Defender for Endpoint with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> 

<span data-ttu-id="5bed0-153">Microsoft Defender for Endpoint può anche essere integrato in altre soluzioni SIEM (Security Information and Event Management).</span><span class="sxs-lookup"><span data-stu-id="5bed0-153">Microsoft Defender for Endpoint can also be integrated into other Security Information and Event Management (SIEM) solutions.</span></span> <span data-ttu-id="5bed0-154">Per altre informazioni, vedi [Abilitare l'integrazione SIEM in Microsoft Defender per Endpoint.](/defender-endpoint/enable-siem-integration)</span><span class="sxs-lookup"><span data-stu-id="5bed0-154">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](/defender-endpoint/enable-siem-integration).</span></span>


## <a name="next-steps"></a><span data-ttu-id="5bed0-155">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5bed0-155">Next steps</span></span>
[<span data-ttu-id="5bed0-156">Abilitare la valutazione</span><span class="sxs-lookup"><span data-stu-id="5bed0-156">Enable the evaluation</span></span>](eval-defender-endpoint-enable-eval.md)

<span data-ttu-id="5bed0-157">Torna alla panoramica per [valutare Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5bed0-157">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="5bed0-158">Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5bed0-158">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>