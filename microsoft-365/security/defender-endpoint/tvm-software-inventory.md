---
title: Inventario software nella gestione delle minacce e delle vulnerabilità
description: La pagina dell'inventario software per la gestione delle minacce e delle vulnerabilità di Microsoft Defender for Endpoint mostra quanti punti deboli e vulnerabilità sono stati rilevati nel software.
keywords: gestione delle minacce e delle vulnerabilità, microsoft defender for endpoint, microsoft defender for endpoint software inventory, mdatp threat & vulnerability management, mdatp threat & vulnerability management software inventory, mdatp tvm software inventory, tvm software inventory
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a4ceb7cc4d39dbddbb4cd325491c16f4503bfc52
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689378"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a><span data-ttu-id="45168-104">Inventario software - Gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="45168-104">Software inventory - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="45168-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="45168-105">**Applies to:**</span></span>
- [<span data-ttu-id="45168-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="45168-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="45168-107">Gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="45168-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="45168-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45168-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="45168-109">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="45168-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="45168-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="45168-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="45168-111">L'inventario software nella gestione delle minacce e delle vulnerabilità è un elenco di software noto nell'organizzazione con le enumerazioni ufficiali della piattaforma comune [(CPE).](https://nvd.nist.gov/products/cpe)</span><span class="sxs-lookup"><span data-stu-id="45168-111">The software inventory in threat and vulnerability management is a list of known software in your organization with official [Common Platform Enumerations (CPE)](https://nvd.nist.gov/products/cpe).</span></span> <span data-ttu-id="45168-112">I prodotti software senza un CPE ufficiale non hanno vulnerabilità pubblicate.</span><span class="sxs-lookup"><span data-stu-id="45168-112">Software products without an official CPE don’t have vulnerabilities published.</span></span> <span data-ttu-id="45168-113">Include inoltre dettagli quali il nome del fornitore, il numero di punti deboli, le minacce e il numero di dispositivi esposti.</span><span class="sxs-lookup"><span data-stu-id="45168-113">It also includes details such as the name of the vendor, number of weaknesses, threats, and number of exposed devices.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="45168-114">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="45168-114">How it works</span></span>

<span data-ttu-id="45168-115">Nel campo dell'individuazione, stiamo sfruttando lo stesso set di segnali responsabile del rilevamento e della valutazione delle vulnerabilità in Microsoft Defender per le funzionalità di rilevamento e risposta degli [endpoint.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="45168-115">In the field of discovery, we're leveraging the same set of signals that is responsible for detection and vulnerability assessment in [Microsoft Defender for Endpoint detection and response capabilities](overview-endpoint-detection-response.md).</span></span>

<span data-ttu-id="45168-116">Dal momento che è in tempo reale, in pochi minuti, vedrai le informazioni sulla vulnerabilità quando vengono individuate.</span><span class="sxs-lookup"><span data-stu-id="45168-116">Since it's real time, in a matter of minutes, you'll see vulnerability information as they get discovered.</span></span> <span data-ttu-id="45168-117">Il motore afferra automaticamente le informazioni da più feed di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="45168-117">The engine automatically grabs information from multiple security feeds.</span></span> <span data-ttu-id="45168-118">Infatti, vedrai se un particolare software è connesso a una campagna di minacce in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="45168-118">In fact, you'll see if a particular software is connected to a live threat campaign.</span></span> <span data-ttu-id="45168-119">Fornisce inoltre un collegamento a un report di Threat Analytics non appena disponibile.</span><span class="sxs-lookup"><span data-stu-id="45168-119">It also provides a link to a Threat Analytics report soon as it's available.</span></span>

## <a name="navigate-to-the-software-inventory-page"></a><span data-ttu-id="45168-120">Passare alla pagina Inventario software</span><span class="sxs-lookup"><span data-stu-id="45168-120">Navigate to the Software inventory page</span></span>

<span data-ttu-id="45168-121">Accedere alla pagina Inventario software selezionando **Inventario software** dal menu di spostamento per la gestione delle minacce e delle vulnerabilità in Microsoft Defender [Security Center.](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="45168-121">Access the Software inventory page by selecting **Software inventory** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md).</span></span>

<span data-ttu-id="45168-122">Visualizzare il software in dispositivi specifici nelle pagine dei singoli dispositivi [dall'elenco dei dispositivi.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="45168-122">View software on specific devices in the individual devices pages from the [devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="45168-123">Se si cerca software utilizzando la ricerca globale di Microsoft Defender for Endpoint, assicurarsi di inserire un carattere di sottolineatura anziché uno spazio.</span><span class="sxs-lookup"><span data-stu-id="45168-123">If you search for software using the Microsoft Defender for Endpoint global search, make sure to put an underscore instead of a space.</span></span> <span data-ttu-id="45168-124">Ad esempio, per i risultati di ricerca migliori devi scrivere "windows_10" anziché "Windows 10".</span><span class="sxs-lookup"><span data-stu-id="45168-124">For example, for the best search results you'd write "windows_10" instead of "Windows 10".</span></span>

## <a name="software-inventory-overview"></a><span data-ttu-id="45168-125">Panoramica dell'inventario software</span><span class="sxs-lookup"><span data-stu-id="45168-125">Software inventory overview</span></span>

<span data-ttu-id="45168-126">La **pagina Inventario software** si apre con un elenco di software installato nella rete, inclusi il nome del fornitore, i punti deboli trovati, le minacce ad essi associate, i dispositivi esposti, l'impatto sul punteggio di esposizione e i tag.</span><span class="sxs-lookup"><span data-stu-id="45168-126">The **Software inventory** page opens with a list of software installed in your network, including the vendor name, weaknesses found, threats associated with them, exposed devices, impact to exposure score, and tags.</span></span>

<span data-ttu-id="45168-127">È possibile filtrare la visualizzazione elenco in base ai punti deboli rilevati nel software, alle minacce associate e ai tag, ad esempio se il software ha raggiunto la fine del supporto.</span><span class="sxs-lookup"><span data-stu-id="45168-127">You can filter the list view based on weaknesses found in the software, threats associated with them, and tags like whether the software has reached end-of-support.</span></span>

![Esempio della pagina di destinazione per l'inventario software.](images/tvm-software-inventory.png)

<span data-ttu-id="45168-129">Selezionare il software che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="45168-129">Select the software that you want to investigate.</span></span> <span data-ttu-id="45168-130">Verrà aperto un riquadro a comparsa con una visualizzazione più compatta delle informazioni nella pagina.</span><span class="sxs-lookup"><span data-stu-id="45168-130">A flyout panel will open with a more compact view of the information on the page.</span></span> <span data-ttu-id="45168-131">È possibile approfondire l'indagine e selezionare Apri pagina **software** oppure contrassegnare eventuali incoerenze tecniche selezionando Segnala **inaccurabilità.**</span><span class="sxs-lookup"><span data-stu-id="45168-131">You can either dive deeper into the investigation and select **Open software page**, or flag any technical inconsistencies by selecting **Report inaccuracy**.</span></span>

### <a name="software-that-isnt-supported"></a><span data-ttu-id="45168-132">Software non supportato</span><span class="sxs-lookup"><span data-stu-id="45168-132">Software that isn't supported</span></span>

<span data-ttu-id="45168-133">Software attualmente non supportato dalle minacce & la gestione delle vulnerabilità potrebbe essere presente nella pagina Inventario software.</span><span class="sxs-lookup"><span data-stu-id="45168-133">Software that isn't currently supported by threat & vulnerability management may be present in the Software inventory page.</span></span> <span data-ttu-id="45168-134">Poiché non è supportato, saranno disponibili solo dati limitati.</span><span class="sxs-lookup"><span data-stu-id="45168-134">Because it is not supported, only limited data will be available.</span></span> <span data-ttu-id="45168-135">Filtra in base al software non supportato con l'opzione "Non disponibile" nella sezione "Debolezza".</span><span class="sxs-lookup"><span data-stu-id="45168-135">Filter by unsupported software with the "Not available" option in the "Weakness" section.</span></span>

![Filtro software non supportato.](images/tvm-unsupported-software-filter.png)

<span data-ttu-id="45168-137">Di seguito viene indicato che un software non è supportato:</span><span class="sxs-lookup"><span data-stu-id="45168-137">The following indicates that a software is not supported:</span></span>

- <span data-ttu-id="45168-138">Il campo Punti deboli mostra "Non disponibile"</span><span class="sxs-lookup"><span data-stu-id="45168-138">Weaknesses field shows "Not available"</span></span>
- <span data-ttu-id="45168-139">Il campo Dispositivi esposti mostra un trattino</span><span class="sxs-lookup"><span data-stu-id="45168-139">Exposed devices field shows a dash</span></span>
- <span data-ttu-id="45168-140">Testo informativo aggiunto nel pannello laterale e nella pagina software</span><span class="sxs-lookup"><span data-stu-id="45168-140">Informational text added in side panel and in software page</span></span>
- <span data-ttu-id="45168-141">Nella pagina del software non sono disponibili i suggerimenti per la sicurezza, le vulnerabilità individuate o le sezioni relative alla sequenza temporale degli eventi</span><span class="sxs-lookup"><span data-stu-id="45168-141">The software page won't have the security recommendations, discovered vulnerabilities, or event timeline sections</span></span>

<span data-ttu-id="45168-142">Attualmente, i prodotti senza CPE non vengono visualizzati nella pagina dell'inventario software, solo nell'inventario software a livello di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="45168-142">Currently, products without a CPE are not shown in the software inventory page, only in the device level software inventory.</span></span>

## <a name="software-inventory-on-devices"></a><span data-ttu-id="45168-143">Inventario software nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="45168-143">Software inventory on devices</span></span>

<span data-ttu-id="45168-144">Dal riquadro di spostamento di Microsoft Defender Security Center vai **[all'elenco Dispositivi.](machines-view-overview.md)**</span><span class="sxs-lookup"><span data-stu-id="45168-144">From the Microsoft Defender Security Center navigation panel, go to the **[Devices list](machines-view-overview.md)**.</span></span> <span data-ttu-id="45168-145">Seleziona il nome di un dispositivo per aprire la pagina del dispositivo (ad esempio Computer1), quindi seleziona la scheda **Inventario** software per visualizzare un elenco di tutti i software noti presenti nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="45168-145">Select the name of a device to open the device page (like Computer1), then select the **Software inventory** tab to see a list of all the known software present on the device.</span></span> <span data-ttu-id="45168-146">Selezionare una voce software specifica per aprire il riquadro a comparsa con ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="45168-146">Select a specific software entry to open the flyout with more information.</span></span>

<span data-ttu-id="45168-147">Il software potrebbe essere visibile a livello di dispositivo anche se attualmente non è supportato dalla gestione delle minacce e delle vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="45168-147">Software may be visible at the device level even if it is currently not supported by threat and vulnerability management.</span></span> <span data-ttu-id="45168-148">Tuttavia, saranno disponibili solo dati limitati.</span><span class="sxs-lookup"><span data-stu-id="45168-148">However, only limited data will be available.</span></span> <span data-ttu-id="45168-149">Saprai se il software non è supportato perché nella colonna "Debolezza" verrà visualizzato "Non disponibile".</span><span class="sxs-lookup"><span data-stu-id="45168-149">You'll know if software is unsupported because it will say "Not available" in the "Weakness" column.</span></span>

<span data-ttu-id="45168-150">Il software senza CPE può anche essere visualizzato in questo inventario software specifico del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="45168-150">Software with no CPE can also show up under this device specific software inventory.</span></span>

### <a name="software-evidence"></a><span data-ttu-id="45168-151">Prove software</span><span class="sxs-lookup"><span data-stu-id="45168-151">Software evidence</span></span>

<span data-ttu-id="45168-152">Vedi la prova della posizione in cui è stato rilevato un software specifico in un dispositivo dal Registro di sistema, dal disco o da entrambi. Puoi trovarlo in qualsiasi dispositivo nell'inventario software del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="45168-152">See evidence of where we detected a specific software on a device from the registry, disk, or both.You can find it on any device in the device software inventory.</span></span>

<span data-ttu-id="45168-153">Selezionare un nome software per aprire il riquadro a comparsa e cercare la sezione "Software Evidence".</span><span class="sxs-lookup"><span data-stu-id="45168-153">Select a software name to open the flyout, and look for the section called "Software Evidence."</span></span>

![Esempio di prova software di Windows 10 dall'elenco dei dispositivi, che mostra il percorso del Registro di sistema delle evidenze software.](images/tvm-software-evidence.png)

## <a name="software-pages"></a><span data-ttu-id="45168-155">Pagine software</span><span class="sxs-lookup"><span data-stu-id="45168-155">Software pages</span></span>

<span data-ttu-id="45168-156">È possibile visualizzare le pagine software in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="45168-156">You can view software pages a few different ways:</span></span>

- <span data-ttu-id="45168-157">Pagina Inventario software > Selezionare un nome software > Seleziona **la pagina Apri software** nel riquadro a comparsa</span><span class="sxs-lookup"><span data-stu-id="45168-157">Software inventory page > Select a software name > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="45168-158">[Pagina Suggerimenti per la](tvm-security-recommendation.md) sicurezza > Selezionare un suggerimento > Selezionare la pagina **Apri software** nel riquadro a comparsa</span><span class="sxs-lookup"><span data-stu-id="45168-158">[Security recommendations page](tvm-security-recommendation.md) > Select a recommendation > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="45168-159">[Pagina Sequenza temporale](threat-and-vuln-mgt-event-timeline.md) evento > Seleziona un evento > Seleziona il nome del software con collegamento ipertestuale (ad esempio Visual Studio 2017) nella sezione denominata "Componente correlato" nel riquadro a comparsa</span><span class="sxs-lookup"><span data-stu-id="45168-159">[Event timeline page](threat-and-vuln-mgt-event-timeline.md) > Select an event > Select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout</span></span>

 <span data-ttu-id="45168-160">Verrà visualizzata una pagina intera con tutti i dettagli di un software specifico e le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="45168-160">A full page will appear with all the details of a specific software and the following information:</span></span>

- <span data-ttu-id="45168-161">Pannello laterale con informazioni sul fornitore, prevalenza del software nell'organizzazione (incluso il numero di dispositivi in cui è installato e dispositivi esposti che non sono patchati), se è disponibile e exploit e impatto sul punteggio di esposizione.</span><span class="sxs-lookup"><span data-stu-id="45168-161">Side panel with vendor information, prevalence of the software in the organization (including number of devices it's installed on, and exposed devices that aren't patched), whether and exploit is available, and impact to your exposure score.</span></span>
- <span data-ttu-id="45168-162">Visualizzazioni dei dati che mostrano il numero e la gravità delle vulnerabilità e delle configurazioni erre.</span><span class="sxs-lookup"><span data-stu-id="45168-162">Data visualizations showing the number of, and severity of, vulnerabilities and misconfigurations.</span></span> <span data-ttu-id="45168-163">Inoltre, grafici con il numero di dispositivi esposti.</span><span class="sxs-lookup"><span data-stu-id="45168-163">Also, graphs with the number of exposed devices.</span></span>
- <span data-ttu-id="45168-164">Schede che mostrano informazioni quali:</span><span class="sxs-lookup"><span data-stu-id="45168-164">Tabs showing information such as:</span></span>
    - <span data-ttu-id="45168-165">Suggerimenti per la sicurezza corrispondenti per i punti deboli e le vulnerabilità identificati.</span><span class="sxs-lookup"><span data-stu-id="45168-165">Corresponding security recommendations for the weaknesses and vulnerabilities identified.</span></span>
    - <span data-ttu-id="45168-166">CVE denominati delle vulnerabilità individuate.</span><span class="sxs-lookup"><span data-stu-id="45168-166">Named CVEs of discovered vulnerabilities.</span></span>
    - <span data-ttu-id="45168-167">Dispositivi in cui è installato il software (insieme al nome del dispositivo, al dominio, al sistema operativo e altro ancora).</span><span class="sxs-lookup"><span data-stu-id="45168-167">Devices that have the software installed (along with device name, domain, OS, and more).</span></span>
    - <span data-ttu-id="45168-168">Elenco delle versioni software (incluso il numero di dispositivi in cui è installata la versione, il numero di vulnerabilità individuate e i nomi dei dispositivi installati).</span><span class="sxs-lookup"><span data-stu-id="45168-168">Software version list (including number of devices the version is installed on, the number of discovered vulnerabilities, and the names of the installed devices).</span></span>

    ![Pagina di esempio software per Visual Studio 2017 con i dettagli del software, i punti deboli, i dispositivi esposti e altro ancora.](images/tvm-software-page-example.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="45168-170">Imprecisione dei report</span><span class="sxs-lookup"><span data-stu-id="45168-170">Report inaccuracy</span></span>

<span data-ttu-id="45168-171">Segnalare un falso positivo quando vengono visualizzate informazioni vaghe, imprecise o incomplete.</span><span class="sxs-lookup"><span data-stu-id="45168-171">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="45168-172">È inoltre possibile segnalare suggerimenti sulla sicurezza che sono già stati corretti.</span><span class="sxs-lookup"><span data-stu-id="45168-172">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="45168-173">Aprire il riquadro a comparsa software nella pagina Inventario software.</span><span class="sxs-lookup"><span data-stu-id="45168-173">Open the software flyout on the Software inventory page.</span></span>
2. <span data-ttu-id="45168-174">Selezionare **Report inaccuracy**.</span><span class="sxs-lookup"><span data-stu-id="45168-174">Select **Report inaccuracy**.</span></span>
3. <span data-ttu-id="45168-175">Nel riquadro a comparsa selezionare la categoria di imprecisione dal menu a discesa, immettere l'indirizzo di posta elettronica e i dettagli sull'imprecisione.</span><span class="sxs-lookup"><span data-stu-id="45168-175">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details about the inaccuracy.</span></span>
4. <span data-ttu-id="45168-176">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="45168-176">Select **Submit**.</span></span> <span data-ttu-id="45168-177">Il feedback viene inviato immediatamente agli esperti di gestione delle minacce e delle vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="45168-177">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="45168-178">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="45168-178">Related articles</span></span>

- [<span data-ttu-id="45168-179">Panoramica della gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="45168-179">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="45168-180">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="45168-180">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="45168-181">Sequenza temporale eventi</span><span class="sxs-lookup"><span data-stu-id="45168-181">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
- [<span data-ttu-id="45168-182">Visualizzare e organizzare l'elenco di Microsoft Defender per dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="45168-182">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
