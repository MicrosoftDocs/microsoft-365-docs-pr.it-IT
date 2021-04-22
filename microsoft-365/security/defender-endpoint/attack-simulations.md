---
title: Esperienza di Microsoft Defender per Endpoint tramite attacchi simulati
description: Esegui le simulazioni dello scenario di attacco fornite per scoprire in che modo Microsoft Defender for Endpoint può rilevare, analizzare e rispondere alle violazioni.
keywords: test, scenario, attacco, simulazione, simulato, diy, Microsoft Defender per Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 6ecbf98c81b1f68e42f39269809592fb446e6036
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934382"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="56ea8-104">Esperienza di Microsoft Defender per Endpoint tramite attacchi simulati</span><span class="sxs-lookup"><span data-stu-id="56ea8-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="56ea8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="56ea8-105">**Applies to:**</span></span>
- [<span data-ttu-id="56ea8-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="56ea8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="56ea8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56ea8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="56ea8-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="56ea8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="56ea8-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="56ea8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="56ea8-110">Informazioni sugli ultimi miglioramenti in Microsoft Defender for Endpoint: [Novità di Defender per Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="56ea8-110">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="56ea8-111">Defender for Endpoint ha dimostrato le funzionalità di ottica e rilevamento leader del settore nella recente valutazione MITRE.</span><span class="sxs-lookup"><span data-stu-id="56ea8-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="56ea8-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="56ea8-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="56ea8-113">Potresti voler provare Defender for Endpoint prima di eseguire l'onboardboard di più di alcuni dispositivi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="56ea8-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="56ea8-114">A tale scopo, è possibile eseguire simulazioni di attacco controllate su alcuni dispositivi di test.</span><span class="sxs-lookup"><span data-stu-id="56ea8-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="56ea8-115">Dopo aver eseguito gli attacchi simulati, puoi esaminare il modo in cui Defender for Endpoint mostra attività dannose ed esplorare il modo in cui consente una risposta efficiente.</span><span class="sxs-lookup"><span data-stu-id="56ea8-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="56ea8-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="56ea8-116">Before you begin</span></span>

<span data-ttu-id="56ea8-117">Per eseguire una delle simulazioni fornite, è necessario almeno [un dispositivo onboarded.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="56ea8-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="56ea8-118">Leggere il documento della procedura dettagliata fornito con ogni scenario di attacco.</span><span class="sxs-lookup"><span data-stu-id="56ea8-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="56ea8-119">Ogni documento include i requisiti del sistema operativo e delle applicazioni, nonché istruzioni dettagliate specifiche per uno scenario di attacco.</span><span class="sxs-lookup"><span data-stu-id="56ea8-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="56ea8-120">Eseguire una simulazione</span><span class="sxs-lookup"><span data-stu-id="56ea8-120">Run a simulation</span></span>

1. <span data-ttu-id="56ea8-121">In   >  **Simulazioni guida & esercitazioni** selezionare quali degli scenari di attacco disponibili si desidera simulare:</span><span class="sxs-lookup"><span data-stu-id="56ea8-121">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="56ea8-122">**Scenario 1: la backdoor** del documento viene simulare la consegna di un documento di esca socialmente progettato.</span><span class="sxs-lookup"><span data-stu-id="56ea8-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="56ea8-123">Il documento avvia una backdoor appositamente predisposta che consente agli utenti malintenzionati di controllare.</span><span class="sxs-lookup"><span data-stu-id="56ea8-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="56ea8-124">**Scenario 2: script di PowerShell in** attacco senza file - Simula un attacco senza file che si basa su PowerShell, che mostra la riduzione della superficie di attacco e il rilevamento di dispositivi di apprendimento di attività di memoria dannose.</span><span class="sxs-lookup"><span data-stu-id="56ea8-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="56ea8-125">**Scenario 3: risposta** automatica agli eventi imprevisti : attiva un'indagine automatizzata, che cerca e correda automaticamente gli artefatti di violazione per ridimensionare la capacità di risposta agli incidenti.</span><span class="sxs-lookup"><span data-stu-id="56ea8-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="56ea8-126">Scaricare e leggere il documento della procedura dettagliata corrispondente fornito con lo scenario selezionato.</span><span class="sxs-lookup"><span data-stu-id="56ea8-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="56ea8-127">Scarica il file di simulazione o copia lo script di simulazione accedendo alla **Guida**  >  **Simulazioni & esercitazioni**.</span><span class="sxs-lookup"><span data-stu-id="56ea8-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="56ea8-128">Puoi scegliere di scaricare il file o lo script nel dispositivo di test, ma non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="56ea8-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="56ea8-129">Eseguire il file o lo script di simulazione nel dispositivo di test come indicato nel documento della procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="56ea8-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="56ea8-130">I file o gli script di simulazione simulano l'attività di attacco, ma sono in realtà benigni e non danneggiano o comprometteranno il dispositivo di test.</span><span class="sxs-lookup"><span data-stu-id="56ea8-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="56ea8-131">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="56ea8-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="56ea8-132">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="56ea8-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="56ea8-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="56ea8-133">Related topics</span></span>

- [<span data-ttu-id="56ea8-134">Dispositivi onboard</span><span class="sxs-lookup"><span data-stu-id="56ea8-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="56ea8-135">Aggiungere di dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="56ea8-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
