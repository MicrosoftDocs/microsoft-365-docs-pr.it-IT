---
title: Risolvere i problemi di onboarding di Microsoft Defender per endpoint
description: Risolvere i problemi che potrebbero verificarsi durante l'onboarding dei dispositivi o nel servizio Microsoft Defender for Endpoint.
keywords: risolvere i problemi di onboarding, onboarding, visualizzatore eventi, raccolte dati e anteprime, dati dei sensori e diagnostica
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: b3ee2f2dcf13402e506b299935459e435fd2f89a
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326904"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-onboarding-issues"></a><span data-ttu-id="c6629-104">Risolvere i problemi di onboarding di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c6629-104">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c6629-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c6629-105">**Applies to:**</span></span>

- [<span data-ttu-id="c6629-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c6629-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- <span data-ttu-id="c6629-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c6629-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="c6629-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c6629-108">Windows Server 2016</span></span>
- [<span data-ttu-id="c6629-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6629-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c6629-110">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c6629-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c6629-111">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c6629-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="c6629-112">In caso di problemi, potrebbe essere necessario risolvere i problemi relativi al processo di onboarding di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c6629-112">You might need to troubleshoot the Microsoft Defender for Endpoint onboarding process if you encounter issues.</span></span>
<span data-ttu-id="c6629-113">Questa pagina fornisce la procedura dettagliata per risolvere i problemi di onboarding che potrebbero verificarsi durante la distribuzione con uno degli strumenti di distribuzione e gli errori comuni che potrebbero verificarsi nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c6629-113">This page provides detailed steps to troubleshoot onboarding issues that might occur when deploying with one of the deployment tools and common errors that might occur on the devices.</span></span>

## <a name="troubleshoot-issues-with-onboarding-tools"></a><span data-ttu-id="c6629-114">Risolvere i problemi relativi agli strumenti di onboarding</span><span class="sxs-lookup"><span data-stu-id="c6629-114">Troubleshoot issues with onboarding tools</span></span>

<span data-ttu-id="c6629-115">Se hai completato il processo di onboarding e [](investigate-machines.md) non vedi i dispositivi nell'elenco Dispositivi dopo un'ora, potrebbe indicare un problema di onboarding o connettività.</span><span class="sxs-lookup"><span data-stu-id="c6629-115">If you have completed the onboarding process and don't see devices in the [Devices list](investigate-machines.md) after an hour, it might indicate an onboarding or connectivity problem.</span></span>

### <a name="troubleshoot-onboarding-when-deploying-with-group-policy"></a><span data-ttu-id="c6629-116">Risolvere i problemi di onboarding durante la distribuzione con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="c6629-116">Troubleshoot onboarding when deploying with Group Policy</span></span>

<span data-ttu-id="c6629-117">La distribuzione con Criteri di gruppo viene eseguita eseguendo lo script di onboarding nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c6629-117">Deployment with Group Policy is done by running the onboarding script on the devices.</span></span> <span data-ttu-id="c6629-118">La console Criteri di gruppo non indica se la distribuzione è riuscita o meno.</span><span class="sxs-lookup"><span data-stu-id="c6629-118">The Group Policy console does not indicate if the deployment has succeeded or not.</span></span>

<span data-ttu-id="c6629-119">Se hai completato il processo di onboarding e [](investigate-machines.md) non vedi i dispositivi nell'elenco Dispositivi dopo un'ora, puoi controllare l'output dello script nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c6629-119">If you have completed the onboarding process and don't see devices in the [Devices list](investigate-machines.md) after an hour, you can check the output of the script on the devices.</span></span> <span data-ttu-id="c6629-120">Per ulteriori informazioni, vedere [Risoluzione dei problemi di onboarding durante la distribuzione con uno script.](#troubleshoot-onboarding-when-deploying-with-a-script)</span><span class="sxs-lookup"><span data-stu-id="c6629-120">For more information, see [Troubleshoot onboarding when deploying with a script](#troubleshoot-onboarding-when-deploying-with-a-script).</span></span>

<span data-ttu-id="c6629-121">Se lo script viene completato correttamente, vedi Risolvere i problemi di [onboarding](#troubleshoot-onboarding-issues-on-the-device) nei dispositivi per ulteriori errori che potrebbero verificarsi.</span><span class="sxs-lookup"><span data-stu-id="c6629-121">If the script completes successfully, see [Troubleshoot onboarding issues on the devices](#troubleshoot-onboarding-issues-on-the-device) for additional errors that might occur.</span></span>

### <a name="troubleshoot-onboarding-issues-when-deploying-with-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="c6629-122">Risolvere i problemi di onboarding durante la distribuzione con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c6629-122">Troubleshoot onboarding issues when deploying with Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="c6629-123">Quando si esegue l'onboarding dei dispositivi con le versioni seguenti di Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="c6629-123">When onboarding devices using the following versions of Configuration Manager:</span></span>

- <span data-ttu-id="c6629-124">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c6629-124">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="c6629-125">System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c6629-125">System Center 2012 Configuration Manager</span></span>
- <span data-ttu-id="c6629-126">System Center Configuration Manager 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c6629-126">System Center 2012 R2 Configuration Manager</span></span>

<span data-ttu-id="c6629-127">La distribuzione con le versioni precedenti di Configuration Manager viene eseguita eseguendo lo script di onboarding nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c6629-127">Deployment with the above-mentioned versions of Configuration Manager is done by running the onboarding script on the devices.</span></span> <span data-ttu-id="c6629-128">È possibile tenere traccia della distribuzione nella console di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="c6629-128">You can track the deployment in the Configuration Manager Console.</span></span>

<span data-ttu-id="c6629-129">Se la distribuzione ha esito negativo, puoi controllare l'output dello script nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c6629-129">If the deployment fails, you can check the output of the script on the devices.</span></span>

<span data-ttu-id="c6629-130">Se l'onboarding è stato completato correttamente  ma i dispositivi non vengono visualizzati nell'elenco Dispositivi dopo un'ora, vedi Risolvere i problemi di [onboarding](#troubleshoot-onboarding-issues-on-the-device) nel dispositivo per ulteriori errori che potrebbero verificarsi.</span><span class="sxs-lookup"><span data-stu-id="c6629-130">If the onboarding completed successfully but the devices are not showing up in the **Devices list** after an hour, see [Troubleshoot onboarding issues on the device](#troubleshoot-onboarding-issues-on-the-device) for additional errors that might occur.</span></span>

### <a name="troubleshoot-onboarding-when-deploying-with-a-script"></a><span data-ttu-id="c6629-131">Risolvere i problemi di onboarding durante la distribuzione con uno script</span><span class="sxs-lookup"><span data-stu-id="c6629-131">Troubleshoot onboarding when deploying with a script</span></span>

<span data-ttu-id="c6629-132">**Controlla il risultato dello script nel dispositivo:**</span><span class="sxs-lookup"><span data-stu-id="c6629-132">**Check the result of the script on the device:**</span></span>

1. <span data-ttu-id="c6629-133">Fare **clic sul pulsante Start,** digitare **Visualizzatore** eventi e premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="c6629-133">Click **Start**, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="c6629-134">Vai a **Windows Logs**  >  **Application**.</span><span class="sxs-lookup"><span data-stu-id="c6629-134">Go to **Windows Logs** > **Application**.</span></span>

3. <span data-ttu-id="c6629-135">Cercare un evento dall'origine evento **WDATPOnboarding.**</span><span class="sxs-lookup"><span data-stu-id="c6629-135">Look for an event from **WDATPOnboarding** event source.</span></span>

<span data-ttu-id="c6629-136">Se lo script ha esito negativo e l'evento è un errore, è possibile controllare l'ID evento nella tabella seguente per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="c6629-136">If the script fails and the event is an error, you can check the event ID in the following table to help you troubleshoot the issue.</span></span>

> [!NOTE]
> <span data-ttu-id="c6629-137">Gli ID evento seguenti sono specifici solo per lo script di onboarding.</span><span class="sxs-lookup"><span data-stu-id="c6629-137">The following event IDs are specific to the onboarding script only.</span></span>

<span data-ttu-id="c6629-138">ID evento</span><span class="sxs-lookup"><span data-stu-id="c6629-138">Event ID</span></span> | <span data-ttu-id="c6629-139">Tipo di errore</span><span class="sxs-lookup"><span data-stu-id="c6629-139">Error Type</span></span> | <span data-ttu-id="c6629-140">Passaggi di risoluzione</span><span class="sxs-lookup"><span data-stu-id="c6629-140">Resolution steps</span></span>
:---:|:---|:---
 `5` | <span data-ttu-id="c6629-141">I dati di offboarding sono stati trovati ma non è stato possibile eliminare</span><span class="sxs-lookup"><span data-stu-id="c6629-141">Offboarding data was found but couldn't be deleted</span></span> | <span data-ttu-id="c6629-142">Controllare le autorizzazioni nel Registro di sistema, in particolare</span><span class="sxs-lookup"><span data-stu-id="c6629-142">Check the permissions on the registry, specifically</span></span><br> <span data-ttu-id="c6629-143">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span><span class="sxs-lookup"><span data-stu-id="c6629-143">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span></span>
`10` | <span data-ttu-id="c6629-144">Impossibile scrivere i dati di onboarding nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="c6629-144">Onboarding data couldn't be written to registry</span></span> |  <span data-ttu-id="c6629-145">Controllare le autorizzazioni nel Registro di sistema, in particolare</span><span class="sxs-lookup"><span data-stu-id="c6629-145">Check the permissions on the registry, specifically</span></span><br> <span data-ttu-id="c6629-146">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span><span class="sxs-lookup"><span data-stu-id="c6629-146">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span></span><br><span data-ttu-id="c6629-147">Verificare che lo script sia stato eseguito come amministratore.</span><span class="sxs-lookup"><span data-stu-id="c6629-147">Verify that the script has been run as an administrator.</span></span>
`15` |  <span data-ttu-id="c6629-148">Impossibile avviare il servizio SENSE</span><span class="sxs-lookup"><span data-stu-id="c6629-148">Failed to start SENSE service</span></span> |<span data-ttu-id="c6629-149">Controllare l'integrità del servizio ( `sc query sense` comando).</span><span class="sxs-lookup"><span data-stu-id="c6629-149">Check the service health (`sc query sense` command).</span></span> <span data-ttu-id="c6629-150">Assicurati che non sia in uno stato intermedio (*'Pending_Stopped'*, *'Pending_Running'*) e prova a eseguire di nuovo lo script (con diritti di amministratore).</span><span class="sxs-lookup"><span data-stu-id="c6629-150">Make sure it's not in an intermediate state (*'Pending_Stopped'*, *'Pending_Running'*) and try to run the script again (with administrator rights).</span></span> <br> <br> <span data-ttu-id="c6629-151">Se il dispositivo esegue Windows 10, versione 1607 ed esecuzione del comando `sc query sense` restituisce `START_PENDING` , riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c6629-151">If the device is running Windows 10, version 1607 and running the command `sc query sense` returns `START_PENDING`, reboot the device.</span></span> <span data-ttu-id="c6629-152">Se il riavvio del dispositivo non consente di risolvere il problema, eseguire l'aggiornamento a KB4015217 e provare di nuovo l'onboarding.</span><span class="sxs-lookup"><span data-stu-id="c6629-152">If rebooting the device doesn't address the issue, upgrade to KB4015217 and try onboarding again.</span></span>
`15` | <span data-ttu-id="c6629-153">Impossibile avviare il servizio SENSE</span><span class="sxs-lookup"><span data-stu-id="c6629-153">Failed to start SENSE service</span></span> | <span data-ttu-id="c6629-154">Se il messaggio dell'errore è: Errore di sistema 577 o errore 1058, è necessario abilitare il driver ELAM Antivirus Microsoft Defender, vedere Verificare che [Antivirus Microsoft Defender](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) non sia disabilitato da un criterio per istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c6629-154">If the message of the error is: System error 577  or error 1058 has occurred, you need to enable the Microsoft Defender Antivirus ELAM driver, see [Ensure that Microsoft Defender Antivirus is not disabled by a policy](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) for instructions.</span></span>
`30` |  <span data-ttu-id="c6629-155">Lo script non è riuscito ad attendere l'avvio dell'esecuzione del servizio</span><span class="sxs-lookup"><span data-stu-id="c6629-155">The script failed to wait for the service to start running</span></span> | <span data-ttu-id="c6629-156">L'avvio del servizio potrebbe aver impiegato più tempo oppure si sono verificati errori durante il tentativo di avvio.</span><span class="sxs-lookup"><span data-stu-id="c6629-156">The service could have taken more time to start or has encountered errors while trying to start.</span></span> <span data-ttu-id="c6629-157">Per ulteriori informazioni sugli eventi e sugli errori correlati a SENSE, vedi [Esaminare gli eventi e gli errori tramite visualizzatore eventi.](event-error-codes.md)</span><span class="sxs-lookup"><span data-stu-id="c6629-157">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`35` |  <span data-ttu-id="c6629-158">Lo script non è riuscito a trovare il valore del Registro di sistema relativo allo stato di onboarding necessario</span><span class="sxs-lookup"><span data-stu-id="c6629-158">The script failed to find needed onboarding status registry value</span></span> | <span data-ttu-id="c6629-159">Quando il servizio SENSE viene avviato per la prima volta, scrive lo stato di onboarding nel percorso del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="c6629-159">When the SENSE service starts for the first time, it writes onboarding status to the registry location</span></span><br><span data-ttu-id="c6629-160">`HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`.</span><span class="sxs-lookup"><span data-stu-id="c6629-160">`HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`.</span></span><br> <span data-ttu-id="c6629-161">Lo script non è riuscito a trovarlo dopo alcuni secondi.</span><span class="sxs-lookup"><span data-stu-id="c6629-161">The script failed to find it after several seconds.</span></span> <span data-ttu-id="c6629-162">Puoi testarlo manualmente e verificare se è presente.</span><span class="sxs-lookup"><span data-stu-id="c6629-162">You can manually test it and check if it's there.</span></span> <span data-ttu-id="c6629-163">Per ulteriori informazioni sugli eventi e sugli errori correlati a SENSE, vedi [Esaminare gli eventi e gli errori tramite visualizzatore eventi.](event-error-codes.md)</span><span class="sxs-lookup"><span data-stu-id="c6629-163">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`40` | <span data-ttu-id="c6629-164">Lo stato di onboarding del servizio SENSE non è impostato su **1**</span><span class="sxs-lookup"><span data-stu-id="c6629-164">SENSE service onboarding status is not set to **1**</span></span> | <span data-ttu-id="c6629-165">L'onboard del servizio SENSE non è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c6629-165">The SENSE service has failed to onboard properly.</span></span> <span data-ttu-id="c6629-166">Per ulteriori informazioni sugli eventi e sugli errori correlati a SENSE, vedi [Esaminare gli eventi e gli errori tramite visualizzatore eventi.](event-error-codes.md)</span><span class="sxs-lookup"><span data-stu-id="c6629-166">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`65` | <span data-ttu-id="c6629-167">Privilegi insufficienti</span><span class="sxs-lookup"><span data-stu-id="c6629-167">Insufficient privileges</span></span>| <span data-ttu-id="c6629-168">Eseguire di nuovo lo script con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="c6629-168">Run the script again with administrator privileges.</span></span>

### <a name="troubleshoot-onboarding-issues-using-microsoft-intune"></a><span data-ttu-id="c6629-169">Risolvere i problemi di onboarding con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c6629-169">Troubleshoot onboarding issues using Microsoft Intune</span></span>

<span data-ttu-id="c6629-170">È possibile utilizzare Microsoft Intune per controllare i codici di errore e tentare di risolvere la causa del problema.</span><span class="sxs-lookup"><span data-stu-id="c6629-170">You can use Microsoft Intune to check error codes and attempt to troubleshoot the cause of the issue.</span></span>

<span data-ttu-id="c6629-171">Se sono stati configurati criteri in Intune e non vengono propagati nei dispositivi, potrebbe essere necessario configurare la registrazione MDM automatica.</span><span class="sxs-lookup"><span data-stu-id="c6629-171">If you have configured policies in Intune and they are not propagated on devices, you might need to configure automatic MDM enrollment.</span></span>

<span data-ttu-id="c6629-172">Utilizzare le tabelle seguenti per comprendere le possibili cause dei problemi durante l'onboarding:</span><span class="sxs-lookup"><span data-stu-id="c6629-172">Use the following tables to understand the possible causes of issues while onboarding:</span></span>

- <span data-ttu-id="c6629-173">Microsoft Intune codici di errore e OMA-URIs tabella</span><span class="sxs-lookup"><span data-stu-id="c6629-173">Microsoft Intune error codes and OMA-URIs table</span></span>
- <span data-ttu-id="c6629-174">Tabella problemi noti relativi alla non conformità</span><span class="sxs-lookup"><span data-stu-id="c6629-174">Known issues with non-compliance table</span></span>
- <span data-ttu-id="c6629-175">Tabella dei registri eventi di Gestione dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="c6629-175">Mobile Device Management (MDM) event logs table</span></span>

<span data-ttu-id="c6629-176">Se nessuno dei registri eventi e dei passaggi per la risoluzione dei problemi funziona, scarica lo script locale dalla sezione **Gestione** dispositivi del portale ed eseguilo in un prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="c6629-176">If none of the event logs and troubleshooting steps work, download the Local script from the **Device management** section of the portal, and run it in an elevated command prompt.</span></span>

#### <a name="microsoft-intune-error-codes-and-oma-uris"></a><span data-ttu-id="c6629-177">Microsoft Intune codici di errore e OMA-URIs</span><span class="sxs-lookup"><span data-stu-id="c6629-177">Microsoft Intune error codes and OMA-URIs</span></span>

<span data-ttu-id="c6629-178">Codice di errore Hex</span><span class="sxs-lookup"><span data-stu-id="c6629-178">Error Code Hex</span></span> | <span data-ttu-id="c6629-179">Codice di errore Dec</span><span class="sxs-lookup"><span data-stu-id="c6629-179">Error Code Dec</span></span> | <span data-ttu-id="c6629-180">Description</span><span class="sxs-lookup"><span data-stu-id="c6629-180">Error Description</span></span> | <span data-ttu-id="c6629-181">URI OMA</span><span class="sxs-lookup"><span data-stu-id="c6629-181">OMA-URI</span></span> | <span data-ttu-id="c6629-182">Possibili cause e procedure di risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="c6629-182">Possible cause and troubleshooting steps</span></span>
:---:|:---|:---|:---|:---
<span data-ttu-id="c6629-183">0x87D1FDE8</span><span class="sxs-lookup"><span data-stu-id="c6629-183">0x87D1FDE8</span></span> | <span data-ttu-id="c6629-184">-2016281112</span><span class="sxs-lookup"><span data-stu-id="c6629-184">-2016281112</span></span> | <span data-ttu-id="c6629-185">Correzione non riuscita</span><span class="sxs-lookup"><span data-stu-id="c6629-185">Remediation failed</span></span> | <span data-ttu-id="c6629-186">Onboarding</span><span class="sxs-lookup"><span data-stu-id="c6629-186">Onboarding</span></span> <br> <span data-ttu-id="c6629-187">Offboarding</span><span class="sxs-lookup"><span data-stu-id="c6629-187">Offboarding</span></span> | <span data-ttu-id="c6629-188">**Causa possibile:** Onboarding o offboarding non riuscito in un BLOB errato: firma errata o campi PreviousOrgIds mancanti.</span><span class="sxs-lookup"><span data-stu-id="c6629-188">**Possible cause:** Onboarding or offboarding failed on a wrong blob: wrong signature or missing PreviousOrgIds fields.</span></span> <br><br> <span data-ttu-id="c6629-189">**Passaggi per la risoluzione dei problemi:**</span><span class="sxs-lookup"><span data-stu-id="c6629-189">**Troubleshooting steps:**</span></span> <br> <span data-ttu-id="c6629-190">Controlla gli ID evento nella sezione Visualizzare gli errori [di onboarding](#view-agent-onboarding-errors-in-the-device-event-log) dell'agente nel registro eventi del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c6629-190">Check the event IDs in the [View agent onboarding errors in the device event log](#view-agent-onboarding-errors-in-the-device-event-log) section.</span></span> <br><br> <span data-ttu-id="c6629-191">Controlla i registri eventi MDM nella tabella seguente o segui le istruzioni in [Diagnosticare](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)gli errori MDM in Windows 10 .</span><span class="sxs-lookup"><span data-stu-id="c6629-191">Check the MDM event logs in the following table or follow the instructions in [Diagnose MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).</span></span>
 | | | | <span data-ttu-id="c6629-192">Onboarding</span><span class="sxs-lookup"><span data-stu-id="c6629-192">Onboarding</span></span> <br> <span data-ttu-id="c6629-193">Offboarding</span><span class="sxs-lookup"><span data-stu-id="c6629-193">Offboarding</span></span> <br> <span data-ttu-id="c6629-194">SampleSharing</span><span class="sxs-lookup"><span data-stu-id="c6629-194">SampleSharing</span></span> | <span data-ttu-id="c6629-195">**Causa possibile:** La chiave del Registro di sistema di Microsoft Defender for Endpoint Policy non esiste o il client OMA DM non dispone delle autorizzazioni per scriverlo.</span><span class="sxs-lookup"><span data-stu-id="c6629-195">**Possible cause:** Microsoft Defender for Endpoint Policy registry key does not exist or the OMA DM client doesn't have permissions to write to it.</span></span> <br><br> <span data-ttu-id="c6629-196">**Passaggi per la risoluzione dei problemi:** Verificare che esista la seguente chiave del Registro di sistema: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="c6629-196">**Troubleshooting steps:** Ensure that the following registry key exists: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span> <br> <br> <span data-ttu-id="c6629-197">Se non esiste, aprire un comando con privilegi elevati e aggiungere la chiave.</span><span class="sxs-lookup"><span data-stu-id="c6629-197">If it doesn't exist, open an elevated command and add the key.</span></span>
 | | | | <span data-ttu-id="c6629-198">SenseIsRunning</span><span class="sxs-lookup"><span data-stu-id="c6629-198">SenseIsRunning</span></span> <br> <span data-ttu-id="c6629-199">OnboardingState</span><span class="sxs-lookup"><span data-stu-id="c6629-199">OnboardingState</span></span> <br> <span data-ttu-id="c6629-200">OrgId</span><span class="sxs-lookup"><span data-stu-id="c6629-200">OrgId</span></span> |  <span data-ttu-id="c6629-201">**Causa possibile:** Tentativo di correzione tramite proprietà di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c6629-201">**Possible cause:** An attempt to remediate by read-only property.</span></span> <span data-ttu-id="c6629-202">Onboarding non riuscito.</span><span class="sxs-lookup"><span data-stu-id="c6629-202">Onboarding has failed.</span></span> <br><br> <span data-ttu-id="c6629-203">**Passaggi per la risoluzione dei problemi:** Controlla la procedura di risoluzione dei problemi in [Risolvere i problemi di onboarding nel dispositivo](#troubleshoot-onboarding-issues-on-the-device).</span><span class="sxs-lookup"><span data-stu-id="c6629-203">**Troubleshooting steps:** Check the troubleshooting steps in [Troubleshoot onboarding issues on the device](#troubleshoot-onboarding-issues-on-the-device).</span></span> <br><br> <span data-ttu-id="c6629-204">Controlla i registri eventi MDM nella tabella seguente o segui le istruzioni in [Diagnosticare](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)gli errori MDM in Windows 10 .</span><span class="sxs-lookup"><span data-stu-id="c6629-204">Check the MDM event logs in the following table or follow the instructions in [Diagnose MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).</span></span>
 | | | | <span data-ttu-id="c6629-205">Tutto</span><span class="sxs-lookup"><span data-stu-id="c6629-205">All</span></span> | <span data-ttu-id="c6629-206">**Causa possibile:** Tenta di distribuire Microsoft Defender per Endpoint su SKU/Piattaforma non supportati, in particolare SKU olografico.</span><span class="sxs-lookup"><span data-stu-id="c6629-206">**Possible cause:** Attempt to deploy Microsoft Defender for Endpoint on non-supported SKU/Platform, particularly Holographic SKU.</span></span> <br><br> <span data-ttu-id="c6629-207">Piattaforme attualmente supportate:</span><span class="sxs-lookup"><span data-stu-id="c6629-207">Currently supported platforms:</span></span><br> <span data-ttu-id="c6629-208">Enterprise, Education e Professional.</span><span class="sxs-lookup"><span data-stu-id="c6629-208">Enterprise, Education, and Professional.</span></span><br> <span data-ttu-id="c6629-209">Server non supportato.</span><span class="sxs-lookup"><span data-stu-id="c6629-209">Server is not supported.</span></span>
 <span data-ttu-id="c6629-210">0x87D101A9</span><span class="sxs-lookup"><span data-stu-id="c6629-210">0x87D101A9</span></span> | <span data-ttu-id="c6629-211">-2016345687</span><span class="sxs-lookup"><span data-stu-id="c6629-211">-2016345687</span></span> |<span data-ttu-id="c6629-212">SyncML(425): il comando richiesto non è riuscito perché il mittente non dispone di autorizzazioni di controllo di accesso (ACL) adeguate per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="c6629-212">SyncML(425): The requested command failed because the sender does not have adequate access control permissions (ACL) on the recipient.</span></span> | <span data-ttu-id="c6629-213">Tutto</span><span class="sxs-lookup"><span data-stu-id="c6629-213">All</span></span> |  <span data-ttu-id="c6629-214">**Causa possibile:** Tenta di distribuire Microsoft Defender per Endpoint su SKU/Piattaforma non supportati, in particolare SKU olografico.</span><span class="sxs-lookup"><span data-stu-id="c6629-214">**Possible cause:** Attempt to deploy Microsoft Defender for Endpoint on non-supported SKU/Platform, particularly Holographic SKU.</span></span><br><br> <span data-ttu-id="c6629-215">Piattaforme attualmente supportate:</span><span class="sxs-lookup"><span data-stu-id="c6629-215">Currently supported platforms:</span></span><br>  <span data-ttu-id="c6629-216">Enterprise, Education e Professional.</span><span class="sxs-lookup"><span data-stu-id="c6629-216">Enterprise, Education, and Professional.</span></span>

#### <a name="known-issues-with-non-compliance"></a><span data-ttu-id="c6629-217">Problemi noti relativi alla non conformità</span><span class="sxs-lookup"><span data-stu-id="c6629-217">Known issues with non-compliance</span></span>

<span data-ttu-id="c6629-218">Nella tabella seguente vengono fornite informazioni sui problemi relativi alla non conformità e su come è possibile risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="c6629-218">The following table provides information on issues with non-compliance and how you can address the issues.</span></span>

<span data-ttu-id="c6629-219">Caso</span><span class="sxs-lookup"><span data-stu-id="c6629-219">Case</span></span> | <span data-ttu-id="c6629-220">Sintomi</span><span class="sxs-lookup"><span data-stu-id="c6629-220">Symptoms</span></span> | <span data-ttu-id="c6629-221">Possibili cause e procedure di risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="c6629-221">Possible cause and troubleshooting steps</span></span>
:---:|:---|:---
 `1` | <span data-ttu-id="c6629-222">Il dispositivo è conforme all'URI OMA SenseIsRunning.</span><span class="sxs-lookup"><span data-stu-id="c6629-222">Device is compliant by SenseIsRunning OMA-URI.</span></span> <span data-ttu-id="c6629-223">Ma non è conforme agli URI OMA orgId, Onboarding e OnboardingState.</span><span class="sxs-lookup"><span data-stu-id="c6629-223">But is non-compliant by OrgId, Onboarding and OnboardingState OMA-URIs.</span></span> | <span data-ttu-id="c6629-224">**Causa possibile:** Verificare che l'utente ha superato la Configurazione guidata dopo Windows'installazione o l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c6629-224">**Possible cause:** Check that user passed OOBE after Windows installation or upgrade.</span></span> <span data-ttu-id="c6629-225">Durante l'onboarding della Configurazione guidata non è stato possibile completare l'onboarding, ma SENSE è già in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c6629-225">During OOBE onboarding couldn't be completed but SENSE is running already.</span></span><br><br> <span data-ttu-id="c6629-226">**Passaggi per la risoluzione dei problemi:** Attendere il completamento della Procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="c6629-226">**Troubleshooting steps:** Wait for OOBE to complete.</span></span>
 `2` |  <span data-ttu-id="c6629-227">Device is compliant by OrgId, Onboarding, and OnboardingState OMA-URIs, but is non-compliant by SenseIsRunning OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="c6629-227">Device is compliant by OrgId, Onboarding, and OnboardingState OMA-URIs, but is non-compliant by SenseIsRunning OMA-URI.</span></span> |  <span data-ttu-id="c6629-228">**Causa possibile:** Il tipo di avvio del servizio Sense è impostato su "Avvio ritardato".</span><span class="sxs-lookup"><span data-stu-id="c6629-228">**Possible cause:** Sense service's startup type is set as "Delayed Start".</span></span> <span data-ttu-id="c6629-229">A volte il server Microsoft Intune segnalare il dispositivo come non conforme da SenseIsRunning quando si verifica una sessione DM all'avvio del sistema.</span><span class="sxs-lookup"><span data-stu-id="c6629-229">Sometimes this causes the Microsoft Intune server to report the device as non-compliant by SenseIsRunning when DM session occurs on system start.</span></span> <br><br> <span data-ttu-id="c6629-230">**Passaggi per la risoluzione dei problemi:** Il problema dovrebbe essere risolto automaticamente entro 24 ore.</span><span class="sxs-lookup"><span data-stu-id="c6629-230">**Troubleshooting steps:** The issue should automatically be fixed within 24 hours.</span></span>
 `3` | <span data-ttu-id="c6629-231">Il dispositivo non è conforme</span><span class="sxs-lookup"><span data-stu-id="c6629-231">Device is non-compliant</span></span> | <span data-ttu-id="c6629-232">**Passaggi per la risoluzione dei problemi:** Assicurati che i criteri di onboarding e offboarding non siano distribuiti nello stesso dispositivo contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c6629-232">**Troubleshooting steps:** Ensure that Onboarding and Offboarding policies are not deployed on the same device at same time.</span></span>

#### <a name="mobile-device-management-mdm-event-logs"></a><span data-ttu-id="c6629-233">Log eventi di Gestione dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="c6629-233">Mobile Device Management (MDM) event logs</span></span>

<span data-ttu-id="c6629-234">Visualizzare i registri eventi MDM per risolvere i problemi che potrebbero verificarsi durante l'onboarding:</span><span class="sxs-lookup"><span data-stu-id="c6629-234">View the MDM event logs to troubleshoot issues that might arise during onboarding:</span></span>

<span data-ttu-id="c6629-235">Nome registro: Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider</span><span class="sxs-lookup"><span data-stu-id="c6629-235">Log name: Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider</span></span>

<span data-ttu-id="c6629-236">Nome canale: Amministratore</span><span class="sxs-lookup"><span data-stu-id="c6629-236">Channel name: Admin</span></span>

<span data-ttu-id="c6629-237">ID</span><span class="sxs-lookup"><span data-stu-id="c6629-237">ID</span></span> | <span data-ttu-id="c6629-238">Gravità</span><span class="sxs-lookup"><span data-stu-id="c6629-238">Severity</span></span> | <span data-ttu-id="c6629-239">Descrizione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c6629-239">Event description</span></span> | <span data-ttu-id="c6629-240">Procedura di risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="c6629-240">Troubleshooting steps</span></span>
:---|:---|:---|:---
<span data-ttu-id="c6629-241">1819</span><span class="sxs-lookup"><span data-stu-id="c6629-241">1819</span></span> | <span data-ttu-id="c6629-242">Errore</span><span class="sxs-lookup"><span data-stu-id="c6629-242">Error</span></span> | <span data-ttu-id="c6629-243">CSP Di Microsoft Defender per endpoint: impossibile impostare il valore del nodo.</span><span class="sxs-lookup"><span data-stu-id="c6629-243">Microsoft Defender for Endpoint CSP: Failed to Set Node's Value.</span></span> <span data-ttu-id="c6629-244">NodeId: (%1), TokenName: (%2), Risultato: (%3).</span><span class="sxs-lookup"><span data-stu-id="c6629-244">NodeId: (%1), TokenName: (%2), Result: (%3).</span></span> | <span data-ttu-id="c6629-245">Scaricare [l'aggiornamento cumulativo per Windows 10, 1607](https://go.microsoft.com/fwlink/?linkid=829760).</span><span class="sxs-lookup"><span data-stu-id="c6629-245">Download the [Cumulative Update for Windows 10, 1607](https://go.microsoft.com/fwlink/?linkid=829760).</span></span>

## <a name="troubleshoot-onboarding-issues-on-the-device"></a><span data-ttu-id="c6629-246">Risolvere i problemi di onboarding nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="c6629-246">Troubleshoot onboarding issues on the device</span></span>

<span data-ttu-id="c6629-247">Se gli strumenti di distribuzione usati non indicano un errore nel processo di onboarding, ma i dispositivi non vengono ancora visualizzati nell'elenco dei dispositivi tra un'ora, passare attraverso gli argomenti di verifica seguenti per verificare se si è verificato un errore con l'agente Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c6629-247">If the deployment tools used does not indicate an error in the onboarding process, but devices are still not appearing in the devices list in an hour, go through the following verification topics to check if an error occurred with the Microsoft Defender for Endpoint agent.</span></span>

- [<span data-ttu-id="c6629-248">Visualizzare gli errori di onboarding degli agenti nel registro eventi del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c6629-248">View agent onboarding errors in the device event log</span></span>](#view-agent-onboarding-errors-in-the-device-event-log)
- [<span data-ttu-id="c6629-249">Verificare che il servizio dati di diagnostica sia abilitato</span><span class="sxs-lookup"><span data-stu-id="c6629-249">Ensure the diagnostic data service is enabled</span></span>](#ensure-the-diagnostics-service-is-enabled)
- [<span data-ttu-id="c6629-250">Verificare che il servizio sia impostato per l'avvio</span><span class="sxs-lookup"><span data-stu-id="c6629-250">Ensure the service is set to start</span></span>](#ensure-the-service-is-set-to-start)
- [<span data-ttu-id="c6629-251">Verificare che il dispositivo abbia una connessione Internet</span><span class="sxs-lookup"><span data-stu-id="c6629-251">Ensure the device has an Internet connection</span></span>](#ensure-the-device-has-an-internet-connection)
- [<span data-ttu-id="c6629-252">Verificare che Antivirus Microsoft Defender non sia disabilitato da un criterio</span><span class="sxs-lookup"><span data-stu-id="c6629-252">Ensure that Microsoft Defender Antivirus is not disabled by a policy</span></span>](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

### <a name="view-agent-onboarding-errors-in-the-device-event-log"></a><span data-ttu-id="c6629-253">Visualizzare gli errori di onboarding degli agenti nel registro eventi del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c6629-253">View agent onboarding errors in the device event log</span></span>

1. <span data-ttu-id="c6629-254">Fare **clic sul pulsante Start,** digitare **Visualizzatore** eventi e premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="c6629-254">Click **Start**, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="c6629-255">Nel riquadro **Visualizzatore eventi (locale),** espandere **Registri applicazioni** e servizi  >  **Microsoft**  >  **Windows**  >  **SENSE**.</span><span class="sxs-lookup"><span data-stu-id="c6629-255">In the **Event Viewer (Local)** pane, expand **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c6629-256">SENSE è il nome interno usato per fare riferimento al sensore comportamentale che alimenta Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c6629-256">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="c6629-257">Selezionare **Operativo** per caricare il registro.</span><span class="sxs-lookup"><span data-stu-id="c6629-257">Select **Operational** to load the log.</span></span>

4. <span data-ttu-id="c6629-258">Nel riquadro **Azioni** fare clic su **Filtra registro corrente.**</span><span class="sxs-lookup"><span data-stu-id="c6629-258">In the **Action** pane, click **Filter Current log**.</span></span>

5. <span data-ttu-id="c6629-259">Nella scheda **Filtro,** in **Livello evento:** selezionare **Critico,** **Avviso** ed **Errore** e fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="c6629-259">On the **Filter** tab, under **Event level:** select **Critical**, **Warning**, and **Error**, and click **OK**.</span></span>

   ![Immagine del filtro del registro del Visualizzatore eventi](images/filter-log.png)

6. <span data-ttu-id="c6629-261">Gli eventi che possono indicare problemi verranno visualizzati nel **riquadro** Operativo.</span><span class="sxs-lookup"><span data-stu-id="c6629-261">Events which can indicate issues will appear in the **Operational** pane.</span></span> <span data-ttu-id="c6629-262">È possibile tentare di risolverli in base alle soluzioni nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="c6629-262">You can attempt to troubleshoot them based on the solutions in the following table:</span></span>

<span data-ttu-id="c6629-263">ID evento</span><span class="sxs-lookup"><span data-stu-id="c6629-263">Event ID</span></span> | <span data-ttu-id="c6629-264">Messaggio</span><span class="sxs-lookup"><span data-stu-id="c6629-264">Message</span></span> | <span data-ttu-id="c6629-265">Passaggi di risoluzione</span><span class="sxs-lookup"><span data-stu-id="c6629-265">Resolution steps</span></span>
:---:|:---|:---
 `5` | <span data-ttu-id="c6629-266">Microsoft Defender for Endpoint service failed to connect to the server at _variable_</span><span class="sxs-lookup"><span data-stu-id="c6629-266">Microsoft Defender for Endpoint service failed to connect to the server at _variable_</span></span> | <span data-ttu-id="c6629-267">[Verificare che il dispositivo abbia accesso a Internet](#ensure-the-device-has-an-internet-connection).</span><span class="sxs-lookup"><span data-stu-id="c6629-267">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection).</span></span>
 `6` | <span data-ttu-id="c6629-268">Il servizio Microsoft Defender for Endpoint non è stato onboarding e non sono stati trovati parametri di onboarding.</span><span class="sxs-lookup"><span data-stu-id="c6629-268">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span> <span data-ttu-id="c6629-269">Codice errore: _variabile_</span><span class="sxs-lookup"><span data-stu-id="c6629-269">Failure code: _variable_</span></span> | <span data-ttu-id="c6629-270">[Eseguire di nuovo lo script di onboarding.](configure-endpoints-script.md)</span><span class="sxs-lookup"><span data-stu-id="c6629-270">[Run the onboarding script again](configure-endpoints-script.md).</span></span>
 `7` | <span data-ttu-id="c6629-271">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span><span class="sxs-lookup"><span data-stu-id="c6629-271">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="c6629-272">Codice errore: _variabile_</span><span class="sxs-lookup"><span data-stu-id="c6629-272">Failure code: _variable_</span></span> | <span data-ttu-id="c6629-273">[Assicurati che il dispositivo abbia accesso a Internet,](#ensure-the-device-has-an-internet-connection)quindi esegui di nuovo l'intero processo di onboarding.</span><span class="sxs-lookup"><span data-stu-id="c6629-273">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection), then run the entire onboarding process again.</span></span>
 `9` | <span data-ttu-id="c6629-274">Microsoft Defender for Endpoint service failed to change its start type.</span><span class="sxs-lookup"><span data-stu-id="c6629-274">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="c6629-275">Codice errore: variabile</span><span class="sxs-lookup"><span data-stu-id="c6629-275">Failure code: variable</span></span> | <span data-ttu-id="c6629-276">Se l'evento si è verificato durante l'onboarding, riavviare e riprovare a eseguire lo script di onboarding.</span><span class="sxs-lookup"><span data-stu-id="c6629-276">If the event happened during onboarding, reboot and re-attempt running the onboarding script.</span></span> <span data-ttu-id="c6629-277">Per ulteriori informazioni, vedere Eseguire di nuovo lo [script di onboarding.](configure-endpoints-script.md)</span><span class="sxs-lookup"><span data-stu-id="c6629-277">For more information, see [Run the onboarding script again](configure-endpoints-script.md).</span></span> <br><br><span data-ttu-id="c6629-278">Se l'evento si è verificato durante l'offboarding, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="c6629-278">If the event happened during offboarding, contact support.</span></span>
`10` | <span data-ttu-id="c6629-279">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span><span class="sxs-lookup"><span data-stu-id="c6629-279">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="c6629-280">Codice errore: variabile</span><span class="sxs-lookup"><span data-stu-id="c6629-280">Failure code: variable</span></span> | <span data-ttu-id="c6629-281">Se l'evento si è verificato durante l'onboarding, riprovare a eseguire lo script di onboarding.</span><span class="sxs-lookup"><span data-stu-id="c6629-281">If the event happened during onboarding, re-attempt running the onboarding script.</span></span> <span data-ttu-id="c6629-282">Per ulteriori informazioni, vedere Eseguire di nuovo lo [script di onboarding.](configure-endpoints-script.md)</span><span class="sxs-lookup"><span data-stu-id="c6629-282">For more information, see [Run the onboarding script again](configure-endpoints-script.md).</span></span> <br><br><span data-ttu-id="c6629-283">Se il problema persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="c6629-283">If the problem persists, contact support.</span></span>
`15` | <span data-ttu-id="c6629-284">Microsoft Defender for Endpoint non può avviare il canale di comando con URL: _variabile_</span><span class="sxs-lookup"><span data-stu-id="c6629-284">Microsoft Defender for Endpoint cannot start command channel with URL: _variable_</span></span> | <span data-ttu-id="c6629-285">[Verificare che il dispositivo abbia accesso a Internet](#ensure-the-device-has-an-internet-connection).</span><span class="sxs-lookup"><span data-stu-id="c6629-285">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection).</span></span>
`17` | <span data-ttu-id="c6629-286">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span><span class="sxs-lookup"><span data-stu-id="c6629-286">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="c6629-287">Codice errore: variabile</span><span class="sxs-lookup"><span data-stu-id="c6629-287">Failure code: variable</span></span> | <span data-ttu-id="c6629-288">[Eseguire di nuovo lo script di onboarding.](configure-endpoints-script.md)</span><span class="sxs-lookup"><span data-stu-id="c6629-288">[Run the onboarding script again](configure-endpoints-script.md).</span></span> <span data-ttu-id="c6629-289">Se il problema persiste, contattare il supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="c6629-289">If the problem persists, contact support.</span></span>
`25` | <span data-ttu-id="c6629-290">Il servizio Microsoft Defender for Endpoint non è riuscito a reimpostare lo stato di integrità nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="c6629-290">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="c6629-291">Codice errore: _variabile_</span><span class="sxs-lookup"><span data-stu-id="c6629-291">Failure code: _variable_</span></span> | <span data-ttu-id="c6629-292">Contattare il supporto.</span><span class="sxs-lookup"><span data-stu-id="c6629-292">Contact support.</span></span>
`27` | <span data-ttu-id="c6629-293">Impossibile abilitare la modalità Microsoft Defender for Endpoint in Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="c6629-293">Failed to enable Microsoft Defender for Endpoint mode in Windows Defender.</span></span> <span data-ttu-id="c6629-294">Processo di onboarding non riuscito.</span><span class="sxs-lookup"><span data-stu-id="c6629-294">Onboarding process failed.</span></span> <span data-ttu-id="c6629-295">Codice errore: variabile</span><span class="sxs-lookup"><span data-stu-id="c6629-295">Failure code: variable</span></span> | <span data-ttu-id="c6629-296">Contattare il supporto.</span><span class="sxs-lookup"><span data-stu-id="c6629-296">Contact support.</span></span>
`29` | <span data-ttu-id="c6629-297">Impossibile leggere i parametri di offboarding.</span><span class="sxs-lookup"><span data-stu-id="c6629-297">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="c6629-298">Tipo di errore: %1, Codice errore: %2, Descrizione: %3</span><span class="sxs-lookup"><span data-stu-id="c6629-298">Error type: %1, Error code: %2, Description: %3</span></span> | <span data-ttu-id="c6629-299">Assicurati che il dispositivo abbia accesso a Internet, quindi esegui di nuovo l'intero processo di offboarding.</span><span class="sxs-lookup"><span data-stu-id="c6629-299">Ensure the device has Internet access, then run the entire offboarding process again.</span></span>
`30` | <span data-ttu-id="c6629-300">Impossibile disabilitare la modalità $(build.sense.productDisplayName) in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c6629-300">Failed to disable $(build.sense.productDisplayName) mode in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c6629-301">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="c6629-301">Failure code: %1</span></span> | <span data-ttu-id="c6629-302">Contattare il supporto.</span><span class="sxs-lookup"><span data-stu-id="c6629-302">Contact support.</span></span>
`32` | <span data-ttu-id="c6629-303">$(build.sense.productDisplayName) service failed to request to stop itself after offboarding process.</span><span class="sxs-lookup"><span data-stu-id="c6629-303">$(build.sense.productDisplayName) service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="c6629-304">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="c6629-304">Failure code: %1</span></span> | <span data-ttu-id="c6629-305">Verificare che il tipo di avvio del servizio sia manuale e riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c6629-305">Verify that the service start type is manual and reboot the device.</span></span>
`55` | <span data-ttu-id="c6629-306">Impossibile creare l'autologger Secure ETW.</span><span class="sxs-lookup"><span data-stu-id="c6629-306">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="c6629-307">Codice errore: %1</span><span class="sxs-lookup"><span data-stu-id="c6629-307">Failure code: %1</span></span> | <span data-ttu-id="c6629-308">Riavviare il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c6629-308">Reboot the device.</span></span>
`63` | <span data-ttu-id="c6629-309">Aggiornamento del tipo di avvio del servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="c6629-309">Updating the start type of external service.</span></span> <span data-ttu-id="c6629-310">Nome: %1, tipo di avvio effettivo: %2, tipo di avvio previsto: %3, codice di uscita: %4</span><span class="sxs-lookup"><span data-stu-id="c6629-310">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span> | <span data-ttu-id="c6629-311">Identificare la causa delle modifiche nel tipo di avvio del servizio menzionato.</span><span class="sxs-lookup"><span data-stu-id="c6629-311">Identify what is causing changes in start type of mentioned service.</span></span> <span data-ttu-id="c6629-312">Se il codice di uscita non è 0, correggere manualmente il tipo di avvio al tipo di avvio previsto.</span><span class="sxs-lookup"><span data-stu-id="c6629-312">If the exit code is not 0, fix the start type manually to expected start type.</span></span>
`64` | <span data-ttu-id="c6629-313">Avvio del servizio esterno arrestato.</span><span class="sxs-lookup"><span data-stu-id="c6629-313">Starting stopped external service.</span></span> <span data-ttu-id="c6629-314">Nome: %1, codice di uscita: %2</span><span class="sxs-lookup"><span data-stu-id="c6629-314">Name: %1, exit code: %2</span></span> | <span data-ttu-id="c6629-315">Contattare il supporto se l'evento continua a comparire.</span><span class="sxs-lookup"><span data-stu-id="c6629-315">Contact support if the event keeps re-appearing.</span></span>
`68` | <span data-ttu-id="c6629-316">Il tipo di avvio del servizio è imprevisto.</span><span class="sxs-lookup"><span data-stu-id="c6629-316">The start type of the service is unexpected.</span></span> <span data-ttu-id="c6629-317">Nome servizio: %1, tipo di avvio effettivo: %2, tipo di avvio previsto: %3</span><span class="sxs-lookup"><span data-stu-id="c6629-317">Service name: %1, actual start type: %2, expected start type: %3</span></span> | <span data-ttu-id="c6629-318">Identificare la causa delle modifiche nel tipo di avvio.</span><span class="sxs-lookup"><span data-stu-id="c6629-318">Identify what is causing changes in start type.</span></span> <span data-ttu-id="c6629-319">Correggere il tipo di avvio del servizio menzionato.</span><span class="sxs-lookup"><span data-stu-id="c6629-319">Fix mentioned service start type.</span></span>
`69` | <span data-ttu-id="c6629-320">Il servizio è stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="c6629-320">The service is stopped.</span></span> <span data-ttu-id="c6629-321">Nome servizio: %1</span><span class="sxs-lookup"><span data-stu-id="c6629-321">Service name: %1</span></span> | <span data-ttu-id="c6629-322">Avviare il servizio menzionato.</span><span class="sxs-lookup"><span data-stu-id="c6629-322">Start the mentioned service.</span></span> <span data-ttu-id="c6629-323">Contattare il supporto se persiste.</span><span class="sxs-lookup"><span data-stu-id="c6629-323">Contact support if persists.</span></span>

<br />

<span data-ttu-id="c6629-324">Nel dispositivo sono presenti componenti aggiuntivi da cui dipende il corretto funzionamento dell'agente di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c6629-324">There are additional components on the device that the Microsoft Defender for Endpoint agent depends on to function properly.</span></span> <span data-ttu-id="c6629-325">Se nel registro eventi dell'agente di Microsoft Defender for Endpoint non sono presenti errori correlati all'onboarding, procedere con la procedura seguente per verificare che i componenti aggiuntivi siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="c6629-325">If there are no onboarding related errors in the Microsoft Defender for Endpoint agent event log, proceed with the following steps to ensure that the additional components are configured correctly.</span></span>

<span id="ensure-the-diagnostics-service-is-enabled" />

### <a name="ensure-the-diagnostic-data-service-is-enabled"></a><span data-ttu-id="c6629-326">Verificare che il servizio dati di diagnostica sia abilitato</span><span class="sxs-lookup"><span data-stu-id="c6629-326">Ensure the diagnostic data service is enabled</span></span>

<span data-ttu-id="c6629-327">Se i dispositivi non segnalano correttamente, potrebbe essere necessario verificare che il servizio dati di diagnostica di Windows 10 sia impostato per l'avvio automatico e sia in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c6629-327">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the device.</span></span> <span data-ttu-id="c6629-328">Il servizio potrebbe essere stato disabilitato da altri programmi o modifiche alla configurazione utente.</span><span class="sxs-lookup"><span data-stu-id="c6629-328">The service might have been disabled by other programs or user configuration changes.</span></span>

<span data-ttu-id="c6629-329">Prima di tutto, è necessario verificare che il servizio sia impostato per l'avvio automatico all'avvio di Windows, quindi verificare che il servizio sia attualmente in esecuzione e avviarlo in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="c6629-329">First, you should check that the service is set to start automatically when Windows starts, then you should check that the service is currently running (and start it if it isn't).</span></span>

### <a name="ensure-the-service-is-set-to-start"></a><span data-ttu-id="c6629-330">Verificare che il servizio sia impostato per l'avvio</span><span class="sxs-lookup"><span data-stu-id="c6629-330">Ensure the service is set to start</span></span>

<span data-ttu-id="c6629-331">**Utilizzare la riga di comando per controllare il tipo** Windows 10 di avvio del servizio dati di diagnostica:</span><span class="sxs-lookup"><span data-stu-id="c6629-331">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="c6629-332">Apri un prompt della riga di comando con privilegi elevati nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c6629-332">Open an elevated command-line prompt on the device:</span></span>

   <span data-ttu-id="c6629-333">a.</span><span class="sxs-lookup"><span data-stu-id="c6629-333">a.</span></span> <span data-ttu-id="c6629-334">Fare **clic sul pulsante Start,** digitare **cmd** e premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="c6629-334">Click **Start**, type **cmd**, and press **Enter**.</span></span>

   <span data-ttu-id="c6629-335">b.</span><span class="sxs-lookup"><span data-stu-id="c6629-335">b.</span></span> <span data-ttu-id="c6629-336">Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c6629-336">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="c6629-337">Immettere il comando seguente e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="c6629-337">Enter the following command, and press **Enter**:</span></span>

   ```text
   sc qc diagtrack
   ```

   <span data-ttu-id="c6629-338">Se il servizio è abilitato, il risultato dovrebbe essere simile allo screenshot seguente:</span><span class="sxs-lookup"><span data-stu-id="c6629-338">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Risultato del comando sc query per diagtrack](images/windefatp-sc-qc-diagtrack.png)

   <span data-ttu-id="c6629-340">Se la proprietà non è impostata su , sarà necessario impostare `START_TYPE` `AUTO_START` l'avvio automatico del servizio.</span><span class="sxs-lookup"><span data-stu-id="c6629-340">If the `START_TYPE` is not set to `AUTO_START`, then you'll need to set the service to automatically start.</span></span>

<span data-ttu-id="c6629-341">**Utilizzare la riga di comando per impostare l'avvio Windows 10 servizio dati di diagnostica:**</span><span class="sxs-lookup"><span data-stu-id="c6629-341">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1. <span data-ttu-id="c6629-342">Apri un prompt della riga di comando con privilegi elevati nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c6629-342">Open an elevated command-line prompt on the device:</span></span>

   <span data-ttu-id="c6629-343">a.</span><span class="sxs-lookup"><span data-stu-id="c6629-343">a.</span></span> <span data-ttu-id="c6629-344">Fare **clic sul pulsante Start,** digitare **cmd** e premere **INVIO.**</span><span class="sxs-lookup"><span data-stu-id="c6629-344">Click **Start**, type **cmd**, and press **Enter**.</span></span>

   <span data-ttu-id="c6629-345">b.</span><span class="sxs-lookup"><span data-stu-id="c6629-345">b.</span></span> <span data-ttu-id="c6629-346">Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c6629-346">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="c6629-347">Immettere il comando seguente e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="c6629-347">Enter the following command, and press **Enter**:</span></span>

   ```text
   sc config diagtrack start=auto
   ```

3. <span data-ttu-id="c6629-348">Viene visualizzato un messaggio di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c6629-348">A success message is displayed.</span></span> <span data-ttu-id="c6629-349">Verificare la modifica immettendo il comando seguente e premere **INVIO:**</span><span class="sxs-lookup"><span data-stu-id="c6629-349">Verify the change by entering the following command, and press **Enter**:</span></span>

   ```text
   sc qc diagtrack
   ```

4. <span data-ttu-id="c6629-350">Avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="c6629-350">Start the service.</span></span>

   <span data-ttu-id="c6629-351">a.</span><span class="sxs-lookup"><span data-stu-id="c6629-351">a.</span></span> <span data-ttu-id="c6629-352">Al prompt dei comandi digitare il comando seguente e premere **INVIO:**</span><span class="sxs-lookup"><span data-stu-id="c6629-352">In the command prompt, type the following command and press **Enter**:</span></span>

   ```text
   sc start diagtrack
   ```

### <a name="ensure-the-device-has-an-internet-connection"></a><span data-ttu-id="c6629-353">Verificare che il dispositivo abbia una connessione Internet</span><span class="sxs-lookup"><span data-stu-id="c6629-353">Ensure the device has an Internet connection</span></span>

<span data-ttu-id="c6629-354">Il sensore Microsoft Defender per endpoint richiede che Microsoft Windows HTTP (WinHTTP) segnali dati dei sensori e comunichi con il servizio Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="c6629-354">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="c6629-355">WinHTTP è indipendente dalle impostazioni del proxy di esplorazione Internet e da altre applicazioni di contesto utente e deve essere in grado di rilevare i server proxy disponibili nell'ambiente specifico.</span><span class="sxs-lookup"><span data-stu-id="c6629-355">WinHTTP is independent of the Internet browsing proxy settings and other user context applications and must be able to detect the proxy servers that are available in your particular environment.</span></span>

<span data-ttu-id="c6629-356">Per verificare che il sensore abbia la connettività del servizio, seguire i passaggi descritti nell'argomento [Verify client connectivity to Microsoft Defender for Endpoint service URLs.](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</span><span class="sxs-lookup"><span data-stu-id="c6629-356">To ensure that sensor has service connectivity, follow the steps described in the [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls) topic.</span></span>

<span data-ttu-id="c6629-357">Se la verifica ha esito negativo e l'ambiente utilizza un proxy per connettersi a Internet, seguire i passaggi descritti nell'argomento [Configure proxy and Internet connectivity settings.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="c6629-357">If the verification fails and your environment is using a proxy to connect to the Internet, then follow the steps described in [Configure proxy and Internet connectivity settings](configure-proxy-internet.md) topic.</span></span>

### <a name="ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy"></a><span data-ttu-id="c6629-358">Verificare che Antivirus Microsoft Defender non sia disabilitato da un criterio</span><span class="sxs-lookup"><span data-stu-id="c6629-358">Ensure that Microsoft Defender Antivirus is not disabled by a policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6629-359">Quanto segue si applica  solo ai dispositivi che non hanno ancora ricevuto l'aggiornamento di agosto 2020 (versione 4.18.2007.8) a Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c6629-359">The following only applies to devices that have **not** yet received the August 2020 (version 4.18.2007.8) update to Microsoft Defender Antivirus.</span></span>
>
> <span data-ttu-id="c6629-360">L'aggiornamento garantisce che Antivirus Microsoft Defender non possa essere disattivato nei dispositivi client tramite i criteri di sistema.</span><span class="sxs-lookup"><span data-stu-id="c6629-360">The update ensures that Microsoft Defender Antivirus cannot be turned off on client devices via system policy.</span></span>

<span data-ttu-id="c6629-361">**Problema:** Il servizio Microsoft Defender for Endpoint non viene avviato dopo l'onboarding.</span><span class="sxs-lookup"><span data-stu-id="c6629-361">**Problem**: The Microsoft Defender for Endpoint service does not start after onboarding.</span></span>

<span data-ttu-id="c6629-362">**Sintomo:** l'onboarding viene completato correttamente, ma viene visualizzato l'errore 577 o l'errore 1058 quando si tenta di avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="c6629-362">**Symptom**: Onboarding successfully completes, but you see error 577 or error 1058 when trying to start the service.</span></span>

<span data-ttu-id="c6629-363">**Soluzione:** se i dispositivi eseguono un client antimalware di terze parti, l'agente Microsoft Defender for Endpoint deve essere abilitato con il driver Antimalware ad avvio anticipato (ELAM).</span><span class="sxs-lookup"><span data-stu-id="c6629-363">**Solution**: If your devices are running a third-party antimalware client, the Microsoft Defender for Endpoint agent needs the Early Launch Antimalware (ELAM) driver to be enabled.</span></span> <span data-ttu-id="c6629-364">È necessario assicurarsi che non sia disattivato da un criterio di sistema.</span><span class="sxs-lookup"><span data-stu-id="c6629-364">You must ensure that it's not turned off by a system policy.</span></span>

- <span data-ttu-id="c6629-365">A seconda dello strumento utilizzato per implementare i criteri, è necessario verificare che i criteri Windows Defender seguenti siano deselezionati:</span><span class="sxs-lookup"><span data-stu-id="c6629-365">Depending on the tool that you use to implement policies, you'll need to verify that the following Windows Defender policies are cleared:</span></span>

  - <span data-ttu-id="c6629-366">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="c6629-366">DisableAntiSpyware</span></span>
  - <span data-ttu-id="c6629-367">DisableAntiVirus</span><span class="sxs-lookup"><span data-stu-id="c6629-367">DisableAntiVirus</span></span>

  <span data-ttu-id="c6629-368">Ad esempio, in Criteri di gruppo non dovrebbero essere presenti voci come i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="c6629-368">For example, in Group Policy there should be no entries such as the following values:</span></span>

  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiSpyware"/></Key>`
  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiVirus"/></Key>`

> [!IMPORTANT]
> <span data-ttu-id="c6629-369">L'impostazione non è più disponibile e verrà ignorata in tutti i dispositivi client, a partire dall'aggiornamento di agosto `disableAntiSpyware` 2020 (versione 4.18.2007.8) a Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c6629-369">The `disableAntiSpyware` setting is discontinued and will be ignored on all client devices, as of the August 2020 (version 4.18.2007.8) update to Microsoft Defender Antivirus.</span></span>

- <span data-ttu-id="c6629-370">Dopo aver deselezionato il criterio, eseguire di nuovo i passaggi di onboarding.</span><span class="sxs-lookup"><span data-stu-id="c6629-370">After clearing the policy, run the onboarding steps again.</span></span>

- <span data-ttu-id="c6629-371">È inoltre possibile controllare i valori precedenti della chiave del Registro di sistema per verificare che il criterio sia disabilitato aprendo la chiave del Registro di sistema `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` .</span><span class="sxs-lookup"><span data-stu-id="c6629-371">You can also check the previous registry key values to verify that the policy is disabled, by opening the registry key `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.</span></span>

    ![Immagine della chiave del Registro di sistema per Antivirus Microsoft Defender](images/atp-disableantispyware-regkey.png)

   > [!NOTE]
   > <span data-ttu-id="c6629-373">Tutti Windows Defender servizi (wdboot, wdfilter, wdnisdrv, wdnissvc e windefend) devono essere nello stato predefinito.</span><span class="sxs-lookup"><span data-stu-id="c6629-373">All Windows Defender services (wdboot, wdfilter, wdnisdrv, wdnissvc, and windefend) should be in their default state.</span></span> <span data-ttu-id="c6629-374">La modifica dell'avvio di questi servizi non è supportata e potrebbe forzare l'immagine del sistema.</span><span class="sxs-lookup"><span data-stu-id="c6629-374">Changing the startup of these services is unsupported and may force you to reimage your system.</span></span>
   >
   > <span data-ttu-id="c6629-375">Configurazioni predefinite di esempio per WdBoot e WdFilter:</span><span class="sxs-lookup"><span data-stu-id="c6629-375">Example default configurations for WdBoot and WdFilter:</span></span>
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdBoot"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdFilter"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`

## <a name="troubleshoot-onboarding-issues-on-a-server"></a><span data-ttu-id="c6629-376">Risolvere i problemi di onboarding in un server</span><span class="sxs-lookup"><span data-stu-id="c6629-376">Troubleshoot onboarding issues on a server</span></span>

>[!NOTE]
><span data-ttu-id="c6629-377">Le indicazioni per la risoluzione dei problemi seguenti sono applicabili solo Windows Server 2016 e inferiori.</span><span class="sxs-lookup"><span data-stu-id="c6629-377">The following troubleshooting guidance is only applicable for Windows Server 2016 and lower.</span></span>

<span data-ttu-id="c6629-378">Se si verificano problemi durante l'onboarding di un server, eseguire la procedura di verifica seguente per risolvere i possibili problemi.</span><span class="sxs-lookup"><span data-stu-id="c6629-378">If you encounter issues while onboarding a server, go through the following verification steps to address possible issues.</span></span>

- [<span data-ttu-id="c6629-379">Verificare Microsoft Monitoring Agent (MMA) sia installato e configurato per segnalare i dati del sensore al servizio</span><span class="sxs-lookup"><span data-stu-id="c6629-379">Ensure Microsoft Monitoring Agent (MMA) is installed and configured to report sensor data to the service</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="c6629-380">Verificare che le impostazioni del proxy del server e della connettività Internet siano configurate correttamente</span><span class="sxs-lookup"><span data-stu-id="c6629-380">Ensure that the server proxy and Internet connectivity settings are configured properly</span></span>](configure-server-endpoints.md)

<span data-ttu-id="c6629-381">Potrebbe inoltre essere necessario controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c6629-381">You might also need to check the following:</span></span>

- <span data-ttu-id="c6629-382">Verificare che sia in esecuzione Microsoft Defender for Endpoint Service nella **scheda Processi** in **Task Manager.**</span><span class="sxs-lookup"><span data-stu-id="c6629-382">Check that there is a Microsoft Defender for Endpoint Service running in the **Processes** tab in **Task Manager**.</span></span> <span data-ttu-id="c6629-383">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c6629-383">For example:</span></span>

    ![Immagine della visualizzazione processo con Microsoft Defender for Endpoint Service in esecuzione](images/atp-task-manager.png)

- <span data-ttu-id="c6629-385">Controllare **Gestione operazioni** applicazioni e registri servizi del Visualizzatore eventi per verificare se sono presenti  >    >   errori.</span><span class="sxs-lookup"><span data-stu-id="c6629-385">Check **Event Viewer** > **Applications and Services Logs** > **Operation Manager** to see if there are any errors.</span></span>

- <span data-ttu-id="c6629-386">In **Servizi** verificare se il **Microsoft Monitoring Agent** è in esecuzione nel server.</span><span class="sxs-lookup"><span data-stu-id="c6629-386">In **Services**, check if the **Microsoft Monitoring Agent** is running on the server.</span></span> <span data-ttu-id="c6629-387">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="c6629-387">For example,</span></span>

    ![Immagine dei servizi](images/atp-services.png)

- <span data-ttu-id="c6629-389">In **Microsoft Monitoring Agent**  >  **Azure Log Analytics (OMS)** controllare le aree di lavoro e verificare che lo stato sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c6629-389">In **Microsoft Monitoring Agent** > **Azure Log Analytics (OMS)**, check the Workspaces and verify that the status is running.</span></span>

    ![Immagine di Microsoft Monitoring Agent proprietà](images/atp-mma-properties.png)

- <span data-ttu-id="c6629-391">Verifica che i dispositivi si riflettano **nell'elenco Dispositivi** nel portale.</span><span class="sxs-lookup"><span data-stu-id="c6629-391">Check to see that devices are reflected in the **Devices list** in the portal.</span></span>

## <a name="confirming-onboarding-of-newly-built-devices"></a><span data-ttu-id="c6629-392">Conferma dell'onboarding dei dispositivi appena creati</span><span class="sxs-lookup"><span data-stu-id="c6629-392">Confirming onboarding of newly built devices</span></span>

<span data-ttu-id="c6629-393">Possono verificarsi casi in cui l'onboarding viene distribuito in un dispositivo appena creato ma non completato.</span><span class="sxs-lookup"><span data-stu-id="c6629-393">There may be instances when onboarding is deployed on a newly built device but not completed.</span></span>

<span data-ttu-id="c6629-394">I passaggi seguenti forniscono indicazioni per lo scenario seguente:</span><span class="sxs-lookup"><span data-stu-id="c6629-394">The steps below provide guidance for the following scenario:</span></span>

- <span data-ttu-id="c6629-395">Il pacchetto di onboarding viene distribuito ai dispositivi appena creati</span><span class="sxs-lookup"><span data-stu-id="c6629-395">Onboarding package is deployed to newly built devices</span></span>
- <span data-ttu-id="c6629-396">Sensor does not start because the Out-of-box experience (OOBE) or first user logon has not been completed</span><span class="sxs-lookup"><span data-stu-id="c6629-396">Sensor does not start because the Out-of-box experience (OOBE) or first user logon has not been completed</span></span>
- <span data-ttu-id="c6629-397">Il dispositivo viene disattivato o riavviato prima che l'utente finale esegua il primo accesso</span><span class="sxs-lookup"><span data-stu-id="c6629-397">Device is turned off or restarted before the end user performs a first logon</span></span>
- <span data-ttu-id="c6629-398">In questo scenario, il servizio SENSE non verrà avviato automaticamente anche se il pacchetto di onboarding è stato distribuito</span><span class="sxs-lookup"><span data-stu-id="c6629-398">In this scenario, the SENSE service will not start automatically even though onboarding package was deployed</span></span>

<div class="alert"><span data-ttu-id="c6629-399"><b>NOTA:</b> L'accesso utente dopo la configurazione non è più necessario per l'avvio del servizio SENSE nelle versioni di Windows seguenti o più recenti: Windows 10, versione 1809 o Windows Server 2019 con aggiornamento cumulativo del 22 aprile [2021](https://support.microsoft.com/kb/5001384) </span><span class="sxs-lookup"><span data-stu-id="c6629-399"><b>NOTE:</b> User Logon after OOBE is no longer required for SENSE service to start on the following or more recent Windows versions: Windows 10, version 1809 or Windows Server 2019 with [April 22 2021 update rollup](https://support.microsoft.com/kb/5001384) </span></span></br> <span data-ttu-id="c6629-400">Windows 10, versione 1909 con aggiornamento cumulativo [di aprile 2021](https://support.microsoft.com/kb/5001396) </span><span class="sxs-lookup"><span data-stu-id="c6629-400">Windows 10, version 1909 with [April 2021 update rollup](https://support.microsoft.com/kb/5001396) </span></span></br> <span data-ttu-id="c6629-401">Windows 10, versione 2004/20H2 con aggiornamento [cumulativo del 28 aprile 2021](https://support.microsoft.com/kb/5001391) </span><span class="sxs-lookup"><span data-stu-id="c6629-401">Windows 10, version 2004/20H2 with [April 28 2021 update rollup](https://support.microsoft.com/kb/5001391) </span></span></div> 
<br></br>
> [!NOTE]
> <span data-ttu-id="c6629-402">I passaggi seguenti sono rilevanti solo quando si usa Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="c6629-402">The following steps are only relevant when using Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="c6629-403">Per altri dettagli sull'onboarding Microsoft Endpoint Configuration Manager, vedi [Microsoft Defender for Endpoint.](/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="c6629-403">For more details about onboarding using Microsoft Endpoint Configuration Manager, see [Microsoft Defender for Endpoint](/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection).</span></span>

1. <span data-ttu-id="c6629-404">Creare un'applicazione in Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="c6629-404">Create an application in Microsoft Endpoint Configuration Manager.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione1](images/mecm-1.png)

2. <span data-ttu-id="c6629-406">Selezionare **Specificare manualmente le informazioni sull'applicazione.**</span><span class="sxs-lookup"><span data-stu-id="c6629-406">Select **Manually specify the application information**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione2](images/mecm-2.png)

3. <span data-ttu-id="c6629-408">Specificare le informazioni sull'applicazione, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-408">Specify information about the application, then select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione3](images/mecm-3.png)

4. <span data-ttu-id="c6629-410">Specificare le informazioni sul Software Center, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-410">Specify information about the software center, then select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione4](images/mecm-4.png)

5. <span data-ttu-id="c6629-412">In **Tipi di distribuzione** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c6629-412">In **Deployment types** select **Add**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione5](images/mecm-5.png)

6. <span data-ttu-id="c6629-414">Selezionare **Specificare manualmente le informazioni sul tipo di distribuzione,** quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-414">Select **Manually specify the deployment type information**, then select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione6](images/mecm-6.png)

7. <span data-ttu-id="c6629-416">Specificare le informazioni sul tipo di distribuzione, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-416">Specify information about the deployment type, then select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione7](images/mecm-7.png)

8. <span data-ttu-id="c6629-418">In **Programma**  >  **di installazione contenuto** specificare il comando: `net start sense` .</span><span class="sxs-lookup"><span data-stu-id="c6629-418">In **Content** > **Installation program** specify the command: `net start sense`.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione8](images/mecm-8.png)

9. <span data-ttu-id="c6629-420">In **Metodo di rilevamento** selezionare Configura regole per rilevare la presenza di questo tipo di **distribuzione,** quindi selezionare Aggiungi **clausola**.</span><span class="sxs-lookup"><span data-stu-id="c6629-420">In **Detection method**, select **Configure rules to detect the presence of this deployment type**, then select **Add Clause**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione9](images/mecm-9.png)

10. <span data-ttu-id="c6629-422">Specificare i dettagli della regola di rilevamento seguenti, quindi selezionare **OK:**</span><span class="sxs-lookup"><span data-stu-id="c6629-422">Specify the following detection rule details, then select **OK**:</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione10](images/mecm-10.png)

11. <span data-ttu-id="c6629-424">In **Metodo di rilevamento** selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6629-424">In **Detection method** select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione11](images/mecm-11.png)

12. <span data-ttu-id="c6629-426">In **Esperienza utente** specificare le informazioni seguenti, quindi selezionare **Avanti:**</span><span class="sxs-lookup"><span data-stu-id="c6629-426">In **User Experience**, specify the following information, then select **Next**:</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione12](images/mecm-12.png)

13. <span data-ttu-id="c6629-428">In **Requisiti** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-428">In **Requirements**, select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione13](images/mecm-13.png)

14. <span data-ttu-id="c6629-430">In **Dipendenze** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-430">In **Dependencies**, select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione14](images/mecm-14.png)

15. <span data-ttu-id="c6629-432">In **Riepilogo** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-432">In **Summary**, select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione15](images/mecm-15.png)

16. <span data-ttu-id="c6629-434">In **Completamento** selezionare **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="c6629-434">In **Completion**, select **Close**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione16](images/mecm-16.png)

17. <span data-ttu-id="c6629-436">In **Tipi di distribuzione** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-436">In **Deployment types**, select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione17](images/mecm-17.png)

18. <span data-ttu-id="c6629-438">In **Riepilogo** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-438">In **Summary**, select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione18](images/mecm-18.png)

    <span data-ttu-id="c6629-440">Viene quindi visualizzato lo stato: ![ Immagine Microsoft Endpoint Configuration Manager configurazione19](images/mecm-19.png)</span><span class="sxs-lookup"><span data-stu-id="c6629-440">The status is then displayed: ![Image of Microsoft Endpoint Configuration Manager configuration19](images/mecm-19.png)</span></span>

19. <span data-ttu-id="c6629-441">In **Completamento** selezionare **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="c6629-441">In **Completion**, select **Close**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione20](images/mecm-20.png)

20. <span data-ttu-id="c6629-443">È ora possibile distribuire l'applicazione facendo clic con il pulsante destro del mouse sull'app e scegliendo **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="c6629-443">You can now deploy the application by right-clicking the app and selecting **Deploy**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione21](images/mecm-21.png)

21. <span data-ttu-id="c6629-445">In **Generale seleziona** **Distribuisci automaticamente il contenuto per le dipendenze e** **Sfoglia.**</span><span class="sxs-lookup"><span data-stu-id="c6629-445">In **General** select **Automatically distribute content for dependencies** and **Browse**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione22](images/mecm-22.png)

22. <span data-ttu-id="c6629-447">In **Contenuto** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-447">In **Content** select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione23](images/mecm-23.png)

23. <span data-ttu-id="c6629-449">In **Impostazioni di distribuzione** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-449">In **Deployment settings**, select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione24](images/mecm-24.png)

24. <span data-ttu-id="c6629-451">In **Pianificazione selezionare** Il prima possibile dopo il tempo **disponibile,** quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-451">In **Scheduling** select **As soon as possible after the available time**, then select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione25](images/mecm-25.png)

25. <span data-ttu-id="c6629-453">In **Esperienza utente** seleziona Conferma modifiche alla scadenza o durante una finestra di manutenzione (richiede riavvii) e quindi seleziona **Avanti.** </span><span class="sxs-lookup"><span data-stu-id="c6629-453">In **User experience**, select **Commit changes at deadline or during a maintenance window (requires restarts)**, then select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione26](images/mecm-26.png)

26. <span data-ttu-id="c6629-455">In **Avvisi selezionare** **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6629-455">In **Alerts** select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione27](images/mecm-27.png)

27. <span data-ttu-id="c6629-457">In **Riepilogo** selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="c6629-457">In **Summary**, select **Next**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione28](images/mecm-28.png)

    <span data-ttu-id="c6629-459">Viene quindi visualizzato lo stato ![ Immagine Microsoft Endpoint Configuration Manager configurazione29](images/mecm-29.png)</span><span class="sxs-lookup"><span data-stu-id="c6629-459">The status is then displayed ![Image of Microsoft Endpoint Configuration Manager configuration29](images/mecm-29.png)</span></span>

28. <span data-ttu-id="c6629-460">In **Completamento** selezionare **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="c6629-460">In **Completion**, select **Close**.</span></span>

    ![Immagine della Microsoft Endpoint Configuration Manager configurazione30](images/mecm-30.png)


## <a name="related-topics"></a><span data-ttu-id="c6629-462">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c6629-462">Related topics</span></span>

- [<span data-ttu-id="c6629-463">Risolvere i problemi di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c6629-463">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-mdatp.md)
- [<span data-ttu-id="c6629-464">Eseguire l'onboarding dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="c6629-464">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="c6629-465">Configurare le impostazioni di connettività Proxy e Internet del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c6629-465">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
