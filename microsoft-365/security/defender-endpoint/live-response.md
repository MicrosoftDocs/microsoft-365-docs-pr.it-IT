---
title: Analizzare le entità nei dispositivi che usano la risposta in tempo reale in Microsoft Defender ATP
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
ms.openlocfilehash: 235df8c84077311444c597b120a19477cfd0986a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760417"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="c8720-104">Analizzare le entità nei dispositivi che usano la risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="c8720-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c8720-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c8720-105">**Applies to:**</span></span>
- [<span data-ttu-id="c8720-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c8720-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c8720-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8720-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="c8720-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c8720-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c8720-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c8720-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="c8720-110">La risposta in tempo reale consente ai team delle operazioni di sicurezza di accedere istantaneamente a un dispositivo (noto anche come computer) utilizzando una connessione shell remota.</span><span class="sxs-lookup"><span data-stu-id="c8720-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="c8720-111">In questo modo è possibile eseguire un lavoro di indagine approfondito e intraprendere azioni di risposta immediate per contenere prontamente le minacce identificate, in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="c8720-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="c8720-112">La risposta in tempo reale è progettata per migliorare le indagini consentendo al team delle operazioni di sicurezza di raccogliere dati forensi, eseguire script, inviare entità sospette per l'analisi, correggere le minacce e cercare in modo proattivo minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="c8720-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="c8720-113">Con la risposta in tempo reale, gli analisti possono eseguire tutte le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8720-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="c8720-114">Esegui comandi di base e avanzati per eseguire attività di indagine su un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="c8720-115">Scaricare file come esempi di malware e risultati degli script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c8720-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="c8720-116">Scaricare i file in background (nuovo!).</span><span class="sxs-lookup"><span data-stu-id="c8720-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="c8720-117">Caricare uno script di PowerShell o un file eseguibile nella raccolta ed eseguirlo in un dispositivo da un livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="c8720-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="c8720-118">Eseguire o annullare azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="c8720-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c8720-119">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c8720-119">Before you begin</span></span>

<span data-ttu-id="c8720-120">Prima di poter avviare una sessione su un dispositivo, assicurati di soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8720-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="c8720-121">**Verificare che sia in esecuzione una versione supportata di Windows**.</span><span class="sxs-lookup"><span data-stu-id="c8720-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="c8720-122">I dispositivi devono eseguire una delle versioni seguenti di Windows</span><span class="sxs-lookup"><span data-stu-id="c8720-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="c8720-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="c8720-123">**Windows 10**</span></span>
    - <span data-ttu-id="c8720-124">[Versione 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) o successiva</span><span class="sxs-lookup"><span data-stu-id="c8720-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="c8720-125">[Versione 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) con [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="c8720-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="c8720-126">[Versione 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) [con KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="c8720-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="c8720-127">[Versione 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) con [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="c8720-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="c8720-128">[Versione 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) con [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="c8720-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="c8720-129">**Windows Server 2019 - Applicabile solo per l'anteprima pubblica**</span><span class="sxs-lookup"><span data-stu-id="c8720-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="c8720-130">Versione 1903 o (con [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) più avanti</span><span class="sxs-lookup"><span data-stu-id="c8720-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="c8720-131">Versione 1809 (con [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span><span class="sxs-lookup"><span data-stu-id="c8720-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="c8720-132">**Abilita risposta in tempo reale dalla pagina delle impostazioni avanzate.**</span><span class="sxs-lookup"><span data-stu-id="c8720-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="c8720-133">Dovrai abilitare la funzionalità di risposta in tempo reale nella [pagina Impostazioni funzionalità](advanced-features.md) avanzate.</span><span class="sxs-lookup"><span data-stu-id="c8720-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="c8720-134">Solo gli utenti con ruoli di amministratore globale o di sicurezza possono modificare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="c8720-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="c8720-135">**Abilitare la risposta in tempo reale per i server dalla pagina delle impostazioni avanzate** (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="c8720-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="c8720-136">Solo gli utenti con ruoli di amministratore globale o di sicurezza possono modificare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="c8720-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="c8720-137">Assicurati che al dispositivo sia assegnato un livello di **correzione dell'automazione.**</span><span class="sxs-lookup"><span data-stu-id="c8720-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="c8720-138">Dovrai abilitare almeno il livello di correzione minimo per un determinato gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c8720-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="c8720-139">In caso contrario, non sarà possibile stabilire una sessione di Risposta in tempo reale a un membro del gruppo.</span><span class="sxs-lookup"><span data-stu-id="c8720-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="c8720-140">Verrà visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="c8720-140">You'll receive the following error:</span></span>

    ![Immagine del messaggio di errore](images/live-response-error.png)

- <span data-ttu-id="c8720-142">**Abilitare l'esecuzione di script non firmati** in risposta attiva (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="c8720-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="c8720-143">Consentire l'uso di script non firmati può aumentare l'esposizione alle minacce.</span><span class="sxs-lookup"><span data-stu-id="c8720-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="c8720-144">L'esecuzione di script non firmati non è consigliata perché può aumentare l'esposizione alle minacce.</span><span class="sxs-lookup"><span data-stu-id="c8720-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="c8720-145">Se tuttavia è necessario utilizzarli, è necessario abilitare l'impostazione nella [pagina Impostazioni funzionalità](advanced-features.md) avanzate.</span><span class="sxs-lookup"><span data-stu-id="c8720-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="c8720-146">**Assicurarsi di disporre delle autorizzazioni appropriate.**</span><span class="sxs-lookup"><span data-stu-id="c8720-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="c8720-147">Solo gli utenti di cui è stato eseguito il provisioning con le autorizzazioni appropriate possono avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="c8720-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="c8720-148">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c8720-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="c8720-149">L'opzione per caricare un file nella raccolta è disponibile solo per gli utenti con le autorizzazioni RBAC appropriate.</span><span class="sxs-lookup"><span data-stu-id="c8720-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="c8720-150">Il pulsante è in grigio per gli utenti con solo autorizzazioni delegate.</span><span class="sxs-lookup"><span data-stu-id="c8720-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="c8720-151">A seconda del ruolo che ti è stato concesso, puoi eseguire comandi di risposta in tempo reale di base o avanzati.</span><span class="sxs-lookup"><span data-stu-id="c8720-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="c8720-152">Le autorizzazioni degli utenti sono controllate dal ruolo personalizzato RBAC.</span><span class="sxs-lookup"><span data-stu-id="c8720-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="c8720-153">Panoramica del dashboard di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="c8720-153">Live response dashboard overview</span></span>
<span data-ttu-id="c8720-154">Quando avvii una sessione di risposta in tempo reale su un dispositivo, viene aperto un dashboard.</span><span class="sxs-lookup"><span data-stu-id="c8720-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="c8720-155">Il dashboard fornisce informazioni sulla sessione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c8720-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="c8720-156">Chi ha creato la sessione</span><span class="sxs-lookup"><span data-stu-id="c8720-156">Who created the session</span></span>
- <span data-ttu-id="c8720-157">All'avvio della sessione</span><span class="sxs-lookup"><span data-stu-id="c8720-157">When the session started</span></span>
- <span data-ttu-id="c8720-158">Durata della sessione</span><span class="sxs-lookup"><span data-stu-id="c8720-158">The duration of the session</span></span>

<span data-ttu-id="c8720-159">Il dashboard consente inoltre di accedere a:</span><span class="sxs-lookup"><span data-stu-id="c8720-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="c8720-160">Disconnetti sessione</span><span class="sxs-lookup"><span data-stu-id="c8720-160">Disconnect session</span></span>
- <span data-ttu-id="c8720-161">Caricare file nella raccolta</span><span class="sxs-lookup"><span data-stu-id="c8720-161">Upload files to the library</span></span> 
- <span data-ttu-id="c8720-162">Console dei comandi</span><span class="sxs-lookup"><span data-stu-id="c8720-162">Command console</span></span>
- <span data-ttu-id="c8720-163">Log dei comandi</span><span class="sxs-lookup"><span data-stu-id="c8720-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="c8720-164">Avviare una sessione di risposta in tempo reale in un dispositivo</span><span class="sxs-lookup"><span data-stu-id="c8720-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="c8720-165">Accedi a Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="c8720-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="c8720-166">Passa alla pagina dell'elenco dei dispositivi e seleziona un dispositivo da analizzare.</span><span class="sxs-lookup"><span data-stu-id="c8720-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="c8720-167">Viene visualizzata la pagina dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c8720-167">The devices page opens.</span></span>

3. <span data-ttu-id="c8720-168">Avviare la sessione di risposta in tempo reale selezionando **Avvia sessione di risposta in tempo reale.**</span><span class="sxs-lookup"><span data-stu-id="c8720-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="c8720-169">Viene visualizzata una console dei comandi.</span><span class="sxs-lookup"><span data-stu-id="c8720-169">A command console is displayed.</span></span> <span data-ttu-id="c8720-170">Attendere che la sessione si connetta al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="c8720-171">Usa i comandi predefiniti per eseguire attività di indagine.</span><span class="sxs-lookup"><span data-stu-id="c8720-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="c8720-172">Per ulteriori informazioni, vedere [Comandi di risposta in tempo reale.](#live-response-commands)</span><span class="sxs-lookup"><span data-stu-id="c8720-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="c8720-173">Dopo aver completato l'indagine, selezionare **Disconnetti sessione** e **quindi** Conferma.</span><span class="sxs-lookup"><span data-stu-id="c8720-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="c8720-174">Comandi di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="c8720-174">Live response commands</span></span>

<span data-ttu-id="c8720-175">A seconda del ruolo che ti è stato concesso, puoi eseguire comandi di risposta in tempo reale di base o avanzati.</span><span class="sxs-lookup"><span data-stu-id="c8720-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="c8720-176">Le autorizzazioni utente sono controllate dai ruoli personalizzati RBAC.</span><span class="sxs-lookup"><span data-stu-id="c8720-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="c8720-177">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c8720-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="c8720-178">La risposta in tempo reale è una shell interattiva basata sul cloud, in quanto tale, l'esperienza di comando specifica può variare in base alla qualità della rete e al carico di sistema tra l'utente finale e il dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c8720-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="c8720-179">Comandi di base</span><span class="sxs-lookup"><span data-stu-id="c8720-179">Basic commands</span></span>

<span data-ttu-id="c8720-180">I comandi seguenti sono disponibili per i ruoli utente a cui viene concessa la possibilità di eseguire comandi **di risposta** in tempo reale di base.</span><span class="sxs-lookup"><span data-stu-id="c8720-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="c8720-181">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c8720-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="c8720-182">Comando</span><span class="sxs-lookup"><span data-stu-id="c8720-182">Command</span></span> | <span data-ttu-id="c8720-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8720-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="c8720-184">Modifica la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="c8720-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="c8720-185">Cancella la schermata della console.</span><span class="sxs-lookup"><span data-stu-id="c8720-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="c8720-186">Avvia una sessione di risposta in tempo reale al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="c8720-187">Mostra tutte le connessioni attive.</span><span class="sxs-lookup"><span data-stu-id="c8720-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="c8720-188">Visualizza un elenco di file e sottodirectory in una directory.</span><span class="sxs-lookup"><span data-stu-id="c8720-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`download <file_path> &` | <span data-ttu-id="c8720-189">Scarica un file in background.</span><span class="sxs-lookup"><span data-stu-id="c8720-189">Downloads a file in the background.</span></span> |
|`drivers` |  <span data-ttu-id="c8720-190">Mostra tutti i driver installati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-190">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="c8720-191">Posiziona il processo specificato in primo piano in primo piano, rendendolo il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="c8720-191">Place the specified job in the foreground in the foreground, making it the current job.</span></span> <br> <span data-ttu-id="c8720-192">NOTA: fg accetta un "ID comando" disponibile dai processi, non un PID</span><span class="sxs-lookup"><span data-stu-id="c8720-192">NOTE: fg takes a “command ID” available from jobs, not a PID</span></span> |
|`fileinfo` | <span data-ttu-id="c8720-193">Ottenere informazioni su un file.</span><span class="sxs-lookup"><span data-stu-id="c8720-193">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="c8720-194">Individua i file con un nome specificato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-194">Locates files by a given name on the device.</span></span> |
|`getfile <file_path>` | <span data-ttu-id="c8720-195">Scarica un file.</span><span class="sxs-lookup"><span data-stu-id="c8720-195">Downloads a file.</span></span> |
|`help` | <span data-ttu-id="c8720-196">Fornisce informazioni della Guida per i comandi di risposta in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="c8720-196">Provides help information for live response commands.</span></span> |
|`jobs` | <span data-ttu-id="c8720-197">Mostra i processi attualmente in esecuzione, il relativo ID e stato.</span><span class="sxs-lookup"><span data-stu-id="c8720-197">Shows currently running jobs, their ID and status.</span></span> |
|`persistence` | <span data-ttu-id="c8720-198">Mostra tutti i metodi di persistenza noti nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-198">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="c8720-199">Mostra tutti i processi in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-199">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="c8720-200">Mostra i valori del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="c8720-200">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="c8720-201">Mostra tutte le attività pianificate nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-201">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="c8720-202">Mostra tutti i servizi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-202">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="c8720-203">Imposta la modalità di registrazione del terminale per il debug.</span><span class="sxs-lookup"><span data-stu-id="c8720-203">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="c8720-204">Comandi avanzati</span><span class="sxs-lookup"><span data-stu-id="c8720-204">Advanced commands</span></span>
<span data-ttu-id="c8720-205">I comandi seguenti sono disponibili per i ruoli utente a cui viene concessa la possibilità di eseguire **comandi di** risposta in tempo reale avanzati.</span><span class="sxs-lookup"><span data-stu-id="c8720-205">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="c8720-206">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c8720-206">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="c8720-207">Comando</span><span class="sxs-lookup"><span data-stu-id="c8720-207">Command</span></span> | <span data-ttu-id="c8720-208">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8720-208">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="c8720-209">Analizza l'entità con vari motori di incriminazione per raggiungere un verdetto.</span><span class="sxs-lookup"><span data-stu-id="c8720-209">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `run` | <span data-ttu-id="c8720-210">Esegue uno script di PowerShell dalla raccolta nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-210">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="c8720-211">Elenca i file caricati nella raccolta di risposte in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="c8720-211">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="c8720-212">Inserisce un file dalla raccolta al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-212">Puts a file from the library to the device.</span></span> <span data-ttu-id="c8720-213">I file vengono salvati in una cartella di lavoro e vengono eliminati al riavvio del dispositivo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c8720-213">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="c8720-214">Correzione di un'entità nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8720-214">Remediates an entity on the device.</span></span> <span data-ttu-id="c8720-215">L'azione di correzione varia a seconda del tipo di entità:</span><span class="sxs-lookup"><span data-stu-id="c8720-215">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="c8720-216">- File: delete</span><span class="sxs-lookup"><span data-stu-id="c8720-216">- File: delete</span></span><br><span data-ttu-id="c8720-217">- Processo: arrestare, eliminare il file di immagine</span><span class="sxs-lookup"><span data-stu-id="c8720-217">- Process: stop, delete image file</span></span><br><span data-ttu-id="c8720-218">- Servizio: arrestare, eliminare il file di immagine</span><span class="sxs-lookup"><span data-stu-id="c8720-218">- Service: stop, delete image file</span></span><br><span data-ttu-id="c8720-219">- Voce del Registro di sistema: delete</span><span class="sxs-lookup"><span data-stu-id="c8720-219">- Registry entry: delete</span></span><br><span data-ttu-id="c8720-220">- Attività pianificata: rimuovere</span><span class="sxs-lookup"><span data-stu-id="c8720-220">- Scheduled task: remove</span></span><br><span data-ttu-id="c8720-221">- Elemento cartella di avvio: elimina file</span><span class="sxs-lookup"><span data-stu-id="c8720-221">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="c8720-222">NOTA: questo comando ha un comando prerequisito.</span><span class="sxs-lookup"><span data-stu-id="c8720-222">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="c8720-223">È possibile utilizzare il `-auto` comando insieme a per eseguire `remediate` automaticamente il comando prerequisito.</span><span class="sxs-lookup"><span data-stu-id="c8720-223">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="c8720-224">Ripristina un'entità che è stata corretti.</span><span class="sxs-lookup"><span data-stu-id="c8720-224">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="c8720-225">Usare i comandi di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="c8720-225">Use live response commands</span></span>

<span data-ttu-id="c8720-226">I comandi che puoi usare nella console seguono principi simili a quelli dei [comandi di Windows.](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c)</span><span class="sxs-lookup"><span data-stu-id="c8720-226">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="c8720-227">I comandi avanzati offrono un set più affidabile di azioni che consentono di eseguire azioni più efficaci, ad esempio scaricare e caricare un file, eseguire script nel dispositivo ed eseguire azioni di correzione su un'entità.</span><span class="sxs-lookup"><span data-stu-id="c8720-227">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="c8720-228">Ottenere un file dal dispositivo</span><span class="sxs-lookup"><span data-stu-id="c8720-228">Get a file from the device</span></span>

<span data-ttu-id="c8720-229">Per gli scenari in cui vuoi ottenere un file da un dispositivo che stai analizzando, puoi usare il `getfile` comando.</span><span class="sxs-lookup"><span data-stu-id="c8720-229">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="c8720-230">In questo modo è possibile salvare il file dal dispositivo per ulteriori indagini.</span><span class="sxs-lookup"><span data-stu-id="c8720-230">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="c8720-231">Si applicano i limiti di dimensione dei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8720-231">The following file size limits apply:</span></span>
>- <span data-ttu-id="c8720-232">`getfile` limite: 3 GB</span><span class="sxs-lookup"><span data-stu-id="c8720-232">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="c8720-233">`fileinfo` limite: 10 GB</span><span class="sxs-lookup"><span data-stu-id="c8720-233">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="c8720-234">`library` limite: 250 MB</span><span class="sxs-lookup"><span data-stu-id="c8720-234">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="c8720-235">Scaricare un file in background</span><span class="sxs-lookup"><span data-stu-id="c8720-235">Download a file in the background</span></span>

<span data-ttu-id="c8720-236">Per consentire al team delle operazioni di sicurezza di continuare a analizzare un dispositivo a impatto, i file possono ora essere scaricati in background.</span><span class="sxs-lookup"><span data-stu-id="c8720-236">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="c8720-237">Per scaricare un file in background, nella console dei comandi di risposta in tempo reale digitare `download <file_path> &` .</span><span class="sxs-lookup"><span data-stu-id="c8720-237">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="c8720-238">Se si è in attesa del download di un file, è possibile spostarlo in background utilizzando Ctrl + Z.</span><span class="sxs-lookup"><span data-stu-id="c8720-238">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="c8720-239">Per portare in primo piano il download di un file, nella console dei comandi di risposta in tempo reale digitare `fg <command_id>` .</span><span class="sxs-lookup"><span data-stu-id="c8720-239">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="c8720-240">Di seguito vengono descritti alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="c8720-240">Here are some examples:</span></span>


|<span data-ttu-id="c8720-241">Comando</span><span class="sxs-lookup"><span data-stu-id="c8720-241">Command</span></span>  |<span data-ttu-id="c8720-242">Funzione</span><span class="sxs-lookup"><span data-stu-id="c8720-242">What it does</span></span>  |
|---------|---------|
|`Download "C:\windows\some_file.exe" &`     |<span data-ttu-id="c8720-243">Avvia il download di un file *denominatosome_file.exe* in background.</span><span class="sxs-lookup"><span data-stu-id="c8720-243">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="c8720-244">Restituisce un download con ID comando *1234* in primo piano.</span><span class="sxs-lookup"><span data-stu-id="c8720-244">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="c8720-245">Inserire un file nella raccolta</span><span class="sxs-lookup"><span data-stu-id="c8720-245">Put a file in the library</span></span>

<span data-ttu-id="c8720-246">La risposta in tempo reale include una raccolta in cui è possibile inserire i file.</span><span class="sxs-lookup"><span data-stu-id="c8720-246">Live response has a library where you can put files into.</span></span> <span data-ttu-id="c8720-247">La raccolta archivia i file,ad esempio gli script, che possono essere eseguiti in una sessione di risposta in tempo reale a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="c8720-247">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="c8720-248">La risposta in tempo reale consente l'esecuzione degli script di PowerShell, tuttavia è necessario innanzitutto inserire i file nella raccolta prima di poterli eseguire.</span><span class="sxs-lookup"><span data-stu-id="c8720-248">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="c8720-249">Puoi avere una raccolta di script di PowerShell che possono essere eseguiti nei dispositivi con cui avvii sessioni di risposta in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="c8720-249">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="c8720-250">Per caricare un file nella raccolta</span><span class="sxs-lookup"><span data-stu-id="c8720-250">To upload a file in the library</span></span>

1. <span data-ttu-id="c8720-251">Fare **clic su Carica file nella raccolta.**</span><span class="sxs-lookup"><span data-stu-id="c8720-251">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="c8720-252">Fare **clic su** Sfoglia e selezionare il file.</span><span class="sxs-lookup"><span data-stu-id="c8720-252">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="c8720-253">Fornire una breve descrizione.</span><span class="sxs-lookup"><span data-stu-id="c8720-253">Provide a brief description.</span></span>

4. <span data-ttu-id="c8720-254">Specificare se si desidera sovrascrivere un file con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="c8720-254">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="c8720-255">Se si desidera, sapere quali parametri sono necessari per lo script, selezionare la casella di controllo Parametri script.</span><span class="sxs-lookup"><span data-stu-id="c8720-255">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="c8720-256">Nel campo di testo immettere un esempio e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="c8720-256">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="c8720-257">Fare clic **su Conferma**.</span><span class="sxs-lookup"><span data-stu-id="c8720-257">Click **Confirm**.</span></span> 

7. <span data-ttu-id="c8720-258">(Facoltativo) Per verificare che il file sia stato caricato nella raccolta, eseguire il `library` comando.</span><span class="sxs-lookup"><span data-stu-id="c8720-258">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="c8720-259">Annullare un comando</span><span class="sxs-lookup"><span data-stu-id="c8720-259">Cancel a command</span></span>
<span data-ttu-id="c8720-260">In qualsiasi momento durante una sessione, è possibile annullare un comando premendo CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="c8720-260">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="c8720-261">L'utilizzo di questo collegamento non arresterà il comando sul lato agente.</span><span class="sxs-lookup"><span data-stu-id="c8720-261">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="c8720-262">Il comando verrà annullato solo nel portale.</span><span class="sxs-lookup"><span data-stu-id="c8720-262">It will only cancel the command in the portal.</span></span> <span data-ttu-id="c8720-263">Pertanto, le operazioni di modifica come "correzione" potrebbero continuare, mentre il comando viene annullato.</span><span class="sxs-lookup"><span data-stu-id="c8720-263">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

### <a name="automatically-run-prerequisite-commands"></a><span data-ttu-id="c8720-264">Eseguire automaticamente i comandi dei prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c8720-264">Automatically run prerequisite commands</span></span>

<span data-ttu-id="c8720-265">Alcuni comandi dispongono di comandi prerequisiti da eseguire.</span><span class="sxs-lookup"><span data-stu-id="c8720-265">Some commands have prerequisite commands to run.</span></span> <span data-ttu-id="c8720-266">Se non si esegue il comando prerequisito, verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="c8720-266">If you don't run the prerequisite command, you'll get an error.</span></span> <span data-ttu-id="c8720-267">Ad esempio, `download` l'esecuzione del comando senza `fileinfo` restituirà un errore.</span><span class="sxs-lookup"><span data-stu-id="c8720-267">For example, running the `download` command without `fileinfo` will return an error.</span></span>

<span data-ttu-id="c8720-268">È possibile utilizzare il flag auto per eseguire automaticamente i comandi dei prerequisiti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c8720-268">You can use the auto flag to automatically run prerequisite commands, for example:</span></span>

```console
getfile c:\Users\user\Desktop\work.txt -auto
```

## <a name="run-a-powershell-script"></a><span data-ttu-id="c8720-269">Eseguire uno script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8720-269">Run a PowerShell script</span></span> 

<span data-ttu-id="c8720-270">Prima di poter eseguire uno script di PowerShell, è necessario caricarlo nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="c8720-270">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="c8720-271">Dopo aver caricato lo script nella raccolta, utilizzare il `run` comando per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="c8720-271">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="c8720-272">Se si prevede di utilizzare uno script non firmato nella sessione, sarà necessario abilitare l'impostazione nella [pagina Impostazioni funzionalità](advanced-features.md) avanzate.</span><span class="sxs-lookup"><span data-stu-id="c8720-272">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="c8720-273">Consentire l'uso di script non firmati può aumentare l'esposizione alle minacce.</span><span class="sxs-lookup"><span data-stu-id="c8720-273">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="c8720-274">Applicare parametri di comando</span><span class="sxs-lookup"><span data-stu-id="c8720-274">Apply command parameters</span></span>

- <span data-ttu-id="c8720-275">Visualizzare la Guida della console per informazioni sui parametri del comando.</span><span class="sxs-lookup"><span data-stu-id="c8720-275">View the console help to learn about command parameters.</span></span> <span data-ttu-id="c8720-276">Per informazioni su un singolo comando, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c8720-276">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="c8720-277">Quando si applicano parametri ai comandi, tenere presente che i parametri vengono gestiti in base a un ordine fisso:</span><span class="sxs-lookup"><span data-stu-id="c8720-277">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="c8720-278">Quando si specificano parametri al di fuori dell'ordine fisso, specificare il nome del parametro con un trattino prima di specificare il valore:</span><span class="sxs-lookup"><span data-stu-id="c8720-278">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="c8720-279">Quando si utilizzano comandi che dispongono di comandi prerequisiti, è possibile utilizzare i flag:</span><span class="sxs-lookup"><span data-stu-id="c8720-279">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="c8720-280">`<command name> -type file -id <file path> - auto` o `remediate file <file path> - auto` .</span><span class="sxs-lookup"><span data-stu-id="c8720-280">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="c8720-281">Tipi di output supportati</span><span class="sxs-lookup"><span data-stu-id="c8720-281">Supported output types</span></span>

<span data-ttu-id="c8720-282">La risposta in tempo reale supporta i tipi di output in formato JSON e tabella.</span><span class="sxs-lookup"><span data-stu-id="c8720-282">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="c8720-283">Per ogni comando esiste un comportamento di output predefinito.</span><span class="sxs-lookup"><span data-stu-id="c8720-283">For each command, there's a default output behavior.</span></span> <span data-ttu-id="c8720-284">Puoi modificare l'output nel formato di output preferito usando i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8720-284">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="c8720-285">Un numero inferiore di campi viene visualizzato in formato tabella a causa dello spazio limitato.</span><span class="sxs-lookup"><span data-stu-id="c8720-285">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="c8720-286">Per visualizzare altri dettagli nell'output, puoi usare il comando di output JSON in modo da visualizzare altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="c8720-286">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="c8720-287">Pipe di output supportate</span><span class="sxs-lookup"><span data-stu-id="c8720-287">Supported output pipes</span></span>

<span data-ttu-id="c8720-288">La risposta in tempo reale supporta l'output piping su CLI e file.</span><span class="sxs-lookup"><span data-stu-id="c8720-288">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="c8720-289">CLI è il comportamento di output predefinito.</span><span class="sxs-lookup"><span data-stu-id="c8720-289">CLI is the default output behavior.</span></span> <span data-ttu-id="c8720-290">È possibile pipeare l'output in un file utilizzando il comando seguente: [comando] > [nomefile].txt.</span><span class="sxs-lookup"><span data-stu-id="c8720-290">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="c8720-291">Esempio:</span><span class="sxs-lookup"><span data-stu-id="c8720-291">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="c8720-292">Visualizzare il log dei comandi</span><span class="sxs-lookup"><span data-stu-id="c8720-292">View the command log</span></span>

<span data-ttu-id="c8720-293">Seleziona la **scheda Registro** comandi per visualizzare i comandi usati nel dispositivo durante una sessione.</span><span class="sxs-lookup"><span data-stu-id="c8720-293">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="c8720-294">Ogni comando viene monitorato con dettagli completi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c8720-294">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="c8720-295">ID</span><span class="sxs-lookup"><span data-stu-id="c8720-295">ID</span></span>
- <span data-ttu-id="c8720-296">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="c8720-296">Command line</span></span>
- <span data-ttu-id="c8720-297">Durata</span><span class="sxs-lookup"><span data-stu-id="c8720-297">Duration</span></span>
- <span data-ttu-id="c8720-298">Barra laterale di stato e input o output</span><span class="sxs-lookup"><span data-stu-id="c8720-298">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="c8720-299">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="c8720-299">Limitations</span></span>

- <span data-ttu-id="c8720-300">Le sessioni di risposta in tempo reale sono limitate a 25 sessioni di risposta in tempo reale alla volta.</span><span class="sxs-lookup"><span data-stu-id="c8720-300">Live response sessions are limited to 25 live response sessions at a time.</span></span>
- <span data-ttu-id="c8720-301">Il valore di timeout inattiva della sessione di risposta in tempo reale è 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="c8720-301">Live response session inactive timeout value is 30 minutes.</span></span> 
- <span data-ttu-id="c8720-302">Un utente può avviare fino a 10 sessioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="c8720-302">A user can initiate up to 10 concurrent sessions.</span></span>
- <span data-ttu-id="c8720-303">Un dispositivo può essere in una sola sessione alla volta.</span><span class="sxs-lookup"><span data-stu-id="c8720-303">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="c8720-304">Si applicano i limiti di dimensione dei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8720-304">The following file size limits apply:</span></span>
   - <span data-ttu-id="c8720-305">`getfile` limite: 3 GB</span><span class="sxs-lookup"><span data-stu-id="c8720-305">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="c8720-306">`fileinfo` limite: 10 GB</span><span class="sxs-lookup"><span data-stu-id="c8720-306">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="c8720-307">`library` limite: 250 MB</span><span class="sxs-lookup"><span data-stu-id="c8720-307">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="c8720-308">Articolo correlato</span><span class="sxs-lookup"><span data-stu-id="c8720-308">Related article</span></span>
- [<span data-ttu-id="c8720-309">Esempi di comandi di Live response</span><span class="sxs-lookup"><span data-stu-id="c8720-309">Live response command examples</span></span>](live-response-command-examples.md)
