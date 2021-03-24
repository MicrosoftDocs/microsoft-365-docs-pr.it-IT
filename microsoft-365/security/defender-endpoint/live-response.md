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
ms.openlocfilehash: d992d98b916f5b59b67706b310edefdb37f157b4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062426"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="ac0c8-104">Analizzare le entità nei dispositivi che usano la risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="ac0c8-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ac0c8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ac0c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="ac0c8-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ac0c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="ac0c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac0c8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="ac0c8-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ac0c8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ac0c8-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="ac0c8-110">La risposta in tempo reale consente ai team delle operazioni di sicurezza di accedere istantaneamente a un dispositivo (noto anche come computer) utilizzando una connessione shell remota.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="ac0c8-111">In questo modo è possibile eseguire un lavoro di indagine approfondito e intraprendere azioni di risposta immediate per contenere prontamente le minacce identificate, in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="ac0c8-112">La risposta in tempo reale è progettata per migliorare le indagini consentendo al team delle operazioni di sicurezza di raccogliere dati forensi, eseguire script, inviare entità sospette per l'analisi, correggere le minacce e cercare in modo proattivo minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="ac0c8-113">Con la risposta in tempo reale, gli analisti possono eseguire tutte le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="ac0c8-114">Esegui comandi di base e avanzati per eseguire attività di indagine su un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="ac0c8-115">Scaricare file come esempi di malware e risultati degli script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="ac0c8-116">Scaricare i file in background (nuovo!).</span><span class="sxs-lookup"><span data-stu-id="ac0c8-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="ac0c8-117">Caricare uno script di PowerShell o un file eseguibile nella raccolta ed eseguirlo in un dispositivo da un livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="ac0c8-118">Eseguire o annullare azioni di correzione.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ac0c8-119">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ac0c8-119">Before you begin</span></span>

