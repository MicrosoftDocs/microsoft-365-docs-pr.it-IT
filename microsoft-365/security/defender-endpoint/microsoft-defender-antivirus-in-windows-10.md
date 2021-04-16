---
title: Protezione di nuova generazione
description: Informazioni su come gestire, configurare e usare Antivirus Microsoft Defender, protezione antimalware e antivirus integrata.
keywords: Antivirus Microsoft Defender, windows defender, antimalware, scep, system center endpoint protection, system center configuration manager, virus, malware, minaccia, rilevamento, protezione, sicurezza
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 6fc6ad69df554cf20fbae0d97fcb30f211f48705
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768795"
---
# <a name="next-generation-protection"></a><span data-ttu-id="35b68-104">Protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="35b68-104">Next-generation protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="35b68-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="35b68-105">**Applies to:**</span></span>

- [<span data-ttu-id="35b68-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="35b68-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a><span data-ttu-id="35b68-107">Antivirus Microsoft Defender: protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="35b68-107">Microsoft Defender Antivirus: Your next-generation protection</span></span>

<span data-ttu-id="35b68-108">Antivirus Microsoft Defender è il componente di protezione di nuova generazione di Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="35b68-108">Microsoft Defender Antivirus is the next-generation protection component of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="35b68-109">Questa protezione raggruppa l'apprendimento automatico, l'analisi dei Big Data, la ricerca approfondita sulla resistenza alle minacce e l'infrastruttura cloud Microsoft per proteggere i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="35b68-109">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices in your enterprise organization.</span></span> <span data-ttu-id="35b68-110">I servizi di protezione di nuova generazione includono le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="35b68-110">Your next-generation protection services include the following capabilities:</span></span>

- <span data-ttu-id="35b68-111">[Protezione antivirus basata sul comportamento, euristica e in tempo reale](configure-protection-features-microsoft-defender-antivirus.md), che include l’analisi sempre attiva usando il monitoraggio del comportamento di file e processi e altre euristiche (anche nota come *protezione in tempo reale*).</span><span class="sxs-lookup"><span data-stu-id="35b68-111">[Behavior-based, heuristic, and real-time antivirus protection](configure-protection-features-microsoft-defender-antivirus.md), which includes always-on scanning using file and process behavior monitoring and other heuristics (also known as *real-time protection*).</span></span> <span data-ttu-id="35b68-112">Include anche il rilevamento e il blocco di app considerate non sicure ma che potrebbero non essere rilevate come malware.</span><span class="sxs-lookup"><span data-stu-id="35b68-112">It also includes detecting and blocking apps that are deemed unsafe, but might not be detected as malware.</span></span>
- <span data-ttu-id="35b68-113">[Protezione fornita dal cloud](cloud-protection-microsoft-defender-antivirus.md) che include il rilevamento quasi istantaneo e il blocco di minacce nuove ed emergenti.</span><span class="sxs-lookup"><span data-stu-id="35b68-113">[Cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md), which includes near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="35b68-114">[Aggiornamenti dedicati per protezione e prodotti](manage-updates-baselines-microsoft-defender-antivirus.md) che includono aggiornamenti per mantenere aggiornato Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="35b68-114">[Dedicated protection and product updates](manage-updates-baselines-microsoft-defender-antivirus.md), which includes updates related to keeping Microsoft Defender Antivirus up to date.</span></span>

## <a name="try-a-demo"></a><span data-ttu-id="35b68-115">Prova una demo!</span><span class="sxs-lookup"><span data-stu-id="35b68-115">Try a demo!</span></span>

<span data-ttu-id="35b68-116">Visitare il [sito Web con le demo di Microsoft Defender per endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare il funzionamento delle funzionalità di protezione seguenti e per esplorarle con scenari demo:</span><span class="sxs-lookup"><span data-stu-id="35b68-116">Visit the [Microsoft Defender for Endpoint demo website](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following protection features are working and explore them using demo scenarios:</span></span>
- <span data-ttu-id="35b68-117">Protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="35b68-117">Cloud-delivered protection</span></span>
- <span data-ttu-id="35b68-118">Protezione con la funzionalità BAFS (Block at first sight), ovvero di blocco al primo rilevamento.</span><span class="sxs-lookup"><span data-stu-id="35b68-118">Block at first sight (BAFS) protection</span></span>
- <span data-ttu-id="35b68-119">Protezione da applicazioni potenzialmente indesiderate</span><span class="sxs-lookup"><span data-stu-id="35b68-119">Potentially unwanted applications (PUA) protection</span></span>

## <a name="minimum-system-requirements"></a><span data-ttu-id="35b68-120">Requisiti minimi di sistema</span><span class="sxs-lookup"><span data-stu-id="35b68-120">Minimum system requirements</span></span>

<span data-ttu-id="35b68-121">Antivirus Microsoft Defender ha gli stessi requisiti hardware di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="35b68-121">Microsoft Defender Antivirus has the same hardware requirements as of Windows 10.</span></span> <span data-ttu-id="35b68-122">Per altre informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="35b68-122">For more information, see the following resources:</span></span>

- [<span data-ttu-id="35b68-123">Requisiti hardware minimi</span><span class="sxs-lookup"><span data-stu-id="35b68-123">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [<span data-ttu-id="35b68-124">Linee guida per i componenti hardware</span><span class="sxs-lookup"><span data-stu-id="35b68-124">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a><span data-ttu-id="35b68-125">Configurare i servizi di protezione di nuova generazione</span><span class="sxs-lookup"><span data-stu-id="35b68-125">Configure next-generation protection services</span></span>

<span data-ttu-id="35b68-126">Per informazioni su come configurare i servizi di protezione di nuova generazione, vedere [Configurare le funzionalità di Antivirus Microsoft Defender](configure-microsoft-defender-antivirus-features.md).</span><span class="sxs-lookup"><span data-stu-id="35b68-126">For information on how to configure next-generation protection services, see [Configure Microsoft Defender Antivirus features](configure-microsoft-defender-antivirus-features.md).</span></span>

> [!Note]  
> <span data-ttu-id="35b68-127">La configurazione e la gestione sono in gran parte uguali in Windows Server 2016 e Windows Server 2019, durante l'esecuzione di Antivirus Microsoft Defender; tuttavia, ci sono alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="35b68-127">Configuration and management is largely the same in Windows Server 2016 and Windows Server 2019, while running Microsoft Defender Antivirus; however, there are some differences.</span></span> <span data-ttu-id="35b68-128">Per altre informazioni, vedere [Antivirus Microsoft Defender in Windows Server 2016 e 2019](microsoft-defender-antivirus-on-windows-server.md).</span><span class="sxs-lookup"><span data-stu-id="35b68-128">To learn more, see [Microsoft Defender Antivirus on Windows Server 2016 and 2019](microsoft-defender-antivirus-on-windows-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35b68-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35b68-129">See also</span></span>

- [<span data-ttu-id="35b68-130">Antivirus Microsoft Defender in Windows Server 2016 e 2019</span><span class="sxs-lookup"><span data-stu-id="35b68-130">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="35b68-131">Gestione e configurazione di Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="35b68-131">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="35b68-132">Valutare la protezione di Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="35b68-132">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)
