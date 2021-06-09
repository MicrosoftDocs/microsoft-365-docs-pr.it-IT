---
title: Analizzare le entità nei dispositivi che usano la risposta in tempo reale in Microsoft Defender for Endpoint
description: Accedi a un dispositivo usando una connessione shell remota sicura per eseguire attività di indagine ed eseguire azioni di risposta immediate su un dispositivo in tempo reale.
keywords: remote, shell, connection, live, response, real-time, command, script, remediate, hunt, export, log, drop, download, file,
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
ms.openlocfilehash: d5e48f1e4f6bc2cfaa836d90e24f2ce8ba3f2114
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845331"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="60ad3-104">Analizzare le entità nei dispositivi che usano la risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="60ad3-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="60ad3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="60ad3-105">**Applies to:**</span></span>
- [<span data-ttu-id="60ad3-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="60ad3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="60ad3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60ad3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="60ad3-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="60ad3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="60ad3-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="60ad3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="60ad3-110">La risposta in tempo reale consente ai team delle operazioni di sicurezza di accedere istantaneamente a un dispositivo (noto anche come computer) utilizzando una connessione shell remota.</span><span class="sxs-lookup"><span data-stu-id="60ad3-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="60ad3-111">In questo modo è possibile eseguire un lavoro di indagine approfondito e intraprendere azioni di risposta immediate per contenere prontamente le minacce identificate, in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="60ad3-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="60ad3-112">La risposta in tempo reale è progettata per migliorare le indagini consentendo al team delle operazioni di sicurezza di raccogliere dati forensi, eseguire script, inviare entità sospette per l'analisi, correggere le minacce e cercare in modo proattivo minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="60ad3-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="60ad3-113">Con la risposta in tempo reale, gli analisti possono eseguire tutte le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="60ad3-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="60ad3-114">Esegui comandi di base e avanzati per eseguire attività di indagine su un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="60ad3-115">Scaricare file come esempi di malware e risultati degli script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60ad3-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="60ad3-116">Scaricare i file in background (nuovo!).</span><span class="sxs-lookup"><span data-stu-id="60ad3-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="60ad3-117">Upload uno script di PowerShell o un file eseguibile nella raccolta ed eseguirlo in un dispositivo a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="60ad3-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="60ad3-118">Eseguire o annullare azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="60ad3-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="60ad3-119">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="60ad3-119">Before you begin</span></span>

<span data-ttu-id="60ad3-120">Prima di poter avviare una sessione su un dispositivo, assicurati di soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="60ad3-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="60ad3-121">**Verificare che sia in esecuzione una versione supportata** di Windows .</span><span class="sxs-lookup"><span data-stu-id="60ad3-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="60ad3-122">I dispositivi devono eseguire una delle versioni seguenti di Windows</span><span class="sxs-lookup"><span data-stu-id="60ad3-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="60ad3-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="60ad3-123">**Windows 10**</span></span>
    - <span data-ttu-id="60ad3-124">[Versione 1909](/windows/whats-new/whats-new-windows-10-version-1909) o successiva</span><span class="sxs-lookup"><span data-stu-id="60ad3-124">[Version 1909](/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="60ad3-125">[Versione 1903](/windows/whats-new/whats-new-windows-10-version-1903) con [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="60ad3-125">[Version 1903](/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="60ad3-126">[Versione 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809) [con KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="60ad3-126">[Version 1809 (RS 5)](/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="60ad3-127">[Versione 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803) con [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="60ad3-127">[Version 1803 (RS 4)](/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="60ad3-128">[Versione 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) con [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="60ad3-128">[Version 1709 (RS 3)](/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="60ad3-129">**Windows Server 2019 - Applicabile solo per l'anteprima pubblica**</span><span class="sxs-lookup"><span data-stu-id="60ad3-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="60ad3-130">Versione 1903 o (con [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) più avanti</span><span class="sxs-lookup"><span data-stu-id="60ad3-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="60ad3-131">Versione 1809 (con [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span><span class="sxs-lookup"><span data-stu-id="60ad3-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="60ad3-132">**Abilita risposta in tempo reale dalla pagina delle impostazioni avanzate.**</span><span class="sxs-lookup"><span data-stu-id="60ad3-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="60ad3-133">Dovrai abilitare la funzionalità di risposta in tempo reale nella [pagina Impostazioni funzionalità](advanced-features.md) avanzate.</span><span class="sxs-lookup"><span data-stu-id="60ad3-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="60ad3-134">Solo gli utenti con ruoli di amministratore globale o di sicurezza possono modificare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="60ad3-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="60ad3-135">**Abilitare la risposta in tempo reale per i server dalla pagina delle impostazioni avanzate** (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="60ad3-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="60ad3-136">Solo gli utenti con ruoli di amministratore globale o di sicurezza possono modificare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="60ad3-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="60ad3-137">Assicurati che al dispositivo sia assegnato un livello di **correzione dell'automazione.**</span><span class="sxs-lookup"><span data-stu-id="60ad3-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="60ad3-138">Dovrai abilitare almeno il livello di correzione minimo per un determinato gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="60ad3-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="60ad3-139">In caso contrario, non sarà possibile stabilire una sessione di Risposta in tempo reale a un membro del gruppo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="60ad3-140">Verrà visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="60ad3-140">You'll receive the following error:</span></span>

    ![Immagine del messaggio di errore](images/live-response-error.png)

- <span data-ttu-id="60ad3-142">**Abilitare l'esecuzione di script non firmati** in risposta attiva (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="60ad3-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="60ad3-143">Consentire l'uso di script non firmati può aumentare l'esposizione alle minacce.</span><span class="sxs-lookup"><span data-stu-id="60ad3-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="60ad3-144">L'esecuzione di script non firmati non è consigliata perché può aumentare l'esposizione alle minacce.</span><span class="sxs-lookup"><span data-stu-id="60ad3-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="60ad3-145">Se tuttavia è necessario utilizzarli, è necessario abilitare l'impostazione nella [pagina Impostazioni funzionalità](advanced-features.md) avanzate.</span><span class="sxs-lookup"><span data-stu-id="60ad3-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="60ad3-146">**Assicurarsi di disporre delle autorizzazioni appropriate.**</span><span class="sxs-lookup"><span data-stu-id="60ad3-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="60ad3-147">Solo gli utenti di cui è stato eseguito il provisioning con le autorizzazioni appropriate possono avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="60ad3-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="60ad3-148">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="60ad3-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="60ad3-149">L'opzione per caricare un file nella raccolta è disponibile solo per gli utenti con le autorizzazioni RBAC appropriate.</span><span class="sxs-lookup"><span data-stu-id="60ad3-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="60ad3-150">Il pulsante è in grigio per gli utenti con solo autorizzazioni delegate.</span><span class="sxs-lookup"><span data-stu-id="60ad3-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="60ad3-151">A seconda del ruolo che ti è stato concesso, puoi eseguire comandi di risposta in tempo reale di base o avanzati.</span><span class="sxs-lookup"><span data-stu-id="60ad3-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="60ad3-152">Le autorizzazioni degli utenti sono controllate dal ruolo personalizzato RBAC.</span><span class="sxs-lookup"><span data-stu-id="60ad3-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="60ad3-153">Panoramica del dashboard di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="60ad3-153">Live response dashboard overview</span></span>
<span data-ttu-id="60ad3-154">Quando avvii una sessione di risposta in tempo reale su un dispositivo, viene aperto un dashboard.</span><span class="sxs-lookup"><span data-stu-id="60ad3-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="60ad3-155">Il dashboard fornisce informazioni sulla sessione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="60ad3-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="60ad3-156">Who creata la sessione</span><span class="sxs-lookup"><span data-stu-id="60ad3-156">Who created the session</span></span>
- <span data-ttu-id="60ad3-157">All'avvio della sessione</span><span class="sxs-lookup"><span data-stu-id="60ad3-157">When the session started</span></span>
- <span data-ttu-id="60ad3-158">Durata della sessione</span><span class="sxs-lookup"><span data-stu-id="60ad3-158">The duration of the session</span></span>

<span data-ttu-id="60ad3-159">Il dashboard consente inoltre di accedere a:</span><span class="sxs-lookup"><span data-stu-id="60ad3-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="60ad3-160">Disconnetti sessione</span><span class="sxs-lookup"><span data-stu-id="60ad3-160">Disconnect session</span></span>
- <span data-ttu-id="60ad3-161">Upload file nella raccolta</span><span class="sxs-lookup"><span data-stu-id="60ad3-161">Upload files to the library</span></span> 
- <span data-ttu-id="60ad3-162">Console dei comandi</span><span class="sxs-lookup"><span data-stu-id="60ad3-162">Command console</span></span>
- <span data-ttu-id="60ad3-163">Log dei comandi</span><span class="sxs-lookup"><span data-stu-id="60ad3-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="60ad3-164">Avviare una sessione di risposta in tempo reale in un dispositivo</span><span class="sxs-lookup"><span data-stu-id="60ad3-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="60ad3-165">Accedi a Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="60ad3-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="60ad3-166">Passa alla pagina dell'elenco dei dispositivi e seleziona un dispositivo da analizzare.</span><span class="sxs-lookup"><span data-stu-id="60ad3-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="60ad3-167">Viene visualizzata la pagina dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="60ad3-167">The devices page opens.</span></span>

3. <span data-ttu-id="60ad3-168">Avviare la sessione di risposta in tempo reale selezionando **Avvia sessione di risposta in tempo reale.**</span><span class="sxs-lookup"><span data-stu-id="60ad3-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="60ad3-169">Viene visualizzata una console dei comandi.</span><span class="sxs-lookup"><span data-stu-id="60ad3-169">A command console is displayed.</span></span> <span data-ttu-id="60ad3-170">Attendere che la sessione si connetta al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="60ad3-171">Usa i comandi predefiniti per eseguire attività di indagine.</span><span class="sxs-lookup"><span data-stu-id="60ad3-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="60ad3-172">Per ulteriori informazioni, vedere [Comandi di risposta in tempo reale.](#live-response-commands)</span><span class="sxs-lookup"><span data-stu-id="60ad3-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="60ad3-173">Dopo aver completato l'indagine, selezionare **Disconnetti sessione** e **quindi** Conferma.</span><span class="sxs-lookup"><span data-stu-id="60ad3-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="60ad3-174">Comandi di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="60ad3-174">Live response commands</span></span>

<span data-ttu-id="60ad3-175">A seconda del ruolo che ti è stato concesso, puoi eseguire comandi di risposta in tempo reale di base o avanzati.</span><span class="sxs-lookup"><span data-stu-id="60ad3-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="60ad3-176">Le autorizzazioni utente sono controllate dai ruoli personalizzati RBAC.</span><span class="sxs-lookup"><span data-stu-id="60ad3-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="60ad3-177">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="60ad3-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="60ad3-178">La risposta in tempo reale è una shell interattiva basata sul cloud, in quanto tale, l'esperienza di comando specifica può variare in base alla qualità della rete e al carico di sistema tra l'utente finale e il dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="60ad3-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="60ad3-179">Comandi di base</span><span class="sxs-lookup"><span data-stu-id="60ad3-179">Basic commands</span></span>

<span data-ttu-id="60ad3-180">I comandi seguenti sono disponibili per i ruoli utente a cui viene concessa la possibilità di eseguire comandi **di risposta** in tempo reale di base.</span><span class="sxs-lookup"><span data-stu-id="60ad3-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="60ad3-181">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="60ad3-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="60ad3-182">Comando</span><span class="sxs-lookup"><span data-stu-id="60ad3-182">Command</span></span> | <span data-ttu-id="60ad3-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60ad3-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="60ad3-184">Modifica la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="60ad3-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="60ad3-185">Cancella la schermata della console.</span><span class="sxs-lookup"><span data-stu-id="60ad3-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="60ad3-186">Avvia una sessione di risposta in tempo reale al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="60ad3-187">Mostra tutte le connessioni attive.</span><span class="sxs-lookup"><span data-stu-id="60ad3-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="60ad3-188">Visualizza un elenco di file e sottodirectory in una directory.</span><span class="sxs-lookup"><span data-stu-id="60ad3-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`drivers` |  <span data-ttu-id="60ad3-189">Mostra tutti i driver installati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-189">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="60ad3-190">Posiziona il processo specificato in primo piano in primo piano, rendendolo il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="60ad3-190">Place the specified job in the foreground in the foreground, making it the current job.</span></span> <br> <span data-ttu-id="60ad3-191">NOTA: fg accetta un "ID comando" disponibile dai processi, non un PID</span><span class="sxs-lookup"><span data-stu-id="60ad3-191">NOTE: fg takes a “command ID” available from jobs, not a PID</span></span> |
|`fileinfo` | <span data-ttu-id="60ad3-192">Ottenere informazioni su un file.</span><span class="sxs-lookup"><span data-stu-id="60ad3-192">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="60ad3-193">Individua i file con un nome specificato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-193">Locates files by a given name on the device.</span></span> |
|`getfile <file_path>` | <span data-ttu-id="60ad3-194">Scarica un file.</span><span class="sxs-lookup"><span data-stu-id="60ad3-194">Downloads a file.</span></span> |
|`help` | <span data-ttu-id="60ad3-195">Fornisce informazioni della Guida per i comandi di risposta in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="60ad3-195">Provides help information for live response commands.</span></span> |
|`jobs` | <span data-ttu-id="60ad3-196">Mostra i processi attualmente in esecuzione, il relativo ID e stato.</span><span class="sxs-lookup"><span data-stu-id="60ad3-196">Shows currently running jobs, their ID and status.</span></span> |
|`persistence` | <span data-ttu-id="60ad3-197">Mostra tutti i metodi di persistenza noti nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-197">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="60ad3-198">Mostra tutti i processi in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-198">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="60ad3-199">Mostra i valori del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="60ad3-199">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="60ad3-200">Mostra tutte le attività pianificate nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-200">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="60ad3-201">Mostra tutti i servizi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-201">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="60ad3-202">Imposta la modalità di registrazione del terminale per il debug.</span><span class="sxs-lookup"><span data-stu-id="60ad3-202">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="60ad3-203">Comandi avanzati</span><span class="sxs-lookup"><span data-stu-id="60ad3-203">Advanced commands</span></span>
<span data-ttu-id="60ad3-204">I comandi seguenti sono disponibili per i ruoli utente a cui viene concessa la possibilità di eseguire **comandi di** risposta in tempo reale avanzati.</span><span class="sxs-lookup"><span data-stu-id="60ad3-204">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="60ad3-205">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="60ad3-205">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="60ad3-206">Comando</span><span class="sxs-lookup"><span data-stu-id="60ad3-206">Command</span></span> | <span data-ttu-id="60ad3-207">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60ad3-207">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="60ad3-208">Analizza l'entità con vari motori di incriminazione per raggiungere un verdetto.</span><span class="sxs-lookup"><span data-stu-id="60ad3-208">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `run` | <span data-ttu-id="60ad3-209">Esegue uno script di PowerShell dalla raccolta nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-209">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="60ad3-210">Elenca i file caricati nella raccolta di risposte in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="60ad3-210">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="60ad3-211">Inserisce un file dalla raccolta al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-211">Puts a file from the library to the device.</span></span> <span data-ttu-id="60ad3-212">I file vengono salvati in una cartella di lavoro e vengono eliminati al riavvio del dispositivo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="60ad3-212">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="60ad3-213">Correzione di un'entità nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60ad3-213">Remediates an entity on the device.</span></span> <span data-ttu-id="60ad3-214">L'azione di correzione varia a seconda del tipo di entità:</span><span class="sxs-lookup"><span data-stu-id="60ad3-214">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="60ad3-215">- File: delete</span><span class="sxs-lookup"><span data-stu-id="60ad3-215">- File: delete</span></span><br><span data-ttu-id="60ad3-216">- Processo: arrestare, eliminare il file di immagine</span><span class="sxs-lookup"><span data-stu-id="60ad3-216">- Process: stop, delete image file</span></span><br><span data-ttu-id="60ad3-217">- Servizio: arrestare, eliminare il file di immagine</span><span class="sxs-lookup"><span data-stu-id="60ad3-217">- Service: stop, delete image file</span></span><br><span data-ttu-id="60ad3-218">- Voce del Registro di sistema: delete</span><span class="sxs-lookup"><span data-stu-id="60ad3-218">- Registry entry: delete</span></span><br><span data-ttu-id="60ad3-219">- Attività pianificata: rimuovere</span><span class="sxs-lookup"><span data-stu-id="60ad3-219">- Scheduled task: remove</span></span><br><span data-ttu-id="60ad3-220">- Elemento cartella di avvio: elimina file</span><span class="sxs-lookup"><span data-stu-id="60ad3-220">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="60ad3-221">NOTA: questo comando ha un comando prerequisito.</span><span class="sxs-lookup"><span data-stu-id="60ad3-221">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="60ad3-222">È possibile utilizzare il `-auto` comando insieme a per eseguire `remediate` automaticamente il comando prerequisito.</span><span class="sxs-lookup"><span data-stu-id="60ad3-222">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="60ad3-223">Ripristina un'entità che è stata corretti.</span><span class="sxs-lookup"><span data-stu-id="60ad3-223">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="60ad3-224">Usare i comandi di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="60ad3-224">Use live response commands</span></span>

<span data-ttu-id="60ad3-225">I comandi che è possibile utilizzare nella console seguono principi simili [a quelli Windows Comandi](/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span><span class="sxs-lookup"><span data-stu-id="60ad3-225">The commands that you can use in the console follow similar principles as [Windows Commands](/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="60ad3-226">I comandi avanzati offrono un set più affidabile di azioni che consentono di eseguire azioni più efficaci, ad esempio scaricare e caricare un file, eseguire script nel dispositivo ed eseguire azioni di correzione su un'entità.</span><span class="sxs-lookup"><span data-stu-id="60ad3-226">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="60ad3-227">Ottenere un file dal dispositivo</span><span class="sxs-lookup"><span data-stu-id="60ad3-227">Get a file from the device</span></span>

<span data-ttu-id="60ad3-228">Per gli scenari in cui vuoi ottenere un file da un dispositivo che stai analizzando, puoi usare il `getfile` comando.</span><span class="sxs-lookup"><span data-stu-id="60ad3-228">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="60ad3-229">In questo modo è possibile salvare il file dal dispositivo per ulteriori indagini.</span><span class="sxs-lookup"><span data-stu-id="60ad3-229">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="60ad3-230">Si applicano i limiti di dimensione dei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="60ad3-230">The following file size limits apply:</span></span>
>- <span data-ttu-id="60ad3-231">`getfile` limite: 3 GB</span><span class="sxs-lookup"><span data-stu-id="60ad3-231">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="60ad3-232">`fileinfo` limite: 10 GB</span><span class="sxs-lookup"><span data-stu-id="60ad3-232">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="60ad3-233">`library` limite: 250 MB</span><span class="sxs-lookup"><span data-stu-id="60ad3-233">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="60ad3-234">Scaricare un file in background</span><span class="sxs-lookup"><span data-stu-id="60ad3-234">Download a file in the background</span></span>

<span data-ttu-id="60ad3-235">Per consentire al team delle operazioni di sicurezza di continuare a analizzare un dispositivo a impatto, i file possono ora essere scaricati in background.</span><span class="sxs-lookup"><span data-stu-id="60ad3-235">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="60ad3-236">Per scaricare un file in background, nella console dei comandi di risposta in tempo reale digitare `download <file_path> &` .</span><span class="sxs-lookup"><span data-stu-id="60ad3-236">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="60ad3-237">Se si è in attesa del download di un file, è possibile spostarlo in background utilizzando Ctrl + Z.</span><span class="sxs-lookup"><span data-stu-id="60ad3-237">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="60ad3-238">Per portare in primo piano il download di un file, nella console dei comandi di risposta in tempo reale digitare `fg <command_id>` .</span><span class="sxs-lookup"><span data-stu-id="60ad3-238">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="60ad3-239">Di seguito vengono descritti alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="60ad3-239">Here are some examples:</span></span>


|<span data-ttu-id="60ad3-240">Comando</span><span class="sxs-lookup"><span data-stu-id="60ad3-240">Command</span></span>  |<span data-ttu-id="60ad3-241">Funzione</span><span class="sxs-lookup"><span data-stu-id="60ad3-241">What it does</span></span>  |
|---------|---------|
|`getfile "C:\windows\some_file.exe" &`     |<span data-ttu-id="60ad3-242">Avvia il download di un file *denominatosome_file.exe* in background.</span><span class="sxs-lookup"><span data-stu-id="60ad3-242">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="60ad3-243">Restituisce un download con ID comando *1234* in primo piano.</span><span class="sxs-lookup"><span data-stu-id="60ad3-243">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="60ad3-244">Inserire un file nella raccolta</span><span class="sxs-lookup"><span data-stu-id="60ad3-244">Put a file in the library</span></span>

<span data-ttu-id="60ad3-245">La risposta in tempo reale include una raccolta in cui è possibile inserire i file.</span><span class="sxs-lookup"><span data-stu-id="60ad3-245">Live response has a library where you can put files into.</span></span> <span data-ttu-id="60ad3-246">La raccolta archivia i file,ad esempio gli script, che possono essere eseguiti in una sessione di risposta in tempo reale a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="60ad3-246">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="60ad3-247">La risposta in tempo reale consente l'esecuzione degli script di PowerShell, tuttavia è necessario innanzitutto inserire i file nella raccolta prima di poterli eseguire.</span><span class="sxs-lookup"><span data-stu-id="60ad3-247">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="60ad3-248">Puoi avere una raccolta di script di PowerShell che possono essere eseguiti nei dispositivi con cui avvii sessioni di risposta in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="60ad3-248">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="60ad3-249">Per caricare un file nella raccolta</span><span class="sxs-lookup"><span data-stu-id="60ad3-249">To upload a file in the library</span></span>

1. <span data-ttu-id="60ad3-250">Fare **clic Upload file nella raccolta.**</span><span class="sxs-lookup"><span data-stu-id="60ad3-250">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="60ad3-251">Fare **clic su** Sfoglia e selezionare il file.</span><span class="sxs-lookup"><span data-stu-id="60ad3-251">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="60ad3-252">Fornire una breve descrizione.</span><span class="sxs-lookup"><span data-stu-id="60ad3-252">Provide a brief description.</span></span>

4. <span data-ttu-id="60ad3-253">Specificare se si desidera sovrascrivere un file con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="60ad3-253">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="60ad3-254">Se si desidera, sapere quali parametri sono necessari per lo script, selezionare la casella di controllo Parametri script.</span><span class="sxs-lookup"><span data-stu-id="60ad3-254">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="60ad3-255">Nel campo di testo immettere un esempio e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="60ad3-255">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="60ad3-256">Fare clic **su Conferma**.</span><span class="sxs-lookup"><span data-stu-id="60ad3-256">Click **Confirm**.</span></span> 

7. <span data-ttu-id="60ad3-257">(Facoltativo) Per verificare che il file sia stato caricato nella raccolta, eseguire il `library` comando.</span><span class="sxs-lookup"><span data-stu-id="60ad3-257">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="60ad3-258">Annullare un comando</span><span class="sxs-lookup"><span data-stu-id="60ad3-258">Cancel a command</span></span>
<span data-ttu-id="60ad3-259">In qualsiasi momento durante una sessione, è possibile annullare un comando premendo CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="60ad3-259">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="60ad3-260">L'utilizzo di questo collegamento non arresterà il comando sul lato agente.</span><span class="sxs-lookup"><span data-stu-id="60ad3-260">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="60ad3-261">Il comando verrà annullato solo nel portale.</span><span class="sxs-lookup"><span data-stu-id="60ad3-261">It will only cancel the command in the portal.</span></span> <span data-ttu-id="60ad3-262">Pertanto, le operazioni di modifica come "correzione" potrebbero continuare, mentre il comando viene annullato.</span><span class="sxs-lookup"><span data-stu-id="60ad3-262">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

## <a name="run-a-powershell-script"></a><span data-ttu-id="60ad3-263">Eseguire uno script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="60ad3-263">Run a PowerShell script</span></span> 

<span data-ttu-id="60ad3-264">Prima di poter eseguire uno script di PowerShell, è necessario caricarlo nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="60ad3-264">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="60ad3-265">Dopo aver caricato lo script nella raccolta, utilizzare il `run` comando per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="60ad3-265">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="60ad3-266">Se si prevede di utilizzare uno script non firmato nella sessione, sarà necessario abilitare l'impostazione nella [pagina Impostazioni funzionalità](advanced-features.md) avanzate.</span><span class="sxs-lookup"><span data-stu-id="60ad3-266">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="60ad3-267">Consentire l'uso di script non firmati può aumentare l'esposizione alle minacce.</span><span class="sxs-lookup"><span data-stu-id="60ad3-267">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="60ad3-268">Applicare parametri di comando</span><span class="sxs-lookup"><span data-stu-id="60ad3-268">Apply command parameters</span></span>

- <span data-ttu-id="60ad3-269">Visualizzare la Guida della console per informazioni sui parametri del comando.</span><span class="sxs-lookup"><span data-stu-id="60ad3-269">View the console help to learn about command parameters.</span></span> <span data-ttu-id="60ad3-270">Per informazioni su un singolo comando, eseguire:</span><span class="sxs-lookup"><span data-stu-id="60ad3-270">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="60ad3-271">Quando si applicano parametri ai comandi, tenere presente che i parametri vengono gestiti in base a un ordine fisso:</span><span class="sxs-lookup"><span data-stu-id="60ad3-271">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="60ad3-272">Quando si specificano parametri al di fuori dell'ordine fisso, specificare il nome del parametro con un trattino prima di specificare il valore:</span><span class="sxs-lookup"><span data-stu-id="60ad3-272">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="60ad3-273">Quando si utilizzano comandi che dispongono di comandi prerequisiti, è possibile utilizzare i flag:</span><span class="sxs-lookup"><span data-stu-id="60ad3-273">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="60ad3-274">`<command name> -type file -id <file path> - auto` o `remediate file <file path> - auto` .</span><span class="sxs-lookup"><span data-stu-id="60ad3-274">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="60ad3-275">Tipi di output supportati</span><span class="sxs-lookup"><span data-stu-id="60ad3-275">Supported output types</span></span>

<span data-ttu-id="60ad3-276">La risposta in tempo reale supporta i tipi di output in formato JSON e tabella.</span><span class="sxs-lookup"><span data-stu-id="60ad3-276">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="60ad3-277">Per ogni comando esiste un comportamento di output predefinito.</span><span class="sxs-lookup"><span data-stu-id="60ad3-277">For each command, there's a default output behavior.</span></span> <span data-ttu-id="60ad3-278">Puoi modificare l'output nel formato di output preferito usando i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="60ad3-278">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="60ad3-279">Un numero inferiore di campi viene visualizzato in formato tabella a causa dello spazio limitato.</span><span class="sxs-lookup"><span data-stu-id="60ad3-279">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="60ad3-280">Per visualizzare altri dettagli nell'output, puoi usare il comando di output JSON in modo da visualizzare altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="60ad3-280">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="60ad3-281">Pipe di output supportate</span><span class="sxs-lookup"><span data-stu-id="60ad3-281">Supported output pipes</span></span>

<span data-ttu-id="60ad3-282">La risposta in tempo reale supporta l'output piping su CLI e file.</span><span class="sxs-lookup"><span data-stu-id="60ad3-282">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="60ad3-283">CLI è il comportamento di output predefinito.</span><span class="sxs-lookup"><span data-stu-id="60ad3-283">CLI is the default output behavior.</span></span> <span data-ttu-id="60ad3-284">È possibile pipeare l'output in un file utilizzando il comando seguente: [comando] > [nomefile].txt.</span><span class="sxs-lookup"><span data-stu-id="60ad3-284">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="60ad3-285">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60ad3-285">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="60ad3-286">Visualizzare il log dei comandi</span><span class="sxs-lookup"><span data-stu-id="60ad3-286">View the command log</span></span>

<span data-ttu-id="60ad3-287">Seleziona la **scheda Registro** comandi per visualizzare i comandi usati nel dispositivo durante una sessione.</span><span class="sxs-lookup"><span data-stu-id="60ad3-287">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="60ad3-288">Ogni comando viene monitorato con dettagli completi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="60ad3-288">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="60ad3-289">ID</span><span class="sxs-lookup"><span data-stu-id="60ad3-289">ID</span></span>
- <span data-ttu-id="60ad3-290">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="60ad3-290">Command line</span></span>
- <span data-ttu-id="60ad3-291">Durata</span><span class="sxs-lookup"><span data-stu-id="60ad3-291">Duration</span></span>
- <span data-ttu-id="60ad3-292">Barra laterale di stato e input o output</span><span class="sxs-lookup"><span data-stu-id="60ad3-292">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="60ad3-293">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="60ad3-293">Limitations</span></span>

- <span data-ttu-id="60ad3-294">Le sessioni di risposta in tempo reale sono limitate a 25 sessioni di risposta in tempo reale alla volta.</span><span class="sxs-lookup"><span data-stu-id="60ad3-294">Live response sessions are limited to 25 live response sessions at a time.</span></span>
- <span data-ttu-id="60ad3-295">Il valore di timeout inattiva della sessione di risposta in tempo reale è 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="60ad3-295">Live response session inactive timeout value is 30 minutes.</span></span> 
- <span data-ttu-id="60ad3-296">Un utente può avviare fino a 10 sessioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="60ad3-296">A user can initiate up to 10 concurrent sessions.</span></span>
- <span data-ttu-id="60ad3-297">Un dispositivo può essere in una sola sessione alla volta.</span><span class="sxs-lookup"><span data-stu-id="60ad3-297">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="60ad3-298">Si applicano i limiti di dimensione dei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="60ad3-298">The following file size limits apply:</span></span>
   - <span data-ttu-id="60ad3-299">`getfile` limite: 3 GB</span><span class="sxs-lookup"><span data-stu-id="60ad3-299">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="60ad3-300">`fileinfo` limite: 10 GB</span><span class="sxs-lookup"><span data-stu-id="60ad3-300">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="60ad3-301">`library` limite: 250 MB</span><span class="sxs-lookup"><span data-stu-id="60ad3-301">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="60ad3-302">Articolo correlato</span><span class="sxs-lookup"><span data-stu-id="60ad3-302">Related article</span></span>
- [<span data-ttu-id="60ad3-303">Esempi di comandi di Live response</span><span class="sxs-lookup"><span data-stu-id="60ad3-303">Live response command examples</span></span>](live-response-command-examples.md)
