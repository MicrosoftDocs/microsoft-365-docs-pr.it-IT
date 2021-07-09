---
title: Configurare device discovery
description: Informazioni su come configurare l'individuazione dei dispositivi Microsoft 365 Defender l'individuazione di base o standard
keywords: basic, standard, configure endpoint discovery, device discovery
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 7125a6953b9be46af9073b50c9268ce65dc0cd30
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339528"
---
# <a name="configure-device-discovery"></a><span data-ttu-id="9acf2-104">Configurare device discovery</span><span class="sxs-lookup"><span data-stu-id="9acf2-104">Configure device discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9acf2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9acf2-105">**Applies to:**</span></span>
- [<span data-ttu-id="9acf2-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="9acf2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9acf2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9acf2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="9acf2-108">L'individuazione può essere configurata per essere in modalità standard o di base.</span><span class="sxs-lookup"><span data-stu-id="9acf2-108">Discovery can be configured to be on standard or basic mode.</span></span> <span data-ttu-id="9acf2-109">Usa l'opzione standard per trovare attivamente i dispositivi nella rete, in modo da garantire meglio l'individuazione degli endpoint e fornire una classificazione dei dispositivi più completa.</span><span class="sxs-lookup"><span data-stu-id="9acf2-109">Use the standard option to actively find devices in your network, which will better guarantee the discovery of endpoints and provide richer device classification.</span></span> 

<span data-ttu-id="9acf2-110">Puoi personalizzare l'elenco dei dispositivi usati per eseguire l'individuazione standard.</span><span class="sxs-lookup"><span data-stu-id="9acf2-110">You can customize the list of devices that are used to perform standard discovery.</span></span> <span data-ttu-id="9acf2-111">Puoi abilitare l'individuazione standard in tutti i dispositivi onboarded che supportano anche questa funzionalità (attualmente - solo dispositivi Windows 10) oppure selezionare un sottoinsieme o sottoinsiemi dei dispositivi specificando i tag del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9acf2-111">You can either enable standard discovery on all the onboarded devices that also support this capability (currently - Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9acf2-112">Per l'anteprima, devi prima attivare le funzionalità di anteprima in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9acf2-112">For preview, you'll first need to turn on the Preview features in Microsoft 365 Defender.</span></span>
> <span data-ttu-id="9acf2-113">Puoi quindi accedere alla configurazione di individuazione dei dispositivi nel centro sicurezza Microsoft 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9acf2-113">You can then access the device discovery configuration in Microsoft 365 security center.</span></span> <span data-ttu-id="9acf2-114">L'elenco dei dispositivi non gestiti e i suggerimenti per la sicurezza saranno disponibili sia nel Centro sicurezza Microsoft 365 Defender che Microsoft 365, mentre i riquadri del dashboard saranno disponibili solo nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9acf2-114">The list of unmanaged devices and security recommendations will be available in both Microsoft 365 Defender and Microsoft 365 security center, while the dashboard tiles will only be available in Microsoft 365 security center.</span></span>

<span data-ttu-id="9acf2-115">Eseguire i passaggi di configurazione seguenti nel Centro sicurezza Microsoft 365 sicurezza:</span><span class="sxs-lookup"><span data-stu-id="9acf2-115">Take the following configuration steps in Microsoft 365 security center:</span></span>

1. <span data-ttu-id="9acf2-116">Passare a **Impostazioni > individuazione dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="9acf2-116">Navigate to **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="9acf2-117">Seleziona la modalità di individuazione da usare nei dispositivi onboarded.</span><span class="sxs-lookup"><span data-stu-id="9acf2-117">Select the discovery mode to use on your onboarded devices.</span></span>
3. <span data-ttu-id="9acf2-118">Se hai scelto di usare l'individuazione standard, seleziona i dispositivi da usare per il sondaggio attivo: tutti i dispositivi o in un sottoinsieme specificando i tag del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9acf2-118">If you've selected to use standard discovery, select which devices to use for active probing: all devices or on a subset by specifying their device tags.</span></span>
4. <span data-ttu-id="9acf2-119">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9acf2-119">Click **Save**.</span></span>

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a><span data-ttu-id="9acf2-120">Escludere i dispositivi dalla ricerca attiva nell'individuazione standard</span><span class="sxs-lookup"><span data-stu-id="9acf2-120">Exclude devices from being actively probed in standard discovery</span></span>

<span data-ttu-id="9acf2-121">Se nella rete sono presenti dispositivi che non devono essere analizzati attivamente (ad esempio, i dispositivi usati come honeypot per un altro strumento di sicurezza), puoi anche definire un elenco di esclusioni per impedirne l'analisi.</span><span class="sxs-lookup"><span data-stu-id="9acf2-121">If there are devices on your network which should not be actively scanned (for example, devices used as honeypots for another security tool), you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="9acf2-122">Tieni presente che i dispositivi possono ancora essere individuati usando la modalità di individuazione di base.</span><span class="sxs-lookup"><span data-stu-id="9acf2-122">Note that devices can still be discovered using Basic discovery mode.</span></span> <span data-ttu-id="9acf2-123">Questi dispositivi verranno individuati passivamente, ma non verranno sondati attivamente.</span><span class="sxs-lookup"><span data-stu-id="9acf2-123">Those devices will be passively discovered but won't be actively probed.</span></span> 

## <a name="select-networks-to-monitor"></a><span data-ttu-id="9acf2-124">Selezionare le reti da monitorare</span><span class="sxs-lookup"><span data-stu-id="9acf2-124">Select networks to monitor</span></span>

 <span data-ttu-id="9acf2-125">Microsoft Defender for Endpoint analizza una rete e determina se è una rete aziendale che deve essere monitorata o una rete non aziendale che può essere ignorata.</span><span class="sxs-lookup"><span data-stu-id="9acf2-125">Microsoft Defender for Endpoint analyzes a network and determines if it is a corporate network that needs to be monitored or a non-corporate network that can be ignored.</span></span> <span data-ttu-id="9acf2-126">Le reti aziendali vengono in genere scelte per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="9acf2-126">Corporate networks are typically chosen to be monitored.</span></span> <span data-ttu-id="9acf2-127">Tuttavia, puoi ignorare questa decisione scegliendo di monitorare le reti non aziendali in cui vengono trovati i dispositivi onboarded.</span><span class="sxs-lookup"><span data-stu-id="9acf2-127">However, you can override this decision by choosing to monitor non-corporate networks where onboarded devices are found.</span></span> 

<span data-ttu-id="9acf2-128">Puoi configurare la posizione in cui è possibile eseguire l'individuazione dei dispositivi specificando le reti da monitorare.</span><span class="sxs-lookup"><span data-stu-id="9acf2-128">You can configure where device discovery can be performed by specifying which networks to monitor.</span></span> <span data-ttu-id="9acf2-129">Quando una rete viene monitorata, l'individuazione dei dispositivi può essere eseguita su di essa.</span><span class="sxs-lookup"><span data-stu-id="9acf2-129">When a network is monitored, device discovery can be performed on it.</span></span> 

<span data-ttu-id="9acf2-130">Nella pagina Reti monitorate viene visualizzato un elenco delle reti in cui è possibile eseguire **l'individuazione dei** dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9acf2-130">A list of networks where device discovery can be performed is shown in the **Monitored networks** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="9acf2-131">Solo le prime 50 reti (in base al numero di dispositivi associati) saranno disponibili nell'elenco di rete.</span><span class="sxs-lookup"><span data-stu-id="9acf2-131">Only top 50 networks (according to the number of associated devices) will be available in the network list.</span></span> 

<span data-ttu-id="9acf2-132">L'elenco delle reti monitorate viene ordinato in base al numero totale di dispositivi visualizzati nella rete negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="9acf2-132">The list of monitored networks is sorted based upon the total number of devices seen on the network in the last 7 days.</span></span>

<span data-ttu-id="9acf2-133">È possibile applicare un filtro per visualizzare uno dei seguenti stati di individuazione della rete:</span><span class="sxs-lookup"><span data-stu-id="9acf2-133">You can apply a filter to view any of the following network discovery states:</span></span>

- <span data-ttu-id="9acf2-134">**Reti monitorate: reti** in cui viene eseguito l'individuazione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9acf2-134">**Monitored networks** - Networks where device discovery is performed.</span></span>
- <span data-ttu-id="9acf2-135">**Reti ignorate:** questa rete verrà ignorata e l'individuazione dei dispositivi non verrà eseguita su di essa.</span><span class="sxs-lookup"><span data-stu-id="9acf2-135">**Ignored networks** - This network will be ignored and device discovery will not be performed on it.</span></span>
- <span data-ttu-id="9acf2-136">**All** : verranno visualizzate sia le reti monitorate che le reti ignorate.</span><span class="sxs-lookup"><span data-stu-id="9acf2-136">**All** - Both monitored and ignored networks will be displayed.</span></span>

### <a name="configure-the-network-monitor-state"></a><span data-ttu-id="9acf2-137">Configurare lo stato di Network Monitor</span><span class="sxs-lookup"><span data-stu-id="9acf2-137">Configure the network monitor state</span></span>

<span data-ttu-id="9acf2-138">Puoi controllare dove avviene l'individuazione dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9acf2-138">You control where device discovery takes place.</span></span> <span data-ttu-id="9acf2-139">Le reti monitorate sono il punto in cui verrà eseguita l'individuazione dei dispositivi e in genere sono reti aziendali.</span><span class="sxs-lookup"><span data-stu-id="9acf2-139">Monitored networks is where device discovery will be performed and are typically corporate networks.</span></span> <span data-ttu-id="9acf2-140">È inoltre possibile scegliere di ignorare le reti o selezionare la classificazione di individuazione iniziale dopo aver modificato uno stato.</span><span class="sxs-lookup"><span data-stu-id="9acf2-140">You can also choose to ignore networks or select the initial discovery classification after modifying a state.</span></span>

<span data-ttu-id="9acf2-141">Scegliere la classificazione di individuazione iniziale significa applicare lo stato di Network Monitor predefinito.</span><span class="sxs-lookup"><span data-stu-id="9acf2-141">Choosing the initial discovery classification means applying the default system-made network monitor state.</span></span> <span data-ttu-id="9acf2-142">Se si seleziona lo stato predefinito di Network Monitor creato dal sistema, le reti identificate come aziendali, verranno monitorate e quelle identificate come non aziendali verranno ignorate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9acf2-142">Selecting the default system-made network monitor state means that networks that were identified to be corporate, will be monitored, and ones identified as non-corporate, will be ignored automatically.</span></span>

1. <span data-ttu-id="9acf2-143">Selezionare **Impostazioni > individuazione dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="9acf2-143">Select **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="9acf2-144">Selezionare **Reti monitorate.**</span><span class="sxs-lookup"><span data-stu-id="9acf2-144">Select **Monitored networks**.</span></span>
3. <span data-ttu-id="9acf2-145">Visualizzare l'elenco delle reti.</span><span class="sxs-lookup"><span data-stu-id="9acf2-145">View the list of networks.</span></span>
4. <span data-ttu-id="9acf2-146">Selezionare i tre puntini accanto al nome di rete.</span><span class="sxs-lookup"><span data-stu-id="9acf2-146">Select the three dots next to the network name.</span></span>
5. <span data-ttu-id="9acf2-147">Scegliere se si desidera monitorare, ignorare o utilizzare la classificazione di individuazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="9acf2-147">Choose whether you want to monitor, ignore, or use the initial discovery classification.</span></span>

    > [!WARNING]
    >
    > - <span data-ttu-id="9acf2-148">La scelta di monitorare una rete non identificata da Microsoft Defender for Endpoint come rete aziendale può causare l'individuazione dei dispositivi all'esterno della rete aziendale e quindi rilevare dispositivi di casa o altri dispositivi non aziendali.</span><span class="sxs-lookup"><span data-stu-id="9acf2-148">Choosing to monitor a network that was not identified by Microsoft Defender for Endpoint as a corporate network can cause device discovery outside of your corporate network, and may therefore detect home or other non-corporate devices.</span></span>
    > - <span data-ttu-id="9acf2-149">La scelta di ignorare una rete interromperà il monitoraggio e l'individuazione dei dispositivi in tale rete.</span><span class="sxs-lookup"><span data-stu-id="9acf2-149">Choosing to ignore a network will stop monitoring and discovering devices in that network.</span></span> <span data-ttu-id="9acf2-150">I dispositivi già individuati non verranno rimossi dall'inventario, ma non verranno più aggiornati e i dettagli verranno conservati fino alla scadenza del periodo di conservazione dei dati di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9acf2-150">Devices that were already discovered will not be removed from the inventory, but will no longer be updated, and details will be retained until the data retention period of the Defender for Endpoint expires.</span></span>
    > - <span data-ttu-id="9acf2-151">Prima di scegliere di monitorare le reti non aziendali, è necessario assicurarsi di disporre dell'autorizzazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="9acf2-151">Before choosing to monitor non-corporate networks, you must ensure you have permission to do so.</span></span>

6. <span data-ttu-id="9acf2-152">Confermare che si desidera apportare la modifica.</span><span class="sxs-lookup"><span data-stu-id="9acf2-152">Confirm that you want to make the change.</span></span> 

## <a name="explore-devices-in-the-network"></a><span data-ttu-id="9acf2-153">Esplorare i dispositivi nella rete</span><span class="sxs-lookup"><span data-stu-id="9acf2-153">Explore devices in the network</span></span>

<span data-ttu-id="9acf2-154">È possibile utilizzare la query di ricerca avanzata seguente per ottenere più contesto su ogni nome di rete descritto nell'elenco delle reti.</span><span class="sxs-lookup"><span data-stu-id="9acf2-154">You can use the following advanced hunting query to get more context about each network name described in the networks list.</span></span> <span data-ttu-id="9acf2-155">La query elenca tutti i dispositivi onboarded connessi a una determinata rete negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="9acf2-155">The query lists all the onboarded devices that were connected to a certain network within the last 7 days.</span></span>

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
```

## <a name="see-also"></a><span data-ttu-id="9acf2-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9acf2-156">See also</span></span>

- [<span data-ttu-id="9acf2-157">Panoramica di Device discovery</span><span class="sxs-lookup"><span data-stu-id="9acf2-157">Device discovery overview</span></span>](device-discovery.md)
- [<span data-ttu-id="9acf2-158">Domande frequenti su Individuazione dispositivi</span><span class="sxs-lookup"><span data-stu-id="9acf2-158">Device discovery FAQs</span></span>](device-discovery-faq.md)
