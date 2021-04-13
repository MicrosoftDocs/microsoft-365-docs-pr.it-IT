---
title: Panoramica dell'individuazione dei dispositivi
description: Informazioni su come sfruttare l'individuazione degli endpoint in Microsoft 365 Defender per trovare i dispositivi non gestiti nella rete
keywords: individuazione dei dispositivi, individuazione, passiva, proattiva, rete, visibilità, server, workstation, onboard, dispositivi non gestiti
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2e58b6048f9d815d759cd78ceb3316eb2ed6f66d
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698445"
---
# <a name="device-discovery-overview"></a><span data-ttu-id="bd569-104">Panoramica dell'individuazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="bd569-104">Device discovery overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bd569-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="bd569-105">**Applies to:**</span></span>
- [<span data-ttu-id="bd569-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="bd569-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="bd569-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd569-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="bd569-108">La protezione dell'ambiente richiede l'inventario dei dispositivi presenti nella rete.</span><span class="sxs-lookup"><span data-stu-id="bd569-108">Protecting your environment requires taking inventory of the devices that are in your network.</span></span> <span data-ttu-id="bd569-109">Tuttavia, il mapping dei dispositivi in una rete può spesso essere costoso, impegnativo e dispendioso in termini di tempo.</span><span class="sxs-lookup"><span data-stu-id="bd569-109">However, mapping devices in a network can often be expensive, challenging, and time-consuming.</span></span> 

<span data-ttu-id="bd569-110">Microsoft Defender for Endpoint offre una funzionalità di individuazione dei dispositivi che consente di trovare dispositivi non gestiti connessi alla rete aziendale senza la necessità di dispositivi aggiuntivi o modifiche di processo ingombranti.</span><span class="sxs-lookup"><span data-stu-id="bd569-110">Microsoft Defender for Endpoint provides a device discovery capability that helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span>


<span data-ttu-id="bd569-111">La funzionalità di individuazione dei dispositivi consente di:</span><span class="sxs-lookup"><span data-stu-id="bd569-111">The device discovery capability allows you to:</span></span>

- <span data-ttu-id="bd569-112">**Individuare gli endpoint aziendali connessi alla rete aziendale**</span><span class="sxs-lookup"><span data-stu-id="bd569-112">**Discover enterprise endpoints connected to your corporate network**</span></span> <br>
<span data-ttu-id="bd569-113">Usando le opzioni di individuazione di base o standard, puoi individuare workstation, server ed endpoint mobili non ancora onboarded in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd569-113">Using either basic or standard discovery options, you can discover workstations, servers, and mobile endpoints that are not yet onboarded to Microsoft Defender for Endpoint.</span></span>  

- <span data-ttu-id="bd569-114">**Onboard degli endpoint individuati**</span><span class="sxs-lookup"><span data-stu-id="bd569-114">**Onboard discovered endpoints**</span></span><br>
<span data-ttu-id="bd569-115">Gli endpoint non gestiti nella rete introducono vulnerabilità e rischi per la rete.</span><span class="sxs-lookup"><span data-stu-id="bd569-115">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="bd569-116">L'onboarding al servizio può aumentare la visibilità della sicurezza su di essi.</span><span class="sxs-lookup"><span data-stu-id="bd569-116">Onboarding them to the service can increase the security visibility on them.</span></span> 

<span data-ttu-id="bd569-117">In combinazione con questa funzionalità, una nuova raccomandazione di sicurezza per l'onboard di dispositivi a Microsoft Defender for Endpoint sarà disponibile nell'ambito dell'esperienza di gestione delle minacce e delle vulnerabilità esistente.</span><span class="sxs-lookup"><span data-stu-id="bd569-117">In conjunction with this capability, a new security recommendation to onboard devices to Microsoft Defender for Endpoint will be available as part of the existing Threat and Vulnerability Management experience.</span></span>



## <a name="discovery-methods"></a><span data-ttu-id="bd569-118">Metodi di individuazione</span><span class="sxs-lookup"><span data-stu-id="bd569-118">Discovery methods</span></span>
<span data-ttu-id="bd569-119">Esistono due modalità di individuazione:</span><span class="sxs-lookup"><span data-stu-id="bd569-119">There are two modes of discovery:</span></span> 

-   <span data-ttu-id="bd569-120">Individuazione di base</span><span class="sxs-lookup"><span data-stu-id="bd569-120">Basic discovery</span></span> 
-   <span data-ttu-id="bd569-121">Individuazione standard (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="bd569-121">Standard discovery (recommended)</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="bd569-122">L'individuazione è impostata sulla modalità di base.</span><span class="sxs-lookup"><span data-stu-id="bd569-122">Discovery is set to basic mode.</span></span> <span data-ttu-id="bd569-123">Puoi scegliere di mantenere questa configurazione tramite la pagina delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="bd569-123">You can choose to retain this configuration through the settings page.</span></span> <span data-ttu-id="bd569-124">L'individuazione standard sarà la modalità predefinita per tutti i clienti di anteprima a partire dal 10 maggio 2021, a meno che non venga modificata tramite la pagina delle impostazioni prima di questa data.</span><span class="sxs-lookup"><span data-stu-id="bd569-124">Standard discovery will be the default mode for all preview customers starting May 10, 2021 - unless modified through the settings page before this date.</span></span>

### <a name="basic-discovery"></a><span data-ttu-id="bd569-125">Individuazione di base</span><span class="sxs-lookup"><span data-stu-id="bd569-125">Basic discovery</span></span> 

<span data-ttu-id="bd569-126">In questa modalità, gli endpoint raccoglieranno passivamente gli eventi nella rete ed estrarranno le informazioni sul dispositivo da essi.</span><span class="sxs-lookup"><span data-stu-id="bd569-126">In this mode, endpoints will passively collect events in your network and extract device information from them.</span></span> <span data-ttu-id="bd569-127">L'individuazione di base usa SenseNDR.exe binario per la raccolta passiva dei dati di rete e non verrà avviato alcun traffico di rete.</span><span class="sxs-lookup"><span data-stu-id="bd569-127">Basic discovery uses the SenseNDR.exe binary for passive network data collection and no network traffic will be initiated.</span></span> <span data-ttu-id="bd569-128">Gli endpoint estraggono semplicemente i dati da ogni traffico di rete visualizzato da un dispositivo onboarded.</span><span class="sxs-lookup"><span data-stu-id="bd569-128">Endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> 

### <a name="standard-discovery"></a><span data-ttu-id="bd569-129">Individuazione standard</span><span class="sxs-lookup"><span data-stu-id="bd569-129">Standard discovery</span></span> 

<span data-ttu-id="bd569-130">Questa modalità consente agli endpoint di sondare attivamente i dispositivi osservati nella rete per arricchire i dati raccolti, consentendoti di creare un inventario dei dispositivi affidabile e coerente.</span><span class="sxs-lookup"><span data-stu-id="bd569-130">This mode allows endpoints to actively probe observed devices in the network to enrich collected data - helping you build a reliable and coherent device inventory.</span></span> <span data-ttu-id="bd569-131">La modalità standard usa il probe intelligente e attivo per individuare ulteriori informazioni sui dispositivi osservati per arricchire le informazioni esistenti sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd569-131">Standard mode uses smart, active probing to discover even more information about observed devices to enrich existing device information.</span></span>  

<span data-ttu-id="bd569-132">Quando è abilitata la modalità Standard, le attività di rete minime e trascurabili generate dal sensore di individuazione potrebbero essere osservate dagli strumenti di monitoraggio della rete nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bd569-132">When Standard mode is enabled, minimal and negligible network activity generated by the discovery sensor might be observed by network monitoring tools in your organization.</span></span>  

 <span data-ttu-id="bd569-133">Se scegli di non abilitare questa modalità, ottieni solo una visibilità limitata degli endpoint non gestiti nella rete.</span><span class="sxs-lookup"><span data-stu-id="bd569-133">If you choose not to enable this mode, you will only gain limited visibility of unmanaged endpoints in your network.</span></span>

<span data-ttu-id="bd569-134">L'individuazione standard usa vari script di PowerShell per sondare attivamente i dispositivi nella rete.</span><span class="sxs-lookup"><span data-stu-id="bd569-134">Standard discovery uses various PowerShell scripts to actively probe devices in the network.</span></span> <span data-ttu-id="bd569-135">Tali script di PowerShell sono firmati da Microsoft e vengono eseguiti dal percorso seguente: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` .</span><span class="sxs-lookup"><span data-stu-id="bd569-135">Those PowerShell scripts are Microsoft signed and are executed from the following location: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`.</span></span> <span data-ttu-id="bd569-136">Ad esempio, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span><span class="sxs-lookup"><span data-stu-id="bd569-136">For example, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span></span>

<span data-ttu-id="bd569-137">È possibile modificare e personalizzare le impostazioni di individuazione, per ulteriori informazioni, vedere [Configure device discovery.](configure-device-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="bd569-137">You can change and customize your discovery settings, for more information see [Configure device discovery](configure-device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bd569-138">Il motore di individuazione distingue tra gli eventi di rete ricevuti nella rete aziendale e l'esterno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="bd569-138">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="bd569-139">I dispositivi non connessi a reti aziendali non verranno individuati o elencati nell'inventario dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="bd569-139">Devices that are not connected to corporate networks will not be discovered or listed in the device inventory.</span></span> 



## <a name="device-inventory"></a><span data-ttu-id="bd569-140">Inventario dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="bd569-140">Device Inventory</span></span> 
<span data-ttu-id="bd569-141">I dispositivi individuati ma non ancora stati onboarded e protetti da Microsoft Defender for Endpoint saranno elencati in Inventario dispositivi all'interno della scheda Endpoint. Ora puoi usare un nuovo filtro nell'elenco dell'inventario dei dispositivi denominato Stato onboarding che può avere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd569-141">Devices that have been discovered but have not yet been onboarded and secured by Microsoft Defender for Endpoint will be listed in Device Inventory within the Endpoints tab. You can now use a new filter in the device inventory list called Onboarding status which can have any of the following values:</span></span>

- <span data-ttu-id="bd569-142">Onboarded: l'endpoint viene onboarded in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd569-142">Onboarded – The endpoint is onboarded to Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="bd569-143">Può essere onboarded: l'endpoint è stato individuato nella rete e il sistema operativo è stato identificato come supportato da Microsoft Defender per Endpoint, ma non è attualmente onboarded.</span><span class="sxs-lookup"><span data-stu-id="bd569-143">Can be onboarded – The endpoint was discovered in the network and the Operating System was identified as one that is supported by Microsoft Defender for Endpoint, but it is not currently onboarded.</span></span> <span data-ttu-id="bd569-144">Ti consigliamo vivamente di eseguire l'onboarding di questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="bd569-144">We highly recommend onboarding these devices.</span></span>
- <span data-ttu-id="bd569-145">Non supportato: l'endpoint è stato individuato nella rete ma non è supportato da Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd569-145">Unsupported – The endpoint was discovered in the network but is not supported by Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="bd569-146">Informazioni insufficienti: il sistema non è stato in grado di determinare la supportabilità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd569-146">Insufficient info – The system could not determine the supportability of the device.</span></span> <span data-ttu-id="bd569-147">L'abilitazione dell'individuazione standard in più dispositivi nella rete può arricchire gli attributi individuati.</span><span class="sxs-lookup"><span data-stu-id="bd569-147">Enabling standard discovery on more devices in the network can enrich the discovered attributes.</span></span> 
 

![Immagine del dashboard dell'inventario dei dispositivi](images/2b62255cd3a9dd42f3219e437b956fb9.png)



## <a name="vulnerability-assessment-on-discovered-devices"></a><span data-ttu-id="bd569-149">Valutazione della vulnerabilità nei dispositivi individuati</span><span class="sxs-lookup"><span data-stu-id="bd569-149">Vulnerability assessment on discovered devices</span></span>
<span data-ttu-id="bd569-150">Le vulnerabilità e i rischi nei dispositivi, nonché altri dispositivi non gestiti individuati nella rete, fanno parte dei flussi TVM correnti in "Suggerimenti per la sicurezza" e sono rappresentati nelle pagine delle entità nel portale.</span><span class="sxs-lookup"><span data-stu-id="bd569-150">Vulnerabilities and risks on your devices as well as other discovered unmanaged devices in the network are part of the current TVM flows under "Security Recommendations" and represented in entity pages across the portal.</span></span> <span data-ttu-id="bd569-151">Cercare suggerimenti sulla sicurezza correlati a "SSH" per individuare le vulnerabilità SSH correlate ai dispositivi gestiti e non gestiti.</span><span class="sxs-lookup"><span data-stu-id="bd569-151">Search for "SSH" related security recommendations to find SSH vulnerabilities that are related for unmanaged and managed devices.</span></span> 

![Immagine del dashboard degli elementi consigliati per la sicurezza](images/1156c82ffadd356ce329d1cf551e806c.png)  

## <a name="use-advanced-hunting-on-discovered-devices"></a><span data-ttu-id="bd569-153">Usare Ricerca avanzata nei dispositivi individuati</span><span class="sxs-lookup"><span data-stu-id="bd569-153">Use Advanced Hunting on discovered devices</span></span>
<span data-ttu-id="bd569-154">Puoi usare query di ricerca avanzata per ottenere visibilità sui dispositivi individuati.</span><span class="sxs-lookup"><span data-stu-id="bd569-154">You can use Advanced Hunting queries to gain visibility on discovered devices.</span></span>
<span data-ttu-id="bd569-155">Trova i dettagli sugli endpoint individuati nella tabella DeviceInfo o informazioni correlate alla rete su tali dispositivi nella tabella DeviceNetworkInfo.</span><span class="sxs-lookup"><span data-stu-id="bd569-155">Find details about discovered Endpoints in the DeviceInfo table, or network-related information about those devices in the DeviceNetworkInfo table.</span></span>
  

![Immagine dell'uso avanzato della ricerca](images/f48ba1779eddee9872f167453c24e5c9.png)


<span data-ttu-id="bd569-157">L'individuazione dei dispositivi sfrutta i dispositivi onboarded di Microsoft Defender for Endpoint come origine dati di rete per attribuite le attività ai dispositivi non onboarded.</span><span class="sxs-lookup"><span data-stu-id="bd569-157">Device discovery leverages Microsoft Defender for Endpoint onboarded devices as a network data source to attribute activities to non-onboarded devices.</span></span> <span data-ttu-id="bd569-158">Ciò significa che se un dispositivo onboarded di Microsoft Defender per Endpoint comunica con un dispositivo non onboarded, le attività sul dispositivo non onboarded possono essere visualizzate nella sequenza temporale e tramite la tabella Advanced hunting DeviceNetworkEvents.</span><span class="sxs-lookup"><span data-stu-id="bd569-158">This means that if a Microsoft Defender for Endpoint onboarded device communicated with a non-onboarded device, activities on the non-onboarded device can be seen on the timeline and through the Advanced hunting DeviceNetworkEvents table.</span></span> 



<span data-ttu-id="bd569-159">I nuovi eventi sono basati sulle connessioni TCP (Transmission Control Protocol) e si adattano alla combinazione DeviceNetworkEvents corrente.</span><span class="sxs-lookup"><span data-stu-id="bd569-159">New events are Transmission Control Protocol (TCP) connections-based and will fit to the current DeviceNetworkEvents scheme.</span></span> <span data-ttu-id="bd569-160">Ingresso TCP verso il dispositivo abilitato per Microsoft Defender per Endpoint da un dispositivo non Abilitato per Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bd569-160">TCP ingress to the Microsoft Defender for Endpoint enabled device from a non-Microsoft Defender for Endpoint enabled.</span></span>  

<span data-ttu-id="bd569-161">Sono stati aggiunti anche i seguenti tipi di azione:</span><span class="sxs-lookup"><span data-stu-id="bd569-161">The following action types have also been added:</span></span>  

- <span data-ttu-id="bd569-162">ConnectionAttempt - Tentativo di stabilire una connessione TCP (syn)</span><span class="sxs-lookup"><span data-stu-id="bd569-162">ConnectionAttempt - An attempt to establish a TCP connection (syn)</span></span>  
- <span data-ttu-id="bd569-163">ConnectionAcknowledged - Conferma dell'accettazione di una connessione TCP (syn\ack)</span><span class="sxs-lookup"><span data-stu-id="bd569-163">ConnectionAcknowledged - An acknowledgment that a TCP connection was accepted (syn\ack)</span></span>  

<span data-ttu-id="bd569-164">È possibile provare questa query di esempio:</span><span class="sxs-lookup"><span data-stu-id="bd569-164">You can try this example query:</span></span>  

```
DeviceNetworkEvents  
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"  
| take 10  
```


## <a name="changed-behaviour"></a><span data-ttu-id="bd569-165">Comportamento modificato</span><span class="sxs-lookup"><span data-stu-id="bd569-165">Changed behaviour</span></span>
<span data-ttu-id="bd569-166">Nella sezione seguente sono elencate le modifiche che verranno osservate in Microsoft Defender per Endpoint e/o Centro sicurezza Microsoft 365 quando questa funzionalità è abilitata.</span><span class="sxs-lookup"><span data-stu-id="bd569-166">The following section lists the changes you'll observe in Microsoft Defender for Endpoint and/or Microsoft 365 Security Center when this capability is enabled.</span></span> 
 
1.  <span data-ttu-id="bd569-167">I dispositivi non onboarded in Microsoft Defender to Endpoint dovrebbero essere visualizzati nell'inventario dei dispositivi, nella ricerca avanzata e nelle query API.</span><span class="sxs-lookup"><span data-stu-id="bd569-167">Devices that are not onboarded to Microsoft Defender to Endpoint are expected to appear in the device inventory, advanced hunting, and API queries.</span></span> <span data-ttu-id="bd569-168">Ciò può aumentare in modo significativo le dimensioni dei risultati delle query.</span><span class="sxs-lookup"><span data-stu-id="bd569-168">This may significantly increase the size of query results.</span></span> 
    1. <span data-ttu-id="bd569-169">Le tabelle "DeviceInfo" e "DeviceNetworkInfo" in Ricerca avanzata ora conteneranno il dispositivo individuato.</span><span class="sxs-lookup"><span data-stu-id="bd569-169">"DeviceInfo" and "DeviceNetworkInfo" tables in Advanced Hunting will now hold discovered device.</span></span> <span data-ttu-id="bd569-170">Puoi filtrare tali dispositivi usando l'attributo "OnboardingStatus".</span><span class="sxs-lookup"><span data-stu-id="bd569-170">You can filter out those devices by using “OnboardingStatus” attribute.</span></span>

    2. <span data-ttu-id="bd569-171">Si prevede che i dispositivi individuati vengano visualizzati nei risultati delle query dell'API di streaming.</span><span class="sxs-lookup"><span data-stu-id="bd569-171">Discovered devices are expected to appear in Streaming API query results.</span></span> <span data-ttu-id="bd569-172">È possibile filtrare tali dispositivi utilizzando il `OnboardingStatus` filtro nella query.</span><span class="sxs-lookup"><span data-stu-id="bd569-172">You can filter out those devices by using the `OnboardingStatus` filter in your query.</span></span> 

2.  <span data-ttu-id="bd569-173">I dispositivi non gestiti verranno assegnati ai gruppi di dispositivi esistenti in base ai criteri definiti.</span><span class="sxs-lookup"><span data-stu-id="bd569-173">Unmanaged devices will be assigned to existing device groups based on the defined criteria.</span></span> 
3.  <span data-ttu-id="bd569-174">In rari casi, l'individuazione standard potrebbe attivare avvisi su monitor di rete o strumenti di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bd569-174">In rare cases, Standard discovery might trigger alerts on network monitors or security tools.</span></span> <span data-ttu-id="bd569-175">Inviare commenti e suggerimenti, se si verificano eventi di questo tipo, per evitare che questi problemi si verifichino.</span><span class="sxs-lookup"><span data-stu-id="bd569-175">Please provide feedback, if you experience such events, to help prevent these issues from recurring.</span></span> <span data-ttu-id="bd569-176">È possibile escludere in modo esplicito destinazioni specifiche o intere subnet dal sondaggio attivo tramite l'individuazione standard.</span><span class="sxs-lookup"><span data-stu-id="bd569-176">You can explicitly exclude specific targets or entire subnets from being actively probed by Standard discovery.</span></span> 



## <a name="next-steps"></a><span data-ttu-id="bd569-177">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="bd569-177">Next steps</span></span>
- [<span data-ttu-id="bd569-178">Configurare l'individuazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="bd569-178">Configure device discovery</span></span>](configure-device-discovery.md)
- [<span data-ttu-id="bd569-179">Domande frequenti su Individuazione dispositivi</span><span class="sxs-lookup"><span data-stu-id="bd569-179">Device discovery FAQs</span></span>](device-discovery-faq.md)
