---
title: Scenari e opportunità per i partner di Microsoft Defender for Endpoint
ms.reviewer: ''
description: Scopri come estendere le offerte di sicurezza esistenti oltre al framework aperto e a un ricco set di API per creare estensioni e integrazioni con Microsoft Defender for Endpoint
keywords: API, partner, estendere, open framework, api, estensioni, integrazioni, rilevamento, gestione, risposta, vulnerabilità, intelligence
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: be2f33514a568f290a3fc5cf0adc62db72243a6f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861110"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a><span data-ttu-id="6f094-104">Scenari e opportunità per i partner di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6f094-104">Microsoft Defender for Endpoint partner opportunities and scenarios</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6f094-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6f094-105">**Applies to:**</span></span>
- [<span data-ttu-id="6f094-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6f094-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6f094-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f094-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="6f094-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6f094-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6f094-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="6f094-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="6f094-110">I partner possono estendere facilmente le offerte di sicurezza esistenti oltre al framework aperto e a un set completo e completo di API per creare estensioni e integrazioni con Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f094-110">Partners can easily extend their existing security offerings on top of the open framework and a rich and complete set of APIs to build extensions and integrations with Defender for Endpoint.</span></span> 

<span data-ttu-id="6f094-111">Le API si estendono su aree funzionali, tra cui rilevamento, gestione, risposta, vulnerabilità e un'ampia gamma di casi d'uso a livello di intelligence.</span><span class="sxs-lookup"><span data-stu-id="6f094-111">The APIs span functional areas including detection, management, response, vulnerabilities, and intelligence-wide range of use cases.</span></span> <span data-ttu-id="6f094-112">In base al caso d'uso e alle necessità, i partner possono trasmettere o eseguire query sui dati da Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f094-112">Based on the use case and need, partners can either stream or query data from Defender for Endpoint.</span></span> 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a><span data-ttu-id="6f094-113">Scenario 1: correlazione degli avvisi esterni e analisi e correzione automatizzate</span><span class="sxs-lookup"><span data-stu-id="6f094-113">Scenario 1: External alert correlation and Automated investigation and remediation</span></span>
<span data-ttu-id="6f094-114">Defender for Endpoint offre funzionalità di analisi e correzione automatizzate uniche per guidare la risposta agli incidenti su larga scala.</span><span class="sxs-lookup"><span data-stu-id="6f094-114">Defender for Endpoint offers unique automated investigation and remediation capabilities to drive incident response at scale.</span></span> 

<span data-ttu-id="6f094-115">L'integrazione della funzionalità di analisi e risposta automatizzata con altre soluzioni, ad esempio prodotti di sicurezza di rete o altri prodotti per la sicurezza degli endpoint, aiuterà a risolvere gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="6f094-115">Integrating the automated investigation and response capability with other solutions such as network security products or other endpoint security products will help to address alerts.</span></span> <span data-ttu-id="6f094-116">L'integrazione riduce al minimo anche le complessità che circondano la correlazione del segnale di rete e del dispositivo, snellendo in modo efficace le azioni di indagine e correzione delle minacce nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6f094-116">The integration also minimizes the complexities surrounding network and device signal correlation, effectively streamlining the investigation and threat remediation actions on devices.</span></span>

<span data-ttu-id="6f094-117">Defender for Endpoint aggiunge il supporto per questo scenario nei moduli seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f094-117">Defender for Endpoint adds support for this scenario in the following forms:</span></span>

- <span data-ttu-id="6f094-118">Gli avvisi esterni possono essere inseriti in Defender per Endpoint e presentati affiancati a avvisi aggiuntivi basati su dispositivo da Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f094-118">External alerts can be pushed into Defender for Endpoint and presented side by side with additional device-based alerts from Defender for Endpoint.</span></span> <span data-ttu-id="6f094-119">Questa visualizzazione fornisce il contesto completo dell'avviso, con il processo reale e la storia completa dell'attacco.</span><span class="sxs-lookup"><span data-stu-id="6f094-119">This view provides the full context of the alert - with the real process and the full story of attack.</span></span>

- <span data-ttu-id="6f094-120">Una volta generato un avviso, il segnale viene condiviso tra tutti gli endpoint protetti da Defender per Endpoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6f094-120">Once an alert is generated, the signal is shared across all Defender for Endpoint protected endpoints in the enterprise.</span></span> <span data-ttu-id="6f094-121">Defender for Endpoint richiede una risposta immediata automatizzata o assistita dall'operatore per risolvere l'avviso.</span><span class="sxs-lookup"><span data-stu-id="6f094-121">Defender for Endpoint takes immediate automated or operator-assisted response to address the alert.</span></span>

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a><span data-ttu-id="6f094-122">Scenario 2: integrazione dell'orchestrazione della sicurezza e della risposta di automazione (SOAR)</span><span class="sxs-lookup"><span data-stu-id="6f094-122">Scenario 2: Security orchestration and automation response (SOAR) integration</span></span>
<span data-ttu-id="6f094-123">Le soluzioni di orchestrazione possono aiutare a creare playbook e integrare il modello di dati rtf e le azioni che le API di Defender for Endpoint espongono per orchestrare le risposte, ad esempio query per i dati del dispositivo, attivare l'isolamento del dispositivo, bloccare/consentire, risolvere gli avvisi e altri.</span><span class="sxs-lookup"><span data-stu-id="6f094-123">Orchestration solutions can help build playbooks and integrate the rich data model and actions that Defender for Endpoint APIs expose to orchestrate responses, such as query for device data, trigger device isolation, block/allow, resolve alert and others.</span></span>

## <a name="scenario-3-indicators-matching"></a><span data-ttu-id="6f094-124">Scenario 3: corrispondenza degli indicatori</span><span class="sxs-lookup"><span data-stu-id="6f094-124">Scenario 3: Indicators matching</span></span> 
<span data-ttu-id="6f094-125">La corrispondenza degli indicatori di compromissione (IoC) è una funzionalità essenziale in ogni soluzione di protezione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f094-125">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="6f094-126">Questa funzionalità è disponibile in Defender for Endpoint e consente di impostare un elenco di indicatori per la prevenzione, il rilevamento e l'esclusione delle entità.</span><span class="sxs-lookup"><span data-stu-id="6f094-126">This capability is available in Defender for Endpoint and gives the ability to set a list of indicators for prevention, detection, and exclusion of entities.</span></span> <span data-ttu-id="6f094-127">È possibile definire l'azione da eseguire e la durata per l'applicazione dell'azione.</span><span class="sxs-lookup"><span data-stu-id="6f094-127">One can define the action to be taken as well as the duration for when to apply the action.</span></span>

<span data-ttu-id="6f094-128">Gli scenari precedenti fungono da esempi di estendibilità della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="6f094-128">The above scenarios serve as examples of the extensibility of the platform.</span></span> <span data-ttu-id="6f094-129">Non sei limitato agli esempi e ti invitiamo sicuramente a sfruttare il framework aperto per individuare ed esplorare altri scenari.</span><span class="sxs-lookup"><span data-stu-id="6f094-129">You are not limited to the examples and we certainly encourage you to leverage the open framework to discover and explore other scenarios.</span></span>

<span data-ttu-id="6f094-130">Segui i passaggi descritti in [Diventare un partner Microsoft Defender for Endpoint per](get-started-partner-integration.md) integrare la soluzione in Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f094-130">Follow the steps in [Become a Microsoft Defender for Endpoint partner](get-started-partner-integration.md) to integrate your solution in Defender for Endpoint.</span></span>

## <a name="related-topic"></a><span data-ttu-id="6f094-131">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="6f094-131">Related topic</span></span>
- [<span data-ttu-id="6f094-132">Panoramica di gestione e API</span><span class="sxs-lookup"><span data-stu-id="6f094-132">Overview of management and APIs</span></span>](management-apis.md)
