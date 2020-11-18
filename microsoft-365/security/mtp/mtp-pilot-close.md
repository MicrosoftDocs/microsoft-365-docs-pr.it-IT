---
title: Riepilogo dei risultati del progetto pilota Microsoft 365 Defender
description: Concludere il progetto pilota Microsoft 365 Defender completando la scorecard, analizzando i risultati del report e decidendo come procedere.
keywords: Pilota di Microsoft Threat Protection, decidere cosa fare dopo il progetto pilota Microsoft Threat Protection, cosa fare dopo aver valutato Microsoft Threat Protection in produzione, transizione da Microsoft Threat Protection Pilot to Deployment, Cyber Security, Advanced Persistent Threat, Enterprise Security, Devices, Device, Identity, Users, data, Applications, Incidents, Automatic Investigation and remediation, Advanced Hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 3fe5bfdec566b0988d9f565595624fc8dd597788
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130944"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="a7300-104">Chiusura e ricapitolazione del pilota Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7300-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a7300-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a7300-105">**Applies to:**</span></span>
- <span data-ttu-id="a7300-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7300-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="a7300-107">[![Pianificazione](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="a7300-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="a7300-108">Pianificazione</span><span class="sxs-lookup"><span data-stu-id="a7300-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="a7300-109">[![Preparazione](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="a7300-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="a7300-110">Preparazione</span><span class="sxs-lookup"><span data-stu-id="a7300-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="a7300-111">[![Simula attacco](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="a7300-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="a7300-112">Simula attacco</span><span class="sxs-lookup"><span data-stu-id="a7300-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Chiudi e riepiloga](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="a7300-114">Chiudi e riepiloga</span><span class="sxs-lookup"><span data-stu-id="a7300-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="a7300-115">*Sei qui!*</span><span class="sxs-lookup"><span data-stu-id="a7300-115">*You are here!*</span></span>|


<span data-ttu-id="a7300-116">Si è attualmente in fase di chiusura e di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="a7300-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="a7300-117">È stata appena eseguita una simulazione di attacco di solo memoria avanzata che ha eseguito il codice in remoto in un controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="a7300-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="a7300-118">Si è visto come Microsoft Defender per endpoint e Microsoft Defender per il rilevamento delle identità e la creazione di avvisi su attività malevole fraudolente.</span><span class="sxs-lookup"><span data-stu-id="a7300-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="a7300-119">Si è visto anche come gli avvisi provenienti da origini diverse vengono recapitati insieme ad altre informazioni contestuali in un singolo incidente nel portale del Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7300-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="a7300-120">L'esperienza di tale integrazione consente agli analisti SOC di analizzare e intraprendere le azioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="a7300-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="a7300-121">Inoltre, è stata creata una query di ricerca avanzata che consente di identificare i messaggi di posta elettronica in ingresso in cui l'utente ha aperto o salvato l'allegato e ha creato il rilevamento in base a tale query.</span><span class="sxs-lookup"><span data-stu-id="a7300-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="a7300-122">Dopo aver concluso tutti i test, è stata raggiunta la fine del processo.</span><span class="sxs-lookup"><span data-stu-id="a7300-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="a7300-123">L'output finale deve essere:</span><span class="sxs-lookup"><span data-stu-id="a7300-123">The final output should be:</span></span>

- <span data-ttu-id="a7300-124">Una scorecard completata</span><span class="sxs-lookup"><span data-stu-id="a7300-124">A completed scorecard</span></span>
- <span data-ttu-id="a7300-125">Un rapporto dettagliato dei risultati del progetto pilota</span><span class="sxs-lookup"><span data-stu-id="a7300-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="a7300-126">Una decisione su come procedere</span><span class="sxs-lookup"><span data-stu-id="a7300-126">A decision on how to move forward</span></span>

<span data-ttu-id="a7300-127">Presentare i rapporti dall'output finale alle parti interessate interne (identificate durante la fase di [preparazione](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) ) e ai contatti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7300-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="a7300-128">Questo sforzo garantisce che eventuali commenti e suggerimenti possano essere utilizzati per migliorare i prodotti e la documentazione.</span><span class="sxs-lookup"><span data-stu-id="a7300-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="a7300-129">Si spera che questa simulazione sia stata molto apprezzata.</span><span class="sxs-lookup"><span data-stu-id="a7300-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="a7300-130">Per ottenere il massimo dalla soluzione di sicurezza integrata, iniziare a implementare le operazioni apprese in scala maggiore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a7300-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="a7300-131">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a7300-131">Next step</span></span>
<span data-ttu-id="a7300-132">Per ulteriori informazioni, vedere i pilastri di Microsoft 365 Defender tramite le seguenti guide interattive:</span><span class="sxs-lookup"><span data-stu-id="a7300-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="a7300-133">Salvaguardare l'organizzazione con Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="a7300-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="a7300-134">Individuare attività sospette e potenziali attacchi con Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="a7300-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="a7300-135">Individuare le minacce e gestire gli avvisi con Microsoft cloud app Security</span><span class="sxs-lookup"><span data-stu-id="a7300-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="a7300-136">Esaminare e correggere le minacce con Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a7300-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
