---
title: Esaminare eventi ed errori tramite il Visualizzatore eventi
description: Ottenere descrizioni e ulteriori passaggi per la risoluzione dei problemi (se necessario) per tutti gli eventi segnalati dal servizio Microsoft Defender for Endpoint.
keywords: risoluzione dei problemi, visualizzatore eventi, riepilogo del registro, codice di errore, non riuscito, Servizio Microsoft Defender per endpoint, non può essere avviato, interrotto, non può essere avviato
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
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 1b8454107b6a2737f1236a066c3a24a2b9c776cb
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222655"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="d5182-104">Esaminare eventi ed errori tramite il Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="d5182-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d5182-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d5182-105">**Applies to:**</span></span>
- <span data-ttu-id="d5182-106">Visualizzatore eventi</span><span class="sxs-lookup"><span data-stu-id="d5182-106">Event Viewer</span></span>
- [<span data-ttu-id="d5182-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d5182-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d5182-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5182-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d5182-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d5182-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d5182-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d5182-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="d5182-111">Puoi esaminare gli ID evento nel [Visualizzatore eventi](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) nei singoli dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d5182-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="d5182-112">Ad esempio, se i dispositivi non vengono visualizzati nell'elenco **Dispositivi,** potrebbe essere necessario cercare gli ID evento nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d5182-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="d5182-113">È quindi possibile utilizzare questa tabella per determinare ulteriori passaggi per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="d5182-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="d5182-114">**Aprire il Visualizzatore eventi e trovare il registro eventi del servizio Microsoft Defender for Endpoint:**</span><span class="sxs-lookup"><span data-stu-id="d5182-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="d5182-115">Scegliere **Start** dal menu Windows, digitare **Visualizzatore eventi** e premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="d5182-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="d5182-116">Nell'elenco dei registri, in **Log Summary**, scorrere fino a visualizzare **Microsoft-Windows-SENSE/Operational**.</span><span class="sxs-lookup"><span data-stu-id="d5182-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="d5182-117">Fare doppio clic sull'elemento per aprire il registro.</span><span class="sxs-lookup"><span data-stu-id="d5182-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="d5182-118">a.</span><span class="sxs-lookup"><span data-stu-id="d5182-118">a.</span></span>  <span data-ttu-id="d5182-119">Puoi anche accedere al registro espandendo Registri **applicazioni** e servizi  >  **Microsoft**  >  **Windows**  >  **SENSE** e fai clic su **Operativo.**</span><span class="sxs-lookup"><span data-stu-id="d5182-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d5182-120">SENSE è il nome interno usato per fare riferimento al sensore comportamentale che alimenta Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d5182-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="d5182-121">Gli eventi registrati dal servizio verranno visualizzati nel registro.</span><span class="sxs-lookup"><span data-stu-id="d5182-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="d5182-122">Per un elenco degli eventi registrati dal servizio, vedere la tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d5182-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="d5182-123">ID evento</span><span class="sxs-lookup"><span data-stu-id="d5182-123">Event ID</span></span></th>
<th><span data-ttu-id="d5182-124">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d5182-124">Message</span></span></th>
<th><span data-ttu-id="d5182-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5182-125">Description</span></span></th>
<th><span data-ttu-id="d5182-126">Azione</span><span class="sxs-lookup"><span data-stu-id="d5182-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="d5182-127">1</span><span class="sxs-lookup"><span data-stu-id="d5182-127">1</span></span></td>
<td><span data-ttu-id="d5182-128">Servizio Microsoft Defender for Endpoint avviato (versione <code>variable</code> ).</span><span class="sxs-lookup"><span data-stu-id="d5182-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="d5182-129">Si verifica durante l'avvio, l'arresto e l'onboarding del sistema.</span><span class="sxs-lookup"><span data-stu-id="d5182-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="d5182-130">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-131">2 </span><span class="sxs-lookup"><span data-stu-id="d5182-131">2</span></span></td>
<td><span data-ttu-id="d5182-132">Arresto del servizio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d5182-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="d5182-133">Si verifica quando il dispositivo viene arrestato o offboarded.</span><span class="sxs-lookup"><span data-stu-id="d5182-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="d5182-134">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-135">3 </span><span class="sxs-lookup"><span data-stu-id="d5182-135">3</span></span></td>
<td><span data-ttu-id="d5182-136">Avvio del servizio Microsoft Defender for Endpoint non riuscito.</span><span class="sxs-lookup"><span data-stu-id="d5182-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="d5182-137">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-138">Il servizio non è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="d5182-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="d5182-139">Esaminare altri messaggi per determinare le possibili cause e i passaggi per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="d5182-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-140">4 </span><span class="sxs-lookup"><span data-stu-id="d5182-140">4</span></span></td>
<td><span data-ttu-id="d5182-141">Microsoft Defender for Endpoint service ha contattato il server all'indirizzo <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-142">Variabile = URL del Defender per i server di elaborazione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="d5182-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="d5182-143">Questo URL corrisponde a quello visualizzato nel firewall o nell'attività di rete.</span><span class="sxs-lookup"><span data-stu-id="d5182-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="d5182-144">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-145">5 </span><span class="sxs-lookup"><span data-stu-id="d5182-145">5</span></span></td>
<td><span data-ttu-id="d5182-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-147">Variabile = URL del Defender per i server di elaborazione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="d5182-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="d5182-148">Il servizio non è riuscito a contattare i server di elaborazione esterni in tale URL.</span><span class="sxs-lookup"><span data-stu-id="d5182-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="d5182-149">Verificare la connessione all'URL.</span><span class="sxs-lookup"><span data-stu-id="d5182-149">Check the connection to the URL.</span></span> <span data-ttu-id="d5182-150">Vedere <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="d5182-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-151">6 </span><span class="sxs-lookup"><span data-stu-id="d5182-151">6</span></span></td>
<td><span data-ttu-id="d5182-152">Il servizio Microsoft Defender for Endpoint non è stato onboarding e non sono stati trovati parametri di onboarding.</span><span class="sxs-lookup"><span data-stu-id="d5182-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="d5182-153">Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale.</span><span class="sxs-lookup"><span data-stu-id="d5182-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="d5182-154">L'onboarding deve essere eseguito prima di avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="d5182-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="d5182-155">Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="d5182-156">Prova a ridistribuire i pacchetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="d5182-157">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-158">7 </span><span class="sxs-lookup"><span data-stu-id="d5182-158">7</span></span></td>
<td><span data-ttu-id="d5182-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span><span class="sxs-lookup"><span data-stu-id="d5182-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="d5182-160">Errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-161">Variabile = descrizione dettagliata dell'errore.</span><span class="sxs-lookup"><span data-stu-id="d5182-161">Variable = detailed error description.</span></span> <span data-ttu-id="d5182-162">Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale.</span><span class="sxs-lookup"><span data-stu-id="d5182-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="d5182-163">Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="d5182-164">Prova a ridistribuire i pacchetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="d5182-165">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-166">8 </span><span class="sxs-lookup"><span data-stu-id="d5182-166">8</span></span></td>
<td><span data-ttu-id="d5182-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span><span class="sxs-lookup"><span data-stu-id="d5182-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="d5182-168">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-169"><b>Durante l'onboarding:</b> Il servizio non è riuscito a pulire la configurazione durante l'onboarding.</span><span class="sxs-lookup"><span data-stu-id="d5182-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="d5182-170">Il processo di onboarding continua.</span><span class="sxs-lookup"><span data-stu-id="d5182-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="d5182-171"><b>Durante l'offboarding:</b> Il servizio non è riuscito a pulire la configurazione durante l'offboarding.</span><span class="sxs-lookup"><span data-stu-id="d5182-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="d5182-172">Il processo di offboarding è terminato ma il servizio continua a essere in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d5182-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="d5182-173"><b>Onboarding:</b> Non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="d5182-174"><b>Offboarding:</b> Riavviare il sistema.</span><span class="sxs-lookup"><span data-stu-id="d5182-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="d5182-175">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-176">9 </span><span class="sxs-lookup"><span data-stu-id="d5182-176">9</span></span></td>
<td><span data-ttu-id="d5182-177">Microsoft Defender for Endpoint service failed to change its start type.</span><span class="sxs-lookup"><span data-stu-id="d5182-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="d5182-178">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-179"><b>Durante l'onboarding:</b> Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale.</span><span class="sxs-lookup"><span data-stu-id="d5182-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="d5182-180"><b>Durante l'offboarding:</b> Impossibile modificare il tipo di avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="d5182-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="d5182-181">Il processo di offboarding continua.</span><span class="sxs-lookup"><span data-stu-id="d5182-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="d5182-182">Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="d5182-183">Prova a ridistribuire i pacchetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="d5182-184">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-185">10  </span><span class="sxs-lookup"><span data-stu-id="d5182-185">10</span></span></td>
<td><span data-ttu-id="d5182-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span><span class="sxs-lookup"><span data-stu-id="d5182-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="d5182-187">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-188">Il dispositivo non è stato eseguito correttamente e non verrà segnalato al portale.</span><span class="sxs-lookup"><span data-stu-id="d5182-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="d5182-189">Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="d5182-190">Prova a ridistribuire i pacchetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="d5182-191">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-192">11 </span><span class="sxs-lookup"><span data-stu-id="d5182-192">11</span></span></td>
<td><span data-ttu-id="d5182-193">Onboarding o ri-onboarding di Defender per il servizio endpoint completato.</span><span class="sxs-lookup"><span data-stu-id="d5182-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="d5182-194">Il dispositivo è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="d5182-195">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="d5182-196">La visualizzazione del dispositivo nel portale potrebbe richiedere diverse ore.</span><span class="sxs-lookup"><span data-stu-id="d5182-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-197">12 </span><span class="sxs-lookup"><span data-stu-id="d5182-197">12</span></span></td>
<td><span data-ttu-id="d5182-198">Microsoft Defender for Endpoint non è riuscito ad applicare la configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d5182-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="d5182-199">Il servizio non è stato in grado di applicare la configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d5182-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="d5182-200">Questo errore dovrebbe risolversi dopo un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d5182-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-201">13</span><span class="sxs-lookup"><span data-stu-id="d5182-201">13</span></span></td>
<td><span data-ttu-id="d5182-202">Microsoft Defender per l'ID dispositivo endpoint calcolato: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-203">Normale processo operativo.</span><span class="sxs-lookup"><span data-stu-id="d5182-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="d5182-204">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-205">15 </span><span class="sxs-lookup"><span data-stu-id="d5182-205">15</span></span></td>
<td><span data-ttu-id="d5182-206">Microsoft Defender for Endpoint non può avviare il canale di comando con URL: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-207">Variabile = URL del Defender per i server di elaborazione degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="d5182-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="d5182-208">Il servizio non è riuscito a contattare i server di elaborazione esterni in tale URL.</span><span class="sxs-lookup"><span data-stu-id="d5182-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="d5182-209">Verificare la connessione all'URL.</span><span class="sxs-lookup"><span data-stu-id="d5182-209">Check the connection to the URL.</span></span> <span data-ttu-id="d5182-210">Vedere <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="d5182-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-211">17 </span><span class="sxs-lookup"><span data-stu-id="d5182-211">17</span></span></td>
<td><span data-ttu-id="d5182-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span><span class="sxs-lookup"><span data-stu-id="d5182-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="d5182-213">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-214">Si è verificato un errore con il servizio di telemetria di Windows.</span><span class="sxs-lookup"><span data-stu-id="d5182-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="d5182-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verificare che il servizio dati di diagnostica sia abilitato.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="d5182-216">Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="d5182-217">Prova a ridistribuire i pacchetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="d5182-218">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-219">18 </span><span class="sxs-lookup"><span data-stu-id="d5182-219">18</span></span></td>
<td><span data-ttu-id="d5182-220">Configurazione guidata (Windows Welcome) completata.</span><span class="sxs-lookup"><span data-stu-id="d5182-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="d5182-221">Il servizio verrà avviato solo al termine dell'installazione degli aggiornamenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="d5182-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="d5182-222">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-223">19</span><span class="sxs-lookup"><span data-stu-id="d5182-223">19</span></span></td>
<td><span data-ttu-id="d5182-224">Configurazione guidata (Windows Welcome) non è ancora stata completata.</span><span class="sxs-lookup"><span data-stu-id="d5182-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="d5182-225">Il servizio verrà avviato solo al termine dell'installazione degli aggiornamenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="d5182-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="d5182-226">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="d5182-227">Se l'errore persiste dopo un riavvio del sistema, assicurati che tutti gli aggiornamenti di Windows siano installati completamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-228">20</span><span class="sxs-lookup"><span data-stu-id="d5182-228">20</span></span></td>
<td><span data-ttu-id="d5182-229">Impossibile attendere il completamento della Configurazione guidata (Installazione di Windows).</span><span class="sxs-lookup"><span data-stu-id="d5182-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="d5182-230">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-231">Errore interno.</span><span class="sxs-lookup"><span data-stu-id="d5182-231">Internal error.</span></span></td>
<td><span data-ttu-id="d5182-232">Se l'errore persiste dopo un riavvio del sistema, assicurati che tutti gli aggiornamenti di Windows siano installati completamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-233">25</span><span class="sxs-lookup"><span data-stu-id="d5182-233">25</span></span></td>
<td><span data-ttu-id="d5182-234">Il servizio Microsoft Defender for Endpoint non è riuscito a reimpostare lo stato di integrità nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="d5182-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="d5182-235">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-236">Il dispositivo non è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="d5182-237">Verrà segnalata al portale, tuttavia il servizio potrebbe non essere visualizzato come registrato in SCCM o nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="d5182-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="d5182-238">Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="d5182-239">Prova a ridistribuire i pacchetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="d5182-240">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-241">26</span><span class="sxs-lookup"><span data-stu-id="d5182-241">26</span></span></td>
<td><span data-ttu-id="d5182-242">Microsoft Defender for Endpoint service non è riuscito a impostare lo stato di onboarding nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="d5182-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="d5182-243">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-244">Il dispositivo non è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="d5182-245">Verrà segnalata al portale, tuttavia il servizio potrebbe non essere visualizzato come registrato in SCCM o nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="d5182-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="d5182-246">Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="d5182-247">Prova a ridistribuire i pacchetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="d5182-248">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-249">27</span><span class="sxs-lookup"><span data-stu-id="d5182-249">27</span></span></td>
<td><span data-ttu-id="d5182-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="d5182-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="d5182-251">Processo di onboarding non riuscito.</span><span class="sxs-lookup"><span data-stu-id="d5182-251">Onboarding process failed.</span></span> <span data-ttu-id="d5182-252">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-253">In genere, Microsoft Defender Antivirus entra in uno stato passivo speciale se un altro prodotto antimalware in tempo reale viene eseguito correttamente nel dispositivo e il dispositivo segnala a Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d5182-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="d5182-254">Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="d5182-255">Prova a ridistribuire i pacchetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="d5182-256">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="d5182-257">Verificare che la protezione antimalware in tempo reale venga eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-258">28</span><span class="sxs-lookup"><span data-stu-id="d5182-258">28</span></span></td>
<td><span data-ttu-id="d5182-259">Registrazione del servizio Esperienze utente connesse all'endpoint e telemetria di Microsoft Defender per endpoint non riuscita.</span><span class="sxs-lookup"><span data-stu-id="d5182-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="d5182-260">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-261">Si è verificato un errore con il servizio di telemetria di Windows.</span><span class="sxs-lookup"><span data-stu-id="d5182-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="d5182-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verificare che il servizio dati di diagnostica sia abilitato.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="d5182-263">Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="d5182-264">Prova a ridistribuire i pacchetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="d5182-265">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-266">29</span><span class="sxs-lookup"><span data-stu-id="d5182-266">29</span></span></td>
<td><span data-ttu-id="d5182-267">Impossibile leggere i parametri di offboarding.</span><span class="sxs-lookup"><span data-stu-id="d5182-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="d5182-268">Tipo di errore: %1, Codice errore: %2, Descrizione: %3</span><span class="sxs-lookup"><span data-stu-id="d5182-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="d5182-269">Questo evento si verifica quando il sistema non&#39;i parametri di offboarding.</span><span class="sxs-lookup"><span data-stu-id="d5182-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="d5182-270">Assicurati che il dispositivo abbia accesso a Internet, quindi esegui di nuovo l'intero processo di offboarding.</span><span class="sxs-lookup"><span data-stu-id="d5182-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="d5182-271">Assicurati che il pacchetto di offboarding non sia scaduto.</span><span class="sxs-lookup"><span data-stu-id="d5182-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-272">30</span><span class="sxs-lookup"><span data-stu-id="d5182-272">30</span></span></td>
<td><span data-ttu-id="d5182-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="d5182-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="d5182-274">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-275">In genere, Microsoft Defender Antivirus entra in uno stato passivo speciale se un altro prodotto antimalware in tempo reale viene eseguito correttamente nel dispositivo e il dispositivo segnala a Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d5182-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="d5182-276">Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="d5182-277">Prova a ridistribuire i pacchetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="d5182-278">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10</a></span><span class="sxs-lookup"><span data-stu-id="d5182-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="d5182-279">Verificare che la protezione antimalware in tempo reale venga eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-280">31</span><span class="sxs-lookup"><span data-stu-id="d5182-280">31</span></span></td>
<td><span data-ttu-id="d5182-281">Annullamento della registrazione di Esperienze utente connesse e telemetria di Microsoft Defender per endpoint non riuscito.</span><span class="sxs-lookup"><span data-stu-id="d5182-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="d5182-282">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-283">Si è verificato un errore con il servizio di telemetria di Windows durante l'onboarding.</span><span class="sxs-lookup"><span data-stu-id="d5182-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="d5182-284">Il processo di offboarding continua.</span><span class="sxs-lookup"><span data-stu-id="d5182-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="d5182-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Verificare la presenza di errori con il servizio di telemetria di Windows.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-286">32</span><span class="sxs-lookup"><span data-stu-id="d5182-286">32</span></span></td>
<td><span data-ttu-id="d5182-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span><span class="sxs-lookup"><span data-stu-id="d5182-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="d5182-288">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="d5182-289">Si è verificato un errore durante l'offboarding.</span><span class="sxs-lookup"><span data-stu-id="d5182-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="d5182-290">Riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5182-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-291">33</span><span class="sxs-lookup"><span data-stu-id="d5182-291">33</span></span></td>
<td><span data-ttu-id="d5182-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span><span class="sxs-lookup"><span data-stu-id="d5182-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="d5182-293">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-294">Un identificatore univoco viene usato per rappresentare ogni dispositivo che segnala al portale.</span><span class="sxs-lookup"><span data-stu-id="d5182-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="d5182-295">Se l'identificatore non viene salvato in modo permanente, lo stesso dispositivo potrebbe comparire due volte nel portale.</span><span class="sxs-lookup"><span data-stu-id="d5182-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="d5182-296">Controlla le autorizzazioni del Registro di sistema nel dispositivo per assicurarti che il servizio possa aggiornare il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="d5182-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-297">34</span><span class="sxs-lookup"><span data-stu-id="d5182-297">34</span></span></td>
<td><span data-ttu-id="d5182-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span><span class="sxs-lookup"><span data-stu-id="d5182-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="d5182-299">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-300">Si è verificato un errore con il servizio di telemetria di Windows.</span><span class="sxs-lookup"><span data-stu-id="d5182-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="d5182-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verificare che il servizio dati di diagnostica sia abilitato.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="d5182-302">Verificare che le impostazioni e gli script di onboarding siano stati distribuiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="d5182-303">Prova a ridistribuire i pacchetti di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="d5182-304">Vedi <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard di dispositivi Windows 10.</a></span><span class="sxs-lookup"><span data-stu-id="d5182-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-305">35</span><span class="sxs-lookup"><span data-stu-id="d5182-305">35</span></span></td>
<td><span data-ttu-id="d5182-306">Il servizio Microsoft Defender for Endpoint non è riuscito a rimuovere se stesso come dipendenza dal servizio Esperienze utente connesse e telemetria.</span><span class="sxs-lookup"><span data-stu-id="d5182-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="d5182-307">Codice di errore: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-308">Si è verificato un errore con il servizio di telemetria di Windows durante l'offboarding.</span><span class="sxs-lookup"><span data-stu-id="d5182-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="d5182-309">Il processo di offboarding continua.</span><span class="sxs-lookup"><span data-stu-id="d5182-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="d5182-310">Verificare la presenza di errori con il servizio dati di diagnostica Windows.</span><span class="sxs-lookup"><span data-stu-id="d5182-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-311">36</span><span class="sxs-lookup"><span data-stu-id="d5182-311">36</span></span></td>
<td><span data-ttu-id="d5182-312">Registrazione delle esperienze utente connesse all'endpoint e del servizio di telemetria di Microsoft Defender per endpoint completata.</span><span class="sxs-lookup"><span data-stu-id="d5182-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="d5182-313">Codice di completamento: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="d5182-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="d5182-314">Registrazione di Defender per Endpoint con il servizio Esperienze utente connesse e telemetria completata.</span><span class="sxs-lookup"><span data-stu-id="d5182-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="d5182-315">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-316">37</span><span class="sxs-lookup"><span data-stu-id="d5182-316">37</span></span></td>
<td><span data-ttu-id="d5182-317">Microsoft Defender for Endpoint Un modulo sta per superare la quota.</span><span class="sxs-lookup"><span data-stu-id="d5182-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="d5182-318">Modulo: %1, Quota: {%2} {%3}, Percentuale di utilizzo della quota: %4.</span><span class="sxs-lookup"><span data-stu-id="d5182-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="d5182-319">Il dispositivo ha quasi usato la quota allocata della finestra corrente di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="d5182-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="d5182-320">Sta per essere limitato.</span><span class="sxs-lookup"><span data-stu-id="d5182-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="d5182-321">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-322">38</span><span class="sxs-lookup"><span data-stu-id="d5182-322">38</span></span></td>
<td><span data-ttu-id="d5182-323">La connessione di rete viene identificata come bassa.</span><span class="sxs-lookup"><span data-stu-id="d5182-323">Network connection is identified as low.</span></span> <span data-ttu-id="d5182-324">Microsoft Defender for Endpoint contatta il server ogni %1 minuti.</span><span class="sxs-lookup"><span data-stu-id="d5182-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="d5182-325">Connessione a consumo: %2, Internet disponibile: %3, rete gratuita disponibile: %4.</span><span class="sxs-lookup"><span data-stu-id="d5182-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="d5182-326">Il dispositivo utilizza una rete a consumo/a pagamento e contatta il server con minore frequenza.</span><span class="sxs-lookup"><span data-stu-id="d5182-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="d5182-327">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-328">39</span><span class="sxs-lookup"><span data-stu-id="d5182-328">39</span></span></td>
<td><span data-ttu-id="d5182-329">La connessione di rete viene identificata normalmente.</span><span class="sxs-lookup"><span data-stu-id="d5182-329">Network connection is identified as normal.</span></span> <span data-ttu-id="d5182-330">Microsoft Defender for Endpoint contatta il server ogni %1 minuti.</span><span class="sxs-lookup"><span data-stu-id="d5182-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="d5182-331">Connessione a consumo: %2, Internet disponibile: %3, rete gratuita disponibile: %4.</span><span class="sxs-lookup"><span data-stu-id="d5182-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="d5182-332">Il dispositivo non utilizza una connessione a consumo/a pagamento e contatta il server come al solito.</span><span class="sxs-lookup"><span data-stu-id="d5182-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="d5182-333">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-334">40</span><span class="sxs-lookup"><span data-stu-id="d5182-334">40</span></span></td>
<td><span data-ttu-id="d5182-335">Lo stato della batteria è identificato come basso.</span><span class="sxs-lookup"><span data-stu-id="d5182-335">Battery state is identified as low.</span></span> <span data-ttu-id="d5182-336">Microsoft Defender for Endpoint contatta il server ogni %1 minuti.</span><span class="sxs-lookup"><span data-stu-id="d5182-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="d5182-337">Stato batteria: %2.</span><span class="sxs-lookup"><span data-stu-id="d5182-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="d5182-338">Il dispositivo ha un livello di batteria basso e contatta il server con minore frequenza.</span><span class="sxs-lookup"><span data-stu-id="d5182-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="d5182-339">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-340">41</span><span class="sxs-lookup"><span data-stu-id="d5182-340">41</span></span></td>
<td><span data-ttu-id="d5182-341">Lo stato della batteria viene identificato come normale.</span><span class="sxs-lookup"><span data-stu-id="d5182-341">Battery state is identified as normal.</span></span> <span data-ttu-id="d5182-342">Microsoft Defender for Endpoint contatta il server ogni %1 minuti.</span><span class="sxs-lookup"><span data-stu-id="d5182-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="d5182-343">Stato batteria: %2.</span><span class="sxs-lookup"><span data-stu-id="d5182-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="d5182-344">Il dispositivo non ha un livello di batteria basso e contatta il server come al solito.</span><span class="sxs-lookup"><span data-stu-id="d5182-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="d5182-345">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-346">42</span><span class="sxs-lookup"><span data-stu-id="d5182-346">42</span></span></td>
<td><span data-ttu-id="d5182-347">Il componente WDATP di Microsoft Defender for Endpoint non è riuscito a eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-347">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="d5182-348">Componente: %1, Azione: %2, Tipo eccezione: %3, Messaggio eccezione: %4</span><span class="sxs-lookup"><span data-stu-id="d5182-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="d5182-349">Errore interno.</span><span class="sxs-lookup"><span data-stu-id="d5182-349">Internal error.</span></span> <span data-ttu-id="d5182-350">Avvio del servizio non riuscito.</span><span class="sxs-lookup"><span data-stu-id="d5182-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="d5182-351">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-352">43</span><span class="sxs-lookup"><span data-stu-id="d5182-352">43</span></span></td>
<td><span data-ttu-id="d5182-353">Il componente WDATP di Microsoft Defender for Endpoint non è riuscito a eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-353">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="d5182-354">Componente: %1, Azione: %2, Tipo eccezione: %3, Errore eccezione: %4, Messaggio eccezione: %5</span><span class="sxs-lookup"><span data-stu-id="d5182-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="d5182-355">Errore interno.</span><span class="sxs-lookup"><span data-stu-id="d5182-355">Internal error.</span></span> <span data-ttu-id="d5182-356">Avvio del servizio non riuscito.</span><span class="sxs-lookup"><span data-stu-id="d5182-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="d5182-357">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-358">44</span><span class="sxs-lookup"><span data-stu-id="d5182-358">44</span></span></td>
<td><span data-ttu-id="d5182-359">Offboarding di Defender per il servizio endpoint completato.</span><span class="sxs-lookup"><span data-stu-id="d5182-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="d5182-360">Il servizio è stato offboarded.</span><span class="sxs-lookup"><span data-stu-id="d5182-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="d5182-361">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-362">45</span><span class="sxs-lookup"><span data-stu-id="d5182-362">45</span></span></td>
<td><span data-ttu-id="d5182-363">Impossibile eseguire la registrazione e avviare la sessione di traccia eventi [%1].</span><span class="sxs-lookup"><span data-stu-id="d5182-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="d5182-364">Codice errore: %2</span><span class="sxs-lookup"><span data-stu-id="d5182-364">Error code: %2</span></span></td>
<td><span data-ttu-id="d5182-365">Errore durante l'avvio del servizio durante la creazione della sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="d5182-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="d5182-366">Ciò ha causato un errore di avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="d5182-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="d5182-367">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-368">46</span><span class="sxs-lookup"><span data-stu-id="d5182-368">46</span></span></td>
<td><span data-ttu-id="d5182-369">Impossibile registrare e avviare la sessione di traccia eventi [%1] a causa della mancanza di risorse.</span><span class="sxs-lookup"><span data-stu-id="d5182-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="d5182-370">Codice errore: %2.</span><span class="sxs-lookup"><span data-stu-id="d5182-370">Error code: %2.</span></span> <span data-ttu-id="d5182-371">Ciò è molto probabile perché sono presenti troppe sessioni di traccia eventi attive.</span><span class="sxs-lookup"><span data-stu-id="d5182-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="d5182-372">Il servizio verrà ritentato tra 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="d5182-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="d5182-373">Si è verificato un errore durante l'avvio del servizio durante la creazione della sessione ETW a causa della mancanza di risorse.</span><span class="sxs-lookup"><span data-stu-id="d5182-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="d5182-374">Il servizio è stato avviato ed è in esecuzione, ma non segnala alcun evento sensore fino all'avvio della sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="d5182-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="d5182-375">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="d5182-376">Il servizio tenterà di avviare la sessione ogni minuto.</span><span class="sxs-lookup"><span data-stu-id="d5182-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-377">47</span><span class="sxs-lookup"><span data-stu-id="d5182-377">47</span></span></td>
<td><span data-ttu-id="d5182-378">La sessione di traccia eventi è stata registrata e avviata correttamente, recuperata dopo i precedenti tentativi non riusciti.</span><span class="sxs-lookup"><span data-stu-id="d5182-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="d5182-379">Questo evento segue l'evento precedente dopo l'avvio corretto della sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="d5182-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="d5182-380">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d5182-381">48</span><span class="sxs-lookup"><span data-stu-id="d5182-381">48</span></span></td>
<td><span data-ttu-id="d5182-382">Impossibile aggiungere un provider [%1] alla sessione di traccia eventi [%2].</span><span class="sxs-lookup"><span data-stu-id="d5182-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="d5182-383">Codice di errore: %3.</span><span class="sxs-lookup"><span data-stu-id="d5182-383">Error code: %3.</span></span> <span data-ttu-id="d5182-384">Ciò significa che gli eventi di questo provider non verranno segnalati.</span><span class="sxs-lookup"><span data-stu-id="d5182-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="d5182-385">Impossibile aggiungere un provider alla sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="d5182-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="d5182-386">Di conseguenza, gli eventi del provider non vengono segnalati.</span><span class="sxs-lookup"><span data-stu-id="d5182-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="d5182-387">Controllare il codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d5182-387">Check the error code.</span></span> <span data-ttu-id="d5182-388">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="d5182-389">49</span><span class="sxs-lookup"><span data-stu-id="d5182-389">49</span></span></td>
   <td><span data-ttu-id="d5182-390">Comando di configurazione cloud non valido ricevuto e ignorato.</span><span class="sxs-lookup"><span data-stu-id="d5182-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="d5182-391">Versione: %1, stato: %2, codice errore: %3, messaggio: %4</span><span class="sxs-lookup"><span data-stu-id="d5182-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="d5182-392">Ricevuto un file di configurazione non valido dal servizio cloud ignorato.</span><span class="sxs-lookup"><span data-stu-id="d5182-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="d5182-393">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-394">50</span><span class="sxs-lookup"><span data-stu-id="d5182-394">50</span></span></td>
   <td><span data-ttu-id="d5182-395">Nuova configurazione cloud applicata correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="d5182-396">Versione: %1.</span><span class="sxs-lookup"><span data-stu-id="d5182-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="d5182-397">È stata applicata correttamente una nuova configurazione dal servizio cloud.</span><span class="sxs-lookup"><span data-stu-id="d5182-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="d5182-398">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-399">51</span><span class="sxs-lookup"><span data-stu-id="d5182-399">51</span></span></td>
   <td><span data-ttu-id="d5182-400">Impossibile applicare la nuova configurazione cloud, versione: %1.</span><span class="sxs-lookup"><span data-stu-id="d5182-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="d5182-401">Applicazione dell'ultima configurazione valida nota, versione %2.</span><span class="sxs-lookup"><span data-stu-id="d5182-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="d5182-402">Ricevuto un file di configurazione non valido dal servizio cloud.</span><span class="sxs-lookup"><span data-stu-id="d5182-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="d5182-403">L'ultima configurazione valida nota è stata applicata correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="d5182-404">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-405">52</span><span class="sxs-lookup"><span data-stu-id="d5182-405">52</span></span></td>
   <td><span data-ttu-id="d5182-406">Impossibile applicare la nuova configurazione cloud, versione: %1.</span><span class="sxs-lookup"><span data-stu-id="d5182-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="d5182-407">Impossibile applicare anche l'ultima configurazione valida nota, versione %2.</span><span class="sxs-lookup"><span data-stu-id="d5182-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="d5182-408">La configurazione predefinita è stata applicata correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="d5182-409">Ricevuto un file di configurazione non valido dal servizio cloud.</span><span class="sxs-lookup"><span data-stu-id="d5182-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="d5182-410">Impossibile applicare l'ultima configurazione valida nota e la configurazione predefinita è stata applicata.</span><span class="sxs-lookup"><span data-stu-id="d5182-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="d5182-411">Il servizio tenterà di scaricare un nuovo file di configurazione entro 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="d5182-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="d5182-412">Se non vedi l'evento #50 - contatta il supporto.</span><span class="sxs-lookup"><span data-stu-id="d5182-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-413">53</span><span class="sxs-lookup"><span data-stu-id="d5182-413">53</span></span></td>
   <td><span data-ttu-id="d5182-414">Configurazione cloud caricata dall'archiviazione persistente, versione: %1.</span><span class="sxs-lookup"><span data-stu-id="d5182-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="d5182-415">La configurazione è stata caricata dall'archiviazione permanente all'avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="d5182-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="d5182-416">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-417">55</span><span class="sxs-lookup"><span data-stu-id="d5182-417">55</span></span></td>
   <td><span data-ttu-id="d5182-418">Impossibile creare l'autologger Secure ETW.</span><span class="sxs-lookup"><span data-stu-id="d5182-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="d5182-419">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="d5182-420">Impossibile creare il logger ETW sicuro.</span><span class="sxs-lookup"><span data-stu-id="d5182-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="d5182-421">Riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5182-421">Reboot the device.</span></span> <span data-ttu-id="d5182-422">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-423">56</span><span class="sxs-lookup"><span data-stu-id="d5182-423">56</span></span></td>
   <td><span data-ttu-id="d5182-424">Impossibile rimuovere l'autologger Secure ETW.</span><span class="sxs-lookup"><span data-stu-id="d5182-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="d5182-425">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="d5182-426">Impossibile rimuovere la sessione ETW sicura durante l'offboarding.</span><span class="sxs-lookup"><span data-stu-id="d5182-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="d5182-427">Contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-428">57</span><span class="sxs-lookup"><span data-stu-id="d5182-428">57</span></span></td>
   <td><span data-ttu-id="d5182-429">Acquisizione di uno snapshot del computer per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="d5182-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="d5182-430">È in corso la raccolta di un pacchetto di indagine, noto anche come pacchetto forense.</span><span class="sxs-lookup"><span data-stu-id="d5182-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="d5182-431">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-432">59</span><span class="sxs-lookup"><span data-stu-id="d5182-432">59</span></span></td>
   <td><span data-ttu-id="d5182-433">Avvio del comando: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="d5182-434">Avvio dell'esecuzione del comando di risposta.</span><span class="sxs-lookup"><span data-stu-id="d5182-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="d5182-435">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-436">60</span><span class="sxs-lookup"><span data-stu-id="d5182-436">60</span></span></td>
   <td><span data-ttu-id="d5182-437">Impossibile eseguire il comando %1, errore: %2.</span><span class="sxs-lookup"><span data-stu-id="d5182-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="d5182-438">Impossibile eseguire il comando di risposta.</span><span class="sxs-lookup"><span data-stu-id="d5182-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="d5182-439">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-440">61</span><span class="sxs-lookup"><span data-stu-id="d5182-440">61</span></span></td>
   <td><span data-ttu-id="d5182-441">I parametri del comando di raccolta dati non sono validi: SasUri: %1, compressionLevel: %2.</span><span class="sxs-lookup"><span data-stu-id="d5182-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="d5182-442">Impossibile leggere o analizzare gli argomenti del comando di raccolta dati (argomenti non validi).</span><span class="sxs-lookup"><span data-stu-id="d5182-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="d5182-443">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-444">62</span><span class="sxs-lookup"><span data-stu-id="d5182-444">62</span></span></td>
   <td><span data-ttu-id="d5182-445">Impossibile avviare il servizio Esperienze utente connesse e telemetria.</span><span class="sxs-lookup"><span data-stu-id="d5182-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="d5182-446">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="d5182-447">Avvio del servizio Esperienze utente connesse e telemetria (diagtrack) non riuscito.</span><span class="sxs-lookup"><span data-stu-id="d5182-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="d5182-448">La telemetria non di Microsoft Defender for Endpoint non verrà inviata da questo computer.</span><span class="sxs-lookup"><span data-stu-id="d5182-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="d5182-449">Cercare altri suggerimenti per la risoluzione dei problemi nel registro eventi: Microsoft-Windows-UniversalTelemetryClient/Operational.</span><span class="sxs-lookup"><span data-stu-id="d5182-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-450">63</span><span class="sxs-lookup"><span data-stu-id="d5182-450">63</span></span></td>
   <td><span data-ttu-id="d5182-451">Aggiornamento del tipo di avvio del servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="d5182-451">Updating the start type of external service.</span></span> <span data-ttu-id="d5182-452">Nome: %1, tipo di avvio effettivo: %2, tipo di avvio previsto: %3, codice di uscita: %4</span><span class="sxs-lookup"><span data-stu-id="d5182-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="d5182-453">Tipo di avvio aggiornato del servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="d5182-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="d5182-454">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-455">64</span><span class="sxs-lookup"><span data-stu-id="d5182-455">64</span></span></td>
   <td><span data-ttu-id="d5182-456">Avvio del servizio esterno arrestato.</span><span class="sxs-lookup"><span data-stu-id="d5182-456">Starting stopped external service.</span></span> <span data-ttu-id="d5182-457">Nome: %1, codice di uscita: %2</span><span class="sxs-lookup"><span data-stu-id="d5182-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="d5182-458">Avvio di un servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="d5182-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="d5182-459">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-460">65</span><span class="sxs-lookup"><span data-stu-id="d5182-460">65</span></span></td>
   <td><span data-ttu-id="d5182-461">Impossibile caricare il driver Minifilter del componente Eventi di sicurezza Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5182-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="d5182-462">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="d5182-463">Impossibile caricare il minifiltro MsSecFlt.sys filesystem.</span><span class="sxs-lookup"><span data-stu-id="d5182-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="d5182-464">Riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5182-464">Reboot the device.</span></span> <span data-ttu-id="d5182-465">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-466">66</span><span class="sxs-lookup"><span data-stu-id="d5182-466">66</span></span></td>
   <td><span data-ttu-id="d5182-467">Aggiornamento dei criteri: modalità latenza - %1</span><span class="sxs-lookup"><span data-stu-id="d5182-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="d5182-468">Il criterio C&C connection frequency è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d5182-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="d5182-469">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-470">68</span><span class="sxs-lookup"><span data-stu-id="d5182-470">68</span></span></td>
   <td><span data-ttu-id="d5182-471">Il tipo di avvio del servizio è imprevisto.</span><span class="sxs-lookup"><span data-stu-id="d5182-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="d5182-472">Nome servizio: %1, tipo di avvio effettivo: %2, tipo di avvio previsto: %3</span><span class="sxs-lookup"><span data-stu-id="d5182-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="d5182-473">Tipo di avvio del servizio esterno imprevisto.</span><span class="sxs-lookup"><span data-stu-id="d5182-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="d5182-474">Correggere il tipo di avvio del servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="d5182-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-475">69</span><span class="sxs-lookup"><span data-stu-id="d5182-475">69</span></span></td>
   <td><span data-ttu-id="d5182-476">Il servizio è stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="d5182-476">The service is stopped.</span></span> <span data-ttu-id="d5182-477">Nome servizio: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="d5182-478">Il servizio esterno è stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="d5182-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="d5182-479">Avviare il servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="d5182-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-480">70</span><span class="sxs-lookup"><span data-stu-id="d5182-480">70</span></span></td>
   <td><span data-ttu-id="d5182-481">Aggiornamento dei criteri: consenti raccolta di esempio - %1</span><span class="sxs-lookup"><span data-stu-id="d5182-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="d5182-482">Il criterio di raccolta di esempio è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d5182-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="d5182-483">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-484">71</span><span class="sxs-lookup"><span data-stu-id="d5182-484">71</span></span></td>
   <td><span data-ttu-id="d5182-485">Esecuzione del comando completata: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="d5182-486">Il comando è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5182-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="d5182-487">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-488">72</span><span class="sxs-lookup"><span data-stu-id="d5182-488">72</span></span></td>
   <td><span data-ttu-id="d5182-489">Tentativo di inviare il primo report del profilo computer completo.</span><span class="sxs-lookup"><span data-stu-id="d5182-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="d5182-490">Codice risultato: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="d5182-491">Solo informativo.</span><span class="sxs-lookup"><span data-stu-id="d5182-491">Informational only.</span></span></td>
   <td><span data-ttu-id="d5182-492">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-493">73</span><span class="sxs-lookup"><span data-stu-id="d5182-493">73</span></span></td>
   <td><span data-ttu-id="d5182-494">Avvio di Sense per la piattaforma: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="d5182-495">Solo informativo.</span><span class="sxs-lookup"><span data-stu-id="d5182-495">Informational only.</span></span></td>
   <td><span data-ttu-id="d5182-496">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-497">74</span><span class="sxs-lookup"><span data-stu-id="d5182-497">74</span></span></td>
   <td><span data-ttu-id="d5182-498">Il tag del dispositivo nel Registro di sistema supera il limite di lunghezza.</span><span class="sxs-lookup"><span data-stu-id="d5182-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="d5182-499">Nome tag: %2.</span><span class="sxs-lookup"><span data-stu-id="d5182-499">Tag name: %2.</span></span> <span data-ttu-id="d5182-500">Limite di lunghezza: %1.</span><span class="sxs-lookup"><span data-stu-id="d5182-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="d5182-501">Il tag del dispositivo supera il limite di lunghezza.</span><span class="sxs-lookup"><span data-stu-id="d5182-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="d5182-502">Usa un tag dispositivo più breve.</span><span class="sxs-lookup"><span data-stu-id="d5182-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-503">81</span><span class="sxs-lookup"><span data-stu-id="d5182-503">81</span></span></td>
   <td><span data-ttu-id="d5182-504">Non è stato possibile creare Windows Defender autologger ETW advanced threat protection.</span><span class="sxs-lookup"><span data-stu-id="d5182-504">Failed to create Windows Defender Advanced Threat Protection ETW autologger.</span></span> <span data-ttu-id="d5182-505">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="d5182-506">Impossibile creare la sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="d5182-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="d5182-507">Riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5182-507">Reboot the device.</span></span> <span data-ttu-id="d5182-508">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-509">82</span><span class="sxs-lookup"><span data-stu-id="d5182-509">82</span></span></td>
   <td><span data-ttu-id="d5182-510">Impossibile rimuovere Windows Defender autologger ETW di Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="d5182-510">Failed to remove Windows Defender Advanced Threat Protection ETW autologger.</span></span> <span data-ttu-id="d5182-511">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="d5182-512">Impossibile eliminare la sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="d5182-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="d5182-513">Contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-514">84</span><span class="sxs-lookup"><span data-stu-id="d5182-514">84</span></span></td>
   <td><span data-ttu-id="d5182-515">Impostare Windows Defender in esecuzione antivirus.</span><span class="sxs-lookup"><span data-stu-id="d5182-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="d5182-516">Forza modalità passiva: %1, codice risultato: %2.</span><span class="sxs-lookup"><span data-stu-id="d5182-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="d5182-517">Imposta la modalità di esecuzione del defender (attiva o passiva).</span><span class="sxs-lookup"><span data-stu-id="d5182-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="d5182-518">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-519">85</span><span class="sxs-lookup"><span data-stu-id="d5182-519">85</span></span></td>
   <td><span data-ttu-id="d5182-520">Impossibile attivare il Windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="d5182-520">Failed to trigger Windows Defender Advanced Threat Protection executable.</span></span> <span data-ttu-id="d5182-521">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="d5182-522">Impossibile eseguire l'eseguibile SenseIR.</span><span class="sxs-lookup"><span data-stu-id="d5182-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="d5182-523">Riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5182-523">Reboot the device.</span></span> <span data-ttu-id="d5182-524">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-525">86</span><span class="sxs-lookup"><span data-stu-id="d5182-525">86</span></span></td>
   <td><span data-ttu-id="d5182-526">L'avvio ha arrestato nuovamente il servizio esterno che dovrebbe essere in servizio.</span><span class="sxs-lookup"><span data-stu-id="d5182-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="d5182-527">Nome: %1, codice di uscita: %2</span><span class="sxs-lookup"><span data-stu-id="d5182-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="d5182-528">Avvio del servizio esterno di nuovo.</span><span class="sxs-lookup"><span data-stu-id="d5182-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="d5182-529">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-530">87</span><span class="sxs-lookup"><span data-stu-id="d5182-530">87</span></span></td>
   <td><span data-ttu-id="d5182-531">Impossibile avviare il servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="d5182-531">Cannot start the external service.</span></span> <span data-ttu-id="d5182-532">Nome: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-532">Name: %1</span></span></td>
   <td><span data-ttu-id="d5182-533">Impossibile avviare il servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="d5182-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="d5182-534">Contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-535">88</span><span class="sxs-lookup"><span data-stu-id="d5182-535">88</span></span></td>
   <td><span data-ttu-id="d5182-536">Aggiornamento del tipo di avvio del servizio esterno di nuovo.</span><span class="sxs-lookup"><span data-stu-id="d5182-536">Updating the start type of external service again.</span></span> <span data-ttu-id="d5182-537">Nome: %1, tipo di avvio effettivo: %2, tipo di avvio previsto: %3, codice di uscita: %4</span><span class="sxs-lookup"><span data-stu-id="d5182-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="d5182-538">È stato aggiornato il tipo di avvio del servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="d5182-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="d5182-539">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-540">89</span><span class="sxs-lookup"><span data-stu-id="d5182-540">89</span></span></td>
   <td><span data-ttu-id="d5182-541">Impossibile aggiornare il tipo di avvio del servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="d5182-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="d5182-542">Nome: %1, tipo di avvio effettivo: %2, tipo di avvio previsto: %3</span><span class="sxs-lookup"><span data-stu-id="d5182-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="d5182-543">Impossibile aggiornare il tipo di avvio del servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="d5182-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="d5182-544">Contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-545">90</span><span class="sxs-lookup"><span data-stu-id="d5182-545">90</span></span></td>
   <td><span data-ttu-id="d5182-546">Impossibile configurare System Guard Runtime Monitor per la connessione al servizio cloud nell'area geografica %1.</span><span class="sxs-lookup"><span data-stu-id="d5182-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="d5182-547">Codice errore: %2</span><span class="sxs-lookup"><span data-stu-id="d5182-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="d5182-548">System Guard Runtime Monitor non invierà dati di attestazione al servizio cloud.</span><span class="sxs-lookup"><span data-stu-id="d5182-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="d5182-549">Controlla le autorizzazioni nel percorso di registrazione: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="d5182-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="d5182-550">Se non vengono individuati problemi, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-551">91</span><span class="sxs-lookup"><span data-stu-id="d5182-551">91</span></span></td>
   <td><span data-ttu-id="d5182-552">Impossibile rimuovere le informazioni sull'area geografica di System Guard Runtime Monitor.</span><span class="sxs-lookup"><span data-stu-id="d5182-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="d5182-553">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="d5182-554">System Guard Runtime Monitor non invierà dati di attestazione al servizio cloud.</span><span class="sxs-lookup"><span data-stu-id="d5182-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="d5182-555">Controlla le autorizzazioni nel percorso di registrazione: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="d5182-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="d5182-556">Se non vengono individuati problemi, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-557">92</span><span class="sxs-lookup"><span data-stu-id="d5182-557">92</span></span></td>
   <td><span data-ttu-id="d5182-558">Interruzione dell'invio della quota di dati informatici del sensore perché la quota dei dati viene superata.</span><span class="sxs-lookup"><span data-stu-id="d5182-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="d5182-559">Riprenderà l'invio al termine del periodo di quota.</span><span class="sxs-lookup"><span data-stu-id="d5182-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="d5182-560">State Mask: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="d5182-561">Superare il limite di limitazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="d5182-562">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-563">93</span><span class="sxs-lookup"><span data-stu-id="d5182-563">93</span></span></td>
   <td><span data-ttu-id="d5182-564">Ripresa dell'invio dei dati informatici del sensore.</span><span class="sxs-lookup"><span data-stu-id="d5182-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="d5182-565">State Mask: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="d5182-566">Riprendere l'invio di dati informatici.</span><span class="sxs-lookup"><span data-stu-id="d5182-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="d5182-567">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-568">94</span><span class="sxs-lookup"><span data-stu-id="d5182-568">94</span></span></td>
   <td><span data-ttu-id="d5182-569">Windows Defender eseguibile advanced threat protection avviato</span><span class="sxs-lookup"><span data-stu-id="d5182-569">Windows Defender Advanced Threat Protection executable has started</span></span></td>
   <td><span data-ttu-id="d5182-570">L'eseguibile SenseCE è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="d5182-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="d5182-571">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-572">95</span><span class="sxs-lookup"><span data-stu-id="d5182-572">95</span></span></td>
   <td><span data-ttu-id="d5182-573">Windows Defender eseguibile advanced threat protection è terminato</span><span class="sxs-lookup"><span data-stu-id="d5182-573">Windows Defender Advanced Threat Protection executable has ended</span></span></td>
   <td><span data-ttu-id="d5182-574">L'eseguibile SenseCE è terminato.</span><span class="sxs-lookup"><span data-stu-id="d5182-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="d5182-575">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-576">96</span><span class="sxs-lookup"><span data-stu-id="d5182-576">96</span></span></td>
   <td><span data-ttu-id="d5182-577">Windows Defender ha chiamato Advanced Threat Protection Init.</span><span class="sxs-lookup"><span data-stu-id="d5182-577">Windows Defender Advanced Threat Protection Init has called.</span></span> <span data-ttu-id="d5182-578">Codice risultato: %2</span><span class="sxs-lookup"><span data-stu-id="d5182-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="d5182-579">L'eseguibile SenseCE ha chiamato inizializzazione MCE.</span><span class="sxs-lookup"><span data-stu-id="d5182-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="d5182-580">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-581">97</span><span class="sxs-lookup"><span data-stu-id="d5182-581">97</span></span></td>
   <td><span data-ttu-id="d5182-582">Ci sono problemi di connettività al cloud per lo scenario DLP</span><span class="sxs-lookup"><span data-stu-id="d5182-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="d5182-583">Esistono problemi di connettività di rete che influiscono sul flusso di classificazione DLP.</span><span class="sxs-lookup"><span data-stu-id="d5182-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="d5182-584">Controllare la connettività di rete.</span><span class="sxs-lookup"><span data-stu-id="d5182-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-585">98</span><span class="sxs-lookup"><span data-stu-id="d5182-585">98</span></span></td>
   <td><span data-ttu-id="d5182-586">La connettività al cloud per lo scenario DLP è stata ripristinata</span><span class="sxs-lookup"><span data-stu-id="d5182-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="d5182-587">La connettività alla rete è stata ripristinata e il flusso di classificazione DLP può continuare.</span><span class="sxs-lookup"><span data-stu-id="d5182-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="d5182-588">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-589">99</span><span class="sxs-lookup"><span data-stu-id="d5182-589">99</span></span></td>
   <td><span data-ttu-id="d5182-590">Rilevato l'errore seguente durante la comunicazione con il server: (%1).</span><span class="sxs-lookup"><span data-stu-id="d5182-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="d5182-591">Risultato: (%2)</span><span class="sxs-lookup"><span data-stu-id="d5182-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="d5182-592">Si è verificato un errore di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="d5182-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="d5182-593">Per ulteriori dettagli, controllare gli eventi seguenti nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="d5182-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-594">100</span><span class="sxs-lookup"><span data-stu-id="d5182-594">100</span></span></td>
   <td><span data-ttu-id="d5182-595">Windows Defender'avvio del file eseguibile di Advanced Threat Protection non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="d5182-595">Windows Defender Advanced Threat Protection executable failed to start.</span></span> <span data-ttu-id="d5182-596">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="d5182-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="d5182-597">Impossibile avviare il file eseguibile SenseCE.</span><span class="sxs-lookup"><span data-stu-id="d5182-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="d5182-598">Riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5182-598">Reboot the device.</span></span> <span data-ttu-id="d5182-599">Se l'errore persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="d5182-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-600">102</span><span class="sxs-lookup"><span data-stu-id="d5182-600">102</span></span></td>
   <td><span data-ttu-id="d5182-601">Windows Defender file eseguibile di rilevamento e risposta di Advanced Threat Protection network detection and response è stato avviato</span><span class="sxs-lookup"><span data-stu-id="d5182-601">Windows Defender Advanced Threat Protection Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="d5182-602">L'eseguibile SenseNdr è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="d5182-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="d5182-603">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="d5182-604">103</span><span class="sxs-lookup"><span data-stu-id="d5182-604">103</span></span></td>
   <td><span data-ttu-id="d5182-605">Windows Defender file eseguibile advanced threat protection network detection and response è terminato</span><span class="sxs-lookup"><span data-stu-id="d5182-605">Windows Defender Advanced Threat Protection Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="d5182-606">L'eseguibile SenseNdr è terminato.</span><span class="sxs-lookup"><span data-stu-id="d5182-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="d5182-607">Normale notifica operativa; non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="d5182-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="d5182-608">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d5182-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d5182-609">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d5182-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="d5182-610">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d5182-610">Related topics</span></span>
- [<span data-ttu-id="d5182-611">Onboard di dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="d5182-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="d5182-612">Configurare le impostazioni del proxy del dispositivo e della connettività Internet</span><span class="sxs-lookup"><span data-stu-id="d5182-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="d5182-613">Risolvere i problemi di Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="d5182-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)