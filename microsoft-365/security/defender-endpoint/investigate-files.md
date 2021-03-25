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
ms.openlocfilehash: b509ab6d0c3e5183b99173e950198bad0ccd8ee0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186066"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="2c04a-104">Analizzare un file associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c04a-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2c04a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2c04a-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c04a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="2c04a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2c04a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c04a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="2c04a-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2c04a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2c04a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="2c04a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="2c04a-110">Analizzare i dettagli di un file associato a un avviso, un comportamento o un evento specifico per determinare se il file presenta attività dannose, identificare la motivazione dell'attacco e comprendere l'ambito potenziale della violazione.</span><span class="sxs-lookup"><span data-stu-id="2c04a-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="2c04a-111">Esistono molti modi per accedere alla pagina del profilo dettagliata di un file specifico.</span><span class="sxs-lookup"><span data-stu-id="2c04a-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="2c04a-112">Ad esempio, puoi usare la funzionalità di ricerca, fare clic su un collegamento nell'albero del processo di **avviso,** nel grafico degli eventi **imprevisti,** nella sequenza temporale artefatto o selezionare un evento elencato nella sequenza temporale del **dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="2c04a-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="2c04a-113">Una volta visualizzata la pagina dettagliata del profilo, è possibile passare dal layout di pagina nuovo a quello precedente tramite la creazione di **una nuova pagina file.**</span><span class="sxs-lookup"><span data-stu-id="2c04a-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="2c04a-114">Il resto di questo articolo descrive il layout di pagina più recente.</span><span class="sxs-lookup"><span data-stu-id="2c04a-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="2c04a-115">È possibile ottenere informazioni dalle sezioni seguenti nella visualizzazione file:</span><span class="sxs-lookup"><span data-stu-id="2c04a-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="2c04a-116">Dettagli file, rilevamento malware, diffusione dei file</span><span class="sxs-lookup"><span data-stu-id="2c04a-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="2c04a-117">Analisi approfondita</span><span class="sxs-lookup"><span data-stu-id="2c04a-117">Deep analysis</span></span>
- <span data-ttu-id="2c04a-118">Avvisi</span><span class="sxs-lookup"><span data-stu-id="2c04a-118">Alerts</span></span>
- <span data-ttu-id="2c04a-119">Osservato nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="2c04a-119">Observed in organization</span></span>
- <span data-ttu-id="2c04a-120">Analisi approfondita</span><span class="sxs-lookup"><span data-stu-id="2c04a-120">Deep analysis</span></span>
- <span data-ttu-id="2c04a-121">Nomi di file</span><span class="sxs-lookup"><span data-stu-id="2c04a-121">File names</span></span>

<span data-ttu-id="2c04a-122">È inoltre possibile eseguire un'azione su un file da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="2c04a-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="2c04a-123">Azioni file</span><span class="sxs-lookup"><span data-stu-id="2c04a-123">File actions</span></span>

<span data-ttu-id="2c04a-124">Nella parte superiore della pagina del profilo, sopra le schede di informazioni sui file.</span><span class="sxs-lookup"><span data-stu-id="2c04a-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="2c04a-125">Le azioni che è possibile eseguire qui includono:</span><span class="sxs-lookup"><span data-stu-id="2c04a-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="2c04a-126">Arrestare e mettere in quarantena</span><span class="sxs-lookup"><span data-stu-id="2c04a-126">Stop and quarantine</span></span>
- <span data-ttu-id="2c04a-127">Indicatore di aggiunta/modifica</span><span class="sxs-lookup"><span data-stu-id="2c04a-127">Add/edit indicator</span></span>
- <span data-ttu-id="2c04a-128">Scarica file</span><span class="sxs-lookup"><span data-stu-id="2c04a-128">Download file</span></span>
- <span data-ttu-id="2c04a-129">Consultare un esperto di minacce</span><span class="sxs-lookup"><span data-stu-id="2c04a-129">Consult a threat expert</span></span>
- <span data-ttu-id="2c04a-130">Centro notifiche</span><span class="sxs-lookup"><span data-stu-id="2c04a-130">Action center</span></span>

