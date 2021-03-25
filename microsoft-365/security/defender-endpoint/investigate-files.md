---
title: Analizzare i file di Microsoft Defender for Endpoint
description: Usa le opzioni di indagine per ottenere dettagli sui file associati ad avvisi, comportamenti o eventi.
keywords: analizzare, analizzare, file, attività dannose, motivazione degli attacchi, analisi approfondita, report di analisi approfondita
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
ms.openlocfilehash: a801b6153cf3f273290721756440cfe974103e92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064570"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="e6090-104">Analizzare un file associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e6090-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e6090-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e6090-105">**Applies to:**</span></span>
- [<span data-ttu-id="e6090-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="e6090-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e6090-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6090-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="e6090-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e6090-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e6090-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="e6090-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="e6090-110">Analizzare i dettagli di un file associato a un avviso, un comportamento o un evento specifico per determinare se il file presenta attività dannose, identificare la motivazione dell'attacco e comprendere l'ambito potenziale della violazione.</span><span class="sxs-lookup"><span data-stu-id="e6090-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="e6090-111">Esistono molti modi per accedere alla pagina del profilo dettagliata di un file specifico.</span><span class="sxs-lookup"><span data-stu-id="e6090-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="e6090-112">Ad esempio, puoi usare la funzionalità di ricerca, fare clic su un collegamento nell'albero del processo di **avviso,** nel grafico degli eventi **imprevisti,** nella sequenza temporale artefatto o selezionare un evento elencato nella sequenza temporale del **dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="e6090-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="e6090-113">Una volta visualizzata la pagina dettagliata del profilo, è possibile passare dal layout di pagina nuovo a quello precedente tramite la creazione di **una nuova pagina file.**</span><span class="sxs-lookup"><span data-stu-id="e6090-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="e6090-114">Il resto di questo articolo descrive il layout di pagina più recente.</span><span class="sxs-lookup"><span data-stu-id="e6090-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="e6090-115">È possibile ottenere informazioni dalle sezioni seguenti nella visualizzazione file:</span><span class="sxs-lookup"><span data-stu-id="e6090-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="e6090-116">Dettagli file, rilevamento malware, diffusione dei file</span><span class="sxs-lookup"><span data-stu-id="e6090-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="e6090-117">Analisi approfondita</span><span class="sxs-lookup"><span data-stu-id="e6090-117">Deep analysis</span></span>
- <span data-ttu-id="e6090-118">Avvisi</span><span class="sxs-lookup"><span data-stu-id="e6090-118">Alerts</span></span>
- <span data-ttu-id="e6090-119">Osservato nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e6090-119">Observed in organization</span></span>
- <span data-ttu-id="e6090-120">Analisi approfondita</span><span class="sxs-lookup"><span data-stu-id="e6090-120">Deep analysis</span></span>
- <span data-ttu-id="e6090-121">Nomi di file</span><span class="sxs-lookup"><span data-stu-id="e6090-121">File names</span></span>

<span data-ttu-id="e6090-122">È inoltre possibile eseguire un'azione su un file da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="e6090-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="e6090-123">Azioni file</span><span class="sxs-lookup"><span data-stu-id="e6090-123">File actions</span></span>

<span data-ttu-id="e6090-124">Nella parte superiore della pagina del profilo, sopra le schede di informazioni sui file.</span><span class="sxs-lookup"><span data-stu-id="e6090-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="e6090-125">Le azioni che è possibile eseguire qui includono:</span><span class="sxs-lookup"><span data-stu-id="e6090-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="e6090-126">Arrestare e mettere in quarantena</span><span class="sxs-lookup"><span data-stu-id="e6090-126">Stop and quarantine</span></span>
- <span data-ttu-id="e6090-127">Indicatore di aggiunta/modifica</span><span class="sxs-lookup"><span data-stu-id="e6090-127">Add/edit indicator</span></span>
- <span data-ttu-id="e6090-128">Scarica file</span><span class="sxs-lookup"><span data-stu-id="e6090-128">Download file</span></span>
- <span data-ttu-id="e6090-129">Consultare un esperto di minacce</span><span class="sxs-lookup"><span data-stu-id="e6090-129">Consult a threat expert</span></span>
- <span data-ttu-id="e6090-130">Centro notifiche</span><span class="sxs-lookup"><span data-stu-id="e6090-130">Action center</span></span>

<span data-ttu-id="e6090-131">Per ulteriori informazioni su queste azioni, vedere [Eseguire un'azione di risposta su un file.](respond-file-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e6090-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="e6090-132">Dettagli file, rilevamento malware e diffusione di file</span><span class="sxs-lookup"><span data-stu-id="e6090-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="e6090-133">I dettagli del file, l'evento imprevisto, il rilevamento malware e le schede di prevalenza dei file visualizzano vari attributi relativi al file.</span><span class="sxs-lookup"><span data-stu-id="e6090-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="e6090-134">Vedrai dettagli come MD5 del file, il rapporto di rilevamento totale virus e il rilevamento di Microsoft Defender AV, se disponibile, e la diffusione del file.</span><span class="sxs-lookup"><span data-stu-id="e6090-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="e6090-135">La scheda di prevalenza dei file mostra dove il file è stato visualizzato nei dispositivi dell'organizzazione e in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="e6090-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="e6090-136">Diversi utenti possono visualizzare valori diversi nella sezione *dispositivi nell'organizzazione* della scheda di diffusione dei file.</span><span class="sxs-lookup"><span data-stu-id="e6090-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="e6090-137">Ciò è dovuto al fatto che nella scheda vengono visualizzate informazioni basate sull'ambito RBAC di un utente.</span><span class="sxs-lookup"><span data-stu-id="e6090-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="e6090-138">Ciò significa che se a un utente è stata concessa visibilità su un set specifico di dispositivi, verrà visualizzata solo la diffusione dell'organizzazione dei file su tali dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e6090-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![Immagine delle informazioni sui file](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="e6090-140">Avvisi</span><span class="sxs-lookup"><span data-stu-id="e6090-140">Alerts</span></span>

<span data-ttu-id="e6090-141">Nella **scheda** Avvisi è disponibile un elenco di avvisi associati al file.</span><span class="sxs-lookup"><span data-stu-id="e6090-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="e6090-142">Questo elenco copre gran parte delle stesse informazioni della coda avvisi, ad eccezione del gruppo di dispositivi, se presente, a cui appartiene il dispositivo interessato.</span><span class="sxs-lookup"><span data-stu-id="e6090-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="e6090-143">È possibile scegliere il tipo di informazioni visualizzate selezionando **Personalizza colonne** dalla barra degli strumenti sopra le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="e6090-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![Immagine degli avvisi correlati alla sezione file](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="e6090-145">Osservato nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="e6090-145">Observed in organization</span></span>

<span data-ttu-id="e6090-146">La **scheda Osservati nell'organizzazione** consente di specificare un intervallo di date per vedere quali dispositivi sono stati osservati con il file.</span><span class="sxs-lookup"><span data-stu-id="e6090-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="e6090-147">Questa scheda mostrerà un numero massimo di 100 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e6090-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="e6090-148">Per visualizzare _tutti_ i dispositivi con il file, esporta la scheda in un file CSV selezionando **Esporta** dal menu azione sopra le intestazioni di colonna della scheda.</span><span class="sxs-lookup"><span data-stu-id="e6090-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![Immagine del dispositivo osservato più recente con il file](images/atp-observed-machines.png)

<span data-ttu-id="e6090-150">Usa il dispositivo di scorrimento o il selettore dell'intervallo per specificare rapidamente un periodo di tempo che vuoi controllare per gli eventi che coinvolgono il file.</span><span class="sxs-lookup"><span data-stu-id="e6090-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="e6090-151">È possibile specificare un intervallo di tempo piccolo come un singolo giorno.</span><span class="sxs-lookup"><span data-stu-id="e6090-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="e6090-152">In questo modo sarà possibile visualizzare solo i file che comunicano con tale indirizzo IP in quel momento, riducendo drasticamente lo scorrimento e la ricerca non necessari.</span><span class="sxs-lookup"><span data-stu-id="e6090-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="e6090-153">Analisi approfondita</span><span class="sxs-lookup"><span data-stu-id="e6090-153">Deep analysis</span></span>

<span data-ttu-id="e6090-154">La **scheda Analisi** approfondita consente di inviare il [file](respond-file-alerts.md#deep-analysis)per l'analisi approfondita, per scoprire ulteriori dettagli sul comportamento del file, nonché l'effetto che ha all'interno delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e6090-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="e6090-155">Dopo aver inviato il file, il report di analisi approfondita verrà visualizzato in questa scheda una volta disponibili i risultati.</span><span class="sxs-lookup"><span data-stu-id="e6090-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="e6090-156">Se l'analisi approfondita non ha trovato alcun elemento, il report sarà vuoto e lo spazio dei risultati rimarrà vuoto.</span><span class="sxs-lookup"><span data-stu-id="e6090-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![Immagine della scheda Analisi approfondita](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="e6090-158">Nomi di file</span><span class="sxs-lookup"><span data-stu-id="e6090-158">File names</span></span>

<span data-ttu-id="e6090-159">Nella **scheda Nomi** file sono elencati tutti i nomi che il file è stato osservato per l'utilizzo all'interno delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e6090-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![Scheda Immagine dei nomi di file](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="e6090-161">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e6090-161">Related topics</span></span>

- [<span data-ttu-id="e6090-162">Visualizzare e organizzare la coda di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e6090-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="e6090-163">Gestire gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e6090-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="e6090-164">Analizzare gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e6090-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="e6090-165">Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="e6090-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="e6090-166">Analizzare un indirizzo IP associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e6090-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="e6090-167">Analizzare un dominio associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e6090-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="e6090-168">Analizzare un account utente in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e6090-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="e6090-169">Eseguire azioni di risposta su un file</span><span class="sxs-lookup"><span data-stu-id="e6090-169">Take response actions on a file</span></span>](respond-file-alerts.md)