---
title: Riepilogo dei risultati del progetto pilota Microsoft 365 Defender progetto pilota
description: Concludere il progetto Microsoft 365 Defender progetto pilota completando la scorecard, analizzando i risultati dei report e decidendo come procedere.
keywords: Microsoft 365 Defender pilota, decidere cosa fare dopo il progetto pilota Microsoft 365 Defender, cosa fare dopo aver valutato Microsoft 365 Defender in produzione, transizione da un progetto pilota Microsoft 365 Defender alla distribuzione, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 64cdb37b64780a651b2689e68e21c5a385df5ba9
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458439"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="a1343-104">Chiusura e riepilogo della Microsoft 365 Defender pilota</span><span class="sxs-lookup"><span data-stu-id="a1343-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a1343-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a1343-105">**Applies to:**</span></span>
- <span data-ttu-id="a1343-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1343-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="a1343-107">[![Pianificazione](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="a1343-107">[![Planning](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span></span><br/>[<span data-ttu-id="a1343-108">Pianificazione</span><span class="sxs-lookup"><span data-stu-id="a1343-108">Planning</span></span>](m365d-pilot-plan.md) |<span data-ttu-id="a1343-109">[![Preparazione](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="a1343-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="a1343-110">Preparazione</span><span class="sxs-lookup"><span data-stu-id="a1343-110">Preparation</span></span>](prepare-m365d-eval.md) | <span data-ttu-id="a1343-111">[![Simula attacco](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="a1343-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="a1343-112">Simula attacco</span><span class="sxs-lookup"><span data-stu-id="a1343-112">Simulate attack</span></span>](m365d-pilot-simulate.md) | ![Chiudi e riepiloga](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="a1343-114">Chiudi e riepiloga</span><span class="sxs-lookup"><span data-stu-id="a1343-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="a1343-115">*Sei qui!*</span><span class="sxs-lookup"><span data-stu-id="a1343-115">*You are here!*</span></span>|


<span data-ttu-id="a1343-116">È in corso la fase di chiusura e riepilogo.</span><span class="sxs-lookup"><span data-stu-id="a1343-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="a1343-117">È stata appena eseguita una simulazione avanzata di attacco solo memoria che ha eseguito codice in modalità remota in un controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="a1343-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="a1343-118">Hai visto come Microsoft Defender for Endpoint e Microsoft Defender for Identity rilevano e creano avvisi su attività dannose furtive.</span><span class="sxs-lookup"><span data-stu-id="a1343-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="a1343-119">Hai anche visto come gli avvisi provenienti da origini diverse vengono recapitati insieme ad altre informazioni contestuali in un singolo evento imprevisto nel portale del Centro sicurezza Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a1343-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="a1343-120">L'esperienza di tale integrazione consente agli analisti SOC di analizzare e intraprendere le azioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="a1343-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="a1343-121">È stata inoltre creata una query di ricerca avanzata che identificherà i messaggi di posta elettronica in ingresso in cui l'utente ha aperto o salvato l'allegato e creato il rilevamento in base a tale query.</span><span class="sxs-lookup"><span data-stu-id="a1343-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="a1343-122">È stata raggiunta la fine del processo al termine di tutti i test.</span><span class="sxs-lookup"><span data-stu-id="a1343-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="a1343-123">L'output finale deve essere:</span><span class="sxs-lookup"><span data-stu-id="a1343-123">The final output should be:</span></span>

- <span data-ttu-id="a1343-124">Scorecard completata</span><span class="sxs-lookup"><span data-stu-id="a1343-124">A completed scorecard</span></span>
- <span data-ttu-id="a1343-125">Un report dettagliato dei risultati del progetto pilota</span><span class="sxs-lookup"><span data-stu-id="a1343-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="a1343-126">Una decisione su come procedere</span><span class="sxs-lookup"><span data-stu-id="a1343-126">A decision on how to move forward</span></span>

<span data-ttu-id="a1343-127">Presenta i rapporti dall'output finale alle parti interessate interne (identificate durante la fase [di](./prepare-m365d-eval.md) preparazione) e ai contatti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a1343-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](./prepare-m365d-eval.md) phase) and Microsoft contacts.</span></span> <span data-ttu-id="a1343-128">Questo sforzo garantisce che qualsiasi feedback possa essere usato per migliorare i prodotti e la documentazione.</span><span class="sxs-lookup"><span data-stu-id="a1343-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="a1343-129">Ci auguriamo che questa simulazione sia stata apprezzata.</span><span class="sxs-lookup"><span data-stu-id="a1343-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="a1343-130">Iniziare a implementare quanto appreso su una scala più ampia nell'organizzazione per ottenere il massimo dalla soluzione di sicurezza integrata.</span><span class="sxs-lookup"><span data-stu-id="a1343-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="a1343-131">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a1343-131">Next step</span></span>
<span data-ttu-id="a1343-132">Per ulteriori informazioni sui pilastri Microsoft 365 Defender, vedere le seguenti guide interattive:</span><span class="sxs-lookup"><span data-stu-id="a1343-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="a1343-133">Proteggere l'organizzazione con Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="a1343-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="a1343-134">Individuare attività sospette e potenziali attacchi con Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="a1343-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="a1343-135">Rilevare le minacce e gestire gli avvisi con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a1343-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="a1343-136">Analizzare e correggere le minacce con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a1343-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)