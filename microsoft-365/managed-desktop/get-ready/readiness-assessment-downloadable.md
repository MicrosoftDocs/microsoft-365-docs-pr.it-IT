---
title: Strumento di verifica della preparazione scaricabile
description: Controlla le impostazioni del dispositivo e della rete, inclusi gli endpoint necessari
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49922022"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="6817f-104">Strumento di verifica della preparazione scaricabile</span><span class="sxs-lookup"><span data-stu-id="6817f-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="6817f-105">Per funzionare correttamente con Microsoft Managed Desktop, i dispositivi devono soddisfare determinati requisiti hardware e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6817f-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="6817f-106">Inoltre, ogni dispositivo deve essere in grado di raggiungere gli endpoint chiave.</span><span class="sxs-lookup"><span data-stu-id="6817f-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="6817f-107">Scaricare ed eseguire questo strumento per ottenere un report HTML, visualizzare i risultati e quindi eseguire un'azione.</span><span class="sxs-lookup"><span data-stu-id="6817f-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="6817f-108">Dovrai scaricare lo strumento e i file di supporto e quindi eseguirlo manualmente in ogni dispositivo che vuoi registrare in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6817f-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="6817f-109">Per ogni controllo, lo strumento segnala uno dei tre possibili risultati:</span><span class="sxs-lookup"><span data-stu-id="6817f-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="6817f-110">Risultato</span><span class="sxs-lookup"><span data-stu-id="6817f-110">Result</span></span>  |<span data-ttu-id="6817f-111">Significato</span><span class="sxs-lookup"><span data-stu-id="6817f-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="6817f-112">Pronto</span><span class="sxs-lookup"><span data-stu-id="6817f-112">Ready</span></span>     | <span data-ttu-id="6817f-113">Non è necessaria alcuna azione prima di completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="6817f-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="6817f-114">Avviso</span><span class="sxs-lookup"><span data-stu-id="6817f-114">Advisory</span></span>    | <span data-ttu-id="6817f-115">Seguire i passaggi dello strumento per un'esperienza ottimale con la registrazione e per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6817f-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="6817f-116">È *possibile* completare la registrazione, ma è necessario risolvere questi problemi prima di distribuire il primo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6817f-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="6817f-117">Non pronto</span><span class="sxs-lookup"><span data-stu-id="6817f-117">Not ready</span></span> | <span data-ttu-id="6817f-118">*La registrazione avrà esito* negativo se questi problemi non vengono risolti.</span><span class="sxs-lookup"><span data-stu-id="6817f-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="6817f-119">Seguire i passaggi dello strumento per risolverli.</span><span class="sxs-lookup"><span data-stu-id="6817f-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="6817f-120">Ottenere lo verifica</span><span class="sxs-lookup"><span data-stu-id="6817f-120">Obtain the checker</span></span>

<span data-ttu-id="6817f-121">Scaricare il file ZIP da https://aka.ms/mmddratoolv0 .</span><span class="sxs-lookup"><span data-stu-id="6817f-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="6817f-122">L'utente che esegue lo strumento deve disporre dei diritti di amministratore locale nel dispositivo in cui lo esegue.</span><span class="sxs-lookup"><span data-stu-id="6817f-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="6817f-123">Eseguire quindi lo strumento seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="6817f-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="6817f-124">Copia il file ZIP scaricato in ogni dispositivo che vuoi controllare.</span><span class="sxs-lookup"><span data-stu-id="6817f-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="6817f-125">Estrarre tutti i file nel download compresso.</span><span class="sxs-lookup"><span data-stu-id="6817f-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="6817f-126">Eseguire **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span><span class="sxs-lookup"><span data-stu-id="6817f-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="6817f-127">Quando viene visualizzata la richiesta di controllo di accesso utente, selezionare **Sì.**</span><span class="sxs-lookup"><span data-stu-id="6817f-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="6817f-128">Lo strumento viene eseguito e apre un report nel browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="6817f-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="6817f-129">Puoi anche scaricare ed estrarre l'archivio ZIP  in un percorso condiviso, accedereMicrosoft.MMD.DeviceReadinessAssessmentTool.exeda ogni dispositivo e quindi eseguirlo localmente.</span><span class="sxs-lookup"><span data-stu-id="6817f-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="6817f-130">Controlli</span><span class="sxs-lookup"><span data-stu-id="6817f-130">Checks</span></span>

<span data-ttu-id="6817f-131">Lo strumento scaricabile controlla questi elementi correlati al dispositivo e alla rete:</span><span class="sxs-lookup"><span data-stu-id="6817f-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="6817f-132">Hardware</span><span class="sxs-lookup"><span data-stu-id="6817f-132">Hardware</span></span>

