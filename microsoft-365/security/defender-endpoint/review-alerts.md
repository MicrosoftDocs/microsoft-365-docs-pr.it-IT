---
title: Esaminare gli avvisi in Microsoft Defender for Endpoint
description: Esaminare le informazioni sull'avviso, tra cui una storia di avviso e i dettagli per ogni passaggio della catena.
keywords: incidente, incidenti, computer, dispositivi, utenti, avvisi, avviso, indagine, grafico, prova
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b791f2b62cb4a3f8062c80ceeb04ccfa72f704bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062133"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="eebf1-104">Esaminare gli avvisi in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eebf1-104">Review alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="eebf1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="eebf1-105">**Applies to:**</span></span>
- [<span data-ttu-id="eebf1-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="eebf1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="eebf1-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="eebf1-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eebf1-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="eebf1-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="eebf1-109">La pagina di avviso in Microsoft Defender for Endpoint fornisce il contesto completo dell'avviso, combinando segnali di attacco e avvisi correlati all'avviso selezionato, per creare una storia di avviso dettagliata.</span><span class="sxs-lookup"><span data-stu-id="eebf1-109">The alert page in Microsoft Defender for Endpoint provides full context to the alert, by combining attack signals and alerts related to the selected alert, to construct a detailed alert story.</span></span>

<span data-ttu-id="eebf1-110">Analizzare, analizzare ed eseguire rapidamente azioni efficaci sugli avvisi che influiscono sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="eebf1-110">Quickly triage, investigate, and take effective action on alerts that affect your organization.</span></span> <span data-ttu-id="eebf1-111">Comprendere il motivo per cui sono stati attivati e il loro impatto da una posizione.</span><span class="sxs-lookup"><span data-stu-id="eebf1-111">Understand why they were triggered, and their impact from one location.</span></span> <span data-ttu-id="eebf1-112">Altre informazioni in questa panoramica.</span><span class="sxs-lookup"><span data-stu-id="eebf1-112">Learn more in this overview.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a><span data-ttu-id="eebf1-113">Introduzione a un avviso</span><span class="sxs-lookup"><span data-stu-id="eebf1-113">Getting started with an alert</span></span>

<span data-ttu-id="eebf1-114">Selezionando il nome di un avviso in Defender for Endpoint, verrà visualizzata la relativa pagina di avviso.</span><span class="sxs-lookup"><span data-stu-id="eebf1-114">Selecting an alert's name in Defender for Endpoint will land you on its alert page.</span></span> <span data-ttu-id="eebf1-115">Nella pagina dell'avviso verranno visualizzate tutte le informazioni nel contesto dell'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="eebf1-115">On the alert page, all the information will be shown in context of the selected alert.</span></span> <span data-ttu-id="eebf1-116">Ogni pagina di avviso è costituita da 4 sezioni:</span><span class="sxs-lookup"><span data-stu-id="eebf1-116">Each alert page consists of 4 sections:</span></span>

1. <span data-ttu-id="eebf1-117">**Il titolo dell'avviso** mostra il nome dell'avviso ed è presente per ricordarti quale avviso ha avviato l'indagine corrente indipendentemente da ciò che hai selezionato nella pagina.</span><span class="sxs-lookup"><span data-stu-id="eebf1-117">**The alert title** shows the alert's name and is there to remind you which alert started your current investigation regardless of what you have selected on the page.</span></span>
2. <span data-ttu-id="eebf1-118">[**Gli asset interessati elencano**](#review-affected-assets) le schede dei dispositivi e degli utenti interessati da questo avviso che possono essere selezionate per ulteriori informazioni e azioni.</span><span class="sxs-lookup"><span data-stu-id="eebf1-118">[**Affected assets**](#review-affected-assets) lists cards of devices and users affected by this alert that are clickable for further information and actions.</span></span>
3. <span data-ttu-id="eebf1-119">La **storia dell'avviso** visualizza tutte le entità correlate all'avviso, interconnesse da una visualizzazione albero.</span><span class="sxs-lookup"><span data-stu-id="eebf1-119">The **alert story** displays all entities related to the alert, interconnected by a tree view.</span></span> <span data-ttu-id="eebf1-120">L'avviso nel titolo sarà quello attivo quando si atterra per la prima volta nella pagina dell'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="eebf1-120">The alert in the title will be the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="eebf1-121">Le entità nella storia dell'avviso sono espandibili e selezionabili, per fornire informazioni aggiuntive e accelerare la risposta consentendoti di eseguire azioni direttamente nel contesto della pagina di avviso.</span><span class="sxs-lookup"><span data-stu-id="eebf1-121">Entities in the alert story are expandable and clickable, to provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> <span data-ttu-id="eebf1-122">Usa la storia di avviso per avviare l'indagine.</span><span class="sxs-lookup"><span data-stu-id="eebf1-122">Use the alert story to start your investigation.</span></span> <span data-ttu-id="eebf1-123">Scopri come analizzare [gli avvisi in Microsoft Defender for Endpoint.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="eebf1-123">Learn how in [Investigate alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>
4. <span data-ttu-id="eebf1-124">Il **riquadro dei** dettagli mostrerà i dettagli dell'avviso selezionato in un primo momento, con i dettagli e le azioni correlati a questo avviso.</span><span class="sxs-lookup"><span data-stu-id="eebf1-124">The **details pane** will show the details of the selected alert at first, with details and actions related to this alert.</span></span> <span data-ttu-id="eebf1-125">Se si seleziona una delle risorse o entità interessate nella storia di avviso, il riquadro dei dettagli verrà modificato per fornire informazioni contestuali e azioni per l'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="eebf1-125">If you select any of the affected assets or entities in the alert story, the details pane will change to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="eebf1-126">Prendere nota dello stato di rilevamento dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="eebf1-126">Note the detection status for your alert.</span></span> 
- <span data-ttu-id="eebf1-127">Non consentito: il tentativo di azione sospetta è stato evitato.</span><span class="sxs-lookup"><span data-stu-id="eebf1-127">Prevented – The attempted suspicious action was avoided.</span></span> <span data-ttu-id="eebf1-128">Ad esempio, un file non è stato scritto su disco o eseguito.</span><span class="sxs-lookup"><span data-stu-id="eebf1-128">For example, a file either wasn’t written to disk or executed.</span></span>
<span data-ttu-id="eebf1-129">![Una pagina di avviso che mostra la minaccia è stata impedita](images/detstat-prevented.png)</span><span class="sxs-lookup"><span data-stu-id="eebf1-129">![An alert page showing threat was prevented](images/detstat-prevented.png)</span></span>
- <span data-ttu-id="eebf1-130">Bloccato: il comportamento sospetto è stato eseguito e quindi bloccato.</span><span class="sxs-lookup"><span data-stu-id="eebf1-130">Blocked – Suspicious behavior was executed and then blocked.</span></span> <span data-ttu-id="eebf1-131">Ad esempio, un processo è stato eseguito ma, poiché in seguito presentava comportamenti sospetti, il processo è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="eebf1-131">For example, a process was executed but because it subsequently exhibited suspicious behaviors, the process was terminated.</span></span>
<span data-ttu-id="eebf1-132">![Una pagina di avviso che mostra la minaccia è stata bloccata](images/detstat-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="eebf1-132">![An alert page showing threat was blocked](images/detstat-blocked.png)</span></span>
- <span data-ttu-id="eebf1-133">Rilevato: è stato rilevato un attacco ed è probabilmente ancora attivo.</span><span class="sxs-lookup"><span data-stu-id="eebf1-133">Detected – An attack was detected and is possibly still active.</span></span>
<span data-ttu-id="eebf1-134">![È stata rilevata una pagina di avviso che mostra la minaccia](images/detstat-detected.png)</span><span class="sxs-lookup"><span data-stu-id="eebf1-134">![An alert page showing threat was detected](images/detstat-detected.png)</span></span>




<span data-ttu-id="eebf1-135">È inoltre possibile  esaminare i dettagli dell'indagine automatizzata nel riquadro dei dettagli dell'avviso per vedere quali azioni sono già state eseguite, nonché leggere la descrizione dell'avviso per le azioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="eebf1-135">You can then also review the *automated investigation details* in your alert's details pane, to see which actions were already taken, as well as reading the alert's description for recommended actions.</span></span>

![Frammento del riquadro dei dettagli con la descrizione dell'avviso e le sezioni di indagine automatica evidenziate](images/alert-air-and-alert-description.png)

<span data-ttu-id="eebf1-137">Altre informazioni disponibili nel riquadro dei dettagli all'apertura dell'avviso includono tecniche MITRE, origine e ulteriori dettagli contestuali.</span><span class="sxs-lookup"><span data-stu-id="eebf1-137">Other information available in the details pane when the alert opens includes MITRE techniques, source, and additional contextual details.</span></span>




## <a name="review-affected-assets"></a><span data-ttu-id="eebf1-138">Esaminare gli asset interessati</span><span class="sxs-lookup"><span data-stu-id="eebf1-138">Review affected assets</span></span>

<span data-ttu-id="eebf1-139">Selezionando un dispositivo o una scheda utente nelle sezioni degli asset interessati, si passa ai dettagli del dispositivo o dell'utente nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="eebf1-139">Selecting a device or a user card in the affected assets sections will switch to the details of the device or user in the details pane.</span></span>

- <span data-ttu-id="eebf1-140">**Per i** dispositivi , nel riquadro dei dettagli verranno visualizzate informazioni sul dispositivo stesso, ad esempio Dominio, Sistema operativo e IP.</span><span class="sxs-lookup"><span data-stu-id="eebf1-140">**For devices**, the details pane will display information about the device itself, like Domain, Operating System, and IP.</span></span> <span data-ttu-id="eebf1-141">Sono disponibili anche gli avvisi attivi e gli utenti connessi su tale dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eebf1-141">Active alerts and the logged on users on that device are also available.</span></span> <span data-ttu-id="eebf1-142">Puoi intervenire immediatamente isolando il dispositivo, limitando l'esecuzione dell'app o eseguendo un'analisi antivirus.</span><span class="sxs-lookup"><span data-stu-id="eebf1-142">You can take immediate action by isolating the device, restricting app execution, or running an antivirus scan.</span></span> <span data-ttu-id="eebf1-143">In alternativa, puoi raccogliere un pacchetto di indagine, avviare un'indagine automatizzata o passare alla pagina del dispositivo per analizzare dal punto di vista del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eebf1-143">Alternatively, you could collect an investigation package, initiate an automated investigation, or go to the device page to investigate from the device's point of view.</span></span>

   ![Frammento del riquadro dei dettagli quando viene selezionato un dispositivo](images/device-page-details.png)

- <span data-ttu-id="eebf1-145">Per gli utenti **,** nel riquadro dei dettagli verranno visualizzate informazioni dettagliate sull'utente, ad esempio il nome SAM e il SID dell'utente, nonché i tipi di accesso eseguiti dall'utente e gli avvisi e gli eventi imprevisti ad esso correlati.</span><span class="sxs-lookup"><span data-stu-id="eebf1-145">**For users**, the details pane will display detailed user information, such as the user's SAM name and SID, as well as logon types performed by this user and any alerts and incidents related to it.</span></span> <span data-ttu-id="eebf1-146">È possibile selezionare *Apri pagina utente* per continuare l'indagine dal punto di vista dell'utente.</span><span class="sxs-lookup"><span data-stu-id="eebf1-146">You can select *Open user page* to continue the investigation from that user's point of view.</span></span>

   ![Frammento del riquadro dei dettagli quando viene selezionato un utente](images/user-page-details.png)


## <a name="related-topics"></a><span data-ttu-id="eebf1-148">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="eebf1-148">Related topics</span></span>

- [<span data-ttu-id="eebf1-149">Visualizzare e organizzare la coda degli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="eebf1-149">View and organize the incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="eebf1-150">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="eebf1-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="eebf1-151">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="eebf1-151">Manage incidents</span></span>](manage-incidents.md)
