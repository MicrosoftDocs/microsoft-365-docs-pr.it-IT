---
title: Strumento di verifica di valutazione dell’idonietà scaricabile
description: Controlla le impostazioni di dispositivo e di rete, inclusi gli endpoint obbligatori
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581035"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="6630e-104">Strumento di verifica di valutazione dell’idonietà scaricabile</span><span class="sxs-lookup"><span data-stu-id="6630e-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="6630e-105">Per funzionare correttamente con Microsoft Managed Desktop, i dispositivi devono soddisfare determinati requisiti per l'hardware e le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6630e-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="6630e-106">Inoltre, ogni dispositivo deve essere in grado di raggiungere gli endpoint chiave.</span><span class="sxs-lookup"><span data-stu-id="6630e-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="6630e-107">Scaricare ed eseguire questo strumento per ottenere un report HTML, visualizzare i risultati e quindi eseguire un'azione.</span><span class="sxs-lookup"><span data-stu-id="6630e-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="6630e-108">Dovrai scaricare lo strumento e i file di supporto e quindi eseguirlo manualmente su ogni dispositivo che vuoi registrare in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6630e-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="6630e-109">Per ogni controllo, lo strumento segnala uno dei tre possibili risultati:</span><span class="sxs-lookup"><span data-stu-id="6630e-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="6630e-110">Risultato</span><span class="sxs-lookup"><span data-stu-id="6630e-110">Result</span></span>  |<span data-ttu-id="6630e-111">Significato</span><span class="sxs-lookup"><span data-stu-id="6630e-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="6630e-112">Pronto</span><span class="sxs-lookup"><span data-stu-id="6630e-112">Ready</span></span>     | <span data-ttu-id="6630e-113">Non è necessaria alcuna azione prima di completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="6630e-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="6630e-114">Avviso</span><span class="sxs-lookup"><span data-stu-id="6630e-114">Advisory</span></span>    | <span data-ttu-id="6630e-115">Seguire i passaggi nello strumento per un'esperienza ottimale con la registrazione e per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6630e-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="6630e-116">Puoi *completare* la registrazione, ma devi risolvere questi problemi prima di distribuire il primo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6630e-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="6630e-117">Non pronto</span><span class="sxs-lookup"><span data-stu-id="6630e-117">Not ready</span></span> | <span data-ttu-id="6630e-118">*La registrazione avrà esito* negativo se questi problemi non vengono risolti.</span><span class="sxs-lookup"><span data-stu-id="6630e-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="6630e-119">Segui i passaggi nello strumento per risolverli.</span><span class="sxs-lookup"><span data-stu-id="6630e-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="6630e-120">Ottenere lo correttore</span><span class="sxs-lookup"><span data-stu-id="6630e-120">Obtain the checker</span></span>

<span data-ttu-id="6630e-121">Scaricare il file ZIP da https://aka.ms/mmddratoolv0 .</span><span class="sxs-lookup"><span data-stu-id="6630e-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="6630e-122">L'utente che esegue lo strumento deve disporre dei diritti di amministratore locale nel dispositivo in cui è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6630e-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="6630e-123">Eseguire quindi lo strumento seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="6630e-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="6630e-124">Copia il file ZIP scaricato in ogni dispositivo che vuoi controllare.</span><span class="sxs-lookup"><span data-stu-id="6630e-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="6630e-125">Estrarre tutti i file nel download compresso.</span><span class="sxs-lookup"><span data-stu-id="6630e-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="6630e-126">Eseguire **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span><span class="sxs-lookup"><span data-stu-id="6630e-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="6630e-127">Quando viene visualizzato il prompt Controllo di accesso utente, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6630e-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="6630e-128">Lo strumento viene eseguito e apre un report nel browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="6630e-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="6630e-129">Puoi anche scaricare ed estrarre l'archivio zip  in un percorso condiviso, accedereMicrosoft.MMD.DeviceReadinessAssessmentTool.exeda ogni dispositivo ed eseguirlo in locale.</span><span class="sxs-lookup"><span data-stu-id="6630e-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="6630e-130">Controlli</span><span class="sxs-lookup"><span data-stu-id="6630e-130">Checks</span></span>

<span data-ttu-id="6630e-131">Lo strumento scaricabile controlla questi elementi correlati al dispositivo e alla rete:</span><span class="sxs-lookup"><span data-stu-id="6630e-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="6630e-132">Hardware</span><span class="sxs-lookup"><span data-stu-id="6630e-132">Hardware</span></span>