<span data-ttu-id="6817f-133">I dispositivi devono soddisfare requisiti hardware specifici per funzionare con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6817f-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="6817f-134">Attualmente, solo dispositivi [approvati specifici](../service-description/device-list.md) sono autorizzati a registrarsi.</span><span class="sxs-lookup"><span data-stu-id="6817f-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="6817f-135">Se il dispositivo non supera uno dei controlli, non è compatibile con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6817f-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="6817f-136">Endpoint di rete</span><span class="sxs-lookup"><span data-stu-id="6817f-136">Network endpoints</span></span>

<span data-ttu-id="6817f-137">I dispositivi sono in grado di raggiungere diversi [endpoint chiave](network.md) per funzionare con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6817f-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="6817f-138">Se lo strumento segnala **un risultato** Non pronto, vedi il report dettagliato per scoprire quali endpoint non erano raggiungibili.</span><span class="sxs-lookup"><span data-stu-id="6817f-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="6817f-139">Regola quindi il firewall o altre impostazioni di rete per assicurarti che tali endpoint possano essere raggiunti.</span><span class="sxs-lookup"><span data-stu-id="6817f-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="6817f-140">Altre impostazioni</span><span class="sxs-lookup"><span data-stu-id="6817f-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="6817f-141">Profili Wi-Fi aziendali</span><span class="sxs-lookup"><span data-stu-id="6817f-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="6817f-142">Un **risultato di avviso** indica che stai usando alcuni profili Wi-Fi che necessitano di certificati e profili per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="6817f-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="6817f-143">Per altre informazioni, vedi [Distribuire certificati e profilo Wi-Fi/VPN.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)</span><span class="sxs-lookup"><span data-stu-id="6817f-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="6817f-144">Profili LAN</span><span class="sxs-lookup"><span data-stu-id="6817f-144">LAN profiles</span></span>

<span data-ttu-id="6817f-145">Un **risultato di avviso** indica che sono disponibili LAN che necessitano di certificati e profili per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="6817f-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="6817f-146">Per ulteriori informazioni, vedere [Preparare certificati e profili di rete per Microsoft Managed Desktop.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="6817f-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="6817f-147">Profili VPN</span><span class="sxs-lookup"><span data-stu-id="6817f-147">VPN profiles</span></span>

<span data-ttu-id="6817f-148">Un **risultato di** avviso indica che stai usando una rete privata virtuale (VPN).</span><span class="sxs-lookup"><span data-stu-id="6817f-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="6817f-149">Creare un profilo VPN che distribuisca i certificati integrati con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="6817f-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="6817f-150">Per ulteriori informazioni, vedere [Preparare certificati e profili di rete per Microsoft Managed Desktop.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="6817f-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="6817f-151">Unità mappate</span><span class="sxs-lookup"><span data-stu-id="6817f-151">Mapped drives</span></span>

<span data-ttu-id="6817f-152">Un **risultato di avviso** indica che alcune unità mappate non sono consigliate.</span><span class="sxs-lookup"><span data-stu-id="6817f-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="6817f-153">Per ulteriori informazioni, vedere [Preparare le unità mappate per Microsoft Managed Desktop.](mapped-drives.md)</span><span class="sxs-lookup"><span data-stu-id="6817f-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="6817f-154">Code di stampa</span><span class="sxs-lookup"><span data-stu-id="6817f-154">Print queues</span></span>

<span data-ttu-id="6817f-155">Un **risultato di avviso** indica che si dispone di alcune code di stampa in sospeso, che non sono consigliate.</span><span class="sxs-lookup"><span data-stu-id="6817f-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="6817f-156">Una soluzione consiste nell'usare la stampa cloud.</span><span class="sxs-lookup"><span data-stu-id="6817f-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="6817f-157">Per ulteriori informazioni, vedere [Preparare le risorse di stampa per Microsoft Managed Desktop.](printing.md)</span><span class="sxs-lookup"><span data-stu-id="6817f-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="6817f-158">Proxy</span><span class="sxs-lookup"><span data-stu-id="6817f-158">Proxies</span></span>

<span data-ttu-id="6817f-159">Un **risultato di avviso** indica che è in uso un server proxy.</span><span class="sxs-lookup"><span data-stu-id="6817f-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="6817f-160">Per ulteriori informazioni, vedere [Configurazione di rete per Microsoft Managed Desktop.](network.md)</span><span class="sxs-lookup"><span data-stu-id="6817f-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

