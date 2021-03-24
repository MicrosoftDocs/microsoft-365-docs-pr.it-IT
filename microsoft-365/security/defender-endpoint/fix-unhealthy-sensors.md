---
title: Risolvere i sensori non integri in Microsoft Defender for Endpoint
description: Correggere i sensori del dispositivo che segnalano come non configurati correttamente o inattivi in modo che il servizio riceva i dati dal dispositivo.
keywords: non configurato correttamente, inattivo, correggere il sensore, l'integrità del sensore, nessun dato del sensore, dati del sensore, comunicazioni compromesse, comunicazione
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: a24dc4ef23d32b19de9d2871b7d87aae90d05828
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065698"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9413c-104">Risolvere i sensori non integri in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9413c-104">Fix unhealthy sensors in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9413c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9413c-105">**Applies to:**</span></span>
- [<span data-ttu-id="9413c-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="9413c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="9413c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9413c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="9413c-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="9413c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9413c-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="9413c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

<span data-ttu-id="9413c-110">I dispositivi classificati come non configurati correttamente o inattivi possono essere contrassegnati a causa di cause diverse.</span><span class="sxs-lookup"><span data-stu-id="9413c-110">Devices that are categorized as misconfigured or inactive can be flagged due to varying causes.</span></span> <span data-ttu-id="9413c-111">Questa sezione fornisce alcune spiegazioni su cosa potrebbe aver causato la categorizzazione di un dispositivo come inattivo o non configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9413c-111">This section provides some explanations as to what might have caused a device to be categorized as inactive or misconfigured.</span></span>

## <a name="inactive-devices"></a><span data-ttu-id="9413c-112">Dispositivi inattivi</span><span class="sxs-lookup"><span data-stu-id="9413c-112">Inactive devices</span></span>

<span data-ttu-id="9413c-113">Un dispositivo inattivo non è necessariamente contrassegnato a causa di un problema.</span><span class="sxs-lookup"><span data-stu-id="9413c-113">An inactive device is not necessarily flagged due to an issue.</span></span> <span data-ttu-id="9413c-114">Le azioni seguenti eseguite su un dispositivo possono causare la categorizzazione di un dispositivo come inattivo:</span><span class="sxs-lookup"><span data-stu-id="9413c-114">The following actions taken on a device can cause a device to be categorized as inactive:</span></span>

### <a name="device-is-not-in-use"></a><span data-ttu-id="9413c-115">Il dispositivo non è in uso</span><span class="sxs-lookup"><span data-stu-id="9413c-115">Device is not in use</span></span>

<span data-ttu-id="9413c-116">Se il dispositivo non è in uso da più di sette giorni per qualsiasi motivo, rimarrà nello stato "Inattivo" nel portale.</span><span class="sxs-lookup"><span data-stu-id="9413c-116">If the device has not been in use for more than seven days for any reason, it will remain in an ‘Inactive’ status in the portal.</span></span>

### <a name="device-was-reinstalled-or-renamed"></a><span data-ttu-id="9413c-117">Il dispositivo è stato reinstallato o rinominato</span><span class="sxs-lookup"><span data-stu-id="9413c-117">Device was reinstalled or renamed</span></span>
<span data-ttu-id="9413c-118">Un dispositivo reinstallato o rinominato genererà una nuova entità dispositivo in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="9413c-118">A reinstalled or renamed device will generate a new device entity in Microsoft Defender Security Center.</span></span> <span data-ttu-id="9413c-119">L'entità dispositivo precedente rimarrà con stato "Inattivo" nel portale.</span><span class="sxs-lookup"><span data-stu-id="9413c-119">The previous device entity will remain with an ‘Inactive’ status in the portal.</span></span> <span data-ttu-id="9413c-120">Se hai reinstallato un dispositivo e distribuito il pacchetto Defender for Endpoint, cerca il nuovo nome del dispositivo per verificare che il dispositivo segnala normalmente.</span><span class="sxs-lookup"><span data-stu-id="9413c-120">If you reinstalled a device and deployed the Defender for Endpoint package, search for the new device name to verify that the device is reporting normally.</span></span>

### <a name="device-was-offboarded"></a><span data-ttu-id="9413c-121">Il dispositivo è stato offboarded</span><span class="sxs-lookup"><span data-stu-id="9413c-121">Device was offboarded</span></span>
<span data-ttu-id="9413c-122">Se il dispositivo è stato offboarded, verrà comunque visualizzato nell'elenco dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9413c-122">If the device was offboarded, it will still appear in devices list.</span></span> <span data-ttu-id="9413c-123">Dopo sette giorni, lo stato di integrità del dispositivo deve essere inattivo.</span><span class="sxs-lookup"><span data-stu-id="9413c-123">After seven days, the device health state should change to inactive.</span></span>

### <a name="device-is-not-sending-signals"></a><span data-ttu-id="9413c-124">Il dispositivo non invia segnali</span><span class="sxs-lookup"><span data-stu-id="9413c-124">Device is not sending signals</span></span>
<span data-ttu-id="9413c-125">Se il dispositivo non invia alcun segnale per più di sette giorni a uno qualsiasi dei canali di Microsoft Defender for Endpoint per qualsiasi motivo, incluse le condizioni che rientrano nella classificazione dei dispositivi non configurati correttamente, un dispositivo può essere considerato inattivo.</span><span class="sxs-lookup"><span data-stu-id="9413c-125">If the device is not sending any signals for more than seven days to any of the Microsoft Defender for Endpoint channels for any reason including conditions that fall under misconfigured devices classification, a device can be considered inactive.</span></span> 

<span data-ttu-id="9413c-126">Si prevede che un dispositivo sia in stato "Attivo"?</span><span class="sxs-lookup"><span data-stu-id="9413c-126">Do you expect a device to be in ‘Active’ status?</span></span> <span data-ttu-id="9413c-127">[Aprire un ticket di supporto](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span><span class="sxs-lookup"><span data-stu-id="9413c-127">[Open a support ticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span></span>

## <a name="misconfigured-devices"></a><span data-ttu-id="9413c-128">Dispositivi non configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="9413c-128">Misconfigured devices</span></span>
<span data-ttu-id="9413c-129">I dispositivi non configurati correttamente possono essere ulteriormente classificati in:</span><span class="sxs-lookup"><span data-stu-id="9413c-129">Misconfigured devices can further be classified to:</span></span>
- <span data-ttu-id="9413c-130">Comunicazioni con problemi</span><span class="sxs-lookup"><span data-stu-id="9413c-130">Impaired communications</span></span>
- <span data-ttu-id="9413c-131">Nessun dato sensore</span><span class="sxs-lookup"><span data-stu-id="9413c-131">No sensor data</span></span>

### <a name="impaired-communications"></a><span data-ttu-id="9413c-132">Comunicazioni con problemi</span><span class="sxs-lookup"><span data-stu-id="9413c-132">Impaired communications</span></span>
<span data-ttu-id="9413c-133">Questo stato indica che la comunicazione tra il dispositivo e il servizio è limitata.</span><span class="sxs-lookup"><span data-stu-id="9413c-133">This status indicates that there's limited communication between the device and the service.</span></span>

<span data-ttu-id="9413c-134">Le azioni suggerite seguenti possono aiutare a risolvere i problemi relativi a un dispositivo non configurato correttamente con comunicazioni con problemi di comunicazione:</span><span class="sxs-lookup"><span data-stu-id="9413c-134">The following suggested actions can help fix issues related to a misconfigured device with impaired communications:</span></span>

- [<span data-ttu-id="9413c-135">Verificare che il dispositivo abbia una connessione Internet</span><span class="sxs-lookup"><span data-stu-id="9413c-135">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="9413c-136">Il sensore Window Defender ATP richiede Microsoft Windows HTTP (WinHTTP) per segnalare i dati del sensore e comunicare con il servizio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9413c-136">The Window Defender ATP sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="9413c-137">Verificare la connettività client a Microsoft Defender per gli URL del servizio endpoint</span><span class="sxs-lookup"><span data-stu-id="9413c-137">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)</br>
  <span data-ttu-id="9413c-138">Verificare che la configurazione del proxy sia stata completata correttamente, che WinHTTP sia in grado di individuare e comunicare tramite il server proxy nell'ambiente e che il server proxy consenta il traffico verso gli URL del servizio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9413c-138">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

<span data-ttu-id="9413c-139">Se hai intrapreso azioni correttive e lo stato del dispositivo non è ancora configurato correttamente, [apri un ticket di supporto.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="9413c-139">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

### <a name="no-sensor-data"></a><span data-ttu-id="9413c-140">Nessun dato sensore</span><span class="sxs-lookup"><span data-stu-id="9413c-140">No sensor data</span></span>
<span data-ttu-id="9413c-141">Un dispositivo non configurato correttamente con stato "Nessun dato sensore" è in grado di comunicare con il servizio, ma può segnalare solo dati parziali del sensore.</span><span class="sxs-lookup"><span data-stu-id="9413c-141">A misconfigured device with status ‘No sensor data’ has communication with the service but can only report partial sensor data.</span></span>
<span data-ttu-id="9413c-142">Seguire queste azioni per correggere i problemi noti relativi a un dispositivo non configurato correttamente con stato "Nessun dato sensore":</span><span class="sxs-lookup"><span data-stu-id="9413c-142">Follow theses actions to correct known issues related to a misconfigured device with status ‘No sensor data’:</span></span>

- [<span data-ttu-id="9413c-143">Verificare che il dispositivo abbia una connessione Internet</span><span class="sxs-lookup"><span data-stu-id="9413c-143">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="9413c-144">Il sensore Window Defender ATP richiede Microsoft Windows HTTP (WinHTTP) per segnalare i dati del sensore e comunicare con il servizio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9413c-144">The Window Defender ATP sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="9413c-145">Verificare la connettività client a Microsoft Defender per gli URL del servizio endpoint</span><span class="sxs-lookup"><span data-stu-id="9413c-145">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)</br>
  <span data-ttu-id="9413c-146">Verificare che la configurazione del proxy sia stata completata correttamente, che WinHTTP sia in grado di individuare e comunicare tramite il server proxy nell'ambiente e che il server proxy consenta il traffico verso gli URL del servizio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9413c-146">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

- [<span data-ttu-id="9413c-147">Verificare che il servizio dati di diagnostica sia abilitato</span><span class="sxs-lookup"><span data-stu-id="9413c-147">Ensure the diagnostic data service is enabled</span></span>](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
<span data-ttu-id="9413c-148">Se i dispositivi non segnalano correttamente, potrebbe essere necessario verificare che il servizio dati di diagnostica di Windows 10 sia impostato per l'avvio automatico e sia in esecuzione nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9413c-148">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the endpoint.</span></span>

- [<span data-ttu-id="9413c-149">Verificare che Microsoft Defender Antivirus non sia disabilitato dai criteri</span><span class="sxs-lookup"><span data-stu-id="9413c-149">Ensure that Microsoft Defender Antivirus is not disabled by policy</span></span>](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
<span data-ttu-id="9413c-150">Se i dispositivi eseguono un client antimalware di terze parti, l'agente Defender for Endpoint deve essere abilitato il driver Antimalware antimalware (Early Launch Antimalware) di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="9413c-150">If your devices are running a third-party antimalware client, the Defender for Endpoint agent needs the Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver to be enabled.</span></span>

<span data-ttu-id="9413c-151">Se hai intrapreso azioni correttive e lo stato del dispositivo non è ancora configurato correttamente, [apri un ticket di supporto.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="9413c-151">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

## <a name="see-also"></a><span data-ttu-id="9413c-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9413c-152">See also</span></span>
- [<span data-ttu-id="9413c-153">Controllare lo stato di integrità del sensore in Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="9413c-153">Check sensor health state in Microsoft Defender for Endpoint</span></span>](check-sensor-status.md)
