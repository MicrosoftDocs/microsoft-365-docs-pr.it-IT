---
title: Analizzare un indirizzo IP associato a un avviso
description: Usa le opzioni di indagine per esaminare le possibili comunicazioni tra dispositivi e indirizzi IP esterni.
keywords: analizzare, analizzare, indirizzo IP, avviso, Microsoft Defender for Endpoint, IP esterno
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
ms.openlocfilehash: cb95deb890b52f0f5fde26a3a193181713b8ae5f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933830"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="874d1-104">Analizzare un indirizzo IP associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="874d1-104">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="874d1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="874d1-105">**Applies to:**</span></span>
- [<span data-ttu-id="874d1-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="874d1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="874d1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="874d1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="874d1-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="874d1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="874d1-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="874d1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="874d1-110">Esaminare le possibili comunicazioni tra i dispositivi e gli indirizzi IP (Internet Protocol) esterni.</span><span class="sxs-lookup"><span data-stu-id="874d1-110">Examine possible communication between your devices and external internet protocol (IP) addresses.</span></span>

<span data-ttu-id="874d1-111">L'identificazione di tutti i dispositivi dell'organizzazione che comunicano con un indirizzo IP sospetto o noto dannoso, come i server Command and Control (C2), consente di determinare l'ambito potenziale di violazione, i file associati e i dispositivi infetti.</span><span class="sxs-lookup"><span data-stu-id="874d1-111">Identifying all devices in the organization that communicated with a suspected or known malicious IP address, such as Command and Control (C2) servers, helps determine the potential scope of breach, associated files, and infected devices.</span></span>

<span data-ttu-id="874d1-112">È possibile trovare informazioni dalle sezioni seguenti nella visualizzazione degli indirizzi IP:</span><span class="sxs-lookup"><span data-stu-id="874d1-112">You can find information from the following sections in the IP address view:</span></span>

- <span data-ttu-id="874d1-113">IP in tutto il mondo</span><span class="sxs-lookup"><span data-stu-id="874d1-113">IP worldwide</span></span>
- <span data-ttu-id="874d1-114">Nomi DNS inversa</span><span class="sxs-lookup"><span data-stu-id="874d1-114">Reverse DNS names</span></span>
- <span data-ttu-id="874d1-115">Avvisi correlati a questo indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="874d1-115">Alerts related to this IP</span></span>
- <span data-ttu-id="874d1-116">IP nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="874d1-116">IP in organization</span></span>
- <span data-ttu-id="874d1-117">Prevalenza</span><span class="sxs-lookup"><span data-stu-id="874d1-117">Prevalence</span></span>

## <a name="ip-worldwide-and-reverse-dns-names"></a><span data-ttu-id="874d1-118">Ip Worldwide e Reverse DNS names</span><span class="sxs-lookup"><span data-stu-id="874d1-118">IP Worldwide and Reverse DNS names</span></span>

<span data-ttu-id="874d1-119">La sezione Dettagli indirizzo IP mostra gli attributi dell'indirizzo IP, ad esempio il relativo ASN e i relativi nomi DNS inversa.</span><span class="sxs-lookup"><span data-stu-id="874d1-119">The IP address details section shows attributes of the IP address such as its ASN and its Reverse DNS names.</span></span>

## <a name="alerts-related-to-this-ip"></a><span data-ttu-id="874d1-120">Avvisi correlati a questo indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="874d1-120">Alerts related to this IP</span></span>

<span data-ttu-id="874d1-121">La **sezione Avvisi correlati a questo ip** fornisce un elenco di avvisi associati all'IP.</span><span class="sxs-lookup"><span data-stu-id="874d1-121">The **Alerts related to this IP** section provides a list of alerts that are associated with the IP.</span></span>

## <a name="ip-in-organization"></a><span data-ttu-id="874d1-122">IP nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="874d1-122">IP in organization</span></span>

<span data-ttu-id="874d1-123">La **sezione IP nell'organizzazione** fornisce informazioni dettagliate sulla diffusione dell'indirizzo IP nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="874d1-123">The **IP in organization** section provides details on the prevalence of the IP address in the organization.</span></span>

## <a name="prevalence"></a><span data-ttu-id="874d1-124">Prevalenza</span><span class="sxs-lookup"><span data-stu-id="874d1-124">Prevalence</span></span>

<span data-ttu-id="874d1-125">La **sezione Prevalenza** mostra quanti dispositivi si sono connessi a questo indirizzo IP e quando l'IP è stato visualizzato per la prima volta e l'ultima volta.</span><span class="sxs-lookup"><span data-stu-id="874d1-125">The **Prevalence** section displays how many devices have connected to this IP address, and when the IP was first and last seen.</span></span> <span data-ttu-id="874d1-126">È possibile filtrare i risultati di questa sezione in base al periodo di tempo. il periodo predefinito è 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="874d1-126">You can filter the results of this section by time period; the default period is 30 days.</span></span>

## <a name="most-recent-observed-devices-with-ip"></a><span data-ttu-id="874d1-127">Dispositivi osservati più recenti con IP</span><span class="sxs-lookup"><span data-stu-id="874d1-127">Most recent observed devices with IP</span></span>

<span data-ttu-id="874d1-128">La **sezione Dispositivi osservati più recenti** con IP fornisce una visualizzazione cronologica degli eventi e degli avvisi associati che sono stati osservati nell'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="874d1-128">The **Most recent observed devices** with IP section provides a chronological view on the events and associated alerts that were observed on the IP address.</span></span>

<span data-ttu-id="874d1-129">**Analizzare un IP esterno:**</span><span class="sxs-lookup"><span data-stu-id="874d1-129">**Investigate an external IP:**</span></span>

1. <span data-ttu-id="874d1-130">Selezionare **IP** dal menu **a** discesa barra di ricerca.</span><span class="sxs-lookup"><span data-stu-id="874d1-130">Select **IP** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="874d1-131">Immettere l'indirizzo IP nel **campo** Cerca.</span><span class="sxs-lookup"><span data-stu-id="874d1-131">Enter the IP address in the **Search** field.</span></span>
3. <span data-ttu-id="874d1-132">Fare clic sull'icona di ricerca o premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="874d1-132">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="874d1-133">Vengono visualizzati i dettagli sull'indirizzo IP, tra cui: dettagli di registrazione (se disponibili), IP inversi (ad esempio, domini), prevalenza dei dispositivi nell'organizzazione che comunicavano con questo indirizzo IP (durante il periodo di tempo selezionabile) e i dispositivi dell'organizzazione che sono stati osservati comunicare con questo indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="874d1-133">Details about the IP address are displayed, including: registration details (if available), reverse IPs (for example, domains), prevalence of devices in the organization that communicated with this IP Address (during selectable time period), and the devices in the organization that were observed communicating with this IP address.</span></span>

> [!NOTE]
> <span data-ttu-id="874d1-134">I risultati della ricerca verranno restituiti solo per gli indirizzi IP osservati nelle comunicazioni con i dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="874d1-134">Search results will only be returned for IP addresses observed in communication with devices in the organization.</span></span>

<span data-ttu-id="874d1-135">Utilizzare i filtri di ricerca per definire i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="874d1-135">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="874d1-136">Puoi anche usare la casella di ricerca della sequenza temporale per filtrare i risultati visualizzati di tutti i dispositivi dell'organizzazione osservati in comunicazione con l'indirizzo IP, il file associato alla comunicazione e l'ultima data osservata.</span><span class="sxs-lookup"><span data-stu-id="874d1-136">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the IP address, the file associated with the communication and the last date observed.</span></span>

<span data-ttu-id="874d1-137">Se fai clic su uno dei nomi dei dispositivi, potrai passare alla visualizzazione del dispositivo, in cui puoi continuare ad analizzare gli avvisi, i comportamenti e gli eventi segnalati.</span><span class="sxs-lookup"><span data-stu-id="874d1-137">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="874d1-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="874d1-138">Related topics</span></span>

- [<span data-ttu-id="874d1-139">Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts</span><span class="sxs-lookup"><span data-stu-id="874d1-139">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="874d1-140">Gestire gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="874d1-140">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="874d1-141">Analizzare gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="874d1-141">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="874d1-142">Analizzare un file associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="874d1-142">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="874d1-143">Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="874d1-143">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="874d1-144">Analizzare un dominio associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="874d1-144">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="874d1-145">Analizzare un account utente in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="874d1-145">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
