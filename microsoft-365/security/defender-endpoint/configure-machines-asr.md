---
title: Ottimizzare la distribuzione e i rilevamenti delle regole asr
description: Ottimizzare le regole di riduzione della superficie di attacco (ASR) per identificare e impedire exploit di malware tipici.
keywords: onboard, gestione di Intune, Microsoft Defender for Endpoint, Microsoft Defender, Windows Defender, riduzione della superficie di attacco, ASR, baseline di sicurezza
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 91295135c833c6b403078bdfd517c7b84ec7d630
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932848"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="54ad4-104">Ottimizzare la distribuzione e i rilevamenti delle regole asr</span><span class="sxs-lookup"><span data-stu-id="54ad4-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54ad4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="54ad4-105">**Applies to:**</span></span>
- [<span data-ttu-id="54ad4-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="54ad4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="54ad4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54ad4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="54ad4-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="54ad4-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="54ad4-109">[Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="54ad4-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="54ad4-110">[Le regole di riduzione della superficie di](./attack-surface-reduction.md) attacco identificano e impediscono exploit di malware tipici.</span><span class="sxs-lookup"><span data-stu-id="54ad4-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="54ad4-111">Controllano quando e come può essere eseguito codice potenzialmente dannoso.</span><span class="sxs-lookup"><span data-stu-id="54ad4-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="54ad4-112">Ad esempio, possono impedire a JavaScript o VBScript di avviare un file eseguibile scaricato, bloccare le chiamate API Win32 dalle macro di Office e bloccare i processi eseguiti da unità USB.</span><span class="sxs-lookup"><span data-stu-id="54ad4-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="54ad4-113">![Scheda di gestione della superficie di attacco](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="54ad4-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="54ad4-114">*Scheda di gestione della superficie di attacco*</span><span class="sxs-lookup"><span data-stu-id="54ad4-114">*Attack surface management card*</span></span>

<span data-ttu-id="54ad4-115">La *scheda di gestione della superficie* di attacco è un punto di ingresso agli strumenti nel Centro sicurezza Microsoft 365 che è possibile usare per:</span><span class="sxs-lookup"><span data-stu-id="54ad4-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="54ad4-116">Comprendere in che modo le regole DISR sono attualmente distribuite nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="54ad4-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="54ad4-117">Esaminare i rilevamenti asr e identificare possibili rilevamenti non corretti.</span><span class="sxs-lookup"><span data-stu-id="54ad4-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="54ad4-118">Analizzare l'impatto delle esclusioni e generare l'elenco dei percorsi di file da escludere.</span><span class="sxs-lookup"><span data-stu-id="54ad4-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="54ad4-119">Seleziona **Vai a gestione della superficie di** attacco Monitoraggio & report > regole di riduzione della superficie di attacco > Aggiungi  >  **esclusioni.**</span><span class="sxs-lookup"><span data-stu-id="54ad4-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="54ad4-120">Da qui è possibile passare ad altre sezioni del Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="54ad4-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="54ad4-121">![Aggiungere la scheda esclusioni nella pagina Regole di riduzione della superficie di attacco nel Centro sicurezza Microsoft 365](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="54ad4-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="54ad4-122">Scheda Aggiungi esclusioni nella pagina Regole di riduzione della superficie di attacco nel Centro sicurezza *Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="54ad4-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="54ad4-123">Per accedere al Centro sicurezza Microsoft 365, è necessaria una licenza di Microsoft 365 E3 o E5 e un account con determinati ruoli in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="54ad4-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="54ad4-124">[Leggere le licenze e le autorizzazioni necessarie.](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="54ad4-124">[Read about required licenses and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="54ad4-125">Per ulteriori informazioni sulla distribuzione delle regole asr nel Centro sicurezza Microsoft 365, vedere Monitorare e gestire la distribuzione e i rilevamenti delle regole [ASR.](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)</span><span class="sxs-lookup"><span data-stu-id="54ad4-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="54ad4-126">**Argomenti correlati**</span><span class="sxs-lookup"><span data-stu-id="54ad4-126">**Related topics**</span></span>

* [<span data-ttu-id="54ad4-127">Verificare che i dispositivi siano configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="54ad4-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="54ad4-128">Eseguire l'onboarded dei dispositivi in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="54ad4-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="54ad4-129">Monitorare la conformità alla linea di base di sicurezza di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="54ad4-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
