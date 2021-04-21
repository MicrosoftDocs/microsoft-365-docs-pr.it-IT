---
title: Controllare lo stato di integrità del sensore in Microsoft Defender per Endpoint
description: Controlla l'integrità del sensore nei dispositivi per identificare quelli configurati in modo erre, inattivi o che non segnalano i dati del sensore.
keywords: sensore, integrità del sensore, configurazione errata, inattiva, nessun dato del sensore, dati del sensore, comunicazioni compromesse, comunicazione
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
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904165"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="2bba6-104">Controllare lo stato di integrità del sensore in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bba6-104">Check sensor health state in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2bba6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2bba6-105">**Applies to:**</span></span>
- [<span data-ttu-id="2bba6-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="2bba6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2bba6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bba6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2bba6-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2bba6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2bba6-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="2bba6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

<span data-ttu-id="2bba6-110">Il **riquadro Dispositivi con problemi del** sensore è disponibile nel dashboard Operazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2bba6-110">The **Devices with sensor issues** tile is found on the Security Operations dashboard.</span></span> <span data-ttu-id="2bba6-111">Questo riquadro fornisce informazioni sulla capacità del singolo dispositivo di fornire dati del sensore e comunicare con il servizio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2bba6-111">This tile provides information on the individual device’s ability to provide sensor data and communicate with the Defender for Endpoint service.</span></span> <span data-ttu-id="2bba6-112">Segnala il numero di dispositivi che richiedono attenzione e ti aiuta a identificare i dispositivi problematici e a intervenire per correggere i problemi noti.</span><span class="sxs-lookup"><span data-stu-id="2bba6-112">It reports how many devices require attention and helps you identify problematic devices and take action to correct known issues.</span></span>

<span data-ttu-id="2bba6-113">Nel riquadro sono presenti due indicatori di stato che forniscono informazioni sul numero di dispositivi che non segnalano correttamente al servizio:</span><span class="sxs-lookup"><span data-stu-id="2bba6-113">There are two status indicators on the tile that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="2bba6-114">**Configurazione errata: questi** dispositivi potrebbero segnalare parzialmente i dati del sensore al servizio Defender for Endpoint e potrebbero avere errori di configurazione che devono essere corretti.</span><span class="sxs-lookup"><span data-stu-id="2bba6-114">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="2bba6-115">**Inattivo:** dispositivi che hanno interrotto la segnalazione al servizio Defender for Endpoint per più di sette giorni nell'ultimo mese.</span><span class="sxs-lookup"><span data-stu-id="2bba6-115">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="2bba6-116">Se fai clic su uno dei gruppi, viene visualizzato **l'elenco Dispositivi,** filtrato in base alla tua scelta.</span><span class="sxs-lookup"><span data-stu-id="2bba6-116">Clicking any of the groups directs you to **Devices list**, filtered according to your choice.</span></span>

![Screenshot del riquadro Dispositivi con problemi del sensore](images/atp-devices-with-sensor-issues-tile.png)

<span data-ttu-id="2bba6-118">**Nell'elenco Dispositivi** è possibile filtrare l'elenco degli stati di integrità in base allo stato seguente:</span><span class="sxs-lookup"><span data-stu-id="2bba6-118">On **Devices list**, you can filter the health state list by the following status:</span></span>
- <span data-ttu-id="2bba6-119">**Active** - Dispositivi che segnalano attivamente al servizio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2bba6-119">**Active** - Devices that are actively reporting to the Defender for Endpoint service.</span></span>
- <span data-ttu-id="2bba6-120">**Configurazione errata: questi** dispositivi potrebbero segnalare parzialmente i dati del sensore al servizio Defender for Endpoint, ma potrebbero avere errori di configurazione che devono essere corretti.</span><span class="sxs-lookup"><span data-stu-id="2bba6-120">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service but have configuration errors that need to be corrected.</span></span> <span data-ttu-id="2bba6-121">I dispositivi non configurati correttamente possono avere uno o una combinazione dei seguenti problemi:</span><span class="sxs-lookup"><span data-stu-id="2bba6-121">Misconfigured devices can have either one or a combination of the following issues:</span></span>
  - <span data-ttu-id="2bba6-122">**Nessun dato del sensore:** i dispositivi hanno smesso di inviare i dati del sensore.</span><span class="sxs-lookup"><span data-stu-id="2bba6-122">**No sensor data** - Devices has stopped sending sensor data.</span></span> <span data-ttu-id="2bba6-123">Gli avvisi limitati possono essere attivati dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2bba6-123">Limited alerts can be triggered from the device.</span></span>
  - <span data-ttu-id="2bba6-124">**Comunicazioni con problemi** - La capacità di comunicare con il dispositivo è compromessa.</span><span class="sxs-lookup"><span data-stu-id="2bba6-124">**Impaired communications** - Ability to communicate with device is impaired.</span></span> <span data-ttu-id="2bba6-125">L'invio di file per l'analisi approfondita, il blocco dei file, l'isolamento del dispositivo dalla rete e altre azioni che richiedono la comunicazione con il dispositivo potrebbero non funzionare.</span><span class="sxs-lookup"><span data-stu-id="2bba6-125">Sending files for deep analysis, blocking files, isolating device from network and other actions that require communication with the device may not work.</span></span>
- <span data-ttu-id="2bba6-126">**Inattivo:** dispositivi che hanno interrotto la segnalazione al servizio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2bba6-126">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service.</span></span>

<span data-ttu-id="2bba6-127">Puoi anche scaricare l'intero elenco in formato CSV usando la **funzionalità Esporta.**</span><span class="sxs-lookup"><span data-stu-id="2bba6-127">You can also download the entire list in CSV format using the **Export** feature.</span></span> <span data-ttu-id="2bba6-128">Per altre informazioni sui filtri, vedi [Visualizzare e organizzare l'elenco Dispositivi.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2bba6-128">For more information on filters, see [View and organize the Devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="2bba6-129">Esportare l'elenco in formato CSV per visualizzare i dati non filtrati.</span><span class="sxs-lookup"><span data-stu-id="2bba6-129">Export the list in CSV format to display the unfiltered data.</span></span> <span data-ttu-id="2bba6-130">Il file CSV includerà tutti i dispositivi dell'organizzazione, indipendentemente dai filtri applicati nella visualizzazione stessa e può richiedere molto tempo per il download, a seconda delle dimensioni dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2bba6-130">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.</span></span>

![Screenshot della pagina elenco Dispositivi](images/atp-devices-list-page.png)

<span data-ttu-id="2bba6-132">Puoi visualizzare i dettagli del dispositivo quando fai clic su un dispositivo non configurato correttamente o inattivo.</span><span class="sxs-lookup"><span data-stu-id="2bba6-132">You can view the device details when you click on a misconfigured or inactive device.</span></span>

## <a name="related-topic"></a><span data-ttu-id="2bba6-133">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="2bba6-133">Related topic</span></span>
- [<span data-ttu-id="2bba6-134">Risolvere i sensori non integri in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bba6-134">Fix unhealthy sensors in Defender for Endpoint</span></span>](fix-unhealthy-sensors.md)