<span data-ttu-id="2c04a-131">Per ulteriori informazioni su queste azioni, vedere [Eseguire un'azione di risposta su un file.](respond-file-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="2c04a-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="2c04a-132">Dettagli file, rilevamento malware e diffusione di file</span><span class="sxs-lookup"><span data-stu-id="2c04a-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="2c04a-133">I dettagli del file, l'evento imprevisto, il rilevamento malware e le schede di prevalenza dei file visualizzano vari attributi relativi al file.</span><span class="sxs-lookup"><span data-stu-id="2c04a-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="2c04a-134">Vedrai dettagli come MD5 del file, il rapporto di rilevamento totale virus e il rilevamento di Microsoft Defender AV, se disponibile, e la diffusione del file.</span><span class="sxs-lookup"><span data-stu-id="2c04a-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="2c04a-135">La scheda di prevalenza dei file mostra dove il file è stato visualizzato nei dispositivi dell'organizzazione e in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="2c04a-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="2c04a-136">Diversi utenti possono visualizzare valori diversi nella sezione *dispositivi nell'organizzazione* della scheda di diffusione dei file.</span><span class="sxs-lookup"><span data-stu-id="2c04a-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="2c04a-137">Ciò è dovuto al fatto che nella scheda vengono visualizzate informazioni basate sull'ambito RBAC di un utente.</span><span class="sxs-lookup"><span data-stu-id="2c04a-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="2c04a-138">Ciò significa che se a un utente è stata concessa visibilità su un set specifico di dispositivi, verrà visualizzata solo la diffusione dell'organizzazione dei file su tali dispositivi.</span><span class="sxs-lookup"><span data-stu-id="2c04a-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![Immagine delle informazioni sui file](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="2c04a-140">Avvisi</span><span class="sxs-lookup"><span data-stu-id="2c04a-140">Alerts</span></span>

<span data-ttu-id="2c04a-141">Nella **scheda** Avvisi è disponibile un elenco di avvisi associati al file.</span><span class="sxs-lookup"><span data-stu-id="2c04a-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="2c04a-142">Questo elenco copre gran parte delle stesse informazioni della coda avvisi, ad eccezione del gruppo di dispositivi, se presente, a cui appartiene il dispositivo interessato.</span><span class="sxs-lookup"><span data-stu-id="2c04a-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="2c04a-143">È possibile scegliere il tipo di informazioni visualizzate selezionando **Personalizza colonne** dalla barra degli strumenti sopra le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="2c04a-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![Immagine degli avvisi correlati alla sezione file](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="2c04a-145">Osservato nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="2c04a-145">Observed in organization</span></span>

<span data-ttu-id="2c04a-146">La **scheda Osservati nell'organizzazione** consente di specificare un intervallo di date per vedere quali dispositivi sono stati osservati con il file.</span><span class="sxs-lookup"><span data-stu-id="2c04a-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="2c04a-147">Questa scheda mostrerà un numero massimo di 100 dispositivi.</span><span class="sxs-lookup"><span data-stu-id="2c04a-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="2c04a-148">Per visualizzare _tutti_ i dispositivi con il file, esporta la scheda in un file CSV selezionando **Esporta** dal menu azione sopra le intestazioni di colonna della scheda.</span><span class="sxs-lookup"><span data-stu-id="2c04a-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![Immagine del dispositivo osservato più recente con il file](images/atp-observed-machines.png)

<span data-ttu-id="2c04a-150">Usa il dispositivo di scorrimento o il selettore dell'intervallo per specificare rapidamente un periodo di tempo che vuoi controllare per gli eventi che coinvolgono il file.</span><span class="sxs-lookup"><span data-stu-id="2c04a-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="2c04a-151">È possibile specificare un intervallo di tempo piccolo come un singolo giorno.</span><span class="sxs-lookup"><span data-stu-id="2c04a-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="2c04a-152">In questo modo sarà possibile visualizzare solo i file che comunicano con tale indirizzo IP in quel momento, riducendo drasticamente lo scorrimento e la ricerca non necessari.</span><span class="sxs-lookup"><span data-stu-id="2c04a-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="2c04a-153">Analisi approfondita</span><span class="sxs-lookup"><span data-stu-id="2c04a-153">Deep analysis</span></span>

<span data-ttu-id="2c04a-154">La **scheda Analisi** approfondita consente di inviare il [file](respond-file-alerts.md#deep-analysis)per l'analisi approfondita, per scoprire ulteriori dettagli sul comportamento del file, nonché l'effetto che ha all'interno delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2c04a-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="2c04a-155">Dopo aver inviato il file, il report di analisi approfondita verrà visualizzato in questa scheda una volta disponibili i risultati.</span><span class="sxs-lookup"><span data-stu-id="2c04a-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="2c04a-156">Se l'analisi approfondita non ha trovato alcun elemento, il report sarà vuoto e lo spazio dei risultati rimarrà vuoto.</span><span class="sxs-lookup"><span data-stu-id="2c04a-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![Immagine della scheda Analisi approfondita](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="2c04a-158">Nomi di file</span><span class="sxs-lookup"><span data-stu-id="2c04a-158">File names</span></span>

<span data-ttu-id="2c04a-159">Nella **scheda Nomi** file sono elencati tutti i nomi che il file è stato osservato per l'utilizzo all'interno delle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2c04a-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![Scheda Immagine dei nomi di file](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="2c04a-161">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2c04a-161">Related topics</span></span>

- [<span data-ttu-id="2c04a-162">Visualizzare e organizzare la coda di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c04a-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="2c04a-163">Gestire gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c04a-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="2c04a-164">Analizzare gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c04a-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="2c04a-165">Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="2c04a-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="2c04a-166">Analizzare un indirizzo IP associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c04a-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="2c04a-167">Analizzare un dominio associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c04a-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="2c04a-168">Analizzare un account utente in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c04a-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="2c04a-169">Eseguire azioni di risposta su un file</span><span class="sxs-lookup"><span data-stu-id="2c04a-169">Take response actions on a file</span></span>](respond-file-alerts.md)