<span data-ttu-id="6630e-133">I dispositivi devono soddisfare requisiti hardware specifici per l'utilizzo con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6630e-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="6630e-134">Attualmente, solo specifici [dispositivi approvati](../service-description/device-list.md) sono autorizzati a registrare.</span><span class="sxs-lookup"><span data-stu-id="6630e-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="6630e-135">Se il dispositivo non supera uno dei controlli, non è compatibile con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6630e-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="6630e-136">Endpoint di rete</span><span class="sxs-lookup"><span data-stu-id="6630e-136">Network endpoints</span></span>

<span data-ttu-id="6630e-137">I dispositivi sono in grado di raggiungere diversi [endpoint chiave](network.md) per funzionare con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6630e-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="6630e-138">Se lo strumento segnala un **risultato Non** pronto, vedi il report dettagliato per scoprire quali endpoint non erano raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="6630e-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="6630e-139">Regola quindi il firewall o altre impostazioni di rete per assicurarti che tali endpoint possano essere raggiunti.</span><span class="sxs-lookup"><span data-stu-id="6630e-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="6630e-140">Altre impostazioni</span><span class="sxs-lookup"><span data-stu-id="6630e-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="6630e-141">Profili Wi-Fi aziendali</span><span class="sxs-lookup"><span data-stu-id="6630e-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="6630e-142">Un **risultato di advisory** significa che stai usando alcuni profili Wi-Fi che necessitano di certificati e profili per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="6630e-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="6630e-143">Per altre informazioni, vedi [Distribuire certificati e profilo Wi-Fi/VPN.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)</span><span class="sxs-lookup"><span data-stu-id="6630e-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="6630e-144">Profili LAN</span><span class="sxs-lookup"><span data-stu-id="6630e-144">LAN profiles</span></span>

<span data-ttu-id="6630e-145">Un **risultato di advisory** indica che sono disponibili reti LAN che necessitano di certificati e profili per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="6630e-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="6630e-146">Per ulteriori informazioni, vedere [Prepare certificates and network profiles for Microsoft Managed Desktop.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="6630e-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="6630e-147">Profili VPN</span><span class="sxs-lookup"><span data-stu-id="6630e-147">VPN profiles</span></span>

<span data-ttu-id="6630e-148">Un **risultato di** advisory indica che stai usando una rete privata virtuale (VPN).</span><span class="sxs-lookup"><span data-stu-id="6630e-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="6630e-149">Creare un profilo VPN che distribuisca i certificati integrati con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="6630e-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="6630e-150">Per ulteriori informazioni, vedere [Prepare certificates and network profiles for Microsoft Managed Desktop.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="6630e-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="6630e-151">Unità mappate</span><span class="sxs-lookup"><span data-stu-id="6630e-151">Mapped drives</span></span>

<span data-ttu-id="6630e-152">Un **risultato di advisory** indica che sono disponibili alcune unità mappate, che non sono consigliate.</span><span class="sxs-lookup"><span data-stu-id="6630e-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="6630e-153">Per ulteriori informazioni, vedere [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span><span class="sxs-lookup"><span data-stu-id="6630e-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="6630e-154">Code di stampa</span><span class="sxs-lookup"><span data-stu-id="6630e-154">Print queues</span></span>

<span data-ttu-id="6630e-155">Un **risultato di advisory** indica che sono disponibili alcune code di stampa in sospeso, che non sono consigliate.</span><span class="sxs-lookup"><span data-stu-id="6630e-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="6630e-156">Una soluzione consiste nell'usare la stampa cloud.</span><span class="sxs-lookup"><span data-stu-id="6630e-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="6630e-157">Per ulteriori informazioni, vedere [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span><span class="sxs-lookup"><span data-stu-id="6630e-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="6630e-158">Proxy</span><span class="sxs-lookup"><span data-stu-id="6630e-158">Proxies</span></span>

<span data-ttu-id="6630e-159">Un **risultato di advisory** indica che è in uso un server proxy.</span><span class="sxs-lookup"><span data-stu-id="6630e-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="6630e-160">Per ulteriori informazioni, vedere [Configurazione di rete per Microsoft Managed Desktop.](network.md)</span><span class="sxs-lookup"><span data-stu-id="6630e-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

