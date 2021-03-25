---
title: Analizzare gli avvisi di Microsoft Defender for Endpoint
description: Usa le opzioni di indagine per ottenere informazioni dettagliate sugli avvisi che influiscono sulla rete, sul loro significato e su come risolverli.
keywords: indagare, indagine, dispositivi, dispositivo, coda avvisi, dashboard, indirizzo IP, file, inviare, invii, analisi approfondita, sequenza temporale, ricerca, dominio, URL, IP
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 498f2d83af6e2eb7fc56b232bafd9fc49d9d4fd9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067698"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8dc7f-104">Analizzare gli avvisi in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8dc7f-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8dc7f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8dc7f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8dc7f-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8dc7f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="8dc7f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8dc7f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8dc7f-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8dc7f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8dc7f-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="8dc7f-110">Analizzare gli avvisi che interessano la rete, comprenderne il significato e come risolverli.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="8dc7f-111">Selezionare un avviso dalla coda degli avvisi per passare alla pagina di avviso.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="8dc7f-112">Questa visualizzazione contiene il titolo dell'avviso, gli asset interessati, il riquadro laterale dei dettagli e la storia dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="8dc7f-113">Nella pagina di avviso iniziare l'indagine selezionando le risorse interessate o una delle entità nella visualizzazione albero della storia di avviso.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="8dc7f-114">Il riquadro dei dettagli viene popolato automaticamente con ulteriori informazioni sugli elementi selezionati.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="8dc7f-115">Per sapere quali tipi di informazioni è possibile visualizzare qui, vedere [Esaminare gli avvisi in Microsoft Defender per Endpoint.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts)</span><span class="sxs-lookup"><span data-stu-id="8dc7f-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="8dc7f-116">Analizzare usando la storia di avviso</span><span class="sxs-lookup"><span data-stu-id="8dc7f-116">Investigate using the alert story</span></span>

<span data-ttu-id="8dc7f-117">La storia dell'avviso dettaglia il motivo per cui l'avviso è stato attivato, gli eventi correlati che si sono verificati prima e dopo, nonché altre entità correlate.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="8dc7f-118">Le entità sono selezionabili e ogni entità che non è un avviso è espandibile usando l'icona di espansione sul lato destro della scheda dell'entità.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="8dc7f-119">L'entità con lo stato attivo verrà indicata da una striscia blu a sinistra della scheda dell'entità, con l'avviso nel titolo che è stato attivato in un primo momento.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="8dc7f-120">Espandi entità per visualizzare i dettagli a colpo d'occhio.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="8dc7f-121">Se si seleziona un'entità, il contesto del riquadro dei dettagli verrà commutato in questa entità e sarà possibile esaminare ulteriori informazioni e gestire tale entità.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="8dc7f-122">Selezionando *...* a destra della scheda dell'entità verranno mostrate tutte le azioni disponibili per tale entità.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="8dc7f-123">Queste stesse azioni vengono visualizzate nel riquadro dei dettagli quando l'entità è attiva.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="8dc7f-124">La sezione della storia dell'avviso può contenere più di un avviso, con altri avvisi correlati allo stesso albero di esecuzione visualizzati prima o dopo l'avviso selezionato.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![Esempio di una storia di avviso con un avviso attivo e alcune schede espanse](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="8dc7f-126">Eseguire un'azione dal riquadro dei dettagli</span><span class="sxs-lookup"><span data-stu-id="8dc7f-126">Take action from the details pane</span></span>

<span data-ttu-id="8dc7f-127">Dopo aver selezionato un'entità di interesse, il riquadro dei dettagli cambia per visualizzare le informazioni sul tipo  di entità selezionato, le informazioni storiche quando è disponibile e offrire controlli per eseguire azioni su questa entità direttamente dalla pagina di avviso.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="8dc7f-128">Al termine dell'analisi, tornare all'avviso avviato, contrassegnare lo stato dell'avviso come **Risolto** e classificarlo come **Avviso** falso o **Avviso True.**</span><span class="sxs-lookup"><span data-stu-id="8dc7f-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="8dc7f-129">La classificazione degli avvisi consente di ottimizzare questa funzionalità per fornire avvisi più veri e meno falsi.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="8dc7f-130">Se lo classifichiamo come un avviso vero, puoi anche selezionare una determinazione, come mostrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![Frammento del riquadro dei dettagli con un avviso risolto e l'elenco a discesa di determinazione espanso](images/alert-details-resolved-true.png)

<span data-ttu-id="8dc7f-132">Se si verifica un falso avviso con un'applicazione line-of-business, creare una regola di eliminazione per evitare questo tipo di avviso in futuro.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![azioni e classificazione nel riquadro dei dettagli con la regola di eliminazione evidenziata](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="8dc7f-134">Se riscontri problemi non descritti in precedenza, usa il pulsante per fornire feedback o 🙂 aprire un ticket di supporto.</span><span class="sxs-lookup"><span data-stu-id="8dc7f-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="8dc7f-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8dc7f-135">Related topics</span></span>
- [<span data-ttu-id="8dc7f-136">Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts</span><span class="sxs-lookup"><span data-stu-id="8dc7f-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="8dc7f-137">Gestire gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8dc7f-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="8dc7f-138">Analizzare un file associato a un avviso di Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8dc7f-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="8dc7f-139">Analizzare i dispositivi nell'elenco Defender for Endpoint Devices</span><span class="sxs-lookup"><span data-stu-id="8dc7f-139">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="8dc7f-140">Analizzare un indirizzo IP associato a un avviso Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8dc7f-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="8dc7f-141">Analizzare un dominio associato a un avviso Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8dc7f-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="8dc7f-142">Analizzare un account utente in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8dc7f-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)

