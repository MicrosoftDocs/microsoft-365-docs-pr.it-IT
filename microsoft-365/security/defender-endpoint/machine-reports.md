---
title: Report integrità e conformità dei dispositivi in Microsoft Defender ATP
description: Tenere traccia dei rilevamenti dello stato di integrità dei dispositivi, dello stato antivirus, della piattaforma del sistema operativo e delle versioni di Windows 10 usando il report di conformità e integrità del dispositivo
keywords: stato di integrità, antivirus, piattaforma del sistema operativo, versione di Windows 10, versione, integrità, conformità, stato
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
ms.technology: mde
ms.openlocfilehash: 5229ba068672035c2dce3afee1919f9c2d7f9e44
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186450"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="f10d4-104">Report sull'integrità e la conformità dei dispositivi in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f10d4-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f10d4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f10d4-105">**Applies to:**</span></span>
- [<span data-ttu-id="f10d4-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f10d4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f10d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f10d4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="f10d4-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f10d4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f10d4-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f10d4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f10d4-110">Il rapporto sullo stato dei dispositivi fornisce informazioni di alto livello sui dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f10d4-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="f10d4-111">Il report include informazioni sulle tendenze che mostrano lo stato di integrità del sensore, lo stato antivirus, le piattaforme del sistema operativo e le versioni di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f10d4-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="f10d4-112">Il dashboard è strutturato in due sezioni: ![ Immagine del report del dispositivo](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="f10d4-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="f10d4-113">Sezione</span><span class="sxs-lookup"><span data-stu-id="f10d4-113">Section</span></span> | <span data-ttu-id="f10d4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f10d4-114">Description</span></span>
:---|:---
<span data-ttu-id="f10d4-115">1</span><span class="sxs-lookup"><span data-stu-id="f10d4-115">1</span></span> | <span data-ttu-id="f10d4-116">Tendenze dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="f10d4-116">Device trends</span></span>
<span data-ttu-id="f10d4-117">2 </span><span class="sxs-lookup"><span data-stu-id="f10d4-117">2</span></span> | <span data-ttu-id="f10d4-118">Riepilogo dispositivo (giorno corrente)</span><span class="sxs-lookup"><span data-stu-id="f10d4-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="f10d4-119">Tendenze dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="f10d4-119">Device trends</span></span> 
<span data-ttu-id="f10d4-120">Per impostazione predefinita, le tendenze dei dispositivi visualizzano le informazioni sul dispositivo del periodo di 30 giorni che termina con l'ultimo giorno completo.</span><span class="sxs-lookup"><span data-stu-id="f10d4-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="f10d4-121">Per ottenere una prospettiva migliore sulle tendenze che si verificano nell'organizzazione, è possibile ottimizzare il periodo di reporting modificando il periodo di tempo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="f10d4-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="f10d4-122">Per regolare il periodo di tempo, selezionare un intervallo di tempo dalle opzioni a discesa:</span><span class="sxs-lookup"><span data-stu-id="f10d4-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="f10d4-123">30 giorni</span><span class="sxs-lookup"><span data-stu-id="f10d4-123">30 days</span></span>
- <span data-ttu-id="f10d4-124">3 mesi</span><span class="sxs-lookup"><span data-stu-id="f10d4-124">3 months</span></span>
- <span data-ttu-id="f10d4-125">6 mesi</span><span class="sxs-lookup"><span data-stu-id="f10d4-125">6 months</span></span>
- <span data-ttu-id="f10d4-126">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="f10d4-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="f10d4-127">Questi filtri vengono applicati solo nella sezione tendenze del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f10d4-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="f10d4-128">Non influisce sulla sezione di riepilogo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f10d4-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="f10d4-129">Riepilogo dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="f10d4-129">Device summary</span></span> 
<span data-ttu-id="f10d4-130">Mentre le tendenze dei dispositivi mostrano informazioni sui dispositivi di tendenza, il riepilogo dei dispositivi mostra le informazioni sul dispositivo nell'ambito del giorno corrente.</span><span class="sxs-lookup"><span data-stu-id="f10d4-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="f10d4-131">L'ambito dei dati visualizzati nella sezione di riepilogo è 180 giorni prima della data corrente.</span><span class="sxs-lookup"><span data-stu-id="f10d4-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="f10d4-132">Ad esempio, se la data odierna è il 27 marzo 2019, i dati nella sezione di riepilogo rifletteranno i numeri a partire dal 28 settembre 2018 al 27 marzo 2019.</span><span class="sxs-lookup"><span data-stu-id="f10d4-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="f10d4-133">Il filtro applicato alla sezione tendenze non viene applicato alla sezione di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="f10d4-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="f10d4-134">La sezione tendenze dei dispositivi consente di eseguire il drill-down nell'elenco dei dispositivi con il filtro corrispondente applicato.</span><span class="sxs-lookup"><span data-stu-id="f10d4-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="f10d4-135">Ad esempio, facendo clic sulla barra Inattiva nella scheda Stato di integrità sensore verrà visualizzato l'elenco dei dispositivi con risultati che mostrano solo i dispositivi il cui stato del sensore è inattivo.</span><span class="sxs-lookup"><span data-stu-id="f10d4-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="f10d4-136">Attributi del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f10d4-136">Device attributes</span></span>
<span data-ttu-id="f10d4-137">Il report è costituito da schede che visualizzano gli attributi del dispositivo seguenti:</span><span class="sxs-lookup"><span data-stu-id="f10d4-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="f10d4-138">**Stato di** integrità : mostra informazioni sullo stato del sensore nei dispositivi, fornendo una visualizzazione aggregata dei dispositivi attivi, con comunicazioni compromesse, inattive o in cui non vengono visualizzati dati del sensore.</span><span class="sxs-lookup"><span data-stu-id="f10d4-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="f10d4-139">**Stato antivirus per i dispositivi Windows 10 attivi**: mostra il numero di dispositivi e lo stato di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="f10d4-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="f10d4-140">**Piattaforme del sistema operativo**: mostra la distribuzione delle piattaforme del sistema operativo esistenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f10d4-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="f10d4-141">**Versioni di Windows 10**: mostra la distribuzione dei dispositivi Windows 10 e delle relative versioni nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f10d4-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="f10d4-142">Filtrare i dati</span><span class="sxs-lookup"><span data-stu-id="f10d4-142">Filter data</span></span>
 
<span data-ttu-id="f10d4-143">Usa i filtri forniti per includere o escludere i dispositivi con determinati attributi.</span><span class="sxs-lookup"><span data-stu-id="f10d4-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="f10d4-144">Puoi selezionare più filtri da applicare dagli attributi del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f10d4-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="f10d4-145">Questi filtri si **applicano a** tutte le schede del report.</span><span class="sxs-lookup"><span data-stu-id="f10d4-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="f10d4-146">Ad esempio, per mostrare i dati sui dispositivi Windows 10 con stato di integrità del sensore Attivo:</span><span class="sxs-lookup"><span data-stu-id="f10d4-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="f10d4-147">In **Filtri > stato di integrità sensore > Attivo**.</span><span class="sxs-lookup"><span data-stu-id="f10d4-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="f10d4-148">Seleziona quindi **Piattaforme del sistema operativo > Windows 10.**</span><span class="sxs-lookup"><span data-stu-id="f10d4-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="f10d4-149">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="f10d4-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="f10d4-150">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="f10d4-150">Related topic</span></span>
- [<span data-ttu-id="f10d4-151">Report di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="f10d4-151">Threat protection report</span></span>](threat-protection-reports.md)
