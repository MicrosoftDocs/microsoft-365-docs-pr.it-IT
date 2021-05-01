---
title: Preparare la posizione di sicurezza per il primo incidente
description: Configurare la posizione Microsoft 365 sicurezza del tenant per il primo incidente in Microsoft 365 Defender.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 88001dc7126a55539213d4c560127d573a09f4bd
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114803"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="84e78-104">Preparare la posizione di sicurezza per il primo incidente</span><span class="sxs-lookup"><span data-stu-id="84e78-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="84e78-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="84e78-105">**Applies to:**</span></span>
- <span data-ttu-id="84e78-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84e78-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="84e78-107">La preparazione per la gestione degli eventi imprevisti prevede la configurazione di una protezione sufficiente della rete di un'organizzazione da diversi tipi di incidenti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="84e78-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="84e78-108">Per ridurre il rischio di incidenti di sicurezza, il National Institute of Standards and Technology (NIST) consiglia diverse procedure di sicurezza, tra cui valutazioni dei rischi, protezione avanzata della sicurezza dell'host, configurazione sicura delle reti e prevenzione del malware.</span><span class="sxs-lookup"><span data-stu-id="84e78-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="84e78-109">Microsoft 365 Defender può aiutare a risolvere diversi aspetti della prevenzione degli incidenti:</span><span class="sxs-lookup"><span data-stu-id="84e78-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="84e78-110">Implementazione di un framework [zero trust](https://docs.microsoft.com/security/zero-trust/)</span><span class="sxs-lookup"><span data-stu-id="84e78-110">Implementing a [Zero Trust](https://docs.microsoft.com/security/zero-trust/) framework</span></span>
- <span data-ttu-id="84e78-111">Determinare la posizione di sicurezza assegnando un punteggio con [Microsoft Secure Score](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="84e78-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="84e78-112">Prevenzione delle minacce tramite valutazioni delle vulnerabilità in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="84e78-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="84e78-113">Informazioni sulle minacce alla sicurezza più recenti in modo da poterle preparare</span><span class="sxs-lookup"><span data-stu-id="84e78-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="84e78-114">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="84e78-114">Step 1.</span></span> <span data-ttu-id="84e78-115">Implementare zero trust</span><span class="sxs-lookup"><span data-stu-id="84e78-115">Implement Zero Trust</span></span>

<span data-ttu-id="84e78-116">[Zero Trust](https://docs.microsoft.com/security/zero-trust/) è una filosofia di sicurezza integrata e una strategia end-to-end che considera la natura complessa di qualsiasi ambiente moderno, inclusa la forza lavoro mobile e gli utenti, i dispositivi, le applicazioni e i dati, ovunque si trovino.</span><span class="sxs-lookup"><span data-stu-id="84e78-116">[Zero Trust](https://docs.microsoft.com/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="84e78-117">Fornendo un singolo riquadro di vetro per gestire tutti i rilevamenti degli endpoint in modo coerente, Microsoft 365 [](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) Defender può rendere più semplice per il team delle operazioni di sicurezza implementare i principi guida di Zero Trust.</span><span class="sxs-lookup"><span data-stu-id="84e78-117">By providing a single pane of glass to manage all endpoint detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="84e78-118">I componenti di Microsoft 365 Defender possono visualizzare le violazioni delle regole implementate per stabilire criteri di accesso condizionale per Zero Trust integrando i dati di Microsoft Defender for Endpoint (MDE) o di altri fornitori di sicurezza per dispositivi mobili come origine di informazioni per i criteri di conformità dei dispositivi e l'implementazione di criteri di accesso condizionale basati su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84e78-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint (MDE) or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="84e78-119">Il rischio del dispositivo influisce direttamente sulle risorse accessibili dall'utente del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84e78-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="84e78-120">Il rifiuto dell'accesso alle risorse in base a determinati criteri è il tema principale di Zero Trust e Microsoft 365 Defender fornisce le informazioni necessarie per determinare i criteri del livello di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="84e78-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="84e78-121">Ad esempio, Microsoft 365 Defender può fornire il livello di versione software di un dispositivo tramite la pagina Gestione minacce e vulnerabilità, mentre i criteri di accesso condizionale limitano i dispositivi con versioni obsolete o vulnerabili.</span><span class="sxs-lookup"><span data-stu-id="84e78-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="84e78-122">L'automazione è una parte fondamentale dell'implementazione e della gestione di un ambiente zero trust, riducendo al contempo il numero di avvisi che potrebbero causare eventi di risposta a eventi imprevisti( IR).</span><span class="sxs-lookup"><span data-stu-id="84e78-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="84e78-123">I componenti di Microsoft 365 Defender possono essere automatizzati, ad esempio le azioni di correzione (note come indagini per un incidente nel centro sicurezza Microsoft 365), le azioni di notifica e persino la creazione di ticket di supporto, ad esempio in [ServiceNow.](https://microsoft.service-now.com/sp/)</span><span class="sxs-lookup"><span data-stu-id="84e78-123">Components of Microsoft 365 Defender can be automated such as remediation actions (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="84e78-124">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="84e78-124">Step 2.</span></span> <span data-ttu-id="84e78-125">Determinare la posizione di sicurezza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="84e78-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="84e78-126">Successivamente, le organizzazioni possono usare [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender per determinare la posizione di sicurezza corrente e prendere in considerazione suggerimenti su come migliorarlo.</span><span class="sxs-lookup"><span data-stu-id="84e78-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="84e78-127">Più alto è il punteggio, maggiori sono i suggerimenti per la sicurezza e le azioni di miglioramento adottate dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84e78-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="84e78-128">I consigli relativi al punteggio sicuro possono essere presi in prodotti diversi e consentire alle organizzazioni di aumentare ancora di più i propri punteggi.</span><span class="sxs-lookup"><span data-stu-id="84e78-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Esempio di Microsoft Secure Score nel Centro sicurezza Microsoft":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="84e78-130">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="84e78-130">Step 3.</span></span> <span data-ttu-id="84e78-131">Valutare l'esposizione alle vulnerabilità dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="84e78-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="84e78-132">La prevenzione degli incidenti può contribuire a semplificare gli sforzi delle operazioni di sicurezza per concentrarsi sugli incidenti di sicurezza critici e importanti in corso.</span><span class="sxs-lookup"><span data-stu-id="84e78-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="84e78-133">Le vulnerabilità software sono spesso un punto di ingresso prevenibile per gli attacchi che possono portare al furto di dati, alla perdita di dati o all'interruzione delle operazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="84e78-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="84e78-134">Se non sono in corso attacchi, le operazioni di sicurezza [](../defender-endpoint/tvm-exposure-score.md) devono cercare di raggiungere e mantenere un livello accettabile di esposizione alle vulnerabilità nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84e78-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="84e78-135">Per controllare l'avanzamento dell'applicazione di patch al software, visita la pagina [Gestione](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) delle minacce e delle vulnerabilità in Defender for Endpoint, a cui puoi accedere da Microsoft 365 Defender tramite la **scheda Altre** risorse.</span><span class="sxs-lookup"><span data-stu-id="84e78-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Esempio della pagina Minacce e vulnerabilità nel Centro sicurezza Microsoft"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="84e78-137">4. Comprendere le minacce emergenti</span><span class="sxs-lookup"><span data-stu-id="84e78-137">4. Understand emerging threats</span></span>

<span data-ttu-id="84e78-138">Usa [l'analisi](threat-analytics.md) delle minacce Microsoft 365 centro sicurezza per mantenerti aggiornati con l'attuale panorama delle minacce alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="84e78-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="84e78-139">I ricercatori esperti della sicurezza Microsoft creano report che descrivono in dettaglio le minacce informatiche più recenti, in modo da poter comprendere in che modo potrebbero influire sulla sottoscrizione, i dispositivi e gli utenti di Microsoft 365 utenti.</span><span class="sxs-lookup"><span data-stu-id="84e78-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="84e78-140">Questi report possono includere:</span><span class="sxs-lookup"><span data-stu-id="84e78-140">These reports can include:</span></span>

- <span data-ttu-id="84e78-141">Attori delle minacce attive e le loro campagne</span><span class="sxs-lookup"><span data-stu-id="84e78-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="84e78-142">Tecniche di attacco popolari e nuove</span><span class="sxs-lookup"><span data-stu-id="84e78-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="84e78-143">Vulnerabilità critiche</span><span class="sxs-lookup"><span data-stu-id="84e78-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="84e78-144">Superfici di attacco comuni</span><span class="sxs-lookup"><span data-stu-id="84e78-144">Common attack surfaces</span></span>
- <span data-ttu-id="84e78-145">Malware diffuso</span><span class="sxs-lookup"><span data-stu-id="84e78-145">Prevalent malware</span></span>

<span data-ttu-id="84e78-146">Puoi implementare i consigli di una minaccia emergente per rafforzare la posizione di sicurezza e ridurre al minimo la superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="84e78-146">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="84e78-147">Prendere tempo nella pianificazione per controllare regolarmente la sezione [Threat Analytics](threat-analytics.md) del centro sicurezza Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="84e78-147">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="84e78-148">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="84e78-148">Next step</span></span>

<span data-ttu-id="84e78-149">[![Passaggio 1: informazioni su come analizzare e analizzare gli eventi imprevisti](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="84e78-149">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="84e78-150">Informazioni su come [analizzare e analizzare gli eventi imprevisti.](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="84e78-150">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84e78-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84e78-151">See also</span></span>

- [<span data-ttu-id="84e78-152">Panoramica degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="84e78-152">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="84e78-153">Analizzare gli incidenti</span><span class="sxs-lookup"><span data-stu-id="84e78-153">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="84e78-154">Gestire gli incidenti</span><span class="sxs-lookup"><span data-stu-id="84e78-154">Manage incidents</span></span>](manage-incidents.md)