<span data-ttu-id="ac0c8-120">Prima di poter avviare una sessione su un dispositivo, assicurati di soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="ac0c8-121">**Verificare che sia in esecuzione una versione supportata di Windows**.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="ac0c8-122">I dispositivi devono eseguire una delle versioni seguenti di Windows</span><span class="sxs-lookup"><span data-stu-id="ac0c8-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="ac0c8-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="ac0c8-123">**Windows 10**</span></span>
    - <span data-ttu-id="ac0c8-124">[Versione 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) o successiva</span><span class="sxs-lookup"><span data-stu-id="ac0c8-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="ac0c8-125">[Versione 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) con [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="ac0c8-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="ac0c8-126">[Versione 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) [con KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="ac0c8-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="ac0c8-127">[Versione 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) con [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="ac0c8-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="ac0c8-128">[Versione 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) con [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="ac0c8-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="ac0c8-129">**Windows Server 2019 - Applicabile solo per l'anteprima pubblica**</span><span class="sxs-lookup"><span data-stu-id="ac0c8-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="ac0c8-130">Versione 1903 o (con [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) più avanti</span><span class="sxs-lookup"><span data-stu-id="ac0c8-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="ac0c8-131">Versione 1809 (con [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span><span class="sxs-lookup"><span data-stu-id="ac0c8-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="ac0c8-132">**Abilita risposta in tempo reale dalla pagina delle impostazioni avanzate.**</span><span class="sxs-lookup"><span data-stu-id="ac0c8-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="ac0c8-133">Dovrai abilitare la funzionalità di risposta in tempo reale nella [pagina Impostazioni funzionalità](advanced-features.md) avanzate.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="ac0c8-134">Solo gli utenti con ruoli di amministratore globale o di sicurezza possono modificare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="ac0c8-135">**Abilitare la risposta in tempo reale per i server dalla pagina delle impostazioni avanzate** (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="ac0c8-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="ac0c8-136">Solo gli utenti con ruoli di amministratore globale o di sicurezza possono modificare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="ac0c8-137">Assicurati che al dispositivo sia assegnato un livello di **correzione dell'automazione.**</span><span class="sxs-lookup"><span data-stu-id="ac0c8-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="ac0c8-138">Dovrai abilitare almeno il livello di correzione minimo per un determinato gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="ac0c8-139">In caso contrario, non sarà possibile stabilire una sessione di Risposta in tempo reale a un membro del gruppo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="ac0c8-140">Verrà visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-140">You'll receive the following error:</span></span>

    ![Immagine del messaggio di errore](images/live-response-error.png)

- <span data-ttu-id="ac0c8-142">**Abilitare l'esecuzione di script non firmati** in risposta attiva (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="ac0c8-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="ac0c8-143">Consentire l'uso di script non firmati può aumentare l'esposizione alle minacce.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="ac0c8-144">L'esecuzione di script non firmati non è consigliata perché può aumentare l'esposizione alle minacce.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="ac0c8-145">Se tuttavia è necessario utilizzarli, è necessario abilitare l'impostazione nella [pagina Impostazioni funzionalità](advanced-features.md) avanzate.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="ac0c8-146">**Assicurarsi di disporre delle autorizzazioni appropriate.**</span><span class="sxs-lookup"><span data-stu-id="ac0c8-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="ac0c8-147">Solo gli utenti di cui è stato eseguito il provisioning con le autorizzazioni appropriate possono avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="ac0c8-148">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ac0c8-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="ac0c8-149">L'opzione per caricare un file nella raccolta è disponibile solo per gli utenti con le autorizzazioni RBAC appropriate.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="ac0c8-150">Il pulsante è in grigio per gli utenti con solo autorizzazioni delegate.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="ac0c8-151">A seconda del ruolo che ti è stato concesso, puoi eseguire comandi di risposta in tempo reale di base o avanzati.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="ac0c8-152">Le autorizzazioni degli utenti sono controllate dal ruolo personalizzato RBAC.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="ac0c8-153">Panoramica del dashboard di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="ac0c8-153">Live response dashboard overview</span></span>
<span data-ttu-id="ac0c8-154">Quando avvii una sessione di risposta in tempo reale su un dispositivo, viene aperto un dashboard.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="ac0c8-155">Il dashboard fornisce informazioni sulla sessione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="ac0c8-156">Chi ha creato la sessione</span><span class="sxs-lookup"><span data-stu-id="ac0c8-156">Who created the session</span></span>
- <span data-ttu-id="ac0c8-157">All'avvio della sessione</span><span class="sxs-lookup"><span data-stu-id="ac0c8-157">When the session started</span></span>
- <span data-ttu-id="ac0c8-158">Durata della sessione</span><span class="sxs-lookup"><span data-stu-id="ac0c8-158">The duration of the session</span></span>

<span data-ttu-id="ac0c8-159">Il dashboard consente inoltre di accedere a:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="ac0c8-160">Disconnetti sessione</span><span class="sxs-lookup"><span data-stu-id="ac0c8-160">Disconnect session</span></span>
- <span data-ttu-id="ac0c8-161">Caricare file nella raccolta</span><span class="sxs-lookup"><span data-stu-id="ac0c8-161">Upload files to the library</span></span> 
- <span data-ttu-id="ac0c8-162">Console dei comandi</span><span class="sxs-lookup"><span data-stu-id="ac0c8-162">Command console</span></span>
- <span data-ttu-id="ac0c8-163">Log dei comandi</span><span class="sxs-lookup"><span data-stu-id="ac0c8-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="ac0c8-164">Avviare una sessione di risposta in tempo reale in un dispositivo</span><span class="sxs-lookup"><span data-stu-id="ac0c8-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="ac0c8-165">Accedi a Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="ac0c8-166">Passa alla pagina dell'elenco dei dispositivi e seleziona un dispositivo da analizzare.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="ac0c8-167">Viene visualizzata la pagina dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-167">The devices page opens.</span></span>

3. <span data-ttu-id="ac0c8-168">Avviare la sessione di risposta in tempo reale selezionando **Avvia sessione di risposta in tempo reale.**</span><span class="sxs-lookup"><span data-stu-id="ac0c8-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="ac0c8-169">Viene visualizzata una console dei comandi.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-169">A command console is displayed.</span></span> <span data-ttu-id="ac0c8-170">Attendere che la sessione si connetta al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="ac0c8-171">Usa i comandi predefiniti per eseguire attività di indagine.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="ac0c8-172">Per ulteriori informazioni, vedere [Comandi di risposta in tempo reale.](#live-response-commands)</span><span class="sxs-lookup"><span data-stu-id="ac0c8-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="ac0c8-173">Dopo aver completato l'indagine, selezionare **Disconnetti sessione** e **quindi** Conferma.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="ac0c8-174">Comandi di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="ac0c8-174">Live response commands</span></span>

<span data-ttu-id="ac0c8-175">A seconda del ruolo che ti è stato concesso, puoi eseguire comandi di risposta in tempo reale di base o avanzati.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="ac0c8-176">Le autorizzazioni utente sono controllate dai ruoli personalizzati RBAC.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="ac0c8-177">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ac0c8-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="ac0c8-178">La risposta in tempo reale è una shell interattiva basata sul cloud, in quanto tale, l'esperienza di comando specifica può variare in base alla qualità della rete e al carico di sistema tra l'utente finale e il dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="ac0c8-179">Comandi di base</span><span class="sxs-lookup"><span data-stu-id="ac0c8-179">Basic commands</span></span>

<span data-ttu-id="ac0c8-180">I comandi seguenti sono disponibili per i ruoli utente a cui viene concessa la possibilità di eseguire comandi **di risposta** in tempo reale di base.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="ac0c8-181">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ac0c8-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="ac0c8-182">Comando</span><span class="sxs-lookup"><span data-stu-id="ac0c8-182">Command</span></span> | <span data-ttu-id="ac0c8-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac0c8-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="ac0c8-184">Modifica la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="ac0c8-185">Cancella la schermata della console.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="ac0c8-186">Avvia una sessione di risposta in tempo reale al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="ac0c8-187">Mostra tutte le connessioni attive.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="ac0c8-188">Visualizza un elenco di file e sottodirectory in una directory.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`download <file_path> &` | <span data-ttu-id="ac0c8-189">Scarica un file in background.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-189">Downloads a file in the background.</span></span> |
<span data-ttu-id="ac0c8-190">driver</span><span class="sxs-lookup"><span data-stu-id="ac0c8-190">drivers</span></span> |  <span data-ttu-id="ac0c8-191">Mostra tutti i driver installati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-191">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="ac0c8-192">Restituisce un download di file in primo piano.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-192">Returns a file download to the foreground.</span></span> |
|`fileinfo` | <span data-ttu-id="ac0c8-193">Ottenere informazioni su un file.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-193">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="ac0c8-194">Individua i file con un nome specificato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-194">Locates files by a given name on the device.</span></span> |
|`help` | <span data-ttu-id="ac0c8-195">Fornisce informazioni della Guida per i comandi di risposta in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-195">Provides help information for live response commands.</span></span> |
|`persistence` | <span data-ttu-id="ac0c8-196">Mostra tutti i metodi di persistenza noti nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-196">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="ac0c8-197">Mostra tutti i processi in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-197">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="ac0c8-198">Mostra i valori del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-198">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="ac0c8-199">Mostra tutte le attività pianificate nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-199">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="ac0c8-200">Mostra tutti i servizi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-200">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="ac0c8-201">Imposta la modalità di registrazione del terminale per il debug.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-201">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="ac0c8-202">Comandi avanzati</span><span class="sxs-lookup"><span data-stu-id="ac0c8-202">Advanced commands</span></span>
<span data-ttu-id="ac0c8-203">I comandi seguenti sono disponibili per i ruoli utente a cui viene concessa la possibilità di eseguire **comandi di** risposta in tempo reale avanzati.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-203">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="ac0c8-204">Per ulteriori informazioni sulle assegnazioni di ruolo, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ac0c8-204">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="ac0c8-205">Comando</span><span class="sxs-lookup"><span data-stu-id="ac0c8-205">Command</span></span> | <span data-ttu-id="ac0c8-206">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac0c8-206">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="ac0c8-207">Analizza l'entità con vari motori di incriminazione per raggiungere un verdetto.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-207">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `getfile` | <span data-ttu-id="ac0c8-208">Ottiene un file dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-208">Gets a file from the device.</span></span> <br> <span data-ttu-id="ac0c8-209">NOTA: questo comando ha un comando prerequisito.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-209">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="ac0c8-210">È possibile utilizzare il `-auto` comando insieme a per eseguire `getfile` automaticamente il comando prerequisito.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-210">You can use the `-auto` command in conjunction with `getfile` to automatically run the prerequisite command.</span></span> |
| `run` | <span data-ttu-id="ac0c8-211">Esegue uno script di PowerShell dalla raccolta nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-211">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="ac0c8-212">Elenca i file caricati nella raccolta di risposte in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-212">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="ac0c8-213">Inserisce un file dalla raccolta al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-213">Puts a file from the library to the device.</span></span> <span data-ttu-id="ac0c8-214">I file vengono salvati in una cartella di lavoro e vengono eliminati al riavvio del dispositivo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-214">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="ac0c8-215">Correzione di un'entità nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-215">Remediates an entity on the device.</span></span> <span data-ttu-id="ac0c8-216">L'azione di correzione varia a seconda del tipo di entità:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-216">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="ac0c8-217">- File: delete</span><span class="sxs-lookup"><span data-stu-id="ac0c8-217">- File: delete</span></span><br><span data-ttu-id="ac0c8-218">- Processo: arrestare, eliminare il file di immagine</span><span class="sxs-lookup"><span data-stu-id="ac0c8-218">- Process: stop, delete image file</span></span><br><span data-ttu-id="ac0c8-219">- Servizio: arrestare, eliminare il file di immagine</span><span class="sxs-lookup"><span data-stu-id="ac0c8-219">- Service: stop, delete image file</span></span><br><span data-ttu-id="ac0c8-220">- Voce del Registro di sistema: delete</span><span class="sxs-lookup"><span data-stu-id="ac0c8-220">- Registry entry: delete</span></span><br><span data-ttu-id="ac0c8-221">- Attività pianificata: rimuovere</span><span class="sxs-lookup"><span data-stu-id="ac0c8-221">- Scheduled task: remove</span></span><br><span data-ttu-id="ac0c8-222">- Elemento cartella di avvio: elimina file</span><span class="sxs-lookup"><span data-stu-id="ac0c8-222">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="ac0c8-223">NOTA: questo comando ha un comando prerequisito.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-223">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="ac0c8-224">È possibile utilizzare il `-auto` comando insieme a per eseguire `remediate` automaticamente il comando prerequisito.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-224">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="ac0c8-225">Ripristina un'entità che è stata corretti.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-225">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="ac0c8-226">Usare i comandi di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="ac0c8-226">Use live response commands</span></span>

<span data-ttu-id="ac0c8-227">I comandi che puoi usare nella console seguono principi simili a quelli dei [comandi di Windows.](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c)</span><span class="sxs-lookup"><span data-stu-id="ac0c8-227">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="ac0c8-228">I comandi avanzati offrono un set più affidabile di azioni che consentono di eseguire azioni più efficaci, ad esempio scaricare e caricare un file, eseguire script nel dispositivo ed eseguire azioni di correzione su un'entità.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-228">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="ac0c8-229">Ottenere un file dal dispositivo</span><span class="sxs-lookup"><span data-stu-id="ac0c8-229">Get a file from the device</span></span>

<span data-ttu-id="ac0c8-230">Per gli scenari in cui vuoi ottenere un file da un dispositivo che stai analizzando, puoi usare il `getfile` comando.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-230">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="ac0c8-231">In questo modo è possibile salvare il file dal dispositivo per ulteriori indagini.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-231">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="ac0c8-232">Si applicano i limiti di dimensione dei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-232">The following file size limits apply:</span></span>
>- <span data-ttu-id="ac0c8-233">`getfile` limite: 3 GB</span><span class="sxs-lookup"><span data-stu-id="ac0c8-233">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="ac0c8-234">`fileinfo` limite: 10 GB</span><span class="sxs-lookup"><span data-stu-id="ac0c8-234">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="ac0c8-235">`library` limite: 250 MB</span><span class="sxs-lookup"><span data-stu-id="ac0c8-235">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="ac0c8-236">Scaricare un file in background</span><span class="sxs-lookup"><span data-stu-id="ac0c8-236">Download a file in the background</span></span>

<span data-ttu-id="ac0c8-237">Per consentire al team delle operazioni di sicurezza di continuare a analizzare un dispositivo a impatto, i file possono ora essere scaricati in background.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-237">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="ac0c8-238">Per scaricare un file in background, nella console dei comandi di risposta in tempo reale digitare `download <file_path> &` .</span><span class="sxs-lookup"><span data-stu-id="ac0c8-238">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="ac0c8-239">Se si è in attesa del download di un file, è possibile spostarlo in background utilizzando Ctrl + Z.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-239">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="ac0c8-240">Per portare in primo piano il download di un file, nella console dei comandi di risposta in tempo reale digitare `fg <command_id>` .</span><span class="sxs-lookup"><span data-stu-id="ac0c8-240">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="ac0c8-241">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-241">Here are some examples:</span></span>


|<span data-ttu-id="ac0c8-242">Comando</span><span class="sxs-lookup"><span data-stu-id="ac0c8-242">Command</span></span>  |<span data-ttu-id="ac0c8-243">Funzione</span><span class="sxs-lookup"><span data-stu-id="ac0c8-243">What it does</span></span>  |
|---------|---------|
|`Download "C:\windows\some_file.exe" &`     |<span data-ttu-id="ac0c8-244">Avvia il download di un file *denominatosome_file.exe* in background.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-244">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="ac0c8-245">Restituisce un download con ID comando *1234* in primo piano.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-245">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="ac0c8-246">Inserire un file nella raccolta</span><span class="sxs-lookup"><span data-stu-id="ac0c8-246">Put a file in the library</span></span>

<span data-ttu-id="ac0c8-247">La risposta in tempo reale include una raccolta in cui è possibile inserire i file.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-247">Live response has a library where you can put files into.</span></span> <span data-ttu-id="ac0c8-248">La raccolta archivia i file,ad esempio gli script, che possono essere eseguiti in una sessione di risposta in tempo reale a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-248">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="ac0c8-249">La risposta in tempo reale consente l'esecuzione degli script di PowerShell, tuttavia è necessario innanzitutto inserire i file nella raccolta prima di poterli eseguire.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-249">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="ac0c8-250">Puoi avere una raccolta di script di PowerShell che possono essere eseguiti nei dispositivi con cui avvii sessioni di risposta in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-250">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="ac0c8-251">Per caricare un file nella raccolta</span><span class="sxs-lookup"><span data-stu-id="ac0c8-251">To upload a file in the library</span></span>

1. <span data-ttu-id="ac0c8-252">Fare **clic su Carica file nella raccolta.**</span><span class="sxs-lookup"><span data-stu-id="ac0c8-252">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="ac0c8-253">Fare **clic su** Sfoglia e selezionare il file.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-253">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="ac0c8-254">Fornire una breve descrizione.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-254">Provide a brief description.</span></span>

4. <span data-ttu-id="ac0c8-255">Specificare se si desidera sovrascrivere un file con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-255">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="ac0c8-256">Se si desidera, sapere quali parametri sono necessari per lo script, selezionare la casella di controllo Parametri script.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-256">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="ac0c8-257">Nel campo di testo immettere un esempio e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-257">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="ac0c8-258">Fare clic **su Conferma**.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-258">Click **Confirm**.</span></span> 

7. <span data-ttu-id="ac0c8-259">(Facoltativo) Per verificare che il file sia stato caricato nella raccolta, eseguire il `library` comando.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-259">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="ac0c8-260">Annullare un comando</span><span class="sxs-lookup"><span data-stu-id="ac0c8-260">Cancel a command</span></span>
<span data-ttu-id="ac0c8-261">In qualsiasi momento durante una sessione, è possibile annullare un comando premendo CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-261">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="ac0c8-262">L'utilizzo di questo collegamento non arresterà il comando sul lato agente.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-262">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="ac0c8-263">Il comando verrà annullato solo nel portale.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-263">It will only cancel the command in the portal.</span></span> <span data-ttu-id="ac0c8-264">Pertanto, le operazioni di modifica come "correzione" potrebbero continuare, mentre il comando viene annullato.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-264">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

### <a name="automatically-run-prerequisite-commands"></a><span data-ttu-id="ac0c8-265">Eseguire automaticamente i comandi dei prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ac0c8-265">Automatically run prerequisite commands</span></span>

<span data-ttu-id="ac0c8-266">Alcuni comandi dispongono di comandi prerequisiti da eseguire.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-266">Some commands have prerequisite commands to run.</span></span> <span data-ttu-id="ac0c8-267">Se non si esegue il comando prerequisito, verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-267">If you don't run the prerequisite command, you'll get an error.</span></span> <span data-ttu-id="ac0c8-268">Ad esempio, `download` l'esecuzione del comando senza `fileinfo` restituirà un errore.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-268">For example, running the `download` command without `fileinfo` will return an error.</span></span>

<span data-ttu-id="ac0c8-269">È possibile utilizzare il flag auto per eseguire automaticamente i comandi dei prerequisiti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-269">You can use the auto flag to automatically run prerequisite commands, for example:</span></span>

```console
getfile c:\Users\user\Desktop\work.txt -auto
```

## <a name="run-a-powershell-script"></a><span data-ttu-id="ac0c8-270">Eseguire uno script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac0c8-270">Run a PowerShell script</span></span> 

<span data-ttu-id="ac0c8-271">Prima di poter eseguire uno script di PowerShell, è necessario caricarlo nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-271">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="ac0c8-272">Dopo aver caricato lo script nella raccolta, utilizzare il `run` comando per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-272">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="ac0c8-273">Se si prevede di utilizzare uno script non firmato nella sessione, sarà necessario abilitare l'impostazione nella [pagina Impostazioni funzionalità](advanced-features.md) avanzate.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-273">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="ac0c8-274">Consentire l'uso di script non firmati può aumentare l'esposizione alle minacce.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-274">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="ac0c8-275">Applicare parametri di comando</span><span class="sxs-lookup"><span data-stu-id="ac0c8-275">Apply command parameters</span></span>

- <span data-ttu-id="ac0c8-276">Visualizzare la Guida della console per informazioni sui parametri del comando.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-276">View the console help to learn about command parameters.</span></span> <span data-ttu-id="ac0c8-277">Per informazioni su un singolo comando, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-277">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="ac0c8-278">Quando si applicano parametri ai comandi, tenere presente che i parametri vengono gestiti in base a un ordine fisso:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-278">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="ac0c8-279">Quando si specificano parametri al di fuori dell'ordine fisso, specificare il nome del parametro con un trattino prima di specificare il valore:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-279">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="ac0c8-280">Quando si utilizzano comandi che dispongono di comandi prerequisiti, è possibile utilizzare i flag:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-280">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="ac0c8-281">`<command name> -type file -id <file path> - auto` o `remediate file <file path> - auto` .</span><span class="sxs-lookup"><span data-stu-id="ac0c8-281">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="ac0c8-282">Tipi di output supportati</span><span class="sxs-lookup"><span data-stu-id="ac0c8-282">Supported output types</span></span>

<span data-ttu-id="ac0c8-283">La risposta in tempo reale supporta i tipi di output in formato JSON e tabella.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-283">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="ac0c8-284">Per ogni comando esiste un comportamento di output predefinito.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-284">For each command, there's a default output behavior.</span></span> <span data-ttu-id="ac0c8-285">Puoi modificare l'output nel formato di output preferito usando i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-285">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="ac0c8-286">Un numero inferiore di campi viene visualizzato in formato tabella a causa dello spazio limitato.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-286">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="ac0c8-287">Per visualizzare altri dettagli nell'output, puoi usare il comando di output JSON in modo da visualizzare altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-287">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="ac0c8-288">Pipe di output supportate</span><span class="sxs-lookup"><span data-stu-id="ac0c8-288">Supported output pipes</span></span>

<span data-ttu-id="ac0c8-289">La risposta in tempo reale supporta l'output piping su CLI e file.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-289">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="ac0c8-290">CLI è il comportamento di output predefinito.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-290">CLI is the default output behavior.</span></span> <span data-ttu-id="ac0c8-291">È possibile pipeare l'output in un file utilizzando il comando seguente: [comando] > [nomefile].txt.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-291">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="ac0c8-292">Esempio:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-292">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="ac0c8-293">Visualizzare il log dei comandi</span><span class="sxs-lookup"><span data-stu-id="ac0c8-293">View the command log</span></span>

<span data-ttu-id="ac0c8-294">Seleziona la **scheda Registro** comandi per visualizzare i comandi usati nel dispositivo durante una sessione.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-294">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="ac0c8-295">Ogni comando viene monitorato con dettagli completi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-295">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="ac0c8-296">ID</span><span class="sxs-lookup"><span data-stu-id="ac0c8-296">ID</span></span>
- <span data-ttu-id="ac0c8-297">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="ac0c8-297">Command line</span></span>
- <span data-ttu-id="ac0c8-298">Durata</span><span class="sxs-lookup"><span data-stu-id="ac0c8-298">Duration</span></span>
- <span data-ttu-id="ac0c8-299">Barra laterale di stato e input o output</span><span class="sxs-lookup"><span data-stu-id="ac0c8-299">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="ac0c8-300">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="ac0c8-300">Limitations</span></span>

- <span data-ttu-id="ac0c8-301">Le sessioni di risposta in tempo reale sono limitate a 10 sessioni di risposta in tempo reale alla volta.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-301">Live response sessions are limited to 10 live response sessions at a time.</span></span>
- <span data-ttu-id="ac0c8-302">L'esecuzione di comandi su larga scala non è supportata.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-302">Large-scale command execution is not supported.</span></span>
- <span data-ttu-id="ac0c8-303">Il valore di timeout inattivo della sessione di risposta in tempo reale è 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-303">Live response session inactive timeout value is 5 minutes.</span></span> 
- <span data-ttu-id="ac0c8-304">Un utente può avviare una sola sessione alla volta.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-304">A user can only initiate one session at a time.</span></span>
- <span data-ttu-id="ac0c8-305">Un dispositivo può essere in una sola sessione alla volta.</span><span class="sxs-lookup"><span data-stu-id="ac0c8-305">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="ac0c8-306">Si applicano i limiti di dimensione dei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac0c8-306">The following file size limits apply:</span></span>
   - <span data-ttu-id="ac0c8-307">`getfile` limite: 3 GB</span><span class="sxs-lookup"><span data-stu-id="ac0c8-307">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="ac0c8-308">`fileinfo` limite: 10 GB</span><span class="sxs-lookup"><span data-stu-id="ac0c8-308">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="ac0c8-309">`library` limite: 250 MB</span><span class="sxs-lookup"><span data-stu-id="ac0c8-309">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="ac0c8-310">Articolo correlato</span><span class="sxs-lookup"><span data-stu-id="ac0c8-310">Related article</span></span>
- [<span data-ttu-id="ac0c8-311">Esempi di comandi di risposta in tempo reale</span><span class="sxs-lookup"><span data-stu-id="ac0c8-311">Live response command examples</span></span>](live-response-command-examples.md)
